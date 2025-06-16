# C7 Modeladfærd, outputkontrol og sikkerhedssikring

## Kontrolmål

Modeloutput skal være strukturerede, pålidelige, sikre, forklarlige og løbende overvågede i produktionen. Dette reducerer hallucinationer, privatlivslækager, skadeligt indhold og ukontrollerede handlinger, samtidig med at det øger brugertillid og overholdelse af lovgivning.

---

## C7.1 Håndhævelse af outputformat

Strenge skemaer, begrænset dekodning og efterfølgende validering stopper fejlbehæftet eller ondsindet indhold, før det spreder sig.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Bekræft, at svarskemaer (f.eks. JSON Schema) er angivet i systemprompten, og at hvert output automatisk valideres; ikke-konforme output udløser reparation eller afvisning. |   1   | D/V  |
| 7.1.2 | Bekræft, at begrænset dekodning (stoptokens, regex, maksimale token) er aktiveret for at forhindre overflow eller prompt-injektions sidekanaler.                            |   1   | D/V  |
| 7.1.3 | Sørg for, at nedstrøms komponenter behandler output som uautoriserede og validerer dem mod skemaer eller injektionssikre de-serialisatorer.                                 |   2   | D/V  |
| 7.1.4 | Bekræft, at fejludgangsbegivenheder bliver logget, ratebegrænset og vist i overvågningen.                                                                                   |   3   |  V   |

---

## C7.2 Hallucinationsdetektion og afhjælpning

Usikkerhedsvurdering og fallback-strategier begrænser fabrikerede svar.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Bekræft, at token-niveau log-sandsynligheder, ensemble selvkonsistens eller finjusterede hallucinationsdetektorer tildeler en tillidsværdi til hvert svar.                |   1   | D/V  |
| 7.2.2 | Bekræft, at svar under en konfigurerbar tillidsgrænse udløser fallback-arbejdsgange (f.eks. retrieval-augmented generation, sekundær model eller menneskelig gennemgang). |   1   | D/V  |
| 7.2.3 | Sørg for, at hallucinationshændelser bliver mærket med rodårsagsmetadata og tilført til post-mortem- og finjusteringspipelines.                                           |   2   | D/V  |
| 7.2.4 | Bekræft, at tærskler og detektorer genkalibreres efter større opdateringer af modellen eller vidensbasen.                                                                 |   3   | D/V  |
| 7.2.5 | Bekræft, at dashboard-visualiseringer overvåger hallucinationsrater.                                                                                                      |   3   |  V   |

---

## C7.3 Output-sikkerhed og privatlivsfiltrering

Politikfiltre og red-team-dækning beskytter brugere og fortrolige data.

|   #   | Description                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.3.1 | Verificer, at præ- og postgenereringsklassifikatorer blokerer had, chikane, selvskade, ekstremistisk og seksuelt eksplicit indhold i overensstemmelse med politik. |   1   | D/V  |
| 7.3.2 | Bekræft, at PII/PCI-detektion og automatisk redigering kører på hvert svar; overtrædelser forårsager en privatlivshændelse.                                        |   1   | D/V  |
| 7.3.3 | Bekræft, at fortrolighedstag (f.eks. virksomhedshemmeligheder) videreføres på tværs af modaliteter for at forhindre lækage i tekst, billeder eller kode.           |   2   |  D   |
| 7.3.4 | Bekræft, at forsøg på filtreringsomgåelse eller klassificeringer med høj risiko kræver sekundær godkendelse eller brugerens genautentificering.                    |   3   | D/V  |
| 7.3.5 | Bekræft, at filtreringsgrænser afspejler juridiske jurisdiktioner samt brugerens alder/rolle kontekst.                                                             |   3   | D/V  |

---

## C7.4 Begrænsning af output og handlinger

