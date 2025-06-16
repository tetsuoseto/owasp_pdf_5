# C12 Övervakning, Loggning och Anomalidetektion

## Styrningsmål

Denna sektion ger krav för att leverera realtids- och forensisk insyn i vad modellen och andra AI-komponenter ser, gör och returnerar, så att hot kan upptäckas, prioriteras och analyseras.

## C12.1 Förfrågnings- och svarloggning

|   #    | Description                                                                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.1.1 | Verifiera att alla användarpromptar och modellens svar loggas med lämplig metadata (t.ex. tidsstämpel, användar-ID, sessions-ID, modellversion).                                                                                                 |   1   | D/V  |
| 12.1.2 | Verifiera att loggar lagras i säkra, åtkomstkontrollerade arkiv med lämpliga behållningspolicys och säkerhetskopieringsrutiner.                                                                                                                  |   1   | D/V  |
| 12.1.3 | Verifiera att logglagringssystem implementerar kryptering vid vila och under överföring för att skydda känslig information som finns i loggar.                                                                                                   |   1   | D/V  |
| 12.1.4 | Verifiera att känsliga uppgifter i frågor och svar automatiskt raderas eller maskeras innan de loggas, med konfigurerbara regler för radering av personligt identifierbar information (PII), autentiseringsuppgifter och proprietär information. |   1   | D/V  |
| 12.1.5 | Verifiera att policybeslut och säkerhetsfiltreringsåtgärder loggas med tillräcklig detalj för att möjliggöra granskning och felsökning av innehållsmoderationssystem.                                                                            |   2   | D/V  |
| 12.1.6 | Verifiera att loggarnas integritet skyddas genom till exempel kryptografiska signaturer eller skrivskyddad lagring.                                                                                                                              |   2   | D/V  |

---

## C12.2 Missbruksdetektion och larmhantering

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Verifiera att systemet upptäcker och varnar för kända jailbreak-mönster, försök till promptinjektion och fientliga indata med hjälp av signaturbaserad detektion.                            |   1   | D/V  |
| 12.2.2 | Verifiera att systemet integreras med befintliga Security Information and Event Management (SIEM)-plattformar med hjälp av standardiserade loggformat och protokoll.                         |   1   | D/V  |
| 12.2.3 | Verifiera att berikade säkerhetshändelser inkluderar AIspecifik kontext såsom modellidentifierare, förtroendescore och beslut från säkerhetsfilter.                                          |   2   | D/V  |
| 12.2.4 | Verifiera att beteendeavvikelsedetektering identifierar ovanliga konversationsmönster, överdrivna omförsöksförsök eller systematiska sonderingsbeteenden.                                    |   2   | D/V  |
| 12.2.5 | Verifiera att realtidsvarningssystem meddelar säkerhetsteamen när potentiella policyöverträdelser eller attackförsök upptäcks.                                                               |   2   | D/V  |
| 12.2.6 | Verifiera att anpassade regler ingår för att upptäcka AI-specifika hotmönster, inklusive koordinerade jailbreak-försök, kampanjer för injektion av prompts och attacker för modellutvinning. |   2   | D/V  |
| 12.2.7 | Verifiera att automatiserade arbetsflöden för incidenthantering kan isolera komprometterade modeller, blockera illvilliga användare och eskalera kritiska säkerhetshändelser.                |   3   | D/V  |

---

## C12.3 Modellförskjutningsdetektion

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Verifiera att systemet spårar grundläggande prestationsmått såsom noggrannhet, förtroendescore, latens och felprocent över modellversioner och tidsperioder.                     |   1   | D/V  |
| 12.3.2 | Verifiera att automatiska larm utlöses när prestandamått överstiger fördefinierade försämringsgränser eller avviker betydligt från baslinjer.                                    |   2   | D/V  |
| 12.3.3 | Verifiera att hallucinationsdetekteringsövervakningar identifierar och markerar fall när modellutdata innehåller faktamässigt felaktig, inkonsekvent eller påhittad information. |   2   | D/V  |

---

