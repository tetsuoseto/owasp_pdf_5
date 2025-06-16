# 9 Autonóm hangolás és ügynöki cselekvési biztonság

## Vezérlési célkitűzés

Biztosítani kell, hogy az autonóm vagy többügynökös MI-rendszerek csak az egyértelműen szándékolt, hitelesített, auditálható és korlátozott költség- és kockázati küszöbértékeken belüli műveleteket hajthassanak végre. Ez megvédi a rendszert az olyan fenyegetésekkel szemben, mint az autonóm rendszer kompromittálása, eszközhibás használata, ügynök hurkok észlelése, kommunikáció eltérítése, személyazonosság hamisítása, raj manipuláció és szándék manipuláció.

---

## 9.1 Ügynök Feladat-tervezés és Rekurziós Költségvetések

Ütemezze korlátozottan a rekurzív terveket, és kényszerítsen emberi ellenőrzőpontokat a kiváltságos műveletekhez.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Ellenőrizze, hogy az egyes ügynök-futtatások maximális rekurziós mélysége, szélessége, falióra szerinti ideje, tokenek száma és pénzügyi költsége központilag konfigurált és verziókezelt legyen.                    |   1   | D/V  |
| 9.1.2 | Ellenőrizze, hogy a kiváltságos vagy visszafordíthatatlan műveletek (például kódcommitok, pénzügyi átutalások) végrehajtása előtt kifejezett emberi jóváhagyás szükséges legyen egy auditálható csatornán keresztül. |   1   | D/V  |
| 9.1.3 | Ellenőrizze, hogy a valós idejű erőforrás-figyelők kiváltják-e a megszakító megszakítást, amikor bármely költségvetési küszöbérték túllépésre kerül, megállítva a további feladatbővítést.                           |   2   |  D   |
| 9.1.4 | Ellenőrizze, hogy a megszakító események naplózva vannak-e az ügynökazonosítóval, kiváltó feltétellel és a rögzített tervállapottal a jogi vizsgálathoz.                                                             |   2   | D/V  |
| 9.1.5 | Ellenőrizze, hogy a biztonsági tesztek lefedik-e a költségvetés-kimerülés és az elszabadult terv szcenáriókat, megerősítve a biztonságos leállást adatvesztés nélkül.                                                |   3   |  V   |
| 9.1.6 | Ellenőrizze, hogy a költségvetési szabályzatok kódként vannak-e megfogalmazva, és a CI/CD-ben érvényesülnek-e a konfigurációs eltérés megakadályozása érdekében.                                                     |   3   |  D   |

---

## 9.2 Eszköz plugin homokozózás

Izolálja az eszközinterakciókat az illetéktelen rendszerhozzáférés vagy kódvégrehajtás megelőzése érdekében.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Ellenőrizze, hogy minden eszköz/bővítmény egy operációs rendszerben, konténerben vagy WASM-szintű homokozóban fusson a legkisebb jogosultságú fájlrendszer-, hálózat- és rendszerhívás-szabályzatokkal. |   1   | D/V  |
| 9.2.2 | Ellenőrizze, hogy a homokozó erőforrás-kvóták (CPU, memória, lemez, hálózati kimenet) és a végrehajtási időkorlátok érvényesítve és naplózva vannak-e.                                                  |   1   | D/V  |
| 9.2.3 | Ellenőrizze, hogy az eszköz binárisai vagy leírói digitálisan aláírtak-e; az aláírásokat betöltés előtt érvényesítik.                                                                                   |   2   | D/V  |
| 9.2.4 | Ellenőrizze, hogy a homokozó telemetria adatfolyamai a SIEM-be érkeznek-e; az anomáliák (pl. kísérletet tett kimenő kapcsolatok) riasztásokat váltanak ki.                                              |   2   |  V   |
| 9.2.5 | Ellenőrizze, hogy a magas kockázatú beépülő modulok biztonsági átvilágításon és behatolás-tesztelésen esnek át a termelési bevezetés előtt.                                                             |   3   |  V   |
| 9.2.6 | Ellenőrizze, hogy a sandboxból való kitörési kísérletek automatikusan blokkolásra kerülnek-e, és a hibás bővítmény elkülönítésre kerül-e vizsgálatig.                                                   |   3   | D/V  |

