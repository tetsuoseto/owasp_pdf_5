# Správa tréninkových dat C1 a řízení zkreslení

## Řídicí cíl

Tréninková data musí být získávána, zpracovávána a udržována tak, aby byla zachována jejich původnost, bezpečnost, kvalita a spravedlnost. Tím se plní zákonné povinnosti a snižují rizika zaujatosti, otravy dat nebo porušení soukromí během celého životního cyklu umělé inteligence.

---

## C1.1 Původ tréninkových dat

Udržujte ověřitelný inventář všech datasetů, akceptujte pouze důvěryhodné zdroje a zaznamenávejte každou změnu pro audituovatelnost.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Ověřte, že je udržován aktuální seznam všech zdrojů tréninkových dat (původ, správce/vlastník, licence, způsob sběru, omezení zamýšleného použití a historie zpracování).                                                                    |   1   | D/V  |
| 1.1.2 | Ověřte, že jsou povolena pouze datová soubory ověřená z hlediska kvality, reprezentativnosti, etického původu a souladu s licencí, čímž se snižují rizika otravy daty, vestavěných předsudků a porušení duševního vlastnictví.               |   1   | D/V  |
| 1.1.3 | Ověřte, že je uplatňováno minimalizování dat, aby byly vyloučeny zbytečné nebo citlivé atributy.                                                                                                                                             |   1   | D/V  |
| 1.1.4 | Ověřte, že všechny změny v datovém souboru podléhají schválenému schématu pracovního postupu se záznamem.                                                                                                                                    |   2   | D/V  |
| 1.1.5 | Ověřte, že kvalita označování/annotace je zajištěna prostřednictvím křížové kontroly recenzenty nebo konsensem.                                                                                                                              |   2   | D/V  |
| 1.1.6 | Ověřte, že pro významné tréninkové datové sady jsou udržovány "datové karty" nebo "datasheety pro datové sady", které podrobně popisují charakteristiky, motivace, složení, procesy sběru, předzpracování a doporučené/nedoporučené použití. |   2   | D/V  |

---

## C1.2 Bezpečnost a integrita tréninkových dat

Omezte přístup, šifrujte data v klidu i během přenosu a ověřujte integritu, aby se zabránilo manipulaci nebo krádeži.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Ověřte, že přístupové kontroly chrání úložiště a pipeline.                                                                                                                                                                                                                                    |   1   | D/V  |
| 1.2.2 | Ověřte, že datové soubory jsou během přenosu šifrovány a u veškerých citlivých nebo osobně identifikovatelných informací (PII) také v klidu, přičemž jsou použity kryptografické algoritmy odpovídající průmyslovým standardům a postupy správy klíčů.                                        |   2   | D/V  |
| 1.2.3 | Ověřte, že k zajištění integrity dat během ukládání a přenosu jsou používány kryptografické hashovací funkce nebo digitální podpisy, a že jsou aplikovány automatizované techniky detekce anomálií k ochraně proti nepovoleným úpravám nebo poškození, včetně cílených pokusů o otrávení dat. |   2   | D/V  |
| 1.2.4 | Ověřte, že verze datasetu jsou sledovány, aby bylo možné provést návrat zpět.                                                                                                                                                                                                                 |   3   | D/V  |
| 1.2.5 | Ověřte, že zastaralá data jsou bezpečně vymazána nebo anonymizována v souladu s politikami uchovávání dat, regulačními požadavky a za účelem zmenšení povrchu útoku.                                                                                                                          |   2   | D/V  |

---

## C1.3 Úplnost a spravedlnost reprezentace

Detekujte demografické odchylky a aplikujte opatření ke zmírnění, aby míra chyb modelu byla spravedlivá napříč skupinami.

