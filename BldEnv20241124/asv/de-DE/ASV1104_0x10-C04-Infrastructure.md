# C4-Infrastruktur, Konfiguration und Bereitstellungssicherheit

## Kontrollziel

Die KI-Infrastruktur muss durch sichere Konfiguration, Laufzeitisolation, vertrauenswürdige Bereitstellungspipelines und umfassende Überwachung gegen Privilegieneskalation, Manipulation der Lieferkette und laterale Bewegung gehärtet werden. Nur autorisierte, validierte Infrastrukturkomponenten und Konfigurationen gelangen durch kontrollierte Prozesse, die Sicherheit, Integrität und Prüfbarkeit gewährleisten, in die Produktion.

Kernziel der Sicherheit: Nur kryptografisch signierte, auf Schwachstellen geprüfte Infrastrukturkomponenten gelangen über automatisierte Validierungspipelines, die Sicherheitsrichtlinien durchsetzen und unveränderliche Prüfpfade aufrechterhalten, in die Produktion.

---

## C4.1 Laufzeitumgebungsisolation

Verhindern Sie Container-Escape und Privilegieneskalation durch Kernel-Level-Isolationsprimitive und obligatorische Zugriffskontrollen.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Stellen Sie sicher, dass alle KI-Container alle Linux-Fähigkeiten außer CAP_SETUID, CAP_SETGID und ausdrücklich in den Sicherheitsgrundlagen dokumentierten benötigten Fähigkeiten entfernen.                                                     |   1   | D/V  |
| 4.1.2 | Überprüfen Sie, dass Seccomp-Profile alle Systemaufrufe blockieren, außer diejenigen in vorab genehmigten Zulassungslisten, wobei Verstöße zum Beenden des Containers und zur Generierung von Sicherheitswarnungen führen.                        |   1   | D/V  |
| 4.1.3 | Überprüfen Sie, ob KI-Arbeitslasten mit schreibgeschützten Root-Dateisystemen, tmpfs für temporäre Daten und benannten Volumes für persistente Daten ausgeführt werden, wobei noexec-Mount-Optionen durchgesetzt sind.                            |   2   | D/V  |
| 4.1.4 | Überprüfen Sie, ob die auf eBPF-basierte Laufzeitüberwachung (Falco, Tetragon oder gleichwertig) Versuche zur Rechteerweiterung erkennt und rechtsverletzende Prozesse automatisch innerhalb der organisatorischen Reaktionszeitvorgaben beendet. |   2   | D/V  |
| 4.1.5 | Stellen Sie sicher, dass KI-Arbeitslasten mit hohem Risiko in hardware-isolierten Umgebungen (Intel TXT, AMD SVM oder dedizierte Bare-Metal-Knoten) mit Attestationsprüfung ausgeführt werden.                                                    |   3   | D/V  |

---

## C4.2 Sichere Build- und Deployment-Pipelines

Sichern Sie die kryptografische Integrität und die Sicherheit der Lieferkette durch reproduzierbare Builds und signierte Artefakte.

|   #   | Description                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.2.1 | Stellen Sie sicher, dass Infrastructure-as-Code bei jedem Commit mit Tools (tfsec, Checkov oder Terrascan) gescannt wird und das Zusammenführen bei CRITICAL- oder HIGH-Severity-Funden blockiert wird.                                          |   1   | D/V  |
| 4.2.2 | Verifizieren Sie, dass Container-Builds reproduzierbar sind und identische SHA256-Hashes über mehrere Builds hinweg erzeugen, und erstellen Sie SLSA Level 3 Herkunftszertifikate, die mit Sigstore signiert sind.                               |   1   | D/V  |
| 4.2.3 | Stellen Sie sicher, dass Container-Images CycloneDX- oder SPDX-SBOMs einbetten und vor dem Push in das Register mit Cosign signiert sind, wobei unsignierte Images bei der Bereitstellung abgelehnt werden.                                      |   2   | D/V  |
| 4.2.4 | Überprüfen Sie, dass CI/CD-Pipelines OIDC-Token von HashiCorp Vault, AWS IAM-Rollen oder Azure Managed Identity verwenden, deren Gültigkeitsdauer die in der Sicherheitsrichtlinie der Organisation festgelegten Grenzwerte nicht überschreitet. |   2   | D/V  |
| 4.2.5 | Stellen Sie sicher, dass Cosign-Signaturen und SLSA-Provenienz während des Bereitstellungsprozesses vor der Ausführung des Containers überprüft werden und dass Verifizierungsfehler dazu führen, dass die Bereitstellung fehlschlägt.           |   2   | D/V  |
| 4.2.6 | Stellen Sie sicher, dass Build-Umgebungen in flüchtigen Containern oder VMs ohne persistenten Speicher und mit Netzwerkisolation von Produktions-VPCs laufen.                                                                                    |   2   | D/V  |

