# C3 Modell-Lifecycle-Management und Änderungssteuerung

## Kontrollziel

KI-Systeme müssen Prozess zur Änderungssteuerung implementieren, die verhindern, dass unautorisierte oder unsichere Modelländerungen in die Produktion gelangen. Diese Kontrolle gewährleistet die Integrität des Modells während des gesamten Lebenszyklus – von der Entwicklung über die Bereitstellung bis zur Außerbetriebnahme – und ermöglicht eine schnelle Reaktion auf Vorfälle sowie die Nachverfolgbarkeit aller Änderungen.

Kernziel der Sicherheit: Nur autorisierte, validierte Modelle gelangen durch kontrollierte Prozesse, die Integrität, Rückverfolgbarkeit und Wiederherstellbarkeit gewährleisten, in die Produktion.

---

## C3.1 Modellautorisierung & Integrität

Nur autorisierte Modelle mit überprüfter Integrität gelangen in Produktionsumgebungen.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Überprüfen Sie, ob alle Modellartefakte (Gewichte, Konfigurationen, Tokenizer) vor der Bereitstellung kryptografisch von autorisierten Stellen signiert sind.                                                                            |   1   | D/V  |
| 3.1.2 | Stellen Sie sicher, dass die Modellintegrität zum Zeitpunkt der Bereitstellung validiert wird und Signaturprüfungsfehler das Laden des Modells verhindern.                                                                               |   1   | D/V  |
| 3.1.3 | Überprüfen Sie, dass die Herkunftsnachweise des Modells die Identität der autorisierenden Instanz, Prüfsummen der Trainingsdaten, Validierungsergebnisse mit Bestehen/Nichtbestehen-Status sowie einen Erstellungszeitstempel enthalten. |   2   | D/V  |
| 3.1.4 | Stellen Sie sicher, dass alle Modell-Artefakte die semantische Versionsnummerierung (MAJOR.MINOR.PATCH) verwenden, mit dokumentierten Kriterien, die angeben, wann jede Versionskomponente erhöht wird.                                  |   2   | D/V  |
| 3.1.5 | Überprüfen Sie, ob die Abhängigkeitsverfolgung eine Echtzeit-Inventarisierung aufrechterhält, die eine schnelle Identifizierung aller verbrauchenden Systeme ermöglicht.                                                                 |   2   |  V   |

---

## C3.2 Modellvalidierung und -prüfung

Modelle müssen vor der Bereitstellung definierte Sicherheits- und Schutzvalidierungen bestehen.

|   #   | Description                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Stellen Sie sicher, dass Modelle automatisierten Sicherheitstests unterzogen werden, die Eingabevalidierung, Ausgabe-Sanitierung und Sicherheitsbewertungen mit vorher vereinbarten unternehmensinternen Bestehens-/Nichtbestehensgrenzen vor der Bereitstellung umfassen. |   1   | D/V  |
| 3.2.2 | Stellen Sie sicher, dass Validierungsfehler den Modelldeployment nach einer ausdrücklichen Überschreibungsfreigabe von vorab bestimmten autorisierten Personen mit dokumentierten geschäftlichen Begründungen automatisch blockieren.                                      |   1   | D/V  |
| 3.2.3 | Verifizieren Sie, dass die Testergebnisse kryptografisch signiert und unwiderruflich mit dem Hash der spezifischen Modellversion, die validiert wird, verknüpft sind.                                                                                                      |   2   |  V   |
| 3.2.4 | Stellen Sie sicher, dass Notfalleinsätze eine dokumentierte Sicherheitsrisikobewertung und die Genehmigung durch eine vorher festgelegte Sicherheitsbehörde innerhalb vorab vereinbarter Zeitrahmen erfordern.                                                             |   2   | D/V  |

---

## C3.3 Kontrollierte Bereitstellung & Rückrollverfahren

Modellbereitstellungen müssen kontrolliert, überwacht und reversibel sein.

|   #   | Description                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Stellen Sie sicher, dass Produktionsbereitstellungen schrittweise Rollout-Mechanismen (Canary-Deployments, Blue-Green-Deployments) mit automatisierten Rollback-Auslösern basierend auf vorab vereinbarten Fehlerraten, Latenzschwellen oder Sicherheitsalarmkriterien implementieren. |   1   |  D   |
| 3.3.2 | Überprüfen Sie, ob Rollback-Funktionen den vollständigen Modellzustand (Gewichte, Konfigurationen, Abhängigkeiten) atomar innerhalb vorab definierter organisatorischer Zeitfenster wiederherstellen.                                                                                  |   1   | D/V  |
| 3.3.3 | Überprüfen Sie, dass Bereitstellungsprozesse kryptografische Signaturen validieren und Integritätsprüfsummen berechnen, bevor das Modell aktiviert wird, und die Bereitstellung bei jeglicher Abweichung fehlschlägt.                                                                  |   2   | D/V  |
| 3.3.4 | Überprüfen Sie, ob die Notfallabschaltfunktionen des Modells in der Lage sind, Modellendpunkte innerhalb voreingestellter Reaktionszeiten durch automatisierte Stromkreise oder manuelle Abschaltvorrichtungen zu deaktivieren.                                                        |   2   | D/V  |
| 3.3.5 | Überprüfen Sie, ob Rollback-Artefakte (bisherige Modellversionen, Konfigurationen, Abhängigkeiten) gemäß den organisatorischen Richtlinien mit unveränderbarem Speicher für die Vorfallreaktion aufbewahrt werden.                                                                     |   2   |  V   |

