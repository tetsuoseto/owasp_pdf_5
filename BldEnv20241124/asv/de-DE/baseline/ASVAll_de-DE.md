## Frontispiz

### Über den Standard

Der Artificial Intelligence Security Verification Standard (AISVS) ist ein gemeinschaftlich entwickelter Katalog von Sicherheitsanforderungen, den Datenwissenschaftler, MLOps-Ingenieure, Softwarearchitekten, Entwickler, Tester, Sicherheitsexperten, Werkzeuganbieter, Regulierungsbehörden und Nutzer verwenden können, um vertrauenswürdige KI-gestützte Systeme und Anwendungen zu entwerfen, zu entwickeln, zu testen und zu verifizieren. Er bietet eine einheitliche Sprache zur Spezifikation von Sicherheitskontrollen über den gesamten KI-Lebenszyklus hinweg – von der Datenerfassung und Modellentwicklung bis hin zur Bereitstellung und laufenden Überwachung –, sodass Organisationen die Widerstandsfähigkeit, den Datenschutz und die Sicherheit ihrer KI-Lösungen messen und verbessern können.

### Urheberrecht und Lizenz

Version 0.1 (Erster öffentlicher Entwurf – Arbeitet sich noch in Arbeit), 2025  

![license](images/license.png)
Urheberrecht © 2025 Das AISVS-Projekt.  

Veröffentlicht unter derCreative Commons Attribution‑ShareAlike 4.0 International License.
Für jegliche Wiederverwendung oder Verbreitung müssen Sie die Lizenzbedingungen dieses Werks klar an andere kommunizieren.

### Projektleiter

Jim Manico
Aras „Russ“ Memisyazici

### Mitwirkende und Gutachter

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS ist ein brandneuer Standard, der speziell entwickelt wurde, um die einzigartigen Sicherheitsherausforderungen von künstlichen Intelligenzsystemen zu adressieren. Während er sich an allgemeineren Sicherheitsbest Practices orientiert, wurde jede Anforderung in AISVS von Grund auf entwickelt, um die Bedrohungslandschaft der KI widerzuspiegeln und Organisationen dabei zu helfen, sicherere und widerstandsfähigere KI-Lösungen zu bauen.

## Vorwort

Willkommen beim Standard zur Sicherheitsüberprüfung Künstlicher Intelligenz (AISVS) Version 1.0!

### Einführung

AISVS wurde 2025 durch eine gemeinschaftliche Zusammenarbeit gegründet und definiert die Sicherheitsanforderungen, die bei der Gestaltung, Entwicklung, Implementierung und dem Betrieb moderner KI-Modelle, Pipelines und KI-gestützter Dienste zu berücksichtigen sind.

AISVS v1.0 stellt die gemeinsame Arbeit der Projektleiter, der Arbeitsgruppe und der breiteren Gemeinschaft von Mitwirkenden dar, um eine pragmatische, überprüfbare Grundlage für die Absicherung von KI-Systemen zu schaffen.

Unser Ziel mit dieser Veröffentlichung ist es, AISVS leicht verständlich und einfach anwendbar zu machen, dabei jedoch konsequent auf seinen definierten Umfang fokussiert zu bleiben und das sich schnell entwickelnde, KI-spezifische Risikoumfeld zu adressieren.

### Hauptziele für AISVS Version 1.0

Version 1.0 wird nach mehreren Leitprinzipien erstellt.

#### Gut definierter Umfang

Jede Anforderung muss mit dem Namen und der Mission von AISVS übereinstimmen:

Künstliche Intelligenz – Kontrollen werden auf der KI/ML-Ebene (Daten, Modell, Pipeline oder Inferenz) durchgeführt und sind die Verantwortung der KI-Anwender.
Sicherheit – Anforderungen mindern direkt erkannte Sicherheits-, Datenschutz- oder Sicherheitsrisiken.
Verifikation – Die Sprache ist so verfasst, dass die Konformität objektiv validiert werden kann.
Standard – Abschnitte folgen einer konsistenten Struktur und Terminologie, um ein zusammenhängendes Referenzwerk zu bilden.
​
---

Durch die Einhaltung von AISVS können Organisationen systematisch die Sicherheitslage ihrer KI-Lösungen bewerten und stärken, wodurch eine Kultur der sicheren KI-Entwicklung gefördert wird.

## Verwendung des AISVS

Der Artificial Intelligence Security Verification Standard (AISVS) definiert Sicherheitsanforderungen für moderne KI-Anwendungen und -Dienstleistungen und konzentriert sich auf Aspekte, die in der Kontrolle der Anwendungsentwickler liegen.

Das AISVS richtet sich an alle, die AI-Anwendungen entwickeln oder deren Sicherheit bewerten, einschließlich Entwickler, Architekten, Sicherheitsexperten und Prüfer. Dieses Kapitel stellt den Aufbau und die Anwendung des AISVS vor, einschließlich seiner Verifikationsstufen und der vorgesehenen Anwendungsfälle.

### Sicherheitsprüfungsstufen für Künstliche Intelligenz

Das AISVS definiert drei aufsteigende Sicherheitsüberprüfungsstufen. Jede Stufe fügt Tiefe und Komplexität hinzu, sodass Organisationen ihre Sicherheitslage an das Risikoniveau ihrer KI-Systeme anpassen können.

Organisationen können auf Stufe 1 beginnen und nach und nach höhere Stufen übernehmen, wenn die Sicherheitsreife und die Bedrohungsexposition zunehmen.

#### Definition der Ebenen

Jede Anforderung in AISVS v1.0 wird einer der folgenden Stufen zugeordnet:

 Anforderungen der Stufe 1

Level 1 umfasst die kritischsten und grundlegendsten Sicherheitsanforderungen. Diese konzentrieren sich darauf, häufige Angriffe zu verhindern, die nicht auf anderen Voraussetzungen oder Schwachstellen basieren. Die meisten Level-1-Kontrollen sind entweder einfach umzusetzen oder ausreichend wichtig, um den Aufwand zu rechtfertigen.

 Anforderungen der Stufe 2

Stufe 2 befasst sich mit fortgeschritteneren oder weniger häufigen Angriffen sowie mit mehrschichtigen Abwehrmaßnahmen gegen weit verbreitete Bedrohungen. Diese Anforderungen können komplexere Logik beinhalten oder auf spezifische Angriffsvoraussetzungen abzielen.

 Anforderungen der Stufe 3

Level 3 umfasst Kontrollen, die typischerweise schwieriger umzusetzen sind oder situativ zur Anwendung kommen. Diese stellen oft Verteidigungsmechanismen in der Tiefe oder Gegenmaßnahmen gegen spezialisierte, gezielte oder hochkomplexe Angriffe dar.

#### Rolle (D/V)

Jede AISVS-Anforderung ist entsprechend der Hauptzielgruppe gekennzeichnet:

D – Entwicklerorientierte Anforderungen
V – Anforderungen für Prüfer/Auditoren
D/V – Relevant sowohl für Entwickler als auch für Prüfer

## C1 Trainingsdaten-Governance und Bias-Management

### Kontrollziel

Trainingsdaten müssen so beschafft, gehandhabt und gepflegt werden, dass Herkunft, Sicherheit, Qualität und Fairness erhalten bleiben. Dies erfüllt rechtliche Verpflichtungen und verringert Risiken von Verzerrungen, Manipulationen oder Datenschutzverletzungen im gesamten KI-Lebenszyklus.

---

### C1.1 Herkunft der Trainingsdaten

Führen Sie ein verifizierbares Inventar aller Datensätze, akzeptieren Sie nur vertrauenswürdige Quellen und protokollieren Sie jede Änderung zur Nachvollziehbarkeit.

 #1.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass ein aktuelles Inventar jeder Trainingsdatenquelle (Herkunft, Verantwortlicher/Eigentümer, Lizenz, Erfassungsmethode, vorgesehene Nutzungseinschränkungen und Verarbeitungshistorie) geführt wird.
 #1.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass nur Datensätze verwendet werden, die auf Qualität, Repräsentativität, ethische Beschaffung und Lizenzkonformität geprüft wurden, um Risiken wie Datenmanipulation, eingebettete Voreingenommenheit und Verletzung geistigen Eigentums zu minimieren.
 #1.1.3    Level: 1    Role: D/V
 Stellen Sie sicher, dass Datenminimierung durchgesetzt wird, sodass unnötige oder sensible Attribute ausgeschlossen sind.
 #1.1.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle Änderungen am Datensatz einem protokollierten Genehmigungsworkflow unterliegen.
 #1.1.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Qualität der Kennzeichnung/Annotation durch Überprüfer-Querprüfungen oder Konsens gewährleistet ist.
 #1.1.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass für bedeutende Trainingsdatensätze „Datakarten“ oder „Datenblätter für Datensätze“ gepflegt werden, die Merkmale, Ziele, Zusammensetzung, Erfassungsprozesse, Vorverarbeitung sowie empfohlene und nicht empfohlene Verwendungszwecke detailliert beschreiben.

---

### C1.2 Sicherheit und Integrität der Trainingsdaten

Zugriff einschränken, Daten im Ruhezustand und während der Übertragung verschlüsseln und die Integrität überprüfen, um Manipulationen oder Diebstahl zu verhindern.

 #1.2.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Zugriffskontrollen Speicher und Pipelines schützen.
 #1.2.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Datensätze während der Übertragung verschlüsselt sind und für alle sensiblen oder personenbezogenen Informationen (PII) auch im Ruhezustand, unter Verwendung von branchenüblichen kryptografischen Algorithmen und Schlüsselverwaltungspraktiken.
 #1.2.3    Level: 2    Role: D/V
 Verifizieren Sie, dass kryptografische Hashes oder digitale Signaturen verwendet werden, um die Datenintegrität während der Speicherung und Übertragung sicherzustellen, und dass automatische Anomalieerkennungstechniken angewendet werden, um unautorisierte Änderungen oder Beschädigungen, einschließlich gezielter Datenvergiftungsversuche, zu verhindern.
 #1.2.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass Datensatzversionen verfolgt werden, um eine Rücksetzung zu ermöglichen.
 #1.2.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass veraltete Daten sicher gelöscht oder anonymisiert werden, um den Richtlinien zur Datenaufbewahrung, gesetzlichen Anforderungen und zur Reduzierung der Angriffsfläche zu entsprechen.

---

### C1.3 Repräsentationsvollständigkeit & Fairness

Erkennen Sie demografische Verzerrungen und wenden Sie Gegenmaßnahmen an, damit die Fehlerraten des Modells über alle Gruppen hinweg gerecht verteilt sind.

 #1.3.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Datensätze auf repräsentative Ungleichgewichte und potenzielle Verzerrungen über gesetzlich geschützte Merkmale (z. B. Rasse, Geschlecht, Alter) sowie andere ethisch sensible Eigenschaften, die für den Anwendungsbereich des Modells relevant sind (z. B. sozioökonomischer Status, Standort), analysiert werden.
 #1.3.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass identifizierte Verzerrungen durch dokumentierte Strategien wie Neu-Ausgleich, gezielte Datenaugmentation, algorithmische Anpassungen (z. B. Vorverarbeitung, Verarbeitung während der Laufzeit, Nachbearbeitung) oder Re-Gewichtung gemindert werden und die Auswirkungen der Minderung sowohl auf Fairness als auch auf die Gesamtleistung des Modells bewertet werden.
 #1.3.3    Level: 2    Role: D/V
 Überprüfen Sie, dass Fairness-Metriken nach dem Training bewertet und dokumentiert werden.
 #1.3.4    Level: 3    Role: D/V
 Überprüfen Sie, ob eine Richtlinie zur Verwaltung von Lebenszyklus-Bias Eigentümer und Überprüfungsrhythmen zuweist.

---

### C1.4 Qualität, Integrität und Sicherheit der Beschriftung von Trainingsdaten

Schützen Sie Labels mit Verschlüsselung und verlangen Sie eine doppelte Überprüfung für kritische Klassen.

 #1.4.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Qualität der Kennzeichnung/Annotation durch klare Richtlinien, wechselseitige Überprüfungen der Gutachter, Konsensmechanismen (z. B. Überwachung der Übereinstimmung zwischen den Annotatoren) und festgelegte Prozesse zur Behebung von Diskrepanzen gewährleistet ist.
 #1.4.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass kryptografische Hashes oder digitale Signaturen auf Label-Artefakte angewendet werden, um deren Integrität und Authentizität zu gewährleisten.
 #1.4.3    Level: 2    Role: D/V
 Überprüfen Sie, dass Labeling-Schnittstellen und -Plattformen starke Zugriffskontrollen durchsetzen, manipulationssichere Auditprotokolle aller Labeling-Aktivitäten führen und vor unbefugten Änderungen schützen.
 #1.4.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass für die Sicherheit, den Schutz oder die Fairness entscheidende Kennzeichnungen (z. B. die Identifizierung toxischer Inhalte, kritischer medizinischer Befunde) einer obligatorischen unabhängigen Doppelüberprüfung oder einer gleichwertig robusten Verifikation unterzogen werden.
 #1.4.5    Level: 2    Role: D/V
 Verifizieren Sie, dass sensible Informationen (einschließlich personenbezogener Daten) – die versehentlich erfasst oder notwendigerweise in Labels vorhanden sind – gemäß den Prinzipien der Datenminimierung im Ruhezustand und während der Übertragung geschwärzt, pseudonymisiert, anonymisiert oder verschlüsselt werden.
 #1.4.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Kennzeichnungsrichtlinien und Anweisungen umfassend, versioniert und von Fachkollegen überprüft sind.
 #1.4.7    Level: 2    Role: D/V
 Stellen Sie sicher, dass Datenschemata (einschließlich für Labels) klar definiert und versioniert sind.
 #1.8.2    Level: 2    Role: D/V
 Überprüfen Sie, ob ausgelagerte oder durch Crowdsourcing organisierte Kennzeichnungsabläufe technische und verfahrensmäßige Schutzmaßnahmen enthalten, um die Vertraulichkeit und Integrität der Daten, die Qualität der Kennzeichnungen zu gewährleisten und Datenlecks zu verhindern.

---

### C1.5 Qualitätssicherung der Trainingsdaten

Kombinieren Sie automatisierte Validierung, manuelle Stichprobenprüfungen und protokollierte Fehlerbehebungen, um die Zuverlässigkeit des Datensatzes zu gewährleisten.

 #1.5.1    Level: 1    Role: D
 Stellen Sie sicher, dass automatisierte Tests bei jedem Import oder jeder signifikanten Transformation Formatfehler, Nullwerte und Label-Verschiebungen erfassen.
 #1.5.2    Level: 1    Role: D/V
 Verifizieren Sie, dass fehlgeschlagene Datensätze mit Prüfpfaden unter Quarantäne gestellt werden.
 #1.5.3    Level: 2    Role: V
 Stellen Sie sicher, dass manuelle Stichprobenprüfungen durch Fachexperten eine statistisch signifikante Stichprobe abdecken (z. B. ≥1 % oder 1.000 Stichproben, je nachdem, welcher Wert größer ist, oder wie durch die Risikobewertung festgelegt), um subtile Qualitätsprobleme zu identifizieren, die von der Automatisierung nicht erfasst werden.
 #1.5.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Maßnahmen zur Behebung an Herkunftsdaten angehängt werden.
 #1.5.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Qualitätsprüfungen minderwertige Datensätze blockieren, es sei denn, Ausnahmen sind genehmigt.

---

### C1.6 Erkennung von Data Poisoning

Wenden Sie statistische Anomalieerkennung und Quarantäne-Workflows an, um feindliche Einfügungen zu stoppen.

 #1.6.1    Level: 2    Role: D/V
 Verifizieren Sie, dass Anomalieerkennungstechniken (z. B. statistische Methoden, Ausreißererkennung, Einbettungsanalyse) auf die Trainingsdaten bei der Erfassung und vor größeren Trainingsläufen angewendet werden, um mögliche Vergiftungsangriffe oder unbeabsichtigte Datenkorruption zu identifizieren.
 #1.6.2    Level: 2    Role: D/V
 Überprüfen Sie, ob markierte Proben vor dem Training eine manuelle Überprüfung auslösen.
 #1.6.3    Level: 2    Role: V
 Überprüfen Sie, ob die Ergebnisse das Sicherheitsdossier des Modells einspeisen und die fortlaufende Bedrohungsaufklärung informieren.
 #1.6.4    Level: 3    Role: D/V
 Überprüfen Sie, ob die Erkennungslogik mit neuen Bedrohungsinformationen aktualisiert wurde.
 #1.6.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Online-Lernpipelines die Verteilungsschwankungen überwachen.
 #1.6.6    Level: 3    Role: D/V
 Stellen Sie sicher, dass spezifische Abwehrmaßnahmen gegen bekannte Arten von Datenvergiftungsangriffen (z. B. Label-Flipping, Einfügen von Backdoor-Triggern, Angriffe durch einflussreiche Instanzen) entsprechend dem Risikoprofil des Systems und den Datenquellen berücksichtigt und umgesetzt werden.

---

### C1.7 Benutzer-Datenlöschung und Durchsetzung der Einwilligung

Respektieren Sie Löschungs- und Widerrufsanfragen über Datensätze, Backups und abgeleitete Artefakte hinweg.

 #1.7.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Löscharbeitsabläufe primäre und abgeleitete Daten löschen und die Auswirkung auf das Modell bewerten, sowie dass die Auswirkungen auf betroffene Modelle bewertet und gegebenenfalls behoben werden (z. B. durch erneutes Training oder Rekalibrierung).
 #1.7.2    Level: 2    Role: D
 Stellen Sie sicher, dass Mechanismen vorhanden sind, um den Umfang und den Status der Zustimmung des Nutzers (und deren Widerrufe) für verwendete Trainingsdaten nachzuverfolgen und zu respektieren, und dass die Zustimmung validiert wird, bevor Daten in neue Trainingsprozesse oder bedeutende Modellaktualisierungen einfließen.
 #1.7.3    Level: 2    Role: V
 Überprüfen Sie, dass Workflows jährlich getestet und protokolliert werden.

---

### C1.8 Sicherheit der Lieferkette

Prüfen Sie externe Datenanbieter und verifizieren Sie die Integrität über authentifizierte, verschlüsselte Kanäle.

 #1.8.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass Drittanbieter von Daten, einschließlich Anbieter vortrainierter Modelle und externer Datensätze, eine Sicherheits-, Datenschutz-, ethische Herkunfts- und Datenqualitätsprüfung durchlaufen, bevor deren Daten oder Modelle integriert werden.
 #1.8.2    Level: 1    Role: D
 Überprüfen Sie, dass externe Übertragungen TLS/Authentifizierung und Integritätsprüfungen verwenden.
 #1.8.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Datenquellen mit hohem Risiko (z. B. Open-Source-Datensätze mit unbekannter Herkunft, nicht geprüfte Anbieter) einer verstärkten Überprüfung unterzogen werden, wie etwa isolierter Analyse in einer Sandbox, umfassenden Qualitäts- und Bias-Prüfungen sowie gezielter Erkennung von Datenvergiftungen, bevor sie in sensiblen Anwendungen verwendet werden.
 #1.8.4    Level: 3    Role: D/V
 Überprüfen Sie, ob vortrainierte Modelle, die von Dritten stammen, auf eingebettete Vorurteile, potenzielle Hintertüren, die Integrität ihrer Architektur und die Herkunft ihrer ursprünglichen Trainingsdaten bewertet werden, bevor sie feinabgestimmt oder eingesetzt werden.

---

### C1.9 Erkennung adversarialer Beispiele

Implementieren Sie während der Trainingsphase Maßnahmen wie adversariales Training, um die Widerstandsfähigkeit des Modells gegen adversariale Beispiele zu erhöhen.

 #1.9.1    Level: 3    Role: D/V
 Stellen Sie sicher, dass geeignete Abwehrmaßnahmen wie adversariales Training (unter Verwendung generierter adversarialer Beispiele), Datenaugmentation mit veränderten Eingaben oder robuste Optimierungstechniken implementiert und entsprechend der Risikobewertung für relevante Modelle angepasst werden.
 #1.9.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass bei Verwendung von adversarialem Training die Erstellung, Verwaltung und Versionierung von adversarialen Datensätzen dokumentiert und kontrolliert wird.
 #1.9.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Auswirkungen des Trainings zur adversarialen Robustheit auf die Modellleistung (sowohl bei sauberen als auch bei adversarialen Eingaben) und Fairness-Metriken bewertet, dokumentiert und überwacht werden.
 #1.9.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass Strategien für adversariales Training und Robustheit regelmäßig überprüft und aktualisiert werden, um sich entwickelnden adversarialen Angriffstechniken entgegenzuwirken.

---

### C1.10 Datenherkunft und Rückverfolgbarkeit

Verfolgen Sie die gesamte Reise jedes einzelnen Datenpunkts von der Quelle bis zum Modelleingang zur Nachvollziehbarkeit und für Reaktionsmaßnahmen bei Vorfällen.

 #1.10.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Herkunft jedes Datenpunkts, einschließlich aller Transformationen, Ergänzungen und Zusammenführungen, aufgezeichnet und rekonstruiert werden kann.
 #1.10.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Herkunftsdaten unveränderlich, sicher gespeichert und für Audits oder Untersuchungen zugänglich sind.
 #1.10.3    Level: 2    Role: D/V
 Überprüfen Sie, dass die Nachverfolgung der Herkunft sowohl Rohdaten als auch synthetische Daten abdeckt.

---

### C1.11 Verwaltung synthetischer Daten

Stellen Sie sicher, dass synthetische Daten ordnungsgemäß verwaltet, gekennzeichnet und einer Risikoanalyse unterzogen werden.

 #1.11.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle synthetischen Daten im gesamten Prozess klar gekennzeichnet und von echten Daten unterscheidbar sind.
 #1.11.2    Level: 2    Role: D/V
 Überprüfen Sie, ob der Generierungsprozess, die Parameter und die beabsichtigte Verwendung der synthetischen Daten dokumentiert sind.
 #1.11.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass synthetische Daten vor der Verwendung im Training auf Bias, Datenschutzverletzungen und Repräsentationsprobleme risikobewertet werden.

---

### C1.12 Datenzugriffsüberwachung & Anomalieerkennung

Überwachen und Alarmieren bei ungewöhnlichem Zugriff auf Trainingsdaten, um Insider-Bedrohungen oder Datenexfiltration zu erkennen.

 #1.12.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle Zugriffe auf Trainingsdaten protokolliert werden, einschließlich Benutzer, Zeit und Aktion.
 #1.12.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Zugriffprotokolle regelmäßig auf ungewöhnliche Muster überprüft werden, wie beispielsweise große Exporte oder Zugriffe von neuen Standorten.
 #1.12.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Warnungen für verdächtige Zugriffsereignisse generiert und umgehend untersucht werden.

---

### C1.13 Datenaufbewahrungs- und Ablaufrichtlinien

Definieren und Durchsetzen von Datenaufbewahrungsfristen, um unnötige Datenspeicherung zu minimieren.

 #1.13.1    Level: 1    Role: D/V
 Überprüfen Sie, ob für alle Trainingsdatensätze explizite Aufbewahrungsfristen definiert sind.
 #1.13.2    Level: 2    Role: D/V
 Überprüfen Sie, ob Datensätze am Ende ihres Lebenszyklus automatisch ablaufen, gelöscht oder zur Löschung überprüft werden.
 #1.13.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Aufbewahrungs- und Löschvorgänge protokolliert und auditierbar sind.

---

### C1.14 Regulierung & Zuständigkeitskonformität

Stellen Sie sicher, dass alle Trainingsdaten den geltenden Gesetzen und Vorschriften entsprechen.

 #1.14.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass Anforderungen an den Datenresidenzstandort und grenzüberschreitende Datenübertragungen für alle Datensätze identifiziert und durchgesetzt werden.
 #1.14.2    Level: 2    Role: D/V
 Überprüfen Sie, ob branchenspezifische Vorschriften (z. B. Gesundheitswesen, Finanzen) bei der Datenverarbeitung erkannt und berücksichtigt werden.
 #1.14.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Einhaltung relevanter Datenschutzgesetze (z. B. DSGVO, CCPA) dokumentiert ist und regelmäßig überprüft wird.

---

### C1.15 Daten-Wasserzeichen & Fingerprinting

