# Gestione del Ciclo di Vita del Modello C3 e Controllo delle Modifiche

## Obiettivo di Controllo

I sistemi di intelligenza artificiale devono implementare processi di controllo delle modifiche che impediscano modifiche non autorizzate o non sicure del modello di raggiungere la produzione. Questo controllo garantisce l'integrità del modello durante l'intero ciclo di vita, dallo sviluppo al dispiegamento fino alla dismissione, permettendo una rapida risposta agli incidenti e mantenendo la responsabilità per tutte le modifiche.

Obiettivo principale di sicurezza: solo modelli autorizzati e validati raggiungono la produzione attraverso processi controllati che mantengono integrità, tracciabilità e recuperabilità.

---

## C3.1 Autorizzazione e Integrità del Modello

Solo i modelli autorizzati con integrità verificata raggiungono gli ambienti di produzione.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Verificare che tutti gli artefatti del modello (pesi, configurazioni, tokenizer) siano firmati crittograficamente da entità autorizzate prima del deployment.                                                                                |   1   | D/V  |
| 3.1.2 | Verificare che l'integrità del modello venga convalidata al momento del deployment e che i fallimenti della verifica della firma impediscano il caricamento del modello.                                                                     |   1   | D/V  |
| 3.1.3 | Verificare che i record di provenienza del modello includano l'identità dell'entità autorizzante, i checksum dei dati di addestramento, i risultati del test di validazione con stato di superamento/fallimento e un timestamp di creazione. |   2   | D/V  |
| 3.1.4 | Verificare che tutti gli artefatti del modello utilizzino la versionatura semantica (MAJOR.MINOR.PATCH) con criteri documentati che specificano quando incrementare ciascuna componente della versione.                                      |   2   | D/V  |
| 3.1.5 | Verificare che il tracciamento delle dipendenze mantenga un inventario in tempo reale che consenta un'identificazione rapida di tutti i sistemi che utilizzano tali dipendenze.                                                              |   2   |  V   |

---

## C3.2 Validazione e Test del Modello

I modelli devono superare le validazioni di sicurezza e protezione definite prima della distribuzione.

|   #   | Description                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.2.1 | Verificare che i modelli siano sottoposti a test di sicurezza automatizzati che includano la convalida degli input, la sanitizzazione degli output e le valutazioni di sicurezza con soglie di superamento/prestazione concordate preventivamente dall'organizzazione prima della distribuzione. |   1   | D/V  |
| 3.2.2 | Verificare che i fallimenti di validazione blocchino automaticamente il deployment del modello dopo l'approvazione esplicita da parte del personale autorizzato pre-designato, con giustificazioni aziendali documentate.                                                                        |   1   | D/V  |
| 3.2.3 | Verificare che i risultati del test siano firmati crittograficamente e collegati in modo immutabile all'hash della specifica versione del modello che si sta validando.                                                                                                                          |   2   |  V   |
| 3.2.4 | Verificare che le distribuzioni d'emergenza richiedano una valutazione documentata del rischio di sicurezza e l'approvazione da parte di un'autorità di sicurezza predesignata entro i tempi prefissati.                                                                                         |   2   | D/V  |

---

## C3.3 Distribuzione Controllata e Ripristino

Le implementazioni dei modelli devono essere controllate, monitorate e reversibili.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Verificare che le distribuzioni in produzione implementino meccanismi di rollout graduale (distribuzioni canary, distribuzioni blue-green) con trigger automatici di rollback basati su tassi di errore, soglie di latenza o criteri di allerta di sicurezza predefiniti. |   1   |  D   |
| 3.3.2 | Verificare che le capacità di rollback ripristinino lo stato completo del modello (pesi, configurazioni, dipendenze) in modo atomico all'interno delle finestre temporali predefinite dall'organizzazione.                                                                |   1   | D/V  |
| 3.3.3 | Verificare che i processi di distribuzione convalidino le firme crittografiche e calcolino somme di controllo per l'integrità prima dell'attivazione del modello, bloccando la distribuzione in caso di qualsiasi discrepanza.                                            |   2   | D/V  |
| 3.3.4 | Verificare che le capacità di spegnimento di emergenza del modello possano disabilitare gli endpoint del modello entro tempi di risposta predefiniti tramite interruttori automatici di circuito o interruttori di spegnimento manuali.                                   |   2   | D/V  |
| 3.3.5 | Verificare che gli artefatti di rollback (versioni precedenti del modello, configurazioni, dipendenze) siano conservati secondo le politiche organizzative con archiviazione immutabile per la risposta agli incidenti.                                                   |   2   |  V   |