---

## C4.3 Netzwerksicherheit & Zugriffskontrolle

Implementieren Sie Zero-Trust-Netzwerke mit Standard-Deny-Richtlinien und verschlüsselter Kommunikation.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Überprüfen Sie, ob Kubernetes NetworkPolicies oder ein Äquivalent eine Standardverweigerung für Eingangs- und Ausgangsverkehr implementieren, mit expliziten Erlaubnisregeln für die benötigten Ports (443, 8080 usw.). |   1   | D/V  |
| 4.3.2 | Überprüfen Sie, ob SSH (Port 22), RDP (Port 3389) und Cloud-Metadaten-Endpunkte (169.254.169.254) blockiert sind oder eine zertifikatbasierte Authentifizierung erfordern.                                              |   1   | D/V  |
| 4.3.3 | Überprüfen Sie, ob ausgehender Datenverkehr über HTTP/HTTPS-Proxys (Squid, Istio oder Cloud-NAT-Gateways) mit Domain-Whitelist gefiltert wird und blockierte Anfragen protokolliert werden.                             |   2   | D/V  |
| 4.3.4 | Überprüfen Sie, dass die Inter-Service-Kommunikation mutual TLS verwendet, wobei Zertifikate gemäß der Organisationsrichtlinie rotiert und die Zertifikatvalidierung durchgesetzt wird (keine Skip-Verify-Flags).       |   2   | D/V  |
| 4.3.5 | Stellen Sie sicher, dass die KI-Infrastruktur in dedizierten VPCs/VNets ohne direkten Internetzugang läuft und nur über NAT-Gateways oder Bastion-Hosts kommuniziert.                                                   |   2   | D/V  |

---

## C4.4 Geheimnisse und kryptografische Schlüsselverwaltung

Schützen Sie Anmeldeinformationen durch hardwaregestützte Speicherung und automatische Rotation mit Zero-Trust-Zugriff.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Stellen Sie sicher, dass Geheimnisse in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault oder Google Secret Manager mit ruhender Verschlüsselung unter Verwendung von AES-256 gespeichert sind.                                                  |   1   | D/V  |
| 4.4.2 | Stellen Sie sicher, dass kryptografische Schlüssel in FIPS 140-2 Level 2 HSMs (AWS CloudHSM, Azure Dedicated HSM) mit einer Schlüsselrotation gemäß der organisatorischen Kryptografierichtlinie erzeugt werden.                                      |   1   | D/V  |
| 4.4.3 | Verifizieren Sie, dass die Geheimnisrotation automatisiert ist, mit unterbrechungsfreier Bereitstellung und sofortiger Rotation, die durch Personalwechsel oder Sicherheitsvorfälle ausgelöst wird.                                                   |   2   | D/V  |
| 4.4.4 | Stellen Sie sicher, dass Container-Images mit Tools (GitLeaks, TruffleHog oder detect-secrets) gescannt werden, die Builds blockieren, die API-Schlüssel, Passwörter oder Zertifikate enthalten.                                                      |   2   | D/V  |
| 4.4.5 | Überprüfen Sie, dass der Zugriff auf Produktionsgeheimnisse eine Multi-Faktor-Authentifizierung (MFA) mit Hardware-Token (YubiKey, FIDO2) erfordert und durch unveränderliche Audit-Logs mit Benutzeridentitäten und Zeitstempeln protokolliert wird. |   2   | D/V  |
| 4.4.6 | Stellen Sie sicher, dass Geheimnisse über Kubernetes-Secrets, eingehängte Volumes oder Init-Container bereitgestellt werden, und gewährleisten Sie, dass Geheimnisse niemals in Umgebungsvariablen oder Images eingebettet sind.                      |   2   | D/V  |

---

## C4.5 KI-Arbeitslast-Sandboxing und Validierung