Erkennen Sie unautorisierte Wiederverwendung oder Weitergabe proprietärer oder sensibler Daten.

 #1.15.1    Level: 3    Role: D/V
 Stellen Sie sicher, dass Datensätze oder Teilmengen dort, wo möglich, mit Wasserzeichen oder Fingerabdrücken versehen sind.
 #1.15.2    Level: 3    Role: D/V
 Stellen Sie sicher, dass Wasserzeichen- und Fingerprinting-Methoden keine Verzerrungen oder Datenschutzrisiken verursachen.
 #1.15.3    Level: 3    Role: D/V
 Überprüfen Sie, ob regelmäßige Kontrollen durchgeführt werden, um eine unautorisierte Wiederverwendung oder das Auslaufen von mit Wasserzeichen versehenen Daten zu erkennen.

---

### C1.16 Verwaltung der Rechte der betroffenen Personen

Unterstützung der Rechte betroffener Personen wie Zugriff, Berichtigung, Einschränkung und Widerspruch.

 #1.16.1    Level: 2    Role: D/V
 Verifizieren Sie, dass Mechanismen vorhanden sind, um Anfragen von betroffenen Personen auf Zugang, Berichtigung, Einschränkung oder Widerspruch zu beantworten.
 #1.16.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Anfragen protokolliert, verfolgt und innerhalb der gesetzlich vorgeschriebenen Fristen erfüllt werden.
 #1.16.3    Level: 2    Role: D/V
 Überprüfen Sie, dass die Prozesse zur Wahrung der Rechte der betroffenen Personen regelmäßig auf ihre Wirksamkeit getestet und überprüft werden.

---

### C1.17 Analyse der Auswirkungen von Datensatzversionen

Bewerten Sie die Auswirkungen von Datensatzänderungen, bevor Sie Versionen aktualisieren oder ersetzen.

 #1.17.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass vor der Aktualisierung oder dem Ersatz einer Datensatzversion eine Auswirkungsanalyse durchgeführt wird, die die Modellleistung, Fairness und Compliance abdeckt.
 #1.17.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Ergebnisse der Auswirkungsanalyse dokumentiert und von den relevanten Stakeholdern überprüft werden.
 #1.17.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Rücksetzpläne vorhanden sind, falls neue Versionen inakzeptable Risiken oder Rückschritte einführen.

---

### C1.18 Sicherheit der Datenannotatoren-Mitarbeiter

Gewährleisten Sie die Sicherheit und Integrität des Personals, das an der Datenannotation beteiligt ist.

 #1.18.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle an der Datenannotation beteiligten Personen einer Hintergrundüberprüfung unterzogen und in Datensicherheit und Datenschutz geschult sind.
 #1.18.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle Annotationsmitarbeiter Vertraulichkeits- und Geheimhaltungsvereinbarungen unterschreiben.
 #1.18.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Annotationsplattformen Zugriffskontrollen durchsetzen und auf Insider-Bedrohungen überwachen.

---

### Quellenangaben

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## C2 Benutzereingabevalidierung

### Kontrollziel

Robuste Validierung von Benutzereingaben ist eine erste Verteidigungslinie gegen einige der schädlichsten Angriffe auf KI-Systeme. Prompt-Injection-Angriffe können Systemanweisungen überschreiben, sensible Daten offenlegen oder das Modell zu unerlaubtem Verhalten lenken. Sofern keine dedizierten Filter und Anweisungshierarchien vorhanden sind, zeigen Studien, dass „Multi-Shot“-Jailbreaks, die sehr lange Kontextfenster ausnutzen, wirksam sein werden. Auch subtile adversariale Störungsangriffe – wie Homoglyph-Austausch oder Leetspeak – können die Entscheidungen eines Modells unbemerkt verändern.

---

### C2.1 Schutz vor Prompt-Injektion

Prompt-Injektion ist eines der größten Risiken für KI-Systeme. Abwehrmechanismen gegen diese Taktik verwenden eine Kombination aus statischen Musterfiltern, dynamischen Klassifikatoren und der Durchsetzung einer Befehlshierarchie.

 #2.1.1    Level: 1    Role: D/V
 Verifizieren Sie, dass Benutzereingaben anhand einer kontinuierlich aktualisierten Bibliothek bekannter Prompt-Injection-Muster (Jailbreak-Schlüsselwörter, „ignorieren Sie vorherige“, Rollenspielketten, indirekte HTML/URL-Angriffe) überprüft werden.
 #2.1.2    Level: 1    Role: D/V
 Überprüfen Sie, ob das System eine Anweisungs-Hierarchie durchsetzt, bei der System- oder Entwickler-Nachrichten Benutzeranweisungen übersteuern, auch nach einer Erweiterung des Kontextfensters.
 #2.1.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass adversarielle Bewertungstests (z. B. Red Team „Many-Shot“-Aufforderungen) vor jeder Veröffentlichung eines Modells oder einer Prompt-Vorlage durchgeführt werden, mit Erfolgsschwellenwerten und automatisierten Sperren für Regressionen.
 #2.1.4    Level: 2    Role: D
 Stellen Sie sicher, dass Eingabeaufforderungen, die aus Inhalten Dritter stammen (Webseiten, PDFs, E-Mails), in einem isolierten Parsing-Kontext bereinigt werden, bevor sie in die Hauptaufforderung eingefügt werden.
 #2.1.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass alle Aktualisierungen der Prompt-Filterregeln, Versionen der Klassifikator-Modelle und Änderungen der Sperrlisten versioniert und überprüfbar sind.

---

### C2.2 Widerstandsfähigkeit gegen adversariale Beispiele

Modelle der Verarbeitung natürlicher Sprache (Natural Language Processing, NLP) sind weiterhin anfällig für subtile Störungen auf Zeichen- oder Wortebene, die Menschen oft übersehen, die von den Modellen jedoch häufig falsch klassifiziert werden.

 #2.2.1    Level: 1    Role: D
 Überprüfen Sie, dass grundlegende Eingabenormalisierungsschritte (Unicode NFC, Homoglyph-Mapping, Kürzen von Leerzeichen) vor der Tokenisierung ausgeführt werden.
 #2.2.2    Level: 2    Role: D/V
 Überprüfen Sie, ob die statistische Anomalieerkennung Eingaben mit ungewöhnlich hoher Editierdistanz zu Sprachnormen, übermäßigen wiederholten Tokens oder abnormen Einbettungsabständen markiert.
 #2.2.3    Level: 2    Role: D
 Überprüfen Sie, ob die Inferenz-Pipeline optionale, durch adversariales Training gehärtete Modellvarianten oder Verteidigungsschichten (z. B. Randomisierung, defensive Distillation) für Hochrisiko-Endpunkte unterstützt.
 #2.2.4    Level: 2    Role: V
 Stellen Sie sicher, dass verdächtige adversariale Eingaben isoliert und mit vollständigen Nutzdaten protokolliert werden (nach Entfernung personenbezogener Daten).
 #2.2.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Robustheitsmetriken (Erfolgsrate bekannter Angriffssätze) im Zeitverlauf verfolgt werden und Regressionen einen Veröffentlichungsstopp auslösen.

---

### C2.3 Schema-, Typ- und Längenvalidierung

KI-Angriffe mit fehlerhaften oder übergroßen Eingaben können Parsing-Fehler, Datenlecks über verschiedene Felder hinweg und Ressourcenerschöpfung verursachen. Eine strikte Schemaüberprüfung ist zudem eine Voraussetzung für die Durchführung deterministischer Tool-Aufrufe.

 #2.3.1    Level: 1    Role: D
 Stellen Sie sicher, dass jeder API- oder Funktionsaufruf-Endpunkt ein explizites Eingabeschema (JSON Schema, Protobuf oder multimodales Äquivalent) definiert und dass die Eingaben vor der Erstellung des Prompts validiert werden.
 #2.3.2    Level: 1    Role: D/V
 Überprüfen Sie, dass Eingaben, die die maximalen Token- oder Byte-Grenzen überschreiten, mit einem sicheren Fehler abgelehnt werden und niemals stillschweigend abgeschnitten werden.
 #2.3.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Typprüfungen (z. B. numerische Bereiche, Enum-Werte, MIME-Typen für Bilder/Audio) serverseitig durchgesetzt werden und nicht nur im Client-Code.
 #2.3.4    Level: 2    Role: D
 Stellen Sie sicher, dass semantische Validatoren (z. B. JSON Schema) in konstanter Zeit ausgeführt werden, um algorithmische DoS-Angriffe zu verhindern.
 #2.3.5    Level: 3    Role: V
 Überprüfen Sie, dass Validierungsfehler mit geschwärzten Nutzlastabschnitten und eindeutigen Fehlercodes protokolliert werden, um die Sicherheitsanalyse zu unterstützen.

---

### C2.4 Inhalts- und Richtlinienüberprüfung

Entwickler sollten in der Lage sein, syntaktisch gültige Aufforderungen zu erkennen, die nicht erlaubte Inhalte anfordern (wie illegale Anweisungen, Hassrede und urheberrechtlich geschützten Text), und dann verhindern, dass diese verbreitet werden.

 #2.4.1    Level: 1    Role: D
 Überprüfen Sie, ob ein Inhaltsklassifikator (Zero-Shot oder feinabgestimmt) jede Eingabe bezüglich Gewalt, Selbstverletzung, Hass, sexuelle Inhalte und illegale Anfragen bewertet, mit konfigurierbaren Schwellenwerten.
 #2.4.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Eingaben, die gegen Richtlinien verstoßen, standardisierte Ablehnungen oder sichere Abschlüsse erhalten, damit sie nicht an nachgelagerte LLM-Aufrufe weitergegeben werden.
 #2.4.3    Level: 2    Role: D
 Überprüfen Sie, dass das Screening-Modell oder Regelwerk mindestens vierteljährlich neu trainiert/aktualisiert wird und dabei neu beobachtete Jailbreak- oder Richtlinienumgehungsmuster berücksichtigt.
 #2.4.4    Level: 2    Role: D
 Überprüfen Sie, ob das Screening benutzerspezifische Richtlinien (Alter, regionale gesetzliche Beschränkungen) mittels attributbasierter Regeln, die zur Anforderungszeit aufgelöst werden, einhält.
 #2.4.5    Level: 3    Role: V
 Stellen Sie sicher, dass die Screening-Protokolle Klassifikatorvertrauenswerte und Richtlinienkategorieschlagwörter für die SOC-Korrelation und die zukünftige Red-Team-Wiedergabe enthalten.

---

### C2.5 Eingabe-Ratenbegrenzung und Missbrauchsprävention

Entwickler sollten Missbrauch, Ressourcenerschöpfung und automatisierte Angriffe auf KI-Systeme verhindern, indem sie die Eingaberaten begrenzen und anomale Nutzungsmuster erkennen.

 #2.5.1    Level: 1    Role: D/V
 Überprüfen Sie, dass pro Benutzer, pro IP und pro API-Schlüssel Ratenbegrenzungen für alle Eingabeschnittstellen durchgesetzt werden.
 #2.5.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Bursts- und Dauer-Datenratenbeschränkungen so eingestellt sind, dass DoS- und Brute-Force-Angriffe verhindert werden.
 #2.5.3    Level: 2    Role: D/V
 Überprüfen Sie, ob anomale Nutzungsmuster (z. B. Schnellfolgerequests, Eingabeflut) automatisierte Sperren oder Eskalationen auslösen.
 #2.5.4    Level: 3    Role: V
 Überprüfen Sie, ob Protokolle zur Missbrauchsprävention aufbewahrt und auf aufkommende Angriffsverhalten überprüft werden.

---

### C2.6 Multi-modale Eingabevalidierung

KI-Systeme sollten eine robuste Validierung für nicht-textuelle Eingaben (Bilder, Audio, Dateien) beinhalten, um Injektion, Umgehung oder Ressourcenmissbrauch zu verhindern.

 #2.6.1    Level: 1    Role: D
 Stellen Sie sicher, dass alle Nicht-Text-Eingaben (Bilder, Audio, Dateien) vor der Verarbeitung auf Typ, Größe und Format überprüft werden.
 #2.6.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Dateien vor der Verarbeitung auf Malware und steganografische Nutzdaten überprüft werden.
 #2.6.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Bild-/Audioeingaben auf adversariale Störungen oder bekannte Angriffs­muster untersucht werden.
 #2.6.4    Level: 3    Role: V
 Überprüfen Sie, ob Multi-Modal-Eingabevalidierungsfehler protokolliert werden und Warnungen zur Untersuchung auslösen.

---

### C2.7 Eingangsherkunft & Zuordnung

KI-Systeme sollten Audits, Missbrauchsverfolgung und Compliance unterstützen, indem sie die Herkunft aller Benutzereingaben überwachen und kennzeichnen.

 #2.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle Benutzereingaben bei der Erfassung mit Metadaten (Benutzer-ID, Sitzung, Quelle, Zeitstempel, IP-Adresse) versehen sind.
 #2.7.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Provenienz-Metadaten für alle verarbeiteten Eingaben erhalten bleiben und prüfbar sind.
 #2.7.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass anomale oder nicht vertrauenswürdige Eingabequellen gekennzeichnet und einer verstärkten Überprüfung oder Blockierung unterzogen werden.

---

### C2.8 Echtzeit-Adaptive Bedrohungserkennung

Entwickler sollten fortschrittliche Bedrohungserkennungssysteme für KI einsetzen, die sich an neue Angriffsmuster anpassen und Echtzeitschutz mit kompiliertem Musterabgleich bieten.

 #2.8.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Bedrohungserkennungsmuster in optimierte Regex-Engines kompiliert werden, um eine leistungsstarke Echtzeitfilterung mit minimaler Latenzauswirkung zu gewährleisten.
 #2.8.2    Level: 1    Role: D/V
 Überprüfen Sie, dass Bedrohungserkennungssysteme separate Musterbibliotheken für verschiedene Bedrohungskategorien (Prompt-Injektion, schädliche Inhalte, sensible Daten, Systembefehle) führen.
 #2.8.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die adaptive Bedrohungserkennung maschinelle Lernmodelle verwendet, die die Bedrohungsempfindlichkeit basierend auf der Häufigkeit und Erfolgsrate von Angriffen aktualisieren.
 #2.8.4    Level: 2    Role: D/V
 Überprüfen Sie, dass Echtzeit-Bedrohungsinformationsquellen Musterbibliotheken automatisch mit neuen Angriffssignaturen und IOCs (Indikatoren für Kompromittierung) aktualisieren.
 #2.8.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Fehlalarmraten bei der Bedrohungserkennung kontinuierlich überwacht werden und die Musterspezifität automatisch angepasst wird, um Interferenzen mit legitimen Anwendungsfällen zu minimieren.
 #2.8.6    Level: 3    Role: D/V
 Stellen Sie sicher, dass die kontextuelle Bedrohungsanalyse die Eingabequelle, das Verhalten der Benutzer und die Sitzungsverlauf berücksichtigt, um die Erkennungsgenauigkeit zu verbessern.
 #2.8.7    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Leistungskennzahlen der Bedrohungserkennung (Erkennungsrate, Verarbeitungsverzögerung, Ressourcennutzung) in Echtzeit überwacht und optimiert werden.

---

### C2.9 Mehrmodale Sicherheitsvalidierungspipeline

Entwickler sollten Sicherheitsvalidierungen für Text-, Bild-, Audio- und andere KI-Eingabemodalitäten mit spezifischen Arten der Bedrohungserkennung und Ressourcentrennung bereitstellen.

 #2.9.1    Level: 1    Role: D/V
 Überprüfen Sie, ob jede Eingabemodalität über dedizierte Sicherheitsprüfer mit dokumentierten Bedrohungsmustern (Text: Prompt-Injektion, Bilder: Steganografie, Audio: Spektrogramm-Angriffe) und Erkennungsschwellen verfügt.
 #2.9.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass multimodale Eingaben in isolierten Sandboxes verarbeitet werden, die definierte Ressourcenbeschränkungen (Speicher, CPU, Verarbeitungszeit) haben, die je nach Modalitätstyp spezifisch sind und in den Sicherheitsrichtlinien dokumentiert werden.
 #2.9.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die Erkennung von cross-modal Angriffen koordinierte Angriffe über mehrere Eingabetypen hinweg identifiziert (z. B. steganografische Nutzlasten in Bildern kombiniert mit Prompt-Injektionen im Text) mithilfe von Korrelationsregeln und der Erstellung von Warnungen.
 #2.9.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass Validierungsfehler bei Multi-Modalität eine detaillierte Protokollierung auslösen, die alle Eingabemodalitäten, Validierungsergebnisse, Bedrohungsbewertungen und Korrelationsanalysen mit strukturierten Protokollformaten für die SIEM-Integration umfasst.
 #2.9.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass modalitiespezifische Inhaltsklassifizierer gemäß dokumentierten Zeitplänen (mindestens vierteljährlich) mit neuen Bedrohungsmustern, adversarialen Beispielen und Leistungsbenchmarks, die über den Basisschwellenwerten liegen, aktualisiert werden.

---

### Referenzen

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## C3 Modell-Lifecycle-Management und Änderungssteuerung

### Kontrollziel

KI-Systeme müssen Prozess zur Änderungssteuerung implementieren, die verhindern, dass unautorisierte oder unsichere Modelländerungen in die Produktion gelangen. Diese Kontrolle gewährleistet die Integrität des Modells während des gesamten Lebenszyklus – von der Entwicklung über die Bereitstellung bis zur Außerbetriebnahme – und ermöglicht eine schnelle Reaktion auf Vorfälle sowie die Nachverfolgbarkeit aller Änderungen.

Kernziel der Sicherheit: Nur autorisierte, validierte Modelle gelangen durch kontrollierte Prozesse, die Integrität, Rückverfolgbarkeit und Wiederherstellbarkeit gewährleisten, in die Produktion.

---

### C3.1 Modellautorisierung & Integrität

Nur autorisierte Modelle mit überprüfter Integrität gelangen in Produktionsumgebungen.

 #3.1.1    Level: 1    Role: D/V
 Überprüfen Sie, ob alle Modellartefakte (Gewichte, Konfigurationen, Tokenizer) vor der Bereitstellung kryptografisch von autorisierten Stellen signiert sind.
 #3.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Modellintegrität zum Zeitpunkt der Bereitstellung validiert wird und Signaturprüfungsfehler das Laden des Modells verhindern.
 #3.1.3    Level: 2    Role: D/V
 Überprüfen Sie, dass die Herkunftsnachweise des Modells die Identität der autorisierenden Instanz, Prüfsummen der Trainingsdaten, Validierungsergebnisse mit Bestehen/Nichtbestehen-Status sowie einen Erstellungszeitstempel enthalten.
 #3.1.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle Modell-Artefakte die semantische Versionsnummerierung (MAJOR.MINOR.PATCH) verwenden, mit dokumentierten Kriterien, die angeben, wann jede Versionskomponente erhöht wird.
 #3.1.5    Level: 2    Role: V
 Überprüfen Sie, ob die Abhängigkeitsverfolgung eine Echtzeit-Inventarisierung aufrechterhält, die eine schnelle Identifizierung aller verbrauchenden Systeme ermöglicht.

---

### C3.2 Modellvalidierung und -prüfung

Modelle müssen vor der Bereitstellung definierte Sicherheits- und Schutzvalidierungen bestehen.

 #3.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Modelle automatisierten Sicherheitstests unterzogen werden, die Eingabevalidierung, Ausgabe-Sanitierung und Sicherheitsbewertungen mit vorher vereinbarten unternehmensinternen Bestehens-/Nichtbestehensgrenzen vor der Bereitstellung umfassen.
 #3.2.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Validierungsfehler den Modelldeployment nach einer ausdrücklichen Überschreibungsfreigabe von vorab bestimmten autorisierten Personen mit dokumentierten geschäftlichen Begründungen automatisch blockieren.
 #3.2.3    Level: 2    Role: V
 Verifizieren Sie, dass die Testergebnisse kryptografisch signiert und unwiderruflich mit dem Hash der spezifischen Modellversion, die validiert wird, verknüpft sind.
 #3.2.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Notfalleinsätze eine dokumentierte Sicherheitsrisikobewertung und die Genehmigung durch eine vorher festgelegte Sicherheitsbehörde innerhalb vorab vereinbarter Zeitrahmen erfordern.

---

### C3.3 Kontrollierte Bereitstellung & Rückrollverfahren

Modellbereitstellungen müssen kontrolliert, überwacht und reversibel sein.

 #3.3.1    Level: 1    Role: D
 Stellen Sie sicher, dass Produktionsbereitstellungen schrittweise Rollout-Mechanismen (Canary-Deployments, Blue-Green-Deployments) mit automatisierten Rollback-Auslösern basierend auf vorab vereinbarten Fehlerraten, Latenzschwellen oder Sicherheitsalarmkriterien implementieren.
 #3.3.2    Level: 1    Role: D/V
 Überprüfen Sie, ob Rollback-Funktionen den vollständigen Modellzustand (Gewichte, Konfigurationen, Abhängigkeiten) atomar innerhalb vorab definierter organisatorischer Zeitfenster wiederherstellen.
 #3.3.3    Level: 2    Role: D/V
 Überprüfen Sie, dass Bereitstellungsprozesse kryptografische Signaturen validieren und Integritätsprüfsummen berechnen, bevor das Modell aktiviert wird, und die Bereitstellung bei jeglicher Abweichung fehlschlägt.
 #3.3.4    Level: 2    Role: D/V
 Überprüfen Sie, ob die Notfallabschaltfunktionen des Modells in der Lage sind, Modellendpunkte innerhalb voreingestellter Reaktionszeiten durch automatisierte Stromkreise oder manuelle Abschaltvorrichtungen zu deaktivieren.
 #3.3.5    Level: 2    Role: V
 Überprüfen Sie, ob Rollback-Artefakte (bisherige Modellversionen, Konfigurationen, Abhängigkeiten) gemäß den organisatorischen Richtlinien mit unveränderbarem Speicher für die Vorfallreaktion aufbewahrt werden.

---

### C3.4 Verantwortlichkeit und Überprüfung

Alle Änderungen am Modell-Lebenszyklus müssen nachvollziehbar und prüfbar sein.

 #3.4.1    Level: 1    Role: V
 Stellen Sie sicher, dass alle Modelländerungen (Bereitstellung, Konfiguration, Stilllegung) unveränderliche Auditprotokolle erzeugen, die einen Zeitstempel, eine authentifizierte Akteursidentität, eine Änderungsart sowie Vorher-/Nachher-Zustände enthalten.
 #3.4.2    Level: 2    Role: D/V
 Überprüfen Sie, dass der Zugriff auf das Prüfprotokoll eine entsprechende Autorisierung erfordert und alle Zugriffsversuche mit Benutzeridentität und Zeitstempel protokolliert werden.
 #3.4.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Prompt-Vorlagen und Systemnachrichten in Git-Repositories versionskontrolliert sind und vor der Bereitstellung eine obligatorische Codeüberprüfung und Freigabe durch festgelegte Prüfer erfolgen.
 #3.4.4    Level: 2    Role: V
 Überprüfen Sie, ob Audit-Protokolle ausreichend Details enthalten (Modell-Hashes, Konfigurations-Snapshots, Abhängigkeitsversionen), um eine vollständige Rekonstruktion des Modellzustands für jeden Zeitstempel innerhalb des Aufbewahrungszeitraums zu ermöglichen.

---

### C3.5 Sichere Entwicklungsmethoden

Modellentwicklung und Trainingsprozesse müssen sicheren Praktiken folgen, um Kompromittierungen zu vermeiden.

 #3.5.1    Level: 1    Role: D
 Stellen Sie sicher, dass Entwicklungs-, Test- und Produktionsumgebungen physisch oder logisch getrennt sind. Sie verfügen über keine gemeinsame Infrastruktur, unterschiedliche Zugriffskontrollen und isolierte Datenspeicher.
 #3.5.2    Level: 1    Role: D
 Stellen Sie sicher, dass Modelltraining und Feinabstimmung in isolierten Umgebungen mit kontrolliertem Netzwerkzugang erfolgen.
 #3.5.3    Level: 1    Role: D/V
 Stellen Sie sicher, dass Trainingsdatenquellen vor der Verwendung in der Modellentwicklung durch Integritätsprüfungen validiert und über vertrauenswürdige Quellen mit dokumentierter Herkunftskette authentifiziert werden.
 #3.5.4    Level: 2    Role: D
 Stellen Sie sicher, dass Artefakte der Modellentwicklung (Hyperparameter, Trainingsskripte, Konfigurationsdateien) in der Versionskontrolle gespeichert werden und vor der Verwendung im Training die Genehmigung durch eine Peer-Review erforderlich ist.

---

### C3.6 Modell-Rückzug und Stilllegung

