# C1 Képzési Adatkezelés és Elfogultságkezelés

## Ellenőrzési célkitűzés

A tanítóadatokat olyan módon kell beszerezni, kezelni és fenntartani, amely megőrzi az eredetiségüket, biztonságukat, minőségüket és méltányosságukat. Ennek betartásával teljesítjük a jogi kötelezettségeket és csökkentjük az AI-életciklus során felmerülő torzítás, manipuláció vagy adatvédelmi incidensek kockázatát.

---

## C1.1 Képzési Adatok Eredete

Tartson fenn ellenőrizhető nyilvántartást az összes adattárról, csak megbízható forrásokat fogadjon el, és minden változást naplózzon az ellenőrizhetőség érdekében.

|   #   | Description                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Ellenőrizze, hogy naprakész nyilvántartás készült-e minden egyes képzési adattárról (eredet, kezelő/tulajdonos, licenc, gyűjtési mód, tervezett felhasználási korlátozások és feldolgozási történelem).                                                                                              |   1   | D/V  |
| 1.1.2 | Ellenőrizze, hogy csak olyan adatkészletek legyenek engedélyezve, amelyek minőségi, reprezentativitási, etikai forrásellenőrzési és licencmegfelelőségi szempontból átmentek, ezáltal csökkentve a mérgezés, beágyazott elfogultság és szellemi tulajdonjogok sértésének kockázatát.                 |   1   | D/V  |
| 1.1.3 | Ellenőrizze, hogy az adatminimalizálás érvényesül-e, így a felesleges vagy érzékeny attribútumok kizárásra kerülnek.                                                                                                                                                                                 |   1   | D/V  |
| 1.1.4 | Ellenőrizze, hogy minden adatbázis-módosítást jóváhagyási folyamat naplózása kísérjen.                                                                                                                                                                                                               |   2   | D/V  |
| 1.1.5 | Ellenőrizze, hogy a címkézés/jelölés minősége biztosított-e a felülvizsgáló átvizsgálások vagy konszenzus révén.                                                                                                                                                                                     |   2   | D/V  |
| 1.1.6 | Ellenőrizze, hogy a "adatkártyák" vagy a "adatlapok a tanulási adathalmazokhoz" fenn vannak-e tartva a jelentős tanulási adathalmazok esetében, részletezve azok jellemzőit, céljait, összetételét, gyűjtési folyamatait, előfeldolgozását, valamint az ajánlott és nem ajánlott használati módokat. |   2   | D/V  |

---

## C1.2 Képzési Adatok Biztonsága és Integritása

Korlátozza a hozzáférést, titkosítsa az adatokat tárolás közben és átvitel során, valamint ellenőrizze az integritást, hogy megakadályozza a manipulációt vagy lopást.

|   #   | Description                                                                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Ellenőrizze, hogy a hozzáférés-vezérlések védik-e a tárolókat és az adatfeldolgozó csővezetékeket.                                                                                                                                                                                                                                                   |   1   | D/V  |
| 1.2.2 | Ellenőrizze, hogy az adathalmazok átvitel közben titkosítva vannak-e, és minden érzékeny vagy személyesen azonosítható információ (PII) esetében nyugalmi állapotban is, az iparági szabványoknak megfelelő kriptográfiai algoritmusokkal és kulcskezelési gyakorlatokkal.                                                                           |   2   | D/V  |
| 1.2.3 | Ellenőrizze, hogy a kriptográfiai hash-eket vagy digitális aláírásokat használják-e az adatok sértetlenségének biztosítására tárolás és átvitel során, valamint hogy automatizált anomáliaészlelő technikákat alkalmaznak-e az illetéktelen módosítások vagy sérülések, beleértve a célzott adatmérgezési kísérleteket is, elleni védelem érdekében. |   2   | D/V  |
| 1.2.4 | Ellenőrizze, hogy az adatkészlet verziói nyomon vannak-e követve a visszaállítás lehetőségének biztosítása érdekében.                                                                                                                                                                                                                                |   3   | D/V  |
| 1.2.5 | Ellenőrizze, hogy az elavult adatok biztonságosan törlődnek vagy anonimizálódnak az adatmegőrzési irányelveknek, szabályozási követelményeknek megfelelően, valamint az támadási felület csökkentése érdekében.                                                                                                                                      |   2   | D/V  |

