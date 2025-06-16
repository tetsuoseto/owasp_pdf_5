# 9 Autonomní orchestrace a agentické zabezpečení akcí

## Cíl kontroly

Zajistěte, aby autonomní nebo multiagentní systémy umělé inteligence mohly vykonávat pouze akce, které jsou explicitně zamýšlené, autentizované, auditovatelné a v rámci stanovených hranic nákladů a rizik. Tím se chrání před hrozbami, jako je kompromitace autonomního systému, zneužití nástrojů, detekce agentních smyček, únos komunikace, falšování identity, manipulace s rojovými systémy a manipulace s úmysly.

---

## 9.1 Agentní plánování úkolů a rozpočty rekurze

Omezujte rekurzivní plány a vyžadujte lidské kontroly pro privilegované akce.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Ověřte, že maximální hloubka rekurze, šířka, skutečný čas, tokeny a finanční náklady na každý běh agenta jsou centrálně konfigurovány a verzovány.                                 |   1   | D/V  |
| 9.1.2 | Ověřte, že privilegované nebo nezvratné akce (např. potvrzení kódu, finanční převody) vyžadují před provedením explicitní lidské schválení prostřednictvím auditovatelného kanálu. |   1   | D/V  |
| 9.1.3 | Ověřte, že monitory prostředků v reálném čase vyvolají přerušení obvodového jističe, když je překročena jakákoli hranice rozpočtu, čímž zastaví další rozšiřování úloh.            |   2   |  D   |
| 9.1.4 | Ověřte, že události vypínače jsou zaznamenávány s ID agenta, spouštěcí podmínkou a zachyceným stavem plánu pro forenzní přezkum.                                                   |   2   | D/V  |
| 9.1.5 | Ověřte, že bezpečnostní testy pokrývají scénáře vyčerpání rozpočtu a nekontrolovaného plánu, a potvrďte bezpečné zastavení bez ztráty dat.                                         |   3   |  V   |
| 9.1.6 | Ověřte, že rozpočtové politiky jsou vyjádřeny jako politika-v-kódu a vynucovány v CI/CD za účelem zablokování odchylek v konfiguraci.                                              |   3   |  D   |

---

## 9.2 Izolace pluginů nástrojů (sandboxing)

Izolujte interakce s nástroji, aby se zabránilo neoprávněnému přístupu k systému nebo spuštění kódu.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Ověřte, že každý nástroj/plugin běží uvnitř operačního systému, kontejneru nebo sandboxu na úrovni WASM s politikami souborového systému, sítě a systémových volání s nejmenšími oprávněními. |   1   | D/V  |
| 9.2.2 | Ověřte, že limity zdrojů sandboxu (CPU, paměť, disk, výstupní síťový provoz) a časové limity vykonávání jsou vynuceny a zaznamenávány.                                                        |   1   | D/V  |
| 9.2.3 | Ověřte, že binární soubory nebo deskriptory nástrojů jsou digitálně podepsané; podpisy jsou ověřovány před načtením.                                                                          |   2   | D/V  |
| 9.2.4 | Ověřte, že telemetrie sandboxu se přenáší do SIEM; anomálie (např. pokusy o odchozí připojení) vyvolávají upozornění.                                                                         |   2   |  V   |
| 9.2.5 | Ověřte, že vysokorizikové pluginy procházejí bezpečnostní kontrolou a penetračním testováním před nasazením do produkce.                                                                      |   3   |  V   |
| 9.2.6 | Ověřte, že pokusy o únik z pískoviště jsou automaticky blokovány a postižený plugin je umístěn do karantény do doby vyšetření.                                                                |   3   | D/V  |

---

## 9.3 Autonomní smyčka a omezení nákladů

Detekujte a zastavte nekontrolovanou rekurzi mezi agenty a výbuchy nákladů.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Ověřte, že volání mezi agenty zahrnují omezení počtu přeskoků (hop-limit) nebo TTL, které běhové prostředí snižuje a vynucuje.                      |   1   | D/V  |
| 9.3.2 | Ověřte, že agenti udržují jedinečné ID grafu vyvolání, aby bylo možné rozpoznat samovolné vyvolání nebo cyklické vzory.                             |   2   |  D   |
| 9.3.3 | Ověřte, že kumulativní čítače výpočetních jednotek a výdajů jsou sledovány pro každý řetězec požadavků; překročení limitu vede k přerušení řetězce. |   2   | D/V  |
| 9.3.4 | Ověřte, že formální analýza nebo model checking prokazuje nepřítomnost neomezené rekurze v protokolech agentů.                                      |   3   |  V   |
| 9.3.5 | Ověřte, že události přerušení smyčky generují upozornění a poskytují metriky pro nepřetržité zlepšování.                                            |   3   |  D   |

