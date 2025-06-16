## Frontespizio

### Informazioni sullo Standard

Lo Standard di Verifica della Sicurezza dell'Intelligenza Artificiale (AISVS) è un catalogo di requisiti di sicurezza guidato dalla comunità che data scientist, ingegneri MLOps, architetti software, sviluppatori, tester, professionisti della sicurezza, fornitori di strumenti, regolatori e consumatori possono utilizzare per progettare, costruire, testare e verificare sistemi e applicazioni abilitati all'IA affidabili. Fornisce un linguaggio comune per specificare i controlli di sicurezza lungo l'intero ciclo di vita dell'IA — dalla raccolta dei dati e sviluppo del modello fino al deployment e al monitoraggio continuo — in modo che le organizzazioni possano misurare e migliorare la resilienza, la privacy e la sicurezza delle loro soluzioni di IA.

### Copyright e Licenza

Versione 0.1 (Prima bozza pubblica - Lavori in corso), 2025  

![license](images/license.png)
Copyright © 2025 Il Progetto AISVS.  

Rilasciato sotto laCreative Commons Attribution‑ShareAlike 4.0 International License.
Per qualsiasi riutilizzo o distribuzione, devi comunicare chiaramente i termini della licenza di questo lavoro agli altri.

### Responsabili di Progetto

Jim Manico
Aras “Russ” Memisyazici

### Contributori e Revisori

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS è un nuovo standard creato appositamente per affrontare le sfide uniche di sicurezza dei sistemi di intelligenza artificiale. Pur traendo ispirazione dalle migliori pratiche di sicurezza più ampie, ogni requisito di AISVS è stato sviluppato da zero per riflettere il panorama delle minacce dell'IA e per aiutare le organizzazioni a costruire soluzioni di IA più sicure e resilienti.

## Prefazione

Benvenuti allo Standard di Verifica della Sicurezza dell'Intelligenza Artificiale (AISVS) versione 1.0!

### Introduzione

Fondata nel 2025 tramite uno sforzo collaborativo della comunità, AISVS definisce i requisiti di sicurezza da considerare nella progettazione, sviluppo, distribuzione e gestione di modelli di IA moderni, pipeline e servizi abilitati all'IA.

AISVS v1.0 rappresenta il lavoro combinato dei suoi responsabili di progetto, del gruppo di lavoro e dei contributori della comunità più ampia per produrre una baseline pragmatica e testabile per la sicurezza dei sistemi di IA.

Il nostro obiettivo con questa versione è rendere AISVS facile da adottare, mantenendo al contempo un focus preciso sul suo ambito definito e affrontando il panorama dei rischi in rapida evoluzione, unico per l'IA.

### Obiettivi principali per AISVS Versione 1.0

La versione 1.0 sarà creata seguendo diversi principi guida.

#### Ambito Ben Definito

Ogni requisito deve essere allineato con il nome e la missione di AISVS:

Intelligenza Artificiale – I controlli operano a livello AI/ML (dati, modello, pipeline o inferenza) e sono responsabilità degli operatori AI.
Sicurezza – I requisiti mitigano direttamente i rischi identificati di sicurezza, privacy o sicurezza operativa.
Verifica – Il linguaggio è scritto in modo che la conformità possa essere convalidata oggettivamente.
Standard – Le sezioni seguono una struttura e una terminologia coerenti per formare un riferimento omogeneo.
​
---

Seguendo AISVS, le organizzazioni possono valutare sistematicamente e rafforzare la postura di sicurezza delle loro soluzioni di intelligenza artificiale, promuovendo una cultura di ingegneria dell'IA sicura.

## Utilizzando l'AISVS

Lo Standard di Verifica della Sicurezza dell'Intelligenza Artificiale (AISVS) definisce i requisiti di sicurezza per le moderne applicazioni e servizi di IA, concentrandosi sugli aspetti sotto il controllo degli sviluppatori di applicazioni.

L'AISVS è destinato a chiunque sviluppi o valuti la sicurezza delle applicazioni di intelligenza artificiale, inclusi sviluppatori, architetti, ingegneri della sicurezza e revisori. Questo capitolo introduce la struttura e l'uso dell'AISVS, inclusi i suoi livelli di verifica e i casi d'uso previsti.

### Livelli di verifica della sicurezza dell'Intelligenza Artificiale

L'AISVS definisce tre livelli crescenti di verifica della sicurezza. Ogni livello aggiunge profondità e complessità, permettendo alle organizzazioni di adattare la loro postura di sicurezza al livello di rischio dei loro sistemi di intelligenza artificiale.

Le organizzazioni possono iniziare al Livello 1 e adottare progressivamente livelli superiori man mano che la maturità della sicurezza e l'esposizione alle minacce aumentano.

#### Definizione dei Livelli

Ogni requisito in AISVS v1.0 è assegnato a uno dei seguenti livelli:

 Requisiti di Livello 1

Il Livello 1 include i requisiti di sicurezza più critici e fondamentali. Questi si concentrano sulla prevenzione di attacchi comuni che non si basano su altre condizioni preliminari o vulnerabilità. La maggior parte dei controlli di Livello 1 è o semplice da implementare o abbastanza essenziale da giustificare lo sforzo.

 Requisiti di livello 2

Il Livello 2 affronta attacchi più avanzati o meno comuni, nonché difese stratificate contro minacce diffuse. Questi requisiti possono comportare logiche più complesse o mirare a prerequisiti specifici degli attacchi.

 Requisiti di livello 3

Il livello 3 include controlli che sono tipicamente più difficili da implementare o situazionali nella loro applicabilità. Questi spesso rappresentano meccanismi di difesa in profondità o mitigazioni contro attacchi di nicchia, mirati o ad alta complessità.

#### Ruolo (D/V)

Ogni requisito AISVS è contrassegnato in base al pubblico principale:

D – Requisiti focalizzati sullo sviluppatore
V – Requisiti focalizzati sul verificatore/revisore
D/V – Rilevante sia per sviluppatori che per verificatori

## C1 Governance dei Dati di Addestramento e Gestione dei Bias

### Obiettivo di Controllo

I dati di addestramento devono essere reperiti, gestiti e mantenuti in modo da preservare la provenienza, la sicurezza, la qualità e l'equità. Farlo soddisfa gli obblighi legali e riduce i rischi di bias, avvelenamento o violazioni della privacy durante l'intero ciclo di vita dell'IA.

---

### C1.1 Provenienza dei dati di addestramento

Mantieni un inventario verificabile di tutti i dataset, accetta solo fonti affidabili e registra ogni modifica per garantire la tracciabilità.

 #1.1.1    Level: 1    Role: D/V
 Verificare che venga mantenuto un inventario aggiornato di ogni fonte di dati di addestramento (origine, responsabile/proprietario, licenza, metodo di raccolta, vincoli d’uso previsti e cronologia di elaborazione).
 #1.1.2    Level: 1    Role: D/V
 Verificare che siano consentiti solo set di dati verificati per qualità, rappresentatività, provenienza etica e conformità alle licenze, riducendo i rischi di avvelenamento, bias incorporati e violazione della proprietà intellettuale.
 #1.1.3    Level: 1    Role: D/V
 Verificare che la minimizzazione dei dati sia applicata in modo che attributi non necessari o sensibili siano esclusi.
 #1.1.4    Level: 2    Role: D/V
 Verificare che tutte le modifiche al dataset siano soggette a un processo di approvazione registrato.
 #1.1.5    Level: 2    Role: D/V
 Verificare che la qualità dell'etichettatura/annotazione sia garantita tramite controlli incrociati dei revisori o consenso.
 #1.1.6    Level: 2    Role: D/V
 Verificare che siano mantenute "schede dati" o "schede tecniche per dataset" per i dataset di addestramento significativi, dettagliando caratteristiche, motivazioni, composizione, processi di raccolta, preprocessamento e usi consigliati/sconsigliati.

---

### C1.2 Sicurezza e Integrità dei Dati di Addestramento

Limitare l'accesso, criptare i dati a riposo e in transito, e convalidare l'integrità per bloccare manomissioni o furti.

 #1.2.1    Level: 1    Role: D/V
 Verificare che i controlli di accesso proteggano l'archiviazione e le pipeline.
 #1.2.2    Level: 2    Role: D/V
 Verificare che i dataset siano crittografati durante il transito e, per tutte le informazioni sensibili o identificabili personalmente (PII), anche a riposo, utilizzando algoritmi crittografici standard del settore e pratiche di gestione delle chiavi.
 #1.2.3    Level: 2    Role: D/V
 Verificare che vengano utilizzati hash crittografici o firme digitali per garantire l'integrità dei dati durante l'archiviazione e il trasferimento, e che vengano applicate tecniche automatiche di rilevamento delle anomalie per proteggere contro modifiche non autorizzate o corruzioni, inclusi tentativi mirati di avvelenamento dei dati.
 #1.2.4    Level: 3    Role: D/V
 Verificare che le versioni del dataset siano tracciate per consentire il rollback.
 #1.2.5    Level: 2    Role: D/V
 Verificare che i dati obsoleti vengano eliminati in modo sicuro o anonimizzati in conformità con le politiche di conservazione dei dati, i requisiti normativi e per ridurre la superficie di attacco.

---

### C1.3 Completezza e equità della rappresentazione

Rilevare le distorsioni demografiche e applicare misure correttive affinché i tassi di errore del modello siano equi tra i gruppi.

 #1.3.1    Level: 1    Role: D/V
 Verificare che i dataset siano analizzati per squilibri rappresentativi e potenziali bias tra attributi protetti dalla legge (ad esempio, razza, genere, età) e altre caratteristiche eticamente sensibili rilevanti per il dominio di applicazione del modello (ad esempio, stato socio-economico, luogo).
 #1.3.2    Level: 2    Role: D/V
 Verificare che i bias identificati siano mitigati tramite strategie documentate come il riequilibrio, l'aumento mirato dei dati, aggiustamenti algoritmici (ad esempio, tecniche di pre-elaborazione, elaborazione in corso, post-elaborazione) o la ripesatura, e che l'impatto della mitigazione sia valutato sia sulla equità sia sulle prestazioni complessive del modello.
 #1.3.3    Level: 2    Role: D/V
 Verificare che le metriche di equità post-addestramento siano valutate e documentate.
 #1.3.4    Level: 3    Role: D/V
 Verificare che una politica di gestione del bias nel ciclo di vita assegni i proprietari e la cadenza delle revisioni.

---

### C1.4 Qualità, Integrità e Sicurezza dell'Etichettatura dei Dati di Addestramento

Proteggi le etichette con crittografia e richiedi una doppia revisione per le classi critiche.

 #1.4.1    Level: 2    Role: D/V
 Verificare che la qualità dell'etichettatura/annotazione sia garantita tramite linee guida chiare, controlli incrociati da parte dei revisori, meccanismi di consenso (ad esempio, monitoraggio dell'accordo tra annotatori) e processi definiti per la risoluzione delle discrepanze.
 #1.4.2    Level: 2    Role: D/V
 Verificare che hash crittografici o firme digitali siano applicati agli artefatti delle etichette per garantirne l'integrità e l'autenticità.
 #1.4.3    Level: 2    Role: D/V
 Verificare che le interfacce e le piattaforme di etichettatura applichino controlli di accesso rigorosi, mantengano registri di audit anti-manomissione di tutte le attività di etichettatura e proteggano contro modifiche non autorizzate.
 #1.4.4    Level: 3    Role: D/V
 Verificare che le etichette critiche per la sicurezza, la protezione o l'equità (ad esempio, l'identificazione di contenuti tossici, risultati medici critici) ricevano una revisione doppia indipendente obbligatoria o una verifica robusta equivalente.
 #1.4.5    Level: 2    Role: D/V
 Verificare che le informazioni sensibili (inclusi i dati personali identificabili - PII) catturate involontariamente o necessariamente presenti nelle etichette siano oscurate, pseudonimizzate, anonimizzate o criptate a riposo e in transito, conformemente ai principi di minimizzazione dei dati.
 #1.4.6    Level: 2    Role: D/V
 Verificare che le guide di etichettatura e le istruzioni siano complete, controllate nelle versioni e sottoposte a revisione tra pari.
 #1.4.7    Level: 2    Role: D/V
 Verificare che gli schemi dei dati (inclusi quelli per le etichette) siano chiaramente definiti e sottoposti a controllo di versione.
 #1.8.2    Level: 2    Role: D/V
 Verificare che i flussi di lavoro di etichettatura esternalizzati o basati sul crowdsourcing includano salvaguardie tecniche/procedurali per garantire la riservatezza, l'integrità dei dati, la qualità delle etichette e prevenire la fuoriuscita di dati.

---

### C1.5 Garanzia della qualità dei dati di addestramento

Combina la convalida automatica, i controlli manuali a campione e la registrazione delle correzioni per garantire l'affidabilità del set di dati.

 #1.5.1    Level: 1    Role: D
 Verificare che i test automatizzati individuino errori di formato, valori nulli e distorsioni delle etichette ad ogni ingestione o trasformazione significativa.
 #1.5.2    Level: 1    Role: D/V
 Verificare che i dataset falliti siano messi in quarantena con tracce di controllo.
 #1.5.3    Level: 2    Role: V
 Verificare che i controlli manuali a campione effettuati da esperti del settore coprano un campione statisticamente significativo (ad esempio, ≥1% o 1.000 campioni, a seconda di quale sia maggiore, o come determinato dalla valutazione del rischio) per identificare problemi di qualità sottili non rilevati dall'automazione.
 #1.5.4    Level: 2    Role: D/V
 Verificare che i passaggi di rimedio siano aggiunti ai record di provenienza.
 #1.5.5    Level: 2    Role: D/V
 Verificare che le quality gate blocchino i dataset di qualità inferiore a meno che non siano approvate eccezioni.

---

### C1.6 Rilevamento Avvelenamento dei Dati

Applicare il rilevamento statistico delle anomalie e i flussi di lavoro di quarantena per bloccare le inserzioni avversarie.

 #1.6.1    Level: 2    Role: D/V
 Verificare che le tecniche di rilevamento delle anomalie (ad esempio, metodi statistici, rilevamento di outlier, analisi degli embeddings) siano applicate ai dati di addestramento al momento dell’ingestione e prima delle principali sessioni di addestramento per identificare potenziali attacchi di avvelenamento o errori di corruzione accidentale dei dati.
 #1.6.2    Level: 2    Role: D/V
 Verificare che i campioni segnalati attivino una revisione manuale prima dell'addestramento.
 #1.6.3    Level: 2    Role: V
 Verificare che i risultati alimentino il dossier di sicurezza del modello e informino l'intelligence sulle minacce in corso.
 #1.6.4    Level: 3    Role: D/V
 Verificare che la logica di rilevamento sia aggiornata con nuove informazioni sulle minacce.
 #1.6.5    Level: 3    Role: D/V
 Verifica che le pipeline di apprendimento online monitorino il cambiamento di distribuzione.
 #1.6.6    Level: 3    Role: D/V
 Verificare che siano prese in considerazione e implementate difese specifiche contro tipi noti di attacchi di avvelenamento dei dati (ad esempio, inversione delle etichette, inserimento di trigger di backdoor, attacchi con istanze influenti) in base al profilo di rischio del sistema e alle fonti dei dati.

---

### C1.7 Cancellazione dei dati utente e applicazione del consenso

Onorare le richieste di cancellazione e di ritiro del consenso attraverso i dataset, i backup e gli artefatti derivati.

 #1.7.1    Level: 1    Role: D/V
 Verificare che i flussi di lavoro di cancellazione eliminino i dati primari e derivati e valutare l'impatto sul modello, assicurandosi che l'impatto sui modelli interessati venga valutato e, se necessario, affrontato (ad esempio, tramite riaddestramento o ricalibrazione).
 #1.7.2    Level: 2    Role: D
 Verificare che siano in atto meccanismi per monitorare e rispettare l'ambito e lo stato del consenso dell'utente (e dei suoi eventuali ritiri) riguardo ai dati utilizzati nell'addestramento, e che il consenso sia convalidato prima che i dati vengano incorporati in nuovi processi di addestramento o in aggiornamenti significativi del modello.
 #1.7.3    Level: 2    Role: V
 Verificare che i flussi di lavoro siano testati annualmente e registrati.

---

### C1.8 Sicurezza della catena di approvvigionamento

Verificare i fornitori esterni di dati e garantire l'integrità tramite canali autenticati e criptati.

 #1.8.1    Level: 2    Role: D/V
 Verificare che i fornitori di dati terzi, inclusi i provider di modelli pre-addestrati e dataset esterni, siano sottoposti a controlli di sicurezza, privacy, approvvigionamento etico e qualità dei dati prima che i loro dati o modelli vengano integrati.
 #1.8.2    Level: 1    Role: D
 Verificare che i trasferimenti esterni utilizzino TLS/autenticazione e controlli di integrità.
 #1.8.3    Level: 2    Role: D/V
 Verificare che le fonti di dati ad alto rischio (ad esempio, set di dati open-source con provenienza sconosciuta, fornitori non verificati) ricevano un esame approfondito, come analisi in ambiente isolato (sandbox), controlli estesi di qualità/bias e rilevamento mirato di avvelenamento, prima dell’uso in applicazioni sensibili.
 #1.8.4    Level: 3    Role: D/V
 Verificare che i modelli pre-addestrati ottenuti da terze parti siano valutati per bias incorporati, potenziali backdoor, integrità della loro architettura e provenienza dei dati originali di addestramento prima di procedere al fine-tuning o al deployment.

---

### C1.9 Rilevamento di Campioni Avversari

Implementare misure durante la fase di addestramento, come l'addestramento avversariale, per migliorare la resilienza del modello contro esempi avversari.

 #1.9.1    Level: 3    Role: D/V
 Verificare che siano implementate e ottimizzate difese appropriate, come l'addestramento avversariale (utilizzando esempi avversariali generati), l'aumento dei dati con input perturbati o tecniche di ottimizzazione robusta, per i modelli rilevanti in base alla valutazione del rischio.
 #1.9.2    Level: 2    Role: D/V
 Verificare che, se viene utilizzato l'addestramento avversariale, la generazione, la gestione e la versione dei dataset avversariali siano documentate e controllate.
 #1.9.3    Level: 3    Role: D/V
 Verificare che l'impatto dell'addestramento alla robustezza avversaria sulle prestazioni del modello (sia contro input puliti che avversari) e sulle metriche di equità sia valutato, documentato e monitorato.
 #1.9.4    Level: 3    Role: D/V
 Verificare che le strategie per l'addestramento avversariale e la robustezza vengano periodicamente revisionate e aggiornate per contrastare le tecniche di attacco avversario in evoluzione.

---

### C1.10 Tracciabilità e Lineage dei Dati

Traccia l'intero percorso di ogni dato, dalla fonte all'input del modello, per garantire la tracciabilità e la risposta agli incidenti.

 #1.10.1    Level: 2    Role: D/V
 Verificare che la provenienza di ogni punto dati, comprese tutte le trasformazioni, aumenti e fusioni, sia registrata e possa essere ricostruita.
 #1.10.2    Level: 2    Role: D/V
 Verificare che i record di provenienza siano immutabili, memorizzati in modo sicuro e accessibili per audit o indagini.
 #1.10.3    Level: 2    Role: D/V
 Verificare che il tracciamento della provenienza copra sia i dati grezzi sia quelli sintetici.

---

### C1.11 Gestione dei dati sintetici

Garantire che i dati sintetici siano gestiti correttamente, etichettati e valutati in termini di rischio.

 #1.11.1    Level: 2    Role: D/V
 Verificare che tutti i dati sintetici siano chiaramente etichettati e distinguibili dai dati reali lungo l'intero flusso di elaborazione.
 #1.11.2    Level: 2    Role: D/V
 Verificare che il processo di generazione, i parametri e l'uso previsto dei dati sintetici siano documentati.
 #1.11.3    Level: 2    Role: D/V
 Verificare che i dati sintetici siano valutati per i rischi di bias, perdita di privacy e problemi di rappresentazione prima dell'uso nell'addestramento.

---

### C1.12 Monitoraggio dell’Accesso ai Dati e Rilevamento delle Anomalie

Monitorare e segnalare accessi anomali ai dati di addestramento per rilevare minacce interne o esfiltrazioni.

 #1.12.1    Level: 2    Role: D/V
 Verificare che ogni accesso ai dati di addestramento sia registrato, includendo utente, orario e azione.
 #1.12.2    Level: 2    Role: D/V
 Verificare che i registri di accesso vengano regolarmente esaminati per rilevare modelli insoliti, come grandi esportazioni o accessi da nuove località.
 #1.12.3    Level: 2    Role: D/V
 Verificare che vengano generate allerte per eventi di accesso sospetti e che vengano indagate tempestivamente.

---

### C1.13 Politiche di conservazione e scadenza dei dati

Definire e applicare periodi di conservazione dei dati per ridurre al minimo l'archiviazione di dati non necessaria.

 #1.13.1    Level: 1    Role: D/V
 Verificare che siano definiti periodi di conservazione espliciti per tutti i set di dati di addestramento.
 #1.13.2    Level: 2    Role: D/V
 Verificare che i dataset vengano automaticamente scaduti, eliminati o esaminati per la cancellazione alla fine del loro ciclo di vita.
 #1.13.3    Level: 2    Role: D/V
 Verificare che le azioni di conservazione e cancellazione siano registrate e verificabili.

---

### C1.14 Conformità Normativa e Giurisdizionale

Garantire che tutti i dati di addestramento siano conformi alle leggi e alle normative applicabili.

 #1.14.1    Level: 2    Role: D/V
 Verificare che i requisiti di residenza dei dati e di trasferimento transfrontaliero siano identificati e applicati per tutti i set di dati.
 #1.14.2    Level: 2    Role: D/V
 Verificare che le normative specifiche di settore (ad esempio, sanità, finanza) siano identificate e rispettate nella gestione dei dati.
 #1.14.3    Level: 2    Role: D/V
 Verificare che la conformità alle leggi sulla privacy pertinenti (ad es. GDPR, CCPA) sia documentata e revisionata regolarmente.

