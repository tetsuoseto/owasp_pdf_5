# C2 Gebruikersinvoervalidatie

## Beheersdoelstelling

Robuuste validatie van gebruikersinvoer is een eerste verdedigingslinie tegen enkele van de meest schadelijke aanvallen op AI-systemen. Prompt-injectie-aanvallen kunnen systeeminstructies overschrijven, gevoelige gegevens lekken of het model aansturen naar gedrag dat niet is toegestaan. Tenzij er speciale filters en instructiehiërarchieën aanwezig zijn, toont onderzoek aan dat "multi-shot" jailbreaks die gebruikmaken van zeer lange contextvensters effectief zullen zijn. Ook subtiele aanvalsverstoringen—zoals homoglyph-wisselingen of leetspeak—kunnen geruisloos de beslissingen van een model veranderen.

---

## C2.1 Prompt Injection Verdediging

Promptinjectie is een van de grootste risico's voor AI-systemen. Verdedigingen tegen deze tactiek maken gebruik van een combinatie van statische patroonfilters, dynamische classificatoren en handhaving van instructiehiërarchie.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Verifieer dat gebruikersinvoer wordt gecontroleerd aan de hand van een continu bijgewerkte bibliotheek van bekende promptinjectiepatronen (jailbreak-trefwoorden, "negeer voorgaande", rollenspelketens, indirecte HTML/URL-aanvallen). |   1   | D/V  |
| 2.1.2 | Controleer of het systeem een instructiehiërarchie afdwingt waarbij systeem- of ontwikkelaarsberichten gebruikersinstructies overschrijven, zelfs na uitbreiding van het contextvenster.                                                |   1   | D/V  |
| 2.1.3 | Verifieer dat adversariale evaluatietests (bijv. Red Team "many-shot" prompts) worden uitgevoerd vóór elke release van een model of prompt-sjabloon, met succesratio-drempels en geautomatiseerde blokkeringen voor regressies.         |   2   | D/V  |
| 2.1.4 | Controleer of prompts afkomstig van content van derden (webpagina's, PDF's, e-mails) worden geschoond in een geïsoleerde parsingcontext voordat ze worden samengevoegd met de hoofdprompt.                                              |   2   |  D   |
| 2.1.5 | Controleer of alle updates van prompt-filterregels, versies van classificatormodellen en wijzigingen in de blokkadelijst versiebeheerbaar en controleerbaar zijn.                                                                       |   3   | D/V  |

---

## C2.2 Weerstand tegen tegenvoorbeelden

Modellen voor natuurlijke taalverwerking (NLP) zijn nog steeds kwetsbaar voor subtiele verstoringen op karakter- of woordniveau die mensen vaak over het hoofd zien, maar die modellen vaak verkeerd classificeren.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Controleer of de basisstappen voor invoernormalisatie (Unicode NFC, homoglyph-mapping, witruimte-trimming) worden uitgevoerd vóór de tokenisatie.                                                 |   1   |  D   |
| 2.2.2 | Controleer of statistische anomaliedetectie invoer markeert met een ongewoon hoge bewerkingsafstand tot taalkundige normen, overmatige herhaalde tokens of abnormale embedding-afstanden.         |   2   | D/V  |
| 2.2.3 | Controleer of de inferentie-pijplijn optionele modelvarianten met adversariële training of verdedigingslagen (bijv. randomisatie, defensieve distillatie) ondersteunt voor hoogrisico-eindpunten. |   2   |  D   |
| 2.2.4 | Verifieer dat vermoede adversariale invoer in quarantaine wordt geplaatst en wordt geregistreerd met volledige payloads (na verwijdering van persoonlijk identificeerbare informatie – PII).      |   2   |  V   |
| 2.2.5 | Verifieer dat robuustheidsmaatregelen (succespercentage van bekende aanvalspakketten) in de loop van de tijd worden gevolgd en dat regressies een release-blocker activeren.                      |   3   | D/V  |

---

## C2.3 Schema-, Type- en Lengtevalidatie

