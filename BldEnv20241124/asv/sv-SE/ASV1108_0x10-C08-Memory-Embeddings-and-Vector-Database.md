# C8-minne, inbäddningar och säkerhet för vektordatabaser

## Kontrollmål

Embeddingar och vektorlager fungerar som den "levande minnet" i moderna AI-system, som kontinuerligt tar emot användargenererad data och återför den till modellkontexter via Retrieval-Augmented Generation (RAG). Om detta minne lämnas oreglerat kan det läcka personligt identifierbar information (PII), bryta mot samtycke eller inverteras för att återskapa originaltexten. Syftet med denna kontrollfamilj är att förstärka minnespipelines och vektordatabaser så att åtkomst sker med minsta möjliga behörighet, embeddingar bevarar integriteten, lagrade vektorer upphör att gälla eller kan återkallas på begäran, och att minne per användare aldrig förorenar en annan användares prompts eller genererade svar.

---

## C8.1 Åtkomstkontroller för minne och RAG-index

Tillämpa detaljerade åtkomstkontroller på varje vektorsamling.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.1.1 | Verifiera att åtkomstkontrollregler på rad-/namnrymdsnivå begränsar insättnings-, raderings- och frågeoperationer per hyresgäst, samling eller dokumenttagg. |   1   | D/V  |
| 8.1.2 | Verifiera att API-nycklar eller JWT:er innehåller avgränsade påståenden (t.ex. samlings-ID:n, åtgärdsverb) och roteras minst kvartalsvis.                    |   1   | D/V  |
| 8.1.3 | Verifiera att försök till privilegieupptrappning (t.ex. likhetsfrågor över olika namnrymder) upptäcks och loggas till en SIEM inom 5 minuter.                |   2   | D/V  |
| 8.1.4 | Verifiera att vektor-DB granskar loggarna för ämnesidentifierare, operation, vektor-ID/namnrymd, likhetströskel och resultatantal.                           |   2   | D/V  |
| 8.1.5 | Verifiera att åtkomstbeslut testas för omgångsfel när motorer uppgraderas eller regler för index-sharding ändras.                                            |   3   |  V   |

---

## C8.2 Inbäddningssanering och validering

Förhandsgranska texten för personligt identifierbar information (PII), ta bort eller pseudonymisera innan vektorisering, och bearbeta eventuellt inbäddningarna i efterhand för att ta bort kvarvarande signaler.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Verifiera att PII och reglerade data upptäcks via automatiska klassificerare och maskeras, tokeniseras eller tas bort före inbäddning.                                                          |   1   | D/V  |
| 8.2.2 | Verifiera att inbäddningspipelines avvisar eller isolerar indata som innehåller exekverbara koder eller icke-UTF-8-artifakter som kan förorena indexet.                                         |   1   |  D   |
| 8.2.3 | Verifiera att lokal eller metrisk differentierad sekretess-sanitization tillämpas på meningsembeddingar vars avstånd till någon känd PII-token understiger en konfigurerbar tröskel.            |   2   | D/V  |
| 8.2.4 | Verifiera att effektiviteten i saneringen (t.ex. återkallelse av borttagning av personligt identifierbar information, semantisk förskjutning) valideras minst halvårsvis mot referenssamlingar. |   2   |  V   |
| 8.2.5 | Verifiera att saneringskonfigurationer är versionskontrollerade och att ändringar genomgår granskning av kollegor.                                                                              |   3   | D/V  |

---

## C8.3 Minnesutgång, återkallande och radering

GDPR:s "rätt att bli glömd" och liknande lagar kräver snabb radering; vektorlager måste därför stödja TTL (time-to-live), hårda borttagningar och tomb-stoning så att återkallade vektorer inte kan återställas eller indexeras igen.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Verifiera att varje vektor- och metadata post har en TTL eller en explicit kvarhållningsetikett som efterföljs av automatiska rensningsjobb.                        |   1   | D/V  |
| 8.3.2 | Verifiera att användarinitierade raderingsförfrågningar raderar vektorer, metadata, cachekopior och härledda index inom 30 dagar.                                   |   1   | D/V  |
| 8.3.3 | Verifiera att logiska borttagningar följs av kryptografisk utsuddning av lagringsblock om hårdvaran stödjer det, eller genom förstörelse av nycklar i nyckelvalvet. |   2   |  D   |
| 8.3.4 | Verifiera att utgångna vektorer utesluts från närmaste granne-sökresultat inom < 500 ms efter utgången.                                                             |   3   | D/V  |