---

## C1.3 Reprezentáció teljessége és méltányossága

Észlelje a demográfiai eltéréseket, és alkalmazzon mérséklést annak érdekében, hogy a modell hibaarányai csoportok között egyenlőek legyenek.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Ellenőrizze, hogy az adatállományokat jellemzik-e a reprezentációs egyensúlyhiány és a potenciális elfogultságok szempontjából a jogilag védett attribútumok (például faj, nem, életkor) és a modell alkalmazási területéhez kapcsolódó más, etikai szempontból érzékeny jellemzők (például társadalmi-gazdasági helyzet, földrajzi elhelyezkedés) tekintetében.                         |   1   | D/V  |
| 1.3.2 | Ellenőrizze, hogy az azonosított torzítások dokumentált stratégiák révén enyhítve vannak-e, például átrendezéssel, célzott adatnöveléssel, algoritmikus igazításokkal (pl. előfeldolgozási, feldolgozási közbeni vagy utófeldolgozási technikákkal), illetve súlyozás újraelosztásával, és értékelje a mérséklés hatását mind az igazságosságra, mind az általános modellteljesítményre. |   2   | D/V  |
| 1.3.3 | Ellenőrizze, hogy az utótréning utáni méltányossági mutatókat kiértékelték és dokumentálták.                                                                                                                                                                                                                                                                                             |   2   | D/V  |
| 1.3.4 | Ellenőrizze, hogy az életciklus-alapú torzításkezelési szabályzat tulajdonosokat és felülvizsgálati időközöket rendel-e hozzá.                                                                                                                                                                                                                                                           |   3   | D/V  |

---

## C1.4 A képzési adatok címkézésének minősége, integritása és biztonsága

Védd címkéket titkosítással, és kritikus osztályok esetén írj elő kétszakaszos felülvizsgálatot.

|   #   | Description                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Ellenőrizze, hogy a címkézés/annotáció minősége biztosított-e világos iránymutatások, felülvizsgáló közötti ellenőrzések, konszenzus-mechanizmusok (pl. annotátorok közti egyetértés figyelése) és a nézeteltérések rendezésére szolgáló meghatározott folyamatok révén.                                 |   2   | D/V  |
| 1.4.2 | Ellenőrizze, hogy kriptográfiai hashek vagy digitális aláírások vannak-e alkalmazva a címke műtárgyakon az integritásuk és hitelességük biztosítása érdekében.                                                                                                                                           |   2   | D/V  |
| 1.4.3 | Ellenőrizze, hogy a címkézési felületek és platformok erős hozzáférés-ellenőrzést alkalmaznak-e, fenntartják-e a hamisítás-ellenálló naplókat az összes címkézési tevékenységről, és védik-e a jogosulatlan módosítások ellen.                                                                           |   2   | D/V  |
| 1.4.4 | Ellenőrizze, hogy a biztonság, védettség vagy méltányosság szempontjából kritikus címkék (például mérgező tartalom azonosítása, kritikus orvosi megállapítások) kötelező, független kettős felülvizsgálaton vagy azzal egyenértékű, megbízható ellenőrzésen essenek át.                                  |   3   | D/V  |
| 1.4.5 | Ellenőrizze, hogy a címkékben véletlenül rögzített vagy szükségszerűen jelen lévő érzékeny információk (beleértve a személyes azonosításra alkalmas adatokat - PII) a adatminimalizálás elvei szerint fel vannak-e tüntetve, álnevesítve, anonimizálva vagy titkosítva mind tároláskor, mind átvitelkor. |   2   | D/V  |
| 1.4.6 | Ellenőrizze, hogy a címkézési útmutatók és utasítások átfogóak, verziókezelték és szakértők által felülvizsgáltak legyenek.                                                                                                                                                                              |   2   | D/V  |
| 1.4.7 | Ellenőrizze, hogy az adatsémák (beleértve a címkéket is) világosan definiáltak és verziókövetettek legyenek.                                                                                                                                                                                             |   2   | D/V  |
| 1.8.2 | Ellenőrizze, hogy a kiszervezett vagy közösségi címkézési munkafolyamatok tartalmazzanak műszaki/eljárási biztonsági intézkedéseket az adatok bizalmasságának, integritásának, a címkék minőségének biztosítása, valamint az adatvédelmi szivárgás megelőzése érdekében.                                 |   2   | D/V  |

