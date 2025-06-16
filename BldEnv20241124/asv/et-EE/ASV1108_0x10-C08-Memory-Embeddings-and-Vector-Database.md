# C8 mälu, manused ja vektorandmebaasi turvalisus

## Kontrolli eesmärk

Embedid ja vektoripangad toimivad kaasaegsete tehisintellekti süsteemide „elava mäluna“, võttes pidevalt vastu kasutajate sisestatud andmeid ja kuvades neid mudeli kontekstides tagasi tagasitoomisega täiendatud genereerimise (RAG) kaudu. Kui seda mälu ei reguleerita, võib see lekkida isikutuvastavat teavet (PII), rikkuda nõusolekut või pöörata selle originaalteksti rekonstrueerimiseks. Selle kontrolliperioodi eesmärk on tugevdada mäluporteesid ja vektorandmebaase nii, et juurdepääs oleks miinimumnõuetes, embedid säilitaksid privaatsust, salvestatud vektorid aeguksid või neid saaks nõudmisel tühistada ning ühe kasutaja mälu ei saastaks teise kasutaja päringuid ega väljundeid.

---

## C8.1 Juurdepääsukontrollid mälu ja RAG indeksite suhtes

Rakenda peenekoelisi juurdepääsukontrolle iga vektorikogu jaoks.

|   #   | Description                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Kontrollige, et rea-/nimedevahemiku tasemel ligipääsu kontrolli reeglid piiravad lisamise, kustutamise ja päringu operatsioone iga rentniku, kogumi või dokumendi märgise kohta. |   1   | D/V  |
| 8.1.2 | Kontrollige, et API võtmed või JWT-d sisaldaksid ulatusega seotud õigusi (nt kogu ID-d, tegevussõnad) ning et neid vahetataks vähemalt kord kvartalis.                           |   1   | D/V  |
| 8.1.3 | Kinnitage, et privileegide eskaleerimise katsed (nt ristnimevahemiku sarnasuse päringud) avastatakse ja logitakse SIEM-süsteemi jooksul 5 minuti jooksul.                        |   2   | D/V  |
| 8.1.4 | Kinnitage, et vektorandmebaasi auditis salvestatakse subjekt-identifikaator, operatsioon, vektori ID/ruum, sarnasuse lävi ja tulemuste arv.                                      |   2   | D/V  |
| 8.1.5 | Veenduge, et juurdepääsuotsuseid testitakse kõrvalejuhtimise vigade suhtes iga kord, kui mootorid uuendatakse või kui muutuvad indeksipilude reeglid.                            |   3   |  V   |

---

## C8.2 Manustamise puhastus ja valideerimine

Eelkontrolli tekst isikut tuvastava informatsiooni (PII) suhtes, tee see enne vektoreerimist tsenseerituks või pseudonümiseerituks ning vajadusel töötle vektoriseeritud esitusi täiendavalt, et eemaldada järelejäänud signaalid.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Kontrollige, et isikuandmed (PII) ja reguleeritud andmed tuvastatakse automatiseeritud klassifikaatorite abil ning neid varjatakse, märgendatakse või eemaldatakse enne sisestamist.                                        |   1   | D/V  |
| 8.2.2 | Kinnitage, et sisestusvood embeddingute jaoks lükkavad tagasi või panevad karantiini sisendid, mis sisaldavad täidetavat koodi või mitte-UTF-8 artefakte, mis võivad indeksit kahjustada.                                   |   1   |  D   |
| 8.2.3 | Kinnitage, et lokaalne või mõõtmel põhinev diferentsiaalprivaatsuse sanitiseerimine rakendatakse lause manustustele, mille kaugus mis tahes teadaolevast isikutuvastatavast teabemärgist (PII) jääb alla seadistatava läve. |   2   | D/V  |
| 8.2.4 | Kinnitage, et sanitaarse puhastamise tõhusust (nt isikuandmete eemaldamise tunnetuslik kordamine, semantilise nihe) hinnatakse vähemalt poolaastaselt võrdlusandmestike alusel.                                             |   2   |  V   |
| 8.2.5 | Kontrolli, et puhastuskonfiguratsioonid oleksid versioonihalduses ning muudatused läbiksid eakaaslaste ülevaatuse.                                                                                                          |   3   | D/V  |

---

## C8.3 Mälu aegumine, tühistamine ja kustutamine

GDPR "õigus olla unustatud" ja sarnased seadused nõuavad õigeaegset kustutamist; vektoripoodidel peab seetõttu olema tugi tõrkeaja (TTL), raske kustutamise ja haudumise (tomb-stoning) jaoks, et tühistatud vektoreid ei saaks taastada ega uuesti indekseerida.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Kinnitage, et igal vektori ja metaandmete kirjel on TTL või selgesõnaline säilitussilt, mida austavad automaatsed puhastustööd.                                  |   1   | D/V  |
| 8.3.2 | Kontrollige, et kasutajapoolsed kustutustaotlused kustutaksid vektorid, metaandmed, vahemällukoopiad ja tuletatud indeksid 30 päeva jooksul.                     |   1   | D/V  |
| 8.3.3 | Kontrollige, et loogiliste kustutuste järel järgiks krüptograafiline salvestusplokkide purustamine, kui riistvara seda toetab, või võtmehoidla võtme hävitamine. |   2   |  D   |
| 8.3.4 | Kinnita, et aegunud vektorid on välistatud lähima naabri otsingu tulemustest vähem kui 500 ms pärast aegumist.                                                   |   3   | D/V  |

