# Controllo di Accesso C5 e Identità per Componenti e Utenti AI

## Obiettivo di Controllo

Il controllo accessi efficace per i sistemi di IA richiede una gestione robusta delle identità, un’autorizzazione consapevole del contesto e un’applicazione in tempo reale basata sui principi di zero-trust. Questi controlli garantiscono che esseri umani, servizi e agenti autonomi interagiscano solo con modelli, dati e risorse computazionali entro ambiti esplicitamente concessi, con capacità di verifica continua e audit.

---

## C5.1 Gestione dell'Identità e Autenticazione

Stabilire identità supportate da crittografia per tutte le entità con autenticazione multi-fattore per operazioni privilegiate.

|   #   | Description                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Verificare che tutti gli utenti umani e i service principal si autentichino tramite un provider di identità aziendale centralizzato (IdP) utilizzando i protocolli OIDC/SAML con mappature univoche identità-token (nessun account o credenziali condivise).                                   |   1   | D/V  |
| 5.1.2 | Verificare che le operazioni ad alto rischio (implementazione del modello, esportazione dei pesi, accesso ai dati di addestramento, modifiche alla configurazione di produzione) richiedano l'autenticazione multi-fattore o un'autenticazione aumentata con la ri-validazione della sessione. |   1   | D/V  |
| 5.1.3 | Verificare che i nuovi responsabili sottopongano a un processo di verifica dell'identità conforme al NIST 800-63-3 IAL-2 o a standard equivalenti prima di ricevere l'accesso ai sistemi di produzione.                                                                                        |   2   |  D   |
| 5.1.4 | Verificare che le revisioni degli accessi siano effettuate trimestralmente con rilevamento automatico degli account inattivi, applicazione della rotazione delle credenziali e flussi di lavoro per la de-provisioning.                                                                        |   2   |  V   |
| 5.1.5 | Verificare che gli agenti AI federati si autentichino tramite asserzioni JWT firmate che abbiano una durata massima di 24 ore e includano una prova crittografica di origine.                                                                                                                  |   3   | D/V  |

---

## C5.2 Autorizzazione delle Risorse e Privilegio Minimo

Implementare controlli di accesso dettagliati per tutte le risorse di intelligenza artificiale con modelli di autorizzazione espliciti e tracciamenti di audit.

