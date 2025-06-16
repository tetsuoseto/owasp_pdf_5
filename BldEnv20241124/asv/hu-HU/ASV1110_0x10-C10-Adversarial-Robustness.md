# 10 Ellenséges robusztusság és adatvédelmi védelem

## Ellenőrzési célkitűzés

Biztosítsuk, hogy az MI modellek megbízhatóak, adatvédelmet megtartók és visszaélések elleni védettek maradjanak, amikor kerülési, következtetési, kivonási vagy mérgezési támadásokkal szembesülnek.

---

## 10.1 Modellkövetés és biztonság

Óvd meg a káros vagy a szabályzatot sértő kimenetek ellen.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.1.1 | Ellenőrizze, hogy az összehangolási tesztcsomag (red-team parancsok, jailbreak próbasorok, tiltott tartalom) verziókezelve van-e, és minden modellkiadásnál futtatják-e. |   1   | D/V  |
| 10.1.2 | Ellenőrizze, hogy a visszautasítási és biztonságos befejezési védősávok érvényesülnek-e.                                                                                 |   1   |  D   |
| 10.1.3 | Ellenőrizze, hogy az automatizált értékelő mérje a káros tartalom arányát, és jelezze a küszöbértéket meghaladó visszaeséseket.                                          |   2   | D/V  |
| 10.1.4 | Ellenőrizze, hogy az ellen-jailbreak képzés dokumentált és reprodukálható-e.                                                                                             |   2   |  D   |
| 10.1.5 | Ellenőrizze, hogy a formális szabályzati megfelelőségi bizonyítékok vagy a tanúsított megfigyelés lefedik-e a kritikus területeket.                                      |   3   |  V   |

---

## 10.2 Ellenséges példa elleni megerősítés

Növelje a manipulált bemenetekkel szembeni ellenállóképességet. A robusztus adverszáriális tanítás és a benchmark pontozás jelenleg a legjobb gyakorlat.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.2.1 | Ellenőrizze, hogy a projekt adattárai tartalmaznak-e ellenséges tanítással kapcsolatos konfigurációkat reprodukálható véletlenszám-generátor magokkal. |   1   |  D   |
| 10.2.2 | Ellenőrizze, hogy a támadópélda-felismerés figyelmeztető blokkoló jelzéseket ad-e a gyártási folyamatokban.                                            |   2   | D/V  |
| 10.2.4 | Ellenőrizze, hogy a tanúsított-robusság bizonyítások vagy intervallumhatár tanúsítványok legalább a legkritikusabb osztályokat lefedik-e.              |   3   |  V   |
| 10.2.5 | Ellenőrizze, hogy a regressziós tesztek adaptív támadásokat használnak-e annak megerősítésére, hogy nincs mérhető robusztusságveszteség.               |   3   |  V   |

---

## 10.3 Tagság-inferenciás támadások csökkentése

Korlátozza annak lehetőségét, hogy eldöntsék, egy rekord szerepelt-e a tanító adatok között. A differenciális adatvédelem és a bizalmi pontszám maszkolása továbbra is a leghatékonyabb ismert védekezési módszerek.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Ellenőrizze, hogy az egyes lekérdezések szerinti entrópia szabályozás vagy a hőmérséklet-skálázás csökkenti-e a túlzottan magabiztos előrejelzéseket. |   1   |  D   |
| 10.3.2 | Ellenőrizze, hogy a tanítás ε-korlátozott differenciálisan privát optimalizációt alkalmaz-e érzékeny adatkészletek esetében.                          |   2   |  D   |
| 10.3.3 | Ellenőrizze, hogy a támadási szimulációk (árnyékmodell vagy fekete dobozos) támadási AUC értéke ≤ 0,60 legyen a külön tartott adatokon.               |   2   |  V   |

---

## 10.4 Modell-inverzió elleni ellenállás

Meg kell akadályozni a privát attribútumok rekonstrukcióját. A legújabb felmérések a kimenet levágását és a DP garanciákat hangsúlyozzák, mint gyakorlati védekezéseket.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Győződjön meg arról, hogy az érzékeny attribútumokat soha ne adják közvetlenül ki; ahol szükséges, használjon tartományokat vagy egyirányú átalakításokat. |   1   |  D   |
| 10.4.2 | Ellenőrizze, hogy a lekérdezési aránykorlátok korlátozzák-e az ismétlődő, adaptív lekérdezéseket ugyanattól a jogosulttól.                                 |   1   | D/V  |
| 10.4.3 | Ellenőrizze, hogy a modellt adatvédelmet biztosító zajjal képezték-e.                                                                                      |   2   |  D   |

---

## 10.5 Modellkivonás elleni védelem

Azonosítsa és akadályozza meg az engedély nélküli klónozást. Javasolt a vízjelzés és a lekérdezési mintaelemzés alkalmazása.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.5.1 | Ellenőrizze, hogy az inferencia átjárók betartják-e a globális és az egyes API-kulcsokra vonatkozó korlátokat, amelyek a modell memorizálási küszöbéhez vannak hangolva. |   1   |  D   |
| 10.5.2 | Ellenőrizze, hogy a lekérdezési entrópia és a bemeneti plurális statisztikák táplálják-e az automatikus kinyerő detektort.                                               |   2   | D/V  |
| 10.5.3 | Ellenőrizze, hogy a törékeny vagy valószínűségi vízjeleket p < 0,01 szinten igazolni lehet-e legfeljebb 1 000 lekérdezés során a gyanúsított klón ellen.                 |   2   |  V   |
| 10.5.4 | Ellenőrizze, hogy a vízjel kulcsok és a kiváltó készletek hardverbiztonsági modulban vannak tárolva, és évente forgatva vannak.                                          |   3   |  D   |
| 10.5.5 | Ellenőrizze, hogy az extraction-alert események tartalmazzák-e a szabályszegő lekérdezéseket, és integrálva vannak-e az incidens-válasz játékkönyvekkel.                 |   3   |  V   |