---

## 9.3 Autonóm hurok és költségkorlátozás

Észlelje és állítsa meg az ellenőrizetlen ügynök-ügynök közötti rekurziót és a költségrobbanásokat.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Ellenőrizze, hogy az ügynökök közötti hívások tartalmaznak-e egy ugrásszám-korlátot vagy TTL-t, amelyet a futtatókörnyezet csökkent és érvényesít.            |   1   | D/V  |
| 9.3.2 | Ellenőrizze, hogy az ügynökök egyedi meghívási gráfazonosítót tartanak fenn az önmeghívás vagy ciklikus minták észlelésére.                                   |   2   |  D   |
| 9.3.3 | Ellenőrizze, hogy a felhalmozódó számítási egység- és költési számlálók kéréslánconként követve vannak-e; ha a határérték túllépésre kerül, a lánc megszakad. |   2   | D/V  |
| 9.3.4 | Ellenőrizze, hogy a formális elemzés vagy a modellellenőrzés bizonyítja-e, hogy az ügynökprotokollokban nincs korlátlan rekurzió.                             |   3   |  V   |
| 9.3.5 | Ellenőrizze, hogy a ciklus-megszakítási események riasztásokat generálnak-e, és szolgáltatnak-e folyamatos fejlesztési mutatókat.                             |   3   |  D   |

---

## 9.4 Protokollszintű visszaélés elleni védelem

Biztonságos kommunikációs csatornák az ügynökök és külső rendszerek között a eltérítés vagy manipuláció megelőzése érdekében.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Ellenőrizze, hogy az összes ügynök-hoz eszköz és ügynök-hoz ügynök üzenet hitelesítve van-e (például kölcsönös TLS vagy JWT használatával), és végponttól végpontig titkosítva van-e. |   1   | D/V  |
| 9.4.2 | Ellenőrizze, hogy a sémák szigorúan érvényesítve vannak-e; az ismeretlen mezőket vagy hibás üzeneteket el kell utasítani.                                                             |   1   |  D   |
| 9.4.3 | Ellenőrizze, hogy az integritás-ellenőrzések (MAC-ok vagy digitális aláírások) kiterjednek-e az egész üzenetterjedelemre, beleértve az eszközparamétereket is.                        |   2   | D/V  |
| 9.4.4 | Ellenőrizze, hogy az ismétlődés elleni védelem (nonce-ok vagy időbélyeg-ablakok) érvényesítve van-e a protokollrétegen.                                                               |   2   |  D   |
| 9.4.5 | Ellenőrizze, hogy a protokollimplementációk átesnek-e fuzzingon és statikus elemzésen injekciós vagy deszerializációs hibák keresése érdekében.                                       |   3   |  V   |

---

## 9.5 Ügynökazonosság és manipulációbiztos bizonyíték

Biztosítsa, hogy a tevékenységek hozzárendelhetők legyenek, és a módosítások észlelhetők maradjanak.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Ellenőrizze, hogy minden egyes ügynök példány egyedi kriptográfiai azonosítóval (kulcspárral vagy hardverhez kötött hitelesítő adatokkal) rendelkezik-e.        |   1   | D/V  |
| 9.5.2 | Ellenőrizze, hogy minden ügynöki művelet alá van-e írva és időbélyeggel van-e ellátva; a naplók tartalmazzák az aláírást a visszautasítás elkerülése érdekében. |   2   | D/V  |
| 9.5.3 | Ellenőrizze, hogy a hamisításra utaló logok csak hozzáfűzéssel vagy egyszeri írással rendelkező közegen vannak-e tárolva.                                       |   2   |  V   |
| 9.5.4 | Ellenőrizze, hogy az identitáskulcsok meghatározott ütemezés szerint és a kompromittálódás jeleire forgatódnak-e.                                               |   3   |  D   |
| 9.5.5 | Ellenőrizze, hogy az illetéktelen hozzáférési vagy kulcskonfliktus kísérletek az érintett ügynök azonnali elkülönítését váltják-e ki.                           |   3   | D/V  |

---

