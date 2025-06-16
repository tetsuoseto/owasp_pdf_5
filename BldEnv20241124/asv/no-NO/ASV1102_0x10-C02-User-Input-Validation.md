# C2 Brukervalidert inndata

## Kontrollmål

Robust validering av brukerinnspill er en første forsvarslinje mot noen av de mest skadelige angrepene på AI-systemer. Prompt-injeksjonsangrep kan overstyre systeminstruksjoner, lekke sensitiv data eller styre modellen mot uønsket atferd. Med mindre dedikerte filtre og instruksjonshierarkier er på plass, viser forskning at "multi-shot" jailbreaks som utnytter svært lange kontekstvinduer vil være effektive. Også subtile adversarielle perturbasjonsangrep—slik som homoglyfbytter eller leetspeak—kan stille endre modellens beslutninger.

---

## C2.1 Forsvar mot promptinjeksjon

Promptinjeksjon er en av de største risikoene for AI-systemer. Forsvar mot denne taktikken benytter en kombinasjon av statiske mønsterfiltre, dynamiske klassifiserere og håndhevelse av instruksjonshierarki.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Sørg for at brukerinnspill blir kontrollert mot et kontinuerlig oppdatert bibliotek av kjente mønstre for promptinjeksering (jailbreak-stikkord, "ignorer tidligere", rollelek-kjeder, indirekte HTML/URL-angrep). |   1   | D/V  |
| 2.1.2 | Bekreft at systemet håndhever en instruksjonshierarki der system- eller utviklermeldinger overstyrer brukerinstruksjoner, selv etter utvidelse av kontekstvinduet.                                                 |   1   | D/V  |
| 2.1.3 | Bekreft at adversarial evalueringstester (f.eks. Red Team "many-shot" prompt) kjøres før hver modell- eller promptmalutgivelse, med suksessrategrenser og automatiske sperrer for tilbakeslag.                     |   2   | D/V  |
| 2.1.4 | Bekreft at spørsmål som stammer fra tredjepartsinnhold (nettsteder, PDF-filer, e-poster) blir renset i en isolert parsingsammenheng før de settes sammen med hovedspørsmålet.                                      |   2   |  D   |
| 2.1.5 | Sørg for at alle oppdateringer av prompt-filter-regler, versjoner av klassifiseringsmodeller og endringer i blokklisten er versjonskontrollerte og reviderbare.                                                    |   3   | D/V  |

---

## C2.2 Motstand mot adversarial-eksempler

Modeller for naturlig språkbehandling (NLP) er fortsatt sårbare for subtile tegn- eller ordnivåforstyrrelser som mennesker ofte overser, men som modellene har en tendens til å feilkategorisere.

|   #   | Description                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Bekreft at grunnleggende inndata normaliseringssteg (Unicode NFC, homoglyph-mapping, trimming av mellomrom) kjøres før tokenisering.                                             |   1   |  D   |
| 2.2.2 | Verifiser at statistisk anomalideteksjon merker inndata med uvanlig høy redigeringsavstand til språknormer, overdreven gjentakelse av token, eller unormale innebygde avstander. |   2   | D/V  |
| 2.2.3 | Bekreft at inferensrøret støtter valgfrie modeller hardnet med adversarial trening eller forsvarslag (f.eks. randomisering, defensiv destillasjon) for høyrisiko-endepunkter.    |   2   |  D   |
| 2.2.4 | Bekreft at mistenkte fiendtlige inndata blir satt i karantene og loggført med fullstendige nyttelaster (etter fjerning av personopplysninger).                                   |   2   |  V   |
| 2.2.5 | Verifiser at robusthetsmålinger (suksessrate for kjente angrepssuiter) spores over tid, og at regresjoner utløser en utgivelsesblokkering.                                       |   3   | D/V  |

---

## C2.3 Skjema-, type- og lengdevalidering

