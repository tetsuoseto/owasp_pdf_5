# C1 Trainingsdaten-Governance und Bias-Management

## Kontrollziel

Trainingsdaten müssen so beschafft, gehandhabt und gepflegt werden, dass Herkunft, Sicherheit, Qualität und Fairness erhalten bleiben. Dies erfüllt rechtliche Verpflichtungen und verringert Risiken von Verzerrungen, Manipulationen oder Datenschutzverletzungen im gesamten KI-Lebenszyklus.

---

## C1.1 Herkunft der Trainingsdaten

Führen Sie ein verifizierbares Inventar aller Datensätze, akzeptieren Sie nur vertrauenswürdige Quellen und protokollieren Sie jede Änderung zur Nachvollziehbarkeit.

|   #   | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Stellen Sie sicher, dass ein aktuelles Inventar jeder Trainingsdatenquelle (Herkunft, Verantwortlicher/Eigentümer, Lizenz, Erfassungsmethode, vorgesehene Nutzungseinschränkungen und Verarbeitungshistorie) geführt wird.                                                              |   1   | D/V  |
| 1.1.2 | Stellen Sie sicher, dass nur Datensätze verwendet werden, die auf Qualität, Repräsentativität, ethische Beschaffung und Lizenzkonformität geprüft wurden, um Risiken wie Datenmanipulation, eingebettete Voreingenommenheit und Verletzung geistigen Eigentums zu minimieren.           |   1   | D/V  |
| 1.1.3 | Stellen Sie sicher, dass Datenminimierung durchgesetzt wird, sodass unnötige oder sensible Attribute ausgeschlossen sind.                                                                                                                                                               |   1   | D/V  |
| 1.1.4 | Stellen Sie sicher, dass alle Änderungen am Datensatz einem protokollierten Genehmigungsworkflow unterliegen.                                                                                                                                                                           |   2   | D/V  |
| 1.1.5 | Stellen Sie sicher, dass die Qualität der Kennzeichnung/Annotation durch Überprüfer-Querprüfungen oder Konsens gewährleistet ist.                                                                                                                                                       |   2   | D/V  |
| 1.1.6 | Stellen Sie sicher, dass für bedeutende Trainingsdatensätze „Datakarten“ oder „Datenblätter für Datensätze“ gepflegt werden, die Merkmale, Ziele, Zusammensetzung, Erfassungsprozesse, Vorverarbeitung sowie empfohlene und nicht empfohlene Verwendungszwecke detailliert beschreiben. |   2   | D/V  |

---

## C1.2 Sicherheit und Integrität der Trainingsdaten

Zugriff einschränken, Daten im Ruhezustand und während der Übertragung verschlüsseln und die Integrität überprüfen, um Manipulationen oder Diebstahl zu verhindern.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Überprüfen Sie, ob Zugriffskontrollen Speicher und Pipelines schützen.                                                                                                                                                                                                                                                                                            |   1   | D/V  |
| 1.2.2 | Stellen Sie sicher, dass Datensätze während der Übertragung verschlüsselt sind und für alle sensiblen oder personenbezogenen Informationen (PII) auch im Ruhezustand, unter Verwendung von branchenüblichen kryptografischen Algorithmen und Schlüsselverwaltungspraktiken.                                                                                       |   2   | D/V  |
| 1.2.3 | Verifizieren Sie, dass kryptografische Hashes oder digitale Signaturen verwendet werden, um die Datenintegrität während der Speicherung und Übertragung sicherzustellen, und dass automatische Anomalieerkennungstechniken angewendet werden, um unautorisierte Änderungen oder Beschädigungen, einschließlich gezielter Datenvergiftungsversuche, zu verhindern. |   2   | D/V  |
| 1.2.4 | Stellen Sie sicher, dass Datensatzversionen verfolgt werden, um eine Rücksetzung zu ermöglichen.                                                                                                                                                                                                                                                                  |   3   | D/V  |
| 1.2.5 | Stellen Sie sicher, dass veraltete Daten sicher gelöscht oder anonymisiert werden, um den Richtlinien zur Datenaufbewahrung, gesetzlichen Anforderungen und zur Reduzierung der Angriffsfläche zu entsprechen.                                                                                                                                                    |   2   | D/V  |

