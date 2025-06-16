## Címlap

### A szabványról

A Mesterséges Intelligencia Biztonsági Ellenőrzési Szabvány (AISVS) egy közösség által vezérelt biztonsági követelményeket tartalmazó katalógus, amelyet adattudósok, MLOps mérnökök, szoftverarchitektusok, fejlesztők, tesztelők, biztonsági szakemberek, eszközszállítók, szabályozók és felhasználók használhatnak megbízható, MI-alapú rendszerek és alkalmazások tervezéséhez, fejlesztéséhez, teszteléséhez és ellenőrzéséhez. Közös nyelvet biztosít a biztonsági intézkedések meghatározásához az MI életciklusa során — az adatgyűjtéstől és modellfejlesztéstől a telepítésen át a folyamatos megfigyelésig —, így a szervezetek mérni és javítani tudják MI-megoldásaik ellenálló képességét, adatvédelmét és biztonságát.

### Szerzői jog és licenc

Verzió 0.1 (Első nyilvános tervezet - Fejlesztés alatt), 2025  

![license](images/license.png)
Szerzői jog © 2025 Az AISVS Projekt.  

Kiadva az alatt aCreative Commons Attribution‑ShareAlike 4.0 International License.
Bármilyen újrafelhasználás vagy terjesztés esetén világosan közölnie kell a mű licencfeltételeit másokkal.

### Projektvezetők

Jim Manico
Aras „Russ” Memisyazici

### Közreműködők és Bírálók

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

Az AISVS egy vadonatúj szabvány, amelyet kifejezetten a mesterséges intelligencia rendszerek egyedi biztonsági kihívásainak kezelésére hoztak létre. Bár szélesebb körű biztonsági legjobb gyakorlatokból merít inspirációt, az AISVS minden egyes követelménye az AI fenyegetettségi környezet tükrözésére és a szervezetek számára biztonságosabb, ellenállóbb AI-megoldások kialakításának elősegítésére került kidolgozásra.

## Előszó

Üdvözöljük a Mesterséges Intelligencia Biztonsági Ellenőrzési Szabvány (AISVS) 1.0 verziójában!

### Bevezetés

Az AISVS-t 2025-ben hozták létre egy együttműködő közösségi erőfeszítés eredményeként, és meghatározza a biztonsági követelményeket, amelyeket figyelembe kell venni modern AI modellek, folyamatok és AI-képességekkel rendelkező szolgáltatások tervezése, fejlesztése, telepítése és működtetése során.

Az AISVS v1.0 az AI rendszerek biztonságossá tételéhez szükséges pragmatikus, tesztelhető alapvonal előállítására irányuló projektvezetők, munkacsoport és szélesebb közösség hozzájárulóinak együttes munkáját képviseli.

E kiadással a célunk, hogy az AISVS könnyen alkalmazható legyen, miközben szigorúan a meghatározott hatókörére összpontosítunk, és kezeljük az AI-ra jellemző gyorsan változó kockázati környezetet.

### Az AISVS 1.0 verziójának fő céljai

Az 1.0 verzió több irányelv alapján készül majd.

#### Jól meghatározott hatókör

Minden követelménynek összhangban kell állnia az AISVS nevével és küldetésével:

Mesterséges Intelligencia – Az ellenőrzések az AI/ML rétegen (adat, modell, munkafolyamat vagy következtetés) működnek, és az AI szakemberek felelőssége.
Biztonság – A követelmények közvetlenül enyhítik az azonosított biztonsági, adatvédelmi vagy biztonsági kockázatokat.
Ellenőrzés – A nyelvezet olyan módon van megírva, hogy a megfelelőség objektíven igazolható legyen.
Szabvány – A szakaszok következetes szerkezetet és terminológiát követnek, hogy koherens hivatkozást alkossanak.
​
---

Az AISVS követésével a szervezetek rendszerszerűen értékelhetik és erősíthetik mesterséges intelligencia megoldásaik biztonsági helyzetét, elősegítve a biztonságos MI mérnöki kultúra kialakulását.

## Az AISVS használata

A Mesterséges Intelligencia Biztonsági Ellenőrzési Szabvány (AISVS) meghatározza a biztonsági követelményeket a modern MI-alkalmazások és szolgáltatások számára, különös tekintettel az alkalmazásfejlesztők ellenőrzése alatt álló szempontokra.

Az AISVS bármely, AI-alkalmazások biztonságának fejlesztésével vagy értékelésével foglalkozó személy számára készült, beleértve a fejlesztőket, rendszermérnököket, biztonsági mérnököket és auditálókat. Ez a fejezet bemutatja az AISVS felépítését és használatát, beleértve annak ellenőrzési szintjeit és célzott felhasználási eseteit.

### Mesterséges intelligencia biztonsági ellenőrzési szintek

Az AISVS három fokozatosan emelkedő biztonsági ellenőrzési szintet határoz meg. Minden szint mélységet és összetettséget ad hozzá, lehetővé téve a szervezetek számára, hogy biztonsági helyzetüket az AI rendszereik kockázati szintjéhez igazítsák.

A szervezetek az 1. szintről kezdhetnek, és fokozatosan átvehetik a magasabb szinteket, ahogy a biztonsági érettség és a fenyegetettség növekszik.

#### A szintek definíciója

Az AISVS v1.0 minden követelménye a következő szintek egyikéhez van rendelve:

 1. szintű követelmények

Az 1. szint a legkritikusabb és alapvetőbb biztonsági követelményeket tartalmazza. Ezek az olyan gyakori támadások megelőzésére összpontosítanak, amelyek nem függnek más előfeltételektől vagy sebezhetőségektől. A legtöbb 1. szintű ellenőrzés egyszerűen megvalósítható vagy eléggé lényeges ahhoz, hogy indokolja a ráfordított erőfeszítést.

 2. szint követelményei

A 2. szint fejlettebb vagy kevésbé gyakori támadásokkal, valamint többrétegű védelemmel foglalkozik a széles körben elterjedt fenyegetések ellen. Ezek a követelmények összetettebb logikát vagy bizonyos támadási előfeltételeket célozhatnak meg.

 3. szintű követelmények

A 3. szint olyan kontrollokat tartalmaz, amelyek általában nehezebben megvalósíthatók vagy helyzetfüggő alkalmazhatóságúak. Ezek gyakran a mélyvédelmi mechanizmusokat vagy speciális, célzott vagy magas komplexitású támadások elleni mérsékléseket képviselnek.

#### Szerep (D/V)

Minden AISVS követelmény a fő célközönség szerint van jelölve:

D – Fejlesztőközpontú követelmények
V – Igazoló/ellenőrző fókuszú követelmények
D/V – Mind a fejlesztők, mind a ellenőrzők számára releváns

## C1 Képzési Adatkezelés és Elfogultságkezelés

### Ellenőrzési célkitűzés

A tanítóadatokat olyan módon kell beszerezni, kezelni és fenntartani, amely megőrzi az eredetiségüket, biztonságukat, minőségüket és méltányosságukat. Ennek betartásával teljesítjük a jogi kötelezettségeket és csökkentjük az AI-életciklus során felmerülő torzítás, manipuláció vagy adatvédelmi incidensek kockázatát.

---

### C1.1 Képzési Adatok Eredete

Tartson fenn ellenőrizhető nyilvántartást az összes adattárról, csak megbízható forrásokat fogadjon el, és minden változást naplózzon az ellenőrizhetőség érdekében.

 #1.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy naprakész nyilvántartás készült-e minden egyes képzési adattárról (eredet, kezelő/tulajdonos, licenc, gyűjtési mód, tervezett felhasználási korlátozások és feldolgozási történelem).
 #1.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy csak olyan adatkészletek legyenek engedélyezve, amelyek minőségi, reprezentativitási, etikai forrásellenőrzési és licencmegfelelőségi szempontból átmentek, ezáltal csökkentve a mérgezés, beágyazott elfogultság és szellemi tulajdonjogok sértésének kockázatát.
 #1.1.3    Level: 1    Role: D/V
 Ellenőrizze, hogy az adatminimalizálás érvényesül-e, így a felesleges vagy érzékeny attribútumok kizárásra kerülnek.
 #1.1.4    Level: 2    Role: D/V
 Ellenőrizze, hogy minden adatbázis-módosítást jóváhagyási folyamat naplózása kísérjen.
 #1.1.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a címkézés/jelölés minősége biztosított-e a felülvizsgáló átvizsgálások vagy konszenzus révén.
 #1.1.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a "adatkártyák" vagy a "adatlapok a tanulási adathalmazokhoz" fenn vannak-e tartva a jelentős tanulási adathalmazok esetében, részletezve azok jellemzőit, céljait, összetételét, gyűjtési folyamatait, előfeldolgozását, valamint az ajánlott és nem ajánlott használati módokat.

---

### C1.2 Képzési Adatok Biztonsága és Integritása

Korlátozza a hozzáférést, titkosítsa az adatokat tárolás közben és átvitel során, valamint ellenőrizze az integritást, hogy megakadályozza a manipulációt vagy lopást.

 #1.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a hozzáférés-vezérlések védik-e a tárolókat és az adatfeldolgozó csővezetékeket.
 #1.2.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az adathalmazok átvitel közben titkosítva vannak-e, és minden érzékeny vagy személyesen azonosítható információ (PII) esetében nyugalmi állapotban is, az iparági szabványoknak megfelelő kriptográfiai algoritmusokkal és kulcskezelési gyakorlatokkal.
 #1.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kriptográfiai hash-eket vagy digitális aláírásokat használják-e az adatok sértetlenségének biztosítására tárolás és átvitel során, valamint hogy automatizált anomáliaészlelő technikákat alkalmaznak-e az illetéktelen módosítások vagy sérülések, beleértve a célzott adatmérgezési kísérleteket is, elleni védelem érdekében.
 #1.2.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az adatkészlet verziói nyomon vannak-e követve a visszaállítás lehetőségének biztosítása érdekében.
 #1.2.5    Level: 2    Role: D/V
 Ellenőrizze, hogy az elavult adatok biztonságosan törlődnek vagy anonimizálódnak az adatmegőrzési irányelveknek, szabályozási követelményeknek megfelelően, valamint az támadási felület csökkentése érdekében.

---

### C1.3 Reprezentáció teljessége és méltányossága

Észlelje a demográfiai eltéréseket, és alkalmazzon mérséklést annak érdekében, hogy a modell hibaarányai csoportok között egyenlőek legyenek.

 #1.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az adatállományokat jellemzik-e a reprezentációs egyensúlyhiány és a potenciális elfogultságok szempontjából a jogilag védett attribútumok (például faj, nem, életkor) és a modell alkalmazási területéhez kapcsolódó más, etikai szempontból érzékeny jellemzők (például társadalmi-gazdasági helyzet, földrajzi elhelyezkedés) tekintetében.
 #1.3.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az azonosított torzítások dokumentált stratégiák révén enyhítve vannak-e, például átrendezéssel, célzott adatnöveléssel, algoritmikus igazításokkal (pl. előfeldolgozási, feldolgozási közbeni vagy utófeldolgozási technikákkal), illetve súlyozás újraelosztásával, és értékelje a mérséklés hatását mind az igazságosságra, mind az általános modellteljesítményre.
 #1.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az utótréning utáni méltányossági mutatókat kiértékelték és dokumentálták.
 #1.3.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az életciklus-alapú torzításkezelési szabályzat tulajdonosokat és felülvizsgálati időközöket rendel-e hozzá.

---

### C1.4 A képzési adatok címkézésének minősége, integritása és biztonsága

Védd címkéket titkosítással, és kritikus osztályok esetén írj elő kétszakaszos felülvizsgálatot.

 #1.4.1    Level: 2    Role: D/V
 Ellenőrizze, hogy a címkézés/annotáció minősége biztosított-e világos iránymutatások, felülvizsgáló közötti ellenőrzések, konszenzus-mechanizmusok (pl. annotátorok közti egyetértés figyelése) és a nézeteltérések rendezésére szolgáló meghatározott folyamatok révén.
 #1.4.2    Level: 2    Role: D/V
 Ellenőrizze, hogy kriptográfiai hashek vagy digitális aláírások vannak-e alkalmazva a címke műtárgyakon az integritásuk és hitelességük biztosítása érdekében.
 #1.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a címkézési felületek és platformok erős hozzáférés-ellenőrzést alkalmaznak-e, fenntartják-e a hamisítás-ellenálló naplókat az összes címkézési tevékenységről, és védik-e a jogosulatlan módosítások ellen.
 #1.4.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a biztonság, védettség vagy méltányosság szempontjából kritikus címkék (például mérgező tartalom azonosítása, kritikus orvosi megállapítások) kötelező, független kettős felülvizsgálaton vagy azzal egyenértékű, megbízható ellenőrzésen essenek át.
 #1.4.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a címkékben véletlenül rögzített vagy szükségszerűen jelen lévő érzékeny információk (beleértve a személyes azonosításra alkalmas adatokat - PII) a adatminimalizálás elvei szerint fel vannak-e tüntetve, álnevesítve, anonimizálva vagy titkosítva mind tároláskor, mind átvitelkor.
 #1.4.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a címkézési útmutatók és utasítások átfogóak, verziókezelték és szakértők által felülvizsgáltak legyenek.
 #1.4.7    Level: 2    Role: D/V
 Ellenőrizze, hogy az adatsémák (beleértve a címkéket is) világosan definiáltak és verziókövetettek legyenek.
 #1.8.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a kiszervezett vagy közösségi címkézési munkafolyamatok tartalmazzanak műszaki/eljárási biztonsági intézkedéseket az adatok bizalmasságának, integritásának, a címkék minőségének biztosítása, valamint az adatvédelmi szivárgás megelőzése érdekében.

---

### C1.5 Képzési Adatok Minőségbiztosítása

Az automatizált érvényesítés, a manuális ellenőrzések és a naplózott hibajavítás együttes alkalmazásával garantálja az adatkészlet megbízhatóságát.

 #1.5.1    Level: 1    Role: D
 Ellenőrizze, hogy az automatizált tesztek minden adatbetöltés vagy jelentős átalakítás során észlelik-e a formátumhibákat, null értékeket és címkeeltolódásokat.
 #1.5.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a sikertelen adatállományok karanténba kerülnek-e audit nyomvonalakkal.
 #1.5.3    Level: 2    Role: V
 Ellenőrizze, hogy a tématerületi szakértők által végzett manuális mintavételes ellenőrzések statisztikailag jelentős mintát fednek-e le (pl. ≥1% vagy 1 000 minta, a nagyobb érték alapján, vagy a kockázatértékelés szerint meghatározva), hogy az automatizálás által nem észlelt finom minőségi problémákat azonosítani lehessen.
 #1.5.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a javítási lépések hozzá vannak-e fűzve az eredetiség rekordokhoz.
 #1.5.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a minőségi kapuk letiltják a gyenge minőségű adatokat, kivéve, ha az kivételek jóváhagyásra kerültek.

---

### C1.6 Adathamisítás Felismerése

Alkalmazzon statisztikai anomáliaészlelést és elkülönítési munkafolyamatokat az ellenséges beszúrások megállítására.

 #1.6.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az anomáliaészlelési technikákat (például statisztikai módszerek, kiugró értékek felismerése, beágyazás elemzés) alkalmazzák-e a betanítási adatok feldolgozásakor és a főbb tanítási futtatások előtt a potenciális mérgezési támadások vagy szándékos adatkárosodás azonosítása érdekében.
 #1.6.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a jelzett minták kézi felülvizsgálatot váltanak-e ki a képzés előtt.
 #1.6.3    Level: 2    Role: V
 Ellenőrizze, hogy az eredmények beillesztésre kerülnek-e a modell biztonsági dossziéjába, és tájékoztatják-e a folyamatos fenyegetettségi hírszerzést.
 #1.6.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a felismerési logika frissüljön az új fenyegetésinformációkkal.
 #1.6.5    Level: 3    Role: D/V
 Ellenőrizze, hogy az online tanulási folyamatok figyelik-e az eloszláseltolódást.
 #1.6.6    Level: 3    Role: D/V
 Ellenőrizze, hogy a rendszer kockázati profilja és adatforrásai alapján figyelembe vették-e és végrehajtották-e a specifikus védelmi intézkedéseket a ismert adatmérgezési támadástípusok, például címkeátszabás, hátsóajtó trigger beszúrása, befolyásoló példányok elleni támadások ellen.

---

### C1.7 Felhasználói adatok törlése és hozzájárulás érvényesítése

Tiszteld a törlési és hozzájárulás-visszavonási kéréseket az összes adattáron, biztonsági mentésen és származtatott állományon.

 #1.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a törlési munkafolyamatok eltávolítják-e az elsődleges és származtatott adatokat, valamint értékeljék a modellre gyakorolt hatást, továbbá hogy az érintett modellekre gyakorolt hatást értékelik és szükség esetén kezelik (például újratanítással vagy újrakalibrálással).
 #1.7.2    Level: 2    Role: D
 Ellenőrizze, hogy léteznek-e olyan mechanizmusok, amelyek nyomon követik és tiszteletben tartják a felhasználói hozzájárulás (és visszavonások) terjedelmét és állapotát a tanításhoz használt adatok esetében, valamint hogy a hozzájárulást érvényesítik, mielőtt az adatokat beépítenék új tanítási folyamatokba vagy jelentős modellfrissítésekbe.
 #1.7.3    Level: 2    Role: V
 Ellenőrizze, hogy a munkafolyamatokat évente tesztelik és naplózzák.

---

### C1.8 Ellátási lánc biztonság

Külső adatforrásokat ellenőrizzen, és az integritást hitelesített, titkosított csatornákon keresztül igazolja.

 #1.8.1    Level: 2    Role: D/V
 Ellenőrizze, hogy a harmadik fél adatbeszállítók, beleértve az előre betanított modellek és külső adatkészletek szolgáltatóit, megfelelnek-e a biztonsági, adatvédelmi, etikus beszerzési és adatminőségi előzetes vizsgálatoknak, mielőtt az adataikat vagy modelljeiket integrálják.
 #1.8.2    Level: 1    Role: D
 Ellenőrizze, hogy a külső átvitelek TLS-t, hitelesítést és integritásellenőrzéseket használnak-e.
 #1.8.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a magas kockázatú adatforrások (pl. ismeretlen eredetű nyílt forráskódú adatkészletek, jóváhagyatlan beszállítók) fokozott vizsgálatnak legyenek alávetve, például elszigetelt elemzés, átfogó minőség- és torzításellenőrzés, valamint célzott mérgezésészlelés, mielőtt érzékeny alkalmazásokban használnák őket.
 #1.8.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a harmadik felektől származó előre betanított modelleket megvizsgálták-e beágyazott torzítások, esetleges hátsóajtók, az architektúrájuk integritása, valamint az eredeti tanító adatok eredete szempontjából a finomhangolás vagy bevezetés előtt.

---

### C1.9 Ellenséges mintaészlelés

Alkalmazzon intézkedéseket a tanítási fázis során, például ellenséges tanítást, a modell ellenállóképességének növelésére az ellenséges példákkal szemben.

 #1.9.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a megfelelő védekezések, például az ellenséges tréning (generált ellenséges példák használatával), a perturbált bemenetekkel történő adatnövelés vagy a robusztus optimalizációs technikák be vannak-e vezetve és hangolva a releváns modellek számára a kockázatértékelés alapján.
 #1.9.2    Level: 2    Role: D/V
 Ellenőrizze, hogy ha adversariális képzést alkalmaznak, akkor az adversariális adathalmazok létrehozása, kezelése és verziókövetése dokumentált és ellenőrzött legyen.
 #1.9.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az ellenséges robusztusságú tréning hatása a modell teljesítményére (mind tiszta, mind ellenséges bemenetek esetén) és a méltányossági mutatókra ki van értékelve, dokumentálva és nyomon követve.
 #1.9.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a támadóellenes képzés és a robusztusság stratégiáit időszakosan felülvizsgálják és frissítik az evolúciós támadási technikák elleni védekezés érdekében.

---

### C1.10 Adatvonal követhetősége és nyomonkövethetősége

Kövesse nyomon minden adatpont teljes útját a forrástól a modell bemenetéig az átláthatóság és az incidenskezelés érdekében.

 #1.10.1    Level: 2    Role: D/V
 Ellenőrizze, hogy minden adatpont származási lánca, beleértve az összes átalakítást, bővítést és összevonást, dokumentálva van-e és visszaállítható legyen.
 #1.10.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a származási rekordok megváltoztathatatlanok, biztonságosan tároltak, és hozzáférhetők legyenek auditok vagy vizsgálatok számára.
 #1.10.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a származáskövetés mind a nyers, mind a szintetikus adatokat lefedi-e.

---

### C1.11 Szintetikus adatkezelés

Biztosítsa, hogy a szintetikus adatokat megfelelően kezeljék, címkézzék és kockázatértékeljék.

 #1.11.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az összes szintetikus adat egyértelműen fel legyen címkézve, és megkülönböztethető legyen a valós adatoktól a teljes adatfeldolgozási folyamat során.
 #1.11.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a szintetikus adatok generálási folyamata, paraméterei és a tervezett felhasználásuk dokumentálva vannak-e.
 #1.11.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a szintetikus adatokat kockázatértékelték-e elfogultság, adatvédelmi szivárgás és reprezentációs problémák szempontjából, mielőtt azokat a tréning során felhasználnák.

---

### C1.12 Adathozzáférés-figyelés és anomáliadetektálás

Figyelje és jelezze a szokatlan hozzáféréseket a tanítóadatokhoz, hogy felismerje a belső fenyegetéseket vagy az adatkiszivárgást.

 #1.12.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az összes hozzáférés a képzési adatokhoz naplózva van, beleértve a felhasználót, az időpontot és a műveletet.
 #1.12.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az elérési naplókat rendszeresen átvizsgálják szokatlan mintázatok, például nagy mennyiségű export vagy új helyekről történő hozzáférés esetén.
 #1.12.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a riasztások gyanús hozzáférési események esetén keletkeznek-e, és azokat haladéktalanul kivizsgálják-e.

---

### C1.13 Adatmegőrzési és lejárati szabályzatok

Határozzon meg és érvényesítsen adatmegőrzési időszakokat a felesleges adattárolás minimalizálása érdekében.

 #1.13.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden képzési adathalmazra vonatkozóan meg vannak-e határozva a kifejezett megtartási időszakok.
 #1.13.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az adatkészletek életciklusuk végén automatikusan lejárnak-e, törlődnek-e vagy felülvizsgálatra kerülnek a törlés érdekében.
 #1.13.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a megőrzési és törlési műveletek naplózottak és auditálhatók legyenek.

---

### C1.14 Szabályozói és joghatósági megfelelés

Biztosítsa, hogy minden képzési adat megfeleljen az alkalmazandó jogszabályoknak és előírásoknak.

 #1.14.1    Level: 2    Role: D/V
 Ellenőrizze, hogy minden adatállomány esetében az adathelyzet és a határokon átnyúló adatátviteli követelmények azonosításra kerülnek és érvényesítésre kerülnek.
 #1.14.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az adott ágazatra vonatkozó előírásokat (pl. egészségügy, pénzügy) azonosították-e és kezelik-e az adatkezelés során.
 #1.14.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a vonatkozó adatvédelmi törvényeknek (pl. GDPR, CCPA) való megfelelés dokumentált és rendszeresen felülvizsgált legyen.

---

### C1.15 Adatvízjelzés és ujjlenyomatkészítés

