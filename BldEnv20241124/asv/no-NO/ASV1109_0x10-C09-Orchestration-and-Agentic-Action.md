# 9 Autonom orkestrering og agentisk handlingssikkerhet

## Kontrollmål

Sørg for at autonome eller multi-agent AI-systemer kun kan utføre handlinger som er eksplisitt tiltenkt, autentisert, reviderbare og innenfor avgrensede kostnads- og risikogrenseverdier. Dette beskytter mot trusler som kompromittering av autonome systemer, feilbruk av verktøy, agentløkkeoppdagelse, kommunikasjonshijacking, identitetsspoofing, flokkmanipulasjon og intensjonsmanipulasjon.

---

## 9.1 Agentens oppgaveplanlegging og resirkuleringsbudsjetter

Begrens rekursive planer og påtving menneskelige sjekkpunkter for privilegerte handlinger.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.1.1 | Bekreft at maksimal rekursjonsdybde, bredde, veggklokketid, antall tokens og monetær kostnad per agentkjøring er sentralt konfigurert og versjonskontrollert.                              |   1   | D/V  |
| 9.1.2 | Bekreft at privilegerte eller irreversible handlinger (f.eks. kodeinnsendinger, finansielle overføringer) krever eksplisitt menneskelig godkjenning via en reviderbar kanal før utførelse. |   1   | D/V  |
| 9.1.3 | Bekreft at sanntids ressursovervåkere utløser avbrudd i kretsbryteren når noen budsjettterskel overskrides, og stopper ytterligere oppgaveutvidelse.                                       |   2   |  D   |
| 9.1.4 | Bekreft at circuit-breaker-hendelser logges med agent-ID, utløsende betingelse og fanget planstatus for rettsmedisinsk gjennomgang.                                                        |   2   | D/V  |
| 9.1.5 | Bekreft at sikkerhetstester dekker scenarier med budsjettutarming og løpsk plan, og bekreft trygg avslutning uten datatap.                                                                 |   3   |  V   |
| 9.1.6 | Bekreft at budsjettpolitikker er uttrykt som policy-som-kode og håndheves i CI/CD for å blokkere konfigurasjonsdrift.                                                                      |   3   |  D   |

---

## 9.2 Verktøy-plugin Sandboxing

Isoler verktøyinteraksjoner for å forhindre uautorisert systemtilgang eller kodeutførelse.

|   #   | Description                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Sørg for at hvert verktøy/plugin kjører innenfor et OS-, container- eller WASM-nivå sandbox med minste privilegium for filsystem-, nettverks- og systemkallpolicyer. |   1   | D/V  |
| 9.2.2 | Verifiser at kvoter for sandkasseressurser (CPU, minne, disk, nettverksutgang) og kjøretidsavbrudd håndheves og loggføres.                                           |   1   | D/V  |
| 9.2.3 | Verifiser at verktøybinarier eller beskrivelser er digitalt signert; signaturer valideres før lasting.                                                               |   2   | D/V  |
| 9.2.4 | Bekreft at sandkassens telemetri strømmer til en SIEM; avvik (f.eks. forsøk på utgående tilkoblinger) utløser varsler.                                               |   2   |  V   |
| 9.2.5 | Verifiser at høyrisiko-plugins gjennomgår sikkerhetsgjennomgang og penetrasjonstesting før produksjonsdistribusjon.                                                  |   3   |  V   |
| 9.2.6 | Bekreft at forsøk på å bryte ut av sandkassen automatisk blokkeres og at den feilaktige pluginen settes i karantene i påvente av undersøkelse.                       |   3   | D/V  |

---

## 9.3 Autonom løkke og kostnadsavgrensning

Oppdag og stopp ukontrollert agent-til-agent rekursjon og kostnadseksplosjoner.

