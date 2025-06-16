# C3 modelio gyvavimo ciklo valdymas ir pakeitimų kontrolė

## Valdymo tikslas

DI sistemos turi įdiegti pakeitimų valdymo procesus, kurie užkerta kelią neautorizuotiems ar nesaugiai modelio pakeitimams patekti į gamybą. Ši kontrolė užtikrina modelio vientisumą viso gyvavimo ciklo metu – nuo vystymo iki diegimo ir pašalinimo – kas leidžia greitai reaguoti į incidentus ir išlaikyti atsakomybę už visus pakeitimus.

Pagrindinis saugumo tikslas: į gamybą pristatyti tik įgaliotus, patvirtintus modelius, naudojant kontroliuojamus procesus, kurie užtikrina vientisumą, atsekamumą ir atkuriamumą.

---

## C3.1 Modelio autorizacija ir vientisumas

Į gamybos aplinką patenka tik autorizuoti modeliai, kurių vientisumas patvirtintas.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Prieš diegiant įsitikinkite, kad visi modelio artefaktai (svoriai, konfigūracijos, žodynai) yra kriptografiškai pasirašyti autorizuotų subjektų.                                                                |   1   | D/V  |
| 3.1.2 | Patikrinkite, ar modelio vientisumas yra patvirtinamas diegimo metu ir ar nepavykus parašo patikrinimui modelis neįkeliamas.                                                                                    |   1   | D/V  |
| 3.1.3 | Patikrinkite, ar modelio kilmės įrašai apima autorizuotos institucijos tapatybę, mokymo duomenų kontrolinių sumų reikšmes, patvirtinimo testų rezultatus su praėjimo/nepraėjimo statusu ir sukūrimo laiko žymą. |   2   | D/V  |
| 3.1.4 | Patikrinkite, ar visi modelio artefaktai naudoja semantinį versijavimą (MAJOR.MINOR.PATCH) su dokumentuotais kriterijais, nurodančiais, kada kiekvienas versijos komponentas turi būti didinamas.               |   2   | D/V  |
| 3.1.5 | Patikrinkite, ar priklausomybių sekimas palaiko realaus laiko atsargų sąrašą, leidžiantį greitai identifikuoti visas vartojančias sistemas.                                                                     |   2   |  V   |

---

## C3.2 Modelio patvirtinimas ir testavimas

Modeliai turi praeiti apibrėžtus saugumo ir patikimumo patikrinimus prieš diegiant.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Patikrinkite, ar modeliai praeina automatizuotus saugumo bandymus, įskaitant įvesties patvirtinimą, išvesties valymą ir saugumo įvertinimus pagal iš anksto sutartus organizacijos priėmimo/atmetimo ribinius rodiklius prieš diegiant. |   1   | D/V  |
| 3.2.2 | Patikrinkite, ar patvirtinimo klaidos automatiškai blokuoja modelio diegimą po aiškaus patvirtinimo iš anksto paskirtų įgaliotų asmenų, turinčių dokumentuotus verslo pagrindimus.                                                      |   1   | D/V  |
| 3.2.3 | Patikrinkite, ar testo rezultatai yra kriptografiškai pasirašyti ir nekeičiami susieti su konkretaus verifikuojamo modelio versijos hešu.                                                                                               |   2   |  V   |
| 3.2.4 | Patikrinkite, ar avariniai įdiegimai reikalauja dokumentuotos saugumo rizikos vertinimo ir patvirtinimo iš iš anksto paskirtos saugumo institucijos per iš anksto sutartus terminus.                                                    |   2   | D/V  |

---

## C3.3 Valdomas diegimas ir grąžinimas atgal

Modelių diegimas privalo būti kontroliuojamas, stebimas ir grįžtamas.

|   #   | Description                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Patikrinkite, ar gamybos diegimai įgyvendina palaipsniui vykdomus diegimo mechanizmus (canary diegimai, mėlyna-žalia diegimai) su automatizuotais grąžinimo trigeriais, pagrįstais iš anksto sutartais klaidų lygiais, delsos slenksčiais ar saugumo įspėjimų kriterijais. |   1   |  D   |
| 3.3.2 | Patikrinkite, ar atkūrimo galimybės atkuria visą modelio būseną (svorius, konfigūracijas, priklausomybes) atominiu būdu iš anksto nustatytu organizacijos laiko intervale.                                                                                                 |   1   | D/V  |
| 3.3.3 | Patikrinkite, ar diegimo procesai tikrina kriptografines parašus ir apskaičiuoja integralumo kontrolines sumas prieš aktyvuojant modelį, ir nutraukia diegimą, jei aptinkama neatitikimų.                                                                                  |   2   | D/V  |
| 3.3.4 | Patikrinkite, ar neatidėliotinos modelio sustabdymo galimybės gali išjungti modelio galus per iš anksto apibrėžtą reagavimo laiką, naudojant automatinius grandinių pertraukiklius arba rankinius sustabdymo jungiklius.                                                   |   2   | D/V  |
| 3.3.5 | Patikrinkite, ar atšaukimo artefaktai (ankstesnės modelio versijos, konfigūracijos, priklausomybės) yra saugomi pagal organizacijos politiką nekeičiamos saugyklos principu, skirtu incidentų valdymui.                                                                    |   2   |  V   |

