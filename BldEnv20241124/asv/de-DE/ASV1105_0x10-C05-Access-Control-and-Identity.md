# C5 Zugriffskontrolle und Identität für KI-Komponenten und Nutzer

## Kontrollziel

Effektive Zugriffskontrolle für KI-Systeme erfordert ein robustes Identitätsmanagement, kontextbewusste Autorisierung und Laufzeitdurchsetzung gemäß den Zero-Trust-Prinzipien. Diese Kontrollen stellen sicher, dass Menschen, Dienste und autonome Agenten nur innerhalb ausdrücklich gewährter Bereiche mit Modellen, Daten und Rechenressourcen interagieren, mit kontinuierlicher Verifizierungs- und Prüfungsmöglichkeit.

---

## C5.1 Identitätsverwaltung & Authentifizierung

Erstellen Sie kryptografisch gesicherte Identitäten für alle Entitäten mit Multi-Faktor-Authentifizierung für privilegierte Operationen.

|   #   | Description                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Stellen Sie sicher, dass alle menschlichen Benutzer und Dienstprinzipale über einen zentralisierten Unternehmens-Identitätsanbieter (IdP) mithilfe von OIDC/SAML-Protokollen mit eindeutigen Identitäts-zu-Token-Zuordnungen (keine geteilten Konten oder Anmeldeinformationen) authentifiziert werden. |   1   | D/V  |
| 5.1.2 | Stellen Sie sicher, dass Hochrisikooperationen (Modelldeployment, Gewichts-Export, Zugriff auf Trainingsdaten, Änderungen an der Produktionskonfiguration) Multi-Faktor-Authentifizierung oder Step-Up-Authentifizierung mit Sitzungsnevalidierung erfordern.                                           |   1   | D/V  |
| 5.1.3 | Vergewissern Sie sich, dass neue Hauptbenutzer eine Identitätsprüfung durchlaufen, die mit NIST 800-63-3 IAL-2 oder gleichwertigen Standards übereinstimmt, bevor sie Zugriff auf das Produktionssystem erhalten.                                                                                       |   2   |  D   |
| 5.1.4 | Überprüfen Sie, ob Zugriffsüberprüfungen vierteljährlich durchgeführt werden, einschließlich automatischer Erkennung von inaktiven Konten, Durchsetzung der Anmeldedatenrotation und Deaktivierungs-Workflows.                                                                                          |   2   |  V   |
| 5.1.5 | Stellen Sie sicher, dass föderierte KI-Agenten sich über signierte JWT-Assertions authentifizieren, die eine maximale Lebensdauer von 24 Stunden haben und einen kryptografischen Herkunftsnachweis enthalten.                                                                                          |   3   | D/V  |

---

## C5.2 Ressourcenautorisierung & Prinzip der geringsten Privilegien

Implementieren Sie fein abgestufte Zugriffskontrollen für alle KI-Ressourcen mit expliziten Berechtigungsmodellen und Prüfpfaden.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Stellen Sie sicher, dass jede KI-Ressource (Datensätze, Modelle, Endpunkte, Vektorsammlungen, Einbettungsindizes, Recheninstanzen) rollenbasierte Zugriffskontrollen mit expliziten Erlaubnislisten und Standard-Sperr-Richtlinien durchsetzt.                 |   1   | D/V  |
| 5.2.2 | Stellen Sie sicher, dass das Prinzip der geringsten Rechte standardmäßig bei Servicekonten durchgesetzt wird, beginnend mit schreibgeschützten Berechtigungen, und dass eine dokumentierte geschäftliche Rechtfertigung für Schreibzugriff erforderlich ist.   |   1   | D/V  |
| 5.2.3 | Stellen Sie sicher, dass alle Änderungen an den Zugriffskontrollen mit genehmigten Änderungsanträgen verknüpft und unveränderlich protokolliert werden, einschließlich Zeitstempel, Identitäten der Akteure, Ressourcenkennungen und Berechtigungsdifferenzen. |   1   |  V   |
| 5.2.4 | Überprüfen Sie, dass Datenklassifizierungskennzeichnungen (PII, PHI, exportkontrolliert, proprietär) automatisch auf abgeleitete Ressourcen (Embeddings, Prompt-Caches, Modellausgaben) mit konsistenter Durchsetzung der Richtlinien übertragen werden.       |   2   |  D   |
| 5.2.5 | Überprüfen Sie, ob unautorisierte Zugriffsversuche und Ereignisse der Privilegieneskalation Echtzeit-Warnungen mit kontextbezogenen Metadaten an SIEM-Systeme innerhalb von 5 Minuten auslösen.                                                                |   2   | D/V  |

