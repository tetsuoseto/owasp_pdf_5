# 10 Gegnerschaftliche Robustheit und Datenschutzabwehr

## Kontrollziel

Stellen Sie sicher, dass KI-Modelle zuverlässig, datenschutzwahrend und missbrauchsresistent bleiben, wenn sie Evasion-, Inferenz-, Extraktions- oder Vergiftungsangriffen ausgesetzt sind.

---

## 10.1 Modellanpassung & Sicherheit

Schützen Sie vor schädlichen oder gegen Richtlinien verstoßenden Ausgaben.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Stellen Sie sicher, dass ein Alignment-Test-Suite (Red-Team-Eingabeaufforderungen, Jailbreak-Tests, nicht erlaubte Inhalte) versioniert und bei jeder Modellfreigabe ausgeführt wird. |   1   | D/V  |
| 10.1.2 | Überprüfen Sie, ob Ablehnungs- und sichere Abschluss-Schutzmechanismen durchgesetzt werden.                                                                                           |   1   |  D   |
| 10.1.3 | Überprüfen Sie, ob ein automatisierter Bewertungsautomat die Schadstoffrate misst und Rückschritte, die einen festgelegten Schwellenwert überschreiten, kennzeichnet.                 |   2   | D/V  |
| 10.1.4 | Überprüfen Sie, ob das Counter-Jailbreak-Training dokumentiert und reproduzierbar ist.                                                                                                |   2   |  D   |
| 10.1.5 | Überprüfen Sie, ob formale Richtlinien-Konformitätsnachweise oder zertifizierte Überwachungen kritische Bereiche abdecken.                                                            |   3   |  V   |

---

## 10.2 Härtung gegen adversarielle Beispiele

Erhöhen Sie die Widerstandsfähigkeit gegen manipulierte Eingaben. Robustes adversariales Training und Benchmark-Bewertungen sind derzeit der beste Standard.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.2.1 | Überprüfen Sie, ob die Projekt-Repositorien adversariale Training-Konfigurationen mit reproduzierbaren Seeds enthalten.                          |   1   |  D   |
| 10.2.2 | Überprüfen Sie, ob die Erkennung von adversarialen Beispielen in Produktionspipelines Blockierungswarnungen auslöst.                             |   2   | D/V  |
| 10.2.4 | Verifizieren Sie, dass zertifizierte Robustheitsnachweise oder Intervallgrenzzertifikate mindestens die wichtigsten kritischen Klassen abdecken. |   3   |  V   |
| 10.2.5 | Überprüfen Sie, dass Regressions tests adaptive Angriffe verwenden, um keinen messbaren Robustheitsverlust zu bestätigen.                        |   3   |  V   |

---

## 10.3 Minderungsmaßnahmen gegen Mitgliedschafts-Inferenz

Begrenzen Sie die Fähigkeit zu entscheiden, ob ein Datensatz im Trainingsdatenbestand enthalten war. Differentielle Privatsphäre und das Maskieren von Vertrauensscores bleiben die bekanntesten und effektivsten Abwehrmaßnahmen.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Überprüfen Sie, ob die Entropieregulierung pro Abfrage oder Temperaturskalierung übermäßige Zuversicht bei Vorhersagen reduziert.                   |   1   |  D   |
| 10.3.2 | Überprüfen Sie, ob das Training eine ε-begrenzte differentielle Privatsphäre-Optimierung für sensible Datensätze verwendet.                         |   2   |  D   |
| 10.3.3 | Überprüfen Sie, dass Angriffssimulationen (Shadow-Modell oder Black-Box) eine Angriffs-AUC ≤ 0,60 bei nicht verwendeten (Hold-out) Daten aufweisen. |   2   |  V   |

---

## 10.4 Widerstandsfähigkeit gegen Modellinversion

Verhindern Sie die Rekonstruktion privater Attribute. Aktuelle Umfragen betonen die Ausgabeabschnittung und DP-Garantien als praktikable Schutzmaßnahmen.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Stellen Sie sicher, dass sensible Attribute niemals direkt ausgegeben werden; verwenden Sie, wo nötig, Kategorien oder Einwegtransformationen. |   1   |  D   |
| 10.4.2 | Überprüfen Sie, ob Abfrage-Ratenbegrenzungen wiederholte adaptive Abfragen vom selben Prinzipal drosseln.                                      |   1   | D/V  |
| 10.4.3 | Überprüfen Sie, ob das Modell mit datenschutzfreundlichem Rauschen trainiert wurde.                                                            |   2   |  D   |

---

## 10.5 Verteidigung gegen Modell-Extraktion

Erkennung und Verhinderung unerlaubter Klonung. Wasserzeichen und Analyse von Abfragemustern werden empfohlen.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.5.1 | Überprüfen Sie, dass Inferenz-Gateways globale und pro-API-Schlüssel festgelegte Grenzwerte für die Anfragerate durchsetzen, die auf die Merkfähigkeitsgrenze des Modells abgestimmt sind. |   1   |  D   |
| 10.5.2 | Überprüfen Sie, dass die Statistiken zur Abfrage-Entropie und Eingabe-Mehrzahligkeit einen automatisierten Extraktionsdetektor speisen.                                                    |   2   | D/V  |
| 10.5.3 | Überprüfen Sie, dass fragile oder probabilistische Wasserzeichen mit p < 0,01 in ≤ 1.000 Anfragen gegen einen verdächtigten Klon nachgewiesen werden können.                               |   2   |  V   |
| 10.5.4 | Stellen Sie sicher, dass Wasserzeichen-Schlüssel und Auslöse-Sets in einem Hardware-Sicherheitsmodul gespeichert und jährlich rotiert werden.                                              |   3   |  D   |
| 10.5.5 | Stellen Sie sicher, dass Extraktionswarnungsereignisse die anstößigen Abfragen enthalten und in Incident-Response-Playbooks integriert sind.                                               |   3   |  V   |

