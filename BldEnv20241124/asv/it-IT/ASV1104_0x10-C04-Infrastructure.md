# Sicurezza dell'Infrastruttura C4, della Configurazione e del Deployment

## Obiettivo di Controllo

L'infrastruttura di intelligenza artificiale deve essere rafforzata contro l'escalation di privilegi, la manomissione della catena di fornitura e i movimenti laterali mediante configurazioni sicure, isolamento in fase di esecuzione, pipeline di distribuzione affidabili e monitoraggio completo. Solo componenti e configurazioni dell'infrastruttura autorizzati e verificati raggiungono la produzione attraverso processi controllati che mantengono sicurezza, integrità e tracciabilità.

Obiettivo principale di sicurezza: Solo i componenti infrastrutturali firmati crittograficamente e sottoposti a scansione per vulnerabilità raggiungono la produzione attraverso pipeline di validazione automatizzate che applicano le politiche di sicurezza e mantengono registri di audit immutabili.

---

## C4.1 Isolamento dell'Ambiente di Esecuzione

Prevenire l'evasione dei container e l'escalation dei privilegi attraverso primitive di isolamento a livello kernel e controlli di accesso obbligatori.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Verificare che tutti i container AI rimuovano TUTTE le capacità Linux tranne CAP_SETUID, CAP_SETGID e le capacità esplicitamente richieste e documentate nelle baseline di sicurezza.                                                     |   1   | D/V  |
| 4.1.2 | Verificare che i profili seccomp blocchino tutte le syscall tranne quelle presenti nelle liste di consenso pre-approvate, con violazioni che terminano il container e generano avvisi di sicurezza.                                       |   1   | D/V  |
| 4.1.3 | Verificare che i carichi di lavoro AI vengano eseguiti con filesystem root in sola lettura, tmpfs per i dati temporanei e volumi nominati per i dati persistenti con opzioni di mount noexec applicate.                                   |   2   | D/V  |
| 4.1.4 | Verificare che il monitoraggio runtime basato su eBPF (Falco, Tetragon o equivalente) rilevi i tentativi di escalation dei privilegi e termini automaticamente i processi colpevoli entro i requisiti di tempo di risposta organizzativi. |   2   | D/V  |
| 4.1.5 | Verificare che i carichi di lavoro AI ad alto rischio vengano eseguiti in ambienti isolati a livello hardware (Intel TXT, AMD SVM o nodi bare-metal dedicati) con verifica di attestazione.                                               |   3   | D/V  |

---

## C4.2 Pipeline di Build e Distribuzione Sicure

Garantire l'integrità crittografica e la sicurezza della catena di approvvigionamento attraverso build riproducibili e artefatti firmati.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Verificare che l'infrastruttura come codice venga esaminata con strumenti (tfsec, Checkov o Terrascan) ad ogni commit, bloccando le fusioni in presenza di risultati con criticità CRITICA o ALTA.                            |   1   | D/V  |
| 4.2.2 | Verificare che le build dei container siano riproducibili con hash SHA256 identici in tutte le build e generare attestazioni di provenienza SLSA Livello 3 firmate con Sigstore.                                              |   1   | D/V  |
| 4.2.3 | Verificare che le immagini dei container incorporino SBOM CycloneDX o SPDX e siano firmate con Cosign prima del push nel registry, con il rifiuto delle immagini non firmate durante il deployment.                           |   2   | D/V  |
| 4.2.4 | Verificare che le pipeline CI/CD utilizzino token OIDC da HashiCorp Vault, ruoli IAM di AWS o Identità Gestita di Azure con durate che non superino i limiti stabiliti dalla politica di sicurezza aziendale.                 |   2   | D/V  |
| 4.2.5 | Verificare che le firme Cosign e la provenienza SLSA siano convalidate durante il processo di distribuzione prima dell'esecuzione del container e che eventuali errori di verifica causino il fallimento della distribuzione. |   2   | D/V  |
| 4.2.6 | Verificare che gli ambienti di build vengano eseguiti in container o macchine virtuali effimeri senza memoria persistente e con isolamento di rete dalle VPC di produzione.                                                   |   2   | D/V  |

---

## C4.3 Sicurezza di Rete e Controllo degli Accessi

