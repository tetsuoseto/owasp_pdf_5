# 9 Autonom orkestrering og agentbaseret handlingssikkerhed

## Kontrolmål

Sørg for, at autonome eller multi-agent AI-systemer kun kan udføre handlinger, der er eksplicit tilsigtede, godkendte, reviderbare og inden for afgrænsede omkostnings- og risikogrænser. Dette beskytter mod trusler som kompromittering af autonome systemer, værktøjsmisbrug, agent-loop-detektion, kommunikationskapring, identitetsspoofing, sværmmemanipulation og intentionmanipulation.

---

## 9.1 Agent Opgaveplanlægning & Rekursionsbudgetter

Begræns rekursive planer og pålæg menneskelige kontrolpunkter for privilegerede handlinger.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Verificer, at maksimal rekursionsdybde, bredde, væg-ur tid, tokens og monetære omkostninger pr. agentudførelse er centralt konfigureret og versionsstyret.                                    |   1   | D/V  |
| 9.1.2 | Bekræft, at privilegerede eller irreversible handlinger (f.eks. kodeforpligtelser, finansielle overførsler) kræver eksplicit menneskelig godkendelse via en reviderbar kanal, før de udføres. |   1   | D/V  |
| 9.1.3 | Bekræft, at realtidsressourcemonitorer udløser afbrydelse via kredsløbsafbryder, når nogen budgetgrænse overskrides, hvilket stopper yderligere opgaveudvidelse.                              |   2   |  D   |
| 9.1.4 | Bekræft, at kredsløbsafbryderhændelser logges med agent-ID, udløsende betingelse og fanget planstatus til retsmedicinsk gennemgang.                                                           |   2   | D/V  |
| 9.1.5 | Sørg for, at sikkerhedstests dækker scenarier med budgetudmattelse og løber løbsk plan, og bekræft sikker standsning uden datatab.                                                            |   3   |  V   |
| 9.1.6 | Bekræft, at budgetpolitikker er udtrykt som politik-som-kode og håndhæves i CI/CD for at forhindre konfigurationsdrift.                                                                       |   3   |  D   |

---

## 9.2 Værktøjs-plugin Sandboxning

Isolér værktøjsinteraktioner for at forhindre uautoriseret systems adgang eller kodeeksekvering.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Bekræft, at hvert værktøj/plugin kører inden for et OS-, container- eller WASM-niveau sandbox med mindst privilegerede filsystem-, netværks- og systemkaldspolitikker. |   1   | D/V  |
| 9.2.2 | Bekræft, at grænser for ressourcer i sandkassen (CPU, hukommelse, disk, netværksudgang) og udførelsestidsbegrænsninger håndhæves og logges.                            |   1   | D/V  |
| 9.2.3 | Bekræft, at værktøjsbinærfiler eller deskriptorer er digitalt signeret; signaturer valideres inden indlæsning.                                                         |   2   | D/V  |
| 9.2.4 | Bekræft, at sandkassetelemetri strømmer til et SIEM; afvigelser (f.eks. forsøg på udgående forbindelser) udløser alarmer.                                              |   2   |  V   |
| 9.2.5 | Sørg for, at højrisiko-plugins gennemgår sikkerhedsvurdering og penetrationstest, inden de tages i brug i produktionen.                                                |   3   |  V   |
| 9.2.6 | Bekræft, at forsøg på at undslippe sandboxen automatisk blokeres, og at den krænkende plugin sættes i karantæne i afventning af undersøgelse.                          |   3   | D/V  |

---

## 9.3 Autonom Løkke og Omkostningsbegrænsning

Registrer og stop ukontrolleret agent-til-agent rekursion og omkostningseksplosioner.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Bekræft, at opkald mellem agenter inkluderer en hop-grænse eller TTL, som runtime-miljøet nedskriver og håndhæver.                    |   1   | D/V  |
| 9.3.2 | Sørg for, at agenter opretholder en unik invocations-graf-ID for at opdage selv-invokation eller cykliske mønstre.                    |   2   |  D   |
| 9.3.3 | Bekræft, at kumulative beregningsenheds- og forbrugsoptællere føres for hver anmodningskæde; overskridelse af grænsen afbryder kæden. |   2   | D/V  |
| 9.3.4 | Bekræft, at formel analyse eller modelkontrol demonstrerer fravær af ubegrænset rekursion i agentprotokoller.                         |   3   |  V   |
| 9.3.5 | Bekræft, at loop-afbrudsbegivenheder genererer advarsler og leverer metrics til løbende forbedring.                                   |   3   |  D   |

