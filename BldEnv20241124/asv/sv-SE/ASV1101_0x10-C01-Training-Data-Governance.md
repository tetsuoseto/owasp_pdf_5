# C1 Träningsdatahantering och Hantering av Fördomar

## Styrningsmål

Träningsdata måste hämtas, hanteras och underhållas på ett sätt som bevarar ursprung, säkerhet, kvalitet och rättvisa. Genom att göra detta uppfylls juridiska skyldigheter och riskerna för partiskhet, förgiftning eller integritetsbrott minskas under hela AI-livscykeln.

---

## C1.1 Träningsdatans ursprung

Behåll en verifierbar inventering av alla dataset, acceptera endast betrodda källor och logga varje förändring för granskningsbarhet.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Verifiera att en uppdaterad inventering av varje träningsdatakälla (ursprung, ansvarig/ägare, licens, insamlingsmetod, avsedda användningsbegränsningar och bearbetningshistorik) upprätthålls.                                              |   1   | D/V  |
| 1.1.2 | Verifiera att endast dataset som har granskats för kvalitet, representativitet, etisk källhänvisning och licensöverensstämmelse tillåts, vilket minskar riskerna för förgiftning, inbäddad bias och intrång i immateriella rättigheter.      |   1   | D/V  |
| 1.1.3 | Verifiera att dataminimering efterlevs så att onödiga eller känsliga attribut utesluts.                                                                                                                                                      |   1   | D/V  |
| 1.1.4 | Verifiera att alla ändringar i datasetet är föremål för ett godkänt arbetsflöde som loggas.                                                                                                                                                  |   2   | D/V  |
| 1.1.5 | Verifiera att kvaliteten på märkning/annotering säkerställs genom granskarnas korsgranskningar eller konsensus.                                                                                                                              |   2   | D/V  |
| 1.1.6 | Verifiera att "datakort" eller "datablad för datamängder" underhålls för betydande träningsdatamängder, där egenskaper, motiv, sammansättning, insamlingsprocesser, förbehandling och rekommenderade/avrådda användningar beskrivs i detalj. |   2   | D/V  |

---

## C1.2 Säkerhet och integritet för träningsdata

Begränsa åtkomst, kryptera under lagring och överföring samt validera integritet för att förhindra manipulering eller stöld.

|   #   | Description                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Verifiera att åtkomstkontroller skyddar lagring och pipelines.                                                                                                                                                                                                                                                  |   1   | D/V  |
| 1.2.2 | Verifiera att datamängder är krypterade under överföring och, för all känslig eller personligt identifierbar information (PII), i vila, med hjälp av industriellt standardiserade kryptografiska algoritmer och nyckelhanteringsmetoder.                                                                        |   2   | D/V  |
| 1.2.3 | Verifiera att kryptografiska hashvärden eller digitala signaturer används för att säkerställa dataintegritet under lagring och överföring, samt att automatiska tekniker för anomalidetektion tillämpas för att skydda mot obehöriga förändringar eller korruption, inklusive riktade försök till datapåverkan. |   2   | D/V  |
| 1.2.4 | Verifiera att datasetversioner spåras för att möjliggöra återställning.                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.2.5 | Verifiera att föråldrad data säkert raderas eller anonymiseras i enlighet med datalagringspolicyer, regulatoriska krav och för att minska angreppsyta.                                                                                                                                                          |   2   | D/V  |

---

## C1.3 Representationsfullständighet och rättvisa

Upptäck demografiska skevheter och tillämpa åtgärder så att modellens felprocent är rättvisa över olika grupper.

|   #   | Description                                                                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Verifiera att dataseten är profilerade för representativ obalans och potentiella partiskheter över lagligt skyddade attribut (t.ex. ras, kön, ålder) och andra etiskt känsliga egenskaper som är relevanta för modellens tillämpningsområde (t.ex. socioekonomisk status, plats).                                                                    |   1   | D/V  |
| 1.3.2 | Verifiera att identifierade bias motverkas genom dokumenterade strategier såsom ombalansering, riktad dataförstärkning, algoritmiska justeringar (t.ex. förbehandling, bearbetning under körning, efterbehandlingstekniker) eller omviktning, och att effekten av motverkandet på både rättvisa och den övergripande modellens prestanda utvärderas. |   2   | D/V  |
| 1.3.3 | Verifiera att efterträningens rättvise-mått utvärderas och dokumenteras.                                                                                                                                                                                                                                                                             |   2   | D/V  |
| 1.3.4 | Verifiera att en livscykelhanteringspolicy för partiskhet tilldelar ägare och granskningsfrekvens.                                                                                                                                                                                                                                                   |   3   | D/V  |

