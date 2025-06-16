# C6 Sicherheit der Lieferkette für Modelle, Frameworks und Daten

## Kontrollziel

KI-Lieferkettenangriffe nutzen Drittanbieter-Modelle, Frameworks oder Datensätze aus, um Hintertüren, Verzerrungen oder ausnutzbaren Code einzuschleusen. Diese Kontrollen bieten eine durchgängige Herkunftsnachverfolgung, Schwachstellenmanagement und Überwachung, um den gesamten Lebenszyklus des Modells zu schützen.

---

## C6.1 Überprüfung und Herkunft vortrainierter Modelle

Bewerten und authentifizieren Sie die Herkunft, Lizenzen und versteckte Verhaltensweisen von Drittanbieter-Modellen, bevor Sie diese feinabstimmen oder bereitstellen.

|   #   | Description                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Verifizieren Sie, dass jedes Drittanbieter-Modellartefakt einen signierten Herkunftsdatensatz enthält, der das Quell-Repository und den Commit-Hash identifiziert.                                   |   1   | D/V  |
| 6.1.2 | Stellen Sie sicher, dass Modelle vor dem Import mit automatisierten Werkzeugen auf bösartige Schichten oder Trojaner-Auslöser überprüft werden.                                                      |   1   | D/V  |
| 6.1.3 | Überprüfen Sie, dass das Transferlernen durch Feinabstimmung die adversariale Evaluierung besteht, um verborgene Verhaltensweisen zu erkennen.                                                       |   2   |  D   |
| 6.1.4 | Überprüfen Sie, ob Modelllizenzen, Exportkontrollkennzeichnungen und Angaben zur Datenherkunft in einem ML-BOM-Eintrag erfasst sind.                                                                 |   2   |  V   |
| 6.1.5 | Stellen Sie sicher, dass Modelle mit hohem Risiko (öffentlich hochgeladene Gewichte, nicht verifizierte Ersteller) in Quarantäne bleiben, bis eine menschliche Überprüfung und Freigabe erfolgt ist. |   3   | D/V  |

---

## C6.2 Rahmenwerk- und Bibliotheksscanning

Scannen Sie kontinuierlich ML-Frameworks und Bibliotheken auf CVEs und bösartigen Code, um den Laufzeit-Stack sicher zu halten.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Stellen Sie sicher, dass CI-Pipelines Abhängigkeitsprüfer für KI-Frameworks und kritische Bibliotheken ausführen.                                         |   1   | D/V  |
| 6.2.2 | Überprüfen Sie, ob kritische Schwachstellen (CVSS ≥ 7,0) die Freigabe zur Produktion von Images blockieren.                                               |   1   | D/V  |
| 6.2.3 | Stellen Sie sicher, dass die statische Codeanalyse bei geforkten oder eingebundenen ML-Bibliotheken durchgeführt wird.                                    |   2   |  D   |
| 6.2.4 | Stellen Sie sicher, dass Vorschläge für Framework-Upgrades eine Sicherheitsauswirkungsbewertung enthalten, die sich auf öffentliche CVE-Feeds bezieht.    |   2   |  V   |
| 6.2.5 | Überprüfen Sie, ob Laufzeitsensoren Alarm schlagen, wenn unerwartete dynamische Bibliotheksladevorgänge auftreten, die von der signierten SBOM abweichen. |   3   |  V   |

---

## C6.3 Abhängigkeitsfestlegung und -überprüfung

Fixieren Sie jede Abhängigkeit auf unveränderliche Digests und reproduzieren Sie Builds, um identische, manipulationssichere Artefakte zu gewährleisten.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Überprüfen Sie, ob alle Paketmanager Versionsfixierung über Sperrdateien durchsetzen.                                                                   |   1   | D/V  |
| 6.3.2 | Stellen Sie sicher, dass unveränderliche Hashwerte (Digests) anstelle von veränderlichen Tags in Containerreferenzen verwendet werden.                  |   1   | D/V  |
| 6.3.3 | Überprüfen Sie, dass die Reproducible-Build-Prüfungen Hashes über CI-Durchläufe hinweg vergleichen, um identische Ausgaben sicherzustellen.             |   2   |  D   |
| 6.3.4 | Stellen Sie sicher, dass Build-Atteste für 18 Monate zur Audit-Rückverfolgbarkeit gespeichert werden.                                                   |   2   |  V   |
| 6.3.5 | Überprüfen Sie, ob abgelaufene Abhängigkeiten automatisierte Pull-Requests auslösen, um aktualisierte oder geforkte festgelegte Versionen zu erstellen. |   3   |  D   |

---

## C6.4 Durchsetzung vertrauenswürdiger Quellen

