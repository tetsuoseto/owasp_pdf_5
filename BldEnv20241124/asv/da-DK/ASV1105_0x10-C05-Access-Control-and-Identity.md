# C5 Adgangskontrol og identitet for AI-komponenter og brugere

## Kontrolmål

Effektiv adgangskontrol for AI-systemer kræver robust identitetsstyring, kontekstbevidst autorisation og håndhævelse under kørsel i overensstemmelse med principperne for zero-trust. Disse kontroller sikrer, at mennesker, tjenester og autonome agenter kun interagerer med modeller, data og beregningsressourcer inden for eksplicit tildelte rammer, med kontinuerlig verifikation og revisionsmuligheder.

---

## C5.1 Identitetsstyring og autentificering

Etabler kryptografisk-sikrede identiteter for alle enheder med multifaktorgodkendelse til privilegerede operationer.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Bekræft, at alle menneskelige brugere og serviceprincipaler godkendes gennem en centraliseret virksomhedsidentitetsudbyder (IdP) ved hjælp af OIDC/SAML-protokoller med unikke identitet-til-token kortlægninger (ingen delte konti eller legitimationsoplysninger). |   1   | D/V  |
| 5.1.2 | Bekræft, at højrisikooperationer (modeludrulning, vægtekport, adgang til træningsdata, ændringer i produktionskonfiguration) kræver multifaktorgodkendelse eller trinvis godkendelse med sessionsrevalidering.                                                       |   1   | D/V  |
| 5.1.3 | Bekræft, at nye principper gennemgår identitetsbekræftelse, der er i overensstemmelse med NIST 800-63-3 IAL-2 eller tilsvarende standarder, før de får adgang til produktionssystemet.                                                                               |   2   |  D   |
| 5.1.4 | Bekræft, at adgangsgennemgange udføres kvartalsvis med automatiseret detektion af inaktive konti, håndhævelse af credential rotation og workflows for afvikling af adgang.                                                                                           |   2   |  V   |
| 5.1.5 | Bekræft, at fødererede AI-agenter autentificerer via signerede JWT-påstande, som har en maksimal levetid på 24 timer og inkluderer kryptografisk bevis for oprindelsen.                                                                                              |   3   | D/V  |

---

## C5.2 Ressourceautorisation og mindste privilegium

Implementer detaljerede adgangskontroller for alle AI-ressourcer med eksplicitte tilladelsesmodeller og revisionsspor.

|   #   | Description                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Bekræft, at alle AI-ressourcer (datasæt, modeller, endepunkter, vektorsamlinger, indlejringsindekser, compute-instanser) håndhæver rollebaserede adgangskontroller med eksplicitte tilladelseslister og standardafvisningspolitikker. |   1   | D/V  |
| 5.2.2 | Bekræft, at principperne om mindst privilegium håndhæves som standard for servicekonti, startende med skrivebeskyttede tilladelser, og at der kræves dokumenteret forretningsmæssig begrundelse for skriveadgang.                     |   1   | D/V  |
| 5.2.3 | Bekræft, at alle ændringer i adgangskontrollen er knyttet til godkendte ændringsanmodninger og logget uforanderligt med tidsstempler, aktøridentiteter, ressourceidentifikatorer og ændringsdifferencer i tilladelser.                |   1   |  V   |
| 5.2.4 | Bekræft, at dataklassifikationsmærker (PII, PHI, eksportkontrol, proprietær) automatisk videreføres til afledte ressourcer (indlejring, prompt-cache, modeloutput) med konsekvent politikhåndhævelse.                                 |   2   |  D   |
| 5.2.5 | Bekræft, at uautoriserede adgangsforsøg og hændelser med privilegieforhøjelse udløser realtidsalarmer med kontekstuel metadata til SIEM-systemer inden for 5 minutter.                                                                |   2   | D/V  |

---

## C5.3 Dynamisk politikvurdering

Implementer attributbaserede adgangskontrol (ABAC) motorer til kontekstbevidste autorisationsbeslutninger med revisionsmuligheder.

|   #   | Description                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Bekræft, at autorisationsbeslutninger er eksterne og håndteres af en dedikeret politikmotor (OPA, Cedar eller tilsvarende), som er tilgængelig via autentificerede API'er med kryptografisk integritetsbeskyttelse. |   1   | D/V  |
| 5.3.2 | Bekræft, at politikker evaluerer dynamiske attributter under kørsel, herunder brugernes sikkerhedsniveau, ressourcefølsomhedsklassifikation, anmodningskontekst, lejerisolation og tidsmæssige begrænsninger.       |   1   | D/V  |
| 5.3.3 | Bekræft, at politikdefinitioner er versionsstyrede, fagmæssigt gennemgået og valideret gennem automatiserede tests i CI/CD-pipelines, før de implementeres i produktion.                                            |   2   |  D   |
| 5.3.4 | Bekræft, at resultatet af politikvurdering inkluderer strukturerede beslutningsbegrundelser og overføres til SIEM-systemer til korrelationsanalyse og rapportering om overholdelse.                                 |   2   |  V   |
| 5.3.5 | Bekræft, at politikcachens levetid (TTL) ikke overstiger 5 minutter for højsensitive ressourcer og 1 time for standardressourcer med cache-udløsningsmuligheder.                                                    |   3   | D/V  |

---

## C5.4 Sikkerhedshåndhævelse ved forespørgselstidspunktet