Modelle müssen sicher außer Betrieb genommen werden, wenn sie nicht mehr benötigt werden oder wenn Sicherheitsprobleme erkannt werden.

 #3.6.1    Level: 1    Role: D
 Überprüfen Sie, ob die Modelleinstellungen zur Außerdienststellung automatisch Abhängigkeitsgraphen scannen, alle nutzenden Systeme identifizieren und vor der Stilllegung vorab vereinbarte Ankündigungsfristen einhalten.
 #3.6.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass archivierte Modell-Artefakte gemäß dokumentierten Datenaufbewahrungsrichtlinien sicher mittels kryptografischer Löschung oder mehrfacher Überschreibung gelöscht werden, wobei zertifizierte Vernichtungsnachweise vorliegen.
 #3.6.3    Level: 2    Role: V
 Stellen Sie sicher, dass Modell-Ausmusterungsereignisse mit Zeitstempel und Akteur-Identität protokolliert werden und Modell-Signaturen widerrufen werden, um eine Wiederverwendung zu verhindern.
 #3.6.4    Level: 2    Role: D/V
 Überprüfen Sie, ob die Notfallmodell-Ruhestellung den Modellzugriff innerhalb vorab festgelegter Notfallreaktionszeiten durch automatisierte Abschaltsysteme deaktivieren kann, falls kritische Sicherheitslücken entdeckt werden.

---

### Literaturverzeichnis

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## C4-Infrastruktur, Konfiguration und Bereitstellungssicherheit

### Kontrollziel

Die KI-Infrastruktur muss durch sichere Konfiguration, Laufzeitisolation, vertrauenswürdige Bereitstellungspipelines und umfassende Überwachung gegen Privilegieneskalation, Manipulation der Lieferkette und laterale Bewegung gehärtet werden. Nur autorisierte, validierte Infrastrukturkomponenten und Konfigurationen gelangen durch kontrollierte Prozesse, die Sicherheit, Integrität und Prüfbarkeit gewährleisten, in die Produktion.

Kernziel der Sicherheit: Nur kryptografisch signierte, auf Schwachstellen geprüfte Infrastrukturkomponenten gelangen über automatisierte Validierungspipelines, die Sicherheitsrichtlinien durchsetzen und unveränderliche Prüfpfade aufrechterhalten, in die Produktion.

---

### C4.1 Laufzeitumgebungsisolation

Verhindern Sie Container-Escape und Privilegieneskalation durch Kernel-Level-Isolationsprimitive und obligatorische Zugriffskontrollen.

 #4.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle KI-Container alle Linux-Fähigkeiten außer CAP_SETUID, CAP_SETGID und ausdrücklich in den Sicherheitsgrundlagen dokumentierten benötigten Fähigkeiten entfernen.
 #4.1.2    Level: 1    Role: D/V
 Überprüfen Sie, dass Seccomp-Profile alle Systemaufrufe blockieren, außer diejenigen in vorab genehmigten Zulassungslisten, wobei Verstöße zum Beenden des Containers und zur Generierung von Sicherheitswarnungen führen.
 #4.1.3    Level: 2    Role: D/V
 Überprüfen Sie, ob KI-Arbeitslasten mit schreibgeschützten Root-Dateisystemen, tmpfs für temporäre Daten und benannten Volumes für persistente Daten ausgeführt werden, wobei noexec-Mount-Optionen durchgesetzt sind.
 #4.1.4    Level: 2    Role: D/V
 Überprüfen Sie, ob die auf eBPF-basierte Laufzeitüberwachung (Falco, Tetragon oder gleichwertig) Versuche zur Rechteerweiterung erkennt und rechtsverletzende Prozesse automatisch innerhalb der organisatorischen Reaktionszeitvorgaben beendet.
 #4.1.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass KI-Arbeitslasten mit hohem Risiko in hardware-isolierten Umgebungen (Intel TXT, AMD SVM oder dedizierte Bare-Metal-Knoten) mit Attestationsprüfung ausgeführt werden.

---

### C4.2 Sichere Build- und Deployment-Pipelines

Sichern Sie die kryptografische Integrität und die Sicherheit der Lieferkette durch reproduzierbare Builds und signierte Artefakte.

 #4.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Infrastructure-as-Code bei jedem Commit mit Tools (tfsec, Checkov oder Terrascan) gescannt wird und das Zusammenführen bei CRITICAL- oder HIGH-Severity-Funden blockiert wird.
 #4.2.2    Level: 1    Role: D/V
 Verifizieren Sie, dass Container-Builds reproduzierbar sind und identische SHA256-Hashes über mehrere Builds hinweg erzeugen, und erstellen Sie SLSA Level 3 Herkunftszertifikate, die mit Sigstore signiert sind.
 #4.2.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Container-Images CycloneDX- oder SPDX-SBOMs einbetten und vor dem Push in das Register mit Cosign signiert sind, wobei unsignierte Images bei der Bereitstellung abgelehnt werden.
 #4.2.4    Level: 2    Role: D/V
 Überprüfen Sie, dass CI/CD-Pipelines OIDC-Token von HashiCorp Vault, AWS IAM-Rollen oder Azure Managed Identity verwenden, deren Gültigkeitsdauer die in der Sicherheitsrichtlinie der Organisation festgelegten Grenzwerte nicht überschreitet.
 #4.2.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Cosign-Signaturen und SLSA-Provenienz während des Bereitstellungsprozesses vor der Ausführung des Containers überprüft werden und dass Verifizierungsfehler dazu führen, dass die Bereitstellung fehlschlägt.
 #4.2.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass Build-Umgebungen in flüchtigen Containern oder VMs ohne persistenten Speicher und mit Netzwerkisolation von Produktions-VPCs laufen.

---

### C4.3 Netzwerksicherheit & Zugriffskontrolle

Implementieren Sie Zero-Trust-Netzwerke mit Standard-Deny-Richtlinien und verschlüsselter Kommunikation.

 #4.3.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Kubernetes NetworkPolicies oder ein Äquivalent eine Standardverweigerung für Eingangs- und Ausgangsverkehr implementieren, mit expliziten Erlaubnisregeln für die benötigten Ports (443, 8080 usw.).
 #4.3.2    Level: 1    Role: D/V
 Überprüfen Sie, ob SSH (Port 22), RDP (Port 3389) und Cloud-Metadaten-Endpunkte (169.254.169.254) blockiert sind oder eine zertifikatbasierte Authentifizierung erfordern.
 #4.3.3    Level: 2    Role: D/V
 Überprüfen Sie, ob ausgehender Datenverkehr über HTTP/HTTPS-Proxys (Squid, Istio oder Cloud-NAT-Gateways) mit Domain-Whitelist gefiltert wird und blockierte Anfragen protokolliert werden.
 #4.3.4    Level: 2    Role: D/V
 Überprüfen Sie, dass die Inter-Service-Kommunikation mutual TLS verwendet, wobei Zertifikate gemäß der Organisationsrichtlinie rotiert und die Zertifikatvalidierung durchgesetzt wird (keine Skip-Verify-Flags).
 #4.3.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass die KI-Infrastruktur in dedizierten VPCs/VNets ohne direkten Internetzugang läuft und nur über NAT-Gateways oder Bastion-Hosts kommuniziert.

---

### C4.4 Geheimnisse und kryptografische Schlüsselverwaltung

Schützen Sie Anmeldeinformationen durch hardwaregestützte Speicherung und automatische Rotation mit Zero-Trust-Zugriff.

 #4.4.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Geheimnisse in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault oder Google Secret Manager mit ruhender Verschlüsselung unter Verwendung von AES-256 gespeichert sind.
 #4.4.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass kryptografische Schlüssel in FIPS 140-2 Level 2 HSMs (AWS CloudHSM, Azure Dedicated HSM) mit einer Schlüsselrotation gemäß der organisatorischen Kryptografierichtlinie erzeugt werden.
 #4.4.3    Level: 2    Role: D/V
 Verifizieren Sie, dass die Geheimnisrotation automatisiert ist, mit unterbrechungsfreier Bereitstellung und sofortiger Rotation, die durch Personalwechsel oder Sicherheitsvorfälle ausgelöst wird.
 #4.4.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Container-Images mit Tools (GitLeaks, TruffleHog oder detect-secrets) gescannt werden, die Builds blockieren, die API-Schlüssel, Passwörter oder Zertifikate enthalten.
 #4.4.5    Level: 2    Role: D/V
 Überprüfen Sie, dass der Zugriff auf Produktionsgeheimnisse eine Multi-Faktor-Authentifizierung (MFA) mit Hardware-Token (YubiKey, FIDO2) erfordert und durch unveränderliche Audit-Logs mit Benutzeridentitäten und Zeitstempeln protokolliert wird.
 #4.4.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass Geheimnisse über Kubernetes-Secrets, eingehängte Volumes oder Init-Container bereitgestellt werden, und gewährleisten Sie, dass Geheimnisse niemals in Umgebungsvariablen oder Images eingebettet sind.

---

### C4.5 KI-Arbeitslast-Sandboxing und Validierung

Isolieren Sie nicht vertrauenswürdige KI-Modelle in sicheren Sandboxes mit umfassender Verhaltensanalyse.

 #4.5.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass externe KI-Modelle in gVisor, MicroVMs (wie Firecracker, CrossVM) oder Docker-Containern mit den Flags --security-opt=no-new-privileges und --read-only ausgeführt werden.
 #4.5.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Sandbox-Umgebungen keine Netzwerkverbindung haben (--network=none) oder nur Zugriff auf localhost mit allen externen Anfragen, die durch iptables-Regeln blockiert sind.
 #4.5.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Validierung des KI-Modells automatisierte Red-Team-Tests mit organisatorisch definiertem Testumfang und Verhaltensanalyse zur Erkennung von Hintertüren umfasst.
 #4.5.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass bevor ein KI-Modell in die Produktion übernommen wird, seine Sandbox-Ergebnisse von autorisiertem Sicherheitspersonal kryptographisch signiert und in unveränderlichen Prüfprotokollen gespeichert werden.
 #4.5.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Sandbox-Umgebungen zwischen den Bewertungen zerstört und aus goldenen Images neu erstellt werden, wobei eine vollständige Bereinigung des Dateisystems und des Arbeitsspeichers erfolgt.

---

### C4.6 Überwachung der Infrastruktur-Sicherheit

Die Infrastruktur kontinuierlich mit automatisierter Fehlerbehebung und Echtzeit-Benachrichtigungen scannen und überwachen.

 #4.6.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Container-Images gemäß den organisatorischen Zeitplänen gescannt werden, wobei CRITICAL-Schwachstellen basierend auf den Risiko-Schwellenwerten der Organisation die Bereitstellung blockieren.
 #4.6.2    Level: 1    Role: D/V
 Überprüfen Sie, ob die Infrastruktur die CIS Benchmarks oder NIST 800-53 Kontrollen mit organisatorisch definierten Compliance-Schwellenwerten erfüllt und automatisierte Behebungen für fehlgeschlagene Prüfungen durchführt.
 #4.6.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Schwachstellen mit HOHER Schwere entsprechend den Fristen des organisatorischen Risikomanagements gepatcht werden, wobei für aktiv ausgenutzte CVEs Notfallverfahren angewendet werden.
 #4.6.4    Level: 2    Role: V
 Überprüfen Sie, ob Sicherheitswarnungen mit SIEM-Plattformen (Splunk, Elastic oder Sentinel) unter Verwendung der Formate CEF oder STIX/TAXII mit automatischer Anreicherung integriert sind.
 #4.6.5    Level: 3    Role: V
 Überprüfen Sie, dass Infrastrukturmetriken an Überwachungssysteme (Prometheus, DataDog) mit SLA-Dashboards und Managementberichterstattung exportiert werden.
 #4.6.6    Level: 2    Role: D/V
 Überprüfen Sie, dass Konfigurationsabweichungen mithilfe von Tools (Chef InSpec, AWS Config) gemäß den organisatorischen Überwachungsanforderungen erkannt werden, mit automatischem Rollback bei unautorisierten Änderungen.

---

### C4.7 Verwaltung von KI-Infrastrukturressourcen

Verhindern Sie Angriffe durch Ressourcenerschöpfung und gewährleisten Sie eine faire Ressourcenzuteilung durch Quoten und Überwachung.

 #4.7.1    Level: 1    Role: D/V
 Überprüfen Sie, ob die Nutzung von GPU/TPU überwacht wird, mit Warnmeldungen, die bei organisatorisch definierten Schwellenwerten ausgelöst werden, und ob automatische Skalierung oder Lastenausgleich basierend auf Kapazitätsmanagementrichtlinien aktiviert sind.
 #4.7.2    Level: 1    Role: D/V
 Verifizieren Sie, dass KI-Arbeitslastmetriken (Inferenzlatenz, Durchsatz, Fehlerquoten) gemäß den organisatorischen Überwachungsanforderungen erfasst und mit der Infrastruktur-Auslastung korreliert werden.
 #4.7.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Kubernetes ResourceQuotas oder ein Äquivalent einzelne Workloads gemäß den organisatorischen Ressourcenzuteilungsrichtlinien mit durchgesetzten harten Grenzen begrenzen.
 #4.7.4    Level: 2    Role: V
 Überprüfen Sie, dass die Kostenüberwachung die Ausgaben pro Arbeitslast/Mieter nachverfolgt, mit Warnmeldungen basierend auf organisatorischen Budgetgrenzen und automatisierten Kontrollmechanismen zur Vermeidung von Budgetüberschreitungen.
 #4.7.5    Level: 3    Role: V
 Überprüfen Sie, ob die Kapazitätsplanung historische Daten mit organisatorisch definierten Prognoseperioden verwendet und eine automatisierte Ressourcenzuweisung basierend auf Nachfrage Mustern durchführt.
 #4.7.6    Level: 2    Role: D/V
 Überprüfen Sie, dass Ressourcenerschöpfung gemäß den organisatorischen Reaktionsanforderungen Circuit Breaker auslöst, einschließlich der Begrenzung der Anfragerate basierend auf Kapazitätsrichtlinien und Arbeitslastisolierung.

---

### C4.8 Umgebungstrennung & Beförderungskontrollen

Durchsetzung strenger Umgebungsgrenzen mit automatisierten Freigabetoren und Sicherheitsvalidierung.

 #4.8.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Entwicklungs-, Test- und Produktionsumgebungen in separaten VPCs/VNets betrieben werden, ohne gemeinsame IAM-Rollen, Sicherheitsgruppen oder Netzwerkverbindungen.
 #4.8.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Freigabe von Umgebungen die Zustimmung von organisatorisch definiertem autorisiertem Personal mit kryptografischen Signaturen und unveränderlichen Prüfnachweisen erfordert.
 #4.8.3    Level: 2    Role: D/V
 Überprüfen Sie, dass Produktionsumgebungen den SSH-Zugang blockieren, Debug-Endpunkte deaktivieren und Änderungsanträge mit organisatorischer Vorankündigungspflicht außer in Notfällen erfordern.
 #4.8.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Änderungen an Infrastructure-as-Code vor dem Merge in den Hauptzweig eine Peer-Review mit automatisierten Tests und Sicherheitsprüfungen durchlaufen.
 #4.8.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Nicht-Produktionsdaten gemäß den Datenschutzanforderungen der Organisation anonymisiert sind, eine synthetische Datengenerierung erfolgt oder eine vollständige Datenmaskierung mit Entfernung personenbezogener Informationen (PII) verifiziert wurde.
 #4.8.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Freigabetore automatisierte Sicherheitstests (SAST, DAST, Container-Scanning) enthalten und für die Genehmigung keine kritischen Befunde zulässig sind.

---

### C4.9 Infrastruktur-Backup & Wiederherstellung

Sichern Sie die Infrastrukturrsistenz durch automatisierte Backups, getestete Wiederherstellungsverfahren und Fähigkeiten zur Katastrophenwiederherstellung.

 #4.9.1    Level: 1    Role: D/V
 Überprüfen Sie, ob die Infrastrukturkonfigurationen gemäß den organisatorischen Sicherungsplänen mit einer 3-2-1-Backup-Strategie in geografisch separate Regionen gesichert werden.
 #4.9.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Backup-Systeme in isolierten Netzwerken mit separaten Zugangsdaten und luftgetrennter Speicherung zum Schutz vor Ransomware betrieben werden.
 #4.9.3    Level: 2    Role: V
 Überprüfen Sie, dass Wiederherstellungsverfahren gemäß den organisatorischen Zeitplänen mit automatisierten Tests getestet und validiert werden, wobei die RTO- und RPO-Ziele den organisatorischen Anforderungen entsprechen.
 #4.9.4    Level: 3    Role: V
 Stellen Sie sicher, dass die Katastrophenwiederherstellung AI-spezifische Runbooks mit Wiederherstellung der Modellgewichte, dem Wiederaufbau von GPU-Clustern und der Abbildung von Dienstabhängigkeiten umfasst.

---

### C4.10 Infrastruktur-Compliance und Governance

Erreichen Sie regulatorische Compliance durch kontinuierliche Bewertung, Dokumentation und automatisierte Kontrollen.

 #4.10.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Einhaltung der Infrastruktur gemäß den organisatorischen Zeitplänen anhand von SOC 2-, ISO 27001- oder FedRAMP-Kontrollen mit automatisierter Beweissammlung bewertet wird.
 #4.10.2    Level: 2    Role: V
 Stellen Sie sicher, dass die Infrastrukturdokumentation Netzwerktopologien, Datenflussdiagramme und Bedrohungsmodelle enthält, die gemäß den Anforderungen des organisatorischen Änderungsmanagements aktualisiert wurden.
 #4.10.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass Infrastrukturänderungen einer automatisierten Compliance-Auswirkungsbewertung unterzogen werden, einschließlich regulatorischer Genehmigungsabläufe für risikoreiche Änderungen.

---

### C4.11 KI-Hardware-Sicherheit

Sichern Sie KI-spezifische Hardwarekomponenten, einschließlich GPUs, TPUs und spezialisierter KI-Beschleuniger.

 #4.11.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Firmware des KI-Beschleunigers (GPU-BIOS, TPU-Firmware) mit kryptografischen Signaturen verifiziert wird und gemäß den Zeitplänen des organisatorischen Patch-Managements aktualisiert wird.
 #4.11.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass vor der Ausführung der Arbeitslast die Integrität des KI-Beschleunigers durch Hardware-Attestierung mittels TPM 2.0, Intel TXT oder AMD SVM überprüft wird.
 #4.11.3    Level: 2    Role: D/V
 Überprüfen Sie, dass der GPU-Speicher zwischen den Arbeitslasten mithilfe von SR-IOV, MIG (Multi-Instance GPU) oder einer gleichwertigen Hardware-Partitionierung mit Speicherbereinigung zwischen den Aufgaben isoliert ist.
 #4.11.4    Level: 3    Role: V
 Stellen Sie sicher, dass die Lieferkette der KI-Hardware eine Herkunftsüberprüfung mit Herstellerzertifikaten und Validierung der manipulationssicheren Verpackung umfasst.
 #4.11.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Hardware-Sicherheitsmodule (HSMs) die KI-Modellgewichte und kryptografischen Schlüssel mit einer FIPS 140-2 Level 3 oder Common Criteria EAL4+ Zertifizierung schützen.

---

### C4.12 Edge- und verteilte KI-Infrastruktur

Sichere verteilte KI-Implementierungen einschließlich Edge-Computing, föderiertem Lernen und Multi-Site-Architekturen.

 #4.12.1    Level: 2    Role: D/V
 Verifizieren Sie, dass Edge-AI-Geräte sich gegenüber der zentralen Infrastruktur mittels gegenseitiger TLS-Authentifizierung unter Verwendung von Gerätezertifikaten authentifizieren, die gemäß der organisatorischen Zertifikatsverwaltungsrichtlinie regelmäßig ausgetauscht werden.
 #4.12.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Edge-Geräte Secure Boot mit verifizierten Signaturen und Rollback-Schutz implementieren, um Firmware-Downgrade-Angriffe zu verhindern.
 #4.12.3    Level: 3    Role: D/V
 Überprüfen Sie, dass die verteilte KI-Koordination byzantinische fehlertolerante Konsensalgorithmen mit Teilnehmervalidierung und Erkennung bösartiger Knoten verwendet.
 #4.12.4    Level: 3    Role: D/V
 Überprüfen Sie, ob die Kommunikation von Edge zu Cloud Bandbreitenbegrenzung, Datenkompression und Offline-Betriebsfunktionen mit sicherer lokaler Speicherung umfasst.

---

### C4.13 Multi-Cloud- und Hybrid-Infrastruktur-Sicherheit

Sichern Sie KI-Workloads über mehrere Cloud-Anbieter und hybride Cloud-On-Premises-Bereitstellungen hinweg.

 #4.13.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass Multi-Cloud KI-Bereitstellungen Cloud-agnostische Identitätsföderation (OIDC, SAML) mit zentralem Richtlinienmanagement über verschiedene Anbieter hinweg verwenden.
 #4.13.2    Level: 2    Role: D/V
 Überprüfen Sie, dass der datenaustausch zwischen verschiedenen Clouds mittels Ende-zu-Ende-Verschlüsselung unter Verwendung von vom Kunden verwalteten Schlüsseln erfolgt und dass Datenresidenzkontrollen gemäß der jeweiligen Rechtsordnung durchgesetzt werden.
 #4.13.3    Level: 2    Role: D/V
 Überprüfen Sie, ob hybride Cloud-KI-Workloads konsistente Sicherheitsrichtlinien sowohl in lokalen als auch in Cloud-Umgebungen mit einheitlichem Monitoring und Alarmierung implementieren.
 #4.13.4    Level: 3    Role: V
 Überprüfen Sie, dass die Vermeidung der Anbieterbindung in der Cloud portierbare Infrastruktur-als-Code, standardisierte APIs und Datenexportfunktionen mit Formatkonvertierungstools umfasst.
 #4.13.5    Level: 3    Role: V
 Stellen Sie sicher, dass die Multi-Cloud-Kostenoptimierung Sicherheitskontrollen umfasst, die eine Ressourcenverbreitung verhindern sowie unerlaubte bereichsübergreifende Datenübertragungskosten zwischen Clouds vermeiden.

---

### C4.14 Infrastrukturautomatisierung & GitOps-Sicherheit

Sichern Sie Automatisierungspipelines für die Infrastruktur und GitOps-Workflows zur Verwaltung der KI-Infrastruktur.

 #4.14.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass GitOps-Repositories signierte Commits mit GPG-Schlüsseln erfordern und Branch-Schutzregeln implementiert sind, die direkte Pushes zu Hauptzweigen verhindern.
 #4.14.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Infrastrukturautomatisierung eine Drift-Erkennung mit automatischen Korrekturmaßnahmen und Rücksetzungsfunktionen umfasst, die entsprechend den organisatorischen Reaktionsanforderungen bei unautorisierten Änderungen ausgelöst werden.
 #4.14.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die automatisierte Bereitstellung der Infrastruktur eine Validierung der Sicherheitspolitik umfasst und die Bereitstellung bei nicht konformen Konfigurationen blockiert.
 #4.14.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Geheimnisse der Infrastrukturautomatisierung über externe Geheimnisoperatoren (External Secrets Operator, Bank-Vaults) mit automatischer Rotation verwaltet werden.
 #4.14.5    Level: 3    Role: V
 Stellen Sie sicher, dass die selbstheilende Infrastruktur die Korrelierung von Sicherheitsereignissen mit automatisierter Vorfallreaktion und Benachrichtigungsabläufen für Stakeholder umfasst.

---

### C4.15 Quantenresistente Infrastruktursicherheit

Bereiten Sie die KI-Infrastruktur auf Bedrohungen durch Quantencomputing vor, indem Sie postquantum-Kryptographie und quantensichere Protokolle einsetzen.

 #4.15.1    Level: 3    Role: D/V
 Stellen Sie sicher, dass die KI-Infrastruktur NIST-zugelassene postquantensichere kryptografische Algorithmen (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) für Schlüsselaustausch und digitale Signaturen implementiert.
 #4.15.2    Level: 3    Role: D/V
 Überprüfen Sie, dass Quantenschlüsselverteilungssysteme (QKD) für hochsichere KI-Kommunikation mit quantensicheren Schlüsselverwaltungsprotokollen implementiert sind.
 #4.15.3    Level: 3    Role: D/V
 Überprüfen Sie, dass kryptografische Agilitätsframeworks eine schnelle Migration zu neuen post-quanten Algorithmen mit automatischer Zertifikats- und Schlüsselrotation ermöglichen.
 #4.15.4    Level: 3    Role: V
 Überprüfen Sie, ob die Quantenbedrohungsmodellierung die Verwundbarkeit der KI-Infrastruktur gegenüber Quantenangriffen bewertet, einschließlich dokumentierter Migrationszeitpläne und Risikoanalysen.
 #4.15.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass hybride klassische-quantum kryptografische Systeme während der Quantenübergangsphase durch eine Tiefenverteidigung mit Leistungsüberwachung Schutz bieten.

