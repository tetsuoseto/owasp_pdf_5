# C7 Modellverhalten, Ausgabe-Steuerung und Sicherheitsgarantie

## Kontrollziel

Modellausgaben müssen strukturiert, zuverlässig, sicher, erklärbar und kontinuierlich in der Produktion überwacht werden. Dies reduziert Halluzinationen, Datenschutzverletzungen, schädliche Inhalte und ungeplante Aktionen, während es das Vertrauen der Nutzer und die Einhaltung von Vorschriften erhöht.

---

## C7.1 Durchsetzung des Ausgabeformats

Strenge Schemata, eingeschränkte Dekodierung und nachgelagerte Validierung verhindern, dass fehlerhafte oder bösartige Inhalte sich verbreiten.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Überprüfen Sie, ob Antwortschemata (z. B. JSON-Schema) im Systemprompt bereitgestellt werden und jede Ausgabe automatisch validiert wird; nicht konforme Ausgaben lösen eine Reparatur oder Ablehnung aus. |   1   | D/V  |
| 7.1.2 | Überprüfen Sie, ob beschränktes Decodieren (Stoppzeichen, reguläre Ausdrücke, maximale Tokenanzahl) aktiviert ist, um Überläufe oder Seiteneffekte durch Prompt-Injektionen zu verhindern.                 |   1   | D/V  |
| 7.1.3 | Stellen Sie sicher, dass nachgelagerte Komponenten Ausgaben als nicht vertrauenswürdig behandeln und sie gegen Schemata oder injektionssichere Deserialisierer validieren.                                 |   2   | D/V  |
| 7.1.4 | Überprüfen Sie, dass Ereignisse mit fehlerhaften Ausgaben protokolliert, ratenbegrenzt und in der Überwachung angezeigt werden.                                                                            |   3   |  V   |

---

## C7.2 Halluzinations-erkennung und -minderung

Unsicherheitsabschätzung und Rückfallstrategien begrenzen erfundene Antworten.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Überprüfen Sie, ob tokenbasierte Log-Wahrscheinlichkeiten, Ensemble-Selbstkonsistenz oder feinabgestimmte Halluzinationsdetektoren jedem Antwort eine Vertrauensbewertung zuweisen.                       |   1   | D/V  |
| 7.2.2 | Überprüfen Sie, ob Antworten unterhalb eines konfigurierbaren Vertrauensschwellenwerts Fallback-Workflows auslösen (z. B. abrufunterstützte Generierung, sekundäres Modell oder menschliche Überprüfung). |   1   | D/V  |
| 7.2.3 | Stellen Sie sicher, dass Halluzinationsvorfälle mit Ursachen-Metadaten gekennzeichnet und an Post-Mortem- sowie Feinabstimmungsprozesse weitergeleitet werden.                                            |   2   | D/V  |
| 7.2.4 | Überprüfen Sie, dass Schwellenwerte und Detektoren nach wesentlichen Aktualisierungen des Modells oder der Wissensbasis neu kalibriert werden.                                                            |   3   | D/V  |
| 7.2.5 | Überprüfen Sie, ob die Dashboard-Visualisierungen die Halluzinationsraten nachverfolgen.                                                                                                                  |   3   |  V   |

---

## C7.3 Ausgabe-Sicherheits- und Datenschutzfilterung

Richtlinienfilter und Red-Team-Abdeckung schützen Benutzer und vertrauliche Daten.

|   #   | Description                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Überprüfen Sie, ob Vor- und Nachgenerations-Klassifikatoren hasserfüllte, belästigende, selbstverletzende, extremistische und sexuell explizite Inhalte, die der Richtlinie entsprechen, blockieren. |   1   | D/V  |
| 7.3.2 | Stellen Sie sicher, dass die Erkennung von PII/PCI und die automatische Schwärzung bei jeder Antwort ausgeführt werden; Verstöße führen zu einem Datenschutzvorfall.                                 |   1   | D/V  |
| 7.3.3 | Überprüfen Sie, ob Vertraulichkeitstags (z. B. Geschäftsgeheimnisse) über Modalitäten hinweg propagiert werden, um Lecks in Text, Bildern oder Code zu verhindern.                                   |   2   |  D   |
| 7.3.4 | Stellen Sie sicher, dass Versuche zur Umgehung von Filtern oder Klassifikationen mit hohem Risiko eine sekundäre Genehmigung oder eine erneute Benutzerauthentifizierung erfordern.                  |   3   | D/V  |
| 7.3.5 | Überprüfen Sie, ob die Filtergrenzwerte die rechtlichen Zuständigkeiten sowie den Kontext von Benutzeralter und -rolle widerspiegeln.                                                                |   3   | D/V  |

---

## C7.4 Ausgabe- und Aktionsbegrenzung