Isolieren Sie nicht vertrauenswürdige KI-Modelle in sicheren Sandboxes mit umfassender Verhaltensanalyse.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Stellen Sie sicher, dass externe KI-Modelle in gVisor, MicroVMs (wie Firecracker, CrossVM) oder Docker-Containern mit den Flags --security-opt=no-new-privileges und --read-only ausgeführt werden.                                 |   1   | D/V  |
| 4.5.2 | Stellen Sie sicher, dass Sandbox-Umgebungen keine Netzwerkverbindung haben (--network=none) oder nur Zugriff auf localhost mit allen externen Anfragen, die durch iptables-Regeln blockiert sind.                                   |   1   | D/V  |
| 4.5.3 | Stellen Sie sicher, dass die Validierung des KI-Modells automatisierte Red-Team-Tests mit organisatorisch definiertem Testumfang und Verhaltensanalyse zur Erkennung von Hintertüren umfasst.                                       |   2   | D/V  |
| 4.5.4 | Stellen Sie sicher, dass bevor ein KI-Modell in die Produktion übernommen wird, seine Sandbox-Ergebnisse von autorisiertem Sicherheitspersonal kryptographisch signiert und in unveränderlichen Prüfprotokollen gespeichert werden. |   2   | D/V  |
| 4.5.5 | Stellen Sie sicher, dass Sandbox-Umgebungen zwischen den Bewertungen zerstört und aus goldenen Images neu erstellt werden, wobei eine vollständige Bereinigung des Dateisystems und des Arbeitsspeichers erfolgt.                   |   2   | D/V  |

---

## C4.6 Überwachung der Infrastruktur-Sicherheit

Die Infrastruktur kontinuierlich mit automatisierter Fehlerbehebung und Echtzeit-Benachrichtigungen scannen und überwachen.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.6.1 | Stellen Sie sicher, dass Container-Images gemäß den organisatorischen Zeitplänen gescannt werden, wobei CRITICAL-Schwachstellen basierend auf den Risiko-Schwellenwerten der Organisation die Bereitstellung blockieren.       |   1   | D/V  |
| 4.6.2 | Überprüfen Sie, ob die Infrastruktur die CIS Benchmarks oder NIST 800-53 Kontrollen mit organisatorisch definierten Compliance-Schwellenwerten erfüllt und automatisierte Behebungen für fehlgeschlagene Prüfungen durchführt. |   1   | D/V  |
| 4.6.3 | Stellen Sie sicher, dass Schwachstellen mit HOHER Schwere entsprechend den Fristen des organisatorischen Risikomanagements gepatcht werden, wobei für aktiv ausgenutzte CVEs Notfallverfahren angewendet werden.               |   2   | D/V  |
| 4.6.4 | Überprüfen Sie, ob Sicherheitswarnungen mit SIEM-Plattformen (Splunk, Elastic oder Sentinel) unter Verwendung der Formate CEF oder STIX/TAXII mit automatischer Anreicherung integriert sind.                                  |   2   |  V   |
| 4.6.5 | Überprüfen Sie, dass Infrastrukturmetriken an Überwachungssysteme (Prometheus, DataDog) mit SLA-Dashboards und Managementberichterstattung exportiert werden.                                                                  |   3   |  V   |
| 4.6.6 | Überprüfen Sie, dass Konfigurationsabweichungen mithilfe von Tools (Chef InSpec, AWS Config) gemäß den organisatorischen Überwachungsanforderungen erkannt werden, mit automatischem Rollback bei unautorisierten Änderungen.  |   2   | D/V  |

---

## C4.7 Verwaltung von KI-Infrastrukturressourcen

Verhindern Sie Angriffe durch Ressourcenerschöpfung und gewährleisten Sie eine faire Ressourcenzuteilung durch Quoten und Überwachung.

|   #   | Description                                                                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Überprüfen Sie, ob die Nutzung von GPU/TPU überwacht wird, mit Warnmeldungen, die bei organisatorisch definierten Schwellenwerten ausgelöst werden, und ob automatische Skalierung oder Lastenausgleich basierend auf Kapazitätsmanagementrichtlinien aktiviert sind. |   1   | D/V  |
| 4.7.2 | Verifizieren Sie, dass KI-Arbeitslastmetriken (Inferenzlatenz, Durchsatz, Fehlerquoten) gemäß den organisatorischen Überwachungsanforderungen erfasst und mit der Infrastruktur-Auslastung korreliert werden.                                                         |   1   | D/V  |
| 4.7.3 | Stellen Sie sicher, dass Kubernetes ResourceQuotas oder ein Äquivalent einzelne Workloads gemäß den organisatorischen Ressourcenzuteilungsrichtlinien mit durchgesetzten harten Grenzen begrenzen.                                                                    |   2   | D/V  |
| 4.7.4 | Überprüfen Sie, dass die Kostenüberwachung die Ausgaben pro Arbeitslast/Mieter nachverfolgt, mit Warnmeldungen basierend auf organisatorischen Budgetgrenzen und automatisierten Kontrollmechanismen zur Vermeidung von Budgetüberschreitungen.                       |   2   |  V   |
| 4.7.5 | Überprüfen Sie, ob die Kapazitätsplanung historische Daten mit organisatorisch definierten Prognoseperioden verwendet und eine automatisierte Ressourcenzuweisung basierend auf Nachfrage Mustern durchführt.                                                         |   3   |  V   |
| 4.7.6 | Überprüfen Sie, dass Ressourcenerschöpfung gemäß den organisatorischen Reaktionsanforderungen Circuit Breaker auslöst, einschließlich der Begrenzung der Anfragerate basierend auf Kapazitätsrichtlinien und Arbeitslastisolierung.                                   |   2   | D/V  |

