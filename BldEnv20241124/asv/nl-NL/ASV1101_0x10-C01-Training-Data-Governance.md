# C1 Trainingsgegevensbeheer en Vooringenomenheidsbeheer

## Doel van de controle

Trainingsgegevens moeten worden verkregen, behandeld en onderhouden op een manier die herkomst, veiligheid, kwaliteit en rechtvaardigheid waarborgt. Dit voldoet aan wettelijke verplichtingen en vermindert het risico op vooringenomenheid, vergiftiging of privacyschendingen gedurende de hele levenscyclus van AI.

---

## C1.1 Oorsprong van Trainingsgegevens

Beheer een verifieerbare inventaris van alle datasets, accepteer alleen vertrouwde bronnen en registreer elke wijziging voor controleerbaarheid.

|   #   | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Verifieer dat er een actuele inventaris wordt bijgehouden van elke trainingsdatabron (oorsprong, beheerder/eigenaar, licentie, verzamelmethode, beperkingen voor bedoeld gebruik en verwerkingsgeschiedenis).                                                                  |   1   | D/V  |
| 1.1.2 | Controleer of alleen datasets die zijn getoetst op kwaliteit, representativiteit, ethische herkomst en naleving van licentie-eisen worden toegestaan, om risico's van besmetting, ingebouwde vooringenomenheid en schending van intellectuele eigendomsrechten te verminderen. |   1   | D/V  |
| 1.1.3 | Controleer of dataminimalisatie wordt gehandhaafd zodat onnodige of gevoelige attributen worden uitgesloten.                                                                                                                                                                   |   1   | D/V  |
| 1.1.4 | Controleer of alle datasetwijzigingen onderhevig zijn aan een geregistreerde goedkeuringsworkflow.                                                                                                                                                                             |   2   | D/V  |
| 1.1.5 | Controleer of de kwaliteit van labelen/annoteren wordt gegarandeerd via kruiscontroles door beoordelaars of consensus.                                                                                                                                                         |   2   | D/V  |
| 1.1.6 | Verifieer dat er "datakaarten" of "datasheets voor datasets" worden bijgehouden voor belangrijke trainingsdatasets, waarin kenmerken, motieven, samenstelling, verzamelingsprocessen, voorbewerking en aanbevolen/afgeraden gebruik worden beschreven.                         |   2   | D/V  |

---

## C1.2 Beveiliging en Integriteit van Trainingsgegevens

Beperk toegang, versleutel gegevens in rust en tijdens overdracht, en valideer de integriteit om manipulatie of diefstal te voorkomen.

|   #   | Description                                                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Controleer of toegangscontroles opslag en pijpleidingen beschermen.                                                                                                                                                                                                                                                                         |   1   | D/V  |
| 1.2.2 | Controleer of datasets tijdens overdracht zijn versleuteld en, voor alle gevoelige of persoonlijk identificeerbare informatie (PII), ook in rust, met behulp van cryptografische algoritmen en sleutelbeheerpraktijken die voldoen aan de industrienormen.                                                                                  |   2   | D/V  |
| 1.2.3 | Verifieer dat cryptografische hashes of digitale handtekeningen worden gebruikt om de gegevensintegriteit tijdens opslag en overdracht te waarborgen, en dat geautomatiseerde anomaliedetectietechnieken worden toegepast om te beschermen tegen ongeautoriseerde wijzigingen of corruptie, inclusief gerichte pogingen tot datavervuiling. |   2   | D/V  |
| 1.2.4 | Controleer of datasetversies worden bijgehouden om terugdraaien mogelijk te maken.                                                                                                                                                                                                                                                          |   3   | D/V  |
| 1.2.5 | Controleer of verouderde gegevens veilig worden verwijderd of geanonimiseerd in overeenstemming met het gegevensretentiebeleid, de regelgeving en om het aanvalsoppervlak te verkleinen.                                                                                                                                                    |   2   | D/V  |

---

## C1.3 Representatievolledigheid en rechtvaardigheid

