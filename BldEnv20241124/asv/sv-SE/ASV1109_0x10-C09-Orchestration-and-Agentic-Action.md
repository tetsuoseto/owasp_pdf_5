# 9 Självständig orkestrering och agentbaserad handlingssäkerhet

## Kontrollmål

Säkerställ att autonoma eller multi-agent AI-system endast kan utföra handlingar som uttryckligen är avsedda, autentiserade, granskbara och inom avgränsade kostnads- och risktrösklar. Detta skyddar mot hot som kompromettering av autonoma system, felanvändning av verktyg, detektering av agentloopar, kapning av kommunikation, identitetsförfalskning, svärmmanipulation och avsiktsmanipulation.

---

## 9.1 Agentens uppgiftsplanering och rekursionsbudgetar

Begränsa rekursiva planer och tvinga fram mänskliga kontrollpunkter för privilegierade åtgärder.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Verifiera att maximal rekursionsdjup, bredd, väggklocktid, tokenantalk och monetär kostnad per agentkörning är centralt konfigurerade och versionshanterade.                                    |   1   | D/V  |
| 9.1.2 | Verifiera att privilegierade eller oåterkalleliga åtgärder (t.ex. kodinlämningar, finansiella överföringar) kräver uttryckligt mänskligt godkännande via en granskbar kanal innan de genomförs. |   1   | D/V  |
| 9.1.3 | Verifiera att övervakare för resurser i realtid utlöser avbrott av kretsbrytaren när någon budgetgräns överskrids, vilket stoppar vidare uppgiftsutvidgning.                                    |   2   |  D   |
| 9.1.4 | Verifiera att kretsbrytarehändelser loggas med agent-ID, utlösande villkor och fångat planläge för rättsmedicinsk granskning.                                                                   |   2   | D/V  |
| 9.1.5 | Verifiera att säkerhetstester täcker scenarier för budgetutarmning och oändlig plan, och bekräfta säker avstängning utan dataförlust.                                                           |   3   |  V   |
| 9.1.6 | Verifiera att budgetpolicys uttrycks som policy-som-kod och upprätthålls i CI/CD för att förhindra konfigurationsavvikelse.                                                                     |   3   |  D   |

---

## 9.2 Sandboxning av verktygsplugin

Isolera verktygsinteraktioner för att förhindra obehörig systemåtkomst eller kodexekvering.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Verifiera att varje verktyg/plugin körs inom ett OS-, container- eller WASM-nivå sandbox med filsystem-, nätverks- och systemanropspolicyer med minsta privilegium. |   1   | D/V  |
| 9.2.2 | Verifiera att resurskvoter för sandbox (CPU, minne, disk, nätverksutgång) och exekveringstidsgränser efterlevs och loggas.                                          |   1   | D/V  |
| 9.2.3 | Verifiera att verktygsbinärer eller deskriptorer är digitalt signerade; signaturer valideras innan de laddas.                                                       |   2   | D/V  |
| 9.2.4 | Verifiera att sandbox-telemetri strömmas till en SIEM; avvikelser (t.ex. försök till utgående anslutningar) utlöser larm.                                           |   2   |  V   |
| 9.2.5 | Verifiera att hög-riskplugins genomgår säkerhetsgranskning och penetrationstestning innan de tas i produktion.                                                      |   3   |  V   |
| 9.2.6 | Verifiera att försök att rymma från sandbox automatiskt blockeras och att den förargande plugin-programmet sätts i karantän i väntan på undersökning.               |   3   | D/V  |

---

## 9.3 Autonom slinga och kostnadsbegränsning

Upptäck och stoppa okontrollerad agent-till-agent rekursion och kostnadsexplosioner.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Verifiera att anrop mellan agenter inkluderar en hop-gräns eller TTL som körmiljön minskar och upprätthåller.                       |   1   | D/V  |
| 9.3.2 | Verifiera att agenter upprätthåller ett unikt anropsgraf-ID för att upptäcka självuppmaning eller cykliska mönster.                 |   2   |  D   |
| 9.3.3 | Verifiera att kumulativa beräkningsenhets- och utgiftsräknare spåras per förfrågningskedja; att överskrida gränsen avbryter kedjan. |   2   | D/V  |
| 9.3.4 | Verifiera att formell analys eller modellkontroll visar frånvaro av obegränsad rekursion i agentprotokoll.                          |   3   |  V   |
| 9.3.5 | Verifiera att loop-avbrottshändelser genererar varningar och matar kontinuerliga förbättringsmått.                                  |   3   |  D   |