---

## 9.4 Ochrana proti zneužití na úrovni protokolu

Zabezpečit komunikační kanály mezi agenty a externími systémy, aby se zabránilo převzetí kontroly nebo manipulaci.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.4.1 | Ověřte, že všechny zprávy mezi agentem a nástrojem i mezi agenty jsou autentizovány (například pomocí vzájemného TLS nebo JWT) a šifrovány end-to-end. |   1   | D/V  |
| 9.4.2 | Ověřte, že jsou schémata přísně validována; neznámá pole nebo chybně formátované zprávy jsou zamítány.                                                 |   1   |  D   |
| 9.4.3 | Ověřte, že kontrolní integrity (MAC nebo digitální podpisy) pokrývají celé tělo zprávy včetně parametrů nástroje.                                      |   2   | D/V  |
| 9.4.4 | Ověřte, že ochrana proti přehrání (nonce nebo časová okna) je vynucena na úrovni protokolu.                                                            |   2   |  D   |
| 9.4.5 | Ověřte, že implementace protokolů jsou podrobeny fuzzingu a statické analýze kvůli zranitelnostem typu injekce nebo deserializace.                     |   3   |  V   |

---

## 9.5 Identita agenta a důkaz zásahu

Zajistěte, aby byly akce přiřaditelné a úpravy detekovatelné.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Ověřte, že každá instance agenta má unikátní kryptografickou identitu (klíčový pár nebo hardwarově založený oprávnění).                 |   1   | D/V  |
| 9.5.2 | Ověřte, že všechny akce agentů jsou podepsané a opatřené časovou značkou; protokoly zahrnují podpis pro zabránění popření odpovědnosti. |   2   | D/V  |
| 9.5.3 | Ověřte, že záznamy s důkazem proti neoprávněným změnám jsou ukládány v médiu pouze pro připojování nebo zápis jednou.                   |   2   |  V   |
| 9.5.4 | Ověřte, že klíče identity se mění podle stanoveného plánu a při indikátorech kompromitace.                                              |   3   |  D   |
| 9.5.5 | Ověřte, že pokusy o podvržení identity nebo konflikty klíčů okamžitě vyvolají karanténu postiženého agenta.                             |   3   | D/V  |

---

## 9.6 Snížení rizik při použití víceagentových rojů

Zmírnit rizika související s kolektivním chováním prostřednictvím izolace a formálního modelování bezpečnosti.

|   #   | Description                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Ověřte, že agenti pracující v různých bezpečnostních doménách běží v izolovaných runtime pískovištích nebo síťových segmentech.           |   1   | D/V  |
| 9.6.2 | Ověřte, že chování swarmu je modelováno a formálně ověřeno z hlediska živosti a bezpečnosti před nasazením.                               |   3   |  V   |
| 9.6.3 | Ověřte, že monitorovací nástroje za běhu detekují vznikající nebezpečné vzory (např. oscilace, zablokování) a iniciují nápravná opatření. |   3   |  D   |

---

## 9.7 Autentizace / autorizace uživatelů a nástrojů

Implementujte robustní kontrolu přístupu pro každou akci spuštěnou agentem.

|   #   | Description                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Ověřte, že agenti se autentizují jako hlavní subjekty prvního řádu do následných systémů a nikdy znovu nepoužívají přihlašovací údaje koncových uživatelů. |   1   | D/V  |
| 9.7.2 | Ověřte, že detailní politiky autorizace omezují, které nástroje může agent vyvolat a jaké parametry může zadat.                                            |   2   |  D   |
| 9.7.3 | Ověřte, že kontroly oprávnění jsou znovu vyhodnocovány při každém volání (kontinuální autorizace), nikoli pouze na začátku relace.                         |   2   |  V   |
| 9.7.4 | Ověřte, že delegovaná oprávnění automaticky vyprší a po uplynutí časového limitu nebo změně rozsahu vyžadují nový souhlas.                                 |   3   |  D   |