---

## C4.8 Umgebungstrennung & Beförderungskontrollen

Durchsetzung strenger Umgebungsgrenzen mit automatisierten Freigabetoren und Sicherheitsvalidierung.

|   #   | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Überprüfen Sie, dass Entwicklungs-, Test- und Produktionsumgebungen in separaten VPCs/VNets betrieben werden, ohne gemeinsame IAM-Rollen, Sicherheitsgruppen oder Netzwerkverbindungen.                                                                                          |   1   | D/V  |
| 4.8.2 | Stellen Sie sicher, dass die Freigabe von Umgebungen die Zustimmung von organisatorisch definiertem autorisiertem Personal mit kryptografischen Signaturen und unveränderlichen Prüfnachweisen erfordert.                                                                        |   1   | D/V  |
| 4.8.3 | Überprüfen Sie, dass Produktionsumgebungen den SSH-Zugang blockieren, Debug-Endpunkte deaktivieren und Änderungsanträge mit organisatorischer Vorankündigungspflicht außer in Notfällen erfordern.                                                                               |   2   | D/V  |
| 4.8.4 | Stellen Sie sicher, dass Änderungen an Infrastructure-as-Code vor dem Merge in den Hauptzweig eine Peer-Review mit automatisierten Tests und Sicherheitsprüfungen durchlaufen.                                                                                                   |   2   | D/V  |
| 4.8.5 | Stellen Sie sicher, dass Nicht-Produktionsdaten gemäß den Datenschutzanforderungen der Organisation anonymisiert sind, eine synthetische Datengenerierung erfolgt oder eine vollständige Datenmaskierung mit Entfernung personenbezogener Informationen (PII) verifiziert wurde. |   2   | D/V  |
| 4.8.6 | Stellen Sie sicher, dass die Freigabetore automatisierte Sicherheitstests (SAST, DAST, Container-Scanning) enthalten und für die Genehmigung keine kritischen Befunde zulässig sind.                                                                                             |   2   | D/V  |

---

## C4.9 Infrastruktur-Backup & Wiederherstellung

Sichern Sie die Infrastrukturrsistenz durch automatisierte Backups, getestete Wiederherstellungsverfahren und Fähigkeiten zur Katastrophenwiederherstellung.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.9.1 | Überprüfen Sie, ob die Infrastrukturkonfigurationen gemäß den organisatorischen Sicherungsplänen mit einer 3-2-1-Backup-Strategie in geografisch separate Regionen gesichert werden.                                           |   1   | D/V  |
| 4.9.2 | Stellen Sie sicher, dass Backup-Systeme in isolierten Netzwerken mit separaten Zugangsdaten und luftgetrennter Speicherung zum Schutz vor Ransomware betrieben werden.                                                         |   2   | D/V  |
| 4.9.3 | Überprüfen Sie, dass Wiederherstellungsverfahren gemäß den organisatorischen Zeitplänen mit automatisierten Tests getestet und validiert werden, wobei die RTO- und RPO-Ziele den organisatorischen Anforderungen entsprechen. |   2   |  V   |
| 4.9.4 | Stellen Sie sicher, dass die Katastrophenwiederherstellung AI-spezifische Runbooks mit Wiederherstellung der Modellgewichte, dem Wiederaufbau von GPU-Clustern und der Abbildung von Dienstabhängigkeiten umfasst.             |   3   |  V   |

---

## C4.10 Infrastruktur-Compliance und Governance

Erreichen Sie regulatorische Compliance durch kontinuierliche Bewertung, Dokumentation und automatisierte Kontrollen.

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Stellen Sie sicher, dass die Einhaltung der Infrastruktur gemäß den organisatorischen Zeitplänen anhand von SOC 2-, ISO 27001- oder FedRAMP-Kontrollen mit automatisierter Beweissammlung bewertet wird.                   |   2   | D/V  |
| 4.10.2 | Stellen Sie sicher, dass die Infrastrukturdokumentation Netzwerktopologien, Datenflussdiagramme und Bedrohungsmodelle enthält, die gemäß den Anforderungen des organisatorischen Änderungsmanagements aktualisiert wurden. |   2   |  V   |
| 4.10.3 | Stellen Sie sicher, dass Infrastrukturänderungen einer automatisierten Compliance-Auswirkungsbewertung unterzogen werden, einschließlich regulatorischer Genehmigungsabläufe für risikoreiche Änderungen.                  |   3   | D/V  |

