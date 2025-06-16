# Anhang D: KI-gestützte Governance und Verifizierung sicherer Programmierung

## Zielsetzung

Dieses Kapitel definiert grundlegende organisatorische Kontrollen für die sichere und effektive Nutzung von KI-unterstützten Codierwerkzeugen während der Softwareentwicklung und gewährleistet Sicherheit und Nachverfolgbarkeit über den gesamten SDLC hinweg.

---

## AD.1 KI-unterstützter Workflow für sicheres Programmieren

Integrieren Sie KI-Tools in den sicheren Software-Entwicklungslebenszyklus (Secure Software Development Lifecycle, SSDLC) der Organisation, ohne die bestehenden Sicherheitsbarrieren zu schwächen.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Überprüfen Sie, ob ein dokumentierter Arbeitsablauf beschreibt, wann und wie KI-Werkzeuge Code generieren, refaktorieren oder überprüfen können.                                |   1   | D/V  |
| AD.1.2 | Überprüfen Sie, ob der Workflow jeder Phase des sicheren Softwareentwicklungszyklus (SSDLC) zugeordnet ist (Design, Implementierung, Code-Überprüfung, Testen, Bereitstellung). |   2   |  D   |
| AD.1.3 | Überprüfen Sie, ob Metriken (z. B. Verwundbarkeitsdichte, mittlere Erkennungszeit) für AI-erzeugten Code erfasst und mit rein menschlichen Referenzwerten verglichen werden.    |   3   | D/V  |

---

## AD.2 KI-Werkzeugqualifikation & Bedrohungsmodellierung

Stellen Sie sicher, dass KI-Codierungswerkzeuge vor der Einführung auf Sicherheitsfunktionen, Risiken und Auswirkungen auf die Lieferkette bewertet werden.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Stellen Sie sicher, dass ein Bedrohungsmodell für jedes KI-Tool Missbrauch, Modell-Inversion, Datenleckage und Risiken in der Abhängigkeitskette identifiziert.                                            |   1   | D/V  |
| AD.2.2 | Stellen Sie sicher, dass Toolbewertungen statische/dynamische Analysen aller lokalen Komponenten sowie die Bewertung von SaaS-Endpunkten (TLS, Authentifizierung/Autorisierung, Protokollierung) umfassen. |   2   |  D   |
| AD.2.3 | Stellen Sie sicher, dass Bewertungen einem anerkannten Rahmenwerk folgen und nach größeren Versionsänderungen erneut durchgeführt werden.                                                                  |   3   | D/V  |

---

## AD.3 Sicheres Prompt- und Kontextmanagement

Verhindern Sie das Austreten von Geheimnissen, proprietärem Code und persönlichen Daten beim Erstellen von Eingabeaufforderungen oder Kontexten für KI-Modelle.

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Verifizieren Sie, dass schriftliche Richtlinien das Senden von Geheimnissen, Zugangsdaten oder geheimen Informationen in Eingabeaufforderungen untersagen.                                                        |   1   | D/V  |
| AD.3.2 | Überprüfen Sie, ob technische Kontrollen (Redaktion auf der Client-Seite, genehmigte Kontextfilter) automatisch sensible Artefakte entfernen.                                                                     |   2   |  D   |
| AD.3.3 | Verifizieren Sie, dass Aufforderungen und Antworten tokenisiert, während der Übertragung und im Ruhezustand verschlüsselt sind und die Aufbewahrungsfristen den Richtlinien zur Datenklassifizierung entsprechen. |   3   | D/V  |

---

## AD.4 Validierung von KI-generiertem Code

Erkennen und Beheben von Schwachstellen, die durch KI-Ausgaben eingeführt wurden, bevor der Code zusammengeführt oder bereitgestellt wird.

|   #    | Description                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Stellen Sie sicher, dass von KI generierter Code stets einer manuellen Codeüberprüfung unterzogen wird.                                                                                         |   1   | D/V  |
| AD.4.2 | Stellen Sie sicher, dass automatisierte Scanner (SAST/IAST/DAST) bei jedem Pull Request mit KI-generiertem Code ausgeführt werden und bei kritischen Befunden die Zusammenführungen blockieren. |   2   |  D   |
| AD.4.3 | Überprüfen Sie, dass differenzielles Fuzz-Testing oder eigenschaftsbasierte Tests sicherheitskritische Verhaltensweisen (z. B. Eingabevalidierung, Autorisierungslogik) nachweisen.             |   3   | D/V  |

---

## AD.5 Erklärbarkeit und Rückverfolgbarkeit von Codevorschlägen

Bieten Sie Prüfern und Entwicklern Einblick darin, warum ein Vorschlag gemacht wurde und wie er sich entwickelt hat.

|   #    | Description                                                                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Überprüfen Sie, ob Prompt-/Antwortpaare mit Commit-IDs protokolliert werden.                                                                                                                                      |   1   | D/V  |
| AD.5.2 | Überprüfen Sie, ob Entwickler Modellquellen (Trainingsausschnitte, Dokumentation) anzeigen können, die eine Vorschlag unterstützen.                                                                               |   2   |  D   |
| AD.5.3 | Stellen Sie sicher, dass Erklärbarkeitsberichte zusammen mit Design-Artefakten gespeichert und in Sicherheitsbewertungen referenziert werden, um die Rückverfolgbarkeitsprinzipien der ISO/IEC 42001 zu erfüllen. |   3   | D/V  |

---

## AD.6 Kontinuierliches Feedback & Feinabstimmung des Modells

Verbessern Sie die Sicherheitsleistung des Modells im Laufe der Zeit, während Sie negative Abweichungen verhindern.

|   #    | Description                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.6.1 | Überprüfen Sie, dass Entwickler unsichere oder nicht konforme Vorschläge kennzeichnen können und dass diese Kennzeichnungen erfasst werden.                                                                              |   1   | D/V  |
| AD.6.2 | Stellen Sie sicher, dass aggregiertes Feedback die periodische Feinabstimmung oder retrieval-unterstützte Generierung mit überprüften, sicherheitsorientierten Codierungs-Corpora (z. B. OWASP Cheat Sheets) informiert. |   2   |  D   |
| AD.6.3 | Überprüfen Sie, dass ein Closed-Loop-Auswertungssystem nach jeder Feinabstimmung Regressionstests durchführt; Sicherheitsmetriken müssen vor der Bereitstellung frühere Baselines erreichen oder übertreffen.            |   3   | D/V  |

---

### Quellenangaben

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

