# C13 Menschliche Aufsicht, Rechenschaftspflicht und Governance

## Kontrollziel

Dieses Kapitel enthält Anforderungen zur Aufrechterhaltung der menschlichen Aufsicht und klarer Verantwortlichkeitsketten in KI-Systemen und stellt Erklärbarkeit, Transparenz und ethische Führung im gesamten KI-Lebenszyklus sicher.

---

## C13.1 Not-Aus- und Überschreibemechanismen

Stellen Sie Abschalt- oder Rücksetzwege bereit, wenn unsicheres Verhalten des KI-Systems beobachtet wird.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Verifizieren Sie, dass ein manueller Notausschalter vorhanden ist, um die Inferenz und Ausgabe des KI-Modells sofort zu stoppen. |   1   | D/V  |
| 13.1.2 | Stellen Sie sicher, dass Override-Steuerungen nur für autorisiertes Personal zugänglich sind.                                    |   1   |  D   |
| 13.1.3 | Überprüfen Sie, dass Rücksetzverfahren zu vorherigen Modellversionen oder zum sicheren Betriebsmodus zurückkehren können.        |   3   | D/V  |
| 13.1.4 | Stellen Sie sicher, dass Übersteuerungsmechanismen regelmäßig getestet werden.                                                   |   3   |  V   |

---

## C13.2 Mensch-im-Loop Entscheidungsprüfpunkte

Erfordern Sie menschliche Genehmigungen, wenn die Einsätze vordefinierte Risikoschwellen überschreiten.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Stellen Sie sicher, dass KI-Entscheidungen mit hohem Risiko vor der Ausführung eine ausdrückliche menschliche Genehmigung erfordern.                                                          |   1   | D/V  |
| 13.2.2 | Stellen Sie sicher, dass Risikoschwellenwerte klar definiert sind und automatisch menschliche Überprüfungsabläufe auslösen.                                                                   |   1   |  D   |
| 13.2.3 | Stellen Sie sicher, dass zeitkritische Entscheidungen über Ausweichverfahren verfügen, wenn eine menschliche Genehmigung innerhalb der erforderlichen Zeitrahmen nicht eingeholt werden kann. |   2   |  D   |
| 13.2.4 | Stellen Sie sicher, dass Eskalationsverfahren klare Autoritätsstufen für verschiedene Entscheidungstypen oder Risikokategorien definieren, falls zutreffend.                                  |   3   | D/V  |

---

## C13.3 Verantwortlichkeitskette & Prüfbarkeit

Protokollieren Sie Bedieneraktionen und Modellentscheidungen.

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.3.1 | Stellen Sie sicher, dass alle Entscheidungen des KI-Systems und menschliche Interventionen mit Zeitstempeln, Benutzeridentitäten und Entscheidungsbegründungen protokolliert werden. |   1   | D/V  |
| 13.3.2 | Stellen Sie sicher, dass Audit-Logs nicht manipuliert werden können und Integritätsprüfmechanismen enthalten.                                                                        |   2   |  D   |

---

## C13.4 Erklärbare KI-Techniken

Oberflächenmerkmal-Wichtigkeit, Gegenfaktische und lokale Erklärungen.

|   #    | Description                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Überprüfen Sie, ob KI-Systeme grundlegende Erklärungen für ihre Entscheidungen in einem für Menschen lesbaren Format bereitstellen.                                                 |   1   | D/V  |
| 13.4.2 | Stellen Sie sicher, dass die Qualität der Erklärung durch menschliche Evaluationsstudien und Metriken validiert wird.                                                               |   2   |  V   |
| 13.4.3 | Stellen Sie sicher, dass Merkmalswichtigkeitswerte oder Attributionsmethoden (SHAP, LIME usw.) für kritische Entscheidungen verfügbar sind.                                         |   3   | D/V  |
| 13.4.4 | Überprüfen Sie, ob kontrafaktische Erklärungen zeigen, wie Eingaben geändert werden könnten, um Ergebnisse zu verändern, falls dies auf den Anwendungsfall und die Domäne zutrifft. |   3   |  V   |

---

## C13.5 Modellkarten & Nutzungshinweise

Pflegen Sie Modellkarten für die beabsichtigte Nutzung, Leistungsmetriken und ethische Überlegungen.

|   #    | Description                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Verifizieren Sie, dass Modellkarten die beabsichtigten Anwendungsfälle, Einschränkungen und bekannten Ausfallmodi dokumentieren.                                                                                              |   1   |  D   |
| 13.5.2 | Stellen Sie sicher, dass Leistungskennzahlen für verschiedene anwendbare Anwendungsfälle offengelegt werden.                                                                                                                  |   1   | D/V  |
| 13.5.3 | Stellen Sie sicher, dass ethische Überlegungen, Bewertungen von Verzerrungen, Fairness-Analysen, Merkmale der Trainingsdaten und bekannte Einschränkungen der Trainingsdaten dokumentiert und regelmäßig aktualisiert werden. |   2   |  D   |
| 13.5.4 | Stellen Sie sicher, dass Modellkarten versionskontrolliert sind und während des gesamten Modelllebenszyklus mit Änderungsverfolgung gepflegt werden.                                                                          |   2   | D/V  |

---

## C13.6 Unsicherheitsquantifizierung

Verbreiten Sie Vertrauenswerte oder Entropie-Maße in den Antworten.

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.6.1 | Überprüfen Sie, ob KI-Systeme mit ihren Ausgaben Vertrauenswerte oder Unsicherheitsmaße bereitstellen.                               |   1   |  D   |
| 13.6.2 | Überprüfen Sie, ob Unsicherheitsschwellenwerte eine zusätzliche menschliche Überprüfung oder alternative Entscheidungswege auslösen. |   2   | D/V  |
| 13.6.3 | Überprüfen Sie, ob Unsicherheitsquantifizierungsmethoden kalibriert sind und anhand von Referenzdaten validiert werden.              |   2   |  V   |
| 13.6.4 | Stellen Sie sicher, dass die Unsicherheitsfortpflanzung durch mehrstufige KI-Workflows erhalten bleibt.                              |   3   | D/V  |

---

## C13.7 Benutzerorientierte Transparenzberichte

Stellen Sie regelmäßige Offenlegungen zu Vorfällen, Drift und Datennutzung bereit.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Stellen Sie sicher, dass die Richtlinien zur Datennutzung und die Praktiken zum Management der Nutzereinwilligung klar an die Beteiligten kommuniziert werden. |   1   | D/V  |
| 13.7.2 | Überprüfen Sie, dass KI-Auswirkungsbewertungen durchgeführt werden und die Ergebnisse in die Berichterstattung einfließen.                                     |   2   | D/V  |
| 13.7.3 | Überprüfen Sie, ob regelmäßig veröffentlichte Transparenzberichte KI-Vorfälle und Betriebskennzahlen in angemessenem Detail offenlegen.                        |   2   | D/V  |

### Referenzen

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

