# 11 Protezione della Privacy e Gestione dei Dati Personali

## Obiettivo di Controllo

Mantenere rigorose garanzie di privacy lungo l'intero ciclo di vita dell'IA—raccolta, addestramento, inferenza e risposta agli incidenti—affinché i dati personali siano trattati solo con consenso esplicito, ambito minimo necessario, cancellazione dimostrabile e garanzie formali di privacy.

---

## 11.1 Anonimizzazione e Minimizzazione dei Dati

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Verificare che gli identificatori diretti e quasi-identificatori siano rimossi o trasformati tramite hash.                                                                       |   1   | D/V  |
| 11.1.2 | Verificare che le revisioni automatizzate misurino k-anonimato/l-diversità e segnalino quando le soglie scendono al di sotto della politica.                                     |   2   | D/V  |
| 11.1.3 | Verificare che i report sull'importanza delle caratteristiche del modello dimostrino l'assenza di perdite di identificatori oltre ε = 0,01 di informazione mutua.                |   2   |  V   |
| 11.1.4 | Verificare che le dimostrazioni formali o la certificazione basata su dati sintetici mostrino un rischio di re-identificazione ≤ 0,05 anche in caso di attacchi di collegamento. |   3   |  V   |

---

## 11.2 Diritto all'oblio e applicazione della cancellazione

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Verificare che le richieste di cancellazione dei dati soggetti si propaghino ai dataset grezzi, ai checkpoint, agli embedding, ai log e ai backup entro accordi sui livelli di servizio inferiori a 30 giorni. |   1   | D/V  |
| 11.2.2 | Verificare che le routine di "machine-unlearning" effettivamente riaddestrino o approssimino la rimozione utilizzando algoritmi certificati di unlearning.                                                     |   2   |  D   |
| 11.2.3 | Verificare che la valutazione del modello ombra dimostri che i record dimenticati influenzano meno dell'1% degli output dopo il processo di unlearning.                                                        |   2   |  V   |
| 11.2.4 | Verificare che gli eventi di cancellazione siano registrati in modo immutabile e siano verificabili per i regolatori.                                                                                          |   3   |  V   |

---

## 11.3 Salvaguardie per la Privacy Differenziale

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Verificare che i cruscotti di contabilità della perdita di privacy segnalino quando il valore cumulativo di ε supera le soglie di politica. |   2   | D/V  |
| 11.3.2 | Verificare che le verifiche di privacy black-box stimino ε̂ entro il 10% del valore dichiarato.                                             |   2   |  V   |
| 11.3.3 | Verificare che le dimostrazioni formali coprano tutte le rifiniture post-addestramento e gli embedding.                                     |   3   |  V   |

---

## 11.4 Limitazione dello scopo e protezione contro l'espansione non autorizzata dell'ambito

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Verificare che ogni set di dati e punto di controllo del modello abbia un tag di scopo leggibile da macchina allineato al consenso originale.     |   1   |  D   |
| 11.4.2 | Verificare che i monitor di runtime rilevino query incoerenti con lo scopo dichiarato e attivino un rifiuto soft.                                 |   1   | D/V  |
| 11.4.3 | Verificare che le policy-as-code impediscano la ridistribuzione dei modelli su nuovi domini senza revisione DPIA.                                 |   3   |  D   |
| 11.4.4 | Verificare che le prove formali di tracciabilità dimostrino che ogni ciclo di vita dei dati personali rimanga all'interno dell'ambito consentito. |   3   |  V   |

---

## 11.5 Gestione del Consenso e Tracciamento della Base Giuridica

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Verificare che una piattaforma di gestione del consenso (CMP) registri lo stato di opt-in, lo scopo e il periodo di conservazione per ciascun interessato. |   1   | D/V  |
| 11.5.2 | Verificare che le API espongano i token di consenso; i modelli devono convalidare l'ambito del token prima dell'inferenza.                                 |   2   |  D   |
| 11.5.3 | Verificare che il consenso negato o revocato fermi le pipeline di elaborazione entro 24 ore.                                                               |   2   | D/V  |

---

## 11.6 Apprendimento Federato con Controlli sulla Privacy

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Verificare che gli aggiornamenti del client utilizzino l'aggiunta di rumore con privacy differenziale locale prima dell'aggregazione. |   1   |  D   |
| 11.6.2 | Verificare che le metriche di addestramento siano differenzialmente private e non rivelino mai la perdita di un singolo cliente.      |   2   | D/V  |
| 11.6.3 | Verificare che l'aggregazione resistente all'avvelenamento (ad esempio, Krum/Media Tagliata) sia abilitata.                           |   2   |  V   |
| 11.6.4 | Verificare che le dimostrazioni formali dimostrino un budget ε complessivo con una perdita di utilità inferiore a 5.                  |   3   |  V   |

---

### Riferimenti

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