---

## 9.8 Bezpečnost komunikace mezi agenty

Šifrujte a zajistěte integritu všech meziagentových zpráv, aby se zabránilo odposlouchávání a manipulaci.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Ověřte, že vzájemná autentizace a šifrování s dokonalým tajemstvím vpřed (např. TLS 1.3) jsou pro kanály agentů povinné.                     |   1   | D/V  |
| 9.8.2 | Ověřte, že integrita zprávy a její původ jsou ověřeny před zpracováním; v případě neúspěchu se generují upozornění a zpráva je zahozená.     |   1   |  D   |
| 9.8.3 | Ověřte, že jsou zaznamenávány metadata komunikace (časová razítka, pořadová čísla) na podporu forenzní rekonstrukce.                         |   2   | D/V  |
| 9.8.4 | Ověřte, že formální verifikace nebo modelové ověřování potvrzují, že stavové automaty protokolu nemohou být přivedeny do nebezpečných stavů. |   3   |  V   |

---

## 9.9 Ověření záměru a vynucení omezení

Ověřte, že akce agenta odpovídají uvedenému záměru uživatele a systémovým omezením.

|   #   | Description                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Ověřte, že předběžné řešiče omezení kontrolují navrhované akce podle pevně zakódovaných pravidel bezpečnosti a politiky.                                                      |   1   |  D   |
| 9.9.2 | Ověřte, že akce s vysokým dopadem (finanční, destruktivní, citlivé na soukromí) vyžadují výslovné potvrzení úmyslu od uživatele, který je iniciuje.                           |   2   | D/V  |
| 9.9.3 | Ověřte, že kontroly post-podmínek validují, že dokončené akce dosáhly zamýšlených efektů bez vedlejších účinků; nesrovnalosti vyvolají návrat k předchozímu stavu (rollback). |   2   |  V   |
| 9.9.4 | Ověřte, že formální metody (např. kontrola modelu, dokazování vět) nebo testy založené na vlastnostech prokazují, že plány agentů splňují všechny deklarované omezení.        |   3   |  V   |
| 9.9.5 | Ověřte, že incidenty s nesouladem záměrů nebo porušením omezení jsou zahrnuty do cyklů kontinuálního zlepšování a sdílení hrozebných informací.                               |   3   |  D   |

---

## 9.10 Strategie zabezpečení agentního uvažování

Bezpečný výběr a provádění různých strategií uvažování, včetně přístupů ReAct, Chain-of-Thought a Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Ověřte, že výběr strategie uvažování používá deterministická kritéria (složitost vstupu, typ úkolu, bezpečnostní kontext) a že identické vstupy produkují identické výběry strategie ve stejném bezpečnostním kontextu.             |   1   | D/V  |
| 9.10.2 | Ověřte, že každá strategie uvažování (ReAct, Chain-of-Thought, Tree-of-Thoughts) má vyhrazenou kontrolu vstupu, sanitaci výstupu a časové limity vykonávání specifické pro svůj kognitivní přístup.                                 |   1   | D/V  |
| 9.10.3 | Ověřte, že přechody strategií uvažování jsou zaznamenávány s kompletním kontextem včetně charakteristik vstupu, hodnot kritérií výběru a metadat provádění pro rekonstrukci auditu.                                                 |   2   | D/V  |
| 9.10.4 | Ověřte, že uvažování pomocí Stromu myšlenek zahrnuje mechanismy pro ořezávání větví, které ukončují průzkum při detekci porušení pravidel, limitů zdrojů nebo bezpečnostních hranic.                                                |   2   | D/V  |
| 9.10.5 | Ověřte, že cykly ReAct (Reason-Act-Observe) zahrnují validační kontrolní body v každé fázi: ověření kroku uvažování, autorizaci akce a sanitaci pozorování před pokračováním.                                                       |   2   | D/V  |
| 9.10.6 | Ověřte, že jsou metriky výkonu strategie uvažování (doba vykonání, využití zdrojů, kvalita výstupu) sledovány s automatizovanými upozorněními, pokud metriky překročí nastavené prahové hodnoty.                                    |   3   | D/V  |
| 9.10.7 | Ověřte, že hybridní přístupy k roz reasoning, které kombinují více strategií, zachovávají validaci vstupů a omezení výstupů všech součástí strategií, aniž by obcházely jakékoli bezpečnostní kontroly.                             |   3   | D/V  |
| 9.10.8 | Ověřte, že testování bezpečnosti strategického uvažování zahrnuje fuzzing s nesprávně formátovanými vstupy, nepřátelské výzvy navržené k vynucení přepínání strategie a testování hraničních podmínek pro každý kognitivní přístup. |   3   | D/V  |

