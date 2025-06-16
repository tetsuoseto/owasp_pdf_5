# C5 Hozzáférés-vezérlés és azonosítás az MI komponensek és felhasználók számára

## Irányítási célkitűzés

Az AI rendszerek hatékony hozzáférés-ellenőrzése robusztus identitáskezelést, kontextusérzékeny engedélyezést és a nulla megbízáson alapuló elvek szerinti futásidejű végrehajtást igényel. Ezek az ellenőrzések biztosítják, hogy emberek, szolgáltatások és autonóm ügynökök csak az explicit módon megadott hatókörökön belül lévő modellekkel, adatokkal és számítási erőforrásokkal lépjenek kapcsolatba, folyamatos ellenőrzés és auditálási képességek mellett.

---

## C5.1 Identitáskezelés és hitelesítés

Állítsanak fel kriptográfiailag alátámasztott identitásokat minden entitás számára, többtényezős hitelesítéssel a jogosultságot igénylő műveletekhez.

|   #   | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Ellenőrizze, hogy minden emberi felhasználó és szolgáltatási főnév egy központosított vállalati identitásszolgáltatón (IdP) keresztül hitelesítse magát OIDC/SAML protokollok használatával, egyedi azonosító-token leképezésekkel (nincs megosztott fiók vagy hitelesítő adat). |   1   | D/V  |
| 5.1.2 | Ellenőrizze, hogy a magas kockázatú műveletek (modell telepítése, súlyok exportálása, képzési adatok elérése, éles konfigurációs változtatások) többtényezős hitelesítést vagy lépcsőzetes hitelesítést igényelnek-e munkamenet újbóli érvényesítésével.                         |   1   | D/V  |
| 5.1.3 | Ellenőrizze, hogy az új vezetők átesnek-e az NIST 800-63-3 IAL-2 vagy azzal egyenértékű szabványoknak megfelelő személyazonosság-igazoláson, mielőtt hozzáférést kapnának az éles rendszerhez.                                                                                   |   2   |  D   |
| 5.1.4 | Ellenőrizze, hogy az hozzáférés-áttekintések negyedévente megtörténnek-e, automatikus inaktív fiókok felismeréssel, hitelesítő adatok cseréjének érvényesítésével és eltávolítási munkafolyamatokkal.                                                                            |   2   |  V   |
| 5.1.5 | Ellenőrizze, hogy a federált MI-ügynökök aláírt JWT-igazolásokon keresztül hitelesítik magukat, amelyek maximális élettartama 24 óra, és tartalmazzák az eredet kriptográfiai bizonyítékát.                                                                                      |   3   | D/V  |

---

## C5.2 Erőforrás-engedélyezés és legkisebb jogosultság

Valósítson meg részletes hozzáférés-vezérlést minden MI-erőforrás esetében kifejezett engedélyezési modellekkel és auditnaplókkal.

|   #   | Description                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Ellenőrizze, hogy minden MI-erőforrás (adatkészletek, modellek, végpontok, vektorgyűjtemények, beágyazási indexek, számítási példányok) szerepalapú hozzáférés-ellenőrzést alkalmaz-e explicit engedélyezőlistákkal és alapértelmezett megtagadási szabályokkal. |   1   | D/V  |
| 5.2.2 | Ellenőrizze, hogy a legkisebb jogosultság elvei alapértelmezés szerint érvényesülnek-e a szolgáltatásfiókok esetében, kezdve az olvasási jogosultságokkal, és írják elő dokumentált üzleti indoklást az írási hozzáféréshez.                                     |   1   | D/V  |
| 5.2.3 | Ellenőrizze, hogy minden hozzáférés-vezérlési módosítás jóváhagyott változáskérelmekhez van-e kapcsolva, és változtathatatlanul naplózva van-e időbélyeggel, végrehajtó azonosítókkal, erőforrás-azonosítókkal és jogosultságváltozásokkal.                      |   1   |  V   |
| 5.2.4 | Ellenőrizze, hogy az adatosztályozási címkék (PII, PHI, export-ellenőrzött, tulajdonosi) automatikusan átterjednek-e a leszármaztatott erőforrásokra (beágyazások, prompt gyorsítótárak, modellkimenetek) következetes szabályzatvégrehajtással.                 |   2   |  D   |
| 5.2.5 | Ellenőrizze, hogy az illetéktelen hozzáférési kísérletek és jogosultság-kibővítési események valós idejű riasztásokat váltanak-e ki kontextuális metaadatokkal együtt az SIEM rendszerek felé 5 percen belül.                                                    |   2   | D/V  |

