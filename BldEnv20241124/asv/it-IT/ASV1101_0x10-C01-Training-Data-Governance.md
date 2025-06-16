# C1 Governance dei Dati di Addestramento e Gestione dei Bias

## Obiettivo di Controllo

I dati di addestramento devono essere reperiti, gestiti e mantenuti in modo da preservare la provenienza, la sicurezza, la qualità e l'equità. Farlo soddisfa gli obblighi legali e riduce i rischi di bias, avvelenamento o violazioni della privacy durante l'intero ciclo di vita dell'IA.

---

## C1.1 Provenienza dei dati di addestramento

Mantieni un inventario verificabile di tutti i dataset, accetta solo fonti affidabili e registra ogni modifica per garantire la tracciabilità.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Verificare che venga mantenuto un inventario aggiornato di ogni fonte di dati di addestramento (origine, responsabile/proprietario, licenza, metodo di raccolta, vincoli d’uso previsti e cronologia di elaborazione).                                     |   1   | D/V  |
| 1.1.2 | Verificare che siano consentiti solo set di dati verificati per qualità, rappresentatività, provenienza etica e conformità alle licenze, riducendo i rischi di avvelenamento, bias incorporati e violazione della proprietà intellettuale.                 |   1   | D/V  |
| 1.1.3 | Verificare che la minimizzazione dei dati sia applicata in modo che attributi non necessari o sensibili siano esclusi.                                                                                                                                     |   1   | D/V  |
| 1.1.4 | Verificare che tutte le modifiche al dataset siano soggette a un processo di approvazione registrato.                                                                                                                                                      |   2   | D/V  |
| 1.1.5 | Verificare che la qualità dell'etichettatura/annotazione sia garantita tramite controlli incrociati dei revisori o consenso.                                                                                                                               |   2   | D/V  |
| 1.1.6 | Verificare che siano mantenute "schede dati" o "schede tecniche per dataset" per i dataset di addestramento significativi, dettagliando caratteristiche, motivazioni, composizione, processi di raccolta, preprocessamento e usi consigliati/sconsigliati. |   2   | D/V  |

---

## C1.2 Sicurezza e Integrità dei Dati di Addestramento

Limitare l'accesso, criptare i dati a riposo e in transito, e convalidare l'integrità per bloccare manomissioni o furti.

|   #   | Description                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Verificare che i controlli di accesso proteggano l'archiviazione e le pipeline.                                                                                                                                                                                                                                                                   |   1   | D/V  |
| 1.2.2 | Verificare che i dataset siano crittografati durante il transito e, per tutte le informazioni sensibili o identificabili personalmente (PII), anche a riposo, utilizzando algoritmi crittografici standard del settore e pratiche di gestione delle chiavi.                                                                                       |   2   | D/V  |
| 1.2.3 | Verificare che vengano utilizzati hash crittografici o firme digitali per garantire l'integrità dei dati durante l'archiviazione e il trasferimento, e che vengano applicate tecniche automatiche di rilevamento delle anomalie per proteggere contro modifiche non autorizzate o corruzioni, inclusi tentativi mirati di avvelenamento dei dati. |   2   | D/V  |
| 1.2.4 | Verificare che le versioni del dataset siano tracciate per consentire il rollback.                                                                                                                                                                                                                                                                |   3   | D/V  |
| 1.2.5 | Verificare che i dati obsoleti vengano eliminati in modo sicuro o anonimizzati in conformità con le politiche di conservazione dei dati, i requisiti normativi e per ridurre la superficie di attacco.                                                                                                                                            |   2   | D/V  |

---

## C1.3 Completezza e equità della rappresentazione