---

## C1.3 Repräsentationsvollständigkeit & Fairness

Erkennen Sie demografische Verzerrungen und wenden Sie Gegenmaßnahmen an, damit die Fehlerraten des Modells über alle Gruppen hinweg gerecht verteilt sind.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Stellen Sie sicher, dass Datensätze auf repräsentative Ungleichgewichte und potenzielle Verzerrungen über gesetzlich geschützte Merkmale (z. B. Rasse, Geschlecht, Alter) sowie andere ethisch sensible Eigenschaften, die für den Anwendungsbereich des Modells relevant sind (z. B. sozioökonomischer Status, Standort), analysiert werden.                                                     |   1   | D/V  |
| 1.3.2 | Stellen Sie sicher, dass identifizierte Verzerrungen durch dokumentierte Strategien wie Neu-Ausgleich, gezielte Datenaugmentation, algorithmische Anpassungen (z. B. Vorverarbeitung, Verarbeitung während der Laufzeit, Nachbearbeitung) oder Re-Gewichtung gemindert werden und die Auswirkungen der Minderung sowohl auf Fairness als auch auf die Gesamtleistung des Modells bewertet werden. |   2   | D/V  |
| 1.3.3 | Überprüfen Sie, dass Fairness-Metriken nach dem Training bewertet und dokumentiert werden.                                                                                                                                                                                                                                                                                                        |   2   | D/V  |
| 1.3.4 | Überprüfen Sie, ob eine Richtlinie zur Verwaltung von Lebenszyklus-Bias Eigentümer und Überprüfungsrhythmen zuweist.                                                                                                                                                                                                                                                                              |   3   | D/V  |

---

## C1.4 Qualität, Integrität und Sicherheit der Beschriftung von Trainingsdaten

Schützen Sie Labels mit Verschlüsselung und verlangen Sie eine doppelte Überprüfung für kritische Klassen.

|   #   | Description                                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Stellen Sie sicher, dass die Qualität der Kennzeichnung/Annotation durch klare Richtlinien, wechselseitige Überprüfungen der Gutachter, Konsensmechanismen (z. B. Überwachung der Übereinstimmung zwischen den Annotatoren) und festgelegte Prozesse zur Behebung von Diskrepanzen gewährleistet ist.                         |   2   | D/V  |
| 1.4.2 | Stellen Sie sicher, dass kryptografische Hashes oder digitale Signaturen auf Label-Artefakte angewendet werden, um deren Integrität und Authentizität zu gewährleisten.                                                                                                                                                       |   2   | D/V  |
| 1.4.3 | Überprüfen Sie, dass Labeling-Schnittstellen und -Plattformen starke Zugriffskontrollen durchsetzen, manipulationssichere Auditprotokolle aller Labeling-Aktivitäten führen und vor unbefugten Änderungen schützen.                                                                                                           |   2   | D/V  |
| 1.4.4 | Stellen Sie sicher, dass für die Sicherheit, den Schutz oder die Fairness entscheidende Kennzeichnungen (z. B. die Identifizierung toxischer Inhalte, kritischer medizinischer Befunde) einer obligatorischen unabhängigen Doppelüberprüfung oder einer gleichwertig robusten Verifikation unterzogen werden.                 |   3   | D/V  |
| 1.4.5 | Verifizieren Sie, dass sensible Informationen (einschließlich personenbezogener Daten) – die versehentlich erfasst oder notwendigerweise in Labels vorhanden sind – gemäß den Prinzipien der Datenminimierung im Ruhezustand und während der Übertragung geschwärzt, pseudonymisiert, anonymisiert oder verschlüsselt werden. |   2   | D/V  |
| 1.4.6 | Stellen Sie sicher, dass die Kennzeichnungsrichtlinien und Anweisungen umfassend, versioniert und von Fachkollegen überprüft sind.                                                                                                                                                                                            |   2   | D/V  |
| 1.4.7 | Stellen Sie sicher, dass Datenschemata (einschließlich für Labels) klar definiert und versioniert sind.                                                                                                                                                                                                                       |   2   | D/V  |
| 1.8.2 | Überprüfen Sie, ob ausgelagerte oder durch Crowdsourcing organisierte Kennzeichnungsabläufe technische und verfahrensmäßige Schutzmaßnahmen enthalten, um die Vertraulichkeit und Integrität der Daten, die Qualität der Kennzeichnungen zu gewährleisten und Datenlecks zu verhindern.                                       |   2   | D/V  |