---

## C1.5 Képzési Adatok Minőségbiztosítása

Az automatizált érvényesítés, a manuális ellenőrzések és a naplózott hibajavítás együttes alkalmazásával garantálja az adatkészlet megbízhatóságát.

|   #   | Description                                                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Ellenőrizze, hogy az automatizált tesztek minden adatbetöltés vagy jelentős átalakítás során észlelik-e a formátumhibákat, null értékeket és címkeeltolódásokat.                                                                                                                                                                     |   1   |  D   |
| 1.5.2 | Ellenőrizze, hogy a sikertelen adatállományok karanténba kerülnek-e audit nyomvonalakkal.                                                                                                                                                                                                                                            |   1   | D/V  |
| 1.5.3 | Ellenőrizze, hogy a tématerületi szakértők által végzett manuális mintavételes ellenőrzések statisztikailag jelentős mintát fednek-e le (pl. ≥1% vagy 1 000 minta, a nagyobb érték alapján, vagy a kockázatértékelés szerint meghatározva), hogy az automatizálás által nem észlelt finom minőségi problémákat azonosítani lehessen. |   2   |  V   |
| 1.5.4 | Ellenőrizze, hogy a javítási lépések hozzá vannak-e fűzve az eredetiség rekordokhoz.                                                                                                                                                                                                                                                 |   2   | D/V  |
| 1.5.5 | Ellenőrizze, hogy a minőségi kapuk letiltják a gyenge minőségű adatokat, kivéve, ha az kivételek jóváhagyásra kerültek.                                                                                                                                                                                                              |   2   | D/V  |

---

## C1.6 Adathamisítás Felismerése

Alkalmazzon statisztikai anomáliaészlelést és elkülönítési munkafolyamatokat az ellenséges beszúrások megállítására.

|   #   | Description                                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Ellenőrizze, hogy az anomáliaészlelési technikákat (például statisztikai módszerek, kiugró értékek felismerése, beágyazás elemzés) alkalmazzák-e a betanítási adatok feldolgozásakor és a főbb tanítási futtatások előtt a potenciális mérgezési támadások vagy szándékos adatkárosodás azonosítása érdekében. |   2   | D/V  |
| 1.6.2 | Ellenőrizze, hogy a jelzett minták kézi felülvizsgálatot váltanak-e ki a képzés előtt.                                                                                                                                                                                                                         |   2   | D/V  |
| 1.6.3 | Ellenőrizze, hogy az eredmények beillesztésre kerülnek-e a modell biztonsági dossziéjába, és tájékoztatják-e a folyamatos fenyegetettségi hírszerzést.                                                                                                                                                         |   2   |  V   |
| 1.6.4 | Ellenőrizze, hogy a felismerési logika frissüljön az új fenyegetésinformációkkal.                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.5 | Ellenőrizze, hogy az online tanulási folyamatok figyelik-e az eloszláseltolódást.                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.6 | Ellenőrizze, hogy a rendszer kockázati profilja és adatforrásai alapján figyelembe vették-e és végrehajtották-e a specifikus védelmi intézkedéseket a ismert adatmérgezési támadástípusok, például címkeátszabás, hátsóajtó trigger beszúrása, befolyásoló példányok elleni támadások ellen.                   |   3   | D/V  |

