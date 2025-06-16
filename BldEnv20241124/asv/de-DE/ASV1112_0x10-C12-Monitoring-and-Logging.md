# C12 Überwachung, Protokollierung und Anomalieerkennung

## Kontrollziel

Dieser Abschnitt enthält Anforderungen für die Bereitstellung von Echtzeit- und forensischer Transparenz darüber, was das Modell und andere KI-Komponenten sehen, tun und zurückgeben, damit Bedrohungen erkannt, priorisiert und daraus gelernt werden kann.

## C12.1 Anfrage- und Antwortprotokollierung

|   #    | Description                                                                                                                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Verifizieren Sie, dass alle Benutzeranfragen und Modellantworten mit den entsprechenden Metadaten (z. B. Zeitstempel, Benutzer-ID, Sitzungs-ID, Modellversion) protokolliert werden.                                                                                  |   1   | D/V  |
| 12.1.2 | Stellen Sie sicher, dass Protokolle in sicheren, zugangsgesteuerten Repositorys mit geeigneten Aufbewahrungsrichtlinien und Sicherungsverfahren gespeichert werden.                                                                                                   |   1   | D/V  |
| 12.1.3 | Überprüfen Sie, ob Log-Speichersysteme Verschlüsselung im Ruhezustand und während der Übertragung implementieren, um sensible Informationen in den Protokollen zu schützen.                                                                                           |   1   | D/V  |
| 12.1.4 | Stellen Sie sicher, dass sensible Daten in Eingabeaufforderungen und Ausgaben vor dem Protokollieren automatisch geschwärzt oder maskiert werden, mit konfigurierbaren Schwärzungsregeln für personenbezogene Daten (PII), Zugangsdaten und geschützte Informationen. |   1   | D/V  |
| 12.1.5 | Stellen Sie sicher, dass Richtlinienentscheidungen und Sicherheitsfiltermaßnahmen mit ausreichenden Details protokolliert werden, um eine Prüfung und Fehlerbehebung von Inhaltsmoderationssystemen zu ermöglichen.                                                   |   2   | D/V  |
| 12.1.6 | Stellen Sie sicher, dass die Integrität der Protokolle durch z.B. kryptografische Signaturen oder schreibgeschützten Speicher geschützt ist.                                                                                                                          |   2   | D/V  |

---

## C12.2 Missbrauchserkennung und Alarmierung

|   #    | Description                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.2.1 | Überprüfen Sie, ob das System bekannte Jailbreak-Muster, Prompt-Injection-Versuche und adversariale Eingaben mithilfe einer signaturbasierten Erkennung erkennt und meldet.                                              |   1   | D/V  |
| 12.2.2 | Stellen Sie sicher, dass das System in bestehende Security Information and Event Management (SIEM)-Plattformen mittels standardisierter Protokollformate und -protokolle integriert wird.                                |   1   | D/V  |
| 12.2.3 | Stellen Sie sicher, dass angereicherte Sicherheitsereignisse KI-spezifische Kontexte wie Modellkennungen, Vertrauenswerte und Entscheidungen des Sicherheitsfilters enthalten.                                           |   2   | D/V  |
| 12.2.4 | Überprüfen Sie, ob die verhaltensbasierte Anomalieerkennung ungewöhnliche Gesprächsmuster, übermäßige Wiederholungsversuche oder systematische Sondierungsverhalten identifiziert.                                       |   2   | D/V  |
| 12.2.5 | Stellen Sie sicher, dass Echtzeit-Benachrichtigungsmechanismen Sicherheitsteams informieren, wenn potenzielle Richtlinienverstöße oder Angriffsversuche erkannt werden.                                                  |   2   | D/V  |
| 12.2.6 | Überprüfen Sie, ob benutzerdefinierte Regeln enthalten sind, um KI-spezifische Bedrohungsmuster zu erkennen, einschließlich koordinierter Jailbreak-Versuche, Prompt-Injektionskampagnen und Modell-Extraktionsangriffe. |   2   | D/V  |
| 12.2.7 | Überprüfen Sie, dass automatisierte Incident-Response-Workflows kompromittierte Modelle isolieren, bösartige Benutzer blockieren und kritische Sicherheitsereignisse eskalieren können.                                  |   3   | D/V  |

---

## C12.3 Modell-Abweichungserkennung

|   #    | Description                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Überprüfen Sie, ob das System grundlegende Leistungskennzahlen wie Genauigkeit, Vertrauenswerte, Latenzzeiten und Fehlerraten über verschiedene Modellversionen und Zeiträume hinweg verfolgt.  |   1   | D/V  |
| 12.3.2 | Überprüfen Sie, ob automatisierte Warnmeldungen ausgelöst werden, wenn Leistungskennzahlen vordefinierte Verschlechterungsschwellen überschreiten oder erheblich von den Basiswerten abweichen. |   2   | D/V  |
| 12.3.3 | Überprüfen Sie, ob die Halluzinationserkennungsmonitore Instanzen identifizieren und markieren, wenn Modellausgaben faktisch inkorrekte, inkonsistente oder erfundene Informationen enthalten.  |   2   | D/V  |

---

## C12.4 Leistungs- und Verhaltens-Telemetrie