|   #   | Description                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Ověřte, zda jsou datové sady analyzovány z hlediska nerovnováhy v zastoupení a potenciálních zkreslení napříč zákonem chráněnými atributy (např. rasa, pohlaví, věk) a dalšími eticky citlivými charakteristikami relevantními pro oblast použití modelu (např. socioekonomický status, lokalita).                                |   1   | D/V  |
| 1.3.2 | Ověřte, že identifikované předpojatosti jsou zmírněny pomocí zdokumentovaných strategií, jako je vyvážení, cílená augmentace dat, algoritmické úpravy (např. techniky předzpracování, zpracování v průběhu, následné zpracování) nebo převažování, a že je posouzen dopad těchto opatření na spravedlnost i celkový výkon modelu. |   2   | D/V  |
| 1.3.3 | Ověřte, že metriky spravedlnosti po tréninku jsou vyhodnoceny a zdokumentovány.                                                                                                                                                                                                                                                   |   2   | D/V  |
| 1.3.4 | Ověřte, že politika správy životního cyklu zkreslení přiřazuje vlastníky a frekvenci přehledů.                                                                                                                                                                                                                                    |   3   | D/V  |

---

## C1.4 Kvalita, integrita a bezpečnost označování tréninkových dat

Chraňte štítky šifrováním a vyžadujte dvojí kontrolu u kritických tříd.

|   #   | Description                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Ověřte, že kvalita označování/komentování je zajištěna prostřednictvím jasných pokynů, vzájemných kontrol recenzentů, mechanismů dosažení konsensu (např. sledování shody mezi anotátory) a definovaných procesů pro řešení nesrovnalostí.                                         |   2   | D/V  |
| 1.4.2 | Ověřte, že kryptografické haše nebo digitální podpisy jsou aplikovány na označení artefaktů, aby byla zajištěna jejich integrita a autenticita.                                                                                                                                    |   2   | D/V  |
| 1.4.3 | Ověřte, že rozhraní a platformy pro označování zajišťují přísné přístupové kontroly, udržují nezfalšovatelné auditní záznamy všech aktivit označování a chrání před neoprávněnými úpravami.                                                                                        |   2   | D/V  |
| 1.4.4 | Ověřte, že označení kritická pro bezpečnost, zabezpečení nebo spravedlnost (např. identifikace toxického obsahu, zásadních lékařských nálezů) podléhají povinnému nezávislému dvojímu přezkumu nebo ekvivalentní robustní verifikaci.                                              |   3   | D/V  |
| 1.4.5 | Ověřte, že citlivé informace (včetně identifikovatelných osobních údajů - PII), které byly neúmyslně zachyceny nebo nezbytně přítomny v označeních, jsou při uložení i přenosu odstraněny, pseudonymizovány, anonymizovány nebo zašifrovány v souladu s principy minimalizace dat. |   2   | D/V  |
| 1.4.6 | Ověřte, že návody k označování a pokyny jsou komplexní, řízené verzemi a revidované vrstevníky.                                                                                                                                                                                    |   2   | D/V  |
| 1.4.7 | Ověřte, že datové schémata (včetně štítků) jsou jasně definována a řízena verzováním.                                                                                                                                                                                              |   2   | D/V  |
| 1.8.2 | Ověřte, že zpracování označování, které je outsourcováno nebo zajišťováno prostřednictvím crowdsourcingu, obsahuje technická a procedurální opatření k zajištění důvěrnosti dat, integrity, kvality štítků a prevenci úniku dat.                                                   |   2   | D/V  |

---

## C1.5 Zajištění kvality tréninkových dat

Kombinujte automatizovanou validaci, manuální náhodné kontroly a zaznamenané opravy, aby byla zajištěna spolehlivost datové sady.

|   #   | Description                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Ověřte, že automatizované testy zachycují chyby formátu, nulové hodnoty a posuny štítků při každém příjmu dat nebo významné transformaci.                                                                                                                                                   |   1   |  D   |
| 1.5.2 | Ověřte, že neúspěšné datové sady jsou izolovány s auditními stopami.                                                                                                                                                                                                                        |   1   | D/V  |
| 1.5.3 | Ověřte, že manuální náhodné kontroly prováděné odborníky na danou oblast pokrývají statisticky významný vzorek (např. ≥1 % nebo 1 000 vzorků, podle toho, co je větší, nebo podle určení hodnocením rizik) k identifikaci jemných problémů s kvalitou, které nejsou zachyceny automatizací. |   2   |  V   |
| 1.5.4 | Ověřte, že kroky nápravy jsou připojeny k záznamům o původu.                                                                                                                                                                                                                                |   2   | D/V  |
| 1.5.5 | Ověřte, že kvalitní brány blokují nekvalitní datové sady, pokud nejsou schváleny výjimky.                                                                                                                                                                                                   |   2   | D/V  |

