# 9 Autonome Orchestrierung und agentisches Handlungssicherheitsmanagement

## Kontrollziel

Stellen Sie sicher, dass autonome oder Multi-Agenten-KI-Systeme nur Aktionen ausführen können, die ausdrücklich beabsichtigt, authentifiziert, auditierbar und innerhalb definierter Kosten- und Risikoschwellen liegen. Dies schützt vor Bedrohungen wie Kompromittierung autonomer Systeme, Fehlgebrauch von Werkzeugen, Erkennung von Agentenschleifen, Übernahme von Kommunikation, Identitätsfälschung, Schwarmmanipulation und Absichtsmanipulation.

---

## 9.1 Aufgabenplanung von Agenten und Rekursionsbudgets

Drosseln Sie rekursive Pläne und erzwingen Sie menschliche Kontrollpunkte für privilegierte Aktionen.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Stellen Sie sicher, dass maximale Rekursionstiefe, Breite, Echtzeitdauer, Tokens und monetäre Kosten pro Agenten-Ausführung zentral konfiguriert und versioniert sind.                                                |   1   | D/V  |
| 9.1.2 | Stellen Sie sicher, dass privilegierte oder irreversible Aktionen (z. B. Code-Commits, finanzielle Überweisungen) vor der Ausführung eine ausdrückliche menschliche Genehmigung über einen prüfbaren Kanal erfordern. |   1   | D/V  |
| 9.1.3 | Überprüfen Sie, ob Echtzeit-Ressourcenmonitore eine Unterbrechung des Circuit-Breakers auslösen, wenn eine Budgetgrenze überschritten wird, und dadurch die weitere Erweiterung der Aufgabe stoppen.                  |   2   |  D   |
| 9.1.4 | Überprüfen Sie, dass Circuit-Breaker-Ereignisse mit Agenten-ID, auslösendem Zustand und erfasstem Planstatus für die forensische Überprüfung protokolliert werden.                                                    |   2   | D/V  |
| 9.1.5 | Verifizieren Sie, dass Sicherheitstests Szenarien der Budgeterschöpfung und des ausufernden Plans abdecken und bestätigen Sie ein sicheres Anhalten ohne Datenverlust.                                                |   3   |  V   |
| 9.1.6 | Stellen Sie sicher, dass Budgetrichtlinien als Policy-as-Code formuliert und im CI/CD-Prozess durchgesetzt werden, um Konfigurationsabweichungen zu verhindern.                                                       |   3   |  D   |

---

## 9.2 Werkzeug-Plugin-Sandboxing

Isolieren Sie Werkzeuginteraktionen, um unbefugten Systemzugriff oder Codeausführung zu verhindern.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Stellen Sie sicher, dass jedes Werkzeug/Plugin innerhalb eines Betriebssystems, Containers oder einer WASM-Ebene-Sandbox mit minimalen Privilegien bezüglich Datei-System-, Netzwerk- und Systemaufruf-Richtlinien ausgeführt wird. |   1   | D/V  |
| 9.2.2 | Überprüfen Sie, ob die Ressourcenquoten des Sandkastens (CPU, Arbeitsspeicher, Festplatte, Netzwerkausgang) und die Ausführungszeitbegrenzungen durchgesetzt und protokolliert werden.                                              |   1   | D/V  |
| 9.2.3 | Stellen Sie sicher, dass Tool-Binärdateien oder -Deskriptoren digital signiert sind; Signaturen werden vor dem Laden überprüft.                                                                                                     |   2   | D/V  |
| 9.2.4 | Überprüfen Sie, dass die Sandbox-Telemetriedaten an ein SIEM übertragen werden; Anomalien (z. B. versuchte ausgehende Verbindungen) lösen Alarme aus.                                                                               |   2   |  V   |
| 9.2.5 | Stellen Sie sicher, dass Plugins mit hohem Risiko vor der Produktionsbereitstellung einer Sicherheitsüberprüfung und Penetrationstest unterzogen werden.                                                                            |   3   |  V   |
| 9.2.6 | Stellen Sie sicher, dass Versuche, die Sandbox zu umgehen, automatisch blockiert werden und das verursachende Plugin bis zur Untersuchung unter Quarantäne gestellt wird.                                                           |   3   | D/V  |