---

## 9.4 Skydd mot missbruk på protokollnivå

Säkra kommunikationskanaler mellan agenter och externa system för att förhindra kapning eller manipulation.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Verifiera att alla meddelanden från agent till verktyg och agent till agent är autentiserade (t.ex. ömsesidig TLS eller JWT) och end-to-end-krypterade. |   1   | D/V  |
| 9.4.2 | Verifiera att scheman strikt valideras; okända fält eller felaktigt formaterade meddelanden avvisas.                                                    |   1   |  D   |
| 9.4.3 | Verifiera att integritetskontroller (MAC:ar eller digitala signaturer) täcker hela meddelandets nyttolast inklusive verktygsparametrar.                 |   2   | D/V  |
| 9.4.4 | Verifiera att uppspelningsskydd (nonces eller tidsstämpelsfönster) genomförs på protokollagret.                                                         |   2   |  D   |
| 9.4.5 | Verifiera att protokollimplementationer genomgår fuzz-testning och statisk analys för injektions- eller deserialiseringsfel.                            |   3   |  V   |

---

## 9.5 Agentidentitet och manipuleringsskydd

Säkerställ att åtgärder kan tillskrivas och att ändringar är upptäckbara.

|   #   | Description                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Verifiera att varje agentinstans har en unik kryptografisk identitet (nyckelpar eller hårdvarubaserad certifikat).          |   1   | D/V  |
| 9.5.2 | Verifiera att alla agentåtgärder är signerade och tidsstämplade; loggar inkluderar signaturen för att förhindra förnekande. |   2   | D/V  |
| 9.5.3 | Verifiera att manipulationssäkra loggar lagras i ett endast-tilläggs- eller skriv-enda medium.                              |   2   |  V   |
| 9.5.4 | Verifiera att identitetsnycklar roteras enligt ett definierat schema och vid indikatorer på intrång.                        |   3   |  D   |
| 9.5.5 | Verifiera att förfalsknings- eller nyckelkonfliktsförsök omedelbart leder till karantän av den berörda agenten.             |   3   | D/V  |

---

## 9.6 Multifagent-svärm Riskreduktion

Minska risker relaterade till kollektivt beteende genom isolering och formell säkerhetsmodellering.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Verifiera att agenter som arbetar i olika säkerhetsdomäner körs i isolerade exekveringsmiljöer eller nätverkssegment.                           |   1   | D/V  |
| 9.6.2 | Verifiera att svärmbeteenden är modellerade och formellt verifierade för livskraft och säkerhet innan implementering.                           |   3   |  V   |
| 9.6.3 | Verifiera att driftövervakare upptäcker framväxande osäkra mönster (t.ex. oscillationer, återvändsgränder) och initierar korrigerande åtgärder. |   3   |  D   |

---

## 9.7 Användar- och verktygsautentisering/-auktorisation

Implementera robusta åtkomstkontroller för varje agentinitierad åtgärd.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Verifiera att agenter autentiserar sig som förstklassiga huvudmän till nedströms system, utan att någonsin återanvända slutanvändarens referenser. |   1   | D/V  |
| 9.7.2 | Verifiera att detaljerade auktoriseringspolicyer begränsar vilka verktyg en agent får anropa och vilka parametrar den får använda.                 |   2   |  D   |
| 9.7.3 | Verifiera att behörighetskontroller omvärderas vid varje anrop (kontinuerlig auktorisering), inte endast vid sessionsstart.                        |   2   |  V   |
| 9.7.4 | Verifiera att delegerade behörigheter automatiskt upphör att gälla och kräver nytt samtycke efter tidsgräns eller ändring av omfattning.           |   3   |  D   |