AI-angrep med feilformede eller overdimensjonerte inndata kan forårsake parsningsfeil, lekkasje mellom felt i prompten og ressursutmattelse. Streng skjemahåndhevelse er også en forutsetning ved utførelse av deterministiske verktøyanrop.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Verifiser at hvert API- eller funksjonskall-endepunkt definerer et eksplisitt inndataskjema (JSON Schema, Protobuf eller multimodalt ekvivalent) og at inndata valideres før promptens sammensetning. |   1   |  D   |
| 2.3.2 | Bekreft at inndata som overskrider maksimalt antall tokens eller byte-grenser blir avvist med en sikker feilmelding og aldri blir stille avkortet.                                                    |   1   | D/V  |
| 2.3.3 | Bekreft at typekontroller (for eksempel numeriske intervaller, enum-verdier, MIME-typer for bilder/lyd) håndheves på serversiden, ikke bare i klientkoden.                                            |   2   | D/V  |
| 2.3.4 | Verifiser at semantiske validatorer (f.eks. JSON Schema) kjører i konstant tid for å forhindre algoritmisk DoS.                                                                                       |   2   |  D   |
| 2.3.5 | Bekreft at valideringsfeil logges med redigerte nyttelastutdrag og entydige feilkoder for å støtte sikkerhetstriage.                                                                                  |   3   |  V   |

---

## C2.4 Innhold- og policykontroll

Utviklere bør kunne oppdage syntaktisk gyldige forespørsler som etterspør forbudt innhold (slik som ulovlige instruksjoner, hatprat og opphavsrettsbeskyttet tekst), og deretter forhindre at disse sprer seg.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Verifiser at en innholdsklassifiserer (zero shot eller finjustert) vurderer hvert innspill for vold, selvskading, hat, seksuelt innhold og ulovlige forespørsler, med konfigurerbare terskler. |   1   |  D   |
| 2.4.2 | Bekreft at inndata som bryter med retningslinjene vil motta standardiserte avslag eller sikre fullføringer slik at de ikke videreføres til etterfølgende LLM-kall.                             |   1   | D/V  |
| 2.4.3 | Bekreft at screeningsmodellen eller regelsettet blir trent på nytt/oppdatert minst kvartalsvis, og inkluderer nylig observerte jailbreak- eller policyomgåelsesmønstre.                        |   2   |  D   |
| 2.4.4 | Verifiser at screening respekterer brukerspesifikke regler (alder, regionale juridiske begrensninger) via attributtbaserte regler løst ved forespørselstidspunkt.                              |   2   |  D   |
| 2.4.5 | Bekreft at screeningslogger inkluderer klassifiseringskonfidenspoeng og policy-kategorietagger for SOC-korrelasjon og fremtidig rødlagspillavspilling.                                         |   3   |  V   |

---

## C2.5 Begrensning av inngangshastighet og forebygging av misbruk

Utviklere bør forhindre misbruk, ressursutarming og automatiserte angrep mot AI-systemer ved å begrense inntaksrater og oppdage unormale bruks mønstre.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Bekreft at ratebegrensninger per bruker, per IP og per API-nøkkel håndheves for alle inndatapunkter.                                  |   1   | D/V  |
| 2.5.2 | Verifiser at burst- og vedvarende grenseverdier er justert for å forhindre DoS- og brute force-angrep.                                |   2   | D/V  |
| 2.5.3 | Verifiser at unormale bruks mønstre (f.eks. raske forespørsler, input-overbelastning) utløser automatiske blokker eller eskaleringer. |   2   | D/V  |
| 2.5.4 | Bekreft at logger for misbrukforebygging blir beholdt og gjennomgått for nye angrepsmønstre.                                          |   3   |  V   |

---

## C2.6 Multi-modale inndata-validering

AI-systemer bør inkludere robust validering for ikke-tekstlige input (bilder, lyd, filer) for å forhindre injeksjon, unnvikelse eller ressursmisbruk.

|   #   | Description                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Sørg for at alle ikke-tekstlige inndata (bilder, lyd, filer) valideres for type, størrelse og format før behandling. |   1   |  D   |
| 2.6.2 | Bekreft at filer blir skannet for skadelig programvare og steganografiske nyttelaster før innlasting.                |   2   | D/V  |
| 2.6.3 | Bekreft at bilde-/lyd-inndata kontrolleres for fiendtlige forstyrrelser eller kjente angrepsmønstre.                 |   2   | D/V  |
| 2.6.4 | Bekreft at bekreftelsesfeil for multimodale inndata blir logget og utløser varsler for undersøkelse.                 |   3   |  V   |

---

## C2.7 Inngangsopprinnelse og attribusjon

KI-systemer bør støtte revisjon, misbrukssporing og etterlevelse ved å overvåke og merke opprinnelsen til alle brukerinput.