---

## C1.6 Detekce otravy dat

Použijte statistickou detekci anomálií a pracovní postupy karantény k zastavení protivníkových vložení.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Ověřte, že techniky detekce anomálií (např. statistické metody, detekce odlehlých dat, analýza embeddingů) jsou aplikovány na tréninková data při jejich příjmu a před hlavními tréninkovými běhy za účelem identifikace potenciálních útoků otravy dat nebo neúmyslné korupce dat. |   2   | D/V  |
| 1.6.2 | Ověřte, že označené vzorky vyvolávají ruční kontrolu před tréninkem.                                                                                                                                                                                                                |   2   | D/V  |
| 1.6.3 | Ověřte, že výsledky jsou začleněny do bezpečnostního spisu modelu a informují průběžnou hrozbu inteligence.                                                                                                                                                                         |   2   |  V   |
| 1.6.4 | Ověřte, že detekční logika je aktualizována s novými informacemi o hrozbách.                                                                                                                                                                                                        |   3   | D/V  |
| 1.6.5 | Ověřte, že online učební pipelines sledují změnu rozdělení (distribution drift).                                                                                                                                                                                                    |   3   | D/V  |
| 1.6.6 | Ověřte, že jsou zohledněny a implementovány konkrétní obrany proti známým typům útoků na otravu dat (např. převracení štítků, vkládání spouštěčů zadních vrátek, útoky pomocí vlivných instancí) na základě profilu rizik systému a zdrojů dat.                                     |   3   | D/V  |

---

## C1.7 Mazání uživatelských dat a vynucování souhlasu

Respektujte požadavky na vymazání a odvolání souhlasu napříč datovými sadami, zálohami a odvozenými artefakty.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Ověřte, že pracovní postupy mazání odstraňují primární a odvozená data a posuďte dopad na modely, a že dopad na postižené modely je vyhodnocen a v případě potřeby řešen (například zpětným učením nebo překalibrací).                                               |   1   | D/V  |
| 1.7.2 | Ověřte, že existují mechanismy pro sledování a respektování rozsahu a stavu uživatelského souhlasu (a jeho odvolání) pro data používaná při tréninku, a že je souhlas ověřován před zařazením dat do nových tréninkových procesů nebo významných aktualizací modelu. |   2   |  D   |
| 1.7.3 | Ověřte, že pracovní postupy jsou testovány každoročně a zaznamenávány.                                                                                                                                                                                               |   2   |  V   |

---

## C1.8 Bezpečnost dodavatelského řetězce

Provádějte ověřování externích poskytovatelů dat a ověřujte integritu přes autentizované, šifrované kanály.

|   #   | Description                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.8.1 | Ověřte, že dodavatelé dat třetích stran, včetně poskytovatelů předem natrénovaných modelů a externích datových sad, procházejí kontrolou bezpečnosti, ochrany soukromí, etického získávání a kvality dat před tím, než jsou jejich data nebo modely integrovány.                                 |   2   | D/V  |
| 1.8.2 | Ověřte, zda externí převody používají TLS/autentizaci a kontroly integrity.                                                                                                                                                                                                                      |   1   |  D   |
| 1.8.3 | Ověřte, že zdroje dat s vysokým rizikem (např. otevřené datové sady s neznámým původem, nesrovnaní dodavatelé) jsou před použitím v citlivých aplikacích podrobeny zvýšené kontrole, jako je izolovaná analýza (sandboxing), rozsáhlé kontroly kvality a zaujatosti a cílená detekce otravy dat. |   2   | D/V  |
| 1.8.4 | Ověřte, že předem vytrénované modely získané od třetích stran jsou hodnoceny z hlediska zabudovaných předsudků, potenciálních zadních vrátek, integrity jejich architektury a původu původních tréninkových dat před doladěním nebo nasazením.                                                   |   3   | D/V  |