---

## 9.8 Säkerhet vid agent-till-agent-kommunikation

Kryptera och skydda integriteten för alla meddelanden mellan agenter för att förhindra avlyssning och manipulation.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Verifiera att ömsesidig autentisering och perfekt framåtriktad sekretesskryptering (t.ex. TLS 1.3) är obligatoriska för agentkanaler. |   1   | D/V  |
| 9.8.2 | Verifiera att meddelandets integritet och ursprung valideras innan bearbetning; felaktigheter utlöser larm och meddelandet avslås.    |   1   |  D   |
| 9.8.3 | Verifiera att kommunikationsmetadata (tidsstämplar, sekvensnummer) loggas för att stödja rättsmedicinsk rekonstruktion.               |   2   | D/V  |
| 9.8.4 | Verifiera att formell verifiering eller modellkontroll bekräftar att protokollstatemaskiner inte kan drivas in i osäkra tillstånd.    |   3   |  V   |

---

## 9.9 Avsiktsverifiering och begränsningsupprätthållande

Verifiera att agentens åtgärder överensstämmer med användarens angivna avsikt och systemets begränsningar.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Verifiera att förlösningsbegränsningslösare kontrollerar föreslagna åtgärder mot hårdkodade säkerhets- och policyriktlinjer.                                      |   1   |  D   |
| 9.9.2 | Verifiera att åtgärder med hög påverkan (finansiella, destruktiva, integritetskänsliga) kräver uttrycklig avsiktsbekräftelse från den initierande användaren.     |   2   | D/V  |
| 9.9.3 | Verifiera att eftervillkorskontroller säkerställer att avslutade åtgärder uppnått avsedda effekter utan sidoeffekter; avvikelser utlöser återställning.           |   2   |  V   |
| 9.9.4 | Verifiera att formella metoder (t.ex. modellkontroll, teorembevis) eller egenskapsbaserade tester visar att agentplaner uppfyller alla deklarerade begränsningar. |   3   |  V   |
| 9.9.5 | Verifiera att incidenter med avsiktsmismatch eller regelöverträdelse bidrar till kontinuerliga förbättringscykler och delning av hotinformation.                  |   3   |  D   |

---

## 9.10 Agentens resonemangsstrategisäkerhet

Säker val och utförande av olika resonemangsstrategier inklusive ReAct, Chain-of-Thought och Tree-of-Thoughts metoder.

|   #    | Description                                                                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Verifiera att valet av resonemangsstrategi använder deterministiska kriterier (inmatningskomplexitet, uppgiftstyp, säkerhetskontext) och att identiska indata ger identiska strategival inom samma säkerhetskontext.            |   1   | D/V  |
| 9.10.2 | Verifiera att varje resonemangsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikerad inmatningsvalidering, outputsanitering och exekveringstidsbegränsningar specifika för dess kognitiva tillvägagångssätt.       |   1   | D/V  |
| 9.10.3 | Verifiera att övergångar i resonstrategi loggas med fullständig kontext inklusive ingångsegenskaper, urvalskriterievärden och exekveringsmetadata för att möjliggöra rekonstruktion av revisionsspår.                           |   2   | D/V  |
| 9.10.4 | Verifiera att Tree-of-Thoughts-resonemang inkluderar grenkapningsmekanismer som avslutar utforskning när policysöverträdelser, resursbegränsningar eller säkerhetsgränser upptäcks.                                             |   2   | D/V  |
| 9.10.5 | Verifiera att ReAct (Reason-Act-Observe)-cykler inkluderar valideringskontroller vid varje fas: verifiering av resonemangssteg, auktorisering av åtgärder och sanering av observationer innan de fortsätter.                    |   2   | D/V  |
| 9.10.6 | Verifiera att prestandamått för resonemangsstrategin (exekveringstid, resursanvändning, resultatkvalitet) övervakas med automatiska varningar när mätvärden avviker från konfigurerade tröskelvärden.                           |   3   | D/V  |
| 9.10.7 | Verifiera att hybrida resonemangsmetoder som kombinerar flera strategier upprätthåller indata-validering och utdata-begränsningar för alla ingående strategier utan att kringgå några säkerhetskontroller.                      |   3   | D/V  |
| 9.10.8 | Verifiera att säkerhetstestning av resonemangsstrategier inkluderar fuzzning med felaktiga indata, adversariella prompts utformade för att tvinga till strategiomkoppling, samt gränsvillkorsprovning för varje kognitiv metod. |   3   | D/V  |