Implementare una rete a fiducia zero con politiche di negazione predefinite e comunicazioni crittografate.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Verificare che le NetworkPolicy di Kubernetes o qualsiasi equivalente implementino un blocco predefinito (default-deny) per ingressi/uscite con regole di autorizzazione esplicite per le porte richieste (443, 8080, ecc.). |   1   | D/V  |
| 4.3.2 | Verificare che SSH (porta 22), RDP (porta 3389) e gli endpoint dei metadata cloud (169.254.169.254) siano bloccati o richiedano l'autenticazione basata su certificato.                                                      |   1   | D/V  |
| 4.3.3 | Verificare che il traffico in uscita sia filtrato tramite proxy HTTP/HTTPS (Squid, Istio o gateway NAT cloud) con liste di domini consentiti e che le richieste bloccate vengano registrate.                                 |   2   | D/V  |
| 4.3.4 | Verificare che la comunicazione inter-servizi utilizzi mutual TLS con certificati ruotati secondo la politica organizzativa e con la validazione dei certificati applicata (senza flag di skip-verify).                      |   2   | D/V  |
| 4.3.5 | Verificare che l'infrastruttura di intelligenza artificiale operi in VPC/VNet dedicate senza accesso diretto a Internet e che comunichi esclusivamente tramite gateway NAT o host bastion.                                   |   2   | D/V  |

---

## C4.4 Gestione dei Segreti e delle Chiavi Crittografiche

Proteggi le credenziali tramite archiviazione supportata da hardware e rotazione automatizzata con accesso a zero-trust.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Verificare che i segreti siano memorizzati in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault o Google Secret Manager con crittografia a riposo utilizzando AES-256.                                                   |   1   | D/V  |
| 4.4.2 | Verificare che le chiavi crittografiche siano generate in HSM conformi a FIPS 140-2 Livello 2 (AWS CloudHSM, Azure Dedicated HSM) con rotazione delle chiavi secondo la politica crittografica organizzativa.                |   1   | D/V  |
| 4.4.3 | Verificare che la rotazione dei segreti sia automatizzata con deployment zero-downtime e rotazione immediata attivata da cambiamenti del personale o incidenti di sicurezza.                                                 |   2   | D/V  |
| 4.4.4 | Verificare che le immagini dei container siano scansionate con strumenti (GitLeaks, TruffleHog o detect-secrets) che bloccano le build contenenti chiavi API, password o certificati.                                        |   2   | D/V  |
| 4.4.5 | Verificare che l'accesso segreto alla produzione richieda l'autenticazione multifattoriale (MFA) con token hardware (YubiKey, FIDO2) e sia registrato tramite log di audit immutabili con identità degli utenti e timestamp. |   2   | D/V  |
| 4.4.6 | Verificare che i segreti vengano inseriti tramite i segreti di Kubernetes, volumi montati o container di inizializzazione e garantire che i segreti non siano mai incorporati nelle variabili d'ambiente o nelle immagini.   |   2   | D/V  |

---

## C4.5 Isolamento e Validazione del Carico di Lavoro AI

Isolare i modelli di intelligenza artificiale non affidabili in sandbox sicuri con un'analisi comportamentale completa.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Verificare che i modelli di intelligenza artificiale esterni vengano eseguiti in gVisor, microVM (come Firecracker, CrossVM) o container Docker con le opzioni --security-opt=no-new-privileges e --read-only.                |   1   | D/V  |
| 4.5.2 | Verificare che gli ambienti sandbox non abbiano connettività di rete (--network=none) o abbiano solo accesso localhost con tutte le richieste esterne bloccate dalle regole iptables.                                         |   1   | D/V  |
| 4.5.3 | Verificare che la convalida del modello di IA includa test automatizzati di tipo red-team con una copertura di test definita dall'organizzazione e un'analisi comportamentale per il rilevamento di backdoor.                 |   2   | D/V  |
| 4.5.4 | Verificare che, prima che un modello AI venga promosso in produzione, i risultati ottenuti nella sandbox siano firmati crittograficamente dal personale di sicurezza autorizzato e archiviati in log di controllo immutabili. |   2   | D/V  |
| 4.5.5 | Verificare che gli ambienti sandbox vengano distrutti e ricreati da immagini golden tra le valutazioni, con una completa pulizia del filesystem e della memoria.                                                              |   2   | D/V  |

---

## C4.6 Monitoraggio della Sicurezza dell'Infrastruttura