Detecteer demografische vertekeningen en pas mitigatie toe zodat de foutpercentages van het model gelijkmatig verdeeld zijn over groepen.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Controleer of datasets geprofileerd zijn op representatieve onevenwichtigheid en potentiële vooroordelen over wettelijk beschermde kenmerken (bijv. ras, geslacht, leeftijd) en andere ethisch gevoelige eigenschappen die relevant zijn voor het toepassingsgebied van het model (bijv. sociaaleconomische status, locatie).                                              |   1   | D/V  |
| 1.3.2 | Verifieer dat de geïdentificeerde vooroordelen worden verminderd via gedocumenteerde strategieën zoals het herbalanceren, gerichte data-augmentatie, algoritmische aanpassingen (bijv. pre-processing, in-processing, post-processing technieken) of herweging, en dat de impact van deze mitigatie op zowel eerlijkheid als de algehele modelprestaties wordt beoordeeld. |   2   | D/V  |
| 1.3.3 | Verifieer dat na-training eerlijkheidsmetingen worden geëvalueerd en gedocumenteerd.                                                                                                                                                                                                                                                                                       |   2   | D/V  |
| 1.3.4 | Controleer of een beleid voor levenscyclusbeheer van vooringenomenheid eigenaren toewijst en een beoordelingsfrequentie vaststelt.                                                                                                                                                                                                                                         |   3   | D/V  |

---

## C1.4 Kwaliteit, Integriteit en Beveiliging van Trainingsdata Labeling

Bescherm labels met encryptie en vereist een dubbele beoordeling voor kritieke klassen.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.4.1 | Verifieer dat de kwaliteit van labeling/annotatie wordt gewaarborgd via duidelijke richtlijnen, kruiscontroles door beoordelaars, consensusmechanismen (bijv. het monitoren van overeenstemming tussen annotators) en gedefinieerde processen voor het oplossen van verschillen.     |   2   | D/V  |
| 1.4.2 | Controleer of cryptografische hashes of digitale handtekeningen worden toegepast op labelartefacten om hun integriteit en authenticiteit te waarborgen.                                                                                                                              |   2   | D/V  |
| 1.4.3 | Verifieer dat labelinterfaces en -platforms sterke toegangscontroles afdwingen, tamper-evidente auditlogs van alle labelactiviteiten bijhouden, en bescherming bieden tegen ongeautoriseerde wijzigingen.                                                                            |   2   | D/V  |
| 1.4.4 | Verifieer dat labels die cruciaal zijn voor veiligheid, beveiliging of eerlijkheid (bijvoorbeeld het identificeren van toxische inhoud, kritieke medische bevindingen) een verplichte onafhankelijke dubbele beoordeling of een equivalente degelijke verificatie ondergaan.         |   3   | D/V  |
| 1.4.5 | Controleer of gevoelige informatie (inclusief PII) die per ongeluk is vastgelegd of die noodzakelijk aanwezig is in labels, wordt geschrapt, gepseudonimiseerd, geanonimiseerd of versleuteld, zowel in rust als tijdens overdracht, volgens de principes van gegevensminimalisatie. |   2   | D/V  |
| 1.4.6 | Controleer of de labelrichtlijnen en instructies volledig, versiebeheerd en peer-reviewed zijn.                                                                                                                                                                                      |   2   | D/V  |
| 1.4.7 | Controleer of dataschema's (inclusief voor labels) duidelijk zijn gedefinieerd en versiebeheer hebben.                                                                                                                                                                               |   2   | D/V  |
| 1.8.2 | Verifieer of uitbestede of crowdsourced labeling-workflows technische/procedurele waarborgen bevatten om de vertrouwelijkheid van gegevens, integriteit, labelkwaliteit te waarborgen en datalekken te voorkomen.                                                                    |   2   | D/V  |

---

## C1.5 Kwaliteitsborging van trainingsgegevens

Combineer geautomatiseerde validatie, handmatige steekproeven en geregistreerde herstelacties om de betrouwbaarheid van datasets te garanderen.

