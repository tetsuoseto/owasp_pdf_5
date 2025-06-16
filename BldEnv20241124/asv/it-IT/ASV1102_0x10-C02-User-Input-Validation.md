# Validazione dell'input utente C2

## Obiettivo di Controllo

Una validazione robusta dell'input dell'utente è una prima linea di difesa contro alcuni degli attacchi più dannosi ai sistemi di intelligenza artificiale. Gli attacchi di injection dei prompt possono sovrascrivere le istruzioni di sistema, divulgare dati sensibili o indirizzare il modello verso comportamenti non consentiti. A meno che non siano presenti filtri dedicati e gerarchie di istruzioni, la ricerca dimostra che le "multi-shot" jailbreak che sfruttano finestre di contesto molto lunghe saranno efficaci. Inoltre, attacchi sottili di perturbazione adversariale — come scambi di omoglyph o leetspeak — possono silenziosamente alterare le decisioni di un modello.

---

## C2.1 Difesa contro l'Iniezione di Prompt

L'iniezione di prompt è uno dei principali rischi per i sistemi di intelligenza artificiale. Le difese contro questa tattica utilizzano una combinazione di filtri statici basati su pattern, classificatori dinamici e l'applicazione gerarchica delle istruzioni.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Verificare che gli input degli utenti siano controllati rispetto a una libreria continuamente aggiornata di modelli noti di iniezione di prompt (parole chiave per il jailbreak, “ignora precedente”, catene di gioco di ruolo, attacchi indiretti HTML/URL). |   1   | D/V  |
| 2.1.2 | Verificare che il sistema applichi una gerarchia di istruzioni in cui i messaggi del sistema o dello sviluppatore sovrascrivano le istruzioni dell’utente, anche dopo l’espansione della finestra di contesto.                                                |   1   | D/V  |
| 2.1.3 | Verificare che i test di valutazione avversaria (ad esempio, prompt "many-shot" del Red Team) vengano eseguiti prima di ogni rilascio di modello o modello di prompt, con soglie di tasso di successo e blocchi automatici per regressioni.                   |   2   | D/V  |
| 2.1.4 | Verificare che i prompt provenienti da contenuti di terze parti (pagine web, PDF, email) vengano sanificati in un contesto di parsing isolato prima di essere concatenati al prompt principale.                                                               |   2   |  D   |
| 2.1.5 | Verificare che tutti gli aggiornamenti delle regole del filtro dei prompt, le versioni dei modelli classificatori e le modifiche alle liste di blocco siano controllati nelle versioni e verificabili.                                                        |   3   | D/V  |

---

## C2.2 Resistenza agli esempi avversari

I modelli di Elaborazione del Linguaggio Naturale (NLP) sono ancora vulnerabili a sottili perturbazioni a livello di caratteri o parole che gli esseri umani spesso non percepiscono, ma che i modelli tendono a classificare erroneamente.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Verificare che le operazioni di normalizzazione input di base (Unicode NFC, mappatura degli omoglifi, rimozione degli spazi bianchi) vengano eseguite prima della tokenizzazione.                                                |   1   |  D   |
| 2.2.2 | Verificare che il rilevamento di anomalie statistiche segnali input con distanza di modifica insolitamente elevata rispetto alle norme linguistiche, token ripetuti in eccesso o distanze di embedding anomale.                  |   2   | D/V  |
| 2.2.3 | Verificare che la pipeline di inferenza supporti varianti opzionali del modello irrobustite con addestramento avversario o strati di difesa (ad esempio, randomizzazione, distillazione difensiva) per endpoint ad alto rischio. |   2   |  D   |
| 2.2.4 | Verificare che gli input sospetti di essere avversari siano messi in quarantena, registrati con payload completi (dopo la redazione dei dati personali identificabili - PII).                                                    |   2   |  V   |
| 2.2.5 | Verificare che le metriche di robustezza (tasso di successo delle suite di attacchi conosciuti) siano monitorate nel tempo e che le regressioni attivino un blocco di rilascio.                                                  |   3   | D/V  |

---

## C2.3 Validazione di Schema, Tipo e Lunghezza