|   #   | Description                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Verificare che ogni risorsa AI (dataset, modelli, endpoint, raccolte vettoriali, indici di embedding, istanze di calcolo) applichi controlli di accesso basati sui ruoli con liste di autorizzazione esplicite e politiche di diniego predefinito.               |   1   | D/V  |
| 5.2.2 | Verificare che i principi del minimo privilegio siano applicati di default agli account di servizio, iniziando con permessi in sola lettura e richiedendo una giustificazione aziendale documentata per l’accesso in scrittura.                                  |   1   | D/V  |
| 5.2.3 | Verificare che tutte le modifiche al controllo degli accessi siano collegate a richieste di modifica approvate e registrate in modo immutabile con timestamp, identità degli attori, identificatori delle risorse e delta delle autorizzazioni.                  |   1   |  V   |
| 5.2.4 | Verificare che le etichette di classificazione dei dati (PII, PHI, controllati per l'esportazione, proprietari) si propaghino automaticamente alle risorse derivate (embedding, cache dei prompt, output del modello) con un'applicazione coerente delle policy. |   2   |  D   |
| 5.2.5 | Verificare che i tentativi di accesso non autorizzati e gli eventi di escalation dei privilegi attivino avvisi in tempo reale con metadati contestuali ai sistemi SIEM entro 5 minuti.                                                                           |   2   | D/V  |

---

## C5.3 Valutazione Dinamica delle Policy

Distribuire motori di controllo degli accessi basati su attributi (ABAC) per decisioni di autorizzazione consapevoli del contesto con capacità di audit.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Verificare che le decisioni di autorizzazione siano esternalizzate a un motore di policy dedicato (OPA, Cedar o equivalente) accessibile tramite API autenticati con protezione dell'integrità crittografica.                                                  |   1   | D/V  |
| 5.3.2 | Verificare che le policy valutino gli attributi dinamici in fase di esecuzione, inclusi il livello di autorizzazione dell'utente, la classificazione di sensibilità della risorsa, il contesto della richiesta, l'isolamento del tenant e i vincoli temporali. |   1   | D/V  |
| 5.3.3 | Verificare che le definizioni delle policy siano gestite con controllo delle versioni, revisionate da pari e validate tramite test automatizzati nelle pipeline CI/CD prima del deployment in produzione.                                                      |   2   |  D   |
| 5.3.4 | Verificare che i risultati della valutazione delle policy includano motivazioni decisionali strutturate e siano trasmessi ai sistemi SIEM per l'analisi di correlazione e la reportistica di conformità.                                                       |   2   |  V   |
| 5.3.5 | Verificare che i valori del time-to-live (TTL) della cache delle policy non superino i 5 minuti per le risorse ad alta sensibilità e 1 ora per le risorse standard con capacità di invalidazione della cache.                                                  |   3   | D/V  |

---

## C5.4 Applicazione della Sicurezza in Tempo di Query

Implementare controlli di sicurezza a livello di database con filtraggio obbligatorio e politiche di sicurezza a livello di riga.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Verificare che tutte le query per database vettoriali e SQL includano filtri di sicurezza obbligatori (ID tenant, etichette di sensibilità, ambito utente) applicati a livello del motore di database, non nel codice applicativo.                      |   1   | D/V  |
| 5.4.2 | Verificare che le politiche di sicurezza a livello di riga (RLS) e la mascheratura a livello di campo siano abilitate con l’ereditarietà delle politiche per tutti i database vettoriali, gli indici di ricerca e i dataset di addestramento.           |   1   | D/V  |
| 5.4.3 | Verificare che le valutazioni di autorizzazione fallite impediscano gli "attacchi del deputy confuso" interrompendo immediatamente le query e restituendo codici di errore di autorizzazione espliciti invece di restituire insiemi di risultati vuoti. |   2   |  D   |
| 5.4.4 | Verificare che la latenza di valutazione delle politiche sia monitorata continuamente con avvisi automatizzati per condizioni di timeout che potrebbero consentire il bypass dell'autorizzazione.                                                       |   2   |  V   |
| 5.4.5 | Verificare che i meccanismi di ritentativo delle query rivalutino le politiche di autorizzazione per tenere conto delle modifiche dinamiche dei permessi durante le sessioni utente attive.                                                             |   3   | D/V  |

---

## Filtraggio Output C5.5 e Prevenzione della Perdita di Dati

Implementare controlli di post-elaborazione per prevenire la divulgazione non autorizzata di dati nei contenuti generati dall'IA.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.5.1 | Verificare che i meccanismi di filtraggio post-inferenza eseguano la scansione e la cancellazione di PII non autorizzate, informazioni classificate e dati proprietari prima di consegnare i contenuti ai richiedenti.   |   1   | D/V  |
| 5.5.2 | Verificare che citazioni, riferimenti e attribuzioni delle fonti nei risultati del modello siano convalidati rispetto ai diritti di accesso del chiamante e rimossi se viene rilevato un accesso non autorizzato.        |   1   | D/V  |
| 5.5.3 | Verificare che le restrizioni sul formato di output (PDF sanitizzati, immagini senza metadati, tipi di file approvati) siano applicate in base ai livelli di autorizzazione dell'utente e alle classificazioni dei dati. |   2   |  D   |
| 5.5.4 | Verificare che gli algoritmi di cancellazione siano deterministici, controllati in versione e mantengano registri di audit per supportare le indagini di conformità e l'analisi forense.                                 |   2   |  V   |
| 5.5.5 | Verificare che gli eventi di redazione ad alto rischio generino log adattivi che includano hash crittografici del contenuto originale per il recupero forense senza esposizione dei dati.                                |   3   |  V   |

---

## C5.6 Isolamento Multi-Tenant

Garantire l'isolamento crittografico e logico tra i tenant in un'infrastruttura di intelligenza artificiale condivisa.

|   #   | Description                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Verificare che gli spazi di memoria, gli archivi di embedding, le voci della cache e i file temporanei siano segregati per namespace per ogni tenant, con una cancellazione sicura al momento della cancellazione del tenant o della terminazione della sessione. |   1   | D/V  |
| 5.6.2 | Verificare che ogni richiesta API includa un identificatore tenant autenticato che sia convalidato crittograficamente rispetto al contesto della sessione e ai diritti dell'utente.                                                                               |   1   | D/V  |
| 5.6.3 | Verificare che le policy di rete implementino regole di negazione predefinite per la comunicazione tra tenant diversi all'interno di service mesh e piattaforme di orchestrazione di container.                                                                   |   2   |  D   |
| 5.6.4 | Verificare che le chiavi di crittografia siano uniche per ogni tenant con supporto per chiavi gestite dal cliente (CMK) e isolamento crittografico tra gli archivi dati dei tenant.                                                                               |   3   |  D   |

---

## C5.7 Autorizzazione dell'Agente Autonomo

Controllo dei permessi per agenti AI e sistemi autonomi tramite token di capacità con ambito definito e autorizzazione continua.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Verificare che gli agenti autonomi ricevano token di capacità limitata che elencano esplicitamente le azioni consentite, le risorse accessibili, i confini temporali e i vincoli operativi.                                                                                         |   1   | D/V  |
| 5.7.2 | Verificare che le funzionalità ad alto rischio (accesso al file system, esecuzione di codice, chiamate API esterne, transazioni finanziarie) siano disabilitate per impostazione predefinita e richiedano autorizzazioni esplicite per l’attivazione con giustificazioni aziendali. |   1   | D/V  |
| 5.7.3 | Verificare che i token di capacità siano associati alle sessioni utente, includano una protezione crittografica dell'integrità e garantire che non possano essere conservati o riutilizzati in scenari offline.                                                                     |   2   |  D   |
| 5.7.4 | Verificare che le azioni avviate dall'agente siano soggette a una seconda autorizzazione tramite il motore di policy ABAC con valutazione completa del contesto e registrazione degli audit.                                                                                        |   2   |  V   |
| 5.7.5 | Verificare che le condizioni di errore dell'agente e la gestione delle eccezioni includano informazioni sull'ambito delle capacità per supportare l'analisi degli incidenti e l'investigazione forense.                                                                             |   3   |  V   |

---

## Riferimenti

### Norme e Quadri di Riferimento

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Guide di Implementazione

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Sicurezza Specifica per l'IA

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

