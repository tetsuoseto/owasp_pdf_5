# C5 Toegangscontrole en Identiteit voor AI-componenten en Gebruikers

## Controle Doelstelling

Effectieve toegangscontrole voor AI-systemen vereist robuust identiteitsbeheer, contextbewuste autorisatie en runtime-handhaving volgens zero-trustprincipes. Deze controles zorgen ervoor dat mensen, diensten en autonome agenten alleen interactie hebben met modellen, data en computationele middelen binnen expliciet toegekende reikwijdtes, met voortdurende verificatie- en auditmogelijkheden.

---

## C5.1 Identiteitsbeheer & Authenticatie

Stel cryptografisch ondersteunde identiteiten vast voor alle entiteiten met multi-factor authenticatie voor bevoorrechte operaties.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Verifieer dat alle menselijke gebruikers en serviceprincipals zich authenticeren via een gecentraliseerde enterprise identity provider (IdP) met behulp van OIDC/SAML-protocollen met unieke identiteit-naar-token mappings (geen gedeelde accounts of referenties). |   1   | D/V  |
| 5.1.2 | Verifieer dat hoogrisico-operaties (modelimplementatie, gewichtsexport, toegang tot trainingsgegevens, wijzigingen in productieconfiguraties) multi-factorauthenticatie of stap-omhoog authenticatie met sessieherverificatie vereisen.                              |   1   | D/V  |
| 5.1.3 | Verifieer dat nieuwe leidinggevenden een identiteitsverificatie ondergaan die overeenkomt met NIST 800-63-3 IAL-2 of gelijkwaardige normen voordat zij toegang krijgen tot het productiesysteem.                                                                     |   2   |  D   |
| 5.1.4 | Controleer of toegangsbeoordelingen elk kwartaal worden uitgevoerd met geautomatiseerde detectie van inactieve accounts, afdwinging van het wijzigen van inloggegevens en workflows voor het deactiveren van accounts.                                               |   2   |  V   |
| 5.1.5 | Controleer of federatieve AI-agenten zich authenticeren via ondertekende JWT-verklaringen die een maximale levensduur van 24 uur hebben en cryptografisch bewijs van oorsprong bevatten.                                                                             |   3   | D/V  |

---

## C5.2 Middelenautorisatie & Minst Bevoorrechte Toegang

Implementeer fijnmazige toegangscontroles voor alle AI-bronnen met expliciete toestemmingsmodellen en auditsporen.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Verifieer dat elke AI-bron (datasets, modellen, eindpunten, vectorverzamelingen, embedding-indexen, rekeninstanties) rolgebaseerde toegangscontroles afdwingt met expliciete toestaanlijsten en beleid voor standaard weigering. |   1   | D/V  |
| 5.2.2 | Controleer of het minste-privilegeprincipe standaard wordt gehandhaafd voor serviceaccounts, beginnend met alleen-lezen machtigingen en met gedocumenteerde zakelijke rechtvaardiging die vereist is voor schrijf-toegang.       |   1   | D/V  |
| 5.2.3 | Verifieer dat alle wijzigingen in toegangscontrole gekoppeld zijn aan goedgekeurde wijzigingsverzoeken en onveranderlijk worden vastgelegd met tijdstempels, actorgegevens, resource-identificaties en permissieverschillen.     |   1   |  V   |
| 5.2.4 | Controleer of dataclassificatielabels (PII, PHI, exportbeperkt, eigendom) automatisch worden doorgegeven aan afgeleide bronnen (embeddings, promptcaches, modeluitvoer) met consistente beleidsafhandeling.                      |   2   |  D   |
| 5.2.5 | Verifieer dat pogingen tot ongeautoriseerde toegang en gebeurtenissen van privilege-escalatie real-time waarschuwingen met contextuele metadata naar SIEM-systemen binnen 5 minuten activeren.                                   |   2   | D/V  |

---

## C5.3 Dynamische Beleidsevaluatie

Implementeer op attributen gebaseerde toegangscontrole (ABAC) systemen voor contextbewuste autorisatiebeslissingen met auditmogelijkheden.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Verifieer dat autorisatiebeslissingen worden uitbesteed aan een toegewijde beleidsmotor (OPA, Cedar of gelijkwaardig) die toegankelijk is via geauthenticeerde API's met cryptografische integriteitsbeveiliging.                                 |   1   | D/V  |
| 5.3.2 | Controleer of beleidsregels dynamische attributen evalueren tijdens runtime, inclusief het beveiligingsniveau van de gebruiker, de gevoeligheidsclassificatie van de bron, de context van het verzoek, tenant-isolatie en tijdelijke beperkingen. |   1   | D/V  |
| 5.3.3 | Verifieer dat beleidsdefinities versiebeheerd, peer-reviewed en gevalideerd zijn door middel van geautomatiseerde tests in CI/CD-pijplijnen voordat ze in productie worden uitgerold.                                                             |   2   |  D   |
| 5.3.4 | Verifieer dat de beoordeling van het beleid gestructureerde besluitvormingsmotieven bevat en wordt verzonden naar SIEM-systemen voor correlatieanalyse en nalevingsrapportage.                                                                    |   2   |  V   |
| 5.3.5 | Controleer of de time-to-live (TTL)-waarden van het beleidscache de 5 minuten niet overschrijden voor hooggevoelige bronnen en 1 uur voor standaardbronnen met cache-invalideringsmogelijkheden.                                                  |   3   | D/V  |

---

## C5.4 Handhaving van beveiliging tijdens query-uitvoering