Hamisítás nélküli újrafelhasználás vagy tulajdonjogi, illetve érzékeny adatok kiszivárgásának észlelése.

 #1.15.1    Level: 3    Role: D/V
 Ellenőrizze, hogy az adatkészletek vagy alkészletek vízjellel vagy ujjlenyomattal vannak-e ellátva, ahol lehetséges.
 #1.15.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a vízjelező/ujjlenyomat-azonosító módszerek nem vezetnek-e be elfogultságot vagy adatvédelmi kockázatokat.
 #1.15.3    Level: 3    Role: D/V
 Győződjön meg arról, hogy rendszeres ellenőrzéseket végeznek az engedély nélküli vízjeles adatok újrafelhasználásának vagy kiszivárgásának észlelésére.

---

### C1.16 Adatvédelmi érintett jogainak kezelése

Támogassa az adatvédelmi érintetti jogokat, mint például a hozzáférést, helyesbítést, korlátozást és tiltakozást.

 #1.16.1    Level: 2    Role: D/V
 Ellenőrizze, hogy léteznek-e mechanizmusok az érintetti kérelmekre vonatkozó hozzáférés, helyesbítés, korlátozás vagy tiltakozás kezelésére.
 #1.16.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a kérelmek rögzítve, nyomon követve és a jogszabályban előírt határidőn belül teljesítve legyenek.
 #1.16.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az adat alany jogainak folyamatát rendszeresen tesztelik és felülvizsgálják hatékonyságuk érdekében.

---

### C1.17 Adatkészlet verzió hatás elemzése

Értékelje a adatbázis-változások hatását, mielőtt frissítené vagy lecserélné a verziókat.

 #1.17.1    Level: 2    Role: D/V
 Ellenőrizze, hogy hatáselemzést végeznek-e egy adatállomány verziójának frissítése vagy cseréje előtt, amely kiterjed a modell teljesítményére, méltányosságára és megfelelőségére.
 #1.17.2    Level: 2    Role: D/V
 Győződjön meg arról, hogy a hatáselemzés eredményei dokumentáltak és az érintett érdekeltek által átvizsgáltak.
 #1.17.3    Level: 2    Role: D/V
 Ellenőrizze, hogy léteznek-e visszaállítási tervek arra az esetre, ha az új verziók elfogadhatatlan kockázatokat vagy visszalépéseket vezetnének be.

---

### C1.18 Adatmegjelölési munkaerő biztonsága

Biztosítsák az adatok annotálásában részt vevő személyzet biztonságát és épségét.

 #1.18.1    Level: 2    Role: D/V
 Ellenőrizze, hogy minden adatmegjelölésben részt vevő személy háttérellenőrzésen esett át, valamint képzést kapott az adatbiztonság és adatvédelem terén.
 #1.18.2    Level: 2    Role: D/V
 Ellenőrizze, hogy minden annotációs személyzet aláírta-e a titoktartási és titokvédelmi megállapodásokat.
 #1.18.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az annotációs platformok érvényesítik-e a hozzáférési szabályokat, és figyelik-e a belső fenyegetéseket.

---

### Hivatkozások

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## C2 Felhasználói Bemenet Érvényesítés

### Ellenőrzési Célkitűzés

A felhasználói bemenet megbízható érvényesítése az elsődleges védelem az AI rendszerek legkárosabb támadásaival szemben. A prompt befecskendezési támadások felülírhatják a rendszer utasításait, kiszivárogtathatják az érzékeny adatokat, vagy a modellt nem engedélyezett viselkedés felé terelhetik. Kutatások szerint, amíg nincsenek dedikált szűrők és utasítási hierarchiák, a nagyon hosszú kontextus ablakokat kihasználó "többszörös" jailbreak támadások hatékonyak lesznek. Emellett a finom ellenfél perturbációs támadások — például homoglif cserék vagy leetspeak — csendesen megváltoztathatják a modell döntéseit.

---

### C2.1 Utasításbefecskendezés elleni védelem

A prompt befecskendezés az egyik legnagyobb kockázat az AI rendszerek számára. Ennek a taktikának a kivédésére statikus mintaszűrők, dinamikus osztályozók és az utasítási hierarchia betartásának kombinációját alkalmazzák.

 #2.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a felhasználói bemenetek folyamatosan frissített ismert promptinjekció-mintákat tartalmazó könyvtár ellen legyenek szűrve (például jailbreak kulcsszavak, "figyelmen kívül hagyni az előzőt", szerepjáték-láncok, közvetett HTML/URL támadások).
 #2.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a rendszer érvényesíti-e az utasítási hierarchiát, amelyben a rendszer- vagy fejlesztői üzenetek felülírják a felhasználói utasításokat, még a kontextusablak bővítése után is.
 #2.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a támadó értékelési teszteket (például a Red Team "many-shot" kéréseit) minden modell- vagy prompt-sablon kiadás előtt elvégzik-e, sikerességi küszöbértékek és automatizált akadályozók alkalmazásával a visszaesések elkerülésére.
 #2.1.4    Level: 2    Role: D
 Ellenőrizze, hogy a harmadik féltől származó tartalmakból (weboldalak, PDF-ek, e-mailek) eredő kérések elkülönített elemzési környezetben vannak-e megtisztítva, mielőtt beillesztésre kerülnek a fő kérésbe.
 #2.1.5    Level: 3    Role: D/V
 Ellenőrizze, hogy minden prompt-szűrő szabályfrissítés, osztályozó modellverzió és tiltólista változás verziókezelve és auditálható legyen.

---

### C2.2 Ellenséges példák elleni ellenálló képesség

A természetes nyelvfeldolgozó (NLP) modellek továbbra is érzékenyek az apró karakter- vagy szószintű módosításokra, amelyeket az emberek gyakran nem vesznek észre, ám a modellek hajlamosak tévesen osztályozni.

 #2.2.1    Level: 1    Role: D
 Ellenőrizze, hogy az alapvető bemeneti normalizációs lépések (Unicode NFC, homoglifák leképezése, szóközök eltávolítása) lefutnak-e a tokenizálás előtt.
 #2.2.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a statisztikai anomáliaészlelés jelzi-e azokat a bemeneteket, amelyek szokatlanul magas szerkesztési távolsággal rendelkeznek a nyelvi normákhoz képest, túlzottan ismétlődő tokeneket tartalmaznak, vagy rendellenes beágyazási távolságokat mutatnak.
 #2.2.3    Level: 2    Role: D
 Ellenőrizze, hogy az inferencia-pipeline támogatja-e az opcionális, támadásálló képzéssel megerősített modellváltozatokat vagy védelmi rétegeket (például véletlenszerűsítés, védelmi desztilláció) a nagy kockázatú végpontok számára.
 #2.2.4    Level: 2    Role: V
 Ellenőrizze, hogy a gyanús támadó bemenetek elkülönítésre kerülnek, és a teljes adatcsomaggal együtt naplózva vannak (az azonosítható személyes adatok eltávolítása után).
 #2.2.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a robosztussági mutatókat (ismert támadási csomagok sikerességi aránya) időben nyomon követik-e, és hogy a regressziók kiadási blokkolót indítanak-e.

---

### C2.3 Séma, típus és hossz validáció

Az AI támadások, amelyek hibás vagy túlméretezett bemeneteket tartalmaznak, elemzési hibákat, mezők közötti prompt szivárgást és erőforrás-kimerülést okozhatnak. A szigorú séma-ellenőrzés szintén alapfeltétel a determinisztikus eszközhívások végrehajtásakor.

 #2.3.1    Level: 1    Role: D
 Ellenőrizze, hogy minden API vagy függvényhívási végpont egyértelmű bemeneti sémát definiál-e (JSON Schema, Protobuf vagy multimodális megfelelő), és hogy a bemenetek érvényesítve vannak-e a prompt összeállítása előtt.
 #2.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a maximális token- vagy bájthatárokat meghaladó bemenetek biztonságos hibával elutasításra kerülnek, és soha nem kerülnek néma levágásra.
 #2.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a típusellenőrzések (pl. numerikus tartományok, enumerációs értékek, képek/hangok MIME-típusai) szerveroldalon is érvényesítve legyenek, ne csak a kliensoldali kódban.
 #2.3.4    Level: 2    Role: D
 Ellenőrizze, hogy a szemantikai validátorok (pl. JSON Schema) állandó idő alatt futnak-e, hogy megakadályozzák az algoritmikus DoS-t.
 #2.3.5    Level: 3    Role: V
 Ellenőrizze, hogy az érvényesítési hibákat vörösített adatdarabokkal és egyértelmű hibakódokkal rögzítik-e a biztonsági kivizsgálás segítése érdekében.

---

### C2.4 Tartalom- és irányelvellenőrzés

A fejlesztőknek képesnek kell lenniük felismerni a szintaktikailag érvényes, de tiltott tartalomra (például illegális utasítások, gyűlöletbeszéd és szerzői jog által védett szöveg) vonatkozó kéréseket, és meg kell akadályozniuk azok terjedését.

 #2.4.1    Level: 1    Role: D
 Ellenőrizze, hogy a tartalom osztályozó (nulladik lépéses vagy finomhangolt) minden bemenetet értékel-e erőszak, önkárosítás, gyűlölet, szexuális tartalom és illegális kérés szempontjából, konfigurálható küszöbértékekkel.
 #2.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a szabályzatot sértő bemenetek egységes elutasításokat vagy biztonságos befejezéseket kapnak-e, hogy ne terjedjenek tovább a további LLM-hívásokban.
 #2.4.3    Level: 2    Role: D
 Ellenőrizze, hogy a szűrőmodellt vagy szabályrendszert legalább negyedévente átképezték/frissítették-e, újonnan észlelt jailbreak vagy szabálykerülési minták bevonásával.
 #2.4.4    Level: 2    Role: D
 Ellenőrizze, hogy a szűrés megfelel-e a felhasználóra szabott szabályzatoknak (életkor, regionális jogi korlátozások) a kérés időpontjában feloldott attribútumalapú szabályok révén.
 #2.4.5    Level: 3    Role: V
 Ellenőrizze, hogy a szűrési naplók tartalmazzák-e az osztályozó bizalmi pontszámait és a szabályzati kategória címkéket a SOC korrelációhoz és a későbbi red-team lejátszáshoz.

---

### C2.5 Bemeneti sebességkorlátozás és visszaélések megelőzése

A fejlesztőknek meg kell akadályozniuk a visszaéléseket, az erőforrás-kimerülést és az automatizált támadásokat az AI rendszerek ellen az input sebességének korlátozásával és a rendellenes használati minták felismerésével.

 #2.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden bemeneti végponton érvényesülnek-e a felhasználónkénti, IP-címenkénti és API-kulcsonkénti lekérési korlátozások.
 #2.5.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a burst és fenntartott sebességkorlátok megfelelően vannak-e beállítva a DoS és brute force támadások megelőzése érdekében.
 #2.5.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a rendellenes használati minták (pl. gyors egymás utáni kérések, bemeneti túlterhelés) automatikus blokkolást vagy továbbításokat váltanak-e ki.
 #2.5.4    Level: 3    Role: V
 Ellenőrizze, hogy az visszaélés megelőzési naplók megőrzésre és áttekintésre kerülnek-e az újonnan megjelenő támadási minták felderítése érdekében.

---

### C2.6 Többmódusú bemeneti érvényesítés

Az AI rendszereknek robosztus érvényesítést kell tartalmazniuk nem szöveges bemenetekre (képek, hang, fájlok), hogy megakadályozzák az injekciót, kikerülést vagy az erőforrásokkal való visszaélést.

 #2.6.1    Level: 1    Role: D
 Ellenőrizze, hogy minden nem szöveges bemenetet (képek, hangok, fájlok) típus, méret és formátum szerint validálnak-e a feldolgozás előtt.
 #2.6.2    Level: 2    Role: D/V
 Győződjön meg arról, hogy a fájlokat malware és szteganográfiai terhelések szempontjából átvizsgálják a feldolgozás előtt.
 #2.6.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kép/hang bemeneteket ártalmas módosítások vagy ismert támadási minták szempontjából vizsgálták-e.
 #2.6.4    Level: 3    Role: V
 Ellenőrizze, hogy a multimodális bemeneti érvényesítési hibákat naplózzák-e, és hogy ezek riasztásokat váltanak-e ki vizsgálat céljából.

---

### C2.7 Bemeneti eredetiség és hivatkozás

Az AI rendszereknek támogatniuk kell az auditálást, visszaélések nyomon követését és a megfelelést azáltal, hogy figyelik és megjelölik az összes felhasználói bemenet eredetét.

 #2.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden felhasználói bemenet metaadatokkal (felhasználói azonosító, munkamenet, forrás, időbélyeg, IP-cím) van-e ellátva a bevitelkor.
 #2.7.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az összes feldolgozott bemenet esetében a származási metaadatok megőrződnek és auditálhatók legyenek.
 #2.7.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az anomalikus vagy nem megbízható bemeneti forrásokat jelzik-e, és fokozott ellenőrzés vagy blokkolás alá esnek-e.

---

### C2.8 Valós idejű adaptív fenyegetésészlelés

A fejlesztőknek fejlett, mesterséges intelligenciára specializált fenyegetésészlelő rendszereket kell alkalmazniuk, amelyek alkalmazkodnak az új támadási mintákhoz, és valós idejű védelmet nyújtanak összekompilált mintaillesztéssel.

 #2.8.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a fenyegetésészlelési minták optimalizált reguláris kifejezés motorokká vannak-e fordítva a nagy teljesítményű valós idejű szűrés érdekében, minimális késleltetési hatással.
 #2.8.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a fenyegetésészlelő rendszerek külön mintakönyvtárakat tartanak-e fenn a különböző fenyegetéskategóriákhoz (utasításinjekció, káros tartalom, érzékeny adatok, rendszerparancsok).
 #2.8.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az adaptív fenyegetésészlelés tartalmaz-e gépi tanulási modelleket, amelyek frissítik a fenyegetésérzékenységet a támadások gyakorisága és sikerrátái alapján.
 #2.8.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a valós idejű fenyegetésfelderítő adatok automatikusan frissítik-e a mintagyűjteményeket új támadási aláírásokkal és kompromittálódási indikátorokkal (IOC-k).
 #2.8.5    Level: 3    Role: D/V
 Bizonyosodjon meg arról, hogy a fenyegetésészlelési hamis pozitív arányokat folyamatosan figyelik, és a minták specifikusságát automatikusan hangolják úgy, hogy minimalizálják a jogos használati esetekbe történő beavatkozást.
 #2.8.6    Level: 3    Role: D/V
 Ellenőrizze, hogy a kontextuális fenyegetés elemzés figyelembe veszi-e a bemeneti forrást, a felhasználói viselkedési mintákat és a munkamenet előzményeit a felismerési pontosság javítása érdekében.
 #2.8.7    Level: 3    Role: D/V
 Ellenőrizze, hogy a fenyegetésészlelési teljesítménymutatókat (észlelési arány, feldolgozási késleltetés, erőforrás-használat) valós időben figyelik és optimalizálják.

---

### C2.9 Többmodális biztonsági érvényesítési folyamat

A fejlesztőknek biztonsági érvényesítést kell biztosítaniuk a szöveg, kép, hang és egyéb mesterséges intelligencia bemeneti módok esetében, konkrét fenyegetésészlelési típusokkal és erőforrás-elszigeteléssel.

 #2.9.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden bemeneti modalitás rendelkezik-e dedikált biztonsági érvényesítőkkel, dokumentált fenyegetési mintákkal (szöveg: prompt injekció, képek: steganográfia, hang: spektrogram támadások) és érzékelési küszöbértékekkel.
 #2.9.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a többmodális bemenetek elkülönített homokozókban kerülnek feldolgozásra, amelyeknél meghatározott erőforrás-korlátok (memória, CPU, feldolgozási idő) vannak érvényben, melyek minden egyes modalitás típusra külön-külön vonatkoznak, és ezek dokumentálva vannak a biztonsági szabályzatokban.
 #2.9.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kereszt-modalitású támadásészlelés felismeri-e a több bemeneti típust átfogó koordinált támadásokat (pl. szteganográfiai adatkódok képekben, melyeket szöveges promptinjekcióval kombinálnak) korrelációs szabályok és riasztásgenerálás segítségével.
 #2.9.4    Level: 3    Role: D/V
 Igazolja, hogy a többmodális érvényesítési hibák részletes naplózást váltanak ki, beleértve az összes bemeneti modalitást, az érvényesítési eredményeket, a fenyegetési pontszámokat és a korrelációs elemzést strukturált naplóformátumokkal a SIEM integrációhoz.
 #2.9.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a modalitás-specifikus tartalom-osztályozók a dokumentált ütemtervek szerint (legalább negyedévente) frissítve legyenek, az új fenyegetési mintákkal, támadó példákkal, és a teljesítménybenchmarkok a minimális küszöbértékek felett maradjanak.

---

### Hivatkozások

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## C3 modell életciklus-kezelés és változásvezérlés

### Irányítási célkitűzés

A mesterséges intelligencia rendszereknek olyan változáskezelési folyamatokat kell alkalmazniuk, amelyek megakadályozzák, hogy illetéktelen vagy nem biztonságos modellmódosítások kerüljenek éles környezetbe. Ez az ellenőrzés biztosítja a modell integritását az egész életciklus során – a fejlesztéstől a telepítésen át a kiselejtezésig –, ami lehetővé teszi a gyors incidensválaszt és fenntartja a felelősségre vonhatóságot minden változtatás esetén.

Alapvető biztonsági cél: Csak az engedélyezett, ellenőrzött modellek jussanak a termelésbe olyan szabályozott folyamatok alkalmazásával, amelyek biztosítják az integritást, nyomon követhetőséget és helyreállíthatóságot.

---

### C3.1 Modellengedélyezés és integritás

Csak az ellenőrzött integritású, engedélyezett modellek kerülhetnek gyártási környezetbe.

 #3.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az összes modell tárgy (súlyok, konfigurációk, tokenizálók) kriptográfiailag aláírt-e az arra jogosult entitások által a telepítés előtt.
 #3.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a modell integritását a telepítéskor igazolják-e, és hogy a aláírás-ellenőrzési hibák megakadályozzák a modell betöltését.
 #3.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a modell eredetét igazoló feljegyzések tartalmazzák-e az engedélyező fél azonosítóját, a képzési adatok ellenőrzőösszegeit, az érvényesítési teszteredményeket sikerességi/hibajelentési státusszal, valamint a létrehozás időbélyegét.
 #3.1.4    Level: 2    Role: D/V
 Ellenőrizze, hogy az összes modell műtárgy szemantikus verziózást (FŐ.VÁLTOZAT.PONT) használ-e, és legyen dokumentált kritérium arra, hogy mikor növekszik az egyes verziókomponens.
 #3.1.5    Level: 2    Role: V
 Ellenőrizze, hogy a függőségkövetés valós idejű készletet tart fenn, amely lehetővé teszi az összes fogyasztó rendszer gyors azonosítását.

---

### C3.2 Modell validálás és tesztelés

A modelleknek a telepítés előtt meg kell felelniük a meghatározott biztonsági és védelmi érvényesítéseknek.

 #3.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a modellek automatikus biztonsági tesztelésen mennek-e keresztül, amely magában foglalja a bemeneti érvényesítést, a kimeneti tisztítást és a biztonsági értékeléseket előre meghatározott szervezeti átmeneti/elbukási küszöbértékekkel a telepítés előtt.
 #3.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a validációs hibák automatikusan blokkolják-e a modell telepítését az előre kijelölt, engedéllyel rendelkező személyek által dokumentált üzleti indoklással történő kifejezett felülbírálati jóváhagyása után.
 #3.2.3    Level: 2    Role: V
 Ellenőrizze, hogy a teszteredmények kriptográfiailag alá vannak-e írva, és visszafordíthatatlanul kapcsolódnak-e a validált adott modellverzió hash-éhez.
 #3.2.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a sürgősségi telepítésekhez dokumentált biztonsági kockázatértékelés és előre kijelölt biztonsági hatóság jóváhagyása szükséges-e az előre egyeztetett határidőkön belül.

---

### C3.3 Szabályozott Telepítés és Visszagörgetés

A modelltelepítéseket szabályozni, ellenőrizni és visszafordíthatóvá kell tenni.

 #3.3.1    Level: 1    Role: D
 Ellenőrizze, hogy a termelési telepítések fokozatos bevezetési mechanizmusokat valósítanak-e meg (pl. kanári telepítések, kék-zöld telepítések), amelyek automatikus visszagörgetési kiváltó okokkal rendelkeznek az előre egyeztetett hibaarányok, késleltetési küszöbök vagy biztonsági figyelmeztetési kritériumok alapján.
 #3.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a visszagörgetési képességek atomi módon állítják-e vissza a teljes modell állapotát (súlyokat, konfigurációkat, függőségeket) a szervezet által előre meghatározott időablakokban.
 #3.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a telepítési folyamatok érvényesítik-e a kriptográfiai aláírásokat és kiszámítják-e a sértetlenségi ellenőrzőösszegeket a modell aktiválása előtt, és sikertelenül zárulnak-e a telepítés bármilyen eltérés esetén.
 #3.3.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a vészhelyzeti modellleállítási képességek képesek-e az előre meghatározott válaszidőn belül letiltani a modell végpontjait automatizált áramkör-megszakítók vagy kézi leállítókapcsolók segítségével.
 #3.3.5    Level: 2    Role: V
 Ellenőrizze, hogy a visszagörgetési műtermékek (korábbi modellverziók, konfigurációk, függőségek) az szervezeti szabályzatoknak megfelelően megőrzésre kerülnek-e változtathatatlan tárolás révén az incidenskezelés érdekében.

---

### C3.4 Változásfelelősség és Ellenőrzés

Az összes modell életciklusában bekövetkező változásnak nyomon követhetőnek és auditálhatónak kell lennie.

 #3.4.1    Level: 1    Role: V
 Ellenőrizze, hogy minden modellváltoztatás (telepítés, konfiguráció, kivonás) rögzít-e megváltoztathatatlan auditfeljegyzéseket, amelyek tartalmaznak egy időbélyeget, egy hitelesített végrehajtó személyazonosságot, a változás típusát, valamint az előző és utáni állapotokat.
 #3.4.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az audit naplóhoz való hozzáférés megfelelő jogosultságot igényel, és minden hozzáférési kísérletet felhasználói azonosítóval és időbélyeggel naplóznak.
 #3.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a prompt sablonok és rendszerüzenetek verziókezelve vannak-e git tárolókban, kötelező kódáttekintéssel és kijelölt felülvizsgálók jóváhagyásával a telepítés előtt.
 #3.4.4    Level: 2    Role: V
 Ellenőrizze, hogy az auditnaplók tartalmaznak-e elegendő részletet (modell kivonatok, konfigurációs pillanatképek, függőségi verziók) a modell állapotának teljes rekonstrukciójához bármely, a megőrzési időszakon belüli időbélyegző alapján.

---

### C3.5 Biztonságos Fejlesztési Gyakorlatok

A modellfejlesztési és betanítási folyamatoknak biztonságos gyakorlatokat kell követniük a sérülések megelőzése érdekében.

 #3.5.1    Level: 1    Role: D
 Ellenőrizze, hogy a modellfejlesztési, tesztelési és éles környezetek fizikailag vagy logikailag elkülönítettek-e. Nincs közös infrastruktúrájuk, különálló hozzáférés-vezérlésük és elszigetelt adattáraik.
 #3.5.2    Level: 1    Role: D
 Ellenőrizze, hogy a modellképzés és finomhangolás elszigetelt környezetekben történik, korlátozott hálózati hozzáféréssel.
 #3.5.3    Level: 1    Role: D/V
 Bizonyosodjon meg arról, hogy az edzési adatforrásokat integritásellenőrzésekkel validálják, és megbízható források által hitelesítik, dokumentált nyomonkövetési lánccal a modellfejlesztés előtti használat előtt.
 #3.5.4    Level: 2    Role: D
 Ellenőrizze, hogy a modellfejlesztési anyagok (hiperparaméterek, tanítási szkriptek, konfigurációs fájlok) verziókezelés alatt állnak, és a tanításhoz való használat előtt szükséges a társszakértői jóváhagyás.

