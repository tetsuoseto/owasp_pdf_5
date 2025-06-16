# C12 Monitoraggio, Registrazione e Rilevamento di Anomalie

## Obiettivo di Controllo

Questa sezione fornisce i requisiti per offrire una visibilità in tempo reale e forense su ciò che il modello e gli altri componenti di intelligenza artificiale vedono, fanno e restituiscono, in modo che le minacce possano essere rilevate, valutate e apprese.

## C12.1 Registrazione delle Richieste e delle Risposte

|   #    | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Verificare che tutte le richieste degli utenti e le risposte del modello siano registrate con i metadati appropriati (ad esempio, timestamp, ID utente, ID sessione, versione del modello).                                                                                   |   1   | D/V  |
| 12.1.2 | Verificare che i log siano archiviati in repository sicuri e controllati da accessi, con politiche di conservazione appropriate e procedure di backup.                                                                                                                        |   1   | D/V  |
| 12.1.3 | Verificare che i sistemi di archiviazione dei log implementino la crittografia a riposo e in transito per proteggere le informazioni sensibili contenute nei log.                                                                                                             |   1   | D/V  |
| 12.1.4 | Verificare che i dati sensibili nei prompt e negli output vengano automaticamente oscurati o mascherati prima della registrazione, con regole di oscuramento configurabili per le informazioni personali identificabili (PII), le credenziali e le informazioni proprietarie. |   1   | D/V  |
| 12.1.5 | Verificare che le decisioni politiche e le azioni di filtraggio per la sicurezza siano registrate con dettagli sufficienti per consentire l’audit e il debug dei sistemi di moderazione dei contenuti.                                                                        |   2   | D/V  |
| 12.1.6 | Verificare che l'integrità dei log sia protetta tramite, ad esempio, firme crittografiche o memorizzazione scrittura-sola.                                                                                                                                                    |   2   | D/V  |

---

## C12.2 Rilevamento degli Abusi e Segnalazione

|   #    | Description                                                                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Verificare che il sistema rilevi e avvisi su modelli di jailbreak noti, tentativi di iniezione di prompt e input avversari utilizzando il rilevamento basato su firme.                                                 |   1   | D/V  |
| 12.2.2 | Verificare che il sistema si integri con le piattaforme esistenti di Security Information and Event Management (SIEM) utilizzando formati di log e protocolli standard.                                                |   1   | D/V  |
| 12.2.3 | Verificare che gli eventi di sicurezza arricchiti includano contesti specifici dell'IA come identificatori di modelli, punteggi di confidenza e decisioni dei filtri di sicurezza.                                     |   2   | D/V  |
| 12.2.4 | Verificare che il rilevamento delle anomalie comportamentali identifichi modelli di conversazione insoliti, tentativi di ripetizione eccessivi o comportamenti sistematici di sondaggio.                               |   2   | D/V  |
| 12.2.5 | Verificare che i meccanismi di allerta in tempo reale notificano i team di sicurezza quando vengono rilevate potenziali violazioni delle policy o tentativi di attacco.                                                |   2   | D/V  |
| 12.2.6 | Verificare che siano incluse regole personalizzate per rilevare modelli di minacce specifici dell'IA, tra cui tentativi coordinati di jailbreak, campagne di iniezione di prompt e attacchi di estrazione del modello. |   2   | D/V  |
| 12.2.7 | Verificare che i flussi di lavoro automatizzati per la risposta agli incidenti siano in grado di isolare i modelli compromessi, bloccare gli utenti maligni e gestire eventi di sicurezza critici.                     |   3   | D/V  |

---

## C12.3 Rilevamento del Drift del Modello

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Verificare che il sistema monitori metriche di prestazione di base come accuratezza, punteggi di confidenza, latenza e tassi di errore tra le versioni del modello e i periodi di tempo.       |   1   | D/V  |
| 12.3.2 | Verificare che l'attivazione degli avvisi automatici avvenga quando le metriche di prestazione superano soglie di degrado predefinite o si discostano significativamente dalle linee di base.  |   2   | D/V  |
| 12.3.3 | Verificare che i monitor di rilevamento delle allucinazioni identifichino e segnalino i casi in cui le uscite del modello contengano informazioni fattualmente errate, incoerenti o inventate. |   2   | D/V  |

---

## C12.4 Telemetria delle Prestazioni e del Comportamento

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Verificare che le metriche operative, inclusi la latenza delle richieste, il consumo di token, l'utilizzo della memoria e la capacità di elaborazione, siano raccolte e monitorate continuamente. |   1   | D/V  |
| 12.4.2 | Verificare che i tassi di successo e di fallimento siano monitorati con la categorizzazione dei tipi di errore e delle loro cause principali.                                                     |   1   | D/V  |
| 12.4.3 | Verificare che il monitoraggio dell'utilizzo delle risorse includa l'uso della GPU/CPU, il consumo di memoria e i requisiti di archiviazione, con notifiche in caso di superamento delle soglie.  |   2   | D/V  |

