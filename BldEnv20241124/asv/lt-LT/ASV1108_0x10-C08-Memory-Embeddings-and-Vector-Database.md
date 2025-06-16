# C8 atminties, įterpimų ir vektorinės duomenų bazės saugumas

## Valdymo tikslas

Įterpimai ir vektorių saugyklos veikia kaip šiuolaikinių DI sistemų „gyvoji atmintis“, nuolat priimdamos vartotojo pateiktus duomenis ir grąžindamos juos į modelio kontekstus per paieškos papildytą generavimą (RAG). Jei ši atmintis nėra tinkamai valdomi, ji gali išleisti asmens identifikuojančią informaciją (PII), pažeisti sutikimą arba būti panaudota originaliam tekstui atkurti. Šios kontrolės šeimos tikslas yra sustiprinti atminties srautus ir vektorių duomenų bazes taip, kad prieiga būtų minimaliai privilegijuota, įterpimai išsaugotų privatumą, saugomi vektoriai pasibaigtų galiojimu arba būtų atšaukiami pagal poreikį, o kiekvieno vartotojo atmintis niekada nesimaišytų su kito vartotojo užklausomis ar atsakymais.

---

## C8.1 Prieigos valdymas atmintyje ir RAG indeksuose

Įgyvendinkite smulkiai sugriežtintą prieigos kontrolę kiekvienoje vektorių kolekcijoje.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.1.1 | Patikrinkite, ar eilučių/erdvės lygių prieigos valdymo taisyklės riboja įterpimo, trynimo ir užklausų operacijas pagal nuomininką, kolekciją ar dokumento žymą.          |   1   | D/V  |
| 8.1.2 | Patikrinkite, ar API raktai arba JWT turi aprėpties teiginius (pvz., kolekcijų ID, veiksmų veiksmažodžius) ir ar jie keičiami bent kartą per ketvirtį.                   |   1   | D/V  |
| 8.1.3 | Patikrinkite, ar privilegijų eskalavimo bandymai (pvz., kryžminio vardų srities panašumo užklausos) yra aptinkami ir per 5 minutes registruojami SIEM.                   |   2   | D/V  |
| 8.1.4 | Patikrinkite, ar vektorinė duomenų bazė audituoja logus, įskaitant subjekto identifikatorių, operaciją, vektorinio ID/vardų sritį, panašumo slenkstį ir rezultatų kiekį. |   2   | D/V  |
| 8.1.5 | Patikrinkite, ar prieigos sprendimai yra tikrinami dėl apeidimo trūkumų kiekvieną kartą atnaujinant variklius arba keičiant indeksų skaidymo taisykles.                  |   3   |  V   |

---

## C8.2 Įterpimų valymas ir patikra

Išankstinai patikrinkite tekstą dėl asmeninių identifikuojamų duomenų (PII), užmaskuokite ar pseudonimizuokite prieš vektorizavimą ir, jei pageidaujama, atlikite papildomą įdėjų apdorojimą, kad pašalintumėte liekamuosius signalus.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Patikrinkite, ar asmeninė tapatybės informacija (PII) ir reguliuojami duomenys yra aptinkami automatinių klasifikatorių pagalba bei prieš įterpimą yra maskuojami, pavirstami į žetonus arba pašalinami.                   |   1   | D/V  |
| 8.2.2 | Patikrinkite, ar įdiegimo vamzdynai atmeta arba izoliuoja įvestis, kuriose yra vykdomojo kodo arba ne UTF-8 artefaktų, galinčių užnuodyti indeksą.                                                                         |   1   |  D   |
| 8.2.3 | Patikrinkite, ar vietinis arba metrinis skirtumo privatumo (differential-privacy) sanitarizavimas yra taikomas sakinių įterpimams, kurių atstumas iki bet kurio žinomo PII žymens yra mažesnis už konfigūruojamą slenkstį. |   2   | D/V  |
| 8.2.4 | Patikrinkite, ar sanitarizacijos efektyvumas (pvz., asmeninės informacijos (PII) redagavimo atsimenamumas, semantinis poslinkis) yra patvirtintas bent pusmečio dažnumu naudojant etalonines korpusų rinkinius.            |   2   |  V   |
| 8.2.5 | Patikrinkite, ar sanitizacijos konfigūracijos yra valdomos versijų sistema ir ar pakeitimai yra peržiūrimi kolegų.                                                                                                         |   3   | D/V  |

---

## C8.3 Atminties galiojimo pabaiga, atšaukimas ir ištrynimas

BDAR „teisė būti pamirštam“ ir panašūs įstatymai reikalauja laiku ištrinti duomenis; todėl vektorių saugyklos turi palaikyti gyvavimo trukmės ribojimą (TTL), griežtą ištrynimą ir užrašų naikinimą (tomb-stoning), kad atšaukti vektoriai negalėtų būti atkurti arba vėl indeksuoti.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Patikrinkite, ar kiekvienas vektorius ir metaduomenų įrašas turi TTL arba aiškų saugojimo etiketę, kurią gerbia automatiniai valymo darbai.                    |   1   | D/V  |
| 8.3.2 | Patikrinkite, ar vartotojo inicijuoti ištrynimo prašymai per 30 dienų ištrina vektorius, metaduomenis, talpyklos kopijas ir darinines indeksus.                |   1   | D/V  |
| 8.3.3 | Patikrinkite, ar loginiai ištrynimai yra sekami kriptografiniu saugojimo blokų sunaikinimu, jei aparatūra tai palaiko, arba rakto saugyklos rakto sunaikinimu. |   2   |  D   |
| 8.3.4 | Patikrinkite, ar pasibaigę vektoriai yra pašalinti iš artimiausių kaimynų paieškos rezultatų per mažiau nei 500 ms po galiojimo pabaigos.                      |   3   | D/V  |

