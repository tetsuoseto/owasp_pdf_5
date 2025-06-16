# C2 Användarens inmatningsvalidering

## Kontrollmål

Robust validering av användarinmatning är ett första försvarslinje mot några av de mest skadliga attackerna mot AI-system. Promptinjektionsattacker kan åsidosätta systeminstruktioner, läcka känslig data eller styra modellen mot otillåtet beteende. Om inte dedikerade filter och instruktionshierarkier är på plats visar forskning att "multi-shot" jailbreaks som utnyttjar mycket långa kontextfönster kommer att vara effektiva. Även subtila adversariella störningsattacker—såsom homoglyfbyten eller leetspeak—kan tyst ändra en modells beslut.

---

## C2.1 Försvar mot promptinjektion

Promptinjektion är en av de största riskerna för AI-system. Försvar mot denna taktik använder en kombination av statiska mönsterfilter, dynamiska klassificerare och upprätthållande av instruktionshierarki.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Verifiera att användarinmatningar kontrolleras mot ett kontinuerligt uppdaterat bibliotek av kända mönster för promptinjektion (jailbreak-nyckelord, "ignorera tidigare", rollspelskedjor, indirekta HTML/URL-attacker). |   1   | D/V  |
| 2.1.2 | Verifiera att systemet upprätthåller en instruktionhierarki där system- eller utvecklarmeddelanden åsidosätter användarinstruktioner, även efter utökning av kontextfönstret.                                            |   1   | D/V  |
| 2.1.3 | Verifiera att adversarial utvärderingstester (t.ex. Red Team "many-shot" prompts) genomförs innan varje modell- eller prompt-mallsläpp, med framgångströsklar och automatiska blockeringar för regressioner.             |   2   | D/V  |
| 2.1.4 | Verifiera att promptar som kommer från tredjepartsinnehåll (webbsidor, PDF-filer, e-postmeddelanden) saneras i en isolerad parsningkontext innan de sammanfogas med huvudprompten.                                       |   2   |  D   |
| 2.1.5 | Verifiera att alla uppdateringar av prompt-filterregler, versioner av klassificeringsmodeller och ändringar i blocklistor är versionskontrollerade och granskbara.                                                       |   3   | D/V  |

---

## C2.2 Motståndskraft mot adversariella exempel

Modeller för naturlig språkbehandling (NLP) är fortfarande sårbara för subtila störningar på tecken- eller ordnivå som människor ofta missar men som modeller tenderar att felklassificera.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.2.1 | Verifiera att grundläggande steg för indata-normalisering (Unicode NFC, homoglyf-kartläggning, borttagning av blanksteg) körs innan tokenisering.                                    |   1   |  D   |
| 2.2.2 | Verifiera att statistisk avvikelsedetektering markerar indata med ovanligt hög redigeringsavstånd till språknormer, överdrivet upprepade token eller onormala inbäddningsavstånd.    |   2   | D/V  |
| 2.2.3 | Verifiera att inferenspipelin stöder valfria adversarial-tränade, förhärdade modellvarianter eller försvarslager (t.ex. randomisering, defensiv destillering) för högriskändpunkter. |   2   |  D   |
| 2.2.4 | Verifiera att misstänkta adversariella indata isoleras, loggas med fullständiga nyttolaster (efter borttagning av personligt identifierbar information).                             |   2   |  V   |
| 2.2.5 | Verifiera att robusthetsmått (framgångsfrekvens för kända attacksviter) spåras över tid och att regressioner utlöser ett blockerande av release.                                     |   3   | D/V  |

---

## C2.3 Schema-, Typ- och Längdvalidering

