# C12 Megfigyelés, Naplózás és Anomáliaészlelés

## Ellenőrzési célkitűzés

Ez a szakasz követelményeket határoz meg annak érdekében, hogy valós idejű és forenzikus láthatóságot biztosítson arra vonatkozóan, mit lát, mit csinál és mit ad vissza a modell és egyéb AI-komponensek, így a fenyegetéseket észlelni, osztályozni és tanulni lehessen belőlük.

## C12.1 Kérés- és válasznaplózás

|   #    | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Ellenőrizze, hogy az összes felhasználói utasítás és a modell válaszai megfelelő metaadatokkal (pl. időbélyeg, felhasználói azonosító, munkamenet-azonosító, modell verzió) együtt legyenek naplózva.                                                                            |   1   | D/V  |
| 12.1.2 | Ellenőrizze, hogy a naplók biztonságos, hozzáférés-ellenőrzött tárhelyeken vannak-e tárolva, megfelelő megőrzési szabályzatokkal és biztonsági mentési eljárásokkal.                                                                                                             |   1   | D/V  |
| 12.1.3 | Ellenőrizze, hogy a napló tároló rendszerek implementálnak-e adatok nyugalmi állapotbeli és átvitel közbeni titkosítást a naplókban található érzékeny információk védelme érdekében.                                                                                            |   1   | D/V  |
| 12.1.4 | Ellenőrizze, hogy a promptokban és kimenetekben lévő érzékeny adatok automatikusan el legyenek távolítva vagy maszkolva a naplózás előtt, konfigurálható eltávolítási szabályokkal a személyes azonosító információk (PII), hitelesítő adatok és tulajdonosi információk esetén. |   1   | D/V  |
| 12.1.5 | Ellenőrizze, hogy a szabályzat döntései és a biztonsági szűrési intézkedések kellő részletességgel legyenek naplózva, hogy lehetővé tegyék a tartalommenedzsment rendszerek auditálását és hibakeresését.                                                                        |   2   | D/V  |
| 12.1.6 | Ellenőrizze, hogy a napló integritását védik-e például kriptográfiai aláírások vagy csak írásra alkalmas tárolás segítségével.                                                                                                                                                   |   2   | D/V  |

---

## C12.2 Visszaélésészlelés és riasztás

|   #    | Description                                                                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.2.1 | Ellenőrizze, hogy a rendszer felismeri-e és riaszt-e ismert jailbreak mintázatok, prompt injekciós kísérletek és ellenséges bemenetek esetén aláírásalapú észlelés segítségével.                                                     |   1   | D/V  |
| 12.2.2 | Ellenőrizze, hogy a rendszer integrálódik-e a meglévő Biztonsági Információ- és Eseménykezelő (SIEM) platformokkal szabványos naplóformátumok és protokollok használatával.                                                          |   1   | D/V  |
| 12.2.3 | Ellenőrizze, hogy a kibővített biztonsági események tartalmazzák-e az AI-specifikus kontextust, például modellazonosítókat, megbízhatósági pontszámokat és a biztonsági szűrő döntéseit.                                             |   2   | D/V  |
| 12.2.4 | Ellenőrizze, hogy a viselkedési anomáliafelismerés azonosítja-e a szokatlan beszélgetési mintázatokat, a túlzott ismétlési kísérleteket vagy a rendszerszintű kutató jellegű viselkedéseket.                                         |   2   | D/V  |
| 12.2.5 | Ellenőrizze, hogy az valós idejű riasztási mechanizmusok értesítik-e a biztonsági csapatokat, amikor potenciális szabályzat megsértéseket vagy támadási kísérleteket észlelnek.                                                      |   2   | D/V  |
| 12.2.6 | Ellenőrizze, hogy a személyre szabott szabályok tartalmazzák-e az AI-specifikus fenyegetési minták észlelését, beleértve az összehangolt jailbreak kísérleteket, prompt befecskendezési kampányokat és a modellkivonási támadásokat. |   2   | D/V  |
| 12.2.7 | Ellenőrizze, hogy az automatikus incidensválasz-munkafolyamatok képesek-e elszigetelni a kompromittált modelleket, blokkolni a rosszindulatú felhasználókat, és súlyos biztonsági események esetén továbbítani azokat.               |   3   | D/V  |

---

## C12.3 Modell-eltolódás észlelése

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Ellenőrizze, hogy a rendszer nyomon követi-e az alapvető teljesítménymutatókat, például a pontosságot, a bizalmi pontszámokat, a késleltetést és a hibaarányokat a modellverziók és az időszakok során. |   1   | D/V  |
| 12.3.2 | Ellenőrizze, hogy az automatizált riasztás aktiválódik-e, amikor a teljesítménymutatók túllépik az előre meghatározott degradációs küszöbértékeket, vagy jelentősen eltérnek az alapértékektől.         |   2   | D/V  |
| 12.3.3 | Ellenőrizze, hogy a hallucinációészlelő monitorok azonosítják-e és jelölik-e azokat az eseteket, amikor a modell kimenete tényileg helytelen, inkonzisztens vagy kitalált információkat tartalmaz.      |   2   | D/V  |

---