Scansionare e monitorare continuamente l'infrastruttura con rimedio automatizzato e allerta in tempo reale.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Verificare che le immagini dei container siano sottoposte a scansione secondo i programmi organizzativi, con le vulnerabilità CRITICHE che bloccano il deployment in base alle soglie di rischio organizzativo.                  |   1   | D/V  |
| 4.6.2 | Verificare che l'infrastruttura rispetti i CIS Benchmarks o i controlli NIST 800-53 con soglie di conformità definite dall'organizzazione e la correzione automatizzata per verifiche non superate.                              |   1   | D/V  |
| 4.6.3 | Verificare che le vulnerabilità di gravità ALTA siano corrette secondo le tempistiche di gestione del rischio dell'organizzazione, con procedure di emergenza per le CVE attivamente sfruttate.                                  |   2   | D/V  |
| 4.6.4 | Verificare che gli avvisi di sicurezza si integrino con le piattaforme SIEM (Splunk, Elastic o Sentinel) utilizzando i formati CEF o STIX/TAXII con arricchimento automatizzato.                                                 |   2   |  V   |
| 4.6.5 | Verificare che le metriche dell'infrastruttura vengano esportate ai sistemi di monitoraggio (Prometheus, DataDog) con dashboard SLA e reportistica esecutiva.                                                                    |   3   |  V   |
| 4.6.6 | Verificare che la deriva di configurazione venga rilevata utilizzando strumenti (Chef InSpec, AWS Config) in conformità con i requisiti di monitoraggio organizzativi, con rollback automatico per le modifiche non autorizzate. |   2   | D/V  |

---

## Gestione delle risorse dell'infrastruttura AI C4.7

Prevenire attacchi di esaurimento delle risorse e garantire una distribuzione equa delle risorse attraverso quote e monitoraggio.

|   #   | Description                                                                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Verificare che l'utilizzo di GPU/TPU sia monitorato con avvisi attivati a soglie definite dall'organizzazione e che la scalabilità automatica o il bilanciamento del carico vengano attivati in base alle politiche di gestione della capacità. |   1   | D/V  |
| 4.7.2 | Verificare che le metriche del carico di lavoro AI (latenza di inferenza, throughput, tassi di errore) siano raccolte secondo i requisiti di monitoraggio organizzativi e correlate con l'utilizzo dell'infrastruttura.                         |   1   | D/V  |
| 4.7.3 | Verificare che Kubernetes ResourceQuotas o equivalenti limitino i singoli carichi di lavoro secondo le politiche di allocazione delle risorse aziendali con limiti rigidi applicati.                                                            |   2   | D/V  |
| 4.7.4 | Verificare che il monitoraggio dei costi tracci la spesa per carico di lavoro/inquilino con avvisi basati sulle soglie di budget organizzativo e controlli automatizzati per i superamenti di budget.                                           |   2   |  V   |
| 4.7.5 | Verificare che la pianificazione della capacità utilizzi dati storici con periodi di previsione definiti dall'organizzazione e l'approvvigionamento automatico delle risorse basato sui modelli di domanda.                                     |   3   |  V   |
| 4.7.6 | Verificare che l'esaurimento delle risorse attivi gli interruttori a circuito secondo i requisiti di risposta organizzativi, inclusi il controllo della velocità basato sulle politiche di capacità e l'isolamento del carico di lavoro.        |   2   | D/V  |

---

## C4.8 Controlli per la Separazione e la Promozione degli Ambienti

Applicare rigidi confini ambientali con cancelli di promozione automatizzati e convalida della sicurezza.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Verificare che gli ambienti di sviluppo/test/produzione funzionino in VPC/VNet separate senza ruoli IAM, gruppi di sicurezza o connettività di rete condivisi.                                                                                          |   1   | D/V  |
| 4.8.2 | Verificare che la promozione dell'ambiente richieda l'approvazione da parte del personale autorizzato definito dall'organizzazione, con firme crittografiche e registri di controllo immutabili.                                                        |   1   | D/V  |
| 4.8.3 | Verificare che gli ambienti di produzione blocchino l'accesso SSH, disabilitino gli endpoint di debug e richiedano richieste di modifica con preavviso organizzativo, tranne in caso di emergenze.                                                      |   2   | D/V  |
| 4.8.4 | Verificare che le modifiche all'infrastruttura come codice richiedano una revisione tra pari con test automatizzati e scansione di sicurezza prima della fusione nel ramo principale.                                                                   |   2   | D/V  |
| 4.8.5 | Verificare che i dati non di produzione siano anonimizzati secondo i requisiti di riservatezza organizzativa, mediante generazione di dati sintetici o mascheramento completo dei dati con rimozione delle informazioni personali identificabili (PII). |   2   | D/V  |
| 4.8.6 | Verificare che le soglie di promozione includano test di sicurezza automatizzati (SAST, DAST, scansione dei container) con zero risultati CRITICI richiesti per l'approvazione.                                                                         |   2   | D/V  |