---

## C3.4 Atsakomybės ir audito keitimas

Visi modelio gyvavimo ciklo pakeitimai turi būti sekami ir audituojami.

|   #   | Description                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Patikrinkite, ar visi modelio pakeitimai (paleidimas, konfigūracija, pasitraukimas) generuoja nekeičiamos auditorijos įrašus, įskaitant laiko žymą, autentifikuoto veiksmo atlikėjo tapatybę, pakeitimo tipą ir būsenas prieš ir po pakeitimo.  |   1   |  V   |
| 3.4.2 | Patikrinkite, ar prieiga prie audito žurnalo reikalauja tinkamos autorizacijos ir ar visi prieigos bandymai yra registruojami su vartotojo tapatybe ir laiko žyma.                                                                              |   2   | D/V  |
| 3.4.3 | Patikrinkite, ar užklausų šablonai ir sistemos pranešimai yra valdomi versijų kontrolės sistemoje git saugyklose, kur reikalingas privalomas kodo peržiūrėjimas ir patvirtinimas iš paskirtų peržiūrėtojų prieš diegiant.                       |   2   | D/V  |
| 3.4.4 | Patikrinkite, ar audito įrašai apima pakankamai detalių (modelių maišos, konfigūracijos momentinės nuotraukos, priklausomybių versijos), kad būtų galima visiškai atkurti modelio būseną bet kuriuo laiko momentu saugojimo laikotarpio viduje. |   2   |  V   |

---

## C3.5 Saugios kūrimo praktikos

Modelio kūrimo ir mokymo procesai turi laikytis saugių praktikų siekiant išvengti pažeidimų.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Patikrinkite, ar modelio kūrimo, testavimo ir gamybos aplinkos yra fiziškai arba logiškai atskirtos. Jos neturi bendros infrastruktūros, turi atskiras prieigos kontrolės priemones ir izoliuotas duomenų saugyklas. |   1   |  D   |
| 3.5.2 | Patikrinkite, ar modelio mokymas ir smulkus reguliavimas vyksta izoliuotose aplinkose su kontroliuojama tinklo prieiga.                                                                                              |   1   |  D   |
| 3.5.3 | Patikrinkite, ar mokymo duomenų šaltiniai yra patvirtinti atliekant vientisumo patikrinimus ir autentifikuoti per patikimus šaltinius su dokumentuotu grandinės valdymu prieš naudojimą modelio kūrime.              |   1   | D/V  |
| 3.5.4 | Patikrinkite, ar modelio kūrimo artefaktai (hiperparametrai, treniruočių scenarijai, konfigūracijos failai) yra saugomi versijų kontrolėje ir reikalauja kolegų peržiūros patvirtinimo prieš naudojimą treniruotėje. |   2   |  D   |

---

## C3.6 Modelio pensija ir nutraukimas

Modeliai privalo būti saugiai pašalinami, kai jų nebereikia arba kai nustatomi saugumo trūkumai.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.6.1 | Patikrinkite, ar modelio nutraukimo procesai automatiškai nuskenuoja priklausomybių grafus, identifikuoja visus naudojančius sistemas ir pateikia iš anksto sutartus įspėjimo terminus prieš dekomisijavimą.                   |   1   |  D   |
| 3.6.2 | Patikrinkite, ar nebenaudojami modelio artefaktai yra saugiai ištrinti naudojant kriptografinį naikinimą arba kelis perrašymus pagal dokumentuotas duomenų saugojimo politiką, patvirtintas naikinimo sertifikatais.           |   1   | D/V  |
| 3.6.3 | Patikrinkite, ar modelio pašalinimo įvykiai užfiksuoti su laiko žyma ir veiksmo atlikėjo tapatybe, taip pat ar modelio parašai atšaukti, siekiant užkirsti kelią pakartotiniam naudojimui.                                     |   2   |  V   |
| 3.6.4 | Patikrinkite, ar avarinis modelio pasitraukimas gali išjungti modelio prieigą per iš anksto nustatytus avarinio reagavimo laikotarpius naudojant automatizuotus išjungimo jungiklius, jei aptinkamos kritinės saugumo spragos. |   2   | D/V  |

---

## Nuorodos

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