Rilevare le distorsioni demografiche e applicare misure correttive affinché i tassi di errore del modello siano equi tra i gruppi.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Verificare che i dataset siano analizzati per squilibri rappresentativi e potenziali bias tra attributi protetti dalla legge (ad esempio, razza, genere, età) e altre caratteristiche eticamente sensibili rilevanti per il dominio di applicazione del modello (ad esempio, stato socio-economico, luogo).                                                                     |   1   | D/V  |
| 1.3.2 | Verificare che i bias identificati siano mitigati tramite strategie documentate come il riequilibrio, l'aumento mirato dei dati, aggiustamenti algoritmici (ad esempio, tecniche di pre-elaborazione, elaborazione in corso, post-elaborazione) o la ripesatura, e che l'impatto della mitigazione sia valutato sia sulla equità sia sulle prestazioni complessive del modello. |   2   | D/V  |
| 1.3.3 | Verificare che le metriche di equità post-addestramento siano valutate e documentate.                                                                                                                                                                                                                                                                                           |   2   | D/V  |
| 1.3.4 | Verificare che una politica di gestione del bias nel ciclo di vita assegni i proprietari e la cadenza delle revisioni.                                                                                                                                                                                                                                                          |   3   | D/V  |

---

## C1.4 Qualità, Integrità e Sicurezza dell'Etichettatura dei Dati di Addestramento

Proteggi le etichette con crittografia e richiedi una doppia revisione per le classi critiche.

|   #   | Description                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.4.1 | Verificare che la qualità dell'etichettatura/annotazione sia garantita tramite linee guida chiare, controlli incrociati da parte dei revisori, meccanismi di consenso (ad esempio, monitoraggio dell'accordo tra annotatori) e processi definiti per la risoluzione delle discrepanze.                 |   2   | D/V  |
| 1.4.2 | Verificare che hash crittografici o firme digitali siano applicati agli artefatti delle etichette per garantirne l'integrità e l'autenticità.                                                                                                                                                          |   2   | D/V  |
| 1.4.3 | Verificare che le interfacce e le piattaforme di etichettatura applichino controlli di accesso rigorosi, mantengano registri di audit anti-manomissione di tutte le attività di etichettatura e proteggano contro modifiche non autorizzate.                                                           |   2   | D/V  |
| 1.4.4 | Verificare che le etichette critiche per la sicurezza, la protezione o l'equità (ad esempio, l'identificazione di contenuti tossici, risultati medici critici) ricevano una revisione doppia indipendente obbligatoria o una verifica robusta equivalente.                                             |   3   | D/V  |
| 1.4.5 | Verificare che le informazioni sensibili (inclusi i dati personali identificabili - PII) catturate involontariamente o necessariamente presenti nelle etichette siano oscurate, pseudonimizzate, anonimizzate o criptate a riposo e in transito, conformemente ai principi di minimizzazione dei dati. |   2   | D/V  |
| 1.4.6 | Verificare che le guide di etichettatura e le istruzioni siano complete, controllate nelle versioni e sottoposte a revisione tra pari.                                                                                                                                                                 |   2   | D/V  |
| 1.4.7 | Verificare che gli schemi dei dati (inclusi quelli per le etichette) siano chiaramente definiti e sottoposti a controllo di versione.                                                                                                                                                                  |   2   | D/V  |
| 1.8.2 | Verificare che i flussi di lavoro di etichettatura esternalizzati o basati sul crowdsourcing includano salvaguardie tecniche/procedurali per garantire la riservatezza, l'integrità dei dati, la qualità delle etichette e prevenire la fuoriuscita di dati.                                           |   2   | D/V  |

---

## C1.5 Garanzia della qualità dei dati di addestramento

Combina la convalida automatica, i controlli manuali a campione e la registrazione delle correzioni per garantire l'affidabilità del set di dati.

