# C3 modell életciklus-kezelés és változásvezérlés

## Irányítási célkitűzés

A mesterséges intelligencia rendszereknek olyan változáskezelési folyamatokat kell alkalmazniuk, amelyek megakadályozzák, hogy illetéktelen vagy nem biztonságos modellmódosítások kerüljenek éles környezetbe. Ez az ellenőrzés biztosítja a modell integritását az egész életciklus során – a fejlesztéstől a telepítésen át a kiselejtezésig –, ami lehetővé teszi a gyors incidensválaszt és fenntartja a felelősségre vonhatóságot minden változtatás esetén.

Alapvető biztonsági cél: Csak az engedélyezett, ellenőrzött modellek jussanak a termelésbe olyan szabályozott folyamatok alkalmazásával, amelyek biztosítják az integritást, nyomon követhetőséget és helyreállíthatóságot.

---

## C3.1 Modellengedélyezés és integritás

Csak az ellenőrzött integritású, engedélyezett modellek kerülhetnek gyártási környezetbe.

|   #   | Description                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Ellenőrizze, hogy az összes modell tárgy (súlyok, konfigurációk, tokenizálók) kriptográfiailag aláírt-e az arra jogosult entitások által a telepítés előtt.                                                                                               |   1   | D/V  |
| 3.1.2 | Ellenőrizze, hogy a modell integritását a telepítéskor igazolják-e, és hogy a aláírás-ellenőrzési hibák megakadályozzák a modell betöltését.                                                                                                              |   1   | D/V  |
| 3.1.3 | Ellenőrizze, hogy a modell eredetét igazoló feljegyzések tartalmazzák-e az engedélyező fél azonosítóját, a képzési adatok ellenőrzőösszegeit, az érvényesítési teszteredményeket sikerességi/hibajelentési státusszal, valamint a létrehozás időbélyegét. |   2   | D/V  |
| 3.1.4 | Ellenőrizze, hogy az összes modell műtárgy szemantikus verziózást (FŐ.VÁLTOZAT.PONT) használ-e, és legyen dokumentált kritérium arra, hogy mikor növekszik az egyes verziókomponens.                                                                      |   2   | D/V  |
| 3.1.5 | Ellenőrizze, hogy a függőségkövetés valós idejű készletet tart fenn, amely lehetővé teszi az összes fogyasztó rendszer gyors azonosítását.                                                                                                                |   2   |  V   |

---

## C3.2 Modell validálás és tesztelés

A modelleknek a telepítés előtt meg kell felelniük a meghatározott biztonsági és védelmi érvényesítéseknek.

|   #   | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Ellenőrizze, hogy a modellek automatikus biztonsági tesztelésen mennek-e keresztül, amely magában foglalja a bemeneti érvényesítést, a kimeneti tisztítást és a biztonsági értékeléseket előre meghatározott szervezeti átmeneti/elbukási küszöbértékekkel a telepítés előtt. |   1   | D/V  |
| 3.2.2 | Ellenőrizze, hogy a validációs hibák automatikusan blokkolják-e a modell telepítését az előre kijelölt, engedéllyel rendelkező személyek által dokumentált üzleti indoklással történő kifejezett felülbírálati jóváhagyása után.                                              |   1   | D/V  |
| 3.2.3 | Ellenőrizze, hogy a teszteredmények kriptográfiailag alá vannak-e írva, és visszafordíthatatlanul kapcsolódnak-e a validált adott modellverzió hash-éhez.                                                                                                                     |   2   |  V   |
| 3.2.4 | Ellenőrizze, hogy a sürgősségi telepítésekhez dokumentált biztonsági kockázatértékelés és előre kijelölt biztonsági hatóság jóváhagyása szükséges-e az előre egyeztetett határidőkön belül.                                                                                   |   2   | D/V  |

---

## C3.3 Szabályozott Telepítés és Visszagörgetés

A modelltelepítéseket szabályozni, ellenőrizni és visszafordíthatóvá kell tenni.

|   #   | Description                                                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.3.1 | Ellenőrizze, hogy a termelési telepítések fokozatos bevezetési mechanizmusokat valósítanak-e meg (pl. kanári telepítések, kék-zöld telepítések), amelyek automatikus visszagörgetési kiváltó okokkal rendelkeznek az előre egyeztetett hibaarányok, késleltetési küszöbök vagy biztonsági figyelmeztetési kritériumok alapján. |   1   |  D   |
| 3.3.2 | Ellenőrizze, hogy a visszagörgetési képességek atomi módon állítják-e vissza a teljes modell állapotát (súlyokat, konfigurációkat, függőségeket) a szervezet által előre meghatározott időablakokban.                                                                                                                          |   1   | D/V  |
| 3.3.3 | Ellenőrizze, hogy a telepítési folyamatok érvényesítik-e a kriptográfiai aláírásokat és kiszámítják-e a sértetlenségi ellenőrzőösszegeket a modell aktiválása előtt, és sikertelenül zárulnak-e a telepítés bármilyen eltérés esetén.                                                                                          |   2   | D/V  |
| 3.3.4 | Ellenőrizze, hogy a vészhelyzeti modellleállítási képességek képesek-e az előre meghatározott válaszidőn belül letiltani a modell végpontjait automatizált áramkör-megszakítók vagy kézi leállítókapcsolók segítségével.                                                                                                       |   2   | D/V  |
| 3.3.5 | Ellenőrizze, hogy a visszagörgetési műtermékek (korábbi modellverziók, konfigurációk, függőségek) az szervezeti szabályzatoknak megfelelően megőrzésre kerülnek-e változtathatatlan tárolás révén az incidenskezelés érdekében.                                                                                                |   2   |  V   |