---

## C1.5 Qualitätssicherung der Trainingsdaten

Kombinieren Sie automatisierte Validierung, manuelle Stichprobenprüfungen und protokollierte Fehlerbehebungen, um die Zuverlässigkeit des Datensatzes zu gewährleisten.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Stellen Sie sicher, dass automatisierte Tests bei jedem Import oder jeder signifikanten Transformation Formatfehler, Nullwerte und Label-Verschiebungen erfassen.                                                                                                                                                                                      |   1   |  D   |
| 1.5.2 | Verifizieren Sie, dass fehlgeschlagene Datensätze mit Prüfpfaden unter Quarantäne gestellt werden.                                                                                                                                                                                                                                                     |   1   | D/V  |
| 1.5.3 | Stellen Sie sicher, dass manuelle Stichprobenprüfungen durch Fachexperten eine statistisch signifikante Stichprobe abdecken (z. B. ≥1 % oder 1.000 Stichproben, je nachdem, welcher Wert größer ist, oder wie durch die Risikobewertung festgelegt), um subtile Qualitätsprobleme zu identifizieren, die von der Automatisierung nicht erfasst werden. |   2   |  V   |
| 1.5.4 | Stellen Sie sicher, dass Maßnahmen zur Behebung an Herkunftsdaten angehängt werden.                                                                                                                                                                                                                                                                    |   2   | D/V  |
| 1.5.5 | Stellen Sie sicher, dass Qualitätsprüfungen minderwertige Datensätze blockieren, es sei denn, Ausnahmen sind genehmigt.                                                                                                                                                                                                                                |   2   | D/V  |

---

## C1.6 Erkennung von Data Poisoning

Wenden Sie statistische Anomalieerkennung und Quarantäne-Workflows an, um feindliche Einfügungen zu stoppen.

|   #   | Description                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verifizieren Sie, dass Anomalieerkennungstechniken (z. B. statistische Methoden, Ausreißererkennung, Einbettungsanalyse) auf die Trainingsdaten bei der Erfassung und vor größeren Trainingsläufen angewendet werden, um mögliche Vergiftungsangriffe oder unbeabsichtigte Datenkorruption zu identifizieren. |   2   | D/V  |
| 1.6.2 | Überprüfen Sie, ob markierte Proben vor dem Training eine manuelle Überprüfung auslösen.                                                                                                                                                                                                                      |   2   | D/V  |
| 1.6.3 | Überprüfen Sie, ob die Ergebnisse das Sicherheitsdossier des Modells einspeisen und die fortlaufende Bedrohungsaufklärung informieren.                                                                                                                                                                        |   2   |  V   |
| 1.6.4 | Überprüfen Sie, ob die Erkennungslogik mit neuen Bedrohungsinformationen aktualisiert wurde.                                                                                                                                                                                                                  |   3   | D/V  |
| 1.6.5 | Stellen Sie sicher, dass Online-Lernpipelines die Verteilungsschwankungen überwachen.                                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.6 | Stellen Sie sicher, dass spezifische Abwehrmaßnahmen gegen bekannte Arten von Datenvergiftungsangriffen (z. B. Label-Flipping, Einfügen von Backdoor-Triggern, Angriffe durch einflussreiche Instanzen) entsprechend dem Risikoprofil des Systems und den Datenquellen berücksichtigt und umgesetzt werden.   |   3   | D/V  |

