# C3 Modell livscykelhantering och förändringskontroll

## Kontrollmål

AI-system måste implementera ändringskontrollprocesser som förhindrar obehöriga eller osäkra modelländringar från att nå produktion. Denna kontroll säkerställer modellens integritet genom hela livscykeln – från utveckling till distribution och till avveckling – vilket möjliggör snabb incidenthantering och upprätthåller ansvar för alla ändringar.

Kärnsäkerhetsmål: Endast auktoriserade, validerade modeller når produktion genom att använda kontrollerade processer som säkerställer integritet, spårbarhet och återhämtningsbarhet.

---

## C3.1 Modellautentisering och integritet

Endast auktoriserade modeller med verifierad integritet når produktionsmiljöer.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Verifiera att alla modellartefakter (vikter, konfigurationer, tokenizers) är kryptografiskt signerade av auktoriserade enheter innan distribution.                                                         |   1   | D/V  |
| 3.1.2 | Verifiera att modellens integritet valideras vid distribution och att fel vid signaturverifiering förhindrar modellinläsning.                                                                              |   1   | D/V  |
| 3.1.3 | Verifiera att modellens proveniensregister inkluderar en auktoriserande enhets identitet, checksummor för träningsdata, valideringstestresultat med godkänd/underkänd status, samt en skapandetidsstämpel. |   2   | D/V  |
| 3.1.4 | Verifiera att alla modellelement använder semantisk versionering (MAJOR.MINOR.PATCH) med dokumenterade kriterier som specificerar när varje versionskomponent ska ökas.                                    |   2   | D/V  |
| 3.1.5 | Verifiera att beroendehantering upprätthåller ett realtidslager som möjliggör snabb identifiering av alla förbrukande system.                                                                              |   2   |  V   |

---

## C3.2 Modellvalidering och testning

Modeller måste genomgå definierade säkerhets- och trygghetsvalideringar innan de tas i bruk.

|   #   | Description                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Verifiera att modeller genomgår automatiserad säkerhetstestning som inkluderar inmatningsvalidering, utmatningssanering och säkerhetsutvärderingar med förhandsöverenskomna organisatoriska godkännande-/underkännandetrösklar innan de tas i bruk. |   1   | D/V  |
| 3.2.2 | Verifiera att valideringsfel automatiskt blockerar modellimplementering efter uttryckligt godkännande från förutbestämda behöriga personer med dokumenterade affärsskäl.                                                                            |   1   | D/V  |
| 3.2.3 | Verifiera att testresultaten är kryptografiskt signerade och oföränderligt kopplade till den specifika modellversionshash som valideras.                                                                                                            |   2   |  V   |
| 3.2.4 | Verifiera att nödsituationer kräver dokumenterad säkerhetsriskbedömning och godkännande från en förutbestämd säkerhetsmyndighet inom förhandsöverenskomna tidsramar.                                                                                |   2   | D/V  |

---

## C3.3 Kontrollerad distribution och återgång

Modellutrullningar måste kontrolleras, övervakas och vara reversibla.

|   #   | Description                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Verifiera att produktionsdriftsättningar implementerar gradvisa utrullningsmekanismer (canary-driftsättningar, blue-green-driftsättningar) med automatiska återställningstriggers baserade på förutbestämda felnivåer, latensgränser eller säkerhetsvarningskriterier. |   1   |  D   |
| 3.3.2 | Verifiera att rollback-funktioner återställer hela modellens tillstånd (vikter, konfigurationer, beroenden) atomiskt inom fördefinierade organisatoriska tidsfönster.                                                                                                  |   1   | D/V  |
| 3.3.3 | Verifiera att driftsättningsprocesser validerar kryptografiska signaturer och beräknar integritetskontrollsummor innan modellen aktiveras, och att driftsättningen avbryts vid någon avvikelse.                                                                        |   2   | D/V  |
| 3.3.4 | Verifiera att nödstopp för modeller kan stänga av modeländpunkter inom fördefinierade svarstider via automatiska brytare eller manuella avstängningsmekanismer.                                                                                                        |   2   | D/V  |
| 3.3.5 | Verifiera att återställningsartefakter (tidigare modellversioner, konfigurationer, beroenden) behålls enligt organisationens policyer med oföränderlig lagring för incidenthantering.                                                                                  |   2   |  V   |

---

## C3.4 Ändra ansvarsskyldighet och granskning

Alla förändringar i modellens livscykel måste vara spårbara och granskningsbara.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Verifiera att alla modelländringar (distribution, konfiguration, pensionering) genererar oföränderliga revisionsposter som inkluderar en tidsstämpel, en autentiserad aktörsidentitet, en ändringstyp samt tillstånd före och efter ändringen.                |   1   |  V   |
| 3.4.2 | Verifiera att åtkomst till revisionsloggen kräver lämplig auktorisation och att alla åtkomstförsök loggas med användaridentitet och tidsstämpel.                                                                                                              |   2   | D/V  |
| 3.4.3 | Verifiera att mallar för promptar och systemmeddelanden är versionshanterade i git-repositorier med obligatorisk kodgranskning och godkännande från utsedda granskare före distribution.                                                                      |   2   | D/V  |
| 3.4.4 | Verifiera att revisionsposter innehåller tillräckliga detaljer (modelhashar, konfigurationsögonblicksbilder, beroendeversioner) för att möjliggöra fullständig rekonstruktion av modellens tillstånd vid vilken tidsstämpel som helst inom bevarandeperioden. |   2   |  V   |

---

## C3.5 Säker utvecklingspraxis

Modellutvecklings- och träningsprocesser måste följa säkra metoder för att förhindra kompromiss.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Verifiera att modellutveckling, testning och produktionsmiljöer är fysiskt eller logiskt separerade. De ska inte ha gemensam infrastruktur, ha särskilda åtkomstkontroller och isolerade datalagringar.   |   1   |  D   |
| 3.5.2 | Verifiera att modellträning och finjustering sker i isolerade miljöer med kontrollerad nätverksåtkomst.                                                                                                   |   1   |  D   |
| 3.5.3 | Verifiera att träningsdatakällor valideras genom integritetskontroller och autentiseras via betrodda källor med dokumenterad kedja av vårdnad innan de används i modellutveckling.                        |   1   | D/V  |
| 3.5.4 | Verifiera att artefakter för modellutveckling (hyperparametrar, träningsskript, konfigurationsfiler) lagras i versionskontroll och kräver godkännande från granskande kollega innan de används i träning. |   2   |  D   |

---

## C3.6 Modellavveckling och avställning

Modeller måste säkert tas ur bruk när de inte längre behövs eller när säkerhetsproblem upptäcks.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Verifiera att processen för att pensionera modeller automatiskt skannar beroendegrafer, identifierar alla konsumtionssystem och ger förutbestämda förhandsmeddelandeperioder innan avveckling.                    |   1   |  D   |
| 3.6.2 | Verifiera att pensionerade modellartefakter tas bort säkert genom kryptografisk radering eller överskrivning i flera omgångar enligt dokumenterade datalagringspolicyer med verifierade destruktionsintyg.        |   1   | D/V  |
| 3.6.3 | Verifiera att modellens avvecklingshändelser loggas med tidsstämpel och aktörsidentitet, samt att modellsignaturer återkallas för att förhindra återanvändning.                                                   |   2   |  V   |
| 3.6.4 | Verifiera att nödsituationens modellavveckling kan inaktivera modellåtkomst inom förutbestämda tidsramar för nödsituationens respons genom automatiska avstängningsknappar om kritiska säkerhetsbrister upptäcks. |   2   | D/V  |

---

## Referenser

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