|   #   | Description                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Bekreft at samtaler mellom agenter inkluderer en hopp-grense eller TTL som kjøretiden reduserer og håndhever.                     |   1   | D/V  |
| 9.3.2 | Verifiser at agenter opprettholder en unik invokasjonsgraf-ID for å oppdage selvinvokasjon eller sykliske mønstre.                |   2   |  D   |
| 9.3.3 | Bekreft at kumulative beregningsenhets- og forbrukstellere spores per forespørselkjede; overskridelse av grensen avbryter kjeden. |   2   | D/V  |
| 9.3.4 | Verifiser at formell analyse eller modellkontroll påviser fravær av ubegrenset rekursjon i agentprotokoller.                      |   3   |  V   |
| 9.3.5 | Verifiser at loop-avbruddsbegivenheter genererer varsler og leverer kontinuerlige forbedringsmetrikker.                           |   3   |  D   |

---

## 9.4 Protokollnivå Misbruksbeskyttelse

Sikre kommunikasjonskanaler mellom agenter og eksterne systemer for å forhindre kapring eller manipulering.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Bekreft at alle meldinger mellom agent og verktøy og mellom agenter er autentisert (f.eks. gjensidig TLS eller JWT) og ende-til-ende kryptert. |   1   | D/V  |
| 9.4.2 | Sørg for at skjemaer blir strengt validert; ukjente felt eller feilformaterte meldinger blir avvist.                                           |   1   |  D   |
| 9.4.3 | Verifiser at integritetskontroller (MAC-er eller digitale signaturer) dekker hele meldingsinnholdet, inkludert verktøyparametere.              |   2   | D/V  |
| 9.4.4 | Sjekk at gjenspillingsbeskyttelse (nonser eller tidsstempelvinduer) håndheves på protokollaget.                                                |   2   |  D   |
| 9.4.5 | Bekreft at protokollimplementeringer gjennomgår fuzzing og statisk analyse for injeksjons- eller deserialiseringsfeil.                         |   3   |  V   |

---

## 9.5 Agentidentitet og manipulasjonssikkerhet

Sørg for at handlinger kan tilskrives og at endringer er oppdagbare.

|   #   | Description                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Bekreft at hver agentinstans har en unik kryptografisk identitet (nøkkelpar eller maskinvarebasert rotlegitimasjon). |   1   | D/V  |
| 9.5.2 | Bekreft at alle agenthandlinger er signert og tidsstemplet; logger inkluderer signaturen for ikke-avvisning.         |   2   | D/V  |
| 9.5.3 | Bekreft at manipuleringsevidente logger lagres i et kun-tillegg eller skrivebeskyttet medium.                        |   2   |  V   |
| 9.5.4 | Verifiser at identitetsnøkler roteres etter en definert tidsplan og ved indikasjoner på kompromittering.             |   3   |  D   |
| 9.5.5 | Bekreft at forsøk på forfalskning eller nøkkelkonflikt utløser umiddelbar karantene av den berørte agenten.          |   3   | D/V  |

---

## 9.6 Fleragent-sverm risikoreduksjon

Reduser fare for kollektiv atferd gjennom isolasjon og formell sikkerhetsmodellering.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Bekreft at agenter som opererer i forskjellige sikkerhetsdomener kjører i isolerte kjøretids-sandbokser eller nettverkssegmenter.            |   1   | D/V  |
| 9.6.2 | Sørg for at sværmatferder modelleres og formelt verifiseres for livlighet og sikkerhet før distribusjon.                                     |   3   |  V   |
| 9.6.3 | Verifiser at kjøretidsovervåkere oppdager fremvoksende usikre mønstre (f.eks. oscillasjoner, stillstand) og iverksetter korrigerende tiltak. |   3   |  D   |

---

## 9.7 Bruker- og verktøyautentisering / autorisasjon

Implementer robuste tilgangskontroller for hver handling utløst av agent.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Verifiser at agenter autentiserer som førsteklasses prinsipper til nedstrøms systemer, og aldri gjenbruker sluttbrukerens legitimasjon. |   1   | D/V  |
| 9.7.2 | Verifiser at detaljerte autorisasjonspolicyer begrenser hvilke verktøy en agent kan bruke og hvilke parametere den kan oppgi.           |   2   |  D   |
| 9.7.3 | Verifiser at privilegjekontroller blir evaluert på nytt ved hvert kall (kontinuerlig autorisasjon), ikke bare ved sesjonsstart.         |   2   |  V   |
| 9.7.4 | Bekreft at delegerte privilegier utløper automatisk og krever ny samtykke etter tidsavbrudd eller endring i omfang.                     |   3   |  D   |

