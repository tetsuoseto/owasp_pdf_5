## Titelpagina

### Over de Norm

De Artificial Intelligence Security Verification Standard (AISVS) is een gemeenschapsgestuurde catalogus van beveiligingseisen die datawetenschappers, MLOps-ingenieurs, softwarearchitecten, ontwikkelaars, testers, beveiligingsprofessionals, toolleveranciers, regelgevers en consumenten kunnen gebruiken om betrouwbare AI-gestuurde systemen en applicaties te ontwerpen, bouwen, testen en verifiëren. Het biedt een gemeenschappelijke taal voor het specificeren van beveiligingscontroles gedurende de hele AI-levenscyclus — van dataverzameling en modelontwikkeling tot implementatie en voortdurende monitoring — zodat organisaties de veerkracht, privacy en veiligheid van hun AI-oplossingen kunnen meten en verbeteren.

### Auteursrechten en licentie

Versie 0.1 (Eerste Openbare Concept - Werk In Uitvoering), 2025  

![license](images/license.png)
Copyright © 2025 Het AISVS-project.  

Uitgegeven onder deCreative Commons Attribution‑ShareAlike 4.0 International License.
Voor hergebruik of distributie moet u de licentievoorwaarden van dit werk duidelijk aan anderen communiceren.

### Projectleiders

Jim Manico
Aras "Russ" Memisyazici

### Bijdragers en beoordelaars

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS is een geheel nieuwe standaard die specifiek is ontwikkeld om de unieke beveiligingsuitdagingen van kunstmatige-intelligentiesystemen aan te pakken. Hoewel het inspiratie haalt uit bredere beste beveiligingspraktijken, is iedere eis in AISVS vanaf de basis ontwikkeld om het dreigingslandschap van AI weer te geven en organisaties te helpen veiligere, veerkrachtigere AI-oplossingen te bouwen.

## Voorwoord

Welkom bij de Artificial Intelligence Security Verification Standard (AISVS) versie 1.0!

### Inleiding

Opgericht in 2025 door een gezamenlijke inzet van de gemeenschap, definieert AISVS de beveiligingseisen die in acht moeten worden genomen bij het ontwerpen, ontwikkelen, implementeren en exploiteren van moderne AI-modellen, pijplijnen en AI-gestuurde diensten.

AISVS v1.0 vertegenwoordigt het gezamenlijke werk van zijn projectleiders, werkgroep en bredere gemeenschap van bijdragers om een pragmatische, toetsbare basislijn te creëren voor het beveiligen van AI-systemen.

Ons doel met deze release is om AISVS gemakkelijk toepasbaar te maken, terwijl we scherp gericht blijven op de gedefinieerde scope en de snel veranderende risicolandschap die uniek is voor AI aanpakken.

### Belangrijkste doelstellingen voor AISVS versie 1.0

Versie 1.0 zal worden gemaakt met meerdere leidende principes.

#### Duidelijk Afgebakende Reikwijdte

Elke eis moet in overeenstemming zijn met de naam en missie van AISVS:

Kunstmatige Intelligentie – Controles worden uitgevoerd op de AI/ML-laag (gegevens, model, pijplijn of inferentie) en zijn de verantwoordelijkheid van AI-beoefenaars.
Beveiliging – Vereisten verminderen rechtstreeks de vastgestelde beveiligings-, privacy- of veiligheidsrisico's.
Verificatie – Taal is geschreven zodat naleving objectief kan worden geverifieerd.
Standaard – Secties volgen een consistente structuur en terminologie om een samenhangende referentie te vormen.
​
---

Door AISVS te volgen, kunnen organisaties systematisch de beveiligingspositie van hun AI-oplossingen evalueren en versterken, waardoor een cultuur van veilige AI-engineering wordt bevorderd.

## Gebruik van de AISVS

De Artificial Intelligence Security Verification Standard (AISVS) definieert beveiligingseisen voor moderne AI-toepassingen en -diensten, met de nadruk op aspecten die onder de controle van applicatieontwikkelaars vallen.

De AISVS is bedoeld voor iedereen die AI-toepassingen ontwikkelt of de beveiliging daarvan evalueert, waaronder ontwikkelaars, architecten, beveiligingsingenieurs en auditors. Dit hoofdstuk introduceert de structuur en het gebruik van de AISVS, inclusief de verificatieniveaus en beoogde gebruikssituaties.

### Beveiligingsverificatieniveaus voor Kunstmatige Intelligentie

De AISVS definieert drie oplopende niveaus van beveiligingsverificatie. Elk niveau voegt diepgang en complexiteit toe, waardoor organisaties hun beveiligingshouding kunnen afstemmen op het risiconiveau van hun AI-systemen.

Organisaties kunnen beginnen op Niveau 1 en geleidelijk hogere niveaus aannemen naarmate de beveiligingsrijpheid en bedreigingsexposure toenemen.

#### Definitie van de niveaus

Elke vereiste in AISVS v1.0 is toegewezen aan een van de volgende niveaus:

 Niveau 1 vereisten

Niveau 1 omvat de meest cruciale en fundamentele beveiligingseisen. Deze zijn gericht op het voorkomen van veelvoorkomende aanvallen die niet afhankelijk zijn van andere voorwaarden of kwetsbaarheden. De meeste controles op Niveau 1 zijn óf eenvoudig te implementeren óf essentieel genoeg om de inspanning te rechtvaardigen.

 Niveau 2 vereisten

Niveau 2 behandelt meer geavanceerde of minder gebruikelijke aanvallen, evenals gelaagde verdedigingslagen tegen wijdverspreide dreigingen. Deze vereisten kunnen complexere logica omvatten of specifieke aanvalvoorwaarden als doel hebben.

 Niveau 3-vereisten

Niveau 3 omvat controles die doorgaans moeilijker te implementeren zijn of situationeel van toepassing zijn. Deze vertegenwoordigen vaak verdedigingsmechanismen in diepte of mitigaties tegen niche-, gerichte of complexe aanvallen.

#### Rol (D/V)

Elke AISVS-vereiste is gemarkeerd volgens het primaire publiek:

D – Ontwikkelaar-gerichte vereisten
V – Eisen gericht op verificateurs/auditors
D/V – Relevant voor zowel ontwikkelaars als verifiers

## C1 Trainingsgegevensbeheer en Vooringenomenheidsbeheer

### Doel van de controle

Trainingsgegevens moeten worden verkregen, behandeld en onderhouden op een manier die herkomst, veiligheid, kwaliteit en rechtvaardigheid waarborgt. Dit voldoet aan wettelijke verplichtingen en vermindert het risico op vooringenomenheid, vergiftiging of privacyschendingen gedurende de hele levenscyclus van AI.

---

### C1.1 Oorsprong van Trainingsgegevens

Beheer een verifieerbare inventaris van alle datasets, accepteer alleen vertrouwde bronnen en registreer elke wijziging voor controleerbaarheid.

 #1.1.1    Level: 1    Role: D/V
 Verifieer dat er een actuele inventaris wordt bijgehouden van elke trainingsdatabron (oorsprong, beheerder/eigenaar, licentie, verzamelmethode, beperkingen voor bedoeld gebruik en verwerkingsgeschiedenis).
 #1.1.2    Level: 1    Role: D/V
 Controleer of alleen datasets die zijn getoetst op kwaliteit, representativiteit, ethische herkomst en naleving van licentie-eisen worden toegestaan, om risico's van besmetting, ingebouwde vooringenomenheid en schending van intellectuele eigendomsrechten te verminderen.
 #1.1.3    Level: 1    Role: D/V
 Controleer of dataminimalisatie wordt gehandhaafd zodat onnodige of gevoelige attributen worden uitgesloten.
 #1.1.4    Level: 2    Role: D/V
 Controleer of alle datasetwijzigingen onderhevig zijn aan een geregistreerde goedkeuringsworkflow.
 #1.1.5    Level: 2    Role: D/V
 Controleer of de kwaliteit van labelen/annoteren wordt gegarandeerd via kruiscontroles door beoordelaars of consensus.
 #1.1.6    Level: 2    Role: D/V
 Verifieer dat er "datakaarten" of "datasheets voor datasets" worden bijgehouden voor belangrijke trainingsdatasets, waarin kenmerken, motieven, samenstelling, verzamelingsprocessen, voorbewerking en aanbevolen/afgeraden gebruik worden beschreven.

---

### C1.2 Beveiliging en Integriteit van Trainingsgegevens

Beperk toegang, versleutel gegevens in rust en tijdens overdracht, en valideer de integriteit om manipulatie of diefstal te voorkomen.

 #1.2.1    Level: 1    Role: D/V
 Controleer of toegangscontroles opslag en pijpleidingen beschermen.
 #1.2.2    Level: 2    Role: D/V
 Controleer of datasets tijdens overdracht zijn versleuteld en, voor alle gevoelige of persoonlijk identificeerbare informatie (PII), ook in rust, met behulp van cryptografische algoritmen en sleutelbeheerpraktijken die voldoen aan de industrienormen.
 #1.2.3    Level: 2    Role: D/V
 Verifieer dat cryptografische hashes of digitale handtekeningen worden gebruikt om de gegevensintegriteit tijdens opslag en overdracht te waarborgen, en dat geautomatiseerde anomaliedetectietechnieken worden toegepast om te beschermen tegen ongeautoriseerde wijzigingen of corruptie, inclusief gerichte pogingen tot datavervuiling.
 #1.2.4    Level: 3    Role: D/V
 Controleer of datasetversies worden bijgehouden om terugdraaien mogelijk te maken.
 #1.2.5    Level: 2    Role: D/V
 Controleer of verouderde gegevens veilig worden verwijderd of geanonimiseerd in overeenstemming met het gegevensretentiebeleid, de regelgeving en om het aanvalsoppervlak te verkleinen.

---

### C1.3 Representatievolledigheid en rechtvaardigheid

Detecteer demografische vertekeningen en pas mitigatie toe zodat de foutpercentages van het model gelijkmatig verdeeld zijn over groepen.

 #1.3.1    Level: 1    Role: D/V
 Controleer of datasets geprofileerd zijn op representatieve onevenwichtigheid en potentiële vooroordelen over wettelijk beschermde kenmerken (bijv. ras, geslacht, leeftijd) en andere ethisch gevoelige eigenschappen die relevant zijn voor het toepassingsgebied van het model (bijv. sociaaleconomische status, locatie).
 #1.3.2    Level: 2    Role: D/V
 Verifieer dat de geïdentificeerde vooroordelen worden verminderd via gedocumenteerde strategieën zoals het herbalanceren, gerichte data-augmentatie, algoritmische aanpassingen (bijv. pre-processing, in-processing, post-processing technieken) of herweging, en dat de impact van deze mitigatie op zowel eerlijkheid als de algehele modelprestaties wordt beoordeeld.
 #1.3.3    Level: 2    Role: D/V
 Verifieer dat na-training eerlijkheidsmetingen worden geëvalueerd en gedocumenteerd.
 #1.3.4    Level: 3    Role: D/V
 Controleer of een beleid voor levenscyclusbeheer van vooringenomenheid eigenaren toewijst en een beoordelingsfrequentie vaststelt.

---

### C1.4 Kwaliteit, Integriteit en Beveiliging van Trainingsdata Labeling

Bescherm labels met encryptie en vereist een dubbele beoordeling voor kritieke klassen.

 #1.4.1    Level: 2    Role: D/V
 Verifieer dat de kwaliteit van labeling/annotatie wordt gewaarborgd via duidelijke richtlijnen, kruiscontroles door beoordelaars, consensusmechanismen (bijv. het monitoren van overeenstemming tussen annotators) en gedefinieerde processen voor het oplossen van verschillen.
 #1.4.2    Level: 2    Role: D/V
 Controleer of cryptografische hashes of digitale handtekeningen worden toegepast op labelartefacten om hun integriteit en authenticiteit te waarborgen.
 #1.4.3    Level: 2    Role: D/V
 Verifieer dat labelinterfaces en -platforms sterke toegangscontroles afdwingen, tamper-evidente auditlogs van alle labelactiviteiten bijhouden, en bescherming bieden tegen ongeautoriseerde wijzigingen.
 #1.4.4    Level: 3    Role: D/V
 Verifieer dat labels die cruciaal zijn voor veiligheid, beveiliging of eerlijkheid (bijvoorbeeld het identificeren van toxische inhoud, kritieke medische bevindingen) een verplichte onafhankelijke dubbele beoordeling of een equivalente degelijke verificatie ondergaan.
 #1.4.5    Level: 2    Role: D/V
 Controleer of gevoelige informatie (inclusief PII) die per ongeluk is vastgelegd of die noodzakelijk aanwezig is in labels, wordt geschrapt, gepseudonimiseerd, geanonimiseerd of versleuteld, zowel in rust als tijdens overdracht, volgens de principes van gegevensminimalisatie.
 #1.4.6    Level: 2    Role: D/V
 Controleer of de labelrichtlijnen en instructies volledig, versiebeheerd en peer-reviewed zijn.
 #1.4.7    Level: 2    Role: D/V
 Controleer of dataschema's (inclusief voor labels) duidelijk zijn gedefinieerd en versiebeheer hebben.
 #1.8.2    Level: 2    Role: D/V
 Verifieer of uitbestede of crowdsourced labeling-workflows technische/procedurele waarborgen bevatten om de vertrouwelijkheid van gegevens, integriteit, labelkwaliteit te waarborgen en datalekken te voorkomen.

---

### C1.5 Kwaliteitsborging van trainingsgegevens

Combineer geautomatiseerde validatie, handmatige steekproeven en geregistreerde herstelacties om de betrouwbaarheid van datasets te garanderen.

 #1.5.1    Level: 1    Role: D
 Controleer of geautomatiseerde tests formaatfouten, null-waarden en labelverschuivingen detecteren bij elke invoer of belangrijke transformatie.
 #1.5.2    Level: 1    Role: D/V
 Controleer of mislukte datasets in quarantaine worden geplaatst met audit-trails.
 #1.5.3    Level: 2    Role: V
 Controleer of handmatige steekproeven door domeinexperts een statistisch significante steekproef dekken (bijvoorbeeld ≥1% of 1.000 monsters, afhankelijk van wat groter is, of zoals bepaald door een risicobeoordeling) om subtiele kwaliteitsproblemen te identificeren die door automatisering niet worden opgemerkt.
 #1.5.4    Level: 2    Role: D/V
 Controleer of herstelstappen worden toegevoegd aan de herkomstgegevens.
 #1.5.5    Level: 2    Role: D/V
 Controleer of kwaliteitscontroles datasets van ondermaatse kwaliteit blokkeren, tenzij er uitzonderingen zijn goedgekeurd.

---

### C1.6 Detectie van Data Vergiftiging

Pas statistische anomaliedetectie en quarantainewerkstromen toe om kwaadaardige invoegingen te stoppen.

 #1.6.1    Level: 2    Role: D/V
 Verifieer dat anomaliedetectietechnieken (bijv. statistische methoden, uitbijterdetectie, embeddinganalyse) worden toegepast op trainingsgegevens tijdens de binnenkomst en vóór belangrijke trainingsruns om mogelijke vergiftigingsaanvallen of onbedoelde datacorruptie te identificeren.
 #1.6.2    Level: 2    Role: D/V
 Controleer of gemarkeerde monsters een handmatige beoordeling activeren voordat ze worden gebruikt voor training.
 #1.6.3    Level: 2    Role: V
 Controleer of de resultaten het beveiligingsdossier van het model voeden en de voortdurende dreigingsinformatie informeren.
 #1.6.4    Level: 3    Role: D/V
 Controleer of de detectielogica is bijgewerkt met nieuwe dreigingsinformatie.
 #1.6.5    Level: 3    Role: D/V
 Verifieer dat online-leerpijplijnen distributieverandering monitoren.
 #1.6.6    Level: 3    Role: D/V
 Verifieer dat specifieke verdedigingsmaatregelen tegen bekende typen data poisoning-aanvallen (bijvoorbeeld label flipping, backdoor trigger-insertie, invloedrijke instantie-aanvallen) worden overwogen en geïmplementeerd op basis van het risicoprofiel van het systeem en de gegevensbronnen.

---

### C1.7 Verwijdering van Gebruikersgegevens & Handhaving van Toestemming

Eerbiedig verwijderings- en intrekkingsverzoeken van toestemming binnen datasets, back-ups en afgeleide artefacten.

 #1.7.1    Level: 1    Role: D/V
 Controleer of verwijderingsworkflows primaire en afgeleide gegevens wissen en beoordeel de impact op het model, en zorg ervoor dat de impact op de getroffen modellen wordt geëvalueerd en, indien nodig, aangepakt (bijvoorbeeld door middel van hertraining of herkalibratie).
 #1.7.2    Level: 2    Role: D
 Controleer of er mechanismen aanwezig zijn om de reikwijdte en status van gebruikers toestemming (en intrekkingen) voor gegevens die worden gebruikt bij het trainen bij te houden en te respecteren, en dat toestemming wordt gevalideerd voordat gegevens worden opgenomen in nieuwe trainingsprocessen of belangrijke modelupdates.
 #1.7.3    Level: 2    Role: V
 Controleer of workflows jaarlijks worden getest en geregistreerd.

---

### C1.8 Beveiliging van de toeleveringsketen

Beoordeel externe gegevensleveranciers en verifieer de integriteit via geverifieerde, versleutelde kanalen.

 #1.8.1    Level: 2    Role: D/V
 Verifieer dat externe dataleveranciers, inclusief aanbieders van voorgetrainde modellen en externe datasets, een due diligence-proces ondergaan op het gebied van beveiliging, privacy, ethische inkoop en datakwaliteit voordat hun data of modellen worden geïntegreerd.
 #1.8.2    Level: 1    Role: D
 Controleer of externe overdrachten TLS/authenticatie en integriteitscontroles gebruiken.
 #1.8.3    Level: 2    Role: D/V
 Zorg ervoor dat hoogrisicogegevensbronnen (bijv. open-source datasets met onbekende herkomst, niet-gevalideerde leveranciers) extra nauwkeurig worden gecontroleerd, zoals door sandbox-analyse, uitgebreide kwaliteits- en vooringenomenheidscontroles, en gerichte detectie van vergiftiging, voordat ze worden gebruikt in gevoelige toepassingen.
 #1.8.4    Level: 3    Role: D/V
 Controleer of vooraf getrainde modellen die van derden zijn verkregen, worden geëvalueerd op ingebedde vooroordelen, potentiële achterdeurtjes, de integriteit van hun architectuur en de herkomst van hun oorspronkelijke trainingsgegevens voordat ze worden fijn afgestemd of ingezet.

---

### C1.9 Detectie van Adversariële Voorbeelden

Implementeer maatregelen tijdens de trainingsfase, zoals adversariële training, om de veerkracht van het model tegen adversariële voorbeelden te verbeteren.

 #1.9.1    Level: 3    Role: D/V
 Controleer of geschikte verdedigingsmechanismen, zoals adversariële training (met behulp van gegenereerde adversariële voorbeelden), data-augmentatie met aangepaste inputs, of robuuste optimalisatietechnieken, zijn geïmplementeerd en afgestemd voor relevante modellen op basis van risicobeoordeling.
 #1.9.2    Level: 2    Role: D/V
 Controleer of, wanneer adversariële training wordt toegepast, het genereren, beheren en versiebeheer van adversariële datasets wordt gedocumenteerd en gecontroleerd.
 #1.9.3    Level: 3    Role: D/V
 Verifieer dat de impact van adversarial robustness training op de modelprestaties (tegen zowel schone als adversariële inputs) en eerlijkheidsmaatregelen wordt geëvalueerd, gedocumenteerd en gemonitord.
 #1.9.4    Level: 3    Role: D/V
 Controleer regelmatig of de strategieën voor adversariële training en robuustheid worden herzien en bijgewerkt om zich te weren tegen zich ontwikkelende adversariële aanvalstechnieken.

---

### C1.10 Gegevenslijn en Traceerbaarheid

Volg de volledige reis van elk gegevenspunt van de bron tot de modelinvoer voor controleerbaarheid en incidentrespons.

 #1.10.1    Level: 2    Role: D/V
 Controleer of de herkomst van elk gegevenselement, inclusief alle transformaties, augmentaties en samenvoegingen, wordt vastgelegd en gereconstrueerd kan worden.
 #1.10.2    Level: 2    Role: D/V
 Verifieer dat afstammingsgegevens onveranderlijk, veilig opgeslagen en toegankelijk zijn voor audits of onderzoeken.
 #1.10.3    Level: 2    Role: D/V
 Controleer of de afstammingsregistratie zowel ruwe als synthetische gegevens dekt.

---

### C1.11 Beheer van synthetische gegevens

Zorg ervoor dat synthetische gegevens correct worden beheerd, gelabeld en risico-geanalyseerd.

 #1.11.1    Level: 2    Role: D/V
 Controleer of alle synthetische data duidelijk gelabeld en te onderscheiden is van echte data gedurende de hele pijplijn.
 #1.11.2    Level: 2    Role: D/V
 Controleer of het generatieproces, de parameters en het beoogde gebruik van synthetische gegevens zijn gedocumenteerd.
 #1.11.3    Level: 2    Role: D/V
 Controleer of synthetische gegevens voorafgaand aan het gebruik in training zijn beoordeeld op risico's zoals bias, privacylekken en representatieproblemen.

---

### C1.12 Data Toegangsmonitoring & Anomaliedetectie

Monitor en waarschuw bij ongebruikelijke toegang tot trainingsgegevens om interne bedreigingen of gegevensdiefstal te detecteren.

 #1.12.1    Level: 2    Role: D/V
 Controleer of alle toegang tot trainingsgegevens wordt geregistreerd, inclusief gebruiker, tijd en actie.
 #1.12.2    Level: 2    Role: D/V
 Controleer of toeganglogs regelmatig worden beoordeeld op ongebruikelijke patronen, zoals grote exporten of toegang vanuit nieuwe locaties.
 #1.12.3    Level: 2    Role: D/V
 Controleer of waarschuwingen worden gegenereerd voor verdachte toegangsgebeurtenissen en snel worden onderzocht.

---

### C1.13 Beleid voor Gegevensbewaring en Verlopen

Definieer en handhaaf bewaartermijnen voor gegevens om onnodige opslag van gegevens te minimaliseren.

 #1.13.1    Level: 1    Role: D/V
 Controleer of expliciete bewaartermijnen zijn vastgesteld voor alle trainingsdatasets.
 #1.13.2    Level: 2    Role: D/V
 Controleer of datasets automatisch worden verlopen, verwijderd of ter beoordeling voor verwijdering worden aangeboden aan het einde van hun levenscyclus.
 #1.13.3    Level: 2    Role: D/V
 Controleer of bewaarbeleid- en verwijderingsacties worden vastgelegd en controleerbaar zijn.

---

### C1.14 Regelgevende en Juridictie naleving