Ratenbegrenzungen und Freigabe-Gates verhindern Missbrauch und übermäßige Autonomie.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Überprüfen Sie, dass die Quoten pro Benutzer und pro API-Schlüssel Anfragen, Token und Kosten mit exponentiellem Back-off bei 429-Fehlern begrenzen.                                                                                        |   1   |  D   |
| 7.4.2 | Überprüfen Sie, dass privilegierte Aktionen (Dateischreibvorgänge, Codeausführung, Netzwerkaufrufe) eine richtlinienbasierte Genehmigung oder eine menschliche Überprüfung erfordern.                                                       |   1   | D/V  |
| 7.4.3 | Überprüfen Sie, dass die Konsistenzprüfungen über verschiedene Modalitäten hinweg sicherstellen, dass Bilder, Code und Text, die für dieselbe Anfrage generiert werden, nicht verwendet werden können, um bösartigen Inhalt einzuschleusen. |   2   | D/V  |
| 7.4.4 | Stellen Sie sicher, dass die Tiefe der Agentendelegation, die Rekursionsgrenzen und die zulässigen Werkzeuglisten explizit konfiguriert sind.                                                                                               |   2   |  D   |
| 7.4.5 | Überprüfen Sie, ob die Überschreitung von Grenzwerten strukturierte Sicherheitsevents für die SIEM-Erfassung auslöst.                                                                                                                       |   3   |  V   |

---

## C7.5 Ausgabeerklärbarkeit

Transparente Signale verbessern das Vertrauen der Nutzer und die interne Fehlersuche.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Stellen Sie sicher, dass benutzerseitige Vertrauenswerte oder kurze Begründungszusammenfassungen bereitgestellt werden, wenn die Risikobewertung dies für angemessen hält. |   2   | D/V  |
| 7.5.2 | Stellen Sie sicher, dass generierte Erklärungen keine sensiblen Systemanweisungen oder proprietären Daten offenbaren.                                                      |   2   | D/V  |
| 7.5.3 | Überprüfen Sie, ob das System Token-basierte Log-Wahrscheinlichkeiten oder Aufmerksamkeitskarten erfasst und diese zur autorisierten Überprüfung speichert.                |   3   |  D   |
| 7.5.4 | Stellen Sie sicher, dass Erklärbarkeitsartefakte neben Modellversionen versioniert werden, um die Nachvollziehbarkeit zu gewährleisten.                                    |   3   |  V   |

---

## C7.6 Überwachungsintegration

Echtzeit-Observabilität schließt den Kreislauf zwischen Entwicklung und Produktion.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Stellen Sie sicher, dass Metriken (Schemaverletzungen, Halluzinationsrate, Toxizität, PII-Lecks, Latenz, Kosten) an eine zentrale Überwachungsplattform übertragen werden. |   1   |  D   |
| 7.6.2 | Überprüfen Sie, ob für jede Sicherheitskennzahl Alarmgrenzwerte mit Eskalationswegen für Einsatzbereitschaft definiert sind.                                               |   1   |  V   |
| 7.6.3 | Überprüfen Sie, ob Dashboards Ausgangsanomalien mit Modell/Version, Feature-Flag und Änderungen der vorgelagerten Daten korrelieren.                                       |   2   |  V   |
| 7.6.4 | Überprüfen Sie, dass Überwachungsdaten in einem dokumentierten MLOps-Workflow in die Nachschulung, Feinabstimmung oder Regelaktualisierungen zurückfließen.                |   2   | D/V  |
| 7.6.5 | Stellen Sie sicher, dass Überwachungspipelines auf Penetration getestet und zugangskontrolliert sind, um das Leckage von sensiblen Protokollen zu vermeiden.               |   3   |  V   |

---

## 7.7 Schutzmaßnahmen für generative Medien

Stellen Sie sicher, dass KI-Systeme keine illegalen, schädlichen oder unautorisierten Medieninhalte erzeugen, indem Sie Richtlinienbeschränkungen, Ausgabeverifizierung und Rückverfolgbarkeit durchsetzen.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Stellen Sie sicher, dass System-Prompts und Benutzeranweisungen ausdrücklich die Erstellung illegaler, schädlicher oder nicht einvernehmlicher Deepfake-Medien (z. B. Bild, Video, Audio) untersagen.                                              |   1   | D/V  |
| 7.7.2 | Überprüfen Sie, ob Eingabeaufforderungen auf Versuche gefiltert werden, Nachahmungen, sexuell explizite Deepfakes oder Medien, die reale Personen ohne deren Zustimmung darstellen, zu erzeugen.                                                   |   2   | D/V  |
| 7.7.3 | Überprüfen Sie, ob das System Perceptual Hashing, Wasserzeichenerkennung oder Fingerprinting verwendet, um die unautorisierte Vervielfältigung urheberrechtlich geschützter Medien zu verhindern.                                                  |   2   |  V   |
| 7.7.4 | Verifizieren Sie, dass alle generierten Medien kryptografisch signiert, mit einem Wasserzeichen versehen oder mit manipulationssicheren Herkunftsmetadaten versehen sind, um eine nachgelagerte Rückverfolgbarkeit zu gewährleisten.               |   3   | D/V  |
| 7.7.5 | Stellen Sie sicher, dass Umgehungsversuche (z. B. Aufforderungsverschleierung, Slang, adversative Formulierungen) erkannt, protokolliert und in ihrer Häufigkeit begrenzt werden; wiederholter Missbrauch wird den Überwachungssystemen angezeigt. |   3   |  V   |

## Referenzen

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