Implementeer beveiligingscontroles op databaselaagniveau met verplichte filtering en rijniveaubeveiligingsbeleid.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.4.1 | Controleer of alle vector database- en SQL-query's verplichte beveiligingsfilters bevatten (tenant-ID, gevoeligheidslabels, gebruikersscope) die worden afgedwongen op het niveau van de database-engine, niet in de applicatiecode. |   1   | D/V  |
| 5.4.2 | Controleer of rijniveau-beveiligingsbeleid (RLS) en veldniveau-maskering zijn ingeschakeld met beleids-erfenis voor alle vectordatabases, zoekindices en trainingsdatasets.                                                          |   1   | D/V  |
| 5.4.3 | Verifieer dat mislukte autorisatiebeoordelingen "confused deputy-aanvallen" voorkomen door queries onmiddellijk af te breken en expliciete autorisatiefoutcodes terug te geven in plaats van lege resultaatsets.                     |   2   |  D   |
| 5.4.4 | Controleer of de beleidsbeoordelingslatentie continu wordt gemonitord met automatische waarschuwingen voor time-outcondities die een autorisatieomzeiling mogelijk zouden maken.                                                     |   2   |  V   |
| 5.4.5 | Controleer of query-herstartmechanismen autorisatiebeleid opnieuw evalueren om rekening te houden met dynamische wijzigingen in machtigingen binnen actieve gebruikerssessies.                                                       |   3   | D/V  |

---

## C5.5 Uitvoerfiltering & Voorkoming van Gegevensverlies

Implementeer post-processing controles om ongeautoriseerde blootstelling van gegevens in AI-gegenereerde inhoud te voorkomen.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Verifieer dat post-inferentie filtermechanismen onbevoegde PII, geclassificeerde informatie en propriëtaire gegevens scannen en redigeren voordat de inhoud aan verzoekers wordt geleverd.                            |   1   | D/V  |
| 5.5.2 | Controleer of citaties, verwijzingen en bronvermeldingen in modeluitvoer worden geverifieerd aan de hand van de toegangsrechten van de aanroeper en verwijder ze indien onbevoegde toegang wordt vastgesteld.         |   1   | D/V  |
| 5.5.3 | Controleer of beperkingen voor outputformaten (gesaniteerde PDF's, metadata-verwijderde afbeeldingen, goedgekeurde bestandstypen) worden gehandhaafd op basis van gebruikersmachtigingsniveaus en dataclassificaties. |   2   |  D   |
| 5.5.4 | Controleer of redactiesoftware deterministisch is, versiebeheer heeft en auditlogs bijhoudt om nalevingsonderzoeken en forensische analyses te ondersteunen.                                                          |   2   |  V   |
| 5.5.5 | Controleer of redactiemomenten met hoog risico adaptieve logs genereren die cryptografische hashes van de oorspronkelijke inhoud bevatten voor forensische terugvinding zonder dat er gegevens worden blootgesteld.   |   3   |  V   |

---

## C5.6 Multi-Tenant Isolatie

Zorg voor cryptografische en logische isolatie tussen huurders in gedeelde AI-infrastructuur.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.6.1 | Controleer of geheugenruimten, embedding-opslagplaatsen, cache-items en tijdelijke bestanden per tenant gescheiden zijn op naamruimte, met veilige verwijdering bij het verwijderen van een tenant of het beëindigen van een sessie. |   1   | D/V  |
| 5.6.2 | Verifieer dat elke API-aanvraag een geauthentificeerde tenant-identificatie bevat die cryptografisch wordt gevalideerd aan de hand van de sessiecontext en gebruikersrechten.                                                        |   1   | D/V  |
| 5.6.3 | Controleer of netwerkbeleid standaard-weigerregels implementeert voor communicatie tussen tenants binnen servicenetwerken en containerorkestratieplatforms.                                                                          |   2   |  D   |
| 5.6.4 | Controleer of encryptiesleutels uniek zijn per huurder met ondersteuning voor door de klant beheerde sleutels (CMK) en cryptografische isolatie tussen gegevensopslagplaatsen van huurders.                                          |   3   |  D   |

---

## C5.7 Autonome Agentautorisatie

Beheer machtigingen voor AI-agenten en autonome systemen via gespecificeerde capaciteits-tokens en voortdurende autorisatie.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Controleer of autonome agenten gescopeerde bevoegdheidstokens ontvangen die expliciet de toegestane acties, toegankelijke bronnen, tijdsbeperkingen en operationele beperkingen opsommen.                                                                  |   1   | D/V  |
| 5.7.2 | Controleer of hoogrisico-mogelijkheden (toegang tot het bestandssysteem, code-uitvoering, externe API-aanroepen, financiële transacties) standaard zijn uitgeschakeld en expliciete goedkeuringen vereisen voor activatie met zakelijke rechtvaardigingen. |   1   | D/V  |
| 5.7.3 | Verifieer dat capaciteits tokens gebonden zijn aan gebruikerssessies, cryptografische integriteitsbescherming bevatten, en zorg ervoor dat ze niet kunnen worden opgeslagen of hergebruikt in offline scenario's.                                          |   2   |  D   |
| 5.7.4 | Verifieer dat door agent geïnitieerde acties een secundaire autorisatie ondergaan via de ABAC-beleidsmotor met volledige contextevaluatie en auditlogging.                                                                                                 |   2   |  V   |
| 5.7.5 | Controleer of foutcondities van agenten en uitzonderingsafhandeling informatie over het capaciteitsbereik bevatten om incidentanalyse en forensisch onderzoek te ondersteunen.                                                                             |   3   |  V   |

---

## Referenties

### Normen & Kaders

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Implementatiehandleidingen

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### AI-specifieke beveiliging

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