## C12.4 Prestanda- och beteendetelemetri

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.4.1 | Verifiera att operationella mått, inklusive förfrågningsfördröjning, tokenförbrukning, minnesanvändning och genomströmning, kontinuerligt samlas in och övervakas. |   1   | D/V  |
| 12.4.2 | Verifiera att framgångs- och felprocent registreras med kategorisering av feltyper och deras grundorsaker.                                                         |   1   | D/V  |
| 12.4.3 | Verifiera att övervakning av resursanvändning inkluderar GPU/CPU-användning, minnesförbrukning och lagringskrav med larm vid tröskelöverskridanden.                |   2   | D/V  |

---

## C12.5 Planering och genomförande av AI-händelsehantering

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Verifiera att incidenthanteringsplaner specifikt hanterar AI-relaterade säkerhetshändelser inklusive modellkompromettering, datapoisning och adversarial-attacker.        |   1   | D/V  |
| 12.5.2 | Verifiera att incidenthanteringsteam har tillgång till AI-specifika forensiska verktyg och expertis för att undersöka modellbeteende och angreppsvägar.                   |   2   | D/V  |
| 12.5.3 | Verifiera att efterincidentanalysen inkluderar överväganden om modellomträning, uppdateringar av säkerhetsfilter och integrering av erfarenheter i säkerhetskontrollerna. |   3   | D/V  |

---

## C12.5 AI-prestandanedbrytning upptäckt

Övervaka och upptäck försämring i AI-modellens prestanda och kvalitet över tid.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Verifiera att modellens noggrannhet, precision, återkallelse och F1-poäng kontinuerligt övervakas och jämförs med baslinjetrösklar.                |   1   | D/V  |
| 12.5.2 | Verifiera att detektionssystemet för dataförskjutning övervakar förändringar i inmatningsfördelningen som kan påverka modellens prestanda.         |   1   | D/V  |
| 12.5.3 | Verifiera att konceptdriftupptäckt identifierar förändringar i relationen mellan indata och förväntade resultat.                                   |   2   | D/V  |
| 12.5.4 | Verifiera att prestandaförsämring utlöser automatiska varningar och initierar arbetsflöden för omträning eller utbyte av modellen.                 |   2   | D/V  |
| 12.5.5 | Verifiera att rotorsaksanalys av försämring korrelerar prestationsminskningar med datamodifieringar, infrastruktursproblem eller externa faktorer. |   3   |  V   |

---

## C12.6 DAG-visualisering och arbetsflödessäkerhet

Skydda arbetsflödesvisualiseringssystem från informationsläckage och manipulationsattacker.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Verifiera att DAG-visualiseringsdata saneras för att ta bort känslig information innan lagring eller överföring.                                                  |   1   | D/V  |
| 12.6.2 | Verifiera att åtkomstkontroller för arbetsflödesvisualisering säkerställer att endast auktoriserade användare kan se agentens beslutsvägar och resonemangsspår.   |   1   | D/V  |
| 12.6.3 | Verifiera att DAG:s dataintegritet skyddas genom kryptografiska signaturer och manipulationssäkra lagringsmekanismer.                                             |   2   | D/V  |
| 12.6.4 | Verifiera att system för visualisering av arbetsflöden implementerar inmatningsvalidering för att förhindra injektionsattacker via utformade nod- eller kantdata. |   2   | D/V  |
| 12.6.5 | Verifiera att realtidsuppdateringar av DAG är hastighetsbegränsade och validerade för att förhindra överbelastningsattacker på visualiseringssystem.              |   3   | D/V  |

---

## C12.7 Proaktiv övervakning av säkerhetsbeteende

Upptäckt och förebyggande av säkerhetshot genom proaktiv analys av agentbeteende.

|   #    | Description                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Verifiera att proaktiva agentbeteenden är säkerhetsvaliderade innan de utförs med integrerad riskbedömning.                   |   1   | D/V  |
| 12.7.2 | Verifiera att autonoma initiativutlösare inkluderar utvärdering av säkerhetskontext och bedömning av hotlandskapet.           |   2   | D/V  |
| 12.7.3 | Verifiera att proaktiva beteendemönster analyseras för potentiella säkerhetskonsekvenser och oavsiktliga följder.             |   2   | D/V  |
| 12.7.4 | Verifiera att säkerhetskritiska proaktiva åtgärder kräver uttryckliga godkännandeprocesser med revisionsspår.                 |   3   | D/V  |
| 12.7.5 | Verifiera att beteendeavvikelsedetektering identifierar avvikelser i proaktiva agentmönster som kan indikera kompromettering. |   3   | D/V  |

---

## Referenser

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