---

## 9.3 Autonome Schleife und Kostenbegrenzung

Erkennen und stoppen Sie unkontrollierte Agent-zu-Agent-Rekursion und Kostenexplosionen.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Verifizieren Sie, dass Inter-Agent-Aufrufe eine Hop-Limit- oder TTL (Time-to-Live) enthalten, die zur Laufzeit dekrementiert und durchgesetzt wird.  |   1   | D/V  |
| 9.3.2 | Überprüfen Sie, dass Agenten eine eindeutige Invocation-Graph-ID beibehalten, um Selbstaufrufe oder zyklische Muster zu erkennen.                    |   2   |  D   |
| 9.3.3 | Überprüfen Sie, dass kumulative Compute-Unit- und Ausgabenzähler pro Anfragekette verfolgt werden; das Überschreiten des Limits bricht die Kette ab. |   2   | D/V  |
| 9.3.4 | Überprüfen Sie, ob formale Analysen oder Model-Checking die Abwesenheit von unbeschränkter Rekursion in Agentenprotokollen nachweisen.               |   3   |  V   |
| 9.3.5 | Überprüfen Sie, dass Schleifen-Abbruch-Ereignisse Warnmeldungen erzeugen und kontinuierliche Verbesserungsmetriken speisen.                          |   3   |  D   |

---

## 9.4 Schutz vor Missbrauch auf Protokollebene

Sichere Kommunikationskanäle zwischen Agenten und externen Systemen, um Übernahmen oder Manipulationen zu verhindern.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Stellen Sie sicher, dass alle Nachrichten zwischen Agenten und Werkzeugen sowie zwischen Agenten und Agenten authentifiziert sind (z. B. durch beidseitiges TLS oder JWT) und Ende-zu-Ende verschlüsselt werden. |   1   | D/V  |
| 9.4.2 | Stellen Sie sicher, dass Schemata strikt validiert werden; unbekannte Felder oder fehlerhafte Nachrichten werden abgelehnt.                                                                                      |   1   |  D   |
| 9.4.3 | Stellen Sie sicher, dass Integritätsprüfungen (MACs oder digitale Signaturen) den gesamten Nachrichteninhalt einschließlich der Werkzeugparameter abdecken.                                                      |   2   | D/V  |
| 9.4.4 | Stellen Sie sicher, dass der Wiedergabeschutz (Nonces oder Zeitstempelfenster) auf der Protokollebene durchgesetzt wird.                                                                                         |   2   |  D   |
| 9.4.5 | Überprüfen Sie, dass Protokollimplementierungen einer Fuzz-Analyse und statischen Analyse auf Injektions- oder Deserialisierungsschwachstellen unterzogen werden.                                                |   3   |  V   |

---

## 9.5 Agent-Identität und Manipulationssicherheit

Stellen Sie sicher, dass Aktionen zuordenbar sind und Änderungen erkennbar bleiben.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Stellen Sie sicher, dass jede Agenteninstanz über eine eindeutige kryptografische Identität (Schlüsselpaar oder hardwarebasierte Berechtigung) verfügt.     |   1   | D/V  |
| 9.5.2 | Stellen Sie sicher, dass alle Agentenaktionen signiert und mit einem Zeitstempel versehen sind; Protokolle enthalten die Signatur zur Nichtabstreitbarkeit. |   2   | D/V  |
| 9.5.3 | Stellen Sie sicher, dass manipulationssichere Protokolle in einem nur anfügbaren oder einmal beschreibbaren Medium gespeichert werden.                      |   2   |  V   |
| 9.5.4 | Überprüfen Sie, dass Identitätsschlüssel gemäß einem definierten Zeitplan und bei Anzeichen einer Kompromittierung rotieren.                                |   3   |  D   |
| 9.5.5 | Überprüfen Sie, ob Spoofing- oder Schlüsselkonfliktversuche eine sofortige Quarantäne des betroffenen Agenten auslösen.                                     |   3   | D/V  |

---