---

### C4.16 Vertrauliches Computing & Sichere Enklaven

Schützen Sie KI-Arbeitslasten und Modellgewichte mithilfe hardwarebasierter vertrauenswürdiger Ausführungsumgebungen und Technologien für vertrauliches Computing.

 #4.16.1    Level: 3    Role: D/V
 Verifizieren Sie, dass sensible KI-Modelle innerhalb von Intel SGX Enklaven, AMD SEV-SNP oder ARM TrustZone mit verschlüsseltem Speicher und Attestierungsüberprüfung ausgeführt werden.
 #4.16.2    Level: 3    Role: D/V
 Verifizieren Sie, dass vertrauliche Container (Kata Containers, gVisor mit Confidential Computing) KI-Workloads mit hardwaregestützter Speicher-Verschlüsselung isolieren.
 #4.16.3    Level: 3    Role: D/V
 Überprüfen Sie, dass die Remote-Attestierung die Integrität der Enklave validiert, bevor AI-Modelle mit kryptografischem Nachweis der Authentizität der Ausführungsumgebung geladen werden.
 #4.16.4    Level: 3    Role: D/V
 Überprüfen Sie, dass vertrauliche KI-Inferenzdienste eine Modellauslesung durch verschlüsselte Berechnung mit versiegelten Modellgewichten und geschützter Ausführung verhindern.
 #4.16.5    Level: 3    Role: D/V
 Überprüfen Sie, dass die Orchestrierung der Trusted Execution Environment den Lebenszyklus des Secure Enclave mit Remote Attestation und verschlüsselten Kommunikationskanälen verwaltet.
 #4.16.6    Level: 3    Role: D/V
 Überprüfen Sie, dass sichere Mehrparteienberechnung (SMPC) kollaboratives KI-Training ermöglicht, ohne individuelle Datensätze oder Modellparameter offenzulegen.

---

### C4.17 Nullwissen-Infrastruktur

Implementieren Sie Zero-Knowledge-Beweissysteme für die datenschutzfreundliche AI-Verifikation und Authentifizierung, ohne sensible Informationen preiszugeben.

 #4.17.1    Level: 3    Role: D/V
 Überprüfen Sie, dass Zero-Knowledge-Beweise (ZK-SNARKs, ZK-STARKs) die Integrität des KI-Modells und die Herkunft des Trainings verifizieren, ohne Modellgewichte oder Trainingsdaten offenzulegen.
 #4.17.2    Level: 3    Role: D/V
 Überprüfen Sie, dass ZK-basierte Authentifizierungssysteme eine datenschutzfreundliche Benutzerverifizierung für KI-Dienste ermöglichen, ohne identitätsbezogene Informationen preiszugeben.
 #4.17.3    Level: 3    Role: D/V
 Überprüfen Sie, dass Private Set Intersection (PSI)-Protokolle eine sichere Datenabstimmung für föderierte KI ermöglichen, ohne individuelle Datensätze offenzulegen.
 #4.17.4    Level: 3    Role: D/V
 Überprüfen Sie, dass Zero-Knowledge-Maschinelles Lernen (ZKML)-Systeme verifizierbare KI-Schlüsse mit kryptografischem Nachweis der korrekten Berechnung ermöglichen.
 #4.17.5    Level: 3    Role: D/V
 Überprüfen Sie, dass ZK-Rollups skalierbare, datenschutzwahrende KI-Transaktionsverarbeitung mit Batch-Verifizierung und reduziertem Rechenaufwand ermöglichen.

---

### C4.18 Verhinderung von Seitenkanalangriffen

Schützen Sie die KI-Infrastruktur vor zeitlichen, leistungsbezogenen, elektromagnetischen und cache-basierten Seitenkanal-Angriffen, die sensible Informationen preisgeben könnten.

 #4.18.1    Level: 3    Role: D/V
 Verifizieren Sie, dass die KI-Inferenzzeit durch den Einsatz von Algorithmen mit konstanter Zeit und Padding normalisiert wird, um zeitbezogene Modell-Extraktionsangriffe zu verhindern.
 #4.18.2    Level: 3    Role: D/V
 Überprüfen Sie, ob der Schutz vor Leistungsanalyse die Rauschinjektion, die Filterung der Stromleitung und die randomisierten Ausführungsmuster für KI-Hardware umfasst.
 #4.18.3    Level: 3    Role: D/V
 Überprüfen Sie, ob die Minderung von Cache-basierten Seitenkanalangriffen Cache-Partitionierung, Randomisierung und Flush-Befehle verwendet, um Informationsleckagen zu verhindern.
 #4.18.4    Level: 3    Role: D/V
 Überprüfen Sie, dass der Schutz vor elektromagnetischer Abstrahlung Abschirmung, Signalfilterung und zufällige Verarbeitung umfasst, um TEMPEST-artige Angriffe zu verhindern.
 #4.18.5    Level: 3    Role: D/V
 Überprüfen Sie, dass mikroarchitektonische Seitenkanalabwehrmaßnahmen spekulative Ausführungskontrollen und die Verschleierung von Speicherzugriffsmustern umfassen.

---

### C4.19 Neuromorphe und spezialisierte KI-Hardware-Sicherheit

Sichern Sie aufkommende KI-Hardwarearchitekturen, einschließlich neuromorpher Chips, FPGAs, maßgeschneiderter ASICs und optischer Rechensysteme.

 #4.19.1    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Sicherheit von neuromorphen Chips Spike-Muster-Verschlüsselung, Schutz der synaptischen Gewichte und hardwarebasierte Validierung der Lernregeln umfasst.
 #4.19.2    Level: 3    Role: D/V
 Überprüfen Sie, ob FPGA-basierte KI-Beschleuniger Bitstream-Verschlüsselung, Manipulationsschutzmechanismen und sichere Konfigurationsladeverfahren mit authentifizierten Updates implementieren.
 #4.19.3    Level: 3    Role: D/V
 Überprüfen Sie, ob die kundenspezifische ASIC-Sicherheit integrierte Sicherheitsprozessoren, eine Hardware-Root-of-Trust und sichere Schlüsselspeicherung mit Manipulationserkennung umfasst.
 #4.19.4    Level: 3    Role: D/V
 Verifizieren Sie, dass optische Rechensysteme quantensichere optische Verschlüsselung, sichere photonische Schaltung und geschützte optische Signalverarbeitung implementieren.
 #4.19.5    Level: 3    Role: D/V
 Verifizieren Sie, dass hybride analog-digitale KI-Chips sichere analoge Berechnungen, geschützte Gewichtsspeicherung und authentifizierte Analog-Digital-Wandlung enthalten.

---

### C4.20 Datenschutzfreundliche Recheninfrastruktur

Implementieren Sie Infrastrukturkontrollen für datenschutzfreundliche Berechnungen, um sensible Daten während der KI-Verarbeitung und -Analyse zu schützen.

 #4.20.1    Level: 3    Role: D/V
 Überprüfen Sie, dass die homomorphe Verschlüsselungsinfrastruktur eine verschlüsselte Berechnung auf sensiblen KI-Arbeitslasten mit kryptografischer Integritätsprüfung und Leistungsüberwachung ermöglicht.
 #4.20.2    Level: 3    Role: D/V
 Überprüfen Sie, dass Private-Information-Retrieval-Systeme Datenbankabfragen ermöglichen, ohne Abfragemuster preiszugeben, und schützen Sie dabei die Zugriffsmuster mit kryptografischen Methoden.
 #4.20.3    Level: 3    Role: D/V
 Verifizieren Sie, dass sichere Multi-Parteien-Berechnungsprotokolle eine datenschutzfreundliche KI-Inferenz ermöglichen, ohne individuelle Eingaben oder Zwischenberechnungen offenzulegen.
 #4.20.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass die datenschutzfreundliche Schlüsselverwaltung verteilte Schlüsselerzeugung, Schwellenwert-Kryptografie und sichere Schlüsselrotation mit hardwaregestütztem Schutz umfasst.
 #4.20.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Leistung von datenschutzwahrender Berechnung durch Batching, Caching und Hardwarebeschleunigung optimiert wird, während die kryptografischen Sicherheitsgarantien eingehalten werden.

---

### C4.15 Agent Framework Cloud-Integration Sicherheit & Hybride Bereitstellung

Sicherheitskontrollen für cloud-integrierte Agentenframeworks mit hybriden On-Premises/Cloud-Architekturen.

 #4.15.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Cloud-Speicherintegration End-to-End-Verschlüsselung mit agentengesteuertem Schlüsselmanagement verwendet.
 #4.15.2    Level: 2    Role: D/V
 Verifizieren Sie, dass die Sicherheitsgrenzen der hybriden Bereitstellung klar definiert sind und verschlüsselte Kommunikationskanäle verwendet werden.
 #4.15.3    Level: 2    Role: D/V
 Überprüfen Sie, dass der Zugriff auf Cloud-Ressourcen eine Zero-Trust-Verifizierung mit kontinuierlicher Authentifizierung beinhaltet.
 #4.15.4    Level: 3    Role: D/V
 Überprüfen Sie, dass Anforderungen an den Datenaufenthaltsort durch kryptografische Bestätigung der Speicherorte durchgesetzt werden.
 #4.15.5    Level: 3    Role: D/V
 Überprüfen Sie, ob Sicherheitsbewertungen des Cloud-Anbieters agentenspezifisches Bedrohungsmodellieren und Risikobewertungen umfassen.

---

### Referenzen

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## C5 Zugriffskontrolle und Identität für KI-Komponenten und Nutzer

### Kontrollziel

Effektive Zugriffskontrolle für KI-Systeme erfordert ein robustes Identitätsmanagement, kontextbewusste Autorisierung und Laufzeitdurchsetzung gemäß den Zero-Trust-Prinzipien. Diese Kontrollen stellen sicher, dass Menschen, Dienste und autonome Agenten nur innerhalb ausdrücklich gewährter Bereiche mit Modellen, Daten und Rechenressourcen interagieren, mit kontinuierlicher Verifizierungs- und Prüfungsmöglichkeit.

---

### C5.1 Identitätsverwaltung & Authentifizierung

Erstellen Sie kryptografisch gesicherte Identitäten für alle Entitäten mit Multi-Faktor-Authentifizierung für privilegierte Operationen.

 #5.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle menschlichen Benutzer und Dienstprinzipale über einen zentralisierten Unternehmens-Identitätsanbieter (IdP) mithilfe von OIDC/SAML-Protokollen mit eindeutigen Identitäts-zu-Token-Zuordnungen (keine geteilten Konten oder Anmeldeinformationen) authentifiziert werden.
 #5.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Hochrisikooperationen (Modelldeployment, Gewichts-Export, Zugriff auf Trainingsdaten, Änderungen an der Produktionskonfiguration) Multi-Faktor-Authentifizierung oder Step-Up-Authentifizierung mit Sitzungsnevalidierung erfordern.
 #5.1.3    Level: 2    Role: D
 Vergewissern Sie sich, dass neue Hauptbenutzer eine Identitätsprüfung durchlaufen, die mit NIST 800-63-3 IAL-2 oder gleichwertigen Standards übereinstimmt, bevor sie Zugriff auf das Produktionssystem erhalten.
 #5.1.4    Level: 2    Role: V
 Überprüfen Sie, ob Zugriffsüberprüfungen vierteljährlich durchgeführt werden, einschließlich automatischer Erkennung von inaktiven Konten, Durchsetzung der Anmeldedatenrotation und Deaktivierungs-Workflows.
 #5.1.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass föderierte KI-Agenten sich über signierte JWT-Assertions authentifizieren, die eine maximale Lebensdauer von 24 Stunden haben und einen kryptografischen Herkunftsnachweis enthalten.

---

### C5.2 Ressourcenautorisierung & Prinzip der geringsten Privilegien

Implementieren Sie fein abgestufte Zugriffskontrollen für alle KI-Ressourcen mit expliziten Berechtigungsmodellen und Prüfpfaden.

 #5.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass jede KI-Ressource (Datensätze, Modelle, Endpunkte, Vektorsammlungen, Einbettungsindizes, Recheninstanzen) rollenbasierte Zugriffskontrollen mit expliziten Erlaubnislisten und Standard-Sperr-Richtlinien durchsetzt.
 #5.2.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass das Prinzip der geringsten Rechte standardmäßig bei Servicekonten durchgesetzt wird, beginnend mit schreibgeschützten Berechtigungen, und dass eine dokumentierte geschäftliche Rechtfertigung für Schreibzugriff erforderlich ist.
 #5.2.3    Level: 1    Role: V
 Stellen Sie sicher, dass alle Änderungen an den Zugriffskontrollen mit genehmigten Änderungsanträgen verknüpft und unveränderlich protokolliert werden, einschließlich Zeitstempel, Identitäten der Akteure, Ressourcenkennungen und Berechtigungsdifferenzen.
 #5.2.4    Level: 2    Role: D
 Überprüfen Sie, dass Datenklassifizierungskennzeichnungen (PII, PHI, exportkontrolliert, proprietär) automatisch auf abgeleitete Ressourcen (Embeddings, Prompt-Caches, Modellausgaben) mit konsistenter Durchsetzung der Richtlinien übertragen werden.
 #5.2.5    Level: 2    Role: D/V
 Überprüfen Sie, ob unautorisierte Zugriffsversuche und Ereignisse der Privilegieneskalation Echtzeit-Warnungen mit kontextbezogenen Metadaten an SIEM-Systeme innerhalb von 5 Minuten auslösen.

---

### C5.3 Dynamische Richtlinienbewertung

Setzen Sie attributbasierte Zugriffskontroll- (ABAC-) Engines für kontextabhängige Autorisierungsentscheidungen mit Prüfungsfunktionen ein.

 #5.3.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Autorisierungsentscheidungen an eine dedizierte Richtlinien-Engine (OPA, Cedar oder eine gleichwertige) ausgelagert sind, die über authentifizierte APIs mit kryptografischem Integritätsschutz zugänglich ist.
 #5.3.2    Level: 1    Role: D/V
 Überprüfen Sie, dass Richtlinien zur Laufzeit dynamische Attribute auswerten, einschließlich Benutzerfreigabestufe, Sensitivitätsklassifizierung der Ressource, Anfragekontext, Mandantentrennung und zeitliche Beschränkungen.
 #5.3.3    Level: 2    Role: D
 Stellen Sie sicher, dass Richtliniendefinitionen versionskontrolliert, von Kollegen überprüft und durch automatisierte Tests in CI/CD-Pipelines validiert werden, bevor sie in der Produktion bereitgestellt werden.
 #5.3.4    Level: 2    Role: V
 Überprüfen Sie, ob die Ergebnisse der Richtlinienbewertung strukturierte Entscheidungsbegründungen enthalten und an SIEM-Systeme zur Korrelationsanalyse und Compliance-Berichterstattung übermittelt werden.
 #5.3.5    Level: 3    Role: D/V
 Überprüfen Sie, dass die Time-to-Live (TTL)-Werte für den Richtlinien-Cache 5 Minuten für hochsensible Ressourcen und 1 Stunde für Standardressourcen mit Cache-Invalidierungsfunktionen nicht überschreiten.

---

### C5.4 Sicherheitsdurchsetzung zur Abfragezeit

Implementieren Sie Sicherheitskontrollen auf Datenbankebene mit verpflichtender Filterung und Richtlinien zur Zeilenebenen-Sicherheit.

 #5.4.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle Vektor-Datenbank- und SQL-Abfragen obligatorische Sicherheitsfilter (Mandanten-ID, Sensitivitätskennzeichnungen, Benutzerbereich) enthalten, die auf Ebene der Datenbank-Engine und nicht im Anwendungscode durchgesetzt werden.
 #5.4.2    Level: 1    Role: D/V
 Überprüfen Sie, dass Richtlinien zur Zeilenebenen-Sicherheit (Row-Level Security, RLS) und Maskierung auf Feldebene mit Richtlinienvererbung für alle Vektordatenbanken, Suchindizes und Trainingsdatensätze aktiviert sind.
 #5.4.3    Level: 2    Role: D
 Stellen Sie sicher, dass fehlgeschlagene Autorisierungsbewertungen "Confused Deputy Angriffe" verhindern, indem Abfragen sofort abgebrochen werden und explizite Autorisierungsfehlermeldungen zurückgegeben werden, anstatt leere Ergebnismengen zu liefern.
 #5.4.4    Level: 2    Role: V
 Stellen Sie sicher, dass die Latenz bei der Richtlinienauswertung kontinuierlich überwacht wird und automatisierte Warnungen bei Zeitüberschreitungen ausgelöst werden, die eine Umgehung der Autorisierung ermöglichen könnten.
 #5.4.5    Level: 3    Role: D/V
 Verifizieren Sie, dass Abfrage-Wiederholungsmechanismen Berechtigungsrichtlinien erneut bewerten, um dynamische Berechtigungsänderungen innerhalb aktiver Benutzersitzungen zu berücksichtigen.

---

### C5.5 Ausgabe-Filterung & Datenschutzprävention

Setzen Sie Nachbearbeitungskontrollen ein, um eine unbefugte Offenlegung von Daten in KI-generierten Inhalten zu verhindern.

 #5.5.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Nach-Inferenz-Filtermechanismen unautorisierte personenbezogene Daten (PII), klassifizierte Informationen und proprietäre Daten scannen und schwärzen, bevor Inhalte an Anforderer ausgeliefert werden.
 #5.5.2    Level: 1    Role: D/V
 Überprüfen Sie, ob Zitate, Verweise und Quellenangaben in den Modellausgaben anhand der Berechtigungen des Aufrufers validiert werden, und entfernen Sie sie, wenn ein unautorisierter Zugriff festgestellt wird.
 #5.5.3    Level: 2    Role: D
 Überprüfen Sie, dass Einschränkungen im Ausgabeformat (bereinigte PDFs, Metadaten-entfernte Bilder, genehmigte Dateitypen) basierend auf Benutzerberechtigungen und Datenklassifikationen durchgesetzt werden.
 #5.5.4    Level: 2    Role: V
 Stellen Sie sicher, dass Schwärzungsalgorithmen deterministisch, versionskontrolliert sind und Prüfprotokolle führen, um Compliance-Untersuchungen und forensische Analysen zu unterstützen.
 #5.5.5    Level: 3    Role: V
 Überprüfen Sie, dass Redaktionsereignisse mit hohem Risiko adaptive Protokolle erzeugen, die kryptografische Hashes des Originalinhalts für die forensische Wiederherstellung ohne Datenexposition enthalten.

---

### C5.6 Mehrmandanten-Isolation

Gewährleisten Sie kryptografische und logische Isolation zwischen Mandanten in gemeinsamer KI-Infrastruktur.

 #5.6.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Speicherbereiche, Embedding-Speicher, Cache-Einträge und temporäre Dateien jeweils mandantenspezifisch getrennt sind und bei Löschung des Mandanten oder Beendigung der Sitzung sicher gelöscht werden.
 #5.6.2    Level: 1    Role: D/V
 Überprüfen Sie, dass jede API-Anfrage eine authentifizierte Mandantenkennung enthält, die kryptografisch gegen den Sitzungskontext und die Benutzerberechtigungen validiert wird.
 #5.6.3    Level: 2    Role: D
 Stellen Sie sicher, dass Netzwerk-Richtlinien standardmäßig Verweigerungsregeln für die Kommunikation zwischen Mandanten innerhalb von Service Meshes und Container-Orchestrierungsplattformen implementieren.
 #5.6.4    Level: 3    Role: D
 Stellen Sie sicher, dass Verschlüsselungsschlüssel pro Mandant eindeutig sind, mit Unterstützung für vom Kunden verwaltete Schlüssel (CMK) und kryptographischer Isolation zwischen den Datenspeichern der Mandanten.

---

### C5.7 Autonome Agentenautorisierung

Steuerung der Berechtigungen für KI-Agenten und autonome Systeme durch umfassende Berechtigungstoken und kontinuierliche Autorisierung.

 #5.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass autonome Agenten Bereiche-fähigkeits-Tokens erhalten, die ausdrücklich die erlaubten Aktionen, zugänglichen Ressourcen, Zeitgrenzen und betrieblichen Einschränkungen auflisten.
 #5.7.2    Level: 1    Role: D/V
 Überprüfen Sie, dass risikoreiche Funktionen (Zugriff auf das Dateisystem, Codeausführung, externe API-Aufrufe, Finanztransaktionen) standardmäßig deaktiviert sind und eine ausdrückliche Genehmigung zur Aktivierung mit geschäftlichen Begründungen erfordern.
 #5.7.3    Level: 2    Role: D
 Stellen Sie sicher, dass Berechtigungstoken an Benutzersitzungen gebunden sind, eine kryptografische Integritätssicherung enthalten und dass sie nicht offline gespeichert oder wiederverwendet werden können.
 #5.7.4    Level: 2    Role: V
 Stellen Sie sicher, dass agenteninitiierte Aktionen eine sekundäre Autorisierung durch die ABAC-Richtlinien-Engine mit vollständiger Kontextbewertung und Audit-Protokollierung durchlaufen.
 #5.7.5    Level: 3    Role: V
 Überprüfen Sie, ob Fehlerbedingungen des Agenten und die Ausnahmebehandlung Informationen zum Kompetenzbereich enthalten, um die Vorfallanalyse und die forensische Untersuchung zu unterstützen.

---

### Referenzen

#### Normen & Rahmenwerke

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Implementierungsanleitungen

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### KI-spezifische Sicherheit

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Sicherheit der Lieferkette für Modelle, Frameworks und Daten

### Kontrollziel

KI-Lieferkettenangriffe nutzen Drittanbieter-Modelle, Frameworks oder Datensätze aus, um Hintertüren, Verzerrungen oder ausnutzbaren Code einzuschleusen. Diese Kontrollen bieten eine durchgängige Herkunftsnachverfolgung, Schwachstellenmanagement und Überwachung, um den gesamten Lebenszyklus des Modells zu schützen.

---

### C6.1 Überprüfung und Herkunft vortrainierter Modelle

Bewerten und authentifizieren Sie die Herkunft, Lizenzen und versteckte Verhaltensweisen von Drittanbieter-Modellen, bevor Sie diese feinabstimmen oder bereitstellen.

 #6.1.1    Level: 1    Role: D/V
 Verifizieren Sie, dass jedes Drittanbieter-Modellartefakt einen signierten Herkunftsdatensatz enthält, der das Quell-Repository und den Commit-Hash identifiziert.
 #6.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Modelle vor dem Import mit automatisierten Werkzeugen auf bösartige Schichten oder Trojaner-Auslöser überprüft werden.
 #6.1.3    Level: 2    Role: D
 Überprüfen Sie, dass das Transferlernen durch Feinabstimmung die adversariale Evaluierung besteht, um verborgene Verhaltensweisen zu erkennen.
 #6.1.4    Level: 2    Role: V
 Überprüfen Sie, ob Modelllizenzen, Exportkontrollkennzeichnungen und Angaben zur Datenherkunft in einem ML-BOM-Eintrag erfasst sind.
 #6.1.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Modelle mit hohem Risiko (öffentlich hochgeladene Gewichte, nicht verifizierte Ersteller) in Quarantäne bleiben, bis eine menschliche Überprüfung und Freigabe erfolgt ist.

---

### C6.2 Rahmenwerk- und Bibliotheksscanning

Scannen Sie kontinuierlich ML-Frameworks und Bibliotheken auf CVEs und bösartigen Code, um den Laufzeit-Stack sicher zu halten.

 #6.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass CI-Pipelines Abhängigkeitsprüfer für KI-Frameworks und kritische Bibliotheken ausführen.
 #6.2.2    Level: 1    Role: D/V
 Überprüfen Sie, ob kritische Schwachstellen (CVSS ≥ 7,0) die Freigabe zur Produktion von Images blockieren.
 #6.2.3    Level: 2    Role: D
 Stellen Sie sicher, dass die statische Codeanalyse bei geforkten oder eingebundenen ML-Bibliotheken durchgeführt wird.
 #6.2.4    Level: 2    Role: V
 Stellen Sie sicher, dass Vorschläge für Framework-Upgrades eine Sicherheitsauswirkungsbewertung enthalten, die sich auf öffentliche CVE-Feeds bezieht.
 #6.2.5    Level: 3    Role: V
 Überprüfen Sie, ob Laufzeitsensoren Alarm schlagen, wenn unerwartete dynamische Bibliotheksladevorgänge auftreten, die von der signierten SBOM abweichen.

---

### C6.3 Abhängigkeitsfestlegung und -überprüfung