|   #   | Description                                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Verificare che i test automatizzati individuino errori di formato, valori nulli e distorsioni delle etichette ad ogni ingestione o trasformazione significativa.                                                                                                                                                                    |   1   |  D   |
| 1.5.2 | Verificare che i dataset falliti siano messi in quarantena con tracce di controllo.                                                                                                                                                                                                                                                 |   1   | D/V  |
| 1.5.3 | Verificare che i controlli manuali a campione effettuati da esperti del settore coprano un campione statisticamente significativo (ad esempio, ≥1% o 1.000 campioni, a seconda di quale sia maggiore, o come determinato dalla valutazione del rischio) per identificare problemi di qualità sottili non rilevati dall'automazione. |   2   |  V   |
| 1.5.4 | Verificare che i passaggi di rimedio siano aggiunti ai record di provenienza.                                                                                                                                                                                                                                                       |   2   | D/V  |
| 1.5.5 | Verificare che le quality gate blocchino i dataset di qualità inferiore a meno che non siano approvate eccezioni.                                                                                                                                                                                                                   |   2   | D/V  |

---

## C1.6 Rilevamento Avvelenamento dei Dati

Applicare il rilevamento statistico delle anomalie e i flussi di lavoro di quarantena per bloccare le inserzioni avversarie.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verificare che le tecniche di rilevamento delle anomalie (ad esempio, metodi statistici, rilevamento di outlier, analisi degli embeddings) siano applicate ai dati di addestramento al momento dell’ingestione e prima delle principali sessioni di addestramento per identificare potenziali attacchi di avvelenamento o errori di corruzione accidentale dei dati. |   2   | D/V  |
| 1.6.2 | Verificare che i campioni segnalati attivino una revisione manuale prima dell'addestramento.                                                                                                                                                                                                                                                                         |   2   | D/V  |
| 1.6.3 | Verificare che i risultati alimentino il dossier di sicurezza del modello e informino l'intelligence sulle minacce in corso.                                                                                                                                                                                                                                         |   2   |  V   |
| 1.6.4 | Verificare che la logica di rilevamento sia aggiornata con nuove informazioni sulle minacce.                                                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.5 | Verifica che le pipeline di apprendimento online monitorino il cambiamento di distribuzione.                                                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.6 | Verificare che siano prese in considerazione e implementate difese specifiche contro tipi noti di attacchi di avvelenamento dei dati (ad esempio, inversione delle etichette, inserimento di trigger di backdoor, attacchi con istanze influenti) in base al profilo di rischio del sistema e alle fonti dei dati.                                                   |   3   | D/V  |

---

## C1.7 Cancellazione dei dati utente e applicazione del consenso

Onorare le richieste di cancellazione e di ritiro del consenso attraverso i dataset, i backup e gli artefatti derivati.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.7.1 | Verificare che i flussi di lavoro di cancellazione eliminino i dati primari e derivati e valutare l'impatto sul modello, assicurandosi che l'impatto sui modelli interessati venga valutato e, se necessario, affrontato (ad esempio, tramite riaddestramento o ricalibrazione).                                                                       |   1   | D/V  |
| 1.7.2 | Verificare che siano in atto meccanismi per monitorare e rispettare l'ambito e lo stato del consenso dell'utente (e dei suoi eventuali ritiri) riguardo ai dati utilizzati nell'addestramento, e che il consenso sia convalidato prima che i dati vengano incorporati in nuovi processi di addestramento o in aggiornamenti significativi del modello. |   2   |  D   |
| 1.7.3 | Verificare che i flussi di lavoro siano testati annualmente e registrati.                                                                                                                                                                                                                                                                              |   2   |  V   |

---

## C1.8 Sicurezza della catena di approvvigionamento

Verificare i fornitori esterni di dati e garantire l'integrità tramite canali autenticati e criptati.