Raterestriktioner og godkendelsesporte forhindrer misbrug og overdreven autonomi.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Bekræft, at kvoter pr. bruger og pr. API-nøgle begrænser forespørgsler, tokens og omkostninger med eksponentiel tilbagekobling ved 429-fejl.                           |   1   |  D   |
| 7.4.2 | Bekræft, at privilegerede handlinger (filskrivninger, kodeudførelser, netværksopkald) kræver godkendelse baseret på politik eller involvering af menneske i processen. |   1   | D/V  |
| 7.4.3 | Bekræft, at tværmodal konsistenskontrol sikrer, at billeder, kode og tekst genereret til den samme anmodning ikke kan bruges til at smugle ondsindet indhold.          |   2   | D/V  |
| 7.4.4 | Bekræft, at agentdelegeringsdybde, rekursionsgrænser og tilladte værktøjslister er eksplicit konfigureret.                                                             |   2   |  D   |
| 7.4.5 | Bekræft, at overskridelse af grænser udsender strukturerede sikkerhedshændelser til SIEM-indtagning.                                                                   |   3   |  V   |

---

## C7.5 Output Forklarlighed

Gennemsigtige signaler forbedrer brugerens tillid og intern fejlfinding.

|   #   | Description                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Bekræft, at brugerorienterede tillidsvurderinger eller korte resuméer af begrundelser vises, når risikovurderingen skønner det passende. |   2   | D/V  |
| 7.5.2 | Bekræft, at genererede forklaringer undgår at afsløre følsomme systemprompter eller proprietære data.                                    |   2   | D/V  |
| 7.5.3 | Bekræft, at systemet indfanger token-niveau log-sandsynligheder eller opmærksomhedskort og gemmer dem til autoriseret inspektion.        |   3   |  D   |
| 7.5.4 | Sørg for, at forklaringsartefakter er versionsstyrede sammen med modeludgivelser for revisionssporbarhed.                                |   3   |  V   |

---

## C7.6 Overvågningsintegration

Realtime observabilitet lukker løkken mellem udvikling og produktion.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.6.1 | Bekræft, at metrikker (skemasvigter, hallucinationsrate, toksicitet, PII-lækager, latenstid, omkostninger) sendes til en central overvågningsplatform. |   1   |  D   |
| 7.6.2 | Bekræft, at alarmgrænser er defineret for hver sikkerhedsmåling, med eskaleringsveje til on-call.                                                      |   1   |  V   |
| 7.6.3 | Bekræft, at dashboards korrelerer output-anomalier med model/version, feature-flag og ændringer i opstrømsdata.                                        |   2   |  V   |
| 7.6.4 | Bekræft, at overvågningsdata feedbackes til genuddannelse, finjustering eller regelopdateringer inden for en dokumenteret MLOps-arbejdsgang.           |   2   | D/V  |
| 7.6.5 | Sørg for, at overvågningspipelines er penetrationstestet og adgangskontrolleret for at undgå lækage af følsomme logfiler.                              |   3   |  V   |

---

## 7.7 Generative medier sikkerhedsforanstaltninger

Sørg for, at AI-systemer ikke genererer ulovligt, skadeligt eller uautoriseret medieindhold ved at håndhæve politikrestriktioner, outputvalidering og sporbarhed.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Bekræft, at systemprompter og brugervejledninger eksplicit forbyder generering af ulovligt, skadeligt eller ikke-samtykkende deepfake-medie (f.eks. billede, video, lyd).                     |   1   | D/V  |
| 7.7.2 | Bekræft, at prompts bliver filtreret for forsøg på at generere efterligninger, seksuelt eksplicitte deepfakes eller medier, der viser rigtige individer uden samtykke.                        |   2   | D/V  |
| 7.7.3 | Bekræft, at systemet bruger perceptuel hashing, vandmærke-detektion eller fingeraftryk til at forhindre uautoriseret reproduktion af ophavsretligt beskyttet materiale.                       |   2   |  V   |
| 7.7.4 | Bekræft, at alt genereret medie er kryptografisk underskrevet, vandmærket eller indlejret med manipulationsresistent oprindelsesmetadata til efterfølgende sporbarhed.                        |   3   | D/V  |
| 7.7.5 | Bekræft, at forsøg på omgåelse (f.eks. promptforvrængning, slang, modstridende formuleringer) opdages, logges og begrænses i frekvens; gentagen misbrug rapporteres til overvågningssystemer. |   3   |  V   |

## Referencer

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

