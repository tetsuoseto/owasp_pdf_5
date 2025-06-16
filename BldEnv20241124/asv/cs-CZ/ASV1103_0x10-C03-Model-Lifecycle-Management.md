# Řízení životního cyklu modelu C3 a kontrola změn

## Řídicí cíl

Systémy umělé inteligence musí zavádět procesy řízení změn, které zabrání neoprávněným nebo nebezpečným úpravám modelu dostat se do produkčního prostředí. Tato kontrola zajišťuje integritu modelu po celou dobu jeho životního cyklu – od vývoje přes nasazení až po vyřazení z provozu – což umožňuje rychlou reakci na incidenty a udržuje odpovědnost za všechny změny.

Hlavní bezpečnostní cíl: Do produkce jsou nasazeny pouze autorizované a ověřené modely prostřednictvím kontrolovaných procesů, které zajišťují integritu, sledovatelnost a obnovitelnost.

---

## C3.1 Autorizace modelu a integrita

Do výrobního prostředí smí proniknout pouze autorizované modely s ověřenou integritou.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.1.1 | Ověřte, že všechny modelové artefakty (váhy, konfigurace, tokenizéry) jsou kryptograficky podepsány autorizovanými subjekty před nasazením.                                                      |   1   | D/V  |
| 3.1.2 | Ověřte, že integrita modelu je validována při nasazení a chyby při ověřování podpisu zabraňují načtení modelu.                                                                                   |   1   | D/V  |
| 3.1.3 | Ověřte, že záznamy o původu modelu zahrnují identitu autorizující entity, kontrolní součty trénovacích dat, výsledky validačních testů s označením úspěchu/neúspěchu a časové razítko vytvoření. |   2   | D/V  |
| 3.1.4 | Ověřte, že všechny modelové artefakty používají sémantické verzování (MAJOR.MINOR.PATCH) s dokumentovanými kritérii určujícími, kdy se každá složka verze zvyšuje.                               |   2   | D/V  |
| 3.1.5 | Ověřte, že sledování závislostí udržuje aktuální inventář, který umožňuje rychlou identifikaci všech spotřebitelských systémů.                                                                   |   2   |  V   |

---

## C3.2 Validace a testování modelu

Modely musí před nasazením projít definovanými bezpečnostními a bezpečnostními ověřeními.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Ověřte, že modely podstupují automatizované bezpečnostní testování, které zahrnuje validaci vstupů, sanitaci výstupů a bezpečnostní hodnocení s předem dohodnutými organizačními prahovými hodnotami pro úspěch/neúspěch před nasazením. |   1   | D/V  |
| 3.2.2 | Ověřte, že neúspěchy ověření automaticky blokují nasazení modelu po explicitním schválení přepisem od předem určených oprávněných osob s dokumentovanými obchodními odůvodněními.                                                        |   1   | D/V  |
| 3.2.3 | Ověřte, že výsledky testů jsou kryptograficky podepsané a neměnitelně propojené s konkrétním hashem verze modelu, který je ověřován.                                                                                                     |   2   |  V   |
| 3.2.4 | Ověřte, že nouzová nasazení vyžadují zdokumentované hodnocení bezpečnostních rizik a schválení od předem určené bezpečnostní autority v předem dohodnutých časových rámcích.                                                             |   2   | D/V  |

---

## C3.3 Řízené nasazení a návrat k předchozí verzi

Nasazení modelů musí být kontrolováno, monitorováno a reverzibilní.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Ověřte, že produkční nasazení implementují mechanismy postupného zavádění (canary nasazení, blue-green nasazení) s automatickými spouštěči návratu zpět založenými na předem dohodnutých mírách chyb, prahových hodnotách latence nebo kritériích bezpečnostních upozornění. |   1   |  D   |
| 3.3.2 | Ověřte, že schopnosti návratu zpět obnovují úplný stav modelu (váhy, konfigurace, závislosti) atomicky v rámci předem definovaných organizačních časových oken.                                                                                                              |   1   | D/V  |
| 3.3.3 | Ověřte, že procesy nasazení validují kryptografické podpisy a vypočítávají kontrolní součty integrity před aktivací modelu, a v případě jakéhokoli nesouladu nasazení selžou.                                                                                                |   2   | D/V  |
| 3.3.4 | Ověřte, že schopnosti nouzového vypnutí modelu mohou deaktivovat koncové body modelu v rámci předem definovaných reakčních časů prostřednictvím automatizovaných jističů nebo manuálních vypínačů.                                                                           |   2   | D/V  |
| 3.3.5 | Ověřte, že rollback artefakty (předchozí verze modelu, konfigurace, závislosti) jsou uchovávány v souladu s organizačními politikami s neměnným úložištěm pro reakci na incidenty.                                                                                           |   2   |  V   |