---

## C5.3 Dinamikus szabályzatértékelés

Telepítsen attribútumalapú hozzáférés-szabályozó (ABAC) motorokat kontextusfüggő jogosultságkezelési döntésekhez auditálási képességekkel.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Ellenőrizze, hogy az engedélyezési döntések külső, dedikált szabályzatmotorhoz (OPA, Cedar vagy egyenértékű) vannak-e delegálva, amely hitelesített API-kon keresztül érhető el, kriptográfiai integritásvédelemmel.                              |   1   | D/V  |
| 5.3.2 | Ellenőrizze, hogy a szabályzatok a dinamikus attribútumokat futásidőben értékelik-e ki, beleértve a felhasználó biztonsági szintjét, az erőforrás érzékenységi besorolását, a kérés kontextusát, a bérlői izolációt és az időbeli korlátozásokat. |   1   | D/V  |
| 5.3.3 | Ellenőrizze, hogy a szabályzatdefiníciók verziókezeltek, szakértői felülvizsgálaton estek át, és automatizált teszteléssel igazoltak a CI/CD folyamatokban a termelési bevezetés előtt.                                                           |   2   |  D   |
| 5.3.4 | Győződjön meg arról, hogy a szabályzatértékelés eredményei tartalmazzák a strukturált döntési indoklásokat, és továbbítódnak a SIEM rendszerekhez korrelációs elemzés és megfelelőségi jelentések céljából.                                       |   2   |  V   |
| 5.3.5 | Ellenőrizze, hogy a szabályzat gyorsítótárazási élettartamának (TTL) értékei ne haladják meg az 5 percet magas érzékenységű erőforrások esetében, illetve az 1 órát az érvénytelenítésre képes szabványos erőforrásoknál.                         |   3   | D/V  |

---

## C5.4 Lekérdezés idejű biztonsági érvényesítés

Valósítsa meg az adatbázis-réteg biztonsági vezérlőit kötelező szűréssel és sor-szintű biztonsági szabályzatokkal.

|   #   | Description                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Ellenőrizze, hogy minden vektoradatbázis- és SQL-lekérdezés tartalmazza-e a kötelező biztonsági szűrőket (bérlőazonosító, érzékenységi címkék, felhasználói jogosultság), amelyeket az adatbázis-kezelő motor szintjén érvényesítenek, nem az alkalmazáskódban. |   1   | D/V  |
| 5.4.2 | Ellenőrizze, hogy az egy sor szintű biztonsági (RLS) szabályzatok és a mező szintű maszkolás be vannak-e kapcsolva, valamint hogy a szabályzati öröklődés érvényesül-e az összes vektoralapú adatbázis, keresési index és képzési adatállomány esetében.        |   1   | D/V  |
| 5.4.3 | Ellenőrizze, hogy a sikertelen jogosultság-ellenőrzések megakadályozzák-e a "confused deputy támadásokat" azáltal, hogy azonnal megszakítják a lekérdezéseket, és explicit jogosultsági hibakódokat adnak vissza az üres eredményhalmazok visszaadása helyett.  |   2   |  D   |
| 5.4.4 | Ellenőrizze, hogy a házirend értékelési késleltetése folyamatosan monitorozva van-e, és hogy vannak-e automatizált riasztások az időtúllépési helyzetekre, amelyek engedélyezési megkerülést eredményezhetnek.                                                  |   2   |  V   |
| 5.4.5 | Ellenőrizze, hogy a lekérdezés újrapróbálási mechanizmusai újraértékelik-e az engedélyezési irányelveket a dinamikus jogosultságváltozások figyelembevételével az aktív felhasználói munkamenetek során.                                                        |   3   | D/V  |

---

## C5.5 Kimeneti szűrés és adatvesztés megelőzése

