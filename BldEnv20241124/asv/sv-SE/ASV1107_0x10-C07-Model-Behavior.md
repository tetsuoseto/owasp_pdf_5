# C7 Modellbeteende, Utgångskontroll och Säkerhetsgaranti

## Kontrollmål

Modellutdata måste vara strukturerade, tillförlitliga, säkra, förklarliga och kontinuerligt övervakade i produktion. Detta minskar hallucinationer, integritetsläckor, skadligt innehåll och okontrollerade åtgärder, samtidigt som användarnas förtroende och regelefterlevnad ökar.

---

## C7.1 Tillämpning av utdataformat

Strikta scheman, begränsad avkodning och efterföljande validering stoppar felaktigt formaterat eller skadligt innehåll innan det sprids.

|   #   | Description                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Verifiera att svarsformat (t.ex. JSON Schema) tillhandahålls i systemprompten och att varje utdata automatiskt valideras; utdata som inte överensstämmer utlöser reparation eller avvisning. |   1   | D/V  |
| 7.1.2 | Verifiera att begränsad avkodning (stopptoken, regex, max-token) är aktiverad för att förhindra överflöd eller sidoeffekter från prompt-injektion.                                           |   1   | D/V  |
| 7.1.3 | Verifiera att nedströmskomponenter behandlar utdata som icke-pålitliga och validerar dem mot scheman eller injektionssäkra deserialiserare.                                                  |   2   | D/V  |
| 7.1.4 | Verifiera att felaktiga utdatahändelser loggas, hastighetsbegränsas och visas i övervakningen.                                                                                               |   3   |  V   |

---

## C7.2 Hallucinationsdetektion och åtgärder

Osäkerhetsbedömning och fallback-strategier begränsar fabricerade svar.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.2.1 | Verifiera att token-nivå log-sannolikheter, ensemble självkonsekvens eller finjusterade hallucinationsdetektorer tilldelar en förtroendescore till varje svar.           |   1   | D/V  |
| 7.2.2 | Verifiera att svar under en konfigurerbar förtroendenivå utlöser fallback-arbetsflöden (t.ex. hämtning-förstärkt generering, sekundär modell eller mänsklig granskning). |   1   | D/V  |
| 7.2.3 | Verifiera att hallucinationhändelser är taggade med rotorsaksmetadata och matas in i post-mortem- och finjusteringspipelines.                                            |   2   | D/V  |
| 7.2.4 | Verifiera att tröskelvärden och detektorer kalibreras om efter större uppdateringar av modellen eller kunskapsbasen.                                                     |   3   | D/V  |
| 7.2.5 | Verifiera att instrumentpanelens visualiseringar spårar hallucinationsfrekvenser.                                                                                        |   3   |  V   |

---

## C7.3 Utgångssäkerhet och sekretessfiltrering

Policysfilter och red-team-täckning skyddar användare och konfidentiell data.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Verifiera att för- och eftergenerationsklassificerare blockerar hat, trakasserier, självskada, extremist- och sexuellt explicit innehåll i enlighet med policyn. |   1   | D/V  |
| 7.3.2 | Verifiera att PII/PCI-detektering och automatisk maskering körs på varje svar; överträdelser utlöser en integritetsincident.                                     |   1   | D/V  |
| 7.3.3 | Verifiera att sekretessetiketter (t.ex. affärshemligheter) sprids över olika modaliteter för att förhindra läckage i text, bilder eller kod.                     |   2   |  D   |
| 7.3.4 | Verifiera att försök att kringgå filter eller högriskklassificeringar kräver sekundär godkännande eller användarautentisering igen.                              |   3   | D/V  |
| 7.3.5 | Verifiera att filtreringströsklar återspeglar juridiska jurisdiktioner samt användarens ålder/rollkontext.                                                       |   3   | D/V  |

---

## C7.4 Begränsning av utdata och åtgärder

