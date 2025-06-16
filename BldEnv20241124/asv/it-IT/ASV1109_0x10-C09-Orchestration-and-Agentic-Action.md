# 9 Orchestrazione Autonoma e Sicurezza dell’Azione Agentica

## Obiettivo di Controllo

Assicurarsi che i sistemi di intelligenza artificiale autonomi o multi-agente possano eseguire solo azioni esplicitamente intenzionate, autenticate, verificabili e all'interno di limiti prestabiliti di costo e rischio. Ciò protegge contro minacce quali Compromissione del Sistema Autonomo, Uso Improprio degli Strumenti, Rilevamento del Ciclo degli Agenti, Dirottamento delle Comunicazioni, Falsificazione dell'Identità, Manipolazione dello Sciame e Manipolazione dell'Intento.

---

## 9.1 Budget di Pianificazione dei Compiti e Ricorsione dell’Agente

Limita i piani ricorsivi e imposta checkpoint umani obbligatori per azioni privilegiate.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Verificare che la profondità massima della ricorsione, la larghezza, il tempo effettivo, i token e il costo monetario per esecuzione dell'agente siano configurati centralmente e sottoposti a controllo di versione. |   1   | D/V  |
| 9.1.2 | Verificare che le azioni privilegiate o irreversibili (ad esempio, commit di codice, trasferimenti finanziari) richiedano l'approvazione esplicita umana tramite un canale auditabile prima dell'esecuzione.          |   1   | D/V  |
| 9.1.3 | Verificare che i monitor di risorse in tempo reale attivino l'interruzione del circuito di sicurezza quando viene superata qualsiasi soglia di budget, fermando ulteriori espansioni del compito.                     |   2   |  D   |
| 9.1.4 | Verificare che gli eventi del circuito di interruzione siano registrati con l'ID dell'agente, la condizione di attivazione e lo stato del piano catturato per la revisione forense.                                   |   2   | D/V  |
| 9.1.5 | Verificare che i test di sicurezza coprano gli scenari di esaurimento del budget e di piano fuori controllo, confermando un arresto sicuro senza perdita di dati.                                                     |   3   |  V   |
| 9.1.6 | Verificare che le politiche di budget siano espresse come policy-as-code e applicate nel CI/CD per bloccare la deriva della configurazione.                                                                           |   3   |  D   |

---

## 9.2 Isolamento dei Plugin degli Strumenti

Isolare le interazioni degli strumenti per prevenire accessi non autorizzati al sistema o l'esecuzione di codice.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Verificare che ogni strumento/plugin venga eseguito all'interno di un sistema operativo, container o sandbox a livello WASM con politiche di minimo privilegio per file system, rete e chiamate di sistema. |   1   | D/V  |
| 9.2.2 | Verificare che le quote delle risorse del sandbox (CPU, memoria, disco, uscita di rete) e i timeout di esecuzione siano applicati e registrati.                                                             |   1   | D/V  |
| 9.2.3 | Verificare che i binari o i descrittori degli strumenti siano firmati digitalmente; le firme devono essere convalidate prima del caricamento.                                                               |   2   | D/V  |
| 9.2.4 | Verificare che la telemetria della sandbox fluisca verso un SIEM; le anomalie (ad esempio, tentativi di connessioni in uscita) generano allerte.                                                            |   2   |  V   |
| 9.2.5 | Verificare che i plugin ad alto rischio siano sottoposti a revisione della sicurezza e test di penetrazione prima della distribuzione in produzione.                                                        |   3   |  V   |
| 9.2.6 | Verificare che i tentativi di fuga dalla sandbox siano bloccati automaticamente e che il plugin non conforme venga messo in quarantena in attesa di indagine.                                               |   3   | D/V  |

---

## 9.3 Ciclo Autonomo e Limitazione dei Costi

