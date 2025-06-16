# C2 Benutzereingabevalidierung

## Kontrollziel

Robuste Validierung von Benutzereingaben ist eine erste Verteidigungslinie gegen einige der schädlichsten Angriffe auf KI-Systeme. Prompt-Injection-Angriffe können Systemanweisungen überschreiben, sensible Daten offenlegen oder das Modell zu unerlaubtem Verhalten lenken. Sofern keine dedizierten Filter und Anweisungshierarchien vorhanden sind, zeigen Studien, dass „Multi-Shot“-Jailbreaks, die sehr lange Kontextfenster ausnutzen, wirksam sein werden. Auch subtile adversariale Störungsangriffe – wie Homoglyph-Austausch oder Leetspeak – können die Entscheidungen eines Modells unbemerkt verändern.

---

## C2.1 Schutz vor Prompt-Injektion

Prompt-Injektion ist eines der größten Risiken für KI-Systeme. Abwehrmechanismen gegen diese Taktik verwenden eine Kombination aus statischen Musterfiltern, dynamischen Klassifikatoren und der Durchsetzung einer Befehlshierarchie.

|   #   | Description                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Verifizieren Sie, dass Benutzereingaben anhand einer kontinuierlich aktualisierten Bibliothek bekannter Prompt-Injection-Muster (Jailbreak-Schlüsselwörter, „ignorieren Sie vorherige“, Rollenspielketten, indirekte HTML/URL-Angriffe) überprüft werden.           |   1   | D/V  |
| 2.1.2 | Überprüfen Sie, ob das System eine Anweisungs-Hierarchie durchsetzt, bei der System- oder Entwickler-Nachrichten Benutzeranweisungen übersteuern, auch nach einer Erweiterung des Kontextfensters.                                                                  |   1   | D/V  |
| 2.1.3 | Stellen Sie sicher, dass adversarielle Bewertungstests (z. B. Red Team „Many-Shot“-Aufforderungen) vor jeder Veröffentlichung eines Modells oder einer Prompt-Vorlage durchgeführt werden, mit Erfolgsschwellenwerten und automatisierten Sperren für Regressionen. |   2   | D/V  |
| 2.1.4 | Stellen Sie sicher, dass Eingabeaufforderungen, die aus Inhalten Dritter stammen (Webseiten, PDFs, E-Mails), in einem isolierten Parsing-Kontext bereinigt werden, bevor sie in die Hauptaufforderung eingefügt werden.                                             |   2   |  D   |
| 2.1.5 | Stellen Sie sicher, dass alle Aktualisierungen der Prompt-Filterregeln, Versionen der Klassifikator-Modelle und Änderungen der Sperrlisten versioniert und überprüfbar sind.                                                                                        |   3   | D/V  |

---

## C2.2 Widerstandsfähigkeit gegen adversariale Beispiele

Modelle der Verarbeitung natürlicher Sprache (Natural Language Processing, NLP) sind weiterhin anfällig für subtile Störungen auf Zeichen- oder Wortebene, die Menschen oft übersehen, die von den Modellen jedoch häufig falsch klassifiziert werden.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Überprüfen Sie, dass grundlegende Eingabenormalisierungsschritte (Unicode NFC, Homoglyph-Mapping, Kürzen von Leerzeichen) vor der Tokenisierung ausgeführt werden.                                                          |   1   |  D   |
| 2.2.2 | Überprüfen Sie, ob die statistische Anomalieerkennung Eingaben mit ungewöhnlich hoher Editierdistanz zu Sprachnormen, übermäßigen wiederholten Tokens oder abnormen Einbettungsabständen markiert.                          |   2   | D/V  |
| 2.2.3 | Überprüfen Sie, ob die Inferenz-Pipeline optionale, durch adversariales Training gehärtete Modellvarianten oder Verteidigungsschichten (z. B. Randomisierung, defensive Distillation) für Hochrisiko-Endpunkte unterstützt. |   2   |  D   |
| 2.2.4 | Stellen Sie sicher, dass verdächtige adversariale Eingaben isoliert und mit vollständigen Nutzdaten protokolliert werden (nach Entfernung personenbezogener Daten).                                                         |   2   |  V   |
| 2.2.5 | Stellen Sie sicher, dass Robustheitsmetriken (Erfolgsrate bekannter Angriffssätze) im Zeitverlauf verfolgt werden und Regressionen einen Veröffentlichungsstopp auslösen.                                                   |   3   | D/V  |