|   #   | Description                                                                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verificare che i fornitori di dati terzi, inclusi i provider di modelli pre-addestrati e dataset esterni, siano sottoposti a controlli di sicurezza, privacy, approvvigionamento etico e qualità dei dati prima che i loro dati o modelli vengano integrati.                                                                              |   2   | D/V  |
| 1.8.2 | Verificare che i trasferimenti esterni utilizzino TLS/autenticazione e controlli di integrità.                                                                                                                                                                                                                                            |   1   |  D   |
| 1.8.3 | Verificare che le fonti di dati ad alto rischio (ad esempio, set di dati open-source con provenienza sconosciuta, fornitori non verificati) ricevano un esame approfondito, come analisi in ambiente isolato (sandbox), controlli estesi di qualità/bias e rilevamento mirato di avvelenamento, prima dell’uso in applicazioni sensibili. |   2   | D/V  |
| 1.8.4 | Verificare che i modelli pre-addestrati ottenuti da terze parti siano valutati per bias incorporati, potenziali backdoor, integrità della loro architettura e provenienza dei dati originali di addestramento prima di procedere al fine-tuning o al deployment.                                                                          |   3   | D/V  |

---

## C1.9 Rilevamento di Campioni Avversari

Implementare misure durante la fase di addestramento, come l'addestramento avversariale, per migliorare la resilienza del modello contro esempi avversari.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Verificare che siano implementate e ottimizzate difese appropriate, come l'addestramento avversariale (utilizzando esempi avversariali generati), l'aumento dei dati con input perturbati o tecniche di ottimizzazione robusta, per i modelli rilevanti in base alla valutazione del rischio. |   3   | D/V  |
| 1.9.2 | Verificare che, se viene utilizzato l'addestramento avversariale, la generazione, la gestione e la versione dei dataset avversariali siano documentate e controllate.                                                                                                                         |   2   | D/V  |
| 1.9.3 | Verificare che l'impatto dell'addestramento alla robustezza avversaria sulle prestazioni del modello (sia contro input puliti che avversari) e sulle metriche di equità sia valutato, documentato e monitorato.                                                                               |   3   | D/V  |
| 1.9.4 | Verificare che le strategie per l'addestramento avversariale e la robustezza vengano periodicamente revisionate e aggiornate per contrastare le tecniche di attacco avversario in evoluzione.                                                                                                 |   3   | D/V  |

---

## C1.10 Tracciabilità e Lineage dei Dati

Traccia l'intero percorso di ogni dato, dalla fonte all'input del modello, per garantire la tracciabilità e la risposta agli incidenti.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verificare che la provenienza di ogni punto dati, comprese tutte le trasformazioni, aumenti e fusioni, sia registrata e possa essere ricostruita. |   2   | D/V  |
| 1.10.2 | Verificare che i record di provenienza siano immutabili, memorizzati in modo sicuro e accessibili per audit o indagini.                           |   2   | D/V  |
| 1.10.3 | Verificare che il tracciamento della provenienza copra sia i dati grezzi sia quelli sintetici.                                                    |   2   | D/V  |

---

## C1.11 Gestione dei dati sintetici

Garantire che i dati sintetici siano gestiti correttamente, etichettati e valutati in termini di rischio.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Verificare che tutti i dati sintetici siano chiaramente etichettati e distinguibili dai dati reali lungo l'intero flusso di elaborazione.                 |   2   | D/V  |
| 1.11.2 | Verificare che il processo di generazione, i parametri e l'uso previsto dei dati sintetici siano documentati.                                             |   2   | D/V  |
| 1.11.3 | Verificare che i dati sintetici siano valutati per i rischi di bias, perdita di privacy e problemi di rappresentazione prima dell'uso nell'addestramento. |   2   | D/V  |

---

## C1.12 Monitoraggio dell’Accesso ai Dati e Rilevamento delle Anomalie

Monitorare e segnalare accessi anomali ai dati di addestramento per rilevare minacce interne o esfiltrazioni.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Verificare che ogni accesso ai dati di addestramento sia registrato, includendo utente, orario e azione.                                                 |   2   | D/V  |
| 1.12.2 | Verificare che i registri di accesso vengano regolarmente esaminati per rilevare modelli insoliti, come grandi esportazioni o accessi da nuove località. |   2   | D/V  |
| 1.12.3 | Verificare che vengano generate allerte per eventi di accesso sospetti e che vengano indagate tempestivamente.                                           |   2   | D/V  |

---

## C1.13 Politiche di conservazione e scadenza dei dati

