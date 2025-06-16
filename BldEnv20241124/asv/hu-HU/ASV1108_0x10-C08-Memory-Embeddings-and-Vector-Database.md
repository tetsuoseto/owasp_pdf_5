# C8 memória, beágyazások és vektordb biztonság

## Vezérlési célkitűzés

A beágyazások és vektortárolók a korszerű MI rendszerek „élő memóriájaként” működnek, folyamatosan fogadják a felhasználók által szolgáltatott adatokat, és visszakeresett generálás (Retrieval-Augmented Generation, RAG) révén visszajuttatják azokat a modell kontextusába. Ha ezek a memóriák nincsenek megfelelően szabályozva, személyes azonosításra alkalmas információk (PII) szivároghatnak ki, sérülhetnek a hozzájárulások, vagy visszafejthetővé válhat az eredeti szöveg. Ennek a szabályozási családnak a célja, hogy megerősítse a memóriaadat-folyamatokat és a vektoralapú adatbázisokat úgy, hogy az hozzáférés minimális jogosultságú legyen, a beágyazások adatvédő jellegűek legyenek, a tárolt vektorok lejárjanak vagy kérésre visszavonhatók legyenek, valamint hogy a felhasználónkénti memória ne szennyezze más felhasználók parancsait vagy eredményeit.

---

## C8.1 Hozzáférési szabályok a memórián és a RAG indexeken

Alkalmazzon finomított hozzáférés-vezérlést minden vektor gyűjteményen.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Ellenőrizze, hogy a sor/névtér szintű hozzáférés-vezérlési szabályok korlátozzák-e a beszúrás, törlés és lekérdezés műveleteket bérlőnként, gyűjteményenként vagy dokumentum címke szerint.    |   1   | D/V  |
| 8.1.2 | Ellenőrizze, hogy az API-kulcsok vagy JWT-k tartalmaznak-e körülhatárolt jogosultságokat (például gyűjteményazonosítókat, műveleti igéket), és hogy legalább negyedévente lecserélik őket.     |   1   | D/V  |
| 8.1.3 | Ellenőrizze, hogy a jogosultságnövelési kísérletek (pl. cross-namespace hasonlósági lekérdezések) észlelve legyenek, és 5 percen belül naplózva legyenek egy SIEM rendszeren.                  |   2   | D/V  |
| 8.1.4 | Ellenőrizze, hogy a vektor adatbázis naplózza-e a tárgy-azonosítót, a műveletet, a vektorazonosítót/névteret, a hasonlósági küszöbértéket és az eredményszámot.                                |   2   | D/V  |
| 8.1.5 | Ellenőrizze, hogy a hozzáférési döntések átjárhatósági hibák ellen való tesztelése megtörténik-e minden alkalommal, amikor a motorokat frissítik vagy az index-shardolási szabályok változnak. |   3   |  V   |

---

## C8.2 Beágyazás tisztítása és érvényesítése

A személyként azonosítható információkat (PII) előzetesen szűrje, anonimizálja vagy álnevesítse a vektorizálás előtt, és opcionálisan dolgozza fel utólag az embeddingeket a maradék jelek eltávolítása érdekében.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Ellenőrizze, hogy a személyes azonosító információk (PII) és a szabályozott adatok automatikus osztályozók által észlelhetők-e, és hogy azok beágyazás előtt maszkolva, tokenizálva vagy eldobva vannak-e.                                               |   1   | D/V  |
| 8.2.2 | Ellenőrizze, hogy az embedding feldolgozó folyamatok elutasítják vagy elkülönítik-e az olyan bemeneteket, amelyek futtatható kódot vagy nem UTF-8 karaktereket tartalmaznak, amelyek mérgezhetnék a indexet.                                             |   1   |  D   |
| 8.2.3 | Ellenőrizze, hogy helyi vagy metrikus differenciálpszichológiai adatvédelmi tisztítás van-e alkalmazva azokon a mondatbeágyazásokon, amelyek távolsága bármely ismert Személyes Azonosító Információ (PII) tokenhez egy konfigurálható küszöb alatt van. |   2   | D/V  |
| 8.2.4 | Ellenőrizze, hogy a tisztítás hatékonysága (például a személyes adatok kitakarásának visszahívása, szemantikai eltolódás) legalább félévente érvényesítve legyen referencia korpuszokkal szemben.                                                        |   2   |  V   |
| 8.2.5 | Ellenőrizze, hogy a tisztítási konfigurációk verziókövetettek-e, és a változtatások átesnek-e a kollégák általi felülvizsgálaton.                                                                                                                        |   3   | D/V  |

---

## C8.3 Memória lejárat, visszavonás és törlés

A GDPR „az elfeledtetéshez való jog” és hasonló törvények időben történő törlést írnak elő; ezért a vektortáraknak támogatniuk kell az élettartam-beállításokat (TTL), a végleges törlést és a sírköves törlést, hogy a visszavont vektorokat ne lehessen helyreállítani vagy újra indexelni.

|   #   | Description                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Ellenőrizze, hogy minden vektor és metaadat rekord rendelkezik-e TTL-lel vagy explicit megőrzési címkével, amelyet az automatizált tisztító feladatok betartanak.       |   1   | D/V  |
| 8.3.2 | Ellenőrizze, hogy a felhasználó által indított törlési kérelmek 30 napon belül törlik-e a vektorokat, metaadatokat, gyorsítótár példányokat és származtatott indexeket. |   1   | D/V  |
| 8.3.3 | Ellenőrizze, hogy a logikai törléseket kriptográfiai blokktörlések kövessék, ha a hardver támogatja, vagy kulcstömb kulcstöredeztetés által történjen.                  |   2   |  D   |
| 8.3.4 | Ellenőrizze, hogy az lejárt vektorok kizárásra kerülnek-e a legközelebbi szomszéd keresési eredményeiből legfeljebb 500 ms-on belül a lejárat után.                     |   3   | D/V  |