---

## C1.4 Kvalitet, integritet och säkerhet för märkning av träningsdata

Skydda etiketter med kryptering och kräva dubbel granskning för kritiska klasser.

|   #   | Description                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Verifiera att etiketterings-/annotationskvaliteten säkerställs genom tydliga riktlinjer, korsgranskningar av granskare, konsensusmekanismer (t.ex. övervakning av överensstämmelse mellan annotatörer) samt definierade processer för att lösa oenigheter.                      |   2   | D/V  |
| 1.4.2 | Verifiera att kryptografiska hashvärden eller digitala signaturer tillämpas på etikettartefakter för att säkerställa deras integritet och äkthet.                                                                                                                               |   2   | D/V  |
| 1.4.3 | Verifiera att märkningsgränssnitt och plattformar upprätthåller starka åtkomstkontroller, behåller manipulationssäkra revisionsloggar över all märkningsaktivitet och skyddar mot obehöriga ändringar.                                                                          |   2   | D/V  |
| 1.4.4 | Verifiera att etiketter som är kritiska för säkerhet, trygghet eller rättvisa (t.ex. identifiering av giftigt innehåll, kritiska medicinska fynd) genomgår obligatorisk oberoende dubbelgranskning eller motsvarande robust verifiering.                                        |   3   | D/V  |
| 1.4.5 | Verifiera att känslig information (inklusive personligt identifierbar information, PII) som oavsiktligt fångats eller nödvändigtvis finns i etiketter är raderad, pseudonymiserad, anonymiserad eller krypterad vid vila och överföring, enligt principerna för dataminimering. |   2   | D/V  |
| 1.4.6 | Verifiera att märkvägledningar och instruktioner är omfattande, versionskontrollerade och granskade av kollegor.                                                                                                                                                                |   2   | D/V  |
| 1.4.7 | Verifiera att datascheman (inklusive för etiketter) är tydligt definierade och versionshanterade.                                                                                                                                                                               |   2   | D/V  |
| 1.8.2 | Verifiera att outsourcade eller crowdsourcade märkningarbetsflöden inkluderar tekniska/procedurmässiga skyddsåtgärder för att säkerställa datakonfidentialitet, integritet, etikettkvalitet och förhindra dataläckage.                                                          |   2   | D/V  |

---

## C1.5 Kvalitetssäkring av träningsdata

Kombinera automatiserad validering, manuella stickprov och loggad åtgärd för att garantera datasetets tillförlitlighet.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Verifiera att automatiserade tester fångar formatfel, nullvärden och etikettförskjutningar vid varje inläsning eller betydande transformation.                                                                                                                                       |   1   |  D   |
| 1.5.2 | Verifiera att misslyckade dataset är isolerade med revisionsspår.                                                                                                                                                                                                                    |   1   | D/V  |
| 1.5.3 | Verifiera att manuella stickprovskontroller av domänexperter täcker ett statistiskt signifikant urval (t.ex. ≥1% eller 1 000 prover, beroende på vilket som är störst, eller enligt riskbedömning) för att identifiera subtila kvalitetsproblem som inte upptäcks av automatisering. |   2   |  V   |
| 1.5.4 | Verifiera att åtgärdsstegen läggs till i härledningsposter.                                                                                                                                                                                                                          |   2   | D/V  |
| 1.5.5 | Verifiera att kvalitetsgrindar blockerar undermåliga dataset om inte undantag godkänns.                                                                                                                                                                                              |   2   | D/V  |

---

## C1.6 Upptäckt av dataförgiftning

Tillämpa statistisk avvikelsedetektering och karantänarbetsflöden för att stoppa illvilliga insättningar.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verifiera att anomalidetektionstekniker (t.ex. statistiska metoder, avvikelsedetektion, inbäddningsanalys) tillämpas på träningsdata vid inläsning och före större träningskörningar för att identifiera potentiella förgiftningattacker eller oavsiktlig datakorruption. |   2   | D/V  |
| 1.6.2 | Verifiera att flaggade prover utlöser manuell granskning innan träning.                                                                                                                                                                                                   |   2   | D/V  |
| 1.6.3 | Verifiera att resultaten matas in i modellens säkerhetsdossier och informerar pågående hotintelligens.                                                                                                                                                                    |   2   |  V   |
| 1.6.4 | Verifiera att detektionslogiken uppdateras med ny hotintelligens.                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.5 | Verifiera att online-inlärningspipelines övervakar förskjutning i fördelningen.                                                                                                                                                                                           |   3   | D/V  |
| 1.6.6 | Verifiera att specifika försvar mot kända typer av dataförgiftning (t.ex. etikettomkastning, insättning av bakdörrstrigger, attacker med inflytelserika instanser) beaktas och implementeras baserat på systemets riskprofil och datakällor.                              |   3   | D/V  |