AI-aanvallen met onjuist gevormde of te grote invoer kunnen parsingfouten veroorzaken, overschrijding van prompts over velden heen en uitputting van middelen. Strikte naleving van het schema is ook een vereiste bij het uitvoeren van deterministische toolaanroepen.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Controleer of elke API- of functieaanroependpoint een expliciet invoerschema definieert (JSON Schema, Protobuf of multimodaal equivalent) en dat invoerfouten worden gevalideerd voordat de prompt wordt samengesteld. |   1   |  D   |
| 2.3.2 | Controleer of invoer die de maximale limiet voor tokens of bytes overschrijdt wordt afgewezen met een veilige foutmelding en nooit stilzwijgend wordt afgekapt.                                                        |   1   | D/V  |
| 2.3.3 | Controleer of typecontroles (bijv. numerieke bereiken, enumwaarden, MIME-typen voor afbeeldingen/audio) aan de serverzijde worden afgedwongen, en niet alleen in de clientcode.                                        |   2   | D/V  |
| 2.3.4 | Controleer of semantische validateurs (bijv. JSON Schema) in constante tijd worden uitgevoerd om algoritmische DoS te voorkomen.                                                                                       |   2   |  D   |
| 2.3.5 | Controleer of validatiefouten worden vastgelegd met gecensureerde payloadfragmenten en ondubbelzinnige foutcodes om veiligheidsdrietal te ondersteunen.                                                                |   3   |  V   |

---

## C2.4 Inhouds- en Beleidscontrole

Ontwikkelaars moeten in staat zijn om syntactisch geldige prompts te detecteren die niet-toegestane inhoud aanvragen (zoals illegale instructies, haatzaaiende uitlatingen en auteursrechtelijk beschermd materiaal) en moeten vervolgens voorkomen dat deze zich verspreiden.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Controleer dat een contentclassificator (zero shot of fijn afgesteld) elke invoer beoordeelt op geweld, zelfbeschadiging, haat, seksuele inhoud en illegale verzoeken, met configureerbare drempelwaarden. |   1   |  D   |
| 2.4.2 | Controleer of invoer die de beleidsregels overtreedt gestandaardiseerde weigeringen of veilige voltooiingen ontvangt, zodat deze niet doorgegeven worden aan volgende LLM-aanroepen.                       |   1   | D/V  |
| 2.4.3 | Controleer of het screeningsmodel of regelsysteem ten minste elk kwartaal wordt opnieuw getraind/geüpdatet, waarbij nieuw waargenomen jailbreak- of beleidsomzeilingspatronen worden opgenomen.            |   2   |  D   |
| 2.4.4 | Verifieer dat screening gebruikersspecifieke beleidsregels respecteert (leeftijd, regionale wettelijke beperkingen) via attribuutgebaseerde regels die worden opgelost op het moment van de aanvraag.      |   2   |  D   |
| 2.4.5 | Controleer of screeningslogboeken de betrouwbaarheidscores van de classifier en beleidscategorie-tags bevatten voor SOC-correlatie en toekomstige redteam-herhaling.                                       |   3   |  V   |

---

## C2.5 Invoersnelheid Beperking & Misbruik Preventie

Ontwikkelaars moeten misbruik, uitputting van middelen en geautomatiseerde aanvallen op AI-systemen voorkomen door het beperken van invoersnelheden en het detecteren van afwijkende gebruikspatronen.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Controleer of per-gebruiker, per-IP en per-API-sleutel snelheidslimieten worden afgedwongen voor alle invoerendpoints.                        |   1   | D/V  |
| 2.5.2 | Controleer of burst- en voortdurende snelheidslimieten zijn afgesteld om DoS- en brute force-aanvallen te voorkomen.                          |   2   | D/V  |
| 2.5.3 | Controleer of afwijkende gebruikspatronen (bijv. razendsnelle verzoeken, inputoverstroming) automatische blokkades of escalaties veroorzaken. |   2   | D/V  |
| 2.5.4 | Controleer of misbruikpreventielogs worden bewaard en beoordeeld op opkomende aanvalspatronen.                                                |   3   |  V   |

---

## C2.6 Multi-modale invoervalidatie

AI-systemen moeten robuuste validatie bevatten voor niet-tekstuele invoer (afbeeldingen, audio, bestanden) om injectie, ontwijking of misbruik van middelen te voorkomen.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Controleer of alle niet-tekstuele invoer (afbeeldingen, audio, bestanden) wordt gevalideerd op type, grootte en formaat voordat ze worden verwerkt. |   1   |  D   |
| 2.6.2 | Verifieer dat bestanden worden gescand op malware en steganografische payloads voordat ze worden opgenomen.                                         |   2   | D/V  |
| 2.6.3 | Controleer of beeld-/geluidsinvoer wordt gecontroleerd op vijandige verstoringen of bekende aanvalspatronen.                                        |   2   | D/V  |
| 2.6.4 | Controleer of multi-modale invoervalidatiefouten worden geregistreerd en waarschuwingen activeren voor onderzoek.                                   |   3   |  V   |

---

## C2.7 Invoergegevensherkomst & Toeschrijving