---

## C3.4 Změna odpovědnosti a auditu

Všechny změny v životním cyklu modelu musí být sledovatelné a auditovatelné.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Ověřte, že všechny změny modelu (nasazení, konfigurace, vyřazení) generují neměnné auditní záznamy, včetně časové značky, ověřené identity aktéra, typu změny a stavů před a po změně.                                |   1   |  V   |
| 3.4.2 | Ověřte, že přístup k auditnímu protokolu vyžaduje odpovídající autorizaci a všechny pokusy o přístup jsou zaznamenány s identitou uživatele a časovou značkou.                                                        |   2   | D/V  |
| 3.4.3 | Ověřte, že šablony promptů a systémové zprávy jsou verzovány v git repozitářích s povinnou kontrolou kódu a schválením určenými recenzenty před nasazením.                                                            |   2   | D/V  |
| 3.4.4 | Ověřte, že auditní záznamy obsahují dostatečné podrobnosti (hashy modelu, snímky konfigurace, verze závislostí), aby bylo možné kompletně rekonstruovat stav modelu pro jakýkoli časový údaj v rámci doby uchovávání. |   2   |  V   |

---

## C3.5 Bezpečné vývojové postupy

Procesy vývoje a školení modelů musí dodržovat bezpečné postupy, aby se zabránilo jejich kompromitaci.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Ověřte, že prostředí pro vývoj modelu, testování a produkci jsou fyzicky nebo logicky oddělena. Nemají společnou infrastrukturu, mají odlišné přístupové kontroly a izolované úložiště dat.         |   1   |  D   |
| 3.5.2 | Ověřte, že trénink a doladění modelu probíhají v izolovaných prostředích s řízeným přístupem k síti.                                                                                                |   1   |  D   |
| 3.5.3 | Ověřte, že zdroje tréninkových dat jsou validovány pomocí kontrol integrity a autentizovány prostřednictvím důvěryhodných zdrojů s dokumentovaným řetězcem důvěry před použitím ve vývoji modelu.   |   1   | D/V  |
| 3.5.4 | Ověřte, že artefakty vývoje modelu (hyperparametry, skripty pro trénink, konfigurační soubory) jsou uloženy v systému pro správu verzí a vyžadují schválení peer review před použitím při tréninku. |   2   |  D   |

---

## C3.6 Ukončení a vyřazení modelu

Modely musí být bezpečně vyřazeny, když již nejsou potřeba nebo když jsou identifikovány bezpečnostní problémy.

|   #   | Description                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.6.1 | Ověřte, že procesy ukončení modelu automaticky prohledávají závislostní grafy, identifikují všechny spotřebitelské systémy a poskytují předem dohodnuté lhůty upozornění před vyřazením z provozu.                                                     |   1   |  D   |
| 3.6.2 | Ověřte, že artefakty starých modelů jsou bezpečně vymazány pomocí kryptografického vymazání nebo vícenásobného přepisování v souladu s dokumentovanými zásadami uchovávání dat a s ověřenými certifikáty o zničení.                                    |   1   | D/V  |
| 3.6.3 | Ověřte, že události vyřazení modelu jsou zaznamenány s časovým razítkem a identitou aktéra, a že podpisy modelu jsou zrušeny, aby se zabránilo jejich opětovnému použití.                                                                              |   2   |  V   |
| 3.6.4 | Ověřte, že mimořádné odstavení modelu může zakázat přístup k modelu v rámci předem stanovených časových rámců pro reakci na nouzové situace prostřednictvím automatických vypínacích spínačů, pokud jsou zjištěny kritické bezpečnostní zranitelnosti. |   2   | D/V  |

---

## Reference

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