Rilevare e fermare la ricorsione incontrollata tra agenti e l’esplosione dei costi.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.3.1 | Verificare che le chiamate inter-agente includano un limite di salto o TTL che il runtime decrementa e applica.                                              |   1   | D/V  |
| 9.3.2 | Verificare che gli agenti mantengano un ID univoco del grafo di invocazione per individuare auto-invocazioni o schemi ciclici.                               |   2   |  D   |
| 9.3.3 | Verificare che i contatori cumulativi delle unità di calcolo e della spesa siano tracciati per catena di richiesta; superare il limite interrompe la catena. |   2   | D/V  |
| 9.3.4 | Verificare che l'analisi formale o il model checking dimostrino l'assenza di ricorsione illimitata nei protocolli degli agenti.                              |   3   |  V   |
| 9.3.5 | Verificare che gli eventi di interruzione del ciclo generino avvisi e alimentino metriche di miglioramento continuo.                                         |   3   |  D   |

---

## 9.4 Protezione contro l'uso improprio a livello di protocollo

Canali di comunicazione sicuri tra agenti e sistemi esterni per prevenire dirottamenti o manipolazioni.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Verificare che tutti i messaggi da agente a strumento e da agente ad agente siano autenticati (ad esempio, TLS reciproco o JWT) e crittografati end-to-end.   |   1   | D/V  |
| 9.4.2 | Verificare che gli schemi siano rigorosamente convalidati; i campi sconosciuti o i messaggi malformati vengono rifiutati.                                     |   1   |  D   |
| 9.4.3 | Verificare che i controlli di integrità (MAC o firme digitali) coprano l'intero payload del messaggio, inclusi i parametri degli strumenti.                   |   2   | D/V  |
| 9.4.4 | Verificare che la protezione contro la ripetizione (nonce o finestre di timestamp) sia applicata a livello di protocollo.                                     |   2   |  D   |
| 9.4.5 | Verificare che le implementazioni del protocollo siano sottoposte a fuzzing e analisi statica per individuare vulnerabilità di injection o deserializzazione. |   3   |  V   |

---

## 9.5 Identità dell’Agente e Evidenza di Manomissione

Garantire che le azioni siano attribuibili e che le modifiche siano rilevabili.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Verificare che ogni istanza dell'agente possieda un'identità crittografica unica (coppia di chiavi o credenziale basata su hardware). |   1   | D/V  |
| 9.5.2 | Verificare che tutte le azioni dell'agente siano firmate e datate; i log includono la firma per la non ripudiabilità.                 |   2   | D/V  |
| 9.5.3 | Verificare che i log a prova di manomissione siano archiviati in un supporto di sola aggiunta o scrittura unica.                      |   2   |  V   |
| 9.5.4 | Verificare che le chiavi di identità ruotino secondo un programma definito e in presenza di indicatori di compromissione.             |   3   |  D   |
| 9.5.5 | Verificare che i tentativi di spoofing o conflitto di chiavi attivino l'isolamento immediato dell'agente interessato.                 |   3   | D/V  |

---

## 9.6 Riduzione del Rischio con Sciame Multi-Agente

Mitigare i rischi legati al comportamento collettivo tramite isolamento e modellazione formale della sicurezza.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Verificare che gli agenti che operano in diversi domini di sicurezza vengano eseguiti in ambienti di runtime isolati o in segmenti di rete separati.        |   1   | D/V  |
| 9.6.2 | Verificare che i comportamenti dello sciame siano modellati e formalmente verificati per la vivacità e la sicurezza prima della distribuzione.              |   3   |  V   |
| 9.6.3 | Verificare che i monitor di runtime rilevino schemi di comportamento pericolosi emergenti (ad esempio, oscillazioni, deadlock) e avviino azioni correttive. |   3   |  D   |

---

## 9.7 Autenticazione / Autorizzazione Utente e Strumento

Implementare controlli di accesso robusti per ogni azione attivata dall'agente.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Verificare che gli agenti si autentichino come principali di prima classe nei sistemi a valle, senza mai riutilizzare le credenziali dell'utente finale. |   1   | D/V  |
| 9.7.2 | Verificare che le politiche di autorizzazione a grana fine limitino gli strumenti che un agente può invocare e quali parametri può fornire.              |   2   |  D   |
| 9.7.3 | Verificare che i controlli dei privilegi vengano rivalutati ad ogni chiamata (autorizzazione continua), e non solo all'inizio della sessione.            |   2   |  V   |
| 9.7.4 | Verificare che i privilegi delegati scadano automaticamente e richiedano un nuovo consenso dopo il timeout o una modifica dell'ambito.                   |   3   |  D   |

---