## 9.6 Többügynökös rajkockázat-csökkentés

Csökkentse a kollektív viselkedési veszélyeket elkülönítéssel és formális biztonsági modellezéssel.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Ellenőrizze, hogy a különböző biztonsági tartományokban működő ügynökök elszigetelt futtatókörnyezetekben vagy hálózati szegmensekben hajtódnak-e végre.                   |   1   | D/V  |
| 9.6.2 | Ellenőrizze, hogy a rajviselkedések modellezve és formálisan ellenőrizve legyenek élhetőség és biztonság szempontjából a telepítés előtt.                                  |   3   |  V   |
| 9.6.3 | Ellenőrizze, hogy a futásidejű megfigyelők észlelik-e a felmerülő veszélyes mintázatokat (például oszcillációkat, holttereket) és megkezdik-e a korrekciós intézkedéseket. |   3   |  D   |

---

## 9.7 Felhasználói és Eszköz Hitelesítés / Jogosultságkezelés

Minden ágens által indított művelet esetén valósítsunk meg robusztus hozzáférés-vezérlést.

|   #   | Description                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Ellenőrizze, hogy az ügynökök elsőrendű jogosultként hitelesítik magukat a kimenő rendszerek felé, és soha nem újrahasználják a végfelhasználói hitelesítő adatokat. |   1   | D/V  |
| 9.7.2 | Ellenőrizze, hogy a részletes jogosultsági szabályok korlátozzák-e, mely eszközöket hívhat meg egy ügynök, és milyen paramétereket adhat meg azokhoz.                |   2   |  D   |
| 9.7.3 | Ellenőrizze, hogy a jogosultság-ellenőrzések minden híváskor újraértékelődnek-e (folyamatos jogosultság-ellenőrzés), nem csak a munkamenet indításakor.              |   2   |  V   |
| 9.7.4 | Ellenőrizze, hogy a delegált jogosultságok automatikusan lejárnak-e, és újbóli jóváhagyást igényelnek-e időkorlát vagy jogosultsági kör változás esetén.             |   3   |  D   |

---

## 9.8 Ügynök-ügynök közötti kommunikáció biztonsága

Titkosítsa és biztosítsa az összes ügynökök közötti üzenet integritását, hogy megakadályozza a lehallgatást és a manipulációt.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Ellenőrizze, hogy a kölcsönös hitelesítés és a tökéletes előre titoktartású titkosítás (például TLS 1.3) kötelező-e az ügynökcsatornák számára.                 |   1   | D/V  |
| 9.8.2 | Ellenőrizze, hogy az üzenet integritása és eredete hitelesítve van-e a feldolgozás előtt; a sikertelen ellenőrzés riasztásokat vált ki, és az üzenetet eldobja. |   1   |  D   |
| 9.8.3 | Ellenőrizze, hogy a kommunikáció metaadatai (időbélyegek, sorrendszámok) naplózásra kerülnek-e a vizsgálati rekonstrukció támogatása érdekében.                 |   2   | D/V  |
| 9.8.4 | Ellenőrizze, hogy a formális verifikáció vagy a modellellenőrzés megerősíti-e, hogy a protokoll állapotgépei nem hajthatók veszélyes állapotokba.               |   3   |  V   |

---

## 9.9 Szándékellenőrzés és korlátozások érvényesítése

Ellenőrizze, hogy az ügynök műveletei összhangban vannak-e a felhasználó megadott szándékával és a rendszer korlátaival.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Ellenőrizze, hogy a végrehajtás előtti megszorításmegoldók a javasolt műveleteket a kemény kódolt biztonsági és irányelvek szabályai szerint vizsgálják-e.                                        |   1   |  D   |
| 9.9.2 | Ellenőrizze, hogy a nagy hatású műveletek (pénzügyi, pusztító, adatvédelmi szempontból érzékeny) egyértelmű szándékmegerősítést igényelnek-e az indító felhasználótól.                            |   2   | D/V  |
| 9.9.3 | Ellenőrizze, hogy az utófeltétel-ellenőrzések igazolják, hogy a befejezett műveletek elérték a kívánt hatásokat mellékhatások nélkül; az eltérések visszagörgetést váltanak ki.                   |   2   |  V   |
| 9.9.4 | Ellenőrizze, hogy a formális módszerek (például modell-ellenőrzés, tételbizonyítás) vagy a tulajdonság-alapú tesztek igazolják, hogy az ügynök tervek megfelelnek az összes kijelölt feltételnek. |   3   |  V   |
| 9.9.5 | Bizonyosodjon meg arról, hogy a szándékeltérés vagy megszorításmegsértés események folyamatos fejlesztési ciklusokat és fenyegetés-információ megosztást táplálnak.                               |   3   |  D   |

