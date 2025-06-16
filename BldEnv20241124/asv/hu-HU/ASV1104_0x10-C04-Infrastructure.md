# C4 infrastruktúra, konfiguráció és telepítési biztonság

## Irányítási célkitűzés

Az AI infrastruktúrát meg kell erősíteni a jogosultságnövelés, az ellátási lánc manipulációja és az oldalirányú mozgás ellen biztonságos konfiguráció, futásidejű elkülönítés, megbízható telepítési folyamatok és átfogó megfigyelés révén. Csak a jogosult, ellenőrzött infrastruktúraelemek és konfigurációk juthatnak el a termelési környezetbe olyan ellenőrzött folyamatokon keresztül, amelyek fenntartják a biztonságot, integritást és auditálhatóságot.

Alapvető biztonsági cél: Csak kriptográfiai aláírással rendelkező, sebezhetőség-ellenőrzött infrastruktúraelemek juthatnak el a gyártási környezetbe automatizált érvényesítési folyamatokon keresztül, amelyek érvényesítik a biztonsági szabályzatokat és megőrzik a megváltoztathatatlan audit nyomvonalakat.

---

## C4.1 Futásidejű környezet izolációja

Megakadályozza a konténerből való kijutást és a jogosultságkiterjesztést kernel-szintű izolációs primitívek és kötelező hozzáférés-vezérlés alkalmazásával.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Ellenőrizze, hogy minden AI-konténer eltávolítja-e az összes Linux képességet, kivéve a CAP_SETUID, CAP_SETGID és a biztonsági alapvonalakban dokumentált, kifejezetten szükséges képességeket.                                                               |   1   | D/V  |
| 4.1.2 | Ellenőrizze, hogy a seccomp profilok minden rendszerhívást blokkolnak, kivéve az előzetesen jóváhagyott engedélyezőlistákon szereplőket, és hogy a megsértések a konténer leállítását és biztonsági riasztások generálását eredményezik-e.                    |   1   | D/V  |
| 4.1.3 | Ellenőrizze, hogy az MI-munkaterhelések olvasható gyökérfájlrendszerrel, tmpfs ideiglenes adatokhoz, valamint nevük szerint hivatkozott kötetekkel futnak-e tartós adatok esetén, és hogy az noexec csatolási opciók érvényesítve vannak-e.                   |   2   | D/V  |
| 4.1.4 | Ellenőrizze, hogy az eBPF-alapú futásidejű megfigyelés (Falco, Tetragon vagy azzal egyenértékű) felismeri-e a jogosultságnövelési kísérleteket, és automatikusan leállítja-e a szabályszegő folyamatokat a szervezeti válaszidő követelményeinek megfelelően. |   2   | D/V  |
| 4.1.5 | Ellenőrizze, hogy a magas kockázatú AI munkaterhelések hardveralapú elkülönített környezetekben futnak-e (Intel TXT, AMD SVM vagy dedikált bare-metal csomópontok), és rendelkeznek azonosítási megerősítéssel.                                               |   3   | D/V  |

---

## C4.2 Biztonságos építési és telepítési csővezetékek

Biztosítsa a kriptográfiai integritást és az ellátási lánc biztonságát reprodukálható buildelések és aláírt műtárgyak segítségével.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.2.1 | Ellenőrizze, hogy az infrastruktúra-kód minden commit esetén eszközökkel (tfsec, Checkov vagy Terrascan) legyen átvizsgálva, és blokkolja az egyesítéseket KRITIKUS vagy MAGAS súlyosságú hibák esetén.                                    |   1   | D/V  |
| 4.2.2 | Ellenőrizze, hogy a konténerépítések reprodukálhatók-e azonos SHA256 hashekkel az építések között, és hozza létre a Sigstore által aláírt, SLSA 3. szintű eredettörténeti igazolásokat.                                                    |   1   | D/V  |
| 4.2.3 | Ellenőrizze, hogy a tárolókép tartalmazza-e a CycloneDX vagy SPDX SBOM-okat, és a Cosign-nal alá legyen-e írva a regiszterbe történő feltöltés előtt, az aláíratlan képeket pedig a telepítésnél elutasítja.                               |   2   | D/V  |
| 4.2.4 | Ellenőrizze, hogy a CI/CD pipeline-ok HashiCorp Vault, AWS IAM-szerepkörök vagy Azure Managed Identity OIDC tokenjeit használják-e, amelyek élettartama nem haladja meg a szervezeti biztonsági előírásokban meghatározott határértékeket. |   2   | D/V  |
| 4.2.5 | Ellenőrizze, hogy a Cosign aláírások és az SLSA eredetiség hitelesítése megtörténik-e a telepítési folyamat során a konténer futtatása előtt, és hogy a hitelesítési hibák a telepítés sikertelenségéhez vezetnek-e.                       |   2   | D/V  |
| 4.2.6 | Ellenőrizze, hogy az építési környezetek ideiglenes konténerekben vagy virtuális gépekben futnak-e, amelyek nem tartalmaznak tartós tárolót, és hálózati izolációval rendelkeznek a termelési VPC-ktől.                                    |   2   | D/V  |