|   #   | Description                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Bekreft at alle brukerinnspill er merket med metadata (bruker-ID, økt, kilde, tidsstempel, IP-adresse) ved inntak.     |   1   | D/V  |
| 2.7.2 | Bekreft at opprinnelsesmetadata beholdes og kan revideres for alle behandlede innganger.                               |   2   | D/V  |
| 2.7.3 | Bekreft at avvikende eller ikke-pålitelig inngangskilder blir flagget og underlagt skjerpet kontroll eller blokkering. |   2   | D/V  |

---

## C2.8 Sanntids adaptiv trusseldeteksjon

Utviklere bør bruke avanserte trusseldeteksjonssystemer for AI som tilpasser seg nye angrepsmønstre og gir sanntidsbeskyttelse med kompilert mønstergjenkjenning.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Sørg for at trusseldeteksjonsmønstre er kompilerte inn i optimaliserte regex-motorer for høy ytelse i sanntidsfiltrering med minimal forsinkelsespåvirkning.                            |   1   | D/V  |
| 2.8.2 | Bekreft at trusseldeteksjonssystemer opprettholder separate mønsterbiblioteker for forskjellige trusselkategorier (promptinjeksjon, skadelig innhold, sensitiv data, systemkommandoer). |   1   | D/V  |
| 2.8.3 | Bekreft at adaptiv trusseldeteksjon inkluderer maskinlæringsmodeller som oppdaterer trusselens følsomhet basert på angrepsfrekvens og suksessrater.                                     |   2   | D/V  |
| 2.8.4 | Bekreft at trusselintelligensstrømmer i sanntid automatisk oppdaterer mønsterbiblioteker med nye angrepssignaturer og IOCs (indikatorer på kompromittering).                            |   2   | D/V  |
| 2.8.5 | Sørg for at falske positive rater i trusseldeteksjon overvåkes kontinuerlig, og at mønsterspesifisitet automatisk justeres for å minimere forstyrrelser i legitime bruksområder.        |   3   | D/V  |
| 2.8.6 | Bekreft at kontekstuell trusselanalyse tar hensyn til inndatakilde, brukeratferdsmønstre og sesjonshistorikk for å forbedre deteksjonsnøyaktigheten.                                    |   3   | D/V  |
| 2.8.7 | Sørg for at ytelsesmålinger for trusseldeteksjon (deteksjonsrate, behandlingsforsinkelse, ressursutnyttelse) overvåkes og optimaliseres i sanntid.                                      |   3   | D/V  |

---

## C2.9 Flermodalt sikkerhetsvalideringspipeline

Utviklere bør sørge for sikkerhetsvalidering for tekst, bilde, lyd og andre AI-inndatamodaliteter med spesifikke typer trusseldeteksjon og ressursisolasjon.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Bekreft at hver inputmodalitet har dedikerte sikkerhetsvalidatorer med dokumenterte trusselmodeller (tekst: promptinjeksjon, bilder: steganografi, lyd: spektrogramangrep) og deteksjonsterskler.                                                    |   1   | D/V  |
| 2.9.2 | Bekreft at multimodale innganger behandles i isolerte sandkasser med definerte ressursgrenser (minne, CPU, behandlingstid) spesifikke for hver modalitetstype og dokumentert i sikkerhetspolicyer.                                                   |   2   | D/V  |
| 2.9.3 | Verifiser at kryssmodale angrepsdeteksjon identifiserer koordinerte angrep som spenner over flere inputtyper (f.eks. steganografiske payloads i bilder kombinert med prompt-injeksjon i tekst) ved hjelp av korrelasjonsregler og varselsgenerering. |   2   | D/V  |
| 2.9.4 | Bekreft at feil ved multimodal validering utløser detaljert logging som inkluderer alle inngangsmodaliteter, valideringsresultater, trusselpoeng og korrelasjonsanalyse med strukturerte loggformater for SIEM-integrasjon.                          |   3   | D/V  |
| 2.9.5 | Bekreft at modalitetsspesifikke innholdsklassifiserere oppdateres i henhold til dokumenterte tidsplaner (minst kvartalsvis) med nye trusselmønstre, adversariale eksempler og ytelsesstandarder som opprettholdes over grunnlinjenivåer.             |   3   | D/V  |

---

## Referanser

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