Hastighetsbegränsningar och godkännandekontroller förhindrar missbruk och överdriven autonomi.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Verifiera att kvoter per användare och per API-nyckel begränsar förfrågningar, token och kostnader med exponentiell återförsök vid 429-fel.                               |   1   |  D   |
| 7.4.2 | Verifiera att privilegierade åtgärder (filskrivningar, kodkörning, nätverksanrop) kräver policybaserat godkännande eller mänsklig inblandning.                            |   1   | D/V  |
| 7.4.3 | Verifiera att korsmodal konsekvenskontroll säkerställer att bilder, kod och text som genereras för samma förfrågan inte kan användas för att smuggla illvilligt innehåll. |   2   | D/V  |
| 7.4.4 | Verifiera att agentdelegeringsdjup, rekursionsgränser och tillåtna verktygslistor är tydligt konfigurerade.                                                               |   2   |  D   |
| 7.4.5 | Verifiera att överträdelser av begränsningar genererar strukturerade säkerhetshändelser för SIEM-inmatning.                                                               |   3   |  V   |

---

## C7.5 Utdataförklarbarhet

Transparanta signaler förbättrar användarnas förtroende och intern felsökning.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Verifiera att användarorienterade förtroendesiffror eller kortfattade resonemangssammanfattningar visas när riskbedömningen anser det lämpligt. |   2   | D/V  |
| 7.5.2 | Verifiera att genererade förklaringar undviker att avslöja känsliga systemuppmaningar eller proprietär data.                                    |   2   | D/V  |
| 7.5.3 | Verifiera att systemet fångar upp sannolikheter på token-nivå eller uppmärksamhetskartor och lagrar dem för auktoriserad inspektion.            |   3   |  D   |
| 7.5.4 | Verifiera att förklarbarhetsartefakter är versionsstyrda tillsammans med modellsläpp för spårbarhet.                                            |   3   |  V   |

---

## C7.6 Övervakningsintegration

Realtidsobservation sluter kretsen mellan utveckling och produktion.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Verifiera att metriker (schemabrott, hallucinationsfrekvens, toxicitet, PII-läckor, latens, kostnad) strömmas till en central övervakningsplattform. |   1   |  D   |
| 7.6.2 | Verifiera att larmtrösklar är definierade för varje säkerhetsmått, med eskaleringsvägar för beredskap.                                               |   1   |  V   |
| 7.6.3 | Verifiera att instrumentpaneler korrelerar utdataavvikelser med modell/version, feature-flagga och ändringar i upstream-data.                        |   2   |  V   |
| 7.6.4 | Verifiera att övervakningsdata matas tillbaka till omträning, finjustering eller regeluppdateringar inom en dokumenterad MLOps-arbetsflöde.          |   2   | D/V  |
| 7.6.5 | Verifiera att övervakningspipelines är penetrationsprovade och åtkomstkontrollerade för att undvika läckage av känsliga loggar.                      |   3   |  V   |

---

## 7.7 Säkerhetsåtgärder för generativ media

Säkerställ att AI-system inte genererar olagligt, skadligt eller obehörigt mediainnehåll genom att tillämpa policybegränsningar, validering av output och spårbarhet.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.7.1 | Verifiera att systemuppmaningar och användarinstruktioner uttryckligen förbjuder generering av olagligt, skadligt eller icke-samtyckande deepfake-material (t.ex. bild, video, ljud).                        |   1   | D/V  |
| 7.7.2 | Verifiera att uppmaningar filtreras för försök att generera imitationer, sexuellt explicita deepfakes eller media som avbildar verkliga individer utan samtycke.                                             |   2   | D/V  |
| 7.7.3 | Verifiera att systemet använder perceptuell hashing, vattenmärkning eller fingeravtryck för att förhindra obehörig kopiering av upphovsrättsskyddat material.                                                |   2   |  V   |
| 7.7.4 | Verifiera att all genererad media är kryptografiskt signerad, vattenmärkt eller inbäddad med manipulationssäker ursprungsmetadata för spårbarhet nedströms.                                                  |   3   | D/V  |
| 7.7.5 | Verifiera att försök till omgåelse (t.ex. förvrängning av prompt, slang, adversariella formuleringar) upptäcks, loggas och hastighetsbegränsas; upprepade överträdelser rapporteras till övervakningssystem. |   3   |  V   |

## Referenser

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