---

### C1.15 Filigrana e Marcatura dei Dati

Rilevare il riutilizzo non autorizzato o la fuoriuscita di dati proprietari o sensibili.

 #1.15.1    Level: 3    Role: D/V
 Verificare che i dataset o i sottoinsiemi siano contrassegnati con watermark o fingerprint dove possibile.
 #1.15.2    Level: 3    Role: D/V
 Verificare che i metodi di watermarking/fingerprinting non introducano pregiudizi o rischi per la privacy.
 #1.15.3    Level: 3    Role: D/V
 Verificare che vengano effettuati controlli periodici per rilevare l'uso non autorizzato o la perdita di dati con filigrana.

---

### C1.16 Gestione dei Diritti degli Interessati ai Dati

Supportare i diritti del soggetto dei dati come accesso, rettifica, limitazione e opposizione.

 #1.16.1    Level: 2    Role: D/V
 Verificare che esistano meccanismi per rispondere alle richieste dei soggetti interessati di accesso, rettifica, limitazione o opposizione.
 #1.16.2    Level: 2    Role: D/V
 Verificare che le richieste siano registrate, monitorate e soddisfatte entro i termini di legge previsti.
 #1.16.3    Level: 2    Role: D/V
 Verificare che i processi relativi ai diritti degli interessati siano testati e revisionati regolarmente per garantirne l'efficacia.

---

### C1.17 Analisi dell'Impatto della Versione del Dataset

Valutare l'impatto delle modifiche al dataset prima di aggiornare o sostituire le versioni.

 #1.17.1    Level: 2    Role: D/V
 Verificare che venga eseguita un'analisi d'impatto prima di aggiornare o sostituire una versione del dataset, coprendo le prestazioni del modello, l'equità e la conformità.
 #1.17.2    Level: 2    Role: D/V
 Verificare che i risultati dell'analisi d'impatto siano documentati e revisionati dalle parti interessate rilevanti.
 #1.17.3    Level: 2    Role: D/V
 Verificare che esistano piani di rollback nel caso in cui le nuove versioni introducano rischi inaccettabili o regressioni.

---

### C1.18 Sicurezza della forza lavoro per l'annotazione dei dati

Garantire la sicurezza e l'integrità del personale coinvolto nell'annotazione dei dati.

 #1.18.1    Level: 2    Role: D/V
 Verificare che tutto il personale coinvolto nell'annotazione dei dati sia sottoposto a controllo dei precedenti e formato sulla sicurezza e la privacy dei dati.
 #1.18.2    Level: 2    Role: D/V
 Verificare che tutto il personale di annotazione firmi accordi di riservatezza e di non divulgazione.
 #1.18.3    Level: 2    Role: D/V
 Verificare che le piattaforme di annotazione applichino controlli di accesso e monitorino le minacce interne.

---

### Riferimenti

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Validazione dell'input utente C2

### Obiettivo di Controllo

Una validazione robusta dell'input dell'utente è una prima linea di difesa contro alcuni degli attacchi più dannosi ai sistemi di intelligenza artificiale. Gli attacchi di injection dei prompt possono sovrascrivere le istruzioni di sistema, divulgare dati sensibili o indirizzare il modello verso comportamenti non consentiti. A meno che non siano presenti filtri dedicati e gerarchie di istruzioni, la ricerca dimostra che le "multi-shot" jailbreak che sfruttano finestre di contesto molto lunghe saranno efficaci. Inoltre, attacchi sottili di perturbazione adversariale — come scambi di omoglyph o leetspeak — possono silenziosamente alterare le decisioni di un modello.

---

### C2.1 Difesa contro l'Iniezione di Prompt

