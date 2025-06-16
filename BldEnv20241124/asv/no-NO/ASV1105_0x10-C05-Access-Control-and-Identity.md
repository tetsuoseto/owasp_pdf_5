# C5 Tilgangskontroll og identitet for AI-komponenter og brukere

## Kontrollmål

Effektiv tilgangskontroll for AI-systemer krever robust identitetsstyring, kontekstbevisst autorisasjon og håndheving i sanntid i samsvar med prinsippene for nulltillit. Disse kontrollene sikrer at mennesker, tjenester og autonome agenter kun samhandler med modeller, data og beregningsressurser innenfor uttrykkelig tildelte områder, med kontinuerlig verifisering og revisjonsmuligheter.

---

## C5.1 Identitetsstyring og autentisering

Etabler kryptografisk sikrede identiteter for alle enheter med multifaktorautentisering for privilegerte operasjoner.

|   #   | Description                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.1.1 | Bekreft at alle menneskelige brukere og tjenesteprinsipper autentiserer gjennom en sentralisert bedriftsidentitetsleverandør (IdP) ved bruk av OIDC/SAML-protokoller med unike identitet-til-token-kartlegginger (ingen delte kontoer eller legitimasjoner). |   1   | D/V  |
| 5.1.2 | Verifiser at høy-risiko operasjoner (modellutplassering, eksport av vekter, tilgang til treningsdata, endringer i produksjonskonfigurasjon) krever flerfaktorautentisering eller trinnvis autentisering med sesjonsrevalidering.                             |   1   | D/V  |
| 5.1.3 | Bekreft at nye ledere gjennomgår identitetsverifisering i samsvar med NIST 800-63-3 IAL-2 eller tilsvarende standarder før de får tilgang til produksjonssystemet.                                                                                           |   2   |  D   |
| 5.1.4 | Bekreft at tilgangsvurderinger gjennomføres kvartalsvis med automatisk deteksjon av inaktive kontoer, håndheving av legitimasjonsrotasjon og arbeidsflyter for avvikling av tilganger.                                                                       |   2   |  V   |
| 5.1.5 | Bekreft at fødererte AI-agenter autentiserer via signerte JWT-påstander som har en maksimal levetid på 24 timer og inkluderer kryptografisk bevis på opprinnelse.                                                                                            |   3   | D/V  |

---

## C5.2 Ressursautorisasjon og minst privilegium

Implementer detaljerte tilgangskontroller for alle AI-ressurser med eksplisitte rettighetsmodeller og revisjonsspor.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Bekreft at alle AI-ressurser (datasett, modeller, endepunkter, vektorsamlinger, innebygde indekser, databehandlingsinstanser) håndhever rollebaserte tilgangskontroller med eksplisitte tillatelseslister og standard-avvisningsregler. |   1   | D/V  |
| 5.2.2 | Verifiser at prinsippene for minst privilegium håndheves som standard for tjenestekontoer, med start i lese-only tillatelser og dokumentert forretningsbegrunnelse kreves for skrivetilgang.                                            |   1   | D/V  |
| 5.2.3 | Bekreft at alle endringer i tilgangskontroll er knyttet til godkjente endringsforespørsler og loggført uforanderlig med tidsstempler, aktøridentiteter, ressursidentifikatorer og tillatelsesendringer.                                 |   1   |  V   |
| 5.2.4 | Bekreft at dataklassifiseringsetiketter (PII, PHI, eksportkontrollert, proprietær) automatisk overføres til avledede ressurser (innebygde data, prompt-cacher, modellutdata) med konsekvent håndhevelse av retningslinjer.              |   2   |  D   |
| 5.2.5 | Bekreft at uautoriserte tilgangsforsøk og hendelser med privilegieeskalering utløser sanntidsvarsler med kontekstuell metadata til SIEM-systemer innen 5 minutter.                                                                      |   2   | D/V  |

---

## C5.3 Dynamisk policyevaluering

Distribuer attributtbaserte tilgangskontrollmotorer (ABAC) for kontekstbevisste autorisasjonsbeslutninger med revisjonsmuligheter.

|   #   | Description                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Bekreft at autorisasjonsbeslutninger er eksternalisert til en dedikert policy-motor (OPA, Cedar eller tilsvarende) tilgjengelig via autentiserte API-er med kryptografisk integritetsbeskyttelse.                   |   1   | D/V  |
| 5.3.2 | Bekreft at policyer evaluerer dynamiske attributter ved kjøretid, inkludert brukerens klareringsnivå, ressursens sensitivitetklassifisering, forespørselskontekst, leietakerisolasjon og tidsmessige begrensninger. |   1   | D/V  |
| 5.3.3 | Bekreft at policydefinisjoner er versjonskontrollerte, fagfellevurderte og validert gjennom automatisert testing i CI/CD-pipelines før produksjonsutrulling.                                                        |   2   |  D   |
| 5.3.4 | Verifiser at resultatene av policyvurderinger inkluderer strukturerte beslutningsbegrunnelser og overføres til SIEM-systemer for korrelasjonsanalyse og samsvarsrapportering.                                       |   2   |  V   |
| 5.3.5 | Verifiser at policyens hurtigbuffer leve tid (TTL) ikke overstiger 5 minutter for høysensitive ressurser og 1 time for standardressurser med muligheter for hurtigbufferinvalidering.                               |   3   | D/V  |

---

## C5.4 Sikkerhetskontroll ved spørringstidspunktet

