# Comportamento del Modello C7, Controllo dell'Uscita e Garanzia di Sicurezza

## Obiettivo di Controllo

I risultati del modello devono essere strutturati, affidabili, sicuri, spiegabili e costantemente monitorati in produzione. Ciò riduce le allucinazioni, le fughe di dati privati, i contenuti dannosi e le azioni incontrollate, aumentando al contempo la fiducia degli utenti e la conformità normativa.

---

## C7.1 Applicazione del formato di output

Schemi rigidi, decodifica vincolata e convalida a valle impediscono che contenuti malformati o dannosi si propaghino.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Verificare che gli schemi di risposta (ad esempio, JSON Schema) siano forniti nel prompt di sistema e che ogni output venga automaticamente convalidato; gli output non conformi attivano una riparazione o un rifiuto. |   1   | D/V  |
| 7.1.2 | Verificare che la decodifica vincolata (token di stop, espressioni regolari, max-token) sia abilitata per prevenire overflow o canali laterali di iniezione di prompt.                                                  |   1   | D/V  |
| 7.1.3 | Verificare che i componenti a valle considerino le uscite come non attendibili e le convalidino rispetto a schemi o de-serializzatori sicuri contro le iniezioni.                                                       |   2   | D/V  |
| 7.1.4 | Verificare che gli eventi di output improprio vengano registrati, limitati nel tasso e segnalati nel sistema di monitoraggio.                                                                                           |   3   |  V   |

---

## C7.2 Rilevamento e Mitigazione delle Allucinazioni

La stima dell'incertezza e le strategie di fallback limitano le risposte fabbricate.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Verificare che le log-probabilità a livello di token, la coerenza autonoma dell'ensemble o i rilevatori di allucinazioni affinati assegnino un punteggio di confidenza a ciascuna risposta.                   |   1   | D/V  |
| 7.2.2 | Verificare che le risposte al di sotto di una soglia di confidenza configurabile attivino flussi di lavoro di fallback (ad esempio, generazione aumentata da recupero, modello secondario o revisione umana). |   1   | D/V  |
| 7.2.3 | Verificare che gli incidenti di allucinazione siano contrassegnati con metadati di causa principale e inseriti nelle pipeline di analisi post-mortem e di affinamento.                                        |   2   | D/V  |
| 7.2.4 | Verificare che le soglie e i rilevatori siano ricalibrati dopo aggiornamenti importanti del modello o della base di conoscenza.                                                                               |   3   | D/V  |
| 7.2.5 | Verificare che le visualizzazioni della dashboard monitorino i tassi di allucinazione.                                                                                                                        |   3   |  V   |

---

## C7.3 Filtraggio della Sicurezza e della Privacy dell'Uscita

I filtri di policy e la copertura red-team proteggono gli utenti e i dati riservati.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Verificare che i classificatori pre e post-generazione blocchino contenuti di odio, molestie, autolesionismo, estremismo e contenuti sessualmente espliciti in conformità alla politica. |   1   | D/V  |
| 7.3.2 | Verificare che il rilevamento di PII/PCI e la redazione automatica vengano eseguiti su ogni risposta; le violazioni generano un incidente di privacy.                                    |   1   | D/V  |
| 7.3.3 | Verificare che i tag di riservatezza (ad esempio, segreti commerciali) si propaghino attraverso le modalità per prevenire la fuoriuscita in testi, immagini o codice.                    |   2   |  D   |
| 7.3.4 | Verificare che i tentativi di elusione del filtro o le classificazioni ad alto rischio richiedano un'approvazione secondaria o una riautenticazione dell'utente.                         |   3   | D/V  |
| 7.3.5 | Verificare che le soglie di filtraggio riflettano le giurisdizioni legali e il contesto di età/ruolo dell'utente.                                                                        |   3   | D/V  |

---

## C7.4 Limitazione dell'Output e delle Azioni