---

## C1.7 Benutzer-Datenlöschung und Durchsetzung der Einwilligung

Respektieren Sie Löschungs- und Widerrufsanfragen über Datensätze, Backups und abgeleitete Artefakte hinweg.

|   #   | Description                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Überprüfen Sie, dass Löscharbeitsabläufe primäre und abgeleitete Daten löschen und die Auswirkung auf das Modell bewerten, sowie dass die Auswirkungen auf betroffene Modelle bewertet und gegebenenfalls behoben werden (z. B. durch erneutes Training oder Rekalibrierung).                                                          |   1   | D/V  |
| 1.7.2 | Stellen Sie sicher, dass Mechanismen vorhanden sind, um den Umfang und den Status der Zustimmung des Nutzers (und deren Widerrufe) für verwendete Trainingsdaten nachzuverfolgen und zu respektieren, und dass die Zustimmung validiert wird, bevor Daten in neue Trainingsprozesse oder bedeutende Modellaktualisierungen einfließen. |   2   |  D   |
| 1.7.3 | Überprüfen Sie, dass Workflows jährlich getestet und protokolliert werden.                                                                                                                                                                                                                                                             |   2   |  V   |

---

## C1.8 Sicherheit der Lieferkette

Prüfen Sie externe Datenanbieter und verifizieren Sie die Integrität über authentifizierte, verschlüsselte Kanäle.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Stellen Sie sicher, dass Drittanbieter von Daten, einschließlich Anbieter vortrainierter Modelle und externer Datensätze, eine Sicherheits-, Datenschutz-, ethische Herkunfts- und Datenqualitätsprüfung durchlaufen, bevor deren Daten oder Modelle integriert werden.                                                                                                                |   2   | D/V  |
| 1.8.2 | Überprüfen Sie, dass externe Übertragungen TLS/Authentifizierung und Integritätsprüfungen verwenden.                                                                                                                                                                                                                                                                                   |   1   |  D   |
| 1.8.3 | Stellen Sie sicher, dass Datenquellen mit hohem Risiko (z. B. Open-Source-Datensätze mit unbekannter Herkunft, nicht geprüfte Anbieter) einer verstärkten Überprüfung unterzogen werden, wie etwa isolierter Analyse in einer Sandbox, umfassenden Qualitäts- und Bias-Prüfungen sowie gezielter Erkennung von Datenvergiftungen, bevor sie in sensiblen Anwendungen verwendet werden. |   2   | D/V  |
| 1.8.4 | Überprüfen Sie, ob vortrainierte Modelle, die von Dritten stammen, auf eingebettete Vorurteile, potenzielle Hintertüren, die Integrität ihrer Architektur und die Herkunft ihrer ursprünglichen Trainingsdaten bewertet werden, bevor sie feinabgestimmt oder eingesetzt werden.                                                                                                       |   3   | D/V  |

---

## C1.9 Erkennung adversarialer Beispiele

Implementieren Sie während der Trainingsphase Maßnahmen wie adversariales Training, um die Widerstandsfähigkeit des Modells gegen adversariale Beispiele zu erhöhen.

|   #   | Description                                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Stellen Sie sicher, dass geeignete Abwehrmaßnahmen wie adversariales Training (unter Verwendung generierter adversarialer Beispiele), Datenaugmentation mit veränderten Eingaben oder robuste Optimierungstechniken implementiert und entsprechend der Risikobewertung für relevante Modelle angepasst werden. |   3   | D/V  |
| 1.9.2 | Stellen Sie sicher, dass bei Verwendung von adversarialem Training die Erstellung, Verwaltung und Versionierung von adversarialen Datensätzen dokumentiert und kontrolliert wird.                                                                                                                              |   2   | D/V  |
| 1.9.3 | Stellen Sie sicher, dass die Auswirkungen des Trainings zur adversarialen Robustheit auf die Modellleistung (sowohl bei sauberen als auch bei adversarialen Eingaben) und Fairness-Metriken bewertet, dokumentiert und überwacht werden.                                                                       |   3   | D/V  |
| 1.9.4 | Stellen Sie sicher, dass Strategien für adversariales Training und Robustheit regelmäßig überprüft und aktualisiert werden, um sich entwickelnden adversarialen Angriffstechniken entgegenzuwirken.                                                                                                            |   3   | D/V  |

