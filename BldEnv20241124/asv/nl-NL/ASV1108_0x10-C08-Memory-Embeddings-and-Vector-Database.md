# C8 Geheugen, Embeddings en Beveiliging van Vector Databases

## Beheersdoelstelling

Embeddings en vectoropslag fungeren als het "levende geheugen" van hedendaagse AI-systemen, waarbij ze continu door gebruikers aangeleverde gegevens accepteren en deze via Retrieval-Augmented Generation (RAG) terug in modelcontexten brengen. Als dit geheugen niet wordt beheerst, kan het leiden tot het lekken van persoonlijke identificeerbare informatie (PII), het schenden van toestemming of het omkeren om de oorspronkelijke tekst te reconstrueren. Het doel van deze controlegroep is het beveiligen van geheugensystemen en vectordatabases zodat de toegang het minste privilege heeft, embeddings privacybeschermend zijn, opgeslagen vectoren vervallen of op verzoek kunnen worden ingetrokken, en dat het geheugen per gebruiker nooit de prompts of voltooingen van een andere gebruiker besmet.

---

## C8.1 Toegangscontroles op geheugen en RAG-indexen

Handhaaf fijnmazige toegangscontroles op elke vectorverzameling.

|   #   | Description                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Controleer of regels voor toegangsbeheer op rij-/namespace-niveau de invoeg-, verwijder- en querybewerkingen beperken per huurder, collectie of documentlabel.          |   1   | D/V  |
| 8.1.2 | Controleer of API-sleutels of JWT's gescoorde claims bevatten (bijv. collectie-ID's, actie-werkwoorden) en minimaal elk kwartaal worden geroteerd.                      |   1   | D/V  |
| 8.1.3 | Verifieer dat pogingen tot privilege-escalatie (bijvoorbeeld vergelijkingsqueries tussen namespaces) binnen 5 minuten worden gedetecteerd en geregistreerd in een SIEM. |   2   | D/V  |
| 8.1.4 | Controleer of de vector DB audits de onderwerpidentifier, bewerking, vector ID/namespace, gelijkenisdrempel en resultaatcount loggen.                                   |   2   | D/V  |
| 8.1.5 | Controleer of toegangsbeslissingen worden getest op omzeilingsfouten telkens wanneer engines worden geüpgraded of index-shardingregels worden gewijzigd.                |   3   |  V   |

---

## C8.2 Insluitingssanering en validatie

Vooraf de tekst op PII controleren, anonimiseren of pseudonimiseren voor vectorisatie, en indien gewenst de embeddings nabewerken om resterende signalen te verwijderen.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Controleer of PII en gereguleerde gegevens worden gedetecteerd via geautomatiseerde classificatiesystemen en voorafgaand aan embedding worden gemaskeerd, getokeniseerd of verwijderd.   |   1   | D/V  |
| 8.2.2 | Controleer of embedding-pijplijnen invoer die uitvoerbare code of niet-UTF-8-artifacten bevat, die de index kunnen besmetten, afwijzen of in quarantaine plaatsen.                       |   1   |  D   |
| 8.2.3 | Controleer of lokale of metrische differentiële privacy-sanering wordt toegepast op zinsem-beddings waarvan de afstand tot een bekende PII-token onder een configureerbare drempel ligt. |   2   | D/V  |
| 8.2.4 | Verifieer dat de doeltreffendheid van sanering (bijvoorbeeld recall van PII-redactie, semantische drift) ten minste halfjaarlijks wordt gevalideerd aan de hand van benchmarkcorpora.    |   2   |  V   |
| 8.2.5 | Controleer of saneringsconfiguraties versiebeheerd zijn en of wijzigingen een peer review ondergaan.                                                                                     |   3   | D/V  |

---

## C8.3 Geheugenverval, Intrekking & Verwijdering

GDPR "recht om vergeten te worden" en soortgelijke wetten vereisen tijdige verwijdering; vectoropslag moet daarom TTL's, harde verwijderingen en tombstoning ondersteunen zodat ingetrokken vectoren niet kunnen worden hersteld of opnieuw geïndexeerd.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Controleer of elk vector- en metagegevensrecord een TTL of expliciet bewaarbeleid bevat dat wordt gerespecteerd door geautomatiseerde opruimwerkzaamheden.                               |   1   | D/V  |
| 8.3.2 | Verifieer dat door de gebruiker geïnitieerde verwijderingsverzoeken vectoren, metadata, cachekopieën en afgeleide indexen binnen 30 dagen verwijderen.                                   |   1   | D/V  |
| 8.3.3 | Controleer of logische verwijderingen worden gevolgd door cryptografisch wissen van opslagblokken als de hardware dat ondersteunt, of door vernietiging van sleutels in de sleutelkluis. |   2   |  D   |
| 8.3.4 | Controleer of verlopen vectoren binnen < 500 ms na verval zijn uitgesloten van de resultaten van de dichtstbijzijnde-buurzoektocht.                                                      |   3   | D/V  |