---

## C4.9 Backup e Ripristino dell'Infrastruttura

Garantire la resilienza dell'infrastruttura attraverso backup automatizzati, procedure di recupero testate e capacità di disaster recovery.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Verificare che le configurazioni dell'infrastruttura siano sottoposte a backup secondo i programmi di backup organizzativi, con destinazione in regioni geograficamente separate, implementando la strategia di backup 3-2-1. |   1   | D/V  |
| 4.9.2 | Verificare che i sistemi di backup funzionino in reti isolate con credenziali separate e storage isolato (air-gapped) per la protezione contro i ransomware.                                                                  |   2   | D/V  |
| 4.9.3 | Verificare che le procedure di recupero siano testate e validate attraverso test automatizzati secondo i programmi organizzativi, con obiettivi RTO e RPO conformi ai requisiti dell'organizzazione.                          |   2   |  V   |
| 4.9.4 | Verificare che il disaster recovery includa runbook specifici per l'IA con il ripristino dei pesi del modello, la ricostruzione del cluster GPU e la mappatura delle dipendenze di servizio.                                  |   3   |  V   |

---

## C4.10 Conformità e Governance delle Infrastrutture

Mantenere la conformità normativa attraverso la valutazione continua, la documentazione e i controlli automatizzati.

|   #    | Description                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Verificare che la conformità dell'infrastruttura sia valutata in base ai programmi organizzativi rispetto ai controlli SOC 2, ISO 27001 o FedRAMP con raccolta automatizzata delle prove.                 |   2   | D/V  |
| 4.10.2 | Verificare che la documentazione dell'infrastruttura includa diagrammi di rete, mappe di flusso dei dati e modelli di minacce aggiornati secondo i requisiti di gestione del cambiamento organizzativo.   |   2   |  V   |
| 4.10.3 | Verificare che le modifiche all'infrastruttura siano soggette a una valutazione automatizzata dell'impatto sulla conformità con flussi di lavoro di approvazione normativa per modifiche ad alto rischio. |   3   | D/V  |

---

## C4.11 Sicurezza dell'Hardware per l'IA

Componenti hardware specifici per l'IA sicuri, inclusi GPU, TPU e acceleratori AI specializzati.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Verificare che il firmware dell'acceleratore AI (BIOS GPU, firmware TPU) sia verificato con firme crittografiche e aggiornato secondo le tempistiche di gestione delle patch dell'organizzazione.  |   2   | D/V  |
| 4.11.2 | Verificare che prima dell'esecuzione del carico di lavoro, l'integrità dell'acceleratore AI venga convalidata tramite attestazione hardware utilizzando TPM 2.0, Intel TXT o AMD SVM.              |   2   | D/V  |
| 4.11.3 | Verificare che la memoria GPU sia isolata tra i carichi di lavoro utilizzando SR-IOV, MIG (GPU Multi-Instance) o una partizione hardware equivalente con sanificazione della memoria tra i lavori. |   2   | D/V  |
| 4.11.4 | Verificare che la catena di approvvigionamento dell'hardware AI includa la verifica della provenienza con certificati del produttore e la validazione dell'imballaggio a prova di manomissione.    |   3   |  V   |
| 4.11.5 | Verificare che i moduli di sicurezza hardware (HSM) proteggano i pesi dei modelli AI e le chiavi crittografiche con certificazione FIPS 140-2 Livello 3 o Common Criteria EAL4+.                   |   3   | D/V  |

---

## C4.12 Infrastruttura AI Edge e Distribuita

Distribuzioni sicure di AI distribuita, inclusi edge computing, apprendimento federato e architetture multi-sito.