---

## C1.7 Radering av användardata och efterlevnad av samtycke

Respektera raderings- och samtyckesåterkallelseförfrågningar över dataset, säkerhetskopior och härledda artefakter.

|   #   | Description                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Verifiera att raderingsarbetsflöden rensar primär och härledd data samt bedömer modellens påverkan, och att påverkan på berörda modeller bedöms och, om nödvändigt, åtgärdas (t.ex. genom omträning eller omkalibrering).                                                              |   1   | D/V  |
| 1.7.2 | Verifiera att mekanismer finns på plats för att spåra och respektera omfattningen och statusen för användarsamtycke (och återkallelser) för data som används i träning, samt att samtycke valideras innan data införlivas i nya träningsprocesser eller betydande modelluppdateringar. |   2   |  D   |
| 1.7.3 | Verifiera att arbetsflöden testas årligen och loggas.                                                                                                                                                                                                                                  |   2   |  V   |

---

## C1.8 Säkerhet i leverantörskedjan

Granska externa dataleverantörer och verifiera integritet över autentiserade, krypterade kanaler.

|   #   | Description                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verifiera att tredjepartsdataleverantörer, inklusive leverantörer av förtränade modeller och externa datamängder, genomgår säkerhets-, integritets-, etisk sourcing- och datakvalitetsgranskning innan deras data eller modeller integreras.                                      |   2   | D/V  |
| 1.8.2 | Verifiera att externa överföringar använder TLS/autentisering och integritetskontroller.                                                                                                                                                                                          |   1   |  D   |
| 1.8.3 | Verifiera att hög risk-data källor (t.ex. öppna dataset med okänt ursprung, ogenomgångna leverantörer) får förhöjd granskning, såsom sandlådsanalys, omfattande kvalitets-/partiskhetskontroller och målinriktad föroreningsdetektion, innan de används i känsliga tillämpningar. |   2   | D/V  |
| 1.8.4 | Verifiera att förtränade modeller som erhållits från tredje part utvärderas för inbäddade bias, potentiella bakdörrar, arkitekturens integritet och ursprunget till deras ursprungliga träningsdata innan finjustering eller implementering.                                      |   3   | D/V  |

---

## C1.9 Detektion av adversariella prover

Implementera åtgärder under träningsfasen, såsom adversariell träning, för att öka modellens motståndskraft mot adversariella exempel.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Verifiera att lämpliga försvar, såsom adversarial träning (med genererade adversariala exempel), dataförstärkning med störda indata eller robusta optimeringstekniker, är implementerade och anpassade för relevanta modeller baserat på riskbedömning. |   3   | D/V  |
| 1.9.2 | Verifiera att om adversarial träning används, är genereringen, hanteringen och versioneringen av adversarial-dataset dokumenterad och kontrollerad.                                                                                                     |   2   | D/V  |
| 1.9.3 | Verifiera att effekten av träning för motståndskraft mot angrepp på modellens prestanda (mot både rena och adversariella indata) samt rättvise-måttvärden utvärderas, dokumenteras och övervakas.                                                       |   3   | D/V  |
| 1.9.4 | Verifiera att strategier för adversarial träning och robusthet regelbundet granskas och uppdateras för att motverka utvecklande tekniker för adversarial attacker.                                                                                      |   3   | D/V  |

---

## C1.10 Data härstamning och spårbarhet

Följ hela resan för varje datapunkt från källa till modellinmatning för granskningsbarhet och incidenthantering.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verifiera att härkomsten för varje datapunkt, inklusive alla transformationer, förstärkningar och sammanslagningar, är dokumenterad och kan rekonstrueras. |   2   | D/V  |
| 1.10.2 | Verifiera att härkomstuppgifter är oföränderliga, säkert lagrade och tillgängliga för revisioner eller utredningar.                                        |   2   | D/V  |
| 1.10.3 | Verifiera att spårning av härstamning täcker både rådata och syntetisk data.                                                                               |   2   | D/V  |

---

## C1.11 Hantering av syntetiska data

Se till att syntetiska data hanteras korrekt, märks och riskbedöms.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Verifiera att all syntetisk data är tydligt märkt och skiljer sig från verklig data genom hela processen.                          |   2   | D/V  |
| 1.11.2 | Verifiera att genereringsprocessen, parametrarna och avsedd användning av syntetiska data är dokumenterade.                        |   2   | D/V  |
| 1.11.3 | Verifiera att syntetiska data riskbedöms för partiskhet, integritetsläckage och representativa problem innan de används i träning. |   2   | D/V  |