---

## C8.4 Užkirsti kelią įterpimo inversijai ir nutekėjimui

Naujausios apsaugos priemonės – triukšmo pridėjimas, projekcijos tinklai, privatumo neuronų trikdymas ir aplikacijos sluoksnio šifravimas – gali sumažinti simbolių lygio apvertimo rodiklius iki mažiau nei 5%.

|   #   | Description                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Patikrinkite, ar egzistuoja oficialus grėsmių modelis, apimantis inversijos, narystės ir atributo spėjimo atakas, ir ar jis peržiūrimas kasmet.                              |   1   |  V   |
| 8.4.2 | Patikrinkite, ar programinio sluoksnio šifravimas arba ieškoma šifravimas apsaugo vektorius nuo tiesioginių skaitymų infrastruktūros administratorių ar debesijos personalo. |   2   | D/V  |
| 8.4.3 | Patikrinkite, ar gynybos parametrai (ε DP, triukšmas σ, projekcijos rangas k) užtikrina privatumą ≥ 99 % tokenų apsaugą ir naudingumą ≤ 3 % tikslumo sumažėjimą.             |   3   |  V   |
| 8.4.4 | Patikrinkite, ar apverčiamosios atsparumo metrikos yra modelio atnaujinimų išleidimo slenksčių dalis, su apibrėžtais regresijos biudžetais.                                  |   3   | D/V  |

---

## C8.5 Vartotojui būdingos atminties aprėpties įgyvendinimas

Kryžminis duomenų nutekėjimas tarp nuomininkų išlieka pagrindine RAG rizika: netinkamai filtruoti panašumo užklausos gali atskleisti kito kliento privačius dokumentus.

|   #   | Description                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Patikrinkite, ar kiekvienas užklausimo atgavimas yra filtruojamas pagal nuomininko/vartotojo ID prieš pateikiant LLM užklausos formavimo metu.                                   |   1   | D/V  |
| 8.5.2 | Patikrinkite, ar kolekcijų pavadinimai arba vardų erdvėje naudojami ID yra pasūdyti kiekvienam vartotojui arba nuomininkui, kad vektoriai negalėtų sutapti skirtingose apimtyse. |   1   |  D   |
| 8.5.3 | Patikrinkite, ar panašumo rezultatai, viršijantys konfigūruojamą atstumo ribą, tačiau už kvietėjo aprėpties ribų, yra atmestami ir sukelia saugumo įspėjimus.                    |   2   | D/V  |
| 8.5.4 | Patikrinkite, ar daugianuominiai apkrovos testai imituoja priešiškus užklausas, siekiančias gauti netinkamus dokumentus, ir užtikrina, kad nebūtų jokio nutekėjimo.              |   2   |  V   |
| 8.5.5 | Patikrinkite, ar šifravimo raktai yra atskirti kiekvienam nuomininkui, užtikrinant kriptografinį izoliavimą net jei fizinė saugykla yra bendrinama.                              |   3   | D/V  |

---

## C8.6 Pažangi atminties sistemos sauga

Saugumo valdymas pažangioms atminties architektūroms, įskaitant epizodinę, semantinę ir darbinę atmintį, su specifiniais izoliacijos ir validacijos reikalavimais.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Patikrinkite, ar skirtingi atminties tipai (episodinė, semantinė, darbinė) turi atskirus saugumo kontekstus su vaidmenimis pagrįstomis prieigos kontrolėmis, atskirus šifravimo raktus ir dokumentuotus prieigos modelius kiekvienam atminties tipui. |   1   | D/V  |
| 8.6.2 | Patikrinkite, ar atminties konsolidavimo procesai apima saugumo patikrą, siekiant išvengti kenkėjiškų atminties įrašų įterpimo per turinio valymą, šaltinio patikrinimą ir vientisumo patikras prieš saugojimą.                                       |   2   | D/V  |
| 8.6.3 | Patikrinkite, ar atminties užklausos yra patvirtintos ir išvalytos, kad būtų užkirstas kelias neautorizuotos informacijos gavimui per užklausų modelių analizę, prieigos valdymo užtikrinimą ir rezultatų filtravimą.                                 |   2   | D/V  |
| 8.6.4 | Patikrinkite, ar atminties užmaršumo mechanizmai saugiai ištrina jautrią informaciją su kriptografinio ištrynimo garantijomis, naudodami rakto ištrynimą, keliaprasmį perrašymą arba aparatinį saugų ištrynimą su patikrinimo pažymėjimais.           |   3   | D/V  |
| 8.6.5 | Patikrinkite, ar atminties sistemos integralumas nuolat stebimas dėl neleistinų pakeitimų ar pažeidimų, naudojant kontrolines sumas, audito žurnalus ir automatinius įspėjimus, kai atminties turinys keičiasi už normalios veiklos ribų.             |   3   | D/V  |

---

## Nuorodos

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