---

## 9.10 Ügynök Érvelési Stratégia Biztonsága

Biztonságos kiválasztása és végrehajtása különböző érvelési stratégiáknak, beleértve a ReAct, a Gondolatlánc (Chain-of-Thought) és a Gondolatfák (Tree-of-Thoughts) megközelítéseket.

|   #    | Description                                                                                                                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Ellenőrizze, hogy az érvelési stratégia kiválasztása determinisztikus kritériumokon alapul-e (bemeneti összetettség, feladattípus, biztonsági kontextus), és hogy az azonos bemenetek azonos stratégia kiválasztást eredményeznek-e ugyanazon biztonsági kontextuson belül.                 |   1   | D/V  |
| 9.10.2 | Ellenőrizze, hogy minden egyes érvelési stratégia (ReAct, Chain-of-Thought, Tree-of-Thoughts) rendelkezik-e dedikált bemeneti érvényesítéssel, kimeneti tisztítással és az adott kognitív megközelítéshez igazított végrehajtási időkorlátokkal.                                            |   1   | D/V  |
| 9.10.3 | Ellenőrizze, hogy az érvelési stratégia átmenetek naplózva vannak-e teljes kontextussal, beleértve a bemeneti jellemzőket, a kiválasztási kritériumok értékeit és a végrehajtási metaadatokat az audit nyomvonal rekonstruálásához.                                                         |   2   | D/V  |
| 9.10.4 | Ellenőrizze, hogy a Gondolatfa-alapú következtetés tartalmaz-e ágelvágó mechanizmusokat, amelyek megszakítják a feltárást, ha szabályszegéseket, erőforrás-korlátokat vagy biztonsági határokat észlelnek.                                                                                  |   2   | D/V  |
| 9.10.5 | Ellenőrizze, hogy a ReAct (Reason-Act-Observe) ciklusok tartalmaznak-e érvényesítési ellenőrzőpontokat minden egyes fázisban: az érvelési lépés ellenőrzését, a cselekvés engedélyezését és a megfigyelés tisztítását, mielőtt továbblépnének.                                              |   2   | D/V  |
| 9.10.6 | Ellenőrizze, hogy az érvelési stratégia teljesítménymutatóit (végrehajtási idő, erőforrás-használat, kimeneti minőség) automatikus riasztások figyelik-e, amikor a mutatók a beállított küszöbértékeket meghaladják.                                                                        |   3   | D/V  |
| 9.10.7 | Ellenőrizze, hogy a több stratégiát kombináló hibrid érvelési megközelítések mindegyik alkotó stratégiájának bemeneti érvényesítését és kimeneti korlátait betartják-e, anélkül, hogy megkerülnék bármely biztonsági vezérlőt.                                                              |   3   | D/V  |
| 9.10.8 | Ellenőrizze, hogy az érvelési stratégia biztonsági tesztelése magában foglalja-e a hibás bemenetekkel végzett fuzzingot, az ellenfél által tervezett kéréseket az érvelési stratégia váltására kényszerítéshez, valamint a határfeltételek tesztelését minden kognitív megközelítés esetén. |   3   | D/V  |

---

## 9.11 Ügynök Életciklus Állapotkezelés és Biztonság

Biztonságos ügynök inicializálás, állapotátmenetek és befejezés kriptográfiai audit nyomvonalakkal és meghatározott helyreállítási eljárásokkal.