---

## C2.3 Schema-, Typ- und Längenvalidierung

KI-Angriffe mit fehlerhaften oder übergroßen Eingaben können Parsing-Fehler, Datenlecks über verschiedene Felder hinweg und Ressourcenerschöpfung verursachen. Eine strikte Schemaüberprüfung ist zudem eine Voraussetzung für die Durchführung deterministischer Tool-Aufrufe.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.3.1 | Stellen Sie sicher, dass jeder API- oder Funktionsaufruf-Endpunkt ein explizites Eingabeschema (JSON Schema, Protobuf oder multimodales Äquivalent) definiert und dass die Eingaben vor der Erstellung des Prompts validiert werden. |   1   |  D   |
| 2.3.2 | Überprüfen Sie, dass Eingaben, die die maximalen Token- oder Byte-Grenzen überschreiten, mit einem sicheren Fehler abgelehnt werden und niemals stillschweigend abgeschnitten werden.                                                |   1   | D/V  |
| 2.3.3 | Überprüfen Sie, ob Typprüfungen (z. B. numerische Bereiche, Enum-Werte, MIME-Typen für Bilder/Audio) serverseitig durchgesetzt werden und nicht nur im Client-Code.                                                                  |   2   | D/V  |
| 2.3.4 | Stellen Sie sicher, dass semantische Validatoren (z. B. JSON Schema) in konstanter Zeit ausgeführt werden, um algorithmische DoS-Angriffe zu verhindern.                                                                             |   2   |  D   |
| 2.3.5 | Überprüfen Sie, dass Validierungsfehler mit geschwärzten Nutzlastabschnitten und eindeutigen Fehlercodes protokolliert werden, um die Sicherheitsanalyse zu unterstützen.                                                            |   3   |  V   |

---

## C2.4 Inhalts- und Richtlinienüberprüfung

Entwickler sollten in der Lage sein, syntaktisch gültige Aufforderungen zu erkennen, die nicht erlaubte Inhalte anfordern (wie illegale Anweisungen, Hassrede und urheberrechtlich geschützten Text), und dann verhindern, dass diese verbreitet werden.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Überprüfen Sie, ob ein Inhaltsklassifikator (Zero-Shot oder feinabgestimmt) jede Eingabe bezüglich Gewalt, Selbstverletzung, Hass, sexuelle Inhalte und illegale Anfragen bewertet, mit konfigurierbaren Schwellenwerten. |   1   |  D   |
| 2.4.2 | Stellen Sie sicher, dass Eingaben, die gegen Richtlinien verstoßen, standardisierte Ablehnungen oder sichere Abschlüsse erhalten, damit sie nicht an nachgelagerte LLM-Aufrufe weitergegeben werden.                      |   1   | D/V  |
| 2.4.3 | Überprüfen Sie, dass das Screening-Modell oder Regelwerk mindestens vierteljährlich neu trainiert/aktualisiert wird und dabei neu beobachtete Jailbreak- oder Richtlinienumgehungsmuster berücksichtigt.                  |   2   |  D   |
| 2.4.4 | Überprüfen Sie, ob das Screening benutzerspezifische Richtlinien (Alter, regionale gesetzliche Beschränkungen) mittels attributbasierter Regeln, die zur Anforderungszeit aufgelöst werden, einhält.                      |   2   |  D   |
| 2.4.5 | Stellen Sie sicher, dass die Screening-Protokolle Klassifikatorvertrauenswerte und Richtlinienkategorieschlagwörter für die SOC-Korrelation und die zukünftige Red-Team-Wiedergabe enthalten.                             |   3   |  V   |