## 9.6 Risikominderung durch Multi-Agenten-Schwärme

Mildern Sie Risiken kollektiven Verhaltens durch Isolation und formale Sicherheitsmodellierung.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Stellen Sie sicher, dass Agenten, die in verschiedenen Sicherheitsdomänen operieren, in isolierten Laufzeit-Sandboxen oder Netzwerksegmenten ausgeführt werden. |   1   | D/V  |
| 9.6.2 | Stellen Sie sicher, dass Schwarmverhalten modelliert und formell auf Lebendigkeit und Sicherheit vor der Bereitstellung verifiziert werden.                     |   3   |  V   |
| 9.6.3 | Überprüfen Sie, dass Laufzeitüberwachungen neu auftretende unsichere Muster (z. B. Oszillationen, Deadlocks) erkennen und Korrekturmaßnahmen einleiten.         |   3   |  D   |

---

## 9.7 Benutzer- und Werkzeugauthentifizierung / -autorisierung

Implementieren Sie robuste Zugriffskontrollen für jede agentenausgelöste Aktion.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Stellen Sie sicher, dass Agenten sich als erstklassige Prinzipale bei nachgelagerten Systemen authentifizieren und niemals Endbenutzeranmeldeinformationen wiederverwenden. |   1   | D/V  |
| 9.7.2 | Überprüfen Sie, dass fein abgestimmte Autorisierungsrichtlinien einschränken, welche Werkzeuge ein Agent aufrufen darf und welche Parameter er übergeben darf.              |   2   |  D   |
| 9.7.3 | Überprüfen Sie, dass die Berechtigungsprüfungen bei jedem Aufruf neu bewertet werden (kontinuierliche Autorisierung) und nicht lediglich zu Beginn der Sitzung.             |   2   |  V   |
| 9.7.4 | Überprüfen Sie, dass delegierte Berechtigungen automatisch ablaufen und nach Ablauf der Frist oder bei Änderung des Umfangs erneut zustimmungspflichtig sind.               |   3   |  D   |

---

## 9.8 Sicherheit der Agent-zu-Agent-Kommunikation

Verschlüsseln und integritätsschützen Sie alle Nachrichten zwischen Agenten, um Abhören und Manipulation zu verhindern.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Stellen Sie sicher, dass gegenseitige Authentifizierung und perfekte Vorwärtsgeheimnis-Verschlüsselung (z.B. TLS 1.3) für Agentenkanäle obligatorisch sind.            |   1   | D/V  |
| 9.8.2 | Stellen Sie sicher, dass die Nachrichtenintegrität und der Ursprung vor der Verarbeitung überprüft werden; Fehler führen zu Warnungen und zum Verwerfen der Nachricht. |   1   |  D   |
| 9.8.3 | Stellen Sie sicher, dass Kommunikations-Metadaten (Zeitstempel, Sequenznummern) protokolliert werden, um eine forensische Rekonstruktion zu unterstützen.              |   2   | D/V  |
| 9.8.4 | Überprüfen Sie, dass formale Verifikation oder Model Checking bestätigt, dass Protokoll-Zustandsautomaten nicht in unsichere Zustände gebracht werden können.          |   3   |  V   |

---

## 9.9 Absichtverifikation und Durchsetzung von Einschränkungen

Validieren Sie, dass die Aktionen des Agenten mit der angegebenen Absicht des Benutzers und den Systembeschränkungen übereinstimmen.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Überprüfen Sie, ob vorgelagerte Constraint-Solver vorgeschlagene Aktionen anhand von fest codierten Sicherheits- und Richtlinienregeln prüfen.                                                        |   1   |  D   |
| 9.9.2 | Überprüfen Sie, dass Maßnahmen mit hoher Auswirkung (finanziell, destruktiv, datenschutzrelevant) eine ausdrückliche Bestätigung der Absicht des auslösenden Benutzers erfordern.                     |   2   | D/V  |
| 9.9.3 | Überprüfen Sie, dass die Nachbedingungsprüfungen validieren, dass abgeschlossene Aktionen die beabsichtigten Effekte ohne Nebeneffekte erreicht haben; Abweichungen lösen eine Rücksetzung aus.       |   2   |  V   |
| 9.9.4 | Verifizieren Sie, dass formale Methoden (z. B. Model Checking, Theorembeweis) oder eigenschaftsbasierte Tests nachweisen, dass Agentenpläne alle erklärten Einschränkungen erfüllen.                  |   3   |  V   |
| 9.9.5 | Stellen Sie sicher, dass Vorfälle von Absichten-Missverständnissen oder Verstoß gegen Einschränkungen kontinuierliche Verbesserungszyklen und den Austausch von Bedrohungsinformationen unterstützen. |   3   |  D   |