---

## 9.4 Protokolniveau Misbrugsbeskyttelse

Sikre kommunikationskanaler mellem agenter og eksterne systemer for at forhindre overtagelse eller manipulation.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Bekræft, at alle beskeder mellem agent og værktøj samt agent og agent er autentificerede (f.eks. gensidig TLS eller JWT) og krypterede fra ende til ende. |   1   | D/V  |
| 9.4.2 | Sørg for, at skemaer bliver strengt valideret; ukendte felter eller fejlagtige beskeder afvises.                                                          |   1   |  D   |
| 9.4.3 | Bekræft, at integritetskontroller (MAC'er eller digitale signaturer) dækker hele beskedens nyttelast, inklusive værktøjsparametre.                        |   2   | D/V  |
| 9.4.4 | Bekræft, at gengivelsesbeskyttelse (noncer eller tidsstempelvinduer) håndhæves på protokollaget.                                                          |   2   |  D   |
| 9.4.5 | Bekræft, at protokolimplementeringer gennemgår fuzzing og statisk analyse for injektions- eller deserialiseringsfejl.                                     |   3   |  V   |

---

## 9.5 Agentidentitet & manipulationssikkerhed

Sørg for, at handlinger kan tilskrives, og at ændringer kan opdages.

|   #   | Description                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Bekræft, at hver agentinstans har en unik kryptografisk identitet (nøglepar eller hardwareforankret legitimationsoplysning). |   1   | D/V  |
| 9.5.2 | Bekræft, at alle agenthandlinger er underskrevet og tidsstemplet; logfiler inkluderer underskriften for ikke-benægtelse.     |   2   | D/V  |
| 9.5.3 | Bekræft, at manipulationssikre logs gemmes i et append-only eller write-once medie.                                          |   2   |  V   |
| 9.5.4 | Bekræft, at identitetsnøgler roterer efter en defineret tidsplan og ved indikatorer for kompromittering.                     |   3   |  D   |
| 9.5.5 | Bekræft, at spoofing- eller nøglekonfliktforsøg straks udløser karantæne af den berørte agent.                               |   3   | D/V  |

---

## 9.6 Risiko-reduktion ved multi-agent-sværm

Afhjælp risici ved kollektiv adfærd gennem isolation og formel sikkerhedsmodellering.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Bekræft, at agenter, der opererer i forskellige sikkerhedsdomaener, kører i isolerede runtime-sandkasser eller netværkssegmenter.               |   1   | D/V  |
| 9.6.2 | Bekræft, at sværmbeslutninger er modelleret og formelt verificeret for livskraft og sikkerhed før implementering.                               |   3   |  V   |
| 9.6.3 | Verificer, at runtime-overvågninger opdager fremvoksende usikre mønstre (f.eks. oscillationer, dødlåse) og iværksætter korrigerende handlinger. |   3   |  D   |

---

## 9.7 Bruger- og værktøjsautentifikation / autorisation

Implementer robuste adgangskontroller for enhver agentudløst handling.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Bekræft, at agenter autentificerer som førsteklasses aktører over for downstream-systemer og aldrig genbruger slutbrugerens legitimationsoplysninger. |   1   | D/V  |
| 9.7.2 | Bekræft, at detaljerede autorisationspolitikker begrænser, hvilke værktøjer en agent må påkalde, og hvilke parametre den må levere.                   |   2   |  D   |
| 9.7.3 | Bekræft, at rettighedstjek genvurderes ved hvert kald (kontinuerlig autorisation), ikke kun ved sessionens start.                                     |   2   |  V   |
| 9.7.4 | Bekræft, at delegerede privilegier udløber automatisk og kræver fornyet samtykke efter timeout eller ændring af omfang.                               |   3   |  D   |

---

## 9.8 Agent-til-Agent Kommunikationssikkerhed

Krypter og integritetsbeskyt alle beskeder mellem agenter for at forhindre aflytning og manipulation.

|   #   | Description                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.8.1 | Bekræft, at gensidig autentificering og kryptering med perfekt fremadrettet hemmeligholdelse (f.eks. TLS 1.3) er obligatoriske for agentkanaler. |   1   | D/V  |
| 9.8.2 | Bekræft, at beskedens integritet og oprindelse valideres, før den behandles; fejl udløser alarmer og forkaster beskeden.                         |   1   |  D   |
| 9.8.3 | Bekræft, at kommunikationsmetadata (tidsstempler, sekvensnumre) logges for at understøtte retsmedicinsk rekonstruktion.                          |   2   | D/V  |
| 9.8.4 | Bekræft, at formel verifikation eller modelkontrol bekræfter, at protokoltilstandsmaskiner ikke kan drives ind i usikre tilstande.               |   3   |  V   |

---

## 9.9 Intentionverifikation og håndhævelse af begrænsninger

Bekræft, at agentens handlinger stemmer overens med brugerens angivne intention og systemets begrænsninger.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Bekræft, at pre-eksekveringsbegrænsningsløsere kontrollerer foreslåede handlinger op imod hardkodede sikkerheds- og politikregler.                              |   1   |  D   |
| 9.9.2 | Bekræft, at handlinger med stor indvirkning (økonomiske, destruktive, privatlivsfølsomme) kræver eksplicit bekræftelse af hensigten fra den initierende bruger. |   2   | D/V  |
| 9.9.3 | Bekræft, at efterbetingelsestjek validerer, at fuldførte handlinger opnåede tilsigtede effekter uden bivirkninger; uoverensstemmelser udløser tilbagerulning.   |   2   |  V   |
| 9.9.4 | Bekræft, at formelle metoder (f.eks. modelkontrol, teorembevis) eller egenskabsbaserede tests viser, at agentplaner opfylder alle erklærede begrænsninger.      |   3   |  V   |
| 9.9.5 | Bekræft, at hændelser med formåls-mismatch eller overtrædelse af begrænsninger fodrer kontinuerlige forbedringscyklusser og deling af trusselsintelligens.      |   3   |  D   |

---

## 9.10 Agentbegrænsningsstrategi Sikkerhed

Sikker valg og udførelse af forskellige ræsonnementstrategier, herunder ReAct, Chain-of-Thought og Tree-of-Thoughts tilgange.

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Bekræft, at valg af ræsonnementstrategi bruger deterministiske kriterier (inputkompleksitet, opgavetype, sikkerhedskontekst), og at identiske input giver identiske strategivalg inden for samme sikkerhedskontekst. |   1   | D/V  |
| 9.10.2 | Bekræft, at hver ræsonneringsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikeret inputvalidering, outputrensning og eksekveringstidsgrænser specifikt til dens kognitive tilgang.                     |   1   | D/V  |
| 9.10.3 | Sørg for, at overgange i ræsonneringsstrategi bliver logget med komplet kontekst, inklusive inputkarakteristika, værdier for udvælgelseskriterier og udførelsesmetadata, til rekonstruktion af revisionsspor.        |   2   | D/V  |
| 9.10.4 | Bekræft, at Tree-of-Thoughts-ræsonnering inkluderer grenbeskæringsmekanismer, der afslutter udforskning, når politikovertrædelser, ressourcebegrænsninger eller sikkerhedsgrænser opdages.                           |   2   | D/V  |
| 9.10.5 | Bekræft, at ReAct (Reason-Act-Observe) cyklusser inkluderer valideringskontrolpunkter i hver fase: verifikation af ræsonnementstrin, godkendelse af handling og sanitering af observation, før der fortsættes.       |   2   | D/V  |
| 9.10.6 | Bekræft, at præstationsmålinger for ræsonneringsstrategien (eksekveringstid, ressourceforbrug, outputkvalitet) overvåges med automatiserede alarmer, når målingerne afviger ud over konfigurerede grænseværdier.     |   3   | D/V  |
| 9.10.7 | Verificer, at hybride ræsonnementstilgange, der kombinerer flere strategier, opretholder inputvalidering og outputbegrænsninger for alle de enkelte strategier uden at omgå nogen sikkerhedskontroller.              |   3   | D/V  |
| 9.10.8 | Bekræft, at strategisikkerhedstestning omfatter fuzzing med fejlbehæftede input, modstridende anmodninger designet til at tvinge strategiskift, samt grænsetilstandstestning for hver kognitiv tilgang.              |   3   | D/V  |

---

## 9.11 Agentens livscyklusstyring og sikkerhed

Sikker agentinitialisering, tilstandsovergange og afslutning med kryptografiske revisionsspor og definerede genoprettelsesprocedurer.

|   #    | Description                                                                                                                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Bekræft, at agentinitialisering inkluderer etablering af kryptografisk identitet med hardware-understøttede legitimationsoplysninger og uforanderlige opstartsrevisionslogs, der indeholder agent-ID, tidsstempel, konfigurationshash og initialiseringsparametre.                                        |   1   | D/V  |
| 9.11.2 | Bekræft, at agentens tilstandsovergange er kryptografisk underskrevet, tidsstemplet og logget med fuldstændig kontekst, inklusive udløsende begivenheder, tidligere tilstandshash, ny tilstandshash og udførte sikkerhedsvalideringer.                                                                    |   2   | D/V  |
| 9.11.3 | Bekræft, at agentens nedlukningsprocedurer inkluderer sikker hukommelsesrydning ved hjælp af kryptografisk sletning eller flerpasset overskrivning, tilbagekaldelse af legitimationsoplysninger med underretning til certifikatmyndigheden samt generering af manipulationssikre afslutningscertifikater. |   2   | D/V  |
| 9.11.4 | Bekræft, at agentens genoprettelsesmekanismer validerer tilstandsintegritet ved hjælp af kryptografiske kontrolsummer (minimum SHA-256) og ruller tilbage til kendte gode tilstande, når der opdages korruption, med automatiske advarsler og krav om manuel godkendelse.                                 |   3   | D/V  |
| 9.11.5 | Bekræft, at agentens vedholdenhedsmekanismer krypterer følsomme tilstandsdata med AES-256-nøgler per agent og implementerer sikker nøglerotation efter konfigurerbare tidsplaner (maksimalt 90 dage) med uafbrudt implementering.                                                                         |   3   | D/V  |

---

## 9.12 Værktøjsintegrationssikkerhedsramme

Sikkerhedskontroller for dynamisk indlæsning af værktøjer, udførelse og resultatvalidering med definerede risikovurderings- og godkendelsesprocesser.

|   #    | Description                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Bekræft, at værktøjsbeskrivelser inkluderer sikkerhedsmetadata, der specificerer nødvendige privilegier (læs/skriv/udfør), risikoniveauer (lav/mellem/høj), ressourcelimiter (CPU, hukommelse, netværk) samt valideringskrav dokumenteret i værktøjsmanifest. |   1   | D/V  |
| 9.12.2 | Bekræft, at værktøjets udførelsesresultater valideres mod forventede skemaer (JSON-skema, XML-skema) og sikkerhedspolitikker (outputrensning, dataklassificering), inden integration med tidsbegrænsninger og fejlbehandlingsprocedurer.                      |   1   | D/V  |
| 9.12.3 | Bekræft, at værktøjsinteraktionslogfiler indeholder detaljeret sikkerhedskontekst, herunder brug af privilegier, datatilgangsmønstre, eksekveringstid, ressourceforbrug og returkoder med struktureret logning til SIEM-integration.                          |   2   | D/V  |
| 9.12.4 | Bekræft, at mekanismer til dynamisk værktøjsindlæsning validerer digitale signaturer ved hjælp af PKI-infrastruktur og implementerer sikre indlæsningsprotokoller med sandkasse-isolation og tilladelsesverifikation før udførelse.                           |   2   | D/V  |
| 9.12.5 | Bekræft, at værktøjssikkerhedsvurderinger automatisk udløses for nye versioner med obligatoriske godkendelsesgate, inklusive statisk analyse, dynamisk test og sikkerhedsteamets gennemgang med dokumenterede godkendelseskriterier og SLA-krav.              |   3   | D/V  |

---

### Referencer

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