---

## C4.3 Hálózati biztonság és hozzáférés-vezérlés

Valósítson meg nullatérelv alapú hálózatot alapértelmezett megtagadási szabályokkal és titkosított kommunikációval.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Ellenőrizze, hogy a Kubernetes NetworkPolicy-k vagy bármilyen megfelelő megoldás alapértelmezett tiltást alkalmaz-e a bejövő/kimenő forgalomra, explicit engedélyezési szabályokkal a szükséges portokra (443, 8080 stb.).          |   1   | D/V  |
| 4.3.2 | Ellenőrizze, hogy az SSH (22-es port), az RDP (3389-es port) és a felhő metaadat végpontok (169.254.169.254) le vannak-e tiltva vagy tanúsítvány-alapú hitelesítést igényelnek-e.                                                   |   1   | D/V  |
| 4.3.3 | Ellenőrizze, hogy a kimenő forgalom HTTP/HTTPS proxykon (például Squid, Istio vagy felhő NAT átjárók) keresztül szűrve van-e, domén engedélyező listákkal, és a letiltott kérések naplózásra kerülnek-e.                            |   2   | D/V  |
| 4.3.4 | Ellenőrizze, hogy a szolgáltatások közötti kommunikáció kölcsönös TLS-t használ-e, a tanúsítványokat a szervezeti szabályzat szerint forgatják, és a tanúsítványok érvényesítése érvényben van-e (nincs kihagyás-ellenőrzés jelző). |   2   | D/V  |
| 4.3.5 | Ellenőrizze, hogy az MI infrastruktúra kizárólag dedikált VPC-kben/VNet-ekben működik, közvetlen internet-hozzáférés nélkül, és kizárólag NAT átjárókon vagy bastion hosztokon keresztül kommunikál.                                |   2   | D/V  |

---

## C4.4 Titkok és kriptográfiai kulcskezelés

Védd a hitelesítő adatokat hardveralapú tárolással és automatikus cserével, nulla bizalmi hozzáférés mellett.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Ellenőrizze, hogy a titkok a HashiCorp Vaultban, az AWS Secrets Managerben, az Azure Key Vaultban vagy a Google Secret Managerben vannak-e tárolva, titkosítva AES-256-os állományi titkosítással.                              |   1   | D/V  |
| 4.4.2 | Ellenőrizze, hogy a kriptográfiai kulcsok FIPS 140-2 2. szintű HSM-ekben (AWS CloudHSM, Azure Dedicated HSM) vannak-e generálva, és hogy a kulcsforgatás megfelel-e a szervezeti kriptográfiai szabványnak.                     |   1   | D/V  |
| 4.4.3 | Ellenőrizze, hogy a titkok forgatása automatizált-e nulla leállási idővel történő telepítéssel, és azonnali forgatás történik-e személyzeti változások vagy biztonsági események kiváltására.                                   |   2   | D/V  |
| 4.4.4 | Ellenőrizze, hogy a konténerképeket olyan eszközökkel (GitLeaks, TruffleHog vagy detect-secrets) vizsgálják-e, amelyek megakadályozzák az API-kulcsokat, jelszavakat vagy tanúsítványokat tartalmazó build-ek elkészítését.     |   2   | D/V  |
| 4.4.5 | Ellenőrizze, hogy a gyártási titkos hozzáférés többfaktoros hitelesítést (MFA) igényel-e hardvertokenekkel (YubiKey, FIDO2), és hogy azt változtathatatlan auditnaplók rögzítik-e felhasználói azonosítókkal és időbélyegekkel. |   2   | D/V  |
| 4.4.6 | Ellenőrizze, hogy a titkok Kubernetes titkok, csatolt kötetek vagy init konténerek útján kerülnek-e beillesztésre, és győződjön meg arról, hogy a titkok soha nem kerülnek környezeti változókba vagy képekbe ágyazásra.        |   2   | D/V  |

---

## C4.5 AI Munkaterhelés Homokozózás és Érvényesítés

