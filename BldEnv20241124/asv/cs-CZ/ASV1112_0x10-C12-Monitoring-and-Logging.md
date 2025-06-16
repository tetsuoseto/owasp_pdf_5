# C12 Monitorování, protokolování a detekce anomálií

## Cíl kontroly

Tato sekce poskytuje požadavky na zajištění viditelnosti v reálném čase a forenzní viditelnosti do toho, co model a další součásti umělé inteligence vidí, vykonávají a vracejí, aby bylo možné detekovat hrozby, třídit je a získávat z nich poznatky.

## C12.1 Protokolování požadavků a odpovědí

|   #    | Description                                                                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.1.1 | Ověřte, že všechny uživatelské výzvy a odpovědi modelu jsou zaznamenány s příslušnými metadaty (např. časové razítko, ID uživatele, ID relace, verze modelu).                                                                                    |   1   | D/V  |
| 12.1.2 | Ověřte, že jsou protokoly ukládány v zabezpečených, přístupem řízených úložištích s odpovídajícími zásadami uchovávání a zálohovacími postupy.                                                                                                   |   1   | D/V  |
| 12.1.3 | Ověřte, že systémy pro ukládání logů implementují šifrování dat v klidu i při přenosu, aby chránily citlivé informace obsažené v logech.                                                                                                         |   1   | D/V  |
| 12.1.4 | Ověřte, že citlivá data v zadáních a výstupech jsou před protokolováním automaticky zcenzurována nebo maskována, s konfigurovatelnými pravidly cenzurování pro osobně identifikovatelné informace (PII), přihlašovací údaje a důvěrné informace. |   1   | D/V  |
| 12.1.5 | Ověřte, že rozhodnutí politiky a akce filtrování bezpečnosti jsou zaznamenávány s dostatečnými podrobnostmi, aby bylo možné provést audit a ladění systémů moderování obsahu.                                                                    |   2   | D/V  |
| 12.1.6 | Ověřte, že integrita záznamů je chráněna například pomocí kryptografických podpisů nebo zapisovatelných úložišť pouze pro zápis.                                                                                                                 |   2   | D/V  |

---

## C12.2 Detekce zneužití a oznamování

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.2.1 | Ověřte, že systém detekuje a upozorňuje na známé vzory prolomení zabezpečení, pokusy o injektáž promptu a protivné vstupy pomocí detekce založené na signaturách.                          |   1   | D/V  |
| 12.2.2 | Ověřte, že systém se integruje se stávajícími platformami pro správu bezpečnostních informací a událostí (SIEM) pomocí standardních formátů a protokolů záznamů.                           |   1   | D/V  |
| 12.2.3 | Ověřte, že obohacené bezpečnostní události zahrnují kontext specifický pro umělou inteligenci, jako jsou identifikátory modelů, skóre důvěryhodnosti a rozhodnutí bezpečnostních filtrů.   |   2   | D/V  |
| 12.2.4 | Ověřte, že detekce behaviorálních odchylek identifikuje neobvyklé vzory konverzace, nadměrné pokusy o opakování nebo systematické prozkoumávací chování.                                   |   2   | D/V  |
| 12.2.5 | Ověřte, že mechanismy upozornění v reálném čase informují bezpečnostní týmy při detekci možných porušení politik nebo pokusů o útok.                                                       |   2   | D/V  |
| 12.2.6 | Ověřte, že jsou zahrnuta vlastní pravidla pro detekci vzorců hrozeb specifických pro AI, včetně koordinovaných pokusů o jailbreak, kampaní na injektáž promptu a útoků na extrakci modelu. |   2   | D/V  |
| 12.2.7 | Ověřte, že automatizované pracovní postupy reakce na incidenty dokážou izolovat kompromitované modely, zablokovat škodlivé uživatele a eskalovat kritické bezpečnostní události.           |   3   | D/V  |

---

## C12.3 Detekce driftu modelu

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Ověřte, že systém sleduje základní metriky výkonu, jako jsou přesnost, skóre důvěry, latence a chybovost napříč verzemi modelu a časovými obdobími.                   |   1   | D/V  |
| 12.3.2 | Ověřte, že automatické upozornění se spustí, když výkonové metriky překročí předem definované prahové hodnoty degradace nebo se výrazně odchýlí od základních hodnot. |   2   | D/V  |
| 12.3.3 | Ověřte, že monitorování detekce halucinací identifikuje a označuje případy, kdy výstupy modelu obsahují fakticky nesprávné, nekonzistentní nebo vymyšlené informace.  |   2   | D/V  |

---