L'iniezione di prompt è uno dei principali rischi per i sistemi di intelligenza artificiale. Le difese contro questa tattica utilizzano una combinazione di filtri statici basati su pattern, classificatori dinamici e l'applicazione gerarchica delle istruzioni.

 #2.1.1    Level: 1    Role: D/V
 Verificare che gli input degli utenti siano controllati rispetto a una libreria continuamente aggiornata di modelli noti di iniezione di prompt (parole chiave per il jailbreak, “ignora precedente”, catene di gioco di ruolo, attacchi indiretti HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Verificare che il sistema applichi una gerarchia di istruzioni in cui i messaggi del sistema o dello sviluppatore sovrascrivano le istruzioni dell’utente, anche dopo l’espansione della finestra di contesto.
 #2.1.3    Level: 2    Role: D/V
 Verificare che i test di valutazione avversaria (ad esempio, prompt "many-shot" del Red Team) vengano eseguiti prima di ogni rilascio di modello o modello di prompt, con soglie di tasso di successo e blocchi automatici per regressioni.
 #2.1.4    Level: 2    Role: D
 Verificare che i prompt provenienti da contenuti di terze parti (pagine web, PDF, email) vengano sanificati in un contesto di parsing isolato prima di essere concatenati al prompt principale.
 #2.1.5    Level: 3    Role: D/V
 Verificare che tutti gli aggiornamenti delle regole del filtro dei prompt, le versioni dei modelli classificatori e le modifiche alle liste di blocco siano controllati nelle versioni e verificabili.

---

### C2.2 Resistenza agli esempi avversari

I modelli di Elaborazione del Linguaggio Naturale (NLP) sono ancora vulnerabili a sottili perturbazioni a livello di caratteri o parole che gli esseri umani spesso non percepiscono, ma che i modelli tendono a classificare erroneamente.

 #2.2.1    Level: 1    Role: D
 Verificare che le operazioni di normalizzazione input di base (Unicode NFC, mappatura degli omoglifi, rimozione degli spazi bianchi) vengano eseguite prima della tokenizzazione.
 #2.2.2    Level: 2    Role: D/V
 Verificare che il rilevamento di anomalie statistiche segnali input con distanza di modifica insolitamente elevata rispetto alle norme linguistiche, token ripetuti in eccesso o distanze di embedding anomale.
 #2.2.3    Level: 2    Role: D
 Verificare che la pipeline di inferenza supporti varianti opzionali del modello irrobustite con addestramento avversario o strati di difesa (ad esempio, randomizzazione, distillazione difensiva) per endpoint ad alto rischio.
 #2.2.4    Level: 2    Role: V
 Verificare che gli input sospetti di essere avversari siano messi in quarantena, registrati con payload completi (dopo la redazione dei dati personali identificabili - PII).
 #2.2.5    Level: 3    Role: D/V
 Verificare che le metriche di robustezza (tasso di successo delle suite di attacchi conosciuti) siano monitorate nel tempo e che le regressioni attivino un blocco di rilascio.

---

### C2.3 Validazione di Schema, Tipo e Lunghezza

Gli attacchi AI che presentano input malformati o sovradimensionati possono causare errori di parsing, fuoriuscita di prompt tra campi e esaurimento delle risorse. L'applicazione rigorosa dello schema è inoltre un requisito fondamentale durante l'esecuzione di chiamate a strumenti deterministici.

 #2.3.1    Level: 1    Role: D
 Verificare che ogni endpoint di chiamata API o funzione definisca uno schema di input esplicito (JSON Schema, Protobuf o equivalente multimodale) e che gli input vengano convalidati prima dell’assemblaggio del prompt.
 #2.3.2    Level: 1    Role: D/V
 Verificare che gli input che superano il limite massimo di token o byte vengano rifiutati con un errore sicuro e non mai troncati silenziosamente.
 #2.3.3    Level: 2    Role: D/V
 Verificare che i controlli di tipo (ad esempio, intervalli numerici, valori enum, tipi MIME per immagini/audio) siano applicati lato server, non solo nel codice client.
 #2.3.4    Level: 2    Role: D
 Verificare che i validatori semantici (ad esempio, JSON Schema) vengano eseguiti in tempo costante per prevenire attacchi DoS algoritmici.
 #2.3.5    Level: 3    Role: V
 Verificare che i fallimenti di convalida siano registrati con estratti del payload oscurati e codici di errore inequivocabili per facilitare la triage della sicurezza.

---

### C2.4 Controllo dei Contenuti e delle Politiche

Gli sviluppatori dovrebbero essere in grado di rilevare prompt sintatticamente validi che richiedono contenuti non consentiti (come istruzioni illecite, discorsi di odio e testi protetti da copyright) e impedirne la diffusione.

 #2.4.1    Level: 1    Role: D
 Verificare che un classificatore di contenuti (zero shot o fine-tuned) valuti ogni input per violenza, autolesionismo, odio, contenuti sessuali e richieste illegali, con soglie configurabili.
 #2.4.2    Level: 1    Role: D/V
 Verificare che gli input che violano le politiche ricevano rifiuti standardizzati o completamenti sicuri in modo che non si propaghino alle chiamate LLM successive.
 #2.4.3    Level: 2    Role: D
 Verificare che il modello di screening o l'insieme di regole venga riaddestrato/aggiornato almeno trimestralmente, incorporando i nuovi schemi di jailbreak o di elusione delle policy osservati.
 #2.4.4    Level: 2    Role: D
 Verificare che lo screening rispetti le politiche specifiche dell'utente (età, vincoli legali regionali) tramite regole basate su attributi risolte al momento della richiesta.
 #2.4.5    Level: 3    Role: V
 Verificare che i registri di screening includano i punteggi di confidenza del classificatore e i tag della categoria di politica per la correlazione SOC e la riproduzione futura del red-team.

---

### C2.5 Limitazione della velocità di input e prevenzione degli abusi

Gli sviluppatori dovrebbero prevenire abusi, esaurimento delle risorse e attacchi automatizzati contro i sistemi di intelligenza artificiale limitando i tassi di input e rilevando modelli di utilizzo anomali.

 #2.5.1    Level: 1    Role: D/V
 Verifica che i limiti di velocità per utente, per indirizzo IP e per chiave API siano applicati per tutti i punti di accesso in ingresso.
 #2.5.2    Level: 2    Role: D/V
 Verificare che i limiti di velocità a raffica e sostenuti siano configurati per prevenire attacchi DoS e di forza bruta.
 #2.5.3    Level: 2    Role: D/V
 Verificare che i modelli di utilizzo anomali (ad esempio, richieste rapid-fire, inondazione di input) attivino blocchi automatici o escalation.
 #2.5.4    Level: 3    Role: V
 Verificare che i registri di prevenzione degli abusi siano conservati e revisionati per individuare schemi di attacco emergenti.

---

### C2.6 Validazione di Input Multi-Modalità

I sistemi di intelligenza artificiale dovrebbero includere una convalida robusta per input non testuali (immagini, audio, file) per prevenire iniezioni, elusioni o abuso di risorse.

 #2.6.1    Level: 1    Role: D
 Verificare che tutti gli input non testuali (immagini, audio, file) siano validati per tipo, dimensione e formato prima dell'elaborazione.
 #2.6.2    Level: 2    Role: D/V
 Verificare che i file vengano scansionati per malware e payload steganografici prima dell'ingestione.
 #2.6.3    Level: 2    Role: D/V
 Verificare che gli input di immagini/audio siano controllati per perturbazioni avversarie o schemi di attacco noti.
 #2.6.4    Level: 3    Role: V
 Verificare che i fallimenti della validazione degli input multimodali siano registrati e attivino allarmi per l'indagine.

---

### C2.7 Provenienza e attribuzione degli input

I sistemi di intelligenza artificiale dovrebbero supportare l'auditing, il monitoraggio degli abusi e la conformità attraverso il monitoraggio e l'etichettatura delle origini di tutti gli input degli utenti.

 #2.7.1    Level: 1    Role: D/V
 Verificare che tutti gli input degli utenti siano taggati con metadata (ID utente, sessione, fonte, timestamp, indirizzo IP) al momento dell'ingestione.
 #2.7.2    Level: 2    Role: D/V
 Verificare che i metadati di provenienza siano mantenuti e verificabili per tutti gli input elaborati.
 #2.7.3    Level: 2    Role: D/V
 Verificare che le fonti di input anomale o non affidabili siano segnalate e soggette a un controllo rafforzato o al blocco.

---

### C2.8 Rilevamento delle minacce adattivo in tempo reale

Gli sviluppatori dovrebbero utilizzare sistemi avanzati di rilevamento delle minacce per l'IA che si adattino a nuovi modelli di attacco e forniscano protezione in tempo reale tramite il matching di pattern compilati.

 #2.8.1    Level: 1    Role: D/V
 Verificare che i modelli di rilevamento delle minacce vengano compilati in motori regex ottimizzati per un filtraggio in tempo reale ad alte prestazioni con un impatto minimo sulla latenza.
 #2.8.2    Level: 1    Role: D/V
 Verificare che i sistemi di rilevamento delle minacce mantengano librerie di modelli separate per diverse categorie di minacce (iniezione di prompt, contenuti dannosi, dati sensibili, comandi di sistema).
 #2.8.3    Level: 2    Role: D/V
 Verificare che il rilevamento delle minacce adattivo includa modelli di machine learning che aggiornano la sensibilità alle minacce in base alla frequenza degli attacchi e ai tassi di successo.
 #2.8.4    Level: 2    Role: D/V
 Verificare che i feed di intelligence sulle minacce in tempo reale aggiornino automaticamente le librerie di pattern con nuove firme di attacco e IOC (Indicatori di Compromissione).
 #2.8.5    Level: 3    Role: D/V
 Verificare che i tassi di falsi positivi nella rilevazione delle minacce siano monitorati continuamente e che la specificità dei modelli sia automaticamente regolata per minimizzare l'interferenza con i casi d'uso legittimi.
 #2.8.6    Level: 3    Role: D/V
 Verifica che l'analisi delle minacce contestuale consideri la fonte dell'input, i modelli di comportamento dell'utente e la cronologia della sessione per migliorare la precisione della rilevazione.
 #2.8.7    Level: 3    Role: D/V
 Verificare che le metriche di prestazione del rilevamento delle minacce (tasso di rilevamento, latenza di elaborazione, utilizzo delle risorse) siano monitorate e ottimizzate in tempo reale.

---

### C2.9 Pipeline di Validazione della Sicurezza Multi-Modale

Gli sviluppatori dovrebbero fornire una validazione di sicurezza per testo, immagini, audio e altre modalità di input AI con tipi specifici di rilevamento delle minacce e isolamento delle risorse.

 #2.9.1    Level: 1    Role: D/V
 Verificare che ogni modalità di input abbia validatori di sicurezza dedicati con modelli di minaccia documentati (testo: iniezione di prompt, immagini: steganografia, audio: attacchi spettrogramma) e soglie di rilevamento.
 #2.9.2    Level: 2    Role: D/V
 Verificare che gli input multi-modali siano elaborati in sandbox isolate con limiti di risorse definiti (memoria, CPU, tempo di elaborazione) specifici per ogni tipo di modalità e documentati nelle politiche di sicurezza.
 #2.9.3    Level: 2    Role: D/V
 Verificare che il rilevamento degli attacchi cross-modali identifichi attacchi coordinati che coinvolgono molteplici tipologie di input (ad esempio, payload steganografici nelle immagini combinati con iniezione di prompt nel testo) tramite regole di correlazione e generazione di allarmi.
 #2.9.4    Level: 3    Role: D/V
 Verificare che i fallimenti di validazione multimodale attivino una registrazione dettagliata che includa tutte le modalità di input, i risultati della validazione, i punteggi di minaccia e l'analisi di correlazione con formati di registro strutturati per l'integrazione SIEM.
 #2.9.5    Level: 3    Role: D/V
 Verificare che i classificatori di contenuti specifici per modalità siano aggiornati secondo i calendari documentati (almeno trimestralmente) con nuovi schemi di minacce, esempi avversari e benchmark di prestazioni mantenuti al di sopra delle soglie di base.

---

### Riferimenti

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Gestione del Ciclo di Vita del Modello C3 e Controllo delle Modifiche

### Obiettivo di Controllo

I sistemi di intelligenza artificiale devono implementare processi di controllo delle modifiche che impediscano modifiche non autorizzate o non sicure del modello di raggiungere la produzione. Questo controllo garantisce l'integrità del modello durante l'intero ciclo di vita, dallo sviluppo al dispiegamento fino alla dismissione, permettendo una rapida risposta agli incidenti e mantenendo la responsabilità per tutte le modifiche.

Obiettivo principale di sicurezza: solo modelli autorizzati e validati raggiungono la produzione attraverso processi controllati che mantengono integrità, tracciabilità e recuperabilità.

---

### C3.1 Autorizzazione e Integrità del Modello

Solo i modelli autorizzati con integrità verificata raggiungono gli ambienti di produzione.

 #3.1.1    Level: 1    Role: D/V
 Verificare che tutti gli artefatti del modello (pesi, configurazioni, tokenizer) siano firmati crittograficamente da entità autorizzate prima del deployment.
 #3.1.2    Level: 1    Role: D/V
 Verificare che l'integrità del modello venga convalidata al momento del deployment e che i fallimenti della verifica della firma impediscano il caricamento del modello.
 #3.1.3    Level: 2    Role: D/V
 Verificare che i record di provenienza del modello includano l'identità dell'entità autorizzante, i checksum dei dati di addestramento, i risultati del test di validazione con stato di superamento/fallimento e un timestamp di creazione.
 #3.1.4    Level: 2    Role: D/V
 Verificare che tutti gli artefatti del modello utilizzino la versionatura semantica (MAJOR.MINOR.PATCH) con criteri documentati che specificano quando incrementare ciascuna componente della versione.
 #3.1.5    Level: 2    Role: V
 Verificare che il tracciamento delle dipendenze mantenga un inventario in tempo reale che consenta un'identificazione rapida di tutti i sistemi che utilizzano tali dipendenze.

---

### C3.2 Validazione e Test del Modello

I modelli devono superare le validazioni di sicurezza e protezione definite prima della distribuzione.

 #3.2.1    Level: 1    Role: D/V
 Verificare che i modelli siano sottoposti a test di sicurezza automatizzati che includano la convalida degli input, la sanitizzazione degli output e le valutazioni di sicurezza con soglie di superamento/prestazione concordate preventivamente dall'organizzazione prima della distribuzione.
 #3.2.2    Level: 1    Role: D/V
 Verificare che i fallimenti di validazione blocchino automaticamente il deployment del modello dopo l'approvazione esplicita da parte del personale autorizzato pre-designato, con giustificazioni aziendali documentate.
 #3.2.3    Level: 2    Role: V
 Verificare che i risultati del test siano firmati crittograficamente e collegati in modo immutabile all'hash della specifica versione del modello che si sta validando.
 #3.2.4    Level: 2    Role: D/V
 Verificare che le distribuzioni d'emergenza richiedano una valutazione documentata del rischio di sicurezza e l'approvazione da parte di un'autorità di sicurezza predesignata entro i tempi prefissati.

---

### C3.3 Distribuzione Controllata e Ripristino

Le implementazioni dei modelli devono essere controllate, monitorate e reversibili.

 #3.3.1    Level: 1    Role: D
 Verificare che le distribuzioni in produzione implementino meccanismi di rollout graduale (distribuzioni canary, distribuzioni blue-green) con trigger automatici di rollback basati su tassi di errore, soglie di latenza o criteri di allerta di sicurezza predefiniti.
 #3.3.2    Level: 1    Role: D/V
 Verificare che le capacità di rollback ripristinino lo stato completo del modello (pesi, configurazioni, dipendenze) in modo atomico all'interno delle finestre temporali predefinite dall'organizzazione.
 #3.3.3    Level: 2    Role: D/V
 Verificare che i processi di distribuzione convalidino le firme crittografiche e calcolino somme di controllo per l'integrità prima dell'attivazione del modello, bloccando la distribuzione in caso di qualsiasi discrepanza.
 #3.3.4    Level: 2    Role: D/V
 Verificare che le capacità di spegnimento di emergenza del modello possano disabilitare gli endpoint del modello entro tempi di risposta predefiniti tramite interruttori automatici di circuito o interruttori di spegnimento manuali.
 #3.3.5    Level: 2    Role: V
 Verificare che gli artefatti di rollback (versioni precedenti del modello, configurazioni, dipendenze) siano conservati secondo le politiche organizzative con archiviazione immutabile per la risposta agli incidenti.

---

### C3.4 Responsabilità delle Modifiche e Audit

Tutte le modifiche del ciclo di vita del modello devono essere tracciabili e verificabili.

 #3.4.1    Level: 1    Role: V
 Verificare che tutte le modifiche al modello (deploy, configurazione, disattivazione) generino registrazioni di audit immutabili che includano un timestamp, un'identità dell'attore autenticata, un tipo di modifica e gli stati precedente e successivo.
 #3.4.2    Level: 2    Role: D/V
 Verificare che l'accesso al registro di audit richieda un'autorizzazione appropriata e che tutti i tentativi di accesso siano registrati con l'identità dell'utente e un timestamp.
 #3.4.3    Level: 2    Role: D/V
 Verificare che i modelli di prompt e i messaggi di sistema siano controllati nella versione tramite repository git con revisione del codice obbligatoria e approvazione da parte di revisori designati prima del rilascio.
 #3.4.4    Level: 2    Role: V
 Verificare che i registri di controllo includano dettagli sufficienti (hash del modello, snapshot delle configurazioni, versioni delle dipendenze) per consentire la completa ricostruzione dello stato del modello per qualsiasi momento all'interno del periodo di conservazione.

---

### C3.5 Pratiche di Sviluppo Sicuro

I processi di sviluppo e addestramento del modello devono seguire pratiche sicure per prevenire compromissioni.

 #3.5.1    Level: 1    Role: D
 Verificare che gli ambienti di sviluppo, test e produzione del modello siano separati fisicamente o logicamente. Non devono condividere infrastrutture, devono avere controlli di accesso distinti e archivi dati isolati.
 #3.5.2    Level: 1    Role: D
 Verificare che l'addestramento del modello e il fine-tuning avvengano in ambienti isolati con accesso di rete controllato.
 #3.5.3    Level: 1    Role: D/V
 Verificare che le fonti dei dati di addestramento siano validate tramite controlli di integrità e autenticate attraverso fonti fidate con una catena di custodia documentata prima dell'uso nello sviluppo del modello.
 #3.5.4    Level: 2    Role: D
 Verificare che gli artefatti di sviluppo del modello (iperparametri, script di addestramento, file di configurazione) siano archiviati nel controllo delle versioni e richiedano l'approvazione di una revisione tra pari prima di essere utilizzati nell'addestramento.

---

### C3.6 Ritiro e dismissione del modello

I modelli devono essere ritirati in modo sicuro quando non sono più necessari o quando vengono identificati problemi di sicurezza.

 #3.6.1    Level: 1    Role: D
 Verificare che i processi di ritiro del modello scansionino automaticamente i grafici di dipendenza, identifichino tutti i sistemi consumatori e forniscano periodi di preavviso concordati prima della dismissione.
 #3.6.2    Level: 1    Role: D/V
 Verificare che i modelli ritirati siano cancellati in modo sicuro utilizzando l'eliminazione crittografica o la sovrascrittura multipla secondo le politiche di conservazione dei dati documentate, con certificati di distruzione verificati.
 #3.6.3    Level: 2    Role: V
 Verificare che gli eventi di dismissione del modello siano registrati con timestamp e identità dell'attore, e che le firme del modello vengano revocate per prevenire il riutilizzo.
 #3.6.4    Level: 2    Role: D/V
 Verificare che il ritiro d'emergenza del modello possa disabilitare l'accesso al modello entro i tempi di risposta di emergenza predefiniti tramite interruttori di spegnimento automatici in caso di rilevamento di vulnerabilità di sicurezza critiche.

---

### Riferimenti

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Sicurezza dell'Infrastruttura C4, della Configurazione e del Deployment

### Obiettivo di Controllo

L'infrastruttura di intelligenza artificiale deve essere rafforzata contro l'escalation di privilegi, la manomissione della catena di fornitura e i movimenti laterali mediante configurazioni sicure, isolamento in fase di esecuzione, pipeline di distribuzione affidabili e monitoraggio completo. Solo componenti e configurazioni dell'infrastruttura autorizzati e verificati raggiungono la produzione attraverso processi controllati che mantengono sicurezza, integrità e tracciabilità.

Obiettivo principale di sicurezza: Solo i componenti infrastrutturali firmati crittograficamente e sottoposti a scansione per vulnerabilità raggiungono la produzione attraverso pipeline di validazione automatizzate che applicano le politiche di sicurezza e mantengono registri di audit immutabili.

---

### C4.1 Isolamento dell'Ambiente di Esecuzione

Prevenire l'evasione dei container e l'escalation dei privilegi attraverso primitive di isolamento a livello kernel e controlli di accesso obbligatori.

 #4.1.1    Level: 1    Role: D/V
 Verificare che tutti i container AI rimuovano TUTTE le capacità Linux tranne CAP_SETUID, CAP_SETGID e le capacità esplicitamente richieste e documentate nelle baseline di sicurezza.
 #4.1.2    Level: 1    Role: D/V
 Verificare che i profili seccomp blocchino tutte le syscall tranne quelle presenti nelle liste di consenso pre-approvate, con violazioni che terminano il container e generano avvisi di sicurezza.
 #4.1.3    Level: 2    Role: D/V
 Verificare che i carichi di lavoro AI vengano eseguiti con filesystem root in sola lettura, tmpfs per i dati temporanei e volumi nominati per i dati persistenti con opzioni di mount noexec applicate.
 #4.1.4    Level: 2    Role: D/V
 Verificare che il monitoraggio runtime basato su eBPF (Falco, Tetragon o equivalente) rilevi i tentativi di escalation dei privilegi e termini automaticamente i processi colpevoli entro i requisiti di tempo di risposta organizzativi.
 #4.1.5    Level: 3    Role: D/V
 Verificare che i carichi di lavoro AI ad alto rischio vengano eseguiti in ambienti isolati a livello hardware (Intel TXT, AMD SVM o nodi bare-metal dedicati) con verifica di attestazione.

---

### C4.2 Pipeline di Build e Distribuzione Sicure

Garantire l'integrità crittografica e la sicurezza della catena di approvvigionamento attraverso build riproducibili e artefatti firmati.

 #4.2.1    Level: 1    Role: D/V
 Verificare che l'infrastruttura come codice venga esaminata con strumenti (tfsec, Checkov o Terrascan) ad ogni commit, bloccando le fusioni in presenza di risultati con criticità CRITICA o ALTA.
 #4.2.2    Level: 1    Role: D/V
 Verificare che le build dei container siano riproducibili con hash SHA256 identici in tutte le build e generare attestazioni di provenienza SLSA Livello 3 firmate con Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verificare che le immagini dei container incorporino SBOM CycloneDX o SPDX e siano firmate con Cosign prima del push nel registry, con il rifiuto delle immagini non firmate durante il deployment.
 #4.2.4    Level: 2    Role: D/V
 Verificare che le pipeline CI/CD utilizzino token OIDC da HashiCorp Vault, ruoli IAM di AWS o Identità Gestita di Azure con durate che non superino i limiti stabiliti dalla politica di sicurezza aziendale.
 #4.2.5    Level: 2    Role: D/V
 Verificare che le firme Cosign e la provenienza SLSA siano convalidate durante il processo di distribuzione prima dell'esecuzione del container e che eventuali errori di verifica causino il fallimento della distribuzione.
 #4.2.6    Level: 2    Role: D/V
 Verificare che gli ambienti di build vengano eseguiti in container o macchine virtuali effimeri senza memoria persistente e con isolamento di rete dalle VPC di produzione.

---

### C4.3 Sicurezza di Rete e Controllo degli Accessi

Implementare una rete a fiducia zero con politiche di negazione predefinite e comunicazioni crittografate.

 #4.3.1    Level: 1    Role: D/V
 Verificare che le NetworkPolicy di Kubernetes o qualsiasi equivalente implementino un blocco predefinito (default-deny) per ingressi/uscite con regole di autorizzazione esplicite per le porte richieste (443, 8080, ecc.).
 #4.3.2    Level: 1    Role: D/V
 Verificare che SSH (porta 22), RDP (porta 3389) e gli endpoint dei metadata cloud (169.254.169.254) siano bloccati o richiedano l'autenticazione basata su certificato.
 #4.3.3    Level: 2    Role: D/V
 Verificare che il traffico in uscita sia filtrato tramite proxy HTTP/HTTPS (Squid, Istio o gateway NAT cloud) con liste di domini consentiti e che le richieste bloccate vengano registrate.
 #4.3.4    Level: 2    Role: D/V
 Verificare che la comunicazione inter-servizi utilizzi mutual TLS con certificati ruotati secondo la politica organizzativa e con la validazione dei certificati applicata (senza flag di skip-verify).
 #4.3.5    Level: 2    Role: D/V
 Verificare che l'infrastruttura di intelligenza artificiale operi in VPC/VNet dedicate senza accesso diretto a Internet e che comunichi esclusivamente tramite gateway NAT o host bastion.

---

### C4.4 Gestione dei Segreti e delle Chiavi Crittografiche

Proteggi le credenziali tramite archiviazione supportata da hardware e rotazione automatizzata con accesso a zero-trust.

 #4.4.1    Level: 1    Role: D/V
 Verificare che i segreti siano memorizzati in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault o Google Secret Manager con crittografia a riposo utilizzando AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verificare che le chiavi crittografiche siano generate in HSM conformi a FIPS 140-2 Livello 2 (AWS CloudHSM, Azure Dedicated HSM) con rotazione delle chiavi secondo la politica crittografica organizzativa.
 #4.4.3    Level: 2    Role: D/V
 Verificare che la rotazione dei segreti sia automatizzata con deployment zero-downtime e rotazione immediata attivata da cambiamenti del personale o incidenti di sicurezza.
 #4.4.4    Level: 2    Role: D/V
 Verificare che le immagini dei container siano scansionate con strumenti (GitLeaks, TruffleHog o detect-secrets) che bloccano le build contenenti chiavi API, password o certificati.
 #4.4.5    Level: 2    Role: D/V
 Verificare che l'accesso segreto alla produzione richieda l'autenticazione multifattoriale (MFA) con token hardware (YubiKey, FIDO2) e sia registrato tramite log di audit immutabili con identità degli utenti e timestamp.
 #4.4.6    Level: 2    Role: D/V
 Verificare che i segreti vengano inseriti tramite i segreti di Kubernetes, volumi montati o container di inizializzazione e garantire che i segreti non siano mai incorporati nelle variabili d'ambiente o nelle immagini.

---

### C4.5 Isolamento e Validazione del Carico di Lavoro AI

Isolare i modelli di intelligenza artificiale non affidabili in sandbox sicuri con un'analisi comportamentale completa.

 #4.5.1    Level: 1    Role: D/V
 Verificare che i modelli di intelligenza artificiale esterni vengano eseguiti in gVisor, microVM (come Firecracker, CrossVM) o container Docker con le opzioni --security-opt=no-new-privileges e --read-only.
 #4.5.2    Level: 1    Role: D/V
 Verificare che gli ambienti sandbox non abbiano connettività di rete (--network=none) o abbiano solo accesso localhost con tutte le richieste esterne bloccate dalle regole iptables.
 #4.5.3    Level: 2    Role: D/V
 Verificare che la convalida del modello di IA includa test automatizzati di tipo red-team con una copertura di test definita dall'organizzazione e un'analisi comportamentale per il rilevamento di backdoor.
 #4.5.4    Level: 2    Role: D/V
 Verificare che, prima che un modello AI venga promosso in produzione, i risultati ottenuti nella sandbox siano firmati crittograficamente dal personale di sicurezza autorizzato e archiviati in log di controllo immutabili.
 #4.5.5    Level: 2    Role: D/V
 Verificare che gli ambienti sandbox vengano distrutti e ricreati da immagini golden tra le valutazioni, con una completa pulizia del filesystem e della memoria.

---

### C4.6 Monitoraggio della Sicurezza dell'Infrastruttura

Scansionare e monitorare continuamente l'infrastruttura con rimedio automatizzato e allerta in tempo reale.

 #4.6.1    Level: 1    Role: D/V
 Verificare che le immagini dei container siano sottoposte a scansione secondo i programmi organizzativi, con le vulnerabilità CRITICHE che bloccano il deployment in base alle soglie di rischio organizzativo.
 #4.6.2    Level: 1    Role: D/V
 Verificare che l'infrastruttura rispetti i CIS Benchmarks o i controlli NIST 800-53 con soglie di conformità definite dall'organizzazione e la correzione automatizzata per verifiche non superate.
 #4.6.3    Level: 2    Role: D/V
 Verificare che le vulnerabilità di gravità ALTA siano corrette secondo le tempistiche di gestione del rischio dell'organizzazione, con procedure di emergenza per le CVE attivamente sfruttate.
 #4.6.4    Level: 2    Role: V
 Verificare che gli avvisi di sicurezza si integrino con le piattaforme SIEM (Splunk, Elastic o Sentinel) utilizzando i formati CEF o STIX/TAXII con arricchimento automatizzato.
 #4.6.5    Level: 3    Role: V
 Verificare che le metriche dell'infrastruttura vengano esportate ai sistemi di monitoraggio (Prometheus, DataDog) con dashboard SLA e reportistica esecutiva.
 #4.6.6    Level: 2    Role: D/V
 Verificare che la deriva di configurazione venga rilevata utilizzando strumenti (Chef InSpec, AWS Config) in conformità con i requisiti di monitoraggio organizzativi, con rollback automatico per le modifiche non autorizzate.

---

### Gestione delle risorse dell'infrastruttura AI C4.7

Prevenire attacchi di esaurimento delle risorse e garantire una distribuzione equa delle risorse attraverso quote e monitoraggio.

 #4.7.1    Level: 1    Role: D/V
 Verificare che l'utilizzo di GPU/TPU sia monitorato con avvisi attivati a soglie definite dall'organizzazione e che la scalabilità automatica o il bilanciamento del carico vengano attivati in base alle politiche di gestione della capacità.
 #4.7.2    Level: 1    Role: D/V
 Verificare che le metriche del carico di lavoro AI (latenza di inferenza, throughput, tassi di errore) siano raccolte secondo i requisiti di monitoraggio organizzativi e correlate con l'utilizzo dell'infrastruttura.
 #4.7.3    Level: 2    Role: D/V
 Verificare che Kubernetes ResourceQuotas o equivalenti limitino i singoli carichi di lavoro secondo le politiche di allocazione delle risorse aziendali con limiti rigidi applicati.
 #4.7.4    Level: 2    Role: V
 Verificare che il monitoraggio dei costi tracci la spesa per carico di lavoro/inquilino con avvisi basati sulle soglie di budget organizzativo e controlli automatizzati per i superamenti di budget.
 #4.7.5    Level: 3    Role: V
 Verificare che la pianificazione della capacità utilizzi dati storici con periodi di previsione definiti dall'organizzazione e l'approvvigionamento automatico delle risorse basato sui modelli di domanda.
 #4.7.6    Level: 2    Role: D/V
 Verificare che l'esaurimento delle risorse attivi gli interruttori a circuito secondo i requisiti di risposta organizzativi, inclusi il controllo della velocità basato sulle politiche di capacità e l'isolamento del carico di lavoro.

---

### C4.8 Controlli per la Separazione e la Promozione degli Ambienti

Applicare rigidi confini ambientali con cancelli di promozione automatizzati e convalida della sicurezza.

 #4.8.1    Level: 1    Role: D/V
 Verificare che gli ambienti di sviluppo/test/produzione funzionino in VPC/VNet separate senza ruoli IAM, gruppi di sicurezza o connettività di rete condivisi.
 #4.8.2    Level: 1    Role: D/V
 Verificare che la promozione dell'ambiente richieda l'approvazione da parte del personale autorizzato definito dall'organizzazione, con firme crittografiche e registri di controllo immutabili.
 #4.8.3    Level: 2    Role: D/V
 Verificare che gli ambienti di produzione blocchino l'accesso SSH, disabilitino gli endpoint di debug e richiedano richieste di modifica con preavviso organizzativo, tranne in caso di emergenze.
 #4.8.4    Level: 2    Role: D/V
 Verificare che le modifiche all'infrastruttura come codice richiedano una revisione tra pari con test automatizzati e scansione di sicurezza prima della fusione nel ramo principale.
 #4.8.5    Level: 2    Role: D/V
 Verificare che i dati non di produzione siano anonimizzati secondo i requisiti di riservatezza organizzativa, mediante generazione di dati sintetici o mascheramento completo dei dati con rimozione delle informazioni personali identificabili (PII).
 #4.8.6    Level: 2    Role: D/V
 Verificare che le soglie di promozione includano test di sicurezza automatizzati (SAST, DAST, scansione dei container) con zero risultati CRITICI richiesti per l'approvazione.

---

### C4.9 Backup e Ripristino dell'Infrastruttura

Garantire la resilienza dell'infrastruttura attraverso backup automatizzati, procedure di recupero testate e capacità di disaster recovery.

 #4.9.1    Level: 1    Role: D/V
 Verificare che le configurazioni dell'infrastruttura siano sottoposte a backup secondo i programmi di backup organizzativi, con destinazione in regioni geograficamente separate, implementando la strategia di backup 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Verificare che i sistemi di backup funzionino in reti isolate con credenziali separate e storage isolato (air-gapped) per la protezione contro i ransomware.
 #4.9.3    Level: 2    Role: V
 Verificare che le procedure di recupero siano testate e validate attraverso test automatizzati secondo i programmi organizzativi, con obiettivi RTO e RPO conformi ai requisiti dell'organizzazione.
 #4.9.4    Level: 3    Role: V
 Verificare che il disaster recovery includa runbook specifici per l'IA con il ripristino dei pesi del modello, la ricostruzione del cluster GPU e la mappatura delle dipendenze di servizio.

---

### C4.10 Conformità e Governance delle Infrastrutture

Mantenere la conformità normativa attraverso la valutazione continua, la documentazione e i controlli automatizzati.

 #4.10.1    Level: 2    Role: D/V
 Verificare che la conformità dell'infrastruttura sia valutata in base ai programmi organizzativi rispetto ai controlli SOC 2, ISO 27001 o FedRAMP con raccolta automatizzata delle prove.
 #4.10.2    Level: 2    Role: V
 Verificare che la documentazione dell'infrastruttura includa diagrammi di rete, mappe di flusso dei dati e modelli di minacce aggiornati secondo i requisiti di gestione del cambiamento organizzativo.
 #4.10.3    Level: 3    Role: D/V
 Verificare che le modifiche all'infrastruttura siano soggette a una valutazione automatizzata dell'impatto sulla conformità con flussi di lavoro di approvazione normativa per modifiche ad alto rischio.

---

### C4.11 Sicurezza dell'Hardware per l'IA

Componenti hardware specifici per l'IA sicuri, inclusi GPU, TPU e acceleratori AI specializzati.

 #4.11.1    Level: 2    Role: D/V
 Verificare che il firmware dell'acceleratore AI (BIOS GPU, firmware TPU) sia verificato con firme crittografiche e aggiornato secondo le tempistiche di gestione delle patch dell'organizzazione.
 #4.11.2    Level: 2    Role: D/V
 Verificare che prima dell'esecuzione del carico di lavoro, l'integrità dell'acceleratore AI venga convalidata tramite attestazione hardware utilizzando TPM 2.0, Intel TXT o AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Verificare che la memoria GPU sia isolata tra i carichi di lavoro utilizzando SR-IOV, MIG (GPU Multi-Instance) o una partizione hardware equivalente con sanificazione della memoria tra i lavori.
 #4.11.4    Level: 3    Role: V
 Verificare che la catena di approvvigionamento dell'hardware AI includa la verifica della provenienza con certificati del produttore e la validazione dell'imballaggio a prova di manomissione.
 #4.11.5    Level: 3    Role: D/V
 Verificare che i moduli di sicurezza hardware (HSM) proteggano i pesi dei modelli AI e le chiavi crittografiche con certificazione FIPS 140-2 Livello 3 o Common Criteria EAL4+.

---

### C4.12 Infrastruttura AI Edge e Distribuita

Distribuzioni sicure di AI distribuita, inclusi edge computing, apprendimento federato e architetture multi-sito.

 #4.12.1    Level: 2    Role: D/V
 Verificare che i dispositivi edge AI si autentichino all'infrastruttura centrale utilizzando TLS mutuo con certificati dei dispositivi ruotati secondo la politica di gestione dei certificati dell'organizzazione.
 #4.12.2    Level: 2    Role: D/V
 Verificare che i dispositivi edge implementino il boot sicuro con firme verificate e protezione contro il rollback per prevenire attacchi di downgrade del firmware.
 #4.12.3    Level: 3    Role: D/V
 Verificare che il coordinamento dell'IA distribuita utilizzi algoritmi di consenso tolleranti ai guasti bizantini con validazione dei partecipanti e rilevamento di nodi maligni.
 #4.12.4    Level: 3    Role: D/V
 Verificare che la comunicazione edge-to-cloud includa limitazione della larghezza di banda, compressione dei dati e capacità di funzionamento offline con archiviazione locale sicura.

---

### C4.13 Sicurezza dell'Infrastruttura Multi-Cloud e Ibrida

Proteggi i carichi di lavoro AI su più fornitori di cloud e distribuzioni ibride cloud-on-premises.

 #4.13.1    Level: 2    Role: D/V
 Verificare che le distribuzioni di AI multi-cloud utilizzino la federazione di identità cloud-agnostica (OIDC, SAML) con gestione centralizzata delle politiche tra i fornitori.
 #4.13.2    Level: 2    Role: D/V
 Verificare che il trasferimento dei dati tra cloud utilizzi la crittografia end-to-end con chiavi gestite dal cliente e che i controlli sulla residenza dei dati siano applicati in base alla giurisdizione.
 #4.13.3    Level: 2    Role: D/V
 Verificare che i carichi di lavoro AI in cloud ibrido implementino politiche di sicurezza coerenti tra ambienti on-premise e cloud con monitoraggio e allerta unificati.
 #4.13.4    Level: 3    Role: V
 Verificare che la prevenzione del lock-in del fornitore cloud includa infrastruttura-as-code portabile, API standardizzate e funzionalità di esportazione dati con strumenti di conversione di formato.
 #4.13.5    Level: 3    Role: V
 Verificare che l'ottimizzazione dei costi multi-cloud includa controlli di sicurezza che prevengano la proliferazione incontrollata delle risorse e addebiti non autorizzati per il trasferimento di dati tra cloud diversi.

---

### C4.14 Automazione dell'Infrastruttura e Sicurezza GitOps

Pipeline di automazione dell'infrastruttura sicura e flussi di lavoro GitOps per la gestione dell'infrastruttura AI.

 #4.14.1    Level: 2    Role: D/V
 Verificare che i repository GitOps richiedano commit firmati con chiavi GPG e regole di protezione dei branch che impediscano push diretti ai branch principali.
 #4.14.2    Level: 2    Role: D/V
 Verifica che l'automazione dell'infrastruttura includa il rilevamento delle deviazioni con capacità di rimedio automatico e rollback attivate in base ai requisiti di risposta organizzativa per modifiche non autorizzate.
 #4.14.3    Level: 2    Role: D/V
 Verificare che il provisioning automatizzato dell'infrastruttura includa la convalida delle politiche di sicurezza con blocco del deployment per configurazioni non conformi.
 #4.14.4    Level: 2    Role: D/V
 Verificare che i segreti per l'automazione dell'infrastruttura siano gestiti tramite operatori esterni per i segreti (External Secrets Operator, Bank-Vaults) con rotazione automatica.
 #4.14.5    Level: 3    Role: V
 Verificare che l'infrastruttura auto-riparante includa la correlazione degli eventi di sicurezza con la risposta automatizzata agli incidenti e i flussi di lavoro per la notifica ai portatori di interesse.

---

### C4.15 Sicurezza dell'Infrastruttura Resistente ai Quantum

Prepara l'infrastruttura AI per le minacce del calcolo quantistico attraverso la crittografia post-quantistica e i protocolli quantum-safe.

 #4.15.1    Level: 3    Role: D/V
 Verificare che l'infrastruttura AI implementi algoritmi crittografici post-quantistici approvati dal NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) per lo scambio di chiavi e le firme digitali.
 #4.15.2    Level: 3    Role: D/V
 Verificare che i sistemi di distribuzione delle chiavi quantistiche (QKD) siano implementati per comunicazioni AI ad alta sicurezza con protocolli di gestione delle chiavi sicuri contro attacchi quantistici.
 #4.15.3    Level: 3    Role: D/V
 Verificare che i framework per l'agilità crittografica consentano una migrazione rapida verso nuovi algoritmi post-quantum con rotazione automatica di certificati e chiavi.
 #4.15.4    Level: 3    Role: V
 Verificare che la modellazione delle minacce quantistiche valuti la vulnerabilità dell'infrastruttura AI agli attacchi quantistici con cronoprogrammi di migrazione documentati e valutazioni del rischio.
 #4.15.5    Level: 3    Role: D/V
 Verificare che i sistemi crittografici ibridi classico-quantistici offrano una difesa stratificata durante il periodo di transizione quantistica, con monitoraggio delle prestazioni.

---

### C4.16 Computing Confidenziale e Enclave Sicure

Proteggi i carichi di lavoro AI e i pesi dei modelli utilizzando ambienti di esecuzione affidabili basati su hardware e tecnologie di computing confidenziale.

 #4.16.1    Level: 3    Role: D/V
 Verificare che i modelli AI sensibili vengano eseguiti all'interno degli enclave Intel SGX, AMD SEV-SNP o ARM TrustZone con memoria crittografata e verifica dell'attestazione.
 #4.16.2    Level: 3    Role: D/V
 Verificare che i container riservati (Kata Containers, gVisor con computing riservato) isolino i carichi di lavoro AI con crittografia della memoria applicata dall'hardware.
 #4.16.3    Level: 3    Role: D/V
 Verificare che l'attestazione remota convalidi l'integrità dell'enclave prima di caricare i modelli di intelligenza artificiale tramite una prova crittografica dell'autenticità dell'ambiente di esecuzione.
 #4.16.4    Level: 3    Role: D/V
 Verificare che i servizi di inferenza AI riservati prevengano l’estrazione del modello tramite computazione crittografata con pesi del modello sigillati e esecuzione protetta.
 #4.16.5    Level: 3    Role: D/V
 Verificare che l'orchestrazione dell'ambiente di esecuzione affidabile gestisca il ciclo di vita dell'enclave sicura con attestazione remota e canali di comunicazione criptati.
 #4.16.6    Level: 3    Role: D/V
 Verificare che il calcolo multi-parte sicuro (SMPC) consenta l'addestramento collaborativo dell'IA senza esporre set di dati individuali o parametri del modello.

---

### C4.17 Infrastruttura a Conoscenza Zero

Implementare sistemi di prova a conoscenza zero per la verifica e l'autenticazione dell'IA preservando la privacy senza rivelare informazioni sensibili.

 #4.17.1    Level: 3    Role: D/V
 Verificare che le prove a conoscenza zero (ZK-SNARKs, ZK-STARKs) confermino l'integrità del modello AI e la provenienza dell'addestramento senza esporre i pesi del modello o i dati di addestramento.
 #4.17.2    Level: 3    Role: D/V
 Verifica che i sistemi di autenticazione basati su ZK consentano la verifica dell'utente preservando la privacy per i servizi di intelligenza artificiale senza rivelare informazioni correlate all'identità.
 #4.17.3    Level: 3    Role: D/V
 Verificare che i protocolli di intersezione di insiemi privati (PSI) consentano un confronto sicuro dei dati per l’intelligenza artificiale federata senza esporre i singoli set di dati.
 #4.17.4    Level: 3    Role: D/V
 Verificare che i sistemi di apprendimento automatico a conoscenza zero (ZKML) consentano inferenze AI verificabili con prova crittografica del corretto calcolo.
 #4.17.5    Level: 3    Role: D/V
 Verificare che gli ZK-rollup forniscano un'elaborazione delle transazioni AI scalabile e che preservi la privacy, con verifica batch e riduzione del carico computazionale.

---

### C4.18 Prevenzione degli attacchi di canale laterale

Proteggi l'infrastruttura AI da attacchi side-channel basati su tempistica, consumo energetico, elettromagnetismo e cache che potrebbero divulgare informazioni sensibili.

 #4.18.1    Level: 3    Role: D/V
 Verificare che il tempo di inferenza dell’IA sia normalizzato utilizzando algoritmi a tempo costante e padding per prevenire attacchi di estrazione del modello basati sul tempo.
 #4.18.2    Level: 3    Role: D/V
 Verificare che la protezione dall'analisi di potenza includa l'iniezione di rumore, il filtraggio della linea di alimentazione e schemi di esecuzione randomizzati per l'hardware AI.
 #4.18.3    Level: 3    Role: D/V
 Verificare che la mitigazione dei canali laterali basati sulla cache utilizzi la partizione della cache, la randomizzazione e le istruzioni di flush per prevenire la fuoriuscita di informazioni.
 #4.18.4    Level: 3    Role: D/V
 Verificare che la protezione dalle emanazioni elettromagnetiche includa schermatura, filtraggio del segnale e elaborazione randomizzata per prevenire attacchi in stile TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Verificare che le difese contro i canali laterali microarchitetturali includano controlli sull'esecuzione speculativa e offuscamento dei modelli di accesso alla memoria.

---

### C4.19 Sicurezza dell'Hardware Neuromorfico e AI Specializzato

Garantire la sicurezza delle nuove architetture hardware AI emergenti, inclusi chip neuromorfici, FPGA, ASIC personalizzati e sistemi di calcolo ottico.

 #4.19.1    Level: 3    Role: D/V
 Verificare che la sicurezza del chip neuromorfico includa la crittografia del modello di impulsi, la protezione del peso sinaptico e la convalida delle regole di apprendimento basata sull'hardware.
 #4.19.2    Level: 3    Role: D/V
 Verificare che gli accelerator AI basati su FPGA implementino la crittografia del bitstream, meccanismi anti-manomissione e caricamento sicuro della configurazione con aggiornamenti autenticati.
 #4.19.3    Level: 3    Role: D/V
 Verificare che la sicurezza ASIC personalizzata includa processori di sicurezza on-chip, root hardware di fiducia e archiviazione sicura delle chiavi con rilevamento di manomissioni.
 #4.19.4    Level: 3    Role: D/V
 Verificare che i sistemi di calcolo ottico implementino crittografia ottica quantisticamente sicura, commutazione fotonica sicura e elaborazione protetta del segnale ottico.
 #4.19.5    Level: 3    Role: D/V
 Verificare che i chip AI ibridi analogico-digitali includano calcolo analogico sicuro, memorizzazione protetta dei pesi e conversione autenticata da analogico a digitale.

---

### C4.20 Infrastruttura di Calcolo che Preserva la Privacy

Implementare controlli infrastrutturali per il calcolo che preserva la privacy al fine di proteggere i dati sensibili durante l'elaborazione e l'analisi dell'IA.

 #4.20.1    Level: 3    Role: D/V
 Verificare che l'infrastruttura di crittografia omomorfica consenta il calcolo crittografato su carichi di lavoro sensibili di intelligenza artificiale con verifica dell'integrità crittografica e monitoraggio delle prestazioni.
 #4.20.2    Level: 3    Role: D/V
 Verificare che i sistemi di retrieval di informazioni private consentano interrogazioni al database senza rivelare i modelli di query, garantendo la protezione crittografica dei modelli di accesso.
 #4.20.3    Level: 3    Role: D/V
 Verificare che i protocolli di calcolo multi-parte sicuro consentano un'inferenza AI che preservi la privacy senza esporre dati individuali o calcoli intermedi.
 #4.20.4    Level: 3    Role: D/V
 Verificare che la gestione delle chiavi con preservazione della privacy includa generazione distribuita delle chiavi, crittografia a soglia e rotazione sicura delle chiavi con protezione supportata dall'hardware.
 #4.20.5    Level: 3    Role: D/V
 Verificare che le prestazioni del calcolo a tutela della privacy siano ottimizzate tramite l'elaborazione in batch, la memorizzazione nella cache e l'accelerazione hardware, mantenendo al contempo le garanzie di sicurezza crittografica.

---

### C4.15 Sicurezza dell'Integrazione Cloud del Framework Agent e Distribuzione Ibrida

Controlli di sicurezza per framework di agenti integrati con il cloud in architetture ibride on-premises/cloud.

 #4.15.1    Level: 1    Role: D/V
 Verificare che l'integrazione dello storage cloud utilizzi la crittografia end-to-end con gestione delle chiavi controllata dall'agente.
 #4.15.2    Level: 2    Role: D/V
 Verificare che i confini di sicurezza nel deployment ibrido siano chiaramente definiti con canali di comunicazione criptati.
 #4.15.3    Level: 2    Role: D/V
 Verificare che l'accesso alle risorse cloud includa una verifica zero-trust con autenticazione continua.
 #4.15.4    Level: 3    Role: D/V
 Verificare che i requisiti di residenza dei dati siano applicati tramite attestazione crittografica delle posizioni di archiviazione.
 #4.15.5    Level: 3    Role: D/V
 Verificare che le valutazioni di sicurezza del fornitore cloud includano la modellazione delle minacce specifica per l'agente e la valutazione del rischio.

---

### Riferimenti

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Controllo di Accesso C5 e Identità per Componenti e Utenti AI

### Obiettivo di Controllo

Il controllo accessi efficace per i sistemi di IA richiede una gestione robusta delle identità, un’autorizzazione consapevole del contesto e un’applicazione in tempo reale basata sui principi di zero-trust. Questi controlli garantiscono che esseri umani, servizi e agenti autonomi interagiscano solo con modelli, dati e risorse computazionali entro ambiti esplicitamente concessi, con capacità di verifica continua e audit.

---

### C5.1 Gestione dell'Identità e Autenticazione

Stabilire identità supportate da crittografia per tutte le entità con autenticazione multi-fattore per operazioni privilegiate.

 #5.1.1    Level: 1    Role: D/V
 Verificare che tutti gli utenti umani e i service principal si autentichino tramite un provider di identità aziendale centralizzato (IdP) utilizzando i protocolli OIDC/SAML con mappature univoche identità-token (nessun account o credenziali condivise).
 #5.1.2    Level: 1    Role: D/V
 Verificare che le operazioni ad alto rischio (implementazione del modello, esportazione dei pesi, accesso ai dati di addestramento, modifiche alla configurazione di produzione) richiedano l'autenticazione multi-fattore o un'autenticazione aumentata con la ri-validazione della sessione.
 #5.1.3    Level: 2    Role: D
 Verificare che i nuovi responsabili sottopongano a un processo di verifica dell'identità conforme al NIST 800-63-3 IAL-2 o a standard equivalenti prima di ricevere l'accesso ai sistemi di produzione.
 #5.1.4    Level: 2    Role: V
 Verificare che le revisioni degli accessi siano effettuate trimestralmente con rilevamento automatico degli account inattivi, applicazione della rotazione delle credenziali e flussi di lavoro per la de-provisioning.
 #5.1.5    Level: 3    Role: D/V
 Verificare che gli agenti AI federati si autentichino tramite asserzioni JWT firmate che abbiano una durata massima di 24 ore e includano una prova crittografica di origine.

---

### C5.2 Autorizzazione delle Risorse e Privilegio Minimo

Implementare controlli di accesso dettagliati per tutte le risorse di intelligenza artificiale con modelli di autorizzazione espliciti e tracciamenti di audit.

 #5.2.1    Level: 1    Role: D/V
 Verificare che ogni risorsa AI (dataset, modelli, endpoint, raccolte vettoriali, indici di embedding, istanze di calcolo) applichi controlli di accesso basati sui ruoli con liste di autorizzazione esplicite e politiche di diniego predefinito.
 #5.2.2    Level: 1    Role: D/V
 Verificare che i principi del minimo privilegio siano applicati di default agli account di servizio, iniziando con permessi in sola lettura e richiedendo una giustificazione aziendale documentata per l’accesso in scrittura.
 #5.2.3    Level: 1    Role: V
 Verificare che tutte le modifiche al controllo degli accessi siano collegate a richieste di modifica approvate e registrate in modo immutabile con timestamp, identità degli attori, identificatori delle risorse e delta delle autorizzazioni.
 #5.2.4    Level: 2    Role: D
 Verificare che le etichette di classificazione dei dati (PII, PHI, controllati per l'esportazione, proprietari) si propaghino automaticamente alle risorse derivate (embedding, cache dei prompt, output del modello) con un'applicazione coerente delle policy.
 #5.2.5    Level: 2    Role: D/V
 Verificare che i tentativi di accesso non autorizzati e gli eventi di escalation dei privilegi attivino avvisi in tempo reale con metadati contestuali ai sistemi SIEM entro 5 minuti.

---

### C5.3 Valutazione Dinamica delle Policy

Distribuire motori di controllo degli accessi basati su attributi (ABAC) per decisioni di autorizzazione consapevoli del contesto con capacità di audit.

 #5.3.1    Level: 1    Role: D/V
 Verificare che le decisioni di autorizzazione siano esternalizzate a un motore di policy dedicato (OPA, Cedar o equivalente) accessibile tramite API autenticati con protezione dell'integrità crittografica.
 #5.3.2    Level: 1    Role: D/V
 Verificare che le policy valutino gli attributi dinamici in fase di esecuzione, inclusi il livello di autorizzazione dell'utente, la classificazione di sensibilità della risorsa, il contesto della richiesta, l'isolamento del tenant e i vincoli temporali.
 #5.3.3    Level: 2    Role: D
 Verificare che le definizioni delle policy siano gestite con controllo delle versioni, revisionate da pari e validate tramite test automatizzati nelle pipeline CI/CD prima del deployment in produzione.
 #5.3.4    Level: 2    Role: V
 Verificare che i risultati della valutazione delle policy includano motivazioni decisionali strutturate e siano trasmessi ai sistemi SIEM per l'analisi di correlazione e la reportistica di conformità.
 #5.3.5    Level: 3    Role: D/V
 Verificare che i valori del time-to-live (TTL) della cache delle policy non superino i 5 minuti per le risorse ad alta sensibilità e 1 ora per le risorse standard con capacità di invalidazione della cache.

---

### C5.4 Applicazione della Sicurezza in Tempo di Query

Implementare controlli di sicurezza a livello di database con filtraggio obbligatorio e politiche di sicurezza a livello di riga.

 #5.4.1    Level: 1    Role: D/V
 Verificare che tutte le query per database vettoriali e SQL includano filtri di sicurezza obbligatori (ID tenant, etichette di sensibilità, ambito utente) applicati a livello del motore di database, non nel codice applicativo.
 #5.4.2    Level: 1    Role: D/V
 Verificare che le politiche di sicurezza a livello di riga (RLS) e la mascheratura a livello di campo siano abilitate con l’ereditarietà delle politiche per tutti i database vettoriali, gli indici di ricerca e i dataset di addestramento.
 #5.4.3    Level: 2    Role: D
 Verificare che le valutazioni di autorizzazione fallite impediscano gli "attacchi del deputy confuso" interrompendo immediatamente le query e restituendo codici di errore di autorizzazione espliciti invece di restituire insiemi di risultati vuoti.
 #5.4.4    Level: 2    Role: V
 Verificare che la latenza di valutazione delle politiche sia monitorata continuamente con avvisi automatizzati per condizioni di timeout che potrebbero consentire il bypass dell'autorizzazione.
 #5.4.5    Level: 3    Role: D/V
 Verificare che i meccanismi di ritentativo delle query rivalutino le politiche di autorizzazione per tenere conto delle modifiche dinamiche dei permessi durante le sessioni utente attive.

---

### Filtraggio Output C5.5 e Prevenzione della Perdita di Dati

Implementare controlli di post-elaborazione per prevenire la divulgazione non autorizzata di dati nei contenuti generati dall'IA.

 #5.5.1    Level: 1    Role: D/V
 Verificare che i meccanismi di filtraggio post-inferenza eseguano la scansione e la cancellazione di PII non autorizzate, informazioni classificate e dati proprietari prima di consegnare i contenuti ai richiedenti.
 #5.5.2    Level: 1    Role: D/V
 Verificare che citazioni, riferimenti e attribuzioni delle fonti nei risultati del modello siano convalidati rispetto ai diritti di accesso del chiamante e rimossi se viene rilevato un accesso non autorizzato.
 #5.5.3    Level: 2    Role: D
 Verificare che le restrizioni sul formato di output (PDF sanitizzati, immagini senza metadati, tipi di file approvati) siano applicate in base ai livelli di autorizzazione dell'utente e alle classificazioni dei dati.
 #5.5.4    Level: 2    Role: V
 Verificare che gli algoritmi di cancellazione siano deterministici, controllati in versione e mantengano registri di audit per supportare le indagini di conformità e l'analisi forense.
 #5.5.5    Level: 3    Role: V
 Verificare che gli eventi di redazione ad alto rischio generino log adattivi che includano hash crittografici del contenuto originale per il recupero forense senza esposizione dei dati.

---

### C5.6 Isolamento Multi-Tenant

Garantire l'isolamento crittografico e logico tra i tenant in un'infrastruttura di intelligenza artificiale condivisa.

 #5.6.1    Level: 1    Role: D/V
 Verificare che gli spazi di memoria, gli archivi di embedding, le voci della cache e i file temporanei siano segregati per namespace per ogni tenant, con una cancellazione sicura al momento della cancellazione del tenant o della terminazione della sessione.
 #5.6.2    Level: 1    Role: D/V
 Verificare che ogni richiesta API includa un identificatore tenant autenticato che sia convalidato crittograficamente rispetto al contesto della sessione e ai diritti dell'utente.
 #5.6.3    Level: 2    Role: D
 Verificare che le policy di rete implementino regole di negazione predefinite per la comunicazione tra tenant diversi all'interno di service mesh e piattaforme di orchestrazione di container.
 #5.6.4    Level: 3    Role: D
 Verificare che le chiavi di crittografia siano uniche per ogni tenant con supporto per chiavi gestite dal cliente (CMK) e isolamento crittografico tra gli archivi dati dei tenant.

---

### C5.7 Autorizzazione dell'Agente Autonomo

Controllo dei permessi per agenti AI e sistemi autonomi tramite token di capacità con ambito definito e autorizzazione continua.

 #5.7.1    Level: 1    Role: D/V
 Verificare che gli agenti autonomi ricevano token di capacità limitata che elencano esplicitamente le azioni consentite, le risorse accessibili, i confini temporali e i vincoli operativi.
 #5.7.2    Level: 1    Role: D/V
 Verificare che le funzionalità ad alto rischio (accesso al file system, esecuzione di codice, chiamate API esterne, transazioni finanziarie) siano disabilitate per impostazione predefinita e richiedano autorizzazioni esplicite per l’attivazione con giustificazioni aziendali.
 #5.7.3    Level: 2    Role: D
 Verificare che i token di capacità siano associati alle sessioni utente, includano una protezione crittografica dell'integrità e garantire che non possano essere conservati o riutilizzati in scenari offline.
 #5.7.4    Level: 2    Role: V
 Verificare che le azioni avviate dall'agente siano soggette a una seconda autorizzazione tramite il motore di policy ABAC con valutazione completa del contesto e registrazione degli audit.
 #5.7.5    Level: 3    Role: V
 Verificare che le condizioni di errore dell'agente e la gestione delle eccezioni includano informazioni sull'ambito delle capacità per supportare l'analisi degli incidenti e l'investigazione forense.

---

### Riferimenti

#### Norme e Quadri di Riferimento

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Guide di Implementazione

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Sicurezza Specifica per l'IA

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Sicurezza della catena di approvvigionamento per modelli, framework e dati

### Obiettivo di Controllo

Gli attacchi alla supply chain dell'IA sfruttano modelli, framework o set di dati di terze parti per inserire backdoor, bias o codice vulnerabile. Questi controlli offrono una provenienza end-to-end, gestione delle vulnerabilità e monitoraggio per proteggere l'intero ciclo di vita del modello.

---

### C6.1 Verifica e Provenienza del Modello Preaddestrato

Valutare e autenticare origini, licenze e comportamenti nascosti dei modelli di terze parti prima di qualsiasi messa a punto o distribuzione.

 #6.1.1    Level: 1    Role: D/V
 Verificare che ogni artefatto di modello di terze parti includa un record di provenienza firmato che identifichi il repository sorgente e l'hash del commit.
 #6.1.2    Level: 1    Role: D/V
 Verificare che i modelli vengano scansionati per rilevare layer dannosi o trigger Trojan utilizzando strumenti automatizzati prima dell'importazione.
 #6.1.3    Level: 2    Role: D
 Verificare che il trasferimento dell'apprendimento (transfer-learning) affini (fine-tunes) superi la valutazione avversaria per rilevare comportamenti nascosti.
 #6.1.4    Level: 2    Role: V
 Verificare che le licenze del modello, i tag di controllo delle esportazioni e le dichiarazioni di origine dei dati siano registrati in una voce ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Verificare che i modelli ad alto rischio (pesi caricati pubblicamente, creatori non verificati) rimangano in quarantena fino alla revisione e all'approvazione umana.

---

### C6.2 Scansione di Framework e Librerie

Scansionare continuamente i framework e le librerie di ML alla ricerca di CVE e codice dannoso per mantenere sicuro lo stack di runtime.

 #6.2.1    Level: 1    Role: D/V
 Verificare che le pipeline CI eseguano scanner di dipendenze su framework AI e librerie critiche.
 #6.2.2    Level: 1    Role: D/V
 Verificare che le vulnerabilità critiche (CVSS ≥ 7.0) blocchino la promozione alle immagini di produzione.
 #6.2.3    Level: 2    Role: D
 Verificare che l'analisi statica del codice venga eseguita sulle librerie ML forkate o fornite come dipendenze vendute.
 #6.2.4    Level: 2    Role: V
 Verificare che le proposte di aggiornamento del framework includano una valutazione dell'impatto sulla sicurezza con riferimento ai feed pubblici CVE.
 #6.2.5    Level: 3    Role: V
 Verificare che i sensori a runtime segnalino i caricamenti imprevisti di librerie dinamiche che deviano dal SBOM firmato.

---

### C6.3 Blocco delle dipendenze e verifica

Blocca ogni dipendenza su digest immutabili e riproduci le build per garantire artefatti identici e privi di manomissioni.

 #6.3.1    Level: 1    Role: D/V
 Verificare che tutti i gestori di pacchetti applichino il blocco delle versioni tramite file di blocco.
 #6.3.2    Level: 1    Role: D/V
 Verificare che nei riferimenti ai container vengano utilizzati digest immutabili invece di tag mutabili.
 #6.3.3    Level: 2    Role: D
 Verifica che i controlli di build riproducibili confrontino gli hash tra le esecuzioni CI per garantire output identici.
 #6.3.4    Level: 2    Role: V
 Verificare che le attestazioni di build siano conservate per 18 mesi per la tracciabilità dell'audit.
 #6.3.5    Level: 3    Role: D
 Verifica che le dipendenze scadute attivino PR automatiche per aggiornare o forcare le versioni bloccate.

---

### C6.4 Applicazione della Fonte Affidabile

Consenti il download di artifact solo da fonti approvate dall'organizzazione e verificate crittograficamente, bloccando tutto il resto.

 #6.4.1    Level: 1    Role: D/V
 Verificare che i pesi del modello, i dataset e i container siano scaricati solo da domini approvati o registri interni.
 #6.4.2    Level: 1    Role: D/V
 Verificare che le firme Sigstore/Cosign convalidino l'identità dell'editore prima che gli artefatti vengano memorizzati nella cache localmente.
 #6.4.3    Level: 2    Role: D
 Verificare che i proxy di uscita blocchino i download di artefatti non autenticati per applicare la politica della fonte attendibile.
 #6.4.4    Level: 2    Role: V
 Verificare che le liste bianche del repository vengano riviste trimestralmente con prova della giustificazione commerciale per ogni voce.
 #6.4.5    Level: 3    Role: V
 Verificare che le violazioni delle politiche attivino la quarantena degli artifact e il rollback delle esecuzioni delle pipeline dipendenti.

---

### C6.5 Valutazione del Rischio dei Dataset di Terze Parti

Valutare i dataset esterni per avvelenamento, bias e conformità legale, e monitorarli durante tutto il loro ciclo di vita.

 #6.5.1    Level: 1    Role: D/V
 Verificare che i dataset esterni siano sottoposti a una valutazione del rischio di avvelenamento (ad esempio, impronta digitale dei dati, rilevamento degli outlier).
 #6.5.2    Level: 1    Role: D
 Verificare che le metriche di bias (parità demografica, pari opportunità) siano calcolate prima dell'approvazione del dataset.
 #6.5.3    Level: 2    Role: V
 Verificare che la provenienza e i termini di licenza dei dataset siano registrati nelle voci ML-BOM.
 #6.5.4    Level: 2    Role: V
 Verificare che il monitoraggio periodico rilevi deviazioni o corruzioni nei dataset ospitati.
 #6.5.5    Level: 3    Role: D
 Verificare che i contenuti non consentiti (copyright, dati personali identificabili) vengano rimossi tramite un processo automatico di pulizia prima dell'addestramento.

---

### C6.6 Monitoraggio degli Attacchi alla Catena di Fornitura

Rileva precocemente le minacce alla catena di fornitura attraverso feed CVE, analisi dei log di audit e simulazioni red-team.

 #6.6.1    Level: 1    Role: V
 Verificare che i log di audit CI/CD vengano trasmessi al SIEM per il rilevamento di prelievi di pacchetti anomali o passaggi di build manomessi.
 #6.6.2    Level: 2    Role: D
 Verificare che i playbook di risposta agli incidenti includano procedure di rollback per modelli o librerie compromesse.
 #6.6.3    Level: 3    Role: V
 Verifica che l’arricchimento delle informazioni sulle minacce etichetti gli indicatori specifici per ML (ad esempio, gli IoC di avvelenamento del modello) nella triage degli alert.

---

### C6.7 ML‑BOM per gli Artifact del Modello

Generare e firmare SBOM specifici per il machine learning (ML-BOM) dettagliati in modo che i destinatari a valle possano verificare l'integrità dei componenti al momento del deploy.

 #6.7.1    Level: 1    Role: D/V
 Verificare che ogni artefatto modello pubblichi un ML‑BOM che elenchi i set di dati, i pesi, gli iperparametri e le licenze.
 #6.7.2    Level: 1    Role: D/V
 Verificare che la generazione di ML‑BOM e la firma Cosign siano automatizzate nel CI e richieste per la fusione.
 #6.7.3    Level: 2    Role: D
 Verificare che i controlli di completezza ML-BOM interrompano la build se manca qualche metadato del componente (hash, licenza).
 #6.7.4    Level: 2    Role: V
 Verificare che i consumatori a valle possano interrogare gli ML-BOM tramite API per convalidare i modelli importati al momento del deployment.
 #6.7.5    Level: 3    Role: V
 Verificare che gli ML-BOM siano sotto controllo di versione e confrontati per rilevare modifiche non autorizzate.

---

### Riferimenti

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Comportamento del Modello C7, Controllo dell'Uscita e Garanzia di Sicurezza

### Obiettivo di Controllo

I risultati del modello devono essere strutturati, affidabili, sicuri, spiegabili e costantemente monitorati in produzione. Ciò riduce le allucinazioni, le fughe di dati privati, i contenuti dannosi e le azioni incontrollate, aumentando al contempo la fiducia degli utenti e la conformità normativa.

---

### C7.1 Applicazione del formato di output

Schemi rigidi, decodifica vincolata e convalida a valle impediscono che contenuti malformati o dannosi si propaghino.

 #7.1.1    Level: 1    Role: D/V
 Verificare che gli schemi di risposta (ad esempio, JSON Schema) siano forniti nel prompt di sistema e che ogni output venga automaticamente convalidato; gli output non conformi attivano una riparazione o un rifiuto.
 #7.1.2    Level: 1    Role: D/V
 Verificare che la decodifica vincolata (token di stop, espressioni regolari, max-token) sia abilitata per prevenire overflow o canali laterali di iniezione di prompt.
 #7.1.3    Level: 2    Role: D/V
 Verificare che i componenti a valle considerino le uscite come non attendibili e le convalidino rispetto a schemi o de-serializzatori sicuri contro le iniezioni.
 #7.1.4    Level: 3    Role: V
 Verificare che gli eventi di output improprio vengano registrati, limitati nel tasso e segnalati nel sistema di monitoraggio.

---

### C7.2 Rilevamento e Mitigazione delle Allucinazioni

La stima dell'incertezza e le strategie di fallback limitano le risposte fabbricate.

 #7.2.1    Level: 1    Role: D/V
 Verificare che le log-probabilità a livello di token, la coerenza autonoma dell'ensemble o i rilevatori di allucinazioni affinati assegnino un punteggio di confidenza a ciascuna risposta.
 #7.2.2    Level: 1    Role: D/V
 Verificare che le risposte al di sotto di una soglia di confidenza configurabile attivino flussi di lavoro di fallback (ad esempio, generazione aumentata da recupero, modello secondario o revisione umana).
 #7.2.3    Level: 2    Role: D/V
 Verificare che gli incidenti di allucinazione siano contrassegnati con metadati di causa principale e inseriti nelle pipeline di analisi post-mortem e di affinamento.
 #7.2.4    Level: 3    Role: D/V
 Verificare che le soglie e i rilevatori siano ricalibrati dopo aggiornamenti importanti del modello o della base di conoscenza.
 #7.2.5    Level: 3    Role: V
 Verificare che le visualizzazioni della dashboard monitorino i tassi di allucinazione.

---

### C7.3 Filtraggio della Sicurezza e della Privacy dell'Uscita

I filtri di policy e la copertura red-team proteggono gli utenti e i dati riservati.

 #7.3.1    Level: 1    Role: D/V
 Verificare che i classificatori pre e post-generazione blocchino contenuti di odio, molestie, autolesionismo, estremismo e contenuti sessualmente espliciti in conformità alla politica.
 #7.3.2    Level: 1    Role: D/V
 Verificare che il rilevamento di PII/PCI e la redazione automatica vengano eseguiti su ogni risposta; le violazioni generano un incidente di privacy.
 #7.3.3    Level: 2    Role: D
 Verificare che i tag di riservatezza (ad esempio, segreti commerciali) si propaghino attraverso le modalità per prevenire la fuoriuscita in testi, immagini o codice.
 #7.3.4    Level: 3    Role: D/V
 Verificare che i tentativi di elusione del filtro o le classificazioni ad alto rischio richiedano un'approvazione secondaria o una riautenticazione dell'utente.
 #7.3.5    Level: 3    Role: D/V
 Verificare che le soglie di filtraggio riflettano le giurisdizioni legali e il contesto di età/ruolo dell'utente.

---

### C7.4 Limitazione dell'Output e delle Azioni

I limiti di velocità e i cancelli di approvazione prevengono abusi e autonomia eccessiva.

 #7.4.1    Level: 1    Role: D
 Verificare che le quote per utente e per chiave API limitino le richieste, i token e i costi con back-off esponenziale sugli errori 429.
 #7.4.2    Level: 1    Role: D/V
 Verificare che le azioni privilegiate (scrittura di file, esecuzione di codice, chiamate di rete) richiedano l'approvazione basata su policy o l'intervento umano.
 #7.4.3    Level: 2    Role: D/V
 Verificare che i controlli di coerenza cross-modale garantiscano che immagini, codice e testo generati per la stessa richiesta non possano essere utilizzati per introdurre contenuti dannosi.
 #7.4.4    Level: 2    Role: D
 Verificare che la profondità di delega dell’agente, i limiti di ricorsione e le liste di strumenti consentiti siano configurati esplicitamente.
 #7.4.5    Level: 3    Role: V
 Verificare che la violazione dei limiti generi eventi di sicurezza strutturati per l'ingestione da parte del SIEM.

---

### C7.5 Spiegabilità dell'Uscita

I segnali trasparenti migliorano la fiducia dell'utente e il debug interno.

 #7.5.1    Level: 2    Role: D/V
 Verificare che i punteggi di fiducia rivolti all'utente o brevi riassunti delle motivazioni siano esposti quando la valutazione del rischio lo ritiene appropriato.
 #7.5.2    Level: 2    Role: D/V
 Verificare che le spiegazioni generate evitino di rivelare prompt di sistema sensibili o dati proprietari.
 #7.5.3    Level: 3    Role: D
 Verificare che il sistema acquisisca le probabilità logaritmiche a livello di token o le mappe di attenzione e le memorizzi per un'ispezione autorizzata.
 #7.5.4    Level: 3    Role: V
 Verificare che gli artefatti di spiegabilità siano soggetti a controllo delle versioni insieme alle release dei modelli per garantire la tracciabilità.

---

### C7.6 Integrazione del Monitoraggio

L'osservabilità in tempo reale chiude il ciclo tra sviluppo e produzione.

 #7.6.1    Level: 1    Role: D
 Verificare che le metriche (violazioni dello schema, tasso di allucinazioni, tossicità, perdite di PII, latenza, costo) vengano trasmesse a una piattaforma centrale di monitoraggio.
 #7.6.2    Level: 1    Role: V
 Verificare che siano definiti soglie di allerta per ogni parametro di sicurezza, con percorsi di escalation disponibili per il personale reperibile.
 #7.6.3    Level: 2    Role: V
 Verifica che le dashboard mettano in correlazione le anomalie di output con il modello/versione, il flag della funzione e le modifiche ai dati upstream.
 #7.6.4    Level: 2    Role: D/V
 Verificare che i dati di monitoraggio vengano reinseriti nel processo di retraining, fine-tuning o aggiornamento delle regole all'interno di un flusso di lavoro MLOps documentato.
 #7.6.5    Level: 3    Role: V
 Verificare che le pipeline di monitoraggio siano sottoposte a test di penetrazione e protette da controlli di accesso per evitare la perdita di log sensibili.

---

### 7.7 Salvaguardie per i Media Generativi

Garantire che i sistemi di IA non generino contenuti multimediali illegali, dannosi o non autorizzati mediante l'applicazione di vincoli di policy, la validazione dell'output e la tracciabilità.

 #7.7.1    Level: 1    Role: D/V
 Verificare che i prompt di sistema e le istruzioni per l'utente vietino esplicitamente la generazione di contenuti deepfake illegali, dannosi o non consensuali (ad esempio, immagini, video, audio).
 #7.7.2    Level: 2    Role: D/V
 Verificare che i prompt siano filtrati per tentativi di generare imitazioni, deepfake sessualmente espliciti o media che rappresentano individui reali senza consenso.
 #7.7.3    Level: 2    Role: V
 Verificare che il sistema utilizzi hashing percettivo, rilevamento watermark o fingerprinting per prevenire la riproduzione non autorizzata di contenuti protetti da copyright.
 #7.7.4    Level: 3    Role: D/V
 Verificare che tutti i media generati siano firmati crittograficamente, con filigrana o incorporati con metadati di provenienza resistenti alla manomissione per la tracciabilità a valle.
 #7.7.5    Level: 3    Role: V
 Verificare che i tentativi di elusione (ad esempio, offuscamento del prompt, gergo, formulazione avversaria) vengano rilevati, registrati e soggetti a limitazione di frequenza; gli abusi ripetuti devono essere segnalati ai sistemi di monitoraggio.

### Riferimenti

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Sicurezza della Memoria C8, degli Embeddings e dei Database Vettoriali

### Obiettivo di Controllo

Gli embeddings e gli archivi vettoriali agiscono come la "memoria attiva" dei sistemi di intelligenza artificiale contemporanei, accettando continuamente dati forniti dagli utenti e riportandoli nei contesti del modello tramite Retrieval-Augmented Generation (RAG). Se lasciata senza controllo, questa memoria può divulgare dati personali identificabili (PII), violare il consenso o essere invertita per ricostruire il testo originale. L'obiettivo di questa famiglia di controlli è rafforzare le pipeline di memoria e i database vettoriali affinché l'accesso sia a privilegio minimo, gli embeddings preservino la privacy, i vettori memorizzati scadano o possano essere revocati su richiesta e la memoria per utente non contamini mai i prompt o le completazioni di un altro utente.

---

### C8.1 Controlli di Accesso su Memoria e Indici RAG

Applicare controlli di accesso granulare su ogni collezione di vettori.

 #8.1.1    Level: 1    Role: D/V
 Verificare che le regole di controllo accessi a livello di riga/namespace limitino le operazioni di inserimento, eliminazione e interrogazione per inquilino, raccolta o tag del documento.
 #8.1.2    Level: 1    Role: D/V
 Verificare che le chiavi API o i JWT contengano claim con ambito definito (ad es., ID delle collezioni, verbi di azione) e vengano ruotati almeno ogni trimestre.
 #8.1.3    Level: 2    Role: D/V
 Verificare che i tentativi di escalation dei privilegi (ad esempio, query di somiglianza cross-namespace) siano rilevati e registrati in un SIEM entro 5 minuti.
 #8.1.4    Level: 2    Role: D/V
 Verificare che il database vettoriale registri nel log l'identificatore del soggetto, l'operazione, l'ID/namespace del vettore, la soglia di similarità e il conteggio dei risultati.
 #8.1.5    Level: 3    Role: V
 Verificare che le decisioni di accesso vengano testate per individuare eventuali falle di bypass ogni volta che i motori vengono aggiornati o le regole di partizionamento dell'indice vengono modificate.

---

### C8.2 Sanitizzazione e Validazione degli Embedding

Pre-filtrare il testo per informazioni personali identificabili (PII), oscurare o pseudonimizzare prima della vettorizzazione e, opzionalmente, post-elaborare gli embeddings per rimuovere segnali residui.

 #8.2.1    Level: 1    Role: D/V
 Verificare che i dati PII e regolamentati vengano rilevati tramite classificatori automatizzati e mascherati, tokenizzati o eliminati prima dell'embedding.
 #8.2.2    Level: 1    Role: D
 Verificare che le pipeline di embedding rifiutino o isolino gli input contenenti codice eseguibile o artefatti non UTF-8 che potrebbero compromettere l'indice.
 #8.2.3    Level: 2    Role: D/V
 Verificare che sia applicata una sanificazione differenziale locale o metrica alla privacy agli embedding delle frasi la cui distanza da qualsiasi token PII noto scende al di sotto di una soglia configurabile.
 #8.2.4    Level: 2    Role: V
 Verificare che l'efficacia della sanitizzazione (ad esempio, il richiamo della redazione delle informazioni personali identificabili, la deriva semantica) sia convalidata almeno semestralmente rispetto a corpora di riferimento.
 #8.2.5    Level: 3    Role: D/V
 Verificare che le configurazioni di sanitizzazione siano gestite con controllo di versione e che le modifiche vengano sottoposte a revisione tra pari.

---

### C8.3 Scadenza, Revoca e Cancellazione della Memoria

Il GDPR "diritto all'oblio" e leggi simili richiedono la cancellazione tempestiva; pertanto, gli archivi vettoriali devono supportare TTL, cancellazioni definitive e tombamento affinché i vettori revocati non possano essere recuperati o reindicizzati.

 #8.3.1    Level: 1    Role: D/V
 Verificare che ogni vettore e record di metadata abbia un TTL o un'etichetta di conservazione esplicita rispettata dai processi di pulizia automatizzati.
 #8.3.2    Level: 1    Role: D/V
 Verificare che le richieste di cancellazione avviate dall'utente eliminino vettori, metadati, copie cache e indici derivati entro 30 giorni.
 #8.3.3    Level: 2    Role: D
 Verificare che le cancellazioni logiche siano seguite dalla distruzione crittografica dei blocchi di memoria se l'hardware lo supporta, oppure dalla distruzione della chiave nel key vault.
 #8.3.4    Level: 3    Role: D/V
 Verificare che i vettori scaduti siano esclusi dai risultati della ricerca del vicino più vicino entro meno di 500 ms dopo la scadenza.

---

### C8.4 Prevenire l'Inversione e la Perdita di Embedding

Le recenti difese—sovrapposizione di rumore, reti di proiezione, perturbazione dei neuroni della privacy e crittografia a livello di applicazione—possono ridurre i tassi di inversione a livello di token al di sotto del 5%.

 #8.4.1    Level: 1    Role: V
 Verificare che esista un modello di minaccia formale che copra attacchi di inversione, appartenenza e inferenza di attributi, e che venga revisionato annualmente.
 #8.4.2    Level: 2    Role: D/V
 Verificare che la crittografia a livello applicativo o la crittografia ricercabile proteggano i vettori da letture dirette da parte degli amministratori dell'infrastruttura o del personale cloud.
 #8.4.3    Level: 3    Role: V
 Verificare che i parametri di difesa (ε per DP, rumore σ, rango di proiezione k) bilancino la privacy ≥ 99% di protezione dei token e l’utilità ≤ 3% di perdita di accuratezza.
 #8.4.4    Level: 3    Role: D/V
 Verificare che le metriche di resilienza all'inversione facciano parte delle soglie di rilascio per gli aggiornamenti del modello, con budget di regressione definiti.

---

### C8.5 Applicazione dell'ambito per la memoria specifica dell'utente

La perdita di dati tra tenant rimane un rischio principale per RAG: query di similarità filtrate in modo improprio possono far emergere i documenti privati di un altro cliente.

 #8.5.1    Level: 1    Role: D/V
 Verificare che ogni query di recupero venga filtrata successivamente per ID tenant/utente prima di essere passata al prompt LLM.
 #8.5.2    Level: 1    Role: D
 Verifica che i nomi delle collezioni o gli ID con namespace siano salati per utente o tenant in modo che i vettori non possano collidere tra diversi ambiti.
 #8.5.3    Level: 2    Role: D/V
 Verificare che i risultati di similarità superiori a una soglia di distanza configurabile ma al di fuori dell'ambito del chiamante vengano scartati e attivino allarmi di sicurezza.
 #8.5.4    Level: 2    Role: V
 Verificare che i test di stress multi-tenant simulino query avversarie che tentano di recuperare documenti fuori dal loro ambito e dimostrino l'assenza di perdite di dati.
 #8.5.5    Level: 3    Role: D/V
 Verificare che le chiavi di crittografia siano separate per ogni tenant, garantendo l'isolamento crittografico anche se lo storage fisico è condiviso.

---

### C8.6 Sicurezza Avanzata del Sistema di Memoria

Controlli di sicurezza per architetture di memoria sofisticate, inclusi memoria episodica, semantica e di lavoro, con requisiti specifici di isolamento e validazione.

 #8.6.1    Level: 1    Role: D/V
 Verificare che i diversi tipi di memoria (episodica, semantica, di lavoro) abbiano contesti di sicurezza isolati con controlli di accesso basati sui ruoli, chiavi di crittografia separate e modelli di accesso documentati per ciascun tipo di memoria.
 #8.6.2    Level: 2    Role: D/V
 Verificare che i processi di consolidamento della memoria includano una validazione della sicurezza per prevenire l'iniezione di memorie dannose tramite la sanitizzazione del contenuto, la verifica della fonte e i controlli di integrità prima della memorizzazione.
 #8.6.3    Level: 2    Role: D/V
 Verificare che le query di recupero della memoria siano validate e sanificate per prevenire l'estrazione di informazioni non autorizzate tramite l'analisi dei modelli di query, l'applicazione del controllo degli accessi e il filtraggio dei risultati.
 #8.6.4    Level: 3    Role: D/V
 Verificare che i meccanismi di cancellazione della memoria eliminino in modo sicuro le informazioni sensibili con garanzie di cancellazione crittografica utilizzando la cancellazione delle chiavi, la sovrascrittura multipla o la cancellazione sicura basata su hardware con certificati di verifica.
 #8.6.5    Level: 3    Role: D/V
 Verificare che l'integrità del sistema di memoria sia continuamente monitorata per modifiche non autorizzate o corruzione tramite somme di controllo, registri di audit e avvisi automatici quando il contenuto della memoria cambia al di fuori delle operazioni normali.

---

### Riferimenti

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Orchestrazione Autonoma e Sicurezza dell’Azione Agentica

### Obiettivo di Controllo

Assicurarsi che i sistemi di intelligenza artificiale autonomi o multi-agente possano eseguire solo azioni esplicitamente intenzionate, autenticate, verificabili e all'interno di limiti prestabiliti di costo e rischio. Ciò protegge contro minacce quali Compromissione del Sistema Autonomo, Uso Improprio degli Strumenti, Rilevamento del Ciclo degli Agenti, Dirottamento delle Comunicazioni, Falsificazione dell'Identità, Manipolazione dello Sciame e Manipolazione dell'Intento.

---

### 9.1 Budget di Pianificazione dei Compiti e Ricorsione dell’Agente

Limita i piani ricorsivi e imposta checkpoint umani obbligatori per azioni privilegiate.

 #9.1.1    Level: 1    Role: D/V
 Verificare che la profondità massima della ricorsione, la larghezza, il tempo effettivo, i token e il costo monetario per esecuzione dell'agente siano configurati centralmente e sottoposti a controllo di versione.
 #9.1.2    Level: 1    Role: D/V
 Verificare che le azioni privilegiate o irreversibili (ad esempio, commit di codice, trasferimenti finanziari) richiedano l'approvazione esplicita umana tramite un canale auditabile prima dell'esecuzione.
 #9.1.3    Level: 2    Role: D
 Verificare che i monitor di risorse in tempo reale attivino l'interruzione del circuito di sicurezza quando viene superata qualsiasi soglia di budget, fermando ulteriori espansioni del compito.
 #9.1.4    Level: 2    Role: D/V
 Verificare che gli eventi del circuito di interruzione siano registrati con l'ID dell'agente, la condizione di attivazione e lo stato del piano catturato per la revisione forense.
 #9.1.5    Level: 3    Role: V
 Verificare che i test di sicurezza coprano gli scenari di esaurimento del budget e di piano fuori controllo, confermando un arresto sicuro senza perdita di dati.
 #9.1.6    Level: 3    Role: D
 Verificare che le politiche di budget siano espresse come policy-as-code e applicate nel CI/CD per bloccare la deriva della configurazione.

---

### 9.2 Isolamento dei Plugin degli Strumenti

Isolare le interazioni degli strumenti per prevenire accessi non autorizzati al sistema o l'esecuzione di codice.

 #9.2.1    Level: 1    Role: D/V
 Verificare che ogni strumento/plugin venga eseguito all'interno di un sistema operativo, container o sandbox a livello WASM con politiche di minimo privilegio per file system, rete e chiamate di sistema.
 #9.2.2    Level: 1    Role: D/V
 Verificare che le quote delle risorse del sandbox (CPU, memoria, disco, uscita di rete) e i timeout di esecuzione siano applicati e registrati.
 #9.2.3    Level: 2    Role: D/V
 Verificare che i binari o i descrittori degli strumenti siano firmati digitalmente; le firme devono essere convalidate prima del caricamento.
 #9.2.4    Level: 2    Role: V
 Verificare che la telemetria della sandbox fluisca verso un SIEM; le anomalie (ad esempio, tentativi di connessioni in uscita) generano allerte.
 #9.2.5    Level: 3    Role: V
 Verificare che i plugin ad alto rischio siano sottoposti a revisione della sicurezza e test di penetrazione prima della distribuzione in produzione.
 #9.2.6    Level: 3    Role: D/V
 Verificare che i tentativi di fuga dalla sandbox siano bloccati automaticamente e che il plugin non conforme venga messo in quarantena in attesa di indagine.

---

### 9.3 Ciclo Autonomo e Limitazione dei Costi

Rilevare e fermare la ricorsione incontrollata tra agenti e l’esplosione dei costi.

 #9.3.1    Level: 1    Role: D/V
 Verificare che le chiamate inter-agente includano un limite di salto o TTL che il runtime decrementa e applica.
 #9.3.2    Level: 2    Role: D
 Verificare che gli agenti mantengano un ID univoco del grafo di invocazione per individuare auto-invocazioni o schemi ciclici.
 #9.3.3    Level: 2    Role: D/V
 Verificare che i contatori cumulativi delle unità di calcolo e della spesa siano tracciati per catena di richiesta; superare il limite interrompe la catena.
 #9.3.4    Level: 3    Role: V
 Verificare che l'analisi formale o il model checking dimostrino l'assenza di ricorsione illimitata nei protocolli degli agenti.
 #9.3.5    Level: 3    Role: D
 Verificare che gli eventi di interruzione del ciclo generino avvisi e alimentino metriche di miglioramento continuo.

---

### 9.4 Protezione contro l'uso improprio a livello di protocollo

Canali di comunicazione sicuri tra agenti e sistemi esterni per prevenire dirottamenti o manipolazioni.

 #9.4.1    Level: 1    Role: D/V
 Verificare che tutti i messaggi da agente a strumento e da agente ad agente siano autenticati (ad esempio, TLS reciproco o JWT) e crittografati end-to-end.
 #9.4.2    Level: 1    Role: D
 Verificare che gli schemi siano rigorosamente convalidati; i campi sconosciuti o i messaggi malformati vengono rifiutati.
 #9.4.3    Level: 2    Role: D/V
 Verificare che i controlli di integrità (MAC o firme digitali) coprano l'intero payload del messaggio, inclusi i parametri degli strumenti.
 #9.4.4    Level: 2    Role: D
 Verificare che la protezione contro la ripetizione (nonce o finestre di timestamp) sia applicata a livello di protocollo.
 #9.4.5    Level: 3    Role: V
 Verificare che le implementazioni del protocollo siano sottoposte a fuzzing e analisi statica per individuare vulnerabilità di injection o deserializzazione.

---

### 9.5 Identità dell’Agente e Evidenza di Manomissione

Garantire che le azioni siano attribuibili e che le modifiche siano rilevabili.

 #9.5.1    Level: 1    Role: D/V
 Verificare che ogni istanza dell'agente possieda un'identità crittografica unica (coppia di chiavi o credenziale basata su hardware).
 #9.5.2    Level: 2    Role: D/V
 Verificare che tutte le azioni dell'agente siano firmate e datate; i log includono la firma per la non ripudiabilità.
 #9.5.3    Level: 2    Role: V
 Verificare che i log a prova di manomissione siano archiviati in un supporto di sola aggiunta o scrittura unica.
 #9.5.4    Level: 3    Role: D
 Verificare che le chiavi di identità ruotino secondo un programma definito e in presenza di indicatori di compromissione.
 #9.5.5    Level: 3    Role: D/V
 Verificare che i tentativi di spoofing o conflitto di chiavi attivino l'isolamento immediato dell'agente interessato.

---

### 9.6 Riduzione del Rischio con Sciame Multi-Agente

Mitigare i rischi legati al comportamento collettivo tramite isolamento e modellazione formale della sicurezza.

 #9.6.1    Level: 1    Role: D/V
 Verificare che gli agenti che operano in diversi domini di sicurezza vengano eseguiti in ambienti di runtime isolati o in segmenti di rete separati.
 #9.6.2    Level: 3    Role: V
 Verificare che i comportamenti dello sciame siano modellati e formalmente verificati per la vivacità e la sicurezza prima della distribuzione.
 #9.6.3    Level: 3    Role: D
 Verificare che i monitor di runtime rilevino schemi di comportamento pericolosi emergenti (ad esempio, oscillazioni, deadlock) e avviino azioni correttive.

---

### 9.7 Autenticazione / Autorizzazione Utente e Strumento

Implementare controlli di accesso robusti per ogni azione attivata dall'agente.

 #9.7.1    Level: 1    Role: D/V
 Verificare che gli agenti si autentichino come principali di prima classe nei sistemi a valle, senza mai riutilizzare le credenziali dell'utente finale.
 #9.7.2    Level: 2    Role: D
 Verificare che le politiche di autorizzazione a grana fine limitino gli strumenti che un agente può invocare e quali parametri può fornire.
 #9.7.3    Level: 2    Role: V
 Verificare che i controlli dei privilegi vengano rivalutati ad ogni chiamata (autorizzazione continua), e non solo all'inizio della sessione.
 #9.7.4    Level: 3    Role: D
 Verificare che i privilegi delegati scadano automaticamente e richiedano un nuovo consenso dopo il timeout o una modifica dell'ambito.

---

### 9.8 Sicurezza nella comunicazione tra agenti

Cripta e proteggi l'integrità di tutti i messaggi tra agenti per evitare intercettazioni e manomissioni.

 #9.8.1    Level: 1    Role: D/V
 Verificare che l'autenticazione reciproca e la crittografia con perfetto segreto avanti (ad esempio TLS 1.3) siano obbligatorie per i canali degli agenti.
 #9.8.2    Level: 1    Role: D
 Verificare che l'integrità e l'origine del messaggio siano convalidate prima dell'elaborazione; in caso di errori, vengono generati allarmi e il messaggio viene scartato.
 #9.8.3    Level: 2    Role: D/V
 Verificare che i metadati della comunicazione (timestamp, numeri di sequenza) siano registrati per supportare la ricostruzione forense.
 #9.8.4    Level: 3    Role: V
 Verificare che la verifica formale o il model checking confermino che le macchine a stati del protocollo non possano essere portate in stati non sicuri.

---

### 9.9 Verifica dell'Intento e Applicazione dei Vincoli

Verificare che le azioni dell'agente siano allineate con l'intento dichiarato dall'utente e con i vincoli di sistema.

 #9.9.1    Level: 1    Role: D
 Verificare che i risolutori di vincoli pre-esecuzione controllino le azioni proposte rispetto a regole rigide di sicurezza e di politica predefinite.
 #9.9.2    Level: 2    Role: D/V
 Verificare che le azioni ad alto impatto (finanziarie, distruttive, sensibili alla privacy) richiedano una conferma esplicita dell'intento da parte dell'utente che le avvia.
 #9.9.3    Level: 2    Role: V
 Verificare che i controlli post-condizione confermino che le azioni completate abbiano raggiunto gli effetti desiderati senza effetti collaterali; le discrepanze attivano il rollback.
 #9.9.4    Level: 3    Role: V
 Verificare che metodi formali (ad esempio, model checking, dimostrazione di teoremi) o test basati su proprietà dimostrino che i piani dell'agente soddisfano tutti i vincoli dichiarati.
 #9.9.5    Level: 3    Role: D
 Verificare che gli incidenti di incongruenza di intenti o violazione di vincoli alimentino cicli di miglioramento continuo e condivisione delle informazioni sulle minacce.

---

### 9.10 Strategia di Ragionamento dell'Agente per la Sicurezza

Selezione ed esecuzione sicura di diverse strategie di ragionamento, inclusi gli approcci ReAct, Chain-of-Thought e Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Verificare che la selezione della strategia di ragionamento utilizzi criteri deterministici (complessità dell’input, tipo di compito, contesto di sicurezza) e che input identici producano selezioni di strategia identiche all’interno dello stesso contesto di sicurezza.
 #9.10.2    Level: 1    Role: D/V
 Verifica che ogni strategia di ragionamento (ReAct, Chain-of-Thought, Tree-of-Thoughts) abbia una validazione di input dedicata, una sanificazione dell'output e limiti di tempo di esecuzione specifici per il suo approccio cognitivo.
 #9.10.3    Level: 2    Role: D/V
 Verificare che le transizioni della strategia di ragionamento siano registrate con contesto completo, inclusi le caratteristiche dell'input, i valori dei criteri di selezione e i metadati di esecuzione, per la ricostruzione della traccia di controllo.
 #9.10.4    Level: 2    Role: D/V
 Verificare che il ragionamento Tree-of-Thoughts includa meccanismi di potatura dei rami che terminano l'esplorazione quando vengono rilevate violazioni di policy, limiti di risorse o confini di sicurezza.
 #9.10.5    Level: 2    Role: D/V
 Verificare che i cicli ReAct (Reason-Act-Observe) includano punti di controllo di validazione in ogni fase: verifica del passo di ragionamento, autorizzazione dell'azione e sanificazione dell'osservazione prima di procedere.
 #9.10.6    Level: 3    Role: D/V
 Verificare che i metriche di prestazione della strategia di ragionamento (tempo di esecuzione, utilizzo delle risorse, qualità dell'output) siano monitorate con avvisi automatici quando i metriche si discostano oltre le soglie configurate.
 #9.10.7    Level: 3    Role: D/V
 Verificare che gli approcci di ragionamento ibrido che combinano più strategie mantengano la validazione dell'input e i vincoli di output di tutte le strategie costituenti senza aggirare alcun controllo di sicurezza.
 #9.10.8    Level: 3    Role: D/V
 Verificare che il testing della sicurezza della strategia di ragionamento includa il fuzzing con input malformati, prompt avversari progettati per forzare il cambio di strategia e il testing delle condizioni limite per ogni approccio cognitivo.

---

### 9.11 Gestione dello Stato del Ciclo di Vita dell'Agente e Sicurezza

Inizializzazione sicura dell'agente, transizioni di stato e terminazione con tracciamenti di controllo crittografici e procedure di recupero definite.

 #9.11.1    Level: 1    Role: D/V
 Verificare che l'inizializzazione dell'agente includa l'istituzione dell'identità crittografica con credenziali basate su hardware e registri di controllo di avvio immutabili contenenti ID agente, timestamp, hash della configurazione e parametri di inizializzazione.
 #9.11.2    Level: 2    Role: D/V
 Verificare che le transizioni di stato dell'agente siano firmate crittograficamente, corredate di timestamp e registrate con un contesto completo che includa eventi scatenanti, hash dello stato precedente, hash del nuovo stato e le validazioni di sicurezza eseguite.
 #9.11.3    Level: 2    Role: D/V
 Verificare che le procedure di arresto dell'agente includano la cancellazione sicura della memoria mediante cancellazione crittografica o sovrascrittura multipla, la revoca delle credenziali con notifica all'autorità di certificazione e la generazione di certificati di terminazione a prova di manomissione.
 #9.11.4    Level: 3    Role: D/V
 Verificare che i meccanismi di recupero degli agenti convalidino l'integrità dello stato utilizzando checksum crittografici (minimo SHA-256) e ripristinino stati noti privi di errori quando viene rilevata una corruzione, con allarmi automatizzati e requisiti di approvazione manuale.
 #9.11.5    Level: 3    Role: D/V
 Verificare che i meccanismi di persistenza dell'agente crittografino i dati di stato sensibili con chiavi AES-256 uniche per agente e implementino la rotazione sicura delle chiavi secondo programmi configurabili (massimo 90 giorni) con distribuzione a zero tempi di inattività.

---

### 9.12 Framework di Sicurezza per l'Integrazione degli Strumenti

Controlli di sicurezza per il caricamento dinamico degli strumenti, l'esecuzione e la validazione dei risultati con processi definiti di valutazione del rischio e approvazione.

 #9.12.1    Level: 1    Role: D/V
 Verificare che i descrittori degli strumenti includano metadati di sicurezza specificando i privilegi richiesti (lettura/scrittura/esecuzione), i livelli di rischio (basso/medio/alto), i limiti delle risorse (CPU, memoria, rete) e i requisiti di convalida documentati nei manifest degli strumenti.
 #9.12.2    Level: 1    Role: D/V
 Verificare che i risultati dell'esecuzione degli strumenti siano convalidati rispetto agli schemi previsti (JSON Schema, XML Schema) e alle politiche di sicurezza (sanitizzazione dell'output, classificazione dei dati) prima dell'integrazione, con limiti di timeout e procedure di gestione degli errori.
 #9.12.3    Level: 2    Role: D/V
 Verificare che i log di interazione degli strumenti includano un contesto di sicurezza dettagliato, compreso l'uso dei privilegi, i modelli di accesso ai dati, i tempi di esecuzione, il consumo di risorse e i codici di ritorno, con una registrazione strutturata per l'integrazione SIEM.
 #9.12.4    Level: 2    Role: D/V
 Verificare che i meccanismi di caricamento dinamico degli strumenti convalidino le firme digitali utilizzando l'infrastruttura PKI e implementino protocolli di caricamento sicuri con isolamento sandbox e verifica delle autorizzazioni prima dell'esecuzione.
 #9.12.5    Level: 3    Role: D/V
 Verificare che le valutazioni di sicurezza degli strumenti siano attivate automaticamente per le nuove versioni con gate di approvazione obbligatori, inclusi analisi statica, test dinamici e revisione da parte del team di sicurezza, con criteri di approvazione documentati e requisiti di SLA.

---

#### Riferimenti

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Robustezza Avversariale e Difesa della Privacy

### Obiettivo di Controllo

Garantire che i modelli di IA rimangano affidabili, rispettosi della privacy e resistenti agli abusi quando affrontano attacchi di elusione, inferenza, estrazione o avvelenamento.

---

### 10.1 Allineamento e Sicurezza del Modello

Proteggi contro output dannosi o che violano le politiche.

 #10.1.1    Level: 1    Role: D/V
 Verificare che un test-suite di allineamento (prompt di red-team, sonde di jailbreak, contenuti non consentiti) sia sotto controllo di versione e venga eseguito ad ogni rilascio del modello.
 #10.1.2    Level: 1    Role: D
 Verificare che i meccanismi di rifiuto e le barriere di completamento sicuro siano applicati correttamente.
 #10.1.3    Level: 2    Role: D/V
 Verificare che un valutatore automatico misuri il tasso di contenuti dannosi e segnali regressioni oltre una soglia prestabilita.
 #10.1.4    Level: 2    Role: D
 Verificare che l'addestramento contro il jailbreak sia documentato e riproducibile.
 #10.1.5    Level: 3    Role: V
 Verificare che le prove formali di conformità alle politiche o il monitoraggio certificato coprano domini critici.

---

### 10.2 Indurimento contro esempi avversari

Aumentare la resilienza agli input manipolati. L'addestramento avversariale robusto e la valutazione tramite benchmark sono le migliori pratiche attuali.

 #10.2.1    Level: 1    Role: D
 Verificare che i repository dei progetti includano configurazioni di addestramento avversariale con semi riproducibili.
 #10.2.2    Level: 2    Role: D/V
 Verificare che il rilevamento degli esempi avversari generi avvisi di blocco nelle pipeline di produzione.
 #10.2.4    Level: 3    Role: V
 Verificare che le prove di robustezza certificata o i certificati a intervalli coprano almeno le classi critiche principali.
 #10.2.5    Level: 3    Role: V
 Verificare che i test di regressione utilizzino attacchi adattativi per confermare l’assenza di perdita di robustezza misurabile.

---

### 10.3 Mitigazione dell'inferenza di appartenenza

Limitare la possibilità di decidere se un record era nei dati di addestramento. La privacy differenziale e la mascheratura del punteggio di confidenza rimangono le difese più efficaci conosciute.

 #10.3.1    Level: 1    Role: D
 Verificare che la regolarizzazione dell'entropia per query o la scalatura della temperatura riducano le predizioni eccessivamente sicure.
 #10.3.2    Level: 2    Role: D
 Verificare che l'addestramento impieghi un'ottimizzazione a privacy differenziale con vincolo ε per dataset sensibili.
 #10.3.3    Level: 2    Role: V
 Verificare che le simulazioni di attacco (modello ombra o black-box) mostrino un AUC di attacco ≤ 0,60 sui dati non utilizzati per l’addestramento.

---

### 10.4 Resistenza all'Inversione del Modello

Impedire la ricostruzione degli attributi privati. Recenti indagini sottolineano la troncatura dell'output e le garanzie di DP come difese pratiche.

 #10.4.1    Level: 1    Role: D
 Verificare che gli attributi sensibili non vengano mai restituiti direttamente; dove necessario, utilizzare intervalli (bucket) o trasformazioni unidirezionali.
 #10.4.2    Level: 1    Role: D/V
 Verificare che i limiti di velocità delle query limitino le query adattive ripetute dallo stesso soggetto.
 #10.4.3    Level: 2    Role: D
 Verificare che il modello sia addestrato con rumore che preserva la privacy.

---

### 10.5 Difesa contro l'Estrrazione del Modello

Rilevare e prevenire la clonazione non autorizzata. Si raccomandano tecniche di watermarking e analisi dei pattern di query.

 #10.5.1    Level: 1    Role: D
 Verificare che i gateway di inferenza impongano limiti di velocità globali e per chiave API, calibrati sulla soglia di memorizzazione del modello.
 #10.5.2    Level: 2    Role: D/V
 Verificare che le statistiche di entropia della query e pluralità degli input alimentino un rilevatore di estrazione automatica.
 #10.5.3    Level: 2    Role: V
 Verificare che i watermark fragili o probabilistici possano essere dimostrati con p < 0,01 in ≤ 1.000 interrogazioni contro un clone sospetto.
 #10.5.4    Level: 3    Role: D
 Verifica che le chiavi di watermark e i set di trigger siano memorizzati in un modulo di sicurezza hardware e ruotati annualmente.
 #10.5.5    Level: 3    Role: V
 Verificare che gli eventi di extraction-alert includano le query offender e siano integrati con i playbook di risposta agli incidenti.

---

### 10.6 Rilevamento di dati avvelenati durante il tempo di inferenza

Identificare e neutralizzare input con backdoor o avvelenati.

 #10.6.1    Level: 1    Role: D
 Verificare che gli input passino attraverso un rilevatore di anomalie (ad esempio, STRIP, punteggio di coerenza) prima dell'inferenza del modello.
 #10.6.2    Level: 1    Role: V
 Verificare che le soglie del rilevatore siano tarate su set di validazione puliti/velenosi per raggiungere meno del 5% di falsi positivi.
 #10.6.3    Level: 2    Role: D
 Verifica che gli input segnalati come contaminati attivino il blocco morbido e i flussi di lavoro di revisione umana.
 #10.6.4    Level: 2    Role: V
 Verificare che i rilevatori siano sottoposti a stress test con attacchi backdoor adattivi e senza trigger.
 #10.6.5    Level: 3    Role: D
 Verificare che le metriche di efficacia del rilevamento siano registrate e periodicamente rivalutate con nuove informazioni sulle minacce.

---

### 10.7 Adattamento Dinamico della Politica di Sicurezza

Aggiornamenti in tempo reale delle politiche di sicurezza basati su informazioni sulle minacce e analisi comportamentale.

 #10.7.1    Level: 1    Role: D/V
 Verificare che le politiche di sicurezza possano essere aggiornate dinamicamente senza riavviare l'agente, garantendo al contempo l'integrità della versione della politica.
 #10.7.2    Level: 2    Role: D/V
 Verificare che gli aggiornamenti delle politiche siano firmati crittograficamente dal personale di sicurezza autorizzato e convalidati prima dell'applicazione.
 #10.7.3    Level: 2    Role: D/V
 Verificare che le modifiche dinamiche alle policy siano registrate con tracciati di audit completi, inclusi giustificazioni, catene di approvazione e procedure di rollback.
 #10.7.4    Level: 3    Role: D/V
 Verificare che i meccanismi di sicurezza adattativi regolino la sensibilità del rilevamento delle minacce in base al contesto di rischio e ai modelli comportamentali.
 #10.7.5    Level: 3    Role: D/V
 Verificare che le decisioni di adattamento della policy siano spiegabili e includano tracce di evidenza per la revisione del team di sicurezza.

---

### 10.8 Analisi di Sicurezza Basata sulla Riflessività

Validazione della sicurezza tramite auto-riflessione dell'agente e analisi meta-cognitiva.

 #10.8.1    Level: 1    Role: D/V
 Verificare che i meccanismi di riflessione dell'agente includano un'autovalutazione delle decisioni e delle azioni focalizzata sulla sicurezza.
 #10.8.2    Level: 2    Role: D/V
 Verificare che le uscite di riflessione siano validate per prevenire la manipolazione dei meccanismi di autovalutazione da parte di input avversari.
 #10.8.3    Level: 2    Role: D/V
 Verificare che l'analisi di sicurezza meta-cognitiva identifichi potenziali pregiudizi, manipolazioni o compromissioni nei processi di ragionamento dell'agente.
 #10.8.4    Level: 3    Role: D/V
 Verificare che gli avvisi di sicurezza basati sulla riflessione attivino il monitoraggio avanzato e potenziali flussi di lavoro di intervento umano.
 #10.8.5    Level: 3    Role: D/V
 Verificare che l'apprendimento continuo dalle riflessioni sulla sicurezza migliori il rilevamento delle minacce senza degradare la funzionalità legittima.

---

### 10.9 Evoluzione e Sicurezza dell'Auto-Miglioramento

Controlli di sicurezza per sistemi agenti capaci di auto-modifica ed evoluzione.

 #10.9.1    Level: 1    Role: D/V
 Verificare che le capacità di auto-modifica siano limitate ad aree designate sicure con confini di verifica formale.
 #10.9.2    Level: 2    Role: D/V
 Verificare che le proposte di evoluzione siano sottoposte a una valutazione dell'impatto sulla sicurezza prima dell'implementazione.
 #10.9.3    Level: 2    Role: D/V
 Verificare che i meccanismi di auto-miglioramento includano capacità di rollback con verifica dell'integrità.
 #10.9.4    Level: 3    Role: D/V
 Verificare che la sicurezza del meta-apprendimento prevenga la manipolazione avversaria degli algoritmi di miglioramento.
 #10.9.5    Level: 3    Role: D/V
 Verificare che il miglioramento ricorsivo di sé stesso sia vincolato da restrizioni formali di sicurezza con dimostrazioni matematiche della convergenza.

---

#### Riferimenti

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Protezione della Privacy e Gestione dei Dati Personali

### Obiettivo di Controllo

Mantenere rigorose garanzie di privacy lungo l'intero ciclo di vita dell'IA—raccolta, addestramento, inferenza e risposta agli incidenti—affinché i dati personali siano trattati solo con consenso esplicito, ambito minimo necessario, cancellazione dimostrabile e garanzie formali di privacy.

---

### 11.1 Anonimizzazione e Minimizzazione dei Dati

 #11.1.1    Level: 1    Role: D/V
 Verificare che gli identificatori diretti e quasi-identificatori siano rimossi o trasformati tramite hash.
 #11.1.2    Level: 2    Role: D/V
 Verificare che le revisioni automatizzate misurino k-anonimato/l-diversità e segnalino quando le soglie scendono al di sotto della politica.
 #11.1.3    Level: 2    Role: V
 Verificare che i report sull'importanza delle caratteristiche del modello dimostrino l'assenza di perdite di identificatori oltre ε = 0,01 di informazione mutua.
 #11.1.4    Level: 3    Role: V
 Verificare che le dimostrazioni formali o la certificazione basata su dati sintetici mostrino un rischio di re-identificazione ≤ 0,05 anche in caso di attacchi di collegamento.

---

### 11.2 Diritto all'oblio e applicazione della cancellazione

 #11.2.1    Level: 1    Role: D/V
 Verificare che le richieste di cancellazione dei dati soggetti si propaghino ai dataset grezzi, ai checkpoint, agli embedding, ai log e ai backup entro accordi sui livelli di servizio inferiori a 30 giorni.
 #11.2.2    Level: 2    Role: D
 Verificare che le routine di "machine-unlearning" effettivamente riaddestrino o approssimino la rimozione utilizzando algoritmi certificati di unlearning.
 #11.2.3    Level: 2    Role: V
 Verificare che la valutazione del modello ombra dimostri che i record dimenticati influenzano meno dell'1% degli output dopo il processo di unlearning.
 #11.2.4    Level: 3    Role: V
 Verificare che gli eventi di cancellazione siano registrati in modo immutabile e siano verificabili per i regolatori.

---

### 11.3 Salvaguardie per la Privacy Differenziale

 #11.3.1    Level: 2    Role: D/V
 Verificare che i cruscotti di contabilità della perdita di privacy segnalino quando il valore cumulativo di ε supera le soglie di politica.
 #11.3.2    Level: 2    Role: V
 Verificare che le verifiche di privacy black-box stimino ε̂ entro il 10% del valore dichiarato.
 #11.3.3    Level: 3    Role: V
 Verificare che le dimostrazioni formali coprano tutte le rifiniture post-addestramento e gli embedding.

---

### 11.4 Limitazione dello scopo e protezione contro l'espansione non autorizzata dell'ambito

 #11.4.1    Level: 1    Role: D
 Verificare che ogni set di dati e punto di controllo del modello abbia un tag di scopo leggibile da macchina allineato al consenso originale.
 #11.4.2    Level: 1    Role: D/V
 Verificare che i monitor di runtime rilevino query incoerenti con lo scopo dichiarato e attivino un rifiuto soft.
 #11.4.3    Level: 3    Role: D
 Verificare che le policy-as-code impediscano la ridistribuzione dei modelli su nuovi domini senza revisione DPIA.
 #11.4.4    Level: 3    Role: V
 Verificare che le prove formali di tracciabilità dimostrino che ogni ciclo di vita dei dati personali rimanga all'interno dell'ambito consentito.

---

### 11.5 Gestione del Consenso e Tracciamento della Base Giuridica

 #11.5.1    Level: 1    Role: D/V
 Verificare che una piattaforma di gestione del consenso (CMP) registri lo stato di opt-in, lo scopo e il periodo di conservazione per ciascun interessato.
 #11.5.2    Level: 2    Role: D
 Verificare che le API espongano i token di consenso; i modelli devono convalidare l'ambito del token prima dell'inferenza.
 #11.5.3    Level: 2    Role: D/V
 Verificare che il consenso negato o revocato fermi le pipeline di elaborazione entro 24 ore.

---

### 11.6 Apprendimento Federato con Controlli sulla Privacy

 #11.6.1    Level: 1    Role: D
 Verificare che gli aggiornamenti del client utilizzino l'aggiunta di rumore con privacy differenziale locale prima dell'aggregazione.
 #11.6.2    Level: 2    Role: D/V
 Verificare che le metriche di addestramento siano differenzialmente private e non rivelino mai la perdita di un singolo cliente.
 #11.6.3    Level: 2    Role: V
 Verificare che l'aggregazione resistente all'avvelenamento (ad esempio, Krum/Media Tagliata) sia abilitata.
 #11.6.4    Level: 3    Role: V
 Verificare che le dimostrazioni formali dimostrino un budget ε complessivo con una perdita di utilità inferiore a 5.

---

#### Riferimenti

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Monitoraggio, Registrazione e Rilevamento di Anomalie

### Obiettivo di Controllo

Questa sezione fornisce i requisiti per offrire una visibilità in tempo reale e forense su ciò che il modello e gli altri componenti di intelligenza artificiale vedono, fanno e restituiscono, in modo che le minacce possano essere rilevate, valutate e apprese.

### C12.1 Registrazione delle Richieste e delle Risposte

 #12.1.1    Level: 1    Role: D/V
 Verificare che tutte le richieste degli utenti e le risposte del modello siano registrate con i metadati appropriati (ad esempio, timestamp, ID utente, ID sessione, versione del modello).
 #12.1.2    Level: 1    Role: D/V
 Verificare che i log siano archiviati in repository sicuri e controllati da accessi, con politiche di conservazione appropriate e procedure di backup.
 #12.1.3    Level: 1    Role: D/V
 Verificare che i sistemi di archiviazione dei log implementino la crittografia a riposo e in transito per proteggere le informazioni sensibili contenute nei log.
 #12.1.4    Level: 1    Role: D/V
 Verificare che i dati sensibili nei prompt e negli output vengano automaticamente oscurati o mascherati prima della registrazione, con regole di oscuramento configurabili per le informazioni personali identificabili (PII), le credenziali e le informazioni proprietarie.
 #12.1.5    Level: 2    Role: D/V
 Verificare che le decisioni politiche e le azioni di filtraggio per la sicurezza siano registrate con dettagli sufficienti per consentire l’audit e il debug dei sistemi di moderazione dei contenuti.
 #12.1.6    Level: 2    Role: D/V
 Verificare che l'integrità dei log sia protetta tramite, ad esempio, firme crittografiche o memorizzazione scrittura-sola.

---

### C12.2 Rilevamento degli Abusi e Segnalazione

 #12.2.1    Level: 1    Role: D/V
 Verificare che il sistema rilevi e avvisi su modelli di jailbreak noti, tentativi di iniezione di prompt e input avversari utilizzando il rilevamento basato su firme.
 #12.2.2    Level: 1    Role: D/V
 Verificare che il sistema si integri con le piattaforme esistenti di Security Information and Event Management (SIEM) utilizzando formati di log e protocolli standard.
 #12.2.3    Level: 2    Role: D/V
 Verificare che gli eventi di sicurezza arricchiti includano contesti specifici dell'IA come identificatori di modelli, punteggi di confidenza e decisioni dei filtri di sicurezza.
 #12.2.4    Level: 2    Role: D/V
 Verificare che il rilevamento delle anomalie comportamentali identifichi modelli di conversazione insoliti, tentativi di ripetizione eccessivi o comportamenti sistematici di sondaggio.
 #12.2.5    Level: 2    Role: D/V
 Verificare che i meccanismi di allerta in tempo reale notificano i team di sicurezza quando vengono rilevate potenziali violazioni delle policy o tentativi di attacco.
 #12.2.6    Level: 2    Role: D/V
 Verificare che siano incluse regole personalizzate per rilevare modelli di minacce specifici dell'IA, tra cui tentativi coordinati di jailbreak, campagne di iniezione di prompt e attacchi di estrazione del modello.
 #12.2.7    Level: 3    Role: D/V
 Verificare che i flussi di lavoro automatizzati per la risposta agli incidenti siano in grado di isolare i modelli compromessi, bloccare gli utenti maligni e gestire eventi di sicurezza critici.

---

### C12.3 Rilevamento del Drift del Modello

 #12.3.1    Level: 1    Role: D/V
 Verificare che il sistema monitori metriche di prestazione di base come accuratezza, punteggi di confidenza, latenza e tassi di errore tra le versioni del modello e i periodi di tempo.
 #12.3.2    Level: 2    Role: D/V
 Verificare che l'attivazione degli avvisi automatici avvenga quando le metriche di prestazione superano soglie di degrado predefinite o si discostano significativamente dalle linee di base.
 #12.3.3    Level: 2    Role: D/V
 Verificare che i monitor di rilevamento delle allucinazioni identifichino e segnalino i casi in cui le uscite del modello contengano informazioni fattualmente errate, incoerenti o inventate.

---

### C12.4 Telemetria delle Prestazioni e del Comportamento

 #12.4.1    Level: 1    Role: D/V
 Verificare che le metriche operative, inclusi la latenza delle richieste, il consumo di token, l'utilizzo della memoria e la capacità di elaborazione, siano raccolte e monitorate continuamente.
 #12.4.2    Level: 1    Role: D/V
 Verificare che i tassi di successo e di fallimento siano monitorati con la categorizzazione dei tipi di errore e delle loro cause principali.
 #12.4.3    Level: 2    Role: D/V
 Verificare che il monitoraggio dell'utilizzo delle risorse includa l'uso della GPU/CPU, il consumo di memoria e i requisiti di archiviazione, con notifiche in caso di superamento delle soglie.

---

### C12.5 Pianificazione ed esecuzione della risposta agli incidenti di intelligenza artificiale

 #12.5.1    Level: 1    Role: D/V
 Verificare che i piani di risposta agli incidenti affrontino specificamente gli eventi di sicurezza legati all'IA, inclusi compromissione del modello, avvelenamento dei dati e attacchi avversari.
 #12.5.2    Level: 2    Role: D/V
 Verificare che i team di risposta agli incidenti abbiano accesso a strumenti e competenze forensi specifici per l'IA per investigare il comportamento del modello e i vettori di attacco.
 #12.5.3    Level: 3    Role: D/V
 Verificare che l'analisi post-incidente includa considerazioni sul retraining del modello, aggiornamenti dei filtri di sicurezza e l'integrazione delle lezioni apprese nei controlli di sicurezza.

---

### C12.5 Rilevamento del Degrado delle Prestazioni dell'IA

Monitorare e rilevare il degrado delle prestazioni e della qualità del modello di intelligenza artificiale nel tempo.

 #12.5.1    Level: 1    Role: D/V
 Verificare che accuratezza, precisione, richiamo e punteggi F1 del modello siano continuamente monitorati e confrontati con le soglie di riferimento.
 #12.5.2    Level: 1    Role: D/V
 Verificare che il rilevamento del drift dei dati monitori i cambiamenti nella distribuzione degli input che potrebbero influire sulle prestazioni del modello.
 #12.5.3    Level: 2    Role: D/V
 Verificare che il rilevamento del drift concettuale identifichi i cambiamenti nella relazione tra input e output attesi.
 #12.5.4    Level: 2    Role: D/V
 Verificare che il degrado delle prestazioni inneschi avvisi automatici e avvii i flussi di lavoro di riaddestramento o sostituzione del modello.
 #12.5.5    Level: 3    Role: V
 Verificare che l'analisi delle cause principali del degrado colleghi il calo delle prestazioni a cambiamenti nei dati, problemi infrastrutturali o fattori esterni.

---

### C12.6 Visualizzazione DAG e Sicurezza del Flusso di Lavoro

Proteggere i sistemi di visualizzazione dei flussi di lavoro da perdite di informazioni e attacchi di manipolazione.

 #12.6.1    Level: 1    Role: D/V
 Verificare che i dati di visualizzazione del DAG siano sanitizzati per rimuovere informazioni sensibili prima della memorizzazione o della trasmissione.
 #12.6.2    Level: 1    Role: D/V
 Verificare che i controlli di accesso alla visualizzazione del flusso di lavoro garantiscano che solo gli utenti autorizzati possano visualizzare i percorsi decisionali degli agenti e le tracce del ragionamento.
 #12.6.3    Level: 2    Role: D/V
 Verificare che l'integrità dei dati del DAG sia protetta tramite firme crittografiche e meccanismi di archiviazione a prova di manomissione.
 #12.6.4    Level: 2    Role: D/V
 Verificare che i sistemi di visualizzazione dei flussi di lavoro implementino la convalida degli input per prevenire attacchi di injection tramite dati di nodi o archi manipolati.
 #12.6.5    Level: 3    Role: D/V
 Verificare che gli aggiornamenti in tempo reale del DAG siano limitati in frequenza e validati per prevenire attacchi di denial-of-service sui sistemi di visualizzazione.

---

### C12.7 Monitoraggio Proattivo del Comportamento di Sicurezza

Rilevamento e prevenzione delle minacce alla sicurezza attraverso l'analisi proattiva del comportamento degli agenti.

 #12.7.1    Level: 1    Role: D/V
 Verificare che i comportamenti proattivi degli agenti siano convalidati in termini di sicurezza prima dell'esecuzione, integrando la valutazione del rischio.
 #12.7.2    Level: 2    Role: D/V
 Verificare che le iniziative autonome includano la valutazione del contesto di sicurezza e l'analisi del panorama delle minacce.
 #12.7.3    Level: 2    Role: D/V
 Verificare che i modelli di comportamento proattivo siano analizzati per potenziali implicazioni di sicurezza e conseguenze indesiderate.
 #12.7.4    Level: 3    Role: D/V
 Verificare che le azioni proattive critiche per la sicurezza richiedano catene di approvazione esplicite con tracciamenti di controllo.
 #12.7.5    Level: 3    Role: D/V
 Verificare che il rilevamento delle anomalie comportamentali identifichi deviazioni nei modelli degli agenti proattivi che potrebbero indicare una compromissione.

---

### Riferimenti

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Supervisione Umana, Responsabilità e Governance

### Obiettivo di Controllo

Questo capitolo fornisce requisiti per mantenere la supervisione umana e catene di responsabilità chiare nei sistemi di intelligenza artificiale, garantendo spiegabilità, trasparenza e gestione etica durante tutto il ciclo di vita dell'IA.

---

### C13.1 Meccanismi di Interruttore di Sicurezza e Override

Fornire percorsi di spegnimento o rollback quando si osserva un comportamento non sicuro del sistema di intelligenza artificiale.

 #13.1.1    Level: 1    Role: D/V
 Verificare che esista un meccanismo manuale di interruzione per fermare immediatamente l'inferenza e le uscite del modello di IA.
 #13.1.2    Level: 1    Role: D
 Verificare che i controlli di override siano accessibili solo al personale autorizzato.
 #13.1.3    Level: 3    Role: D/V
 Verificare che le procedure di rollback possano ripristinare versioni precedenti del modello o operazioni in modalità sicura.
 #13.1.4    Level: 3    Role: V
 Verificare che i meccanismi di override siano testati regolarmente.

---

### C13.2 Punti di Controllo per le Decisioni con Intervento Umano

Richiedere approvazioni umane quando le poste in gioco superano le soglie di rischio predefinite.

 #13.2.1    Level: 1    Role: D/V
 Verificare che le decisioni AI ad alto rischio richiedano un'esplicita approvazione umana prima dell'esecuzione.
 #13.2.2    Level: 1    Role: D
 Verificare che le soglie di rischio siano chiaramente definite e attivino automaticamente i flussi di lavoro per la revisione umana.
 #13.2.3    Level: 2    Role: D
 Verificare che le decisioni sensibili al tempo dispongano di procedure alternative nel caso in cui l'approvazione umana non possa essere ottenuta entro i tempi previsti.
 #13.2.4    Level: 3    Role: D/V
 Verificare che le procedure di escalation definiscano livelli di autorità chiari per i diversi tipi di decisione o categorie di rischio, se applicabile.

---

### C13.3 Catena di Responsabilità e Auditabilità

Registra le azioni dell'operatore e le decisioni del modello.

 #13.3.1    Level: 1    Role: D/V
 Verificare che tutte le decisioni del sistema di IA e gli interventi umani siano registrati con timestamp, identità degli utenti e motivazioni delle decisioni.
 #13.3.2    Level: 2    Role: D
 Verificare che i log di audit non possano essere manomessi e includano meccanismi di verifica dell'integrità.

---

### C13.4 Tecniche di Intelligenza Artificiale Spiegabile

Importanza delle caratteristiche superficiali, controfattuali e spiegazioni locali.

 #13.4.1    Level: 1    Role: D/V
 Verificare che i sistemi di intelligenza artificiale forniscano spiegazioni di base per le loro decisioni in un formato leggibile dall'uomo.
 #13.4.2    Level: 2    Role: V
 Verificare che la qualità della spiegazione sia convalidata attraverso studi di valutazione umana e metriche.
 #13.4.3    Level: 3    Role: D/V
 Verificare che i punteggi di importanza delle caratteristiche o i metodi di attribuzione (SHAP, LIME, ecc.) siano disponibili per decisioni critiche.
 #13.4.4    Level: 3    Role: V
 Verificare che le spiegazioni controfattuali mostrino come gli input potrebbero essere modificati per cambiare gli esiti, se applicabile al caso d'uso e al dominio.

---

### C13.5 Schede Modello e Divulgazioni sull'Uso

Mantieni le schede del modello per l'uso previsto, le metriche di prestazione e le considerazioni etiche.

 #13.5.1    Level: 1    Role: D
 Verificare che le schede modello documentino i casi d'uso previsti, le limitazioni e le modalità di errore conosciute.
 #13.5.2    Level: 1    Role: D/V
 Verificare che le metriche di performance relative ai diversi casi d'uso applicabili siano divulgate.
 #13.5.3    Level: 2    Role: D
 Verificare che le considerazioni etiche, le valutazioni dei pregiudizi, le analisi di equità, le caratteristiche dei dati di addestramento e le limitazioni note dei dati di addestramento siano documentate e aggiornate regolarmente.
 #13.5.4    Level: 2    Role: D/V
 Verificare che le schede modello siano sottoposte a controllo di versione e mantenute durante tutto il ciclo di vita del modello con tracciamento delle modifiche.

---

### C13.6 Quantificazione dell'Incertezza

Propagare i punteggi di confidenza o le misure di entropia nelle risposte.

 #13.6.1    Level: 1    Role: D
 Verificare che i sistemi di intelligenza artificiale forniscano punteggi di confidenza o misure di incertezza con i loro output.
 #13.6.2    Level: 2    Role: D/V
 Verificare che le soglie di incertezza attivino una revisione umana aggiuntiva o percorsi decisionali alternativi.
 #13.6.3    Level: 2    Role: V
 Verificare che i metodi di quantificazione dell'incertezza siano calibrati e validati rispetto ai dati di riferimento.
 #13.6.4    Level: 3    Role: D/V
 Verificare che la propagazione dell'incertezza sia mantenuta attraverso flussi di lavoro AI multi-step.

---

### C13.7 Rapporti di Trasparenza per gli Utenti

Fornire divulgazioni periodiche su incidenti, deriva e utilizzo dei dati.

 #13.7.1    Level: 1    Role: D/V
 Verificare che le politiche di utilizzo dei dati e le pratiche di gestione del consenso degli utenti siano comunicate chiaramente alle parti interessate.
 #13.7.2    Level: 2    Role: D/V
 Verificare che le valutazioni dell'impatto dell'IA siano condotte e che i risultati siano inclusi nel reporting.
 #13.7.3    Level: 2    Role: D/V
 Verificare che i rapporti di trasparenza pubblicati regolarmente divulghino gli incidenti di intelligenza artificiale e le metriche operative con un dettaglio ragionevole.

#### Riferimenti

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Appendice A: Glossario

Questo glossario completo fornisce definizioni dei termini chiave di AI, ML e sicurezza utilizzati in tutto l'AISVS per garantire chiarezza e comprensione comune.
​
Esempio avversario: un input appositamente creato per indurre un modello di intelligenza artificiale a commettere un errore, spesso aggiungendo perturbazioni sottili impercettibili per gli esseri umani.
​
Robustezza avversaria – La robustezza avversaria nell'IA si riferisce alla capacità di un modello di mantenere le proprie prestazioni e resistere a essere ingannato o manipolato da input maligni appositamente creati per causare errori.
​
Agente – Gli agenti AI sono sistemi software che utilizzano l'intelligenza artificiale per perseguire obiettivi e completare compiti per conto degli utenti. Dimostrano capacità di ragionamento, pianificazione e memoria, e possiedono un livello di autonomia per prendere decisioni, apprendere e adattarsi.
​
AI agentico: Sistemi di intelligenza artificiale che possono operare con un certo grado di autonomia per raggiungere obiettivi, spesso prendendo decisioni e agendo senza intervento umano diretto.
​
Controllo degli Accessi Basato su Attributi (ABAC): un paradigma di controllo degli accessi in cui le decisioni di autorizzazione si basano sugli attributi dell'utente, della risorsa, dell'azione e dell'ambiente, valutati al momento della richiesta.
​
Attacco Backdoor: Un tipo di attacco di avvelenamento dei dati in cui il modello viene addestrato a rispondere in un modo specifico a determinati trigger mentre si comporta normalmente altrimenti.
​
Bias: Errori sistematici nei risultati dei modelli di IA che possono portare a risultati ingiusti o discriminatori per determinati gruppi o in contesti specifici.
​
Sfruttamento dei bias: una tecnica di attacco che sfrutta i bias noti nei modelli di IA per manipolare risultati o esiti.
​
Cedar: il linguaggio e motore di policy di Amazon per permessi dettagliati utilizzati nell'implementazione di ABAC per sistemi di intelligenza artificiale.
​
Catena di Pensiero: una tecnica per migliorare il ragionamento nei modelli linguistici generando passaggi intermedi di ragionamento prima di produrre una risposta finale.
​
Interruttori automatici: meccanismi che interrompono automaticamente le operazioni del sistema AI quando vengono superate soglie di rischio specifiche.
​
Perdita di dati: esposizione non intenzionale di informazioni sensibili attraverso output o comportamenti del modello di IA.
​
Avvelenamento dei dati: La corruzione deliberata dei dati di addestramento per compromettere l'integrità del modello, spesso per installare backdoor o degradare le prestazioni.
​
Privacy Differenziale – La privacy differenziale è un quadro matematicamente rigoroso per rilasciare informazioni statistiche su set di dati proteggendo allo stesso tempo la privacy dei singoli individui. Consente al detentore dei dati di condividere modelli aggregati del gruppo limitando le informazioni trapelate riguardo a individui specifici.
​
Embedding: rappresentazioni vettoriali dense di dati (testo, immagini, ecc.) che catturano il significato semantico in uno spazio ad alta dimensione.
​
Spiegabilità – La spiegabilità nell’IA è la capacità di un sistema di intelligenza artificiale di fornire motivazioni comprensibili all’essere umano per le sue decisioni e predizioni, offrendo approfondimenti sul suo funzionamento interno.
​
Intelligenza Artificiale Spiegabile (XAI): Sistemi di intelligenza artificiale progettati per fornire spiegazioni comprensibili agli esseri umani riguardo alle loro decisioni e comportamenti attraverso varie tecniche e framework.
​
Apprendimento Federato: un approccio di machine learning in cui i modelli vengono addestrati su più dispositivi decentralizzati che possiedono dati locali, senza scambiare i dati stessi.
​
Barriere di sicurezza: vincoli implementati per impedire ai sistemi di intelligenza artificiale di produrre output dannosi, faziosi o altrimenti indesiderati.
​
Allucinazione – Un'allucinazione dell'IA si riferisce a un fenomeno in cui un modello di intelligenza artificiale genera informazioni errate o fuorvianti che non si basano sui dati di addestramento o sulla realtà fattuale.
​
Human-in-the-Loop (HITL): Sistemi progettati per richiedere supervisione, verifica o intervento umano nei punti decisionali cruciali.
​
Infrastructure as Code (IaC): Gestione e provisioning dell'infrastruttura tramite codice anziché processi manuali, consentendo scansioni di sicurezza e distribuzioni coerenti.
​
Jailbreak: Tecniche utilizzate per aggirare le protezioni di sicurezza nei sistemi di intelligenza artificiale, in particolare nei grandi modelli di linguaggio, per produrre contenuti proibiti.
​
Minimo privilegio: il principio di sicurezza che consiste nel concedere solo i diritti di accesso minimi necessari agli utenti e ai processi.
​
LIME (Spiegazioni Locali Interpretabili Agnostiche al Modello): una tecnica per spiegare le predizioni di qualsiasi classificatore di machine learning approssimandolo localmente con un modello interpretabile.
​
Attacco di Inferenza sulla Membri: Un attacco che mira a determinare se un punto dati specifico è stato utilizzato per addestrare un modello di apprendimento automatico.
​
MITRE ATLAS: Paesaggio delle minacce avversarie per i sistemi di intelligenza artificiale; una base di conoscenza di tattiche e tecniche avversarie contro i sistemi di IA.
​
Scheda del Modello – Una scheda del modello è un documento che fornisce informazioni standardizzate sulle prestazioni di un modello di intelligenza artificiale, le limitazioni, gli usi previsti e le considerazioni etiche per promuovere la trasparenza e uno sviluppo responsabile dell'IA.
​
Estrazione del Modello: Un attacco in cui un avversario interroga ripetutamente un modello target per creare una copia funzionalmente simile senza autorizzazione.
​
Inversione del modello: un attacco che tenta di ricostruire i dati di addestramento analizzando gli output del modello.
​
Gestione del Ciclo di Vita del Modello – La Gestione del Ciclo di Vita del Modello AI è il processo di supervisione di tutte le fasi dell'esistenza di un modello AI, inclusi progettazione, sviluppo, implementazione, monitoraggio, manutenzione e eventuale ritiro, per garantire che rimanga efficace e allineato agli obiettivi.
​
Avvelenamento del modello: introduzione di vulnerabilità o backdoor direttamente in un modello durante il processo di addestramento.
​
Furto/Estrazione del Modello: Ottenere una copia o un'approssimazione di un modello proprietario tramite interrogazioni ripetute.
​
Sistema multi-agente: un sistema composto da molteplici agenti di intelligenza artificiale interagenti, ciascuno con potenzialmente diverse capacità e obiettivi.
​
OPA (Open Policy Agent): Un motore di policy open-source che consente l'applicazione unificata delle policy attraverso l'intero stack.
​
Apprendimento Automatico Privacy-Preserving (PPML): Tecniche e metodi per addestrare e implementare modelli di ML proteggendo la privacy dei dati di addestramento.
​
Iniezione di Prompt: Un attacco in cui istruzioni malevoli sono inserite negli input per sovrascrivere il comportamento previsto di un modello.
​
RAG (Generazione Incrementata dal Recupero): Una tecnica che migliora i modelli di linguaggio di grandi dimensioni recuperando informazioni rilevanti da fonti di conoscenza esterne prima di generare una risposta.
​
Red-Teaming: La pratica di testare attivamente i sistemi di intelligenza artificiale simulando attacchi avversari per identificare le vulnerabilità.
​
SBOM (Elenco dei Componenti del Software): Un registro formale che contiene i dettagli e le relazioni della catena di fornitura di vari componenti utilizzati nella costruzione di software o modelli di intelligenza artificiale.
​
SHAP (SHapley Additive exPlanations): Un approccio basato sulla teoria dei giochi per spiegare l'output di qualsiasi modello di machine learning calcolando il contributo di ogni caratteristica alla previsione.
​
Attacco alla catena di approvvigionamento: Compromettere un sistema prendendo di mira gli elementi meno sicuri nella sua catena di approvvigionamento, come librerie di terze parti, dataset o modelli pre-addestrati.
​
Apprendimento per trasferimento: una tecnica in cui un modello sviluppato per un compito viene riutilizzato come punto di partenza per un modello destinato a un secondo compito.
​
Database vettoriale: un database specializzato progettato per memorizzare vettori ad alta dimensionalità (embedding) e eseguire ricerche di similarità efficienti.
​
Scansione delle vulnerabilità: strumenti automatizzati che identificano vulnerabilità di sicurezza note nei componenti software, inclusi framework di intelligenza artificiale e dipendenze.
​
Filigranatura: Tecniche per incorporare marcatori impercettibili nei contenuti generati dall'IA per tracciare la loro origine o rilevare la generazione tramite IA.
​
Vulnerabilità Zero-Day: Una vulnerabilità precedentemente sconosciuta che gli aggressori possono sfruttare prima che gli sviluppatori creino e distribuiscano una patch.

## Appendice B: Riferimenti

### TODO

## Appendice C: Governance e Documentazione della Sicurezza AI

### Obiettivo

Questo appendix fornisce i requisiti fondamentali per stabilire strutture organizzative, politiche e processi per governare la sicurezza dell'IA durante l'intero ciclo di vita del sistema.

---

### AC.1 Adozione del Framework di Gestione del Rischio AI

Fornire un quadro formale per identificare, valutare e mitigare i rischi specifici dell'IA durante l'intero ciclo di vita del sistema.

 #AC.1.1    Level: 1    Role: D/V
 Verificare che una metodologia di valutazione del rischio specifica per l'IA sia documentata e implementata.
 #AC.1.2    Level: 2    Role: D
 Verificare che le valutazioni del rischio vengano condotte nei punti chiave del ciclo di vita dell'IA e prima di cambiamenti significativi.
 #AC.1.3    Level: 3    Role: D/V
 Verificare che il framework di gestione del rischio sia conforme agli standard stabiliti (ad esempio, NIST AI RMF).

---

### AC.2 Politica e Procedure di Sicurezza per l'IA

Definire e far rispettare gli standard organizzativi per lo sviluppo, il deployment e l'operazione sicuri dell'IA.

 #AC.2.1    Level: 1    Role: D/V
 Verificare che esistano politiche di sicurezza per l'IA documentate.
 #AC.2.2    Level: 2    Role: D
 Verificare che le politiche siano riesaminate e aggiornate almeno annualmente e dopo cambiamenti significativi nel panorama delle minacce.
 #AC.2.3    Level: 3    Role: D/V
 Verificare che le politiche coprano tutte le categorie AISVS e i requisiti normativi applicabili.

---

### AC.3 Ruoli e Responsabilità per la Sicurezza dell'IA

Stabilire una chiara responsabilità per la sicurezza dell'IA in tutta l'organizzazione.

 #AC.3.1    Level: 1    Role: D/V
 Verificare che i ruoli e le responsabilità per la sicurezza dell'IA siano documentati.
 #AC.3.2    Level: 2    Role: D
 Verificare che le persone responsabili posseggano competenze adeguate in materia di sicurezza.
 #AC.3.3    Level: 3    Role: D/V
 Verificare che sia stato istituito un comitato etico per l'IA o un consiglio di governance per i sistemi di IA ad alto rischio.

---

### AC.4 Applicazione delle linee guida sull'IA etica

Garantire che i sistemi di intelligenza artificiale operino secondo principi etici consolidati.

 #AC.4.1    Level: 1    Role: D/V
 Verificare che esistano linee guida etiche per lo sviluppo e l'implementazione dell'IA.
 #AC.4.2    Level: 2    Role: D
 Verificare che siano presenti meccanismi per rilevare e segnalare violazioni etiche.
 #AC.4.3    Level: 3    Role: D/V
 Verificare che vengano eseguite revisioni etiche regolari sui sistemi di IA implementati.

---

### AC.5 Monitoraggio della conformità normativa sull'IA

Mantenere consapevolezza e conformità con le normative AI in evoluzione.

 #AC.5.1    Level: 1    Role: D/V
 Verificare che esistano processi per identificare le normative AI applicabili.
 #AC.5.2    Level: 2    Role: D
 Verificare che la conformità a tutti i requisiti normativi sia valutata.
 #AC.5.3    Level: 3    Role: D/V
 Verificare che le modifiche normative attivino revisioni e aggiornamenti tempestivi ai sistemi di intelligenza artificiale.

#### Riferimenti

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Appendice D: Governance e Verifica della Programmazione Sicura Assistita da AI

### Obiettivo

Questo capitolo definisce i controlli organizzativi di base per l'uso sicuro ed efficace degli strumenti di codifica assistita da IA durante lo sviluppo del software, garantendo sicurezza e tracciabilità lungo l'intero ciclo di vita del software (SDLC).

---

### AD.1 Flusso di lavoro per la programmazione sicura assistita dall'IA

Integrare gli strumenti di intelligenza artificiale nel ciclo di vita dello sviluppo software sicuro (SSDLC) dell'organizzazione senza indebolire le attuali barriere di sicurezza.

 #AD.1.1    Level: 1    Role: D/V
 Verificare che un flusso di lavoro documentato descriva quando e come gli strumenti di IA possono generare, rifattorizzare o revisionare il codice.
 #AD.1.2    Level: 2    Role: D
 Verificare che il flusso di lavoro corrisponda a ogni fase del SSDLC (design, implementazione, revisione del codice, testing, deployment).
 #AD.1.3    Level: 3    Role: D/V
 Verificare che le metriche (ad esempio, densità delle vulnerabilità, tempo medio di rilevamento) siano raccolte sul codice prodotto dall'IA e confrontate con i parametri di riferimento esclusivamente umani.

---

### AD.2 Qualificazione degli Strumenti di IA e Modellazione delle Minacce

Assicurarsi che gli strumenti di codifica basati su AI vengano valutati per le capacità di sicurezza, il rischio e l'impatto sulla catena di fornitura prima dell'adozione.

 #AD.2.1    Level: 1    Role: D/V
 Verificare che un modello di minaccia per ogni strumento di intelligenza artificiale identifichi rischi di uso improprio, inversione del modello, perdita di dati e rischi della catena di dipendenza.
 #AD.2.2    Level: 2    Role: D
 Verificare che le valutazioni degli strumenti includano l'analisi statica/dinamica di eventuali componenti locali e la valutazione degli endpoint SaaS (TLS, autenticazione/autorizzazione, logging).
 #AD.2.3    Level: 3    Role: D/V
 Verificare che le valutazioni seguano un quadro riconosciuto e vengano ripetute dopo cambiamenti significativi di versione.

---

### AD.3 Gestione Sicura di Prompt e Contesto

Prevenire la fuoriuscita di segreti, codice proprietario e dati personali durante la costruzione di prompt o contesti per modelli di intelligenza artificiale.

 #AD.3.1    Level: 1    Role: D/V
 Verificare che le linee guida scritte vietino l'invio di segreti, credenziali o dati riservati nei prompt.
 #AD.3.2    Level: 2    Role: D
 Verificare che i controlli tecnici (redazione lato client, filtri di contesto approvati) rimuovano automaticamente gli artefatti sensibili.
 #AD.3.3    Level: 3    Role: D/V
 Verificare che i prompt e le risposte siano tokenizzati, criptati durante il transito e a riposo, e che i periodi di conservazione siano conformi alla politica di classificazione dei dati.

---

### AD.4 Validazione del codice generato dall'IA

Individua e correggi le vulnerabilità introdotte dall'output dell'IA prima che il codice venga unito o distribuito.

 #AD.4.1    Level: 1    Role: D/V
 Verificare che il codice generato da AI sia sempre sottoposto a revisione umana del codice.
 #AD.4.2    Level: 2    Role: D
 Verificare che gli scanner automatizzati (SAST/IAST/DAST) vengano eseguiti su ogni pull request contenente codice generato dall'IA e bloccare le fusioni in caso di rilevamenti critici.
 #AD.4.3    Level: 3    Role: D/V
 Verificare che il differential fuzz testing o i test basati su proprietà dimostrino comportamenti critici per la sicurezza (ad esempio, la convalida dell'input, la logica di autorizzazione).

---

### AD.5 Spiegabilità e Tracciabilità dei Suggerimenti di Codice

Fornire agli auditor e agli sviluppatori una comprensione del motivo per cui è stata fatta una proposta e di come si è evoluta.

 #AD.5.1    Level: 1    Role: D/V
 Verificare che le coppie prompt/risposta siano registrate con gli ID di commit.
 #AD.5.2    Level: 2    Role: D
 Verificare che gli sviluppatori possano mostrare citazioni del modello (frammenti di addestramento, documentazione) a supporto di un suggerimento.
 #AD.5.3    Level: 3    Role: D/V
 Verificare che i report di spiegabilità siano archiviati insieme agli artefatti di progettazione e referenziati nelle revisioni di sicurezza, soddisfacendo i principi di tracciabilità ISO/IEC 42001.

---

### AD.6 Feedback Continuo e Messa a Punto del Modello

Migliorare nel tempo le prestazioni di sicurezza del modello prevenendo la deriva negativa.

 #AD.6.1    Level: 1    Role: D/V
 Verificare che gli sviluppatori possano segnalare suggerimenti non sicuri o non conformi e che le segnalazioni siano monitorate.
 #AD.6.2    Level: 2    Role: D
 Verificare che il feedback aggregato informi il fine-tuning periodico o la generazione aumentata da retrieval con corpora di codifica sicura verificati (ad esempio, le OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verificare che un sistema di valutazione a circuito chiuso esegua test di regressione dopo ogni fine-tuning; le metriche di sicurezza devono soddisfare o superare i livelli di riferimento precedenti prima della distribuzione.

---

#### Riferimenti

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Appendice E: Esempi di Strumenti e Framework

### Obiettivo

Questo capitolo fornisce esempi di strumenti e framework che possono supportare l'implementazione o il soddisfacimento di un requisito AISVS specifico. Questi non devono essere considerati come raccomandazioni o approvazioni da parte del team AISVS o del progetto OWASP GenAI Security.

---

### AE.1 Governance dei Dati di Addestramento e Gestione dei Bias

Strumenti utilizzati per l'analisi dei dati, la governance e la gestione dei bias.

 #AE.1.1    Section: 1.1
 Strumenti per l'inventario dei dati: Strumenti per la gestione dell'inventario dei dati come...
 #AE.1.2    Section: 1.2
 Crittografia in Transito Usa TLS per applicazioni basate su HTTPS, con strumenti come openSSL e Python's`ssl`biblioteca.

---

### AE.2 Validazione dell'input utente

Strumenti per gestire e convalidare gli input degli utenti.

 #AE.2.1    Section: 2.1
 Strumenti di Difesa contro l'Iniezione di Prompt: Utilizzare strumenti di protezione come NeMo di NVIDIA o Guardrails AI.

---

## Governance dei dati di addestramento C1 e gestione del bias

### C1.1 Provenienza dei Dati di Addestramento

Mantieni un inventario verificabile di tutti i set di dati, accetta solo fonti affidabili e registra ogni modifica per garantirne la tracciabilità.

 #1.1.1    Level: 1    Role: D/V
 Verificare che venga mantenuto un inventario aggiornato di ogni fonte di dati di addestramento (origine, responsabile/proprietario, licenza, metodo di raccolta, vincoli d'uso previsti e storico di elaborazione).