|   #    | Description                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Verificare che i dispositivi edge AI si autentichino all'infrastruttura centrale utilizzando TLS mutuo con certificati dei dispositivi ruotati secondo la politica di gestione dei certificati dell'organizzazione. |   2   | D/V  |
| 4.12.2 | Verificare che i dispositivi edge implementino il boot sicuro con firme verificate e protezione contro il rollback per prevenire attacchi di downgrade del firmware.                                                |   2   | D/V  |
| 4.12.3 | Verificare che il coordinamento dell'IA distribuita utilizzi algoritmi di consenso tolleranti ai guasti bizantini con validazione dei partecipanti e rilevamento di nodi maligni.                                   |   3   | D/V  |
| 4.12.4 | Verificare che la comunicazione edge-to-cloud includa limitazione della larghezza di banda, compressione dei dati e capacità di funzionamento offline con archiviazione locale sicura.                              |   3   | D/V  |

---

## C4.13 Sicurezza dell'Infrastruttura Multi-Cloud e Ibrida

Proteggi i carichi di lavoro AI su più fornitori di cloud e distribuzioni ibride cloud-on-premises.

|   #    | Description                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Verificare che le distribuzioni di AI multi-cloud utilizzino la federazione di identità cloud-agnostica (OIDC, SAML) con gestione centralizzata delle politiche tra i fornitori.                                             |   2   | D/V  |
| 4.13.2 | Verificare che il trasferimento dei dati tra cloud utilizzi la crittografia end-to-end con chiavi gestite dal cliente e che i controlli sulla residenza dei dati siano applicati in base alla giurisdizione.                 |   2   | D/V  |
| 4.13.3 | Verificare che i carichi di lavoro AI in cloud ibrido implementino politiche di sicurezza coerenti tra ambienti on-premise e cloud con monitoraggio e allerta unificati.                                                     |   2   | D/V  |
| 4.13.4 | Verificare che la prevenzione del lock-in del fornitore cloud includa infrastruttura-as-code portabile, API standardizzate e funzionalità di esportazione dati con strumenti di conversione di formato.                      |   3   |  V   |
| 4.13.5 | Verificare che l'ottimizzazione dei costi multi-cloud includa controlli di sicurezza che prevengano la proliferazione incontrollata delle risorse e addebiti non autorizzati per il trasferimento di dati tra cloud diversi. |   3   |  V   |

---

## C4.14 Automazione dell'Infrastruttura e Sicurezza GitOps

Pipeline di automazione dell'infrastruttura sicura e flussi di lavoro GitOps per la gestione dell'infrastruttura AI.

|   #    | Description                                                                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Verificare che i repository GitOps richiedano commit firmati con chiavi GPG e regole di protezione dei branch che impediscano push diretti ai branch principali.                                                            |   2   | D/V  |
| 4.14.2 | Verifica che l'automazione dell'infrastruttura includa il rilevamento delle deviazioni con capacità di rimedio automatico e rollback attivate in base ai requisiti di risposta organizzativa per modifiche non autorizzate. |   2   | D/V  |
| 4.14.3 | Verificare che il provisioning automatizzato dell'infrastruttura includa la convalida delle politiche di sicurezza con blocco del deployment per configurazioni non conformi.                                               |   2   | D/V  |
| 4.14.4 | Verificare che i segreti per l'automazione dell'infrastruttura siano gestiti tramite operatori esterni per i segreti (External Secrets Operator, Bank-Vaults) con rotazione automatica.                                     |   2   | D/V  |
| 4.14.5 | Verificare che l'infrastruttura auto-riparante includa la correlazione degli eventi di sicurezza con la risposta automatizzata agli incidenti e i flussi di lavoro per la notifica ai portatori di interesse.               |   3   |  V   |

---

## C4.15 Sicurezza dell'Infrastruttura Resistente ai Quantum

Prepara l'infrastruttura AI per le minacce del calcolo quantistico attraverso la crittografia post-quantistica e i protocolli quantum-safe.

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verificare che l'infrastruttura AI implementi algoritmi crittografici post-quantistici approvati dal NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) per lo scambio di chiavi e le firme digitali.          |   3   | D/V  |
| 4.15.2 | Verificare che i sistemi di distribuzione delle chiavi quantistiche (QKD) siano implementati per comunicazioni AI ad alta sicurezza con protocolli di gestione delle chiavi sicuri contro attacchi quantistici. |   3   | D/V  |
| 4.15.3 | Verificare che i framework per l'agilità crittografica consentano una migrazione rapida verso nuovi algoritmi post-quantum con rotazione automatica di certificati e chiavi.                                    |   3   | D/V  |
| 4.15.4 | Verificare che la modellazione delle minacce quantistiche valuti la vulnerabilità dell'infrastruttura AI agli attacchi quantistici con cronoprogrammi di migrazione documentati e valutazioni del rischio.      |   3   |  V   |
| 4.15.5 | Verificare che i sistemi crittografici ibridi classico-quantistici offrano una difesa stratificata durante il periodo di transizione quantistica, con monitoraggio delle prestazioni.                           |   3   | D/V  |