---

## C3.4 Verantwortlichkeit und Überprüfung

Alle Änderungen am Modell-Lebenszyklus müssen nachvollziehbar und prüfbar sein.

|   #   | Description                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Stellen Sie sicher, dass alle Modelländerungen (Bereitstellung, Konfiguration, Stilllegung) unveränderliche Auditprotokolle erzeugen, die einen Zeitstempel, eine authentifizierte Akteursidentität, eine Änderungsart sowie Vorher-/Nachher-Zustände enthalten.       |   1   |  V   |
| 3.4.2 | Überprüfen Sie, dass der Zugriff auf das Prüfprotokoll eine entsprechende Autorisierung erfordert und alle Zugriffsversuche mit Benutzeridentität und Zeitstempel protokolliert werden.                                                                                |   2   | D/V  |
| 3.4.3 | Stellen Sie sicher, dass Prompt-Vorlagen und Systemnachrichten in Git-Repositories versionskontrolliert sind und vor der Bereitstellung eine obligatorische Codeüberprüfung und Freigabe durch festgelegte Prüfer erfolgen.                                            |   2   | D/V  |
| 3.4.4 | Überprüfen Sie, ob Audit-Protokolle ausreichend Details enthalten (Modell-Hashes, Konfigurations-Snapshots, Abhängigkeitsversionen), um eine vollständige Rekonstruktion des Modellzustands für jeden Zeitstempel innerhalb des Aufbewahrungszeitraums zu ermöglichen. |   2   |  V   |

---

## C3.5 Sichere Entwicklungsmethoden

Modellentwicklung und Trainingsprozesse müssen sicheren Praktiken folgen, um Kompromittierungen zu vermeiden.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Stellen Sie sicher, dass Entwicklungs-, Test- und Produktionsumgebungen physisch oder logisch getrennt sind. Sie verfügen über keine gemeinsame Infrastruktur, unterschiedliche Zugriffskontrollen und isolierte Datenspeicher.                            |   1   |  D   |
| 3.5.2 | Stellen Sie sicher, dass Modelltraining und Feinabstimmung in isolierten Umgebungen mit kontrolliertem Netzwerkzugang erfolgen.                                                                                                                            |   1   |  D   |
| 3.5.3 | Stellen Sie sicher, dass Trainingsdatenquellen vor der Verwendung in der Modellentwicklung durch Integritätsprüfungen validiert und über vertrauenswürdige Quellen mit dokumentierter Herkunftskette authentifiziert werden.                               |   1   | D/V  |
| 3.5.4 | Stellen Sie sicher, dass Artefakte der Modellentwicklung (Hyperparameter, Trainingsskripte, Konfigurationsdateien) in der Versionskontrolle gespeichert werden und vor der Verwendung im Training die Genehmigung durch eine Peer-Review erforderlich ist. |   2   |  D   |

---

## C3.6 Modell-Rückzug und Stilllegung

Modelle müssen sicher außer Betrieb genommen werden, wenn sie nicht mehr benötigt werden oder wenn Sicherheitsprobleme erkannt werden.

|   #   | Description                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.6.1 | Überprüfen Sie, ob die Modelleinstellungen zur Außerdienststellung automatisch Abhängigkeitsgraphen scannen, alle nutzenden Systeme identifizieren und vor der Stilllegung vorab vereinbarte Ankündigungsfristen einhalten.                            |   1   |  D   |
| 3.6.2 | Stellen Sie sicher, dass archivierte Modell-Artefakte gemäß dokumentierten Datenaufbewahrungsrichtlinien sicher mittels kryptografischer Löschung oder mehrfacher Überschreibung gelöscht werden, wobei zertifizierte Vernichtungsnachweise vorliegen. |   1   | D/V  |
| 3.6.3 | Stellen Sie sicher, dass Modell-Ausmusterungsereignisse mit Zeitstempel und Akteur-Identität protokolliert werden und Modell-Signaturen widerrufen werden, um eine Wiederverwendung zu verhindern.                                                     |   2   |  V   |
| 3.6.4 | Überprüfen Sie, ob die Notfallmodell-Ruhestellung den Modellzugriff innerhalb vorab festgelegter Notfallreaktionszeiten durch automatisierte Abschaltsysteme deaktivieren kann, falls kritische Sicherheitslücken entdeckt werden.                     |   2   | D/V  |

---

## Literaturverzeichnis

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

