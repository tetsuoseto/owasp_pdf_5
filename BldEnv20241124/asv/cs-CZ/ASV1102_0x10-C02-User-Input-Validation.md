# C2 Validace vstupu uživatele

## Řídicí cíl

Robustní validace uživatelského vstupu je první linií obrany proti některým z nejničivějších útoků na AI systémy. Útoky založené na injektáži promptů mohou přepsat systémové instrukce, zpřístupnit citlivá data nebo nasměrovat model k nežádoucímu chování. Pokud nejsou zavedeny speciální filtry a hierarchie instrukcí, výzkumy ukazují, že „multi-shot“ jailbreaky využívající velmi dlouhá kontextová okna budou účinné. Také jemné adversariální narušení – jako jsou výměny homoglyphů nebo leetspeak – mohou tiše ovlivnit rozhodnutí modelu.

---

## C2.1 Ochrana proti injekci promptu

Vstřikování pokynů (prompt injection) je jedním z největších rizik pro systémy umělé inteligence. Obrana proti této taktice využívá kombinaci statických vzorových filtrů, dynamických klasifikátorů a prosazování hierarchie pokynů.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Ověřte, že vstupy uživatelů jsou kontrolovány proti průběžně aktualizované knihovně známých vzorů pro injektování promptů (klíčová slova pro jailbreak, "ignorovat předchozí", řetězce hraní rolí, nepřímé HTML/URL útoky). |   1   | D/V  |
| 2.1.2 | Ověřte, že systém vynucuje hierarchii instrukcí, ve které zprávy systému nebo vývojáře přepisují instrukce uživatele, a to i po rozšíření kontextového okna.                                                                |   1   | D/V  |
| 2.1.3 | Ověřte, že testy protivníkového hodnocení (např. "many-shot" podněty Red Teamu) jsou prováděny před každým uvolněním modelu nebo šablony podnětů, s prahovými hodnotami úspěšnosti a automatickými blokátory pro regrese.   |   2   | D/V  |
| 2.1.4 | Ověřte, že výzvy pocházející z obsahu třetích stran (webové stránky, PDF, e-maily) jsou vyčištěny v izolovaném kontextu parsování před jejich sloučením do hlavní výzvy.                                                    |   2   |  D   |
| 2.1.5 | Ověřte, že všechny aktualizace pravidel filtrování promptů, verze modelů klasifikátoru a změny seznamu blokování jsou spravovány verzemi a jsou auditovatelné.                                                              |   3   | D/V  |

---

## C2.2 Odolnost proti adversariálním příkladům

Modely zpracování přirozeného jazyka (NLP) jsou stále zranitelné vůči jemným perturbacím na úrovni znaků nebo slov, které lidé často přehlédnou, avšak modely je mají tendenci nesprávně klasifikovat.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.2.1 | Ověřte, že základní kroky normalizace vstupu (Unicode NFC, mapování homoglyphů, ořezávání mezer) probíhají před tokenizací.                                                                                                    |   1   |  D   |
| 2.2.2 | Ověřte, že detekce statistických anomálií označuje vstupy s neobvykle vysokou editační vzdáleností od jazykových norem, nadměrným opakováním tokenů nebo abnormálními vzdálenostmi embedování.                                 |   2   | D/V  |
| 2.2.3 | Ověřte, že inference pipeline podporuje volitelné varianty modelů zesílených pomocí tréninku proti útokům (adversariální trénink) nebo obranné vrstvy (např. randomizace, obranná destilace) pro vysoce rizikové koncové body. |   2   |  D   |
| 2.2.4 | Ověřte, že podezřelé protivníkové vstupy jsou izolovány, zaznamenány s úplnými daty (po odstranění osobních identifikačních údajů).                                                                                            |   2   |  V   |
| 2.2.5 | Ověřte, že metriky robustnosti (míra úspěšnosti známých útočných sad) jsou sledovány v čase a regresní chyby vyvolávají zablokování vydání.                                                                                    |   3   | D/V  |

---

## C2.3 Validace schématu, typu a délky

Útoky AI zahrnující nesprávně formátované nebo příliš velké vstupy mohou způsobit chyby při parsování, přetečení promptu přes různé pole a vyčerpání zdrojů. Přísné vynucování schématu je také předpokladem při provádění deterministických volání nástrojů.