Izolálja a nem megbízható MI-modelleket biztonságos homokozókban átfogó viselkedéselemzéssel.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Ellenőrizze, hogy a külső MI-modellek gVisorban, microVM-ekben (például Firecracker, CrossVM) vagy Docker konténerekben futnak-e --security-opt=no-new-privileges és --read-only zászlókkal.                      |   1   | D/V  |
| 4.5.2 | Ellenőrizze, hogy a homokozó környezeteknek nincs hálózati kapcsolata (--network=none), vagy csak localhost hozzáférése van, és minden külső kérést iptables szabályok blokkolnak.                                |   1   | D/V  |
| 4.5.3 | Ellenőrizze, hogy az MI-modell érvényesítése tartalmazza-e az automatizált red-team tesztelést, amely szervezetileg meghatározott tesztlefedettséggel és viselkedéselemzéssel történik a hátsóajtó detektálására. |   2   | D/V  |
| 4.5.4 | Ellenőrizze, hogy mielőtt egy MI-modellt élesítésre bocsátanak, a homokozós eredményeit jogosított biztonsági személyzet kriptográfiailag aláírja és megváltoztathatatlan audit naplókban tárolja.                |   2   | D/V  |
| 4.5.5 | Ellenőrizze, hogy az elszigetelt környezetek értékelések között megsemmisülnek és aranykép alapján újból létrejönnek, teljes fájlrendszer és memória tisztítással.                                                |   2   | D/V  |

---

## C4.6 Infrastruktúra biztonsági megfigyelés

Folyamatosan vizsgálja és figyelje az infrastruktúrát automatizált javítással és valós idejű riasztással.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Ellenőrizze, hogy a konténerképeket a szervezeti ütemtervek szerint átvizsgálják-e, ahol a KRITIKUS sebezhetőségek a szervezeti kockázati küszöbértékek alapján megakadályozzák a telepítést.                                      |   1   | D/V  |
| 4.6.2 | Ellenőrizze, hogy az infrastruktúra megfelel-e a CIS Benchmarkoknak vagy a NIST 800-53 szabályozásoknak, az szervezet által meghatározott megfelelőségi küszöbökkel és az automatikus javítással a sikertelen ellenőrzések esetén. |   1   | D/V  |
| 4.6.3 | Ellenőrizze, hogy a MAGAS súlyosságú sérülékenységek a szervezeti kockázatkezelési ütemtervek szerint javítva legyenek, és legyenek vészhelyzeti eljárások az aktívan kihasznált CVE-k esetére.                                    |   2   | D/V  |
| 4.6.4 | Ellenőrizze, hogy a biztonsági riasztások integrálódnak-e a SIEM platformokkal (Splunk, Elastic vagy Sentinel) CEF vagy STIX/TAXII formátumok használatával, automatikus bővítéssel.                                               |   2   |  V   |
| 4.6.5 | Ellenőrizze, hogy az infrastruktúra-mutatók ki legyenek exportálva a megfigyelőrendszerekbe (Prometheus, DataDog) SLA műszerfalakkal és vezetői jelentésekkel.                                                                     |   3   |  V   |
| 4.6.6 | Ellenőrizze, hogy a konfigurációs eltérés észlelve van-e eszközök (Chef InSpec, AWS Config) segítségével a szervezeti megfigyelési követelmények szerint, automatikus visszaállítással az illetéktelen változtatások esetén.       |   2   | D/V  |

---

## C4.7 AI infrastruktúra erőforrás-menedzsment

Megakadályozza az erőforrás-kimerülési támadásokat, és biztosítja az erőforrások méltányos elosztását kvóták és megfigyelés révén.

|   #   | Description                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Ellenőrizze, hogy a GPU/TPU kihasználtságát figyelik-e, riasztások váltanak-e ki a szervezeti szinten meghatározott küszöbértékeknél, és automatikus skálázás vagy terheléselosztás történik-e a kapacitáskezelési irányelvek alapján.                    |   1   | D/V  |
| 4.7.2 | Ellenőrizze, hogy az AI munkaterhelés mérőszámai (inferencia késleltetés, áteresztőképesség, hibaarányok) a szervezeti megfigyelési követelmények szerint kerülnek-e összegyűjtésre, és összefüggésbe vannak-e hozva az infrastruktúra kihasználtságával. |   1   | D/V  |
| 4.7.3 | Ellenőrizze, hogy a Kubernetes ResourceQuotas vagy azonos funkcionalitású megoldások korlátozzák-e az egyes munkaterheléseket a szervezeti erőforrás-elosztási irányelvek szerint, kitartó (hard) korlátok érvényesítésével.                              |   2   | D/V  |
| 4.7.4 | Ellenőrizze, hogy a költségfigyelés nyomon követi-e a kiadásokat munkaterhelésenként/bérlőnként, figyelmeztetésekkel az szervezeti költségvetési küszöbök alapján és automatikus ellenőrzésekkel a költségvetés túllépése esetén.                         |   2   |  V   |
| 4.7.5 | Ellenőrizze, hogy a kapacitástervezés szervezeti szinten meghatározott előrejelzési időszakokkal és a keresletminták alapján automatizált erőforrás-ellátással történik-e, történelmi adatok felhasználásával.                                            |   3   |  V   |
| 4.7.6 | Ellenőrizze, hogy az erőforrás-kimerülés kiváltja-e a kapcsolóvédelmeket a szervezeti válasz követelményeinek megfelelően, ideértve a kapacitáspolitikákon alapuló sebességkorlátozást és a munkaterhelés elkülönítését.                                  |   2   | D/V  |