---

## C4.11 KI-Hardware-Sicherheit

Sichern Sie KI-spezifische Hardwarekomponenten, einschließlich GPUs, TPUs und spezialisierter KI-Beschleuniger.

|   #    | Description                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Stellen Sie sicher, dass die Firmware des KI-Beschleunigers (GPU-BIOS, TPU-Firmware) mit kryptografischen Signaturen verifiziert wird und gemäß den Zeitplänen des organisatorischen Patch-Managements aktualisiert wird.     |   2   | D/V  |
| 4.11.2 | Stellen Sie sicher, dass vor der Ausführung der Arbeitslast die Integrität des KI-Beschleunigers durch Hardware-Attestierung mittels TPM 2.0, Intel TXT oder AMD SVM überprüft wird.                                          |   2   | D/V  |
| 4.11.3 | Überprüfen Sie, dass der GPU-Speicher zwischen den Arbeitslasten mithilfe von SR-IOV, MIG (Multi-Instance GPU) oder einer gleichwertigen Hardware-Partitionierung mit Speicherbereinigung zwischen den Aufgaben isoliert ist. |   2   | D/V  |
| 4.11.4 | Stellen Sie sicher, dass die Lieferkette der KI-Hardware eine Herkunftsüberprüfung mit Herstellerzertifikaten und Validierung der manipulationssicheren Verpackung umfasst.                                                   |   3   |  V   |
| 4.11.5 | Stellen Sie sicher, dass Hardware-Sicherheitsmodule (HSMs) die KI-Modellgewichte und kryptografischen Schlüssel mit einer FIPS 140-2 Level 3 oder Common Criteria EAL4+ Zertifizierung schützen.                              |   3   | D/V  |

---

## C4.12 Edge- und verteilte KI-Infrastruktur

Sichere verteilte KI-Implementierungen einschließlich Edge-Computing, föderiertem Lernen und Multi-Site-Architekturen.

|   #    | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Verifizieren Sie, dass Edge-AI-Geräte sich gegenüber der zentralen Infrastruktur mittels gegenseitiger TLS-Authentifizierung unter Verwendung von Gerätezertifikaten authentifizieren, die gemäß der organisatorischen Zertifikatsverwaltungsrichtlinie regelmäßig ausgetauscht werden. |   2   | D/V  |
| 4.12.2 | Stellen Sie sicher, dass Edge-Geräte Secure Boot mit verifizierten Signaturen und Rollback-Schutz implementieren, um Firmware-Downgrade-Angriffe zu verhindern.                                                                                                                         |   2   | D/V  |
| 4.12.3 | Überprüfen Sie, dass die verteilte KI-Koordination byzantinische fehlertolerante Konsensalgorithmen mit Teilnehmervalidierung und Erkennung bösartiger Knoten verwendet.                                                                                                                |   3   | D/V  |
| 4.12.4 | Überprüfen Sie, ob die Kommunikation von Edge zu Cloud Bandbreitenbegrenzung, Datenkompression und Offline-Betriebsfunktionen mit sicherer lokaler Speicherung umfasst.                                                                                                                 |   3   | D/V  |

---

## C4.13 Multi-Cloud- und Hybrid-Infrastruktur-Sicherheit

Sichern Sie KI-Workloads über mehrere Cloud-Anbieter und hybride Cloud-On-Premises-Bereitstellungen hinweg.