---

### C3.6 Modell visszavonása és kivonása a használatból

A modelleket biztonságosan nyugdíjazni kell, amikor már nincs rájuk szükség, vagy amikor biztonsági problémákat azonosítanak.

 #3.6.1    Level: 1    Role: D
 Ellenőrizze, hogy a modellleállítási folyamatok automatikusan átvizsgálják-e a függőségi gráfokat, azonosítják-e az összes felhasználó rendszert, és biztosítanak-e előre egyeztetett értesítési időszakokat a leállítás előtt.
 #3.6.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a nyugdíjazott modell artifactumok biztonságosan törlődnek-e kriptográfiai törlés vagy többszörös felülírás alkalmazásával, az dokumentált adatokmegőrzési szabályzatok szerint, és rendelkezzenek igazolt megsemmisítési tanúsítványokkal.
 #3.6.3    Level: 2    Role: V
 Ellenőrizze, hogy a modell kivezetési események időbélyeggel és végrehajtó azonosítóval vannak rögzítve, valamint hogy a modell aláírásokat visszavonják a további felhasználás megakadályozása érdekében.
 #3.6.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a vészhelyzeti modellkivonás képes-e letiltani a modell hozzáférését az előre meghatározott vészhelyzeti válaszidőn belül automatizált leállító kapcsolókon keresztül, amennyiben kritikus biztonsági sebezhetőségek kerülnek felfedezésre.

---

### Hivatkozások

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## C4 infrastruktúra, konfiguráció és telepítési biztonság

### Irányítási célkitűzés

Az AI infrastruktúrát meg kell erősíteni a jogosultságnövelés, az ellátási lánc manipulációja és az oldalirányú mozgás ellen biztonságos konfiguráció, futásidejű elkülönítés, megbízható telepítési folyamatok és átfogó megfigyelés révén. Csak a jogosult, ellenőrzött infrastruktúraelemek és konfigurációk juthatnak el a termelési környezetbe olyan ellenőrzött folyamatokon keresztül, amelyek fenntartják a biztonságot, integritást és auditálhatóságot.

Alapvető biztonsági cél: Csak kriptográfiai aláírással rendelkező, sebezhetőség-ellenőrzött infrastruktúraelemek juthatnak el a gyártási környezetbe automatizált érvényesítési folyamatokon keresztül, amelyek érvényesítik a biztonsági szabályzatokat és megőrzik a megváltoztathatatlan audit nyomvonalakat.

---

### C4.1 Futásidejű környezet izolációja

Megakadályozza a konténerből való kijutást és a jogosultságkiterjesztést kernel-szintű izolációs primitívek és kötelező hozzáférés-vezérlés alkalmazásával.

 #4.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden AI-konténer eltávolítja-e az összes Linux képességet, kivéve a CAP_SETUID, CAP_SETGID és a biztonsági alapvonalakban dokumentált, kifejezetten szükséges képességeket.
 #4.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a seccomp profilok minden rendszerhívást blokkolnak, kivéve az előzetesen jóváhagyott engedélyezőlistákon szereplőket, és hogy a megsértések a konténer leállítását és biztonsági riasztások generálását eredményezik-e.
 #4.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az MI-munkaterhelések olvasható gyökérfájlrendszerrel, tmpfs ideiglenes adatokhoz, valamint nevük szerint hivatkozott kötetekkel futnak-e tartós adatok esetén, és hogy az noexec csatolási opciók érvényesítve vannak-e.
 #4.1.4    Level: 2    Role: D/V
 Ellenőrizze, hogy az eBPF-alapú futásidejű megfigyelés (Falco, Tetragon vagy azzal egyenértékű) felismeri-e a jogosultságnövelési kísérleteket, és automatikusan leállítja-e a szabályszegő folyamatokat a szervezeti válaszidő követelményeinek megfelelően.
 #4.1.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a magas kockázatú AI munkaterhelések hardveralapú elkülönített környezetekben futnak-e (Intel TXT, AMD SVM vagy dedikált bare-metal csomópontok), és rendelkeznek azonosítási megerősítéssel.

---

### C4.2 Biztonságos építési és telepítési csővezetékek

Biztosítsa a kriptográfiai integritást és az ellátási lánc biztonságát reprodukálható buildelések és aláírt műtárgyak segítségével.

 #4.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az infrastruktúra-kód minden commit esetén eszközökkel (tfsec, Checkov vagy Terrascan) legyen átvizsgálva, és blokkolja az egyesítéseket KRITIKUS vagy MAGAS súlyosságú hibák esetén.
 #4.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a konténerépítések reprodukálhatók-e azonos SHA256 hashekkel az építések között, és hozza létre a Sigstore által aláírt, SLSA 3. szintű eredettörténeti igazolásokat.
 #4.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a tárolókép tartalmazza-e a CycloneDX vagy SPDX SBOM-okat, és a Cosign-nal alá legyen-e írva a regiszterbe történő feltöltés előtt, az aláíratlan képeket pedig a telepítésnél elutasítja.
 #4.2.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a CI/CD pipeline-ok HashiCorp Vault, AWS IAM-szerepkörök vagy Azure Managed Identity OIDC tokenjeit használják-e, amelyek élettartama nem haladja meg a szervezeti biztonsági előírásokban meghatározott határértékeket.
 #4.2.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a Cosign aláírások és az SLSA eredetiség hitelesítése megtörténik-e a telepítési folyamat során a konténer futtatása előtt, és hogy a hitelesítési hibák a telepítés sikertelenségéhez vezetnek-e.
 #4.2.6    Level: 2    Role: D/V
 Ellenőrizze, hogy az építési környezetek ideiglenes konténerekben vagy virtuális gépekben futnak-e, amelyek nem tartalmaznak tartós tárolót, és hálózati izolációval rendelkeznek a termelési VPC-ktől.

---

### C4.3 Hálózati biztonság és hozzáférés-vezérlés

Valósítson meg nullatérelv alapú hálózatot alapértelmezett megtagadási szabályokkal és titkosított kommunikációval.

 #4.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a Kubernetes NetworkPolicy-k vagy bármilyen megfelelő megoldás alapértelmezett tiltást alkalmaz-e a bejövő/kimenő forgalomra, explicit engedélyezési szabályokkal a szükséges portokra (443, 8080 stb.).
 #4.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az SSH (22-es port), az RDP (3389-es port) és a felhő metaadat végpontok (169.254.169.254) le vannak-e tiltva vagy tanúsítvány-alapú hitelesítést igényelnek-e.
 #4.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kimenő forgalom HTTP/HTTPS proxykon (például Squid, Istio vagy felhő NAT átjárók) keresztül szűrve van-e, domén engedélyező listákkal, és a letiltott kérések naplózásra kerülnek-e.
 #4.3.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a szolgáltatások közötti kommunikáció kölcsönös TLS-t használ-e, a tanúsítványokat a szervezeti szabályzat szerint forgatják, és a tanúsítványok érvényesítése érvényben van-e (nincs kihagyás-ellenőrzés jelző).
 #4.3.5    Level: 2    Role: D/V
 Ellenőrizze, hogy az MI infrastruktúra kizárólag dedikált VPC-kben/VNet-ekben működik, közvetlen internet-hozzáférés nélkül, és kizárólag NAT átjárókon vagy bastion hosztokon keresztül kommunikál.

---

### C4.4 Titkok és kriptográfiai kulcskezelés

Védd a hitelesítő adatokat hardveralapú tárolással és automatikus cserével, nulla bizalmi hozzáférés mellett.

 #4.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a titkok a HashiCorp Vaultban, az AWS Secrets Managerben, az Azure Key Vaultban vagy a Google Secret Managerben vannak-e tárolva, titkosítva AES-256-os állományi titkosítással.
 #4.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a kriptográfiai kulcsok FIPS 140-2 2. szintű HSM-ekben (AWS CloudHSM, Azure Dedicated HSM) vannak-e generálva, és hogy a kulcsforgatás megfelel-e a szervezeti kriptográfiai szabványnak.
 #4.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a titkok forgatása automatizált-e nulla leállási idővel történő telepítéssel, és azonnali forgatás történik-e személyzeti változások vagy biztonsági események kiváltására.
 #4.4.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a konténerképeket olyan eszközökkel (GitLeaks, TruffleHog vagy detect-secrets) vizsgálják-e, amelyek megakadályozzák az API-kulcsokat, jelszavakat vagy tanúsítványokat tartalmazó build-ek elkészítését.
 #4.4.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a gyártási titkos hozzáférés többfaktoros hitelesítést (MFA) igényel-e hardvertokenekkel (YubiKey, FIDO2), és hogy azt változtathatatlan auditnaplók rögzítik-e felhasználói azonosítókkal és időbélyegekkel.
 #4.4.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a titkok Kubernetes titkok, csatolt kötetek vagy init konténerek útján kerülnek-e beillesztésre, és győződjön meg arról, hogy a titkok soha nem kerülnek környezeti változókba vagy képekbe ágyazásra.

---

### C4.5 AI Munkaterhelés Homokozózás és Érvényesítés

Izolálja a nem megbízható MI-modelleket biztonságos homokozókban átfogó viselkedéselemzéssel.

 #4.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a külső MI-modellek gVisorban, microVM-ekben (például Firecracker, CrossVM) vagy Docker konténerekben futnak-e --security-opt=no-new-privileges és --read-only zászlókkal.
 #4.5.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a homokozó környezeteknek nincs hálózati kapcsolata (--network=none), vagy csak localhost hozzáférése van, és minden külső kérést iptables szabályok blokkolnak.
 #4.5.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az MI-modell érvényesítése tartalmazza-e az automatizált red-team tesztelést, amely szervezetileg meghatározott tesztlefedettséggel és viselkedéselemzéssel történik a hátsóajtó detektálására.
 #4.5.4    Level: 2    Role: D/V
 Ellenőrizze, hogy mielőtt egy MI-modellt élesítésre bocsátanak, a homokozós eredményeit jogosított biztonsági személyzet kriptográfiailag aláírja és megváltoztathatatlan audit naplókban tárolja.
 #4.5.5    Level: 2    Role: D/V
 Ellenőrizze, hogy az elszigetelt környezetek értékelések között megsemmisülnek és aranykép alapján újból létrejönnek, teljes fájlrendszer és memória tisztítással.

---

### C4.6 Infrastruktúra biztonsági megfigyelés

Folyamatosan vizsgálja és figyelje az infrastruktúrát automatizált javítással és valós idejű riasztással.

 #4.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a konténerképeket a szervezeti ütemtervek szerint átvizsgálják-e, ahol a KRITIKUS sebezhetőségek a szervezeti kockázati küszöbértékek alapján megakadályozzák a telepítést.
 #4.6.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az infrastruktúra megfelel-e a CIS Benchmarkoknak vagy a NIST 800-53 szabályozásoknak, az szervezet által meghatározott megfelelőségi küszöbökkel és az automatikus javítással a sikertelen ellenőrzések esetén.
 #4.6.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a MAGAS súlyosságú sérülékenységek a szervezeti kockázatkezelési ütemtervek szerint javítva legyenek, és legyenek vészhelyzeti eljárások az aktívan kihasznált CVE-k esetére.
 #4.6.4    Level: 2    Role: V
 Ellenőrizze, hogy a biztonsági riasztások integrálódnak-e a SIEM platformokkal (Splunk, Elastic vagy Sentinel) CEF vagy STIX/TAXII formátumok használatával, automatikus bővítéssel.
 #4.6.5    Level: 3    Role: V
 Ellenőrizze, hogy az infrastruktúra-mutatók ki legyenek exportálva a megfigyelőrendszerekbe (Prometheus, DataDog) SLA műszerfalakkal és vezetői jelentésekkel.
 #4.6.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a konfigurációs eltérés észlelve van-e eszközök (Chef InSpec, AWS Config) segítségével a szervezeti megfigyelési követelmények szerint, automatikus visszaállítással az illetéktelen változtatások esetén.

---

### C4.7 AI infrastruktúra erőforrás-menedzsment

Megakadályozza az erőforrás-kimerülési támadásokat, és biztosítja az erőforrások méltányos elosztását kvóták és megfigyelés révén.

 #4.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a GPU/TPU kihasználtságát figyelik-e, riasztások váltanak-e ki a szervezeti szinten meghatározott küszöbértékeknél, és automatikus skálázás vagy terheléselosztás történik-e a kapacitáskezelési irányelvek alapján.
 #4.7.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az AI munkaterhelés mérőszámai (inferencia késleltetés, áteresztőképesség, hibaarányok) a szervezeti megfigyelési követelmények szerint kerülnek-e összegyűjtésre, és összefüggésbe vannak-e hozva az infrastruktúra kihasználtságával.
 #4.7.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a Kubernetes ResourceQuotas vagy azonos funkcionalitású megoldások korlátozzák-e az egyes munkaterheléseket a szervezeti erőforrás-elosztási irányelvek szerint, kitartó (hard) korlátok érvényesítésével.
 #4.7.4    Level: 2    Role: V
 Ellenőrizze, hogy a költségfigyelés nyomon követi-e a kiadásokat munkaterhelésenként/bérlőnként, figyelmeztetésekkel az szervezeti költségvetési küszöbök alapján és automatikus ellenőrzésekkel a költségvetés túllépése esetén.
 #4.7.5    Level: 3    Role: V
 Ellenőrizze, hogy a kapacitástervezés szervezeti szinten meghatározott előrejelzési időszakokkal és a keresletminták alapján automatizált erőforrás-ellátással történik-e, történelmi adatok felhasználásával.
 #4.7.6    Level: 2    Role: D/V
 Ellenőrizze, hogy az erőforrás-kimerülés kiváltja-e a kapcsolóvédelmeket a szervezeti válasz követelményeinek megfelelően, ideértve a kapacitáspolitikákon alapuló sebességkorlátozást és a munkaterhelés elkülönítését.

---

### C4.8 Környezetelkülönítés és előmeneteli szabályozások

Szigorú környezeti határokat érvényesítsen automatizált előléptetési kapukkal és biztonsági ellenőrzésekkel.

 #4.8.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a fejlesztői, teszt- és termelési környezetek külön VPC-kben/VNet-ekben futnak-e, megosztott IAM szerepkörök, biztonsági csoportok vagy hálózati kapcsolatok nélkül.
 #4.8.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a környezeti előléptetéshez az szervezet által meghatározott, jogosult személyek jóváhagyása szükséges-e kriptográfiai aláírásokkal és megváltoztathatatlan audit nyomvonalakkal.
 #4.8.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a termelési környezetek blokkolják-e az SSH-hozzáférést, letiltják-e a hibakeresési végpontokat, és előírják-e a változtatási kérelmeket szervezeti előzetes értesítési követelményekkel, kivéve a vészhelyzeteket.
 #4.8.4    Level: 2    Role: D/V
 Ellenőrizze, hogy az infrastruktúra-kódként történő változtatások átesnek-e társ általi felülvizsgálaton automatikus teszteléssel és biztonsági vizsgálattal a fő ágba történő egyesítés előtt.
 #4.8.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a nem termelési adatok anonimizálva vannak-e a szervezeti adatvédelmi követelmények szerint, szintetikus adatgenerálással vagy teljes adatmaszkolással, valamint a személyes azonosító információk (PII) eltávolításának igazolásával.
 #4.8.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a promóciós kapuk tartalmazzák-e az automatizált biztonsági teszteket (SAST, DAST, konténeres szkennelés), amelyeknél a jóváhagyáshoz nulla KRITIKUS hibát kell találnia.

---

### C4.9 Infrastruktúra Biztonsági Mentése és Helyreállítása

Biztosítsa az infrastruktúra ellenálló képességét automatizált biztonsági mentésekkel, tesztelt helyreállítási eljárásokkal és katasztrófa utáni helyreállítási képességekkel.

 #4.9.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az infrastruktúra konfigurációk az szervezeti biztonsági mentési ütemtervek szerint le vannak-e mentve földrajzilag elkülönített régiókban a 3-2-1 biztonsági mentési stratégia alkalmazásával.
 #4.9.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a biztonsági mentési rendszerek elszigetelt hálózatokban működnek-e, külön hitelesítő adatokkal és levegőrekeszes tárolóval a zsarolóvírus elleni védelem érdekében.
 #4.9.3    Level: 2    Role: V
 Ellenőrizze, hogy a helyreállítási eljárásokat automatizált teszteléssel tesztelik és érvényesítik a szervezeti ütemtervek szerint, az RTO és RPO célokkal összhangban, amelyek megfelelnek a szervezeti követelményeknek.
 #4.9.4    Level: 3    Role: V
 Ellenőrizze, hogy a katasztrófa utáni helyreállítás tartalmaz-e AI-specifikus működési utasításokat, beleértve a modell súlyainak visszaállítását, a GPU klaszter újjáépítését és a szolgáltatásfüggőségek feltérképezését.

---

### C4.10 Infrastruktúra megfelelőség és irányítás

Fenntartsa a szabályozási megfelelést folyamatos értékelés, dokumentálás és automatizált ellenőrzések révén.

 #4.10.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az infrastruktúra megfelelőségét az szervezeti ütemtervek szerint értékelik-e SOC 2, ISO 27001 vagy FedRAMP irányelvek alapján automatikus bizonyítékgyűjtéssel.
 #4.10.2    Level: 2    Role: V
 Ellenőrizze, hogy az infrastruktúra dokumentációja tartalmaz-e hálózati diagramokat, adatfolyam térképeket és fenyegetésmodelleket, amelyek az szervezeti változáskezelési követelmények szerint frissítettek.
 #4.10.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az infrastrukturális változtatások automatizált megfelelőségi hatáselemzésen mennek keresztül, magas kockázatú módosítások esetén pedig szabályozói jóváhagyási munkafolyamatokkal.

---

### C4.11 Mesterséges Intelligencia Hardverbiztonság

Biztonságos AI-specifikus hardverkomponensek, beleértve a GPU-kat, TPU-kat és speciális AI-gyorsítókat.

 #4.11.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az AI gyorsító firmware-je (GPU BIOS, TPU firmware) kriptográfiai aláírásokkal van-e hitelesítve, és a szervezeti frissítéskezelési idővonalaknak megfelelően frissítik-e.
 #4.11.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a munkaterhelés végrehajtása előtt az MI gyorsító integritása hardveres igazolással validálva van-e TPM 2.0, Intel TXT vagy AMD SVM használatával.
 #4.11.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a GPU memória elkülönített a munkaterhelések között SR-IOV, MIG (többszörös példány GPU) vagy egyenértékű hardverpartícionálás használatával, ahol a memóriát tisztítják a feladatok között.
 #4.11.4    Level: 3    Role: V
 Ellenőrizze, hogy az AI hardver ellátási lánc tartalmazza-e az eredetet igazoló gyártói tanúsítványokat és a sérülésbiztos csomagolás érvényesítését.
 #4.11.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a hardverbiztonsági modulok (HSM-ek) FIPS 140-2 Level 3 vagy Common Criteria EAL4+ tanúsítvánnyal védik-e a mesterséges intelligencia modell súlyait és a kriptográfiai kulcsokat.

---

### C4.12 Perifériás és elosztott MI infrastruktúra

Biztonságos elosztott mesterséges intelligencia telepítések, beleértve az edge computingot, a federált tanulást és a többhelyszínes architektúrákat.

 #4.12.1    Level: 2    Role: D/V
 Ellenőrizze, hogy az edge AI eszközök kölcsönös TLS segítségével hitelesítik-e magukat a központi infrastruktúrához, az eszköztanúsítványokat pedig az szervezeti tanúsítványkezelési irányelv szerint forgatják.
 #4.12.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az élő eszközök biztonságos indítást valósítanak meg ellenőrzött aláírásokkal és visszafordítás elleni védelemmel, megakadályozva ezzel a firmware visszaminősítési támadásokat.
 #4.12.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az elosztott MI koordináció bizánci hibatűrő konszenzus algoritmusokat alkalmaz-e résztvevő-ellenőrzéssel és rosszindulatú csomópontok felismerésével.
 #4.12.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az élőhálózati és felhő közötti kommunikáció tartalmazza-e a sávszélesség korlátozását, adat tömörítést, valamint az offline működési képességeket biztonságos helyi tárolással.

---

### C4.13 Többfelhős és hibrid infrastruktúra biztonsága

Biztonságos mesterséges intelligencia munkafolyamatok több felhőszolgáltatónál és hibrid felhő-helyszíni telepítéseknél.

 #4.13.1    Level: 2    Role: D/V
 Ellenőrizze, hogy a többfelhős MI-telepítések felhőfüggetlen azonosítási szövetséget (OIDC, SAML) használnak-e, központosított házirendkezeléssel a szolgáltatók között.
 #4.13.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a felhők közötti adatátvitel végpontok közötti titkosítást használ-e az ügyfél által kezelt kulcsokkal, és hogy az adathelyzet-szabályozások az adott joghatóság szerint érvényesülnek-e.
 #4.13.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a hibrid felhőalapú MI munkaterhelések következetes biztonsági szabályzatokat valósítanak-e meg a helyszíni és felhőalapú környezetek között, egységes monitorozással és riasztással.
 #4.13.4    Level: 3    Role: V
 Ellenőrizze, hogy a felhőszolgáltató zárolásának megelőzése magában foglalja-e a hordozható infrastruktúra-kódot, a szabványosított API-kat és az adat-exportálási képességeket formátumátalakító eszközökkel.
 #4.13.5    Level: 3    Role: V
 Ellenőrizze, hogy a többfelhős költségoptimalizáció tartalmazza-e az erőforrások szétszóródását megakadályozó biztonsági vezérlőket, valamint az illetéktelen felhők közötti adatforgalmi díjak megelőzését.

---

### C4.14 Infrastruktúra automatizálás és GitOps biztonság

Biztonságos infrastruktúra automatizálási folyamatok és GitOps munkafolyamatok az MI infrastruktúra kezeléséhez.

 #4.14.1    Level: 2    Role: D/V
 Ellenőrizze, hogy a GitOps tárolók megkövetelik-e az aláírt commitokat GPG kulcsokkal, valamint ággal védelmi szabályokat alkalmaznak, amelyek megakadályozzák a közvetlen pushokat a fő ágakra.
 #4.14.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az infrastruktúra-automatizálás tartalmaz-e eltérésészlelést automatikus javítással és visszagörgetési képességekkel, amelyek a szervezeti válaszkövetelményeknek megfelelően aktiválódnak jogosulatlan változtatások esetén.
 #4.14.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az automatizált infrastruktúra-kiépítés tartalmazza-e a biztonsági házirend érvényesítését, és blokkolja-e a telepítést a nem megfelelő konfigurációk esetén.
 #4.14.4    Level: 2    Role: D/V
 Ellenőrizze, hogy az infrastruktúra-automatizálási titkokat külső titkászkezelő rendszereken (External Secrets Operator, Bank-Vaults) keresztül kezelik-e automatikus forgatással.
 #4.14.5    Level: 3    Role: V
 Ellenőrizze, hogy az önjavító infrastruktúra tartalmazza-e a biztonsági események korrelációját automatizált incidenskezeléssel és az érintettek értesítési munkafolyamataival.

---

### C4.15 Kvantumrezisztens infrastruktúra biztonság

