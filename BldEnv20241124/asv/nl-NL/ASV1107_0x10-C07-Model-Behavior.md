# C7 Modelgedrag, Uitvoercontrole & Veiligheidsgarantie

## Controle Doelstelling

Modeluitvoer moet gestructureerd, betrouwbaar, veilig, verklaarbaar en continu gemonitord worden in productie. Dit vermindert hallucinaties, privacylekken, schadelijke inhoud en ongecontroleerde acties, terwijl het het vertrouwen van gebruikers en naleving van regelgeving verhoogt.

---

## C7.1 Handhaving van het uitvoerformaat

Strikte schema's, beperkte decodering en downstream validatie voorkomen dat verkeerd gevormde of kwaadaardige inhoud zich verspreidt.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Controleer of responschema's (bijv. JSON-schema) in de systeemprompt zijn opgenomen en dat elke output automatisch wordt gevalideerd; niet-conforme outputs veroorzaken reparatie of afwijzing. |   1   | D/V  |
| 7.1.2 | Controleer of beperkt decoderen (stopwoorden, regex, maximum aantal tokens) is ingeschakeld om overflow of prompt-injectie-zijkanalen te voorkomen.                                             |   1   | D/V  |
| 7.1.3 | Controleer of downstreamcomponenten de output als onbetrouwbaar behandelen en deze valideren aan de hand van schema's of injectieveilige deserializers.                                         |   2   | D/V  |
| 7.1.4 | Controleer of onjuiste-uitvoer gebeurtenissen worden gelogd, geratelimiteerd en zichtbaar gemaakt voor monitoring.                                                                              |   3   |  V   |

---

## C7.2 Detectie en mitigatie van hallucinaties

Onzekerheidsinschatting en terugvalstrategieën beperken gefabriceerde antwoorden.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.2.1 | Controleer of token-niveau log-waarschijnlijkheden, ensemble zelfconsistentie, of fijn-afgestelde hallucinatie detectoren een betrouwbaarheidscore toewijzen aan elk antwoord.                   |   1   | D/V  |
| 7.2.2 | Controleer of antwoorden onder een configureerbare betrouwbaarheidsdrempel fallback-workflows activeren (bijvoorbeeld retrieval-augmented generatie, secundair model of menselijke beoordeling). |   1   | D/V  |
| 7.2.3 | Controleer of hallucinatie-incidenten worden gelabeld met root-cause metadata en worden doorgegeven aan post-mortem en fijnsturing pipelines.                                                    |   2   | D/V  |
| 7.2.4 | Controleer of drempels en detectoren opnieuw worden gekalibreerd na grote model- of kennisbankupdates.                                                                                           |   3   | D/V  |
| 7.2.5 | Controleer of dashboardvisualisaties de hallucinatiepercentages bijhouden.                                                                                                                       |   3   |  V   |

---

## C7.3 Output Veiligheid & Privacy Filtering

Beleidsfilters en red-teamdekking beschermen gebruikers en vertrouwelijke gegevens.

|   #   | Description                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Controleer of pre- en post-generatie-classifiers haat, intimidatie, zelfbeschadiging, extremistische en seksueel expliciete inhoud die in overeenstemming is met het beleid blokkeren. |   1   | D/V  |
| 7.3.2 | Verifieer dat PII/PCI-detectie en automatische redactie op elke reactie worden uitgevoerd; overtredingen leiden tot een privacy-incident.                                              |   1   | D/V  |
| 7.3.3 | Controleer of vertrouwelijkheidslabels (bijv. handelsgeheimen) zich over modaliteiten heen voortplanten om lekken in tekst, afbeeldingen of code te voorkomen.                         |   2   |  D   |
| 7.3.4 | Controleer of pogingen om filters te omzeilen of classificaties met een hoog risico secundaire goedkeuring of gebruikerherauthenticatie vereisen.                                      |   3   | D/V  |
| 7.3.5 | Controleer of de filterdrempels overeenkomen met de wettelijke jurisdicties en de context van de leeftijd/rol van de gebruiker.                                                        |   3   | D/V  |

---

## C7.4 Beperking van uitvoer en acties

