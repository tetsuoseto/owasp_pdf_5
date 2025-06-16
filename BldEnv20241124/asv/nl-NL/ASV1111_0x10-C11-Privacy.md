# 11 Privacybescherming & Beheer van Persoonsgegevens

## Beheersingsdoelstelling

Handhaaf strikte privacygaranties gedurende de gehele AI-levenscyclus—verzameling, training, inferentie en incidentrespons—zodat persoonlijke gegevens alleen worden verwerkt met duidelijke toestemming, minimale noodzakelijke omvang, aantoonbare verwijdering en formele privacywaarborgen.

---

## 11.1 Anonimisering & Data Minimalisatie

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Verifieer dat directe en quasi-identificatoren worden verwijderd of gehasht.                                                                            |   1   | D/V  |
| 11.1.2 | Controleer of geautomatiseerde audits k-anonimiteit/l-diversiteit meten en een waarschuwing geven wanneer de drempelwaarden onder het beleid dalen.     |   2   | D/V  |
| 11.1.3 | Verifieer dat de rapporten over de belangrijkheid van modelkenmerken geen identifierlekkage aantonen boven ε = 0,01 wederzijdse informatie.             |   2   |  V   |
| 11.1.4 | Controleer of formele bewijzen of certificering met synthetische data aantonen dat het re-identificatierisico ≤ 0,05 is, zelfs bij koppelingsaanvallen. |   3   |  V   |

---

## 11.2 Recht om te worden vergeten & handhaving van verwijdering

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Verifieer dat verzoeken tot verwijdering van gegevenssubjecten worden doorgevoerd naar ruwe datasets, checkpoints, embeddings, logs en back-ups binnen servicetijdafspraken van minder dan 30 dagen. |   1   | D/V  |
| 11.2.2 | Verifieer dat "machine-unlearning"-routines fysiek opnieuw trainen of een benadering van verwijdering gebruiken met gecertificeerde unlearning-algoritmen.                                           |   2   |  D   |
| 11.2.3 | Controleer of de evaluatie van het shadow-model bewijst dat vergeten records minder dan 1% van de output beïnvloeden na unlearning.                                                                  |   2   |  V   |
| 11.2.4 | Controleer of verwijderingsgebeurtenissen onveranderlijk worden vastgelegd en controleerbaar zijn voor toezichthouders.                                                                              |   3   |  V   |

---

## 11.3 Bescherming van differentiële privacy

|   #    | Description                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Controleer of privacyverlies-rapportagedashboards waarschuwen wanneer de cumulatieve ε de beleidsdrempels overschrijdt. |   2   | D/V  |
| 11.3.2 | Verifieer dat black-box privacy audits ε̂ binnen 10% van de opgegeven waarde schatten.                                  |   2   |  V   |
| 11.3.3 | Controleer of formele bewijzen alle na-training finesse-aanpassingen en embeddings omvatten.                            |   3   |  V   |

---

## 11.4 Doelbeperking en bescherming tegen scope creep

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Controleer of elke dataset en modelcheckpoint een machinelesbare doelaanduiding draagt die overeenkomt met de oorspronkelijke toestemming.   |   1   |  D   |
| 11.4.2 | Verifieer dat runtime monitors queries detecteren die niet consistent zijn met het verklaarde doel en een zachte weigering activeren.        |   1   | D/V  |
| 11.4.3 | Verifieer dat beleid-als-code poorten het opnieuw implementeren van modellen naar nieuwe domeinen zonder DPIA-beoordeling blokkeren.         |   3   |  D   |
| 11.4.4 | Controleer of formele traceerbaarheidsbewijzen aantonen dat elke levenscyclus van persoonlijke gegevens binnen het toegestane bereik blijft. |   3   |  V   |

---

## 11.5 Toestemmingsbeheer en Wettige Grondslag Tracking

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Controleer of een Consent-Management Platform (CMP) de toestemmingsstatus, het doel en de bewaartermijn per betrokkene vastlegt. |   1   | D/V  |
| 11.5.2 | Controleer of API's toestemmings tokens onthullen; modellen moeten het tokenbereik valideren voordat ze inferentie uitvoeren.    |   2   |  D   |
| 11.5.3 | Verifieer dat geweigerde of ingetrokken toestemming de verwerkingspijplijnen binnen 24 uur stopzet.                              |   2   | D/V  |

---

## 11.6 Gefedereerd leren met privacycontroles

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.6.1 | Controleer of clientupdates lokale differentiële privacyruis toevoegen voordat ze worden geaggregeerd.             |   1   |  D   |
| 11.6.2 | Controleer of trainingsstatistieken differentieel privé zijn en nooit het verlies van een enkele cliënt onthullen. |   2   | D/V  |
| 11.6.3 | Controleer of vergiftigingsbestendige aggregatie (bijv. Krum/Trimmed-Mean) is ingeschakeld.                        |   2   |  V   |
| 11.6.4 | Verifieer dat formele bewijzen het totale ε-budget aantonen met minder dan 5 nutverlies.                           |   3   |  V   |

---

### Referenties

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

