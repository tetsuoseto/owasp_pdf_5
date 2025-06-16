# C3 mudeli elutsükli haldus ja muudatuste kontroll

## Juhtimise Eesmärk

Tehisintellekti süsteemid peavad rakendama muudatuste juhtimise protsesse, mis takistavad volitamata või ebaturvaliste mudeli muudatuste jõudmist tootmiskeskkonda. See kontroll tagab mudeli terviklikkuse kogu elutsükli vältel – arendusest kasutuselevõtuni ja kuni kasutusest kõrvaldamiseni – võimaldades kiiret intsidentidele reageerimist ning säilitades vastutuse kõigi muudatuste eest.

Põhiturvalisuse eesmärk: tootmisse jõuavad ainult volitatud ja valideeritud mudelid, kasutades kontrollitud protsesse, mis tagavad terviklikkuse, jälgitavuse ja taastatavuse.

---

## C3.1 Mudeli autoriseerimine ja terviklikkus

Tootmiskeskkondadesse jõuavad ainult volitatud mudelid, mille terviklikkus on kontrollitud.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Enne juurutamist tuleb veenduda, et kõik mudeli artefaktid (kaalud, konfiguratsioonid, tokeniseerijad) on krüptograafiliselt allkirjastatud volitatud üksuste poolt.                                       |   1   | D/V  |
| 3.1.2 | Kontrollige, et mudeli terviklikkust kinnitatakse juurutamise ajal ning allkirja kontrolli tõrked takistavad mudeli laadimist.                                                                             |   1   | D/V  |
| 3.1.3 | Kontrollige, et mudeli päritolu kirjed sisaldaksid volitava üksuse identiteeti, treeningandmete kontrolltihendeid, valideerimiskatsete tulemusi koos läbitud/eelidatud staatusega ning loomise ajatemplit. |   2   | D/V  |
| 3.1.4 | Kontrolli, kas kõik mudeli artefaktid kasutavad semantilist versioonihaldust (PEAMINE.VÄHENE.PARANDUS) koos dokumenteeritud kriteeriumidega, mis määravad, millal iga versioonikomponent suureneb.         |   2   | D/V  |
| 3.1.5 | Kinnitage, et sõltuvuste jälgimine hoiab reaalajas inventuuri, mis võimaldab kiiret kõiki tarbivaid süsteeme tuvastamist.                                                                                  |   2   |  V   |

---

## C3.2 Mudeli valideerimine ja testimine

Mudelit peavad enne juurutamist läbima määratletud turbe- ja ohutusvalidatsioonid.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Kontrollige, et mudelid läbiksid automatiseeritud turvatestid, mis hõlmavad sisendi valideerimist, väljundi puhastamist ja ohutushindamisi eelnevalt kokkulepitud organisatsiooni läviväärtuste alusel enne kasutuselevõttu. |   1   | D/V  |
| 3.2.2 | Kinnitage, et valideerimisvead blokeerivad mudeli juurutamise automaatselt pärast eelnevalt määratud volitatud isikute selgesõnalist ülekirjutamise kinnitust koos dokumenteeritud ärilistel põhjustel.                      |   1   | D/V  |
| 3.2.3 | Kinnitage, et testitulemused on krüptograafiliselt allkirjastatud ja jäävalt seotud konkreetse valideeritava mudeliversiooni räsi (hash) väärtusega.                                                                         |   2   |  V   |
| 3.2.4 | Kinnitage, et hädaolukorras kasutusele võtmine nõuab dokumenteeritud turvariski hindamist ja eelnevalt määratud turvaameti kinnitust kokkulepitud aja jooksul.                                                               |   2   | D/V  |

---

## C3.3 Kontrollitud juurutamine ja tagasipööramine

Mudelite juurutamist peab kontrollima, jälgima ja olema tagasipööratav.

|   #   | Description                                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Kontrollige, et tootmisjuurutused rakendaksid järkjärgulise kasutuselevõtu mehhanisme (kanarilendude juurutused, sinise-rohelise juurutuse mudelid) koos automaatsete tagasikerimise käivitajatega, mis põhinevad eelnevalt kokkulepitud vigade määradel, latentsuspiiridel või turvahoiatuste kriteeriumidel. |   1   |  D   |
| 3.3.2 | Kontrollige, et tagasipööramise võimalused taastaksid täieliku mudeli oleku (kaalud, konfiguratsioonid, sõltuvused) aatomiliselt ette määratud organisatsiooni ajavahemike jooksul.                                                                                                                            |   1   | D/V  |
| 3.3.3 | Kinnitage, et juurutusprotsessid kontrollivad krüptograafilisi allkirju ja arvutavad terviklikkuse kontrollsummasid enne mudeli aktiveerimist, ebaõnnestudes juurutamine mistahes sobimatusel.                                                                                                                 |   2   | D/V  |
| 3.3.4 | Kinnitage, et hädaolukorra mudeli väljalülitamise funktsioonid suudavad mudeli lõpp-punktid määratletud reageerimisaja jooksul keelata, kasutades automatiseeritud ahelkatkestajaid või käsitsi väljalülitamise lüliteid.                                                                                      |   2   | D/V  |
| 3.3.5 | Kinnitage, et tagasipööramise artifaktid (varasemad mudeliversioonid, konfiguratsioonid, sõltuvused) säilitatakse vastavalt organisatsiooni poliitikatele kasutades muutumatut salvestust intsidentidele reageerimiseks.                                                                                       |   2   |  V   |