AI-attacker som involverar felaktiga eller överdimensionerade indata kan orsaka parsningfel, överflöd av promptar över fält och resursutmattning. Strikt schema-hantering är också en förutsättning vid deterministiska verktygsanrop.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.3.1 | Verifiera att varje API- eller funktionsanropsendpoint definierar ett explicit inschema (JSON Schema, Protobuf eller multimodalt motsvarande) och att indata valideras innan promptens sammansättning. |   1   |  D   |
| 2.3.2 | Verifiera att indata som överskrider maximala gränser för token eller byte avvisas med ett säkert felmeddelande och aldrig tyst förkortas.                                                             |   1   | D/V  |
| 2.3.3 | Verifiera att typkontroller (t.ex. numeriska intervall, enum-värden, MIME-typer för bilder/ljud) genomförs på serversidan, inte bara i klientkoden.                                                    |   2   | D/V  |
| 2.3.4 | Verifiera att semantiska validerare (t.ex. JSON-schema) körs i konstant tid för att förhindra algoritmisk DoS.                                                                                         |   2   |  D   |
| 2.3.5 | Verifiera att valideringsfel loggas med raderade nyttolastutdrag och entydiga felkoder för att underlätta säkerhetstriage.                                                                             |   3   |  V   |

---

## C2.4 Innehålls- och policygranskning

Utvecklare bör kunna upptäcka syntaktiskt giltiga promptar som begär otillåtet innehåll (såsom olagliga instruktioner, hatretorik och upphovsrättsskyddad text) och därefter förhindra att dessa sprids.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Verifiera att en innehållsklassificerare (nollskott eller finjusterad) bedömer varje inmatning för våld, självskada, hat, sexuellt innehåll och olagliga förfrågningar, med konfigurerbara tröskelvärden. |   1   |  D   |
| 2.4.2 | Verifiera att indata som bryter mot policyer får standardiserade avvisningar eller säkra avslut, så att de inte förs vidare till efterföljande LLM-anrop.                                                 |   1   | D/V  |
| 2.4.3 | Verifiera att screeningsmodellen eller regelsatsen tränas om/uppdateras minst varje kvartal, och att nyligen observerade jailbreak- eller policysundandragelsesmönster inkluderas.                        |   2   |  D   |
| 2.4.4 | Verifiera att screening respekterar användarspecifika policyer (ålder, regionala rättsliga begränsningar) via attributbaserade regler som löses vid förfrågan.                                            |   2   |  D   |
| 2.4.5 | Verifiera att screeningloggar inkluderar klassificerarsäkerhetspoäng och policykategori-taggar för SOC-korrelation och framtida red-team-uppspelning.                                                     |   3   |  V   |

---

## C2.5 Inmatningsfrekvensbegränsning och förebyggande av missbruk

Utvecklare bör förhindra missbruk, resursutarmning och automatiserade attacker mot AI-system genom att begränsa inmatningshastigheter och upptäcka avvikande användningsmönster.

|   #   | Description                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.5.1 | Verifiera att begränsningar för hastighet per användare, per IP och per API-nyckel upprätthålls för alla ingångsändpunkter.                      |   1   | D/V  |
| 2.5.2 | Verifiera att takterna för burst och uthållighet är justerade för att förhindra DoS- och brute force-attacker.                                   |   2   | D/V  |
| 2.5.3 | Verifiera att onormala användningsmönster (t.ex. snabba förfrågningar, inputöverbelastning) triggar automatiska blockeringar eller eskaleringar. |   2   | D/V  |
| 2.5.4 | Verifiera att loggar för missbruksprevention sparas och granskas för att upptäcka nya attacker.                                                  |   3   |  V   |

---

## C2.6 Multimodal inmatningsvalidering

AI-system bör inkludera robust validering för icke-textuella indata (bilder, ljud, filer) för att förhindra injektion, undvikande eller resursmissbruk.

|   #   | Description                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Verifiera att alla icke-textbaserade indata (bilder, ljud, filer) valideras för typ, storlek och format innan de bearbetas. |   1   |  D   |
| 2.6.2 | Verifiera att filer skannas efter skadlig programvara och steganografiska belastningar innan de importeras.                 |   2   | D/V  |
| 2.6.3 | Verifiera att bild-/ljudingångar kontrolleras för adversariella perturbationer eller kända attackmönster.                   |   2   | D/V  |
| 2.6.4 | Verifiera att fel vid multimodal inmatningsvalidering loggas och utlöser varningar för undersökning.                        |   3   |  V   |

---

## C2.7 Inmatningsursprung och Attribution