Implementer sikkerhetskontroller på databaselaget med obligatorisk filtrering og sikkerhetspolicyer på radnivå.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Sørg for at alle spørringer mot vektordatabaser og SQL inkluderer obligatoriske sikkerhetsfiltre (leietaker-ID, sensitivitetsetiketter, brukeromfang) som håndheves på databasmotornivå, ikke i applikasjonskoden.                |   1   | D/V  |
| 5.4.2 | Verifiser at retningslinjer for radnivåsikkerhet (RLS) og feltnivåmaskering er aktivert med policyarv for alle vektordatabaser, søkeindekser og treningsdatasett.                                                                 |   1   | D/V  |
| 5.4.3 | Bekreft at mislykkede autorisasjonsvurderinger vil forhindre "forvirret stedfortreder-angrep" ved umiddelbart å avbryte forespørsler og returnere eksplisitte autorisasjonsfeilkoder i stedet for å returnere tomme resultatsett. |   2   |  D   |
| 5.4.4 | Bekreft at evaluering av policy-latenstid kontinuerlig overvåkes med automatiske varsler for tidsavbruddsbetingelser som kan muliggjøre omgåring av autorisasjon.                                                                 |   2   |  V   |
| 5.4.5 | Bekreft at mekanismer for forsøk på nytt av spørringer revurderer autorisasjonspolicyer for å ta hensyn til dynamiske endringer i tillatelser innen aktive brukersesjoner.                                                        |   3   | D/V  |

---

## C5.5 Utdatafiltrering og datatapforebygging

Implementer etterbehandlingskontroller for å forhindre uautorisert datalekkasjer i AI-generert innhold.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Verifiser at filtreringsmekanismer etter inferens skanner og fjerner uautorisert personlig identifiserbar informasjon (PII), klassifisert informasjon og proprietære data før innhold leveres til forespørslere. |   1   | D/V  |
| 5.5.2 | Bekreft at henvisninger, referanser og kildeangivelser i modellresultater er validert mot anroperens rettigheter, og fjernes hvis uautorisert tilgang oppdages.                                                  |   1   | D/V  |
| 5.5.3 | Bekreft at restriksjoner for utdataformat (rengjorte PDF-filer, metadata-frie bilder, godkjente filtyper) håndheves basert på brukerens tillatelsesnivåer og dataklassifiseringer.                               |   2   |  D   |
| 5.5.4 | Sørg for at redigeringsalgoritmer er deterministiske, versjonskontrollerte og opprettholder revisjonslogger for å støtte samsvarsetterforskninger og rettsmedisinsk analyse.                                     |   2   |  V   |
| 5.5.5 | Bekreft at høy-risiko redigeringshendelser genererer adaptive logger som inkluderer kryptografiske hashverdier av originalt innhold for rettsmedisinsk gjenfinning uten datalekkasjer.                           |   3   |  V   |

---

## C5.6 Multi-leietakerisolasjon

Sikre kryptografisk og logisk isolasjon mellom leietakere i delt AI-infrastruktur.

|   #   | Description                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Verifiser at minneområder, innebygde lagre, hurtigbufferoppføringer og midlertidige filer er adskilt per leietaker med sikker sletting ved sletting av leietaker eller avslutning av økt. |   1   | D/V  |
| 5.6.2 | Verifiser at hver API-forespørsel inkluderer en autentisert leietakeridentifikator som er kryptografisk validert mot sesjonskontekst og brukerrettigheter.                                |   1   | D/V  |
| 5.6.3 | Bekreft at nettverkspolitikker implementerer standard-nekt regler for kommunikasjon på tvers av leietakere innen tjenestenettverk og plattformer for containerorkestrering.               |   2   |  D   |
| 5.6.4 | Bekreft at krypteringsnøkler er unike per leietaker med kundeadministrert nøkkel (CMK)-støtte og kryptografisk isolasjon mellom leietakers datalagre.                                     |   3   |  D   |

---

## C5.7 Autonom agentgodkjenning

Kontroller tillatelser for AI-agenter og autonome systemer gjennom avgrensede kapabilitetstokener og kontinuerlig autorisasjon.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Bekreft at autonome agenter mottar begrensede kapabilitetstokener som eksplisitt angir tillatte handlinger, tilgjengelige ressurser, tidsrammer og driftsbegrensninger.                                                                |   1   | D/V  |
| 5.7.2 | Bekreft at høy-risiko funksjoner (tilgang til filsystem, kodekjøring, eksterne API-kall, finansielle transaksjoner) er deaktivert som standard og krever eksplisitte godkjenninger for aktivering med forretningsmessige begrunnelser. |   1   | D/V  |
| 5.7.3 | Bekreft at kapabilitetstokener er knyttet til brukersesjoner, inkluderer kryptografisk integritetsbeskyttelse, og sikre at de verken kan lagres eller gjenbrukes i frakoblede situasjoner.                                             |   2   |  D   |
| 5.7.4 | Bekreft at agent-initierte handlinger gjennomgår sekundær godkjenning via ABAC-policy-motoren med full kontekstevaluering og revisjonslogging.                                                                                         |   2   |  V   |
| 5.7.5 | Bekreft at agentfeilbetingelser og unntakshåndtering inkluderer informasjon om kapabilitetsomfang for å støtte hendelsesanalyse og rettsmedisinsk etterforskning.                                                                      |   3   |  V   |

---

## Referanser

### Standarder og rammeverk

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Implementasjonsveiledninger

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### AI-spesifikk sikkerhet

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