Gli attacchi AI che presentano input malformati o sovradimensionati possono causare errori di parsing, fuoriuscita di prompt tra campi e esaurimento delle risorse. L'applicazione rigorosa dello schema è inoltre un requisito fondamentale durante l'esecuzione di chiamate a strumenti deterministici.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Verificare che ogni endpoint di chiamata API o funzione definisca uno schema di input esplicito (JSON Schema, Protobuf o equivalente multimodale) e che gli input vengano convalidati prima dell’assemblaggio del prompt. |   1   |  D   |
| 2.3.2 | Verificare che gli input che superano il limite massimo di token o byte vengano rifiutati con un errore sicuro e non mai troncati silenziosamente.                                                                        |   1   | D/V  |
| 2.3.3 | Verificare che i controlli di tipo (ad esempio, intervalli numerici, valori enum, tipi MIME per immagini/audio) siano applicati lato server, non solo nel codice client.                                                  |   2   | D/V  |
| 2.3.4 | Verificare che i validatori semantici (ad esempio, JSON Schema) vengano eseguiti in tempo costante per prevenire attacchi DoS algoritmici.                                                                                |   2   |  D   |
| 2.3.5 | Verificare che i fallimenti di convalida siano registrati con estratti del payload oscurati e codici di errore inequivocabili per facilitare la triage della sicurezza.                                                   |   3   |  V   |

---

## C2.4 Controllo dei Contenuti e delle Politiche

Gli sviluppatori dovrebbero essere in grado di rilevare prompt sintatticamente validi che richiedono contenuti non consentiti (come istruzioni illecite, discorsi di odio e testi protetti da copyright) e impedirne la diffusione.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Verificare che un classificatore di contenuti (zero shot o fine-tuned) valuti ogni input per violenza, autolesionismo, odio, contenuti sessuali e richieste illegali, con soglie configurabili.   |   1   |  D   |
| 2.4.2 | Verificare che gli input che violano le politiche ricevano rifiuti standardizzati o completamenti sicuri in modo che non si propaghino alle chiamate LLM successive.                              |   1   | D/V  |
| 2.4.3 | Verificare che il modello di screening o l'insieme di regole venga riaddestrato/aggiornato almeno trimestralmente, incorporando i nuovi schemi di jailbreak o di elusione delle policy osservati. |   2   |  D   |
| 2.4.4 | Verificare che lo screening rispetti le politiche specifiche dell'utente (età, vincoli legali regionali) tramite regole basate su attributi risolte al momento della richiesta.                   |   2   |  D   |
| 2.4.5 | Verificare che i registri di screening includano i punteggi di confidenza del classificatore e i tag della categoria di politica per la correlazione SOC e la riproduzione futura del red-team.   |   3   |  V   |

---

## C2.5 Limitazione della velocità di input e prevenzione degli abusi

Gli sviluppatori dovrebbero prevenire abusi, esaurimento delle risorse e attacchi automatizzati contro i sistemi di intelligenza artificiale limitando i tassi di input e rilevando modelli di utilizzo anomali.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Verifica che i limiti di velocità per utente, per indirizzo IP e per chiave API siano applicati per tutti i punti di accesso in ingresso.       |   1   | D/V  |
| 2.5.2 | Verificare che i limiti di velocità a raffica e sostenuti siano configurati per prevenire attacchi DoS e di forza bruta.                        |   2   | D/V  |
| 2.5.3 | Verificare che i modelli di utilizzo anomali (ad esempio, richieste rapid-fire, inondazione di input) attivino blocchi automatici o escalation. |   2   | D/V  |
| 2.5.4 | Verificare che i registri di prevenzione degli abusi siano conservati e revisionati per individuare schemi di attacco emergenti.                |   3   |  V   |

---

## C2.6 Validazione di Input Multi-Modalità

I sistemi di intelligenza artificiale dovrebbero includere una convalida robusta per input non testuali (immagini, audio, file) per prevenire iniezioni, elusioni o abuso di risorse.

|   #   | Description                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.6.1 | Verificare che tutti gli input non testuali (immagini, audio, file) siano validati per tipo, dimensione e formato prima dell'elaborazione. |   1   |  D   |
| 2.6.2 | Verificare che i file vengano scansionati per malware e payload steganografici prima dell'ingestione.                                      |   2   | D/V  |
| 2.6.3 | Verificare che gli input di immagini/audio siano controllati per perturbazioni avversarie o schemi di attacco noti.                        |   2   | D/V  |
| 2.6.4 | Verificare che i fallimenti della validazione degli input multimodali siano registrati e attivino allarmi per l'indagine.                  |   3   |  V   |

---

## C2.7 Provenienza e attribuzione degli input