---

## C8.4 Megelőzni a beágyazás inverzióját és szivárgását

A legújabb védekezések — zajszuperpozíció, projekciós hálózatok, adatvédelmi neuron zavarás és alkalmazásrétegbeli titkosítás — képesek csökkenteni a token-szintű inverziós arányokat 5% alá.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.4.1 | Ellenőrizze, hogy létezik-e egy formális fenyegetési modell, amely lefedi az inverziót, tagsági és attribútum-inferenciás támadásokat, és hogy azt évente áttekintik.                                                    |   1   |  V   |
| 8.4.2 | Ellenőrizze, hogy az alkalmazásrétegű titkosítás vagy a kereshető titkosítás megvédi-e a vektorokat az infrastruktúra-adminisztrátorok vagy a felhőszolgáltató személyzete általi közvetlen olvasástól.                  |   2   | D/V  |
| 8.4.3 | Ellenőrizze, hogy a védelemparaméterek (ε a DP-hez, zaj σ, projektálási rang k) biztosítják-e az adatvédelmet legalább 99%-os tokenvédettség mellett, és az hasznosság legfeljebb 3%-os pontosságveszteséget eredményez. |   3   |  V   |
| 8.4.4 | Ellenőrizze, hogy az invertálás-állósági mérőszámok részei-e a modellfrissítések kiadási zárjainak, és hogy a regressziós költségkeretek meghatározásra kerültek-e.                                                      |   3   | D/V  |

---

## C8.5 Felhasználóspecifikus memória hatókörének érvényesítése

Az általa kezelt több bérlős környezetek közötti adat-szivárgás továbbra is az egyik legnagyobb RAG kockázat: a nem megfelelően szűrt hasonlósági lekérdezések egy másik ügyfél privát dokumentumait tehetik láthatóvá.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Ellenőrizze, hogy minden lekérdezési kérés a bérlő/felhasználói azonosító alapján van-e utószűrve, mielőtt átkerül az LLM parancsba.                                                                    |   1   | D/V  |
| 8.5.2 | Ellenőrizze, hogy a gyűjteménynévek vagy névterezett azonosítók felhasználónként vagy bérlőnként sózva vannak-e, hogy a vektorok ne ütközzenek tartományok között.                                      |   1   |  D   |
| 8.5.3 | Ellenőrizze, hogy a konfigurálható távolsági küszöbérték fölötti, de a hívó hatókörén kívüli hasonlósági eredményeket elvetik-e és biztonsági riasztásokat váltanak-e ki.                               |   2   | D/V  |
| 8.5.4 | Ellenőrizze, hogy a többbérlős terheléses tesztek szimulálják-e a rosszindulatú lekérdezéseket, amelyek megpróbálják kinyerni a hatáskörön kívüli dokumentumokat, és mutassák be a nulla adatkinyerést. |   2   |  V   |
| 8.5.5 | Ellenőrizze, hogy a titkosítási kulcsok bérlőnként külön vannak-e választva, biztosítva a kriptográfiai elkülönítést akkor is, ha a fizikai tárolás közös.                                              |   3   | D/V  |

---

## C8.6 Fejlett memória rendszerbiztonság

Biztonsági vezérlők fejlett memóriaarchitektúrákhoz, beleértve az epizodikus, szemantikus és munkamemóriát, amelyek specifikus elszigetelési és érvényesítési követelményeket támasztanak.

|   #   | Description                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Ellenőrizze, hogy a különböző memóriatípusok (epizodikus, szemantikus, munkamemória) izolált biztonsági kontextusokkal rendelkeznek-e szerepalapú hozzáférés-vezérléssel, külön titkosítási kulcsokkal és dokumentált hozzáférési mintákkal mindegyik memória típusra. |   1   | D/V  |
| 8.6.2 | Ellenőrizze, hogy a memória-konszolidációs folyamatok tartalmazzák-e a biztonsági ellenőrzést a rosszindulatú emlékek befecskendezésének megelőzése érdekében, amely tartalmi tisztítást, forrásellenőrzést és integritásellenőrzést foglal magában a tárolás előtt.   |   2   | D/V  |
| 8.6.3 | Ellenőrizze, hogy a memórialekérdezések érvényesítve és megtisztítva vannak-e az illetéktelen információk kivonásának megelőzése érdekében lekérdezési mintaelemzés, hozzáférés-ellenőrzés és eredményszűrés révén.                                                    |   2   | D/V  |
| 8.6.4 | Ellenőrizze, hogy a memóriafelejtési mechanizmusok biztonságosan törlik-e a érzékeny információkat kriptográfiai törlési garanciákkal, például kulcs törléssel, többszörös felülírással vagy hardveralapú biztonságos törléssel és igazolási tanúsítványokkal.         |   3   | D/V  |
| 8.6.5 | Ellenőrizze, hogy a memóriarendszer integritását folyamatosan figyelik-e jogosulatlan módosítások vagy sérülések ellen ellenőrzőösszegek, auditnaplók és automatikus riasztások segítségével, amikor a memória tartalma a normál működésen kívül megváltozik.          |   3   | D/V  |

---

## Hivatkozások

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