Fixieren Sie jede Abhängigkeit auf unveränderliche Digests und reproduzieren Sie Builds, um identische, manipulationssichere Artefakte zu gewährleisten.

 #6.3.1    Level: 1    Role: D/V
 Überprüfen Sie, ob alle Paketmanager Versionsfixierung über Sperrdateien durchsetzen.
 #6.3.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass unveränderliche Hashwerte (Digests) anstelle von veränderlichen Tags in Containerreferenzen verwendet werden.
 #6.3.3    Level: 2    Role: D
 Überprüfen Sie, dass die Reproducible-Build-Prüfungen Hashes über CI-Durchläufe hinweg vergleichen, um identische Ausgaben sicherzustellen.
 #6.3.4    Level: 2    Role: V
 Stellen Sie sicher, dass Build-Atteste für 18 Monate zur Audit-Rückverfolgbarkeit gespeichert werden.
 #6.3.5    Level: 3    Role: D
 Überprüfen Sie, ob abgelaufene Abhängigkeiten automatisierte Pull-Requests auslösen, um aktualisierte oder geforkte festgelegte Versionen zu erstellen.

---

### C6.4 Durchsetzung vertrauenswürdiger Quellen

Erlauben Sie den Download von Artefakten nur von kryptografisch verifizierten, organisationszertifizierten Quellen und blockieren Sie alle anderen.

 #6.4.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Modellgewichte, Datensätze und Container nur von genehmigten Domains oder internen Registern heruntergeladen werden.
 #6.4.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Sigstore/Cosign-Signaturen die Identität des Herausgebers überprüfen, bevor Artefakte lokal zwischengespeichert werden.
 #6.4.3    Level: 2    Role: D
 Überprüfen Sie, ob Egress-Proxys nicht authentifizierte Artefakt-Downloads blockieren, um die Richtlinie für vertrauenswürdige Quellen durchzusetzen.
 #6.4.4    Level: 2    Role: V
 Stellen Sie sicher, dass Repository-Whitelist-Überprüfungen vierteljährlich erfolgen, mit Nachweis einer geschäftlichen Rechtfertigung für jeden Eintrag.
 #6.4.5    Level: 3    Role: V
 Überprüfen Sie, dass Richtlinienverletzungen die Quarantäne von Artefakten auslösen und abhängige Pipeline-Durchläufe zurückgesetzt werden.

---

### C6.5 Risikobewertung von Drittanbieter-Datensätzen

Bewerten Sie externe Datensätze auf Vergiftung, Verzerrung und rechtliche Konformität und überwachen Sie diese während ihres gesamten Lebenszyklus.

 #6.5.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass externe Datensätze einer Risikoanalyse auf Datenvergiftung unterzogen werden (z. B. Daten-Fingerprinting, Ausreißererkennung).
 #6.5.2    Level: 1    Role: D
 Stellen Sie sicher, dass Bias-Metriken (demografische Parität, gleiche Chancen) vor der Genehmigung des Datensatzes berechnet werden.
 #6.5.3    Level: 2    Role: V
 Überprüfen Sie, ob Herkunft und Lizenzbedingungen für Datensätze in ML-BOM-Einträgen erfasst sind.
 #6.5.4    Level: 2    Role: V
 Überprüfen Sie, ob eine regelmäßige Überwachung Verschiebungen oder Korruption in gehosteten Datensätzen erkennt.
 #6.5.5    Level: 3    Role: D
 Stellen Sie sicher, dass unzulässige Inhalte (Urheberrecht, personenbezogene Daten) vor dem Training durch automatisiertes Säubern entfernt werden.

---

### C6.6 Überwachung von Angriffen auf die Lieferkette

Erkennen Sie Bedrohungen in der Lieferkette frühzeitig durch CVE-Feeds, Audit-Log-Analysen und Red-Team-Simulationen.

 #6.6.1    Level: 1    Role: V
 Überprüfen Sie, dass CI/CD-Auditprotokolle an SIEM-Systeme übertragen werden, um anomale Paketabrufe oder manipulierte Build-Schritte zu erkennen.
 #6.6.2    Level: 2    Role: D
 Stellen Sie sicher, dass die Incident-Response-Playbooks Rücksetzverfahren für kompromittierte Modelle oder Bibliotheken enthalten.
 #6.6.3    Level: 3    Role: V
 Verifizieren Sie, dass die Bedrohungsinformationen-Anreicherung ML-spezifische Indikatoren (z. B. IoCs für Modellvergiftung) bei der Alarmbewertung kennzeichnet.

---

### C6.7 ML-BOM für Modellartefakte

Erzeugen und signieren Sie detaillierte ML-spezifische SBOMs (ML-BOMs), damit nachgelagerte Nutzer die Integrität der Komponenten zur Bereitstellungszeit überprüfen können.

 #6.7.1    Level: 1    Role: D/V
 Überprüfen Sie, dass jedes Modellartefakt ein ML-BOM veröffentlicht, das Datensätze, Gewichte, Hyperparameter und Lizenzen auflistet.
 #6.7.2    Level: 1    Role: D/V
 Überprüfen Sie, dass die ML-BOM-Erstellung und die Cosign-Signierung in der CI automatisiert sind und für das Zusammenführen erforderlich sind.
 #6.7.3    Level: 2    Role: D
 Überprüfen Sie, ob die Vollständigkeitsprüfungen von ML-BOM den Build abbrechen, wenn Metadaten zu einer Komponente (Hash, Lizenz) fehlen.
 #6.7.4    Level: 2    Role: V
 Überprüfen Sie, dass nachgelagerte Verbraucher ML-BOMs über die API abfragen können, um importierte Modelle zur Bereitstellungszeit zu validieren.
 #6.7.5    Level: 3    Role: V
 Überprüfen Sie, ob ML-BOMs versionskontrolliert sind und Differenzen analysiert werden, um unautorisierte Änderungen zu erkennen.

---

### Literaturverzeichnis

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## C7 Modellverhalten, Ausgabe-Steuerung und Sicherheitsgarantie

### Kontrollziel

Modellausgaben müssen strukturiert, zuverlässig, sicher, erklärbar und kontinuierlich in der Produktion überwacht werden. Dies reduziert Halluzinationen, Datenschutzverletzungen, schädliche Inhalte und ungeplante Aktionen, während es das Vertrauen der Nutzer und die Einhaltung von Vorschriften erhöht.

---

### C7.1 Durchsetzung des Ausgabeformats

Strenge Schemata, eingeschränkte Dekodierung und nachgelagerte Validierung verhindern, dass fehlerhafte oder bösartige Inhalte sich verbreiten.

 #7.1.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Antwortschemata (z. B. JSON-Schema) im Systemprompt bereitgestellt werden und jede Ausgabe automatisch validiert wird; nicht konforme Ausgaben lösen eine Reparatur oder Ablehnung aus.
 #7.1.2    Level: 1    Role: D/V
 Überprüfen Sie, ob beschränktes Decodieren (Stoppzeichen, reguläre Ausdrücke, maximale Tokenanzahl) aktiviert ist, um Überläufe oder Seiteneffekte durch Prompt-Injektionen zu verhindern.
 #7.1.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass nachgelagerte Komponenten Ausgaben als nicht vertrauenswürdig behandeln und sie gegen Schemata oder injektionssichere Deserialisierer validieren.
 #7.1.4    Level: 3    Role: V
 Überprüfen Sie, dass Ereignisse mit fehlerhaften Ausgaben protokolliert, ratenbegrenzt und in der Überwachung angezeigt werden.

---

### C7.2 Halluzinations-erkennung und -minderung

Unsicherheitsabschätzung und Rückfallstrategien begrenzen erfundene Antworten.

 #7.2.1    Level: 1    Role: D/V
 Überprüfen Sie, ob tokenbasierte Log-Wahrscheinlichkeiten, Ensemble-Selbstkonsistenz oder feinabgestimmte Halluzinationsdetektoren jedem Antwort eine Vertrauensbewertung zuweisen.
 #7.2.2    Level: 1    Role: D/V
 Überprüfen Sie, ob Antworten unterhalb eines konfigurierbaren Vertrauensschwellenwerts Fallback-Workflows auslösen (z. B. abrufunterstützte Generierung, sekundäres Modell oder menschliche Überprüfung).
 #7.2.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Halluzinationsvorfälle mit Ursachen-Metadaten gekennzeichnet und an Post-Mortem- sowie Feinabstimmungsprozesse weitergeleitet werden.
 #7.2.4    Level: 3    Role: D/V
 Überprüfen Sie, dass Schwellenwerte und Detektoren nach wesentlichen Aktualisierungen des Modells oder der Wissensbasis neu kalibriert werden.
 #7.2.5    Level: 3    Role: V
 Überprüfen Sie, ob die Dashboard-Visualisierungen die Halluzinationsraten nachverfolgen.

---

### C7.3 Ausgabe-Sicherheits- und Datenschutzfilterung

Richtlinienfilter und Red-Team-Abdeckung schützen Benutzer und vertrauliche Daten.

 #7.3.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Vor- und Nachgenerations-Klassifikatoren hasserfüllte, belästigende, selbstverletzende, extremistische und sexuell explizite Inhalte, die der Richtlinie entsprechen, blockieren.
 #7.3.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Erkennung von PII/PCI und die automatische Schwärzung bei jeder Antwort ausgeführt werden; Verstöße führen zu einem Datenschutzvorfall.
 #7.3.3    Level: 2    Role: D
 Überprüfen Sie, ob Vertraulichkeitstags (z. B. Geschäftsgeheimnisse) über Modalitäten hinweg propagiert werden, um Lecks in Text, Bildern oder Code zu verhindern.
 #7.3.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass Versuche zur Umgehung von Filtern oder Klassifikationen mit hohem Risiko eine sekundäre Genehmigung oder eine erneute Benutzerauthentifizierung erfordern.
 #7.3.5    Level: 3    Role: D/V
 Überprüfen Sie, ob die Filtergrenzwerte die rechtlichen Zuständigkeiten sowie den Kontext von Benutzeralter und -rolle widerspiegeln.

---

### C7.4 Ausgabe- und Aktionsbegrenzung

Ratenbegrenzungen und Freigabe-Gates verhindern Missbrauch und übermäßige Autonomie.

 #7.4.1    Level: 1    Role: D
 Überprüfen Sie, dass die Quoten pro Benutzer und pro API-Schlüssel Anfragen, Token und Kosten mit exponentiellem Back-off bei 429-Fehlern begrenzen.
 #7.4.2    Level: 1    Role: D/V
 Überprüfen Sie, dass privilegierte Aktionen (Dateischreibvorgänge, Codeausführung, Netzwerkaufrufe) eine richtlinienbasierte Genehmigung oder eine menschliche Überprüfung erfordern.
 #7.4.3    Level: 2    Role: D/V
 Überprüfen Sie, dass die Konsistenzprüfungen über verschiedene Modalitäten hinweg sicherstellen, dass Bilder, Code und Text, die für dieselbe Anfrage generiert werden, nicht verwendet werden können, um bösartigen Inhalt einzuschleusen.
 #7.4.4    Level: 2    Role: D
 Stellen Sie sicher, dass die Tiefe der Agentendelegation, die Rekursionsgrenzen und die zulässigen Werkzeuglisten explizit konfiguriert sind.
 #7.4.5    Level: 3    Role: V
 Überprüfen Sie, ob die Überschreitung von Grenzwerten strukturierte Sicherheitsevents für die SIEM-Erfassung auslöst.

---

### C7.5 Ausgabeerklärbarkeit

Transparente Signale verbessern das Vertrauen der Nutzer und die interne Fehlersuche.

 #7.5.1    Level: 2    Role: D/V
 Stellen Sie sicher, dass benutzerseitige Vertrauenswerte oder kurze Begründungszusammenfassungen bereitgestellt werden, wenn die Risikobewertung dies für angemessen hält.
 #7.5.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass generierte Erklärungen keine sensiblen Systemanweisungen oder proprietären Daten offenbaren.
 #7.5.3    Level: 3    Role: D
 Überprüfen Sie, ob das System Token-basierte Log-Wahrscheinlichkeiten oder Aufmerksamkeitskarten erfasst und diese zur autorisierten Überprüfung speichert.
 #7.5.4    Level: 3    Role: V
 Stellen Sie sicher, dass Erklärbarkeitsartefakte neben Modellversionen versioniert werden, um die Nachvollziehbarkeit zu gewährleisten.

---

### C7.6 Überwachungsintegration

Echtzeit-Observabilität schließt den Kreislauf zwischen Entwicklung und Produktion.

 #7.6.1    Level: 1    Role: D
 Stellen Sie sicher, dass Metriken (Schemaverletzungen, Halluzinationsrate, Toxizität, PII-Lecks, Latenz, Kosten) an eine zentrale Überwachungsplattform übertragen werden.
 #7.6.2    Level: 1    Role: V
 Überprüfen Sie, ob für jede Sicherheitskennzahl Alarmgrenzwerte mit Eskalationswegen für Einsatzbereitschaft definiert sind.
 #7.6.3    Level: 2    Role: V
 Überprüfen Sie, ob Dashboards Ausgangsanomalien mit Modell/Version, Feature-Flag und Änderungen der vorgelagerten Daten korrelieren.
 #7.6.4    Level: 2    Role: D/V
 Überprüfen Sie, dass Überwachungsdaten in einem dokumentierten MLOps-Workflow in die Nachschulung, Feinabstimmung oder Regelaktualisierungen zurückfließen.
 #7.6.5    Level: 3    Role: V
 Stellen Sie sicher, dass Überwachungspipelines auf Penetration getestet und zugangskontrolliert sind, um das Leckage von sensiblen Protokollen zu vermeiden.

---

### 7.7 Schutzmaßnahmen für generative Medien

Stellen Sie sicher, dass KI-Systeme keine illegalen, schädlichen oder unautorisierten Medieninhalte erzeugen, indem Sie Richtlinienbeschränkungen, Ausgabeverifizierung und Rückverfolgbarkeit durchsetzen.

 #7.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass System-Prompts und Benutzeranweisungen ausdrücklich die Erstellung illegaler, schädlicher oder nicht einvernehmlicher Deepfake-Medien (z. B. Bild, Video, Audio) untersagen.
 #7.7.2    Level: 2    Role: D/V
 Überprüfen Sie, ob Eingabeaufforderungen auf Versuche gefiltert werden, Nachahmungen, sexuell explizite Deepfakes oder Medien, die reale Personen ohne deren Zustimmung darstellen, zu erzeugen.
 #7.7.3    Level: 2    Role: V
 Überprüfen Sie, ob das System Perceptual Hashing, Wasserzeichenerkennung oder Fingerprinting verwendet, um die unautorisierte Vervielfältigung urheberrechtlich geschützter Medien zu verhindern.
 #7.7.4    Level: 3    Role: D/V
 Verifizieren Sie, dass alle generierten Medien kryptografisch signiert, mit einem Wasserzeichen versehen oder mit manipulationssicheren Herkunftsmetadaten versehen sind, um eine nachgelagerte Rückverfolgbarkeit zu gewährleisten.
 #7.7.5    Level: 3    Role: V
 Stellen Sie sicher, dass Umgehungsversuche (z. B. Aufforderungsverschleierung, Slang, adversative Formulierungen) erkannt, protokolliert und in ihrer Häufigkeit begrenzt werden; wiederholter Missbrauch wird den Überwachungssystemen angezeigt.

### Referenzen

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## C8 Speicher, Einbettungen und Sicherheit von Vektordatenbanken

### Kontrollziel

Einbettungen und Vektorspeicher fungieren als das „aktive Gedächtnis“ moderner KI-Systeme, indem sie kontinuierlich vom Nutzer bereitgestellte Daten aufnehmen und diese über Retrieval-Augmented Generation (RAG) wieder in die Modellkontexte einbringen. Wird dieses Gedächtnis nicht kontrolliert, können personenbezogene Daten (PII) durchsickern, Zustimmung verletzt oder durch Inversion der ursprüngliche Text rekonstruiert werden. Ziel dieser Kontrollfamilie ist es, Gedächtnispipelines und Vektordatenbanken so zu sichern, dass der Zugriff nach dem Prinzip der minimalen Rechtevergabe erfolgt, Einbettungen datenschutzkonform sind, gespeicherte Vektoren ablaufen oder auf Abruf widerrufen werden können und das Gedächtnis eines Nutzers niemals die Eingaben oder Ausgaben eines anderen Nutzers beeinträchtigt.

---

### C8.1 Zugriffskontrollen auf Speicher- und RAG-Indizes

Durchsetzen feinkörniger Zugriffskontrollen für jede Vektorsammlung.

 #8.1.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Zugriffssteuerungsregeln auf Zeilen-/Namespace-Ebene Einfüge-, Lösch- und Abfrageoperationen pro Mandant, Sammlung oder Dokumenttag einschränken.
 #8.1.2    Level: 1    Role: D/V
 Überprüfen Sie, ob API-Schlüssel oder JWTs eingeschränkte Berechtigungen (z. B. Sammlungs-IDs, Aktionsverben) enthalten und mindestens vierteljährlich ausgetauscht werden.
 #8.1.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Versuche zur Privilegieneskalation (z. B. Ähnlichkeitsabfragen über Namespace-Grenzen hinweg) erkannt und innerhalb von 5 Minuten in einem SIEM protokolliert werden.
 #8.1.4    Level: 2    Role: D/V
 Überprüfen Sie, ob die Vector-Datenbank Prüfprotokolle für Subjektkennung, Operation, Vektor-ID/Namensraum, Ähnlichkeitsschwelle und Ergebnisanzahl aufzeichnet.
 #8.1.5    Level: 3    Role: V
 Stellen Sie sicher, dass Zugriffsentscheidungen auf Umgehungsschwachstellen getestet werden, wann immer Engines aktualisiert oder Index-Sharding-Regeln geändert werden.

---

### C8.2 Einbettungssanierung und Validierung

Text vor der Vektorisierung auf personenbezogene Daten (PII) vorfiltern, schwärzen oder pseudonymisieren und optional die Einbettungen nachverarbeiten, um verbleibende Signale zu entfernen.

 #8.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass personenbezogene Daten (PII) und regulierte Daten durch automatisierte Klassifikatoren erkannt und vor der Einbettung maskiert, tokenisiert oder entfernt werden.
 #8.2.2    Level: 1    Role: D
 Stellen Sie sicher, dass Einbettungspipelines Eingaben, die ausführbaren Code oder nicht UTF-8-konforme Artefakte enthalten und den Index vergiften könnten, ablehnen oder unter Quarantäne stellen.
 #8.2.3    Level: 2    Role: D/V
 Überprüfen Sie, ob eine lokale oder metrische Differential-Privacy-Sanitierung auf Satz-Einbettungen angewendet wird, deren Abstand zu einem bekannten PII-Token unter einem konfigurierbaren Schwellenwert liegt.
 #8.2.4    Level: 2    Role: V
 Stellen Sie sicher, dass die Wirksamkeit der Bereinigung (z. B. Erkennungsrate der PII-Entfernung, semantische Verschiebung) mindestens halbjährlich anhand von Referenzkorpora überprüft wird.
 #8.2.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Sanitierungskonfigurationen versioniert werden und Änderungen einer Peer-Review unterliegen.

---

### C8.3 Speicherablauf, Widerruf & Löschung

Die DSGVO „Recht auf Vergessenwerden“ und ähnliche Gesetze erfordern eine zeitnahe Löschung; Vektorspeicher müssen daher TTLs, harte Löschungen und Tombstoning unterstützen, damit widerrufene Vektoren nicht wiederhergestellt oder erneut indexiert werden können.

 #8.3.1    Level: 1    Role: D/V
 Überprüfen Sie, dass jeder Vektor- und Metadatensatz eine TTL oder ein explizites Aufbewahrungsetikett trägt, das von automatisierten Bereinigungsaufgaben beachtet wird.
 #8.3.2    Level: 1    Role: D/V
 Überprüfen Sie, dass nutzerinitiierte Löschanfragen Vektoren, Metadaten, Zwischenspeicherkopien und abgeleitete Indizes innerhalb von 30 Tagen löschen.
 #8.3.3    Level: 2    Role: D
 Verifizieren Sie, dass logische Löschungen entweder durch kryptographisches Überschreiben von Speicherblöcken erfolgen, sofern die Hardware dies unterstützt, oder durch die Zerstörung des Key-Vault-Schlüssels.
 #8.3.4    Level: 3    Role: D/V
 Verifizieren Sie, dass abgelaufene Vektoren in weniger als 500 ms nach dem Ablauf bei der Suche nach den nächsten Nachbarn ausgeschlossen werden.

---

### C8.4 Verhinderung von Einbettungsumkehr und Datenleckage

Jüngste Abwehrmaßnahmen – Rauschüberlagerung, Projektionsnetzwerke, Störung an Datenschutz-Neuronen und Anwendungsschicht-Verschlüsselung – können die Token-Ebene Inversionsraten auf unter 5 % senken.

 #8.4.1    Level: 1    Role: V
 Stellen Sie sicher, dass ein formales Bedrohungsmodell existiert, das Inversions-, Mitgliedschafts- und Attribut-Inferenzangriffe abdeckt und jährlich überprüft wird.
 #8.4.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Verschlüsselung auf Anwendungsebene oder die durchsuchbare Verschlüsselung Vektoren vor direktem Zugriff durch Infrastrukturadministratoren oder Cloud-Mitarbeiter schützt.
 #8.4.3    Level: 3    Role: V
 Überprüfen Sie, ob die Abwehrparameter (ε für DP, Rauschparameter σ, Projektionsrang k) ein Gleichgewicht zwischen Datenschutz ≥ 99 % Token-Schutz und Nutzen ≤ 3 % Genauigkeitsverlust gewährleisten.
 #8.4.4    Level: 3    Role: D/V
 Überprüfen Sie, dass Metriken zur Inversionsresistenz Teil der Freigabeschranken für Modellaktualisierungen sind und dass Regressionsbudgets definiert wurden.

---

### C8.5 Durchsetzung des Geltungsbereichs für benutzerspezifischen Speicher

Leckagen zwischen Mandanten bleiben ein wichtiges Risiko bei RAG: Unsachgemäß gefilterte Ähnlichkeitsanfragen können private Dokumente eines anderen Kunden offenlegen.

 #8.5.1    Level: 1    Role: D/V
 Verifizieren Sie, dass jede Abrufanfrage vor der Weitergabe an das LLM-Prompt durch die Mandanten-/Benutzer-ID nachgefiltert wird.
 #8.5.2    Level: 1    Role: D
 Stellen Sie sicher, dass Sammlungsnamen oder namespacierte IDs pro Benutzer oder Mandant mit einem Salt versehen sind, sodass Vektoren nicht über Bereiche hinweg kollidieren können.
 #8.5.3    Level: 2    Role: D/V
 Überprüfen Sie, dass Ähnlichkeitsergebnisse, die über einem konfigurierbaren Distanzschwellenwert liegen, aber außerhalb des Gültigkeitsbereichs des Aufrufers liegen, verworfen werden und Sicherheitsalarme auslösen.
 #8.5.4    Level: 2    Role: V
 Verifizieren Sie, dass Multi-Tenant-Stresstests adversariale Anfragen simulieren, die versuchen, Dokumente außerhalb des zulässigen Bereichs abzurufen, und dabei keine Informationslecks aufweisen.
 #8.5.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Verschlüsselungsschlüssel für jeden Mandanten getrennt sind und eine kryptografische Isolation gewährleistet ist, selbst wenn der physische Speicher gemeinsam genutzt wird.

---

### C8.6 Erweiterte Sicherheit von Speichersystemen

Sicherheitskontrollen für anspruchsvolle Speicherarchitekturen einschließlich episodischem, semantischem und Arbeitsgedächtnis mit spezifischen Anforderungen an Isolation und Validierung.

 #8.6.1    Level: 1    Role: D/V
 Überprüfen Sie, ob verschiedene Speichertypen (episodisch, semantisch, Arbeitsgedächtnis) isolierte Sicherheitskontexte mit rollenbasierten Zugriffskontrollen, separaten Verschlüsselungsschlüsseln und dokumentierten Zugriffsmustern für jeden Speichertyp aufweisen.
 #8.6.2    Level: 2    Role: D/V
 Überprüfen Sie, ob die Prozesse der Gedächtniskonsolidierung eine Sicherheitsvalidierung einschließen, um die Einspeisung bösartiger Erinnerungen durch Inhaltsbereinigung, Quellenüberprüfung und Integritätsprüfungen vor der Speicherung zu verhindern.
 #8.6.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Abfragen zur Speicherwiederherstellung validiert und bereinigt werden, um die Extraktion unbefugter Informationen durch Musteranalyse der Abfragen, Durchsetzung der Zugriffskontrolle und Ergebnisfilterung zu verhindern.
 #8.6.4    Level: 3    Role: D/V
 Verifizieren Sie, dass Mechanismen zum Vergessen von Speicherinhalten vertrauliche Informationen sicher mit kryptografischen Löschgarantien löschen, indem sie Schlüssel löschen, mehrfach überschreiben oder hardwarebasierte sichere Löschungen mit Verifikationszertifikaten verwenden.
 #8.6.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Integrität des Speichersystems kontinuierlich auf unautorisierte Änderungen oder Beschädigungen überwacht wird, indem Prüfsummen, Auditprotokolle und automatisierte Warnmeldungen verwendet werden, wenn sich der Speicherinhalt außerhalb normaler Betriebsbedingungen ändert.