---

## C2.5 Eingabe-Ratenbegrenzung und Missbrauchsprävention

Entwickler sollten Missbrauch, Ressourcenerschöpfung und automatisierte Angriffe auf KI-Systeme verhindern, indem sie die Eingaberaten begrenzen und anomale Nutzungsmuster erkennen.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Überprüfen Sie, dass pro Benutzer, pro IP und pro API-Schlüssel Ratenbegrenzungen für alle Eingabeschnittstellen durchgesetzt werden.          |   1   | D/V  |
| 2.5.2 | Stellen Sie sicher, dass Bursts- und Dauer-Datenratenbeschränkungen so eingestellt sind, dass DoS- und Brute-Force-Angriffe verhindert werden. |   2   | D/V  |
| 2.5.3 | Überprüfen Sie, ob anomale Nutzungsmuster (z. B. Schnellfolgerequests, Eingabeflut) automatisierte Sperren oder Eskalationen auslösen.         |   2   | D/V  |
| 2.5.4 | Überprüfen Sie, ob Protokolle zur Missbrauchsprävention aufbewahrt und auf aufkommende Angriffsverhalten überprüft werden.                     |   3   |  V   |

---

## C2.6 Multi-modale Eingabevalidierung

KI-Systeme sollten eine robuste Validierung für nicht-textuelle Eingaben (Bilder, Audio, Dateien) beinhalten, um Injektion, Umgehung oder Ressourcenmissbrauch zu verhindern.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Stellen Sie sicher, dass alle Nicht-Text-Eingaben (Bilder, Audio, Dateien) vor der Verarbeitung auf Typ, Größe und Format überprüft werden. |   1   |  D   |
| 2.6.2 | Stellen Sie sicher, dass Dateien vor der Verarbeitung auf Malware und steganografische Nutzdaten überprüft werden.                          |   2   | D/V  |
| 2.6.3 | Überprüfen Sie, ob Bild-/Audioeingaben auf adversariale Störungen oder bekannte Angriffs­muster untersucht werden.                          |   2   | D/V  |
| 2.6.4 | Überprüfen Sie, ob Multi-Modal-Eingabevalidierungsfehler protokolliert werden und Warnungen zur Untersuchung auslösen.                      |   3   |  V   |

---

## C2.7 Eingangsherkunft & Zuordnung

KI-Systeme sollten Audits, Missbrauchsverfolgung und Compliance unterstützen, indem sie die Herkunft aller Benutzereingaben überwachen und kennzeichnen.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Stellen Sie sicher, dass alle Benutzereingaben bei der Erfassung mit Metadaten (Benutzer-ID, Sitzung, Quelle, Zeitstempel, IP-Adresse) versehen sind.             |   1   | D/V  |
| 2.7.2 | Stellen Sie sicher, dass Provenienz-Metadaten für alle verarbeiteten Eingaben erhalten bleiben und prüfbar sind.                                                  |   2   | D/V  |
| 2.7.3 | Stellen Sie sicher, dass anomale oder nicht vertrauenswürdige Eingabequellen gekennzeichnet und einer verstärkten Überprüfung oder Blockierung unterzogen werden. |   2   | D/V  |

---

## C2.8 Echtzeit-Adaptive Bedrohungserkennung