---

## C1.9 Detekce adversariálních vzorků

Implementujte opatření během fáze tréninku, jako je adversariální trénink, aby se zvýšila odolnost modelu proti adversariálním příkladům.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Ověřte, že jsou implementovány a laděny vhodné obranné mechanismy, jako je adversariální trénink (používání generovaných adversariálních příkladů), rozšíření dat s porušenými vstupy nebo techniky robustní optimalizace, pro relevantní modely na základě hodnocení rizik. |   3   | D/V  |
| 1.9.2 | Ověřte, že pokud je použito protivníkové trénování, je generování, správa a verzování protivníkových datových sad zdokumentováno a kontrolováno.                                                                                                                             |   2   | D/V  |
| 1.9.3 | Zajistěte, aby byl vliv tréninku odolnosti vůči nepřátelským útokům na výkon modelu (proti jak čistým, tak nepřátelským vstupům) a metriky spravedlnosti vyhodnocován, dokumentován a monitorován.                                                                           |   3   | D/V  |
| 1.9.4 | Ověřte, že strategie pro adversariální trénink a robustnost jsou pravidelně přezkoumávány a aktualizovány, aby se zabránilo vyvíjejícím se technikám adversariálních útoků.                                                                                                  |   3   | D/V  |

---

## C1.10 Sledovatelnost a původ dat

Sledujte celou cestu každého datového bodu od zdroje až po vstup modelu pro auditovatelnost a reakci na incidenty.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Ověřte, že linie každého datového bodu, včetně všech transformací, augmentací a sloučení, je zaznamenána a může být rekonstruována. |   2   | D/V  |
| 1.10.2 | Ověřte, že záznamy o původu jsou neměnné, bezpečně uloženy a dostupné pro audity nebo vyšetřování.                                  |   2   | D/V  |
| 1.10.3 | Ověřte, že sledování původu pokrývá jak surová, tak syntetická data.                                                                |   2   | D/V  |

---

## C1.11 Správa syntetických dat

Zajistěte, aby byla syntetická data řádně spravována, označována a oceněna z hlediska rizik.

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Ověřte, že všechna syntetická data jsou jasně označena a rozlišitelná od skutečných dat v celém procesu.                                                             |   2   | D/V  |
| 1.11.2 | Ověřte, že proces generování, parametry a zamýšlené použití syntetických dat jsou zdokumentovány.                                                                    |   2   | D/V  |
| 1.11.3 | Ověřte, že syntetická data jsou před použitím při tréninku hodnocena z hlediska rizik týkajících se zkreslení, úniku soukromých informací a problémů s reprezentací. |   2   | D/V  |

---

## C1.12 Monitorování přístupu k datům a detekce anomálií

Monitorujte a upozorňujte na neobvyklý přístup k tréninkovým datům k detekci vnitřních hrozeb nebo exfiltrace.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Ověřte, že všechny přístupy k tréninkovým datům jsou zaznamenány, včetně uživatele, času a provedené akce.                                |   2   | D/V  |
| 1.12.2 | Ověřte, že jsou přístupové záznamy pravidelně kontrolovány kvůli neobvyklým vzorcům, jako jsou velké exporty nebo přístupy z nových míst. |   2   | D/V  |
| 1.12.3 | Ověřte, že jsou generovány upozornění na podezřelé přístupy a že jsou tyto události neprodleně vyšetřovány.                               |   2   | D/V  |

---

## C1.13 Zásady uchovávání a vypršení platnosti dat