---

## C8.4 Voorkom Inversie en Lekken van Embeddings

Recente verdedigingsmethoden—zoals ruisopsomming, projectienetwerken, perturbatie van privacyneuronen en versleuteling op applicatielaag—kunnen token-niveau inversieratio's onder de 5% brengen.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Controleer of er een formeel dreigingsmodel bestaat dat omkering, lidmaatschaps- en attribuut-inferentie-aanvallen omvat en jaarlijks wordt herzien.                               |   1   |  V   |
| 8.4.2 | Controleer of applicatielaagversleuteling of doorzoekbare encryptie vectoren beschermt tegen directe uitlezing door infrastructuurbeheerders of cloudpersoneel.                    |   2   | D/V  |
| 8.4.3 | Controleer of de verdedigingsparameters (ε voor DP, ruis σ, projectierang k) een balans vinden tussen privacy ≥ 99% tokenbescherming en bruikbaarheid ≤ 3% nauwkeurigheidsverlies. |   3   |  V   |
| 8.4.4 | Verifieer dat omkeerbestendigheidsmetingen deel uitmaken van release-poorten voor modelupdates, met gedefinieerde regressiebudgetten.                                              |   3   | D/V  |

---

## C8.5 Toepassing van bereikbeperking voor gebruikersspecifiek geheugen

Cross-tenant lekkage blijft een groot risico bij RAG: onjuist gefilterde gelijkenisquery's kunnen privédocumenten van een andere klant aan het licht brengen.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Verifieer dat elke ophaalquery wordt nabehandeld met tenant-/gebruikers-ID voordat deze aan de LLM-prompt wordt doorgegeven.                                                                |   1   | D/V  |
| 8.5.2 | Controleer of collectienamen of genamespaceerde ID's per gebruiker of huurder gezouten zijn zodat vectoren niet kunnen botsen tussen verschillende scopes.                                  |   1   |  D   |
| 8.5.3 | Controleer of gelijkenisresultaten boven een configureerbare afstandsdrempel, maar buiten de scope van de aanroeper, worden verworpen en beveiligingswaarschuwingen veroorzaken.            |   2   | D/V  |
| 8.5.4 | Controleer of multi-tenant stresstests adversariële queries simuleren die proberen documenten buiten de toegestane scope op te halen en toon aan dat er geen informatielekkage plaatsvindt. |   2   |  V   |
| 8.5.5 | Verifieer dat encryptiesleutels per huurder gescheiden zijn, waardoor cryptografische isolatie wordt gegarandeerd, zelfs als de fysieke opslag gedeeld wordt.                               |   3   | D/V  |

---

## C8.6 Geavanceerde beveiliging van geheugensystemen

Beveiligingsmaatregelen voor geavanceerde geheugenarchitecturen, inclusief episodisch, semantisch en werkgeheugen, met specifieke isolatie- en validatievereisten.

|   #   | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.6.1 | Verifieer dat verschillende geheugentypen (episodisch, semantisch, werkgeheugen) geïsoleerde beveiligingscontexten hebben met op rollen gebaseerde toegangscontrole, aparte encryptiesleutels en gedocumenteerde toegangsmodellen voor elk geheugentype.                       |   1   | D/V  |
| 8.6.2 | Controleer of processen voor geheugenconsolidatie beveiligingsvalidatie omvatten om de injectie van kwaadaardige herinneringen te voorkomen via inhoudssanering, bronverificatie en integriteitscontroles vóór opslag.                                                         |   2   | D/V  |
| 8.6.3 | Controleer of geheugenophaalqueries worden gevalideerd en gesaneerd om te voorkomen dat ongeautoriseerde informatie wordt verkregen via analyse van querypatronen, handhaving van toegangscontrole en filtering van resultaten.                                                |   2   | D/V  |
| 8.6.4 | Controleer of geheugenvergeetmechanismen gevoelige informatie veilig wissen met cryptografische verwijderingsgaranties door middel van sleuteldeletie, meervoudig overschrijven of hardware-gebaseerde beveiligde verwijdering met verificatiecertificaten.                    |   3   | D/V  |
| 8.6.5 | Controleer of de integriteit van het geheugensysteem continu wordt gecontroleerd op ongeautoriseerde wijzigingen of corruptie door middel van checksums, auditlogs en geautomatiseerde waarschuwingen wanneer de inhoud van het geheugen buiten normale bewerkingen verandert. |   3   | D/V  |

---

## Referenties

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