## C12.4 Telemetrie výkonnosti a chování

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.4.1 | Ověřte, že jsou průběžně shromažďovány a monitorovány provozní metriky včetně latence požadavků, spotřeby tokenů, využití paměti a propustnosti.                         |   1   | D/V  |
| 12.4.2 | Ověřte, že jsou sledovány míry úspěšnosti a neúspěšnosti s kategorizací typů chyb a jejich základních příčin.                                                            |   1   | D/V  |
| 12.4.3 | Ověřte, že monitorování využití zdrojů zahrnuje využití GPU/CPU, spotřebu paměti a požadavky na úložiště, a že při překročení prahových hodnot je generováno upozornění. |   2   | D/V  |

---

## C12.5 Plánování a provádění reakce na incidenty AI

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Ověřte, že plány reakce na incidenty konkrétně řeší bezpečnostní události související s umělou inteligencí, včetně kompromitace modelu, otravování dat a protivníkových útoků.     |   1   | D/V  |
| 12.5.2 | Ověřte, že týmy pro reakci na incidenty mají přístup k forenzním nástrojům specifickým pro umělou inteligenci a odborné znalosti k vyšetřování chování modelu a útokových vektorů. |   2   | D/V  |
| 12.5.3 | Ověřte, že post-incidentní analýza zahrnuje zvážení přeškolení modelu, aktualizace bezpečnostních filtrů a integraci získaných poznatků do bezpečnostních kontrol.                 |   3   | D/V  |

---

## C12.5 Detekce poklesu výkonnosti AI

Monitorujte a detekujte zhoršování výkonu a kvality AI modelu v průběhu času.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Ověřte, že přesnost modelu, preciznost, připomenutí a F1 skóre jsou průběžně sledovány a porovnávány s referenčními hodnotami.     |   1   | D/V  |
| 12.5.2 | Ověřte, že detekce posunu dat monitoruje změny ve vstupním rozložení, které mohou ovlivnit výkon modelu.                           |   1   | D/V  |
| 12.5.3 | Ověřte, že detekce posunu konceptu identifikuje změny ve vztahu mezi vstupy a očekávanými výstupy.                                 |   2   | D/V  |
| 12.5.4 | Ověřte, že pokles výkonu spouští automatizovaná upozornění a zahajuje pracovní postupy pro opětovné školení nebo nahrazení modelu. |   2   | D/V  |
| 12.5.5 | Ověřte, že analýza příčiny degradace koreluje pokles výkonu se změnami dat, problémy v infrastruktuře nebo vnějšími faktory.       |   3   |  V   |

---

## C12.6 Vizualizace DAG a bezpečnost pracovního postupu

Chraňte systémy pro vizualizaci pracovních postupů před únikem informací a útoky na manipulaci.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.6.1 | Ověřte, že data vizualizace DAG jsou očištěna od citlivých informací před uložením nebo přenosem.                                                                        |   1   | D/V  |
| 12.6.2 | Ověřte, že přístupová kontrola k vizualizaci pracovních postupů zajišťuje, že pouze autorizovaní uživatelé mohou zobrazovat rozhodovací cesty agentů a stopy odůvodnění. |   1   | D/V  |
| 12.6.3 | Ověřte, že integrita dat DAG je chráněna pomocí kryptografických podpisů a mechanismů pro uchovávání odolného proti manipulaci.                                          |   2   | D/V  |
| 12.6.4 | Ověřte, že systémy vizualizace pracovních toků implementují validaci vstupů, aby předešly injekčním útokům prostřednictvím záměrně upravených dat uzlů nebo hran.        |   2   | D/V  |
| 12.6.5 | Ověřte, že aktualizace DAG v reálném čase jsou omezeny rychlostí a validovány, aby se zabránilo útokům typu denial-of-service na vizualizační systémy.                   |   3   | D/V  |

---

## C12.7 Proaktivní monitorování bezpečnostního chování

Detekce a prevence bezpečnostních hrozeb prostřednictvím proaktivní analýzy chování agentů.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Ověřte, že proaktivní chování agentů je před provedením bezpečnostně ověřeno s integrací hodnocení rizik.                              |   1   | D/V  |
| 12.7.2 | Ověřte, že spouštěče svobodné iniciativy zahrnují hodnocení bezpečnostního kontextu a posouzení hrozeb.                                |   2   | D/V  |
| 12.7.3 | Ověřte, že jsou analyzovány vzory proaktivního chování z hlediska možných bezpečnostních dopadů a neúmyslných následků.                |   2   | D/V  |
| 12.7.4 | Ověřte, že bezpečnostně kritické proaktivní akce vyžadují explicitní schvalovací řetězce s auditními stopami.                          |   3   | D/V  |
| 12.7.5 | Ověřte, že detekce behaviorálních anomálií identifikuje odchylky v progrativních vzorcích agentů, které mohou naznačovat kompromitaci. |   3   | D/V  |

---

## Reference

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