Alkalmazzon utófeldolgozási ellenőrzéseket az AI által generált tartalmak jogosulatlan adatkiszivárgásának megakadályozására.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Ellenőrizze, hogy a levezénylés utáni szűrőmechanizmusok átvizsgálják-e és kitakarítják-e az illetéktelenül kezelt személyes azonosító információkat (PII), a titkosított adatokat és a szellemi tulajdont tartalmazó adatokat, mielőtt azokat a kérelmezőknek továbbítanák. |   1   | D/V  |
| 5.5.2 | Ellenőrizze, hogy a modell kimeneteiben szereplő idézetek, hivatkozások és forrásmegjelölések megfelelnek-e a hívó jogosultságainak, és távolítsa el azokat, ha jogosulatlan hozzáférést észlel.                                                                             |   1   | D/V  |
| 5.5.3 | Ellenőrizze, hogy az output formátum korlátozásai (tisztított PDF-ek, metaadatoktól mentesített képek, jóváhagyott fájltípusok) érvényesítésre kerülnek-e a felhasználói jogosultsági szintek és az adat-osztályozások alapján.                                              |   2   |  D   |
| 5.5.4 | Ellenőrizze, hogy a redakciós algoritmusok determinisztikusak, verziókövetettek legyenek, és audit naplókat vezessenek a megfelelőségi vizsgálatok és a forenzikus elemzés támogatására.                                                                                     |   2   |  V   |
| 5.5.5 | Ellenőrizze, hogy a magas kockázatú eltávolítási események adaptív naplókat generálnak-e, amelyek tartalmazzák az eredeti tartalom kriptográfiai kivonatait a forenzikus visszakereséshez anélkül, hogy adatokat tennének ki.                                                |   3   |  V   |

---

## C5.6 Többbérlős elszigetelés

Biztosítsa a kriptográfiai és logikai elkülönítést a bérlők között a megosztott MI infrastruktúrában.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Ellenőrizze, hogy a memóriahelyek, beágyazott tárolók, gyorsítótár-bejegyzések és ideiglenes fájlok az egyes bérlők szerint nevetér alapján elkülönítve vannak-e, és biztosított-e a biztonságos törlés a bérlő törlése vagy a munkamenet megszakítása esetén. |   1   | D/V  |
| 5.6.2 | Győződjön meg arról, hogy minden API-kérés tartalmaz egy hitelesített bérlőazonosítót, amely kriptográfiailag érvényesítve van a munkamenet kontextusa és a felhasználói jogosultságok alapján.                                                                |   1   | D/V  |
| 5.6.3 | Ellenőrizze, hogy a hálózati szabályzatok alapértelmezett megtagadó (default-deny) szabályokat valósítanak-e meg a bérlők közötti kommunikációban a szolgáltatáshálókban (service mesh) és a konténer-orchesztrációs platformokon.                             |   2   |  D   |
| 5.6.4 | Ellenőrizze, hogy az titkosítási kulcsok egyediek-e bérlőnként, ügyfél által kezelt kulcs (CMK) támogatással, valamint a bérlői adat-tárolók közötti kriptográfiai izolációval.                                                                                |   3   |  D   |

---

## C5.7 Autonóm ügynök engedélyezése

AI-ügynökök és autonóm rendszerek vezérlési jogosultságai körülhatárolt képességtokenek és folyamatos engedélyezés révén.

|   #   | Description                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.7.1 | Ellenőrizze, hogy az autonóm ügynökök megkapják-e a körülhatárolt képességtokeneket, amelyek egyértelműen felsorolják az engedélyezett műveleteket, elérhető erőforrásokat, időbeli korlátokat és működési megszorításokat.                            |   1   | D/V  |
| 5.7.2 | Ellenőrizze, hogy a magas kockázatú képességek (fájlrendszer-hozzáférés, kódvégrehajtás, külső API hívások, pénzügyi tranzakciók) alapértelmezés szerint le vannak-e tiltva, és aktiválásukhoz kifejezett engedélyek szükségesek-e üzleti indoklással. |   1   | D/V  |
| 5.7.3 | Ellenőrizze, hogy a képesség tokenek felhasználói munkamenetekhez kötöttek-e, tartalmaznak-e kriptográfiai integritásvédelmet, és győződjön meg arról, hogy nem tárolhatók vagy használhatók újra offline helyzetekben.                                |   2   |  D   |
| 5.7.4 | Ellenőrizze, hogy az ágens által kezdeményezett műveletek másodlagos engedélyezésen mennek keresztül az ABAC szabálymotor segítségével, teljes kontextusértékeléssel és audit naplózással.                                                             |   2   |  V   |
| 5.7.5 | Ellenőrizze, hogy az ügynökhiba állapotok és a kivételkezelés tartalmazzák-e a képességi hatókör információkat az eseményelemzés és a forenzikus vizsgálat támogatásához.                                                                              |   3   |  V   |

---

## Hivatkozások

### Szabványok és keretrendszerek

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Megvalósítási Útmutatók

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Mesterséges Intelligencia-specifikus Biztonság

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