|   #   | Description                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Controleer of geautomatiseerde tests formaatfouten, null-waarden en labelverschuivingen detecteren bij elke invoer of belangrijke transformatie.                                                                                                                                                                         |   1   |  D   |
| 1.5.2 | Controleer of mislukte datasets in quarantaine worden geplaatst met audit-trails.                                                                                                                                                                                                                                        |   1   | D/V  |
| 1.5.3 | Controleer of handmatige steekproeven door domeinexperts een statistisch significante steekproef dekken (bijvoorbeeld ≥1% of 1.000 monsters, afhankelijk van wat groter is, of zoals bepaald door een risicobeoordeling) om subtiele kwaliteitsproblemen te identificeren die door automatisering niet worden opgemerkt. |   2   |  V   |
| 1.5.4 | Controleer of herstelstappen worden toegevoegd aan de herkomstgegevens.                                                                                                                                                                                                                                                  |   2   | D/V  |
| 1.5.5 | Controleer of kwaliteitscontroles datasets van ondermaatse kwaliteit blokkeren, tenzij er uitzonderingen zijn goedgekeurd.                                                                                                                                                                                               |   2   | D/V  |

---

## C1.6 Detectie van Data Vergiftiging

Pas statistische anomaliedetectie en quarantainewerkstromen toe om kwaadaardige invoegingen te stoppen.

|   #   | Description                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verifieer dat anomaliedetectietechnieken (bijv. statistische methoden, uitbijterdetectie, embeddinganalyse) worden toegepast op trainingsgegevens tijdens de binnenkomst en vóór belangrijke trainingsruns om mogelijke vergiftigingsaanvallen of onbedoelde datacorruptie te identificeren.       |   2   | D/V  |
| 1.6.2 | Controleer of gemarkeerde monsters een handmatige beoordeling activeren voordat ze worden gebruikt voor training.                                                                                                                                                                                  |   2   | D/V  |
| 1.6.3 | Controleer of de resultaten het beveiligingsdossier van het model voeden en de voortdurende dreigingsinformatie informeren.                                                                                                                                                                        |   2   |  V   |
| 1.6.4 | Controleer of de detectielogica is bijgewerkt met nieuwe dreigingsinformatie.                                                                                                                                                                                                                      |   3   | D/V  |
| 1.6.5 | Verifieer dat online-leerpijplijnen distributieverandering monitoren.                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.6 | Verifieer dat specifieke verdedigingsmaatregelen tegen bekende typen data poisoning-aanvallen (bijvoorbeeld label flipping, backdoor trigger-insertie, invloedrijke instantie-aanvallen) worden overwogen en geïmplementeerd op basis van het risicoprofiel van het systeem en de gegevensbronnen. |   3   | D/V  |

---

## C1.7 Verwijdering van Gebruikersgegevens & Handhaving van Toestemming

Eerbiedig verwijderings- en intrekkingsverzoeken van toestemming binnen datasets, back-ups en afgeleide artefacten.

|   #   | Description                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Controleer of verwijderingsworkflows primaire en afgeleide gegevens wissen en beoordeel de impact op het model, en zorg ervoor dat de impact op de getroffen modellen wordt geëvalueerd en, indien nodig, aangepakt (bijvoorbeeld door middel van hertraining of herkalibratie).                                                       |   1   | D/V  |
| 1.7.2 | Controleer of er mechanismen aanwezig zijn om de reikwijdte en status van gebruikers toestemming (en intrekkingen) voor gegevens die worden gebruikt bij het trainen bij te houden en te respecteren, en dat toestemming wordt gevalideerd voordat gegevens worden opgenomen in nieuwe trainingsprocessen of belangrijke modelupdates. |   2   |  D   |
| 1.7.3 | Controleer of workflows jaarlijks worden getest en geregistreerd.                                                                                                                                                                                                                                                                      |   2   |  V   |

---

## C1.8 Beveiliging van de toeleveringsketen

Beoordeel externe gegevensleveranciers en verifieer de integriteit via geverifieerde, versleutelde kanalen.

|   #   | Description                                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verifieer dat externe dataleveranciers, inclusief aanbieders van voorgetrainde modellen en externe datasets, een due diligence-proces ondergaan op het gebied van beveiliging, privacy, ethische inkoop en datakwaliteit voordat hun data of modellen worden geïntegreerd.                                                                            |   2   | D/V  |
| 1.8.2 | Controleer of externe overdrachten TLS/authenticatie en integriteitscontroles gebruiken.                                                                                                                                                                                                                                                              |   1   |  D   |
| 1.8.3 | Zorg ervoor dat hoogrisicogegevensbronnen (bijv. open-source datasets met onbekende herkomst, niet-gevalideerde leveranciers) extra nauwkeurig worden gecontroleerd, zoals door sandbox-analyse, uitgebreide kwaliteits- en vooringenomenheidscontroles, en gerichte detectie van vergiftiging, voordat ze worden gebruikt in gevoelige toepassingen. |   2   | D/V  |
| 1.8.4 | Controleer of vooraf getrainde modellen die van derden zijn verkregen, worden geëvalueerd op ingebedde vooroordelen, potentiële achterdeurtjes, de integriteit van hun architectuur en de herkomst van hun oorspronkelijke trainingsgegevens voordat ze worden fijn afgestemd of ingezet.                                                             |   3   | D/V  |