---

## C5.3 Dynamische Richtlinienbewertung

Setzen Sie attributbasierte Zugriffskontroll- (ABAC-) Engines für kontextabhängige Autorisierungsentscheidungen mit Prüfungsfunktionen ein.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Stellen Sie sicher, dass Autorisierungsentscheidungen an eine dedizierte Richtlinien-Engine (OPA, Cedar oder eine gleichwertige) ausgelagert sind, die über authentifizierte APIs mit kryptografischem Integritätsschutz zugänglich ist. |   1   | D/V  |
| 5.3.2 | Überprüfen Sie, dass Richtlinien zur Laufzeit dynamische Attribute auswerten, einschließlich Benutzerfreigabestufe, Sensitivitätsklassifizierung der Ressource, Anfragekontext, Mandantentrennung und zeitliche Beschränkungen.          |   1   | D/V  |
| 5.3.3 | Stellen Sie sicher, dass Richtliniendefinitionen versionskontrolliert, von Kollegen überprüft und durch automatisierte Tests in CI/CD-Pipelines validiert werden, bevor sie in der Produktion bereitgestellt werden.                     |   2   |  D   |
| 5.3.4 | Überprüfen Sie, ob die Ergebnisse der Richtlinienbewertung strukturierte Entscheidungsbegründungen enthalten und an SIEM-Systeme zur Korrelationsanalyse und Compliance-Berichterstattung übermittelt werden.                            |   2   |  V   |
| 5.3.5 | Überprüfen Sie, dass die Time-to-Live (TTL)-Werte für den Richtlinien-Cache 5 Minuten für hochsensible Ressourcen und 1 Stunde für Standardressourcen mit Cache-Invalidierungsfunktionen nicht überschreiten.                            |   3   | D/V  |

---

## C5.4 Sicherheitsdurchsetzung zur Abfragezeit

Implementieren Sie Sicherheitskontrollen auf Datenbankebene mit verpflichtender Filterung und Richtlinien zur Zeilenebenen-Sicherheit.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Stellen Sie sicher, dass alle Vektor-Datenbank- und SQL-Abfragen obligatorische Sicherheitsfilter (Mandanten-ID, Sensitivitätskennzeichnungen, Benutzerbereich) enthalten, die auf Ebene der Datenbank-Engine und nicht im Anwendungscode durchgesetzt werden. |   1   | D/V  |
| 5.4.2 | Überprüfen Sie, dass Richtlinien zur Zeilenebenen-Sicherheit (Row-Level Security, RLS) und Maskierung auf Feldebene mit Richtlinienvererbung für alle Vektordatenbanken, Suchindizes und Trainingsdatensätze aktiviert sind.                                   |   1   | D/V  |
| 5.4.3 | Stellen Sie sicher, dass fehlgeschlagene Autorisierungsbewertungen "Confused Deputy Angriffe" verhindern, indem Abfragen sofort abgebrochen werden und explizite Autorisierungsfehlermeldungen zurückgegeben werden, anstatt leere Ergebnismengen zu liefern.  |   2   |  D   |
| 5.4.4 | Stellen Sie sicher, dass die Latenz bei der Richtlinienauswertung kontinuierlich überwacht wird und automatisierte Warnungen bei Zeitüberschreitungen ausgelöst werden, die eine Umgehung der Autorisierung ermöglichen könnten.                               |   2   |  V   |
| 5.4.5 | Verifizieren Sie, dass Abfrage-Wiederholungsmechanismen Berechtigungsrichtlinien erneut bewerten, um dynamische Berechtigungsänderungen innerhalb aktiver Benutzersitzungen zu berücksichtigen.                                                                |   3   | D/V  |

---

## C5.5 Ausgabe-Filterung & Datenschutzprävention