---

## C1.12 Övervakning av dataåtkomst och avvikelsedetektering

Övervaka och avisera vid ovanlig åtkomst till träningsdata för att upptäcka insiderhot eller dataläckage.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Verifiera att all åtkomst till träningsdata loggas, inklusive användare, tidpunkt och åtgärd.                               |   2   | D/V  |
| 1.12.2 | Verifiera att åtkomstloggar regelbundet granskas för ovanliga mönster, såsom stora exporter eller åtkomst från nya platser. |   2   | D/V  |
| 1.12.3 | Verifiera att varningar genereras för misstänkta åtkomsthändelser och att dessa undersöks omedelbart.                       |   2   | D/V  |

---

## C1.13 Policys för datalagring och utgångsdatum

Definiera och genomdriv perioder för datalagring för att minimera onödig datalagring.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.13.1 | Verifiera att uttryckliga lagringstider är definierade för alla träningsdatamängder.                               |   1   | D/V  |
| 1.13.2 | Verifiera att datasätt automatiskt förfaller, tas bort eller granskas för borttagning i slutet av deras livscykel. |   2   | D/V  |
| 1.13.3 | Verifiera att åtgärder för kvarhållning och radering loggas och kan granskas.                                      |   2   | D/V  |

---

## C1.14 Regulatorisk och jurisdiktionell efterlevnad

Säkerställ att all träningsdata följer tillämpliga lagar och förordningar.

|   #    | Description                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Verifiera att krav på dataresidens och gränsöverskridande överföring identifieras och tillämpas för alla datamängder. |   2   | D/V  |
| 1.14.2 | Verifiera att sektorspecifika regler (t.ex. hälso- och sjukvård, finans) identifieras och hanteras vid datahantering. |   2   | D/V  |
| 1.14.3 | Verifiera att efterlevnaden av relevanta dataskyddslagar (t.ex. GDPR, CCPA) är dokumenterad och regelbundet granskad. |   2   | D/V  |

---

## C1.15 Data Vattentätning & Fingeravtrycksskapande

Upptäck obehörig återanvändning eller läckage av proprietär eller känslig data.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Verifiera att dataset eller delmängder är vattenmärkta eller fingeravtrycksmärkta där det är möjligt.                  |   3   | D/V  |
| 1.15.2 | Verifiera att vattenmärkning/fingeravtrycksmetoder inte inför partiskhet eller integritetsrisker.                      |   3   | D/V  |
| 1.15.3 | Verifiera att periodiska kontroller utförs för att upptäcka obehörig återanvändning eller läckage av vattenmärkt data. |   3   | D/V  |

---

## C1.16 Hantering av registrerades rättigheter

Stöd datasubjektens rättigheter såsom tillgång, rättelse, begränsning och invändning.

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.16.1 | Verifera att mekanismer finns för att hantera registrerades begäran om tillgång, rättelse, begränsning eller invändning. |   2   | D/V  |
| 1.16.2 | Verifiera att förfrågningar loggas, spåras och uppfylls inom lagstadgade tidsramar.                                      |   2   | D/V  |
| 1.16.3 | Verifiera att processerna för rättigheter för den registrerade testas och granskas regelbundet för effektivitet.         |   2   | D/V  |

---

## C1.17 Analys av påverkan av datasetversioner

Utvärdera effekten av datasetförändringar innan du uppdaterar eller byter versioner.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.17.1 | Verifiera att en konsekvensanalys utförs innan en datasetversion uppdateras eller ersätts, som täcker modellprestanda, rättvisa och efterlevnad. |   2   | D/V  |
| 1.17.2 | Verifiera att resultaten av påverkningsanalysen är dokumenterade och granskade av relevanta intressenter.                                        |   2   | D/V  |
| 1.17.3 | Verifiera att återställningsplaner finns om nya versioner introducerar oacceptabla risker eller försämringar.                                    |   2   | D/V  |

---

## C1.18 Säkerhet för arbetsstyrkan vid dataannotering

Säkerställ säkerheten och integriteten för personal som är involverad i dataannotering.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.18.1 | Verifiera att all personal som är involverad i dataannotering har genomgått bakgrundskontroll och utbildning i datasäkerhet och sekretess. |   2   | D/V  |
| 1.18.2 | Verifera att all annoteringspersonal undertecknar sekretess- och tystnadsavtal.                                                            |   2   | D/V  |
| 1.18.3 | Verifiera att annoteringsplattformar upprätthåller åtkomstkontroller och övervakar för insiderhot.                                         |   2   | D/V  |

---

## Referenser

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