---

## C4.8 Környezetelkülönítés és előmeneteli szabályozások

Szigorú környezeti határokat érvényesítsen automatizált előléptetési kapukkal és biztonsági ellenőrzésekkel.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Ellenőrizze, hogy a fejlesztői, teszt- és termelési környezetek külön VPC-kben/VNet-ekben futnak-e, megosztott IAM szerepkörök, biztonsági csoportok vagy hálózati kapcsolatok nélkül.                                                                   |   1   | D/V  |
| 4.8.2 | Ellenőrizze, hogy a környezeti előléptetéshez az szervezet által meghatározott, jogosult személyek jóváhagyása szükséges-e kriptográfiai aláírásokkal és megváltoztathatatlan audit nyomvonalakkal.                                                      |   1   | D/V  |
| 4.8.3 | Ellenőrizze, hogy a termelési környezetek blokkolják-e az SSH-hozzáférést, letiltják-e a hibakeresési végpontokat, és előírják-e a változtatási kérelmeket szervezeti előzetes értesítési követelményekkel, kivéve a vészhelyzeteket.                    |   2   | D/V  |
| 4.8.4 | Ellenőrizze, hogy az infrastruktúra-kódként történő változtatások átesnek-e társ általi felülvizsgálaton automatikus teszteléssel és biztonsági vizsgálattal a fő ágba történő egyesítés előtt.                                                          |   2   | D/V  |
| 4.8.5 | Ellenőrizze, hogy a nem termelési adatok anonimizálva vannak-e a szervezeti adatvédelmi követelmények szerint, szintetikus adatgenerálással vagy teljes adatmaszkolással, valamint a személyes azonosító információk (PII) eltávolításának igazolásával. |   2   | D/V  |
| 4.8.6 | Ellenőrizze, hogy a promóciós kapuk tartalmazzák-e az automatizált biztonsági teszteket (SAST, DAST, konténeres szkennelés), amelyeknél a jóváhagyáshoz nulla KRITIKUS hibát kell találnia.                                                              |   2   | D/V  |

---

## C4.9 Infrastruktúra Biztonsági Mentése és Helyreállítása

Biztosítsa az infrastruktúra ellenálló képességét automatizált biztonsági mentésekkel, tesztelt helyreállítási eljárásokkal és katasztrófa utáni helyreállítási képességekkel.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Ellenőrizze, hogy az infrastruktúra konfigurációk az szervezeti biztonsági mentési ütemtervek szerint le vannak-e mentve földrajzilag elkülönített régiókban a 3-2-1 biztonsági mentési stratégia alkalmazásával.           |   1   | D/V  |
| 4.9.2 | Ellenőrizze, hogy a biztonsági mentési rendszerek elszigetelt hálózatokban működnek-e, külön hitelesítő adatokkal és levegőrekeszes tárolóval a zsarolóvírus elleni védelem érdekében.                                      |   2   | D/V  |
| 4.9.3 | Ellenőrizze, hogy a helyreállítási eljárásokat automatizált teszteléssel tesztelik és érvényesítik a szervezeti ütemtervek szerint, az RTO és RPO célokkal összhangban, amelyek megfelelnek a szervezeti követelményeknek.  |   2   |  V   |
| 4.9.4 | Ellenőrizze, hogy a katasztrófa utáni helyreállítás tartalmaz-e AI-specifikus működési utasításokat, beleértve a modell súlyainak visszaállítását, a GPU klaszter újjáépítését és a szolgáltatásfüggőségek feltérképezését. |   3   |  V   |

---

## C4.10 Infrastruktúra megfelelőség és irányítás

