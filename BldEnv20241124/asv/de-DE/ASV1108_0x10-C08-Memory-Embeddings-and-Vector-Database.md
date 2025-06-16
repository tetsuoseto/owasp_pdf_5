# C8 Speicher, Einbettungen und Sicherheit von Vektordatenbanken

## Kontrollziel

Einbettungen und Vektorspeicher fungieren als das „aktive Gedächtnis“ moderner KI-Systeme, indem sie kontinuierlich vom Nutzer bereitgestellte Daten aufnehmen und diese über Retrieval-Augmented Generation (RAG) wieder in die Modellkontexte einbringen. Wird dieses Gedächtnis nicht kontrolliert, können personenbezogene Daten (PII) durchsickern, Zustimmung verletzt oder durch Inversion der ursprüngliche Text rekonstruiert werden. Ziel dieser Kontrollfamilie ist es, Gedächtnispipelines und Vektordatenbanken so zu sichern, dass der Zugriff nach dem Prinzip der minimalen Rechtevergabe erfolgt, Einbettungen datenschutzkonform sind, gespeicherte Vektoren ablaufen oder auf Abruf widerrufen werden können und das Gedächtnis eines Nutzers niemals die Eingaben oder Ausgaben eines anderen Nutzers beeinträchtigt.

---

## C8.1 Zugriffskontrollen auf Speicher- und RAG-Indizes

Durchsetzen feinkörniger Zugriffskontrollen für jede Vektorsammlung.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Überprüfen Sie, ob Zugriffssteuerungsregeln auf Zeilen-/Namespace-Ebene Einfüge-, Lösch- und Abfrageoperationen pro Mandant, Sammlung oder Dokumenttag einschränken.                           |   1   | D/V  |
| 8.1.2 | Überprüfen Sie, ob API-Schlüssel oder JWTs eingeschränkte Berechtigungen (z. B. Sammlungs-IDs, Aktionsverben) enthalten und mindestens vierteljährlich ausgetauscht werden.                    |   1   | D/V  |
| 8.1.3 | Stellen Sie sicher, dass Versuche zur Privilegieneskalation (z. B. Ähnlichkeitsabfragen über Namespace-Grenzen hinweg) erkannt und innerhalb von 5 Minuten in einem SIEM protokolliert werden. |   2   | D/V  |
| 8.1.4 | Überprüfen Sie, ob die Vector-Datenbank Prüfprotokolle für Subjektkennung, Operation, Vektor-ID/Namensraum, Ähnlichkeitsschwelle und Ergebnisanzahl aufzeichnet.                               |   2   | D/V  |
| 8.1.5 | Stellen Sie sicher, dass Zugriffsentscheidungen auf Umgehungsschwachstellen getestet werden, wann immer Engines aktualisiert oder Index-Sharding-Regeln geändert werden.                       |   3   |  V   |

---

## C8.2 Einbettungssanierung und Validierung

Text vor der Vektorisierung auf personenbezogene Daten (PII) vorfiltern, schwärzen oder pseudonymisieren und optional die Einbettungen nachverarbeiten, um verbleibende Signale zu entfernen.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.2.1 | Stellen Sie sicher, dass personenbezogene Daten (PII) und regulierte Daten durch automatisierte Klassifikatoren erkannt und vor der Einbettung maskiert, tokenisiert oder entfernt werden.                         |   1   | D/V  |
| 8.2.2 | Stellen Sie sicher, dass Einbettungspipelines Eingaben, die ausführbaren Code oder nicht UTF-8-konforme Artefakte enthalten und den Index vergiften könnten, ablehnen oder unter Quarantäne stellen.               |   1   |  D   |
| 8.2.3 | Überprüfen Sie, ob eine lokale oder metrische Differential-Privacy-Sanitierung auf Satz-Einbettungen angewendet wird, deren Abstand zu einem bekannten PII-Token unter einem konfigurierbaren Schwellenwert liegt. |   2   | D/V  |
| 8.2.4 | Stellen Sie sicher, dass die Wirksamkeit der Bereinigung (z. B. Erkennungsrate der PII-Entfernung, semantische Verschiebung) mindestens halbjährlich anhand von Referenzkorpora überprüft wird.                    |   2   |  V   |
| 8.2.5 | Stellen Sie sicher, dass Sanitierungskonfigurationen versioniert werden und Änderungen einer Peer-Review unterliegen.                                                                                              |   3   | D/V  |

---

## C8.3 Speicherablauf, Widerruf & Löschung

Die DSGVO „Recht auf Vergessenwerden“ und ähnliche Gesetze erfordern eine zeitnahe Löschung; Vektorspeicher müssen daher TTLs, harte Löschungen und Tombstoning unterstützen, damit widerrufene Vektoren nicht wiederhergestellt oder erneut indexiert werden können.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Überprüfen Sie, dass jeder Vektor- und Metadatensatz eine TTL oder ein explizites Aufbewahrungsetikett trägt, das von automatisierten Bereinigungsaufgaben beachtet wird.                                         |   1   | D/V  |
| 8.3.2 | Überprüfen Sie, dass nutzerinitiierte Löschanfragen Vektoren, Metadaten, Zwischenspeicherkopien und abgeleitete Indizes innerhalb von 30 Tagen löschen.                                                           |   1   | D/V  |
| 8.3.3 | Verifizieren Sie, dass logische Löschungen entweder durch kryptographisches Überschreiben von Speicherblöcken erfolgen, sofern die Hardware dies unterstützt, oder durch die Zerstörung des Key-Vault-Schlüssels. |   2   |  D   |
| 8.3.4 | Verifizieren Sie, dass abgelaufene Vektoren in weniger als 500 ms nach dem Ablauf bei der Suche nach den nächsten Nachbarn ausgeschlossen werden.                                                                 |   3   | D/V  |