Készítse elő a mesterséges intelligencia infrastruktúráját a kvantumszámítási fenyegetésekre poszt-kvantum kriptográfia és kvantumbiztos protokollok alkalmazásával.

 #4.15.1    Level: 3    Role: D/V
 Ellenőrizze, hogy az MI infrastruktúra a NIST által jóváhagyott poszt-kvantum kriptográfiai algoritmusokat (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) alkalmazza a kulcscsere és digitális aláírások terén.
 #4.15.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a kvantumkulcs-elosztó (QKD) rendszerek megvalósításra kerülnek-e magas biztonságú AI kommunikációkhoz kvantumbiztos kulcskezelési protokollokkal.
 #4.15.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a kriptográfiai agilitási keretrendszerek lehetővé teszik-e az új poszt-kvantum algoritmusokra való gyors áttérést automatizált tanúsítvány- és kulcscserével.
 #4.15.4    Level: 3    Role: V
 Ellenőrizze, hogy a kvantum fenyegetésmodellezés értékeli-e az AI infrastruktúra kvantumtámadásokkal szembeni sérülékenységét dokumentált migrációs ütemtervekkel és kockázatértékelésekkel.
 #4.15.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a hibrid klasszikus-quantum kriptográfiai rendszerek biztosítanak-e védelmet több rétegben a kvantumos átmeneti időszak alatt, teljesítményfigyeléssel együtt.

---

### C4.16 Bizalmas számítás és biztonságos zónák

Védd meg a mesterséges intelligencia munkaterheléseit és a modell súlyait hardveralapú megbízható végrehajtási környezetek és titkos számítási technológiák segítségével.

 #4.16.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a bizalmas AI modellek az Intel SGX környezetben, az AMD SEV-SNP-ben vagy az ARM TrustZone-ban futnak-e titkosított memóriával és hitelesítés-ellenőrzéssel.
 #4.16.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a bizalmas tárolók (Kata Containers, gVisor bizalmas számítással) elkülönítik-e az AI munkafolyamatokat hardveresen érvényesített memória titkosítással.
 #4.16.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a távoli igazolás érvényesíti-e az enclave integritását az AI modellek betöltése előtt, kriptográfiai bizonyítékkal az végrehajtási környezet hitelességéről.
 #4.16.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a bizalmas AI-inferenciaszolgáltatások megakadályozzák-e a modellkivonást titkosított számításon keresztül zárt modell-súlyokkal és védett végrehajtással.
 #4.16.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a megbízható végrehajtási környezet (Trusted Execution Environment) koordinációja kezeli-e a biztonságos zóna (secure enclave) életciklusát távoli igazolással (remote attestation) és titkosított kommunikációs csatornákkal.
 #4.16.6    Level: 3    Role: D/V
 Ellenőrizze, hogy a biztonságos többoldalú számítás (SMPC) lehetővé teszi-e az együttműködő mesterséges intelligencia képzést anélkül, hogy kockáztatná az egyéni adatkészletek vagy modellparaméterek felfedését.

---

### C4.17 Nulla Tudású Infrastruktúra

Valósítson meg nulla-tudás bizonyítási rendszereket az adatvédelmi szempontból biztonságos mesterséges intelligencia ellenőrzéséhez és hitelesítéséhez, anélkül, hogy érzékeny információkat fedne fel.

 #4.17.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a nulla tudású igazolások (ZK-SNARK-ok, ZK-STARK-ok) igazolják-e a mesterséges intelligencia modell integritását és a képzési eredetet anélkül, hogy felfednék a modell súlyait vagy a képzési adatokat.
 #4.17.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a ZK-alapú hitelesítési rendszerek lehetővé teszik-e a felhasználók adatvédelmi szempontból biztonságos ellenőrzését az AI szolgáltatásokhoz anélkül, hogy felfednék a személyazonossággal kapcsolatos információkat.
 #4.17.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a privát halmazmetszet (PSI) protokollok lehetővé teszik-e a biztonságos adat-egyeztetést a federált mesterséges intelligencia számára anélkül, hogy egyéni adattáblákat tennének láthatóvá.
 #4.17.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a zéró-tudású gépi tanulási (ZKML) rendszerek lehetővé teszik-e az ellenőrizhető MI következtetéseket kriptográfiai bizonyítékkal a helyes számításról.
 #4.17.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a ZK-rollupok biztosítanak-e skálázható, adatvédelmet megőrző AI tranzakciófeldolgozást kötegelt hitelesítéssel és csökkentett számítási terheléssel.

---

### C4.18 Oldalcsatorna-támadás megelőzése

Védje az MI infrastruktúrát az időzítésen, áramfogyasztáson, elektromágneses és gyorsítótár alapú oldalsó csatornás támadásoktól, amelyek érzékeny információkat szivárogtathatnak ki.

 #4.18.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a mesterséges intelligencia következtetési ideje állandó időalgoritmusokkal és kitöltéssel normalizált-e az időalapú modellkinyerési támadások megelőzése érdekében.
 #4.18.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a teljesítményelemzéssel szembeni védelem tartalmazza-e a zajinjektálást, a tápkábel szűrését és a véletlenszerű végrehajtási mintákat az AI hardver esetében.
 #4.18.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a cache-alapú mellékcsatornás támadások elleni védelem cache-particionálást, randomizálást és flush utasításokat használ-e az információszivárgás megelőzése érdekében.
 #4.18.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az elektromágneses kisugárzás elleni védelem tartalmazza-e a árnyékolást, jel szűrést és véletlenszerűsített feldolgozást a TEMPEST-stílusú támadások megelőzésére.
 #4.18.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a mikroarchitektúrára épülő oldalcsatorna elleni védelem tartalmazza-e a spekulatív végrehajtás szabályozását és a memóriahozzáférési minták eltakarását.

---

### C4.19 Neuromorfikus és Speciális MI Hardverbiztonság

Biztosítani az újonnan kifejlődő mesterséges intelligencia hardverarchitektúrák, beleértve a neuromorfikus chipeket, FPGA-kat, egyedi ASIC-eket és optikai számítástechnikai rendszereket.

 #4.19.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a neuromorfikus chip biztonsága magában foglalja-e a tüskeminta titkosítását, a szinaptikus súlyok védelmét és a hardveralapú tanulási szabály érvényesítését.
 #4.19.2    Level: 3    Role: D/V
 Ellenőrizze, hogy az FPGA-alapú MI gyorsítók bitfolyam titkosítást, hamisítás elleni mechanizmusokat, valamint hitelesített frissítésekkel történő biztonságos konfigurációbetöltést valósítanak meg.
 #4.19.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az egyedi ASIC biztonság tartalmazza-e a chipen belüli biztonsági processzorokat, a hardveres bizalmi alapot és a biztonságos kulcstárolást behatolásérzékeléssel.
 #4.19.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az optikai számítástechnikai rendszerek kvantumbiztos optikai titkosítást, biztonságos fotonikus kapcsolást és védett optikai jelfeldolgozást valósítanak-e meg.
 #4.19.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a hibrid analóg-digitális AI chipek tartalmaznak-e biztonságos analóg számítást, védett súlytárolást és hitelesített analóg-digitális átalakítást.

---

### C4.20 Adatvédelmet biztosító számítási infrastruktúra

Valósítson meg infrastruktúra-ellenőrzéseket a magánéletet védő számításokhoz, hogy megvédje az érzékeny adatokat az MI feldolgozása és elemzése során.

 #4.20.1    Level: 3    Role: D/V
 Ellenőrizze, hogy a homomorfikus titkosítási infrastruktúra lehetővé teszi-e a titkosított számításokat érzékeny mesterséges intelligencia munkaterheléseken kriptográfiai integritásellenőrzéssel és teljesítménymonitorozással.
 #4.20.2    Level: 3    Role: D/V
 Ellenőrizze, hogy a privát információlekérdezési rendszerek lehetővé teszik-e az adatbázis-lekérdezéseket a lekérdezési minták feltárása nélkül, az elérési minták kriptográfiai védelmével.
 #4.20.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a biztonságos többrésztvevős számítási protokollok lehetővé teszik-e a magánélet védelmét biztosító MI következtetések végrehajtását anélkül, hogy felfednék az egyes bemeneteket vagy a közbenső számításokat.
 #4.20.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a személyes adatok védelmét biztosító kulcskezelés magában foglalja-e az elosztott kulcsgenerálást, a küszöbkriptográfiát és a biztonságos kulcscserét hardveres védettséggel.
 #4.20.5    Level: 3    Role: D/V
 Bizonyítsa be, hogy az adatvédelmi szempontból biztonságos számítási teljesítmény optimalizálva van csoportosítás, gyorsítótárazás és hardveres gyorsítás révén, miközben megmaradnak a kriptográfiai biztonsági garanciák.

---

### C4.15 Ügynök Keretrendszer Felhőintegráció Biztonság és Hibrid Kivitelezés

Biztonsági vezérlők felhőintegrált ügynök keretrendszerek számára hibrid helyszíni/ felhő architektúrákkal.

 #4.15.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a felhőtároló integráció végpontok közötti titkosítást alkalmaz-e, amelyet az ügynök által vezérelt kulcskezelés biztosít.
 #4.15.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a hibrid telepítési biztonsági határok világosan definiáltak-e titkosított kommunikációs csatornákkal.
 #4.15.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a felhő erőforrás-hozzáférés tartalmaz-e nullatűrés alapú ellenőrzést folyamatos hitelesítéssel.
 #4.15.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az adattartózkodási követelmények teljesülnek-e a tárolási helyek kriptográfiai igazolásával.
 #4.15.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a felhőszolgáltató biztonsági értékelései tartalmazzák-e az ügynökspecifikus fenyegetésmodellezést és kockázatértékelést.

---

### Hivatkozások

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## C5 Hozzáférés-vezérlés és azonosítás az MI komponensek és felhasználók számára

### Irányítási célkitűzés

Az AI rendszerek hatékony hozzáférés-ellenőrzése robusztus identitáskezelést, kontextusérzékeny engedélyezést és a nulla megbízáson alapuló elvek szerinti futásidejű végrehajtást igényel. Ezek az ellenőrzések biztosítják, hogy emberek, szolgáltatások és autonóm ügynökök csak az explicit módon megadott hatókörökön belül lévő modellekkel, adatokkal és számítási erőforrásokkal lépjenek kapcsolatba, folyamatos ellenőrzés és auditálási képességek mellett.

---

### C5.1 Identitáskezelés és hitelesítés

Állítsanak fel kriptográfiailag alátámasztott identitásokat minden entitás számára, többtényezős hitelesítéssel a jogosultságot igénylő műveletekhez.

 #5.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden emberi felhasználó és szolgáltatási főnév egy központosított vállalati identitásszolgáltatón (IdP) keresztül hitelesítse magát OIDC/SAML protokollok használatával, egyedi azonosító-token leképezésekkel (nincs megosztott fiók vagy hitelesítő adat).
 #5.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a magas kockázatú műveletek (modell telepítése, súlyok exportálása, képzési adatok elérése, éles konfigurációs változtatások) többtényezős hitelesítést vagy lépcsőzetes hitelesítést igényelnek-e munkamenet újbóli érvényesítésével.
 #5.1.3    Level: 2    Role: D
 Ellenőrizze, hogy az új vezetők átesnek-e az NIST 800-63-3 IAL-2 vagy azzal egyenértékű szabványoknak megfelelő személyazonosság-igazoláson, mielőtt hozzáférést kapnának az éles rendszerhez.
 #5.1.4    Level: 2    Role: V
 Ellenőrizze, hogy az hozzáférés-áttekintések negyedévente megtörténnek-e, automatikus inaktív fiókok felismeréssel, hitelesítő adatok cseréjének érvényesítésével és eltávolítási munkafolyamatokkal.
 #5.1.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a federált MI-ügynökök aláírt JWT-igazolásokon keresztül hitelesítik magukat, amelyek maximális élettartama 24 óra, és tartalmazzák az eredet kriptográfiai bizonyítékát.

---

### C5.2 Erőforrás-engedélyezés és legkisebb jogosultság

Valósítson meg részletes hozzáférés-vezérlést minden MI-erőforrás esetében kifejezett engedélyezési modellekkel és auditnaplókkal.

 #5.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden MI-erőforrás (adatkészletek, modellek, végpontok, vektorgyűjtemények, beágyazási indexek, számítási példányok) szerepalapú hozzáférés-ellenőrzést alkalmaz-e explicit engedélyezőlistákkal és alapértelmezett megtagadási szabályokkal.
 #5.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a legkisebb jogosultság elvei alapértelmezés szerint érvényesülnek-e a szolgáltatásfiókok esetében, kezdve az olvasási jogosultságokkal, és írják elő dokumentált üzleti indoklást az írási hozzáféréshez.
 #5.2.3    Level: 1    Role: V
 Ellenőrizze, hogy minden hozzáférés-vezérlési módosítás jóváhagyott változáskérelmekhez van-e kapcsolva, és változtathatatlanul naplózva van-e időbélyeggel, végrehajtó azonosítókkal, erőforrás-azonosítókkal és jogosultságváltozásokkal.
 #5.2.4    Level: 2    Role: D
 Ellenőrizze, hogy az adatosztályozási címkék (PII, PHI, export-ellenőrzött, tulajdonosi) automatikusan átterjednek-e a leszármaztatott erőforrásokra (beágyazások, prompt gyorsítótárak, modellkimenetek) következetes szabályzatvégrehajtással.
 #5.2.5    Level: 2    Role: D/V
 Ellenőrizze, hogy az illetéktelen hozzáférési kísérletek és jogosultság-kibővítési események valós idejű riasztásokat váltanak-e ki kontextuális metaadatokkal együtt az SIEM rendszerek felé 5 percen belül.

---

### C5.3 Dinamikus szabályzatértékelés

Telepítsen attribútumalapú hozzáférés-szabályozó (ABAC) motorokat kontextusfüggő jogosultságkezelési döntésekhez auditálási képességekkel.

 #5.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az engedélyezési döntések külső, dedikált szabályzatmotorhoz (OPA, Cedar vagy egyenértékű) vannak-e delegálva, amely hitelesített API-kon keresztül érhető el, kriptográfiai integritásvédelemmel.
 #5.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a szabályzatok a dinamikus attribútumokat futásidőben értékelik-e ki, beleértve a felhasználó biztonsági szintjét, az erőforrás érzékenységi besorolását, a kérés kontextusát, a bérlői izolációt és az időbeli korlátozásokat.
 #5.3.3    Level: 2    Role: D
 Ellenőrizze, hogy a szabályzatdefiníciók verziókezeltek, szakértői felülvizsgálaton estek át, és automatizált teszteléssel igazoltak a CI/CD folyamatokban a termelési bevezetés előtt.
 #5.3.4    Level: 2    Role: V
 Győződjön meg arról, hogy a szabályzatértékelés eredményei tartalmazzák a strukturált döntési indoklásokat, és továbbítódnak a SIEM rendszerekhez korrelációs elemzés és megfelelőségi jelentések céljából.
 #5.3.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a szabályzat gyorsítótárazási élettartamának (TTL) értékei ne haladják meg az 5 percet magas érzékenységű erőforrások esetében, illetve az 1 órát az érvénytelenítésre képes szabványos erőforrásoknál.

---

### C5.4 Lekérdezés idejű biztonsági érvényesítés

Valósítsa meg az adatbázis-réteg biztonsági vezérlőit kötelező szűréssel és sor-szintű biztonsági szabályzatokkal.

 #5.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden vektoradatbázis- és SQL-lekérdezés tartalmazza-e a kötelező biztonsági szűrőket (bérlőazonosító, érzékenységi címkék, felhasználói jogosultság), amelyeket az adatbázis-kezelő motor szintjén érvényesítenek, nem az alkalmazáskódban.
 #5.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az egy sor szintű biztonsági (RLS) szabályzatok és a mező szintű maszkolás be vannak-e kapcsolva, valamint hogy a szabályzati öröklődés érvényesül-e az összes vektoralapú adatbázis, keresési index és képzési adatállomány esetében.
 #5.4.3    Level: 2    Role: D
 Ellenőrizze, hogy a sikertelen jogosultság-ellenőrzések megakadályozzák-e a "confused deputy támadásokat" azáltal, hogy azonnal megszakítják a lekérdezéseket, és explicit jogosultsági hibakódokat adnak vissza az üres eredményhalmazok visszaadása helyett.
 #5.4.4    Level: 2    Role: V
 Ellenőrizze, hogy a házirend értékelési késleltetése folyamatosan monitorozva van-e, és hogy vannak-e automatizált riasztások az időtúllépési helyzetekre, amelyek engedélyezési megkerülést eredményezhetnek.
 #5.4.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a lekérdezés újrapróbálási mechanizmusai újraértékelik-e az engedélyezési irányelveket a dinamikus jogosultságváltozások figyelembevételével az aktív felhasználói munkamenetek során.

---

### C5.5 Kimeneti szűrés és adatvesztés megelőzése

Alkalmazzon utófeldolgozási ellenőrzéseket az AI által generált tartalmak jogosulatlan adatkiszivárgásának megakadályozására.

 #5.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a levezénylés utáni szűrőmechanizmusok átvizsgálják-e és kitakarítják-e az illetéktelenül kezelt személyes azonosító információkat (PII), a titkosított adatokat és a szellemi tulajdont tartalmazó adatokat, mielőtt azokat a kérelmezőknek továbbítanák.
 #5.5.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a modell kimeneteiben szereplő idézetek, hivatkozások és forrásmegjelölések megfelelnek-e a hívó jogosultságainak, és távolítsa el azokat, ha jogosulatlan hozzáférést észlel.
 #5.5.3    Level: 2    Role: D
 Ellenőrizze, hogy az output formátum korlátozásai (tisztított PDF-ek, metaadatoktól mentesített képek, jóváhagyott fájltípusok) érvényesítésre kerülnek-e a felhasználói jogosultsági szintek és az adat-osztályozások alapján.
 #5.5.4    Level: 2    Role: V
 Ellenőrizze, hogy a redakciós algoritmusok determinisztikusak, verziókövetettek legyenek, és audit naplókat vezessenek a megfelelőségi vizsgálatok és a forenzikus elemzés támogatására.
 #5.5.5    Level: 3    Role: V
 Ellenőrizze, hogy a magas kockázatú eltávolítási események adaptív naplókat generálnak-e, amelyek tartalmazzák az eredeti tartalom kriptográfiai kivonatait a forenzikus visszakereséshez anélkül, hogy adatokat tennének ki.

---

### C5.6 Többbérlős elszigetelés

Biztosítsa a kriptográfiai és logikai elkülönítést a bérlők között a megosztott MI infrastruktúrában.

 #5.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a memóriahelyek, beágyazott tárolók, gyorsítótár-bejegyzések és ideiglenes fájlok az egyes bérlők szerint nevetér alapján elkülönítve vannak-e, és biztosított-e a biztonságos törlés a bérlő törlése vagy a munkamenet megszakítása esetén.
 #5.6.2    Level: 1    Role: D/V
 Győződjön meg arról, hogy minden API-kérés tartalmaz egy hitelesített bérlőazonosítót, amely kriptográfiailag érvényesítve van a munkamenet kontextusa és a felhasználói jogosultságok alapján.
 #5.6.3    Level: 2    Role: D
 Ellenőrizze, hogy a hálózati szabályzatok alapértelmezett megtagadó (default-deny) szabályokat valósítanak-e meg a bérlők közötti kommunikációban a szolgáltatáshálókban (service mesh) és a konténer-orchesztrációs platformokon.
 #5.6.4    Level: 3    Role: D
 Ellenőrizze, hogy az titkosítási kulcsok egyediek-e bérlőnként, ügyfél által kezelt kulcs (CMK) támogatással, valamint a bérlői adat-tárolók közötti kriptográfiai izolációval.

---

### C5.7 Autonóm ügynök engedélyezése

AI-ügynökök és autonóm rendszerek vezérlési jogosultságai körülhatárolt képességtokenek és folyamatos engedélyezés révén.

 #5.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az autonóm ügynökök megkapják-e a körülhatárolt képességtokeneket, amelyek egyértelműen felsorolják az engedélyezett műveleteket, elérhető erőforrásokat, időbeli korlátokat és működési megszorításokat.
 #5.7.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a magas kockázatú képességek (fájlrendszer-hozzáférés, kódvégrehajtás, külső API hívások, pénzügyi tranzakciók) alapértelmezés szerint le vannak-e tiltva, és aktiválásukhoz kifejezett engedélyek szükségesek-e üzleti indoklással.
 #5.7.3    Level: 2    Role: D
 Ellenőrizze, hogy a képesség tokenek felhasználói munkamenetekhez kötöttek-e, tartalmaznak-e kriptográfiai integritásvédelmet, és győződjön meg arról, hogy nem tárolhatók vagy használhatók újra offline helyzetekben.
 #5.7.4    Level: 2    Role: V
 Ellenőrizze, hogy az ágens által kezdeményezett műveletek másodlagos engedélyezésen mennek keresztül az ABAC szabálymotor segítségével, teljes kontextusértékeléssel és audit naplózással.
 #5.7.5    Level: 3    Role: V
 Ellenőrizze, hogy az ügynökhiba állapotok és a kivételkezelés tartalmazzák-e a képességi hatókör információkat az eseményelemzés és a forenzikus vizsgálat támogatásához.

---

### Hivatkozások

#### Szabványok és keretrendszerek

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Megvalósítási Útmutatók

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Mesterséges Intelligencia-specifikus Biztonság

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Ellátási lánc biztonsága modellek, keretrendszerek és adatok esetében

### Ellenőrzési célkitűzés

Az AI ellátási lánc támadások kihasználják a harmadik féltől származó modelleket, keretrendszereket vagy adatállományokat hátsó ajtók, torzítások vagy kihasználható kód beágyazására. Ezek az ellenőrzések végponttól végpontig biztosítják az eredetiség nyomonkövetését, a sérülékenységek kezelését és a megfigyelést, hogy megvédjék az egész modell életciklusát.

---

### C6.1 Előre betanított modell átvilágítása és eredetellenőrzése

Értékelje és hitelesítse a harmadik fél modelljeinek eredetét, licencét és rejtett viselkedését bármilyen finomhangolás vagy telepítés előtt.

 #6.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden harmadik fél modellartifaktum tartalmaz-e egy aláírt származási nyilatkozatot, amely azonosítja a forráskód-tárhelyet és a commit hash-t.
 #6.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a modelleket automatikus eszközökkel átvizsgálták-e káros rétegek vagy hátsóajtó aktiválók szempontjából az importálás előtt.
 #6.1.3    Level: 2    Role: D
 Ellenőrizze, hogy az átviteli tanulással finomhangolt modellek átmennek-e az ellenséges értékelésen a rejtett viselkedések felismeréséhez.
 #6.1.4    Level: 2    Role: V
 Ellenőrizni kell, hogy a modelllicencek, a kivitel-ellenőrzési címkék és az adatforrás-nyilatkozatok rögzítve vannak-e egy ML-BOM bejegyzésben.
 #6.1.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a magas kockázatú modellek (nyilvánosan feltöltött súlyok, nem ellenőrzött alkotók) karanténban maradnak-e addig, amíg emberi felülvizsgálat és jóváhagyás meg nem történik.

---

### C6.2 Keretrendszer- és Könyvtárvizsgálat

Folyamatosan vizsgálja az ML keretrendszereket és könyvtárakat CVE-k és rosszindulatú kódok után, hogy a futtatási környezet biztonságos maradjon.

 #6.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a CI-pipeline-ok futtatnak-e függőségvizsgálókat az AI-keretrendszereken és a kritikus könyvtárakon.
 #6.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a kritikus sebezhetőségek (CVSS ≥ 7,0) megakadályozzák-e a promóciót a gyártási képekhez.
 #6.2.3    Level: 2    Role: D
 Ellenőrizze, hogy a statikus kódelemzés fut-e a fork-olt vagy beágyazott ML könyvtárakon.
 #6.2.4    Level: 2    Role: V
 Ellenőrizze, hogy a keretrendszer frissítési javaslatai tartalmazzák-e a nyilvános CVE adatfolyamokra hivatkozó biztonsági hatáselemzést.
 #6.2.5    Level: 3    Role: V
 Ellenőrizze, hogy a futásidejű érzékelők riasztanak-e az aláírt SBOM-tól eltérő váratlan dinamikus könyvtárbetöltések esetén.