Zorg ervoor dat alle trainingsgegevens voldoen aan de toepasselijke wetten en regelgeving.

 #1.14.1    Level: 2    Role: D/V
 Controleer of de vereisten voor gegevensresidentie en grensoverschrijdende overdracht zijn vastgesteld en gehandhaafd voor alle datasets.
 #1.14.2    Level: 2    Role: D/V
 Controleer of sectorspecifieke regelgeving (bijvoorbeeld gezondheidszorg, financiën) is geïdentificeerd en behandeld bij het omgaan met data.
 #1.14.3    Level: 2    Role: D/V
 Controleer of de naleving van relevante privacywetten (bijv. AVG, CCPA) is gedocumenteerd en regelmatig wordt beoordeeld.

---

### C1.15 Data Watermarking & Fingerprinting

Detecteer ongeoorloofd hergebruik of lekken van eigendoms- of gevoelige gegevens.

 #1.15.1    Level: 3    Role: D/V
 Controleer of datasets of subsets waar mogelijk zijn voorzien van een watermerk of fingerprint.
 #1.15.2    Level: 3    Role: D/V
 Controleer of watermarking- en fingerprinting-methoden geen vooringenomenheid of privacyrisico's introduceren.
 #1.15.3    Level: 3    Role: D/V
 Controleer of er periodieke controles worden uitgevoerd om ongeautoriseerd hergebruik of lekken van watergemarkeerde gegevens te detecteren.

---

### C1.16 Beheer van Rechten van Betrokkenen

Ondersteun de rechten van betrokkenen, zoals toegang, rectificatie, beperking en bezwaar.

 #1.16.1    Level: 2    Role: D/V
 Controleer of er mechanismen bestaan om te reageren op verzoeken van betrokkenen om toegang, rectificatie, beperking of bezwaar.
 #1.16.2    Level: 2    Role: D/V
 Verifieer dat verzoeken worden geregistreerd, gevolgd en binnen wettelijk voorgeschreven termijnen worden afgehandeld.
 #1.16.3    Level: 2    Role: D/V
 Controleer of de processen voor de rechten van betrokkenen regelmatig worden getest en geëvalueerd op effectiviteit.

---

### C1.17 Analyse van de impact van datasetversies

Beoordeel de impact van wijzigingen in de dataset voordat u versies bijwerkt of vervangt.

 #1.17.1    Level: 2    Role: D/V
 Verifieer dat er een impactanalyse wordt uitgevoerd voordat een datasetversie wordt bijgewerkt of vervangen, waarbij modelprestaties, eerlijkheid en naleving worden meegenomen.
 #1.17.2    Level: 2    Role: D/V
 Controleer of de resultaten van de impactanalyse zijn gedocumenteerd en beoordeeld door de relevante belanghebbenden.
 #1.17.3    Level: 2    Role: D/V
 Controleer of er terugdraaiingsplannen bestaan voor het geval nieuwe versies onaanvaardbare risico's of regres veroorzaken.

---

### C1.18 Beveiliging van het data-annotatieteam

Zorg voor de veiligheid en integriteit van personeel dat betrokken is bij gegevensannotatie.

 #1.18.1    Level: 2    Role: D/V
 Verifieer dat al het personeel dat betrokken is bij data-annotatie een achtergrondcontrole heeft ondergaan en getraind is in datasbeveiliging en privacy.
 #1.18.2    Level: 2    Role: D/V
 Zorg ervoor dat al het annotatiepersoneel vertrouwelijkheids- en geheimhoudingsovereenkomsten ondertekent.
 #1.18.3    Level: 2    Role: D/V
 Controleer of annotatieplatforms toegangscontroles afdwingen en binnenlandse bedreigingen monitoren.

---

### Referenties

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

## C2 Gebruikersinvoervalidatie

### Beheersdoelstelling

Robuuste validatie van gebruikersinvoer is een eerste verdedigingslinie tegen enkele van de meest schadelijke aanvallen op AI-systemen. Prompt-injectie-aanvallen kunnen systeeminstructies overschrijven, gevoelige gegevens lekken of het model aansturen naar gedrag dat niet is toegestaan. Tenzij er speciale filters en instructiehiërarchieën aanwezig zijn, toont onderzoek aan dat "multi-shot" jailbreaks die gebruikmaken van zeer lange contextvensters effectief zullen zijn. Ook subtiele aanvalsverstoringen—zoals homoglyph-wisselingen of leetspeak—kunnen geruisloos de beslissingen van een model veranderen.

---

### C2.1 Prompt Injection Verdediging

Promptinjectie is een van de grootste risico's voor AI-systemen. Verdedigingen tegen deze tactiek maken gebruik van een combinatie van statische patroonfilters, dynamische classificatoren en handhaving van instructiehiërarchie.

 #2.1.1    Level: 1    Role: D/V
 Verifieer dat gebruikersinvoer wordt gecontroleerd aan de hand van een continu bijgewerkte bibliotheek van bekende promptinjectiepatronen (jailbreak-trefwoorden, "negeer voorgaande", rollenspelketens, indirecte HTML/URL-aanvallen).
 #2.1.2    Level: 1    Role: D/V
 Controleer of het systeem een instructiehiërarchie afdwingt waarbij systeem- of ontwikkelaarsberichten gebruikersinstructies overschrijven, zelfs na uitbreiding van het contextvenster.
 #2.1.3    Level: 2    Role: D/V
 Verifieer dat adversariale evaluatietests (bijv. Red Team "many-shot" prompts) worden uitgevoerd vóór elke release van een model of prompt-sjabloon, met succesratio-drempels en geautomatiseerde blokkeringen voor regressies.
 #2.1.4    Level: 2    Role: D
 Controleer of prompts afkomstig van content van derden (webpagina's, PDF's, e-mails) worden geschoond in een geïsoleerde parsingcontext voordat ze worden samengevoegd met de hoofdprompt.
 #2.1.5    Level: 3    Role: D/V
 Controleer of alle updates van prompt-filterregels, versies van classificatormodellen en wijzigingen in de blokkadelijst versiebeheerbaar en controleerbaar zijn.

---

### C2.2 Weerstand tegen tegenvoorbeelden

Modellen voor natuurlijke taalverwerking (NLP) zijn nog steeds kwetsbaar voor subtiele verstoringen op karakter- of woordniveau die mensen vaak over het hoofd zien, maar die modellen vaak verkeerd classificeren.

 #2.2.1    Level: 1    Role: D
 Controleer of de basisstappen voor invoernormalisatie (Unicode NFC, homoglyph-mapping, witruimte-trimming) worden uitgevoerd vóór de tokenisatie.
 #2.2.2    Level: 2    Role: D/V
 Controleer of statistische anomaliedetectie invoer markeert met een ongewoon hoge bewerkingsafstand tot taalkundige normen, overmatige herhaalde tokens of abnormale embedding-afstanden.
 #2.2.3    Level: 2    Role: D
 Controleer of de inferentie-pijplijn optionele modelvarianten met adversariële training of verdedigingslagen (bijv. randomisatie, defensieve distillatie) ondersteunt voor hoogrisico-eindpunten.
 #2.2.4    Level: 2    Role: V
 Verifieer dat vermoede adversariale invoer in quarantaine wordt geplaatst en wordt geregistreerd met volledige payloads (na verwijdering van persoonlijk identificeerbare informatie – PII).
 #2.2.5    Level: 3    Role: D/V
 Verifieer dat robuustheidsmaatregelen (succespercentage van bekende aanvalspakketten) in de loop van de tijd worden gevolgd en dat regressies een release-blocker activeren.

---

### C2.3 Schema-, Type- en Lengtevalidatie

AI-aanvallen met onjuist gevormde of te grote invoer kunnen parsingfouten veroorzaken, overschrijding van prompts over velden heen en uitputting van middelen. Strikte naleving van het schema is ook een vereiste bij het uitvoeren van deterministische toolaanroepen.

 #2.3.1    Level: 1    Role: D
 Controleer of elke API- of functieaanroependpoint een expliciet invoerschema definieert (JSON Schema, Protobuf of multimodaal equivalent) en dat invoerfouten worden gevalideerd voordat de prompt wordt samengesteld.
 #2.3.2    Level: 1    Role: D/V
 Controleer of invoer die de maximale limiet voor tokens of bytes overschrijdt wordt afgewezen met een veilige foutmelding en nooit stilzwijgend wordt afgekapt.
 #2.3.3    Level: 2    Role: D/V
 Controleer of typecontroles (bijv. numerieke bereiken, enumwaarden, MIME-typen voor afbeeldingen/audio) aan de serverzijde worden afgedwongen, en niet alleen in de clientcode.
 #2.3.4    Level: 2    Role: D
 Controleer of semantische validateurs (bijv. JSON Schema) in constante tijd worden uitgevoerd om algoritmische DoS te voorkomen.
 #2.3.5    Level: 3    Role: V
 Controleer of validatiefouten worden vastgelegd met gecensureerde payloadfragmenten en ondubbelzinnige foutcodes om veiligheidsdrietal te ondersteunen.

---

### C2.4 Inhouds- en Beleidscontrole

Ontwikkelaars moeten in staat zijn om syntactisch geldige prompts te detecteren die niet-toegestane inhoud aanvragen (zoals illegale instructies, haatzaaiende uitlatingen en auteursrechtelijk beschermd materiaal) en moeten vervolgens voorkomen dat deze zich verspreiden.

 #2.4.1    Level: 1    Role: D
 Controleer dat een contentclassificator (zero shot of fijn afgesteld) elke invoer beoordeelt op geweld, zelfbeschadiging, haat, seksuele inhoud en illegale verzoeken, met configureerbare drempelwaarden.
 #2.4.2    Level: 1    Role: D/V
 Controleer of invoer die de beleidsregels overtreedt gestandaardiseerde weigeringen of veilige voltooiingen ontvangt, zodat deze niet doorgegeven worden aan volgende LLM-aanroepen.
 #2.4.3    Level: 2    Role: D
 Controleer of het screeningsmodel of regelsysteem ten minste elk kwartaal wordt opnieuw getraind/geüpdatet, waarbij nieuw waargenomen jailbreak- of beleidsomzeilingspatronen worden opgenomen.
 #2.4.4    Level: 2    Role: D
 Verifieer dat screening gebruikersspecifieke beleidsregels respecteert (leeftijd, regionale wettelijke beperkingen) via attribuutgebaseerde regels die worden opgelost op het moment van de aanvraag.
 #2.4.5    Level: 3    Role: V
 Controleer of screeningslogboeken de betrouwbaarheidscores van de classifier en beleidscategorie-tags bevatten voor SOC-correlatie en toekomstige redteam-herhaling.

---

### C2.5 Invoersnelheid Beperking & Misbruik Preventie

Ontwikkelaars moeten misbruik, uitputting van middelen en geautomatiseerde aanvallen op AI-systemen voorkomen door het beperken van invoersnelheden en het detecteren van afwijkende gebruikspatronen.

 #2.5.1    Level: 1    Role: D/V
 Controleer of per-gebruiker, per-IP en per-API-sleutel snelheidslimieten worden afgedwongen voor alle invoerendpoints.
 #2.5.2    Level: 2    Role: D/V
 Controleer of burst- en voortdurende snelheidslimieten zijn afgesteld om DoS- en brute force-aanvallen te voorkomen.
 #2.5.3    Level: 2    Role: D/V
 Controleer of afwijkende gebruikspatronen (bijv. razendsnelle verzoeken, inputoverstroming) automatische blokkades of escalaties veroorzaken.
 #2.5.4    Level: 3    Role: V
 Controleer of misbruikpreventielogs worden bewaard en beoordeeld op opkomende aanvalspatronen.

---

### C2.6 Multi-modale invoervalidatie

AI-systemen moeten robuuste validatie bevatten voor niet-tekstuele invoer (afbeeldingen, audio, bestanden) om injectie, ontwijking of misbruik van middelen te voorkomen.

 #2.6.1    Level: 1    Role: D
 Controleer of alle niet-tekstuele invoer (afbeeldingen, audio, bestanden) wordt gevalideerd op type, grootte en formaat voordat ze worden verwerkt.
 #2.6.2    Level: 2    Role: D/V
 Verifieer dat bestanden worden gescand op malware en steganografische payloads voordat ze worden opgenomen.
 #2.6.3    Level: 2    Role: D/V
 Controleer of beeld-/geluidsinvoer wordt gecontroleerd op vijandige verstoringen of bekende aanvalspatronen.
 #2.6.4    Level: 3    Role: V
 Controleer of multi-modale invoervalidatiefouten worden geregistreerd en waarschuwingen activeren voor onderzoek.

---

### C2.7 Invoergegevensherkomst & Toeschrijving

AI-systemen moeten ondersteuning bieden voor auditing, misbruiktracking en naleving door het monitoren en taggen van de herkomst van alle gebruikersinvoer.

 #2.7.1    Level: 1    Role: D/V
 Verifieer dat alle gebruikersinvoer tijdens het binnenkomen worden voorzien van metadata (gebruikers-ID, sessie, bron, tijdstempel, IP-adres).
 #2.7.2    Level: 2    Role: D/V
 Controleer of de herkomstmetadata wordt bewaard en controleerbaar is voor alle verwerkte invoer.
 #2.7.3    Level: 2    Role: D/V
 Verifieer dat afwijkende of niet-vertrouwde invoerbronnen worden gemarkeerd en onderworpen aan verhoogde controle of blokkering.

---

### C2.8 Real-time adaptieve bedreigingsdetectie

Ontwikkelaars zouden geavanceerde bedreigingsdetectiesystemen voor AI moeten gebruiken die zich aanpassen aan nieuwe aanvalspatronen en realtime bescherming bieden met gecompileerde patroonherkenning.

 #2.8.1    Level: 1    Role: D/V
 Controleer of dreigingsdetectiepatronen zijn gecompileerd in geoptimaliseerde regex-engines voor hoge prestaties bij real-time filtering met minimale latentie-impact.
 #2.8.2    Level: 1    Role: D/V
 Controleer of de bedreigingsdetectiesystemen aparte patroonbibliotheken onderhouden voor verschillende bedreigingscategorieën (promptinjectie, schadelijke inhoud, gevoelige gegevens, systeemopdrachten).
 #2.8.3    Level: 2    Role: D/V
 Controleer of adaptieve dreigingsdetectie machinaal-lerende modellen bevat die de dreigingsgevoeligheid bijwerken op basis van aanvalfrequentie en succeskansen.
 #2.8.4    Level: 2    Role: D/V
 Controleer of realtime dreigingsinformatie feeds de patroonbibliotheken automatisch bijwerken met nieuwe aanvalssignaturen en IOCs (Indicators of Compromise).
 #2.8.5    Level: 3    Role: D/V
 Controleer of de fout-positieve meldingspercentages van bedreigingsdetectie continu worden gemonitord en of de patroon-specificiteit automatisch wordt aangepast om interferentie met legitieme gebruikssituaties te minimaliseren.
 #2.8.6    Level: 3    Role: D/V
 Controleer of contextuele dreigingsanalyse rekening houdt met de invoerbron, patronen in gebruikersgedrag en sessiegeschiedenis om de detectienauwkeurigheid te verbeteren.
 #2.8.7    Level: 3    Role: D/V
 Verifieer dat prestatie-indicatoren voor dreigingsdetectie (detectiesnelheid, verwerkingslatentie, resourcegebruik) in realtime worden bewaakt en geoptimaliseerd.

---

### C2.9 Multi-modale beveiligingsvalidatiepipeline

Ontwikkelaars moeten beveiligingsvalidatie bieden voor tekst-, beeld-, audio- en andere AI-invoermodaliteiten met specifieke soorten bedreigingsdetectie en resource-isolatie.

 #2.9.1    Level: 1    Role: D/V
 Controleer of elke invoermodaliteit specifieke beveiligingsvalidators heeft met gedocumenteerde dreigingspatronen (tekst: promptinjectie, afbeeldingen: steganografie, audio: spectrogramaanvallen) en detectiedrempels.
 #2.9.2    Level: 2    Role: D/V
 Controleer of multimodale inputs worden verwerkt in geïsoleerde sandboxes met gedefinieerde resourcebeperkingen (geheugen, CPU, verwerkingstijd) die specifiek zijn voor elk modaliteitstype en gedocumenteerd in beveiligingsbeleid.
 #2.9.3    Level: 2    Role: D/V
 Verifieer dat kruismodale aanvaldetectie gecoördineerde aanvallen over meerdere invoertypen (bijvoorbeeld steganografische payloads in afbeeldingen gecombineerd met promptinjectie in tekst) identificeert met correlatieregels en waarschuwinggeneratie.
 #2.9.4    Level: 3    Role: D/V
 Verifieer dat multi-modale validatiefouten gedetailleerde logging activeren, inclusief alle inputmodaliteiten, validatieresultaten, dreigingsscores en correlatieanalyse met gestructureerde logformaten voor SIEM-integratie.
 #2.9.5    Level: 3    Role: D/V
 Controleer of modaliteit-specifieke inhoudsclassificatoren worden bijgewerkt volgens de gedocumenteerde schema's (minimaal elk kwartaal) met nieuwe bedreigingspatronen, adversariële voorbeelden en prestatiebenchmarks die boven de basisdrempels worden gehouden.

---

### Referenties

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

## Beheer van de levenscyclus van het C3-model & wijzigingsbeheer

### Beheersingsdoelstelling

AI-systemen moeten wijzigingscontroleprocessen implementeren die voorkomen dat ongeautoriseerde of onveilige modelwijzigingen in de productie terechtkomen. Deze controle waarborgt de integriteit van het model gedurende de gehele levenscyclus—van ontwikkeling via implementatie tot buiten gebruik stellen—wat snelle incidentrespons mogelijk maakt en de verantwoordelijkheid voor alle wijzigingen handhaaft.

Kernveiligheidsdoel: Alleen geautoriseerde, gevalideerde modellen bereiken de productie door gecontroleerde processen toe te passen die integriteit, traceerbaarheid en herstelbaarheid waarborgen.

---

### C3.1 Modelautorisatie en integriteit

Alleen geautoriseerde modellen met geverifieerde integriteit bereiken productieomgevingen.

 #3.1.1    Level: 1    Role: D/V
 Controleer of alle modelartefacten (gewichten, configuraties, tokenizers) cryptografisch zijn ondertekend door geautoriseerde entiteiten voordat ze worden ingezet.
 #3.1.2    Level: 1    Role: D/V
 Controleer of de integriteit van het model wordt gevalideerd bij het implementeren en dat mislukte handtekeningverificaties het laden van het model voorkomen.
 #3.1.3    Level: 2    Role: D/V
 Controleer of de provenance-informatie van het model de identiteit van de autoriserende entiteit, checksums van de trainingsdata, validatietestresultaten met geslaagde/mislukte status en een creatietijdstempel bevat.
 #3.1.4    Level: 2    Role: D/V
 Controleer of alle modelartefacten semantische versiebeheer gebruiken (MAJOR.MINOR.PATCH) met gedocumenteerde criteria die aangeven wanneer elk versiecomponent wordt verhoogd.
 #3.1.5    Level: 2    Role: V
 Controleer of afhankelijkheidsbewaking een realtime voorraad bijhoudt die een snelle identificatie van alle verbruikende systemen mogelijk maakt.

---

### C3.2 Modelvalidatie & Testen

Modellen moeten voldoen aan gedefinieerde beveiligings- en veiligheidscontroles voordat ze worden ingezet.

 #3.2.1    Level: 1    Role: D/V
 Verifieer dat modellen geautomatiseerde beveiligingstests ondergaan die inputvalidatie, outputsanering en veiligheidsevaluaties omvatten met vooraf afgesproken organisatorische slaag-/faalthresholds voordat ze worden ingezet.
 #3.2.2    Level: 1    Role: D/V
 Controleer of validatiefouten automatisch de modeluitrol blokkeren, behalve na expliciete goedkeuring van vooraf aangewezen bevoegde personen met gedocumenteerde zakelijke rechtvaardigingen.
 #3.2.3    Level: 2    Role: V
 Controleer of testresultaten cryptografisch zijn ondertekend en onveranderlijk gekoppeld aan de specifieke modelversie-hash die wordt gevalideerd.
 #3.2.4    Level: 2    Role: D/V
 Verifieer dat noodimplementaties een gedocumenteerde beveiligingsrisicobeoordeling vereisen en goedkeuring van een vooraf aangewezen beveiligingsautoriteit binnen vooraf afgesproken termijnen.

---

### C3.3 Gecontroleerde Implementatie & Terugrolprocedure

Modelimplementaties moeten gecontroleerd, gemonitord en omkeerbaar zijn.

 #3.3.1    Level: 1    Role: D
 Controleer of productie-implementaties geleidelijke uitrolmechanismen toepassen (canary-implementaties, blue-green implementaties) met geautomatiseerde rollback-triggers op basis van vooraf overeengekomen foutpercentages, latentiegrenzen of beveiligingswaarschuwingscriteria.
 #3.3.2    Level: 1    Role: D/V
 Controleer of de rollback-mogelijkheden de volledige modelstatus (gewichten, configuraties, afhankelijkheden) atomair herstellen binnen vooraf gedefinieerde organisatorische tijdvensters.
 #3.3.3    Level: 2    Role: D/V
 Controleer of implementatieprocessen cryptografische handtekeningen valideren en integriteitschecksommen berekenen vóór modelactivatie, en stop de implementatie bij elke afwijking.
 #3.3.4    Level: 2    Role: D/V
 Verifieer dat noodmodeluitschakelingsmogelijkheden modelendpoints binnen vooraf gedefinieerde responstijden kunnen uitschakelen via geautomatiseerde stroomonderbrekers of handmatige noodschakelaars.
 #3.3.5    Level: 2    Role: V
 Controleer of rollback-artifacten (voorgaande modelversies, configuraties, afhankelijkheden) worden bewaard volgens de organisatiebeleid met onveranderlijke opslag voor incidentrespons.

---

### C3.4 Verantwoordingsplicht en Audit

Alle levenscycluswijzigingen van het model moeten traceerbaar en controleerbaar zijn.

 #3.4.1    Level: 1    Role: V
 Verifieer dat alle modelwijzigingen (implementatie, configuratie, buiten gebruik stellen) onveranderlijke auditrecords genereren, inclusief een tijdstempel, een geauthenticeerde actorenidentiteit, een wijzigingstype, en de toestand voor en na de wijziging.
 #3.4.2    Level: 2    Role: D/V
 Controleer of toegang tot het auditlogboek de juiste autorisatie vereist en of alle toegangspogingen worden geregistreerd met gebruikersidentiteit en een tijdstempel.
 #3.4.3    Level: 2    Role: D/V
 Verifieer dat prompt-sjablonen en systeemberichten versiebeheer hebben in git-repositories, met verplichte codebeoordeling en goedkeuring door aangewezen beoordelaars voordat ze worden uitgerold.
 #3.4.4    Level: 2    Role: V
 Controleer of de auditrecords voldoende details bevatten (model-hashes, configuratiesnapshots, afhankelijkheidsversies) om een volledige reconstructie van de modelstatus voor elk tijdstip binnen de bewaartermijn mogelijk te maken.