---

## C4.16 Computing Confidenziale e Enclave Sicure

Proteggi i carichi di lavoro AI e i pesi dei modelli utilizzando ambienti di esecuzione affidabili basati su hardware e tecnologie di computing confidenziale.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Verificare che i modelli AI sensibili vengano eseguiti all'interno degli enclave Intel SGX, AMD SEV-SNP o ARM TrustZone con memoria crittografata e verifica dell'attestazione.                               |   3   | D/V  |
| 4.16.2 | Verificare che i container riservati (Kata Containers, gVisor con computing riservato) isolino i carichi di lavoro AI con crittografia della memoria applicata dall'hardware.                                 |   3   | D/V  |
| 4.16.3 | Verificare che l'attestazione remota convalidi l'integrità dell'enclave prima di caricare i modelli di intelligenza artificiale tramite una prova crittografica dell'autenticità dell'ambiente di esecuzione. |   3   | D/V  |
| 4.16.4 | Verificare che i servizi di inferenza AI riservati prevengano l’estrazione del modello tramite computazione crittografata con pesi del modello sigillati e esecuzione protetta.                               |   3   | D/V  |
| 4.16.5 | Verificare che l'orchestrazione dell'ambiente di esecuzione affidabile gestisca il ciclo di vita dell'enclave sicura con attestazione remota e canali di comunicazione criptati.                              |   3   | D/V  |
| 4.16.6 | Verificare che il calcolo multi-parte sicuro (SMPC) consenta l'addestramento collaborativo dell'IA senza esporre set di dati individuali o parametri del modello.                                             |   3   | D/V  |

---

## C4.17 Infrastruttura a Conoscenza Zero

Implementare sistemi di prova a conoscenza zero per la verifica e l'autenticazione dell'IA preservando la privacy senza rivelare informazioni sensibili.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Verificare che le prove a conoscenza zero (ZK-SNARKs, ZK-STARKs) confermino l'integrità del modello AI e la provenienza dell'addestramento senza esporre i pesi del modello o i dati di addestramento.        |   3   | D/V  |
| 4.17.2 | Verifica che i sistemi di autenticazione basati su ZK consentano la verifica dell'utente preservando la privacy per i servizi di intelligenza artificiale senza rivelare informazioni correlate all'identità. |   3   | D/V  |
| 4.17.3 | Verificare che i protocolli di intersezione di insiemi privati (PSI) consentano un confronto sicuro dei dati per l’intelligenza artificiale federata senza esporre i singoli set di dati.                     |   3   | D/V  |
| 4.17.4 | Verificare che i sistemi di apprendimento automatico a conoscenza zero (ZKML) consentano inferenze AI verificabili con prova crittografica del corretto calcolo.                                              |   3   | D/V  |
| 4.17.5 | Verificare che gli ZK-rollup forniscano un'elaborazione delle transazioni AI scalabile e che preservi la privacy, con verifica batch e riduzione del carico computazionale.                                   |   3   | D/V  |

---

## C4.18 Prevenzione degli attacchi di canale laterale

Proteggi l'infrastruttura AI da attacchi side-channel basati su tempistica, consumo energetico, elettromagnetismo e cache che potrebbero divulgare informazioni sensibili.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Verificare che il tempo di inferenza dell’IA sia normalizzato utilizzando algoritmi a tempo costante e padding per prevenire attacchi di estrazione del modello basati sul tempo.                  |   3   | D/V  |
| 4.18.2 | Verificare che la protezione dall'analisi di potenza includa l'iniezione di rumore, il filtraggio della linea di alimentazione e schemi di esecuzione randomizzati per l'hardware AI.              |   3   | D/V  |
| 4.18.3 | Verificare che la mitigazione dei canali laterali basati sulla cache utilizzi la partizione della cache, la randomizzazione e le istruzioni di flush per prevenire la fuoriuscita di informazioni. |   3   | D/V  |
| 4.18.4 | Verificare che la protezione dalle emanazioni elettromagnetiche includa schermatura, filtraggio del segnale e elaborazione randomizzata per prevenire attacchi in stile TEMPEST.                   |   3   | D/V  |
| 4.18.5 | Verificare che le difese contro i canali laterali microarchitetturali includano controlli sull'esecuzione speculativa e offuscamento dei modelli di accesso alla memoria.                          |   3   | D/V  |