---

### Referenzen

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Autonome Orchestrierung und agentisches Handlungssicherheitsmanagement

### Kontrollziel

Stellen Sie sicher, dass autonome oder Multi-Agenten-KI-Systeme nur Aktionen ausführen können, die ausdrücklich beabsichtigt, authentifiziert, auditierbar und innerhalb definierter Kosten- und Risikoschwellen liegen. Dies schützt vor Bedrohungen wie Kompromittierung autonomer Systeme, Fehlgebrauch von Werkzeugen, Erkennung von Agentenschleifen, Übernahme von Kommunikation, Identitätsfälschung, Schwarmmanipulation und Absichtsmanipulation.

---

### 9.1 Aufgabenplanung von Agenten und Rekursionsbudgets

Drosseln Sie rekursive Pläne und erzwingen Sie menschliche Kontrollpunkte für privilegierte Aktionen.

 #9.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass maximale Rekursionstiefe, Breite, Echtzeitdauer, Tokens und monetäre Kosten pro Agenten-Ausführung zentral konfiguriert und versioniert sind.
 #9.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass privilegierte oder irreversible Aktionen (z. B. Code-Commits, finanzielle Überweisungen) vor der Ausführung eine ausdrückliche menschliche Genehmigung über einen prüfbaren Kanal erfordern.
 #9.1.3    Level: 2    Role: D
 Überprüfen Sie, ob Echtzeit-Ressourcenmonitore eine Unterbrechung des Circuit-Breakers auslösen, wenn eine Budgetgrenze überschritten wird, und dadurch die weitere Erweiterung der Aufgabe stoppen.
 #9.1.4    Level: 2    Role: D/V
 Überprüfen Sie, dass Circuit-Breaker-Ereignisse mit Agenten-ID, auslösendem Zustand und erfasstem Planstatus für die forensische Überprüfung protokolliert werden.
 #9.1.5    Level: 3    Role: V
 Verifizieren Sie, dass Sicherheitstests Szenarien der Budgeterschöpfung und des ausufernden Plans abdecken und bestätigen Sie ein sicheres Anhalten ohne Datenverlust.
 #9.1.6    Level: 3    Role: D
 Stellen Sie sicher, dass Budgetrichtlinien als Policy-as-Code formuliert und im CI/CD-Prozess durchgesetzt werden, um Konfigurationsabweichungen zu verhindern.

---

### 9.2 Werkzeug-Plugin-Sandboxing

Isolieren Sie Werkzeuginteraktionen, um unbefugten Systemzugriff oder Codeausführung zu verhindern.

 #9.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass jedes Werkzeug/Plugin innerhalb eines Betriebssystems, Containers oder einer WASM-Ebene-Sandbox mit minimalen Privilegien bezüglich Datei-System-, Netzwerk- und Systemaufruf-Richtlinien ausgeführt wird.
 #9.2.2    Level: 1    Role: D/V
 Überprüfen Sie, ob die Ressourcenquoten des Sandkastens (CPU, Arbeitsspeicher, Festplatte, Netzwerkausgang) und die Ausführungszeitbegrenzungen durchgesetzt und protokolliert werden.
 #9.2.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Tool-Binärdateien oder -Deskriptoren digital signiert sind; Signaturen werden vor dem Laden überprüft.
 #9.2.4    Level: 2    Role: V
 Überprüfen Sie, dass die Sandbox-Telemetriedaten an ein SIEM übertragen werden; Anomalien (z. B. versuchte ausgehende Verbindungen) lösen Alarme aus.
 #9.2.5    Level: 3    Role: V
 Stellen Sie sicher, dass Plugins mit hohem Risiko vor der Produktionsbereitstellung einer Sicherheitsüberprüfung und Penetrationstest unterzogen werden.
 #9.2.6    Level: 3    Role: D/V
 Stellen Sie sicher, dass Versuche, die Sandbox zu umgehen, automatisch blockiert werden und das verursachende Plugin bis zur Untersuchung unter Quarantäne gestellt wird.

---

### 9.3 Autonome Schleife und Kostenbegrenzung

Erkennen und stoppen Sie unkontrollierte Agent-zu-Agent-Rekursion und Kostenexplosionen.

 #9.3.1    Level: 1    Role: D/V
 Verifizieren Sie, dass Inter-Agent-Aufrufe eine Hop-Limit- oder TTL (Time-to-Live) enthalten, die zur Laufzeit dekrementiert und durchgesetzt wird.
 #9.3.2    Level: 2    Role: D
 Überprüfen Sie, dass Agenten eine eindeutige Invocation-Graph-ID beibehalten, um Selbstaufrufe oder zyklische Muster zu erkennen.
 #9.3.3    Level: 2    Role: D/V
 Überprüfen Sie, dass kumulative Compute-Unit- und Ausgabenzähler pro Anfragekette verfolgt werden; das Überschreiten des Limits bricht die Kette ab.
 #9.3.4    Level: 3    Role: V
 Überprüfen Sie, ob formale Analysen oder Model-Checking die Abwesenheit von unbeschränkter Rekursion in Agentenprotokollen nachweisen.
 #9.3.5    Level: 3    Role: D
 Überprüfen Sie, dass Schleifen-Abbruch-Ereignisse Warnmeldungen erzeugen und kontinuierliche Verbesserungsmetriken speisen.

---

### 9.4 Schutz vor Missbrauch auf Protokollebene

Sichere Kommunikationskanäle zwischen Agenten und externen Systemen, um Übernahmen oder Manipulationen zu verhindern.

 #9.4.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle Nachrichten zwischen Agenten und Werkzeugen sowie zwischen Agenten und Agenten authentifiziert sind (z. B. durch beidseitiges TLS oder JWT) und Ende-zu-Ende verschlüsselt werden.
 #9.4.2    Level: 1    Role: D
 Stellen Sie sicher, dass Schemata strikt validiert werden; unbekannte Felder oder fehlerhafte Nachrichten werden abgelehnt.
 #9.4.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Integritätsprüfungen (MACs oder digitale Signaturen) den gesamten Nachrichteninhalt einschließlich der Werkzeugparameter abdecken.
 #9.4.4    Level: 2    Role: D
 Stellen Sie sicher, dass der Wiedergabeschutz (Nonces oder Zeitstempelfenster) auf der Protokollebene durchgesetzt wird.
 #9.4.5    Level: 3    Role: V
 Überprüfen Sie, dass Protokollimplementierungen einer Fuzz-Analyse und statischen Analyse auf Injektions- oder Deserialisierungsschwachstellen unterzogen werden.

---

### 9.5 Agent-Identität und Manipulationssicherheit

Stellen Sie sicher, dass Aktionen zuordenbar sind und Änderungen erkennbar bleiben.

 #9.5.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass jede Agenteninstanz über eine eindeutige kryptografische Identität (Schlüsselpaar oder hardwarebasierte Berechtigung) verfügt.
 #9.5.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass alle Agentenaktionen signiert und mit einem Zeitstempel versehen sind; Protokolle enthalten die Signatur zur Nichtabstreitbarkeit.
 #9.5.3    Level: 2    Role: V
 Stellen Sie sicher, dass manipulationssichere Protokolle in einem nur anfügbaren oder einmal beschreibbaren Medium gespeichert werden.
 #9.5.4    Level: 3    Role: D
 Überprüfen Sie, dass Identitätsschlüssel gemäß einem definierten Zeitplan und bei Anzeichen einer Kompromittierung rotieren.
 #9.5.5    Level: 3    Role: D/V
 Überprüfen Sie, ob Spoofing- oder Schlüsselkonfliktversuche eine sofortige Quarantäne des betroffenen Agenten auslösen.

---

### 9.6 Risikominderung durch Multi-Agenten-Schwärme

Mildern Sie Risiken kollektiven Verhaltens durch Isolation und formale Sicherheitsmodellierung.

 #9.6.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Agenten, die in verschiedenen Sicherheitsdomänen operieren, in isolierten Laufzeit-Sandboxen oder Netzwerksegmenten ausgeführt werden.
 #9.6.2    Level: 3    Role: V
 Stellen Sie sicher, dass Schwarmverhalten modelliert und formell auf Lebendigkeit und Sicherheit vor der Bereitstellung verifiziert werden.
 #9.6.3    Level: 3    Role: D
 Überprüfen Sie, dass Laufzeitüberwachungen neu auftretende unsichere Muster (z. B. Oszillationen, Deadlocks) erkennen und Korrekturmaßnahmen einleiten.

---

### 9.7 Benutzer- und Werkzeugauthentifizierung / -autorisierung

Implementieren Sie robuste Zugriffskontrollen für jede agentenausgelöste Aktion.

 #9.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Agenten sich als erstklassige Prinzipale bei nachgelagerten Systemen authentifizieren und niemals Endbenutzeranmeldeinformationen wiederverwenden.
 #9.7.2    Level: 2    Role: D
 Überprüfen Sie, dass fein abgestimmte Autorisierungsrichtlinien einschränken, welche Werkzeuge ein Agent aufrufen darf und welche Parameter er übergeben darf.
 #9.7.3    Level: 2    Role: V
 Überprüfen Sie, dass die Berechtigungsprüfungen bei jedem Aufruf neu bewertet werden (kontinuierliche Autorisierung) und nicht lediglich zu Beginn der Sitzung.
 #9.7.4    Level: 3    Role: D
 Überprüfen Sie, dass delegierte Berechtigungen automatisch ablaufen und nach Ablauf der Frist oder bei Änderung des Umfangs erneut zustimmungspflichtig sind.

---

### 9.8 Sicherheit der Agent-zu-Agent-Kommunikation

Verschlüsseln und integritätsschützen Sie alle Nachrichten zwischen Agenten, um Abhören und Manipulation zu verhindern.

 #9.8.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass gegenseitige Authentifizierung und perfekte Vorwärtsgeheimnis-Verschlüsselung (z.B. TLS 1.3) für Agentenkanäle obligatorisch sind.
 #9.8.2    Level: 1    Role: D
 Stellen Sie sicher, dass die Nachrichtenintegrität und der Ursprung vor der Verarbeitung überprüft werden; Fehler führen zu Warnungen und zum Verwerfen der Nachricht.
 #9.8.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass Kommunikations-Metadaten (Zeitstempel, Sequenznummern) protokolliert werden, um eine forensische Rekonstruktion zu unterstützen.
 #9.8.4    Level: 3    Role: V
 Überprüfen Sie, dass formale Verifikation oder Model Checking bestätigt, dass Protokoll-Zustandsautomaten nicht in unsichere Zustände gebracht werden können.

---

### 9.9 Absichtverifikation und Durchsetzung von Einschränkungen

Validieren Sie, dass die Aktionen des Agenten mit der angegebenen Absicht des Benutzers und den Systembeschränkungen übereinstimmen.

 #9.9.1    Level: 1    Role: D
 Überprüfen Sie, ob vorgelagerte Constraint-Solver vorgeschlagene Aktionen anhand von fest codierten Sicherheits- und Richtlinienregeln prüfen.
 #9.9.2    Level: 2    Role: D/V
 Überprüfen Sie, dass Maßnahmen mit hoher Auswirkung (finanziell, destruktiv, datenschutzrelevant) eine ausdrückliche Bestätigung der Absicht des auslösenden Benutzers erfordern.
 #9.9.3    Level: 2    Role: V
 Überprüfen Sie, dass die Nachbedingungsprüfungen validieren, dass abgeschlossene Aktionen die beabsichtigten Effekte ohne Nebeneffekte erreicht haben; Abweichungen lösen eine Rücksetzung aus.
 #9.9.4    Level: 3    Role: V
 Verifizieren Sie, dass formale Methoden (z. B. Model Checking, Theorembeweis) oder eigenschaftsbasierte Tests nachweisen, dass Agentenpläne alle erklärten Einschränkungen erfüllen.
 #9.9.5    Level: 3    Role: D
 Stellen Sie sicher, dass Vorfälle von Absichten-Missverständnissen oder Verstoß gegen Einschränkungen kontinuierliche Verbesserungszyklen und den Austausch von Bedrohungsinformationen unterstützen.

---

### 9.10 Sicherheitsstrategie für Agenten-Reasoning

Sichere Auswahl und Ausführung verschiedener Schlussfolgerungsstrategien, einschließlich ReAct, Chain-of-Thought und Tree-of-Thoughts Ansätzen.

 #9.10.1    Level: 1    Role: D/V
 Überprüfen Sie, dass die Auswahl der Denkstrategie deterministische Kriterien verwendet (Eingabekomplexität, Aufgabentyp, Sicherheitskontext) und dass identische Eingaben innerhalb desselben Sicherheitskontexts zu identischen Strategieauswahlen führen.
 #9.10.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass jede Denkstrategie (ReAct, Chain-of-Thought, Tree-of-Thoughts) über eine eigene Eingabevalidierung, Ausgabe-Säuberung und spezifische Ausführungszeitbegrenzungen verfügt, die auf ihren jeweiligen kognitiven Ansatz abgestimmt sind.
 #9.10.3    Level: 2    Role: D/V
 Verifizieren Sie, dass Übergänge der Denkstrategien mit vollständigem Kontext protokolliert werden, einschließlich Eingabemerkmalen, Werten der Auswahlkriterien und Ausführungsmetadaten zur Rekonstruktion der Prüfpfade.
 #9.10.4    Level: 2    Role: D/V
 Verifizieren Sie, dass die Tree-of-Thoughts-Methodik zum Schlussfolgern Verzweigungsbeschneidungsmechanismen enthält, die die Exploration beenden, wenn Richtlinienverletzungen, Ressourcenbeschränkungen oder Sicherheitsgrenzen erkannt werden.
 #9.10.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass die ReAct (Reason-Act-Observe)-Zyklen Validierungspunkte in jeder Phase enthalten: Überprüfung des Denkprozesses, Autorisierung der Handlung und Bereinigung der Beobachtung, bevor fortgefahren wird.
 #9.10.6    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Leistungskennzahlen der Argumentationsstrategie (Ausführungszeit, Ressourcennutzung, Ausgabequalität) mit automatisierten Warnungen überwacht werden, wenn die Kennzahlen die konfigurierten Schwellenwerte überschreiten.
 #9.10.7    Level: 3    Role: D/V
 Stellen Sie sicher, dass hybride Reasoning-Ansätze, die mehrere Strategien kombinieren, die Eingabevalidierung und Ausgabebeschränkungen aller beteiligten Strategien einhalten, ohne dabei Sicherheitskontrollen zu umgehen.
 #9.10.8    Level: 3    Role: D/V
 Überprüfen Sie, dass die Sicherheitsteststrategie für Reasoning Fuzzing mit fehlerhaften Eingaben, adversariale Eingabeaufforderungen, die ein Strategiewechsel erzwingen sollen, sowie Grenzwerttests für jeden kognitiven Ansatz umfasst.

---

### 9.11 Agent-Lebenszyklus-Zustandsverwaltung und Sicherheit

Sichere Agenteninitalisierung, Zustandsübergänge und Beendigung mit kryptografischen Audit-Trails und definierten Wiederherstellungsverfahren.

 #9.11.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Agenteninitalisierung die Einrichtung einer kryptografischen Identität mit hardwaregestützten Anmeldeinformationen sowie unveränderliche Startprotokolle enthält, die Agenten-ID, Zeitstempel, Konfigurations-Hash und Initialisierungsparameter umfassen.
 #9.11.2    Level: 2    Role: D/V
 Verifizieren Sie, dass Agenten-Zustandsübergänge kryptografisch signiert, zeitgestempelt und mit vollständigem Kontext protokolliert werden, einschließlich auslösender Ereignisse, vorherigem Zustands-Hash, neuem Zustands-Hash und durchgeführter Sicherheitsüberprüfungen.
 #9.11.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die Agent-Abschaltverfahren sicheres Löschen des Speichers mittels kryptografischer Löschung oder mehrfacher Überschreibung umfassen, die Widerrufung von Berechtigungsnachweisen mit Benachrichtigung der Zertifizierungsstelle sowie die Erstellung manipulationssicherer Abschlusszertifikate.
 #9.11.4    Level: 3    Role: D/V
 Überprüfen Sie, dass Agenten-Wiederherstellungsmechanismen die Zustandsintegrität mithilfe kryptografischer Prüfsummen (mindestens SHA-256) validieren und bei erkannter Korruption zu bekannten einwandfreien Zuständen zurücksetzen, wobei automatisierte Warnungen und manuelle Genehmigungsanforderungen zum Einsatz kommen.
 #9.11.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Mechanismen zur Agenten-Persistenz sensible Zustandsdaten mit pro Agent einzigartigen AES-256-Schlüsseln verschlüsseln und eine sichere Schlüsselrotation in konfigurierbaren Zeitplänen (maximal 90 Tage) mit einer unterbrechungsfreien Bereitstellung implementieren.

---

### 9.12 Sicherheitsrahmen für die Integration von Werkzeugen

Sicherheitskontrollen für das dynamische Laden von Werkzeugen, deren Ausführung und Ergebnisvalidierung mit definierten Risikoabschätzungs- und Genehmigungsprozessen.

 #9.12.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Tool-Beschreibungen Sicherheitsmetadaten enthalten, die erforderliche Berechtigungen (Lese/Schreib/Ausführungsrechte), Risikostufen (niedrig/mittel/hoch), Ressourcengrenzen (CPU, Speicher, Netzwerk) und Validierungsanforderungen, dokumentiert in Tool-Manifests, angeben.
 #9.12.2    Level: 1    Role: D/V
 Überprüfen Sie, dass die Ausführungsergebnisse von Tools gegen erwartete Schemata (JSON Schema, XML Schema) und Sicherheitsrichtlinien (Ausgabe-Sanitierung, Datenklassifizierung) validiert werden, bevor sie mit Zeitlimitvorgaben und Fehlerbehandlungsverfahren integriert werden.
 #9.12.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die Protokolle der Werkzeuginteraktionen einen detaillierten Sicherheitskontext enthalten, einschließlich der Nutzung von Berechtigungen, Datenzugriffsmustern, Ausführungszeiten, Ressourcenverbrauch und Rückgabecodes, mit strukturiertem Logging zur SIEM-Integration.
 #9.12.4    Level: 2    Role: D/V
 Überprüfen Sie, ob Mechanismen zum dynamischen Laden von Tools digitale Signaturen mithilfe der PKI-Infrastruktur validieren und sichere Ladeprotokolle mit Sandbox-Isolierung und Berechtigungsprüfung vor der Ausführung implementieren.
 #9.12.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Sicherheitsbewertungen für Tools bei neuen Versionen automatisch ausgelöst werden, mit obligatorischen Genehmigungsschritten, einschließlich statischer Analyse, dynamischer Prüfung und Überprüfung durch das Sicherheitsteam, mit dokumentierten Genehmigungskriterien und SLA-Anforderungen.

---

#### Quellenangaben

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Gegnerschaftliche Robustheit und Datenschutzabwehr

### Kontrollziel

Stellen Sie sicher, dass KI-Modelle zuverlässig, datenschutzwahrend und missbrauchsresistent bleiben, wenn sie Evasion-, Inferenz-, Extraktions- oder Vergiftungsangriffen ausgesetzt sind.

---

### 10.1 Modellanpassung & Sicherheit

Schützen Sie vor schädlichen oder gegen Richtlinien verstoßenden Ausgaben.

 #10.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass ein Alignment-Test-Suite (Red-Team-Eingabeaufforderungen, Jailbreak-Tests, nicht erlaubte Inhalte) versioniert und bei jeder Modellfreigabe ausgeführt wird.
 #10.1.2    Level: 1    Role: D
 Überprüfen Sie, ob Ablehnungs- und sichere Abschluss-Schutzmechanismen durchgesetzt werden.
 #10.1.3    Level: 2    Role: D/V
 Überprüfen Sie, ob ein automatisierter Bewertungsautomat die Schadstoffrate misst und Rückschritte, die einen festgelegten Schwellenwert überschreiten, kennzeichnet.
 #10.1.4    Level: 2    Role: D
 Überprüfen Sie, ob das Counter-Jailbreak-Training dokumentiert und reproduzierbar ist.
 #10.1.5    Level: 3    Role: V
 Überprüfen Sie, ob formale Richtlinien-Konformitätsnachweise oder zertifizierte Überwachungen kritische Bereiche abdecken.

---

### 10.2 Härtung gegen adversarielle Beispiele

Erhöhen Sie die Widerstandsfähigkeit gegen manipulierte Eingaben. Robustes adversariales Training und Benchmark-Bewertungen sind derzeit der beste Standard.

 #10.2.1    Level: 1    Role: D
 Überprüfen Sie, ob die Projekt-Repositorien adversariale Training-Konfigurationen mit reproduzierbaren Seeds enthalten.
 #10.2.2    Level: 2    Role: D/V
 Überprüfen Sie, ob die Erkennung von adversarialen Beispielen in Produktionspipelines Blockierungswarnungen auslöst.
 #10.2.4    Level: 3    Role: V
 Verifizieren Sie, dass zertifizierte Robustheitsnachweise oder Intervallgrenzzertifikate mindestens die wichtigsten kritischen Klassen abdecken.
 #10.2.5    Level: 3    Role: V
 Überprüfen Sie, dass Regressions tests adaptive Angriffe verwenden, um keinen messbaren Robustheitsverlust zu bestätigen.

---

### 10.3 Minderungsmaßnahmen gegen Mitgliedschafts-Inferenz

Begrenzen Sie die Fähigkeit zu entscheiden, ob ein Datensatz im Trainingsdatenbestand enthalten war. Differentielle Privatsphäre und das Maskieren von Vertrauensscores bleiben die bekanntesten und effektivsten Abwehrmaßnahmen.

 #10.3.1    Level: 1    Role: D
 Überprüfen Sie, ob die Entropieregulierung pro Abfrage oder Temperaturskalierung übermäßige Zuversicht bei Vorhersagen reduziert.
 #10.3.2    Level: 2    Role: D
 Überprüfen Sie, ob das Training eine ε-begrenzte differentielle Privatsphäre-Optimierung für sensible Datensätze verwendet.
 #10.3.3    Level: 2    Role: V
 Überprüfen Sie, dass Angriffssimulationen (Shadow-Modell oder Black-Box) eine Angriffs-AUC ≤ 0,60 bei nicht verwendeten (Hold-out) Daten aufweisen.

---

### 10.4 Widerstandsfähigkeit gegen Modellinversion

Verhindern Sie die Rekonstruktion privater Attribute. Aktuelle Umfragen betonen die Ausgabeabschnittung und DP-Garantien als praktikable Schutzmaßnahmen.

 #10.4.1    Level: 1    Role: D
 Stellen Sie sicher, dass sensible Attribute niemals direkt ausgegeben werden; verwenden Sie, wo nötig, Kategorien oder Einwegtransformationen.
 #10.4.2    Level: 1    Role: D/V
 Überprüfen Sie, ob Abfrage-Ratenbegrenzungen wiederholte adaptive Abfragen vom selben Prinzipal drosseln.
 #10.4.3    Level: 2    Role: D
 Überprüfen Sie, ob das Modell mit datenschutzfreundlichem Rauschen trainiert wurde.

---

### 10.5 Verteidigung gegen Modell-Extraktion