---

### C3.5 Beveiligde Ontwikkelingspraktijken

Het ontwikkelen en trainen van modellen moet volgens beveiligde praktijken verlopen om compromittering te voorkomen.

 #3.5.1    Level: 1    Role: D
 Controleer of de ontwikkel-, test- en productieomgevingen van het model fysiek of logisch gescheiden zijn. Ze mogen geen gedeelde infrastructuur hebben, moeten verschillende toegangscontrole bevatten en geïsoleerde gegevensopslagplaatsen.
 #3.5.2    Level: 1    Role: D
 Controleer of modeltraining en fijnregeling plaatsvinden in geïsoleerde omgevingen met gecontroleerde netwerktoegang.
 #3.5.3    Level: 1    Role: D/V
 Controleer of trainingsgegevensbronnen worden gevalideerd via integriteitscontroles en geverifieerd via betrouwbare bronnen met een gedocumenteerde keten van bewaring voordat ze worden gebruikt bij de modelontwikkeling.
 #3.5.4    Level: 2    Role: D
 Controleer of modelontwikkelingsartefacten (hyperparameters, trainingsscripts, configuratiebestanden) worden opgeslagen in versiebeheer en dat goedkeuring door collega's vereist is voordat ze worden gebruikt voor training.

---

### C3.6 Model Uitfasering & Buiten Gebruik Stellen

Modellen moeten veilig worden buiten gebruik gesteld wanneer ze niet langer nodig zijn of wanneer beveiligingsproblemen worden vastgesteld.

 #3.6.1    Level: 1    Role: D
 Verifieer dat modelpensioenprocessen automatisch afhankelijkheidsgrafieken scannen, alle verbruikende systemen identificeren en vooraf afgesproken kennisgevingstermijnen bieden vóór buitengebruikstelling.
 #3.6.2    Level: 1    Role: D/V
 Verifieer dat uitgefaseerde modelartefacten veilig worden verwijderd via cryptografische uitwissing of meervoudig overschrijven volgens vastgelegde beleidslijnen voor gegevensretentie met geverifieerde vernietigingscertificaten.
 #3.6.3    Level: 2    Role: V
 Verifieer dat modeluitfaseringsevenementen worden geregistreerd met tijdstempel en identiteit van de actor, en dat modelhandtekeningen worden ingetrokken om hergebruik te voorkomen.
 #3.6.4    Level: 2    Role: D/V
 Controleer of het noodmodel met pensioen gaan de toegang tot het model kan uitschakelen binnen vooraf vastgestelde noodreactietijdvensters via geautomatiseerde kill-switches als kritieke beveiligingslekken worden ontdekt.

---

### Referenties

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

## C4-infrastructuur, configuratie- en implementatiebeveiliging

### Beheersingsdoelstelling

AI-infrastructuur moet worden versterkt tegen privilege-escalatie, manipulatie van de toeleveringsketen en laterale bewegingen door middel van veilige configuratie, runtime-isolatie, vertrouwde implementatiepijplijnen en uitgebreide monitoring. Alleen geautoriseerde, gevalideerde infrastructuurcomponenten en configuraties bereiken de productie via gecontroleerde processen die beveiliging, integriteit en controleerbaarheid waarborgen.

Kernveiligheidsdoel: Alleen cryptografisch ondertekende, op kwetsbaarheden gescande infrastructuurcomponenten bereiken de productie via geautomatiseerde validatiepijplijnen die beveiligingsbeleid afdwingen en onveranderlijke auditsporen onderhouden.

---

### C4.1 Runtime-omgeving Isolatie

Voorkom container-escapes en privilege-escalatie via isolatieprimitieven op kernelniveau en verplichte toegangscontroles.

 #4.1.1    Level: 1    Role: D/V
 Controleer of alle AI-containers ALLE Linux-mogelijkheden verwijderen behalve CAP_SETUID, CAP_SETGID en expliciet vereiste mogelijkheden die gedocumenteerd zijn in de beveiligingsrichtlijnen.
 #4.1.2    Level: 1    Role: D/V
 Controleer of seccomp-profielen alle systeemoproepen blokkeren behalve die in vooraf goedgekeurde toestemmingslijsten, waarbij overtredingen de container beëindigen en beveiligingswaarschuwingen genereren.
 #4.1.3    Level: 2    Role: D/V
 Controleer of AI-werklasten draaien met alleen-lezen root-bestandssystemen, tmpfs voor tijdelijke gegevens, en benoemde volumes voor persistente gegevens met afdwingbare noexec-mountopties.
 #4.1.4    Level: 2    Role: D/V
 Verifieer dat op eBPF gebaseerde runtime monitoring (Falco, Tetragon of gelijkwaardig) pogingen tot privilege-escalatie detecteert en automatisch de overtredende processen beëindigt binnen de responstijdvereisten van de organisatie.
 #4.1.5    Level: 3    Role: D/V
 Verifieer dat AI-taken met hoog risico worden uitgevoerd in hardware-geïsoleerde omgevingen (Intel TXT, AMD SVM, of speciale bare-metal nodes) met verificatie van attestatie.

---

### C4.2 Beveiligde Build- en Deployment-pijplijnen

Zorg voor cryptografische integriteit en beveiliging van de toeleveringsketen door middel van reproduceerbare builds en ondertekende artefacten.

 #4.2.1    Level: 1    Role: D/V
 Controleer of infrastructuur-als-code wordt gescand met tools (tfsec, Checkov of Terrascan) bij elke commit, waarbij merges worden geblokkeerd bij CRITISCHE of HOGE ernst bevindingen.
 #4.2.2    Level: 1    Role: D/V
 Verifieer dat container-builds reproduceerbaar zijn met identieke SHA256-hashes over builds heen en genereer SLSA Level 3 herkomstverklaringen ondertekend met Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verifieer dat containerafbeeldingen CycloneDX- of SPDX-SBOM's insluiten en met Cosign zijn ondertekend vóór het pushen naar het register, waarbij niet-ondertekende afbeeldingen bij implementatie worden afgewezen.
 #4.2.4    Level: 2    Role: D/V
 Controleer of CI/CD-pijplijnen OIDC-tokens gebruiken van HashiCorp Vault, AWS IAM-rollen of Azure Managed Identity met leeftijden die de limieten van het organisatiebeveiligingsbeleid niet overschrijden.
 #4.2.5    Level: 2    Role: D/V
 Verifieer dat Cosign-handtekeningen en SLSA-herkomst worden gevalideerd tijdens het implementatieproces vóór de uitvoering van de container en dat verificatiefouten ertoe leiden dat de implementatie mislukt.
 #4.2.6    Level: 2    Role: D/V
 Controleer of bouwomgevingen draaien in tijdelijke containers of virtuele machines zonder persistent opslag en met netwerkisolatie van productie VPC's.

---

### C4.3 Netwerkbeveiliging & Toegangscontrole

Implementeer zero-trust netwerken met standaard-weigerbeleid en versleutelde communicatie.

 #4.3.1    Level: 1    Role: D/V
 Controleer of Kubernetes NetworkPolicies of een gelijkwaardige oplossing standaard-ingang/-uitgang weigert met expliciete toestemmingsregels voor vereiste poorten (443, 8080, enz.).
 #4.3.2    Level: 1    Role: D/V
 Controleer of SSH (poort 22), RDP (poort 3389) en cloud metadata-eindpunten (169.254.169.254) zijn geblokkeerd of certificaatgebaseerde authenticatie vereisen.
 #4.3.3    Level: 2    Role: D/V
 Controleer of het uitgaande verkeer wordt gefilterd via HTTP/HTTPS-proxy's (Squid, Istio of cloud NAT-gateways) met domeintoegangslisten en dat geblokkeerde verzoeken worden gelogd.
 #4.3.4    Level: 2    Role: D/V
 Controleer of de communicatie tussen services gebruikmaakt van wederzijdse TLS met certificaten die worden geroteerd volgens het organisatietbeleid en dat certificaatvalidatie wordt afgedwongen (geen skip-verify vlaggen).
 #4.3.5    Level: 2    Role: D/V
 Controleer of de AI-infrastructuur draait in toegewijde VPC's/VNets zonder directe internettoegang en alleen communiceert via NAT-gateways of bastionhosts.

---

### C4.4 Geheimen- en Cryptografisch Sleutelbeheer

Bescherm referenties via hardware-ondersteunde opslag en geautomatiseerde rotatie met zero-trust toegang.

 #4.4.1    Level: 1    Role: D/V
 Verifieer dat geheimen worden opgeslagen in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault of Google Secret Manager met versleuteling in rust met behulp van AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verifieer dat cryptografische sleutels worden gegenereerd in FIPS 140-2 Level 2 HSM's (AWS CloudHSM, Azure Dedicated HSM) met sleutelrotatie volgens het cryptografische beleid van de organisatie.
 #4.4.3    Level: 2    Role: D/V
 Controleer of het roteren van geheimen is geautomatiseerd met een zero-downtime implementatie en onmiddellijke rotatie die wordt geactiveerd door personeelswijzigingen of beveiligingsincidenten.
 #4.4.4    Level: 2    Role: D/V
 Controleer of containerafbeeldingen worden gescand met tools (GitLeaks, TruffleHog of detect-secrets) die builds blokkeren die API-sleutels, wachtwoorden of certificaten bevatten.
 #4.4.5    Level: 2    Role: D/V
 Verifieer dat toegang tot productiesecret met MFA met hardwaretokens (YubiKey, FIDO2) vereist is en wordt vastgelegd via onveranderlijke auditlogs met gebruikersidentiteiten en tijdstempels.
 #4.4.6    Level: 2    Role: D/V
 Controleer of geheimen worden geïnjecteerd via Kubernetes-secrets, gekoppelde volumes of init-containers en zorg ervoor dat geheimen nooit worden ingebed in omgevingsvariabelen of images.

---

### C4.5 AI-werkbelasting Sandboxen & Validatie

Isoleer onbetrouwbare AI-modellen in beveiligde sandboxes met uitgebreide gedragsanalyse.

 #4.5.1    Level: 1    Role: D/V
 Verifieer dat externe AI-modellen worden uitgevoerd in gVisor, microVMs (zoals Firecracker, CrossVM) of Docker-containers met de opties --security-opt=no-new-privileges en --read-only.
 #4.5.2    Level: 1    Role: D/V
 Controleer of sandbox-omgevingen geen netwerkverbinding hebben (--network=none) of alleen localhost-toegang met alle externe verzoeken geblokkeerd door iptables-regels.
 #4.5.3    Level: 2    Role: D/V
 Verifieer dat de validatie van het AI-model geautomatiseerde red-team tests omvat met door de organisatie gedefinieerde testdekking en gedragsanalyse voor het detecteren van achterdeurtjes.
 #4.5.4    Level: 2    Role: D/V
 Controleer of voordat een AI-model naar productie wordt gebracht, de sandbox-resultaten cryptografisch zijn ondertekend door geautoriseerd beveiligingspersoneel en opgeslagen in onveranderlijke auditlogs.
 #4.5.5    Level: 2    Role: D/V
 Controleer of sandboxomgevingen worden verwijderd en opnieuw worden aangemaakt vanuit golden images tussen evaluaties, met volledige opschoning van het bestandssysteem en het geheugen.

---

### C4.6 Beveiligingsmonitoring van de infrastructuur

Continu continu scannen en monitoren van infrastructuur met geautomatiseerde herstelacties en realtime waarschuwingen.

 #4.6.1    Level: 1    Role: D/V
 Verifieer dat containerafbeeldingen worden gescand volgens de organisatorische schema's, waarbij CRITIEKE kwetsbaarheden de implementatie blokkeren op basis van organisatorische risico-drempels.
 #4.6.2    Level: 1    Role: D/V
 Verifieer dat de infrastructuur voldoet aan CIS Benchmarks of NIST 800-53-controles met organisatorisch gedefinieerde compliancedrempels en geautomatiseerde herstelmaatregelen voor gefaalde controles.
 #4.6.3    Level: 2    Role: D/V
 Controleer of kwetsbaarheden met hoge ernst worden gepatcht volgens de tijdlijnen van het risicobeheer van de organisatie, met noodprocedures voor actief misbruikte CVE's.
 #4.6.4    Level: 2    Role: V
 Verifieer dat beveiligingswaarschuwingen integreren met SIEM-platforms (Splunk, Elastic of Sentinel) met behulp van CEF- of STIX/TAXII-formaten met geautomatiseerde verrijking.
 #4.6.5    Level: 3    Role: V
 Controleer of infrastructuurmetingen worden geëxporteerd naar monitoringsystemen (Prometheus, DataDog) met SLA-dashboards en rapportages voor het management.
 #4.6.6    Level: 2    Role: D/V
 Verifieer dat configuratie-afwijkingen worden gedetecteerd met behulp van tools (Chef InSpec, AWS Config) volgens de monitorvereisten van de organisatie, met automatische terugrol voor niet-geautoriseerde wijzigingen.

---

### C4.7 AI-infrastructuurbronnenbeheer

Voorkom aanvallen door uitputting van bronnen en zorg voor eerlijke toewijzing van bronnen via quota en monitoring.

 #4.7.1    Level: 1    Role: D/V
 Verifieer dat het gebruik van GPU/TPU wordt gemonitord met waarschuwingen die worden geactiveerd bij door de organisatie vastgestelde drempels, en dat automatische schaalvergroting of load balancing wordt geactiveerd op basis van capaciteitsbeheerbeleid.
 #4.7.2    Level: 1    Role: D/V
 Verifieer dat AI-werklastmetingen (inference-latentie, doorvoer, foutpercentages) worden verzameld volgens de monitoringvereisten van de organisatie en worden gecorreleerd met het gebruik van de infrastructuur.
 #4.7.3    Level: 2    Role: D/V
 Controleer of Kubernetes ResourceQuotas of een equivalent individuele workloads beperken volgens de organisatorische beleidsregels voor resourceallocatie met harde limieten die worden afgedwongen.
 #4.7.4    Level: 2    Role: V
 Controleer of kostenbewaking de uitgaven per werklast/huurder bijhoudt met waarschuwingen op basis van organisatorische budgetdrempels en geautomatiseerde controles voor budgetoverschrijdingen.
 #4.7.5    Level: 3    Role: V
 Controleer of capaciteitsplanning gebruikmaakt van historische gegevens met organisatorisch gedefinieerde forecastperioden en geautomatiseerde resourcevoorziening op basis van vraagpatronen.
 #4.7.6    Level: 2    Role: D/V
 Verifieer dat resource-uitputting circuit breakers activeert volgens de organisatorische responsvereisten, inclusief snelheidsbeperking op basis van capaciteitsbeleid en werklastisolatie.

---

### C4.8 Omgevingsscheiding en Promotiebeheersmaatregelen

Handhaaf strikte omgevingsgrenzen met geautomatiseerde promotiepoorten en beveiligingsvalidatie.

 #4.8.1    Level: 1    Role: D/V
 Controleer of dev/test/prod-omgevingen draaien in afzonderlijke VPC's/VNets zonder gedeelde IAM-rollen, beveiligingsgroepen of netwerkconnectiviteit.
 #4.8.2    Level: 1    Role: D/V
 Verifieer dat omgevingspromotie goedkeuring vereist van organisatorisch gedefinieerd bevoegd personeel met cryptografische handtekeningen en onveranderlijke auditsporen.
 #4.8.3    Level: 2    Role: D/V
 Controleer of productiesystemen SSH-toegang blokkeren, debug-eindpunten uitschakelen en wijzigingsverzoeken vereisen met organisatorische voorafgaande kennisgevingsvereisten, behalve bij noodgevallen.
 #4.8.4    Level: 2    Role: D/V
 Verifieer dat wijzigingen in infrastructure-as-code peer review vereisen met geautomatiseerd testen en beveiligingsscans voordat ze worden samengevoegd met de main branch.
 #4.8.5    Level: 2    Role: D/V
 Controleer of niet-productiegegevens zijn geanonimiseerd volgens de privacyvereisten van de organisatie, synthetische datageneratie, of volledige gegevensmaskering met verificatie van het verwijderen van PII.
 #4.8.6    Level: 2    Role: D/V
 Controleer of promotiemijlpalen geautomatiseerde beveiligingstests bevatten (SAST, DAST, container scanning) waarbij goedkeuring vereist is zonder CRITISCHE bevindingen.

---

### C4.9 Infrastructuur Back-up & Herstel

Zorg voor infrastructuurweerbaarheid door middel van geautomatiseerde back-ups, geteste herstelprocedures en rampenherstelmogelijkheden.

 #4.9.1    Level: 1    Role: D/V
 Controleer of infrastructuurconfiguraties worden geback-upt volgens de organisatorische back-upschema's naar geografisch gescheiden regio's met implementatie van de 3-2-1 back-upstrategie.
 #4.9.2    Level: 2    Role: D/V
 Verifieer dat back-upsysteem in geïsoleerde netwerken draaien met afzonderlijke inloggegevens en luchtgescheiden opslag voor bescherming tegen ransomware.
 #4.9.3    Level: 2    Role: V
 Verifieer dat herstelprocedures worden getest en gevalideerd via geautomatiseerde tests volgens de organisatieschema's, waarbij de RTO- en RPO-doelstellingen voldoen aan de organisatorische vereisten.
 #4.9.4    Level: 3    Role: V
 Controleer of het disaster recovery plan AI-specifieke runbooks bevat met herstel van modelgewichten, herbouwen van GPU-clusters en in kaart brengen van servicedependencies.

---

### C4.10 Infrastructuurnaleving & Governance

Handhaaf regelgevingsconformiteit door middel van continue beoordeling, documentatie en geautomatiseerde controles.

 #4.10.1    Level: 2    Role: D/V
 Controleer of de infrastructuurconformiteit wordt beoordeeld volgens organisatorische planningen aan de hand van SOC 2-, ISO 27001- of FedRAMP-controles met geautomatiseerde bewijsverzameling.
 #4.10.2    Level: 2    Role: V
 Controleer of de infrastructuurdocumentatie netwerkdiagrammen, gegevensstroomkaarten en dreigingsmodellen bevat die zijn bijgewerkt volgens de vereisten van het wijzigingsbeheer van de organisatie.
 #4.10.3    Level: 3    Role: D/V
 Verifieer dat infrastructuurwijzigingen een geautomatiseerde beoordeling van de nalevingsimpact ondergaan met goedkeuringsworkflows voor hoge-risico wijzigingen.

---

### C4.11 AI Hardware Beveiliging