Entwickler sollten fortschrittliche Bedrohungserkennungssysteme für KI einsetzen, die sich an neue Angriffsmuster anpassen und Echtzeitschutz mit kompiliertem Musterabgleich bieten.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Stellen Sie sicher, dass Bedrohungserkennungsmuster in optimierte Regex-Engines kompiliert werden, um eine leistungsstarke Echtzeitfilterung mit minimaler Latenzauswirkung zu gewährleisten.                               |   1   | D/V  |
| 2.8.2 | Überprüfen Sie, dass Bedrohungserkennungssysteme separate Musterbibliotheken für verschiedene Bedrohungskategorien (Prompt-Injektion, schädliche Inhalte, sensible Daten, Systembefehle) führen.                            |   1   | D/V  |
| 2.8.3 | Stellen Sie sicher, dass die adaptive Bedrohungserkennung maschinelle Lernmodelle verwendet, die die Bedrohungsempfindlichkeit basierend auf der Häufigkeit und Erfolgsrate von Angriffen aktualisieren.                    |   2   | D/V  |
| 2.8.4 | Überprüfen Sie, dass Echtzeit-Bedrohungsinformationsquellen Musterbibliotheken automatisch mit neuen Angriffssignaturen und IOCs (Indikatoren für Kompromittierung) aktualisieren.                                          |   2   | D/V  |
| 2.8.5 | Stellen Sie sicher, dass die Fehlalarmraten bei der Bedrohungserkennung kontinuierlich überwacht werden und die Musterspezifität automatisch angepasst wird, um Interferenzen mit legitimen Anwendungsfällen zu minimieren. |   3   | D/V  |
| 2.8.6 | Stellen Sie sicher, dass die kontextuelle Bedrohungsanalyse die Eingabequelle, das Verhalten der Benutzer und die Sitzungsverlauf berücksichtigt, um die Erkennungsgenauigkeit zu verbessern.                               |   3   | D/V  |
| 2.8.7 | Stellen Sie sicher, dass die Leistungskennzahlen der Bedrohungserkennung (Erkennungsrate, Verarbeitungsverzögerung, Ressourcennutzung) in Echtzeit überwacht und optimiert werden.                                          |   3   | D/V  |

---

## C2.9 Mehrmodale Sicherheitsvalidierungspipeline

Entwickler sollten Sicherheitsvalidierungen für Text-, Bild-, Audio- und andere KI-Eingabemodalitäten mit spezifischen Arten der Bedrohungserkennung und Ressourcentrennung bereitstellen.

|   #   | Description                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.9.1 | Überprüfen Sie, ob jede Eingabemodalität über dedizierte Sicherheitsprüfer mit dokumentierten Bedrohungsmustern (Text: Prompt-Injektion, Bilder: Steganografie, Audio: Spektrogramm-Angriffe) und Erkennungsschwellen verfügt.                                                             |   1   | D/V  |
| 2.9.2 | Stellen Sie sicher, dass multimodale Eingaben in isolierten Sandboxes verarbeitet werden, die definierte Ressourcenbeschränkungen (Speicher, CPU, Verarbeitungszeit) haben, die je nach Modalitätstyp spezifisch sind und in den Sicherheitsrichtlinien dokumentiert werden.               |   2   | D/V  |
| 2.9.3 | Überprüfen Sie, ob die Erkennung von cross-modal Angriffen koordinierte Angriffe über mehrere Eingabetypen hinweg identifiziert (z. B. steganografische Nutzlasten in Bildern kombiniert mit Prompt-Injektionen im Text) mithilfe von Korrelationsregeln und der Erstellung von Warnungen. |   2   | D/V  |
| 2.9.4 | Stellen Sie sicher, dass Validierungsfehler bei Multi-Modalität eine detaillierte Protokollierung auslösen, die alle Eingabemodalitäten, Validierungsergebnisse, Bedrohungsbewertungen und Korrelationsanalysen mit strukturierten Protokollformaten für die SIEM-Integration umfasst.     |   3   | D/V  |
| 2.9.5 | Stellen Sie sicher, dass modalitiespezifische Inhaltsklassifizierer gemäß dokumentierten Zeitplänen (mindestens vierteljährlich) mit neuen Bedrohungsmustern, adversarialen Beispielen und Leistungsbenchmarks, die über den Basisschwellenwerten liegen, aktualisiert werden.             |   3   | D/V  |

---

## Referenzen

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