---

## C4.19 Sicurezza dell'Hardware Neuromorfico e AI Specializzato

Garantire la sicurezza delle nuove architetture hardware AI emergenti, inclusi chip neuromorfici, FPGA, ASIC personalizzati e sistemi di calcolo ottico.

|   #    | Description                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Verificare che la sicurezza del chip neuromorfico includa la crittografia del modello di impulsi, la protezione del peso sinaptico e la convalida delle regole di apprendimento basata sull'hardware. |   3   | D/V  |
| 4.19.2 | Verificare che gli accelerator AI basati su FPGA implementino la crittografia del bitstream, meccanismi anti-manomissione e caricamento sicuro della configurazione con aggiornamenti autenticati.    |   3   | D/V  |
| 4.19.3 | Verificare che la sicurezza ASIC personalizzata includa processori di sicurezza on-chip, root hardware di fiducia e archiviazione sicura delle chiavi con rilevamento di manomissioni.                |   3   | D/V  |
| 4.19.4 | Verificare che i sistemi di calcolo ottico implementino crittografia ottica quantisticamente sicura, commutazione fotonica sicura e elaborazione protetta del segnale ottico.                         |   3   | D/V  |
| 4.19.5 | Verificare che i chip AI ibridi analogico-digitali includano calcolo analogico sicuro, memorizzazione protetta dei pesi e conversione autenticata da analogico a digitale.                            |   3   | D/V  |

---

## C4.20 Infrastruttura di Calcolo che Preserva la Privacy

Implementare controlli infrastrutturali per il calcolo che preserva la privacy al fine di proteggere i dati sensibili durante l'elaborazione e l'analisi dell'IA.

|   #    | Description                                                                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Verificare che l'infrastruttura di crittografia omomorfica consenta il calcolo crittografato su carichi di lavoro sensibili di intelligenza artificiale con verifica dell'integrità crittografica e monitoraggio delle prestazioni.          |   3   | D/V  |
| 4.20.2 | Verificare che i sistemi di retrieval di informazioni private consentano interrogazioni al database senza rivelare i modelli di query, garantendo la protezione crittografica dei modelli di accesso.                                        |   3   | D/V  |
| 4.20.3 | Verificare che i protocolli di calcolo multi-parte sicuro consentano un'inferenza AI che preservi la privacy senza esporre dati individuali o calcoli intermedi.                                                                             |   3   | D/V  |
| 4.20.4 | Verificare che la gestione delle chiavi con preservazione della privacy includa generazione distribuita delle chiavi, crittografia a soglia e rotazione sicura delle chiavi con protezione supportata dall'hardware.                         |   3   | D/V  |
| 4.20.5 | Verificare che le prestazioni del calcolo a tutela della privacy siano ottimizzate tramite l'elaborazione in batch, la memorizzazione nella cache e l'accelerazione hardware, mantenendo al contempo le garanzie di sicurezza crittografica. |   3   | D/V  |

---

## C4.15 Sicurezza dell'Integrazione Cloud del Framework Agent e Distribuzione Ibrida

Controlli di sicurezza per framework di agenti integrati con il cloud in architetture ibride on-premises/cloud.

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verificare che l'integrazione dello storage cloud utilizzi la crittografia end-to-end con gestione delle chiavi controllata dall'agente.                    |   1   | D/V  |
| 4.15.2 | Verificare che i confini di sicurezza nel deployment ibrido siano chiaramente definiti con canali di comunicazione criptati.                                |   2   | D/V  |
| 4.15.3 | Verificare che l'accesso alle risorse cloud includa una verifica zero-trust con autenticazione continua.                                                    |   2   | D/V  |
| 4.15.4 | Verificare che i requisiti di residenza dei dati siano applicati tramite attestazione crittografica delle posizioni di archiviazione.                       |   3   | D/V  |
| 4.15.5 | Verificare che le valutazioni di sicurezza del fornitore cloud includano la modellazione delle minacce specifica per l'agente e la valutazione del rischio. |   3   | D/V  |

---

## Riferimenti

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