---

## C3.4 Responsabilità delle Modifiche e Audit

Tutte le modifiche del ciclo di vita del modello devono essere tracciabili e verificabili.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Verificare che tutte le modifiche al modello (deploy, configurazione, disattivazione) generino registrazioni di audit immutabili che includano un timestamp, un'identità dell'attore autenticata, un tipo di modifica e gli stati precedente e successivo.                          |   1   |  V   |
| 3.4.2 | Verificare che l'accesso al registro di audit richieda un'autorizzazione appropriata e che tutti i tentativi di accesso siano registrati con l'identità dell'utente e un timestamp.                                                                                                 |   2   | D/V  |
| 3.4.3 | Verificare che i modelli di prompt e i messaggi di sistema siano controllati nella versione tramite repository git con revisione del codice obbligatoria e approvazione da parte di revisori designati prima del rilascio.                                                          |   2   | D/V  |
| 3.4.4 | Verificare che i registri di controllo includano dettagli sufficienti (hash del modello, snapshot delle configurazioni, versioni delle dipendenze) per consentire la completa ricostruzione dello stato del modello per qualsiasi momento all'interno del periodo di conservazione. |   2   |  V   |

---

## C3.5 Pratiche di Sviluppo Sicuro

I processi di sviluppo e addestramento del modello devono seguire pratiche sicure per prevenire compromissioni.

|   #   | Description                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.5.1 | Verificare che gli ambienti di sviluppo, test e produzione del modello siano separati fisicamente o logicamente. Non devono condividere infrastrutture, devono avere controlli di accesso distinti e archivi dati isolati.                                               |   1   |  D   |
| 3.5.2 | Verificare che l'addestramento del modello e il fine-tuning avvengano in ambienti isolati con accesso di rete controllato.                                                                                                                                               |   1   |  D   |
| 3.5.3 | Verificare che le fonti dei dati di addestramento siano validate tramite controlli di integrità e autenticate attraverso fonti fidate con una catena di custodia documentata prima dell'uso nello sviluppo del modello.                                                  |   1   | D/V  |
| 3.5.4 | Verificare che gli artefatti di sviluppo del modello (iperparametri, script di addestramento, file di configurazione) siano archiviati nel controllo delle versioni e richiedano l'approvazione di una revisione tra pari prima di essere utilizzati nell'addestramento. |   2   |  D   |

---

## C3.6 Ritiro e dismissione del modello

I modelli devono essere ritirati in modo sicuro quando non sono più necessari o quando vengono identificati problemi di sicurezza.

|   #   | Description                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Verificare che i processi di ritiro del modello scansionino automaticamente i grafici di dipendenza, identifichino tutti i sistemi consumatori e forniscano periodi di preavviso concordati prima della dismissione.                                      |   1   |  D   |
| 3.6.2 | Verificare che i modelli ritirati siano cancellati in modo sicuro utilizzando l'eliminazione crittografica o la sovrascrittura multipla secondo le politiche di conservazione dei dati documentate, con certificati di distruzione verificati.            |   1   | D/V  |
| 3.6.3 | Verificare che gli eventi di dismissione del modello siano registrati con timestamp e identità dell'attore, e che le firme del modello vengano revocate per prevenire il riutilizzo.                                                                      |   2   |  V   |
| 3.6.4 | Verificare che il ritiro d'emergenza del modello possa disabilitare l'accesso al modello entro i tempi di risposta di emergenza predefiniti tramite interruttori di spegnimento automatici in caso di rilevamento di vulnerabilità di sicurezza critiche. |   2   | D/V  |

---

## Riferimenti

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