|   #    | Description                                                                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.13.1 | Stellen Sie sicher, dass Multi-Cloud KI-Bereitstellungen Cloud-agnostische Identitätsföderation (OIDC, SAML) mit zentralem Richtlinienmanagement über verschiedene Anbieter hinweg verwenden.                                                                      |   2   | D/V  |
| 4.13.2 | Überprüfen Sie, dass der datenaustausch zwischen verschiedenen Clouds mittels Ende-zu-Ende-Verschlüsselung unter Verwendung von vom Kunden verwalteten Schlüsseln erfolgt und dass Datenresidenzkontrollen gemäß der jeweiligen Rechtsordnung durchgesetzt werden. |   2   | D/V  |
| 4.13.3 | Überprüfen Sie, ob hybride Cloud-KI-Workloads konsistente Sicherheitsrichtlinien sowohl in lokalen als auch in Cloud-Umgebungen mit einheitlichem Monitoring und Alarmierung implementieren.                                                                       |   2   | D/V  |
| 4.13.4 | Überprüfen Sie, dass die Vermeidung der Anbieterbindung in der Cloud portierbare Infrastruktur-als-Code, standardisierte APIs und Datenexportfunktionen mit Formatkonvertierungstools umfasst.                                                                     |   3   |  V   |
| 4.13.5 | Stellen Sie sicher, dass die Multi-Cloud-Kostenoptimierung Sicherheitskontrollen umfasst, die eine Ressourcenverbreitung verhindern sowie unerlaubte bereichsübergreifende Datenübertragungskosten zwischen Clouds vermeiden.                                      |   3   |  V   |

---

## C4.14 Infrastrukturautomatisierung & GitOps-Sicherheit

Sichern Sie Automatisierungspipelines für die Infrastruktur und GitOps-Workflows zur Verwaltung der KI-Infrastruktur.

|   #    | Description                                                                                                                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Stellen Sie sicher, dass GitOps-Repositories signierte Commits mit GPG-Schlüsseln erfordern und Branch-Schutzregeln implementiert sind, die direkte Pushes zu Hauptzweigen verhindern.                                                                                 |   2   | D/V  |
| 4.14.2 | Stellen Sie sicher, dass die Infrastrukturautomatisierung eine Drift-Erkennung mit automatischen Korrekturmaßnahmen und Rücksetzungsfunktionen umfasst, die entsprechend den organisatorischen Reaktionsanforderungen bei unautorisierten Änderungen ausgelöst werden. |   2   | D/V  |
| 4.14.3 | Stellen Sie sicher, dass die automatisierte Bereitstellung der Infrastruktur eine Validierung der Sicherheitspolitik umfasst und die Bereitstellung bei nicht konformen Konfigurationen blockiert.                                                                     |   2   | D/V  |
| 4.14.4 | Stellen Sie sicher, dass Geheimnisse der Infrastrukturautomatisierung über externe Geheimnisoperatoren (External Secrets Operator, Bank-Vaults) mit automatischer Rotation verwaltet werden.                                                                           |   2   | D/V  |
| 4.14.5 | Stellen Sie sicher, dass die selbstheilende Infrastruktur die Korrelierung von Sicherheitsereignissen mit automatisierter Vorfallreaktion und Benachrichtigungsabläufen für Stakeholder umfasst.                                                                       |   3   |  V   |

---

## C4.15 Quantenresistente Infrastruktursicherheit

Bereiten Sie die KI-Infrastruktur auf Bedrohungen durch Quantencomputing vor, indem Sie postquantum-Kryptographie und quantensichere Protokolle einsetzen.

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Stellen Sie sicher, dass die KI-Infrastruktur NIST-zugelassene postquantensichere kryptografische Algorithmen (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) für Schlüsselaustausch und digitale Signaturen implementiert. |   3   | D/V  |
| 4.15.2 | Überprüfen Sie, dass Quantenschlüsselverteilungssysteme (QKD) für hochsichere KI-Kommunikation mit quantensicheren Schlüsselverwaltungsprotokollen implementiert sind.                                                     |   3   | D/V  |
| 4.15.3 | Überprüfen Sie, dass kryptografische Agilitätsframeworks eine schnelle Migration zu neuen post-quanten Algorithmen mit automatischer Zertifikats- und Schlüsselrotation ermöglichen.                                       |   3   | D/V  |
| 4.15.4 | Überprüfen Sie, ob die Quantenbedrohungsmodellierung die Verwundbarkeit der KI-Infrastruktur gegenüber Quantenangriffen bewertet, einschließlich dokumentierter Migrationszeitpläne und Risikoanalysen.                    |   3   |  V   |
| 4.15.5 | Stellen Sie sicher, dass hybride klassische-quantum kryptografische Systeme während der Quantenübergangsphase durch eine Tiefenverteidigung mit Leistungsüberwachung Schutz bieten.                                       |   3   | D/V  |

---

## C4.16 Vertrauliches Computing & Sichere Enklaven