AI-system bör stödja revision, missbruksspårning och efterlevnad genom att övervaka och märka ursprunget för alla användarinmatningar.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.7.1 | Verifiera att alla användarinmatningar är taggade med metadata (användar-ID, session, källa, tidsstämpel, IP-adress) vid mottagning. |   1   | D/V  |
| 2.7.2 | Verifiera att proveniensmetadata bevaras och är granskningsbar för alla bearbetade indata.                                           |   2   | D/V  |
| 2.7.3 | Verifiera att anomalösa eller icke betrodda inmatningskällor markeras och utsätts för ökad granskning eller blockering.              |   2   | D/V  |

---

## C2.8 Realtidsanpassad hotdetektion

Utvecklare bör använda avancerade hotdetekteringssystem för AI som anpassar sig till nya attackmönster och erbjuder realtidsskydd med kompilerad mönstermatchning.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.8.1 | Verifiera att hotdetekteringsmönster är kompilerade till optimerade regex-motorer för högpresterande realtidsfiltrering med minimal latenspåverkan.                                        |   1   | D/V  |
| 2.8.2 | Verifiera att hotupptäcktsystem upprätthåller separata mönsterbibliotek för olika hotkategorier (promptinjektion, skadligt innehåll, känslig data, systemkommandon).                       |   1   | D/V  |
| 2.8.3 | Verifiera att adaptiv hotdetektion innefattar maskininlärningsmodeller som uppdaterar hotkänsligheten baserat på angreppsfrekvens och framgångsfrekvenser.                                 |   2   | D/V  |
| 2.8.4 | Verifiera att realtids hotintelligensflöden automatiskt uppdaterar mönsterbibliotek med nya angreppssignaturer och IOCs (indikatorer på intrång).                                          |   2   | D/V  |
| 2.8.5 | Verifiera att falska positiva nivåer vid hotdetektering kontinuerligt övervakas och att mönsterspecificiteten automatiskt justeras för att minimera störningar i legitima användningsfall. |   3   | D/V  |
| 2.8.6 | Verifiera att kontextuell hotanalys tar hänsyn till inmatningskälla, användarbeteendemönster och sessionshistorik för att förbättra detektionsnoggrannheten.                               |   3   | D/V  |
| 2.8.7 | Verifiera att prestandamått för hotdetektion (detekteringsgrad, bearbetningslatens, resursanvändning) övervakas och optimeras i realtid.                                                   |   3   | D/V  |

---

## C2.9 Flermodal säkerhetsvalideringspipeline

Utvecklare bör tillhandahålla säkerhetsvalidering för text-, bild-, ljud- och andra AI-ingångsmodaliteter med specifika typer av hotdetektion och resursisolering.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Verifiera att varje inmatningsmodalitet har dedikerade säkerhetsvalidatorer med dokumenterade hotmönster (text: promptinjektion, bilder: steganografi, ljud: spektrogramattacker) och detektionsgränser.                                                                  |   1   | D/V  |
| 2.9.2 | Verifiera att multimodala indata bearbetas i isolerade sandlådor med definierade resursgränser (minne, CPU, bearbetningstid) specifika för varje modalitetstyp och dokumenterade i säkerhetspolicys.                                                                      |   2   | D/V  |
| 2.9.3 | Verifiera att korsmodal angreppsdetektion identifierar koordinerade angrepp som sträcker sig över flera typer av indata (t.ex. steganografiska belastningar i bilder kombinerade med promptinjektion i text) med hjälp av korrelationsregler och generering av varningar. |   2   | D/V  |
| 2.9.4 | Verifiera att valideringsfel för multimodalitet utlöser detaljerad loggning inklusive alla inmatningsmodaliteter, valideringsresultat, hotpoäng och korrelationsanalys med strukturerade loggformat för SIEM-integration.                                                 |   3   | D/V  |
| 2.9.5 | Verifiera att modalitetsspecifika innehållsklassificerare uppdateras enligt dokumenterade scheman (minst kvartalsvis) med nya hotmönster, adversariella exempel och att prestandamåtten bibehålls över baslinjenivåer.                                                    |   3   | D/V  |

---

## Referenser

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