Tariefbeperkingen en goedkeuringspoorten voorkomen misbruik en buitensporige autonomie.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.4.1 | Controleer of per-gebruiker en per-API-sleutel quota verzoeken, tokens en kosten beperken met exponentiële back-off bij 429-fouten.                                                                          |   1   |  D   |
| 7.4.2 | Controleer of bevoorrechte acties (bestandsschrijvingen, code-uitvoering, netwerkoproepen) goedkeuring op basis van beleid of menselijke tussenkomst vereisen.                                               |   1   | D/V  |
| 7.4.3 | Controleer of cross-modale consistentiecontroles ervoor zorgen dat afbeeldingen, code en tekst die voor dezelfde aanvraag zijn gegenereerd, niet kunnen worden gebruikt om kwaadaardige inhoud te smokkelen. |   2   | D/V  |
| 7.4.4 | Controleer of de diepte van agentdelegatie, recursielimieten en toegestane lijst met tools expliciet zijn geconfigureerd.                                                                                    |   2   |  D   |
| 7.4.5 | Verifieer dat het overschrijden van limieten gestructureerde beveiligingsgebeurtenissen genereert voor SIEM-inname.                                                                                          |   3   |  V   |

---

## C7.5 Output Verklaarbaarheid

Transparante signalen verbeteren het vertrouwen van gebruikers en interne foutopsporing.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.5.1 | Controleer of gebruikergeoriënteerde betrouwbaarheidscores of korte redeneersamenvattingen worden weergegeven wanneer de risicobeoordeling dit passend acht. |   2   | D/V  |
| 7.5.2 | Controleer of gegenereerde verklaringen vermijden dat gevoelige systeemopdrachten of vertrouwelijke gegevens worden onthuld.                                 |   2   | D/V  |
| 7.5.3 | Verifieer dat het systeem token-niveau log-waarschijnlijkheden of aandachtkaarten vastlegt en opslaat voor geautoriseerde inspectie.                         |   3   |  D   |
| 7.5.4 | Verifieer dat uitlegbaarheidsartefacten versiebeheer hebben naast modelreleases voor controleerbaarheid.                                                     |   3   |  V   |

---

## C7.6 Integratie van monitoring

Realtime observeerbaarheid sluit de lus tussen ontwikkeling en productie.

|   #   | Description                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Verifieer dat metriekgegevens (schema-overtredingen, hallucinatiepercentage, toxiciteit, PII-lekken, latentie, kosten) worden gestreamd naar een centraal monitoringplatform. |   1   |  D   |
| 7.6.2 | Controleer of waarschuwingsdrempels zijn gedefinieerd voor elke veiligheidsmaatstaf, met escalatieroutes voor dienstdoende medewerkers.                                       |   1   |  V   |
| 7.6.3 | Controleer of dashboards outputanomalieën correleren met model/version, featureflag en wijzigingen in upstream-gegevens.                                                      |   2   |  V   |
| 7.6.4 | Controleer of monitoringgegevens terugvloeien in het retrainen, fijn afstemmen of bijwerken van regels binnen een gedocumenteerde MLOps-werkstroom.                           |   2   | D/V  |
| 7.6.5 | Controleer of monitoringpijplijnen zijn onderworpen aan penetratietests en toegangscontrole om het lekken van gevoelige logbestanden te voorkomen.                            |   3   |  V   |

---

## 7.7 Generatieve Media Beveiligingen

Zorg ervoor dat AI-systemen geen illegale, schadelijke of niet-geautoriseerde mediacontent genereren door het afdwingen van beleidsbeperkingen, outputvalidatie en traceerbaarheid.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Controleer of systeemopdrachten en gebruikersinstructies expliciet het genereren van illegale, schadelijke of niet-consensuele deepfake-media (bijv. afbeelding, video, audio) verbieden.                       |   1   | D/V  |
| 7.7.2 | Controleer of prompts worden gefilterd op pogingen om imitaties te genereren, seksueel expliciete deepfakes, of media die echte personen zonder toestemming afbeelden.                                          |   2   | D/V  |
| 7.7.3 | Verifieer dat het systeem gebruikmaakt van perceptuele hashing, watermerkdetectie of fingerprinting om ongeoorloofde reproductie van auteursrechtelijk beschermd materiaal te voorkomen.                        |   2   |  V   |
| 7.7.4 | Verifieer dat alle gegenereerde media cryptografisch zijn ondertekend, watermerk bevatten of zijn ingebed met manipulatiebestendige herkomstmetadata voor traceerbaarheid in latere stadia.                     |   3   | D/V  |
| 7.7.5 | Controleer of pogingen tot omzeiling (bijv. promptverduistering, straattaal, vijandige formuleringen) worden gedetecteerd, gelogd en gelimiteerd; herhaald misbruik wordt gerapporteerd aan monitoringsystemen. |   3   |  V   |

## Referenties

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