## 9.8 Sicurezza nella comunicazione tra agenti

Cripta e proteggi l'integrità di tutti i messaggi tra agenti per evitare intercettazioni e manomissioni.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Verificare che l'autenticazione reciproca e la crittografia con perfetto segreto avanti (ad esempio TLS 1.3) siano obbligatorie per i canali degli agenti.                 |   1   | D/V  |
| 9.8.2 | Verificare che l'integrità e l'origine del messaggio siano convalidate prima dell'elaborazione; in caso di errori, vengono generati allarmi e il messaggio viene scartato. |   1   |  D   |
| 9.8.3 | Verificare che i metadati della comunicazione (timestamp, numeri di sequenza) siano registrati per supportare la ricostruzione forense.                                    |   2   | D/V  |
| 9.8.4 | Verificare che la verifica formale o il model checking confermino che le macchine a stati del protocollo non possano essere portate in stati non sicuri.                   |   3   |  V   |

---

## 9.9 Verifica dell'Intento e Applicazione dei Vincoli

Verificare che le azioni dell'agente siano allineate con l'intento dichiarato dall'utente e con i vincoli di sistema.

|   #   | Description                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Verificare che i risolutori di vincoli pre-esecuzione controllino le azioni proposte rispetto a regole rigide di sicurezza e di politica predefinite.                                     |   1   |  D   |
| 9.9.2 | Verificare che le azioni ad alto impatto (finanziarie, distruttive, sensibili alla privacy) richiedano una conferma esplicita dell'intento da parte dell'utente che le avvia.             |   2   | D/V  |
| 9.9.3 | Verificare che i controlli post-condizione confermino che le azioni completate abbiano raggiunto gli effetti desiderati senza effetti collaterali; le discrepanze attivano il rollback.   |   2   |  V   |
| 9.9.4 | Verificare che metodi formali (ad esempio, model checking, dimostrazione di teoremi) o test basati su proprietà dimostrino che i piani dell'agente soddisfano tutti i vincoli dichiarati. |   3   |  V   |
| 9.9.5 | Verificare che gli incidenti di incongruenza di intenti o violazione di vincoli alimentino cicli di miglioramento continuo e condivisione delle informazioni sulle minacce.               |   3   |  D   |

---

## 9.10 Strategia di Ragionamento dell'Agente per la Sicurezza