---

## 10.6 Feltételezés idejű mérgezett adatok detektálása

Azonosítsa és semlegesítse a hátsóajtós vagy mérgezett bemeneteket.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Ellenőrizze, hogy a bemenetek áthaladnak-e egy anomáliaészlelőn (pl. STRIP, konzisztencia-értékelés) a modell predikciója előtt.                                  |   1   |  D   |
| 10.6.2 | Ellenőrizze, hogy az érzékelő küszöbszintek tiszta/mérgezett validációs készleteken vannak-e beállítva, hogy kevesebb mint 5%-os hamis pozitív arányt érjenek el. |   1   |  V   |
| 10.6.3 | Ellenőrizze, hogy a mérgezettnek jelölt bemenetek kiváltják-e a lágy blokkolást és az emberi felülvizsgálati munkafolyamatokat.                                   |   2   |  D   |
| 10.6.4 | Ellenőrizze, hogy a detektorokat alkalmazkodó, trigger nélküli hátsóajtó támadásokkal stressztesztelik-e.                                                         |   2   |  V   |
| 10.6.5 | Ellenőrizze, hogy a detektálási hatékonysági mutatókat rögzítik-e, és rendszeresen újraértékelik-e friss fenyegetésinformációk alapján.                           |   3   |  D   |

---

## 10.7 Dinamikus biztonsági szabályzat adaptáció

Valós idejű biztonsági szabályzatfrissítések fenyegetésinformációk és viselkedéselemzés alapján.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Ellenőrizze, hogy a biztonsági szabályzatok dinamikusan frissíthetők-e az ügynök újraindítása nélkül, miközben megőrzik a szabályzat verziójának épségét.                    |   1   | D/V  |
| 10.7.2 | Ellenőrizze, hogy a szabályzatfrissítéseket az arra jogosult biztonsági személyzet kriptográfiailag aláírta-e, és alkalmazás előtt érvényesítették-e.                        |   2   | D/V  |
| 10.7.3 | Ellenőrizze, hogy a dinamikus irányelvváltoztatások teljes audit nyomvonalakkal vannak-e naplózva, beleértve az indoklást, jóváhagyási láncokat és visszavonási eljárásokat. |   2   | D/V  |
| 10.7.4 | Ellenőrizze, hogy az adaptív biztonsági mechanizmusok a kockázati kontextus és a viselkedési minták alapján állítják-e be a fenyegetésészlelés érzékenységét.                |   3   | D/V  |
| 10.7.5 | Ellenőrizze, hogy a szabályzat-alkalmazkodási döntések magyarázhatók-e, és tartalmaznak-e bizonyítékláncokat a biztonsági csapat átvizsgálásához.                            |   3   | D/V  |

---

## 10.8 Visszaverődés-alapú biztonsági elemzés

Biztonsági érvényesítés ágens önreflexiója és meta-kognitív elemzése révén.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Ellenőrizze, hogy az ügynök reflexió mechanizmusai tartalmazzák-e a döntések és cselekvések biztonságközpontú önértékelését.                                      |   1   | D/V  |
| 10.8.2 | Ellenőrizze, hogy a reflektált kimenetek érvényesítve vannak-e, hogy megakadályozzák az önértékelési mechanizmusok manipulálását támadó bemenetek által.          |   2   | D/V  |
| 10.8.3 | Ellenőrizze, hogy a metakognitív biztonsági elemzés azonosítja-e a potenciális elfogultságot, manipulációt vagy sérülékenységet az ügynök érvelési folyamataiban. |   2   | D/V  |
| 10.8.4 | Ellenőrizze, hogy a reflektív alapú biztonsági figyelmeztetések aktiválják-e a fokozott megfigyelést és a lehetséges emberi beavatkozási munkafolyamatokat.       |   3   | D/V  |
| 10.8.5 | Ellenőrizze, hogy a biztonsági visszatekintésekből származó folyamatos tanulás javítja-e a fenyegetések észlelését anélkül, hogy rontaná a jogos funkciókat.      |   3   | D/V  |

---

## 10.9 Fejlődés és Önjavító Biztonság

Biztonsági ellenőrzések az önmódosításra és fejlődésre képes ügynök rendszerek számára.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Ellenőrizze, hogy az önmódosító képességek korlátozottak-e kijelölt biztonságos területekre formális verifikációs határokkal.                       |   1   | D/V  |
| 10.9.2 | Győződjön meg arról, hogy a fejlesztési javaslatok biztonsági hatásvizsgálaton mennek keresztül a megvalósítás előtt.                               |   2   | D/V  |
| 10.9.3 | Ellenőrizze, hogy az önfejlesztő mechanizmusok tartalmaznak-e visszagörgetési képességeket integritásellenőrzéssel.                                 |   2   | D/V  |
| 10.9.4 | Ellenőrizze, hogy a meta-tanulás biztonsága megakadályozza-e a fejlődési algoritmusok elleni támadó manipulatív beavatkozást.                       |   3   | D/V  |
| 10.9.5 | Ellenőrizze, hogy a rekurzív önfejlesztés formális biztonsági korlátok által van-e határolva, konvergenciára vonatkozó matematikai bizonyításokkal. |   3   | D/V  |

---

### Hivatkozások

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