Fenntartsa a szabályozási megfelelést folyamatos értékelés, dokumentálás és automatizált ellenőrzések révén.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Ellenőrizze, hogy az infrastruktúra megfelelőségét az szervezeti ütemtervek szerint értékelik-e SOC 2, ISO 27001 vagy FedRAMP irányelvek alapján automatikus bizonyítékgyűjtéssel.                             |   2   | D/V  |
| 4.10.2 | Ellenőrizze, hogy az infrastruktúra dokumentációja tartalmaz-e hálózati diagramokat, adatfolyam térképeket és fenyegetésmodelleket, amelyek az szervezeti változáskezelési követelmények szerint frissítettek. |   2   |  V   |
| 4.10.3 | Ellenőrizze, hogy az infrastrukturális változtatások automatizált megfelelőségi hatáselemzésen mennek keresztül, magas kockázatú módosítások esetén pedig szabályozói jóváhagyási munkafolyamatokkal.          |   3   | D/V  |

---

## C4.11 Mesterséges Intelligencia Hardverbiztonság

Biztonságos AI-specifikus hardverkomponensek, beleértve a GPU-kat, TPU-kat és speciális AI-gyorsítókat.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Ellenőrizze, hogy az AI gyorsító firmware-je (GPU BIOS, TPU firmware) kriptográfiai aláírásokkal van-e hitelesítve, és a szervezeti frissítéskezelési idővonalaknak megfelelően frissítik-e.                   |   2   | D/V  |
| 4.11.2 | Ellenőrizze, hogy a munkaterhelés végrehajtása előtt az MI gyorsító integritása hardveres igazolással validálva van-e TPM 2.0, Intel TXT vagy AMD SVM használatával.                                           |   2   | D/V  |
| 4.11.3 | Ellenőrizze, hogy a GPU memória elkülönített a munkaterhelések között SR-IOV, MIG (többszörös példány GPU) vagy egyenértékű hardverpartícionálás használatával, ahol a memóriát tisztítják a feladatok között. |   2   | D/V  |
| 4.11.4 | Ellenőrizze, hogy az AI hardver ellátási lánc tartalmazza-e az eredetet igazoló gyártói tanúsítványokat és a sérülésbiztos csomagolás érvényesítését.                                                          |   3   |  V   |
| 4.11.5 | Ellenőrizze, hogy a hardverbiztonsági modulok (HSM-ek) FIPS 140-2 Level 3 vagy Common Criteria EAL4+ tanúsítvánnyal védik-e a mesterséges intelligencia modell súlyait és a kriptográfiai kulcsokat.           |   3   | D/V  |

---

## C4.12 Perifériás és elosztott MI infrastruktúra

Biztonságos elosztott mesterséges intelligencia telepítések, beleértve az edge computingot, a federált tanulást és a többhelyszínes architektúrákat.

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Ellenőrizze, hogy az edge AI eszközök kölcsönös TLS segítségével hitelesítik-e magukat a központi infrastruktúrához, az eszköztanúsítványokat pedig az szervezeti tanúsítványkezelési irányelv szerint forgatják. |   2   | D/V  |
| 4.12.2 | Ellenőrizze, hogy az élő eszközök biztonságos indítást valósítanak meg ellenőrzött aláírásokkal és visszafordítás elleni védelemmel, megakadályozva ezzel a firmware visszaminősítési támadásokat.                |   2   | D/V  |
| 4.12.3 | Ellenőrizze, hogy az elosztott MI koordináció bizánci hibatűrő konszenzus algoritmusokat alkalmaz-e résztvevő-ellenőrzéssel és rosszindulatú csomópontok felismerésével.                                          |   3   | D/V  |
| 4.12.4 | Ellenőrizze, hogy az élőhálózati és felhő közötti kommunikáció tartalmazza-e a sávszélesség korlátozását, adat tömörítést, valamint az offline működési képességeket biztonságos helyi tárolással.                |   3   | D/V  |

---

## C4.13 Többfelhős és hibrid infrastruktúra biztonsága

Biztonságos mesterséges intelligencia munkafolyamatok több felhőszolgáltatónál és hibrid felhő-helyszíni telepítéseknél.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Ellenőrizze, hogy a többfelhős MI-telepítések felhőfüggetlen azonosítási szövetséget (OIDC, SAML) használnak-e, központosított házirendkezeléssel a szolgáltatók között.                                       |   2   | D/V  |
| 4.13.2 | Ellenőrizze, hogy a felhők közötti adatátvitel végpontok közötti titkosítást használ-e az ügyfél által kezelt kulcsokkal, és hogy az adathelyzet-szabályozások az adott joghatóság szerint érvényesülnek-e.    |   2   | D/V  |
| 4.13.3 | Ellenőrizze, hogy a hibrid felhőalapú MI munkaterhelések következetes biztonsági szabályzatokat valósítanak-e meg a helyszíni és felhőalapú környezetek között, egységes monitorozással és riasztással.        |   2   | D/V  |
| 4.13.4 | Ellenőrizze, hogy a felhőszolgáltató zárolásának megelőzése magában foglalja-e a hordozható infrastruktúra-kódot, a szabványosított API-kat és az adat-exportálási képességeket formátumátalakító eszközökkel. |   3   |  V   |
| 4.13.5 | Ellenőrizze, hogy a többfelhős költségoptimalizáció tartalmazza-e az erőforrások szétszóródását megakadályozó biztonsági vezérlőket, valamint az illetéktelen felhők közötti adatforgalmi díjak megelőzését.   |   3   |  V   |