Setzen Sie Nachbearbeitungskontrollen ein, um eine unbefugte Offenlegung von Daten in KI-generierten Inhalten zu verhindern.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Überprüfen Sie, dass Nach-Inferenz-Filtermechanismen unautorisierte personenbezogene Daten (PII), klassifizierte Informationen und proprietäre Daten scannen und schwärzen, bevor Inhalte an Anforderer ausgeliefert werden. |   1   | D/V  |
| 5.5.2 | Überprüfen Sie, ob Zitate, Verweise und Quellenangaben in den Modellausgaben anhand der Berechtigungen des Aufrufers validiert werden, und entfernen Sie sie, wenn ein unautorisierter Zugriff festgestellt wird.            |   1   | D/V  |
| 5.5.3 | Überprüfen Sie, dass Einschränkungen im Ausgabeformat (bereinigte PDFs, Metadaten-entfernte Bilder, genehmigte Dateitypen) basierend auf Benutzerberechtigungen und Datenklassifikationen durchgesetzt werden.               |   2   |  D   |
| 5.5.4 | Stellen Sie sicher, dass Schwärzungsalgorithmen deterministisch, versionskontrolliert sind und Prüfprotokolle führen, um Compliance-Untersuchungen und forensische Analysen zu unterstützen.                                 |   2   |  V   |
| 5.5.5 | Überprüfen Sie, dass Redaktionsereignisse mit hohem Risiko adaptive Protokolle erzeugen, die kryptografische Hashes des Originalinhalts für die forensische Wiederherstellung ohne Datenexposition enthalten.                |   3   |  V   |

---

## C5.6 Mehrmandanten-Isolation

Gewährleisten Sie kryptografische und logische Isolation zwischen Mandanten in gemeinsamer KI-Infrastruktur.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Stellen Sie sicher, dass Speicherbereiche, Embedding-Speicher, Cache-Einträge und temporäre Dateien jeweils mandantenspezifisch getrennt sind und bei Löschung des Mandanten oder Beendigung der Sitzung sicher gelöscht werden. |   1   | D/V  |
| 5.6.2 | Überprüfen Sie, dass jede API-Anfrage eine authentifizierte Mandantenkennung enthält, die kryptografisch gegen den Sitzungskontext und die Benutzerberechtigungen validiert wird.                                                |   1   | D/V  |
| 5.6.3 | Stellen Sie sicher, dass Netzwerk-Richtlinien standardmäßig Verweigerungsregeln für die Kommunikation zwischen Mandanten innerhalb von Service Meshes und Container-Orchestrierungsplattformen implementieren.                   |   2   |  D   |
| 5.6.4 | Stellen Sie sicher, dass Verschlüsselungsschlüssel pro Mandant eindeutig sind, mit Unterstützung für vom Kunden verwaltete Schlüssel (CMK) und kryptographischer Isolation zwischen den Datenspeichern der Mandanten.            |   3   |  D   |

---

## C5.7 Autonome Agentenautorisierung

Steuerung der Berechtigungen für KI-Agenten und autonome Systeme durch umfassende Berechtigungstoken und kontinuierliche Autorisierung.

|   #   | Description                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Stellen Sie sicher, dass autonome Agenten Bereiche-fähigkeits-Tokens erhalten, die ausdrücklich die erlaubten Aktionen, zugänglichen Ressourcen, Zeitgrenzen und betrieblichen Einschränkungen auflisten.                                                         |   1   | D/V  |
| 5.7.2 | Überprüfen Sie, dass risikoreiche Funktionen (Zugriff auf das Dateisystem, Codeausführung, externe API-Aufrufe, Finanztransaktionen) standardmäßig deaktiviert sind und eine ausdrückliche Genehmigung zur Aktivierung mit geschäftlichen Begründungen erfordern. |   1   | D/V  |
| 5.7.3 | Stellen Sie sicher, dass Berechtigungstoken an Benutzersitzungen gebunden sind, eine kryptografische Integritätssicherung enthalten und dass sie nicht offline gespeichert oder wiederverwendet werden können.                                                    |   2   |  D   |
| 5.7.4 | Stellen Sie sicher, dass agenteninitiierte Aktionen eine sekundäre Autorisierung durch die ABAC-Richtlinien-Engine mit vollständiger Kontextbewertung und Audit-Protokollierung durchlaufen.                                                                      |   2   |  V   |
| 5.7.5 | Überprüfen Sie, ob Fehlerbedingungen des Agenten und die Ausnahmebehandlung Informationen zum Kompetenzbereich enthalten, um die Vorfallanalyse und die forensische Untersuchung zu unterstützen.                                                                 |   3   |  V   |

---

## Referenzen

### Normen & Rahmenwerke

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Implementierungsanleitungen

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### KI-spezifische Sicherheit

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

