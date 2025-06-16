# C6 Sicurezza della catena di approvvigionamento per modelli, framework e dati

## Obiettivo di Controllo

Gli attacchi alla supply chain dell'IA sfruttano modelli, framework o set di dati di terze parti per inserire backdoor, bias o codice vulnerabile. Questi controlli offrono una provenienza end-to-end, gestione delle vulnerabilità e monitoraggio per proteggere l'intero ciclo di vita del modello.

---

## C6.1 Verifica e Provenienza del Modello Preaddestrato

Valutare e autenticare origini, licenze e comportamenti nascosti dei modelli di terze parti prima di qualsiasi messa a punto o distribuzione.

|   #   | Description                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Verificare che ogni artefatto di modello di terze parti includa un record di provenienza firmato che identifichi il repository sorgente e l'hash del commit.          |   1   | D/V  |
| 6.1.2 | Verificare che i modelli vengano scansionati per rilevare layer dannosi o trigger Trojan utilizzando strumenti automatizzati prima dell'importazione.                 |   1   | D/V  |
| 6.1.3 | Verificare che il trasferimento dell'apprendimento (transfer-learning) affini (fine-tunes) superi la valutazione avversaria per rilevare comportamenti nascosti.      |   2   |  D   |
| 6.1.4 | Verificare che le licenze del modello, i tag di controllo delle esportazioni e le dichiarazioni di origine dei dati siano registrati in una voce ML-BOM.              |   2   |  V   |
| 6.1.5 | Verificare che i modelli ad alto rischio (pesi caricati pubblicamente, creatori non verificati) rimangano in quarantena fino alla revisione e all'approvazione umana. |   3   | D/V  |

---

## C6.2 Scansione di Framework e Librerie

Scansionare continuamente i framework e le librerie di ML alla ricerca di CVE e codice dannoso per mantenere sicuro lo stack di runtime.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.2.1 | Verificare che le pipeline CI eseguano scanner di dipendenze su framework AI e librerie critiche.                                                      |   1   | D/V  |
| 6.2.2 | Verificare che le vulnerabilità critiche (CVSS ≥ 7.0) blocchino la promozione alle immagini di produzione.                                             |   1   | D/V  |
| 6.2.3 | Verificare che l'analisi statica del codice venga eseguita sulle librerie ML forkate o fornite come dipendenze vendute.                                |   2   |  D   |
| 6.2.4 | Verificare che le proposte di aggiornamento del framework includano una valutazione dell'impatto sulla sicurezza con riferimento ai feed pubblici CVE. |   2   |  V   |
| 6.2.5 | Verificare che i sensori a runtime segnalino i caricamenti imprevisti di librerie dinamiche che deviano dal SBOM firmato.                              |   3   |  V   |

---

## C6.3 Blocco delle dipendenze e verifica

Blocca ogni dipendenza su digest immutabili e riproduci le build per garantire artefatti identici e privi di manomissioni.

|   #   | Description                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Verificare che tutti i gestori di pacchetti applichino il blocco delle versioni tramite file di blocco.                  |   1   | D/V  |
| 6.3.2 | Verificare che nei riferimenti ai container vengano utilizzati digest immutabili invece di tag mutabili.                 |   1   | D/V  |
| 6.3.3 | Verifica che i controlli di build riproducibili confrontino gli hash tra le esecuzioni CI per garantire output identici. |   2   |  D   |
| 6.3.4 | Verificare che le attestazioni di build siano conservate per 18 mesi per la tracciabilità dell'audit.                    |   2   |  V   |
| 6.3.5 | Verifica che le dipendenze scadute attivino PR automatiche per aggiornare o forcare le versioni bloccate.                |   3   |  D   |

---

## C6.4 Applicazione della Fonte Affidabile

Consenti il download di artifact solo da fonti approvate dall'organizzazione e verificate crittograficamente, bloccando tutto il resto.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Verificare che i pesi del modello, i dataset e i container siano scaricati solo da domini approvati o registri interni.                         |   1   | D/V  |
| 6.4.2 | Verificare che le firme Sigstore/Cosign convalidino l'identità dell'editore prima che gli artefatti vengano memorizzati nella cache localmente. |   1   | D/V  |
| 6.4.3 | Verificare che i proxy di uscita blocchino i download di artefatti non autenticati per applicare la politica della fonte attendibile.           |   2   |  D   |
| 6.4.4 | Verificare che le liste bianche del repository vengano riviste trimestralmente con prova della giustificazione commerciale per ogni voce.       |   2   |  V   |
| 6.4.5 | Verificare che le violazioni delle politiche attivino la quarantena degli artifact e il rollback delle esecuzioni delle pipeline dipendenti.    |   3   |  V   |

---

## C6.5 Valutazione del Rischio dei Dataset di Terze Parti

Valutare i dataset esterni per avvelenamento, bias e conformità legale, e monitorarli durante tutto il loro ciclo di vita.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Verificare che i dataset esterni siano sottoposti a una valutazione del rischio di avvelenamento (ad esempio, impronta digitale dei dati, rilevamento degli outlier).    |   1   | D/V  |
| 6.5.2 | Verificare che le metriche di bias (parità demografica, pari opportunità) siano calcolate prima dell'approvazione del dataset.                                           |   1   |  D   |
| 6.5.3 | Verificare che la provenienza e i termini di licenza dei dataset siano registrati nelle voci ML-BOM.                                                                     |   2   |  V   |
| 6.5.4 | Verificare che il monitoraggio periodico rilevi deviazioni o corruzioni nei dataset ospitati.                                                                            |   2   |  V   |
| 6.5.5 | Verificare che i contenuti non consentiti (copyright, dati personali identificabili) vengano rimossi tramite un processo automatico di pulizia prima dell'addestramento. |   3   |  D   |

---

## C6.6 Monitoraggio degli Attacchi alla Catena di Fornitura

Rileva precocemente le minacce alla catena di fornitura attraverso feed CVE, analisi dei log di audit e simulazioni red-team.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.6.1 | Verificare che i log di audit CI/CD vengano trasmessi al SIEM per il rilevamento di prelievi di pacchetti anomali o passaggi di build manomessi.                                     |   1   |  V   |
| 6.6.2 | Verificare che i playbook di risposta agli incidenti includano procedure di rollback per modelli o librerie compromesse.                                                             |   2   |  D   |
| 6.6.3 | Verifica che l’arricchimento delle informazioni sulle minacce etichetti gli indicatori specifici per ML (ad esempio, gli IoC di avvelenamento del modello) nella triage degli alert. |   3   |  V   |

---

## C6.7 ML‑BOM per gli Artifact del Modello

Generare e firmare SBOM specifici per il machine learning (ML-BOM) dettagliati in modo che i destinatari a valle possano verificare l'integrità dei componenti al momento del deploy.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Verificare che ogni artefatto modello pubblichi un ML‑BOM che elenchi i set di dati, i pesi, gli iperparametri e le licenze.                   |   1   | D/V  |
| 6.7.2 | Verificare che la generazione di ML‑BOM e la firma Cosign siano automatizzate nel CI e richieste per la fusione.                               |   1   | D/V  |
| 6.7.3 | Verificare che i controlli di completezza ML-BOM interrompano la build se manca qualche metadato del componente (hash, licenza).               |   2   |  D   |
| 6.7.4 | Verificare che i consumatori a valle possano interrogare gli ML-BOM tramite API per convalidare i modelli importati al momento del deployment. |   2   |  V   |
| 6.7.5 | Verificare che gli ML-BOM siano sotto controllo di versione e confrontati per rilevare modifiche non autorizzate.                              |   3   |  V   |

---

## Riferimenti

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