---

## C4.14 Infrastruktúra automatizálás és GitOps biztonság

Biztonságos infrastruktúra automatizálási folyamatok és GitOps munkafolyamatok az MI infrastruktúra kezeléséhez.

|   #    | Description                                                                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Ellenőrizze, hogy a GitOps tárolók megkövetelik-e az aláírt commitokat GPG kulcsokkal, valamint ággal védelmi szabályokat alkalmaznak, amelyek megakadályozzák a közvetlen pushokat a fő ágakra.                                                |   2   | D/V  |
| 4.14.2 | Ellenőrizze, hogy az infrastruktúra-automatizálás tartalmaz-e eltérésészlelést automatikus javítással és visszagörgetési képességekkel, amelyek a szervezeti válaszkövetelményeknek megfelelően aktiválódnak jogosulatlan változtatások esetén. |   2   | D/V  |
| 4.14.3 | Ellenőrizze, hogy az automatizált infrastruktúra-kiépítés tartalmazza-e a biztonsági házirend érvényesítését, és blokkolja-e a telepítést a nem megfelelő konfigurációk esetén.                                                                 |   2   | D/V  |
| 4.14.4 | Ellenőrizze, hogy az infrastruktúra-automatizálási titkokat külső titkászkezelő rendszereken (External Secrets Operator, Bank-Vaults) keresztül kezelik-e automatikus forgatással.                                                              |   2   | D/V  |
| 4.14.5 | Ellenőrizze, hogy az önjavító infrastruktúra tartalmazza-e a biztonsági események korrelációját automatizált incidenskezeléssel és az érintettek értesítési munkafolyamataival.                                                                 |   3   |  V   |

---

## C4.15 Kvantumrezisztens infrastruktúra biztonság

Készítse elő a mesterséges intelligencia infrastruktúráját a kvantumszámítási fenyegetésekre poszt-kvantum kriptográfia és kvantumbiztos protokollok alkalmazásával.

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Ellenőrizze, hogy az MI infrastruktúra a NIST által jóváhagyott poszt-kvantum kriptográfiai algoritmusokat (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) alkalmazza a kulcscsere és digitális aláírások terén. |   3   | D/V  |
| 4.15.2 | Ellenőrizze, hogy a kvantumkulcs-elosztó (QKD) rendszerek megvalósításra kerülnek-e magas biztonságú AI kommunikációkhoz kvantumbiztos kulcskezelési protokollokkal.                                            |   3   | D/V  |
| 4.15.3 | Ellenőrizze, hogy a kriptográfiai agilitási keretrendszerek lehetővé teszik-e az új poszt-kvantum algoritmusokra való gyors áttérést automatizált tanúsítvány- és kulcscserével.                                |   3   | D/V  |
| 4.15.4 | Ellenőrizze, hogy a kvantum fenyegetésmodellezés értékeli-e az AI infrastruktúra kvantumtámadásokkal szembeni sérülékenységét dokumentált migrációs ütemtervekkel és kockázatértékelésekkel.                    |   3   |  V   |
| 4.15.5 | Ellenőrizze, hogy a hibrid klasszikus-quantum kriptográfiai rendszerek biztosítanak-e védelmet több rétegben a kvantumos átmeneti időszak alatt, teljesítményfigyeléssel együtt.                                |   3   | D/V  |

---

## C4.16 Bizalmas számítás és biztonságos zónák

Védd meg a mesterséges intelligencia munkaterheléseit és a modell súlyait hardveralapú megbízható végrehajtási környezetek és titkos számítási technológiák segítségével.