---

## C3.4 Változásfelelősség és Ellenőrzés

Az összes modell életciklusában bekövetkező változásnak nyomon követhetőnek és auditálhatónak kell lennie.

|   #   | Description                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Ellenőrizze, hogy minden modellváltoztatás (telepítés, konfiguráció, kivonás) rögzít-e megváltoztathatatlan auditfeljegyzéseket, amelyek tartalmaznak egy időbélyeget, egy hitelesített végrehajtó személyazonosságot, a változás típusát, valamint az előző és utáni állapotokat. |   1   |  V   |
| 3.4.2 | Ellenőrizze, hogy az audit naplóhoz való hozzáférés megfelelő jogosultságot igényel, és minden hozzáférési kísérletet felhasználói azonosítóval és időbélyeggel naplóznak.                                                                                                         |   2   | D/V  |
| 3.4.3 | Ellenőrizze, hogy a prompt sablonok és rendszerüzenetek verziókezelve vannak-e git tárolókban, kötelező kódáttekintéssel és kijelölt felülvizsgálók jóváhagyásával a telepítés előtt.                                                                                              |   2   | D/V  |
| 3.4.4 | Ellenőrizze, hogy az auditnaplók tartalmaznak-e elegendő részletet (modell kivonatok, konfigurációs pillanatképek, függőségi verziók) a modell állapotának teljes rekonstrukciójához bármely, a megőrzési időszakon belüli időbélyegző alapján.                                    |   2   |  V   |

---

## C3.5 Biztonságos Fejlesztési Gyakorlatok

A modellfejlesztési és betanítási folyamatoknak biztonságos gyakorlatokat kell követniük a sérülések megelőzése érdekében.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Ellenőrizze, hogy a modellfejlesztési, tesztelési és éles környezetek fizikailag vagy logikailag elkülönítettek-e. Nincs közös infrastruktúrájuk, különálló hozzáférés-vezérlésük és elszigetelt adattáraik.         |   1   |  D   |
| 3.5.2 | Ellenőrizze, hogy a modellképzés és finomhangolás elszigetelt környezetekben történik, korlátozott hálózati hozzáféréssel.                                                                                           |   1   |  D   |
| 3.5.3 | Bizonyosodjon meg arról, hogy az edzési adatforrásokat integritásellenőrzésekkel validálják, és megbízható források által hitelesítik, dokumentált nyomonkövetési lánccal a modellfejlesztés előtti használat előtt. |   1   | D/V  |
| 3.5.4 | Ellenőrizze, hogy a modellfejlesztési anyagok (hiperparaméterek, tanítási szkriptek, konfigurációs fájlok) verziókezelés alatt állnak, és a tanításhoz való használat előtt szükséges a társszakértői jóváhagyás.    |   2   |  D   |

---

## C3.6 Modell visszavonása és kivonása a használatból

A modelleket biztonságosan nyugdíjazni kell, amikor már nincs rájuk szükség, vagy amikor biztonsági problémákat azonosítanak.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Ellenőrizze, hogy a modellleállítási folyamatok automatikusan átvizsgálják-e a függőségi gráfokat, azonosítják-e az összes felhasználó rendszert, és biztosítanak-e előre egyeztetett értesítési időszakokat a leállítás előtt.                               |   1   |  D   |
| 3.6.2 | Ellenőrizze, hogy a nyugdíjazott modell artifactumok biztonságosan törlődnek-e kriptográfiai törlés vagy többszörös felülírás alkalmazásával, az dokumentált adatokmegőrzési szabályzatok szerint, és rendelkezzenek igazolt megsemmisítési tanúsítványokkal. |   1   | D/V  |
| 3.6.3 | Ellenőrizze, hogy a modell kivezetési események időbélyeggel és végrehajtó azonosítóval vannak rögzítve, valamint hogy a modell aláírásokat visszavonják a további felhasználás megakadályozása érdekében.                                                    |   2   |  V   |
| 3.6.4 | Ellenőrizze, hogy a vészhelyzeti modellkivonás képes-e letiltani a modell hozzáférését az előre meghatározott vészhelyzeti válaszidőn belül automatizált leállító kapcsolókon keresztül, amennyiben kritikus biztonsági sebezhetőségek kerülnek felfedezésre. |   2   | D/V  |

---

## Hivatkozások

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