---

## 9.11 Agentens livscykelns tillståndshantering och säkerhet

Säker agentinitiering, tillståndsövergångar och avslut med kryptografiska revisionsspår och definierade återställningsprocedurer.

|   #    | Description                                                                                                                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Verifiera att agentens initiering inkluderar fastställande av kryptografisk identitet med hårdvarustödda autentiseringsuppgifter och oföränderliga startrevisionsloggar som innehåller agent-ID, tidsstämpel, konfigurationshash och initieringsparametrar.                              |   1   | D/V  |
| 9.11.2 | Verifiera att agentens tillståndsövergångar är kryptografiskt signerade, tidsstämplade och loggade med fullständig kontext inklusive utlöst händelse, tidigare tillståndshash, ny tillståndshash och utförda säkerhetsvalideringar.                                                      |   2   | D/V  |
| 9.11.3 | Verifiera att agentens avstängningsprocedurer inkluderar säker radering av minne med kryptografisk gallring eller flergångsöverskrivning, återkallelse av behörigheter med notifiering till certifikatutfärdande myndighet, samt generering av manipulation-säker avslutningscertifikat. |   2   | D/V  |
| 9.11.4 | Verifiera att agentens återställningsmekanismer validerar tillståndets integritet med hjälp av kryptografiska kontrollsummor (minst SHA-256) och återgår till kända godtyckliga tillstånd när korruption upptäcks, med automatiska varningar och krav på manuell godkännande.            |   3   | D/V  |
| 9.11.5 | Verifiera att agentens uthållighetsmekanismer krypterar känslig statusdata med per-agent AES-256-nycklar och implementerar säker nyckelrotation enligt konfigurerbara scheman (maximalt 90 dagar) med implementering utan driftstopp.                                                    |   3   | D/V  |

---

## 9.12 Ramverk för Säkerhet vid Verktygsintegration

Säkerhetskontroller för dynamisk verktygsladdning, körning och resultatvalidering med definierade riskbedömnings- och godkännandeprocesser.

|   #    | Description                                                                                                                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Verifiera att verktygsbeskrivare inkluderar säkerhetsmetadata som specificerar nödvändiga privilegier (läs/skriv/utför), risknivåer (låg/medel/hög), resursbegränsningar (CPU, minne, nätverk) samt valideringskrav dokumenterade i verktygsmanifest.       |   1   | D/V  |
| 9.12.2 | Verifiera att verktygsexekveringsresultat valideras mot förväntade scheman (JSON-schema, XML-schema) och säkerhetspolicyer (utmatningssanering, dataklassificering) innan integration, med tidsgränser och felhanteringsprocedurer.                         |   1   | D/V  |
| 9.12.3 | Verifiera att verktygsinteraktionsloggar inkluderar detaljerad säkerhetskontext, inklusive privilegianvändning, dataåtkomstmönster, exekveringstid, resursförbrukning och returkoder med strukturerad loggning för SIEM-integration.                        |   2   | D/V  |
| 9.12.4 | Verifiera att dynamiska verktygsladdningsmekanismer validerar digitala signaturer med PKI-infrastruktur och implementerar säkra laddningsprotokoll med sandbox-isolering och behörighetsverifiering innan exekvering.                                       |   2   | D/V  |
| 9.12.5 | Verifiera att säkerhetsbedömningar av verktyg automatiskt utlöses för nya versioner med obligatoriska godkännandetrösklar, inklusive statisk analys, dynamisk testning och granskning av säkerhetsteam med dokumenterade godkännandekriterier och SLA-krav. |   3   | D/V  |

---

### Referenser

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