Definujte a vynucujte doby uchovávání dat, aby se minimalizovalo zbytečné ukládání dat.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Ověřte, že pro všechna tréninková data jsou definovány explicitní doby uchovávání.                                        |   1   | D/V  |
| 1.13.2 | Ověřte, zda jsou datové sady automaticky ukončeny, smazány nebo přezkoumány k odstranění na konci jejich životního cyklu. |   2   | D/V  |
| 1.13.3 | Ověřte, že akce uchovávání a mazání jsou zaznamenávány a auditovatelné.                                                   |   2   | D/V  |

---

## C1.14 Soulad s předpisy a jurisdikcí

Zajistěte, aby všechna tréninková data byla v souladu s platnými zákony a předpisy.

|   #    | Description                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Ověřte, že požadavky na umístění dat a přeshraniční přenos jsou identifikovány a uplatňovány pro všechny datové sady.             |   2   | D/V  |
| 1.14.2 | Ověřte, že jsou identifikovány a řešeny předpisy specifické pro daný sektor (např. zdravotnictví, finance) při zpracování dat.    |   2   | D/V  |
| 1.14.3 | Ověřte, že dodržování příslušných zákonů o ochraně osobních údajů (např. GDPR, CCPA) je dokumentováno a pravidelně přezkoumáváno. |   2   | D/V  |

---

## C1.15 Vodoznaky a otiskování dat

Detekce neoprávněného opětovného použití nebo úniku vlastních či citlivých dat.

|   #    | Description                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Ověřte, že datové sady nebo jejich podmnožiny jsou opatřeny vodoznakem nebo otiskem tam, kde je to možné.               |   3   | D/V  |
| 1.15.2 | Ověřte, že metody vodotisku/otisků prstů nezavádějí zkreslení ani rizika pro soukromí.                                  |   3   | D/V  |
| 1.15.3 | Ověřte, že jsou prováděny pravidelné kontroly za účelem detekce neoprávněného znovupoužití nebo úniku dat s vodoznakem. |   3   | D/V  |

---

## C1.16 Řízení práv subjektů údajů

Podporovat práva subjektů údajů, jako je přístup, oprava, omezení a námitky.

|   #    | Description                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.16.1 | Ověřte, že existují mechanismy pro reakci na žádosti subjektů údajů o přístup, opravu, omezení nebo námitku. |   2   | D/V  |
| 1.16.2 | Ověřte, že požadavky jsou zaznamenávány, sledovány a vyřizovány v zákonem stanovených lhůtách.               |   2   | D/V  |
| 1.16.3 | Ověřte, že procesy práv subjektů údajů jsou pravidelně testovány a přezkoumávány z hlediska účinnosti.       |   2   | D/V  |

---

## C1.17 Analýza dopadu verze datové sady

Před aktualizací nebo výměnou verzí posuďte dopad změn v datové sadě.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Ověřte, že je provedena analýza dopadů před aktualizací nebo nahrazením verze datové sady, zahrnující výkon modelu, spravedlnost a soulad s předpisy. |   2   | D/V  |
| 1.17.2 | Ověřte, že výsledky analýzy dopadů jsou zdokumentovány a přezkoumány příslušnými zainteresovanými stranami.                                           |   2   | D/V  |
| 1.17.3 | Ověřte, že existují plány na návrat zpět pro případ, že nové verze přinesou nepřijatelné rizika nebo nežádoucí regrese.                               |   2   | D/V  |

---

## C1.18 Bezpečnost pracovní síly pro anotaci dat

Zajistěte bezpečnost a integritu personálu zapojeného do anotace dat.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Ověřte, že všichni zaměstnanci zapojení do anotace dat prošli kontrolou minulosti a byli školeni v oblasti bezpečnosti dat a ochrany soukromí. |   2   | D/V  |
| 1.18.2 | Ověřte, že veškerý personál provádějící anotace podepíše dohody o důvěrnosti a mlčenlivosti.                                                   |   2   | D/V  |
| 1.18.3 | Ověřte, že platformy pro anotaci vynucují přístupová omezení a monitorují hrozby zevnitř organizace.                                           |   2   | D/V  |

---

## Reference

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