---

## C8.4 Takista manustamise pööramist ja lekkimist

Viimased kaitsevahendid—müra superpositsioon, projektsioonivõrgud, privaatsus-neuroni häirumine ja rakenduskihtkrüpteerimine—võivad vähendada tokentasandi pöördumise määra alla 5%.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Kinnitage, et olemas on ametlik ohumudel, mis hõlmab inversiooni, liikmelisuse ja atribuudi-läbivaatamise ründeid, ning seda vaadatakse üle kord aastas.          |   1   |  V   |
| 8.4.2 | Veenduge, et rakenduskihi krüpteerimine või otsitav krüpteerimine kaitseb vektoreid infrastruktuuriadministraatorite või pilvepersonalide otseste lugemiste eest. |   2   | D/V  |
| 8.4.3 | Kontrollige, et kaitseparameetrid (ε DP jaoks, müra σ, projektsiooni aste k) tagaksid privaatsuse ≥ 99% märgisäästu ja kasutusväärtuse ≤ 3% täpsuse kadu.         |   3   |  V   |
| 8.4.4 | Kinnitage, et invertsioonikindluse mõõdikud on mudeli uuenduste vabastustõketes, kus regressioonieelarved on määratletud.                                         |   3   | D/V  |

---

## C8.5 Kasutajapõhise mälu ulatuse rakendamine

Ristüürniku lekked on endiselt üks peamisi RAG-riske: valesti filtreeritud sarnasusküsimused võivad avaldada teise kliendi privaatdokumendid.

|   #   | Description                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Kontrolli, et iga päringu tagastamine oleks enne LLM päringule edastamist filtreeritud rentniku/kasutaja ID järgi.                                                      |   1   | D/V  |
| 8.5.2 | Kinnitage, et kogu nimed või nimeruumi ID-d on kasutaja või tenant'i lõikes soolatud, et vektorid ei saaks kattuda erinevate ulatuste vahel.                            |   1   |  D   |
| 8.5.3 | Kontrollige, et sarnasustulemused, mis ületavad konfigureeritava kauguspiiri, kuid jäävad väljapoole kõneleja ulatust, visatakse ära ja käivitavad turvahoiatused.      |   2   | D/V  |
| 8.5.4 | Kinnitage, et mitmekülgsed stressitestid simuleerivad vaenulikke päringuid, mis püüavad hankida väljaspool ulatust olevaid dokumente, ja tõestavad lekkimise puudumist. |   2   |  V   |
| 8.5.5 | Kontrollige, et krüpteerimisvõtmed oleksid segmenteeritud iga üürniku kohta, tagades krüptograafilise isolatsiooni isegi siis, kui füüsiline salvestusruum on jagatud.  |   3   | D/V  |

---

## C8.6 Täiustatud mälusüsteemi turvalisus

Turvakontrollid keerukate mäluarhitektuuride jaoks, sealhulgas episodiline, semantiline ja töömälu, millel on spetsiifilised isoleerimis- ja valideerimisnõuded.

|   #   | Description                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Kinnitage, et erinevatel mälutüüpidel (episoodiline, semantiline, töömälu) on isoleeritud turvakontekstid rollipõhiste ligipääsukontrollide, eraldi krüptovõtmete ning dokumenteeritud ligipääsumustritega iga mälutüübi jaoks.                             |   1   | D/V  |
| 8.6.2 | Kontrollige, et mälukonsolideerimise protsessid hõlmavad turvakontrolli, et ennetada pahatahtlike mälestuste süstimist sisukorrektsiooni, allikate kinnitamise ja terviklikkuse kontrollide kaudu enne salvestamist.                                        |   2   | D/V  |
| 8.6.3 | Kontrollige, et mälu taastamise päringud oleksid valideeritud ja puhastatud, et vältida volitamata teabe väljavõtmist päringumustri analüüsi, juurdepääsu kontrolli rakendamise ja tulemuste filtreerimise kaudu.                                           |   2   | D/V  |
| 8.6.4 | Kinnitage, et mälu unustamise mehhanismid kustutavad tundliku teabe turvaliselt krüptograafilise hävitamise garantiidega, kasutades võtme kustutamist, mitmekordset ülekirjutamist või riistvarapõhist turvalist kustutamist koos kontrollsertifikaatidega. |   3   | D/V  |
| 8.6.5 | Kinnitage, et mälusüsteemi terviklikkust jälgitakse pidevalt loata muudatuste või korruptsiooni suhtes, kasutades kontrollsummasid, auditeerimislogisid ja automatiseeritud hoiatusi, kui mälu sisu muutub väljaspool tavapäraseid toiminguid.              |   3   | D/V  |

---

## Viited

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