I limiti di velocità e i cancelli di approvazione prevengono abusi e autonomia eccessiva.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Verificare che le quote per utente e per chiave API limitino le richieste, i token e i costi con back-off esponenziale sugli errori 429.                                                       |   1   |  D   |
| 7.4.2 | Verificare che le azioni privilegiate (scrittura di file, esecuzione di codice, chiamate di rete) richiedano l'approvazione basata su policy o l'intervento umano.                             |   1   | D/V  |
| 7.4.3 | Verificare che i controlli di coerenza cross-modale garantiscano che immagini, codice e testo generati per la stessa richiesta non possano essere utilizzati per introdurre contenuti dannosi. |   2   | D/V  |
| 7.4.4 | Verificare che la profondità di delega dell’agente, i limiti di ricorsione e le liste di strumenti consentiti siano configurati esplicitamente.                                                |   2   |  D   |
| 7.4.5 | Verificare che la violazione dei limiti generi eventi di sicurezza strutturati per l'ingestione da parte del SIEM.                                                                             |   3   |  V   |

---

## C7.5 Spiegabilità dell'Uscita

I segnali trasparenti migliorano la fiducia dell'utente e il debug interno.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Verificare che i punteggi di fiducia rivolti all'utente o brevi riassunti delle motivazioni siano esposti quando la valutazione del rischio lo ritiene appropriato. |   2   | D/V  |
| 7.5.2 | Verificare che le spiegazioni generate evitino di rivelare prompt di sistema sensibili o dati proprietari.                                                          |   2   | D/V  |
| 7.5.3 | Verificare che il sistema acquisisca le probabilità logaritmiche a livello di token o le mappe di attenzione e le memorizzi per un'ispezione autorizzata.           |   3   |  D   |
| 7.5.4 | Verificare che gli artefatti di spiegabilità siano soggetti a controllo delle versioni insieme alle release dei modelli per garantire la tracciabilità.             |   3   |  V   |

---

## C7.6 Integrazione del Monitoraggio

L'osservabilità in tempo reale chiude il ciclo tra sviluppo e produzione.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Verificare che le metriche (violazioni dello schema, tasso di allucinazioni, tossicità, perdite di PII, latenza, costo) vengano trasmesse a una piattaforma centrale di monitoraggio. |   1   |  D   |
| 7.6.2 | Verificare che siano definiti soglie di allerta per ogni parametro di sicurezza, con percorsi di escalation disponibili per il personale reperibile.                                  |   1   |  V   |
| 7.6.3 | Verifica che le dashboard mettano in correlazione le anomalie di output con il modello/versione, il flag della funzione e le modifiche ai dati upstream.                              |   2   |  V   |
| 7.6.4 | Verificare che i dati di monitoraggio vengano reinseriti nel processo di retraining, fine-tuning o aggiornamento delle regole all'interno di un flusso di lavoro MLOps documentato.   |   2   | D/V  |
| 7.6.5 | Verificare che le pipeline di monitoraggio siano sottoposte a test di penetrazione e protette da controlli di accesso per evitare la perdita di log sensibili.                        |   3   |  V   |

---

## 7.7 Salvaguardie per i Media Generativi

Garantire che i sistemi di IA non generino contenuti multimediali illegali, dannosi o non autorizzati mediante l'applicazione di vincoli di policy, la validazione dell'output e la tracciabilità.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Verificare che i prompt di sistema e le istruzioni per l'utente vietino esplicitamente la generazione di contenuti deepfake illegali, dannosi o non consensuali (ad esempio, immagini, video, audio).                                                   |   1   | D/V  |
| 7.7.2 | Verificare che i prompt siano filtrati per tentativi di generare imitazioni, deepfake sessualmente espliciti o media che rappresentano individui reali senza consenso.                                                                                  |   2   | D/V  |
| 7.7.3 | Verificare che il sistema utilizzi hashing percettivo, rilevamento watermark o fingerprinting per prevenire la riproduzione non autorizzata di contenuti protetti da copyright.                                                                         |   2   |  V   |
| 7.7.4 | Verificare che tutti i media generati siano firmati crittograficamente, con filigrana o incorporati con metadati di provenienza resistenti alla manomissione per la tracciabilità a valle.                                                              |   3   | D/V  |
| 7.7.5 | Verificare che i tentativi di elusione (ad esempio, offuscamento del prompt, gergo, formulazione avversaria) vengano rilevati, registrati e soggetti a limitazione di frequenza; gli abusi ripetuti devono essere segnalati ai sistemi di monitoraggio. |   3   |  V   |

## Riferimenti

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