---

### C6.3 Függőség rögzítése és ellenőrzése

Minden függőséget rögzíts változtathatatlan digesztként, és építsd újra a buildet az azonos, sértetlen artefaktumok garantálásához.

 #6.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden csomagkezelő érvényesíti-e a verziórögzítést zárolási fájlokon keresztül.
 #6.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a konténerhivatkozásokban módosíthatatlan címkék helyett módosíthatatlan lenyomatok (digestek) legyenek használva.
 #6.3.3    Level: 2    Role: D
 Ellenőrizze, hogy az ismételhető build ellenőrzések összehasonlítják-e a hash-értékeket a CI futások között az azonos kimenetek biztosítása érdekében.
 #6.3.4    Level: 2    Role: V
 Ellenőrizze, hogy az építési tanúsítványok 18 hónapig tárolódnak-e az audit nyomkövethetőséghez.
 #6.3.5    Level: 3    Role: D
 Ellenőrizze, hogy a lejárt függőségek automatikus PR-eket váltanak-e ki a rögzített verziók frissítésére vagy elágaztatására.

---

### C6.4 Megbízható Forrás Érvényesítése

Engedélyezze az artefaktumok letöltését csak kriptográfiailag ellenőrzött, szervezet által jóváhagyott forrásokból, és blokkoljon minden egyéb forrást.

 #6.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a modell súlyait, adatállományokat és tárolókat kizárólag jóváhagyott domainekről vagy belső regisztrációs helyekről töltik le.
 #6.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a Sigstore/Cosign aláírások igazolják-e a kiadó személyazonosságát, mielőtt az artefaktumokat helyileg gyorsítótárazná.
 #6.4.3    Level: 2    Role: D
 Ellenőrizze, hogy a kilépési proxyk blokkolják-e a nem hitelesített műtárgyletöltéseket a megbízható forrásokra vonatkozó szabályzat érvényesítése érdekében.
 #6.4.4    Level: 2    Role: V
 Ellenőrizze, hogy a tárház engedélyezési listáit negyedévente felülvizsgálják, üzleti indoklás igazolásával minden egyes bejegyzéshez.
 #6.4.5    Level: 3    Role: V
 Ellenőrizze, hogy a szabályzati megsértések kiváltják-e az artefaktumok elkülönítését és az egymásra épülő pipeline futások visszavonását.

---

### C6.5 Harmadik fél adatbázis-kockázatértékelése

Értékelje a külső adathalmazokat mérgezés, elfogultság és jogi megfelelés szempontjából, és figyelje őket az egész élettartamuk alatt.

 #6.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a külső adatállományokat megmérik-e mérgezés kockázatára (pl. adatujjlenyomat-készítés, kiugró értékek detektálása).
 #6.5.2    Level: 1    Role: D
 Ellenőrizze, hogy az elfogultsági mutatók (demográfiai egyenlőség, egyenlő esélyek) kiszámítása megtörténik-e az adatkészlet jóváhagyása előtt.
 #6.5.3    Level: 2    Role: V
 Ellenőrizze, hogy az adatállományok eredete és licencfeltételei rögzítve vannak-e az ML-BOM bejegyzésekben.
 #6.5.4    Level: 2    Role: V
 Ellenőrizze, hogy a rendszeres monitorozás észleli-e az eltolódást vagy a sérülést a hosztolt adatállományokban.
 #6.5.5    Level: 3    Role: D
 Ellenőrizze, hogy a tiltott tartalom (szerzői jog, személyes adatok) automatikus tisztítással eltávolításra került-e a képzés előtt.

---

### C6.6 Ellátási lánc támadásfigyelés

A beszállítói lánc fenyegetéseinek korai észlelése CVE-hírcsatornák, audit-napló elemzések és piros csapat szimulációk segítségével.

 #6.6.1    Level: 1    Role: V
 Ellenőrizze, hogy a CI/CD auditnaplók folyamatosan továbbítódnak-e a SIEM rendszerbe a rendellenes csomagletöltések vagy manipulált build lépések észlelésére.
 #6.6.2    Level: 2    Role: D
 Ellenőrizze, hogy az incidenskezelési játékkönyvek tartalmazzák-e a visszagörgetési eljárásokat a sérült modellek vagy könyvtárak esetére.
 #6.6.3    Level: 3    Role: V
 Ellenőrizze, hogy a fenyegetés‑intelligencia gazdagító eszközök az ML‑specifikus indikátorokat (pl. modell‑mérgezési IoC-ket) címkézik‑e a riasztások szűrése során.

---

### C6.7 ML‑BOM a modell artefaktumokhoz

Részletes, gépi tanulásra specifikus SBOM-okat (ML-BOM-okat) generáljon és írjon alá, hogy a későbbi felhasználók a telepítéskor ellenőrizhessék a komponensek integritását.

 #6.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden modell-artifaktum közzétesz-e egy ML-BOM-ot, amely felsorolja az adatállományokat, súlyokat, hiperparamétereket és licenceket.
 #6.7.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az ML-BOM generálása és a Cosign aláírás automatizált-e a CI-ben, és kötelező-e az egyesítéshez.
 #6.7.3    Level: 2    Role: D
 Ellenőrizze, hogy az ML‑BOM teljességi ellenőrzések sikertelenül leállítják-e a buildet, ha bármely komponens metaadata (hash, licenc) hiányzik.
 #6.7.4    Level: 2    Role: V
 Ellenőrizze, hogy a végfelhasználók képesek-e az ML-BOM-ok lekérdezésére API-n keresztül az importált modellek telepítési időbeni érvényesítéséhez.
 #6.7.5    Level: 3    Role: V
 Ellenőrizze, hogy az ML‑BOM-ok verziókövetettek és különbségvizsgálattal vannak ellenőrizve az engedély nélküli módosítások észlelésére.

---

### Hivatkozások

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## C7 Modell Viselkedés, Kimenetvezérlés és Biztonsági Garancia

### Ellenőrzési célkitűzés

A modell kimeneteinek strukturáltnak, megbízhatónak, biztonságosnak, magyarázhatónak kell lenniük, és folyamatosan monitorozni kell őket a termelési környezetben. Ennek eredményeként csökkennek a téves eredmények, az adatvédelmi szivárgások, a káros tartalmak és a kontrollálatlan műveletek, miközben nő a felhasználói bizalom és a szabályozói megfelelőség.

---

### C7.1 Kimeneti formátum érvényesítése

A szigorú sémák, korlátozott dekódolás és az utólagos ellenőrzés megakadályozzák a hibás vagy káros tartalom terjedését.

 #7.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a válasz sémái (pl. JSON Schema) meg vannak-e adva a rendszerüzenetben, és minden kimenet automatikusan érvényesítve van; a nem megfelelő kimenetek javítást vagy elutasítást váltanak ki.
 #7.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az korlátozott dekódolás (stop tokenek, reguláris kifejezések, maximális tokenek) engedélyezve van-e az túlcsordulás vagy prompt-injekciós mellékcsatornák megelőzése érdekében.
 #7.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a leszakadó komponensek kezelik-e a kimeneteket megbízhatatlanként, és érvényesítsék azokat sémák vagy injekcióbiztos de-serializálók ellen.
 #7.1.4    Level: 3    Role: V
 Ellenőrizze, hogy a helytelen kimeneti események naplózásra kerülnek, korlátozva vannak és megjelennek a monitorozásban.

---

### C7.2 Hallucináció felismerése és csökkentése

A bizonytalanságbecslés és a tartalék stratégiák visszaszorítják a kitalált válaszokat.

 #7.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a token szintű log-valószínűségek, az együttes önkonzisztencia vagy a finomhangolt hamis információ detektorok minden válaszhoz hozzárendelnek-e egy bizalmi pontszámot.
 #7.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a konfigurálható bizalmi küszöbérték alatti válaszok kiváltanak-e visszaesési munkafolyamatokat (például lekérdezéssel bővített generálás, másodlagos modell vagy emberi felülvizsgálat).
 #7.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a hallucinációs esetek gyökérok-metaadatokkal vannak-e címkézve, és be vannak-e táplálva a posztmortem és finomhangolási folyamatokba.
 #7.2.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a küszöbértékek és az érzékelők újrakalibrálása megtörténik-e a jelentős modell- vagy tudásbázis-frissítések után.
 #7.2.5    Level: 3    Role: V
 Ellenőrizze, hogy az irányítópult vizualizációi követik-e a tévesztési arányokat.

---

### C7.3 Kimenetbiztonság és Adatvédelmi Szűrés

A szabályzati szűrők és a red team lefedettség védelmet nyújtanak a felhasználók és a bizalmas adatok számára.

 #7.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a generáció előtti és utáni osztályozók blokkolják-e a gyűlöletkeltő, zaklató, öngyilkosságra ösztönző, szélsőséges és a szabályzatnak megfelelően szexuálisan explicit tartalmakat.
 #7.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a személyes azonosító információk (PII)/fizetési kártyaadatok (PCI) felismerése és automatikus elhomályosítása minden válaszon fut-e; a szabályszegések adatvédelmi eseményt váltanak ki.
 #7.3.3    Level: 2    Role: D
 Ellenőrizze, hogy a titoktartási címkék (például üzleti titkok) átöröklődnek-e a modalitások között, hogy megakadályozzák az adatszivárgást szöveg, képek vagy kód esetén.
 #7.3.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a szűrő megkerülési kísérletek vagy a magas kockázatú osztályozások másodlagos jóváhagyást vagy a felhasználó újbóli hitelesítését igénylik-e.
 #7.3.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a szűrési küszöbértékek megfelelnek-e a joghatóságoknak, valamint a felhasználó korának/szerepének kontextusában.

---

### C7.4 Kimenet- és műveletkorlátozás

A sebességkorlátozások és jóváhagyási kapuk megakadályozzák a visszaéléseket és a túlzott önállóságot.

 #7.4.1    Level: 1    Role: D
 Ellenőrizze, hogy a felhasználónként és API-kulcsonként meghatározott kvóták korlátozzák-e a kéréseket, tokeneket és költségeket, valamint alkalmazzák-e az exponenciális visszaállást 429-es hibák esetén.
 #7.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a kiváltságos műveletek (fájlírás, kódvégrehajtás, hálózati hívások) csak szabályalapú jóváhagyással vagy emberi beavatkozással legyenek engedélyezve.
 #7.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kereszt-módusú következetességi ellenőrzések biztosítják-e, hogy ugyanahhoz a kéréshez generált képek, kódok és szövegek ne használhatók rosszindulatú tartalom csempészésére.
 #7.4.4    Level: 2    Role: D
 Ellenőrizze, hogy az ügynök-delegálási mélység, a rekurziós korlátok és az engedélyezett eszközlisták egyértelműen konfigurálva vannak-e.
 #7.4.5    Level: 3    Role: V
 Ellenőrizze, hogy a korlátok megsértése strukturált biztonsági eseményeket generál-e SIEM bevitelhez.

---

### C7.5 Kimenet Magyarázhatósága

Az átlátszó jelek javítják a felhasználói bizalmat és a belső hibakeresést.

 #7.5.1    Level: 2    Role: D/V
 Ellenőrizze, hogy a felhasználó felé irányuló bizalmi pontszámok vagy rövid indoklások összefoglalói megjelennek-e, amikor a kockázatértékelés ezt indokoltnak tartja.
 #7.5.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a generált magyarázatok nem fednek-e fel érzékeny rendszerutasításokat vagy szabadalmi oltalom alatt álló adatokat.
 #7.5.3    Level: 3    Role: D
 Ellenőrizze, hogy a rendszer rögzíti-e a token-szintű log-valószínűségeket vagy figyelmi térképeket, és tárolja-e azokat az engedélyezett ellenőrzéshez.
 #7.5.4    Level: 3    Role: V
 Győződjön meg arról, hogy a magyarázhatósági artefaktumok verziókövetettek a modellkiadásokkal együtt az ellenőrizhetőség érdekében.

---

### C7.6 Felügyeleti integráció

A valós idejű megfigyelhetőség bezárja a kört a fejlesztés és a termelés között.

 #7.6.1    Level: 1    Role: D
 Ellenőrizze, hogy a metrikák (sémasértések, hallucinációs arány, toxicitás, személyes azonosításra alkalmas adatok kiszivárgása, késleltetés, költség) továbbítódnak-e egy központi megfigyelő platformra.
 #7.6.2    Level: 1    Role: V
 Ellenőrizze, hogy minden biztonsági mérőszámra meg vannak-e határozva a riasztási küszöbértékek, valamint a készenléti fokozási útvonalak.
 #7.6.3    Level: 2    Role: V
 Ellenőrizze, hogy a műszerfalak összekapcsolják-e a kimeneti anomáliákat a modell/verzió, a funkciókapcsoló és a felülről érkező adatváltozásokkal.
 #7.6.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a megfigyelési adatok visszacsatolnak-e az újraképzésbe, finomhangolásba vagy szabályfrissítésekbe a dokumentált MLOps munkafolyamatban.
 #7.6.5    Level: 3    Role: V
 Ellenőrizze, hogy a monitorozó csővezetékeket behatolás-ellenőrzés alá vetették-e, és hogy hozzáférés-szabályozottak-e a bizalmas naplók kiszivárgásának elkerülése érdekében.

---

### 7.7 Generatív média védelmi intézkedések

Biztosítani kell, hogy az MI rendszerek ne generáljanak illegális, káros vagy jogosulatlan médiumtartalmat, a szabályzati korlátozások, kimenet-ellenőrzés és nyomonkövethetőség érvényesítésével.

 #7.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a rendszerutasítások és a felhasználói instrukciók kifejezetten tiltják-e az illegális, káros vagy nem konszenzuális deepfake médiák (például kép, videó, hang) generálását.
 #7.7.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a promptokat kiszűrték-e az utánzó kísérletek, szexuálisan explicit deepfake-ek vagy valódi személyeket engedély nélkül ábrázoló média előállítása érdekében.
 #7.7.3    Level: 2    Role: V
 Ellenőrizze, hogy a rendszer használ-e észlelési hash-elést (perceptual hashing), vízjel felismerést vagy ujjlenyomat-azonosítást a szerzői joggal védett média jogosulatlan reprodukciójának megakadályozására.
 #7.7.4    Level: 3    Role: D/V
 Ellenőrizze, hogy minden generált média kriptográfiailag alá van-e írva, vízjellel ellátva vagy manipulációálló forrásadatokkal van-e ellátva a további nyomon követhetőség érdekében.
 #7.7.5    Level: 3    Role: V
 Ellenőrizze, hogy az átjárási kísérletek (pl. utasítás elrejtése, szleng, támadó megfogalmazás) felismerésre, naplózásra és sebességkorlátozásra kerülnek-e; az ismétlődő visszaéléseket jelzik a megfigyelő rendszerek felé.

### Hivatkozások

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## C8 memória, beágyazások és vektordb biztonság

### Vezérlési célkitűzés

A beágyazások és vektortárolók a korszerű MI rendszerek „élő memóriájaként” működnek, folyamatosan fogadják a felhasználók által szolgáltatott adatokat, és visszakeresett generálás (Retrieval-Augmented Generation, RAG) révén visszajuttatják azokat a modell kontextusába. Ha ezek a memóriák nincsenek megfelelően szabályozva, személyes azonosításra alkalmas információk (PII) szivároghatnak ki, sérülhetnek a hozzájárulások, vagy visszafejthetővé válhat az eredeti szöveg. Ennek a szabályozási családnak a célja, hogy megerősítse a memóriaadat-folyamatokat és a vektoralapú adatbázisokat úgy, hogy az hozzáférés minimális jogosultságú legyen, a beágyazások adatvédő jellegűek legyenek, a tárolt vektorok lejárjanak vagy kérésre visszavonhatók legyenek, valamint hogy a felhasználónkénti memória ne szennyezze más felhasználók parancsait vagy eredményeit.

---

### C8.1 Hozzáférési szabályok a memórián és a RAG indexeken

Alkalmazzon finomított hozzáférés-vezérlést minden vektor gyűjteményen.

 #8.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a sor/névtér szintű hozzáférés-vezérlési szabályok korlátozzák-e a beszúrás, törlés és lekérdezés műveleteket bérlőnként, gyűjteményenként vagy dokumentum címke szerint.
 #8.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az API-kulcsok vagy JWT-k tartalmaznak-e körülhatárolt jogosultságokat (például gyűjteményazonosítókat, műveleti igéket), és hogy legalább negyedévente lecserélik őket.
 #8.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a jogosultságnövelési kísérletek (pl. cross-namespace hasonlósági lekérdezések) észlelve legyenek, és 5 percen belül naplózva legyenek egy SIEM rendszeren.
 #8.1.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a vektor adatbázis naplózza-e a tárgy-azonosítót, a műveletet, a vektorazonosítót/névteret, a hasonlósági küszöbértéket és az eredményszámot.
 #8.1.5    Level: 3    Role: V
 Ellenőrizze, hogy a hozzáférési döntések átjárhatósági hibák ellen való tesztelése megtörténik-e minden alkalommal, amikor a motorokat frissítik vagy az index-shardolási szabályok változnak.

---

### C8.2 Beágyazás tisztítása és érvényesítése

A személyként azonosítható információkat (PII) előzetesen szűrje, anonimizálja vagy álnevesítse a vektorizálás előtt, és opcionálisan dolgozza fel utólag az embeddingeket a maradék jelek eltávolítása érdekében.

 #8.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a személyes azonosító információk (PII) és a szabályozott adatok automatikus osztályozók által észlelhetők-e, és hogy azok beágyazás előtt maszkolva, tokenizálva vagy eldobva vannak-e.
 #8.2.2    Level: 1    Role: D
 Ellenőrizze, hogy az embedding feldolgozó folyamatok elutasítják vagy elkülönítik-e az olyan bemeneteket, amelyek futtatható kódot vagy nem UTF-8 karaktereket tartalmaznak, amelyek mérgezhetnék a indexet.
 #8.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy helyi vagy metrikus differenciálpszichológiai adatvédelmi tisztítás van-e alkalmazva azokon a mondatbeágyazásokon, amelyek távolsága bármely ismert Személyes Azonosító Információ (PII) tokenhez egy konfigurálható küszöb alatt van.
 #8.2.4    Level: 2    Role: V
 Ellenőrizze, hogy a tisztítás hatékonysága (például a személyes adatok kitakarásának visszahívása, szemantikai eltolódás) legalább félévente érvényesítve legyen referencia korpuszokkal szemben.
 #8.2.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a tisztítási konfigurációk verziókövetettek-e, és a változtatások átesnek-e a kollégák általi felülvizsgálaton.

---

### C8.3 Memória lejárat, visszavonás és törlés

A GDPR „az elfeledtetéshez való jog” és hasonló törvények időben történő törlést írnak elő; ezért a vektortáraknak támogatniuk kell az élettartam-beállításokat (TTL), a végleges törlést és a sírköves törlést, hogy a visszavont vektorokat ne lehessen helyreállítani vagy újra indexelni.

 #8.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden vektor és metaadat rekord rendelkezik-e TTL-lel vagy explicit megőrzési címkével, amelyet az automatizált tisztító feladatok betartanak.
 #8.3.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a felhasználó által indított törlési kérelmek 30 napon belül törlik-e a vektorokat, metaadatokat, gyorsítótár példányokat és származtatott indexeket.
 #8.3.3    Level: 2    Role: D
 Ellenőrizze, hogy a logikai törléseket kriptográfiai blokktörlések kövessék, ha a hardver támogatja, vagy kulcstömb kulcstöredeztetés által történjen.
 #8.3.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az lejárt vektorok kizárásra kerülnek-e a legközelebbi szomszéd keresési eredményeiből legfeljebb 500 ms-on belül a lejárat után.

---

### C8.4 Megelőzni a beágyazás inverzióját és szivárgását

A legújabb védekezések — zajszuperpozíció, projekciós hálózatok, adatvédelmi neuron zavarás és alkalmazásrétegbeli titkosítás — képesek csökkenteni a token-szintű inverziós arányokat 5% alá.

 #8.4.1    Level: 1    Role: V
 Ellenőrizze, hogy létezik-e egy formális fenyegetési modell, amely lefedi az inverziót, tagsági és attribútum-inferenciás támadásokat, és hogy azt évente áttekintik.
 #8.4.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az alkalmazásrétegű titkosítás vagy a kereshető titkosítás megvédi-e a vektorokat az infrastruktúra-adminisztrátorok vagy a felhőszolgáltató személyzete általi közvetlen olvasástól.
 #8.4.3    Level: 3    Role: V
 Ellenőrizze, hogy a védelemparaméterek (ε a DP-hez, zaj σ, projektálási rang k) biztosítják-e az adatvédelmet legalább 99%-os tokenvédettség mellett, és az hasznosság legfeljebb 3%-os pontosságveszteséget eredményez.
 #8.4.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az invertálás-állósági mérőszámok részei-e a modellfrissítések kiadási zárjainak, és hogy a regressziós költségkeretek meghatározásra kerültek-e.

---

### C8.5 Felhasználóspecifikus memória hatókörének érvényesítése

Az általa kezelt több bérlős környezetek közötti adat-szivárgás továbbra is az egyik legnagyobb RAG kockázat: a nem megfelelően szűrt hasonlósági lekérdezések egy másik ügyfél privát dokumentumait tehetik láthatóvá.

 #8.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden lekérdezési kérés a bérlő/felhasználói azonosító alapján van-e utószűrve, mielőtt átkerül az LLM parancsba.
 #8.5.2    Level: 1    Role: D
 Ellenőrizze, hogy a gyűjteménynévek vagy névterezett azonosítók felhasználónként vagy bérlőnként sózva vannak-e, hogy a vektorok ne ütközzenek tartományok között.
 #8.5.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a konfigurálható távolsági küszöbérték fölötti, de a hívó hatókörén kívüli hasonlósági eredményeket elvetik-e és biztonsági riasztásokat váltanak-e ki.
 #8.5.4    Level: 2    Role: V
 Ellenőrizze, hogy a többbérlős terheléses tesztek szimulálják-e a rosszindulatú lekérdezéseket, amelyek megpróbálják kinyerni a hatáskörön kívüli dokumentumokat, és mutassák be a nulla adatkinyerést.
 #8.5.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a titkosítási kulcsok bérlőnként külön vannak-e választva, biztosítva a kriptográfiai elkülönítést akkor is, ha a fizikai tárolás közös.

---

### C8.6 Fejlett memória rendszerbiztonság