Schützen Sie KI-Arbeitslasten und Modellgewichte mithilfe hardwarebasierter vertrauenswürdiger Ausführungsumgebungen und Technologien für vertrauliches Computing.

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Verifizieren Sie, dass sensible KI-Modelle innerhalb von Intel SGX Enklaven, AMD SEV-SNP oder ARM TrustZone mit verschlüsseltem Speicher und Attestierungsüberprüfung ausgeführt werden.    |   3   | D/V  |
| 4.16.2 | Verifizieren Sie, dass vertrauliche Container (Kata Containers, gVisor mit Confidential Computing) KI-Workloads mit hardwaregestützter Speicher-Verschlüsselung isolieren.                  |   3   | D/V  |
| 4.16.3 | Überprüfen Sie, dass die Remote-Attestierung die Integrität der Enklave validiert, bevor AI-Modelle mit kryptografischem Nachweis der Authentizität der Ausführungsumgebung geladen werden. |   3   | D/V  |
| 4.16.4 | Überprüfen Sie, dass vertrauliche KI-Inferenzdienste eine Modellauslesung durch verschlüsselte Berechnung mit versiegelten Modellgewichten und geschützter Ausführung verhindern.           |   3   | D/V  |
| 4.16.5 | Überprüfen Sie, dass die Orchestrierung der Trusted Execution Environment den Lebenszyklus des Secure Enclave mit Remote Attestation und verschlüsselten Kommunikationskanälen verwaltet.   |   3   | D/V  |
| 4.16.6 | Überprüfen Sie, dass sichere Mehrparteienberechnung (SMPC) kollaboratives KI-Training ermöglicht, ohne individuelle Datensätze oder Modellparameter offenzulegen.                           |   3   | D/V  |

---

## C4.17 Nullwissen-Infrastruktur

Implementieren Sie Zero-Knowledge-Beweissysteme für die datenschutzfreundliche AI-Verifikation und Authentifizierung, ohne sensible Informationen preiszugeben.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Überprüfen Sie, dass Zero-Knowledge-Beweise (ZK-SNARKs, ZK-STARKs) die Integrität des KI-Modells und die Herkunft des Trainings verifizieren, ohne Modellgewichte oder Trainingsdaten offenzulegen. |   3   | D/V  |
| 4.17.2 | Überprüfen Sie, dass ZK-basierte Authentifizierungssysteme eine datenschutzfreundliche Benutzerverifizierung für KI-Dienste ermöglichen, ohne identitätsbezogene Informationen preiszugeben.        |   3   | D/V  |
| 4.17.3 | Überprüfen Sie, dass Private Set Intersection (PSI)-Protokolle eine sichere Datenabstimmung für föderierte KI ermöglichen, ohne individuelle Datensätze offenzulegen.                               |   3   | D/V  |
| 4.17.4 | Überprüfen Sie, dass Zero-Knowledge-Maschinelles Lernen (ZKML)-Systeme verifizierbare KI-Schlüsse mit kryptografischem Nachweis der korrekten Berechnung ermöglichen.                               |   3   | D/V  |
| 4.17.5 | Überprüfen Sie, dass ZK-Rollups skalierbare, datenschutzwahrende KI-Transaktionsverarbeitung mit Batch-Verifizierung und reduziertem Rechenaufwand ermöglichen.                                     |   3   | D/V  |

---

## C4.18 Verhinderung von Seitenkanalangriffen

Schützen Sie die KI-Infrastruktur vor zeitlichen, leistungsbezogenen, elektromagnetischen und cache-basierten Seitenkanal-Angriffen, die sensible Informationen preisgeben könnten.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Verifizieren Sie, dass die KI-Inferenzzeit durch den Einsatz von Algorithmen mit konstanter Zeit und Padding normalisiert wird, um zeitbezogene Modell-Extraktionsangriffe zu verhindern. |   3   | D/V  |
| 4.18.2 | Überprüfen Sie, ob der Schutz vor Leistungsanalyse die Rauschinjektion, die Filterung der Stromleitung und die randomisierten Ausführungsmuster für KI-Hardware umfasst.                  |   3   | D/V  |
| 4.18.3 | Überprüfen Sie, ob die Minderung von Cache-basierten Seitenkanalangriffen Cache-Partitionierung, Randomisierung und Flush-Befehle verwendet, um Informationsleckagen zu verhindern.       |   3   | D/V  |
| 4.18.4 | Überprüfen Sie, dass der Schutz vor elektromagnetischer Abstrahlung Abschirmung, Signalfilterung und zufällige Verarbeitung umfasst, um TEMPEST-artige Angriffe zu verhindern.            |   3   | D/V  |
| 4.18.5 | Überprüfen Sie, dass mikroarchitektonische Seitenkanalabwehrmaßnahmen spekulative Ausführungskontrollen und die Verschleierung von Speicherzugriffsmustern umfassen.                      |   3   | D/V  |

---

## C4.19 Neuromorphe und spezialisierte KI-Hardware-Sicherheit