|   #    | Description                                                                                                                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Ellenőrizze, hogy az ügynök inicializálása magában foglalja-e a kriptográfiai azonosító létrehozását hardveralapú hitelesítő adatokkal és megváltoztathatatlan indítási auditnaplókat, amelyek tartalmazzák az ügynök azonosítóját, az időbélyeget, a konfigurációs hash-t és az inicializációs paramétereket. |   1   | D/V  |
| 9.11.2 | Ellenőrizze, hogy az ügynök állapotátmenetei kriptográfiailag aláírtak, időbélyeggel ellátottak és naplózottak legyenek teljes kontextussal együtt, beleértve a kiváltó eseményeket, az előző állapot hash-ét, az új állapot hash-ét és a végrehajtott biztonsági ellenőrzéseket.                              |   2   | D/V  |
| 9.11.3 | Ellenőrizze, hogy az ügynök leállítási eljárásai tartalmazzák-e a biztonságos memória törlést kriptográfiai törléssel vagy többszörös felülírással, a hitelesítő adatok visszavonását a tanúsítványközpont értesítésével, valamint a manipulációt jelző megszüntetési tanúsítványok létrehozását.              |   2   | D/V  |
| 9.11.4 | Ellenőrizze, hogy az ügynök helyreállítási mechanizmusai kriptográfiai ellenőrzőösszegeket (minimum SHA-256) használnak az állapot integritásának igazolására, és korrupt állapot esetén visszaállnak ismert, jó állapotokra automatizált riasztások és manuális jóváhagyási követelmények mellett.            |   3   | D/V  |
| 9.11.5 | Ellenőrizze, hogy az ügynök perzisztencia mechanizmusai AES-256 kulcsokkal egyedi ügynökenként titkosítják-e az érzékeny állapotadatokat, és biztosítják-e a biztonságos kulcscserét konfigurálható ütemezés szerint (maximálisan 90 nap), valamint a nulla állásidős telepítést.                              |   3   | D/V  |

---

## 9.12 Eszközintegrációs Biztonsági Keretrendszer

Biztonsági intézkedések a dinamikus eszközbetöltéshez, végrehajtáshoz és eredményellenőrzéshez, meghatározott kockázatértékelési és jóváhagyási folyamatokkal.

|   #    | Description                                                                                                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Ellenőrizze, hogy az eszközleírók tartalmazzák-e a biztonsági metaadatokat, amelyek meghatározzák a szükséges jogosultságokat (olvasás/írás/végrehajtás), a kockázati szinteket (alacsony/közepes/magas), az erőforrás-korlátozásokat (CPU, memória, hálózat), valamint a validációs követelményeket, amelyek dokumentálva vannak az eszköz-manifesztumokban. |   1   | D/V  |
| 9.12.2 | Ellenőrizze, hogy az eszköz végrehajtási eredményei megfelelnek-e a várt sémáknak (JSON séma, XML séma) és a biztonsági irányelveknek (kimeneti tisztítás, adatklasszifikáció), mielőtt integrálná azokat időkorlátokkal és hibakezelési eljárásokkal.                                                                                                        |   1   | D/V  |
| 9.12.3 | Ellenőrizze, hogy az eszköz interakciós naplók tartalmazzák-e a részletes biztonsági kontextust, beleértve az jogosultságok használatát, az adathozzáférési mintákat, a végrehajtási időt, az erőforrás-felhasználást és a visszatérési kódokat, továbbá strukturált naplózással történik-e a SIEM integrációhoz.                                             |   2   | D/V  |
| 9.12.4 | Ellenőrizze, hogy a dinamikus eszközbetöltési mechanizmusok azonosítják-e a digitális aláírásokat a PKI infrastruktúra használatával, és valósítanak-e meg biztonságos betöltési protokollokat homokozó izolációval és engedély-ellenőrzéssel a végrehajtás előtt.                                                                                            |   2   | D/V  |
| 9.12.5 | Ellenőrizze, hogy az eszköz biztonsági értékelései automatikusan elindulnak-e az új verziók esetében, kötelező jóváhagyási kapukkal, beleértve a statikus elemzést, dinamikus tesztelést és a biztonsági csapat átvizsgálását dokumentált jóváhagyási kritériumokkal és SLA követelményekkel.                                                                 |   3   | D/V  |

---

### Hivatkozások

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