---

## 9.10 Sicherheitsstrategie für Agenten-Reasoning

Sichere Auswahl und Ausführung verschiedener Schlussfolgerungsstrategien, einschließlich ReAct, Chain-of-Thought und Tree-of-Thoughts Ansätzen.

|   #    | Description                                                                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Überprüfen Sie, dass die Auswahl der Denkstrategie deterministische Kriterien verwendet (Eingabekomplexität, Aufgabentyp, Sicherheitskontext) und dass identische Eingaben innerhalb desselben Sicherheitskontexts zu identischen Strategieauswahlen führen.    |   1   | D/V  |
| 9.10.2 | Stellen Sie sicher, dass jede Denkstrategie (ReAct, Chain-of-Thought, Tree-of-Thoughts) über eine eigene Eingabevalidierung, Ausgabe-Säuberung und spezifische Ausführungszeitbegrenzungen verfügt, die auf ihren jeweiligen kognitiven Ansatz abgestimmt sind. |   1   | D/V  |
| 9.10.3 | Verifizieren Sie, dass Übergänge der Denkstrategien mit vollständigem Kontext protokolliert werden, einschließlich Eingabemerkmalen, Werten der Auswahlkriterien und Ausführungsmetadaten zur Rekonstruktion der Prüfpfade.                                     |   2   | D/V  |
| 9.10.4 | Verifizieren Sie, dass die Tree-of-Thoughts-Methodik zum Schlussfolgern Verzweigungsbeschneidungsmechanismen enthält, die die Exploration beenden, wenn Richtlinienverletzungen, Ressourcenbeschränkungen oder Sicherheitsgrenzen erkannt werden.               |   2   | D/V  |
| 9.10.5 | Stellen Sie sicher, dass die ReAct (Reason-Act-Observe)-Zyklen Validierungspunkte in jeder Phase enthalten: Überprüfung des Denkprozesses, Autorisierung der Handlung und Bereinigung der Beobachtung, bevor fortgefahren wird.                                 |   2   | D/V  |
| 9.10.6 | Stellen Sie sicher, dass die Leistungskennzahlen der Argumentationsstrategie (Ausführungszeit, Ressourcennutzung, Ausgabequalität) mit automatisierten Warnungen überwacht werden, wenn die Kennzahlen die konfigurierten Schwellenwerte überschreiten.         |   3   | D/V  |
| 9.10.7 | Stellen Sie sicher, dass hybride Reasoning-Ansätze, die mehrere Strategien kombinieren, die Eingabevalidierung und Ausgabebeschränkungen aller beteiligten Strategien einhalten, ohne dabei Sicherheitskontrollen zu umgehen.                                   |   3   | D/V  |
| 9.10.8 | Überprüfen Sie, dass die Sicherheitsteststrategie für Reasoning Fuzzing mit fehlerhaften Eingaben, adversariale Eingabeaufforderungen, die ein Strategiewechsel erzwingen sollen, sowie Grenzwerttests für jeden kognitiven Ansatz umfasst.                     |   3   | D/V  |

---

## 9.11 Agent-Lebenszyklus-Zustandsverwaltung und Sicherheit

Sichere Agenteninitalisierung, Zustandsübergänge und Beendigung mit kryptografischen Audit-Trails und definierten Wiederherstellungsverfahren.