Selezione ed esecuzione sicura di diverse strategie di ragionamento, inclusi gli approcci ReAct, Chain-of-Thought e Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Verificare che la selezione della strategia di ragionamento utilizzi criteri deterministici (complessità dell’input, tipo di compito, contesto di sicurezza) e che input identici producano selezioni di strategia identiche all’interno dello stesso contesto di sicurezza. |   1   | D/V  |
| 9.10.2 | Verifica che ogni strategia di ragionamento (ReAct, Chain-of-Thought, Tree-of-Thoughts) abbia una validazione di input dedicata, una sanificazione dell'output e limiti di tempo di esecuzione specifici per il suo approccio cognitivo.                                     |   1   | D/V  |
| 9.10.3 | Verificare che le transizioni della strategia di ragionamento siano registrate con contesto completo, inclusi le caratteristiche dell'input, i valori dei criteri di selezione e i metadati di esecuzione, per la ricostruzione della traccia di controllo.                  |   2   | D/V  |
| 9.10.4 | Verificare che il ragionamento Tree-of-Thoughts includa meccanismi di potatura dei rami che terminano l'esplorazione quando vengono rilevate violazioni di policy, limiti di risorse o confini di sicurezza.                                                                 |   2   | D/V  |
| 9.10.5 | Verificare che i cicli ReAct (Reason-Act-Observe) includano punti di controllo di validazione in ogni fase: verifica del passo di ragionamento, autorizzazione dell'azione e sanificazione dell'osservazione prima di procedere.                                             |   2   | D/V  |
| 9.10.6 | Verificare che i metriche di prestazione della strategia di ragionamento (tempo di esecuzione, utilizzo delle risorse, qualità dell'output) siano monitorate con avvisi automatici quando i metriche si discostano oltre le soglie configurate.                              |   3   | D/V  |
| 9.10.7 | Verificare che gli approcci di ragionamento ibrido che combinano più strategie mantengano la validazione dell'input e i vincoli di output di tutte le strategie costituenti senza aggirare alcun controllo di sicurezza.                                                     |   3   | D/V  |
| 9.10.8 | Verificare che il testing della sicurezza della strategia di ragionamento includa il fuzzing con input malformati, prompt avversari progettati per forzare il cambio di strategia e il testing delle condizioni limite per ogni approccio cognitivo.                         |   3   | D/V  |

---

## 9.11 Gestione dello Stato del Ciclo di Vita dell'Agente e Sicurezza

Inizializzazione sicura dell'agente, transizioni di stato e terminazione con tracciamenti di controllo crittografici e procedure di recupero definite.

|   #    | Description                                                                                                                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Verificare che l'inizializzazione dell'agente includa l'istituzione dell'identità crittografica con credenziali basate su hardware e registri di controllo di avvio immutabili contenenti ID agente, timestamp, hash della configurazione e parametri di inizializzazione.                                          |   1   | D/V  |
| 9.11.2 | Verificare che le transizioni di stato dell'agente siano firmate crittograficamente, corredate di timestamp e registrate con un contesto completo che includa eventi scatenanti, hash dello stato precedente, hash del nuovo stato e le validazioni di sicurezza eseguite.                                          |   2   | D/V  |
| 9.11.3 | Verificare che le procedure di arresto dell'agente includano la cancellazione sicura della memoria mediante cancellazione crittografica o sovrascrittura multipla, la revoca delle credenziali con notifica all'autorità di certificazione e la generazione di certificati di terminazione a prova di manomissione. |   2   | D/V  |
| 9.11.4 | Verificare che i meccanismi di recupero degli agenti convalidino l'integrità dello stato utilizzando checksum crittografici (minimo SHA-256) e ripristinino stati noti privi di errori quando viene rilevata una corruzione, con allarmi automatizzati e requisiti di approvazione manuale.                         |   3   | D/V  |
| 9.11.5 | Verificare che i meccanismi di persistenza dell'agente crittografino i dati di stato sensibili con chiavi AES-256 uniche per agente e implementino la rotazione sicura delle chiavi secondo programmi configurabili (massimo 90 giorni) con distribuzione a zero tempi di inattività.                               |   3   | D/V  |

---

## 9.12 Framework di Sicurezza per l'Integrazione degli Strumenti

Controlli di sicurezza per il caricamento dinamico degli strumenti, l'esecuzione e la validazione dei risultati con processi definiti di valutazione del rischio e approvazione.

|   #    | Description                                                                                                                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Verificare che i descrittori degli strumenti includano metadati di sicurezza specificando i privilegi richiesti (lettura/scrittura/esecuzione), i livelli di rischio (basso/medio/alto), i limiti delle risorse (CPU, memoria, rete) e i requisiti di convalida documentati nei manifest degli strumenti.      |   1   | D/V  |
| 9.12.2 | Verificare che i risultati dell'esecuzione degli strumenti siano convalidati rispetto agli schemi previsti (JSON Schema, XML Schema) e alle politiche di sicurezza (sanitizzazione dell'output, classificazione dei dati) prima dell'integrazione, con limiti di timeout e procedure di gestione degli errori. |   1   | D/V  |
| 9.12.3 | Verificare che i log di interazione degli strumenti includano un contesto di sicurezza dettagliato, compreso l'uso dei privilegi, i modelli di accesso ai dati, i tempi di esecuzione, il consumo di risorse e i codici di ritorno, con una registrazione strutturata per l'integrazione SIEM.                 |   2   | D/V  |
| 9.12.4 | Verificare che i meccanismi di caricamento dinamico degli strumenti convalidino le firme digitali utilizzando l'infrastruttura PKI e implementino protocolli di caricamento sicuri con isolamento sandbox e verifica delle autorizzazioni prima dell'esecuzione.                                               |   2   | D/V  |
| 9.12.5 | Verificare che le valutazioni di sicurezza degli strumenti siano attivate automaticamente per le nuove versioni con gate di approvazione obbligatori, inclusi analisi statica, test dinamici e revisione da parte del team di sicurezza, con criteri di approvazione documentati e requisiti di SLA.           |   3   | D/V  |

---

### Riferimenti

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