---

## C1.9 Detectie van Adversariële Voorbeelden

Implementeer maatregelen tijdens de trainingsfase, zoals adversariële training, om de veerkracht van het model tegen adversariële voorbeelden te verbeteren.

|   #   | Description                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Controleer of geschikte verdedigingsmechanismen, zoals adversariële training (met behulp van gegenereerde adversariële voorbeelden), data-augmentatie met aangepaste inputs, of robuuste optimalisatietechnieken, zijn geïmplementeerd en afgestemd voor relevante modellen op basis van risicobeoordeling. |   3   | D/V  |
| 1.9.2 | Controleer of, wanneer adversariële training wordt toegepast, het genereren, beheren en versiebeheer van adversariële datasets wordt gedocumenteerd en gecontroleerd.                                                                                                                                       |   2   | D/V  |
| 1.9.3 | Verifieer dat de impact van adversarial robustness training op de modelprestaties (tegen zowel schone als adversariële inputs) en eerlijkheidsmaatregelen wordt geëvalueerd, gedocumenteerd en gemonitord.                                                                                                  |   3   | D/V  |
| 1.9.4 | Controleer regelmatig of de strategieën voor adversariële training en robuustheid worden herzien en bijgewerkt om zich te weren tegen zich ontwikkelende adversariële aanvalstechnieken.                                                                                                                    |   3   | D/V  |

---

## C1.10 Gegevenslijn en Traceerbaarheid

Volg de volledige reis van elk gegevenspunt van de bron tot de modelinvoer voor controleerbaarheid en incidentrespons.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Controleer of de herkomst van elk gegevenselement, inclusief alle transformaties, augmentaties en samenvoegingen, wordt vastgelegd en gereconstrueerd kan worden. |   2   | D/V  |
| 1.10.2 | Verifieer dat afstammingsgegevens onveranderlijk, veilig opgeslagen en toegankelijk zijn voor audits of onderzoeken.                                              |   2   | D/V  |
| 1.10.3 | Controleer of de afstammingsregistratie zowel ruwe als synthetische gegevens dekt.                                                                                |   2   | D/V  |

---

## C1.11 Beheer van synthetische gegevens

Zorg ervoor dat synthetische gegevens correct worden beheerd, gelabeld en risico-geanalyseerd.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.11.1 | Controleer of alle synthetische data duidelijk gelabeld en te onderscheiden is van echte data gedurende de hele pijplijn.                                    |   2   | D/V  |
| 1.11.2 | Controleer of het generatieproces, de parameters en het beoogde gebruik van synthetische gegevens zijn gedocumenteerd.                                       |   2   | D/V  |
| 1.11.3 | Controleer of synthetische gegevens voorafgaand aan het gebruik in training zijn beoordeeld op risico's zoals bias, privacylekken en representatieproblemen. |   2   | D/V  |

---

## C1.12 Data Toegangsmonitoring & Anomaliedetectie

Monitor en waarschuw bij ongebruikelijke toegang tot trainingsgegevens om interne bedreigingen of gegevensdiefstal te detecteren.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Controleer of alle toegang tot trainingsgegevens wordt geregistreerd, inclusief gebruiker, tijd en actie.                                   |   2   | D/V  |
| 1.12.2 | Controleer of toeganglogs regelmatig worden beoordeeld op ongebruikelijke patronen, zoals grote exporten of toegang vanuit nieuwe locaties. |   2   | D/V  |
| 1.12.3 | Controleer of waarschuwingen worden gegenereerd voor verdachte toegangsgebeurtenissen en snel worden onderzocht.                            |   2   | D/V  |

---

## C1.13 Beleid voor Gegevensbewaring en Verlopen