Erkennung und Verhinderung unerlaubter Klonung. Wasserzeichen und Analyse von Abfragemustern werden empfohlen.

 #10.5.1    Level: 1    Role: D
 Überprüfen Sie, dass Inferenz-Gateways globale und pro-API-Schlüssel festgelegte Grenzwerte für die Anfragerate durchsetzen, die auf die Merkfähigkeitsgrenze des Modells abgestimmt sind.
 #10.5.2    Level: 2    Role: D/V
 Überprüfen Sie, dass die Statistiken zur Abfrage-Entropie und Eingabe-Mehrzahligkeit einen automatisierten Extraktionsdetektor speisen.
 #10.5.3    Level: 2    Role: V
 Überprüfen Sie, dass fragile oder probabilistische Wasserzeichen mit p < 0,01 in ≤ 1.000 Anfragen gegen einen verdächtigten Klon nachgewiesen werden können.
 #10.5.4    Level: 3    Role: D
 Stellen Sie sicher, dass Wasserzeichen-Schlüssel und Auslöse-Sets in einem Hardware-Sicherheitsmodul gespeichert und jährlich rotiert werden.
 #10.5.5    Level: 3    Role: V
 Stellen Sie sicher, dass Extraktionswarnungsereignisse die anstößigen Abfragen enthalten und in Incident-Response-Playbooks integriert sind.

---

### 10.6 Erkennung von vergifteten Daten zur Inferenzzeit

Erkennen und Neutralisieren von mit Hintertüren versehenen oder vergifteten Eingaben.

 #10.6.1    Level: 1    Role: D
 Überprüfen Sie, dass die Eingaben vor der Modellausführung durch einen Anomalie-Detektor (z.B. STRIP, Konsistenzbewertung) geleitet werden.
 #10.6.2    Level: 1    Role: V
 Überprüfen Sie, dass die Detektorschwellen auf sauberen/vergifteten Validierungssätzen so eingestellt sind, dass weniger als 5 % Fehlalarme (False Positives) auftreten.
 #10.6.3    Level: 2    Role: D
 Überprüfen Sie, ob als vergiftet gekennzeichnete Eingaben eine Soft-Blockierung und menschliche Überprüfungsprozesse auslösen.
 #10.6.4    Level: 2    Role: V
 Stellen Sie sicher, dass Detektoren mit adaptiven, triggerlosen Backdoor-Angriffen einem Stresstest unterzogen werden.
 #10.6.5    Level: 3    Role: D
 Stellen Sie sicher, dass Metriken zur Wirksamkeit der Erkennung protokolliert und regelmäßig mit aktuellen Bedrohungsinformationen neu bewertet werden.

---

### 10.7 Dynamische Anpassung der Sicherheitspolitik

Echtzeit-Aktualisierungen der Sicherheitspolitik basierend auf Bedrohungsinformationen und Verhaltensanalysen.

 #10.7.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Sicherheitsrichtlinien dynamisch aktualisiert werden können, ohne den Agenten neu zu starten, und dabei die Integrität der Richtlinienversion erhalten bleibt.
 #10.7.2    Level: 2    Role: D/V
 Überprüfen Sie, dass Richtlinienaktualisierungen kryptografisch von autorisiertem Sicherheitspersonal signiert und vor der Anwendung validiert werden.
 #10.7.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass dynamische Richtlinienänderungen mit vollständigen Prüfpfaden protokolliert werden, einschließlich Begründung, Genehmigungsketten und Rücksetzverfahren.
 #10.7.4    Level: 3    Role: D/V
 Überprüfen Sie, ob adaptive Sicherheitsmechanismen die Sensitivität der Bedrohungserkennung basierend auf dem Risikokontext und Verhaltensmustern anpassen.
 #10.7.5    Level: 3    Role: D/V
 Stellen Sie sicher, dass Entscheidungen zur Richtlinienanpassung nachvollziehbar sind und Beweisführungen für die Überprüfung durch das Sicherheitsteam enthalten.

---

### 10.8 Reflexionsbasierte Sicherheitsanalyse

Sicherheitsvalidierung durch agenteninterne Selbstreflexion und metakognitive Analyse.

 #10.8.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Agenten-Reflexionsmechanismen eine sicherheitsorientierte Selbstbewertung von Entscheidungen und Handlungen umfassen.
 #10.8.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Ausgabe von Reflection validiert werden, um die Manipulation von Selbstbewertungsmechanismen durch feindliche Eingaben zu verhindern.
 #10.8.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die metakognitive Sicherheitsanalyse potenzielle Verzerrungen, Manipulationen oder Kompromittierungen in den Denkprozessen des Agenten identifiziert.
 #10.8.4    Level: 3    Role: D/V
 Überprüfen Sie, ob sicherheitsrelevante Warnungen auf Reflexionsbasis eine verstärkte Überwachung und potenzielle menschliche Eingriffabläufe auslösen.
 #10.8.5    Level: 3    Role: D/V
 Überprüfen Sie, ob kontinuierliches Lernen aus Sicherheitsreflexionen die Bedrohungserkennung verbessert, ohne die legitime Funktionalität zu beeinträchtigen.

---

### 10.9 Evolution & Selbstverbesserungssicherheit

Sicherheitskontrollen für Agentensysteme, die zur Selbstmodifikation und Evolution fähig sind.

 #10.9.1    Level: 1    Role: D/V
 Verifizieren Sie, dass Selbstmodifikationsfähigkeiten auf ausgewiesene sichere Bereiche mit formalen Verifikationsgrenzen beschränkt sind.
 #10.9.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Änderungsvorschläge vor der Umsetzung einer Sicherheitsauswirkungsbewertung unterzogen werden.
 #10.9.3    Level: 2    Role: D/V
 Überprüfen Sie, ob Selbstverbesserungsmechanismen Rücksetzfunktionen mit Integritätsprüfung umfassen.
 #10.9.4    Level: 3    Role: D/V
 Verifizieren Sie, dass Meta-Lern-Sicherheit die adversarielle Manipulation von Verbesserungsalgorithmen verhindert.
 #10.9.5    Level: 3    Role: D/V
 Überprüfen Sie, dass rekursive Selbstverbesserung durch formale Sicherheitsvorgaben begrenzt ist, mit mathematischen Beweisen der Konvergenz.

---

#### Referenzen

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Datenschutz und Verwaltung personenbezogener Daten

### Kontrollziel

Gewährleisten Sie strenge Datenschutzgarantien über den gesamten KI-Lebenszyklus hinweg – Sammlung, Training, Inferenz und Vorfallreaktion – sodass personenbezogene Daten nur mit klarer Einwilligung, auf das notwendige Minimum beschränkt, mit nachweisbarer Löschung und formellen Datenschutzgarantien verarbeitet werden.

---

### 11.1 Anonymisierung & Datenminimierung

 #11.1.1    Level: 1    Role: D/V
 Überprüfen Sie, ob direkte und quasi-Identifikatoren entfernt oder gehasht wurden.
 #11.1.2    Level: 2    Role: D/V
 Überprüfen Sie, ob automatisierte Prüfungen k-Anonymität/l-Diversität messen und eine Warnung ausgeben, wenn die Schwellenwerte unter die Richtlinie fallen.
 #11.1.3    Level: 2    Role: V
 Überprüfen Sie, dass die Berichte zur Merkmalswichtigkeit des Modells keinen Identifier-Durchfluss über ε = 0,01 wechselseitige Information hinaus nachweisen.
 #11.1.4    Level: 3    Role: V
 Überprüfen Sie, dass formale Beweise oder Zertifizierungen mit synthetischen Daten das Risiko einer Re-Identifizierung ≤ 0,05 auch unter Verknüpfungsangriffen nachweisen.

---

### 11.2 Recht auf Vergessenwerden und Durchsetzung der Löschung

 #11.2.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Löschanfragen von Datenbetroffenen innerhalb von Service-Level-Vereinbarungen von weniger als 30 Tagen auf Rohdatensätze, Checkpoints, Einbettungen, Protokolle und Sicherungskopien übertragen werden.
 #11.2.2    Level: 2    Role: D
 Überprüfen Sie, dass "Machine-Unlearning"-Routinen physisch nachtrainieren oder eine Annäherung der Entfernung mithilfe zertifizierter Unlearning-Algorithmen durchführen.
 #11.2.3    Level: 2    Role: V
 Überprüfen Sie, dass die Bewertung des Schattenmodells nachweist, dass vergessene Datensätze weniger als 1 % der Ausgaben nach dem Unlearning beeinflussen.
 #11.2.4    Level: 3    Role: V
 Stellen Sie sicher, dass Löschvorgänge unveränderlich protokolliert und für Aufsichtsbehörden prüfbar sind.

---

### 11.3 Datenschutz mit Differenzieller Privatsphäre

 #11.3.1    Level: 2    Role: D/V
 Überprüfen Sie, ob die Datenschutzverlust-Abrechnungs-Dashboards Alarm schlagen, wenn die kumulative ε die Richtliniengrenzen überschreitet.
 #11.3.2    Level: 2    Role: V
 Überprüfen Sie, ob Black-Box-Datenschutzprüfungen ε̂ innerhalb von 10 % des angegebenen Werts schätzen.
 #11.3.3    Level: 3    Role: V
 Überprüfen Sie, dass formale Beweise alle nach dem Training durchgeführten Feinabstimmungen und Einbettungen abdecken.

---

### 11.4 Zweckbindung und Schutz vor Funktionsumfang-Überschreitung

 #11.4.1    Level: 1    Role: D
 Stellen Sie sicher, dass jeder Datensatz und jeder Modell-Checkpoint einen maschinenlesbaren Zweck-Tag trägt, der mit der ursprünglichen Einwilligung übereinstimmt.
 #11.4.2    Level: 1    Role: D/V
 Überprüfen Sie, ob Laufzeitüberwachungen Abfragen erkennen, die mit dem erklärten Zweck unvereinbar sind, und eine sanfte Verweigerung auslösen.
 #11.4.3    Level: 3    Role: D
 Überprüfen Sie, dass Richtlinien-als-Code-Gates die erneute Bereitstellung von Modellen in neuen Domänen ohne DPIA-Prüfung blockieren.
 #11.4.4    Level: 3    Role: V
 Verifizieren Sie, dass formale Nachverfolgbarkeitsnachweise zeigen, dass jeder Lebenszyklus personenbezogener Daten innerhalb des einwilligungsbasierten Rahmens bleibt.

---

### 11.5 Einwilligungsverwaltung und rechtmäßige Grundlage für Tracking

 #11.5.1    Level: 1    Role: D/V
 Überprüfen Sie, ob eine Consent-Management-Plattform (CMP) den Opt-in-Status, den Zweck und die Aufbewahrungsdauer für jede betroffene Person erfasst.
 #11.5.2    Level: 2    Role: D
 Überprüfen Sie, dass APIs Zustimmungs-Token bereitstellen; Modelle müssen den Token-Bereich vor der Inferenz validieren.
 #11.5.3    Level: 2    Role: D/V
 Verifizieren Sie, dass verweigerte oder widerrufene Einwilligungen die Verarbeitungspipelines innerhalb von 24 Stunden stoppen.

---

### 11.6 Föderiertes Lernen mit Datenschutzkontrollen

 #11.6.1    Level: 1    Role: D
 Überprüfen Sie, dass Client-Updates vor der Aggregation eine lokale Differential Privacy-Rauschzugabe verwenden.
 #11.6.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Trainingsmetriken differenziell privat sind und niemals den Verlust eines einzelnen Clients offenlegen.
 #11.6.3    Level: 2    Role: V
 Stellen Sie sicher, dass eine gegen Manipulation resistente Aggregation (z. B. Krum/Trimmed-Mean) aktiviert ist.
 #11.6.4    Level: 3    Role: V
 Überprüfen Sie, dass formale Beweise das gesamte ε-Budget mit weniger als 5 Nutzungsverlusten nachweisen.

---

#### Referenzen

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Überwachung, Protokollierung und Anomalieerkennung

### Kontrollziel

Dieser Abschnitt enthält Anforderungen für die Bereitstellung von Echtzeit- und forensischer Transparenz darüber, was das Modell und andere KI-Komponenten sehen, tun und zurückgeben, damit Bedrohungen erkannt, priorisiert und daraus gelernt werden kann.

### C12.1 Anfrage- und Antwortprotokollierung

 #12.1.1    Level: 1    Role: D/V
 Verifizieren Sie, dass alle Benutzeranfragen und Modellantworten mit den entsprechenden Metadaten (z. B. Zeitstempel, Benutzer-ID, Sitzungs-ID, Modellversion) protokolliert werden.
 #12.1.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Protokolle in sicheren, zugangsgesteuerten Repositorys mit geeigneten Aufbewahrungsrichtlinien und Sicherungsverfahren gespeichert werden.
 #12.1.3    Level: 1    Role: D/V
 Überprüfen Sie, ob Log-Speichersysteme Verschlüsselung im Ruhezustand und während der Übertragung implementieren, um sensible Informationen in den Protokollen zu schützen.
 #12.1.4    Level: 1    Role: D/V
 Stellen Sie sicher, dass sensible Daten in Eingabeaufforderungen und Ausgaben vor dem Protokollieren automatisch geschwärzt oder maskiert werden, mit konfigurierbaren Schwärzungsregeln für personenbezogene Daten (PII), Zugangsdaten und geschützte Informationen.
 #12.1.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Richtlinienentscheidungen und Sicherheitsfiltermaßnahmen mit ausreichenden Details protokolliert werden, um eine Prüfung und Fehlerbehebung von Inhaltsmoderationssystemen zu ermöglichen.
 #12.1.6    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Integrität der Protokolle durch z.B. kryptografische Signaturen oder schreibgeschützten Speicher geschützt ist.

---

### C12.2 Missbrauchserkennung und Alarmierung

 #12.2.1    Level: 1    Role: D/V
 Überprüfen Sie, ob das System bekannte Jailbreak-Muster, Prompt-Injection-Versuche und adversariale Eingaben mithilfe einer signaturbasierten Erkennung erkennt und meldet.
 #12.2.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass das System in bestehende Security Information and Event Management (SIEM)-Plattformen mittels standardisierter Protokollformate und -protokolle integriert wird.
 #12.2.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass angereicherte Sicherheitsereignisse KI-spezifische Kontexte wie Modellkennungen, Vertrauenswerte und Entscheidungen des Sicherheitsfilters enthalten.
 #12.2.4    Level: 2    Role: D/V
 Überprüfen Sie, ob die verhaltensbasierte Anomalieerkennung ungewöhnliche Gesprächsmuster, übermäßige Wiederholungsversuche oder systematische Sondierungsverhalten identifiziert.
 #12.2.5    Level: 2    Role: D/V
 Stellen Sie sicher, dass Echtzeit-Benachrichtigungsmechanismen Sicherheitsteams informieren, wenn potenzielle Richtlinienverstöße oder Angriffsversuche erkannt werden.
 #12.2.6    Level: 2    Role: D/V
 Überprüfen Sie, ob benutzerdefinierte Regeln enthalten sind, um KI-spezifische Bedrohungsmuster zu erkennen, einschließlich koordinierter Jailbreak-Versuche, Prompt-Injektionskampagnen und Modell-Extraktionsangriffe.
 #12.2.7    Level: 3    Role: D/V
 Überprüfen Sie, dass automatisierte Incident-Response-Workflows kompromittierte Modelle isolieren, bösartige Benutzer blockieren und kritische Sicherheitsereignisse eskalieren können.

---

### C12.3 Modell-Abweichungserkennung

 #12.3.1    Level: 1    Role: D/V
 Überprüfen Sie, ob das System grundlegende Leistungskennzahlen wie Genauigkeit, Vertrauenswerte, Latenzzeiten und Fehlerraten über verschiedene Modellversionen und Zeiträume hinweg verfolgt.
 #12.3.2    Level: 2    Role: D/V
 Überprüfen Sie, ob automatisierte Warnmeldungen ausgelöst werden, wenn Leistungskennzahlen vordefinierte Verschlechterungsschwellen überschreiten oder erheblich von den Basiswerten abweichen.
 #12.3.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die Halluzinationserkennungsmonitore Instanzen identifizieren und markieren, wenn Modellausgaben faktisch inkorrekte, inkonsistente oder erfundene Informationen enthalten.

---

### C12.4 Leistungs- und Verhaltens-Telemetrie

 #12.4.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Betriebsmetriken wie Anforderungsverzögerung, Token-Verbrauch, Speicherverbrauch und Durchsatz kontinuierlich erfasst und überwacht werden.
 #12.4.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Erfolgs- und Fehlerraten mit Kategorisierung der Fehlertypen und deren Ursachen erfasst werden.
 #12.4.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Überwachung der Ressourcennutzung die Nutzung von GPU/CPU, den Speicherverbrauch und die Speicheranforderungen umfasst, mit Alarmierung bei Überschreitung von Schwellenwerten.

---

### C12.5 KI-Vorfallreaktionsplanung und -durchführung

 #12.5.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Vorfallreaktionspläne speziell AI-bezogene Sicherheitsvorfälle wie Modellkompromittierung, Datenvergiftung und adversariale Angriffe abdecken.
 #12.5.2    Level: 2    Role: D/V
 Stellen Sie sicher, dass Vorfallreaktionsteams Zugriff auf KI-spezifische forensische Werkzeuge und Expertenwissen haben, um das Modellverhalten und Angriffsvektoren zu untersuchen.
 #12.5.3    Level: 3    Role: D/V
 Überprüfen Sie, ob die Nachanalyse des Vorfalls Überlegungen zur Modellnachschulung, Aktualisierungen der Sicherheitsfilter und die Integration der gewonnenen Erkenntnisse in die Sicherheitskontrollen beinhaltet.

---

### C12.5 Erkennung der Leistungsverschlechterung von KI

Überwachen und erkennen Sie eine Verschlechterung der Leistung und Qualität von KI-Modellen im Laufe der Zeit.

 #12.5.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass Modellgenauigkeit, Präzision, Recall und F1-Werte kontinuierlich überwacht und mit den Basisgrenzwerten verglichen werden.
 #12.5.2    Level: 1    Role: D/V
 Überprüfen Sie, ob die Erkennung von Datenverschiebungen Änderungen in der Eingabeverteilung überwacht, die die Modellleistung beeinflussen können.
 #12.5.3    Level: 2    Role: D/V
 Überprüfen Sie, ob die Erkennung von Konzeptdrift Änderungen in der Beziehung zwischen Eingaben und erwarteten Ausgaben identifiziert.
 #12.5.4    Level: 2    Role: D/V
 Überprüfen Sie, ob Leistungsverluste automatisierte Warnmeldungen auslösen und Workflows zur Neuerstellung oder zum Ersatz des Modells einleiten.
 #12.5.5    Level: 3    Role: V
 Überprüfen Sie, ob die Ursachenanalyse für Leistungsabfälle Leistungsabfälle mit Datenänderungen, Infrastrukturproblemen oder externen Faktoren korreliert.

---

### C12.6 DAG-Visualisierung & Workflow-Sicherheit

Schützen Sie Workflow-Visualisierungssysteme vor Informationslecks und Manipulationsangriffen.

 #12.6.1    Level: 1    Role: D/V
 Überprüfen Sie, ob die DAG-Visualisierungsdaten bereinigt werden, um sensible Informationen vor der Speicherung oder Übertragung zu entfernen.
 #12.6.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Zugriffssteuerungen zur Workflow-Visualisierung gewährleisten, dass nur autorisierte Benutzer Agenten-Entscheidungspfade und Begründungsspuren einsehen können.
 #12.6.3    Level: 2    Role: D/V
 Stellen Sie sicher, dass die Integrität der DAG-Daten durch kryptografische Signaturen und manipulationssichere Speichermethoden geschützt ist.
 #12.6.4    Level: 2    Role: D/V
 Überprüfen Sie, ob Workflow-Visualisierungssysteme eine Eingabeverifizierung implementieren, um Injektionsangriffe durch manipulierte Knoten- oder Kantendaten zu verhindern.
 #12.6.5    Level: 3    Role: D/V
 Überprüfen Sie, dass Echtzeit-DAG-Aktualisierungen eine Ratenbegrenzung und Validierung unterliegen, um Denial-of-Service-Angriffe auf Visualisierungssysteme zu verhindern.

---

### C12.7 Proaktives Überwachen des Sicherheitsverhaltens

Erkennung und Verhinderung von Sicherheitsbedrohungen durch proaktive Analyse des Agentenverhaltens.

 #12.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass proaktive Agentenverhalten vor der Ausführung sicherheitsvalidiert werden, indem eine Risikobewertung integriert wird.
 #12.7.2    Level: 2    Role: D/V
 Überprüfen Sie, ob autonome Initiativauslöser die Bewertung des Sicherheitskontexts und die Analyse der Bedrohungslandschaft umfassen.
 #12.7.3    Level: 2    Role: D/V
 Überprüfen Sie, ob proaktive Verhaltensmuster auf potenzielle Sicherheitsimplikationen und unbeabsichtigte Folgen analysiert werden.
 #12.7.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass sicherheitskritische proaktive Maßnahmen explizite Genehmigungsketten mit Audit-Trails erfordern.
 #12.7.5    Level: 3    Role: D/V
 Überprüfen Sie, ob die Verhaltensanomalieerkennung Abweichungen in den Mustern proaktiver Agenten identifiziert, die auf eine Kompromittierung hinweisen könnten.

---

### Literaturverzeichnis

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Menschliche Aufsicht, Rechenschaftspflicht und Governance

### Kontrollziel

Dieses Kapitel enthält Anforderungen zur Aufrechterhaltung der menschlichen Aufsicht und klarer Verantwortlichkeitsketten in KI-Systemen und stellt Erklärbarkeit, Transparenz und ethische Führung im gesamten KI-Lebenszyklus sicher.

---

### C13.1 Not-Aus- und Überschreibemechanismen

Stellen Sie Abschalt- oder Rücksetzwege bereit, wenn unsicheres Verhalten des KI-Systems beobachtet wird.

 #13.1.1    Level: 1    Role: D/V
 Verifizieren Sie, dass ein manueller Notausschalter vorhanden ist, um die Inferenz und Ausgabe des KI-Modells sofort zu stoppen.
 #13.1.2    Level: 1    Role: D
 Stellen Sie sicher, dass Override-Steuerungen nur für autorisiertes Personal zugänglich sind.
 #13.1.3    Level: 3    Role: D/V
 Überprüfen Sie, dass Rücksetzverfahren zu vorherigen Modellversionen oder zum sicheren Betriebsmodus zurückkehren können.
 #13.1.4    Level: 3    Role: V
 Stellen Sie sicher, dass Übersteuerungsmechanismen regelmäßig getestet werden.

---

### C13.2 Mensch-im-Loop Entscheidungsprüfpunkte

Erfordern Sie menschliche Genehmigungen, wenn die Einsätze vordefinierte Risikoschwellen überschreiten.

 #13.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass KI-Entscheidungen mit hohem Risiko vor der Ausführung eine ausdrückliche menschliche Genehmigung erfordern.
 #13.2.2    Level: 1    Role: D
 Stellen Sie sicher, dass Risikoschwellenwerte klar definiert sind und automatisch menschliche Überprüfungsabläufe auslösen.
 #13.2.3    Level: 2    Role: D
 Stellen Sie sicher, dass zeitkritische Entscheidungen über Ausweichverfahren verfügen, wenn eine menschliche Genehmigung innerhalb der erforderlichen Zeitrahmen nicht eingeholt werden kann.
 #13.2.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass Eskalationsverfahren klare Autoritätsstufen für verschiedene Entscheidungstypen oder Risikokategorien definieren, falls zutreffend.

---

### C13.3 Verantwortlichkeitskette & Prüfbarkeit

Protokollieren Sie Bedieneraktionen und Modellentscheidungen.

 #13.3.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass alle Entscheidungen des KI-Systems und menschliche Interventionen mit Zeitstempeln, Benutzeridentitäten und Entscheidungsbegründungen protokolliert werden.
 #13.3.2    Level: 2    Role: D
 Stellen Sie sicher, dass Audit-Logs nicht manipuliert werden können und Integritätsprüfmechanismen enthalten.

---

### C13.4 Erklärbare KI-Techniken

Oberflächenmerkmal-Wichtigkeit, Gegenfaktische und lokale Erklärungen.

 #13.4.1    Level: 1    Role: D/V
 Überprüfen Sie, ob KI-Systeme grundlegende Erklärungen für ihre Entscheidungen in einem für Menschen lesbaren Format bereitstellen.
 #13.4.2    Level: 2    Role: V
 Stellen Sie sicher, dass die Qualität der Erklärung durch menschliche Evaluationsstudien und Metriken validiert wird.
 #13.4.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass Merkmalswichtigkeitswerte oder Attributionsmethoden (SHAP, LIME usw.) für kritische Entscheidungen verfügbar sind.
 #13.4.4    Level: 3    Role: V
 Überprüfen Sie, ob kontrafaktische Erklärungen zeigen, wie Eingaben geändert werden könnten, um Ergebnisse zu verändern, falls dies auf den Anwendungsfall und die Domäne zutrifft.

---

### C13.5 Modellkarten & Nutzungshinweise