---

## 10.6 Erkennung von vergifteten Daten zur Inferenzzeit

Erkennen und Neutralisieren von mit Hintertüren versehenen oder vergifteten Eingaben.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.6.1 | Überprüfen Sie, dass die Eingaben vor der Modellausführung durch einen Anomalie-Detektor (z.B. STRIP, Konsistenzbewertung) geleitet werden.                              |   1   |  D   |
| 10.6.2 | Überprüfen Sie, dass die Detektorschwellen auf sauberen/vergifteten Validierungssätzen so eingestellt sind, dass weniger als 5 % Fehlalarme (False Positives) auftreten. |   1   |  V   |
| 10.6.3 | Überprüfen Sie, ob als vergiftet gekennzeichnete Eingaben eine Soft-Blockierung und menschliche Überprüfungsprozesse auslösen.                                           |   2   |  D   |
| 10.6.4 | Stellen Sie sicher, dass Detektoren mit adaptiven, triggerlosen Backdoor-Angriffen einem Stresstest unterzogen werden.                                                   |   2   |  V   |
| 10.6.5 | Stellen Sie sicher, dass Metriken zur Wirksamkeit der Erkennung protokolliert und regelmäßig mit aktuellen Bedrohungsinformationen neu bewertet werden.                  |   3   |  D   |

---

## 10.7 Dynamische Anpassung der Sicherheitspolitik

Echtzeit-Aktualisierungen der Sicherheitspolitik basierend auf Bedrohungsinformationen und Verhaltensanalysen.

|   #    | Description                                                                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Überprüfen Sie, dass Sicherheitsrichtlinien dynamisch aktualisiert werden können, ohne den Agenten neu zu starten, und dabei die Integrität der Richtlinienversion erhalten bleibt. |   1   | D/V  |
| 10.7.2 | Überprüfen Sie, dass Richtlinienaktualisierungen kryptografisch von autorisiertem Sicherheitspersonal signiert und vor der Anwendung validiert werden.                              |   2   | D/V  |
| 10.7.3 | Stellen Sie sicher, dass dynamische Richtlinienänderungen mit vollständigen Prüfpfaden protokolliert werden, einschließlich Begründung, Genehmigungsketten und Rücksetzverfahren.   |   2   | D/V  |
| 10.7.4 | Überprüfen Sie, ob adaptive Sicherheitsmechanismen die Sensitivität der Bedrohungserkennung basierend auf dem Risikokontext und Verhaltensmustern anpassen.                         |   3   | D/V  |
| 10.7.5 | Stellen Sie sicher, dass Entscheidungen zur Richtlinienanpassung nachvollziehbar sind und Beweisführungen für die Überprüfung durch das Sicherheitsteam enthalten.                  |   3   | D/V  |

---

## 10.8 Reflexionsbasierte Sicherheitsanalyse

Sicherheitsvalidierung durch agenteninterne Selbstreflexion und metakognitive Analyse.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.8.1 | Stellen Sie sicher, dass Agenten-Reflexionsmechanismen eine sicherheitsorientierte Selbstbewertung von Entscheidungen und Handlungen umfassen.                           |   1   | D/V  |
| 10.8.2 | Stellen Sie sicher, dass Ausgabe von Reflection validiert werden, um die Manipulation von Selbstbewertungsmechanismen durch feindliche Eingaben zu verhindern.           |   2   | D/V  |
| 10.8.3 | Überprüfen Sie, ob die metakognitive Sicherheitsanalyse potenzielle Verzerrungen, Manipulationen oder Kompromittierungen in den Denkprozessen des Agenten identifiziert. |   2   | D/V  |
| 10.8.4 | Überprüfen Sie, ob sicherheitsrelevante Warnungen auf Reflexionsbasis eine verstärkte Überwachung und potenzielle menschliche Eingriffabläufe auslösen.                  |   3   | D/V  |
| 10.8.5 | Überprüfen Sie, ob kontinuierliches Lernen aus Sicherheitsreflexionen die Bedrohungserkennung verbessert, ohne die legitime Funktionalität zu beeinträchtigen.           |   3   | D/V  |

---

## 10.9 Evolution & Selbstverbesserungssicherheit

Sicherheitskontrollen für Agentensysteme, die zur Selbstmodifikation und Evolution fähig sind.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Verifizieren Sie, dass Selbstmodifikationsfähigkeiten auf ausgewiesene sichere Bereiche mit formalen Verifikationsgrenzen beschränkt sind.    |   1   | D/V  |
| 10.9.2 | Stellen Sie sicher, dass Änderungsvorschläge vor der Umsetzung einer Sicherheitsauswirkungsbewertung unterzogen werden.                       |   2   | D/V  |
| 10.9.3 | Überprüfen Sie, ob Selbstverbesserungsmechanismen Rücksetzfunktionen mit Integritätsprüfung umfassen.                                         |   2   | D/V  |
| 10.9.4 | Verifizieren Sie, dass Meta-Lern-Sicherheit die adversarielle Manipulation von Verbesserungsalgorithmen verhindert.                           |   3   | D/V  |
| 10.9.5 | Überprüfen Sie, dass rekursive Selbstverbesserung durch formale Sicherheitsvorgaben begrenzt ist, mit mathematischen Beweisen der Konvergenz. |   3   | D/V  |

---

### Referenzen

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