Biztonsági vezérlők fejlett memóriaarchitektúrákhoz, beleértve az epizodikus, szemantikus és munkamemóriát, amelyek specifikus elszigetelési és érvényesítési követelményeket támasztanak.

 #8.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a különböző memóriatípusok (epizodikus, szemantikus, munkamemória) izolált biztonsági kontextusokkal rendelkeznek-e szerepalapú hozzáférés-vezérléssel, külön titkosítási kulcsokkal és dokumentált hozzáférési mintákkal mindegyik memória típusra.
 #8.6.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a memória-konszolidációs folyamatok tartalmazzák-e a biztonsági ellenőrzést a rosszindulatú emlékek befecskendezésének megelőzése érdekében, amely tartalmi tisztítást, forrásellenőrzést és integritásellenőrzést foglal magában a tárolás előtt.
 #8.6.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a memórialekérdezések érvényesítve és megtisztítva vannak-e az illetéktelen információk kivonásának megelőzése érdekében lekérdezési mintaelemzés, hozzáférés-ellenőrzés és eredményszűrés révén.
 #8.6.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a memóriafelejtési mechanizmusok biztonságosan törlik-e a érzékeny információkat kriptográfiai törlési garanciákkal, például kulcs törléssel, többszörös felülírással vagy hardveralapú biztonságos törléssel és igazolási tanúsítványokkal.
 #8.6.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a memóriarendszer integritását folyamatosan figyelik-e jogosulatlan módosítások vagy sérülések ellen ellenőrzőösszegek, auditnaplók és automatikus riasztások segítségével, amikor a memória tartalma a normál működésen kívül megváltozik.

---

### Hivatkozások

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Autonóm hangolás és ügynöki cselekvési biztonság

### Vezérlési célkitűzés

Biztosítani kell, hogy az autonóm vagy többügynökös MI-rendszerek csak az egyértelműen szándékolt, hitelesített, auditálható és korlátozott költség- és kockázati küszöbértékeken belüli műveleteket hajthassanak végre. Ez megvédi a rendszert az olyan fenyegetésekkel szemben, mint az autonóm rendszer kompromittálása, eszközhibás használata, ügynök hurkok észlelése, kommunikáció eltérítése, személyazonosság hamisítása, raj manipuláció és szándék manipuláció.

---

### 9.1 Ügynök Feladat-tervezés és Rekurziós Költségvetések

Ütemezze korlátozottan a rekurzív terveket, és kényszerítsen emberi ellenőrzőpontokat a kiváltságos műveletekhez.

 #9.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az egyes ügynök-futtatások maximális rekurziós mélysége, szélessége, falióra szerinti ideje, tokenek száma és pénzügyi költsége központilag konfigurált és verziókezelt legyen.
 #9.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a kiváltságos vagy visszafordíthatatlan műveletek (például kódcommitok, pénzügyi átutalások) végrehajtása előtt kifejezett emberi jóváhagyás szükséges legyen egy auditálható csatornán keresztül.
 #9.1.3    Level: 2    Role: D
 Ellenőrizze, hogy a valós idejű erőforrás-figyelők kiváltják-e a megszakító megszakítást, amikor bármely költségvetési küszöbérték túllépésre kerül, megállítva a további feladatbővítést.
 #9.1.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a megszakító események naplózva vannak-e az ügynökazonosítóval, kiváltó feltétellel és a rögzített tervállapottal a jogi vizsgálathoz.
 #9.1.5    Level: 3    Role: V
 Ellenőrizze, hogy a biztonsági tesztek lefedik-e a költségvetés-kimerülés és az elszabadult terv szcenáriókat, megerősítve a biztonságos leállást adatvesztés nélkül.
 #9.1.6    Level: 3    Role: D
 Ellenőrizze, hogy a költségvetési szabályzatok kódként vannak-e megfogalmazva, és a CI/CD-ben érvényesülnek-e a konfigurációs eltérés megakadályozása érdekében.

---

### 9.2 Eszköz plugin homokozózás

Izolálja az eszközinterakciókat az illetéktelen rendszerhozzáférés vagy kódvégrehajtás megelőzése érdekében.

 #9.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden eszköz/bővítmény egy operációs rendszerben, konténerben vagy WASM-szintű homokozóban fusson a legkisebb jogosultságú fájlrendszer-, hálózat- és rendszerhívás-szabályzatokkal.
 #9.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a homokozó erőforrás-kvóták (CPU, memória, lemez, hálózati kimenet) és a végrehajtási időkorlátok érvényesítve és naplózva vannak-e.
 #9.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az eszköz binárisai vagy leírói digitálisan aláírtak-e; az aláírásokat betöltés előtt érvényesítik.
 #9.2.4    Level: 2    Role: V
 Ellenőrizze, hogy a homokozó telemetria adatfolyamai a SIEM-be érkeznek-e; az anomáliák (pl. kísérletet tett kimenő kapcsolatok) riasztásokat váltanak ki.
 #9.2.5    Level: 3    Role: V
 Ellenőrizze, hogy a magas kockázatú beépülő modulok biztonsági átvilágításon és behatolás-tesztelésen esnek át a termelési bevezetés előtt.
 #9.2.6    Level: 3    Role: D/V
 Ellenőrizze, hogy a sandboxból való kitörési kísérletek automatikusan blokkolásra kerülnek-e, és a hibás bővítmény elkülönítésre kerül-e vizsgálatig.

---

### 9.3 Autonóm hurok és költségkorlátozás

Észlelje és állítsa meg az ellenőrizetlen ügynök-ügynök közötti rekurziót és a költségrobbanásokat.

 #9.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az ügynökök közötti hívások tartalmaznak-e egy ugrásszám-korlátot vagy TTL-t, amelyet a futtatókörnyezet csökkent és érvényesít.
 #9.3.2    Level: 2    Role: D
 Ellenőrizze, hogy az ügynökök egyedi meghívási gráfazonosítót tartanak fenn az önmeghívás vagy ciklikus minták észlelésére.
 #9.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a felhalmozódó számítási egység- és költési számlálók kéréslánconként követve vannak-e; ha a határérték túllépésre kerül, a lánc megszakad.
 #9.3.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális elemzés vagy a modellellenőrzés bizonyítja-e, hogy az ügynökprotokollokban nincs korlátlan rekurzió.
 #9.3.5    Level: 3    Role: D
 Ellenőrizze, hogy a ciklus-megszakítási események riasztásokat generálnak-e, és szolgáltatnak-e folyamatos fejlesztési mutatókat.

---

### 9.4 Protokollszintű visszaélés elleni védelem

Biztonságos kommunikációs csatornák az ügynökök és külső rendszerek között a eltérítés vagy manipuláció megelőzése érdekében.

 #9.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az összes ügynök-hoz eszköz és ügynök-hoz ügynök üzenet hitelesítve van-e (például kölcsönös TLS vagy JWT használatával), és végponttól végpontig titkosítva van-e.
 #9.4.2    Level: 1    Role: D
 Ellenőrizze, hogy a sémák szigorúan érvényesítve vannak-e; az ismeretlen mezőket vagy hibás üzeneteket el kell utasítani.
 #9.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az integritás-ellenőrzések (MAC-ok vagy digitális aláírások) kiterjednek-e az egész üzenetterjedelemre, beleértve az eszközparamétereket is.
 #9.4.4    Level: 2    Role: D
 Ellenőrizze, hogy az ismétlődés elleni védelem (nonce-ok vagy időbélyeg-ablakok) érvényesítve van-e a protokollrétegen.
 #9.4.5    Level: 3    Role: V
 Ellenőrizze, hogy a protokollimplementációk átesnek-e fuzzingon és statikus elemzésen injekciós vagy deszerializációs hibák keresése érdekében.

---

### 9.5 Ügynökazonosság és manipulációbiztos bizonyíték

Biztosítsa, hogy a tevékenységek hozzárendelhetők legyenek, és a módosítások észlelhetők maradjanak.

 #9.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden egyes ügynök példány egyedi kriptográfiai azonosítóval (kulcspárral vagy hardverhez kötött hitelesítő adatokkal) rendelkezik-e.
 #9.5.2    Level: 2    Role: D/V
 Ellenőrizze, hogy minden ügynöki művelet alá van-e írva és időbélyeggel van-e ellátva; a naplók tartalmazzák az aláírást a visszautasítás elkerülése érdekében.
 #9.5.3    Level: 2    Role: V
 Ellenőrizze, hogy a hamisításra utaló logok csak hozzáfűzéssel vagy egyszeri írással rendelkező közegen vannak-e tárolva.
 #9.5.4    Level: 3    Role: D
 Ellenőrizze, hogy az identitáskulcsok meghatározott ütemezés szerint és a kompromittálódás jeleire forgatódnak-e.
 #9.5.5    Level: 3    Role: D/V
 Ellenőrizze, hogy az illetéktelen hozzáférési vagy kulcskonfliktus kísérletek az érintett ügynök azonnali elkülönítését váltják-e ki.

---

### 9.6 Többügynökös rajkockázat-csökkentés

Csökkentse a kollektív viselkedési veszélyeket elkülönítéssel és formális biztonsági modellezéssel.

 #9.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a különböző biztonsági tartományokban működő ügynökök elszigetelt futtatókörnyezetekben vagy hálózati szegmensekben hajtódnak-e végre.
 #9.6.2    Level: 3    Role: V
 Ellenőrizze, hogy a rajviselkedések modellezve és formálisan ellenőrizve legyenek élhetőség és biztonság szempontjából a telepítés előtt.
 #9.6.3    Level: 3    Role: D
 Ellenőrizze, hogy a futásidejű megfigyelők észlelik-e a felmerülő veszélyes mintázatokat (például oszcillációkat, holttereket) és megkezdik-e a korrekciós intézkedéseket.

---

### 9.7 Felhasználói és Eszköz Hitelesítés / Jogosultságkezelés

Minden ágens által indított művelet esetén valósítsunk meg robusztus hozzáférés-vezérlést.

 #9.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az ügynökök elsőrendű jogosultként hitelesítik magukat a kimenő rendszerek felé, és soha nem újrahasználják a végfelhasználói hitelesítő adatokat.
 #9.7.2    Level: 2    Role: D
 Ellenőrizze, hogy a részletes jogosultsági szabályok korlátozzák-e, mely eszközöket hívhat meg egy ügynök, és milyen paramétereket adhat meg azokhoz.
 #9.7.3    Level: 2    Role: V
 Ellenőrizze, hogy a jogosultság-ellenőrzések minden híváskor újraértékelődnek-e (folyamatos jogosultság-ellenőrzés), nem csak a munkamenet indításakor.
 #9.7.4    Level: 3    Role: D
 Ellenőrizze, hogy a delegált jogosultságok automatikusan lejárnak-e, és újbóli jóváhagyást igényelnek-e időkorlát vagy jogosultsági kör változás esetén.

---

### 9.8 Ügynök-ügynök közötti kommunikáció biztonsága

Titkosítsa és biztosítsa az összes ügynökök közötti üzenet integritását, hogy megakadályozza a lehallgatást és a manipulációt.

 #9.8.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a kölcsönös hitelesítés és a tökéletes előre titoktartású titkosítás (például TLS 1.3) kötelező-e az ügynökcsatornák számára.
 #9.8.2    Level: 1    Role: D
 Ellenőrizze, hogy az üzenet integritása és eredete hitelesítve van-e a feldolgozás előtt; a sikertelen ellenőrzés riasztásokat vált ki, és az üzenetet eldobja.
 #9.8.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kommunikáció metaadatai (időbélyegek, sorrendszámok) naplózásra kerülnek-e a vizsgálati rekonstrukció támogatása érdekében.
 #9.8.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális verifikáció vagy a modellellenőrzés megerősíti-e, hogy a protokoll állapotgépei nem hajthatók veszélyes állapotokba.

---

### 9.9 Szándékellenőrzés és korlátozások érvényesítése

Ellenőrizze, hogy az ügynök műveletei összhangban vannak-e a felhasználó megadott szándékával és a rendszer korlátaival.

 #9.9.1    Level: 1    Role: D
 Ellenőrizze, hogy a végrehajtás előtti megszorításmegoldók a javasolt műveleteket a kemény kódolt biztonsági és irányelvek szabályai szerint vizsgálják-e.
 #9.9.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a nagy hatású műveletek (pénzügyi, pusztító, adatvédelmi szempontból érzékeny) egyértelmű szándékmegerősítést igényelnek-e az indító felhasználótól.
 #9.9.3    Level: 2    Role: V
 Ellenőrizze, hogy az utófeltétel-ellenőrzések igazolják, hogy a befejezett műveletek elérték a kívánt hatásokat mellékhatások nélkül; az eltérések visszagörgetést váltanak ki.
 #9.9.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális módszerek (például modell-ellenőrzés, tételbizonyítás) vagy a tulajdonság-alapú tesztek igazolják, hogy az ügynök tervek megfelelnek az összes kijelölt feltételnek.
 #9.9.5    Level: 3    Role: D
 Bizonyosodjon meg arról, hogy a szándékeltérés vagy megszorításmegsértés események folyamatos fejlesztési ciklusokat és fenyegetés-információ megosztást táplálnak.

---

### 9.10 Ügynök Érvelési Stratégia Biztonsága

Biztonságos kiválasztása és végrehajtása különböző érvelési stratégiáknak, beleértve a ReAct, a Gondolatlánc (Chain-of-Thought) és a Gondolatfák (Tree-of-Thoughts) megközelítéseket.

 #9.10.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az érvelési stratégia kiválasztása determinisztikus kritériumokon alapul-e (bemeneti összetettség, feladattípus, biztonsági kontextus), és hogy az azonos bemenetek azonos stratégia kiválasztást eredményeznek-e ugyanazon biztonsági kontextuson belül.
 #9.10.2    Level: 1    Role: D/V
 Ellenőrizze, hogy minden egyes érvelési stratégia (ReAct, Chain-of-Thought, Tree-of-Thoughts) rendelkezik-e dedikált bemeneti érvényesítéssel, kimeneti tisztítással és az adott kognitív megközelítéshez igazított végrehajtási időkorlátokkal.
 #9.10.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az érvelési stratégia átmenetek naplózva vannak-e teljes kontextussal, beleértve a bemeneti jellemzőket, a kiválasztási kritériumok értékeit és a végrehajtási metaadatokat az audit nyomvonal rekonstruálásához.
 #9.10.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a Gondolatfa-alapú következtetés tartalmaz-e ágelvágó mechanizmusokat, amelyek megszakítják a feltárást, ha szabályszegéseket, erőforrás-korlátokat vagy biztonsági határokat észlelnek.
 #9.10.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a ReAct (Reason-Act-Observe) ciklusok tartalmaznak-e érvényesítési ellenőrzőpontokat minden egyes fázisban: az érvelési lépés ellenőrzését, a cselekvés engedélyezését és a megfigyelés tisztítását, mielőtt továbblépnének.
 #9.10.6    Level: 3    Role: D/V
 Ellenőrizze, hogy az érvelési stratégia teljesítménymutatóit (végrehajtási idő, erőforrás-használat, kimeneti minőség) automatikus riasztások figyelik-e, amikor a mutatók a beállított küszöbértékeket meghaladják.
 #9.10.7    Level: 3    Role: D/V
 Ellenőrizze, hogy a több stratégiát kombináló hibrid érvelési megközelítések mindegyik alkotó stratégiájának bemeneti érvényesítését és kimeneti korlátait betartják-e, anélkül, hogy megkerülnék bármely biztonsági vezérlőt.
 #9.10.8    Level: 3    Role: D/V
 Ellenőrizze, hogy az érvelési stratégia biztonsági tesztelése magában foglalja-e a hibás bemenetekkel végzett fuzzingot, az ellenfél által tervezett kéréseket az érvelési stratégia váltására kényszerítéshez, valamint a határfeltételek tesztelését minden kognitív megközelítés esetén.

---

### 9.11 Ügynök Életciklus Állapotkezelés és Biztonság

Biztonságos ügynök inicializálás, állapotátmenetek és befejezés kriptográfiai audit nyomvonalakkal és meghatározott helyreállítási eljárásokkal.

 #9.11.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az ügynök inicializálása magában foglalja-e a kriptográfiai azonosító létrehozását hardveralapú hitelesítő adatokkal és megváltoztathatatlan indítási auditnaplókat, amelyek tartalmazzák az ügynök azonosítóját, az időbélyeget, a konfigurációs hash-t és az inicializációs paramétereket.
 #9.11.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az ügynök állapotátmenetei kriptográfiailag aláírtak, időbélyeggel ellátottak és naplózottak legyenek teljes kontextussal együtt, beleértve a kiváltó eseményeket, az előző állapot hash-ét, az új állapot hash-ét és a végrehajtott biztonsági ellenőrzéseket.
 #9.11.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az ügynök leállítási eljárásai tartalmazzák-e a biztonságos memória törlést kriptográfiai törléssel vagy többszörös felülírással, a hitelesítő adatok visszavonását a tanúsítványközpont értesítésével, valamint a manipulációt jelző megszüntetési tanúsítványok létrehozását.
 #9.11.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az ügynök helyreállítási mechanizmusai kriptográfiai ellenőrzőösszegeket (minimum SHA-256) használnak az állapot integritásának igazolására, és korrupt állapot esetén visszaállnak ismert, jó állapotokra automatizált riasztások és manuális jóváhagyási követelmények mellett.
 #9.11.5    Level: 3    Role: D/V
 Ellenőrizze, hogy az ügynök perzisztencia mechanizmusai AES-256 kulcsokkal egyedi ügynökenként titkosítják-e az érzékeny állapotadatokat, és biztosítják-e a biztonságos kulcscserét konfigurálható ütemezés szerint (maximálisan 90 nap), valamint a nulla állásidős telepítést.

---

### 9.12 Eszközintegrációs Biztonsági Keretrendszer

Biztonsági intézkedések a dinamikus eszközbetöltéshez, végrehajtáshoz és eredményellenőrzéshez, meghatározott kockázatértékelési és jóváhagyási folyamatokkal.

 #9.12.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az eszközleírók tartalmazzák-e a biztonsági metaadatokat, amelyek meghatározzák a szükséges jogosultságokat (olvasás/írás/végrehajtás), a kockázati szinteket (alacsony/közepes/magas), az erőforrás-korlátozásokat (CPU, memória, hálózat), valamint a validációs követelményeket, amelyek dokumentálva vannak az eszköz-manifesztumokban.
 #9.12.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az eszköz végrehajtási eredményei megfelelnek-e a várt sémáknak (JSON séma, XML séma) és a biztonsági irányelveknek (kimeneti tisztítás, adatklasszifikáció), mielőtt integrálná azokat időkorlátokkal és hibakezelési eljárásokkal.
 #9.12.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az eszköz interakciós naplók tartalmazzák-e a részletes biztonsági kontextust, beleértve az jogosultságok használatát, az adathozzáférési mintákat, a végrehajtási időt, az erőforrás-felhasználást és a visszatérési kódokat, továbbá strukturált naplózással történik-e a SIEM integrációhoz.
 #9.12.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a dinamikus eszközbetöltési mechanizmusok azonosítják-e a digitális aláírásokat a PKI infrastruktúra használatával, és valósítanak-e meg biztonságos betöltési protokollokat homokozó izolációval és engedély-ellenőrzéssel a végrehajtás előtt.
 #9.12.5    Level: 3    Role: D/V
 Ellenőrizze, hogy az eszköz biztonsági értékelései automatikusan elindulnak-e az új verziók esetében, kötelező jóváhagyási kapukkal, beleértve a statikus elemzést, dinamikus tesztelést és a biztonsági csapat átvizsgálását dokumentált jóváhagyási kritériumokkal és SLA követelményekkel.

---

#### Hivatkozások

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Ellenséges robusztusság és adatvédelmi védelem

### Ellenőrzési célkitűzés

Biztosítsuk, hogy az MI modellek megbízhatóak, adatvédelmet megtartók és visszaélések elleni védettek maradjanak, amikor kerülési, következtetési, kivonási vagy mérgezési támadásokkal szembesülnek.

---

### 10.1 Modellkövetés és biztonság

Óvd meg a káros vagy a szabályzatot sértő kimenetek ellen.

 #10.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az összehangolási tesztcsomag (red-team parancsok, jailbreak próbasorok, tiltott tartalom) verziókezelve van-e, és minden modellkiadásnál futtatják-e.
 #10.1.2    Level: 1    Role: D
 Ellenőrizze, hogy a visszautasítási és biztonságos befejezési védősávok érvényesülnek-e.
 #10.1.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az automatizált értékelő mérje a káros tartalom arányát, és jelezze a küszöbértéket meghaladó visszaeséseket.
 #10.1.4    Level: 2    Role: D
 Ellenőrizze, hogy az ellen-jailbreak képzés dokumentált és reprodukálható-e.
 #10.1.5    Level: 3    Role: V
 Ellenőrizze, hogy a formális szabályzati megfelelőségi bizonyítékok vagy a tanúsított megfigyelés lefedik-e a kritikus területeket.

---

### 10.2 Ellenséges példa elleni megerősítés

Növelje a manipulált bemenetekkel szembeni ellenállóképességet. A robusztus adverszáriális tanítás és a benchmark pontozás jelenleg a legjobb gyakorlat.

 #10.2.1    Level: 1    Role: D
 Ellenőrizze, hogy a projekt adattárai tartalmaznak-e ellenséges tanítással kapcsolatos konfigurációkat reprodukálható véletlenszám-generátor magokkal.
 #10.2.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a támadópélda-felismerés figyelmeztető blokkoló jelzéseket ad-e a gyártási folyamatokban.
 #10.2.4    Level: 3    Role: V
 Ellenőrizze, hogy a tanúsított-robusság bizonyítások vagy intervallumhatár tanúsítványok legalább a legkritikusabb osztályokat lefedik-e.
 #10.2.5    Level: 3    Role: V
 Ellenőrizze, hogy a regressziós tesztek adaptív támadásokat használnak-e annak megerősítésére, hogy nincs mérhető robusztusságveszteség.

---

### 10.3 Tagság-inferenciás támadások csökkentése

Korlátozza annak lehetőségét, hogy eldöntsék, egy rekord szerepelt-e a tanító adatok között. A differenciális adatvédelem és a bizalmi pontszám maszkolása továbbra is a leghatékonyabb ismert védekezési módszerek.

 #10.3.1    Level: 1    Role: D
 Ellenőrizze, hogy az egyes lekérdezések szerinti entrópia szabályozás vagy a hőmérséklet-skálázás csökkenti-e a túlzottan magabiztos előrejelzéseket.
 #10.3.2    Level: 2    Role: D
 Ellenőrizze, hogy a tanítás ε-korlátozott differenciálisan privát optimalizációt alkalmaz-e érzékeny adatkészletek esetében.
 #10.3.3    Level: 2    Role: V
 Ellenőrizze, hogy a támadási szimulációk (árnyékmodell vagy fekete dobozos) támadási AUC értéke ≤ 0,60 legyen a külön tartott adatokon.

---

### 10.4 Modell-inverzió elleni ellenállás

Meg kell akadályozni a privát attribútumok rekonstrukcióját. A legújabb felmérések a kimenet levágását és a DP garanciákat hangsúlyozzák, mint gyakorlati védekezéseket.

 #10.4.1    Level: 1    Role: D
 Győződjön meg arról, hogy az érzékeny attribútumokat soha ne adják közvetlenül ki; ahol szükséges, használjon tartományokat vagy egyirányú átalakításokat.
 #10.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a lekérdezési aránykorlátok korlátozzák-e az ismétlődő, adaptív lekérdezéseket ugyanattól a jogosulttól.
 #10.4.3    Level: 2    Role: D
 Ellenőrizze, hogy a modellt adatvédelmet biztosító zajjal képezték-e.

---

### 10.5 Modellkivonás elleni védelem

Azonosítsa és akadályozza meg az engedély nélküli klónozást. Javasolt a vízjelzés és a lekérdezési mintaelemzés alkalmazása.

 #10.5.1    Level: 1    Role: D
 Ellenőrizze, hogy az inferencia átjárók betartják-e a globális és az egyes API-kulcsokra vonatkozó korlátokat, amelyek a modell memorizálási küszöbéhez vannak hangolva.
 #10.5.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a lekérdezési entrópia és a bemeneti plurális statisztikák táplálják-e az automatikus kinyerő detektort.
 #10.5.3    Level: 2    Role: V
 Ellenőrizze, hogy a törékeny vagy valószínűségi vízjeleket p < 0,01 szinten igazolni lehet-e legfeljebb 1 000 lekérdezés során a gyanúsított klón ellen.
 #10.5.4    Level: 3    Role: D
 Ellenőrizze, hogy a vízjel kulcsok és a kiváltó készletek hardverbiztonsági modulban vannak tárolva, és évente forgatva vannak.
 #10.5.5    Level: 3    Role: V
 Ellenőrizze, hogy az extraction-alert események tartalmazzák-e a szabályszegő lekérdezéseket, és integrálva vannak-e az incidens-válasz játékkönyvekkel.