---

## 9.8 Sikkerhet for kommunikasjon mellom agenter

Krypter og sikr integriteten til alle meldinger mellom agenter for å hindre avlytting og manipulering.

|   #   | Description                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.8.1 | Bekreft at gjensidig autentisering og kryptering med perfekt fremoverhemmelighold (for eksempel TLS 1.3) er obligatorisk for agentkanaler. |   1   | D/V  |
| 9.8.2 | Sørg for at meldingsintegritet og opprinnelse blir verifisert før behandling; ved feil utløses varsler og meldingen avvises.               |   1   |  D   |
| 9.8.3 | Bekreft at kommunikasjonens metadata (tidsstempler, sekvensnumre) logges for å støtte rettsmedisinsk rekonstruksjon.                       |   2   | D/V  |
| 9.8.4 | Verifiser at formell verifisering eller modellkontroll bekrefter at protokolltilstandsmaskiner ikke kan settes i usikre tilstander.        |   3   |  V   |

---

## 9.9 Intensjonsverifisering og håndheving av begrensninger

Bekreft at agentens handlinger samsvarer med brukerens angitte intensjon og systemets begrensninger.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Verifiser at forhåndsutførelsesbegrensningsløserne sjekker foreslåtte handlinger mot hardkodede sikkerhets- og policyregler.                                  |   1   |  D   |
| 9.9.2 | Bekreft at handlinger med høy påvirkning (økonomiske, destruktive, personvernsensitive) krever eksplisitt intensjonsbekreftelse fra den initierende brukeren. |   2   | D/V  |
| 9.9.3 | Bekreft at etterbetingelseskontroller validerer at fullførte handlinger oppnådde tiltenkte effekter uten bivirkninger; avvik utløser tilbakestilling.         |   2   |  V   |
| 9.9.4 | Verifiser at formelle metoder (f.eks. modelkontroll, teorembevis) eller egenskapsbaserte tester viser at agentplaner oppfyller alle deklarerte begrensninger. |   3   |  V   |
| 9.9.5 | Bekreft at hendelser med intensjonsavvik eller brudd på begrensninger bidrar til kontinuerlige forbedringssykluser og deling av trusselinformasjon.           |   3   |  D   |

---

## 9.10 Agentresonnement Strategi Sikkerhet

Sikker valg og utførelse av forskjellige resonnementstrategier, inkludert ReAct, Chain-of-Thought og Tree-of-Thoughts tilnærminger.

|   #    | Description                                                                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Bekreft at valg av resonnementstrategi bruker deterministiske kriterier (inngangskompleksitet, oppgavetyp, sikkerhetskontekst) og at identiske innganger gir identiske strategivalg innen samme sikkerhetskontekst.     |   1   | D/V  |
| 9.10.2 | Bekreft at hver resonneringsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikert inndata-validering, utdata-rensing og tidsbegrensninger for utførelse som er spesifikke for dens kognitive tilnærming.    |   1   | D/V  |
| 9.10.3 | Kontroller at overganger i resonnementstrategi blir loggført med fullstendig kontekst, inkludert inndatakjennetegn, verdier for utvalgskriterier, og utførelsesmetadata for rekonstruksjon av revisjonsspor.            |   2   | D/V  |
| 9.10.4 | Bekreft at Tree-of-Thoughts-rasjonering inkluderer mekanismer for beskjæring av grener som avslutter utforskning når policybrudd, ressursgrenser eller sikkerhetsgrenser oppdages.                                      |   2   | D/V  |
| 9.10.5 | Bekreft at ReAct (Resonner-Virk-Observer) sykluser inkluderer valideringskontrollpunkter i hver fase: verifisering av resonnementstrinn, godkjenning av handling og sanitering av observasjon før videreføring.         |   2   | D/V  |
| 9.10.6 | Bekreft at ytelsesmålinger for resonnementstrategien (utførelsestid, ressursbruk, resultatkvalitet) overvåkes med automatiserte varsler når målingene avviker fra de konfigurerte tersklene.                            |   3   | D/V  |
| 9.10.7 | Bekreft at hybride resonneringsmetoder som kombinerer flere strategier opprettholder inngangsvalidering og utgangsbegrensninger for alle de enkelte strategiene uten å omgå noen sikkerhetskontroller.                  |   3   | D/V  |
| 9.10.8 | Bekreft at sikkerhetstesting av resonneringsstrategier inkluderer fuzzing med feilaktige input, adversarielle prompt designet for å tvinge strategiskifte, og testing av grensetilstander for hver kognitiv tilnærming. |   3   | D/V  |

