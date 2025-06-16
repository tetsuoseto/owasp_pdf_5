# C13 Emberi felügyelet, elszámoltathatóság és irányítás

## Ellenőrzési célkitűzés

Ez a fejezet előírja az emberi felügyelet és a világos elszámoltathatósági láncok fenntartásának követelményeit az MI-rendszerekben, biztosítva az átláthatóságot, magyarázhatóságot és etikai irányítást az MI életciklusa során.

---

## C13.1 Vészleállító és felülbírálati mechanizmusok

Biztosítson leállítási vagy visszagörgetési lehetőségeket, amikor az AI rendszer nem biztonságos viselkedése észlelhető.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Ellenőrizze, hogy létezik-e egy kézi vészleállító mechanizmus az AI modell következtetésének és kimeneteinek azonnali leállítására. |   1   | D/V  |
| 13.1.2 | Ellenőrizze, hogy a felülírási vezérlők csak az arra jogosult személyek számára legyenek hozzáférhetők.                             |   1   |  D   |
| 13.1.3 | Ellenőrizze, hogy a visszaállítási eljárások képesek-e visszatérni korábbi modellverziókhoz vagy biztonságos módú műveletekhez.     |   3   | D/V  |
| 13.1.4 | Ellenőrizze, hogy a felülírási mechanizmusokat rendszeresen tesztelik-e.                                                            |   3   |  V   |

---

## C13.2 Ember a ciklusban döntési ellenőrzőpontok

Emberi jóváhagyásokat igényel, amikor a tét meghaladja az előre meghatározott kockázati küszöböket.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Ellenőrizze, hogy a magas kockázatú MI-döntések végrehajtása előtt egyértelmű emberi jóváhagyás szükséges-e.                                                                 |   1   | D/V  |
| 13.2.2 | Ellenőrizze, hogy a kockázati küszöbértékek egyértelműen definiáltak-e, és automatikusan elindítják-e az emberi felülvizsgálati munkafolyamatokat.                           |   1   |  D   |
| 13.2.3 | Ellenőrizze, hogy az időérzékeny döntések esetén léteznek-e tartalék eljárások, ha az emberi jóváhagyás a szükséges határidőn belül nem szerezhető be.                       |   2   |  D   |
| 13.2.4 | Ellenőrizze, hogy a fokozásra vonatkozó eljárások egyértelmű hatásköröket határoznak-e meg a különböző döntéstípusokra vagy kockázati kategóriákra, amennyiben alkalmazható. |   3   | D/V  |

---

## C13.3 Felelősségi Lánc és Auditálhatóság

Naplózza az operátori műveleteket és a modell döntéseit.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Ellenőrizze, hogy minden MI-rendszer döntést és emberi beavatkozást időbélyeggel, felhasználói azonosságokkal és döntési indokolással rögzítenek-e. |   1   | D/V  |
| 13.3.2 | Ellenőrizze, hogy a naplózási adatok nem hamisíthatók-e meg, és tartalmaznak-e integritás-ellenőrzési mechanizmusokat.                              |   2   |  D   |

---

## C13.4 Magyarázható mesterséges intelligencia (Explainable-AI) technikák

Felületi jellemző fontosság, ellen-tények és helyi magyarázatok.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Ellenőrizze, hogy a mesterséges intelligencia rendszerek alapvető magyarázatokat adnak-e döntéseikről ember által olvasható formátumban.                                                                       |   1   | D/V  |
| 13.4.2 | Ellenőrizze, hogy a magyarázat minőségét emberi értékelési tanulmányok és metrikák segítségével igazolták-e.                                                                                                   |   2   |  V   |
| 13.4.3 | Ellenőrizze, hogy a fontos döntésekhez rendelkezésre állnak-e a jellemzőfontossági pontszámok vagy hozzárendelési módszerek (SHAP, LIME stb.).                                                                 |   3   | D/V  |
| 13.4.4 | Ellenőrizze, hogy a kontrafaktuális magyarázatok megmutatják-e, hogyan lehet az inputokat módosítani az eredmények megváltoztatásához, amennyiben ez alkalmazható az adott felhasználási esetben és területen. |   3   |  V   |

---

## C13.5 Modellkártyák és használati nyilatkozatok

Tartsa karban a modellek kártyáit a tervezett felhasználásról, a teljesítménymutatókról és az etikai megfontolásokról.

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.5.1 | Ellenőrizze, hogy a modellkártyák dokumentálják-e a tervezett használati eseteket, korlátozásokat és ismert hibamódokat.                                                                                           |   1   |  D   |
| 13.5.2 | Ellenőrizze, hogy a különböző alkalmazható használati esetekre vonatkozó teljesítménymutatók nyilvánosságra vannak-e hozva.                                                                                        |   1   | D/V  |
| 13.5.3 | Ellenőrizze, hogy az etikai megfontolások, az elfogultságértékelések, a méltányossági vizsgálatok, a képzési adatok jellemzői és a képzési adatok ismert korlátai dokumentálva vannak-e és rendszeresen frissítve. |   2   |  D   |
| 13.5.4 | Ellenőrizze, hogy a modellkártyák verziókezelték-e és karbantartották-e a modell életciklusa során változáskövetéssel.                                                                                             |   2   | D/V  |

---

## C13.6 Bizonytalanság kvantifikálása

Terjessze a bizalmi pontszámokat vagy entrópia-mutatókat a válaszokban.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.6.1 | Ellenőrizze, hogy a mesterséges intelligencia rendszerek megbízhatósági pontszámokat vagy bizonytalansági mértékeket adnak-e az eredményeikkel együtt. |   1   |  D   |
| 13.6.2 | Ellenőrizze, hogy a bizonytalansági küszöbértékek további emberi felülvizsgálatot vagy alternatív döntési útvonalakat váltanak-e ki.                   |   2   | D/V  |
| 13.6.3 | Ellenőrizze, hogy a bizonytalansági kvantifikációs módszerek kalibráltak és a valós adatok alapján validáltak-e.                                       |   2   |  V   |
| 13.6.4 | Ellenőrizze, hogy a bizonytalanság terjedése megmarad-e a többlépéses AI munkafolyamatokon keresztül.                                                  |   3   | D/V  |

---

## C13.7 Felhasználói átláthatósági jelentések

Rendszeres tájékoztatást kell nyújtani az incidensekről, az eltérésekről és az adatok használatáról.

|   #    | Description                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Ellenőrizze, hogy az adatfelhasználási irányelveket és a felhasználói hozzájárulás-kezelési gyakorlatokat egyértelműen kommunikálják az érintettek felé.      |   1   | D/V  |
| 13.7.2 | Ellenőrizze, hogy az AI hatásvizsgálatokat elvégezték-e, és az eredményeket beillesztették-e a jelentésekbe.                                                  |   2   | D/V  |
| 13.7.3 | Ellenőrizze, hogy a rendszeresen közzétett átláthatósági jelentések ésszerű részletességgel közlik-e az MI-vel kapcsolatos eseményeket és működési mutatókat. |   2   | D/V  |

### Hivatkozások

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