---

## C12.5 Pianificazione ed esecuzione della risposta agli incidenti di intelligenza artificiale

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Verificare che i piani di risposta agli incidenti affrontino specificamente gli eventi di sicurezza legati all'IA, inclusi compromissione del modello, avvelenamento dei dati e attacchi avversari. |   1   | D/V  |
| 12.5.2 | Verificare che i team di risposta agli incidenti abbiano accesso a strumenti e competenze forensi specifici per l'IA per investigare il comportamento del modello e i vettori di attacco.           |   2   | D/V  |
| 12.5.3 | Verificare che l'analisi post-incidente includa considerazioni sul retraining del modello, aggiornamenti dei filtri di sicurezza e l'integrazione delle lezioni apprese nei controlli di sicurezza. |   3   | D/V  |

---

## C12.5 Rilevamento del Degrado delle Prestazioni dell'IA

Monitorare e rilevare il degrado delle prestazioni e della qualità del modello di intelligenza artificiale nel tempo.

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Verificare che accuratezza, precisione, richiamo e punteggi F1 del modello siano continuamente monitorati e confrontati con le soglie di riferimento.               |   1   | D/V  |
| 12.5.2 | Verificare che il rilevamento del drift dei dati monitori i cambiamenti nella distribuzione degli input che potrebbero influire sulle prestazioni del modello.      |   1   | D/V  |
| 12.5.3 | Verificare che il rilevamento del drift concettuale identifichi i cambiamenti nella relazione tra input e output attesi.                                            |   2   | D/V  |
| 12.5.4 | Verificare che il degrado delle prestazioni inneschi avvisi automatici e avvii i flussi di lavoro di riaddestramento o sostituzione del modello.                    |   2   | D/V  |
| 12.5.5 | Verificare che l'analisi delle cause principali del degrado colleghi il calo delle prestazioni a cambiamenti nei dati, problemi infrastrutturali o fattori esterni. |   3   |  V   |

---

## C12.6 Visualizzazione DAG e Sicurezza del Flusso di Lavoro

Proteggere i sistemi di visualizzazione dei flussi di lavoro da perdite di informazioni e attacchi di manipolazione.

|   #    | Description                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Verificare che i dati di visualizzazione del DAG siano sanitizzati per rimuovere informazioni sensibili prima della memorizzazione o della trasmissione.                                                            |   1   | D/V  |
| 12.6.2 | Verificare che i controlli di accesso alla visualizzazione del flusso di lavoro garantiscano che solo gli utenti autorizzati possano visualizzare i percorsi decisionali degli agenti e le tracce del ragionamento. |   1   | D/V  |
| 12.6.3 | Verificare che l'integrità dei dati del DAG sia protetta tramite firme crittografiche e meccanismi di archiviazione a prova di manomissione.                                                                        |   2   | D/V  |
| 12.6.4 | Verificare che i sistemi di visualizzazione dei flussi di lavoro implementino la convalida degli input per prevenire attacchi di injection tramite dati di nodi o archi manipolati.                                 |   2   | D/V  |
| 12.6.5 | Verificare che gli aggiornamenti in tempo reale del DAG siano limitati in frequenza e validati per prevenire attacchi di denial-of-service sui sistemi di visualizzazione.                                          |   3   | D/V  |

---

## C12.7 Monitoraggio Proattivo del Comportamento di Sicurezza

Rilevamento e prevenzione delle minacce alla sicurezza attraverso l'analisi proattiva del comportamento degli agenti.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.7.1 | Verificare che i comportamenti proattivi degli agenti siano convalidati in termini di sicurezza prima dell'esecuzione, integrando la valutazione del rischio.      |   1   | D/V  |
| 12.7.2 | Verificare che le iniziative autonome includano la valutazione del contesto di sicurezza e l'analisi del panorama delle minacce.                                   |   2   | D/V  |
| 12.7.3 | Verificare che i modelli di comportamento proattivo siano analizzati per potenziali implicazioni di sicurezza e conseguenze indesiderate.                          |   2   | D/V  |
| 12.7.4 | Verificare che le azioni proattive critiche per la sicurezza richiedano catene di approvazione esplicite con tracciamenti di controllo.                            |   3   | D/V  |
| 12.7.5 | Verificare che il rilevamento delle anomalie comportamentali identifichi deviazioni nei modelli degli agenti proattivi che potrebbero indicare una compromissione. |   3   | D/V  |

---

## Riferimenti

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