---

## C1.7 Felhasználói adatok törlése és hozzájárulás érvényesítése

Tiszteld a törlési és hozzájárulás-visszavonási kéréseket az összes adattáron, biztonsági mentésen és származtatott állományon.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.7.1 | Ellenőrizze, hogy a törlési munkafolyamatok eltávolítják-e az elsődleges és származtatott adatokat, valamint értékeljék a modellre gyakorolt hatást, továbbá hogy az érintett modellekre gyakorolt hatást értékelik és szükség esetén kezelik (például újratanítással vagy újrakalibrálással).                                                         |   1   | D/V  |
| 1.7.2 | Ellenőrizze, hogy léteznek-e olyan mechanizmusok, amelyek nyomon követik és tiszteletben tartják a felhasználói hozzájárulás (és visszavonások) terjedelmét és állapotát a tanításhoz használt adatok esetében, valamint hogy a hozzájárulást érvényesítik, mielőtt az adatokat beépítenék új tanítási folyamatokba vagy jelentős modellfrissítésekbe. |   2   |  D   |
| 1.7.3 | Ellenőrizze, hogy a munkafolyamatokat évente tesztelik és naplózzák.                                                                                                                                                                                                                                                                                   |   2   |  V   |

---

## C1.8 Ellátási lánc biztonság

Külső adatforrásokat ellenőrizzen, és az integritást hitelesített, titkosított csatornákon keresztül igazolja.

|   #   | Description                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Ellenőrizze, hogy a harmadik fél adatbeszállítók, beleértve az előre betanított modellek és külső adatkészletek szolgáltatóit, megfelelnek-e a biztonsági, adatvédelmi, etikus beszerzési és adatminőségi előzetes vizsgálatoknak, mielőtt az adataikat vagy modelljeiket integrálják.                                                |   2   | D/V  |
| 1.8.2 | Ellenőrizze, hogy a külső átvitelek TLS-t, hitelesítést és integritásellenőrzéseket használnak-e.                                                                                                                                                                                                                                     |   1   |  D   |
| 1.8.3 | Ellenőrizze, hogy a magas kockázatú adatforrások (pl. ismeretlen eredetű nyílt forráskódú adatkészletek, jóváhagyatlan beszállítók) fokozott vizsgálatnak legyenek alávetve, például elszigetelt elemzés, átfogó minőség- és torzításellenőrzés, valamint célzott mérgezésészlelés, mielőtt érzékeny alkalmazásokban használnák őket. |   2   | D/V  |
| 1.8.4 | Ellenőrizze, hogy a harmadik felektől származó előre betanított modelleket megvizsgálták-e beágyazott torzítások, esetleges hátsóajtók, az architektúrájuk integritása, valamint az eredeti tanító adatok eredete szempontjából a finomhangolás vagy bevezetés előtt.                                                                 |   3   | D/V  |

---

## C1.9 Ellenséges mintaészlelés

Alkalmazzon intézkedéseket a tanítási fázis során, például ellenséges tanítást, a modell ellenállóképességének növelésére az ellenséges példákkal szemben.

|   #   | Description                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Ellenőrizze, hogy a megfelelő védekezések, például az ellenséges tréning (generált ellenséges példák használatával), a perturbált bemenetekkel történő adatnövelés vagy a robusztus optimalizációs technikák be vannak-e vezetve és hangolva a releváns modellek számára a kockázatértékelés alapján. |   3   | D/V  |
| 1.9.2 | Ellenőrizze, hogy ha adversariális képzést alkalmaznak, akkor az adversariális adathalmazok létrehozása, kezelése és verziókövetése dokumentált és ellenőrzött legyen.                                                                                                                                |   2   | D/V  |
| 1.9.3 | Ellenőrizze, hogy az ellenséges robusztusságú tréning hatása a modell teljesítményére (mind tiszta, mind ellenséges bemenetek esetén) és a méltányossági mutatókra ki van értékelve, dokumentálva és nyomon követve.                                                                                  |   3   | D/V  |
| 1.9.4 | Ellenőrizze, hogy a támadóellenes képzés és a robusztusság stratégiáit időszakosan felülvizsgálják és frissítik az evolúciós támadási technikák elleni védekezés érdekében.                                                                                                                           |   3   | D/V  |