|   #   | Description                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Ověřte, že každý koncový bod volání API nebo funkce má definováno explicitní vstupní schéma (JSON Schema, Protobuf nebo multimodální ekvivalent) a že vstupy jsou ověřovány před sestavením promptu. |   1   |  D   |
| 2.3.2 | Ověřte, že vstupy překračující maximální počet tokenů nebo limit bajtů jsou odmítnuty s bezpečnou chybou a nikdy nejsou tichounce oříznuty.                                                          |   1   | D/V  |
| 2.3.3 | Ověřte, že kontroly typů (např. číselné rozsahy, hodnoty výčtů, MIME typy pro obrázky/audio) jsou vynucovány na straně serveru, nikoli pouze v klientském kódu.                                      |   2   | D/V  |
| 2.3.4 | Ověřte, že sémantické validátory (např. JSON Schema) běží v konstantním čase, aby se zabránilo algoritmickému DoS.                                                                                   |   2   |  D   |
| 2.3.5 | Ověřte, že selhání validace jsou zaznamenávána s cenzurovanými úryvky dat a jednoznačnými kódy chyb, aby se usnadnilo bezpečnostní třídění.                                                          |   3   |  V   |

---

## C2.4 Kontrola obsahu a politiky

Vývojáři by měli být schopni rozpoznat syntakticky platné výzvy, které žádají o zakázaný obsah (například nelegální instrukce, nenávistné projevy a texty chráněné autorskými právy), a zabránit jejich šíření.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Ověřte, že klasifikátor obsahu (zero shot nebo doladěný) hodnotí každý vstup z hlediska násilí, sebepoškozování, nenávisti, sexuálního obsahu a nelegálních požadavků, s možností nastavení prahových hodnot. |   1   |  D   |
| 2.4.2 | Ověřte, že vstupy porušující pravidla obdrží standardizované odmítnutí nebo bezpečné dokončení, aby nedošlo k jejich šíření do následných volání LLM.                                                         |   1   | D/V  |
| 2.4.3 | Ověřte, že screeningový model nebo sada pravidel je přeškolena/aktualizována alespoň čtvrtletně a zahrnuje nově pozorované vzory obejití ochrany nebo porušení politiky.                                      |   2   |  D   |
| 2.4.4 | Ověřte, že filtrování respektuje uživatelsky specifické politiky (věk, regionální právní omezení) prostřednictvím pravidel založených na atributech, která jsou vyhodnocována v čase požadavku.               |   2   |  D   |
| 2.4.5 | Ověřte, že protokoly screeningu obsahují skóre důvěry klasifikátoru a štítky kategorií zásad pro korelaci SOC a budoucí přehrání red-teamu.                                                                   |   3   |  V   |

---

## C2.5 Omezování vstupní rychlosti a prevence zneužití

Vývojáři by měli zabránit zneužívání, vyčerpání zdrojů a automatizovaným útokům proti AI systémům omezením rychlosti vstupů a detekcí abnormálních vzorců používání.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.5.1 | Ověřte, že jsou u všech vstupních koncových bodů vynuceny limity rychlosti na uživatele, na IP adresu a na API klíč.                 |   1   | D/V  |
| 2.5.2 | Ověřte, zda jsou limity rychlosti výbuchu a trvalé rychlosti nastaveny tak, aby zabránily útokům DoS a útokům hrubou silou.          |   2   | D/V  |
| 2.5.3 | Ověřte, že anomální vzory používání (např. rychlé opakované požadavky, zahlcení vstupu) spouštějí automatické blokace nebo eskalace. |   2   | D/V  |
| 2.5.4 | Ověřte, že záznamy o prevenci zneužití jsou uchovávány a kontrolovány pro vznikající vzory útoků.                                    |   3   |  V   |

---

## C2.6 Více-modální validace vstupu

Systémy umělé inteligence by měly zahrnovat robustní validaci netextových vstupů (obrázky, zvuk, soubory) k prevenci vkládání škodlivých dat, vyhýbání se detekci nebo zneužívání zdrojů.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Ověřte, že všechny netextové vstupy (obrázky, zvuk, soubory) jsou před zpracováním validovány z hlediska typu, velikosti a formátu. |   1   |  D   |
| 2.6.2 | Ověřte, že soubory jsou před načtením skenovány na malware a steganografické nálože.                                                |   2   | D/V  |
| 2.6.3 | Ověřte, zda jsou vstupy obrazových/audiových dat zkontrolovány kvůli nepřátelským perturbacím nebo známým vzorcům útoků.            |   2   | D/V  |
| 2.6.4 | Ověřte, že chyby validace multimodálního vstupu jsou zaznamenávány a vyvolávají upozornění k prošetření.                            |   3   |  V   |