---

## C1.10 Datenherkunft und Rückverfolgbarkeit

Verfolgen Sie die gesamte Reise jedes einzelnen Datenpunkts von der Quelle bis zum Modelleingang zur Nachvollziehbarkeit und für Reaktionsmaßnahmen bei Vorfällen.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Stellen Sie sicher, dass die Herkunft jedes Datenpunkts, einschließlich aller Transformationen, Ergänzungen und Zusammenführungen, aufgezeichnet und rekonstruiert werden kann. |   2   | D/V  |
| 1.10.2 | Stellen Sie sicher, dass Herkunftsdaten unveränderlich, sicher gespeichert und für Audits oder Untersuchungen zugänglich sind.                                                  |   2   | D/V  |
| 1.10.3 | Überprüfen Sie, dass die Nachverfolgung der Herkunft sowohl Rohdaten als auch synthetische Daten abdeckt.                                                                       |   2   | D/V  |

---

## C1.11 Verwaltung synthetischer Daten

Stellen Sie sicher, dass synthetische Daten ordnungsgemäß verwaltet, gekennzeichnet und einer Risikoanalyse unterzogen werden.

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Stellen Sie sicher, dass alle synthetischen Daten im gesamten Prozess klar gekennzeichnet und von echten Daten unterscheidbar sind.                             |   2   | D/V  |
| 1.11.2 | Überprüfen Sie, ob der Generierungsprozess, die Parameter und die beabsichtigte Verwendung der synthetischen Daten dokumentiert sind.                           |   2   | D/V  |
| 1.11.3 | Stellen Sie sicher, dass synthetische Daten vor der Verwendung im Training auf Bias, Datenschutzverletzungen und Repräsentationsprobleme risikobewertet werden. |   2   | D/V  |

---

## C1.12 Datenzugriffsüberwachung & Anomalieerkennung

Überwachen und Alarmieren bei ungewöhnlichem Zugriff auf Trainingsdaten, um Insider-Bedrohungen oder Datenexfiltration zu erkennen.

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Stellen Sie sicher, dass alle Zugriffe auf Trainingsdaten protokolliert werden, einschließlich Benutzer, Zeit und Aktion.                                             |   2   | D/V  |
| 1.12.2 | Stellen Sie sicher, dass Zugriffprotokolle regelmäßig auf ungewöhnliche Muster überprüft werden, wie beispielsweise große Exporte oder Zugriffe von neuen Standorten. |   2   | D/V  |
| 1.12.3 | Überprüfen Sie, ob Warnungen für verdächtige Zugriffsereignisse generiert und umgehend untersucht werden.                                                             |   2   | D/V  |

---

## C1.13 Datenaufbewahrungs- und Ablaufrichtlinien

Definieren und Durchsetzen von Datenaufbewahrungsfristen, um unnötige Datenspeicherung zu minimieren.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Überprüfen Sie, ob für alle Trainingsdatensätze explizite Aufbewahrungsfristen definiert sind.                              |   1   | D/V  |
| 1.13.2 | Überprüfen Sie, ob Datensätze am Ende ihres Lebenszyklus automatisch ablaufen, gelöscht oder zur Löschung überprüft werden. |   2   | D/V  |
| 1.13.3 | Überprüfen Sie, ob Aufbewahrungs- und Löschvorgänge protokolliert und auditierbar sind.                                     |   2   | D/V  |

---

## C1.14 Regulierung & Zuständigkeitskonformität