---

## 9.11 Správa stavu životního cyklu agenta a bezpečnost

Zabezpečená inicializace agenta, přechody stavů a ukončení s kryptografickými auditními trasami a definovanými postupy obnovy.

|   #    | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Ověřte, že inicializace agenta zahrnuje vytvoření kryptografické identity s hardwarově zálohovanými pověřeními a nezměnitelnými auditními logy spuštění obsahujícími ID agenta, časové razítko, hash konfigurace a parametry inicializace.                                       |   1   | D/V  |
| 9.11.2 | Ověřte, že přechody stavů agenta jsou kryptograficky podepsány, časově označeny a zaznamenány s kompletním kontextem včetně spouštěcích událostí, hashe předchozího stavu, hashe nového stavu a provedených bezpečnostních validací.                                             |   2   | D/V  |
| 9.11.3 | Ověřte, že postupy vypnutí agenta zahrnují bezpečné vymazání paměti pomocí kryptografického vymazání nebo vícenásobného přepisování, zrušení oprávnění s oznámením autoritě certifikátů a generování terminálních certifikátů odolných proti manipulaci.                         |   2   | D/V  |
| 9.11.4 | Ověřte, že mechanismy obnovy agenta validují integritu stavu pomocí kryptografických kontrolních součtů (minimálně SHA-256) a provádějí návrat k známým správným stavům při detekci poškození, přičemž jsou použita automatizovaná upozornění a požadavky na manuální schválení. |   3   | D/V  |
| 9.11.5 | Ověřte, že mechanismy perzistence agenta šifrují citlivá stavová data pomocí AES-256 klíčů na agentovi a implementují bezpečný rotaci klíčů podle konfigurovatelných plánů (maximálně 90 dní) s nasazením bez výpadků.                                                           |   3   | D/V  |

---

## 9.12 Rámec zabezpečení integrace nástrojů

Bezpečnostní kontroly pro dynamické načítání nástrojů, jejich spouštění a ověřování výsledků s definovanými procesy hodnocení rizik a schvalování.

|   #    | Description                                                                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Ověřte, že popisy nástrojů obsahují bezpečnostní metadata specifikující požadovaná oprávnění (čtení/zápis/spuštění), úrovně rizika (nízká/střední/vysoká), limity zdrojů (CPU, paměť, síť) a požadavky na validaci zdokumentované v manifestech nástrojů.         |   1   | D/V  |
| 9.12.2 | Ověřte, že výsledky spuštění nástroje jsou validovány vůči očekávaným schématům (JSON Schema, XML Schema) a bezpečnostním politikám (čištění výstupu, klasifikace dat) před jejich integrací, s omezením časového limitu a postupy pro zpracování chyb.           |   1   | D/V  |
| 9.12.3 | Ověřte, že záznamy interakcí s nástrojem obsahují podrobný bezpečnostní kontext včetně využití oprávnění, vzorců přístupu k datům, doby provádění, spotřeby zdrojů a návratových kódů se strukturovaným logováním pro integraci se SIEM.                          |   2   | D/V  |
| 9.12.4 | Ověřte, že mechanismy dynamického načítání nástrojů ověřují digitální podpisy pomocí infrastruktury PKI a implementují bezpečné protokoly načítání s izolací v pískovišti a ověřováním oprávnění před spuštěním.                                                  |   2   | D/V  |
| 9.12.5 | Ověřte, že bezpečnostní hodnocení nástrojů jsou automaticky spuštěna pro nové verze s povinnými schvalovacími branami, zahrnujícími statickou analýzu, dynamické testování a přezkum bezpečnostním týmem s dokumentovanými kritérii schválení a požadavky na SLA. |   3   | D/V  |

---

### Reference

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

