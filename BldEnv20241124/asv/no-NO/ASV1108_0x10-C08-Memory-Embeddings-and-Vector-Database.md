# C8-minne, innebygde representasjoner og sikkerhet for vektordatabaser

## Kontrollmål

Innebygginger og vektorlager fungerer som "levende minne" for moderne AI-systemer, ved kontinuerlig å ta imot data fra brukeren og hente dem tilbake inn i modellkontekster via Retrieval-Augmented Generation (RAG). Hvis dette minnet ikke styres, kan det lekke personlig identifiserbar informasjon (PII), bryte samtykke, eller bli reversert for å rekonstruere originalteksten. Målet med denne kontrollfamilien er å styrke minne-pipeliner og vektordatabaser slik at tilgangen er basert på minste privilegium, innebyggerne ivaretar personvern, lagrede vektorer utløper eller kan tilbakekalles ved behov, og at per-bruker-minne aldri forurenser andre brukeres forespørsler eller resultater.

---

## C8.1 Tilgangskontroller på minne og RAG-indekser

Håndhev detaljerte tilgangskontroller på hver vektorsamling.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Verifiser at tilgangskontrollregler på rad-/navneromnivå begrenser innsettings-, slettings- og spørringsoperasjoner per leietaker, samling eller dokumentmerke. |   1   | D/V  |
| 8.1.2 | Bekreft at API-nøkler eller JWT-er inneholder avgrensede påstander (f.eks. samlings-IDer, handlingsverb) og roteres minst kvartalsvis.                          |   1   | D/V  |
| 8.1.3 | Sørg for at forsøk på privilegieeskalering (f.eks. likhetssøk på tvers av namespaces) blir oppdaget og loggført til en SIEM innen 5 minutter.                   |   2   | D/V  |
| 8.1.4 | Bekreft at vektordatabasen logger revisjoner for emneidentifikator, operasjon, vektor-ID/område, likhetsterskel og resultatantall.                              |   2   | D/V  |
| 8.1.5 | Verifiser at tilgangsbeslutninger blir testet for omgåelsesfeil hver gang motorene oppgraderes eller indeks-shardingsregler endres.                             |   3   |  V   |

---

## C8.2 Innebygging Rens og Validering

Forhåndssjekk teksten for personidentifiserbar informasjon (PII), sensurer eller pseudonymiser før vektorisering, og eventuelt etterbehandle innebyggingene for å fjerne gjenværende signaler.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Verifiser at PII og regulert data blir oppdaget via automatiserte klassifikatorer og maskert, tokenisert eller fjernet før embedding.                                       |   1   | D/V  |
| 8.2.2 | Sørg for at innbeddingspipeliner avviser eller karantenerer inndata som inneholder kjørbar kode eller ikke-UTF-8-artifakter som kan forgifte indeksen.                      |   1   |  D   |
| 8.2.3 | Bekreft at lokal eller metrisk differensialt personvern-sanitering anvendes på setningsinnbeddinger hvis avstand til noe kjent PII-token er under en konfigurerbar terskel. |   2   | D/V  |
| 8.2.4 | Verifiser at effektiviteten av sanitering (f.eks. tilbakekalling av PII-redigering, semantisk drift) valideres minst hvert halvår mot referansekorpora.                     |   2   |  V   |
| 8.2.5 | Bekreft at sanitiseringskonfigurasjoner er versjonskontrollert og at endringer gjennomgår kollegavurdering.                                                                 |   3   | D/V  |

---

## C8.3 Minnetid, Tilbakekalling og Sletting

GDPRs "rett til å bli glemt" og lignende lover krever rettidig sletting; vektorbutikker må derfor støtte TTLer, hard sletting og gravmerking slik at tilbakekalte vektorer ikke kan gjenopprettes eller reindekseres.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Verifiser at hver vektor- og metadataoppføring har en TTL eller en eksplisitt oppbevaringsetikett som respekteres av automatiserte ryddejobber.                           |   1   | D/V  |
| 8.3.2 | Bekreft at brukerinitierte slettingsforespørsler fjerner vektorer, metadata, hurtigbufferkopier og avledede indekser innen 30 dager.                                      |   1   | D/V  |
| 8.3.3 | Bekreft at logiske slettinger følges opp med kryptografisk sletting av lagringsblokker dersom maskinvaren støtter det, eller ved destruksjon av nøkkelen i nøkkellageret. |   2   |  D   |
| 8.3.4 | Bekreft at utløpte vektorer er ekskludert fra nærmeste-nabo-søkresultater innen mindre enn 500 ms etter utløp.                                                            |   3   | D/V  |