Definire e applicare periodi di conservazione dei dati per ridurre al minimo l'archiviazione di dati non necessaria.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Verificare che siano definiti periodi di conservazione espliciti per tutti i set di dati di addestramento.                             |   1   | D/V  |
| 1.13.2 | Verificare che i dataset vengano automaticamente scaduti, eliminati o esaminati per la cancellazione alla fine del loro ciclo di vita. |   2   | D/V  |
| 1.13.3 | Verificare che le azioni di conservazione e cancellazione siano registrate e verificabili.                                             |   2   | D/V  |

---

## C1.14 Conformità Normativa e Giurisdizionale

Garantire che tutti i dati di addestramento siano conformi alle leggi e alle normative applicabili.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Verificare che i requisiti di residenza dei dati e di trasferimento transfrontaliero siano identificati e applicati per tutti i set di dati. |   2   | D/V  |
| 1.14.2 | Verificare che le normative specifiche di settore (ad esempio, sanità, finanza) siano identificate e rispettate nella gestione dei dati.     |   2   | D/V  |
| 1.14.3 | Verificare che la conformità alle leggi sulla privacy pertinenti (ad es. GDPR, CCPA) sia documentata e revisionata regolarmente.             |   2   | D/V  |

---

## C1.15 Filigrana e Marcatura dei Dati

Rilevare il riutilizzo non autorizzato o la fuoriuscita di dati proprietari o sensibili.

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Verificare che i dataset o i sottoinsiemi siano contrassegnati con watermark o fingerprint dove possibile.                   |   3   | D/V  |
| 1.15.2 | Verificare che i metodi di watermarking/fingerprinting non introducano pregiudizi o rischi per la privacy.                   |   3   | D/V  |
| 1.15.3 | Verificare che vengano effettuati controlli periodici per rilevare l'uso non autorizzato o la perdita di dati con filigrana. |   3   | D/V  |

---

## C1.16 Gestione dei Diritti degli Interessati ai Dati

Supportare i diritti del soggetto dei dati come accesso, rettifica, limitazione e opposizione.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Verificare che esistano meccanismi per rispondere alle richieste dei soggetti interessati di accesso, rettifica, limitazione o opposizione. |   2   | D/V  |
| 1.16.2 | Verificare che le richieste siano registrate, monitorate e soddisfatte entro i termini di legge previsti.                                   |   2   | D/V  |
| 1.16.3 | Verificare che i processi relativi ai diritti degli interessati siano testati e revisionati regolarmente per garantirne l'efficacia.        |   2   | D/V  |

---

## C1.17 Analisi dell'Impatto della Versione del Dataset

Valutare l'impatto delle modifiche al dataset prima di aggiornare o sostituire le versioni.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Verificare che venga eseguita un'analisi d'impatto prima di aggiornare o sostituire una versione del dataset, coprendo le prestazioni del modello, l'equità e la conformità. |   2   | D/V  |
| 1.17.2 | Verificare che i risultati dell'analisi d'impatto siano documentati e revisionati dalle parti interessate rilevanti.                                                         |   2   | D/V  |
| 1.17.3 | Verificare che esistano piani di rollback nel caso in cui le nuove versioni introducano rischi inaccettabili o regressioni.                                                  |   2   | D/V  |

---

## C1.18 Sicurezza della forza lavoro per l'annotazione dei dati

Garantire la sicurezza e l'integrità del personale coinvolto nell'annotazione dei dati.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Verificare che tutto il personale coinvolto nell'annotazione dei dati sia sottoposto a controllo dei precedenti e formato sulla sicurezza e la privacy dei dati. |   2   | D/V  |
| 1.18.2 | Verificare che tutto il personale di annotazione firmi accordi di riservatezza e di non divulgazione.                                                            |   2   | D/V  |
| 1.18.3 | Verificare che le piattaforme di annotazione applichino controlli di accesso e monitorino le minacce interne.                                                    |   2   | D/V  |

---

## Riferimenti

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

