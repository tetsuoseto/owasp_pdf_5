# C13 Žmogiškoji priežiūra, atsakomybė ir valdymas

## Valdymo tikslas

Šis skyrius pateikia reikalavimus, užtikrinančius žmogaus priežiūrą ir aiškius atsakomybės grandines dirbtinio intelekto sistemose, užtikrinant paaiškinamumą, skaidrumą ir etišką valdymą viso DI gyvavimo ciklo metu.

---

## C13.1 Išjungimo mygtuko ir perjungimo mechanizmai

Pateikite išjungimo arba atstatymo veiksmus, kai pastebimas pavojingas DI sistemos elgesys.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.1.1 | Patikrinkite, ar egzistuoja rankinis atjungimo jungiklio mechanizmas, leidžiantis nedelsiant sustabdyti DI modelio spėjimus ir rezultatus. |   1   | D/V  |
| 13.1.2 | Patikrinkite, ar valdymo perrašymo priemonės yra prieinamos tik autorizuotam personalui.                                                   |   1   |  D   |
| 13.1.3 | Patikrinkite, ar atšaukimo procedūros gali grąžinti ankstesnes modelio versijas arba saugaus režimo veikimą.                               |   3   | D/V  |
| 13.1.4 | Patikrinkite, ar persistumdymo mechanizmai yra reguliariai testuojami.                                                                     |   3   |  V   |

---

## C13.2 Žmogiškoji sprendimų priėmimo kontrolės taškai

Reikalauti žmogaus patvirtinimų, kai rizikos lygis viršija iš anksto nustatytas ribas.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.2.1 | Patikrinkite, ar didelės rizikos DI sprendimai reikalauja aiškaus žmogaus patvirtinimo prieš juos vykdant.                                       |   1   | D/V  |
| 13.2.2 | Patikrinkite, ar rizikos slenksčiai yra aiškiai apibrėžti ir automatiškai sukelia žmogaus peržiūros darbo eigas.                                 |   1   |  D   |
| 13.2.3 | Patikrinkite, ar laiku jautrūs sprendimai turi atsarginius veiksmų planus, kai žmogaus patvirtinimo negalima gauti per reikiamus terminus.       |   2   |  D   |
| 13.2.4 | Patikrinkite, ar eskalavimo procedūros apibrėžia aiškius įgaliojimų lygius skirtingiems sprendimų tipams arba rizikos kategorijoms, jei taikoma. |   3   | D/V  |

---

## C13.3 Atsakomybės grandinė ir audito galimybė

Registruokite operatoriaus veiksmus ir modelio sprendimus.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Patikrinkite, ar visi DI sistemos sprendimai ir žmogaus įsikišimai yra registruojami su laiko žymomis, naudotojo tapatybe ir sprendimų pagrindimu. |   1   | D/V  |
| 13.3.2 | Patikrinkite, ar audito žurnalų negalima klastoti, ir įtraukite vientisumo patikros mechanizmus.                                                   |   2   |  D   |

---

## C13.4 Paaiškinama DI technikos

Paviršinio bruožo svarba, kontrafaktiniai atvejai ir vietinės paaiškinimai.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Patikrinkite, ar DI sistemos pateikia pagrindinius savo sprendimų paaiškinimus žmogui suprantama forma.                                                                   |   1   | D/V  |
| 13.4.2 | Patikrinkite, ar paaiškinimų kokybė yra patvirtinta per žmonių vertinimo tyrimus ir metrikas.                                                                             |   2   |  V   |
| 13.4.3 | Patikrinkite, ar svarbių sprendimų atveju yra prieinami funkcijų svarbos balai arba priskyrimo metodai (SHAP, LIME ir kt.).                                               |   3   | D/V  |
| 13.4.4 | Patikrinkite, ar kontrafaktinės paaiškinimų metodikos rodo, kaip įvestys galėtų būti pakeistos siekiant pakeisti rezultatus, jei tai taikoma naudojimo atveju ir sričiai. |   3   |  V   |

---

## C13.5 Modelių kortelės ir naudojimo atskleidimai

Palaikykite modelių korteles, kuriose nurodomos numatytos panaudojimo sritys, našumo rodikliai ir etiniai svarstymai.

|   #    | Description                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.5.1 | Patikrinkite, ar modelio kortelės dokumentuoja numatytas naudojimo sritis, apribojimus ir žinomas gedimų formas.                                                                                       |   1   |  D   |
| 13.5.2 | Patikrinkite, ar atskleidžiami našumo rodikliai skirtinguose taikomuose naudojimo atvejuose.                                                                                                           |   1   | D/V  |
| 13.5.3 | Patikrinkite, ar etiniai apsvarstymai, šališkumo vertinimai, teisingumo įvertinimai, mokymo duomenų charakteristikos ir žinomi mokymo duomenų apribojimai yra dokumentuoti ir reguliariai atnaujinami. |   2   |  D   |
| 13.5.4 | Patikrinkite, ar modelių kortelės yra versijomis valdomos ir prižiūrimos viso modelio gyvavimo ciklo metu su pakeitimų sekimu.                                                                         |   2   | D/V  |

---

## C13.6 Neapibrėžtumo kiekybinimas

Skleiskite pasitikėjimo balus arba entropijos matavimus atsakymuose.

|   #    | Description                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Patikrinkite, ar DI sistemos pateikia pasitikėjimo vertinimus arba neapibrėžtumo matavimus su savo rezultatais.   |   1   |  D   |
| 13.6.2 | Patikrinkite, ar neapibrėžtumo slenksčiai sukelia papildomą žmogaus peržiūrą arba alternatyvius sprendimų kelius. |   2   | D/V  |
| 13.6.3 | Patikrinkite, ar nežinomybės kiekybinimo metodai yra kalibruoti ir patvirtinti pagal tikrųjų duomenų rezultatus.  |   2   |  V   |
| 13.6.4 | Patikrinkite, ar neapibrėžtumo sklaida išlaikoma per daugiaetapius DI darbo eigas.                                |   3   | D/V  |

---

## C13.7 Vartotojams skirtos skaidrumo ataskaitos

Teikti periodines ataskaitas apie incidentus, nukrypimus ir duomenų naudojimą.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.7.1 | Patikrinkite, ar duomenų naudojimo politikos ir vartotojų sutikimo valdymo praktikos yra aiškiai perduodamos suinteresuotosioms šalims.          |   1   | D/V  |
| 13.7.2 | Patikrinkite, ar atliekami DI poveikio vertinimai ir ar jų rezultatai įtraukiami į ataskaitas.                                                   |   2   | D/V  |
| 13.7.3 | Patikrinkite, ar reguliariai paskelbiamos skaidrumo ataskaitos pakankamai detaliai atskleidžia dirbtinio intelekto įvykius ir veiklos rodiklius. |   2   | D/V  |

### Nuorodos

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

