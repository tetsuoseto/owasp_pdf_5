# C2 brugervalidering

## Kontrolmål

Robust validering af brugerinput er en første forsvarslinje mod nogle af de mest skadelige angreb på AI-systemer. Promptinjektionsangreb kan tilsidesætte systeminstruktioner, lække følsomme data eller styre modellen mod uacceptabel adfærd. Medmindre der er dedikerede filtre og instruktionshierarkier på plads, viser forskning, at "multi-shot" jailbreaks, som udnytter meget lange kontekstvinduer, vil være effektive. Desuden kan subtile adversariale perturbationsangreb—såsom homoglyph-udskiftninger eller leetspeak—stille og roligt ændre en models beslutninger.

---

## C2.1 Forsvar mod promptinjektion

Prompt-injektion er en af de største risici for AI-systemer. Forsvar mod denne taktik anvender en kombination af statiske mønstergeneratorer, dynamiske klassifikatorer og håndhævelse af instruktionshierarki.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Bekræft, at brugerinput bliver kontrolleret mod et kontinuerligt opdateret bibliotek af kendte promptinjektionsmønstre (jailbreak-nøgleord, "ignorér tidligere", rollespilssekvenser, indirekte HTML/URL-angreb).                         |   1   | D/V  |
| 2.1.2 | Bekræft, at systemet håndhæver en instruktionshierarki, hvor system- eller udviklerbeskeder tilsidesætter brugerens instruktioner, selv efter udvidelse af kontekstvinduet.                                                               |   1   | D/V  |
| 2.1.3 | Sørg for, at tests af modstridende evaluering (f.eks. Red Team "many-shot"-prompter) køres før hver udgivelse af en model eller prompt-skabelon, med succesrater som tærskler og automatiserede blokeringsmekanismer for regressionsfejl. |   2   | D/V  |
| 2.1.4 | Bekræft, at prompts, der stammer fra tredjepartsindhold (websider, PDF'er, e-mails), renses i en isoleret parsingskontekst, før de sammenkædes med hovedprompten.                                                                         |   2   |  D   |
| 2.1.5 | Bekræft, at alle opdateringer af prompt-filterregler, versioner af klassifikationsmodeller og ændringer i blokeringslister er versionsstyrede og reviderbare.                                                                             |   3   | D/V  |

---

## C2.2 Modstand mod fjendtlige eksempler

Naturlige sprogbehandlingsmodeller (NLP) er stadig sårbare over for subtile forstyrrelser på tegn- eller ordniveau, som mennesker ofte overser, men som modeller har en tendens til at fejlkategorisere.

|   #   | Description                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Bekræft, at grundlæggende input-normaliseringstrin (Unicode NFC, homoglyph-mapping, fjernelse af mellemrum) udføres før tokenisering.                                        |   1   |  D   |
| 2.2.2 | Bekræft, at statistisk anomalidetektion markerer input med usædvanligt høj redigeringsafstand til sprognormer, overdrevne gentagne token eller unormale indlejringsafstande. |   2   | D/V  |
| 2.2.3 | Bekræft, at inferenspipelinensupporterer valgfrie modstandsdygtige modelvarianter eller forsvarslag (f.eks. randomisering, defensiv destillation) til højrisikoendepunkter.  |   2   |  D   |
| 2.2.4 | Bekræft, at mistænkte fjendtlige input bliver isoleret, logget med fulde nyttelaster (efter fjernelse af personligt identificerbare oplysninger).                            |   2   |  V   |
| 2.2.5 | Bekræft, at robusthedsmål (successrate for kendte angrebssuites) bliver overvåget over tid, og at regressionsfejl udløser en udgivelsesblokering.                            |   3   | D/V  |

---

## C2.3 Skema, Type og Længdevalidering

AI-angreb med fejlbehæftede eller overdimensionerede input kan forårsage parsefejl, promptoverskridelse på tværs af felter og ressourceudmattelse. Streng håndhævelse af skemaet er også en forudsætning ved udførelse af deterministiske værktøjsopkald.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Sørg for, at alle API- eller funktionskaldendepunkter definerer et eksplicit inputschema (JSON Schema, Protobuf eller multimodalt ækvivalent), og at input valideres før samling af prompt. |   1   |  D   |
| 2.3.2 | Bekræft, at input, der overskrider maksimumsgrænserne for tokens eller bytes, afvises med en sikker fejl og aldrig bliver tavst afkortet.                                                   |   1   | D/V  |
| 2.3.3 | Bekræft, at typekontroller (f.eks. numeriske intervaller, enum-værdier, MIME-typer for billeder/lyd) håndhæves på serversiden og ikke kun i klientkoden.                                    |   2   | D/V  |
| 2.3.4 | Bekræft, at semantiske validatorer (f.eks. JSON Schema) kører i konstant tid for at forhindre algoritmisk DoS.                                                                              |   2   |  D   |
| 2.3.5 | Bekræft, at valideringsfejl logges med redigerede nyttelastudsnit og entydige fejlkoder for at lette sikkerhedstriangulering.                                                               |   3   |  V   |

---

## C2.4 Indholds- og politikscreening

Udviklere bør være i stand til at opdage syntaktisk gyldige prompts, der anmoder om forbudt indhold (såsom ulovlige instruktioner, hadtale og ophavsretligt beskyttet tekst), og derefter forhindre, at de spreder sig.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Bekræft, at en indholdsklassificerer (zero shot eller finjusteret) vurderer hver input for vold, selvskade, had, seksuelt indhold og ulovlige anmodninger, med konfigurerbare tærskelværdier. |   1   |  D   |
| 2.4.2 | Bekræft, at input, som overtræder politikker, vil modtage standardiserede afvisninger eller sikre afslutninger, så de ikke videreføres til efterfølgende LLM-kald.                            |   1   | D/V  |
| 2.4.3 | Bekræft, at screeningsmodellen eller regelsættet genoplæres/opdateres mindst hvert kvartal, hvor nye observerede jailbreak- eller politikomgåelsesmønstre indarbejdes.                        |   2   |  D   |
| 2.4.4 | Bekræft, at screening overholder brugerspecifikke politikker (alder, regionale juridiske begrænsninger) via attributbaserede regler, der afgøres ved anmodningstidspunktet.                   |   2   |  D   |
| 2.4.5 | Bekræft, at screeningslogfiler inkluderer klassifikatorens tillidsniveauer og politikategori-tags til SOC-korrelation og fremtidig red-team-genafspilning.                                    |   3   |  V   |

---

## C2.5 Input Rate Begrænsning & Misbrugsforebyggelse

Udviklere bør forhindre misbrug, ressourceudmattelse og automatiserede angreb mod AI-systemer ved at begrænse inputhastigheder og opdage unormale brugsmønstre.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Bekræft, at grænser for hastighedskontrol pr. bruger, pr. IP og pr. API-nøgle håndhæves for alle inputendpoints.                                |   1   | D/V  |
| 2.5.2 | Sørg for, at burst- og vedvarende hastighedsgrænser er justeret til at forhindre DoS- og brute force-angreb.                                    |   2   | D/V  |
| 2.5.3 | Bekræft, at unormale brugsmønstre (f.eks. hurtige gentagne anmodninger, inputoversvømmelse) udløser automatiske blokeringer eller eskalationer. |   2   | D/V  |
| 2.5.4 | Bekræft, at logfiler for misbrugsforebyggelse opbevares og gennemgås for at identificere nye angrebsmønstre.                                    |   3   |  V   |

---

## C2.6 Multi-modal indtastningsvalidering

AI-systemer bør inkludere robust validering for ikke-tekstuelle input (billeder, lyd, filer) for at forhindre injektion, undvigelse eller ressourcemisbrug.

|   #   | Description                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Sørg for, at alle ikke-tekst input (billeder, lyd, filer) valideres for type, størrelse og format, før de behandles. |   1   |  D   |
| 2.6.2 | Bekræft, at filer bliver scannet for malware og steganografiske payloads, før de indtastes.                          |   2   | D/V  |
| 2.6.3 | Bekræft, at billede-/lydinput kontrolleres for fjendtlige forstyrrelser eller kendte angrebsmønstre.                 |   2   | D/V  |
| 2.6.4 | Bekræft, at fejl i multimodal inputvalidering bliver logget og udløser advarsler til undersøgelse.                   |   3   |  V   |

---

## C2.7 Input-Oprindelse og Attribution

AI-systemer bør understøtte revision, misbrugsregistrering og overholdelse ved at overvåge og mærke oprindelsen af alle brugersinputs.

|   #   | Description                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.7.1 | Bekræft, at alle brugerinput er mærket med metadata (bruger-ID, session, kilde, tidsstempel, IP-adresse) ved indtagning. |   1   | D/V  |
| 2.7.2 | Bekræft, at oprindelsesmetadata bevares og er reviderbare for alle behandlede input.                                     |   2   | D/V  |
| 2.7.3 | Bekræft, at anomaløse eller ikke-pålidelige inputkilder bliver markeret og underlagt øget kontrol eller blokeret.        |   2   | D/V  |

---

## C2.8 Realtids adaptiv trusselsdetektion

Udviklere bør anvende avancerede trusselsdetekteringssystemer til AI, som tilpasser sig nye angrebsmønstre og leverer beskyttelse i realtid med kompileret mønstergenkendelse.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Bekræft, at trusselsdetektionsmønstre er kompileret til optimerede regex-motorer for højtydende realtidsfiltrering med minimal latense.                                                     |   1   | D/V  |
| 2.8.2 | Bekræft, at trusselsdetekteringssystemer opretholder separate mønstrekataloger for forskellige trusselkategorier (promptinjektion, skadeligt indhold, følsomme data, systemkommandoer).     |   1   | D/V  |
| 2.8.3 | Bekræft, at adaptiv trusseldetektion inkorporerer maskinlæringsmodeller, der opdaterer trusselsfølsomheden baseret på angrebsfrekvens og succesrater.                                       |   2   | D/V  |
| 2.8.4 | Bekræft, at realtids trusselsinformationsfeeds automatisk opdaterer mønstermapper med nye angrebssignaturer og IOC'er (indikatorer for kompromittering).                                    |   2   | D/V  |
| 2.8.5 | Bekræft, at falske positive rater i trusselsdetektion kontinuerligt overvåges, og at mønsterspecificitet automatisk justeres for at minimere forstyrrelser af legitime anvendelsestilfælde. |   3   | D/V  |
| 2.8.6 | Bekræft, at kontekstuel trusselanalyse tager højde for inputkilde, brugeradfærdsmønstre og sessionshistorik for at forbedre detektionsnøjagtigheden.                                        |   3   | D/V  |
| 2.8.7 | Bekræft, at ydelsesmetrikker for trusselsdetektion (detektionsrate, behandlingstidsforsinkelse, ressourceudnyttelse) overvåges og optimeres i realtid.                                      |   3   | D/V  |

---

## C2.9 Multi-modal sikkerhedsvalideringspipeline

Udviklere bør levere sikkerhedsvalidering for tekst, billede, lyd og andre AI-indgangsmodaliteter med specifikke typer af trusselsdetektion og ressourceisolering.

|   #   | Description                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Bekræft, at hver inputmodalitet har dedikerede sikkerhedsvalideringsværktøjer med dokumenterede trusselsmønstre (tekst: promptinjektion, billeder: steganografi, lyd: spektrogramangreb) og detektionsgrænser.                                  |   1   | D/V  |
| 2.9.2 | Sørg for, at multimodale input behandles i isolerede sandkasser med definerede ressourcelimits (hukommelse, CPU, behandlingstid), som er specifikke for hver modalitetstype og dokumenteret i sikkerhedspolitikker.                             |   2   | D/V  |
| 2.9.3 | Bekræft, at krydsmodal angrebsdetection identificerer koordinerede angreb, der spænder over flere inputtyper (f.eks. steganografiske payloads i billeder kombineret med promptinjektion i tekst) ved hjælp af korrelationsregler og alarmering. |   2   | D/V  |
| 2.9.4 | Bekræft, at multi-modal valideringsfejl udløser detaljeret logføring, der inkluderer alle inputmodaliteter, valideringsresultater, trusselsscorer og korrelationsanalyse med strukturerede logformater til SIEM-integration.                    |   3   | D/V  |
| 2.9.5 | Kontroller, at modalitetsspecifikke indholdsclassificerere opdateres i henhold til dokumenterede tidsplaner (mindst kvartalsvist) med nye trusselmønstre, modstridende eksempler og ydeevnebenchmark, der holdes over basislinjetærskler.       |   3   | D/V  |

---

## Referencer

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

