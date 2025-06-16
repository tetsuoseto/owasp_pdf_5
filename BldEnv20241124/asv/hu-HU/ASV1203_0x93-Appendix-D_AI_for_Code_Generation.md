# D. melléklet: Mesterséges Intelligenciával Támogatott Biztonságos Kódolás Irányítása és Ellenőrzése

## Célkitűzés

Ez a fejezet alapvető szervezeti ellenőrzéseket határoz meg az AI által támogatott kódolási eszközök biztonságos és hatékony használatához a szoftverfejlesztés során, biztosítva a biztonságot és nyomonkövethetőséget a szoftverfejlesztési életciklus (SDLC) során.

---

## AD.1 Mesterséges Intelligencia Segítségével Támogatott Biztonságos Kódolási Munkafolyamat

Integrálja az AI eszközöket a szervezet biztonságos szoftverfejlesztési életciklusába (SSDLC) anélkül, hogy gyengítené a meglévő biztonsági kapukat.

|   #    | Description                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Ellenőrizze, hogy a dokumentált munkafolyamat leírja-e, mikor és hogyan generálhatják, refaktorálhatják vagy felülvizsgálhatják a kódot az AI eszközök.                                 |   1   | D/V  |
| AD.1.2 | Ellenőrizze, hogy a munkafolyamat megfeleltethető-e az egyes SSDLC fázisoknak (tervezés, megvalósítás, kódellenőrzés, tesztelés, telepítés).                                            |   2   |  D   |
| AD.1.3 | Ellenőrizze, hogy az AI által generált kódra vonatkozó metrikákat (pl. sebezhetőségi sűrűség, átlagosészlelési idő) összegyűjtik-e, és összehasonlítják-e az emberi kód alapvonalakkal. |   3   | D/V  |

---

## AD.2 AI eszközminősítés és fenyegetésmodellezés

Biztosítani kell, hogy az AI kódoló eszközöket a bevezetés előtt értékeljék biztonsági képességeik, kockázatuk és ellátási láncra gyakorolt hatásuk szempontjából.

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Ellenőrizze, hogy az egyes MI-eszközök veszélymodelljei azonosítják-e a visszaélést, a modell-inverziót, az adatkisülést és a függőségi lánc kockázatait.                                |   1   | D/V  |
| AD.2.2 | Ellenőrizze, hogy az eszközértékelések tartalmazzák-e a helyi komponensek statikus/dinamikus elemzését, valamint a SaaS végpontok (TLS, hitelesítés/engedélyezés, naplózás) értékelését. |   2   |  D   |
| AD.2.3 | Ellenőrizze, hogy az értékelések egy elismert keretrendszer szerint történnek, és hogy nagyobb verzióváltások után újra elvégzik-e őket.                                                 |   3   | D/V  |

---

## AD.3 Biztonságos Parancs- és Kontextuskezelés

Megakadályozza a titkok, szabadalmi kódok és személyes adatok kiszivárgását AI-modellekhez szánt promptok vagy kontextusok létrehozásakor.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.3.1 | Ellenőrizze, hogy az írásos iránymutatás tiltja-e a titkok, hitelesítő adatok vagy titkosított adatok beküldését a bemenetekben.                                                           |   1   | D/V  |
| AD.3.2 | Ellenőrizze, hogy a műszaki vezérlések (kliensoldali kivonás, jóváhagyott kontextusszűrők) automatikusan eltávolítják-e az érzékeny adathalmazokat.                                        |   2   |  D   |
| AD.3.3 | Ellenőrizze, hogy a parancsok és válaszok tokenizálva vannak-e, titkosítva az átvitel során és a tároláskor, valamint hogy a megőrzési idők megfelelnek-e az adat­osztályozási szabálynak. |   3   | D/V  |

---

## AD.4 Az MI által generált kód érvényesítése

Az AI által generált kimenet által okozott sérülékenységek észlelése és kijavítása a kód egyesítése vagy telepítése előtt.

|   #    | Description                                                                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Ellenőrizze, hogy a mesterséges intelligencia által generált kódot mindig emberi kódátvizsgálatnak vetik alá.                                                                                                    |   1   | D/V  |
| AD.4.2 | Ellenőrizze, hogy az automatizált szkennerek (SAST/IAST/DAST) minden, mesterséges intelligencia által generált kódot tartalmazó pull requesten lefutnak, és kritikus hibák esetén megakadályozzák az egyesítést. |   2   |  D   |
| AD.4.3 | Ellenőrizze, hogy a differenciális fuzz tesztelés vagy a tulajdonságalapú tesztek bizonyítják-e a biztonságkritikus viselkedéseket (pl. bemeneti érvényesítés, jogosultságkezelési logika).                      |   3   | D/V  |

---

## AD.5 A kódjavaslatok magyarázhatósága és visszakövethetősége

Biztosítsanak a könyvvizsgálóknak és fejlesztőknek betekintést abba, hogy miért tették a javaslatot és hogyan fejlődött az.

|   #    | Description                                                                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Ellenőrizze, hogy a prompt/válasz párok commit azonosítókkal vannak-e naplózva.                                                                                                                                       |   1   | D/V  |
| AD.5.2 | Ellenőrizze, hogy a fejlesztők meg tudják-e jeleníteni a modell hivatkozásait (képzési részletek, dokumentáció), amelyek alátámasztják egy javaslatot.                                                                |   2   |  D   |
| AD.5.3 | Ellenőrizze, hogy az értelmezhetőségi jelentések a tervezési dokumentumokkal együtt kerülnek tárolásra, és hivatkoznak rájuk a biztonsági felülvizsgálatok során, megfelelve az ISO/IEC 42001 követhetőségi elveinek. |   3   | D/V  |

---

## AD.6 Folyamatos visszacsatolás és modell finomhangolás

Javítsa a modell biztonsági teljesítményét az idő múlásával, miközben megakadályozza a negatív elmozdulást.

|   #    | Description                                                                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Ellenőrizze, hogy a fejlesztők képesek-e jelölni a nem biztonságos vagy nem megfelelõ javaslatokat, és hogy ezek a jelölések nyomon követhetők-e.                                                                         |   1   | D/V  |
| AD.6.2 | Ellenőrizze, hogy az összesített visszajelzések rendszeres finomhangolást vagy ellenőrzött biztonsági kódolási korpuszokkal (például OWASP Cheat Sheets) támogatott lekérdezés-alapú generálást tájékoztatnak-e.          |   2   |  D   |
| AD.6.3 | Ellenőrizze, hogy a zárt hurkú értékelő környezet minden finomhangolás után végrehajt regressziós teszteket; a biztonsági mutatóknak meg kell felelniük vagy meg kell haladniuk az előző alapértékeket a telepítés előtt. |   3   | D/V  |

---

### Hivatkozások

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