Implementer sikkerhedskontroller på databaseniveau med obligatorisk filtrering og række-niveau sikkerhedspolitikker.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Bekræft, at alle vektor-database- og SQL-forespørgsler inkluderer obligatoriske sikkerhedsfiltre (lejert ID, følsomhedsetiketter, brugerområde), som håndhæves på databasmotor-niveau og ikke i applikationskoden.      |   1   | D/V  |
| 5.4.2 | Bekræft, at politikker for sikkerhed på rækkeniveau (RLS) og maske på feltniveau er aktiveret med politikarv for alle vektordatabaser, søgeindekser og træningsdatasæt.                                                 |   1   | D/V  |
| 5.4.3 | Bekræft, at mislykkede autorisationsvurderinger vil forhindre "confused deputy-angreb" ved straks at afbryde forespørgsler og returnere eksplicitte autorisationsfejlkoder i stedet for at returnere tomme resultatsæt. |   2   |  D   |
| 5.4.4 | Bekræft, at politikvurderingsforsinkelse løbende overvåges med automatiserede advarsler ved timeout-betingelser, som kunne muliggøre omgåelse af autorisation.                                                          |   2   |  V   |
| 5.4.5 | Bekræft, at forespørgselsgenforsøgs-mekanismer genvurderer autorisationspolitikker for at tage højde for dynamiske ændringer i tilladelser inden for aktive brugersessioner.                                            |   3   | D/V  |

---

## C5.5 Outputfiltrering og forebyggelse af data tab

Implementer post-processing kontrolmekanismer for at forhindre uautoriseret dataeksponering i AI-genereret indhold.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Bekræft, at filtre efter inferens scanner og redigerer uautoriserede personoplysninger (PII), klassificerede oplysninger og proprietære data, før indhold leveres til anmodere.       |   1   | D/V  |
| 5.5.2 | Bekræft, at henvisninger, referencer og kildeangivelser i modeloutput er valideret i forhold til kalderens rettigheder og fjernet, hvis uautoriseret adgang opdages.                  |   1   | D/V  |
| 5.5.3 | Bekræft, at outputformatbegrænsninger (rensede PDF'er, metadata-fjernede billeder, godkendte filtyper) håndhæves baseret på brugertilladelsesniveauer og dataklassifikationer.        |   2   |  D   |
| 5.5.4 | Sørg for, at redigeringsalgoritmer er deterministiske, versionskontrollerede og opretholder revisionslogfiler for at understøtte overholdelsesundersøgelser og retsmedicinsk analyse. |   2   |  V   |
| 5.5.5 | Bekræft, at højrisiko redaktionsevents genererer adaptive logfiler, som inkluderer kryptografiske hashes af det oprindelige indhold til retsmedicinsk genfinding uden datalækage.     |   3   |  V   |

---

## C5.6 Flere-lejer isolering

Sikre kryptografisk og logisk isolation mellem lejere i delt AI-infrastruktur.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.6.1 | Bekræft, at hukommelsesrum, indlejringslagre, cache-poster og midlertidige filer er navneområdeseparerede pr. lejer med sikker sletning ved sletning af lejer eller afslutning af session. |   1   | D/V  |
| 5.6.2 | Bekræft, at hver API-anmodning inkluderer en autentificeret lejeridentifikator, som er kryptografisk valideret mod sessionskontekst og brugerrettigheder.                                  |   1   | D/V  |
| 5.6.3 | Bekræft, at netværkspolitikker implementerer standard-afvisningsregler for kommunikation på tværs af lejere inden for servicemeshes og containerorkestreringsplatforme.                    |   2   |  D   |
| 5.6.4 | Bekræft, at krypteringsnøgler er unikke per lejer med kundestyret nøgle (CMK) support og kryptografisk isolation mellem lejerens datalagre.                                                |   3   |  D   |

---

## C5.7 Autorisation af autonom agent

Kontroller tilladelser for AI-agenter og autonome systemer gennem scopespecifikke kapabilitetstokens og kontinuerlig autorisation.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Bekræft, at autonome agenter modtager scoped kapabilitetstokens, der eksplicit angiver tilladte handlinger, tilgængelige ressourcer, tidsgrænser og driftsmæssige begrænsninger.                                                       |   1   | D/V  |
| 5.7.2 | Bekræft, at højrisikofunktioner (adgang til filsystem, kodeudførelse, eksterne API-kald, finansielle transaktioner) er deaktiveret som standard og kræver eksplicitte godkendelser for aktivering med forretningsmæssige begrundelser. |   1   | D/V  |
| 5.7.3 | Bekræft, at kapabilitetstokener er bundet til brugersessioner, inkluderer kryptografisk integritetsbeskyttelse, og sikre, at de ikke kan gemmes eller genbruges i offline-scenarier.                                                   |   2   |  D   |
| 5.7.4 | Bekræft, at agent-initierede handlinger gennemgår sekundær godkendelse via ABAC-politikmotoren med fuld kontekstevaluering og revisionslogning.                                                                                        |   2   |  V   |
| 5.7.5 | Bekræft, at agentfejltilstande og undtagelseshåndtering inkluderer oplysninger om kapabilitetsområde for at understøtte hændelsesanalyse og retsmedicinsk undersøgelse.                                                                |   3   |  V   |

---

## Referencer

### Standarder og rammeværk

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Implementeringsvejledninger

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### AI-specifik sikkerhed

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