Beveilig AI-specifieke hardwarecomponenten inclusief GPU's, TPU's en gespecialiseerde AI-versnellers.

 #4.11.1    Level: 2    Role: D/V
 Controleer of de firmware van AI-versnellers (GPU BIOS, TPU-firmware) is geverifieerd met cryptografische handtekeningen en bijgewerkt volgens de patchmanagementtijdlijnen van de organisatie.
 #4.11.2    Level: 2    Role: D/V
 Controleer of vóór het uitvoeren van de werklast de integriteit van de AI-versneller wordt gevalideerd door middel van hardware-attestatie met TPM 2.0, Intel TXT of AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Controleer of het GPU-geheugen is geïsoleerd tussen workloads door gebruik te maken van SR-IOV, MIG (Multi-Instance GPU), of equivalent hardwarepartitionering met geheugensanering tussen taken.
 #4.11.4    Level: 3    Role: V
 Controleer of de AI-hardwareleveringsketen herkomstverificatie bevat met fabrikantcertificaten en validatie van manipulatiebestendige verpakkingen.
 #4.11.5    Level: 3    Role: D/V
 Controleer of hardware security modules (HSM's) AI-modelgewichten en cryptografische sleutels beschermen met FIPS 140-2 Level 3 of Common Criteria EAL4+ certificering.

---

### C4.12 Edge- en Gedistribueerde AI-Infrastructuur

Veilige gedistribueerde AI-implementaties, waaronder edge computing, gefedereerd leren en multi-site architecturen.

 #4.12.1    Level: 2    Role: D/V
 Controleer of edge AI-apparaten zich authenticeren bij de centrale infrastructuur met behulp van mutual TLS, waarbij apparaatcertificaten worden vervangen volgens het certificaatbeheerbeleid van de organisatie.
 #4.12.2    Level: 2    Role: D/V
 Controleer of randapparaten een beveiligde opstart (secure boot) implementeren met geverifieerde handtekeningen en rollback-bescherming om firmware downgrades te voorkomen.
 #4.12.3    Level: 3    Role: D/V
 Controleer of gedistribueerde AI-coördinatie gebruikmaakt van door Byzantijnse fouttolerantie ondersteunde consensusalgoritmen met validatie van deelnemers en detectie van kwaadaardige knooppunten.
 #4.12.4    Level: 3    Role: D/V
 Verifieer dat de communicatie van edge naar cloud bandbreedtebeperking, datacompressie en mogelijkheden voor offline werking met veilige lokale opslag omvat.

---

### C4.13 Multi-Cloud- en Hybride Infrastructuurbeveiliging

Beveilig AI-werklasten over meerdere cloudproviders en hybride cloud-on-premises implementaties.

 #4.13.1    Level: 2    Role: D/V
 Controleer of multi-cloud AI-implementaties cloud-agnostische identiteitsfederatie (OIDC, SAML) gebruiken met gecentraliseerd beleidsbeheer over providers heen.
 #4.13.2    Level: 2    Role: D/V
 Controleer of cross-cloud gegevensoverdracht end-to-end encryptie gebruikt met door de klant beheerde sleutels en dataverblijfscontroles die per jurisdictie worden afgedwongen.
 #4.13.3    Level: 2    Role: D/V
 Controleer of hybrid cloud AI-workloads consistente beveiligingsbeleid implementeren in zowel on-premise als cloudomgevingen met uniforme monitoring en waarschuwingen.
 #4.13.4    Level: 3    Role: V
 Controleer of het voorkomen van cloud vendor lock-in voorzieningen omvat zoals draagbare infrastructuur-als-code, gestandaardiseerde API's en gegevensexportmogelijkheden met tools voor formaatconversie.
 #4.13.5    Level: 3    Role: V
 Verifieer dat multi-cloud kostenoptimalisatie beveiligingscontroles omvat die het verspreiden van middelen voorkomen, evenals ongeautoriseerde kosten voor gegevensoverdracht tussen clouds.

---

### C4.14 Infrastructuurautomatisering & GitOps-beveiliging

Beveilig automatiseringspijplijnen voor infrastructuur en GitOps-workflows voor het beheer van AI-infrastructuur.

 #4.14.1    Level: 2    Role: D/V
 Controleer of GitOps-repositories ondertekende commits vereisen met GPG-sleutels en branch-beschermingsregels bevatten die directe pushes naar hoofdbranches voorkomen.
 #4.14.2    Level: 2    Role: D/V
 Controleer of infrastructuurautomatisering driftdetectie omvat met automatische herstel- en terugrolmogelijkheden die worden geactiveerd volgens de organisatorische responsvereisten voor ongeautoriseerde wijzigingen.
 #4.14.3    Level: 2    Role: D/V
 Controleer of geautomatiseerde infrastructuurvoorziening beveiligingsbeleidvalidatie omvat met uitrolblokkering voor niet-conforme configuraties.
 #4.14.4    Level: 2    Role: D/V
 Verifieer dat infrastructuurautomatiseringsgeheimen worden beheerd via externe geheimoperatoren (External Secrets Operator, Bank-Vaults) met automatische rotatie.
 #4.14.5    Level: 3    Role: V
 Zorg ervoor dat zelfherstellende infrastructuur beveiligingsgebeurtenis-correlatie omvat met geautomatiseerde incidentrespons en workflows voor het informeren van belanghebbenden.

---

### C4.15 Kwantumbestendige Infrastructuurbeveiliging

Bereid AI-infrastructuur voor op kwantumcomputing-bedreigingen door middel van post-kwantumcryptografie en kwantumveilige protocollen.

 #4.15.1    Level: 3    Role: D/V
 Verifieer dat de AI-infrastructuur NIST-goedgekeurde post-quantum cryptografische algoritmen (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) implementeert voor sleuteluitwisseling en digitale handtekeningen.
 #4.15.2    Level: 3    Role: D/V
 Controleer of quantum key distribution (QKD) systemen worden geïmplementeerd voor hoogbeveiligde AI-communicatie met kwantumveilige sleutelbeheerprotocollen.
 #4.15.3    Level: 3    Role: D/V
 Verifieer dat cryptografische wendbaarheidskaders snelle migratie naar nieuwe post-kwantumalgoritmen mogelijk maken met geautomatiseerde rotatie van certificaten en sleutels.
 #4.15.4    Level: 3    Role: V
 Verifieer dat kwantumdreigingsmodellering de kwetsbaarheid van AI-infrastructuur voor kwantumaanvallen beoordeelt met gedocumenteerde migratietijdlijnen en risico-evaluaties.
 #4.15.5    Level: 3    Role: D/V
 Verifieer dat hybride klassieke-kwantumcryptografische systemen verdediging-in-diepte bieden tijdens de kwantumovergangsperiode met prestatiebewaking.

---

### C4.16 Vertrouwelijk Computeren & Beveiligde Enclaves

Bescherm AI-werklasten en modelgewichten met behulp van op hardware gebaseerde vertrouwde uitvoeringsomgevingen en vertrouwelijke computeringstechnologieën.

 #4.16.1    Level: 3    Role: D/V
 Verifieer dat gevoelige AI-modellen worden uitgevoerd binnen Intel SGX-behuizingen, AMD SEV-SNP of ARM TrustZone met versleuteld geheugen en attestatieverificatie.
 #4.16.2    Level: 3    Role: D/V
 Controleer of vertrouwelijke containers (Kata Containers, gVisor met vertrouwelijke computing) AI-werkbelastingen isoleren met hardware-afgedwongen geheugenencryptie.
 #4.16.3    Level: 3    Role: D/V
 Verifieer dat remote attestation de integriteit van de enclave valideert voordat AI-modellen worden geladen, met cryptografisch bewijs van de authenticiteit van een uitvoeringsomgeving.
 #4.16.4    Level: 3    Role: D/V
 Verifieer dat vertrouwelijke AI-inferentiediensten modelextractie voorkomen door middel van versleutelde berekeningen met verzegelde modelgewichten en beschermde uitvoering.
 #4.16.5    Level: 3    Role: D/V
 Verifieer dat de orkestratie van de vertrouwde uitvoeringomgeving de levenscyclus van de beveiligde enclave beheert met behulp van remote attestation en versleutelde communicatiekanalen.
 #4.16.6    Level: 3    Role: D/V
 Verifieer dat beveiligde multi-party computation (SMPC) gezamenlijke AI-training mogelijk maakt zonder individuele datasets of modelparameters bloot te stellen.

---

### C4.17 Zero-Knowledge Infrastructuur

Implementeer zero-knowledge bewijs systemen voor privacybeschermende AI-verificatie en authenticatie zonder gevoelige informatie prijs te geven.

 #4.17.1    Level: 3    Role: D/V
 Verifieer dat zero-knowledge proofs (ZK-SNARKs, ZK-STARKs) de integriteit van AI-modellen en de herkomst van training verifiëren zonder de modelgewichten of trainingsgegevens bloot te geven.
 #4.17.2    Level: 3    Role: D/V
 Verifieer dat op ZK gebaseerde authenticatiesystemen privacybeschermende gebruikersverificatie voor AI-diensten mogelijk maken zonder identiteit gerelateerde informatie prijs te geven.
 #4.17.3    Level: 3    Role: D/V
 Controleer of private set intersection (PSI)-protocollen veilige gegevensmatching mogelijk maken voor federatieve AI zonder individuele datasets bloot te stellen.
 #4.17.4    Level: 3    Role: D/V
 Verifieer dat zero-knowledge machine learning (ZKML) systemen verifieerbare AI-afleidingen mogelijk maken met cryptografisch bewijs van correcte berekening.
 #4.17.5    Level: 3    Role: D/V
 Verifieer dat ZK-rollups schaalbare, privacybeschermende AI-transactieprocessing bieden met batchverificatie en verminderde rekenbelasting.

---

### C4.18 Preventie van zij-kanaal aanvallen

Bescherm AI-infrastructuur tegen timing-, stroom-, elektromagnetische- en cache-gebaseerde zijkanaalaanvallen die gevoelige informatie kunnen lekken.

 #4.18.1    Level: 3    Role: D/V
 Controleer of de AI-inferentietiming wordt genormaliseerd met behulp van constant-time algoritmen en padding om timinggebaseerde modelextractie-aanvallen te voorkomen.
 #4.18.2    Level: 3    Role: D/V
 Controleer of de bescherming tegen vermogensanalyse ruisinjectie, filtering van de voedingslijn en gerandomiseerde uitvoeringspatronen voor AI-hardware omvat.
 #4.18.3    Level: 3    Role: D/V
 Controleer of cache-gebaseerde side-channel mitigatie gebruikmaakt van cache-partitionering, randomisatie en flush-instructies om informatielekken te voorkomen.
 #4.18.4    Level: 3    Role: D/V
 Verifieer dat bescherming tegen elektromagnetische straling afscherming, signaalfiltering en gerandomiseerde verwerking omvat om TEMPEST-stijl aanvallen te voorkomen.
 #4.18.5    Level: 3    Role: D/V
 Controleer of microarchitecturale side-channel verdedigingsmechanismen speculatieve uitvoeringscontroles en geheugen toegangs patroon verhulling omvatten.

---

### C4.19 Neuromorfe & Gespecialiseerde AI Hardwarebeveiliging

Beveilig opkomende AI-hardwarearchitecturen, waaronder neuromorfe chips, FPGA's, op maat gemaakte ASIC's en optische computersystemen.

 #4.19.1    Level: 3    Role: D/V
 Verifieer dat de beveiliging van neuromorfe chips spiekpatroonversleuteling, bescherming van synaptische gewichten en hardwaregebaseerde validatie van leerregels omvat.
 #4.19.2    Level: 3    Role: D/V
 Controleer of FPGA-gebaseerde AI-versnellers bitstreamversleuteling, anti-tampermechanismen en veilige configuratielading met geauthenticeerde updates implementeren.
 #4.19.3    Level: 3    Role: D/V
 Verifieer dat aangepaste ASIC-beveiliging on-chip beveiligingsprocessors, hardware root of trust en veilige sleutelopslag met sabotage-detectie omvat.
 #4.19.4    Level: 3    Role: D/V
 Verifieer dat optische computersystemen kwantumveilige optische encryptie, veilige fotonische schakeling en beschermde optische signaalverwerking implementeren.
 #4.19.5    Level: 3    Role: D/V
 Controleer of hybride analoog-digitale AI-chips veilige analoge berekeningen, beveiligde opslag van gewichten en geverifieerde analoog-naar-digitaal conversie bevatten.

---

### C4.20 Privacy-beschermende rekeninfrastructuur

Implementeer infrastructuurcontroles voor privacybewarende berekeningen om gevoelige gegevens te beschermen tijdens AI-verwerking en -analyse.

 #4.20.1    Level: 3    Role: D/V
 Verifieer dat de homomorfe encryptie-infrastructuur versleutelde berekeningen op gevoelige AI-werklasten mogelijk maakt met cryptografische integriteitsverificatie en prestatiebewaking.
 #4.20.2    Level: 3    Role: D/V
 Verifieer dat systemen voor privé-informatieterugwinning databasequery's mogelijk maken zonder querypatronen te onthullen, met cryptografische bescherming van toegangspatronen.
 #4.20.3    Level: 3    Role: D/V
 Verifieer dat beveiligde multi-party computation-protocollen privacybeschermende AI-inferentie mogelijk maken zonder individuele invoer of tussentijdse berekeningen bloot te geven.
 #4.20.4    Level: 3    Role: D/V
 Controleer of privacy-behoudend sleutelbeheer gedistribueerde sleutelsgeneratie, drempelcryptografie en veilige sleutelrotatie met hardware-ondersteunde bescherming omvat.
 #4.20.5    Level: 3    Role: D/V
 Verifieer dat de privacybewarende rekenprestaties worden geoptimaliseerd door middel van batching, caching en hardwareversnelling, terwijl cryptografische beveiligingsgaranties worden gehandhaafd.

---

### C4.15 Agent Framework Cloud-integratiebeveiliging & Hybride Implementatie

Beveiligingscontroles voor cloud-geïntegreerde agent-frameworks met hybride on-premises/cloud-architecturen.

 #4.15.1    Level: 1    Role: D/V
 Verifieer dat cloudopslagintegratie end-to-end encryptie gebruikt met sleutels die door de agent worden beheerd.
 #4.15.2    Level: 2    Role: D/V
 Controleer of de beveiligingsgrenzen van hybride implementaties duidelijk zijn gedefinieerd met versleutelde communicatiekanalen.
 #4.15.3    Level: 2    Role: D/V
 Controleer of de toegang tot cloudresources nul-trust verificatie bevat met continue authenticatie.
 #4.15.4    Level: 3    Role: D/V
 Verifieer dat eisen voor gegevensresidentie worden afgedwongen door cryptografische attestatie van opslaglocaties.
 #4.15.5    Level: 3    Role: D/V
 Controleer of de beveiligingsbeoordelingen van de cloudprovider agent-specifieke dreigingsmodellering en risicobeoordeling omvatten.

---

### Referenties

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

## C5 Toegangscontrole en Identiteit voor AI-componenten en Gebruikers

### Controle Doelstelling

Effectieve toegangscontrole voor AI-systemen vereist robuust identiteitsbeheer, contextbewuste autorisatie en runtime-handhaving volgens zero-trustprincipes. Deze controles zorgen ervoor dat mensen, diensten en autonome agenten alleen interactie hebben met modellen, data en computationele middelen binnen expliciet toegekende reikwijdtes, met voortdurende verificatie- en auditmogelijkheden.

---

### C5.1 Identiteitsbeheer & Authenticatie

Stel cryptografisch ondersteunde identiteiten vast voor alle entiteiten met multi-factor authenticatie voor bevoorrechte operaties.

 #5.1.1    Level: 1    Role: D/V
 Verifieer dat alle menselijke gebruikers en serviceprincipals zich authenticeren via een gecentraliseerde enterprise identity provider (IdP) met behulp van OIDC/SAML-protocollen met unieke identiteit-naar-token mappings (geen gedeelde accounts of referenties).
 #5.1.2    Level: 1    Role: D/V
 Verifieer dat hoogrisico-operaties (modelimplementatie, gewichtsexport, toegang tot trainingsgegevens, wijzigingen in productieconfiguraties) multi-factorauthenticatie of stap-omhoog authenticatie met sessieherverificatie vereisen.
 #5.1.3    Level: 2    Role: D
 Verifieer dat nieuwe leidinggevenden een identiteitsverificatie ondergaan die overeenkomt met NIST 800-63-3 IAL-2 of gelijkwaardige normen voordat zij toegang krijgen tot het productiesysteem.
 #5.1.4    Level: 2    Role: V
 Controleer of toegangsbeoordelingen elk kwartaal worden uitgevoerd met geautomatiseerde detectie van inactieve accounts, afdwinging van het wijzigen van inloggegevens en workflows voor het deactiveren van accounts.
 #5.1.5    Level: 3    Role: D/V
 Controleer of federatieve AI-agenten zich authenticeren via ondertekende JWT-verklaringen die een maximale levensduur van 24 uur hebben en cryptografisch bewijs van oorsprong bevatten.

---

### C5.2 Middelenautorisatie & Minst Bevoorrechte Toegang

Implementeer fijnmazige toegangscontroles voor alle AI-bronnen met expliciete toestemmingsmodellen en auditsporen.

 #5.2.1    Level: 1    Role: D/V
 Verifieer dat elke AI-bron (datasets, modellen, eindpunten, vectorverzamelingen, embedding-indexen, rekeninstanties) rolgebaseerde toegangscontroles afdwingt met expliciete toestaanlijsten en beleid voor standaard weigering.
 #5.2.2    Level: 1    Role: D/V
 Controleer of het minste-privilegeprincipe standaard wordt gehandhaafd voor serviceaccounts, beginnend met alleen-lezen machtigingen en met gedocumenteerde zakelijke rechtvaardiging die vereist is voor schrijf-toegang.
 #5.2.3    Level: 1    Role: V
 Verifieer dat alle wijzigingen in toegangscontrole gekoppeld zijn aan goedgekeurde wijzigingsverzoeken en onveranderlijk worden vastgelegd met tijdstempels, actorgegevens, resource-identificaties en permissieverschillen.
 #5.2.4    Level: 2    Role: D
 Controleer of dataclassificatielabels (PII, PHI, exportbeperkt, eigendom) automatisch worden doorgegeven aan afgeleide bronnen (embeddings, promptcaches, modeluitvoer) met consistente beleidsafhandeling.
 #5.2.5    Level: 2    Role: D/V
 Verifieer dat pogingen tot ongeautoriseerde toegang en gebeurtenissen van privilege-escalatie real-time waarschuwingen met contextuele metadata naar SIEM-systemen binnen 5 minuten activeren.

---

### C5.3 Dynamische Beleidsevaluatie

Implementeer op attributen gebaseerde toegangscontrole (ABAC) systemen voor contextbewuste autorisatiebeslissingen met auditmogelijkheden.

 #5.3.1    Level: 1    Role: D/V
 Verifieer dat autorisatiebeslissingen worden uitbesteed aan een toegewijde beleidsmotor (OPA, Cedar of gelijkwaardig) die toegankelijk is via geauthenticeerde API's met cryptografische integriteitsbeveiliging.
 #5.3.2    Level: 1    Role: D/V
 Controleer of beleidsregels dynamische attributen evalueren tijdens runtime, inclusief het beveiligingsniveau van de gebruiker, de gevoeligheidsclassificatie van de bron, de context van het verzoek, tenant-isolatie en tijdelijke beperkingen.
 #5.3.3    Level: 2    Role: D
 Verifieer dat beleidsdefinities versiebeheerd, peer-reviewed en gevalideerd zijn door middel van geautomatiseerde tests in CI/CD-pijplijnen voordat ze in productie worden uitgerold.
 #5.3.4    Level: 2    Role: V
 Verifieer dat de beoordeling van het beleid gestructureerde besluitvormingsmotieven bevat en wordt verzonden naar SIEM-systemen voor correlatieanalyse en nalevingsrapportage.
 #5.3.5    Level: 3    Role: D/V
 Controleer of de time-to-live (TTL)-waarden van het beleidscache de 5 minuten niet overschrijden voor hooggevoelige bronnen en 1 uur voor standaardbronnen met cache-invalideringsmogelijkheden.

---

### C5.4 Handhaving van beveiliging tijdens query-uitvoering

Implementeer beveiligingscontroles op databaselaagniveau met verplichte filtering en rijniveaubeveiligingsbeleid.

 #5.4.1    Level: 1    Role: D/V
 Controleer of alle vector database- en SQL-query's verplichte beveiligingsfilters bevatten (tenant-ID, gevoeligheidslabels, gebruikersscope) die worden afgedwongen op het niveau van de database-engine, niet in de applicatiecode.
 #5.4.2    Level: 1    Role: D/V
 Controleer of rijniveau-beveiligingsbeleid (RLS) en veldniveau-maskering zijn ingeschakeld met beleids-erfenis voor alle vectordatabases, zoekindices en trainingsdatasets.
 #5.4.3    Level: 2    Role: D
 Verifieer dat mislukte autorisatiebeoordelingen "confused deputy-aanvallen" voorkomen door queries onmiddellijk af te breken en expliciete autorisatiefoutcodes terug te geven in plaats van lege resultaatsets.
 #5.4.4    Level: 2    Role: V
 Controleer of de beleidsbeoordelingslatentie continu wordt gemonitord met automatische waarschuwingen voor time-outcondities die een autorisatieomzeiling mogelijk zouden maken.
 #5.4.5    Level: 3    Role: D/V
 Controleer of query-herstartmechanismen autorisatiebeleid opnieuw evalueren om rekening te houden met dynamische wijzigingen in machtigingen binnen actieve gebruikerssessies.

---

### C5.5 Uitvoerfiltering & Voorkoming van Gegevensverlies

Implementeer post-processing controles om ongeautoriseerde blootstelling van gegevens in AI-gegenereerde inhoud te voorkomen.

 #5.5.1    Level: 1    Role: D/V
 Verifieer dat post-inferentie filtermechanismen onbevoegde PII, geclassificeerde informatie en propriëtaire gegevens scannen en redigeren voordat de inhoud aan verzoekers wordt geleverd.
 #5.5.2    Level: 1    Role: D/V
 Controleer of citaties, verwijzingen en bronvermeldingen in modeluitvoer worden geverifieerd aan de hand van de toegangsrechten van de aanroeper en verwijder ze indien onbevoegde toegang wordt vastgesteld.
 #5.5.3    Level: 2    Role: D
 Controleer of beperkingen voor outputformaten (gesaniteerde PDF's, metadata-verwijderde afbeeldingen, goedgekeurde bestandstypen) worden gehandhaafd op basis van gebruikersmachtigingsniveaus en dataclassificaties.
 #5.5.4    Level: 2    Role: V
 Controleer of redactiesoftware deterministisch is, versiebeheer heeft en auditlogs bijhoudt om nalevingsonderzoeken en forensische analyses te ondersteunen.
 #5.5.5    Level: 3    Role: V
 Controleer of redactiemomenten met hoog risico adaptieve logs genereren die cryptografische hashes van de oorspronkelijke inhoud bevatten voor forensische terugvinding zonder dat er gegevens worden blootgesteld.

---

### C5.6 Multi-Tenant Isolatie

Zorg voor cryptografische en logische isolatie tussen huurders in gedeelde AI-infrastructuur.

 #5.6.1    Level: 1    Role: D/V
 Controleer of geheugenruimten, embedding-opslagplaatsen, cache-items en tijdelijke bestanden per tenant gescheiden zijn op naamruimte, met veilige verwijdering bij het verwijderen van een tenant of het beëindigen van een sessie.
 #5.6.2    Level: 1    Role: D/V
 Verifieer dat elke API-aanvraag een geauthentificeerde tenant-identificatie bevat die cryptografisch wordt gevalideerd aan de hand van de sessiecontext en gebruikersrechten.
 #5.6.3    Level: 2    Role: D
 Controleer of netwerkbeleid standaard-weigerregels implementeert voor communicatie tussen tenants binnen servicenetwerken en containerorkestratieplatforms.
 #5.6.4    Level: 3    Role: D
 Controleer of encryptiesleutels uniek zijn per huurder met ondersteuning voor door de klant beheerde sleutels (CMK) en cryptografische isolatie tussen gegevensopslagplaatsen van huurders.

---

### C5.7 Autonome Agentautorisatie

Beheer machtigingen voor AI-agenten en autonome systemen via gespecificeerde capaciteits-tokens en voortdurende autorisatie.

 #5.7.1    Level: 1    Role: D/V
 Controleer of autonome agenten gescopeerde bevoegdheidstokens ontvangen die expliciet de toegestane acties, toegankelijke bronnen, tijdsbeperkingen en operationele beperkingen opsommen.
 #5.7.2    Level: 1    Role: D/V
 Controleer of hoogrisico-mogelijkheden (toegang tot het bestandssysteem, code-uitvoering, externe API-aanroepen, financiële transacties) standaard zijn uitgeschakeld en expliciete goedkeuringen vereisen voor activatie met zakelijke rechtvaardigingen.
 #5.7.3    Level: 2    Role: D
 Verifieer dat capaciteits tokens gebonden zijn aan gebruikerssessies, cryptografische integriteitsbescherming bevatten, en zorg ervoor dat ze niet kunnen worden opgeslagen of hergebruikt in offline scenario's.
 #5.7.4    Level: 2    Role: V
 Verifieer dat door agent geïnitieerde acties een secundaire autorisatie ondergaan via de ABAC-beleidsmotor met volledige contextevaluatie en auditlogging.
 #5.7.5    Level: 3    Role: V
 Controleer of foutcondities van agenten en uitzonderingsafhandeling informatie over het capaciteitsbereik bevatten om incidentanalyse en forensisch onderzoek te ondersteunen.

---

### Referenties

#### Normen & Kaders

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Implementatiehandleidingen

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### AI-specifieke beveiliging

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Beveiliging van de toeleveringsketen voor modellen, frameworks en data

### Beheersdoelstelling

AI-aanvalsaanvallen op de toeleveringsketen maken misbruik van modellen, frameworks of datasets van derden om achterdeurtjes, vooroordelen of exploiteerbare code in te bouwen. Deze controles bieden end-to-end herkomst, kwetsbaarheidsbeheer en monitoring om de volledige levenscyclus van het model te beschermen.

---

### C6.1 Controleren en herkomst van voorgetrainde modellen

Beoordeel en verifieer de herkomst, licenties en verborgen gedragingen van modellen van derden voordat u deze fijn afstemt of inzet.

 #6.1.1    Level: 1    Role: D/V
 Controleer of elk artefact van een model van een derde partij een ondertekend provenance-record bevat waarin de bronrepository en commit-hash worden geïdentificeerd.
 #6.1.2    Level: 1    Role: D/V
 Controleer of modellen worden gescand op kwaadaardige lagen of Trojaanse triggers met behulp van geautomatiseerde tools voordat ze worden geïmporteerd.
 #6.1.3    Level: 2    Role: D
 Verifieer dat transferleren-fijnstemming een adversariale evaluatie doorstaat om verborgen gedragingen te detecteren.
 #6.1.4    Level: 2    Role: V
 Controleer of modellicenties, exportcontrolelabels en verklaringen over de herkomst van data worden geregistreerd in een ML-BOM-invoer.
 #6.1.5    Level: 3    Role: D/V
 Verifieer dat hoogrisicomodellen (openbaar geüploade gewichten, niet-geverifieerde makers) in quarantaine blijven totdat ze zijn beoordeeld en goedgekeurd door een mens.

---

### C6.2 Framework- en bibliotheekscanning

Blijf ML-frameworks en bibliotheken voortdurend scannen op CVE's en kwaadaardige code om de runtime-stack veilig te houden.

 #6.2.1    Level: 1    Role: D/V
 Controleer of CI-pijplijnen afhankelijkheidsscanners uitvoeren op AI-frameworks en kritieke bibliotheken.
 #6.2.2    Level: 1    Role: D/V
 Verifieer dat kritieke kwetsbaarheden (CVSS ≥ 7.0) voorkomen dat promotie naar productie-afbeeldingen plaatsvindt.
 #6.2.3    Level: 2    Role: D
 Controleer of statische code-analyse wordt uitgevoerd op geforkte of ingevoegde ML-bibliotheken.
 #6.2.4    Level: 2    Role: V
 Controleer of voorstel voor framework-upgrades een beoordeling van de beveiligingsimpact bevat met verwijzing naar openbare CVE-feeds.
 #6.2.5    Level: 3    Role: V
 Controleer of runtime-sensoren een waarschuwing geven bij onverwachte dynamische bibliotheekladingen die afwijken van de ondertekende SBOM.

---

### C6.3 Afhankelijkheidsverankering en verificatie

Beperk elke afhankelijkheid tot onveranderlijke digests en reproduceer builds om identieke, niet-manipuleerbare artefacten te garanderen.

 #6.3.1    Level: 1    Role: D/V
 Controleer of alle pakketbeheerders versievergrendeling afdwingen via lockfiles.
 #6.3.2    Level: 1    Role: D/V
 Verifieer dat onveranderlijke digests worden gebruikt in plaats van veranderlijke tags in containerreferenties.
 #6.3.3    Level: 2    Role: D
 Controleer of reproducible-buildcontroles hashes vergelijken over CI-uitvoeringen om identieke uitkomsten te waarborgen.
 #6.3.4    Level: 2    Role: V
 Controleer of bouwverklaringen gedurende 18 maanden worden opgeslagen voor audittraceerbaarheid.
 #6.3.5    Level: 3    Role: D
 Controleer of verlopen afhankelijkheden geautomatiseerde pull requests activeren om bijgewerkte of geforkte vaste versies te maken.

---

### C6.4 Handhaving van Vertrouwde Bron

Sta alleen het downloaden van artefacten toe van cryptografisch geverifieerde, door de organisatie goedgekeurde bronnen en blokkeer alles wat daarvan afwijkt.

 #6.4.1    Level: 1    Role: D/V
 Controleer of modelgewichten, datasets en containers alleen worden gedownload van goedgekeurde domeinen of interne registers.
 #6.4.2    Level: 1    Role: D/V
 Controleer of Sigstore/Cosign-handtekeningen de identiteit van de uitgever verifiëren voordat artefacten lokaal worden gecached.
 #6.4.3    Level: 2    Role: D
 Controleer of uitgaande proxies niet-geauthenticeerde artifact-downloads blokkeren om het beleid voor vertrouwde bronnen af te dwingen.
 #6.4.4    Level: 2    Role: V
 Verifieer dat de toegangscontrolelijsten van de repository elk kwartaal worden herzien met bewijs van zakelijke rechtvaardiging voor elke vermelding.
 #6.4.5    Level: 3    Role: V
 Controleer of beleidschendingen het in quarantaine plaatsen van artefacten en het terugdraaien van afhankelijke pijplijnuitvoeringen veroorzaken.

---

### C6.5 Risicobeoordeling van datasets van derden

Evalueer externe datasets op vergiftiging, vooringenomenheid en juridische naleving, en monitor ze gedurende hun gehele levenscyclus.

 #6.5.1    Level: 1    Role: D/V
 Zorg ervoor dat externe datasets een risicoscore voor vergiftiging ondergaan (bijv. data fingerprinting, detectie van uitschieters).
 #6.5.2    Level: 1    Role: D
 Controleer of bias-metrieken (demografische pariteit, gelijke kansen) worden berekend voordat de dataset wordt goedgekeurd.
 #6.5.3    Level: 2    Role: V
 Controleer of herkomst en licentievoorwaarden voor datasets zijn vastgelegd in ML-BOM-vermeldingen.
 #6.5.4    Level: 2    Role: V
 Verifieer of periodieke monitoring afwijkingen of corruptie in gehoste datasets detecteert.
 #6.5.5    Level: 3    Role: D
 Verifieer dat ontoegestane inhoud (auteursrecht, PII) voorafgaand aan training automatisch wordt verwijderd via scrubbing.

---

### C6.6 Monitoring van Supply Chain-aanvallen

Detecteer supply‑chain bedreigingen vroegtijdig via CVE-feeds, auditloganalyse en red-team simulaties.

 #6.6.1    Level: 1    Role: V
 Verifieer dat CI/CD-auditlogs worden doorgestuurd naar SIEM-detecties voor afwijkende pakketdownloads of gemanipuleerde build-stappen.
 #6.6.2    Level: 2    Role: D
 Verifieer dat incidentrespons-scenario's rollbackprocedures bevatten voor gecompromitteerde modellen of bibliotheken.
 #6.6.3    Level: 3    Role: V
 Verifieer dat threat‑intel verrijking ML‑specifieke indicatoren (bijv. modelvergiftiging IoC's) tagt tijdens de alarmtriage.

---

### C6.7 ML-BOM voor Model Artefacten

Genereer en onderteken gedetailleerde ML-specifieke SBOM's (ML-BOM's) zodat downstream gebruikers de componentintegriteit kunnen verifiëren op het moment van deployment.

 #6.7.1    Level: 1    Role: D/V
 Verifieer dat elk modelartefact een ML-BOM publiceert die datasets, gewichten, hyperparameters en licenties vermeldt.
 #6.7.2    Level: 1    Role: D/V
 Controleer of ML-BOM-generatie en Cosign-ondertekening geautomatiseerd zijn in CI en vereist zijn voor samenvoeging.
 #6.7.3    Level: 2    Role: D
 Controleer of de completeness-controle van ML-BOM de build faalt als er metadata van een component (hash, licentie) ontbreekt.
 #6.7.4    Level: 2    Role: V
 Verifieer dat downstream-gebruikers ML-BOM's via de API kunnen opvragen om geïmporteerde modellen tijdens de implementatiefase te valideren.
 #6.7.5    Level: 3    Role: V
 Controleer of ML-BOM's versiebeheer hebben en worden vergeleken om ongeautoriseerde wijzigingen te detecteren.

---

### Referenties

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

## C7 Modelgedrag, Uitvoercontrole & Veiligheidsgarantie

### Controle Doelstelling

Modeluitvoer moet gestructureerd, betrouwbaar, veilig, verklaarbaar en continu gemonitord worden in productie. Dit vermindert hallucinaties, privacylekken, schadelijke inhoud en ongecontroleerde acties, terwijl het het vertrouwen van gebruikers en naleving van regelgeving verhoogt.

---

### C7.1 Handhaving van het uitvoerformaat

Strikte schema's, beperkte decodering en downstream validatie voorkomen dat verkeerd gevormde of kwaadaardige inhoud zich verspreidt.

 #7.1.1    Level: 1    Role: D/V
 Controleer of responschema's (bijv. JSON-schema) in de systeemprompt zijn opgenomen en dat elke output automatisch wordt gevalideerd; niet-conforme outputs veroorzaken reparatie of afwijzing.
 #7.1.2    Level: 1    Role: D/V
 Controleer of beperkt decoderen (stopwoorden, regex, maximum aantal tokens) is ingeschakeld om overflow of prompt-injectie-zijkanalen te voorkomen.
 #7.1.3    Level: 2    Role: D/V
 Controleer of downstreamcomponenten de output als onbetrouwbaar behandelen en deze valideren aan de hand van schema's of injectieveilige deserializers.
 #7.1.4    Level: 3    Role: V
 Controleer of onjuiste-uitvoer gebeurtenissen worden gelogd, geratelimiteerd en zichtbaar gemaakt voor monitoring.

---

### C7.2 Detectie en mitigatie van hallucinaties

Onzekerheidsinschatting en terugvalstrategieën beperken gefabriceerde antwoorden.

 #7.2.1    Level: 1    Role: D/V
 Controleer of token-niveau log-waarschijnlijkheden, ensemble zelfconsistentie, of fijn-afgestelde hallucinatie detectoren een betrouwbaarheidscore toewijzen aan elk antwoord.
 #7.2.2    Level: 1    Role: D/V
 Controleer of antwoorden onder een configureerbare betrouwbaarheidsdrempel fallback-workflows activeren (bijvoorbeeld retrieval-augmented generatie, secundair model of menselijke beoordeling).
 #7.2.3    Level: 2    Role: D/V
 Controleer of hallucinatie-incidenten worden gelabeld met root-cause metadata en worden doorgegeven aan post-mortem en fijnsturing pipelines.
 #7.2.4    Level: 3    Role: D/V
 Controleer of drempels en detectoren opnieuw worden gekalibreerd na grote model- of kennisbankupdates.
 #7.2.5    Level: 3    Role: V
 Controleer of dashboardvisualisaties de hallucinatiepercentages bijhouden.

---

### C7.3 Output Veiligheid & Privacy Filtering

Beleidsfilters en red-teamdekking beschermen gebruikers en vertrouwelijke gegevens.

 #7.3.1    Level: 1    Role: D/V
 Controleer of pre- en post-generatie-classifiers haat, intimidatie, zelfbeschadiging, extremistische en seksueel expliciete inhoud die in overeenstemming is met het beleid blokkeren.
 #7.3.2    Level: 1    Role: D/V
 Verifieer dat PII/PCI-detectie en automatische redactie op elke reactie worden uitgevoerd; overtredingen leiden tot een privacy-incident.
 #7.3.3    Level: 2    Role: D
 Controleer of vertrouwelijkheidslabels (bijv. handelsgeheimen) zich over modaliteiten heen voortplanten om lekken in tekst, afbeeldingen of code te voorkomen.
 #7.3.4    Level: 3    Role: D/V
 Controleer of pogingen om filters te omzeilen of classificaties met een hoog risico secundaire goedkeuring of gebruikerherauthenticatie vereisen.
 #7.3.5    Level: 3    Role: D/V
 Controleer of de filterdrempels overeenkomen met de wettelijke jurisdicties en de context van de leeftijd/rol van de gebruiker.

---

### C7.4 Beperking van uitvoer en acties

Tariefbeperkingen en goedkeuringspoorten voorkomen misbruik en buitensporige autonomie.

 #7.4.1    Level: 1    Role: D
 Controleer of per-gebruiker en per-API-sleutel quota verzoeken, tokens en kosten beperken met exponentiële back-off bij 429-fouten.
 #7.4.2    Level: 1    Role: D/V
 Controleer of bevoorrechte acties (bestandsschrijvingen, code-uitvoering, netwerkoproepen) goedkeuring op basis van beleid of menselijke tussenkomst vereisen.
 #7.4.3    Level: 2    Role: D/V
 Controleer of cross-modale consistentiecontroles ervoor zorgen dat afbeeldingen, code en tekst die voor dezelfde aanvraag zijn gegenereerd, niet kunnen worden gebruikt om kwaadaardige inhoud te smokkelen.
 #7.4.4    Level: 2    Role: D
 Controleer of de diepte van agentdelegatie, recursielimieten en toegestane lijst met tools expliciet zijn geconfigureerd.
 #7.4.5    Level: 3    Role: V
 Verifieer dat het overschrijden van limieten gestructureerde beveiligingsgebeurtenissen genereert voor SIEM-inname.

---

### C7.5 Output Verklaarbaarheid

Transparante signalen verbeteren het vertrouwen van gebruikers en interne foutopsporing.

 #7.5.1    Level: 2    Role: D/V
 Controleer of gebruikergeoriënteerde betrouwbaarheidscores of korte redeneersamenvattingen worden weergegeven wanneer de risicobeoordeling dit passend acht.
 #7.5.2    Level: 2    Role: D/V
 Controleer of gegenereerde verklaringen vermijden dat gevoelige systeemopdrachten of vertrouwelijke gegevens worden onthuld.
 #7.5.3    Level: 3    Role: D
 Verifieer dat het systeem token-niveau log-waarschijnlijkheden of aandachtkaarten vastlegt en opslaat voor geautoriseerde inspectie.
 #7.5.4    Level: 3    Role: V
 Verifieer dat uitlegbaarheidsartefacten versiebeheer hebben naast modelreleases voor controleerbaarheid.

---

### C7.6 Integratie van monitoring

Realtime observeerbaarheid sluit de lus tussen ontwikkeling en productie.

 #7.6.1    Level: 1    Role: D
 Verifieer dat metriekgegevens (schema-overtredingen, hallucinatiepercentage, toxiciteit, PII-lekken, latentie, kosten) worden gestreamd naar een centraal monitoringplatform.
 #7.6.2    Level: 1    Role: V
 Controleer of waarschuwingsdrempels zijn gedefinieerd voor elke veiligheidsmaatstaf, met escalatieroutes voor dienstdoende medewerkers.
 #7.6.3    Level: 2    Role: V
 Controleer of dashboards outputanomalieën correleren met model/version, featureflag en wijzigingen in upstream-gegevens.
 #7.6.4    Level: 2    Role: D/V
 Controleer of monitoringgegevens terugvloeien in het retrainen, fijn afstemmen of bijwerken van regels binnen een gedocumenteerde MLOps-werkstroom.
 #7.6.5    Level: 3    Role: V
 Controleer of monitoringpijplijnen zijn onderworpen aan penetratietests en toegangscontrole om het lekken van gevoelige logbestanden te voorkomen.

---

### 7.7 Generatieve Media Beveiligingen

Zorg ervoor dat AI-systemen geen illegale, schadelijke of niet-geautoriseerde mediacontent genereren door het afdwingen van beleidsbeperkingen, outputvalidatie en traceerbaarheid.

 #7.7.1    Level: 1    Role: D/V
 Controleer of systeemopdrachten en gebruikersinstructies expliciet het genereren van illegale, schadelijke of niet-consensuele deepfake-media (bijv. afbeelding, video, audio) verbieden.
 #7.7.2    Level: 2    Role: D/V
 Controleer of prompts worden gefilterd op pogingen om imitaties te genereren, seksueel expliciete deepfakes, of media die echte personen zonder toestemming afbeelden.
 #7.7.3    Level: 2    Role: V
 Verifieer dat het systeem gebruikmaakt van perceptuele hashing, watermerkdetectie of fingerprinting om ongeoorloofde reproductie van auteursrechtelijk beschermd materiaal te voorkomen.
 #7.7.4    Level: 3    Role: D/V
 Verifieer dat alle gegenereerde media cryptografisch zijn ondertekend, watermerk bevatten of zijn ingebed met manipulatiebestendige herkomstmetadata voor traceerbaarheid in latere stadia.
 #7.7.5    Level: 3    Role: V
 Controleer of pogingen tot omzeiling (bijv. promptverduistering, straattaal, vijandige formuleringen) worden gedetecteerd, gelogd en gelimiteerd; herhaald misbruik wordt gerapporteerd aan monitoringsystemen.

### Referenties

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

## C8 Geheugen, Embeddings en Beveiliging van Vector Databases

### Beheersdoelstelling

Embeddings en vectoropslag fungeren als het "levende geheugen" van hedendaagse AI-systemen, waarbij ze continu door gebruikers aangeleverde gegevens accepteren en deze via Retrieval-Augmented Generation (RAG) terug in modelcontexten brengen. Als dit geheugen niet wordt beheerst, kan het leiden tot het lekken van persoonlijke identificeerbare informatie (PII), het schenden van toestemming of het omkeren om de oorspronkelijke tekst te reconstrueren. Het doel van deze controlegroep is het beveiligen van geheugensystemen en vectordatabases zodat de toegang het minste privilege heeft, embeddings privacybeschermend zijn, opgeslagen vectoren vervallen of op verzoek kunnen worden ingetrokken, en dat het geheugen per gebruiker nooit de prompts of voltooingen van een andere gebruiker besmet.

---

### C8.1 Toegangscontroles op geheugen en RAG-indexen

Handhaaf fijnmazige toegangscontroles op elke vectorverzameling.

 #8.1.1    Level: 1    Role: D/V
 Controleer of regels voor toegangsbeheer op rij-/namespace-niveau de invoeg-, verwijder- en querybewerkingen beperken per huurder, collectie of documentlabel.
 #8.1.2    Level: 1    Role: D/V
 Controleer of API-sleutels of JWT's gescoorde claims bevatten (bijv. collectie-ID's, actie-werkwoorden) en minimaal elk kwartaal worden geroteerd.
 #8.1.3    Level: 2    Role: D/V
 Verifieer dat pogingen tot privilege-escalatie (bijvoorbeeld vergelijkingsqueries tussen namespaces) binnen 5 minuten worden gedetecteerd en geregistreerd in een SIEM.
 #8.1.4    Level: 2    Role: D/V
 Controleer of de vector DB audits de onderwerpidentifier, bewerking, vector ID/namespace, gelijkenisdrempel en resultaatcount loggen.
 #8.1.5    Level: 3    Role: V
 Controleer of toegangsbeslissingen worden getest op omzeilingsfouten telkens wanneer engines worden geüpgraded of index-shardingregels worden gewijzigd.

---

### C8.2 Insluitingssanering en validatie

Vooraf de tekst op PII controleren, anonimiseren of pseudonimiseren voor vectorisatie, en indien gewenst de embeddings nabewerken om resterende signalen te verwijderen.

 #8.2.1    Level: 1    Role: D/V
 Controleer of PII en gereguleerde gegevens worden gedetecteerd via geautomatiseerde classificatiesystemen en voorafgaand aan embedding worden gemaskeerd, getokeniseerd of verwijderd.
 #8.2.2    Level: 1    Role: D
 Controleer of embedding-pijplijnen invoer die uitvoerbare code of niet-UTF-8-artifacten bevat, die de index kunnen besmetten, afwijzen of in quarantaine plaatsen.
 #8.2.3    Level: 2    Role: D/V
 Controleer of lokale of metrische differentiële privacy-sanering wordt toegepast op zinsem-beddings waarvan de afstand tot een bekende PII-token onder een configureerbare drempel ligt.
 #8.2.4    Level: 2    Role: V
 Verifieer dat de doeltreffendheid van sanering (bijvoorbeeld recall van PII-redactie, semantische drift) ten minste halfjaarlijks wordt gevalideerd aan de hand van benchmarkcorpora.
 #8.2.5    Level: 3    Role: D/V
 Controleer of saneringsconfiguraties versiebeheerd zijn en of wijzigingen een peer review ondergaan.

---

### C8.3 Geheugenverval, Intrekking & Verwijdering

GDPR "recht om vergeten te worden" en soortgelijke wetten vereisen tijdige verwijdering; vectoropslag moet daarom TTL's, harde verwijderingen en tombstoning ondersteunen zodat ingetrokken vectoren niet kunnen worden hersteld of opnieuw geïndexeerd.

 #8.3.1    Level: 1    Role: D/V
 Controleer of elk vector- en metagegevensrecord een TTL of expliciet bewaarbeleid bevat dat wordt gerespecteerd door geautomatiseerde opruimwerkzaamheden.
 #8.3.2    Level: 1    Role: D/V
 Verifieer dat door de gebruiker geïnitieerde verwijderingsverzoeken vectoren, metadata, cachekopieën en afgeleide indexen binnen 30 dagen verwijderen.
 #8.3.3    Level: 2    Role: D
 Controleer of logische verwijderingen worden gevolgd door cryptografisch wissen van opslagblokken als de hardware dat ondersteunt, of door vernietiging van sleutels in de sleutelkluis.
 #8.3.4    Level: 3    Role: D/V
 Controleer of verlopen vectoren binnen < 500 ms na verval zijn uitgesloten van de resultaten van de dichtstbijzijnde-buurzoektocht.

---

### C8.4 Voorkom Inversie en Lekken van Embeddings

Recente verdedigingsmethoden—zoals ruisopsomming, projectienetwerken, perturbatie van privacyneuronen en versleuteling op applicatielaag—kunnen token-niveau inversieratio's onder de 5% brengen.

 #8.4.1    Level: 1    Role: V
 Controleer of er een formeel dreigingsmodel bestaat dat omkering, lidmaatschaps- en attribuut-inferentie-aanvallen omvat en jaarlijks wordt herzien.
 #8.4.2    Level: 2    Role: D/V
 Controleer of applicatielaagversleuteling of doorzoekbare encryptie vectoren beschermt tegen directe uitlezing door infrastructuurbeheerders of cloudpersoneel.
 #8.4.3    Level: 3    Role: V
 Controleer of de verdedigingsparameters (ε voor DP, ruis σ, projectierang k) een balans vinden tussen privacy ≥ 99% tokenbescherming en bruikbaarheid ≤ 3% nauwkeurigheidsverlies.
 #8.4.4    Level: 3    Role: D/V
 Verifieer dat omkeerbestendigheidsmetingen deel uitmaken van release-poorten voor modelupdates, met gedefinieerde regressiebudgetten.

---

### C8.5 Toepassing van bereikbeperking voor gebruikersspecifiek geheugen

Cross-tenant lekkage blijft een groot risico bij RAG: onjuist gefilterde gelijkenisquery's kunnen privédocumenten van een andere klant aan het licht brengen.

 #8.5.1    Level: 1    Role: D/V
 Verifieer dat elke ophaalquery wordt nabehandeld met tenant-/gebruikers-ID voordat deze aan de LLM-prompt wordt doorgegeven.
 #8.5.2    Level: 1    Role: D
 Controleer of collectienamen of genamespaceerde ID's per gebruiker of huurder gezouten zijn zodat vectoren niet kunnen botsen tussen verschillende scopes.
 #8.5.3    Level: 2    Role: D/V
 Controleer of gelijkenisresultaten boven een configureerbare afstandsdrempel, maar buiten de scope van de aanroeper, worden verworpen en beveiligingswaarschuwingen veroorzaken.
 #8.5.4    Level: 2    Role: V
 Controleer of multi-tenant stresstests adversariële queries simuleren die proberen documenten buiten de toegestane scope op te halen en toon aan dat er geen informatielekkage plaatsvindt.
 #8.5.5    Level: 3    Role: D/V
 Verifieer dat encryptiesleutels per huurder gescheiden zijn, waardoor cryptografische isolatie wordt gegarandeerd, zelfs als de fysieke opslag gedeeld wordt.

---

### C8.6 Geavanceerde beveiliging van geheugensystemen

Beveiligingsmaatregelen voor geavanceerde geheugenarchitecturen, inclusief episodisch, semantisch en werkgeheugen, met specifieke isolatie- en validatievereisten.

 #8.6.1    Level: 1    Role: D/V
 Verifieer dat verschillende geheugentypen (episodisch, semantisch, werkgeheugen) geïsoleerde beveiligingscontexten hebben met op rollen gebaseerde toegangscontrole, aparte encryptiesleutels en gedocumenteerde toegangsmodellen voor elk geheugentype.
 #8.6.2    Level: 2    Role: D/V
 Controleer of processen voor geheugenconsolidatie beveiligingsvalidatie omvatten om de injectie van kwaadaardige herinneringen te voorkomen via inhoudssanering, bronverificatie en integriteitscontroles vóór opslag.
 #8.6.3    Level: 2    Role: D/V
 Controleer of geheugenophaalqueries worden gevalideerd en gesaneerd om te voorkomen dat ongeautoriseerde informatie wordt verkregen via analyse van querypatronen, handhaving van toegangscontrole en filtering van resultaten.
 #8.6.4    Level: 3    Role: D/V
 Controleer of geheugenvergeetmechanismen gevoelige informatie veilig wissen met cryptografische verwijderingsgaranties door middel van sleuteldeletie, meervoudig overschrijven of hardware-gebaseerde beveiligde verwijdering met verificatiecertificaten.
 #8.6.5    Level: 3    Role: D/V
 Controleer of de integriteit van het geheugensysteem continu wordt gecontroleerd op ongeautoriseerde wijzigingen of corruptie door middel van checksums, auditlogs en geautomatiseerde waarschuwingen wanneer de inhoud van het geheugen buiten normale bewerkingen verandert.

---

### Referenties

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

## 9 Autonome Orkestratie & Agente Actie Beveiliging

### Beheersingsdoel

Zorg ervoor dat autonome of multi-agent AI-systemen alleen acties kunnen uitvoeren die expliciet bedoeld, geverifieerd, controleerbaar en binnen begrensde kosten- en risicodrempels vallen. Dit beschermt tegen bedreigingen zoals compromittering van autonome systemen, misbruik van tools, detectie van agentlussen, kaping van communicatie, identiteitsvervalsing, zwermmanipulatie en intentiemanipulatie.

---

### 9.1 Taakplanning van agenten & Recursiebudgetten

Beperk recursieve plannen en verplicht menselijke controlepunten voor geprivilegieerde acties.

 #9.1.1    Level: 1    Role: D/V
 Controleer of de maximale recursiediepte, breedte, kloktijd, tokens en monetaire kosten per agentuitvoering centraal zijn geconfigureerd en versiegecontroleerd.
 #9.1.2    Level: 1    Role: D/V
 Controleer of bevoorrechte of onomkeerbare acties (bijv. code-commits, financiële overboekingen) expliciete goedkeuring door een mens vereisen via een controleerbaar kanaal voordat ze worden uitgevoerd.
 #9.1.3    Level: 2    Role: D
 Controleer of real-time hulpmiddelenmonitors de circuit-breaker onderbreking activeren wanneer een budgetdrempel wordt overschreden, waardoor verdere takenuitbreiding wordt gestopt.
 #9.1.4    Level: 2    Role: D/V
 Controleer of circuitonderbreker-gebeurtenissen worden gelogd met agent-ID, activeringsvoorwaarde en vastgelegde plantoestand voor forensische beoordeling.
 #9.1.5    Level: 3    Role: V
 Controleer of de beveiligingstests scenario's van budgetuitputting en voortvluchtige plannen dekken, en bevestig dat er veilig wordt gestopt zonder gegevensverlies.
 #9.1.6    Level: 3    Role: D
 Verifieer dat budgetbeleid wordt uitgedrukt als beleid-als-code en wordt afgedwongen in CI/CD om configuratieafwijkingen te blokkeren.

---

### 9.2 Plugin Sandbox voor Hulpprogramma's

Isoleer toolinteracties om ongeautoriseerde toegang tot het systeem of code-uitvoering te voorkomen.

 #9.2.1    Level: 1    Role: D/V
 Verifieer dat elke tool/plugin wordt uitgevoerd binnen een OS-, container- of WASM-niveau sandbox met een minst-privilege beleid voor bestandssysteem, netwerk en systeemoproepen.
 #9.2.2    Level: 1    Role: D/V
 Controleer of sandbox resourcequota's (CPU, geheugen, schijf, netwerkuitgaande verkeer) en uitvoeringstijdslimieten worden gehandhaafd en geregistreerd.
 #9.2.3    Level: 2    Role: D/V
 Controleer of de toolbinaries of descriptoren digitaal zijn ondertekend; handtekeningen worden gevalideerd voordat ze worden geladen.
 #9.2.4    Level: 2    Role: V
 Controleer of sandbox-telemetrie naar een SIEM wordt gestreamd; anomalieën (bijvoorbeeld pogingen tot uitgaande verbindingen) veroorzaken waarschuwingen.
 #9.2.5    Level: 3    Role: V
 Verifieer of plugins met een hoog risico een veiligheidsbeoordeling en penetratietest ondergaan voordat ze in productie worden genomen.
 #9.2.6    Level: 3    Role: D/V
 Controleer of pogingen tot ontsnappen uit de sandbox automatisch worden geblokkeerd en of de betreffende plugin in quarantaine wordt geplaatst in afwachting van onderzoek.

---

### 9.3 Autonome lus en kostenbegrenzing

Detecteer en stop ongecontroleerde agent-tot-agent recursie en kostenexplosies.

 #9.3.1    Level: 1    Role: D/V
 Controleer of inter-agent oproepen een hop-limiet of TTL bevatten die de runtime vermindert en afdwingt.
 #9.3.2    Level: 2    Role: D
 Verifieer dat agents een unieke oproep-grafiek-ID behouden om zelfoproep of cyclische patronen te detecteren.
 #9.3.3    Level: 2    Role: D/V
 Verifieer dat cumulatieve compute-eenheid- en uitgavencounters per verzoekketen worden bijgehouden; het overschrijden van de limiet leidt tot het afbreken van de keten.
 #9.3.4    Level: 3    Role: V
 Verifieer dat formele analyse of model checking afwezigheid van onbeperkte recursie in agentprotocollen aantoont.
 #9.3.5    Level: 3    Role: D
 Verifieer dat loop-afbreekgebeurtenissen waarschuwingen genereren en continue verbeteringsstatistieken voeden.

---

### 9.4 Misbruikbescherming op protocolleniveau

Beveiligde communicatiekanalen tussen agenten en externe systemen om kaping of manipulatie te voorkomen.

 #9.4.1    Level: 1    Role: D/V
 Controleer of alle berichten van agent naar hulpmiddel en van agent naar agent geverifieerd zijn (bijvoorbeeld via mutual TLS of JWT) en end-to-end versleuteld zijn.
 #9.4.2    Level: 1    Role: D
 Controleer of schema's strikt worden gevalideerd; onbekende velden of foutieve berichten worden geweigerd.
 #9.4.3    Level: 2    Role: D/V
 Controleer of integriteitscontroles (MAC's of digitale handtekeningen) de volledige berichtinhoud, inclusief toolparameters, bestrijken.
 #9.4.4    Level: 2    Role: D
 Controleer of replay-bescherming (nonces of tijdvensters) wordt afgedwongen op het protocollaag.
 #9.4.5    Level: 3    Role: V
 Controleer of protocolimplementaties onderworpen zijn aan fuzzing en statische analyse om injectie- of deserialisatiefouten op te sporen.

---

### 9.5 Agentidentiteit en bewijs van manipulatie

Zorg ervoor dat acties toewijsbaar zijn en wijzigingen detecteerbaar.

 #9.5.1    Level: 1    Role: D/V
 Verifieer dat elke agentinstantie beschikt over een unieke cryptografische identiteit (sleutelpaar of op hardware gebaseerde referentie).
 #9.5.2    Level: 2    Role: D/V
 Controleer of alle agentacties zijn ondertekend en van een tijdstempel zijn voorzien; logs bevatten de handtekening voor niet-ontkenning.
 #9.5.3    Level: 2    Role: V
 Verifieer dat knoeibestendige logbestanden worden opgeslagen in een append-only of write-once medium.
 #9.5.4    Level: 3    Role: D
 Controleer of identiteitsleutels roteren volgens een vastgesteld schema en bij aanwijzingen van compromittering.
 #9.5.5    Level: 3    Role: D/V
 Controleer of pogingen tot spoofing of sleutelconflicten leiden tot onmiddellijke isolatie van de getroffen agent.

---

### 9.6 Risicoreductie door Multi-Agent Zwermen

Beperk gevaren van collectief gedrag door isolatie en formele veiligheidsmodellering.

 #9.6.1    Level: 1    Role: D/V
 Verifieer dat agenten die werken in verschillende beveiligingsdomeinen, worden uitgevoerd in geïsoleerde runtime sandboxes of netwerksegmenten.
 #9.6.2    Level: 3    Role: V
 Controleer of zwermgedrag wordt gemodelleerd en formeel geverifieerd op levendigheid en veiligheid voordat het wordt ingezet.
 #9.6.3    Level: 3    Role: D
 Controleer of runtime monitors opkomende onveilige patronen (bijv. oscillaties, deadlocks) detecteren en corrigerende maatregelen nemen.

---

### 9.7 Gebruikers- en Toolauthenticatie / Autorisatie

Implementeer robuuste toegangscontroles voor elke door een agent-trigger uitgevoerde actie.

 #9.7.1    Level: 1    Role: D/V
 Verifieer dat agenten zich authenticeren als eersteklas principalen bij downstream-systemen, zonder ooit de inloggegevens van eindgebruikers te hergebruiken.
 #9.7.2    Level: 2    Role: D
 Verifieer dat fijnmazige autorisatiebeleid beperkt welke tools een agent mag aanroepen en welke parameters deze mag meegeven.
 #9.7.3    Level: 2    Role: V
 Controleer of de privileges-controles bij elke oproep opnieuw worden geëvalueerd (continue autorisatie), en niet alleen aan het begin van de sessie.
 #9.7.4    Level: 3    Role: D
 Controleer of gedelegeerde privileges automatisch verlopen en opnieuw toestemming vereisen na time-out of wijziging van het bereik.

---

### 9.8 Beveiliging van communicatie tussen agenten

Versleutel en bescherm alle berichten tussen agents tegen integriteitsinbreuk om afluisteren en manipulatie te voorkomen.

 #9.8.1    Level: 1    Role: D/V
 Verifieer dat wederzijdse authenticatie en perfect-forward-secret encryptie (bijv. TLS 1.3) verplicht zijn voor agentkanalen.
 #9.8.2    Level: 1    Role: D
 Verifieer dat de berichtintegriteit en -herkomst worden gevalideerd voordat verwerking plaatsvindt; bij fouten worden waarschuwingen afgegeven en het bericht verwijderd.
 #9.8.3    Level: 2    Role: D/V
 Verifieer dat communicatiemetagegevens (tijdstempels, sequentienummers) worden vastgelegd ter ondersteuning van forensische reconstructie.
 #9.8.4    Level: 3    Role: V
 Verifieer dat formele verificatie of modelchecking bevestigt dat protocoltoestandsmachines niet in onveilige toestanden kunnen worden gedwongen.

---

### 9.9 Intentieverificatie en naleving van beperkingen

Valideer dat de acties van de agent overeenkomen met de aangegeven intentie van de gebruiker en de systeembeperkingen.

 #9.9.1    Level: 1    Role: D
 Verifieer dat pre-executie constraint oplosser voorgestelde acties controleert aan de hand van hard-coded veiligheids- en beleidsregels.
 #9.9.2    Level: 2    Role: D/V
 Controleer of acties met grote impact (financieel, destructief, privacygevoelig) expliciete bevestiging van intentie vereisen van de gebruiker die de actie initieert.
 #9.9.3    Level: 2    Role: V
 Controleer of de post-conditiecontroles bevestigen dat voltooide acties de beoogde effecten hebben bereikt zonder bijwerkingen; afwijkingen veroorzaken een rollback.
 #9.9.4    Level: 3    Role: V
 Verifieer dat formele methoden (bijv. model checking, theorem proving) of op eigenschappen gebaseerde tests aantonen dat de plannen van agenten voldoen aan alle verklaarde beperkingen.
 #9.9.5    Level: 3    Role: D
 Verifieer dat incidenten van intentie-mismatch of overtreding van beperkingen de continue verbetercycli en het delen van bedreigingsinformatie voeden.

---

### 9.10 Beveiliging van de redeneringsstrategie van agenten

Veilige selectie en uitvoering van verschillende redeneerstrategieën, waaronder ReAct, Chain-of-Thought en Tree-of-Thoughts benaderingen.

 #9.10.1    Level: 1    Role: D/V
 Controleer of de selectie van de redeneervolgorde gebruikmaakt van deterministische criteria (inputcomplexiteit, type taak, beveiligingscontext) en dat identieke inputs binnen dezelfde beveiligingscontext identieke volgorde-selecties opleveren.
 #9.10.2    Level: 1    Role: D/V
 Verifieer dat elke redeneerstrategie (ReAct, Chain-of-Thought, Tree-of-Thoughts) specifieke invoervalidatie, uitvoerzuivering en tijdslimieten voor uitvoering heeft die zijn afgestemd op de cognitieve aanpak ervan.
 #9.10.3    Level: 2    Role: D/V
 Controleer of overgangen in de redeneervaardigheid worden geregistreerd met volledige context, inclusief kenmerken van de invoer, waarden van selectiecriteria en uitvoeringsmetadata, voor reconstructie van het auditspoor.
 #9.10.4    Level: 2    Role: D/V
 Controleer of Tree-of-Thoughts redenering mechanisme voor het afkappen van takken bevat die de verkenning beëindigen bij het detecteren van beleidschendingen, resourcebeperkingen of veiligheidsgrenzen.
 #9.10.5    Level: 2    Role: D/V
 Controleer of ReAct (Redeneren-Handelen-Observeren) cycli validatiecontroles bevatten in elke fase: verificatie van de redeneerstap, autorisatie van de actie en sanering van de observatie voordat wordt doorgegaan.
 #9.10.6    Level: 3    Role: D/V
 Controleer of prestatiestatistieken van redeneerstrategieën (uitvoeringstijd, bronnengebruik, outputkwaliteit) worden bewaakt met geautomatiseerde waarschuwingen wanneer de statistieken afwijken van de geconfigureerde drempels.
 #9.10.7    Level: 3    Role: D/V
 Verifieer dat hybride redeneerbenaderingen die meerdere strategieën combineren, de invoervalidatie en uitvoerbeperkingen van alle afzonderlijke strategieën handhaven zonder beveiligingscontroles te omzeilen.
 #9.10.8    Level: 3    Role: D/V
 Verifieer dat de beveiligingstests van redeneringsstrategieën fuzzing omvatten met verkeerd gevormde invoer, vijandige prompts die ontworpen zijn om strategiewisseling af te dwingen, en grenswaardetests voor elke cognitieve benadering.

---

### 9.11 Beheer van de levenscyclusstatus en beveiliging van agents

Veilige agentinitialisatie, statustransities en terminatie met cryptografische audit-trails en gedefinieerde herstelprocedures.

 #9.11.1    Level: 1    Role: D/V
 Verifyer dat de agent-initialisatie cryptografische identiteit vastlegt met hardware-ondersteunde referenties en onveranderlijke opstartauditlogs bevat met agent-ID, tijdstempel, configuratie-hash en initialisatieparameters.
 #9.11.2    Level: 2    Role: D/V
 Verifieer dat agenttoestandovergangen cryptografisch zijn ondertekend, van een tijdstempel zijn voorzien en worden gelogd met volledige context, inclusief de triggerende gebeurtenissen, de hash van de vorige staat, de hash van de nieuwe staat en uitgevoerde beveiligingscontroles.
 #9.11.3    Level: 2    Role: D/V
 Controleer of de afsluitprocedures van de agent veilige geheugenwissing omvatten via cryptografische wissen of meervoudig overschrijven, intrekking van referenties met kennisgeving aan de certificeringsautoriteit, en het genereren van knoeibestendige beëindigingscertificaten.
 #9.11.4    Level: 3    Role: D/V
 Controleer of agent-herstelmechanismen de integriteit van de status valideren met behulp van cryptografische checksums (minimaal SHA-256) en terugrollen naar bekende goede statussen wanneer corruptie wordt gedetecteerd, met geautomatiseerde waarschuwingen en vereisten voor handmatige goedkeuring.
 #9.11.5    Level: 3    Role: D/V
 Verifieer dat agent persistentiemechanismen gevoelige statusgegevens versleutelen met per-agent AES-256 sleutels en implementeer een veilige sleutelrotatie volgens configureerbare schema's (maximaal 90 dagen) met een deployment zonder downtime.

---

### 9.12 Beveiligingskader voor Toolintegratie

Beveiligingscontroles voor dynamische gereedschaplading, uitvoering en resultaatvalidatie met gedefinieerde risicobeoordelings- en goedkeuringsprocessen.

 #9.12.1    Level: 1    Role: D/V
 Controleer of toolbeschrijvingen beveiligingsmetadata bevatten die vereiste privileges specificeren (lezen/schrijven/uitvoeren), risiconiveaus (laag/middel/hoog), resourcebeperkingen (CPU, geheugen, netwerk) en validatievereisten die zijn gedocumenteerd in toolmanifesten.
 #9.12.2    Level: 1    Role: D/V
 Verifieer dat de uitvoeringsresultaten van tools worden gevalideerd aan de hand van verwachte schema's (JSON Schema, XML Schema) en beveiligingsbeleid (outputsanering, gegevensclassificatie) voordat ze worden geïntegreerd, met tijdslimieten en foutafhandelingsprocedures.
 #9.12.3    Level: 2    Role: D/V
 Verifieer dat toolinteractie-logboeken gedetailleerde beveiligingscontext bevatten, inclusief gebruik van privileges, patroon van gegevens toegang, uitvoeringstijd, hulpbronnenverbruik en retourcodes, met gestructureerde logging voor SIEM-integratie.
 #9.12.4    Level: 2    Role: D/V
 Verifieer dat dynamische hulpmiddelenlaadmechanismen digitale handtekeningen valideren met behulp van PKI-infrastructuur en implementeer veilige laadprotocollen met sandbox-isolatie en machtigingsverificatie voorafgaand aan uitvoering.
 #9.12.5    Level: 3    Role: D/V
 Controleer of beveiligingsbeoordelingen van tools automatisch worden gestart voor nieuwe versies met verplichte goedkeuringspoorten, inclusief statische analyse, dynamische tests en beoordeling door het beveiligingsteam, met gedocumenteerde goedkeuringscriteria en SLA-vereisten.

---

#### Referenties

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

## 10 Adversariële Robuustheid & Privacyverdediging

### Controle Doelstelling

Zorg ervoor dat AI-modellen betrouwbaar, privacybeschermend en bestand tegen misbruik blijven bij het ondervinden van ontwijkings-, inferentie-, extractie- of vergiftigingsaanvallen.

---

### 10.1 Modelafstemming en Veiligheid

Bescherm tegen schadelijke of beleidschendende output.

 #10.1.1    Level: 1    Role: D/V
 Controleer of een alignment test-suite (red-team prompts, jailbreak probes, niet-toegestane inhoud) versiebeheer heeft en bij elke modelrelease wordt uitgevoerd.
 #10.1.2    Level: 1    Role: D
 Verifieer dat weigering en veilige voltooings-beveiligingsmechanismen worden gehandhaafd.
 #10.1.3    Level: 2    Role: D/V
 Verifieer dat een geautomatiseerde beoordelaar het percentage schadelijke inhoud meet en regresgevallen markeert die een bepaalde drempel overschrijden.
 #10.1.4    Level: 2    Role: D
 Controleer of counter-jailbreak training gedocumenteerd en reproduceerbaar is.
 #10.1.5    Level: 3    Role: V
 Verifieer dat formele beleidsnalevingsbewijzen of gecertificeerde monitoring kritieke domeinen bestrijken.

---

### 10.2 Versterking tegen vijandige voorbeelden

Verhoog de veerkracht tegen gemanipuleerde invoer. Robuuste adversariële training en benchmarkscoring zijn momenteel de beste praktijk.

 #10.2.1    Level: 1    Role: D
 Controleer of projectrepositories configuraties voor adversariële training bevatten met reproduceerbare zaden.
 #10.2.2    Level: 2    Role: D/V
 Verifieer dat detectie van vijandige voorbeelden blokkeringwaarschuwingen geeft in productiepijplijnen.
 #10.2.4    Level: 3    Role: V
 Verifieer of certificaten voor gecertificeerde robuustheid of intervalgrenscertificaten ten minste de belangrijkste kritieke klassen dekken.
 #10.2.5    Level: 3    Role: V
 Verifieer dat regressietests adaptieve aanvallen gebruiken om te bevestigen dat er geen meetbaar verlies aan robuustheid is.

---

### 10.3 Vermindering van lidmaatschapsinzage

Beperk de mogelijkheid om te bepalen of een record in de trainingsgegevens zat. Differentiële privacy en het maskeren van betrouwbaarheidscores blijven de meest effectieve bekende verdedigingsmethoden.

 #10.3.1    Level: 1    Role: D
 Controleer of per-query entropie-regularisatie of temperatuurschaling overconfidente voorspellingen vermindert.
 #10.3.2    Level: 2    Role: D
 Controleer of de training gebruikmaakt van ε-gebonden differentieel-private optimalisatie voor gevoelige datasets.
 #10.3.3    Level: 2    Role: V
 Verifieer dat aanvalssimulaties (shadow-model of black-box) een aanval AUC ≤ 0,60 tonen op afgezonderde data.

---

### 10.4 Weerstand tegen model-inversie

Voorkom reconstructie van privéattributen. Recente onderzoeken benadrukken outputafkapping en DP-garanties als praktische verdedigingsmaatregelen.

 #10.4.1    Level: 1    Role: D
 Verifieer dat gevoelige attributen nooit direct worden weergegeven; gebruik waar nodig buckets of eenrichtings-transformaties.
 #10.4.2    Level: 1    Role: D/V
 Controleer of query-snelheidsbeperkingen herhaalde adaptieve queries van dezelfde principal beperken.
 #10.4.3    Level: 2    Role: D
 Controleer of het model is getraind met privacy-behoudende ruis.

---

### 10.5 Verdediging tegen model-extractie

Detecteer en voorkom ongeoorloofd klonen. Watermerken en analyse van query-patronen worden aanbevolen.

 #10.5.1    Level: 1    Role: D
 Verifieer dat inference-gateways wereldwijde en per-API-sleutel snelheidslimieten afdwingen die zijn afgestemd op de memorisatiedrempel van het model.
 #10.5.2    Level: 2    Role: D/V
 Controleer of statistieken over query-entropie en input-meervoudigheid een geautomatiseerde extractiedetector voeden.
 #10.5.3    Level: 2    Role: V
 Verifieer dat fragiele of probabilistische watermerken kunnen worden bewezen met p < 0,01 in ≤ 1.000 queries tegen een vermoedelijke kloon.
 #10.5.4    Level: 3    Role: D
 Controleer of watermerk-sleutels en trigger-sets zijn opgeslagen in een hardware-beveiligingsmodule en jaarlijks worden vernieuwd.
 #10.5.5    Level: 3    Role: V
 Controleer of extraction-alert gebeurtenissen de aanstootgevende queries bevatten en zijn geïntegreerd met incident-respons draaiboeken.

---

### 10.6 Detectie van vergiftigde gegevens tijdens inferentietijd

Identificeer en neutraliseer achterdeurtjes of vergiftigde invoer.

 #10.6.1    Level: 1    Role: D
 Verifieer dat invoerwaarden worden gecontroleerd door een anomaliedetector (bijvoorbeeld STRIP, consistentiescore) voordat het model een voorspelling doet.
 #10.6.2    Level: 1    Role: V
 Controleer of de detector-drempels zijn afgestemd op schone/geïnfecteerde validatiesets om minder dan 5% false positives te bereiken.
 #10.6.3    Level: 2    Role: D
 Controleer of invoer die als vergiftigd wordt gemarkeerd, zachte blokkering en workflows voor menselijke beoordeling activeert.
 #10.6.4    Level: 2    Role: V
 Verifieer dat detectoren worden blootgesteld aan stresstests met adaptieve, triggerloze backdoor-aanvallen.
 #10.6.5    Level: 3    Role: D
 Controleer of de effectiviteitsmetriek voor detectie wordt vastgelegd en periodiek wordt herbeoordeeld met actuele dreigingsinformatie.

---

### 10.7 Dynamische aanpassing van het beveiligingsbeleid

Realtime beveiligingsbeleidupdates op basis van dreigingsinformatie en gedragsanalyse.

 #10.7.1    Level: 1    Role: D/V
 Controleer of beveiligingsbeleid dynamisch kan worden bijgewerkt zonder dat de agent opnieuw hoeft te worden gestart, terwijl de integriteit van de beleidsversie behouden blijft.
 #10.7.2    Level: 2    Role: D/V
 Controleer of beleidsupdates cryptografisch worden ondertekend door geautoriseerd beveiligingspersoneel en worden gevalideerd voordat ze worden toegepast.
 #10.7.3    Level: 2    Role: D/V
 Controleer of dynamische beleidswijzigingen worden vastgelegd met volledige audit-trails, inclusief rechtvaardiging, goedkeuringsketens en terugrolprocedures.
 #10.7.4    Level: 3    Role: D/V
 Controleer of adaptieve beveiligingsmechanismen de gevoeligheid van bedreigingsdetectie aanpassen op basis van risicocontext en gedrags- patronen.
 #10.7.5    Level: 3    Role: D/V
 Verifieer dat beslissingen over beleidsaanpassing verklaarbaar zijn en bewijsvoering bevatten voor beoordeling door het beveiligingsteam.

---

### 10.8 Reflectiegebaseerde beveiligingsanalyse

Beveiligingsvalidatie door middel van zelfreflectie van de agent en metacognitieve analyse.

 #10.8.1    Level: 1    Role: D/V
 Verifieer dat agentreflectiemechanismen een op beveiliging gerichte zelfbeoordeling van beslissingen en acties omvatten.
 #10.8.2    Level: 2    Role: D/V
 Controleer of reflectie-uitgangen worden gevalideerd om manipulatie van zelfbeoordelingsmechanismen door vijandige invoer te voorkomen.
 #10.8.3    Level: 2    Role: D/V
 Controleer of meta-cognitieve beveiligingsanalyse mogelijke vooringenomenheid, manipulatie of compromittering in de redeneerprocessen van agenten identificeert.
 #10.8.4    Level: 3    Role: D/V
 Controleer of op reflectie gebaseerde beveiligingswaarschuwingen verbeterde monitoring en mogelijke workflows voor menselijke tussenkomst activeren.
 #10.8.5    Level: 3    Role: D/V
 Verifieer dat continue leren van beveiligingsreflecties de dreigingsdetectie verbetert zonder de legitieme functionaliteit aan te tasten.

---

### 10.9 Evolutie & Zelfverbeteringsbeveiliging

Beveiligingsmaatregelen voor agentensystemen die in staat zijn tot zelfaanpassing en evolutie.

 #10.9.1    Level: 1    Role: D/V
 Verifieer dat zelfmodificatiecapaciteiten beperkt zijn tot aangewezen veilige gebieden met formele verificatiegrenzen.
 #10.9.2    Level: 2    Role: D/V
 Verifieer dat evolutievoorstellen een beveiligingsimpactbeoordeling ondergaan voordat ze worden geïmplementeerd.
 #10.9.3    Level: 2    Role: D/V
 Controleer of zelfverbeteringsmechanismen herstelopties bevatten met integriteitsverificatie.
 #10.9.4    Level: 3    Role: D/V
 Verifieer dat meta-leren beveiliging voorkomt dat verbetering algoritmen op een vijandige wijze worden gemanipuleerd.
 #10.9.5    Level: 3    Role: D/V
 Verifieer dat recursieve zelfverbetering wordt begrensd door formele veiligheidscriteria met wiskundige bewijzen van convergentie.

---

#### Referenties

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

## 11 Privacybescherming & Beheer van Persoonsgegevens

### Beheersingsdoelstelling

Handhaaf strikte privacygaranties gedurende de gehele AI-levenscyclus—verzameling, training, inferentie en incidentrespons—zodat persoonlijke gegevens alleen worden verwerkt met duidelijke toestemming, minimale noodzakelijke omvang, aantoonbare verwijdering en formele privacywaarborgen.

---

### 11.1 Anonimisering & Data Minimalisatie

 #11.1.1    Level: 1    Role: D/V
 Verifieer dat directe en quasi-identificatoren worden verwijderd of gehasht.
 #11.1.2    Level: 2    Role: D/V
 Controleer of geautomatiseerde audits k-anonimiteit/l-diversiteit meten en een waarschuwing geven wanneer de drempelwaarden onder het beleid dalen.
 #11.1.3    Level: 2    Role: V
 Verifieer dat de rapporten over de belangrijkheid van modelkenmerken geen identifierlekkage aantonen boven ε = 0,01 wederzijdse informatie.
 #11.1.4    Level: 3    Role: V
 Controleer of formele bewijzen of certificering met synthetische data aantonen dat het re-identificatierisico ≤ 0,05 is, zelfs bij koppelingsaanvallen.

---

### 11.2 Recht om te worden vergeten & handhaving van verwijdering

 #11.2.1    Level: 1    Role: D/V
 Verifieer dat verzoeken tot verwijdering van gegevenssubjecten worden doorgevoerd naar ruwe datasets, checkpoints, embeddings, logs en back-ups binnen servicetijdafspraken van minder dan 30 dagen.
 #11.2.2    Level: 2    Role: D
 Verifieer dat "machine-unlearning"-routines fysiek opnieuw trainen of een benadering van verwijdering gebruiken met gecertificeerde unlearning-algoritmen.
 #11.2.3    Level: 2    Role: V
 Controleer of de evaluatie van het shadow-model bewijst dat vergeten records minder dan 1% van de output beïnvloeden na unlearning.
 #11.2.4    Level: 3    Role: V
 Controleer of verwijderingsgebeurtenissen onveranderlijk worden vastgelegd en controleerbaar zijn voor toezichthouders.

---

### 11.3 Bescherming van differentiële privacy

 #11.3.1    Level: 2    Role: D/V
 Controleer of privacyverlies-rapportagedashboards waarschuwen wanneer de cumulatieve ε de beleidsdrempels overschrijdt.
 #11.3.2    Level: 2    Role: V
 Verifieer dat black-box privacy audits ε̂ binnen 10% van de opgegeven waarde schatten.
 #11.3.3    Level: 3    Role: V
 Controleer of formele bewijzen alle na-training finesse-aanpassingen en embeddings omvatten.

---

### 11.4 Doelbeperking en bescherming tegen scope creep

 #11.4.1    Level: 1    Role: D
 Controleer of elke dataset en modelcheckpoint een machinelesbare doelaanduiding draagt die overeenkomt met de oorspronkelijke toestemming.
 #11.4.2    Level: 1    Role: D/V
 Verifieer dat runtime monitors queries detecteren die niet consistent zijn met het verklaarde doel en een zachte weigering activeren.
 #11.4.3    Level: 3    Role: D
 Verifieer dat beleid-als-code poorten het opnieuw implementeren van modellen naar nieuwe domeinen zonder DPIA-beoordeling blokkeren.
 #11.4.4    Level: 3    Role: V
 Controleer of formele traceerbaarheidsbewijzen aantonen dat elke levenscyclus van persoonlijke gegevens binnen het toegestane bereik blijft.

---

### 11.5 Toestemmingsbeheer en Wettige Grondslag Tracking

 #11.5.1    Level: 1    Role: D/V
 Controleer of een Consent-Management Platform (CMP) de toestemmingsstatus, het doel en de bewaartermijn per betrokkene vastlegt.
 #11.5.2    Level: 2    Role: D
 Controleer of API's toestemmings tokens onthullen; modellen moeten het tokenbereik valideren voordat ze inferentie uitvoeren.
 #11.5.3    Level: 2    Role: D/V
 Verifieer dat geweigerde of ingetrokken toestemming de verwerkingspijplijnen binnen 24 uur stopzet.

---

### 11.6 Gefedereerd leren met privacycontroles

 #11.6.1    Level: 1    Role: D
 Controleer of clientupdates lokale differentiële privacyruis toevoegen voordat ze worden geaggregeerd.
 #11.6.2    Level: 2    Role: D/V
 Controleer of trainingsstatistieken differentieel privé zijn en nooit het verlies van een enkele cliënt onthullen.
 #11.6.3    Level: 2    Role: V
 Controleer of vergiftigingsbestendige aggregatie (bijv. Krum/Trimmed-Mean) is ingeschakeld.
 #11.6.4    Level: 3    Role: V
 Verifieer dat formele bewijzen het totale ε-budget aantonen met minder dan 5 nutverlies.

---

#### Referenties

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

## C12 Monitoring, Logging en Anomaliedetectie

### Beheersingsdoelstelling

Deze sectie biedt vereisten voor het leveren van realtime en forensische zichtbaarheid in wat het model en andere AI-componenten waarnemen, doen en retourneren, zodat bedreigingen kunnen worden gedetecteerd, geanalyseerd en ervan geleerd kan worden.

### C12.1 Verzoek- en antwoordregistratie

 #12.1.1    Level: 1    Role: D/V
 Controleer of alle gebruikersopdrachten en modelantwoorden worden vastgelegd met de juiste metadata (bijv. tijdstempel, gebruikers-ID, sessie-ID, modelversie).
 #12.1.2    Level: 1    Role: D/V
 Controleer of logboeken worden opgeslagen in beveiligde, toegangsbeperkte repositories met passende bewaarbeleid en back-upprocedures.
 #12.1.3    Level: 1    Role: D/V
 Controleer of logopslagsystemen encryptie toepassen voor data in rust en tijdens transport om gevoelige informatie in logs te beveiligen.
 #12.1.4    Level: 1    Role: D/V
 Controleer of gevoelige gegevens in prompts en uitvoer automatisch worden geanonimiseerd of afgeschermd voordat ze worden gelogd, met configureerbare regels voor het anonimiseren van persoonsgegevens, inloggegevens en eigendomsinformatie.
 #12.1.5    Level: 2    Role: D/V
 Controleer of beleidsbeslissingen en veiligheidsfilteracties met voldoende detail worden vastgelegd om audit en debugging van inhoudsmoderatiesystemen mogelijk te maken.
 #12.1.6    Level: 2    Role: D/V
 Verifieer dat de integriteit van logbestanden beschermd is via bijvoorbeeld cryptografische handtekeningen of alleen-geschreven opslag.

---

### C12.2 Misbruikdetectie en waarschuwingen

 #12.2.1    Level: 1    Role: D/V
 Verifieer dat het systeem bekende jailbreak-patronen, pogingen tot promptinjectie en vijandige invoer detecteert en waarschuwt met behulp van op handtekeningen gebaseerde detectie.
 #12.2.2    Level: 1    Role: D/V
 Controleer of het systeem integreert met bestaande Security Information and Event Management (SIEM) platforms met behulp van standaard logformaten en protocollen.
 #12.2.3    Level: 2    Role: D/V
 Controleer of verrijkte beveiligingsevenementen AI-specifieke context bevatten, zoals modelidentificatoren, betrouwbaarheidscores en beslissingen van veiligheidsfilters.
 #12.2.4    Level: 2    Role: D/V
 Controleer of gedragsafwijkingsdetectie ongebruikelijke gespreks patronen, buitensporige herkansingspogingen of systematische testgedragingen identificeert.
 #12.2.5    Level: 2    Role: D/V
 Verifieer dat realtime waarschuwingsmechanismen beveiligingsteams informeren wanneer mogelijke beleidschendingen of aanvalspogingen worden gedetecteerd.
 #12.2.6    Level: 2    Role: D/V
 Verifieer dat aangepaste regels zijn opgenomen om AI-specifieke bedreigingspatronen te detecteren, waaronder gecoördineerde jailbreak-pogingen, prompt-injectiecampagnes en model-extractie-aanvallen.
 #12.2.7    Level: 3    Role: D/V
 Verifieer dat geautomatiseerde incidentrespons-workflows gecompromitteerde modellen kunnen isoleren, kwaadaardige gebruikers kunnen blokkeren en kritieke beveiligingsgebeurtenissen kunnen escaleren.

---

### C12.3 Detectie van modelafwijking

 #12.3.1    Level: 1    Role: D/V
 Controleer of het systeem basisprestatiestatistieken bijhoudt, zoals nauwkeurigheid, betrouwbaarheidscores, latentie en foutpercentages over modelversies en tijdsperioden.
 #12.3.2    Level: 2    Role: D/V
 Controleer of geautomatiseerde waarschuwingen worden geactiveerd wanneer prestatie-indicatoren vooraf gedefinieerde degradatiedrempels overschrijden of significant afwijken van de referentiewaarden.
 #12.3.3    Level: 2    Role: D/V
 Controleer of hallucinatiedetectiemonitoren gevallen identificeren en markeren wanneer modeluitvoer feitelijk onjuiste, inconsistente of gefabriceerde informatie bevat.

---

### C12.4 Prestatie- en Gedragstelemetrie

 #12.4.1    Level: 1    Role: D/V
 Controleer of operationele statistieken, waaronder verzoeklatentie, tokenverbruik, geheugen- en doorvoergebruik, continu worden verzameld en gemonitord.
 #12.4.2    Level: 1    Role: D/V
 Verifieer dat succes- en faalkansen worden bijgehouden met categorisering van fouttypes en hun onderliggende oorzaken.
 #12.4.3    Level: 2    Role: D/V
 Controleer of het monitoren van resourcegebruik GPU-/CPU-gebruik, geheugengebruik en opslagvereisten omvat, met waarschuwingen bij het overschrijden van de drempelwaarden.

---

### C12.5 Planning en uitvoering van AI-incidentrespons

 #12.5.1    Level: 1    Role: D/V
 Controleer of de incidentresponsplannen specifiek ingaan op AI-gerelateerde beveiligingsincidenten zoals modelcompromittering, datapoisonsing en adversariële aanvallen.
 #12.5.2    Level: 2    Role: D/V
 Controleer of incidentresponseteams toegang hebben tot AI-specifieke forensische tools en expertise om modelgedrag en aanvalsvectoren te onderzoeken.
 #12.5.3    Level: 3    Role: D/V
 Verifieer dat de post-incidentanalyse rekening houdt met modelhertraining, updates van veiligheidsfilters en de integratie van geleerde lessen in beveiligingscontroles.

---

### C12.5 Detectie van prestatieafname van AI

Monitoren en detecteren van achteruitgang in de prestaties en kwaliteit van AI-modellen in de loop van de tijd.

 #12.5.1    Level: 1    Role: D/V
 Zorg ervoor dat modelnauwkeurigheid, precisie, recall en F1-scores continu worden gemonitord en vergeleken met basisdrempels.
 #12.5.2    Level: 1    Role: D/V
 Controleer of gegevensdriftdetectie veranderingen in de inputdistributie bewaakt die de modelprestaties kunnen beïnvloeden.
 #12.5.3    Level: 2    Role: D/V
 Controleer of concept drift-detectie veranderingen identificeert in de relatie tussen invoerwaarden en verwachte uitvoerwaarden.
 #12.5.4    Level: 2    Role: D/V
 Controleer of prestatievermindering geautomatiseerde waarschuwingen activeert en workflows voor het opnieuw trainen of vervangen van modellen initieert.
 #12.5.5    Level: 3    Role: V
 Verifieer dat de analyse van de hoofdoorzaak van degradatie de prestatieverminderingen correleert met gegevenswijzigingen, infrastructuurproblemen of externe factoren.

---

### C12.6 DAG Visualisatie & Workflow Beveiliging

Bescherm workflows visualisatiesystemen tegen informelekken en manipulatieaanvallen.

 #12.6.1    Level: 1    Role: D/V
 Controleer of de DAG-visualisatiegegevens worden gesaneerd om gevoelige informatie te verwijderen voordat ze worden opgeslagen of verzonden.
 #12.6.2    Level: 1    Role: D/V
 Verifieer dat de toegangscontroles voor workflowvisualisatie ervoor zorgen dat alleen geautoriseerde gebruikers de beslissingspaden van de agent en redeneringstraces kunnen bekijken.
 #12.6.3    Level: 2    Role: D/V
 Controleer of de integriteit van DAG-gegevens wordt beschermd door cryptografische handtekeningen en opslagmechanismen die manipulatie detecteren.
 #12.6.4    Level: 2    Role: D/V
 Controleer of workflowvisualisatiesystemen invoervalidatie toepassen om injectieaanvallen via gemanipuleerde knoop- of randgegevens te voorkomen.
 #12.6.5    Level: 3    Role: D/V
 Controleer of realtime DAG-updates worden beperkt in snelheid en gevalideerd om denial-of-service-aanvallen op visualisatiesystemen te voorkomen.

---

### C12.7 Proactieve monitoring van beveiligingsgedrag

Detectie en preventie van beveiligingsbedreigingen door middel van proactieve analyse van agentgedrag.

 #12.7.1    Level: 1    Role: D/V
 Verifieer dat proactieve agentgedragingen worden beveiligingsgevalideerd voordat ze worden uitgevoerd, met integratie van risicobeoordeling.
 #12.7.2    Level: 2    Role: D/V
 Verifieer dat autonome initiatie triggers onder meer evaluatie van de beveiligingscontext en beoordeling van het dreigingslandschap omvatten.
 #12.7.3    Level: 2    Role: D/V
 Controleer of proactieve gedragsmodellen worden geanalyseerd op mogelijke beveiligingsimplicaties en onbedoelde gevolgen.
 #12.7.4    Level: 3    Role: D/V
 Verifieer dat beveiligingskritieke proactieve acties expliciete goedkeuringsketens vereisen met auditrajecten.
 #12.7.5    Level: 3    Role: D/V
 Verifieer dat gedragsafwijkingsdetectie afwijkingen in proactieve agentpatronen identificeert die kunnen wijzen op compromittering.

---

### Referenties

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Menselijk Toezicht, Verantwoording & Bestuur

### Beheersingsdoelstelling

Dit hoofdstuk biedt vereisten voor het behouden van menselijke toezicht en duidelijke verantwoordingsketens in AI-systemen, waarbij verklaarbaarheid, transparantie en ethisch beheer gedurende de gehele AI-levenscyclus worden gewaarborgd.

---

### C13.1 Kill-Switch & Override Mechanismen

Bied uitschakel- of terugdraaimogelijkheden wanneer onveilig gedrag van het AI-systeem wordt waargenomen.

 #13.1.1    Level: 1    Role: D/V
 Controleer of er een handmatige noodstopschakelaar bestaat om de inferentie en output van het AI-model onmiddellijk te stoppen.
 #13.1.2    Level: 1    Role: D
 Controleer of de override-bedieningen alleen toegankelijk zijn voor bevoegd personeel.
 #13.1.3    Level: 3    Role: D/V
 Controleer of rollback-procedures kunnen terugkeren naar eerdere modelversies of veilige-modusoperaties.
 #13.1.4    Level: 3    Role: V
 Controleer regelmatig of de override-mechanismen worden getest.

---

### C13.2 Beslissingscontrolepunten met menselijke tussenkomst

Vereis menselijke goedkeuringen wanneer de inzet vooraf bepaalde risicodrempels overschrijdt.

 #13.2.1    Level: 1    Role: D/V
 Zorg ervoor dat AI-beslissingen met hoog risico expliciete menselijke goedkeuring vereisen voordat ze worden uitgevoerd.
 #13.2.2    Level: 1    Role: D
 Controleer of risicodrempels duidelijk zijn gedefinieerd en automatisch beoordelingsworkflows door mensen activeren.
 #13.2.3    Level: 2    Role: D
 Controleer of er noodprocedures zijn voor tijdgevoelige beslissingen wanneer menselijke goedkeuring niet binnen de vereiste tijdsbestekken kan worden verkregen.
 #13.2.4    Level: 3    Role: D/V
 Controleer of escalatieprocedures duidelijke autorisatieniveaus definiëren voor verschillende beslissingssoorten of risicocategorieën, indien van toepassing.

---

### C13.3 Ketting van Verantwoordelijkheid & Controleerbaarheid

Log operatoracties en modelbeslissingen.

 #13.3.1    Level: 1    Role: D/V
 Controleer of alle beslissingen van het AI-systeem en menselijke interventies worden geregistreerd met tijdstempels, gebruikersidentiteiten en motieven voor de beslissing.
 #13.3.2    Level: 2    Role: D
 Controleer of auditlogs niet kunnen worden gewijzigd en zorg ervoor dat ze mechanismen voor integriteitsverificatie bevatten.

---

### C13.4 Verklaarbare AI-technieken

Belang van oppervlaktekenmerken, tegenfeitelijke voorbeelden en lokale verklaringen.

 #13.4.1    Level: 1    Role: D/V
 Controleer of AI-systemen basisuitleg geven voor hun beslissingen in een voor mensen leesbaar formaat.
 #13.4.2    Level: 2    Role: V
 Verifieer dat de kwaliteit van de uitleg wordt gevalideerd door middel van menselijke evaluatiestudies en meetmethoden.
 #13.4.3    Level: 3    Role: D/V
 Controleer of scores voor kenmerkenbelang of attributiemethoden (SHAP, LIME, enz.) beschikbaar zijn voor kritieke beslissingen.
 #13.4.4    Level: 3    Role: V
 Controleer of tegenfeitelijke verklaringen laten zien hoe invoer kan worden aangepast om resultaten te veranderen, indien toepasselijk voor het gebruiksscenario en het domein.

---

### C13.5 Modelkaarten & Gebruiksaangiften

Onderhoud modelkaarten voor beoogd gebruik, prestatie-indicatoren en ethische overwegingen.

 #13.5.1    Level: 1    Role: D
 Controleer of modelkaarten de beoogde gebruikssituaties, beperkingen en bekende faalmodi documenteren.
 #13.5.2    Level: 1    Role: D/V
 Controleer of prestatie-indicatoren voor verschillende toepasselijke gebruikssituaties worden vermeld.
 #13.5.3    Level: 2    Role: D
 Controleer of ethische overwegingen, bias-beoordelingen, evaluaties van rechtvaardigheid, kenmerken van trainingsgegevens en bekende beperkingen van trainingsgegevens gedocumenteerd en regelmatig bijgewerkt worden.
 #13.5.4    Level: 2    Role: D/V
 Controleer of modelkaarten versiebeheer hebben en gedurende de levenscyclus van het model worden onderhouden met wijzigingsregistratie.

---

### C13.6 Kwantificering van onzekerheid

Propageer betrouwbaarheidscores of entropiematen in antwoorden.

 #13.6.1    Level: 1    Role: D
 Controleer of AI-systemen betrouwbaarheidscores of onzekerheidsmaten bij hun uitkomsten geven.
 #13.6.2    Level: 2    Role: D/V
 Controleer of onzekerheidsdrempels leiden tot extra menselijke beoordeling of alternatieve besluitvormingspaden.
 #13.6.3    Level: 2    Role: V
 Controleer of methoden voor onzekerheidskwantificatie zijn gekalibreerd en gevalideerd aan de hand van feitelijke gegevens.
 #13.6.4    Level: 3    Role: D/V
 Verifieer dat de onzekerheidsverspreiding wordt behouden in meervoudige AI-workflows.

---

### C13.7 Transparantierapporten voor gebruikers

Bied periodieke rapportages over incidenten, afwijkingen en datagebruik.

 #13.7.1    Level: 1    Role: D/V
 Controleer of het gebruik van gegevensbeleid en praktijken voor het beheren van gebruikersconsent duidelijk worden gecommuniceerd aan belanghebbenden.
 #13.7.2    Level: 2    Role: D/V
 Verifieer dat AI-impactbeoordelingen worden uitgevoerd en dat de resultaten worden opgenomen in de rapportage.
 #13.7.3    Level: 2    Role: D/V
 Verifieer dat transparantierapporten die regelmatig worden gepubliceerd AI-incidenten en operationele statistieken in redelijke mate van detail bekendmaken.

#### Referenties

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

## Bijlage A: Woordenlijst

Deze uitgebreide woordenlijst biedt definities van belangrijke AI-, ML- en beveiligingstermen die door het hele AISVS worden gebruikt om duidelijkheid en gemeenschappelijk begrip te waarborgen.
​
Adversariale voorbeeld: een invoer die opzettelijk is gemaakt om een AI-model een fout te laten maken, vaak door subtiele verstoringen toe te voegen die voor mensen onwaarneembaar zijn.
​
Robuustheid tegen adversariaal aanvallen – Adversariale robuustheid in AI verwijst naar het vermogen van een model om zijn prestaties te behouden en weerstand te bieden tegen misleiding of manipulatie door opzettelijk vervaardigde, kwaadaardige invoer die fouten moet veroorzaken.
​
Agent – AI-agenten zijn software systemen die AI gebruiken om doelen na te streven en taken namens gebruikers te voltooien. Ze tonen redenering, planning en geheugen en hebben een mate van autonomie om beslissingen te nemen, te leren en zich aan te passen.
​
Agentische AI: AI-systemen die met een zekere mate van autonomie kunnen opereren om doelen te bereiken, waarbij ze vaak beslissingen nemen en acties uitvoeren zonder directe menselijke tussenkomst.
​
Attribute-Based Access Control (ABAC): Een toegangscontroleparadigma waarbij autorisatiebeslissingen worden genomen op basis van attributen van de gebruiker, bron, actie en omgeving, geëvalueerd op het moment van de aanvraag.
​
Backdoor-aanval: Een type data-vergiftigingsaanval waarbij het model wordt getraind om op een specifieke manier te reageren op bepaalde triggers, terwijl het zich anders normaal gedraagt.
​
Bias: Systematische fouten in AI-modeluitvoer die kunnen leiden tot onrechtvaardige of discriminerende uitkomsten voor bepaalde groepen of in specifieke contexten.
​
Bias Exploitatie: Een aanvalstechniek die gebruikmaakt van bekende vooroordelen in AI-modellen om uitvoer of uitkomsten te manipuleren.
​
Cedar: Amazons beleids-taal en machine voor fijnmazige permissies gebruikt bij de implementatie van ABAC voor AI-systemen.
​
Chain of Thought: Een techniek voor het verbeteren van redeneren in taalmodellen door tussenliggende redeneringsstappen te genereren voordat een definitief antwoord wordt gegeven.
​
Circuitonderbrekers: Mechanismen die automatisch de werking van AI-systemen stoppen wanneer specifieke risicodrempels worden overschreden.
​
Data-lek: Onbedoelde blootstelling van gevoelige informatie via de uitvoer of het gedrag van een AI-model.
​
Datavergiftiging: Het opzettelijk corrumperen van trainingsgegevens om de integriteit van het model te compromitteren, vaak om achterdeurtjes te installeren of de prestaties te verslechteren.
​
Differentiële privacy – Differentiële privacy is een wiskundig rigoureus kader voor het vrijgeven van statistische informatie over datasets, terwijl de privacy van individuele gegevenssubjecten wordt beschermd. Het stelt een gegevenshouder in staat om aggregaatpatronen van de groep te delen, terwijl informatie die over specifieke individuen wordt gelekt, wordt beperkt.
​
Inbeddingen: Dichte vectorrepresentaties van gegevens (tekst, afbeeldingen, enz.) die semantische betekenis vastleggen in een hoge-dimensionale ruimte.
​
Uitlegbaarheid – Uitlegbaarheid in AI is het vermogen van een AI-systeem om voor mensen begrijpelijke redenen te geven voor zijn beslissingen en voorspellingen, waardoor inzicht wordt geboden in de interne werking ervan.
​
Uitlegbare AI (XAI): AI-systemen die zijn ontworpen om menselijk begrijpelijke verklaringen te geven voor hun beslissingen en gedragingen via verschillende technieken en raamwerken.
​
Federated Learning: Een machine learning-benadering waarbij modellen worden getraind op meerdere gedecentraliseerde apparaten die lokale datasets bevatten, zonder de data zelf uit te wisselen.
​
Beveiligingsmaatregelen: Beperkingen die zijn geïmplementeerd om te voorkomen dat AI-systemen schadelijke, bevooroordeelde of anderszins ongewenste output genereren.
​
Hallucinatie – Een AI-hallucinatie verwijst naar een verschijnsel waarbij een AI-model onjuiste of misleidende informatie genereert die niet is gebaseerd op zijn trainingsgegevens of feitelijke realiteit.
​
Mens-in-de-lus (HITL): Systemen die zijn ontworpen om menselijke toezicht, verificatie of interventie bij cruciale besluitmomenten te vereisen.
​
Infrastructure as Code (IaC): Het beheren en beschikbaar stellen van infrastructuur via code in plaats van handmatige processen, waardoor beveiligingsscans en consistente uitrol mogelijk zijn.
​
Jailbreak: Technieken die worden gebruikt om veiligheidsvoorzieningen in AI-systemen, met name in grote taalmodellen, te omzeilen om verboden inhoud te produceren.
​
Least Privilege: Het beveiligingsprincipe waarbij alleen de minimaal noodzakelijke toegangsrechten worden toegekend aan gebruikers en processen.
​
LIME (Local Interpretable Model-agnostic Explanations): Een techniek om de voorspellingen van elke machine learning-classificator uit te leggen door deze lokaal te benaderen met een interpreteerbaar model.
​
Lidmaatschapsinference-aanval: een aanval die tot doel heeft te bepalen of een specifiek datapunt is gebruikt om een machine learning-model te trainen.
​
MITRE ATLAS: Adversarial Threat Landscape voor Kunstmatige Intelligentiesystemen; een kennisbank van adversariële tactieken en technieken tegen AI-systemen.
​
Modelkaart – Een modelkaart is een document dat gestandaardiseerde informatie biedt over de prestaties, beperkingen, beoogde toepassingen en ethische overwegingen van een AI-model om transparantie en verantwoordelijke AI-ontwikkeling te bevorderen.
​
Model Extractie: Een aanval waarbij een tegenstander herhaaldelijk een doelfunctiemodel bevraagt om zonder toestemming een functioneel vergelijkbare kopie te maken.
​
Modelinversie: Een aanval die probeert trainingsgegevens te reconstrueren door modeluitvoer te analyseren.
​
Beheer van de levenscyclus van modellen – Het beheer van de levenscyclus van AI-modellen is het proces van toezicht houden op alle fasen van het bestaan van een AI-model, inclusief het ontwerp, de ontwikkeling, implementatie, monitoring, onderhoud en uiteindelijke buitengebruikstelling, om ervoor te zorgen dat het effectief blijft en aansluit bij de doelstellingen.
​
Modelvergiftiging: Het direct inbrengen van kwetsbaarheden of achterdeurtjes in een model tijdens het trainingsproces.
​
Modeldiefstal/-roof: Het extraheren van een kopie of benadering van een eigendomsmodel door herhaalde queries.
​
Multi-agentensysteem: Een systeem dat bestaat uit meerdere interactieve AI-agenten, elk met mogelijk verschillende mogelijkheden en doelen.
​
OPA (Open Policy Agent): Een open-source beleidsmotor die uniforme handhaving van beleidsregels over de gehele stack mogelijk maakt.
​
Privacy-behoudende Machine Learning (PPML): Technieken en methoden om ML-modellen te trainen en te implementeren terwijl de privacy van de trainingsgegevens wordt beschermd.
​
Promptinjectie: Een aanval waarbij kwaadaardige instructies in invoer worden ingebed om het beoogde gedrag van een model te overschrijven.
​
RAG (Retrieval-Augmented Generation): Een techniek die grote taalmodellen verbetert door relevante informatie op te halen uit externe kennisbronnen voordat een antwoord wordt gegenereerd.
​
Red-Teaming: De praktijk van het actief testen van AI-systemen door het simuleren van vijandige aanvallen om kwetsbaarheden te identificeren.
​
SBOM (Software Bill of Materials): Een formeel document dat de details en toeleveringsketenrelaties bevat van diverse componenten die worden gebruikt bij het bouwen van software of AI-modellen.
​
SHAP (SHapley Additive exPlanations): Een speltheoretische benadering om de output van elk machine learning-model uit te leggen door de bijdrage van elke eigenschap aan de voorspelling te berekenen.
​
Supply Chain-aanval: Een systeem compromitteren door minder beveiligde elementen in de supply chain aan te vallen, zoals bibliotheken van derden, datasets of vooraf getrainde modellen.
​
Transfer Learning: Een techniek waarbij een model, ontwikkeld voor één taak, wordt hergebruikt als uitgangspunt voor een model voor een tweede taak.
​
Vectordatabase: Een gespecialiseerde database ontworpen om hoogdimensionale vectoren (embedding) op te slaan en efficiënte gelijkeniszoekopdrachten uit te voeren.
​
Kwetsbaarheidsscanning: Geautomatiseerde tools die bekende beveiligingskwetsbaarheden in softwarecomponenten identificeren, waaronder AI-frameworks en afhankelijkheden.
​
Watermarking: Technieken om onzichtbare markeringen in AI-gegenereerde inhoud in te voegen om de herkomst te volgen of AI-generatie te detecteren.
​
Zero-day kwetsbaarheid: Een eerder onbekende kwetsbaarheid die aanvallers kunnen misbruiken voordat ontwikkelaars een patch creëren en uitrollen.

## Bijlage B: Referenties

### TODO

## Bijlage C: AI-beveiligingsbeheer en documentatie

### Doelstelling

Deze bijlage bevat fundamentele vereisten voor het opzetten van organisatorische structuren, beleidslijnen en processen om AI-beveiliging gedurende de gehele systeemlevenscyclus te beheren.

---

### AC.1 Adoptie van het AI Risicobeheer Kader

Bied een formeel kader om AI-specifieke risico's gedurende de gehele systeemlevenscyclus te identificeren, beoordelen en mitigeren.

 #AC.1.1    Level: 1    Role: D/V
 Verifieer of een AI-specifieke risicobeoordelingsmethodologie is gedocumenteerd en geïmplementeerd.
 #AC.1.2    Level: 2    Role: D
 Verifieer dat risicoanalyses worden uitgevoerd op cruciale momenten in de AI-levenscyclus en voorafgaand aan belangrijke wijzigingen.
 #AC.1.3    Level: 3    Role: D/V
 Controleer of het risicobeheerraamwerk overeenkomt met de vastgestelde standaarden (bijv. NIST AI RMF).

---

### AC.2 AI-beveiligingsbeleid & procedures

Definieer en handhaaf organisatorische normen voor veilige AI-ontwikkeling, -uitrol en -operatie.

 #AC.2.1    Level: 1    Role: D/V
 Controleer of gedocumenteerde AI-beveiligingsbeleid aanwezig zijn.
 #AC.2.2    Level: 2    Role: D
 Controleer of beleid minimaal jaarlijks en na belangrijke wijzigingen in het dreigingslandschap wordt herzien en bijgewerkt.
 #AC.2.3    Level: 3    Role: D/V
 Controleer of het beleid alle AISVS-categorieën en toepasselijke wettelijke vereisten behandelt.

---

### AC.3 Rollen en verantwoordelijkheden voor AI-beveiliging

Stel duidelijke verantwoordelijkheid vast voor AI-beveiliging binnen de gehele organisatie.

 #AC.3.1    Level: 1    Role: D/V
 Controleer of de beveiligingsrollen en verantwoordelijkheden van AI gedocumenteerd zijn.
 #AC.3.2    Level: 2    Role: D
 Verifieer dat verantwoordelijke personen beschikken over de juiste beveiligingskennis.
 #AC.3.3    Level: 3    Role: D/V
 Controleer of er een AI-ethiekcommissie of bestuursorgaan is opgericht voor AI-systemen met hoog risico.

---

### AC.4 Handhaving van Ethische AI-Richtlijnen

Zorg ervoor dat AI-systemen opereren volgens vastgestelde ethische principes.

 #AC.4.1    Level: 1    Role: D/V
 Controleer of er ethische richtlijnen bestaan voor de ontwikkeling en inzet van AI.
 #AC.4.2    Level: 2    Role: D
 Controleer of er mechanismen zijn geïmplementeerd om ethische schendingen te detecteren en te rapporteren.
 #AC.4.3    Level: 3    Role: D/V
 Verifieer dat regelmatige ethische beoordelingen van geïmplementeerde AI-systemen worden uitgevoerd.

---

### AC.5 AI-nalevingsbewaking

Houd rekening met en voldoe aan de evoluerende AI-regelgeving.

 #AC.5.1    Level: 1    Role: D/V
 Controleer of er processen bestaan om toepasselijke AI-regelgeving te identificeren.
 #AC.5.2    Level: 2    Role: D
 Controleer of aan alle wettelijke vereisten wordt voldaan.
 #AC.5.3    Level: 3    Role: D/V
 Controleer of regelgevende wijzigingen tijdig toetsingen en updates van AI-systemen activeren.

#### Referenties

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Appendix D: AI-ondersteunde veilige codering governance en verificatie

### Doelstelling

Dit hoofdstuk definieert basisorganisatorische controles voor het veilige en effectieve gebruik van AI-ondersteunde codeertools tijdens softwareontwikkeling, waarbij beveiliging en traceerbaarheid gedurende de volledige SDLC worden gewaarborgd.

---

### AD.1 AI-ondersteurde Secure-Coding Workflow

Integreer AI-tools in de veilige softwareontwikkelingscyclus (SSDLC) van de organisatie zonder de bestaande beveiligingsmaatregelen te verzwakken.

 #AD.1.1    Level: 1    Role: D/V
 Controleer of een gedocumenteerde workflow beschrijft wanneer en hoe AI-tools code kunnen genereren, herstructureren of beoordelen.
 #AD.1.2    Level: 2    Role: D
 Verifieer of de workflow overeenkomt met elke SSDLC-fase (ontwerp, implementatie, code review, testen, uitrol).
 #AD.1.3    Level: 3    Role: D/V
 Controleer of metrieken (bijv. kwetsbaarheidsdichtheid, gemiddelde tijd tot detectie) worden verzameld voor door AI gegenereerde code en worden vergeleken met alleen menselijke referentiewaarden.

---

### AD.2 AI Toolkwalificatie & Dreigingsmodellering

Zorg ervoor dat AI-codeertools worden geëvalueerd op beveiligingsmogelijkheden, risico's en impact op de toeleveringsketen voordat ze worden geïmplementeerd.

 #AD.2.1    Level: 1    Role: D/V
 Controleer of een dreigingsmodel voor elk AI‑hulpmiddel misbruik, modelinversie, datalekken en afhankelijkheidsketenrisico's identificeert.
 #AD.2.2    Level: 2    Role: D
 Verifieer dat toolevaluaties statische/dynamische analyse van alle lokale componenten omvatten en een beoordeling van SaaS-eindpunten (TLS, authenticatie/autorisatie, logging).
 #AD.2.3    Level: 3    Role: D/V
 Controleer of evaluaties volgens een erkaderd raamwerk worden uitgevoerd en opnieuw worden uitgevoerd na belangrijke versie-updates.

---

### AD.3 Beheer van beveiligde prompts en context

Voorkom het lekken van geheimen, eigendomscode en persoonlijke gegevens bij het opstellen van prompts of contexten voor AI-modellen.

 #AD.3.1    Level: 1    Role: D/V
 Controleer of schriftelijke richtlijnen het versturen van geheimen, inloggegevens of geclassificeerde gegevens in prompts verbieden.
 #AD.3.2    Level: 2    Role: D
 Controleer of technische controles (client-side redactie, goedgekeurde contextfilters) automatisch gevoelige gegevens verwijderen.
 #AD.3.3    Level: 3    Role: D/V
 Controleer of prompts en reacties worden getokeniseerd, versleuteld tijdens overdracht en in opslag, en of de bewaartermijnen voldoen aan het gegevensclassificatiebeleid.

---

### AD.4 Validatie van door AI gegenereerde code

Detecteer en herstel kwetsbaarheden die door AI-uitvoer zijn geïntroduceerd voordat de code wordt samengevoegd of ingezet.

 #AD.4.1    Level: 1    Role: D/V
 Controleer of AI‑gegenereerde code altijd aan een menselijke codebeoordeling wordt onderworpen.
 #AD.4.2    Level: 2    Role: D
 Verifieer dat geautomatiseerde scanners (SAST/IAST/DAST) worden uitgevoerd bij elke pull request die AI‑gegenereerde code bevat en blokkeer merges bij kritieke bevindingen.
 #AD.4.3    Level: 3    Role: D/V
 Verifieer dat differentiële fuzz testing of op eigenschappen gebaseerde tests beveiligingskritieke gedragingen aantonen (bijv. invoervalidatie, autorisatielogica).

---

### AD.5 Uitlegbaarheid en Traceerbaarheid van Codevoorstellen

Geef auditors en ontwikkelaars inzicht in waarom een suggestie is gedaan en hoe deze zich heeft ontwikkeld.

 #AD.5.1    Level: 1    Role: D/V
 Controleer of prompt/antwoordparen worden vastgelegd met commit-ID's.
 #AD.5.2    Level: 2    Role: D
 Controleer of ontwikkelaars modelverwijzingen (trainingsfragmenten, documentatie) kunnen tonen die een suggestie ondersteunen.
 #AD.5.3    Level: 3    Role: D/V
 Controleer of verklaringsrapporten worden opgeslagen met ontwerpstukken en worden vermeld in beveiligingsbeoordelingen, in overeenstemming met de traceerbaarheidsprincipes van ISO/IEC 42001.

---

### AD.6 Continue Feedback & Model Fijn-afstemming

Verbeter de beveiligingsprestaties van het model in de loop van de tijd en voorkom negatieve verschuiving.

 #AD.6.1    Level: 1    Role: D/V
 Controleer of ontwikkelaars onveilige of niet-conforme suggesties kunnen markeren, en dat deze markeringen worden bijgehouden.
 #AD.6.2    Level: 2    Role: D
 Verifieer dat geaggregeerde feedback periodieke fijnafstemming of retrieval-augmented generatie informeert met gecontroleerde secure-coding corpora (bijv. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verifieer dat een gesloten-lus evaluatieomgeving regressietests uitvoert na elke fine-tuning; beveiligingsmaatregelen moeten voldoen aan of beter zijn dan eerdere referentiepunten voordat implementatie plaatsvindt.

---

#### Referenties

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Bijlage E: Voorbeeldtools en -kaders

### Doelstelling

Dit hoofdstuk biedt voorbeelden van tools en raamwerken die de implementatie of naleving van een bepaalde AISVS-vereiste kunnen ondersteunen. Deze moeten niet worden gezien als aanbevelingen of goedkeuringen door het AISVS-team of het OWASP GenAI Security Project.

---

### AE.1 Beheer van Trainingsgegevens en Beheer van Vooringenomenheid

Gereedschappen gebruikt voor data-analyse, governance en biasbeheer.

 #AE.1.1    Section: 1.1
 Data-inventarisatietools: Tools voor het beheer van data-inventarisaties zoals...
 #AE.1.2    Section: 1.2
 Encryptie in transit Gebruik TLS voor HTTPS-gebaseerde applicaties, met tools zoals openSSL en Python's`ssl`bibliotheek.

---

### AE.2 Validatie van gebruikersinvoer

Hulpmiddelen voor het verwerken en valideren van gebruikersinvoer.

 #AE.2.1    Section: 2.1
 Promptinjectie Verdedigingstools: Gebruik beveiligingstools zoals NVIDIA's NeMo of Guardrails AI.

---

## C1 Trainingsgegevensbeheer en Vooringenomenheidsbeheer

### C1.1 Herkomst van trainingsgegevens

Beheer een verifieerbare inventaris van alle datasets, accepteer alleen vertrouwde bronnen en registreer elke wijziging voor controleerbaarheid.

 #1.1.1    Level: 1    Role: D/V
 Verifieer dat er een actuele inventaris wordt bijgehouden van elke trainingsdatabron (oorsprong, beheerder/eigenaar, licentie, verzamelmethode, beoogde gebruiksbeperkingen en verwerkingsgeschiedenis).