Definieer en handhaaf bewaartermijnen voor gegevens om onnodige opslag van gegevens te minimaliseren.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Controleer of expliciete bewaartermijnen zijn vastgesteld voor alle trainingsdatasets.                                                                    |   1   | D/V  |
| 1.13.2 | Controleer of datasets automatisch worden verlopen, verwijderd of ter beoordeling voor verwijdering worden aangeboden aan het einde van hun levenscyclus. |   2   | D/V  |
| 1.13.3 | Controleer of bewaarbeleid- en verwijderingsacties worden vastgelegd en controleerbaar zijn.                                                              |   2   | D/V  |

---

## C1.14 Regelgevende en Juridictie naleving

Zorg ervoor dat alle trainingsgegevens voldoen aan de toepasselijke wetten en regelgeving.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Controleer of de vereisten voor gegevensresidentie en grensoverschrijdende overdracht zijn vastgesteld en gehandhaafd voor alle datasets.     |   2   | D/V  |
| 1.14.2 | Controleer of sectorspecifieke regelgeving (bijvoorbeeld gezondheidszorg, financiën) is geïdentificeerd en behandeld bij het omgaan met data. |   2   | D/V  |
| 1.14.3 | Controleer of de naleving van relevante privacywetten (bijv. AVG, CCPA) is gedocumenteerd en regelmatig wordt beoordeeld.                     |   2   | D/V  |

---

## C1.15 Data Watermarking & Fingerprinting

Detecteer ongeoorloofd hergebruik of lekken van eigendoms- of gevoelige gegevens.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Controleer of datasets of subsets waar mogelijk zijn voorzien van een watermerk of fingerprint.                                              |   3   | D/V  |
| 1.15.2 | Controleer of watermarking- en fingerprinting-methoden geen vooringenomenheid of privacyrisico's introduceren.                               |   3   | D/V  |
| 1.15.3 | Controleer of er periodieke controles worden uitgevoerd om ongeautoriseerd hergebruik of lekken van watergemarkeerde gegevens te detecteren. |   3   | D/V  |

---

## C1.16 Beheer van Rechten van Betrokkenen

Ondersteun de rechten van betrokkenen, zoals toegang, rectificatie, beperking en bezwaar.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Controleer of er mechanismen bestaan om te reageren op verzoeken van betrokkenen om toegang, rectificatie, beperking of bezwaar. |   2   | D/V  |
| 1.16.2 | Verifieer dat verzoeken worden geregistreerd, gevolgd en binnen wettelijk voorgeschreven termijnen worden afgehandeld.           |   2   | D/V  |
| 1.16.3 | Controleer of de processen voor de rechten van betrokkenen regelmatig worden getest en geëvalueerd op effectiviteit.             |   2   | D/V  |

---

## C1.17 Analyse van de impact van datasetversies

Beoordeel de impact van wijzigingen in de dataset voordat u versies bijwerkt of vervangt.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Verifieer dat er een impactanalyse wordt uitgevoerd voordat een datasetversie wordt bijgewerkt of vervangen, waarbij modelprestaties, eerlijkheid en naleving worden meegenomen. |   2   | D/V  |
| 1.17.2 | Controleer of de resultaten van de impactanalyse zijn gedocumenteerd en beoordeeld door de relevante belanghebbenden.                                                            |   2   | D/V  |
| 1.17.3 | Controleer of er terugdraaiingsplannen bestaan voor het geval nieuwe versies onaanvaardbare risico's of regres veroorzaken.                                                      |   2   | D/V  |

---

## C1.18 Beveiliging van het data-annotatieteam

Zorg voor de veiligheid en integriteit van personeel dat betrokken is bij gegevensannotatie.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Verifieer dat al het personeel dat betrokken is bij data-annotatie een achtergrondcontrole heeft ondergaan en getraind is in datasbeveiliging en privacy. |   2   | D/V  |
| 1.18.2 | Zorg ervoor dat al het annotatiepersoneel vertrouwelijkheids- en geheimhoudingsovereenkomsten ondertekent.                                                |   2   | D/V  |
| 1.18.3 | Controleer of annotatieplatforms toegangscontroles afdwingen en binnenlandse bedreigingen monitoren.                                                      |   2   | D/V  |

---

## Referenties

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