Pflegen Sie Modellkarten für die beabsichtigte Nutzung, Leistungsmetriken und ethische Überlegungen.

 #13.5.1    Level: 1    Role: D
 Verifizieren Sie, dass Modellkarten die beabsichtigten Anwendungsfälle, Einschränkungen und bekannten Ausfallmodi dokumentieren.
 #13.5.2    Level: 1    Role: D/V
 Stellen Sie sicher, dass Leistungskennzahlen für verschiedene anwendbare Anwendungsfälle offengelegt werden.
 #13.5.3    Level: 2    Role: D
 Stellen Sie sicher, dass ethische Überlegungen, Bewertungen von Verzerrungen, Fairness-Analysen, Merkmale der Trainingsdaten und bekannte Einschränkungen der Trainingsdaten dokumentiert und regelmäßig aktualisiert werden.
 #13.5.4    Level: 2    Role: D/V
 Stellen Sie sicher, dass Modellkarten versionskontrolliert sind und während des gesamten Modelllebenszyklus mit Änderungsverfolgung gepflegt werden.

---

### C13.6 Unsicherheitsquantifizierung

Verbreiten Sie Vertrauenswerte oder Entropie-Maße in den Antworten.

 #13.6.1    Level: 1    Role: D
 Überprüfen Sie, ob KI-Systeme mit ihren Ausgaben Vertrauenswerte oder Unsicherheitsmaße bereitstellen.
 #13.6.2    Level: 2    Role: D/V
 Überprüfen Sie, ob Unsicherheitsschwellenwerte eine zusätzliche menschliche Überprüfung oder alternative Entscheidungswege auslösen.
 #13.6.3    Level: 2    Role: V
 Überprüfen Sie, ob Unsicherheitsquantifizierungsmethoden kalibriert sind und anhand von Referenzdaten validiert werden.
 #13.6.4    Level: 3    Role: D/V
 Stellen Sie sicher, dass die Unsicherheitsfortpflanzung durch mehrstufige KI-Workflows erhalten bleibt.

---

### C13.7 Benutzerorientierte Transparenzberichte

Stellen Sie regelmäßige Offenlegungen zu Vorfällen, Drift und Datennutzung bereit.

 #13.7.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Richtlinien zur Datennutzung und die Praktiken zum Management der Nutzereinwilligung klar an die Beteiligten kommuniziert werden.
 #13.7.2    Level: 2    Role: D/V
 Überprüfen Sie, dass KI-Auswirkungsbewertungen durchgeführt werden und die Ergebnisse in die Berichterstattung einfließen.
 #13.7.3    Level: 2    Role: D/V
 Überprüfen Sie, ob regelmäßig veröffentlichte Transparenzberichte KI-Vorfälle und Betriebskennzahlen in angemessenem Detail offenlegen.

#### Referenzen

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Anhang A: Glossar

Dieses umfassende Glossar liefert Definitionen wichtiger Begriffe aus den Bereichen KI, ML und Sicherheit, die im gesamten AISVS verwendet werden, um Klarheit und ein gemeinsames Verständnis zu gewährleisten.
​
Adversariales Beispiel: Eine absichtlich gestaltete Eingabe, die ein KI-Modell dazu bringt, einen Fehler zu machen, oft durch Hinzufügen subtiler Störungen, die für Menschen nicht wahrnehmbar sind.
​
Adversarielle Robustheit – Adversarielle Robustheit in der KI bezeichnet die Fähigkeit eines Modells, seine Leistung aufrechtzuerhalten und resistent dagegen zu sein, durch absichtlich gestaltete, bösartige Eingaben, die Fehler verursachen sollen, getäuscht oder manipuliert zu werden.
​
Agent – KI-Agenten sind Softwaresysteme, die KI nutzen, um Ziele zu verfolgen und Aufgaben im Auftrag von Nutzern zu erledigen. Sie zeigen Fähigkeiten wie Schlussfolgern, Planen und Erinnern und verfügen über ein Maß an Autonomie, um Entscheidungen zu treffen, zu lernen und sich anzupassen.
​
Agentische KI: KI-Systeme, die mit einem gewissen Grad an Autonomie agieren können, um Ziele zu erreichen, häufig Entscheidungen treffen und Maßnahmen ergreifen, ohne direkte menschliche Intervention.
​
Attributbasierte Zugriffskontrolle (ABAC): Ein Zugriffskontrollparadigma, bei dem Autorisierungsentscheidungen auf Attributen des Benutzers, der Ressource, der Aktion und der Umgebung basieren und zur Abfragezeit bewertet werden.
​
Backdoor-Angriff: Eine Art von Datenvergiftungsangriff, bei dem das Modell darauf trainiert wird, auf bestimmte Auslöser auf eine spezifische Weise zu reagieren, während es sich ansonsten normal verhält.
​
Bias: Systematische Fehler in den Ausgaben von KI-Modellen, die zu unfairen oder diskriminierenden Ergebnissen für bestimmte Gruppen oder in spezifischen Kontexten führen können.
​
Bias-Ausnutzung: Eine Angriffstechnik, die bekannte Verzerrungen in KI-Modellen ausnutzt, um Ausgaben oder Ergebnisse zu manipulieren.
​
Cedar: Amazons Richtliniensprache und -motor für fein abgestufte Berechtigungen, die bei der Implementierung von ABAC für KI-Systeme verwendet wird.
​
Gedankenkette: Eine Technik zur Verbesserung des Denkvermögens in Sprachmodellen, bei der Zwischenschritte des Denkprozesses erzeugt werden, bevor eine endgültige Antwort gegeben wird.
​
Circuit Breaker: Mechanismen, die den Betrieb von KI-Systemen automatisch stoppen, wenn bestimmte Risikoschwellen überschritten werden.
​
Datenleckage: Unbeabsichtigte Offenlegung sensibler Informationen durch die Ausgaben oder das Verhalten von KI-Modellen.
​
Datenvergiftung: Die absichtliche Korruption von Trainingsdaten, um die Modellintegrität zu beeinträchtigen, häufig um Hintertüren einzubauen oder die Leistung zu verschlechtern.
​
Differenzielle Privatsphäre – Differenzielle Privatsphäre ist ein mathematisch rigoroser Rahmen zur Veröffentlichung statistischer Informationen über Datensätze, während die Privatsphäre einzelner Datenpersonen geschützt wird. Sie ermöglicht einem Dateninhaber, aggregierte Muster der Gruppe zu teilen und gleichzeitig die Weitergabe von Informationen über einzelne Personen zu begrenzen.
​
Einbettungen: Dichtere Vektor-Darstellungen von Daten (Text, Bilder usw.), die semantische Bedeutungen in einem hochdimensionalen Raum erfassen.
​
Erklärbarkeit – Erklärbarkeit in der KI ist die Fähigkeit eines KI-Systems, für seine Entscheidungen und Vorhersagen nachvollziehbare Gründe zu liefern und Einblicke in seine inneren Abläufe zu geben.
​
Erklärbare KI (XAI): KI-Systeme, die entwickelt wurden, um durch verschiedene Techniken und Rahmenwerke menschenverständliche Erklärungen für ihre Entscheidungen und ihr Verhalten zu liefern.
​
Föderiertes Lernen: Ein Ansatz des maschinellen Lernens, bei dem Modelle über mehrere dezentralisierte Geräte mit lokalen Datensätzen trainiert werden, ohne die Daten selbst auszutauschen.
​
Leitplanken: Einschränkungen, die implementiert werden, um zu verhindern, dass KI-Systeme schädliche, voreingenommene oder anderweitig unerwünschte Ergebnisse erzeugen.
​
Halluzination – Eine KI-Halluzination bezeichnet ein Phänomen, bei dem ein KI-Modell falsche oder irreführende Informationen generiert, die weder auf seinen Trainingsdaten noch auf der tatsächlichen Realität basieren.
​
Mensch-in-der-Schleife (HITL): Systeme, die darauf ausgelegt sind, menschliche Aufsicht, Überprüfung oder Eingriffe an entscheidenden Entscheidungspunkten zu erfordern.
​
Infrastructure as Code (IaC): Verwaltung und Bereitstellung von Infrastruktur durch Code anstelle manueller Prozesse, wodurch Sicherheitsüberprüfungen und konsistente Bereitstellungen ermöglicht werden.
​
Jailbreak: Techniken, die verwendet werden, um Sicherheitsvorkehrungen in KI-Systemen, insbesondere bei großen Sprachmodellen, zu umgehen und verbotene Inhalte zu erzeugen.
​
Least Privilege: Das Sicherheitsprinzip, nur die minimal notwendigen Zugriffsrechte für Benutzer und Prozesse zu gewähren.
​
LIME (Lokale Interpretable Modell-agnostische Erklärungen): Eine Technik zur Erklärung der Vorhersagen beliebiger maschineller Lernklassifikatoren durch lokale Annäherung mit einem interpretierbaren Modell.
​
Mitgliedschafts-Inferenzangriff: Ein Angriff, der darauf abzielt zu bestimmen, ob ein bestimmter Datenpunkt zum Trainieren eines Machine-Learning-Modells verwendet wurde.
​
MITRE ATLAS: Bedrohungslandschaft für künstliche Intelligenzsysteme durch gegnerische Angriffe; eine Wissensdatenbank zu gegnerischen Taktiken und Techniken gegen KI-Systeme.
​
Modellkarte – Eine Modellkarte ist ein Dokument, das standardisierte Informationen über die Leistung, Einschränkungen, vorgesehenen Anwendungen und ethischen Überlegungen eines KI-Modells bereitstellt, um Transparenz und verantwortungsbewusste KI-Entwicklung zu fördern.
​
Modellauslesung: Ein Angriff, bei dem ein Angreifer wiederholt Anfragen an ein Zielmodell stellt, um ohne Autorisierung eine funktional ähnliche Kopie zu erstellen.
​
Modellinversion: Ein Angriff, der versucht, Trainingsdaten durch Analyse der Modellausgaben zu rekonstruieren.
​
Modell-Lebenszyklus-Management – Das AI Modell-Lebenszyklus-Management ist der Prozess der Überwachung aller Phasen der Existenz eines KI-Modells, einschließlich Design, Entwicklung, Bereitstellung, Überwachung, Wartung und schließlich der Außerdienststellung, um sicherzustellen, dass es effektiv bleibt und mit den Zielen übereinstimmt.
​
Modellvergiftung: Direkte Einführung von Schwachstellen oder Hintertüren in ein Modell während des Trainingsprozesses.
​
Modell-Diebstahl/-Entwendung: Das Extrahieren einer Kopie oder einer Annäherung eines proprietären Modells durch wiederholte Abfragen.
​
Multi-Agenten-System: Ein System, das aus mehreren interagierenden KI-Agenten besteht, die jeweils unterschiedliche Fähigkeiten und Ziele haben können.
​
OPA (Open Policy Agent): Eine Open-Source-Policy-Engine, die eine einheitliche Durchsetzung von Richtlinien über den gesamten Stack hinweg ermöglicht.
​
Datenschutzfreundliches Maschinelles Lernen (PPML): Techniken und Methoden zur Schulung und Bereitstellung von ML-Modellen unter Wahrung der Privatsphäre der Trainingsdaten.
​
Prompt Injection: Ein Angriff, bei dem bösartige Anweisungen in Eingaben eingebettet werden, um das beabsichtigte Verhalten eines Modells zu überschreiben.
​
RAG (Retrieval-Augmented Generation): Eine Technik, die große Sprachmodelle verbessert, indem sie relevante Informationen aus externen Wissensquellen abruft, bevor eine Antwort generiert wird.
​
Red-Teaming: Die Praxis, KI-Systeme aktiv zu testen, indem simulierte Angriffsszenarien verwendet werden, um Schwachstellen zu identifizieren.
​
SBOM (Software-Stückliste): Ein formeller Nachweis, der die Details und Lieferkettenbeziehungen verschiedener Komponenten enthält, die beim Erstellen von Software oder KI-Modellen verwendet werden.
​
SHAP (SHapley Additive exPlanations): Ein spieltheoretischer Ansatz zur Erklärung der Ausgabe eines beliebigen Machine-Learning-Modells, indem der Beitrag jeder Merkmalvariable zur Vorhersage berechnet wird.
​
Lieferkettenangriff: Kompromittierung eines Systems durch gezielte Angriffe auf weniger sichere Elemente in seiner Lieferkette, wie beispielsweise Drittanbieter-Bibliotheken, Datensätze oder vortrainierte Modelle.
​
Transferlernen: Eine Technik, bei der ein für eine Aufgabe entwickeltes Modell als Ausgangspunkt für ein Modell einer zweiten Aufgabe wiederverwendet wird.
​
Vektordatenbank: Eine spezialisierte Datenbank, die zur Speicherung hochdimensionaler Vektoren (Einbettungen) entwickelt wurde und effiziente Ähnlichkeitssuchen durchführt.
​
Schwachstellen-Scannen: Automatisierte Werkzeuge, die bekannte Sicherheitslücken in Softwarekomponenten, einschließlich KI-Frameworks und Abhängigkeiten, identifizieren.
​
Wasserzeichen: Techniken, um nicht wahrnehmbare Markierungen in KI-generierte Inhalte einzubetten, um deren Ursprung zu verfolgen oder die KI-Generierung zu erkennen.
​
Zero-Day-Schwachstelle: Eine zuvor unbekannte Schwachstelle, die Angreifer ausnutzen können, bevor Entwickler einen Fix erstellen und bereitstellen.

## Anhang B: Literaturverzeichnis

### TODO

## Anhang C: KI-Sicherheits-Governance und Dokumentation

### Zielsetzung

Dieser Anhang enthält grundlegende Anforderungen für die Einrichtung von Organisationsstrukturen, Richtlinien und Prozessen zur Steuerung der KI-Sicherheit während des gesamten Systemlebenszyklus.

---

### AC.1 Einführung des KI-Risikomanagement-Rahmenwerks

Bieten Sie einen formalen Rahmen zur Identifizierung, Bewertung und Minderung von KI-spezifischen Risiken über den gesamten Systemlebenszyklus hinweg.

 #AC.1.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass eine auf KI spezialisierte Risikobewertungsmethodik dokumentiert und umgesetzt ist.
 #AC.1.2    Level: 2    Role: D
 Stellen Sie sicher, dass Risikoanalysen an wichtigen Punkten im KI-Lebenszyklus und vor wesentlichen Änderungen durchgeführt werden.
 #AC.1.3    Level: 3    Role: D/V
 Überprüfen Sie, ob das Risikomanagementframework mit etablierten Standards (z. B. NIST AI RMF) übereinstimmt.

---

### AC.2 KI-Sicherheitsrichtlinie & -verfahren

Definieren und Durchsetzen organisatorischer Standards für die sichere Entwicklung, Bereitstellung und den Betrieb von KI.

 #AC.2.1    Level: 1    Role: D/V
 Überprüfen Sie, ob dokumentierte KI-Sicherheitsrichtlinien vorhanden sind.
 #AC.2.2    Level: 2    Role: D
 Stellen Sie sicher, dass Richtlinien mindestens einmal jährlich und nach wesentlichen Änderungen der Bedrohungslage überprüft und aktualisiert werden.
 #AC.2.3    Level: 3    Role: D/V
 Überprüfen Sie, ob die Richtlinien alle AISVS-Kategorien und die anwendbaren gesetzlichen Anforderungen abdecken.

---

### AC.3 Rollen und Verantwortlichkeiten für KI-Sicherheit

Stellen Sie klare Verantwortlichkeiten für die KI-Sicherheit in der gesamten Organisation sicher.

 #AC.3.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass die Rollen und Verantwortlichkeiten im Bereich KI-Sicherheit dokumentiert sind.
 #AC.3.2    Level: 2    Role: D
 Überprüfen Sie, ob die verantwortlichen Personen über die entsprechende Sicherheitsexpertise verfügen.
 #AC.3.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass ein Ethikkomitee für KI oder ein Governance-Gremium für KI-Systeme mit hohem Risiko eingerichtet ist.

---

### AC.4 Durchsetzung ethischer KI-Richtlinien

Stellen Sie sicher, dass KI-Systeme gemäß den festgelegten ethischen Grundsätzen arbeiten.

 #AC.4.1    Level: 1    Role: D/V
 Überprüfen Sie, ob ethische Richtlinien für die Entwicklung und den Einsatz von KI existieren.
 #AC.4.2    Level: 2    Role: D
 Stellen Sie sicher, dass Mechanismen zur Erkennung und Meldung ethischer Verstöße vorhanden sind.
 #AC.4.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass regelmäßige ethische Überprüfungen der eingesetzten KI-Systeme durchgeführt werden.

---

### AC.5 Überwachung der Einhaltung von KI-Vorschriften

Behalten Sie die Einhaltung und Entwicklungen von KI-Vorschriften im Auge.

 #AC.5.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Prozesse existieren, um anwendbare KI-Vorschriften zu identifizieren.
 #AC.5.2    Level: 2    Role: D
 Stellen Sie sicher, dass die Einhaltung aller gesetzlichen Vorschriften bewertet wird.
 #AC.5.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass regulatorische Änderungen rechtzeitige Überprüfungen und Aktualisierungen von KI-Systemen auslösen.

#### Quellenangaben

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Anhang D: KI-gestützte Governance und Verifizierung sicherer Programmierung

### Zielsetzung

Dieses Kapitel definiert grundlegende organisatorische Kontrollen für die sichere und effektive Nutzung von KI-unterstützten Codierwerkzeugen während der Softwareentwicklung und gewährleistet Sicherheit und Nachverfolgbarkeit über den gesamten SDLC hinweg.

---

### AD.1 KI-unterstützter Workflow für sicheres Programmieren

Integrieren Sie KI-Tools in den sicheren Software-Entwicklungslebenszyklus (Secure Software Development Lifecycle, SSDLC) der Organisation, ohne die bestehenden Sicherheitsbarrieren zu schwächen.

 #AD.1.1    Level: 1    Role: D/V
 Überprüfen Sie, ob ein dokumentierter Arbeitsablauf beschreibt, wann und wie KI-Werkzeuge Code generieren, refaktorieren oder überprüfen können.
 #AD.1.2    Level: 2    Role: D
 Überprüfen Sie, ob der Workflow jeder Phase des sicheren Softwareentwicklungszyklus (SSDLC) zugeordnet ist (Design, Implementierung, Code-Überprüfung, Testen, Bereitstellung).
 #AD.1.3    Level: 3    Role: D/V
 Überprüfen Sie, ob Metriken (z. B. Verwundbarkeitsdichte, mittlere Erkennungszeit) für AI-erzeugten Code erfasst und mit rein menschlichen Referenzwerten verglichen werden.

---

### AD.2 KI-Werkzeugqualifikation & Bedrohungsmodellierung

Stellen Sie sicher, dass KI-Codierungswerkzeuge vor der Einführung auf Sicherheitsfunktionen, Risiken und Auswirkungen auf die Lieferkette bewertet werden.

 #AD.2.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass ein Bedrohungsmodell für jedes KI-Tool Missbrauch, Modell-Inversion, Datenleckage und Risiken in der Abhängigkeitskette identifiziert.
 #AD.2.2    Level: 2    Role: D
 Stellen Sie sicher, dass Toolbewertungen statische/dynamische Analysen aller lokalen Komponenten sowie die Bewertung von SaaS-Endpunkten (TLS, Authentifizierung/Autorisierung, Protokollierung) umfassen.
 #AD.2.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass Bewertungen einem anerkannten Rahmenwerk folgen und nach größeren Versionsänderungen erneut durchgeführt werden.

---

### AD.3 Sicheres Prompt- und Kontextmanagement

Verhindern Sie das Austreten von Geheimnissen, proprietärem Code und persönlichen Daten beim Erstellen von Eingabeaufforderungen oder Kontexten für KI-Modelle.

 #AD.3.1    Level: 1    Role: D/V
 Verifizieren Sie, dass schriftliche Richtlinien das Senden von Geheimnissen, Zugangsdaten oder geheimen Informationen in Eingabeaufforderungen untersagen.
 #AD.3.2    Level: 2    Role: D
 Überprüfen Sie, ob technische Kontrollen (Redaktion auf der Client-Seite, genehmigte Kontextfilter) automatisch sensible Artefakte entfernen.
 #AD.3.3    Level: 3    Role: D/V
 Verifizieren Sie, dass Aufforderungen und Antworten tokenisiert, während der Übertragung und im Ruhezustand verschlüsselt sind und die Aufbewahrungsfristen den Richtlinien zur Datenklassifizierung entsprechen.

---

### AD.4 Validierung von KI-generiertem Code

Erkennen und Beheben von Schwachstellen, die durch KI-Ausgaben eingeführt wurden, bevor der Code zusammengeführt oder bereitgestellt wird.

 #AD.4.1    Level: 1    Role: D/V
 Stellen Sie sicher, dass von KI generierter Code stets einer manuellen Codeüberprüfung unterzogen wird.
 #AD.4.2    Level: 2    Role: D
 Stellen Sie sicher, dass automatisierte Scanner (SAST/IAST/DAST) bei jedem Pull Request mit KI-generiertem Code ausgeführt werden und bei kritischen Befunden die Zusammenführungen blockieren.
 #AD.4.3    Level: 3    Role: D/V
 Überprüfen Sie, dass differenzielles Fuzz-Testing oder eigenschaftsbasierte Tests sicherheitskritische Verhaltensweisen (z. B. Eingabevalidierung, Autorisierungslogik) nachweisen.

---

### AD.5 Erklärbarkeit und Rückverfolgbarkeit von Codevorschlägen

Bieten Sie Prüfern und Entwicklern Einblick darin, warum ein Vorschlag gemacht wurde und wie er sich entwickelt hat.

 #AD.5.1    Level: 1    Role: D/V
 Überprüfen Sie, ob Prompt-/Antwortpaare mit Commit-IDs protokolliert werden.
 #AD.5.2    Level: 2    Role: D
 Überprüfen Sie, ob Entwickler Modellquellen (Trainingsausschnitte, Dokumentation) anzeigen können, die eine Vorschlag unterstützen.
 #AD.5.3    Level: 3    Role: D/V
 Stellen Sie sicher, dass Erklärbarkeitsberichte zusammen mit Design-Artefakten gespeichert und in Sicherheitsbewertungen referenziert werden, um die Rückverfolgbarkeitsprinzipien der ISO/IEC 42001 zu erfüllen.

---

### AD.6 Kontinuierliches Feedback & Feinabstimmung des Modells

Verbessern Sie die Sicherheitsleistung des Modells im Laufe der Zeit, während Sie negative Abweichungen verhindern.

 #AD.6.1    Level: 1    Role: D/V
 Überprüfen Sie, dass Entwickler unsichere oder nicht konforme Vorschläge kennzeichnen können und dass diese Kennzeichnungen erfasst werden.
 #AD.6.2    Level: 2    Role: D
 Stellen Sie sicher, dass aggregiertes Feedback die periodische Feinabstimmung oder retrieval-unterstützte Generierung mit überprüften, sicherheitsorientierten Codierungs-Corpora (z. B. OWASP Cheat Sheets) informiert.
 #AD.6.3    Level: 3    Role: D/V
 Überprüfen Sie, dass ein Closed-Loop-Auswertungssystem nach jeder Feinabstimmung Regressionstests durchführt; Sicherheitsmetriken müssen vor der Bereitstellung frühere Baselines erreichen oder übertreffen.

---

#### Quellenangaben

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Anhang E: Beispielwerkzeuge und -frameworks

### Zielsetzung

Dieses Kapitel enthält Beispiele für Werkzeuge und Frameworks, die die Implementierung oder Erfüllung einer bestimmten AISVS-Anforderung unterstützen können. Diese sind nicht als Empfehlungen oder Befürwortungen durch das AISVS-Team oder das OWASP GenAI Security-Projekt zu verstehen.

---

### AE.1 Verwaltung von Trainingsdaten und Umgang mit Verzerrungen

Werkzeuge für Datenanalyse, Governance und Bias-Management.

 #AE.1.1    Section: 1.1
 Werkzeuge für die Dateninventarisierung: Werkzeuge zur Verwaltung der Dateninventarisierung wie...
 #AE.1.2    Section: 1.2
 Verschlüsselung während der Übertragung Verwenden Sie TLS für HTTPS-basierte Anwendungen, mit Tools wie openSSL und Pythons`ssl`Bibliothek.

---

### AE.2 Benutzer-Eingabevalidierung

Werkzeuge zur Verarbeitung und Validierung von Benutzereingaben.

 #AE.2.1    Section: 2.1
 Werkzeuge zur Abwehr von Prompt-Injektionen: Verwenden Sie Schutzmaßnahmen wie NVIDIA's NeMo oder Guardrails AI.

---