|   #    | Description                                                                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.4.1 | Stellen Sie sicher, dass Betriebsmetriken wie Anforderungsverzögerung, Token-Verbrauch, Speicherverbrauch und Durchsatz kontinuierlich erfasst und überwacht werden.                                         |   1   | D/V  |
| 12.4.2 | Stellen Sie sicher, dass Erfolgs- und Fehlerraten mit Kategorisierung der Fehlertypen und deren Ursachen erfasst werden.                                                                                     |   1   | D/V  |
| 12.4.3 | Stellen Sie sicher, dass die Überwachung der Ressourcennutzung die Nutzung von GPU/CPU, den Speicherverbrauch und die Speicheranforderungen umfasst, mit Alarmierung bei Überschreitung von Schwellenwerten. |   2   | D/V  |

---

## C12.5 KI-Vorfallreaktionsplanung und -durchführung

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Stellen Sie sicher, dass die Vorfallreaktionspläne speziell AI-bezogene Sicherheitsvorfälle wie Modellkompromittierung, Datenvergiftung und adversariale Angriffe abdecken.                                          |   1   | D/V  |
| 12.5.2 | Stellen Sie sicher, dass Vorfallreaktionsteams Zugriff auf KI-spezifische forensische Werkzeuge und Expertenwissen haben, um das Modellverhalten und Angriffsvektoren zu untersuchen.                                |   2   | D/V  |
| 12.5.3 | Überprüfen Sie, ob die Nachanalyse des Vorfalls Überlegungen zur Modellnachschulung, Aktualisierungen der Sicherheitsfilter und die Integration der gewonnenen Erkenntnisse in die Sicherheitskontrollen beinhaltet. |   3   | D/V  |

---

## C12.5 Erkennung der Leistungsverschlechterung von KI

Überwachen und erkennen Sie eine Verschlechterung der Leistung und Qualität von KI-Modellen im Laufe der Zeit.

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Stellen Sie sicher, dass Modellgenauigkeit, Präzision, Recall und F1-Werte kontinuierlich überwacht und mit den Basisgrenzwerten verglichen werden.         |   1   | D/V  |
| 12.5.2 | Überprüfen Sie, ob die Erkennung von Datenverschiebungen Änderungen in der Eingabeverteilung überwacht, die die Modellleistung beeinflussen können.         |   1   | D/V  |
| 12.5.3 | Überprüfen Sie, ob die Erkennung von Konzeptdrift Änderungen in der Beziehung zwischen Eingaben und erwarteten Ausgaben identifiziert.                      |   2   | D/V  |
| 12.5.4 | Überprüfen Sie, ob Leistungsverluste automatisierte Warnmeldungen auslösen und Workflows zur Neuerstellung oder zum Ersatz des Modells einleiten.           |   2   | D/V  |
| 12.5.5 | Überprüfen Sie, ob die Ursachenanalyse für Leistungsabfälle Leistungsabfälle mit Datenänderungen, Infrastrukturproblemen oder externen Faktoren korreliert. |   3   |  V   |

---

## C12.6 DAG-Visualisierung & Workflow-Sicherheit

Schützen Sie Workflow-Visualisierungssysteme vor Informationslecks und Manipulationsangriffen.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Überprüfen Sie, ob die DAG-Visualisierungsdaten bereinigt werden, um sensible Informationen vor der Speicherung oder Übertragung zu entfernen.                                               |   1   | D/V  |
| 12.6.2 | Stellen Sie sicher, dass die Zugriffssteuerungen zur Workflow-Visualisierung gewährleisten, dass nur autorisierte Benutzer Agenten-Entscheidungspfade und Begründungsspuren einsehen können. |   1   | D/V  |
| 12.6.3 | Stellen Sie sicher, dass die Integrität der DAG-Daten durch kryptografische Signaturen und manipulationssichere Speichermethoden geschützt ist.                                              |   2   | D/V  |
| 12.6.4 | Überprüfen Sie, ob Workflow-Visualisierungssysteme eine Eingabeverifizierung implementieren, um Injektionsangriffe durch manipulierte Knoten- oder Kantendaten zu verhindern.                |   2   | D/V  |
| 12.6.5 | Überprüfen Sie, dass Echtzeit-DAG-Aktualisierungen eine Ratenbegrenzung und Validierung unterliegen, um Denial-of-Service-Angriffe auf Visualisierungssysteme zu verhindern.                 |   3   | D/V  |

---

## C12.7 Proaktives Überwachen des Sicherheitsverhaltens

Erkennung und Verhinderung von Sicherheitsbedrohungen durch proaktive Analyse des Agentenverhaltens.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Stellen Sie sicher, dass proaktive Agentenverhalten vor der Ausführung sicherheitsvalidiert werden, indem eine Risikobewertung integriert wird.                   |   1   | D/V  |
| 12.7.2 | Überprüfen Sie, ob autonome Initiativauslöser die Bewertung des Sicherheitskontexts und die Analyse der Bedrohungslandschaft umfassen.                            |   2   | D/V  |
| 12.7.3 | Überprüfen Sie, ob proaktive Verhaltensmuster auf potenzielle Sicherheitsimplikationen und unbeabsichtigte Folgen analysiert werden.                              |   2   | D/V  |
| 12.7.4 | Stellen Sie sicher, dass sicherheitskritische proaktive Maßnahmen explizite Genehmigungsketten mit Audit-Trails erfordern.                                        |   3   | D/V  |
| 12.7.5 | Überprüfen Sie, ob die Verhaltensanomalieerkennung Abweichungen in den Mustern proaktiver Agenten identifiziert, die auf eine Kompromittierung hinweisen könnten. |   3   | D/V  |

---

## Literaturverzeichnis

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