I sistemi di intelligenza artificiale dovrebbero supportare l'auditing, il monitoraggio degli abusi e la conformità attraverso il monitoraggio e l'etichettatura delle origini di tutti gli input degli utenti.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Verificare che tutti gli input degli utenti siano taggati con metadata (ID utente, sessione, fonte, timestamp, indirizzo IP) al momento dell'ingestione. |   1   | D/V  |
| 2.7.2 | Verificare che i metadati di provenienza siano mantenuti e verificabili per tutti gli input elaborati.                                                   |   2   | D/V  |
| 2.7.3 | Verificare che le fonti di input anomale o non affidabili siano segnalate e soggette a un controllo rafforzato o al blocco.                              |   2   | D/V  |

---

## C2.8 Rilevamento delle minacce adattivo in tempo reale

Gli sviluppatori dovrebbero utilizzare sistemi avanzati di rilevamento delle minacce per l'IA che si adattino a nuovi modelli di attacco e forniscano protezione in tempo reale tramite il matching di pattern compilati.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Verificare che i modelli di rilevamento delle minacce vengano compilati in motori regex ottimizzati per un filtraggio in tempo reale ad alte prestazioni con un impatto minimo sulla latenza.                                    |   1   | D/V  |
| 2.8.2 | Verificare che i sistemi di rilevamento delle minacce mantengano librerie di modelli separate per diverse categorie di minacce (iniezione di prompt, contenuti dannosi, dati sensibili, comandi di sistema).                     |   1   | D/V  |
| 2.8.3 | Verificare che il rilevamento delle minacce adattivo includa modelli di machine learning che aggiornano la sensibilità alle minacce in base alla frequenza degli attacchi e ai tassi di successo.                                |   2   | D/V  |
| 2.8.4 | Verificare che i feed di intelligence sulle minacce in tempo reale aggiornino automaticamente le librerie di pattern con nuove firme di attacco e IOC (Indicatori di Compromissione).                                            |   2   | D/V  |
| 2.8.5 | Verificare che i tassi di falsi positivi nella rilevazione delle minacce siano monitorati continuamente e che la specificità dei modelli sia automaticamente regolata per minimizzare l'interferenza con i casi d'uso legittimi. |   3   | D/V  |
| 2.8.6 | Verifica che l'analisi delle minacce contestuale consideri la fonte dell'input, i modelli di comportamento dell'utente e la cronologia della sessione per migliorare la precisione della rilevazione.                            |   3   | D/V  |
| 2.8.7 | Verificare che le metriche di prestazione del rilevamento delle minacce (tasso di rilevamento, latenza di elaborazione, utilizzo delle risorse) siano monitorate e ottimizzate in tempo reale.                                   |   3   | D/V  |

---

## C2.9 Pipeline di Validazione della Sicurezza Multi-Modale

Gli sviluppatori dovrebbero fornire una validazione di sicurezza per testo, immagini, audio e altre modalità di input AI con tipi specifici di rilevamento delle minacce e isolamento delle risorse.

|   #   | Description                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.9.1 | Verificare che ogni modalità di input abbia validatori di sicurezza dedicati con modelli di minaccia documentati (testo: iniezione di prompt, immagini: steganografia, audio: attacchi spettrogramma) e soglie di rilevamento.                                                                   |   1   | D/V  |
| 2.9.2 | Verificare che gli input multi-modali siano elaborati in sandbox isolate con limiti di risorse definiti (memoria, CPU, tempo di elaborazione) specifici per ogni tipo di modalità e documentati nelle politiche di sicurezza.                                                                    |   2   | D/V  |
| 2.9.3 | Verificare che il rilevamento degli attacchi cross-modali identifichi attacchi coordinati che coinvolgono molteplici tipologie di input (ad esempio, payload steganografici nelle immagini combinati con iniezione di prompt nel testo) tramite regole di correlazione e generazione di allarmi. |   2   | D/V  |
| 2.9.4 | Verificare che i fallimenti di validazione multimodale attivino una registrazione dettagliata che includa tutte le modalità di input, i risultati della validazione, i punteggi di minaccia e l'analisi di correlazione con formati di registro strutturati per l'integrazione SIEM.             |   3   | D/V  |
| 2.9.5 | Verificare che i classificatori di contenuti specifici per modalità siano aggiornati secondo i calendari documentati (almeno trimestralmente) con nuovi schemi di minacce, esempi avversari e benchmark di prestazioni mantenuti al di sopra delle soglie di base.                               |   3   | D/V  |

---

## Riferimenti

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