|   #    | Description                                                                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Ellenőrizze, hogy a bizalmas AI modellek az Intel SGX környezetben, az AMD SEV-SNP-ben vagy az ARM TrustZone-ban futnak-e titkosított memóriával és hitelesítés-ellenőrzéssel.                                                                   |   3   | D/V  |
| 4.16.2 | Ellenőrizze, hogy a bizalmas tárolók (Kata Containers, gVisor bizalmas számítással) elkülönítik-e az AI munkafolyamatokat hardveresen érvényesített memória titkosítással.                                                                       |   3   | D/V  |
| 4.16.3 | Ellenőrizze, hogy a távoli igazolás érvényesíti-e az enclave integritását az AI modellek betöltése előtt, kriptográfiai bizonyítékkal az végrehajtási környezet hitelességéről.                                                                  |   3   | D/V  |
| 4.16.4 | Ellenőrizze, hogy a bizalmas AI-inferenciaszolgáltatások megakadályozzák-e a modellkivonást titkosított számításon keresztül zárt modell-súlyokkal és védett végrehajtással.                                                                     |   3   | D/V  |
| 4.16.5 | Ellenőrizze, hogy a megbízható végrehajtási környezet (Trusted Execution Environment) koordinációja kezeli-e a biztonságos zóna (secure enclave) életciklusát távoli igazolással (remote attestation) és titkosított kommunikációs csatornákkal. |   3   | D/V  |
| 4.16.6 | Ellenőrizze, hogy a biztonságos többoldalú számítás (SMPC) lehetővé teszi-e az együttműködő mesterséges intelligencia képzést anélkül, hogy kockáztatná az egyéni adatkészletek vagy modellparaméterek felfedését.                               |   3   | D/V  |

---

## C4.17 Nulla Tudású Infrastruktúra

Valósítson meg nulla-tudás bizonyítási rendszereket az adatvédelmi szempontból biztonságos mesterséges intelligencia ellenőrzéséhez és hitelesítéséhez, anélkül, hogy érzékeny információkat fedne fel.

|   #    | Description                                                                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Ellenőrizze, hogy a nulla tudású igazolások (ZK-SNARK-ok, ZK-STARK-ok) igazolják-e a mesterséges intelligencia modell integritását és a képzési eredetet anélkül, hogy felfednék a modell súlyait vagy a képzési adatokat.              |   3   | D/V  |
| 4.17.2 | Ellenőrizze, hogy a ZK-alapú hitelesítési rendszerek lehetővé teszik-e a felhasználók adatvédelmi szempontból biztonságos ellenőrzését az AI szolgáltatásokhoz anélkül, hogy felfednék a személyazonossággal kapcsolatos információkat. |   3   | D/V  |
| 4.17.3 | Ellenőrizze, hogy a privát halmazmetszet (PSI) protokollok lehetővé teszik-e a biztonságos adat-egyeztetést a federált mesterséges intelligencia számára anélkül, hogy egyéni adattáblákat tennének láthatóvá.                          |   3   | D/V  |
| 4.17.4 | Ellenőrizze, hogy a zéró-tudású gépi tanulási (ZKML) rendszerek lehetővé teszik-e az ellenőrizhető MI következtetéseket kriptográfiai bizonyítékkal a helyes számításról.                                                               |   3   | D/V  |
| 4.17.5 | Ellenőrizze, hogy a ZK-rollupok biztosítanak-e skálázható, adatvédelmet megőrző AI tranzakciófeldolgozást kötegelt hitelesítéssel és csökkentett számítási terheléssel.                                                                 |   3   | D/V  |

---

## C4.18 Oldalcsatorna-támadás megelőzése

Védje az MI infrastruktúrát az időzítésen, áramfogyasztáson, elektromágneses és gyorsítótár alapú oldalsó csatornás támadásoktól, amelyek érzékeny információkat szivárogtathatnak ki.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Ellenőrizze, hogy a mesterséges intelligencia következtetési ideje állandó időalgoritmusokkal és kitöltéssel normalizált-e az időalapú modellkinyerési támadások megelőzése érdekében.    |   3   | D/V  |
| 4.18.2 | Ellenőrizze, hogy a teljesítményelemzéssel szembeni védelem tartalmazza-e a zajinjektálást, a tápkábel szűrését és a véletlenszerű végrehajtási mintákat az AI hardver esetében.          |   3   | D/V  |
| 4.18.3 | Ellenőrizze, hogy a cache-alapú mellékcsatornás támadások elleni védelem cache-particionálást, randomizálást és flush utasításokat használ-e az információszivárgás megelőzése érdekében. |   3   | D/V  |
| 4.18.4 | Ellenőrizze, hogy az elektromágneses kisugárzás elleni védelem tartalmazza-e a árnyékolást, jel szűrést és véletlenszerűsített feldolgozást a TEMPEST-stílusú támadások megelőzésére.     |   3   | D/V  |
| 4.18.5 | Ellenőrizze, hogy a mikroarchitektúrára épülő oldalcsatorna elleni védelem tartalmazza-e a spekulatív végrehajtás szabályozását és a memóriahozzáférési minták eltakarását.               |   3   | D/V  |

---

## C4.19 Neuromorfikus és Speciális MI Hardverbiztonság

