# Utilizzando l'AISVS

Lo Standard di Verifica della Sicurezza dell'Intelligenza Artificiale (AISVS) definisce i requisiti di sicurezza per le moderne applicazioni e servizi di IA, concentrandosi sugli aspetti sotto il controllo degli sviluppatori di applicazioni.

L'AISVS è destinato a chiunque sviluppi o valuti la sicurezza delle applicazioni di intelligenza artificiale, inclusi sviluppatori, architetti, ingegneri della sicurezza e revisori. Questo capitolo introduce la struttura e l'uso dell'AISVS, inclusi i suoi livelli di verifica e i casi d'uso previsti.

## Livelli di verifica della sicurezza dell'Intelligenza Artificiale

L'AISVS definisce tre livelli crescenti di verifica della sicurezza. Ogni livello aggiunge profondità e complessità, permettendo alle organizzazioni di adattare la loro postura di sicurezza al livello di rischio dei loro sistemi di intelligenza artificiale.

Le organizzazioni possono iniziare al Livello 1 e adottare progressivamente livelli superiori man mano che la maturità della sicurezza e l'esposizione alle minacce aumentano.

### Definizione dei Livelli

Ogni requisito in AISVS v1.0 è assegnato a uno dei seguenti livelli:

#### Requisiti di Livello 1

Il Livello 1 include i requisiti di sicurezza più critici e fondamentali. Questi si concentrano sulla prevenzione di attacchi comuni che non si basano su altre condizioni preliminari o vulnerabilità. La maggior parte dei controlli di Livello 1 è o semplice da implementare o abbastanza essenziale da giustificare lo sforzo.

#### Requisiti di livello 2

Il Livello 2 affronta attacchi più avanzati o meno comuni, nonché difese stratificate contro minacce diffuse. Questi requisiti possono comportare logiche più complesse o mirare a prerequisiti specifici degli attacchi.

#### Requisiti di livello 3

Il livello 3 include controlli che sono tipicamente più difficili da implementare o situazionali nella loro applicabilità. Questi spesso rappresentano meccanismi di difesa in profondità o mitigazioni contro attacchi di nicchia, mirati o ad alta complessità.

### Ruolo (D/V)

Ogni requisito AISVS è contrassegnato in base al pubblico principale:

* D – Requisiti focalizzati sullo sviluppatore
* V – Requisiti focalizzati sul verificatore/revisore
* D/V – Rilevante sia per sviluppatori che per verificatori