Sichern Sie aufkommende KI-Hardwarearchitekturen, einschließlich neuromorpher Chips, FPGAs, maßgeschneiderter ASICs und optischer Rechensysteme.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Stellen Sie sicher, dass die Sicherheit von neuromorphen Chips Spike-Muster-Verschlüsselung, Schutz der synaptischen Gewichte und hardwarebasierte Validierung der Lernregeln umfasst.            |   3   | D/V  |
| 4.19.2 | Überprüfen Sie, ob FPGA-basierte KI-Beschleuniger Bitstream-Verschlüsselung, Manipulationsschutzmechanismen und sichere Konfigurationsladeverfahren mit authentifizierten Updates implementieren. |   3   | D/V  |
| 4.19.3 | Überprüfen Sie, ob die kundenspezifische ASIC-Sicherheit integrierte Sicherheitsprozessoren, eine Hardware-Root-of-Trust und sichere Schlüsselspeicherung mit Manipulationserkennung umfasst.     |   3   | D/V  |
| 4.19.4 | Verifizieren Sie, dass optische Rechensysteme quantensichere optische Verschlüsselung, sichere photonische Schaltung und geschützte optische Signalverarbeitung implementieren.                   |   3   | D/V  |
| 4.19.5 | Verifizieren Sie, dass hybride analog-digitale KI-Chips sichere analoge Berechnungen, geschützte Gewichtsspeicherung und authentifizierte Analog-Digital-Wandlung enthalten.                      |   3   | D/V  |

---

## C4.20 Datenschutzfreundliche Recheninfrastruktur

Implementieren Sie Infrastrukturkontrollen für datenschutzfreundliche Berechnungen, um sensible Daten während der KI-Verarbeitung und -Analyse zu schützen.

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.20.1 | Überprüfen Sie, dass die homomorphe Verschlüsselungsinfrastruktur eine verschlüsselte Berechnung auf sensiblen KI-Arbeitslasten mit kryptografischer Integritätsprüfung und Leistungsüberwachung ermöglicht.       |   3   | D/V  |
| 4.20.2 | Überprüfen Sie, dass Private-Information-Retrieval-Systeme Datenbankabfragen ermöglichen, ohne Abfragemuster preiszugeben, und schützen Sie dabei die Zugriffsmuster mit kryptografischen Methoden.                |   3   | D/V  |
| 4.20.3 | Verifizieren Sie, dass sichere Multi-Parteien-Berechnungsprotokolle eine datenschutzfreundliche KI-Inferenz ermöglichen, ohne individuelle Eingaben oder Zwischenberechnungen offenzulegen.                        |   3   | D/V  |
| 4.20.4 | Stellen Sie sicher, dass die datenschutzfreundliche Schlüsselverwaltung verteilte Schlüsselerzeugung, Schwellenwert-Kryptografie und sichere Schlüsselrotation mit hardwaregestütztem Schutz umfasst.              |   3   | D/V  |
| 4.20.5 | Stellen Sie sicher, dass die Leistung von datenschutzwahrender Berechnung durch Batching, Caching und Hardwarebeschleunigung optimiert wird, während die kryptografischen Sicherheitsgarantien eingehalten werden. |   3   | D/V  |

---

## C4.15 Agent Framework Cloud-Integration Sicherheit & Hybride Bereitstellung

Sicherheitskontrollen für cloud-integrierte Agentenframeworks mit hybriden On-Premises/Cloud-Architekturen.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Stellen Sie sicher, dass die Cloud-Speicherintegration End-to-End-Verschlüsselung mit agentengesteuertem Schlüsselmanagement verwendet.                 |   1   | D/V  |
| 4.15.2 | Verifizieren Sie, dass die Sicherheitsgrenzen der hybriden Bereitstellung klar definiert sind und verschlüsselte Kommunikationskanäle verwendet werden. |   2   | D/V  |
| 4.15.3 | Überprüfen Sie, dass der Zugriff auf Cloud-Ressourcen eine Zero-Trust-Verifizierung mit kontinuierlicher Authentifizierung beinhaltet.                  |   2   | D/V  |
| 4.15.4 | Überprüfen Sie, dass Anforderungen an den Datenaufenthaltsort durch kryptografische Bestätigung der Speicherorte durchgesetzt werden.                   |   3   | D/V  |
| 4.15.5 | Überprüfen Sie, ob Sicherheitsbewertungen des Cloud-Anbieters agentenspezifisches Bedrohungsmodellieren und Risikobewertungen umfassen.                 |   3   | D/V  |

---

## Referenzen

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