Erlauben Sie den Download von Artefakten nur von kryptografisch verifizierten, organisationszertifizierten Quellen und blockieren Sie alle anderen.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Überprüfen Sie, dass Modellgewichte, Datensätze und Container nur von genehmigten Domains oder internen Registern heruntergeladen werden.                 |   1   | D/V  |
| 6.4.2 | Stellen Sie sicher, dass Sigstore/Cosign-Signaturen die Identität des Herausgebers überprüfen, bevor Artefakte lokal zwischengespeichert werden.          |   1   | D/V  |
| 6.4.3 | Überprüfen Sie, ob Egress-Proxys nicht authentifizierte Artefakt-Downloads blockieren, um die Richtlinie für vertrauenswürdige Quellen durchzusetzen.     |   2   |  D   |
| 6.4.4 | Stellen Sie sicher, dass Repository-Whitelist-Überprüfungen vierteljährlich erfolgen, mit Nachweis einer geschäftlichen Rechtfertigung für jeden Eintrag. |   2   |  V   |
| 6.4.5 | Überprüfen Sie, dass Richtlinienverletzungen die Quarantäne von Artefakten auslösen und abhängige Pipeline-Durchläufe zurückgesetzt werden.               |   3   |  V   |

---

## C6.5 Risikobewertung von Drittanbieter-Datensätzen

Bewerten Sie externe Datensätze auf Vergiftung, Verzerrung und rechtliche Konformität und überwachen Sie diese während ihres gesamten Lebenszyklus.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Stellen Sie sicher, dass externe Datensätze einer Risikoanalyse auf Datenvergiftung unterzogen werden (z. B. Daten-Fingerprinting, Ausreißererkennung). |   1   | D/V  |
| 6.5.2 | Stellen Sie sicher, dass Bias-Metriken (demografische Parität, gleiche Chancen) vor der Genehmigung des Datensatzes berechnet werden.                   |   1   |  D   |
| 6.5.3 | Überprüfen Sie, ob Herkunft und Lizenzbedingungen für Datensätze in ML-BOM-Einträgen erfasst sind.                                                      |   2   |  V   |
| 6.5.4 | Überprüfen Sie, ob eine regelmäßige Überwachung Verschiebungen oder Korruption in gehosteten Datensätzen erkennt.                                       |   2   |  V   |
| 6.5.5 | Stellen Sie sicher, dass unzulässige Inhalte (Urheberrecht, personenbezogene Daten) vor dem Training durch automatisiertes Säubern entfernt werden.     |   3   |  D   |

---

## C6.6 Überwachung von Angriffen auf die Lieferkette

Erkennen Sie Bedrohungen in der Lieferkette frühzeitig durch CVE-Feeds, Audit-Log-Analysen und Red-Team-Simulationen.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Überprüfen Sie, dass CI/CD-Auditprotokolle an SIEM-Systeme übertragen werden, um anomale Paketabrufe oder manipulierte Build-Schritte zu erkennen.                |   1   |  V   |
| 6.6.2 | Stellen Sie sicher, dass die Incident-Response-Playbooks Rücksetzverfahren für kompromittierte Modelle oder Bibliotheken enthalten.                               |   2   |  D   |
| 6.6.3 | Verifizieren Sie, dass die Bedrohungsinformationen-Anreicherung ML-spezifische Indikatoren (z. B. IoCs für Modellvergiftung) bei der Alarmbewertung kennzeichnet. |   3   |  V   |

---

## C6.7 ML-BOM für Modellartefakte

Erzeugen und signieren Sie detaillierte ML-spezifische SBOMs (ML-BOMs), damit nachgelagerte Nutzer die Integrität der Komponenten zur Bereitstellungszeit überprüfen können.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Überprüfen Sie, dass jedes Modellartefakt ein ML-BOM veröffentlicht, das Datensätze, Gewichte, Hyperparameter und Lizenzen auflistet.              |   1   | D/V  |
| 6.7.2 | Überprüfen Sie, dass die ML-BOM-Erstellung und die Cosign-Signierung in der CI automatisiert sind und für das Zusammenführen erforderlich sind.    |   1   | D/V  |
| 6.7.3 | Überprüfen Sie, ob die Vollständigkeitsprüfungen von ML-BOM den Build abbrechen, wenn Metadaten zu einer Komponente (Hash, Lizenz) fehlen.         |   2   |  D   |
| 6.7.4 | Überprüfen Sie, dass nachgelagerte Verbraucher ML-BOMs über die API abfragen können, um importierte Modelle zur Bereitstellungszeit zu validieren. |   2   |  V   |
| 6.7.5 | Überprüfen Sie, ob ML-BOMs versionskontrolliert sind und Differenzen analysiert werden, um unautorisierte Änderungen zu erkennen.                  |   3   |  V   |

---

## Literaturverzeichnis

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