---

## C8.4 Verhinderung von Einbettungsumkehr und Datenleckage

Jüngste Abwehrmaßnahmen – Rauschüberlagerung, Projektionsnetzwerke, Störung an Datenschutz-Neuronen und Anwendungsschicht-Verschlüsselung – können die Token-Ebene Inversionsraten auf unter 5 % senken.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Stellen Sie sicher, dass ein formales Bedrohungsmodell existiert, das Inversions-, Mitgliedschafts- und Attribut-Inferenzangriffe abdeckt und jährlich überprüft wird.                                   |   1   |  V   |
| 8.4.2 | Stellen Sie sicher, dass die Verschlüsselung auf Anwendungsebene oder die durchsuchbare Verschlüsselung Vektoren vor direktem Zugriff durch Infrastrukturadministratoren oder Cloud-Mitarbeiter schützt. |   2   | D/V  |
| 8.4.3 | Überprüfen Sie, ob die Abwehrparameter (ε für DP, Rauschparameter σ, Projektionsrang k) ein Gleichgewicht zwischen Datenschutz ≥ 99 % Token-Schutz und Nutzen ≤ 3 % Genauigkeitsverlust gewährleisten.   |   3   |  V   |
| 8.4.4 | Überprüfen Sie, dass Metriken zur Inversionsresistenz Teil der Freigabeschranken für Modellaktualisierungen sind und dass Regressionsbudgets definiert wurden.                                           |   3   | D/V  |

---

## C8.5 Durchsetzung des Geltungsbereichs für benutzerspezifischen Speicher

Leckagen zwischen Mandanten bleiben ein wichtiges Risiko bei RAG: Unsachgemäß gefilterte Ähnlichkeitsanfragen können private Dokumente eines anderen Kunden offenlegen.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Verifizieren Sie, dass jede Abrufanfrage vor der Weitergabe an das LLM-Prompt durch die Mandanten-/Benutzer-ID nachgefiltert wird.                                                                                      |   1   | D/V  |
| 8.5.2 | Stellen Sie sicher, dass Sammlungsnamen oder namespacierte IDs pro Benutzer oder Mandant mit einem Salt versehen sind, sodass Vektoren nicht über Bereiche hinweg kollidieren können.                                   |   1   |  D   |
| 8.5.3 | Überprüfen Sie, dass Ähnlichkeitsergebnisse, die über einem konfigurierbaren Distanzschwellenwert liegen, aber außerhalb des Gültigkeitsbereichs des Aufrufers liegen, verworfen werden und Sicherheitsalarme auslösen. |   2   | D/V  |
| 8.5.4 | Verifizieren Sie, dass Multi-Tenant-Stresstests adversariale Anfragen simulieren, die versuchen, Dokumente außerhalb des zulässigen Bereichs abzurufen, und dabei keine Informationslecks aufweisen.                    |   2   |  V   |
| 8.5.5 | Stellen Sie sicher, dass Verschlüsselungsschlüssel für jeden Mandanten getrennt sind und eine kryptografische Isolation gewährleistet ist, selbst wenn der physische Speicher gemeinsam genutzt wird.                   |   3   | D/V  |

---

## C8.6 Erweiterte Sicherheit von Speichersystemen

Sicherheitskontrollen für anspruchsvolle Speicherarchitekturen einschließlich episodischem, semantischem und Arbeitsgedächtnis mit spezifischen Anforderungen an Isolation und Validierung.

|   #   | Description                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Überprüfen Sie, ob verschiedene Speichertypen (episodisch, semantisch, Arbeitsgedächtnis) isolierte Sicherheitskontexte mit rollenbasierten Zugriffskontrollen, separaten Verschlüsselungsschlüsseln und dokumentierten Zugriffsmustern für jeden Speichertyp aufweisen.                                      |   1   | D/V  |
| 8.6.2 | Überprüfen Sie, ob die Prozesse der Gedächtniskonsolidierung eine Sicherheitsvalidierung einschließen, um die Einspeisung bösartiger Erinnerungen durch Inhaltsbereinigung, Quellenüberprüfung und Integritätsprüfungen vor der Speicherung zu verhindern.                                                    |   2   | D/V  |
| 8.6.3 | Stellen Sie sicher, dass Abfragen zur Speicherwiederherstellung validiert und bereinigt werden, um die Extraktion unbefugter Informationen durch Musteranalyse der Abfragen, Durchsetzung der Zugriffskontrolle und Ergebnisfilterung zu verhindern.                                                          |   2   | D/V  |
| 8.6.4 | Verifizieren Sie, dass Mechanismen zum Vergessen von Speicherinhalten vertrauliche Informationen sicher mit kryptografischen Löschgarantien löschen, indem sie Schlüssel löschen, mehrfach überschreiben oder hardwarebasierte sichere Löschungen mit Verifikationszertifikaten verwenden.                    |   3   | D/V  |
| 8.6.5 | Stellen Sie sicher, dass die Integrität des Speichersystems kontinuierlich auf unautorisierte Änderungen oder Beschädigungen überwacht wird, indem Prüfsummen, Auditprotokolle und automatisierte Warnmeldungen verwendet werden, wenn sich der Speicherinhalt außerhalb normaler Betriebsbedingungen ändert. |   3   | D/V  |

---

## Referenzen

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