---

## C3.4 Vastutuse ja auditeerimise muutmine

Kõik mudeli elutsükli muudatused peavad olema jälgitavad ja auditeeritavad.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Kontrollige, et kõik mudeli muudatused (juurutamine, konfiguratsioon, kõrvaldamine) genereerivad muutumatud auditeerimisandmed, mis sisaldavad ajatemplit, autentitud tegija identiteeti, muudatuse tüüpi ning enne ja pärast olekuid. |   1   |  V   |
| 3.4.2 | Kinnitage, et auditeerimislogi juurde pääsemiseks on vaja asjakohast autoriseerimist ning kõik ligipääsusündmused logitakse koos kasutaja identiteedi ja ajatemplïga.                                                                |   2   | D/V  |
| 3.4.3 | Kinnitage, et käsu mallid ja süsteemisõnumid on versioonihalduses git-hoidlates ning nende juurutamiseks on kohustuslik koodi ülevaatus ja ettenähtud hindajate heakskiit.                                                             |   2   | D/V  |
| 3.4.4 | Kinnitage, et auditi kirjed sisaldavad piisavalt üksikasju (mudeli räside, konfiguratsiooni hetktõmmised, sõltuvuste versioonid), et võimaldada mudeli oleku täielikku taastamist mis tahes ajahetkel säilitustähtaja jooksul.         |   2   |  V   |

---

## C3.5 Turvalise arendamise tavad

Mudeliarendus- ja treeninguprotsessid peavad järgima turvalisi põhimõtteid, et vältida kompromiteerimist.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.5.1 | Kinnitage, et mudeli arenduse, testimise ja tootmise keskkonnad on füüsiliselt või loogiliselt eraldatud. Neil puudub ühine infrastruktuur, neil on erinevad juurdepääsukontrollid ning isoleeritud andmelaod.           |   1   |  D   |
| 3.5.2 | Veenduge, et mudeli koolitus ja täiendõpe toimuvad isoleeritud keskkondades, kus on kontrollitud võrguühendus.                                                                                                           |   1   |  D   |
| 3.5.3 | Kontrollige, et treeningandmete allikaid oleks enne mudeli arendamist valideeritud terviklikkuse kontrollide abil ja autentitud usaldusväärsete allikate kaudu, millel on dokumenteeritud omandiahel.                    |   1   | D/V  |
| 3.5.4 | Kinnitage, et mudeli arenduse artefaktid (hüperparameetrid, treeninguskriptid, konfiguratsioonifailid) on salvestatud versioonihalduses ning nende kasutamine treeningprotsessis nõuab eakaaslaste ülevaatuse kinnitust. |   2   |  D   |

---

## C3.6 Mudeli pensionile jäämine ja kasutusest kõrvaldamine

Mudeleid tuleb turvaliselt kõrvaldada, kui neid enam ei vajata või kui tuvastatakse turvaprobleeme.

|   #   | Description                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Kontrollige, kas mudeli pensionile jäämise protsessid skannivad automaatselt sõltuvusgraafikuid, tuvastavad kõik kasutavad süsteemid ja annavad enne mahavõtmist eelnevalt kokkulepitud etteteatamistähtajad.                                   |   1   |  D   |
| 3.6.2 | Kinnitage, et pensionile jäänud mudeli artefaktid kustutatakse turvaliselt krüptograafilise kustutamise või mitmekordse ülekirjutamisega vastavalt dokumenteeritud andmete säilitamise poliitikatele, kasutades kinnitatud hävitamistunnistusi. |   1   | D/V  |
| 3.6.3 | Kindlustage, et mudelite eemaldamise sündmused logitakse koos ajatempli ja tegevust sooritava isiku identiteediga ning mudeli allkirjad tühistatakse taaskasutuse vältimiseks.                                                                  |   2   |  V   |
| 3.6.4 | Kinnitage, et hädaolukorra mudeli kõrvaldamine suudab mudeli juurdepääsu keelata eelnevalt kindlaksmääratud hädaolukorra reageerimistähtaegade jooksul automaatsete katkestuslülitite abil, kui avastatakse kriitilised turvanõrkused.          |   2   | D/V  |

---

## Viited

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