|   #    | Description                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Stellen Sie sicher, dass die Agenteninitalisierung die Einrichtung einer kryptografischen Identität mit hardwaregestützten Anmeldeinformationen sowie unveränderliche Startprotokolle enthält, die Agenten-ID, Zeitstempel, Konfigurations-Hash und Initialisierungsparameter umfassen.                                          |   1   | D/V  |
| 9.11.2 | Verifizieren Sie, dass Agenten-Zustandsübergänge kryptografisch signiert, zeitgestempelt und mit vollständigem Kontext protokolliert werden, einschließlich auslösender Ereignisse, vorherigem Zustands-Hash, neuem Zustands-Hash und durchgeführter Sicherheitsüberprüfungen.                                                   |   2   | D/V  |
| 9.11.3 | Überprüfen Sie, ob die Agent-Abschaltverfahren sicheres Löschen des Speichers mittels kryptografischer Löschung oder mehrfacher Überschreibung umfassen, die Widerrufung von Berechtigungsnachweisen mit Benachrichtigung der Zertifizierungsstelle sowie die Erstellung manipulationssicherer Abschlusszertifikate.             |   2   | D/V  |
| 9.11.4 | Überprüfen Sie, dass Agenten-Wiederherstellungsmechanismen die Zustandsintegrität mithilfe kryptografischer Prüfsummen (mindestens SHA-256) validieren und bei erkannter Korruption zu bekannten einwandfreien Zuständen zurücksetzen, wobei automatisierte Warnungen und manuelle Genehmigungsanforderungen zum Einsatz kommen. |   3   | D/V  |
| 9.11.5 | Stellen Sie sicher, dass Mechanismen zur Agenten-Persistenz sensible Zustandsdaten mit pro Agent einzigartigen AES-256-Schlüsseln verschlüsseln und eine sichere Schlüsselrotation in konfigurierbaren Zeitplänen (maximal 90 Tage) mit einer unterbrechungsfreien Bereitstellung implementieren.                                |   3   | D/V  |

---

## 9.12 Sicherheitsrahmen für die Integration von Werkzeugen

Sicherheitskontrollen für das dynamische Laden von Werkzeugen, deren Ausführung und Ergebnisvalidierung mit definierten Risikoabschätzungs- und Genehmigungsprozessen.

|   #    | Description                                                                                                                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.12.1 | Überprüfen Sie, dass Tool-Beschreibungen Sicherheitsmetadaten enthalten, die erforderliche Berechtigungen (Lese/Schreib/Ausführungsrechte), Risikostufen (niedrig/mittel/hoch), Ressourcengrenzen (CPU, Speicher, Netzwerk) und Validierungsanforderungen, dokumentiert in Tool-Manifests, angeben.                      |   1   | D/V  |
| 9.12.2 | Überprüfen Sie, dass die Ausführungsergebnisse von Tools gegen erwartete Schemata (JSON Schema, XML Schema) und Sicherheitsrichtlinien (Ausgabe-Sanitierung, Datenklassifizierung) validiert werden, bevor sie mit Zeitlimitvorgaben und Fehlerbehandlungsverfahren integriert werden.                                   |   1   | D/V  |
| 9.12.3 | Überprüfen Sie, ob die Protokolle der Werkzeuginteraktionen einen detaillierten Sicherheitskontext enthalten, einschließlich der Nutzung von Berechtigungen, Datenzugriffsmustern, Ausführungszeiten, Ressourcenverbrauch und Rückgabecodes, mit strukturiertem Logging zur SIEM-Integration.                            |   2   | D/V  |
| 9.12.4 | Überprüfen Sie, ob Mechanismen zum dynamischen Laden von Tools digitale Signaturen mithilfe der PKI-Infrastruktur validieren und sichere Ladeprotokolle mit Sandbox-Isolierung und Berechtigungsprüfung vor der Ausführung implementieren.                                                                               |   2   | D/V  |
| 9.12.5 | Stellen Sie sicher, dass Sicherheitsbewertungen für Tools bei neuen Versionen automatisch ausgelöst werden, mit obligatorischen Genehmigungsschritten, einschließlich statischer Analyse, dynamischer Prüfung und Überprüfung durch das Sicherheitsteam, mit dokumentierten Genehmigungskriterien und SLA-Anforderungen. |   3   | D/V  |

---

### Quellenangaben

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