Biztosítani az újonnan kifejlődő mesterséges intelligencia hardverarchitektúrák, beleértve a neuromorfikus chipeket, FPGA-kat, egyedi ASIC-eket és optikai számítástechnikai rendszereket.

|   #    | Description                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Ellenőrizze, hogy a neuromorfikus chip biztonsága magában foglalja-e a tüskeminta titkosítását, a szinaptikus súlyok védelmét és a hardveralapú tanulási szabály érvényesítését.                      |   3   | D/V  |
| 4.19.2 | Ellenőrizze, hogy az FPGA-alapú MI gyorsítók bitfolyam titkosítást, hamisítás elleni mechanizmusokat, valamint hitelesített frissítésekkel történő biztonságos konfigurációbetöltést valósítanak meg. |   3   | D/V  |
| 4.19.3 | Ellenőrizze, hogy az egyedi ASIC biztonság tartalmazza-e a chipen belüli biztonsági processzorokat, a hardveres bizalmi alapot és a biztonságos kulcstárolást behatolásérzékeléssel.                  |   3   | D/V  |
| 4.19.4 | Ellenőrizze, hogy az optikai számítástechnikai rendszerek kvantumbiztos optikai titkosítást, biztonságos fotonikus kapcsolást és védett optikai jelfeldolgozást valósítanak-e meg.                    |   3   | D/V  |
| 4.19.5 | Ellenőrizze, hogy a hibrid analóg-digitális AI chipek tartalmaznak-e biztonságos analóg számítást, védett súlytárolást és hitelesített analóg-digitális átalakítást.                                  |   3   | D/V  |

---

## C4.20 Adatvédelmet biztosító számítási infrastruktúra

Valósítson meg infrastruktúra-ellenőrzéseket a magánéletet védő számításokhoz, hogy megvédje az érzékeny adatokat az MI feldolgozása és elemzése során.

|   #    | Description                                                                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Ellenőrizze, hogy a homomorfikus titkosítási infrastruktúra lehetővé teszi-e a titkosított számításokat érzékeny mesterséges intelligencia munkaterheléseken kriptográfiai integritásellenőrzéssel és teljesítménymonitorozással. |   3   | D/V  |
| 4.20.2 | Ellenőrizze, hogy a privát információlekérdezési rendszerek lehetővé teszik-e az adatbázis-lekérdezéseket a lekérdezési minták feltárása nélkül, az elérési minták kriptográfiai védelmével.                                      |   3   | D/V  |
| 4.20.3 | Ellenőrizze, hogy a biztonságos többrésztvevős számítási protokollok lehetővé teszik-e a magánélet védelmét biztosító MI következtetések végrehajtását anélkül, hogy felfednék az egyes bemeneteket vagy a közbenső számításokat. |   3   | D/V  |
| 4.20.4 | Ellenőrizze, hogy a személyes adatok védelmét biztosító kulcskezelés magában foglalja-e az elosztott kulcsgenerálást, a küszöbkriptográfiát és a biztonságos kulcscserét hardveres védettséggel.                                  |   3   | D/V  |
| 4.20.5 | Bizonyítsa be, hogy az adatvédelmi szempontból biztonságos számítási teljesítmény optimalizálva van csoportosítás, gyorsítótárazás és hardveres gyorsítás révén, miközben megmaradnak a kriptográfiai biztonsági garanciák.       |   3   | D/V  |

---

## C4.15 Ügynök Keretrendszer Felhőintegráció Biztonság és Hibrid Kivitelezés

Biztonsági vezérlők felhőintegrált ügynök keretrendszerek számára hibrid helyszíni/ felhő architektúrákkal.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Ellenőrizze, hogy a felhőtároló integráció végpontok közötti titkosítást alkalmaz-e, amelyet az ügynök által vezérelt kulcskezelés biztosít. |   1   | D/V  |
| 4.15.2 | Ellenőrizze, hogy a hibrid telepítési biztonsági határok világosan definiáltak-e titkosított kommunikációs csatornákkal.                     |   2   | D/V  |
| 4.15.3 | Ellenőrizze, hogy a felhő erőforrás-hozzáférés tartalmaz-e nullatűrés alapú ellenőrzést folyamatos hitelesítéssel.                           |   2   | D/V  |
| 4.15.4 | Ellenőrizze, hogy az adattartózkodási követelmények teljesülnek-e a tárolási helyek kriptográfiai igazolásával.                              |   3   | D/V  |
| 4.15.5 | Ellenőrizze, hogy a felhőszolgáltató biztonsági értékelései tartalmazzák-e az ügynökspecifikus fenyegetésmodellezést és kockázatértékelést.  |   3   | D/V  |

---

## Hivatkozások

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