---

## 9.11 Agentens livssyklus tilstandsstyring og sikkerhet

Sikker agentinitialisering, tilstandsoverganger og terminering med kryptografiske revisjonsspor og definerte gjenopprettingsprosedyrer.

|   #    | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Sørg for at agentinitialisering inkluderer etablering av kryptografisk identitet med maskinvarebaserte legitimasjoner og uforanderlige oppstartsrevisjonslogger som inneholder agent-ID, tidsstempel, konfigurasjonshash og initialiseringsparametere.                                        |   1   | D/V  |
| 9.11.2 | Verifiser at agentens tilstandsoverganger er kryptografisk signert, tidsstemplet og loggført med komplett kontekst, inkludert utløsende hendelser, forrige tilstandens hash, ny tilstandens hash og utførte sikkerhetsvalideringer.                                                           |   2   | D/V  |
| 9.11.3 | Bekreft at agentens avslutningsprosedyrer inkluderer sikker minnesletting ved bruk av kryptografisk sletting eller flere overskrivingsrunder, tilbakekalling av autentiseringsopplysninger med varsling til sertifikatautoritet, og generering av manipulasjonssikre avslutningssertifikater. |   2   | D/V  |
| 9.11.4 | Bekreft at agentgjenopprettingsmekanismer validerer tilstandsintegritet ved bruk av kryptografiske sjekksummer (minimum SHA-256) og ruller tilbake til kjente gode tilstander når korrupsjon oppdages, med automatiserte varsler og krav om manuell godkjenning.                              |   3   | D/V  |
| 9.11.5 | Bekreft at agentens persistensmekanismer krypterer sensitiv tilstandsdata med per-agent AES-256-nøkler og implementerer sikker nøkkelrotasjon på konfigurerbare tidsplaner (maksimum 90 dager) med utrulling uten nedetid.                                                                    |   3   | D/V  |

---

## 9.12 Verktøyintegrasjonssikkerhetsrammeverk

Sikkerhetskontroller for dynamisk verktøylasting, kjøring og resultatvalidering med definerte risikovurderings- og godkjenningsprosesser.

|   #    | Description                                                                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Bekreft at verktøybeskrivelser inkluderer sikkerhetsmetadata som angir nødvendige privilegier (lese/skrive/utføre), risikonivåer (lav/middels/høy), ressursgrenser (CPU, minne, nettverk) og valideringskrav dokumentert i verktøymanifestene.       |   1   | D/V  |
| 9.12.2 | Verifiser at verktøyets kjøringsresultater valideres mot forventede skjemaer (JSON-skjema, XML-skjema) og sikkerhetspolicyer (utgangssanitering, dataklassifisering) før integrering med tidsavbruddsgrenser og feilhåndteringsprosedyrer.           |   1   | D/V  |
| 9.12.3 | Bekreft at verktøyinteraksjonslogger inkluderer detaljert sikkerhetskontekst, inkludert bruk av privilegier, datatilgangsmønstre, utførelsestid, ressursforbruk og returkoder med strukturert logging for SIEM-integrasjon.                          |   2   | D/V  |
| 9.12.4 | Bekreft at mekanismer for dynamisk verktøyinnlasting validerer digitale signaturer ved bruk av PKI-infrastruktur og implementerer sikre innlastingsprotokoller med sandkasseisolasjon og tillatelsesverifisering før kjøring.                        |   2   | D/V  |
| 9.12.5 | Bekreft at verktøysikkerhetsvurderinger automatisk utløses for nye versjoner med obligatoriske godkjenningsporter, inkludert statisk analyse, dynamisk testing og sikkerhetsteamets gjennomgang, med dokumenterte godkjenningskriterier og SLA-krav. |   3   | D/V  |

---

### Referanser

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