Stellen Sie sicher, dass alle Trainingsdaten den geltenden Gesetzen und Vorschriften entsprechen.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Stellen Sie sicher, dass Anforderungen an den Datenresidenzstandort und grenzüberschreitende Datenübertragungen für alle Datensätze identifiziert und durchgesetzt werden. |   2   | D/V  |
| 1.14.2 | Überprüfen Sie, ob branchenspezifische Vorschriften (z. B. Gesundheitswesen, Finanzen) bei der Datenverarbeitung erkannt und berücksichtigt werden.                        |   2   | D/V  |
| 1.14.3 | Stellen Sie sicher, dass die Einhaltung relevanter Datenschutzgesetze (z. B. DSGVO, CCPA) dokumentiert ist und regelmäßig überprüft wird.                                  |   2   | D/V  |

---

## C1.15 Daten-Wasserzeichen & Fingerprinting

Erkennen Sie unautorisierte Wiederverwendung oder Weitergabe proprietärer oder sensibler Daten.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Stellen Sie sicher, dass Datensätze oder Teilmengen dort, wo möglich, mit Wasserzeichen oder Fingerabdrücken versehen sind.                                                   |   3   | D/V  |
| 1.15.2 | Stellen Sie sicher, dass Wasserzeichen- und Fingerprinting-Methoden keine Verzerrungen oder Datenschutzrisiken verursachen.                                                   |   3   | D/V  |
| 1.15.3 | Überprüfen Sie, ob regelmäßige Kontrollen durchgeführt werden, um eine unautorisierte Wiederverwendung oder das Auslaufen von mit Wasserzeichen versehenen Daten zu erkennen. |   3   | D/V  |

---

## C1.16 Verwaltung der Rechte der betroffenen Personen

Unterstützung der Rechte betroffener Personen wie Zugriff, Berichtigung, Einschränkung und Widerspruch.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Verifizieren Sie, dass Mechanismen vorhanden sind, um Anfragen von betroffenen Personen auf Zugang, Berichtigung, Einschränkung oder Widerspruch zu beantworten. |   2   | D/V  |
| 1.16.2 | Stellen Sie sicher, dass Anfragen protokolliert, verfolgt und innerhalb der gesetzlich vorgeschriebenen Fristen erfüllt werden.                                  |   2   | D/V  |
| 1.16.3 | Überprüfen Sie, dass die Prozesse zur Wahrung der Rechte der betroffenen Personen regelmäßig auf ihre Wirksamkeit getestet und überprüft werden.                 |   2   | D/V  |

---

## C1.17 Analyse der Auswirkungen von Datensatzversionen

Bewerten Sie die Auswirkungen von Datensatzänderungen, bevor Sie Versionen aktualisieren oder ersetzen.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.17.1 | Stellen Sie sicher, dass vor der Aktualisierung oder dem Ersatz einer Datensatzversion eine Auswirkungsanalyse durchgeführt wird, die die Modellleistung, Fairness und Compliance abdeckt. |   2   | D/V  |
| 1.17.2 | Stellen Sie sicher, dass die Ergebnisse der Auswirkungsanalyse dokumentiert und von den relevanten Stakeholdern überprüft werden.                                                          |   2   | D/V  |
| 1.17.3 | Stellen Sie sicher, dass Rücksetzpläne vorhanden sind, falls neue Versionen inakzeptable Risiken oder Rückschritte einführen.                                                              |   2   | D/V  |

---

## C1.18 Sicherheit der Datenannotatoren-Mitarbeiter

Gewährleisten Sie die Sicherheit und Integrität des Personals, das an der Datenannotation beteiligt ist.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Stellen Sie sicher, dass alle an der Datenannotation beteiligten Personen einer Hintergrundüberprüfung unterzogen und in Datensicherheit und Datenschutz geschult sind. |   2   | D/V  |
| 1.18.2 | Stellen Sie sicher, dass alle Annotationsmitarbeiter Vertraulichkeits- und Geheimhaltungsvereinbarungen unterschreiben.                                                 |   2   | D/V  |
| 1.18.3 | Überprüfen Sie, ob Annotationsplattformen Zugriffskontrollen durchsetzen und auf Insider-Bedrohungen überwachen.                                                        |   2   | D/V  |

---

## Quellenangaben

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

