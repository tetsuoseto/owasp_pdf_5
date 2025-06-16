# 11 Adatvédelem és személyes adatkezelés

## Vezérlési cél

Tartsa fenn a szigorú adatvédelmi biztosítékokat az AI teljes életciklusa során — gyűjtés, tanítás, következtetés és incidenskezelés — úgy, hogy a személyes adatokat csak világos hozzájárulással, a szükséges minimális mértékben, bizonyítható törléssel és hivatalos adatvédelmi garanciákkal dolgozzák fel.

---

## 11.1 Anonimizáció és adatminimalizálás

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Ellenőrizze, hogy a közvetlen és kvázi-azonosítók el lettek távolítva vagy kódolva (hash-elve).                                                                              |   1   | D/V  |
| 11.1.2 | Ellenőrizze, hogy az automatizált auditok mérik-e a k-anonimitást/l-sokféleséget, és figyelmeztetnek, amikor a küszöbértékek a szabályzat alattra esnek.                     |   2   | D/V  |
| 11.1.3 | Ellenőrizze, hogy a modell jellemző-importance jelentései igazolják-e, hogy az azonosító szivárgása nem haladja meg az ε = 0,01 kölcsönös információt.                       |   2   |  V   |
| 11.1.4 | Ellenőrizze, hogy a formális bizonyítékok vagy a szintetikus adatok tanúsítása szerint a visszaazonosítási kockázat ≤ 0,05 még összekapcsolási támadások esetén is teljesül. |   3   |  V   |

---

## 11.2 Az elfeledtetéshez való jog és a törlés végrehajtása

|   #    | Description                                                                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.2.1 | Ellenőrizze, hogy az adat alany törlési kérelmei továbbítódnak-e a nyers adatkészletekhez, ellenőrzőpontokhoz, beágyazásokhoz, naplókhoz és biztonsági mentésekhez 30 napon belüli szolgáltatási szint megállapodások szerint. |   1   | D/V  |
| 11.2.2 | Ellenőrizze, hogy a „gépi felejtés” rutinok fizikailag újraképeznek-e vagy megközelítő törlést hajtanak végre tanúsított felejtési algoritmusok alkalmazásával.                                                                |   2   |  D   |
| 11.2.3 | Ellenőrizze, hogy az árnyékmodell-értékelés bizonyítja-e, hogy a felejtett rekordok kevesebb mint 1%-ban befolyásolják a kimeneteket a felejtés után.                                                                          |   2   |  V   |
| 11.2.4 | Ellenőrizze, hogy a törlési események megváltoztathatatlanul rögzítve vannak-e, és megfelelnek-e a szabályozók általi auditálhatóságnak.                                                                                       |   3   |  V   |

---

## 11.3 Differenciálisan privát védelmi intézkedések

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Győződjön meg arról, hogy a privátosságvesztés-számítási irányítópultok riasztanak, amikor a kumulatív ε meghaladja a szabályzati küszöbértékeket. |   2   | D/V  |
| 11.3.2 | Ellenőrizze, hogy a feketedobozos adatvédelmi auditok az ε̂ értéket a deklarált érték 10%-án belül becslik-e.                                      |   2   |  V   |
| 11.3.3 | Ellenőrizze, hogy a hivatalos bizonyítások minden utólagos finomhangolást és beágyazást lefednek-e.                                                |   3   |  V   |

---

## 11.4 Célmeghatározás-korlátozás és Terjedelem-növekedés elleni védelem

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Ellenőrizze, hogy minden adatállomány és modellellenőrzőpont géppel olvasható célcímkével rendelkezzen, amely összhangban van az eredeti hozzájárulással.        |   1   |  D   |
| 11.4.2 | Ellenőrizze, hogy a futásidejű monitorok észlelik-e a nyilatkozott céllal ellentétes lekérdezéseket, és kiváltanak-e puha elutasítást.                           |   1   | D/V  |
| 11.4.3 | Ellenőrizze, hogy a kód alapú irányelvek akadályozzák-e a modellek új területekre történő újbóli telepítését DPIA felülvizsgálat nélkül.                         |   3   |  D   |
| 11.4.4 | Ellenőrizze, hogy a formális követhetőségi bizonyítékok igazolják-e, hogy minden személyes adat életciklusa a beleegyezéssel meghatározott keretek között marad. |   3   |  V   |

---

## 11.5 Hozzájárulás-kezelés és Jogalap-követés

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Ellenőrizze, hogy a Hozzájárulás-kezelési Platform (CMP) rögzíti-e az adatkezeléshez való hozzájárulás státuszát, célját és megőrzési idejét az egyes adat alanyokra vonatkozóan. |   1   | D/V  |
| 11.5.2 | Ellenőrizze, hogy az API-k kiteszik-e a hozzájárulási tokeneket; a modelleknek az előrejelzés előtt érvényesíteniük kell a token jogosultsági körét.                              |   2   |  D   |
| 11.5.3 | Ellenőrizze, hogy a megtagadott vagy visszavont hozzájárulás 24 órán belül leállítja-e a feldolgozási folyamatokat.                                                               |   2   | D/V  |

---

## 11.6 Szövetséges tanulás adatvédelmi szabályozásokkal

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Ellenőrizze, hogy az ügyfél-frissítések helyi differenciális adatvédelmi zajhozzáadást alkalmaznak-e az aggregálás előtt.        |   1   |  D   |
| 11.6.2 | Ellenőrizze, hogy a tanulási metrikák differenciálisan privátak legyenek, és soha ne fedjék fel egyetlen kliens veszteségét sem. |   2   | D/V  |
| 11.6.3 | Ellenőrizze, hogy a mérgezés-ellenálló aggregáció (például Krum/Trimmed-Mean) engedélyezve van-e.                                |   2   |  V   |
| 11.6.4 | Ellenőrizze, hogy a formális bizonyítások az összes ε költségvetést kevesebb, mint 5-ös hasznosságveszteséggel mutatják be.      |   3   |  V   |

---

### Hivatkozások

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