AI-systemen moeten ondersteuning bieden voor auditing, misbruiktracking en naleving door het monitoren en taggen van de herkomst van alle gebruikersinvoer.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Verifieer dat alle gebruikersinvoer tijdens het binnenkomen worden voorzien van metadata (gebruikers-ID, sessie, bron, tijdstempel, IP-adres). |   1   | D/V  |
| 2.7.2 | Controleer of de herkomstmetadata wordt bewaard en controleerbaar is voor alle verwerkte invoer.                                               |   2   | D/V  |
| 2.7.3 | Verifieer dat afwijkende of niet-vertrouwde invoerbronnen worden gemarkeerd en onderworpen aan verhoogde controle of blokkering.               |   2   | D/V  |

---

## C2.8 Real-time adaptieve bedreigingsdetectie

Ontwikkelaars zouden geavanceerde bedreigingsdetectiesystemen voor AI moeten gebruiken die zich aanpassen aan nieuwe aanvalspatronen en realtime bescherming bieden met gecompileerde patroonherkenning.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Controleer of dreigingsdetectiepatronen zijn gecompileerd in geoptimaliseerde regex-engines voor hoge prestaties bij real-time filtering met minimale latentie-impact.                                                              |   1   | D/V  |
| 2.8.2 | Controleer of de bedreigingsdetectiesystemen aparte patroonbibliotheken onderhouden voor verschillende bedreigingscategorieën (promptinjectie, schadelijke inhoud, gevoelige gegevens, systeemopdrachten).                          |   1   | D/V  |
| 2.8.3 | Controleer of adaptieve dreigingsdetectie machinaal-lerende modellen bevat die de dreigingsgevoeligheid bijwerken op basis van aanvalfrequentie en succeskansen.                                                                    |   2   | D/V  |
| 2.8.4 | Controleer of realtime dreigingsinformatie feeds de patroonbibliotheken automatisch bijwerken met nieuwe aanvalssignaturen en IOCs (Indicators of Compromise).                                                                      |   2   | D/V  |
| 2.8.5 | Controleer of de fout-positieve meldingspercentages van bedreigingsdetectie continu worden gemonitord en of de patroon-specificiteit automatisch wordt aangepast om interferentie met legitieme gebruikssituaties te minimaliseren. |   3   | D/V  |
| 2.8.6 | Controleer of contextuele dreigingsanalyse rekening houdt met de invoerbron, patronen in gebruikersgedrag en sessiegeschiedenis om de detectienauwkeurigheid te verbeteren.                                                         |   3   | D/V  |
| 2.8.7 | Verifieer dat prestatie-indicatoren voor dreigingsdetectie (detectiesnelheid, verwerkingslatentie, resourcegebruik) in realtime worden bewaakt en geoptimaliseerd.                                                                  |   3   | D/V  |

---

## C2.9 Multi-modale beveiligingsvalidatiepipeline

Ontwikkelaars moeten beveiligingsvalidatie bieden voor tekst-, beeld-, audio- en andere AI-invoermodaliteiten met specifieke soorten bedreigingsdetectie en resource-isolatie.

|   #   | Description                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Controleer of elke invoermodaliteit specifieke beveiligingsvalidators heeft met gedocumenteerde dreigingspatronen (tekst: promptinjectie, afbeeldingen: steganografie, audio: spectrogramaanvallen) en detectiedrempels.                                             |   1   | D/V  |
| 2.9.2 | Controleer of multimodale inputs worden verwerkt in geïsoleerde sandboxes met gedefinieerde resourcebeperkingen (geheugen, CPU, verwerkingstijd) die specifiek zijn voor elk modaliteitstype en gedocumenteerd in beveiligingsbeleid.                                |   2   | D/V  |
| 2.9.3 | Verifieer dat kruismodale aanvaldetectie gecoördineerde aanvallen over meerdere invoertypen (bijvoorbeeld steganografische payloads in afbeeldingen gecombineerd met promptinjectie in tekst) identificeert met correlatieregels en waarschuwinggeneratie.           |   2   | D/V  |
| 2.9.4 | Verifieer dat multi-modale validatiefouten gedetailleerde logging activeren, inclusief alle inputmodaliteiten, validatieresultaten, dreigingsscores en correlatieanalyse met gestructureerde logformaten voor SIEM-integratie.                                       |   3   | D/V  |
| 2.9.5 | Controleer of modaliteit-specifieke inhoudsclassificatoren worden bijgewerkt volgens de gedocumenteerde schema's (minimaal elk kwartaal) met nieuwe bedreigingspatronen, adversariële voorbeelden en prestatiebenchmarks die boven de basisdrempels worden gehouden. |   3   | D/V  |

---

## Referenties

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