---

## C8.4 Förhindra inbäddningsinversion och läckage

Nya försvar—överlagring av brus, projektionnätverk, störning av integritetsneuroner och applikationslagerskryptering—kan sänka inverteringsfrekvensen på token-nivå till under 5%.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Verifiera att en formell hotmodell som täcker inversion, medlemskaps- och attributinferensattacker finns och granskas årligen.                            |   1   |  V   |
| 8.4.2 | Verifiera att applikationslagskryptering eller sökbar kryptering skyddar vektorer från direkt läsning av infrastrukturadministratörer eller molnpersonal. |   2   | D/V  |
| 8.4.3 | Verifiera att försvarsparametrarna (ε för DP, brus σ, projektion rank k) balanserar integritet ≥ 99 % tokenskydd och nytta ≤ 3 % precisionstapp.          |   3   |  V   |
| 8.4.4 | Verifiera att metrics för inversionsresiliens ingår i släppvillkor för modelluppdateringar, med definierade regressionsbudgetar.                          |   3   | D/V  |

---

## C8.5 Omfångsbegränsning för användarspecifikt minne

Läckage mellan olika hyresgäster är fortfarande en av de största riskerna med RAG: felaktigt filtrerade likhetsfrågor kan avslöja en annan kunds privata dokument.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Verifiera att varje hämtförfrågan filtreras efter hyresgäst-/användar-ID innan den skickas vidare till LLM-prompten.                                          |   1   | D/V  |
| 8.5.2 | Verifiera att samlingsnamn eller namngivna ID:n är salterade per användare eller hyresgäst så att vektorer inte kan kollidera över olika områden.             |   1   |  D   |
| 8.5.3 | Verifiera att likhetsresultat över en konfigurerbar avståndströskel men utanför anroparens räckvidd förkastas och utlöser säkerhetsvarningar.                 |   2   | D/V  |
| 8.5.4 | Verifiera att stress tester för multi-tenant simulerar motståndskraftiga förfrågningar som försöker hämta dokument utanför räckvidden och visar noll läckage. |   2   |  V   |
| 8.5.5 | Verifiera att krypteringsnycklar är åtskilda per hyresgäst, vilket säkerställer kryptografisk isolering även om fysisk lagring delas.                         |   3   | D/V  |

---

## C8.6 Avancerad säkerhet för minnessystem

Säkerhetskontroller för sofistikerade minnesarkitekturer inklusive episodiskt, semantiskt och arbetsminne med specifika isolerings- och valideringskrav.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.6.1 | Verifiera att olika minnestyper (episodiskt, semantiskt, arbetsminne) har isolerade säkerhetskontexter med rollbaserade åtkomstkontroller, separata krypteringsnycklar och dokumenterade åtkomstmönster för varje minnestyp.                                       |   1   | D/V  |
| 8.6.2 | Verifiera att minneskonsolideringsprocesser inkluderar säkerhetsvalidering för att förhindra injektion av skadliga minnen genom innehållsrensning, källverifiering och integritetskontroller innan lagring.                                                        |   2   | D/V  |
| 8.6.3 | Verifiera att minnesåtervinningsfrågor valideras och saneras för att förhindra extrahering av obehörig information genom analys av frågemönster, upprätthållande av åtkomstkontroll och filtrering av resultat.                                                    |   2   | D/V  |
| 8.6.4 | Verifiera att minnesutglömningsmekanismer säkerställer att känslig information raderas på ett säkert sätt med kryptografiska raderingsgarantier genom nyckelborttagning, flerpassetsöverskrivning eller hårdvarubaserad säker radering med verifieringscertifikat. |   3   | D/V  |
| 8.6.5 | Verifiera att minnessystemets integritet kontinuerligt övervakas för obehöriga ändringar eller korruption genom kontrollsummor, revisionsloggar och automatiska varningar när minnesinnehållet ändras utanför normala operationer.                                 |   3   | D/V  |

---

## Referenser

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

