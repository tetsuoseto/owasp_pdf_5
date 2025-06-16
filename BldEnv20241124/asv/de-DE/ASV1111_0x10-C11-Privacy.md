# 11 Datenschutz und Verwaltung personenbezogener Daten

## Kontrollziel

Gewährleisten Sie strenge Datenschutzgarantien über den gesamten KI-Lebenszyklus hinweg – Sammlung, Training, Inferenz und Vorfallreaktion – sodass personenbezogene Daten nur mit klarer Einwilligung, auf das notwendige Minimum beschränkt, mit nachweisbarer Löschung und formellen Datenschutzgarantien verarbeitet werden.

---

## 11.1 Anonymisierung & Datenminimierung

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Überprüfen Sie, ob direkte und quasi-Identifikatoren entfernt oder gehasht wurden.                                                                                         |   1   | D/V  |
| 11.1.2 | Überprüfen Sie, ob automatisierte Prüfungen k-Anonymität/l-Diversität messen und eine Warnung ausgeben, wenn die Schwellenwerte unter die Richtlinie fallen.               |   2   | D/V  |
| 11.1.3 | Überprüfen Sie, dass die Berichte zur Merkmalswichtigkeit des Modells keinen Identifier-Durchfluss über ε = 0,01 wechselseitige Information hinaus nachweisen.             |   2   |  V   |
| 11.1.4 | Überprüfen Sie, dass formale Beweise oder Zertifizierungen mit synthetischen Daten das Risiko einer Re-Identifizierung ≤ 0,05 auch unter Verknüpfungsangriffen nachweisen. |   3   |  V   |

---

## 11.2 Recht auf Vergessenwerden und Durchsetzung der Löschung

|   #    | Description                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Überprüfen Sie, dass Löschanfragen von Datenbetroffenen innerhalb von Service-Level-Vereinbarungen von weniger als 30 Tagen auf Rohdatensätze, Checkpoints, Einbettungen, Protokolle und Sicherungskopien übertragen werden. |   1   | D/V  |
| 11.2.2 | Überprüfen Sie, dass "Machine-Unlearning"-Routinen physisch nachtrainieren oder eine Annäherung der Entfernung mithilfe zertifizierter Unlearning-Algorithmen durchführen.                                                   |   2   |  D   |
| 11.2.3 | Überprüfen Sie, dass die Bewertung des Schattenmodells nachweist, dass vergessene Datensätze weniger als 1 % der Ausgaben nach dem Unlearning beeinflussen.                                                                  |   2   |  V   |
| 11.2.4 | Stellen Sie sicher, dass Löschvorgänge unveränderlich protokolliert und für Aufsichtsbehörden prüfbar sind.                                                                                                                  |   3   |  V   |

---

## 11.3 Datenschutz mit Differenzieller Privatsphäre

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Überprüfen Sie, ob die Datenschutzverlust-Abrechnungs-Dashboards Alarm schlagen, wenn die kumulative ε die Richtliniengrenzen überschreitet. |   2   | D/V  |
| 11.3.2 | Überprüfen Sie, ob Black-Box-Datenschutzprüfungen ε̂ innerhalb von 10 % des angegebenen Werts schätzen.                                      |   2   |  V   |
| 11.3.3 | Überprüfen Sie, dass formale Beweise alle nach dem Training durchgeführten Feinabstimmungen und Einbettungen abdecken.                       |   3   |  V   |

---

## 11.4 Zweckbindung und Schutz vor Funktionsumfang-Überschreitung

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.4.1 | Stellen Sie sicher, dass jeder Datensatz und jeder Modell-Checkpoint einen maschinenlesbaren Zweck-Tag trägt, der mit der ursprünglichen Einwilligung übereinstimmt.     |   1   |  D   |
| 11.4.2 | Überprüfen Sie, ob Laufzeitüberwachungen Abfragen erkennen, die mit dem erklärten Zweck unvereinbar sind, und eine sanfte Verweigerung auslösen.                         |   1   | D/V  |
| 11.4.3 | Überprüfen Sie, dass Richtlinien-als-Code-Gates die erneute Bereitstellung von Modellen in neuen Domänen ohne DPIA-Prüfung blockieren.                                   |   3   |  D   |
| 11.4.4 | Verifizieren Sie, dass formale Nachverfolgbarkeitsnachweise zeigen, dass jeder Lebenszyklus personenbezogener Daten innerhalb des einwilligungsbasierten Rahmens bleibt. |   3   |  V   |

---

## 11.5 Einwilligungsverwaltung und rechtmäßige Grundlage für Tracking

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.5.1 | Überprüfen Sie, ob eine Consent-Management-Plattform (CMP) den Opt-in-Status, den Zweck und die Aufbewahrungsdauer für jede betroffene Person erfasst. |   1   | D/V  |
| 11.5.2 | Überprüfen Sie, dass APIs Zustimmungs-Token bereitstellen; Modelle müssen den Token-Bereich vor der Inferenz validieren.                               |   2   |  D   |
| 11.5.3 | Verifizieren Sie, dass verweigerte oder widerrufene Einwilligungen die Verarbeitungspipelines innerhalb von 24 Stunden stoppen.                        |   2   | D/V  |

---

## 11.6 Föderiertes Lernen mit Datenschutzkontrollen

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Überprüfen Sie, dass Client-Updates vor der Aggregation eine lokale Differential Privacy-Rauschzugabe verwenden.                 |   1   |  D   |
| 11.6.2 | Stellen Sie sicher, dass Trainingsmetriken differenziell privat sind und niemals den Verlust eines einzelnen Clients offenlegen. |   2   | D/V  |
| 11.6.3 | Stellen Sie sicher, dass eine gegen Manipulation resistente Aggregation (z. B. Krum/Trimmed-Mean) aktiviert ist.                 |   2   |  V   |
| 11.6.4 | Überprüfen Sie, dass formale Beweise das gesamte ε-Budget mit weniger als 5 Nutzungsverlusten nachweisen.                        |   3   |  V   |

---

### Referenzen

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