---

### 10.6 Feltételezés idejű mérgezett adatok detektálása

Azonosítsa és semlegesítse a hátsóajtós vagy mérgezett bemeneteket.

 #10.6.1    Level: 1    Role: D
 Ellenőrizze, hogy a bemenetek áthaladnak-e egy anomáliaészlelőn (pl. STRIP, konzisztencia-értékelés) a modell predikciója előtt.
 #10.6.2    Level: 1    Role: V
 Ellenőrizze, hogy az érzékelő küszöbszintek tiszta/mérgezett validációs készleteken vannak-e beállítva, hogy kevesebb mint 5%-os hamis pozitív arányt érjenek el.
 #10.6.3    Level: 2    Role: D
 Ellenőrizze, hogy a mérgezettnek jelölt bemenetek kiváltják-e a lágy blokkolást és az emberi felülvizsgálati munkafolyamatokat.
 #10.6.4    Level: 2    Role: V
 Ellenőrizze, hogy a detektorokat alkalmazkodó, trigger nélküli hátsóajtó támadásokkal stressztesztelik-e.
 #10.6.5    Level: 3    Role: D
 Ellenőrizze, hogy a detektálási hatékonysági mutatókat rögzítik-e, és rendszeresen újraértékelik-e friss fenyegetésinformációk alapján.

---

### 10.7 Dinamikus biztonsági szabályzat adaptáció

Valós idejű biztonsági szabályzatfrissítések fenyegetésinformációk és viselkedéselemzés alapján.

 #10.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a biztonsági szabályzatok dinamikusan frissíthetők-e az ügynök újraindítása nélkül, miközben megőrzik a szabályzat verziójának épségét.
 #10.7.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a szabályzatfrissítéseket az arra jogosult biztonsági személyzet kriptográfiailag aláírta-e, és alkalmazás előtt érvényesítették-e.
 #10.7.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a dinamikus irányelvváltoztatások teljes audit nyomvonalakkal vannak-e naplózva, beleértve az indoklást, jóváhagyási láncokat és visszavonási eljárásokat.
 #10.7.4    Level: 3    Role: D/V
 Ellenőrizze, hogy az adaptív biztonsági mechanizmusok a kockázati kontextus és a viselkedési minták alapján állítják-e be a fenyegetésészlelés érzékenységét.
 #10.7.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a szabályzat-alkalmazkodási döntések magyarázhatók-e, és tartalmaznak-e bizonyítékláncokat a biztonsági csapat átvizsgálásához.

---

### 10.8 Visszaverődés-alapú biztonsági elemzés

Biztonsági érvényesítés ágens önreflexiója és meta-kognitív elemzése révén.

 #10.8.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az ügynök reflexió mechanizmusai tartalmazzák-e a döntések és cselekvések biztonságközpontú önértékelését.
 #10.8.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a reflektált kimenetek érvényesítve vannak-e, hogy megakadályozzák az önértékelési mechanizmusok manipulálását támadó bemenetek által.
 #10.8.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a metakognitív biztonsági elemzés azonosítja-e a potenciális elfogultságot, manipulációt vagy sérülékenységet az ügynök érvelési folyamataiban.
 #10.8.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a reflektív alapú biztonsági figyelmeztetések aktiválják-e a fokozott megfigyelést és a lehetséges emberi beavatkozási munkafolyamatokat.
 #10.8.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a biztonsági visszatekintésekből származó folyamatos tanulás javítja-e a fenyegetések észlelését anélkül, hogy rontaná a jogos funkciókat.

---

### 10.9 Fejlődés és Önjavító Biztonság

Biztonsági ellenőrzések az önmódosításra és fejlődésre képes ügynök rendszerek számára.

 #10.9.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az önmódosító képességek korlátozottak-e kijelölt biztonságos területekre formális verifikációs határokkal.
 #10.9.2    Level: 2    Role: D/V
 Győződjön meg arról, hogy a fejlesztési javaslatok biztonsági hatásvizsgálaton mennek keresztül a megvalósítás előtt.
 #10.9.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az önfejlesztő mechanizmusok tartalmaznak-e visszagörgetési képességeket integritásellenőrzéssel.
 #10.9.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a meta-tanulás biztonsága megakadályozza-e a fejlődési algoritmusok elleni támadó manipulatív beavatkozást.
 #10.9.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a rekurzív önfejlesztés formális biztonsági korlátok által van-e határolva, konvergenciára vonatkozó matematikai bizonyításokkal.

---

#### Hivatkozások

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Adatvédelem és személyes adatkezelés

### Vezérlési cél

Tartsa fenn a szigorú adatvédelmi biztosítékokat az AI teljes életciklusa során — gyűjtés, tanítás, következtetés és incidenskezelés — úgy, hogy a személyes adatokat csak világos hozzájárulással, a szükséges minimális mértékben, bizonyítható törléssel és hivatalos adatvédelmi garanciákkal dolgozzák fel.

---

### 11.1 Anonimizáció és adatminimalizálás

 #11.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a közvetlen és kvázi-azonosítók el lettek távolítva vagy kódolva (hash-elve).
 #11.1.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az automatizált auditok mérik-e a k-anonimitást/l-sokféleséget, és figyelmeztetnek, amikor a küszöbértékek a szabályzat alattra esnek.
 #11.1.3    Level: 2    Role: V
 Ellenőrizze, hogy a modell jellemző-importance jelentései igazolják-e, hogy az azonosító szivárgása nem haladja meg az ε = 0,01 kölcsönös információt.
 #11.1.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális bizonyítékok vagy a szintetikus adatok tanúsítása szerint a visszaazonosítási kockázat ≤ 0,05 még összekapcsolási támadások esetén is teljesül.

---

### 11.2 Az elfeledtetéshez való jog és a törlés végrehajtása

 #11.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az adat alany törlési kérelmei továbbítódnak-e a nyers adatkészletekhez, ellenőrzőpontokhoz, beágyazásokhoz, naplókhoz és biztonsági mentésekhez 30 napon belüli szolgáltatási szint megállapodások szerint.
 #11.2.2    Level: 2    Role: D
 Ellenőrizze, hogy a „gépi felejtés” rutinok fizikailag újraképeznek-e vagy megközelítő törlést hajtanak végre tanúsított felejtési algoritmusok alkalmazásával.
 #11.2.3    Level: 2    Role: V
 Ellenőrizze, hogy az árnyékmodell-értékelés bizonyítja-e, hogy a felejtett rekordok kevesebb mint 1%-ban befolyásolják a kimeneteket a felejtés után.
 #11.2.4    Level: 3    Role: V
 Ellenőrizze, hogy a törlési események megváltoztathatatlanul rögzítve vannak-e, és megfelelnek-e a szabályozók általi auditálhatóságnak.

---

### 11.3 Differenciálisan privát védelmi intézkedések

 #11.3.1    Level: 2    Role: D/V
 Győződjön meg arról, hogy a privátosságvesztés-számítási irányítópultok riasztanak, amikor a kumulatív ε meghaladja a szabályzati küszöbértékeket.
 #11.3.2    Level: 2    Role: V
 Ellenőrizze, hogy a feketedobozos adatvédelmi auditok az ε̂ értéket a deklarált érték 10%-án belül becslik-e.
 #11.3.3    Level: 3    Role: V
 Ellenőrizze, hogy a hivatalos bizonyítások minden utólagos finomhangolást és beágyazást lefednek-e.

---

### 11.4 Célmeghatározás-korlátozás és Terjedelem-növekedés elleni védelem

 #11.4.1    Level: 1    Role: D
 Ellenőrizze, hogy minden adatállomány és modellellenőrzőpont géppel olvasható célcímkével rendelkezzen, amely összhangban van az eredeti hozzájárulással.
 #11.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a futásidejű monitorok észlelik-e a nyilatkozott céllal ellentétes lekérdezéseket, és kiváltanak-e puha elutasítást.
 #11.4.3    Level: 3    Role: D
 Ellenőrizze, hogy a kód alapú irányelvek akadályozzák-e a modellek új területekre történő újbóli telepítését DPIA felülvizsgálat nélkül.
 #11.4.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális követhetőségi bizonyítékok igazolják-e, hogy minden személyes adat életciklusa a beleegyezéssel meghatározott keretek között marad.

---

### 11.5 Hozzájárulás-kezelés és Jogalap-követés

 #11.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a Hozzájárulás-kezelési Platform (CMP) rögzíti-e az adatkezeléshez való hozzájárulás státuszát, célját és megőrzési idejét az egyes adat alanyokra vonatkozóan.
 #11.5.2    Level: 2    Role: D
 Ellenőrizze, hogy az API-k kiteszik-e a hozzájárulási tokeneket; a modelleknek az előrejelzés előtt érvényesíteniük kell a token jogosultsági körét.
 #11.5.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a megtagadott vagy visszavont hozzájárulás 24 órán belül leállítja-e a feldolgozási folyamatokat.

---

### 11.6 Szövetséges tanulás adatvédelmi szabályozásokkal

 #11.6.1    Level: 1    Role: D
 Ellenőrizze, hogy az ügyfél-frissítések helyi differenciális adatvédelmi zajhozzáadást alkalmaznak-e az aggregálás előtt.
 #11.6.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a tanulási metrikák differenciálisan privátak legyenek, és soha ne fedjék fel egyetlen kliens veszteségét sem.
 #11.6.3    Level: 2    Role: V
 Ellenőrizze, hogy a mérgezés-ellenálló aggregáció (például Krum/Trimmed-Mean) engedélyezve van-e.
 #11.6.4    Level: 3    Role: V
 Ellenőrizze, hogy a formális bizonyítások az összes ε költségvetést kevesebb, mint 5-ös hasznosságveszteséggel mutatják be.

---

#### Hivatkozások

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Megfigyelés, Naplózás és Anomáliaészlelés

### Ellenőrzési célkitűzés

Ez a szakasz követelményeket határoz meg annak érdekében, hogy valós idejű és forenzikus láthatóságot biztosítson arra vonatkozóan, mit lát, mit csinál és mit ad vissza a modell és egyéb AI-komponensek, így a fenyegetéseket észlelni, osztályozni és tanulni lehessen belőlük.

### C12.1 Kérés- és válasznaplózás

 #12.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az összes felhasználói utasítás és a modell válaszai megfelelő metaadatokkal (pl. időbélyeg, felhasználói azonosító, munkamenet-azonosító, modell verzió) együtt legyenek naplózva.
 #12.1.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a naplók biztonságos, hozzáférés-ellenőrzött tárhelyeken vannak-e tárolva, megfelelő megőrzési szabályzatokkal és biztonsági mentési eljárásokkal.
 #12.1.3    Level: 1    Role: D/V
 Ellenőrizze, hogy a napló tároló rendszerek implementálnak-e adatok nyugalmi állapotbeli és átvitel közbeni titkosítást a naplókban található érzékeny információk védelme érdekében.
 #12.1.4    Level: 1    Role: D/V
 Ellenőrizze, hogy a promptokban és kimenetekben lévő érzékeny adatok automatikusan el legyenek távolítva vagy maszkolva a naplózás előtt, konfigurálható eltávolítási szabályokkal a személyes azonosító információk (PII), hitelesítő adatok és tulajdonosi információk esetén.
 #12.1.5    Level: 2    Role: D/V
 Ellenőrizze, hogy a szabályzat döntései és a biztonsági szűrési intézkedések kellő részletességgel legyenek naplózva, hogy lehetővé tegyék a tartalommenedzsment rendszerek auditálását és hibakeresését.
 #12.1.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a napló integritását védik-e például kriptográfiai aláírások vagy csak írásra alkalmas tárolás segítségével.

---

### C12.2 Visszaélésészlelés és riasztás

 #12.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a rendszer felismeri-e és riaszt-e ismert jailbreak mintázatok, prompt injekciós kísérletek és ellenséges bemenetek esetén aláírásalapú észlelés segítségével.
 #12.2.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a rendszer integrálódik-e a meglévő Biztonsági Információ- és Eseménykezelő (SIEM) platformokkal szabványos naplóformátumok és protokollok használatával.
 #12.2.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a kibővített biztonsági események tartalmazzák-e az AI-specifikus kontextust, például modellazonosítókat, megbízhatósági pontszámokat és a biztonsági szűrő döntéseit.
 #12.2.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a viselkedési anomáliafelismerés azonosítja-e a szokatlan beszélgetési mintázatokat, a túlzott ismétlési kísérleteket vagy a rendszerszintű kutató jellegű viselkedéseket.
 #12.2.5    Level: 2    Role: D/V
 Ellenőrizze, hogy az valós idejű riasztási mechanizmusok értesítik-e a biztonsági csapatokat, amikor potenciális szabályzat megsértéseket vagy támadási kísérleteket észlelnek.
 #12.2.6    Level: 2    Role: D/V
 Ellenőrizze, hogy a személyre szabott szabályok tartalmazzák-e az AI-specifikus fenyegetési minták észlelését, beleértve az összehangolt jailbreak kísérleteket, prompt befecskendezési kampányokat és a modellkivonási támadásokat.
 #12.2.7    Level: 3    Role: D/V
 Ellenőrizze, hogy az automatikus incidensválasz-munkafolyamatok képesek-e elszigetelni a kompromittált modelleket, blokkolni a rosszindulatú felhasználókat, és súlyos biztonsági események esetén továbbítani azokat.

---

### C12.3 Modell-eltolódás észlelése

 #12.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a rendszer nyomon követi-e az alapvető teljesítménymutatókat, például a pontosságot, a bizalmi pontszámokat, a késleltetést és a hibaarányokat a modellverziók és az időszakok során.
 #12.3.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az automatizált riasztás aktiválódik-e, amikor a teljesítménymutatók túllépik az előre meghatározott degradációs küszöbértékeket, vagy jelentősen eltérnek az alapértékektől.
 #12.3.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a hallucinációészlelő monitorok azonosítják-e és jelölik-e azokat az eseteket, amikor a modell kimenete tényileg helytelen, inkonzisztens vagy kitalált információkat tartalmaz.

---

### C12.4 Teljesítmény- és viselkedéstávoli mérés

 #12.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az olyan működési mutatók, mint a kérés késleltetése, token-felhasználás, memóriahasználat és áteresztőképesség folyamatosan gyűjtésre és figyelésre kerülnek-e.
 #12.4.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a siker- és hibaarányokat egyaránt nyomon követik-e a hibatípusok és azok alapvető okainak kategorizálásával.
 #12.4.3    Level: 2    Role: D/V
 Ellenőrizze, hogy az erőforrás-használat figyelése tartalmazza-e a GPU/CPU használatát, a memóriafogyasztást és a tárolási igényeket, valamint riasztást ad-e a küszöbérték túllépése esetén.

---

### C12.5 MI Eseménykezelési Tervezés és Végrehajtás

 #12.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a incidensreagálási tervek kifejezetten foglalkoznak-e az AI-hoz kapcsolódó biztonsági eseményekkel, beleértve a modell kompromittálását, az adatmérgezést és a támadó jellegű támadásokat.
 #12.5.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az incidenskezelő csapatok hozzáférnek-e az AI-specifikus forenzikai eszközökhöz és szakértelemhez a modell viselkedésének és a támadási vektorok vizsgálatához.
 #12.5.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az esemény utáni elemzés tartalmazza-e a modell újratanításának szempontjait, a biztonsági szűrők frissítését és a tanulságok beépítését a biztonsági ellenőrzésekbe.

---

### C12.5 AI teljesítményromlás észlelése

Figyelje és észlelje az AI-modell teljesítményének és minőségének romlását az idő múlásával.

 #12.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a modell pontosságát, precizitását, visszahívását és F1 pontszámait folyamatosan figyelik és összehasonlítják az alapvonal küszöbértékekkel.
 #12.5.2    Level: 1    Role: D/V
 Ellenőrizze, hogy az adatelmozdulás-észlelés figyeli-e a bemeneti eloszlás változásait, amelyek hatással lehetnek a modell teljesítményére.
 #12.5.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a koncepcióeltolódás-észlelés azonosítja-e a bemenetek és a várt kimenetek közötti kapcsolat változásait.
 #12.5.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a teljesítményromlás automatikus riasztásokat vált-e ki, és elindítja-e a modell újratanítását vagy cseréjét célzó munkafolyamatokat.
 #12.5.5    Level: 3    Role: V
 Ellenőrizze, hogy a teljesítményromlás okainak elemzése összefügg-e az adatok változásaival, az infrastruktúra problémáival vagy külső tényezőkkel.

---

### C12.6 DAG megjelenítés és munkafolyamat-biztonság

Védje a munkafolyamat-visualizációs rendszereket az információszivárgás és a manipulációs támadások ellen.

 #12.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a DAG vizualizációs adatokat megtisztították-e a tárolás vagy továbbítás előtt az érzékeny információk eltávolítása érdekében.
 #12.6.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a munkafolyamat-vizualizáció hozzáférés-vezérlése biztosítja-e, hogy csak az arra jogosult felhasználók tekinthetik meg az ügynök döntési útvonalait és érvelési nyomait.
 #12.6.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a DAG adatintegritása kriptográfiai aláírások és manipulációt kimutató tárolási mechanizmusok révén védett-e.
 #12.6.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a munkafolyamat-visualizációs rendszerek bevezetik-e a bemeneti érvényesítést, hogy megakadályozzák a beszúrásos támadásokat manipulált csomópont- vagy éladatokon keresztül.
 #12.6.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a valós idejű DAG-frissítések sebességkorlátozva és érvényesítve vannak-e a szolgáltatásmegtagadási (DoS) támadásokkal szembeni védelem érdekében a vizualizációs rendszereken.

---

### C12.7 Proaktív biztonsági viselkedésfigyelés

Biztonsági fenyegetések észlelése és megelőzése proaktív ügynök viselkedéselemzés révén.

 #12.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a proaktív ügynök viselkedések végrehajtás előtt biztonságilag validáltak-e, kockázatértékelési integrációval.
 #12.7.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az autonóm kezdeményezések kiváltói tartalmazzák-e a biztonsági környezet értékelését és a fenyegetési helyzet felmérését.
 #12.7.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a proaktív viselkedésmintákat elemezték-e potenciális biztonsági következmények és nem kívánt hatások szempontjából.
 #12.7.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a biztonságkritikus proaktív intézkedésekhez egyértelmű jóváhagyási láncok és auditnaplók szükségesek-e.
 #12.7.5    Level: 3    Role: D/V
 Ellenőrizze, hogy a viselkedéses anomáliaészlelés azonosítja-e az előrejelző ügynök mintázatainak eltéréseit, amelyek kompromittáltságot jelezhetnek.

---

### Hivatkozások

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Emberi felügyelet, elszámoltathatóság és irányítás

### Ellenőrzési célkitűzés

Ez a fejezet előírja az emberi felügyelet és a világos elszámoltathatósági láncok fenntartásának követelményeit az MI-rendszerekben, biztosítva az átláthatóságot, magyarázhatóságot és etikai irányítást az MI életciklusa során.

---

### C13.1 Vészleállító és felülbírálati mechanizmusok

Biztosítson leállítási vagy visszagörgetési lehetőségeket, amikor az AI rendszer nem biztonságos viselkedése észlelhető.

 #13.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy létezik-e egy kézi vészleállító mechanizmus az AI modell következtetésének és kimeneteinek azonnali leállítására.
 #13.1.2    Level: 1    Role: D
 Ellenőrizze, hogy a felülírási vezérlők csak az arra jogosult személyek számára legyenek hozzáférhetők.
 #13.1.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a visszaállítási eljárások képesek-e visszatérni korábbi modellverziókhoz vagy biztonságos módú műveletekhez.
 #13.1.4    Level: 3    Role: V
 Ellenőrizze, hogy a felülírási mechanizmusokat rendszeresen tesztelik-e.

---

### C13.2 Ember a ciklusban döntési ellenőrzőpontok

Emberi jóváhagyásokat igényel, amikor a tét meghaladja az előre meghatározott kockázati küszöböket.

 #13.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a magas kockázatú MI-döntések végrehajtása előtt egyértelmű emberi jóváhagyás szükséges-e.
 #13.2.2    Level: 1    Role: D
 Ellenőrizze, hogy a kockázati küszöbértékek egyértelműen definiáltak-e, és automatikusan elindítják-e az emberi felülvizsgálati munkafolyamatokat.
 #13.2.3    Level: 2    Role: D
 Ellenőrizze, hogy az időérzékeny döntések esetén léteznek-e tartalék eljárások, ha az emberi jóváhagyás a szükséges határidőn belül nem szerezhető be.
 #13.2.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a fokozásra vonatkozó eljárások egyértelmű hatásköröket határoznak-e meg a különböző döntéstípusokra vagy kockázati kategóriákra, amennyiben alkalmazható.

---

### C13.3 Felelősségi Lánc és Auditálhatóság

Naplózza az operátori műveleteket és a modell döntéseit.

 #13.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy minden MI-rendszer döntést és emberi beavatkozást időbélyeggel, felhasználói azonosságokkal és döntési indokolással rögzítenek-e.
 #13.3.2    Level: 2    Role: D
 Ellenőrizze, hogy a naplózási adatok nem hamisíthatók-e meg, és tartalmaznak-e integritás-ellenőrzési mechanizmusokat.

---

### C13.4 Magyarázható mesterséges intelligencia (Explainable-AI) technikák

Felületi jellemző fontosság, ellen-tények és helyi magyarázatok.

 #13.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a mesterséges intelligencia rendszerek alapvető magyarázatokat adnak-e döntéseikről ember által olvasható formátumban.
 #13.4.2    Level: 2    Role: V
 Ellenőrizze, hogy a magyarázat minőségét emberi értékelési tanulmányok és metrikák segítségével igazolták-e.
 #13.4.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a fontos döntésekhez rendelkezésre állnak-e a jellemzőfontossági pontszámok vagy hozzárendelési módszerek (SHAP, LIME stb.).
 #13.4.4    Level: 3    Role: V
 Ellenőrizze, hogy a kontrafaktuális magyarázatok megmutatják-e, hogyan lehet az inputokat módosítani az eredmények megváltoztatásához, amennyiben ez alkalmazható az adott felhasználási esetben és területen.

---

### C13.5 Modellkártyák és használati nyilatkozatok

Tartsa karban a modellek kártyáit a tervezett felhasználásról, a teljesítménymutatókról és az etikai megfontolásokról.

 #13.5.1    Level: 1    Role: D
 Ellenőrizze, hogy a modellkártyák dokumentálják-e a tervezett használati eseteket, korlátozásokat és ismert hibamódokat.
 #13.5.2    Level: 1    Role: D/V
 Ellenőrizze, hogy a különböző alkalmazható használati esetekre vonatkozó teljesítménymutatók nyilvánosságra vannak-e hozva.
 #13.5.3    Level: 2    Role: D
 Ellenőrizze, hogy az etikai megfontolások, az elfogultságértékelések, a méltányossági vizsgálatok, a képzési adatok jellemzői és a képzési adatok ismert korlátai dokumentálva vannak-e és rendszeresen frissítve.
 #13.5.4    Level: 2    Role: D/V
 Ellenőrizze, hogy a modellkártyák verziókezelték-e és karbantartották-e a modell életciklusa során változáskövetéssel.