---

## C1.10 Adatvonal követhetősége és nyomonkövethetősége

Kövesse nyomon minden adatpont teljes útját a forrástól a modell bemenetéig az átláthatóság és az incidenskezelés érdekében.

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Ellenőrizze, hogy minden adatpont származási lánca, beleértve az összes átalakítást, bővítést és összevonást, dokumentálva van-e és visszaállítható legyen. |   2   | D/V  |
| 1.10.2 | Ellenőrizze, hogy a származási rekordok megváltoztathatatlanok, biztonságosan tároltak, és hozzáférhetők legyenek auditok vagy vizsgálatok számára.         |   2   | D/V  |
| 1.10.3 | Ellenőrizze, hogy a származáskövetés mind a nyers, mind a szintetikus adatokat lefedi-e.                                                                    |   2   | D/V  |

---

## C1.11 Szintetikus adatkezelés

Biztosítsa, hogy a szintetikus adatokat megfelelően kezeljék, címkézzék és kockázatértékeljék.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Ellenőrizze, hogy az összes szintetikus adat egyértelműen fel legyen címkézve, és megkülönböztethető legyen a valós adatoktól a teljes adatfeldolgozási folyamat során.                   |   2   | D/V  |
| 1.11.2 | Ellenőrizze, hogy a szintetikus adatok generálási folyamata, paraméterei és a tervezett felhasználásuk dokumentálva vannak-e.                                                             |   2   | D/V  |
| 1.11.3 | Ellenőrizze, hogy a szintetikus adatokat kockázatértékelték-e elfogultság, adatvédelmi szivárgás és reprezentációs problémák szempontjából, mielőtt azokat a tréning során felhasználnák. |   2   | D/V  |

---

## C1.12 Adathozzáférés-figyelés és anomáliadetektálás

Figyelje és jelezze a szokatlan hozzáféréseket a tanítóadatokhoz, hogy felismerje a belső fenyegetéseket vagy az adatkiszivárgást.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Ellenőrizze, hogy az összes hozzáférés a képzési adatokhoz naplózva van, beleértve a felhasználót, az időpontot és a műveletet.                                   |   2   | D/V  |
| 1.12.2 | Ellenőrizze, hogy az elérési naplókat rendszeresen átvizsgálják szokatlan mintázatok, például nagy mennyiségű export vagy új helyekről történő hozzáférés esetén. |   2   | D/V  |
| 1.12.3 | Ellenőrizze, hogy a riasztások gyanús hozzáférési események esetén keletkeznek-e, és azokat haladéktalanul kivizsgálják-e.                                        |   2   | D/V  |

---

## C1.13 Adatmegőrzési és lejárati szabályzatok

Határozzon meg és érvényesítsen adatmegőrzési időszakokat a felesleges adattárolás minimalizálása érdekében.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Ellenőrizze, hogy minden képzési adathalmazra vonatkozóan meg vannak-e határozva a kifejezett megtartási időszakok.                            |   1   | D/V  |
| 1.13.2 | Ellenőrizze, hogy az adatkészletek életciklusuk végén automatikusan lejárnak-e, törlődnek-e vagy felülvizsgálatra kerülnek a törlés érdekében. |   2   | D/V  |
| 1.13.3 | Ellenőrizze, hogy a megőrzési és törlési műveletek naplózottak és auditálhatók legyenek.                                                       |   2   | D/V  |

---

## C1.14 Szabályozói és joghatósági megfelelés