---

## C8.4 Forebygging av embedding-inversjon og lekkasje

Nylige forsvarsmekanismer—støy-supersisjon, projeksjonsnettverk, privatlivs-nevronforstyrrelse og applikasjonslagskryptering—kan redusere token-nivå inversjonsrater til under 5 %.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.4.1 | Bekreft at en formell trusselmodell som dekker inversjons-, medlemskaps- og attributtinferensangrep finnes og gjennomgås årlig.                              |   1   |  V   |
| 8.4.2 | Verifiser at applikasjonslagskryptering eller søkbar kryptering beskytter vektorer mot direkte lesing av infrastrukturadministratorer eller skylpersonell.   |   2   | D/V  |
| 8.4.3 | Bekreft at forsvarsparametrene (ε for DP, støysigma σ, projeksjonsrang k) balanserer personvern ≥ 99 % tokenbeskyttelse og nytteverdi ≤ 3 % nøyaktighetstap. |   3   |  V   |
| 8.4.4 | Bekreft at inverteringsmotstandsmetrikker er en del av frigisingsporter for modelloppdateringer, med definerte regresjonsbudsjetter.                         |   3   | D/V  |

---

## C8.5 Omfangshåndheving for brukerspesifikk minne

Kryss-lekkasje mellom leietakere forblir en ledende RAG-risiko: feilaktig filtrerte likhetsspørringer kan avsløre en annen kundes private dokumenter.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Bekreft at hver hentingsspørring blir post-filtrert etter leietaker-/bruker-ID før den sendes til LLM-prompten.                                             |   1   | D/V  |
| 8.5.2 | Bekreft at samlingsnavn eller navngitte ID-er med navneområde er saltet per bruker eller leietaker slik at vektorer ikke kan kollidere på tvers av områder. |   1   |  D   |
| 8.5.3 | Bekreft at likhetsresultater over en konfigurerbar avstandsterskel, men utenfor anroperens område, blir forkastet og utløser sikkerhetsalarmer.             |   2   | D/V  |
| 8.5.4 | Bekreft at flerbruker-stresstester simulerer motstridende forespørsler som prøver å hente dokumenter utenfor omfang, og demonstrerer null lekkasje.         |   2   |  V   |
| 8.5.5 | Bekreft at krypteringsnøkler er adskilt per leietaker, og sikrer kryptografisk isolasjon selv om fysisk lagring deles.                                      |   3   | D/V  |

---

## C8.6 Avansert sikkerhet for minnesystemer

Sikkerhetskontroller for sofistikerte minnearkitekturer inkludert episodisk, semantisk og arbeidsminne med spesifikke krav til isolasjon og validering.

|   #   | Description                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.6.1 | Verifiser at ulike minnetyper (episodisk, semantisk, arbeidende) har isolerte sikkerhetskontekster med rollebaserte tilgangskontroller, separate krypteringsnøkler og dokumenterte tilgangsmønstre for hver minnetype.                           |   1   | D/V  |
| 8.6.2 | Bekreft at minnekonsolideringsprosesser inkluderer sikkerhetsvalidering for å forhindre injeksjon av skadelige minner gjennom innholdsrensing, kildeverifisering og integritetskontroller før lagring.                                           |   2   | D/V  |
| 8.6.3 | Bekreft at spørringer for minnehenting blir validert og renset for å forhindre uttak av uautorisert informasjon gjennom analyse av spørringsmønstre, håndheving av tilgangskontroll og filtrering av resultater.                                 |   2   | D/V  |
| 8.6.4 | Bekreft at hukommelsesglemmingsmekanismer sikkert sletter sensitiv informasjon med kryptografiske slettingsgarantier ved hjelp av nøkkelsletting, flerpassert overskriving eller maskinvarebasert sikker sletting med verifiseringssertifikater. |   3   | D/V  |
| 8.6.5 | Bekreft at minnesystemets integritet kontinuerlig overvåkes for uautoriserte endringer eller korrupsjon gjennom kontrollsummer, revisjonslogger og automatiserte varsler når minneinnhold endres utenfor normale operasjoner.                    |   3   | D/V  |

---

## Referanser

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