---

### C13.6 Bizonytalanság kvantifikálása

Terjessze a bizalmi pontszámokat vagy entrópia-mutatókat a válaszokban.

 #13.6.1    Level: 1    Role: D
 Ellenőrizze, hogy a mesterséges intelligencia rendszerek megbízhatósági pontszámokat vagy bizonytalansági mértékeket adnak-e az eredményeikkel együtt.
 #13.6.2    Level: 2    Role: D/V
 Ellenőrizze, hogy a bizonytalansági küszöbértékek további emberi felülvizsgálatot vagy alternatív döntési útvonalakat váltanak-e ki.
 #13.6.3    Level: 2    Role: V
 Ellenőrizze, hogy a bizonytalansági kvantifikációs módszerek kalibráltak és a valós adatok alapján validáltak-e.
 #13.6.4    Level: 3    Role: D/V
 Ellenőrizze, hogy a bizonytalanság terjedése megmarad-e a többlépéses AI munkafolyamatokon keresztül.

---

### C13.7 Felhasználói átláthatósági jelentések

Rendszeres tájékoztatást kell nyújtani az incidensekről, az eltérésekről és az adatok használatáról.

 #13.7.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az adatfelhasználási irányelveket és a felhasználói hozzájárulás-kezelési gyakorlatokat egyértelműen kommunikálják az érintettek felé.
 #13.7.2    Level: 2    Role: D/V
 Ellenőrizze, hogy az AI hatásvizsgálatokat elvégezték-e, és az eredményeket beillesztették-e a jelentésekbe.
 #13.7.3    Level: 2    Role: D/V
 Ellenőrizze, hogy a rendszeresen közzétett átláthatósági jelentések ésszerű részletességgel közlik-e az MI-vel kapcsolatos eseményeket és működési mutatókat.

#### Hivatkozások

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Függelék A: Szójegyzék

Ez az átfogó szószedet meghatározásokat nyújt az AISVS-ben használt kulcsfontosságú MI, gépi tanulás és biztonsági kifejezésekhez, hogy biztosítsa a világosságot és a közös megértést.
​
Adverzáriális példa: Egy bemenet, amelyet szándékosan úgy alakítanak ki, hogy egy MI modell hibát kövessen el, gyakran apró, az emberek számára észrevehetetlen zavaró hatások hozzáadásával.
​
Adverzáriális robusztusság – Az adverzáriális robusztusság az MI-ben arra a képességre utal, hogy egy modell képes megőrizni teljesítményét és ellenállni az olyan szándékosan előállított, rosszindulatú bemenetek által okozott megtévesztésnek vagy manipulációnak, amelyek hibákat okoznak.
​
Ügynök – Az AI ügynökök olyan szoftverrendszerek, amelyek mesterséges intelligenciát használnak a felhasználók nevében történő célkitűzések elérésére és feladatok elvégzésére. Képesek érvelésre, tervezésre és emlékezetre, valamint autonómia szinttel rendelkeznek a döntéshozatal, tanulás és alkalmazkodás terén.
​
Agentikus mesterséges intelligencia: Olyan MI rendszerek, amelyek bizonyos fokú autonómiával működhetnek céljaik elérése érdekében, gyakran emberi beavatkozás nélkül hoznak döntéseket és hajtanak végre műveleteket.
​
Attribútum alapú hozzáférés-vezérlés (ABAC): Egy hozzáférés-vezérlési paradigma, ahol az engedélyezési döntések a felhasználó, az erőforrás, a művelet és a környezet attribútumain alapulnak, amelyek a lekérdezés idején kerülnek értékelésre.
​
Hátsó kapu támadás: Egy olyan adatmegfertőzési támadás, amely során a modellt úgy tanítják, hogy bizonyos kiváltó jelekre meghatározott módon reagáljon, miközben egyébként normálisan működik.
​
Elfogultság: Szisztematikus hibák az MI modell kimeneteiben, amelyek igazságtalan vagy diszkriminatív eredményekhez vezethetnek bizonyos csoportok vagy specifikus kontextusok esetén.
​
Elfogultság kihasználása: Egy támadási technika, amely kihasználja az AI modellek ismert elfogultságait az eredmények vagy kimenetek manipulálására.
​
Cedar: Az Amazon szabályzati nyelve és motorja finomhangolt jogosultságokhoz, amelyet ABAC (attribútumalapú hozzáférés-vezérlés) megvalósításához használnak mesterséges intelligencia rendszerekben.
​
Gondolatmenet: Egy olyan technika, amely a nyelvi modellek érvelésének javítására szolgál azáltal, hogy közbenső érvelési lépéseket generál a végső válasz megadása előtt.
​
Áramkörmegszakítók: Olyan mechanizmusok, amelyek automatikusan leállítják a mesterséges intelligencia rendszer működését, amikor a meghatározott kockázati küszöbértékeket átlépik.
​
Adatszivárgás: érzékeny információk nem szándékolt kiszivárogtatása AI modell kimenetei vagy viselkedése révén.
​
Adat mérgezés: A tanító adatok szándékos megrongálása a modell integritásának veszélyeztetése érdekében, gyakran hátuljáratok telepítésére vagy a teljesítmény csökkentésére.
​
Differenciális adatvédelem – A differenciális adatvédelem egy matematikailag szigorú keretrendszer statisztikai információk közzétételére adatállományokról, miközben védi az egyéni adattulajdonosok magánszféráját. Lehetővé teszi az adatszolgáltató számára, hogy megossza a csoport összesített mintázatait, miközben korlátozza az adott egyénekre vonatkozó információk kiszivárgását.
​
Beágyazások: Adatok (szöveg, képek stb.) sűrű vektoros ábrázolásai, amelyek szemantikai jelentést ragadnak meg egy magas dimenziójú térben.
​
Magyarázhatóság – Az AI magyarázhatósága annak a képessége, hogy egy mesterséges intelligencia rendszer ember által érthető okokat szolgáltasson döntéseihez és előrejelzéseihez, betekintést nyújtva belső működésébe.
​
Magyarázható mesterséges intelligencia (XAI): Olyan MI rendszerek, amelyeket úgy terveztek, hogy különféle technikák és keretrendszerek segítségével ember számára érthető magyarázatokat nyújtsanak döntéseikről és viselkedésükről.
​
Federált tanulás: Egy gépi tanulási megközelítés, ahol a modelleket több decentralizált eszközön képezik helyi adatminták felhasználásával, az adatok tényleges cseréje nélkül.
​
Védőkorlátok: Olyan korlátozások, amelyeket az AI rendszerek által káros, elfogult vagy egyébként nem kívánatos kimenetek előállításának megelőzésére vezetnek be.
​
Hallucináció – Az AI hallucináció olyan jelenségre utal, amikor egy mesterséges intelligencia modell hibás vagy félrevezető információt állít elő, amely nem alapul a tanítási adataiban vagy a tényleges valóságban.
​
Ember a ciklusban (HITL): Olyan rendszerek, amelyeket emberi felügyelet, ellenőrzés vagy beavatkozás igényére terveztek kulcsfontosságú döntési pontokon.
​
Infrastruktúra kódként (IaC): az infrastruktúra kezelése és előállítása kódon keresztül, manuális folyamatok helyett, lehetővé téve a biztonsági vizsgálatot és az egységes telepítéseket.
​
Jailbreak: Azok a technikák, amelyeket az AI rendszerek, különösen a nagyméretű nyelvi modellek biztonsági korlátainak megkerülésére használnak tiltott tartalom előállítása érdekében.
​
Legkisebb jogosultság elve: Az a biztonsági elv, amely szerint a felhasználóknak és folyamatoknak csak a minimálisan szükséges hozzáférési jogokat kell megadni.
​
LIME (Helyi Értelmezhető Modellfüggetlen Magyarázatok): Egy olyan technika, amely bármely gépi tanulási osztályozó előrejelzéseit magyarázza meg, azáltal hogy helyileg egy értelmezhető modellel közelíti azt.
​
Tagsági következtetési támadás: Olyan támadás, amelynek célja annak meghatározása, hogy egy adott adatpontot felhasználtak-e egy gépi tanulási modell betanításához.
​
MITRE ATLAS: Ellenséges fenyegetési körkép mesterséges intelligencia rendszerekhez; egy tudásbázis az AI rendszerek elleni ellenséges taktikákról és technikákról.
​
Modellkártya – A modellkártya egy olyan dokumentum, amely szabványosított információkat nyújt egy MI modell teljesítményéről, korlátairól, tervezett felhasználásáról és etikai megfontolásairól, elősegítve ezzel az átláthatóságot és a felelős MI fejlesztést.
​
Modellkivonás: Olyan támadás, amely során a támadó ismételten lekérdez egy céltárgy modellből, hogy engedély nélkül létrehozzon egy funkcionálisan hasonló másolatot.
​
Modellinverzió: Egy támadás, amely a modell kimeneteinek elemzésével próbálja rekonstruálni a tanító adatokat.
​
Modell életciklus kezelése – Az AI modell életciklus kezelése az AI modell létezésének minden szakaszának felügyeletét jelenti, beleértve a tervezést, fejlesztést, alkalmazást, monitorozást, karbantartást és végső nyugdíjazást, annak érdekében, hogy a modell hatékony maradjon és összhangban legyen a kitűzött célokkal.
​
Modelmérgezés: Sérülékenységek vagy hátsóajtók közvetlen bevezetése egy modellbe a tanulási folyamat során.
​
Modelllopás/Tolvajlás: Egy tulajdonosi modell másolatának vagy közelítésének kinyerése ismételt lekérdezések révén.
​
Többügynökös rendszer: Olyan rendszer, amely több, egymással kölcsönhatásban álló mesterséges intelligencia ügynökből áll, amelyek egyenként eltérő képességekkel és célokkal rendelkezhetnek.
​
OPA (Open Policy Agent): Egy nyílt forráskódú szabályozási motor, amely egységes szabályozás végrehajtást tesz lehetővé az egész rendszerben.
​
Adatvédelmet biztosító gépi tanulás (PPML): Módszerek és technikák a gépi tanulási modellek képzésére és alkalmazására úgy, hogy közben megóvják a képzési adatok magánéletét.
​
Promptinjektálás: Egy támadási mód, ahol rosszindulatú utasítások kerülnek beágyazásra a bemenetekbe, hogy felülírják a modell eredetileg szánt viselkedését.
​
RAG (Lekérdezés-Alapú Generálás): Egy olyan technika, amely a nagy nyelvi modelleket úgy fejleszti, hogy a válasz generálása előtt releváns információkat szerez külső tudásforrásokból.
​
Red-Teaming: Az AI rendszerek aktív tesztelésének gyakorlata, amely során ellenséges támadásokat szimulálnak a sebezhetőségek azonosítása érdekében.
​
SBOM (Szoftver-összetevők jegyzéke): Egy hivatalos nyilvántartás, amely tartalmazza a szoftver vagy AI modellek készítéséhez használt különböző összetevők részleteit és ellátási lánc kapcsolatait.
​
SHAP (SHapley Additive exPlanations): Egy játékelméleti megközelítés a gépi tanulási modell bármely kimenetének magyarázatára, amely a predikcióhoz való hozzájárulását számolja ki az egyes jellemzőknek.
​
Ellátási lánc támadás: Egy rendszer kompromittálása az ellátási lánc kevésbé biztonságos elemeinek célozásával, például harmadik fél által biztosított könyvtárak, adatállományok vagy előre betanított modellek révén.
​
Átviteli tanulás: Egy olyan technika, ahol egy adott feladatra fejlesztett modellt újrahasznosítanak kiindulópontként egy második feladathoz tartozó modell esetében.
​
Vektoradatbázis: Olyan speciális adatbázis, amely magasdimenziós vektorok (beágyazások) tárolására és hatékony hasonlósági keresések végrehajtására szolgál.
​
Sebezhetőség-vizsgálat: Automatikus eszközök, amelyek azonosítják a szoftverkomponensek, beleértve a mesterséges intelligencia keretrendszereket és függőségeket, ismert biztonsági sebezhetőségeit.
​
Vízjelzés: Olyan technikák, amelyek segítségével érzékelhetetlen jeleket ágyaznak be AI által generált tartalmakba az eredetük nyomon követése vagy az AI általi generálás felismerése érdekében.
​
Zero-Day sérülékenység: Egy korábban ismeretlen sérülékenység, amelyet a támadók kihasználhatnak, mielőtt a fejlesztők javítást készítenének és telepítenének.

## Függelék B: Hivatkozások

### TODO

## C melléklet: MI Biztonsági Irányítás és Dokumentáció

### Célkitűzés

Ez a függelék alapvető követelményeket biztosít az AI biztonságának irányításához szükséges szervezeti struktúrák, szabályzatok és folyamatok kialakításához a rendszer teljes életciklusa során.

---

### AC.1 Mesterséges intelligencia kockázatkezelési keretrendszer elfogadása

Formális keretrendszer biztosítása az MI-specifikus kockázatok azonosítására, értékelésére és mérséklésére a rendszer életciklusa során.

 #AC.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy egy mesterséges intelligenciára specifikus kockázatértékelési módszertan dokumentált és bevezetett-e.
 #AC.1.2    Level: 2    Role: D
 Ellenőrizze, hogy a kockázatértékeléseket az MI életciklusának kulcsfontosságú pontjain és jelentős változások előtt elvégzik.
 #AC.1.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a kockázatkezelési keretrendszer összhangban van-e a létrehozott szabványokkal (pl. NIST AI RMF).

---

### AC.2 MI Biztonsági Irányelvek és Eljárások

Határozzon meg és érvényesítsen szervezeti szabványokat a biztonságos MI fejlesztésére, telepítésére és működtetésére.

 #AC.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy léteznek-e dokumentált AI biztonsági irányelvek.
 #AC.2.2    Level: 2    Role: D
 Ellenőrizze, hogy a szabályzatokat évente legalább egyszer, valamint jelentős fenyegetési környezetváltozások után felülvizsgálják és frissítik.
 #AC.2.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a szabályzatok minden AISVS kategóriát és az alkalmazandó szabályozási követelményeket lefedjék.

---

### AC.3 Szerepek és felelősségek az MI biztonságában

Állapítsanak meg világos felelősségi köröket az AI biztonságáért a szervezeten belül.

 #AC.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az AI biztonsági szerepek és felelősségek dokumentálva vannak-e.
 #AC.3.2    Level: 2    Role: D
 Ellenőrizze, hogy a felelős személyek rendelkeznek-e a megfelelő biztonsági szakértelemmel.
 #AC.3.3    Level: 3    Role: D/V
 Győződjön meg arról, hogy magas kockázatú MI rendszerekhez létre van hozva egy MI-etikai bizottság vagy irányító testület.

---

### AC.4 Etikai MI irányelvek betartatása

Biztosítani kell, hogy az MI rendszerek az elfogadott etikai elvek szerint működjenek.

 #AC.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy léteznek-e etikai irányelvek az MI fejlesztése és telepítése során.
 #AC.4.2    Level: 2    Role: D
 Ellenőrizze, hogy léteznek-e mechanizmusok az etikai megsértések észlelésére és jelentésére.
 #AC.4.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az üzembe helyezett mesterséges intelligencia rendszerek rendszeres etikai felülvizsgálata megtörténik-e.

---

### AC.5 Mesterséges intelligencia szabályozási megfelelőség ellenőrzése

Tartsa fenn az éberséget és a megfelelést a változó AI szabályozásokkal kapcsolatban.

 #AC.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy léteznek-e olyan folyamatok, amelyek azonosítják az alkalmazandó mesterséges intelligencia szabályozásokat.
 #AC.5.2    Level: 2    Role: D
 Ellenőrizze, hogy az összes szabályozási követelménynek való megfelelést értékelték-e.
 #AC.5.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a szabályozási változások időben kiváltják-e az AI rendszerek felülvizsgálatát és frissítését.

#### Hivatkozások

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## D. melléklet: Mesterséges Intelligenciával Támogatott Biztonságos Kódolás Irányítása és Ellenőrzése

### Célkitűzés

Ez a fejezet alapvető szervezeti ellenőrzéseket határoz meg az AI által támogatott kódolási eszközök biztonságos és hatékony használatához a szoftverfejlesztés során, biztosítva a biztonságot és nyomonkövethetőséget a szoftverfejlesztési életciklus (SDLC) során.

---

### AD.1 Mesterséges Intelligencia Segítségével Támogatott Biztonságos Kódolási Munkafolyamat

Integrálja az AI eszközöket a szervezet biztonságos szoftverfejlesztési életciklusába (SSDLC) anélkül, hogy gyengítené a meglévő biztonsági kapukat.

 #AD.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a dokumentált munkafolyamat leírja-e, mikor és hogyan generálhatják, refaktorálhatják vagy felülvizsgálhatják a kódot az AI eszközök.
 #AD.1.2    Level: 2    Role: D
 Ellenőrizze, hogy a munkafolyamat megfeleltethető-e az egyes SSDLC fázisoknak (tervezés, megvalósítás, kódellenőrzés, tesztelés, telepítés).
 #AD.1.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az AI által generált kódra vonatkozó metrikákat (pl. sebezhetőségi sűrűség, átlagosészlelési idő) összegyűjtik-e, és összehasonlítják-e az emberi kód alapvonalakkal.

---

### AD.2 AI eszközminősítés és fenyegetésmodellezés

Biztosítani kell, hogy az AI kódoló eszközöket a bevezetés előtt értékeljék biztonsági képességeik, kockázatuk és ellátási láncra gyakorolt hatásuk szempontjából.

 #AD.2.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az egyes MI-eszközök veszélymodelljei azonosítják-e a visszaélést, a modell-inverziót, az adatkisülést és a függőségi lánc kockázatait.
 #AD.2.2    Level: 2    Role: D
 Ellenőrizze, hogy az eszközértékelések tartalmazzák-e a helyi komponensek statikus/dinamikus elemzését, valamint a SaaS végpontok (TLS, hitelesítés/engedélyezés, naplózás) értékelését.
 #AD.2.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az értékelések egy elismert keretrendszer szerint történnek, és hogy nagyobb verzióváltások után újra elvégzik-e őket.

---

### AD.3 Biztonságos Parancs- és Kontextuskezelés

Megakadályozza a titkok, szabadalmi kódok és személyes adatok kiszivárgását AI-modellekhez szánt promptok vagy kontextusok létrehozásakor.

 #AD.3.1    Level: 1    Role: D/V
 Ellenőrizze, hogy az írásos iránymutatás tiltja-e a titkok, hitelesítő adatok vagy titkosított adatok beküldését a bemenetekben.
 #AD.3.2    Level: 2    Role: D
 Ellenőrizze, hogy a műszaki vezérlések (kliensoldali kivonás, jóváhagyott kontextusszűrők) automatikusan eltávolítják-e az érzékeny adathalmazokat.
 #AD.3.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a parancsok és válaszok tokenizálva vannak-e, titkosítva az átvitel során és a tároláskor, valamint hogy a megőrzési idők megfelelnek-e az adat­osztályozási szabálynak.

---

### AD.4 Az MI által generált kód érvényesítése

Az AI által generált kimenet által okozott sérülékenységek észlelése és kijavítása a kód egyesítése vagy telepítése előtt.

 #AD.4.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a mesterséges intelligencia által generált kódot mindig emberi kódátvizsgálatnak vetik alá.
 #AD.4.2    Level: 2    Role: D
 Ellenőrizze, hogy az automatizált szkennerek (SAST/IAST/DAST) minden, mesterséges intelligencia által generált kódot tartalmazó pull requesten lefutnak, és kritikus hibák esetén megakadályozzák az egyesítést.
 #AD.4.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a differenciális fuzz tesztelés vagy a tulajdonságalapú tesztek bizonyítják-e a biztonságkritikus viselkedéseket (pl. bemeneti érvényesítés, jogosultságkezelési logika).

---

### AD.5 A kódjavaslatok magyarázhatósága és visszakövethetősége

Biztosítsanak a könyvvizsgálóknak és fejlesztőknek betekintést abba, hogy miért tették a javaslatot és hogyan fejlődött az.

 #AD.5.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a prompt/válasz párok commit azonosítókkal vannak-e naplózva.
 #AD.5.2    Level: 2    Role: D
 Ellenőrizze, hogy a fejlesztők meg tudják-e jeleníteni a modell hivatkozásait (képzési részletek, dokumentáció), amelyek alátámasztják egy javaslatot.
 #AD.5.3    Level: 3    Role: D/V
 Ellenőrizze, hogy az értelmezhetőségi jelentések a tervezési dokumentumokkal együtt kerülnek tárolásra, és hivatkoznak rájuk a biztonsági felülvizsgálatok során, megfelelve az ISO/IEC 42001 követhetőségi elveinek.

---

### AD.6 Folyamatos visszacsatolás és modell finomhangolás

Javítsa a modell biztonsági teljesítményét az idő múlásával, miközben megakadályozza a negatív elmozdulást.

 #AD.6.1    Level: 1    Role: D/V
 Ellenőrizze, hogy a fejlesztők képesek-e jelölni a nem biztonságos vagy nem megfelelõ javaslatokat, és hogy ezek a jelölések nyomon követhetők-e.
 #AD.6.2    Level: 2    Role: D
 Ellenőrizze, hogy az összesített visszajelzések rendszeres finomhangolást vagy ellenőrzött biztonsági kódolási korpuszokkal (például OWASP Cheat Sheets) támogatott lekérdezés-alapú generálást tájékoztatnak-e.
 #AD.6.3    Level: 3    Role: D/V
 Ellenőrizze, hogy a zárt hurkú értékelő környezet minden finomhangolás után végrehajt regressziós teszteket; a biztonsági mutatóknak meg kell felelniük vagy meg kell haladniuk az előző alapértékeket a telepítés előtt.

---

#### Hivatkozások

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## E melléklet: Példák eszközökre és keretrendszerekre

### Célkitűzés

Ez a fejezet példákat nyújt olyan eszközökre és keretrendszerekre, amelyek támogathatják egy adott AISVS követelmény megvalósítását vagy teljesítését. Ezeket nem szabad az AISVS csapat vagy az OWASP GenAI Security Project ajánlásaként vagy támogatásaként értelmezni.

---

### AE.1 Képzési Adatkezelés és Elfogultságkezelés

Adat-elemzéshez, irányításhoz és elfogultságkezeléshez használt eszközök.

 #AE.1.1    Section: 1.1
 Adatkészlet kezelés eszközök: Az adatkészlet kezelésére szolgáló eszközök, mint például...
 #AE.1.2    Section: 1.2
 Titkosítás átvitel közben Használjon TLS-t HTTPS-alapú alkalmazásokhoz, olyan eszközökkel, mint az openSSL és a python`ssl`könyvtár.

---

### AE.2 Felhasználói adatbevitel érvényesítése

Eszközök a felhasználói bevitel kezelésére és érvényesítésére.

 #AE.2.1    Section: 2.1
 Prompt befecskendezés elleni védelem eszközei: Használjon védősín eszközöket, például az NVIDIA NeMo-t vagy a Guardrails AI-t.

---

## C1 Képzési Adatkezelés és Elfogultságkezelés

### C1.1 Képzési adatok származási helye

Tartson fenn ellenőrizhető készletet az összes adatállományról, fogadjon el csak megbízható forrásokat, és rögzítsen minden változást az ellenőrizhetőség érdekében.

 #1.1.1    Level: 1    Role: D/V
 Ellenőrizze, hogy naprakész készlet áll rendelkezésre minden edzési adatok forrásáról (eredet, kezelő/tulajdonos, licenc, gyűjtési módszer, tervezett felhasználási korlátozások és feldolgozási előzmények).

