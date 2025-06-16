# C8 Hukommelse, Embeddings og Vektordatabasesikkerhed

## Kontrolmål

Indlejringer og vektorlager fungerer som den "aktive hukommelse" i moderne AI-systemer, der løbende modtager data leveret af brugeren og bringer det tilbage i modelkontekster via Retrieval-Augmented Generation (RAG). Hvis denne hukommelse forbliver ureguleret, kan den lække personligt identificerbare oplysninger (PII), overtræde samtykke eller vendes om for at rekonstruere den oprindelige tekst. Målet med denne kontrolfamilie er at styrke hukommelsesdatapipelines og vektordatabaser, så adgang er mindst muligt privilegeret, indlejringer bevarer privatlivets fred, lagrede vektorer udløber eller kan tilbagekaldes efter behov, og at hukommelse pr. bruger aldrig forurener en anden brugers forespørgsler eller færdiggørelser.

---

## C8.1 Adgangskontroller på Hukommelse og RAG-Indices

Håndhæv detaljerede adgangskontroller på hver enkelt vektorsamling.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Bekræft, at række-/navneområdeniveau adgangskontrolregler begrænser indsættelse, sletning og forespørgselsoperationer pr. lejer, samling eller dokumentmærke. |   1   | D/V  |
| 8.1.2 | Bekræft, at API-nøgler eller JWT'er indeholder scoped claims (f.eks. samlings-ID'er, handlingsverber) og roteres mindst kvartalsvist.                         |   1   | D/V  |
| 8.1.3 | Bekræft, at forsøg på privilege-eskalering (f.eks. tværs af navneområders lighedsforspørgsler) opdages og logges til en SIEM inden for 5 minutter.            |   2   | D/V  |
| 8.1.4 | Bekræft, at vektor-DAtabasen registrerer loggen for subjekt-identifikator, operation, vektor-ID/namespace, lighedstærskel og resultatantal.                   |   2   | D/V  |
| 8.1.5 | Bekræft, at adgangsbeslutninger testes for omgåelsesfejl, hver gang motorer opgraderes eller regler for indekssharding ændres.                                |   3   |  V   |

---

## C8.2 Indlejringens oprydning og validering

Forudscreen tekst for PII, rediger eller pseudonymiser inden vektorisering, og efterbehandl eventuelt embeddings for at fjerne resterende signaler.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Sørg for, at personligt identificerbare oplysninger (PII) og regulerede data bliver opdaget via automatiserede klassifikatorer og maskeret, tokeniseret eller fjernet før indlejring. |   1   | D/V  |
| 8.2.2 | Bekræft, at embedding-pipelines afviser eller isolerer input, der indeholder eksekverbar kode eller ikke-UTF-8-artefakter, som kunne forgifte indekset.                               |   1   |  D   |
| 8.2.3 | Bekræft, at lokal eller metrisk differentiel-privat sanitization anvendes på sætningsindlejringer, hvis afstand til enhver kendt PII-token falder under en konfigurerbar tærskel.     |   2   | D/V  |
| 8.2.4 | Bekræft, at effektiviteten af sanitization (f.eks. tilbagekaldelse af PII-redigering, semantisk drift) valideres mindst halvårligt mod benchmark-korpora.                             |   2   |  V   |
| 8.2.5 | Bekræft, at sanitiseringskonfigurationer er versionsstyrede, og at ændringer gennemgår kollegial gennemgang.                                                                          |   3   | D/V  |

---

## C8.3 Hukommelsesudløb, tilbagekaldelse og sletning

GDPR "retten til at blive glemt" og lignende love kræver rettidig sletning; vektorlagre skal derfor understøtte TTL'er, permanente sletninger og tomb-stoning, så tilbagekaldte vektorer ikke kan gendannes eller genindekseres.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Bekræft, at hver vektor- og metadataregistrering har en TTL eller en eksplicit opbevaringsetiket, som overholdes af automatiserede oprydningsopgaver.            |   1   | D/V  |
| 8.3.2 | Bekræft, at brugerinitierede sletningsanmodninger fjerner vektorer, metadata, cachekopier og afledte indekser inden for 30 dage.                                 |   1   | D/V  |
| 8.3.3 | Bekræft, at logiske sletninger efterfølges af kryptografisk sletning af lagerblokke, hvis hardware understøtter det, eller af ødelæggelse af nøgle i nøglevault. |   2   |  D   |
| 8.3.4 | Bekræft, at udløbne vektorer er udelukket fra resultaterne af nærmeste-nabo-søgning inden for < 500 ms efter udløb.                                              |   3   | D/V  |