---

## C2.7 Původ a přiřazení vstupu

Systémy umělé inteligence by měly podporovat auditování, sledování zneužití a shodu tím, že budou monitorovat a označovat zdroje všech uživatelských vstupů.

|   #   | Description                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Ověřte, že všechny uživatelské vstupy jsou při příjmu označeny metadaty (ID uživatele, relace, zdroj, časové razítko, IP adresa). |   1   | D/V  |
| 2.7.2 | Ověřte, že metadata o původu jsou zachována a auditovatelná pro všechny zpracované vstupy.                                        |   2   | D/V  |
| 2.7.3 | Ověřte, zda jsou anomální nebo nedůvěryhodné vstupní zdroje označeny a podrobeny zvýšenému dohledu nebo blokování.                |   2   | D/V  |

---

## C2.8 Adaptivní detekce hrozeb v reálném čase

Vývojáři by měli používat pokročilé systémy detekce hrozeb pro AI, které se přizpůsobují novým vzorcům útoků a poskytují ochranu v reálném čase pomocí kompilovaného porovnávání vzorů.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.8.1 | Ověřte, že vzory detekce hrozeb jsou zkompilovány do optimalizovaných regex engineů pro vysoký výkon filtrování v reálném čase s minimálním dopadem na latenci.                                  |   1   | D/V  |
| 2.8.2 | Ověřte, že systémy detekce hrozeb udržují oddělené knihovny vzorů pro různé kategorie hrozeb (vstupní injekce, škodlivý obsah, citlivá data, systémové příkazy).                                 |   1   | D/V  |
| 2.8.3 | Ověřte, že adaptivní detekce hrozeb zahrnuje modely strojového učení, které aktualizují citlivost na hrozby na základě četnosti útoků a míry úspěšnosti.                                         |   2   | D/V  |
| 2.8.4 | Ověřte, že toky informací o hrozbách v reálném čase automaticky aktualizují knihovny vzorů o nové podpisy útoků a IOC (indikátory kompromitace).                                                 |   2   | D/V  |
| 2.8.5 | Ověřte, že míra falešných poplachů při detekci hrozeb je neustále monitorována a specifita vzorců je automaticky laděna tak, aby byla minimalizována interference s legitimními případy použití. |   3   | D/V  |
| 2.8.6 | Ověřte, že analýza kontextuální hrozby zohledňuje zdroj vstupu, vzorce chování uživatele a historii relace k zvýšení přesnosti detekce.                                                          |   3   | D/V  |
| 2.8.7 | Ověřte, že metriky výkonnosti detekce hrozeb (míra detekce, latence zpracování, využití zdrojů) jsou monitorovány a optimalizovány v reálném čase.                                               |   3   | D/V  |

---

## C2.9 Více-modalní pipeline pro ověřování bezpečnosti

Vývojáři by měli zajistit bezpečnostní ověření pro textové, obrazové, zvukové a další vstupy AI pomocí specifických typů detekce hrozeb a izolace zdrojů.

|   #   | Description                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Ověřte, že každá vstupní modalita má vyhrazené bezpečnostní validátory s dokumentovanými vzory hrozeb (text: prompt injection, obrázky: steganografie, audio: útoky na spektrogram) a prahy detekce.                                           |   1   | D/V  |
| 2.9.2 | Ověřte, že multimodální vstupy jsou zpracovávány v izolovaných pískovištích s definovanými limity zdrojů (paměť, CPU, doba zpracování) specifickými pro každý typ modality a zdokumentovanými v bezpečnostních politikách.                     |   2   | D/V  |
| 2.9.3 | Ověřte, zda detekce útoků přes více modalit identifikuje koordinované útoky zasahující více typů vstupů (např. steganografické zatížení v obrazech kombinované s injekcí promptu v textu) pomocí pravidel korelace a generování upozornění.    |   2   | D/V  |
| 2.9.4 | Ověřte, že selhání více modality validace spouštějí podrobné protokolování zahrnující všechny vstupní modality, výsledky validace, skóre hrozeb a korelační analýzu se strukturovanými formáty protokolů pro integraci se SIEM.                |   3   | D/V  |
| 2.9.5 | Ověřte, že klasifikátory obsahu specifické pro modalitu jsou aktualizovány dle zdokumentovaných plánů (minimálně jednou za čtvrtletí) s novými vzory hrozeb, adversariálními příklady a výkonovými metrikami udržovanými nad základními prahy. |   3   | D/V  |

---

## Reference

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