Biztosítsa, hogy minden képzési adat megfeleljen az alkalmazandó jogszabályoknak és előírásoknak.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Ellenőrizze, hogy minden adatállomány esetében az adathelyzet és a határokon átnyúló adatátviteli követelmények azonosításra kerülnek és érvényesítésre kerülnek. |   2   | D/V  |
| 1.14.2 | Ellenőrizze, hogy az adott ágazatra vonatkozó előírásokat (pl. egészségügy, pénzügy) azonosították-e és kezelik-e az adatkezelés során.                           |   2   | D/V  |
| 1.14.3 | Ellenőrizze, hogy a vonatkozó adatvédelmi törvényeknek (pl. GDPR, CCPA) való megfelelés dokumentált és rendszeresen felülvizsgált legyen.                         |   2   | D/V  |

---

## C1.15 Adatvízjelzés és ujjlenyomatkészítés

Hamisítás nélküli újrafelhasználás vagy tulajdonjogi, illetve érzékeny adatok kiszivárgásának észlelése.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Ellenőrizze, hogy az adatkészletek vagy alkészletek vízjellel vagy ujjlenyomattal vannak-e ellátva, ahol lehetséges.                                    |   3   | D/V  |
| 1.15.2 | Ellenőrizze, hogy a vízjelező/ujjlenyomat-azonosító módszerek nem vezetnek-e be elfogultságot vagy adatvédelmi kockázatokat.                            |   3   | D/V  |
| 1.15.3 | Győződjön meg arról, hogy rendszeres ellenőrzéseket végeznek az engedély nélküli vízjeles adatok újrafelhasználásának vagy kiszivárgásának észlelésére. |   3   | D/V  |

---

## C1.16 Adatvédelmi érintett jogainak kezelése

Támogassa az adatvédelmi érintetti jogokat, mint például a hozzáférést, helyesbítést, korlátozást és tiltakozást.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Ellenőrizze, hogy léteznek-e mechanizmusok az érintetti kérelmekre vonatkozó hozzáférés, helyesbítés, korlátozás vagy tiltakozás kezelésére. |   2   | D/V  |
| 1.16.2 | Ellenőrizze, hogy a kérelmek rögzítve, nyomon követve és a jogszabályban előírt határidőn belül teljesítve legyenek.                         |   2   | D/V  |
| 1.16.3 | Ellenőrizze, hogy az adat alany jogainak folyamatát rendszeresen tesztelik és felülvizsgálják hatékonyságuk érdekében.                       |   2   | D/V  |

---

## C1.17 Adatkészlet verzió hatás elemzése

Értékelje a adatbázis-változások hatását, mielőtt frissítené vagy lecserélné a verziókat.

|   #    | Description                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Ellenőrizze, hogy hatáselemzést végeznek-e egy adatállomány verziójának frissítése vagy cseréje előtt, amely kiterjed a modell teljesítményére, méltányosságára és megfelelőségére. |   2   | D/V  |
| 1.17.2 | Győződjön meg arról, hogy a hatáselemzés eredményei dokumentáltak és az érintett érdekeltek által átvizsgáltak.                                                                     |   2   | D/V  |
| 1.17.3 | Ellenőrizze, hogy léteznek-e visszaállítási tervek arra az esetre, ha az új verziók elfogadhatatlan kockázatokat vagy visszalépéseket vezetnének be.                                |   2   | D/V  |

---

## C1.18 Adatmegjelölési munkaerő biztonsága

Biztosítsák az adatok annotálásában részt vevő személyzet biztonságát és épségét.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Ellenőrizze, hogy minden adatmegjelölésben részt vevő személy háttérellenőrzésen esett át, valamint képzést kapott az adatbiztonság és adatvédelem terén. |   2   | D/V  |
| 1.18.2 | Ellenőrizze, hogy minden annotációs személyzet aláírta-e a titoktartási és titokvédelmi megállapodásokat.                                                 |   2   | D/V  |
| 1.18.3 | Ellenőrizze, hogy az annotációs platformok érvényesítik-e a hozzáférési szabályokat, és figyelik-e a belső fenyegetéseket.                                |   2   | D/V  |

---

## Hivatkozások

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