---

## C8.4 Forebyg indlejring-inversion og lækage

Nye forsvarsmekanismer — støj-sammensætning, projektion netværk, privacy-neuron perturbation og applikationslagskryptering — kan reducere token-niveau inversion satser til under 5%.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Bekræft, at der findes en formel trusselsmodel, der dækker inversion, medlemskabs- og attribut-inferensangreb, og at denne gennemgås årligt.                  |   1   |  V   |
| 8.4.2 | Bekræft, at applikationslagskryptering eller søgbar kryptering beskytter vektorer mod direkte læsning af infrastrukturadministratorer eller cloud-personale.  |   2   | D/V  |
| 8.4.3 | Bekræft, at forsvarsparametrene (ε for DP, støj σ, projektionens rang k) balancerer privatliv ≥ 99 % tokenbeskyttelse og anvendelighed ≤ 3 % nøjagtighedstab. |   3   |  V   |
| 8.4.4 | Bekræft, at metrikker for inverteringsmodstand er en del af godkendelseskriterierne for modelopdateringer, med definerede budgetter for regression.           |   3   | D/V  |

---

## C8.5 Omfangshåndhævelse for brugerspecifik hukommelse

Informationslækage mellem lejere forbliver en af de største risici ved RAG: fejlagtigt filtrerede lighedsspørgsmål kan afdække en anden kundes private dokumenter.

|   #   | Description                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Bekræft, at hver hentningsforespørgsel efterfiltreres af lejer-/bruger-ID, før den sendes til LLM-prompten.                                                |   1   | D/V  |
| 8.5.2 | Bekræft, at samlingsnavne eller navne med namespace-ID'er er saltet pr. bruger eller lejer, så vektorer ikke kan kollidere på tværs af scopes.             |   1   |  D   |
| 8.5.3 | Bekræft, at lighedsresultater over en konfigurerbar afstandstærskel, men uden for den kaldendes rækkevidde, bliver afvist og udløser sikkerhedsalarmer.    |   2   | D/V  |
| 8.5.4 | Bekræft, at multi-tenant stresstests simulerer modstridende forespørgsler, der forsøger at hente dokumenter uden for omfanget, og demonstrerer nul lækage. |   2   |  V   |
| 8.5.5 | Bekræft, at krypteringsnøgler er adskilt pr. lejer, hvilket sikrer kryptografisk isolation, selvom fysisk lagring deles.                                   |   3   | D/V  |

---

## C8.6 Avanceret hukommelsessystem sikkerhed

Sikkerhedskontroller for avancerede hukommelsesarkitekturer, herunder episodisk, semantisk og arbejdshukommelse med specifikke isolations- og valideringskrav.

|   #   | Description                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Bekræft, at forskellige hukommelsestyper (episodisk, semantisk, arbejdshukommelse) har isolerede sikkerhedskontekster med rollebaserede adgangskontroller, separate krypteringsnøgler og dokumenterede adgangsmønstre for hver hukommelsestype. |   1   | D/V  |
| 8.6.2 | Bekræft, at processerne for hukommelseskonsolidering inkluderer sikkerhedsvalidering for at forhindre indsprøjtning af ondsindede minder gennem indholdsrensning, kildeverifikation og integritetskontrol før lagring.                          |   2   | D/V  |
| 8.6.3 | Bekræft, at forespørgsler om hukommelsesgenfinding valideres og renses for at forhindre udtrækning af uautoriserede oplysninger gennem analyse af forespørgselsmønstre, håndhævelse af adgangskontrol og filtrering af resultater.              |   2   | D/V  |
| 8.6.4 | Bekræft, at hukommelsesglemning mekanismer sikkert sletter følsomme oplysninger med kryptografiske sletningsgarantier ved hjælp af nøgle-sletning, flerpassoverskrivning eller hardware-baseret sikker sletning med verificeringscertifikater.  |   3   | D/V  |
| 8.6.5 | Bekræft, at hukommelsessystemets integritet kontinuerligt overvåges for uautoriserede ændringer eller korruption gennem checksums, revisionslogfiler og automatiske advarsler, når hukommelsesindholdet ændres uden for normale operationer.    |   3   | D/V  |

---

## Referencer

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