## C12.4 Teljesítmény- és viselkedéstávoli mérés

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Ellenőrizze, hogy az olyan működési mutatók, mint a kérés késleltetése, token-felhasználás, memóriahasználat és áteresztőképesség folyamatosan gyűjtésre és figyelésre kerülnek-e.            |   1   | D/V  |
| 12.4.2 | Ellenőrizze, hogy a siker- és hibaarányokat egyaránt nyomon követik-e a hibatípusok és azok alapvető okainak kategorizálásával.                                                               |   1   | D/V  |
| 12.4.3 | Ellenőrizze, hogy az erőforrás-használat figyelése tartalmazza-e a GPU/CPU használatát, a memóriafogyasztást és a tárolási igényeket, valamint riasztást ad-e a küszöbérték túllépése esetén. |   2   | D/V  |

---

## C12.5 MI Eseménykezelési Tervezés és Végrehajtás

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Ellenőrizze, hogy a incidensreagálási tervek kifejezetten foglalkoznak-e az AI-hoz kapcsolódó biztonsági eseményekkel, beleértve a modell kompromittálását, az adatmérgezést és a támadó jellegű támadásokat. |   1   | D/V  |
| 12.5.2 | Ellenőrizze, hogy az incidenskezelő csapatok hozzáférnek-e az AI-specifikus forenzikai eszközökhöz és szakértelemhez a modell viselkedésének és a támadási vektorok vizsgálatához.                            |   2   | D/V  |
| 12.5.3 | Ellenőrizze, hogy az esemény utáni elemzés tartalmazza-e a modell újratanításának szempontjait, a biztonsági szűrők frissítését és a tanulságok beépítését a biztonsági ellenőrzésekbe.                       |   3   | D/V  |

---

## C12.5 AI teljesítményromlás észlelése

Figyelje és észlelje az AI-modell teljesítményének és minőségének romlását az idő múlásával.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Ellenőrizze, hogy a modell pontosságát, precizitását, visszahívását és F1 pontszámait folyamatosan figyelik és összehasonlítják az alapvonal küszöbértékekkel. |   1   | D/V  |
| 12.5.2 | Ellenőrizze, hogy az adatelmozdulás-észlelés figyeli-e a bemeneti eloszlás változásait, amelyek hatással lehetnek a modell teljesítményére.                    |   1   | D/V  |
| 12.5.3 | Ellenőrizze, hogy a koncepcióeltolódás-észlelés azonosítja-e a bemenetek és a várt kimenetek közötti kapcsolat változásait.                                    |   2   | D/V  |
| 12.5.4 | Ellenőrizze, hogy a teljesítményromlás automatikus riasztásokat vált-e ki, és elindítja-e a modell újratanítását vagy cseréjét célzó munkafolyamatokat.        |   2   | D/V  |
| 12.5.5 | Ellenőrizze, hogy a teljesítményromlás okainak elemzése összefügg-e az adatok változásaival, az infrastruktúra problémáival vagy külső tényezőkkel.            |   3   |  V   |

---

## C12.6 DAG megjelenítés és munkafolyamat-biztonság

Védje a munkafolyamat-visualizációs rendszereket az információszivárgás és a manipulációs támadások ellen.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Ellenőrizze, hogy a DAG vizualizációs adatokat megtisztították-e a tárolás vagy továbbítás előtt az érzékeny információk eltávolítása érdekében.                                                  |   1   | D/V  |
| 12.6.2 | Ellenőrizze, hogy a munkafolyamat-vizualizáció hozzáférés-vezérlése biztosítja-e, hogy csak az arra jogosult felhasználók tekinthetik meg az ügynök döntési útvonalait és érvelési nyomait.       |   1   | D/V  |
| 12.6.3 | Ellenőrizze, hogy a DAG adatintegritása kriptográfiai aláírások és manipulációt kimutató tárolási mechanizmusok révén védett-e.                                                                   |   2   | D/V  |
| 12.6.4 | Ellenőrizze, hogy a munkafolyamat-visualizációs rendszerek bevezetik-e a bemeneti érvényesítést, hogy megakadályozzák a beszúrásos támadásokat manipulált csomópont- vagy éladatokon keresztül.   |   2   | D/V  |
| 12.6.5 | Ellenőrizze, hogy a valós idejű DAG-frissítések sebességkorlátozva és érvényesítve vannak-e a szolgáltatásmegtagadási (DoS) támadásokkal szembeni védelem érdekében a vizualizációs rendszereken. |   3   | D/V  |

---

## C12.7 Proaktív biztonsági viselkedésfigyelés

Biztonsági fenyegetések észlelése és megelőzése proaktív ügynök viselkedéselemzés révén.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Ellenőrizze, hogy a proaktív ügynök viselkedések végrehajtás előtt biztonságilag validáltak-e, kockázatértékelési integrációval.                      |   1   | D/V  |
| 12.7.2 | Ellenőrizze, hogy az autonóm kezdeményezések kiváltói tartalmazzák-e a biztonsági környezet értékelését és a fenyegetési helyzet felmérését.          |   2   | D/V  |
| 12.7.3 | Ellenőrizze, hogy a proaktív viselkedésmintákat elemezték-e potenciális biztonsági következmények és nem kívánt hatások szempontjából.                |   2   | D/V  |
| 12.7.4 | Ellenőrizze, hogy a biztonságkritikus proaktív intézkedésekhez egyértelmű jóváhagyási láncok és auditnaplók szükségesek-e.                            |   3   | D/V  |
| 12.7.5 | Ellenőrizze, hogy a viselkedéses anomáliaészlelés azonosítja-e az előrejelző ügynök mintázatainak eltéréseit, amelyek kompromittáltságot jelezhetnek. |   3   | D/V  |

---

## Hivatkozások

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

