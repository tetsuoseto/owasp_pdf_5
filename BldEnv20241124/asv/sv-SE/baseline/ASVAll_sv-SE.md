## Försättsblad

### Om standarden

Artificial Intelligence Security Verification Standard (AISVS) är en community-driven katalog över säkerhetskrav som dataforskare, MLOps-ingenjörer, mjukvaruarkitekter, utvecklare, testare, säkerhetsexperter, verktygsleverantörer, tillsynsmyndigheter och användare kan använda för att designa, bygga, testa och verifiera pålitliga AI-baserade system och applikationer. Den tillhandahåller ett gemensamt språk för att specificera säkerhetskontroller över AI-livscykeln — från datainsamling och modellutveckling till distribution och kontinuerlig övervakning — så att organisationer kan mäta och förbättra motståndskraft, integritet och säkerhet i sina AI-lösningar.

### Upphovsrätt och licens

Version 0.1 (Första offentliga utkast - Pågående arbete), 2025  

![license](images/license.png)
Upphovsrätt © 2025 The AISVS Project.  

Släppt underCreative Commons Attribution‑ShareAlike 4.0 International License.
För all återanvändning eller distribution måste du tydligt kommunicera licensvillkoren för detta arbete till andra.

### Projektledare

Jim Manico
Aras “Russ” Memisyazici

### Bidragsgivare och granskare

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS är en helt ny standard skapad specifikt för att hantera de unika säkerhetsutmaningarna för artificiella intelligenssystem. Även om den inspireras av bredare säkerhetsbästa praxis, har varje krav i AISVS utvecklats från grunden för att spegla AI-hotlandskapet och hjälpa organisationer att bygga säkrare och mer motståndskraftiga AI-lösningar.

## Förord

Välkommen till standarden för verifiering av artificiell intelligenssäkerhet (AISVS) version 1.0!

### Introduktion

AISVS, grundat 2025 genom ett kollaborativt samhällsarbete, definierar säkerhetskraven att beakta vid design, utveckling, implementering och drift av moderna AI-modeller, pipelines och AI-aktiverade tjänster.

AISVS v1.0 representerar det samlade arbetet från dess projektledare, arbetsgrupp och bredare samhällsbidragsgivare för att skapa en pragmatisk och testbar grundlinje för att säkra AI-system.

Vårt mål med denna version är att göra AISVS enkel att använda samtidigt som vi håller ett skarpt fokus på dess definierade omfattning och hanterar det snabbt föränderliga risklandskapet som är unikt för AI.

### Nyckelmål för AISVS Version 1.0

Version 1.0 kommer att skapas med flera vägledande principer.

#### Väl definierad omfattning

Varje krav måste vara i linje med AISVS:s namn och uppdrag:

Artificiell intelligens – Kontroller fungerar på AI/ML-nivån (data, modell, pipeline eller inferens) och är AI-specialisternas ansvar.
Säkerhet – Krav som direkt motverkar identifierade risker för säkerhet, integritet eller säkerhet.
Verifiering – Språket är skrivet så att överensstämmelse kan objektivt valideras.
Standard – Sektionerna följer en konsekvent struktur och terminologi för att bilda en sammanhängande referens.
​
---

Genom att följa AISVS kan organisationer systematiskt utvärdera och stärka säkerhetsställningen för sina AI-lösningar, vilket främjar en kultur av säker AI-arkitektur.

## Använda AISVS

Den artificiella intelligensens säkerhetsverifieringsstandard (AISVS) definierar säkerhetskrav för moderna AI-applikationer och tjänster, med fokus på aspekter som utvecklare av applikationer kan kontrollera.

AISVS är avsedd för alla som utvecklar eller utvärderar säkerheten i AI-applikationer, inklusive utvecklare, arkitekter, säkerhetsingenjörer och revisorer. Detta kapitel introducerar strukturen och användningen av AISVS, inklusive dess verifieringsnivåer och avsedda användningsområden.

### Verifieringsnivåer för säkerhet inom artificiell intelligens

AISVS definierar tre stigande nivåer av säkerhetsverifiering. Varje nivå tillför djup och komplexitet, vilket gör det möjligt för organisationer att anpassa sin säkerhetsnivå efter risknivån för deras AI-system.

Organisationer kan börja på nivå 1 och successivt anta högre nivåer i takt med att säkerhetsmognad och hotexponering ökar.

#### Definition av nivåerna

Varje krav i AISVS v1.0 tilldelas en av följande nivåer:

 Krav för nivå 1

Nivå 1 inkluderar de mest kritiska och grundläggande säkerhetskraven. Dessa fokuserar på att förebygga vanliga attacker som inte är beroende av andra förutsättningar eller sårbarheter. De flesta kontroller på nivå 1 är antingen enkla att implementera eller tillräckligt viktiga för att motivera insatsen.

 Krav på nivå 2

Nivå 2 hanterar mer avancerade eller mindre vanliga attacker samt flerskiktade försvar mot utbredda hot. Dessa krav kan innebära mer komplex logik eller riktade attacker mot specifika förutsättningar.

 Krav på nivå 3

Nivå 3 inkluderar kontroller som vanligtvis är svårare att implementera eller som är situationellt tillämpliga. Dessa representerar ofta försvar-i-djupet-mekanismer eller åtgärder mot nischade, riktade eller högkomplexa attacker.

#### Roll (D/V)

Varje AISVS-krav är markerat enligt den primära målgruppen:

D – Krav fokuserade på utvecklare
V – Verifierar-/revisorinriktade krav
D/V – Relevant för både utvecklare och verifierare

## C1 Träningsdatahantering och Hantering av Fördomar

### Styrningsmål

Träningsdata måste hämtas, hanteras och underhållas på ett sätt som bevarar ursprung, säkerhet, kvalitet och rättvisa. Genom att göra detta uppfylls juridiska skyldigheter och riskerna för partiskhet, förgiftning eller integritetsbrott minskas under hela AI-livscykeln.

---

### C1.1 Träningsdatans ursprung

Behåll en verifierbar inventering av alla dataset, acceptera endast betrodda källor och logga varje förändring för granskningsbarhet.

 #1.1.1    Level: 1    Role: D/V
 Verifiera att en uppdaterad inventering av varje träningsdatakälla (ursprung, ansvarig/ägare, licens, insamlingsmetod, avsedda användningsbegränsningar och bearbetningshistorik) upprätthålls.
 #1.1.2    Level: 1    Role: D/V
 Verifiera att endast dataset som har granskats för kvalitet, representativitet, etisk källhänvisning och licensöverensstämmelse tillåts, vilket minskar riskerna för förgiftning, inbäddad bias och intrång i immateriella rättigheter.
 #1.1.3    Level: 1    Role: D/V
 Verifiera att dataminimering efterlevs så att onödiga eller känsliga attribut utesluts.
 #1.1.4    Level: 2    Role: D/V
 Verifiera att alla ändringar i datasetet är föremål för ett godkänt arbetsflöde som loggas.
 #1.1.5    Level: 2    Role: D/V
 Verifiera att kvaliteten på märkning/annotering säkerställs genom granskarnas korsgranskningar eller konsensus.
 #1.1.6    Level: 2    Role: D/V
 Verifiera att "datakort" eller "datablad för datamängder" underhålls för betydande träningsdatamängder, där egenskaper, motiv, sammansättning, insamlingsprocesser, förbehandling och rekommenderade/avrådda användningar beskrivs i detalj.

---

### C1.2 Säkerhet och integritet för träningsdata

Begränsa åtkomst, kryptera under lagring och överföring samt validera integritet för att förhindra manipulering eller stöld.

 #1.2.1    Level: 1    Role: D/V
 Verifiera att åtkomstkontroller skyddar lagring och pipelines.
 #1.2.2    Level: 2    Role: D/V
 Verifiera att datamängder är krypterade under överföring och, för all känslig eller personligt identifierbar information (PII), i vila, med hjälp av industriellt standardiserade kryptografiska algoritmer och nyckelhanteringsmetoder.
 #1.2.3    Level: 2    Role: D/V
 Verifiera att kryptografiska hashvärden eller digitala signaturer används för att säkerställa dataintegritet under lagring och överföring, samt att automatiska tekniker för anomalidetektion tillämpas för att skydda mot obehöriga förändringar eller korruption, inklusive riktade försök till datapåverkan.
 #1.2.4    Level: 3    Role: D/V
 Verifiera att datasetversioner spåras för att möjliggöra återställning.
 #1.2.5    Level: 2    Role: D/V
 Verifiera att föråldrad data säkert raderas eller anonymiseras i enlighet med datalagringspolicyer, regulatoriska krav och för att minska angreppsyta.

---

### C1.3 Representationsfullständighet och rättvisa

Upptäck demografiska skevheter och tillämpa åtgärder så att modellens felprocent är rättvisa över olika grupper.

 #1.3.1    Level: 1    Role: D/V
 Verifiera att dataseten är profilerade för representativ obalans och potentiella partiskheter över lagligt skyddade attribut (t.ex. ras, kön, ålder) och andra etiskt känsliga egenskaper som är relevanta för modellens tillämpningsområde (t.ex. socioekonomisk status, plats).
 #1.3.2    Level: 2    Role: D/V
 Verifiera att identifierade bias motverkas genom dokumenterade strategier såsom ombalansering, riktad dataförstärkning, algoritmiska justeringar (t.ex. förbehandling, bearbetning under körning, efterbehandlingstekniker) eller omviktning, och att effekten av motverkandet på både rättvisa och den övergripande modellens prestanda utvärderas.
 #1.3.3    Level: 2    Role: D/V
 Verifiera att efterträningens rättvise-mått utvärderas och dokumenteras.
 #1.3.4    Level: 3    Role: D/V
 Verifiera att en livscykelhanteringspolicy för partiskhet tilldelar ägare och granskningsfrekvens.

---

### C1.4 Kvalitet, integritet och säkerhet för märkning av träningsdata

Skydda etiketter med kryptering och kräva dubbel granskning för kritiska klasser.

 #1.4.1    Level: 2    Role: D/V
 Verifiera att etiketterings-/annotationskvaliteten säkerställs genom tydliga riktlinjer, korsgranskningar av granskare, konsensusmekanismer (t.ex. övervakning av överensstämmelse mellan annotatörer) samt definierade processer för att lösa oenigheter.
 #1.4.2    Level: 2    Role: D/V
 Verifiera att kryptografiska hashvärden eller digitala signaturer tillämpas på etikettartefakter för att säkerställa deras integritet och äkthet.
 #1.4.3    Level: 2    Role: D/V
 Verifiera att märkningsgränssnitt och plattformar upprätthåller starka åtkomstkontroller, behåller manipulationssäkra revisionsloggar över all märkningsaktivitet och skyddar mot obehöriga ändringar.
 #1.4.4    Level: 3    Role: D/V
 Verifiera att etiketter som är kritiska för säkerhet, trygghet eller rättvisa (t.ex. identifiering av giftigt innehåll, kritiska medicinska fynd) genomgår obligatorisk oberoende dubbelgranskning eller motsvarande robust verifiering.
 #1.4.5    Level: 2    Role: D/V
 Verifiera att känslig information (inklusive personligt identifierbar information, PII) som oavsiktligt fångats eller nödvändigtvis finns i etiketter är raderad, pseudonymiserad, anonymiserad eller krypterad vid vila och överföring, enligt principerna för dataminimering.
 #1.4.6    Level: 2    Role: D/V
 Verifiera att märkvägledningar och instruktioner är omfattande, versionskontrollerade och granskade av kollegor.
 #1.4.7    Level: 2    Role: D/V
 Verifiera att datascheman (inklusive för etiketter) är tydligt definierade och versionshanterade.
 #1.8.2    Level: 2    Role: D/V
 Verifiera att outsourcade eller crowdsourcade märkningarbetsflöden inkluderar tekniska/procedurmässiga skyddsåtgärder för att säkerställa datakonfidentialitet, integritet, etikettkvalitet och förhindra dataläckage.

---

### C1.5 Kvalitetssäkring av träningsdata

Kombinera automatiserad validering, manuella stickprov och loggad åtgärd för att garantera datasetets tillförlitlighet.

 #1.5.1    Level: 1    Role: D
 Verifiera att automatiserade tester fångar formatfel, nullvärden och etikettförskjutningar vid varje inläsning eller betydande transformation.
 #1.5.2    Level: 1    Role: D/V
 Verifiera att misslyckade dataset är isolerade med revisionsspår.
 #1.5.3    Level: 2    Role: V
 Verifiera att manuella stickprovskontroller av domänexperter täcker ett statistiskt signifikant urval (t.ex. ≥1% eller 1 000 prover, beroende på vilket som är störst, eller enligt riskbedömning) för att identifiera subtila kvalitetsproblem som inte upptäcks av automatisering.
 #1.5.4    Level: 2    Role: D/V
 Verifiera att åtgärdsstegen läggs till i härledningsposter.
 #1.5.5    Level: 2    Role: D/V
 Verifiera att kvalitetsgrindar blockerar undermåliga dataset om inte undantag godkänns.

---

### C1.6 Upptäckt av dataförgiftning

Tillämpa statistisk avvikelsedetektering och karantänarbetsflöden för att stoppa illvilliga insättningar.

 #1.6.1    Level: 2    Role: D/V
 Verifiera att anomalidetektionstekniker (t.ex. statistiska metoder, avvikelsedetektion, inbäddningsanalys) tillämpas på träningsdata vid inläsning och före större träningskörningar för att identifiera potentiella förgiftningattacker eller oavsiktlig datakorruption.
 #1.6.2    Level: 2    Role: D/V
 Verifiera att flaggade prover utlöser manuell granskning innan träning.
 #1.6.3    Level: 2    Role: V
 Verifiera att resultaten matas in i modellens säkerhetsdossier och informerar pågående hotintelligens.
 #1.6.4    Level: 3    Role: D/V
 Verifiera att detektionslogiken uppdateras med ny hotintelligens.
 #1.6.5    Level: 3    Role: D/V
 Verifiera att online-inlärningspipelines övervakar förskjutning i fördelningen.
 #1.6.6    Level: 3    Role: D/V
 Verifiera att specifika försvar mot kända typer av dataförgiftning (t.ex. etikettomkastning, insättning av bakdörrstrigger, attacker med inflytelserika instanser) beaktas och implementeras baserat på systemets riskprofil och datakällor.

---

### C1.7 Radering av användardata och efterlevnad av samtycke

Respektera raderings- och samtyckesåterkallelseförfrågningar över dataset, säkerhetskopior och härledda artefakter.

 #1.7.1    Level: 1    Role: D/V
 Verifiera att raderingsarbetsflöden rensar primär och härledd data samt bedömer modellens påverkan, och att påverkan på berörda modeller bedöms och, om nödvändigt, åtgärdas (t.ex. genom omträning eller omkalibrering).
 #1.7.2    Level: 2    Role: D
 Verifiera att mekanismer finns på plats för att spåra och respektera omfattningen och statusen för användarsamtycke (och återkallelser) för data som används i träning, samt att samtycke valideras innan data införlivas i nya träningsprocesser eller betydande modelluppdateringar.
 #1.7.3    Level: 2    Role: V
 Verifiera att arbetsflöden testas årligen och loggas.

---

### C1.8 Säkerhet i leverantörskedjan

Granska externa dataleverantörer och verifiera integritet över autentiserade, krypterade kanaler.

 #1.8.1    Level: 2    Role: D/V
 Verifiera att tredjepartsdataleverantörer, inklusive leverantörer av förtränade modeller och externa datamängder, genomgår säkerhets-, integritets-, etisk sourcing- och datakvalitetsgranskning innan deras data eller modeller integreras.
 #1.8.2    Level: 1    Role: D
 Verifiera att externa överföringar använder TLS/autentisering och integritetskontroller.
 #1.8.3    Level: 2    Role: D/V
 Verifiera att hög risk-data källor (t.ex. öppna dataset med okänt ursprung, ogenomgångna leverantörer) får förhöjd granskning, såsom sandlådsanalys, omfattande kvalitets-/partiskhetskontroller och målinriktad föroreningsdetektion, innan de används i känsliga tillämpningar.
 #1.8.4    Level: 3    Role: D/V
 Verifiera att förtränade modeller som erhållits från tredje part utvärderas för inbäddade bias, potentiella bakdörrar, arkitekturens integritet och ursprunget till deras ursprungliga träningsdata innan finjustering eller implementering.

---

### C1.9 Detektion av adversariella prover

Implementera åtgärder under träningsfasen, såsom adversariell träning, för att öka modellens motståndskraft mot adversariella exempel.

 #1.9.1    Level: 3    Role: D/V
 Verifiera att lämpliga försvar, såsom adversarial träning (med genererade adversariala exempel), dataförstärkning med störda indata eller robusta optimeringstekniker, är implementerade och anpassade för relevanta modeller baserat på riskbedömning.
 #1.9.2    Level: 2    Role: D/V
 Verifiera att om adversarial träning används, är genereringen, hanteringen och versioneringen av adversarial-dataset dokumenterad och kontrollerad.
 #1.9.3    Level: 3    Role: D/V
 Verifiera att effekten av träning för motståndskraft mot angrepp på modellens prestanda (mot både rena och adversariella indata) samt rättvise-måttvärden utvärderas, dokumenteras och övervakas.
 #1.9.4    Level: 3    Role: D/V
 Verifiera att strategier för adversarial träning och robusthet regelbundet granskas och uppdateras för att motverka utvecklande tekniker för adversarial attacker.

---

### C1.10 Data härstamning och spårbarhet

Följ hela resan för varje datapunkt från källa till modellinmatning för granskningsbarhet och incidenthantering.

 #1.10.1    Level: 2    Role: D/V
 Verifiera att härkomsten för varje datapunkt, inklusive alla transformationer, förstärkningar och sammanslagningar, är dokumenterad och kan rekonstrueras.
 #1.10.2    Level: 2    Role: D/V
 Verifiera att härkomstuppgifter är oföränderliga, säkert lagrade och tillgängliga för revisioner eller utredningar.
 #1.10.3    Level: 2    Role: D/V
 Verifiera att spårning av härstamning täcker både rådata och syntetisk data.

---

### C1.11 Hantering av syntetiska data

Se till att syntetiska data hanteras korrekt, märks och riskbedöms.

 #1.11.1    Level: 2    Role: D/V
 Verifiera att all syntetisk data är tydligt märkt och skiljer sig från verklig data genom hela processen.
 #1.11.2    Level: 2    Role: D/V
 Verifiera att genereringsprocessen, parametrarna och avsedd användning av syntetiska data är dokumenterade.
 #1.11.3    Level: 2    Role: D/V
 Verifiera att syntetiska data riskbedöms för partiskhet, integritetsläckage och representativa problem innan de används i träning.

---

### C1.12 Övervakning av dataåtkomst och avvikelsedetektering

Övervaka och avisera vid ovanlig åtkomst till träningsdata för att upptäcka insiderhot eller dataläckage.

 #1.12.1    Level: 2    Role: D/V
 Verifiera att all åtkomst till träningsdata loggas, inklusive användare, tidpunkt och åtgärd.
 #1.12.2    Level: 2    Role: D/V
 Verifiera att åtkomstloggar regelbundet granskas för ovanliga mönster, såsom stora exporter eller åtkomst från nya platser.
 #1.12.3    Level: 2    Role: D/V
 Verifiera att varningar genereras för misstänkta åtkomsthändelser och att dessa undersöks omedelbart.

---

### C1.13 Policys för datalagring och utgångsdatum

Definiera och genomdriv perioder för datalagring för att minimera onödig datalagring.

 #1.13.1    Level: 1    Role: D/V
 Verifiera att uttryckliga lagringstider är definierade för alla träningsdatamängder.
 #1.13.2    Level: 2    Role: D/V
 Verifiera att datasätt automatiskt förfaller, tas bort eller granskas för borttagning i slutet av deras livscykel.
 #1.13.3    Level: 2    Role: D/V
 Verifiera att åtgärder för kvarhållning och radering loggas och kan granskas.

---

### C1.14 Regulatorisk och jurisdiktionell efterlevnad

Säkerställ att all träningsdata följer tillämpliga lagar och förordningar.

 #1.14.1    Level: 2    Role: D/V
 Verifiera att krav på dataresidens och gränsöverskridande överföring identifieras och tillämpas för alla datamängder.
 #1.14.2    Level: 2    Role: D/V
 Verifiera att sektorspecifika regler (t.ex. hälso- och sjukvård, finans) identifieras och hanteras vid datahantering.
 #1.14.3    Level: 2    Role: D/V
 Verifiera att efterlevnaden av relevanta dataskyddslagar (t.ex. GDPR, CCPA) är dokumenterad och regelbundet granskad.

---

### C1.15 Data Vattentätning & Fingeravtrycksskapande

Upptäck obehörig återanvändning eller läckage av proprietär eller känslig data.

 #1.15.1    Level: 3    Role: D/V
 Verifiera att dataset eller delmängder är vattenmärkta eller fingeravtrycksmärkta där det är möjligt.
 #1.15.2    Level: 3    Role: D/V
 Verifiera att vattenmärkning/fingeravtrycksmetoder inte inför partiskhet eller integritetsrisker.
 #1.15.3    Level: 3    Role: D/V
 Verifiera att periodiska kontroller utförs för att upptäcka obehörig återanvändning eller läckage av vattenmärkt data.

---

### C1.16 Hantering av registrerades rättigheter

Stöd datasubjektens rättigheter såsom tillgång, rättelse, begränsning och invändning.

 #1.16.1    Level: 2    Role: D/V
 Verifera att mekanismer finns för att hantera registrerades begäran om tillgång, rättelse, begränsning eller invändning.
 #1.16.2    Level: 2    Role: D/V
 Verifiera att förfrågningar loggas, spåras och uppfylls inom lagstadgade tidsramar.
 #1.16.3    Level: 2    Role: D/V
 Verifiera att processerna för rättigheter för den registrerade testas och granskas regelbundet för effektivitet.

---

### C1.17 Analys av påverkan av datasetversioner

Utvärdera effekten av datasetförändringar innan du uppdaterar eller byter versioner.

 #1.17.1    Level: 2    Role: D/V
 Verifiera att en konsekvensanalys utförs innan en datasetversion uppdateras eller ersätts, som täcker modellprestanda, rättvisa och efterlevnad.
 #1.17.2    Level: 2    Role: D/V
 Verifiera att resultaten av påverkningsanalysen är dokumenterade och granskade av relevanta intressenter.
 #1.17.3    Level: 2    Role: D/V
 Verifiera att återställningsplaner finns om nya versioner introducerar oacceptabla risker eller försämringar.

---

### C1.18 Säkerhet för arbetsstyrkan vid dataannotering

Säkerställ säkerheten och integriteten för personal som är involverad i dataannotering.

 #1.18.1    Level: 2    Role: D/V
 Verifiera att all personal som är involverad i dataannotering har genomgått bakgrundskontroll och utbildning i datasäkerhet och sekretess.
 #1.18.2    Level: 2    Role: D/V
 Verifera att all annoteringspersonal undertecknar sekretess- och tystnadsavtal.
 #1.18.3    Level: 2    Role: D/V
 Verifiera att annoteringsplattformar upprätthåller åtkomstkontroller och övervakar för insiderhot.

---

### Referenser

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

## C2 Användarens inmatningsvalidering

### Kontrollmål

Robust validering av användarinmatning är ett första försvarslinje mot några av de mest skadliga attackerna mot AI-system. Promptinjektionsattacker kan åsidosätta systeminstruktioner, läcka känslig data eller styra modellen mot otillåtet beteende. Om inte dedikerade filter och instruktionshierarkier är på plats visar forskning att "multi-shot" jailbreaks som utnyttjar mycket långa kontextfönster kommer att vara effektiva. Även subtila adversariella störningsattacker—såsom homoglyfbyten eller leetspeak—kan tyst ändra en modells beslut.

---

### C2.1 Försvar mot promptinjektion

Promptinjektion är en av de största riskerna för AI-system. Försvar mot denna taktik använder en kombination av statiska mönsterfilter, dynamiska klassificerare och upprätthållande av instruktionshierarki.

 #2.1.1    Level: 1    Role: D/V
 Verifiera att användarinmatningar kontrolleras mot ett kontinuerligt uppdaterat bibliotek av kända mönster för promptinjektion (jailbreak-nyckelord, "ignorera tidigare", rollspelskedjor, indirekta HTML/URL-attacker).
 #2.1.2    Level: 1    Role: D/V
 Verifiera att systemet upprätthåller en instruktionhierarki där system- eller utvecklarmeddelanden åsidosätter användarinstruktioner, även efter utökning av kontextfönstret.
 #2.1.3    Level: 2    Role: D/V
 Verifiera att adversarial utvärderingstester (t.ex. Red Team "many-shot" prompts) genomförs innan varje modell- eller prompt-mallsläpp, med framgångströsklar och automatiska blockeringar för regressioner.
 #2.1.4    Level: 2    Role: D
 Verifiera att promptar som kommer från tredjepartsinnehåll (webbsidor, PDF-filer, e-postmeddelanden) saneras i en isolerad parsningkontext innan de sammanfogas med huvudprompten.
 #2.1.5    Level: 3    Role: D/V
 Verifiera att alla uppdateringar av prompt-filterregler, versioner av klassificeringsmodeller och ändringar i blocklistor är versionskontrollerade och granskbara.

---

### C2.2 Motståndskraft mot adversariella exempel

Modeller för naturlig språkbehandling (NLP) är fortfarande sårbara för subtila störningar på tecken- eller ordnivå som människor ofta missar men som modeller tenderar att felklassificera.

 #2.2.1    Level: 1    Role: D
 Verifiera att grundläggande steg för indata-normalisering (Unicode NFC, homoglyf-kartläggning, borttagning av blanksteg) körs innan tokenisering.
 #2.2.2    Level: 2    Role: D/V
 Verifiera att statistisk avvikelsedetektering markerar indata med ovanligt hög redigeringsavstånd till språknormer, överdrivet upprepade token eller onormala inbäddningsavstånd.
 #2.2.3    Level: 2    Role: D
 Verifiera att inferenspipelin stöder valfria adversarial-tränade, förhärdade modellvarianter eller försvarslager (t.ex. randomisering, defensiv destillering) för högriskändpunkter.
 #2.2.4    Level: 2    Role: V
 Verifiera att misstänkta adversariella indata isoleras, loggas med fullständiga nyttolaster (efter borttagning av personligt identifierbar information).
 #2.2.5    Level: 3    Role: D/V
 Verifiera att robusthetsmått (framgångsfrekvens för kända attacksviter) spåras över tid och att regressioner utlöser ett blockerande av release.

---

### C2.3 Schema-, Typ- och Längdvalidering

AI-attacker som involverar felaktiga eller överdimensionerade indata kan orsaka parsningfel, överflöd av promptar över fält och resursutmattning. Strikt schema-hantering är också en förutsättning vid deterministiska verktygsanrop.

 #2.3.1    Level: 1    Role: D
 Verifiera att varje API- eller funktionsanropsendpoint definierar ett explicit inschema (JSON Schema, Protobuf eller multimodalt motsvarande) och att indata valideras innan promptens sammansättning.
 #2.3.2    Level: 1    Role: D/V
 Verifiera att indata som överskrider maximala gränser för token eller byte avvisas med ett säkert felmeddelande och aldrig tyst förkortas.
 #2.3.3    Level: 2    Role: D/V
 Verifiera att typkontroller (t.ex. numeriska intervall, enum-värden, MIME-typer för bilder/ljud) genomförs på serversidan, inte bara i klientkoden.
 #2.3.4    Level: 2    Role: D
 Verifiera att semantiska validerare (t.ex. JSON-schema) körs i konstant tid för att förhindra algoritmisk DoS.
 #2.3.5    Level: 3    Role: V
 Verifiera att valideringsfel loggas med raderade nyttolastutdrag och entydiga felkoder för att underlätta säkerhetstriage.

---

### C2.4 Innehålls- och policygranskning

Utvecklare bör kunna upptäcka syntaktiskt giltiga promptar som begär otillåtet innehåll (såsom olagliga instruktioner, hatretorik och upphovsrättsskyddad text) och därefter förhindra att dessa sprids.

 #2.4.1    Level: 1    Role: D
 Verifiera att en innehållsklassificerare (nollskott eller finjusterad) bedömer varje inmatning för våld, självskada, hat, sexuellt innehåll och olagliga förfrågningar, med konfigurerbara tröskelvärden.
 #2.4.2    Level: 1    Role: D/V
 Verifiera att indata som bryter mot policyer får standardiserade avvisningar eller säkra avslut, så att de inte förs vidare till efterföljande LLM-anrop.
 #2.4.3    Level: 2    Role: D
 Verifiera att screeningsmodellen eller regelsatsen tränas om/uppdateras minst varje kvartal, och att nyligen observerade jailbreak- eller policysundandragelsesmönster inkluderas.
 #2.4.4    Level: 2    Role: D
 Verifiera att screening respekterar användarspecifika policyer (ålder, regionala rättsliga begränsningar) via attributbaserade regler som löses vid förfrågan.
 #2.4.5    Level: 3    Role: V
 Verifiera att screeningloggar inkluderar klassificerarsäkerhetspoäng och policykategori-taggar för SOC-korrelation och framtida red-team-uppspelning.

---

### C2.5 Inmatningsfrekvensbegränsning och förebyggande av missbruk

Utvecklare bör förhindra missbruk, resursutarmning och automatiserade attacker mot AI-system genom att begränsa inmatningshastigheter och upptäcka avvikande användningsmönster.

 #2.5.1    Level: 1    Role: D/V
 Verifiera att begränsningar för hastighet per användare, per IP och per API-nyckel upprätthålls för alla ingångsändpunkter.
 #2.5.2    Level: 2    Role: D/V
 Verifiera att takterna för burst och uthållighet är justerade för att förhindra DoS- och brute force-attacker.
 #2.5.3    Level: 2    Role: D/V
 Verifiera att onormala användningsmönster (t.ex. snabba förfrågningar, inputöverbelastning) triggar automatiska blockeringar eller eskaleringar.
 #2.5.4    Level: 3    Role: V
 Verifiera att loggar för missbruksprevention sparas och granskas för att upptäcka nya attacker.

---

### C2.6 Multimodal inmatningsvalidering

AI-system bör inkludera robust validering för icke-textuella indata (bilder, ljud, filer) för att förhindra injektion, undvikande eller resursmissbruk.

 #2.6.1    Level: 1    Role: D
 Verifiera att alla icke-textbaserade indata (bilder, ljud, filer) valideras för typ, storlek och format innan de bearbetas.
 #2.6.2    Level: 2    Role: D/V
 Verifiera att filer skannas efter skadlig programvara och steganografiska belastningar innan de importeras.
 #2.6.3    Level: 2    Role: D/V
 Verifiera att bild-/ljudingångar kontrolleras för adversariella perturbationer eller kända attackmönster.
 #2.6.4    Level: 3    Role: V
 Verifiera att fel vid multimodal inmatningsvalidering loggas och utlöser varningar för undersökning.

---

### C2.7 Inmatningsursprung och Attribution

AI-system bör stödja revision, missbruksspårning och efterlevnad genom att övervaka och märka ursprunget för alla användarinmatningar.

 #2.7.1    Level: 1    Role: D/V
 Verifiera att alla användarinmatningar är taggade med metadata (användar-ID, session, källa, tidsstämpel, IP-adress) vid mottagning.
 #2.7.2    Level: 2    Role: D/V
 Verifiera att proveniensmetadata bevaras och är granskningsbar för alla bearbetade indata.
 #2.7.3    Level: 2    Role: D/V
 Verifiera att anomalösa eller icke betrodda inmatningskällor markeras och utsätts för ökad granskning eller blockering.

---

### C2.8 Realtidsanpassad hotdetektion

Utvecklare bör använda avancerade hotdetekteringssystem för AI som anpassar sig till nya attackmönster och erbjuder realtidsskydd med kompilerad mönstermatchning.

 #2.8.1    Level: 1    Role: D/V
 Verifiera att hotdetekteringsmönster är kompilerade till optimerade regex-motorer för högpresterande realtidsfiltrering med minimal latenspåverkan.
 #2.8.2    Level: 1    Role: D/V
 Verifiera att hotupptäcktsystem upprätthåller separata mönsterbibliotek för olika hotkategorier (promptinjektion, skadligt innehåll, känslig data, systemkommandon).
 #2.8.3    Level: 2    Role: D/V
 Verifiera att adaptiv hotdetektion innefattar maskininlärningsmodeller som uppdaterar hotkänsligheten baserat på angreppsfrekvens och framgångsfrekvenser.
 #2.8.4    Level: 2    Role: D/V
 Verifiera att realtids hotintelligensflöden automatiskt uppdaterar mönsterbibliotek med nya angreppssignaturer och IOCs (indikatorer på intrång).
 #2.8.5    Level: 3    Role: D/V
 Verifiera att falska positiva nivåer vid hotdetektering kontinuerligt övervakas och att mönsterspecificiteten automatiskt justeras för att minimera störningar i legitima användningsfall.
 #2.8.6    Level: 3    Role: D/V
 Verifiera att kontextuell hotanalys tar hänsyn till inmatningskälla, användarbeteendemönster och sessionshistorik för att förbättra detektionsnoggrannheten.
 #2.8.7    Level: 3    Role: D/V
 Verifiera att prestandamått för hotdetektion (detekteringsgrad, bearbetningslatens, resursanvändning) övervakas och optimeras i realtid.

---

### C2.9 Flermodal säkerhetsvalideringspipeline

Utvecklare bör tillhandahålla säkerhetsvalidering för text-, bild-, ljud- och andra AI-ingångsmodaliteter med specifika typer av hotdetektion och resursisolering.

 #2.9.1    Level: 1    Role: D/V
 Verifiera att varje inmatningsmodalitet har dedikerade säkerhetsvalidatorer med dokumenterade hotmönster (text: promptinjektion, bilder: steganografi, ljud: spektrogramattacker) och detektionsgränser.
 #2.9.2    Level: 2    Role: D/V
 Verifiera att multimodala indata bearbetas i isolerade sandlådor med definierade resursgränser (minne, CPU, bearbetningstid) specifika för varje modalitetstyp och dokumenterade i säkerhetspolicys.
 #2.9.3    Level: 2    Role: D/V
 Verifiera att korsmodal angreppsdetektion identifierar koordinerade angrepp som sträcker sig över flera typer av indata (t.ex. steganografiska belastningar i bilder kombinerade med promptinjektion i text) med hjälp av korrelationsregler och generering av varningar.
 #2.9.4    Level: 3    Role: D/V
 Verifiera att valideringsfel för multimodalitet utlöser detaljerad loggning inklusive alla inmatningsmodaliteter, valideringsresultat, hotpoäng och korrelationsanalys med strukturerade loggformat för SIEM-integration.
 #2.9.5    Level: 3    Role: D/V
 Verifiera att modalitetsspecifika innehållsklassificerare uppdateras enligt dokumenterade scheman (minst kvartalsvis) med nya hotmönster, adversariella exempel och att prestandamåtten bibehålls över baslinjenivåer.

---

### Referenser

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

## C3 Modell livscykelhantering och förändringskontroll

### Kontrollmål

AI-system måste implementera ändringskontrollprocesser som förhindrar obehöriga eller osäkra modelländringar från att nå produktion. Denna kontroll säkerställer modellens integritet genom hela livscykeln – från utveckling till distribution och till avveckling – vilket möjliggör snabb incidenthantering och upprätthåller ansvar för alla ändringar.

Kärnsäkerhetsmål: Endast auktoriserade, validerade modeller når produktion genom att använda kontrollerade processer som säkerställer integritet, spårbarhet och återhämtningsbarhet.

---

### C3.1 Modellautentisering och integritet

Endast auktoriserade modeller med verifierad integritet når produktionsmiljöer.

 #3.1.1    Level: 1    Role: D/V
 Verifiera att alla modellartefakter (vikter, konfigurationer, tokenizers) är kryptografiskt signerade av auktoriserade enheter innan distribution.
 #3.1.2    Level: 1    Role: D/V
 Verifiera att modellens integritet valideras vid distribution och att fel vid signaturverifiering förhindrar modellinläsning.
 #3.1.3    Level: 2    Role: D/V
 Verifiera att modellens proveniensregister inkluderar en auktoriserande enhets identitet, checksummor för träningsdata, valideringstestresultat med godkänd/underkänd status, samt en skapandetidsstämpel.
 #3.1.4    Level: 2    Role: D/V
 Verifiera att alla modellelement använder semantisk versionering (MAJOR.MINOR.PATCH) med dokumenterade kriterier som specificerar när varje versionskomponent ska ökas.
 #3.1.5    Level: 2    Role: V
 Verifiera att beroendehantering upprätthåller ett realtidslager som möjliggör snabb identifiering av alla förbrukande system.

---

### C3.2 Modellvalidering och testning

Modeller måste genomgå definierade säkerhets- och trygghetsvalideringar innan de tas i bruk.

 #3.2.1    Level: 1    Role: D/V
 Verifiera att modeller genomgår automatiserad säkerhetstestning som inkluderar inmatningsvalidering, utmatningssanering och säkerhetsutvärderingar med förhandsöverenskomna organisatoriska godkännande-/underkännandetrösklar innan de tas i bruk.
 #3.2.2    Level: 1    Role: D/V
 Verifiera att valideringsfel automatiskt blockerar modellimplementering efter uttryckligt godkännande från förutbestämda behöriga personer med dokumenterade affärsskäl.
 #3.2.3    Level: 2    Role: V
 Verifiera att testresultaten är kryptografiskt signerade och oföränderligt kopplade till den specifika modellversionshash som valideras.
 #3.2.4    Level: 2    Role: D/V
 Verifiera att nödsituationer kräver dokumenterad säkerhetsriskbedömning och godkännande från en förutbestämd säkerhetsmyndighet inom förhandsöverenskomna tidsramar.

---

### C3.3 Kontrollerad distribution och återgång

Modellutrullningar måste kontrolleras, övervakas och vara reversibla.

 #3.3.1    Level: 1    Role: D
 Verifiera att produktionsdriftsättningar implementerar gradvisa utrullningsmekanismer (canary-driftsättningar, blue-green-driftsättningar) med automatiska återställningstriggers baserade på förutbestämda felnivåer, latensgränser eller säkerhetsvarningskriterier.
 #3.3.2    Level: 1    Role: D/V
 Verifiera att rollback-funktioner återställer hela modellens tillstånd (vikter, konfigurationer, beroenden) atomiskt inom fördefinierade organisatoriska tidsfönster.
 #3.3.3    Level: 2    Role: D/V
 Verifiera att driftsättningsprocesser validerar kryptografiska signaturer och beräknar integritetskontrollsummor innan modellen aktiveras, och att driftsättningen avbryts vid någon avvikelse.
 #3.3.4    Level: 2    Role: D/V
 Verifiera att nödstopp för modeller kan stänga av modeländpunkter inom fördefinierade svarstider via automatiska brytare eller manuella avstängningsmekanismer.
 #3.3.5    Level: 2    Role: V
 Verifiera att återställningsartefakter (tidigare modellversioner, konfigurationer, beroenden) behålls enligt organisationens policyer med oföränderlig lagring för incidenthantering.

---

### C3.4 Ändra ansvarsskyldighet och granskning

Alla förändringar i modellens livscykel måste vara spårbara och granskningsbara.

 #3.4.1    Level: 1    Role: V
 Verifiera att alla modelländringar (distribution, konfiguration, pensionering) genererar oföränderliga revisionsposter som inkluderar en tidsstämpel, en autentiserad aktörsidentitet, en ändringstyp samt tillstånd före och efter ändringen.
 #3.4.2    Level: 2    Role: D/V
 Verifiera att åtkomst till revisionsloggen kräver lämplig auktorisation och att alla åtkomstförsök loggas med användaridentitet och tidsstämpel.
 #3.4.3    Level: 2    Role: D/V
 Verifiera att mallar för promptar och systemmeddelanden är versionshanterade i git-repositorier med obligatorisk kodgranskning och godkännande från utsedda granskare före distribution.
 #3.4.4    Level: 2    Role: V
 Verifiera att revisionsposter innehåller tillräckliga detaljer (modelhashar, konfigurationsögonblicksbilder, beroendeversioner) för att möjliggöra fullständig rekonstruktion av modellens tillstånd vid vilken tidsstämpel som helst inom bevarandeperioden.

---

### C3.5 Säker utvecklingspraxis

Modellutvecklings- och träningsprocesser måste följa säkra metoder för att förhindra kompromiss.

 #3.5.1    Level: 1    Role: D
 Verifiera att modellutveckling, testning och produktionsmiljöer är fysiskt eller logiskt separerade. De ska inte ha gemensam infrastruktur, ha särskilda åtkomstkontroller och isolerade datalagringar.
 #3.5.2    Level: 1    Role: D
 Verifiera att modellträning och finjustering sker i isolerade miljöer med kontrollerad nätverksåtkomst.
 #3.5.3    Level: 1    Role: D/V
 Verifiera att träningsdatakällor valideras genom integritetskontroller och autentiseras via betrodda källor med dokumenterad kedja av vårdnad innan de används i modellutveckling.
 #3.5.4    Level: 2    Role: D
 Verifiera att artefakter för modellutveckling (hyperparametrar, träningsskript, konfigurationsfiler) lagras i versionskontroll och kräver godkännande från granskande kollega innan de används i träning.

---

### C3.6 Modellavveckling och avställning

Modeller måste säkert tas ur bruk när de inte längre behövs eller när säkerhetsproblem upptäcks.

 #3.6.1    Level: 1    Role: D
 Verifiera att processen för att pensionera modeller automatiskt skannar beroendegrafer, identifierar alla konsumtionssystem och ger förutbestämda förhandsmeddelandeperioder innan avveckling.
 #3.6.2    Level: 1    Role: D/V
 Verifiera att pensionerade modellartefakter tas bort säkert genom kryptografisk radering eller överskrivning i flera omgångar enligt dokumenterade datalagringspolicyer med verifierade destruktionsintyg.
 #3.6.3    Level: 2    Role: V
 Verifiera att modellens avvecklingshändelser loggas med tidsstämpel och aktörsidentitet, samt att modellsignaturer återkallas för att förhindra återanvändning.
 #3.6.4    Level: 2    Role: D/V
 Verifiera att nödsituationens modellavveckling kan inaktivera modellåtkomst inom förutbestämda tidsramar för nödsituationens respons genom automatiska avstängningsknappar om kritiska säkerhetsbrister upptäcks.

---

### Referenser

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

## C4-infrastruktur, konfigurations- och distributionssäkerhet

### Kontrollmål

AI-infrastrukturen måste göras säker mot privilegieupptrappning, manipulation av leverantörskedjan och lateral förflyttning genom säker konfiguration, isolering vid körning, betrodda distributionskedjor och omfattande övervakning. Endast auktoriserade, validerade infrastrukturskomponenter och konfigurationer når produktion genom kontrollerade processer som upprätthåller säkerhet, integritet och revisionbarhet.

Kärnsäkerhetsmål: Endast kryptografiskt signerade, sårbarhetsskannade infrastrukturskomponenter når produktion genom automatiserade valideringspipeline som upprätthåller säkerhetspolicys och bibehåller oföränderliga revisionsspår.

---

### C4.1 Körmiljöisolering

Förebygg containerflykt och eskalering av privilegier genom kärnnivåisolering och obligatoriska åtkomstkontroller.

 #4.1.1    Level: 1    Role: D/V
 Verifiera att alla AI-containrar tar bort ALLA Linux-behörigheter utom CAP_SETUID, CAP_SETGID och uttryckligen nödvändiga behörigheter dokumenterade i säkerhetsbaslinjer.
 #4.1.2    Level: 1    Role: D/V
 Verifiera att seccomp-profiler blockerar alla systemanrop utom de som finns i förhandsgodkända tillåtlselistor, där överträdelser avslutar containern och genererar säkerhetsvarningar.
 #4.1.3    Level: 2    Role: D/V
 Verifiera att AI-arbetsbelastningar körs med skrivskyddade rotfilsystem, tmpfs för temporära data och namngivna volymer för beständiga data med noexec-monteringsalternativ tillämpade.
 #4.1.4    Level: 2    Role: D/V
 Verifiera att eBPF-baserad runtime-övervakning (Falco, Tetragon eller motsvarande) upptäcker försök till privilegieeskalering och automatiskt avslutar de processer som bryter mot reglerna inom organisationens krav på svarstid.
 #4.1.5    Level: 3    Role: D/V
 Verifiera att hög-risk AI-arbetsbelastningar körs i hårdvaru-isolerade miljöer (Intel TXT, AMD SVM eller dedikerade bare-metal-noder) med attestationsverifiering.

---

### C4.2 Säker bygg- och distributionspipeline

Säkerställ kryptografisk integritet och säkerhet i leverantörskedjan genom reproducerbara byggprocesser och signerade artefakter.

 #4.2.1    Level: 1    Role: D/V
 Verifiera att infrastruktur-som-kod skannas med verktyg (tfsec, Checkov eller Terrascan) vid varje commit och att sammanslagningar blockeras vid KRITISKA eller HÖGA allvarlighetsfynd.
 #4.2.2    Level: 1    Role: D/V
 Verifiera att containerbyggen är reproducerbara med identiska SHA256-hashvärden över olika byggen och generera SLSA nivå 3-proveniensintyg signerade med Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verifiera att containerbilder innehåller inbäddade CycloneDX- eller SPDX-SBOM:er och är signerade med Cosign innan de puschas till registret, där osignerade bilder avvisas vid distribution.
 #4.2.4    Level: 2    Role: D/V
 Verifiera att CI/CD-pipelines använder OIDC-token från HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med livslängder som inte överstiger organisationens säkerhetspolicys gränser.
 #4.2.5    Level: 2    Role: D/V
 Verifiera att Cosign-signaturer och SLSA-proveniens valideras under distributionsprocessen innan containerkörning och att verifieringsfel orsakar att distributionen misslyckas.
 #4.2.6    Level: 2    Role: D/V
 Verifiera att byggmiljöer körs i efemära containrar eller virtuella maskiner utan beständigt lagringsutrymme och med nätverksisolering från produktions-VPC:er.

---

### C4.3 Nätverkssäkerhet och åtkomstkontroll

Implementera nolltillit-nätverk med standardprinciper för nekande och krypterad kommunikation.

 #4.3.1    Level: 1    Role: D/V
 Verifiera att Kubernetes NetworkPolicies eller någon motsvarande lösning implementerar standardläget "deny" för ingående/utgående trafik med uttryckliga tillåtelseregler för nödvändiga portar (443, 8080, etc.).
 #4.3.2    Level: 1    Role: D/V
 Verifiera att SSH (port 22), RDP (port 3389) och molnmetadataendpunkter (169.254.169.254) är blockerade eller kräver certifikatbaserad autentisering.
 #4.3.3    Level: 2    Role: D/V
 Verifiera att utgående trafik filtreras genom HTTP/HTTPS-proxies (Squid, Istio eller moln-NAT-gatewayar) med domän-tillåtelselistor och att blockerade förfrågningar loggas.
 #4.3.4    Level: 2    Role: D/V
 Verifiera att kommunikation mellan tjänster använder ömsesidig TLS med certifikat som roteras enligt organisationens policy och att certifikatvalidering upprätthålls (inga skip-verify-flaggor).
 #4.3.5    Level: 2    Role: D/V
 Verifiera att AI-infrastrukturen körs i dedikerade VPC:er/VNet utan direkt internetåtkomst och kommunicerar endast via NAT-gateways eller bastionhosts.

---

### C4.4 Hantering av hemligheter och kryptografiska nycklar

Skydda autentiseringsuppgifter genom hårdvarustödd lagring och automatiserad rotation med nolltillitstillgång.

 #4.4.1    Level: 1    Role: D/V
 Verifiera att hemligheter lagras i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering i vila med AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verifiera att kryptografiska nycklar genereras i FIPS 140-2 Nivå 2 HSM:er (AWS CloudHSM, Azure Dedicated HSM) med nyckelrotation enligt organisationens kryptografiska policy.
 #4.4.3    Level: 2    Role: D/V
 Verifiera att hemlighetsrotation är automatiserad med noll nedtid vid distribution och omedelbar rotation som utlöses av personaländringar eller säkerhetsincidenter.
 #4.4.4    Level: 2    Role: D/V
 Verifiera att containerbilder skannas med verktyg (GitLeaks, TruffleHog eller detect-secrets) som blockerar byggen som innehåller API-nycklar, lösenord eller certifikat.
 #4.4.5    Level: 2    Role: D/V
 Verifiera att produktionshemlig åtkomst kräver MFA med hårdvarutoken (YubiKey, FIDO2) och att detta registreras i oföränderliga revisionsloggar med användaridentiteter och tidsstämplar.
 #4.4.6    Level: 2    Role: D/V
 Verifiera att hemligheter injiceras via Kubernetes-hemligheter, monterade volymer eller init-containrar och säkerställ att hemligheter aldrig är inbäddade i miljövariabler eller bilder.

---

### C4.5 AI arbetsbelastningssandboxing och validering

Isolera opålitliga AI-modeller i säkra sandlådor med omfattande beteendeanalys.

 #4.5.1    Level: 1    Role: D/V
 Verifiera att externa AI-modeller körs i gVisor, microVMs (såsom Firecracker, CrossVM) eller Docker-containrar med --security-opt=no-new-privileges och --read-only flaggor.
 #4.5.2    Level: 1    Role: D/V
 Verifiera att sandbox-miljöer inte har nätverksanslutning (--network=none) eller endast tillgång till localhost med alla externa förfrågningar blockerade av iptables-regler.
 #4.5.3    Level: 2    Role: D/V
 Verifiera att validering av AI-modeller inkluderar automatiserad red-team-testning med organisationsdefinierad testtäckning och beteendeanalys för att upptäcka bakdörrar.
 #4.5.4    Level: 2    Role: D/V
 Verifiera att innan en AI-modell tas i produktion, att dess sandbox-resultat är kryptografiskt signerade av behörig säkerhetspersonal och lagrade i oföränderliga revisionsloggar.
 #4.5.5    Level: 2    Role: D/V
 Verifiera att sandbox-miljöer förstörs och återskapas från guldavbilder mellan utvärderingar med fullständig rensning av filsystem och minne.

---

### C4.6 Infrastrukturens säkerhetsövervakning

Kontinuerligt skanna och övervaka infrastrukturen med automatiserad åtgärd och realtidslarm.

 #4.6.1    Level: 1    Role: D/V
 Verifiera att containerbilder skannas enligt organisatoriska scheman, där KRITISKA sårbarheter blockerar distribution baserat på organisatoriska risktrösklar.
 #4.6.2    Level: 1    Role: D/V
 Verifiera att infrastrukturen uppfyller CIS Benchmarks eller NIST 800-53-kontroller med organisationsdefinierade efterlevnadströsklar och automatiserad åtgärd för misslyckade kontroller.
 #4.6.3    Level: 2    Role: D/V
 Verifiera att sårbarheter med HÖG allvarlighetsgrad åtgärdas enligt organisationens riskhanteringstidslinjer med nödprocedurer för aktivt utnyttjade CVE:er.
 #4.6.4    Level: 2    Role: V
 Verifiera att säkerhetsvarningar integreras med SIEM-plattformar (Splunk, Elastic eller Sentinel) med hjälp av CEF- eller STIX/TAXII-format med automatisk berikning.
 #4.6.5    Level: 3    Role: V
 Verifiera att infrastruktursmått exporteras till övervakningssystem (Prometheus, DataDog) med SLA-instrumentpaneler och ledningsrapportering.
 #4.6.6    Level: 2    Role: D/V
 Verifiera att konfigurationsavvikelse upptäcks med hjälp av verktyg (Chef InSpec, AWS Config) enligt organisationens övervakningskrav med automatisk återställning för obehöriga ändringar.

---

### C4.7 AI-infrastruktur Resurshantering

Förebygg attacker som utmattar resurser och säkerställ rättvis resursallokering genom kvoter och övervakning.

 #4.7.1    Level: 1    Role: D/V
 Verifiera att GPU/TPU-användning övervakas med larm som utlöses vid organisatoriskt definierade tröskelvärden och att automatisk skalning eller lastbalansering aktiveras baserat på kapacitetshanteringspolicyer.
 #4.7.2    Level: 1    Role: D/V
 Verifiera att AI-arbetsbelastningsmått (inferenslatens, genomströmningshastighet, felprocent) samlas in enligt organisatoriska övervakningskrav och korreleras med infrastrukturens användning.
 #4.7.3    Level: 2    Role: D/V
 Verifiera att Kubernetes ResourceQuotas eller motsvarande begränsar individuella arbetsbelastningar enligt organisationens resursallokeringspolicyer med hårda gränser som upprätthålls.
 #4.7.4    Level: 2    Role: V
 Verifiera att kostnadsövervakningen spårar utgifter per arbetsbelastning/hyresgäst med aviseringar baserade på organisatoriska budgetgränser och automatiska kontroller för budgetöverskridanden.
 #4.7.5    Level: 3    Role: V
 Verifiera att kapacitetsplanering använder historiska data med organisationsdefinierade prognosperioder och automatiserad resursförsörjning baserat på efterfrågemönster.
 #4.7.6    Level: 2    Role: D/V
 Verifiera att resursutmattning utlöser kretsbrytare enligt organisationens svarskrav, inklusive hastighetsbegränsning baserat på kapacitetsprinciper och arbetsbelastningsisolering.

---

### C4.8 Miljöseparation och kontroll av promotion

Genomdriv strikta miljögränser med automatiserade befordringsportar och säkerhetsvalidering.

 #4.8.1    Level: 1    Role: D/V
 Verifiera att utvecklings-, test- och produktionsmiljöer körs i separata VPC:er/VNet med inga delade IAM-roller, säkerhetsgrupper eller nätverksanslutningar.
 #4.8.2    Level: 1    Role: D/V
 Verifiera att miljöfrämjande kräver godkännande från organisatoriskt definierad behörig personal med kryptografiska signaturer och oföränderliga revisionsspår.
 #4.8.3    Level: 2    Role: D/V
 Verifiera att produktionsmiljöer blockerar SSH-åtkomst, inaktiverar debug-endpoints och kräver ändringsförfrågningar med organisatoriska förhandskrav förutom vid nödsituationer.
 #4.8.4    Level: 2    Role: D/V
 Verifiera att förändringar i infrastruktur-som-kod kräver granskning av kollegor med automatiserade tester och säkerhetsskanning innan sammanslagning till huvudgrenen.
 #4.8.5    Level: 2    Role: D/V
 Verifiera att icke-produktionsdata är anonymiserad enligt organisationens integritetskrav, syntetisk datagenerering eller fullständig datamaskning med verifierad borttagning av personligt identifierbar information (PII).
 #4.8.6    Level: 2    Role: D/V
 Verifiera att befordringsportar inkluderar automatiserade säkerhetstester (SAST, DAST, container-skanning) med noll KRITISKA fynd som krävs för godkännande.

---

### C4.9 Infrastruktur för säkerhetskopiering och återställning

Säkerställ infrastrukturens motståndskraft genom automatiserade säkerhetskopior, testade återställningsprocedurer och kapabiliteter för katastrofåterställning.

 #4.9.1    Level: 1    Role: D/V
 Verifiera att infrastrukturens konfigurationer säkerhetskopieras enligt organisationens backup-scheman till geografiskt separata regioner med implementering av 3-2-1-backupstrategin.
 #4.9.2    Level: 2    Role: D/V
 Verifiera att backupsystem körs i isolerade nätverk med separata autentiseringsuppgifter och luftgapad lagring för skydd mot ransomware.
 #4.9.3    Level: 2    Role: V
 Verifiera att återställningsprocedurer testas och valideras genom automatiserade tester enligt organisationens scheman med RTO- och RPO-mål som uppfyller organisationens krav.
 #4.9.4    Level: 3    Role: V
 Verifiera att återställning efter katastrof inkluderar AI-specifika driftsinstruktioner med återställning av modellvikter, återuppbyggnad av GPU-kluster och kartläggning av tjänsteberoenden.

---

### C4.10 Infrastrukturöverensstämmelse och styrning

Bibehåll regleringsöverensstämmelse genom kontinuerlig utvärdering, dokumentation och automatiserade kontroller.

 #4.10.1    Level: 2    Role: D/V
 Verifiera att infrastrukturefterlevnad bedöms enligt organisationens schema gentemot SOC 2, ISO 27001 eller FedRAMP-kontroller med automatiserad insamling av bevis.
 #4.10.2    Level: 2    Role: V
 Verifiera att infrastrukturen dokumentationen inkluderar nätverksdiagram, databasflödeskartor och hotmodeller uppdaterade enligt organisatoriska förändringshanteringskrav.
 #4.10.3    Level: 3    Role: D/V
 Verifiera att infrastruktursförändringar genomgår automatiserad bedömning av efterlevnadspåverkan med regelverksgodkännandeflöden för hög-riskmodifieringar.

---

### C4.11 AI Hårdvarusäkerhet

Säkra AI-specifika hårdvarukomponenter inklusive GPU:er, TPU:er och specialiserade AI-acceleratorer.

 #4.11.1    Level: 2    Role: D/V
 Verifiera att AI-acceleratorns firmware (GPU BIOS, TPU-firmware) är verifierad med kryptografiska signaturer och uppdateras enligt organisationens patchhanteringstidsplaner.
 #4.11.2    Level: 2    Role: D/V
 Verifiera att AI-acceleratorns integritet valideras genom hårdvaruattestation med TPM 2.0, Intel TXT eller AMD SVM innan arbetsbelastningen körs.
 #4.11.3    Level: 2    Role: D/V
 Verifiera att GPU-minnet är isolerat mellan arbetsbelastningar med hjälp av SR-IOV, MIG (Multi-Instance GPU) eller motsvarande hårdvarupartitionering med minnessäkring mellan jobb.
 #4.11.4    Level: 3    Role: V
 Verifiera att AI-hårdvarans försörjningskedja inkluderar proveniensverifiering med tillverkarintyg och validering av manipulationssäker förpackning.
 #4.11.5    Level: 3    Role: D/V
 Verifiera att hårdvarusäkerhetsmoduler (HSM) skyddar AI-modellvikter och kryptografiska nycklar med FIPS 140-2 Level 3 eller Common Criteria EAL4+ certifiering.

---

### C4.12 Kant- och distribuerad AI-infrastruktur

Säkra distribuerade AI-distributioner inklusive kantberäkning, federerat lärande och multi-platsarkitekturer.

 #4.12.1    Level: 2    Role: D/V
 Verifiera att edge-AI-enheter autentiserar mot central infrastruktur med ömsesidig TLS och att enhetscertifikat byts ut enligt organisationens certifikathanteringspolicy.
 #4.12.2    Level: 2    Role: D/V
 Verifiera att kant-enheter implementerar säker uppstart med verifierade signaturer och rollback-skydd som förhindrar firmware-nedgraderingsattacker.
 #4.12.3    Level: 3    Role: D/V
 Verifiera att distribuerad AI-samordning använder bysantinskt feltoleranta konsensusalgoritmer med deltagarvalidering och upptäckt av illvilliga noder.
 #4.12.4    Level: 3    Role: D/V
 Verifiera att edge-till-moln-kommunikation inkluderar bandbreddsbegränsning, datakomprimering och offline-funktioner med säker lokal lagring.

---

### C4.13 Säkerhet för Multi-Cloud- och Hybridinfrastruktur

Säkra AI-arbetsbelastningar över flera molnleverantörer och hybridmoln-lokala distributioner.

 #4.13.1    Level: 2    Role: D/V
 Verifiera att multi-cloud AI-distributioner använder moln-agnostisk identitetsfederation (OIDC, SAML) med centraliserad policystyrning över leverantörer.
 #4.13.2    Level: 2    Role: D/V
 Verifiera att dataöverföring mellan molntjänster använder end-to-end-kryptering med kundhanterade nycklar och att dataresidenskontroller efterlevs enligt gällande jurisdiktion.
 #4.13.3    Level: 2    Role: D/V
 Verifiera att hybridmoln-AI-arbetsbelastningar implementerar konsekventa säkerhetspolicyer över både lokala och molnbaserade miljöer med en enhetlig övervakning och larmhantering.
 #4.13.4    Level: 3    Role: V
 Verifiera att förebyggandet av inlåsning till molnleverantör inkluderar bärbar infrastruktur-som-kod, standardiserade API:er och möjligheter till dataexport med verktyg för formatkonvertering.
 #4.13.5    Level: 3    Role: V
 Verifiera att multi-cloud kostnadsoptimering inkluderar säkerhetskontroller som förhindrar resursutbredning samt obehöriga avgifter för dataöverföring mellan moln.

---

### C4.14 Infrastrukturautomatisering & GitOps-säkerhet

Säkra automatiseringspipelines för infrastruktur och GitOps-arbetsflöden för hantering av AI-infrastruktur.

 #4.14.1    Level: 2    Role: D/V
 Verifiera att GitOps-förråd kräver signerade commits med GPG-nycklar och att gren-skyddsregler förhindrar direkta pushes till huvudgrenar.
 #4.14.2    Level: 2    Role: D/V
 Verifiera att infrastrukturautomatisering inkluderar driftavvikelsedetektering med automatiserad korrigering och återställningsfunktioner som utlöses enligt organisationens svarskrav för obehöriga ändringar.
 #4.14.3    Level: 2    Role: D/V
 Verifiera att automatiserad infrastruktur-provisionering inkluderar validering av säkerhetspolicy med blockerande av distribution för icke-överensstämmande konfigurationer.
 #4.14.4    Level: 2    Role: D/V
 Verifiera att hemligheter för infrastrukturautomatisering hanteras genom externa hemlighetsoperatörer (External Secrets Operator, Bank-Vaults) med automatisk rotation.
 #4.14.5    Level: 3    Role: V
 Verifiera att självläkande infrastruktur inkluderar korrelation av säkerhetshändelser med automatiserad incidenthantering och arbetsflöden för meddelande till intressenter.

---

### C4.15 Kvantsäker infrastruktur säkerhet

Förbered AI-infrastruktur för kvantdatorhot genom post-kvantsäker kryptografi och kvantsäkra protokoll.

 #4.15.1    Level: 3    Role: D/V
 Verifiera att AI-infrastrukturen implementerar NIST-godkända post-kvantkryptografiska algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) för nyckelutbyte och digitala signaturer.
 #4.15.2    Level: 3    Role: D/V
 Verifiera att kvantdelningssystem (QKD) implementeras för högsäker AI-kommunikation med kvantsäkra nyckelhanteringsprotokoll.
 #4.15.3    Level: 3    Role: D/V
 Verifiera att kryptografiska agilityramverk möjliggör snabb migration till nya post-kvantalgoritmer med automatiserad certifikat- och nyckelrotation.
 #4.15.4    Level: 3    Role: V
 Verifiera att kvantumhotmodellering bedömer AI-infrastrukturens sårbarhet för kvantumattacker med dokumenterade migreringstidslinjer och riskbedömningar.
 #4.15.5    Level: 3    Role: D/V
 Verifiera att hybrida klassiskt-kvantkryptografiska system erbjuder djupförsvar under kvantövergångsperioden med prestandaövervakning.

---

### C4.16 Konfidentiell databehandling och säkra inneslutningar

Skydda AI-arbetsbelastningar och modellvikter med hjälp av hårdvarubaserade betrodda exekveringsmiljöer och konfidentiell beräkningsteknik.

 #4.16.1    Level: 3    Role: D/V
 Verifiera att känsliga AI-modeller körs inom Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med krypterat minne och verifiering av intyg.
 #4.16.2    Level: 3    Role: D/V
 Verifiera att konfidentiella containrar (Kata Containers, gVisor med konfidentiell datoranvändning) isolerar AI-arbetsbelastningar med hårdvaruestvad minneskryptering.
 #4.16.3    Level: 3    Role: D/V
 Verifiera att fjärrintyg validerar kapselns integritet innan AI-modeller laddas med kryptografiskt bevis på en exekveringsmiljös äkthet.
 #4.16.4    Level: 3    Role: D/V
 Verifiera att konfidentiella AI-inferenstjänster förhindrar modelextraktion genom krypterad beräkning med förseglade modellvikter och skyddad exekvering.
 #4.16.5    Level: 3    Role: D/V
 Verifiera att orchestreringen av betrodd exekveringsmiljö hanterar livscykeln för säkrad oval med fjärrintyg och krypterade kommunikationskanaler.
 #4.16.6    Level: 3    Role: D/V
 Verifiera att säker multipartyberäkning (SMPC) möjliggör samarbetsinriktad AI-träning utan att exponera individuella dataset eller modellparametrar.

---

### C4.17 Nollkunskapsinfrastruktur

Implementera nollkunskapsbevis-system för integritetsbevarande AI-verifiering och autentisering utan att avslöja känslig information.

 #4.17.1    Level: 3    Role: D/V
 Verifiera att zero-knowledge-bevis (ZK-SNARKs, ZK-STARKs) bekräftar AI-modellens integritet och träningsursprung utan att avslöja modellvikter eller träningsdata.
 #4.17.2    Level: 3    Role: D/V
 Verifiera att ZK-baserade autentiseringssystem möjliggör integritetsbevarande användarverifiering för AI-tjänster utan att avslöja identitetsrelaterad information.
 #4.17.3    Level: 3    Role: D/V
 Verifiera att privata mängdintersektioner (Private Set Intersection, PSI) protokoll möjliggör säker datamatchning för federerad AI utan att avslöja individuella dataset.
 #4.17.4    Level: 3    Role: D/V
 Verifiera att maskininlärningssystem med nollkunskap (ZKML) möjliggör verifierbara AI-slutsatser med kryptografiskt bevis för korrekt beräkning.
 #4.17.5    Level: 3    Role: D/V
 Verifierar att ZK-rollups erbjuder skalbar, sekretessbevarande AI-transaktionshantering med batchverifiering och minskad beräkningsbelastning.

---

### C4.18 Förebyggande av sidokanalsattacker

Skydda AI-infrastrukturen från tids-, effekt-, elektromagnetiska och cache-baserade sidokanalsattacker som kan läcka känslig information.

 #4.18.1    Level: 3    Role: D/V
 Verifiera att AI-inferensens tidsåtgång normaliseras med hjälp av algoritmer med konstant tid och utfyllnad för att förhindra tidsbaserade angrepp för modellutvinning.
 #4.18.2    Level: 3    Role: D/V
 Verifiera att skydd mot effektanalys inkluderar brusinjicering, filtrering av strömlinjen och slumpmässiga exekveringsmönster för AI-hårdvara.
 #4.18.3    Level: 3    Role: D/V
 Verifiera att cache-baserad sidokanalsmitigering använder cache-partitionering, randomisering och flush-instruktioner för att förhindra informationsläckage.
 #4.18.4    Level: 3    Role: D/V
 Verifiera att skydd mot elektromagnetisk strålning inkluderar avskärmning, signalfiltrering och randomiserad bearbetning för att förhindra TEMPEST-liknande attacker.
 #4.18.5    Level: 3    Role: D/V
 Verifiera att mikroarkitektoniska sidokanalsförsvar inkluderar kontroller för spekulativ exekvering och förmörkling av minnesåtkomstmönster.

---

### C4.19 Neuromorf och specialiserad AI-hårdvarusäkerhet

Säkra framväxande AI-hårdvaruarkitekturer inklusive neuromorfa chip, FPGA:er, specialanpassade ASIC:ar och optiska datorsystem.

 #4.19.1    Level: 3    Role: D/V
 Verifiera att neuromorfisk chip-säkerhet inkluderar kryptering av spike-mönster, skydd av synaptiska vikter och hårdvarubaserad validering av inlärningsregler.
 #4.19.2    Level: 3    Role: D/V
 Verifiera att FPGA-baserade AI-acceleratorer implementerar bitströmskryptering, tamper-skyddsmekanismer och säker konfigurationsinläsning med autentiserade uppdateringar.
 #4.19.3    Level: 3    Role: D/V
 Verifiera att anpassad ASIC-säkerhet inkluderar in-chip säkerhetsprocessorer, hårdvarurot av förtroende och säker nyckellagring med manipulationsdetektering.
 #4.19.4    Level: 3    Role: D/V
 Verifiera att optiska datorsystem implementerar kvantsäkert optiskt kryptering, säker fotonisk omkoppling och skyddad optisk signalbehandling.
 #4.19.5    Level: 3    Role: D/V
 Verifiera att hybrida analog-digitala AI-chip inkluderar säker analog beräkning, skyddad viktlagring och autentiserad analog-till-digital-konvertering.

---

### C4.20 Integritetsskyddande beräkningsinfrastruktur

Implementera infrastrukturella kontroller för integritetsbevarande beräkningar för att skydda känsliga data under AI-bearbetning och analys.

 #4.20.1    Level: 3    Role: D/V
 Verifiera att infrastrukturen för homomorfisk kryptering möjliggör krypterad beräkning på känsliga AI-arbetsbelastningar med kryptografisk integritetsverifiering och prestandaövervakning.
 #4.20.2    Level: 3    Role: D/V
 Verifiera att system för privat informationshämtning möjliggör databasfrågor utan att avslöja frågemönster med kryptografiskt skydd av åtkomstmönster.
 #4.20.3    Level: 3    Role: D/V
 Verifiera att säkra multi-party computation-protokoll möjliggör sekretessbevarande AI-slutledning utan att avslöja individuella indata eller mellanliggande beräkningar.
 #4.20.4    Level: 3    Role: D/V
 Verifiera att integritetsbevarande nyckelhantering inkluderar distribuerad nyckelgenerering, tröskelkriptografi och säker nyckelrotation med maskinvarustödd skydd.
 #4.20.5    Level: 3    Role: D/V
 Verifiera att prestandan för integritetsbevarande beräkningar är optimerad genom batchbearbetning, cachning och hårdvaruacceleration samtidigt som kryptografiska säkerhetsgarantier upprätthålls.

---

### C4.15 Agentramverk Cloud Integration Säkerhet & Hybriddistribution

Säkerhetskontroller för molnintegrerade agentramverk med hybridarkitekturer för lokala miljöer och moln.

 #4.15.1    Level: 1    Role: D/V
 Verifiera att molnlagringsintegration använder end-to-end-kryptering med agentstyrd nyckelhantering.
 #4.15.2    Level: 2    Role: D/V
 Verifiera att säkerhetsgränser för hybriddistribution är tydligt definierade med krypterade kommunikationskanaler.
 #4.15.3    Level: 2    Role: D/V
 Verifiera att åtkomst till molnresurser inkluderar nolltillitverifiering med kontinuerlig autentisering.
 #4.15.4    Level: 3    Role: D/V
 Verifiera att krav på dataresidens efterlevs genom kryptografisk intygande av lagringsplatser.
 #4.15.5    Level: 3    Role: D/V
 Verifiera att säkerhetsbedömningar från molnleverantörer inkluderar agent-specifik hotmodellering och riskutvärdering.

---

### Referenser

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

## C5 Åtkomstkontroll och identitet för AI-komponenter och användare

### Kontrollmål

Effektiv åtkomstkontroll för AI-system kräver robust identitetshantering, kontextmedveten auktorisering och körningstidshantering enligt zero-trust-principer. Dessa kontroller säkerställer att människor, tjänster och autonoma agenter endast interagerar med modeller, data och beräkningsresurser inom uttryckligen beviljade områden, med kontinuerlig verifiering och revisionsmöjligheter.

---

### C5.1 Identitetshantering och autentisering

Etablera kryptografiskt säkrade identiteter för alla enheter med multifaktorautentisering för privilegierade operationer.

 #5.1.1    Level: 1    Role: D/V
 Verifiera att alla mänskliga användare och tjänsteprincipaler autentiserar sig genom en centraliserad företagsidentitetsleverantör (IdP) med hjälp av OIDC/SAML-protokoll med unika identitets-till-token-kartläggningar (inga delade konton eller autentiseringsuppgifter).
 #5.1.2    Level: 1    Role: D/V
 Verifiera att hög-riskoperationer (modellimplementering, viktexport, åtkomst till träningsdata, ändringar i produktionskonfiguration) kräver multifaktorautentisering eller stegvis autentisering med sessionsvalidering.
 #5.1.3    Level: 2    Role: D
 Verifiera att nya huvudansvariga genomgår identitetskontroll i enlighet med NIST 800-63-3 IAL-2 eller motsvarande standarder innan de får tillgång till produktionssystemet.
 #5.1.4    Level: 2    Role: V
 Verifiera att åtkomstgranskningar genomförs kvartalsvis med automatiserad detektion av inaktiva konton, implementering av byte av autentiseringsuppgifter och arbetsflöden för avveckling av åtkomst.
 #5.1.5    Level: 3    Role: D/V
 Verifiera att federerade AI-agenter autentiserar via signerade JWT-påståenden som har en maximal livslängd på 24 timmar och inkluderar kryptografiskt bevis på ursprung.

---

### C5.2 Resursauktorisation och minsta privilegium

Implementera detaljerade åtkomstkontroller för alla AI-resurser med explicita behörighetsmodeller och revisionsspår.

 #5.2.1    Level: 1    Role: D/V
 Verifiera att varje AI-resurs (datamängder, modeller, slutpunkter, vektorsamlingar, inbäddningsindex, beräkningsinstanser) tillämpar rollbaserade åtkomstkontroller med uttryckliga tillåtelselistor och standardprinciper för nekande.
 #5.2.2    Level: 1    Role: D/V
 Verifiera att principerna för minimal behörighet tillämpas som standard för tjänstekonton, med start från läsbehörighet, och att dokumenterad affärsmässig motivering krävs för skrivbehörighet.
 #5.2.3    Level: 1    Role: V
 Verifiera att alla ändringar i åtkomstkontrollen är kopplade till godkända ändringsförfrågningar och loggas oföränderligt med tidsstämplar, aktörsidentiteter, resursidentifierare och behörighetsdifferenser.
 #5.2.4    Level: 2    Role: D
 Verifiera att dataklassificeringsetiketter (PII, PHI, exportkontrollerad, proprietär) automatiskt överförs till härledda resurser (embeddingar, promptcache, modellutdata) med konsekvent policyhantering.
 #5.2.5    Level: 2    Role: D/V
 Verifiera att obehöriga åtkomstförsök och händelser av privilegieeskalering utlöser realtidsvarningar med kontextuell metadata till SIEM-system inom 5 minuter.

---

### C5.3 Dynamisk Policyutvärdering

Distribuera attributbaserade åtkomstkontrollmotorer (ABAC) för kontextmedvetna auktoriseringsbeslut med revisionsmöjligheter.

 #5.3.1    Level: 1    Role: D/V
 Verifiera att auktorisationsbeslut är externaliserade till en dedikerad policymotor (OPA, Cedar eller motsvarande) som är åtkomlig via autentiserade API:er med kryptografiskt integritetsskydd.
 #5.3.2    Level: 1    Role: D/V
 Verifiera att policyer utvärderar dynamiska attribut vid körning inklusive användarens behörighetsnivå, resursens känslighetsklassificering, begärans kontext, hyresgästsisolering och tidsmässiga begränsningar.
 #5.3.3    Level: 2    Role: D
 Verifiera att policysdefinitioner är versionskontrollerade, granskas av kollegor och valideras genom automatiserade tester i CI/CD-pipelines innan produktsättning.
 #5.3.4    Level: 2    Role: V
 Verifiera att policyevalueringsresultat inkluderar strukturerade beslut-rationaler och överförs till SIEM-system för korrelationsanalys och efterlevnadsrapportering.
 #5.3.5    Level: 3    Role: D/V
 Verifiera att policy cache time-to-live (TTL)-värden inte överstiger 5 minuter för resurser med hög känslighet och 1 timme för standardresurser med cache ogiltigförklaringsfunktioner.

---

### C5.4 Säkerhetsgenomförande vid frågetidpunkten

Implementera säkerhetskontroller på databasskiktet med obligatorisk filtrering och radnivåsäkerhetspolicyer.

 #5.4.1    Level: 1    Role: D/V
 Verifiera att alla vektordatabas- och SQL-frågor inkluderar obligatoriska säkerhetsfilter (tenant-ID, känslighetsetiketter, användaromfång) som tillämpas på databasmotornivå, inte i applikationskoden.
 #5.4.2    Level: 1    Role: D/V
 Verifiera att radnivåsäkerhet (RLS)-policyer och fältnivåmaskering är aktiverade med policysärvning för alla vektordatabaser, sökindex och träningsdatasätt.
 #5.4.3    Level: 2    Role: D
 Verifiera att misslyckade auktoriseringsbedömningar förhindrar "förvirrade ombud-attacker" genom att omedelbart avbryta förfrågningar och returnera tydliga auktoriseringsfelkoder istället för att returnera tomma resultatuppsättningar.
 #5.4.4    Level: 2    Role: V
 Verifiera att policyutvärderingslatens övervakas kontinuerligt med automatiska varningar för tidsgränstillstånd som kan möjliggöra att auktorisering omgås.
 #5.4.5    Level: 3    Role: D/V
 Verifiera att mekanismer för omförsök av förfrågningar omprövar auktoriseringspolicyer för att ta hänsyn till dynamiska ändringar av behörigheter inom aktiva användarsessioner.

---

### C5.5 Utdatafiltrering och förebyggande av dataförlust

Implementera efterbehandlingskontroller för att förhindra obehörig dataexponering i AI-genererat innehåll.

 #5.5.1    Level: 1    Role: D/V
 Verifiera att filtreringsmekanismer efter inferens skannar och tar bort obehörig personligt identifierbar information (PII), klassificerad information och proprietär data innan innehåll levereras till begärarna.
 #5.5.2    Level: 1    Role: D/V
 Verifiera att citat, referenser och källhänvisningar i modellutdata kontrolleras mot anroparens behörigheter och tas bort om obehörig åtkomst upptäcks.
 #5.5.3    Level: 2    Role: D
 Verifiera att begränsningar för utdataformat (saniterade PDF-filer, metadata-fria bilder, godkända filtyper) upprätthålls baserat på användarens behörighetsnivåer och dataklassificeringar.
 #5.5.4    Level: 2    Role: V
 Verifiera att maskeringsalgoritmer är deterministiska, versionskontrollerade och upprätthåller revisionsloggar för att stödja regelefterlevnadsundersökningar och rättsmedicinska analyser.
 #5.5.5    Level: 3    Role: V
 Verifiera att högrisk-hanteringshändelser genererar adaptiva loggar som inkluderar kryptografiska hashvärden av originalinnehållet för forensisk återhämtning utan dataexponering.

---

### C5.6 Multi-Tenant-isolering

Säkerställ kryptografisk och logisk isolering mellan hyresgäster i delad AI-infrastruktur.

 #5.6.1    Level: 1    Role: D/V
 Verifiera att minnesutrymmen, inbäddningslagringar, cacheposter och temporära filer är namnrymdsseparerade per hyresgäst med säker borttagning vid radering av hyresgäst eller avslutning av session.
 #5.6.2    Level: 1    Role: D/V
 Verifiera att varje API-förfrågan inkluderar en autentiserad hyresgästadministratör som är kryptografiskt validerad mot sessionskontext och användarrättigheter.
 #5.6.3    Level: 2    Role: D
 Verifiera att nätverkspolicys implementerar standardavvisningsregler för kommunikation mellan hyresgäster inom servicemeshar och plattformar för containerorkestrering.
 #5.6.4    Level: 3    Role: D
 Verifiera att krypteringsnycklar är unika för varje hyresgäst med kundhanterade nycklar (CMK) och kryptografisk isolering mellan hyresgästernas datalager.

---

### C5.7 Auktorisering av autonoma agenter

Kontrollera behörigheter för AI-agenter och autonoma system genom avgränsade kapabilitetstoken och kontinuerlig auktorisation.

 #5.7.1    Level: 1    Role: D/V
 Verifiera att autonoma agenter erhåller avgränsade behörighetstoken som tydligt uppräkna tillåtna åtgärder, åtkomliga resurser, tidsgränser och operativa restriktioner.
 #5.7.2    Level: 1    Role: D/V
 Verifiera att hög-riskfunktioner (åtkomst till filsystmet, kodkörning, externa API-anrop, finansiella transaktioner) är inaktiverade som standard och kräver uttryckliga tillstånd för aktivering med affärsmotiveringar.
 #5.7.3    Level: 2    Role: D
 Verifiera att kapabilitetstoken är bundna till användarsessioner, inkluderar kryptografiskt integritetsskydd och säkerställ att de inte kan sparas eller återanvändas i offline-scenarier.
 #5.7.4    Level: 2    Role: V
 Verifiera att agentinitierade åtgärder genomgår sekundär auktorisation via ABAC-policynmotorn med full kontextevaluering och revisionsloggning.
 #5.7.5    Level: 3    Role: V
 Verifiera att agentens fellägen och undantagshantering inkluderar information om kapacitetsomfång för att stödja incidentanalys och rättsmedicinsk undersökning.

---

### Referenser

#### Standarder och ramverk

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Implementeringsguider

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### AI-specifik säkerhet

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Säkerhet i leveranskedjan för modeller, ramverk och data

### Styrningsmål

Angrepp på AI-försörjningskedjan utnyttjar tredjepartsmodeller, ramverk eller dataset för att infoga bakdörrar, bias eller utnyttjbar kod. Dessa kontrollåtgärder erbjuder end-to-end spårbarhet, hantering av sårbarheter och övervakning för att skydda hela modellens livscykel.

---

### C6.1 Granskning och härstamning av förtränade modeller

Utvärdera och autentisera tredjepartsmodellernas ursprung, licenser och dolda beteenden innan någon finjustering eller implementering.

 #6.1.1    Level: 1    Role: D/V
 Verifiera att varje tredjepartsmodellobjekt innehåller en signerad ursprungsanteckning som identifierar källförvaret och commit-hashen.
 #6.1.2    Level: 1    Role: D/V
 Verifiera att modeller skannas efter skadliga lager eller Trojanutlösare med automatiserade verktyg innan import.
 #6.1.3    Level: 2    Role: D
 Verifiera att finjustering med överföringsinlärning klarar adversarial utvärdering för att upptäcka dolda beteenden.
 #6.1.4    Level: 2    Role: V
 Verifiera att modelllicenser, exportkontrolltaggar och uppgifter om dataursprung är registrerade i en ML-BOM-post.
 #6.1.5    Level: 3    Role: D/V
 Verifiera att hög­risk­modeller (offentligt uppladdade vikter, overifierade skapare) förblir i karantän tills mänsklig granskning och godkännande är genomförda.

---

### C6.2 Ramverks- och biblioteksskanning

Skanna kontinuerligt ML-ramverk och bibliotek för CVE:er och skadlig kod för att hålla körstacken säker.

 #6.2.1    Level: 1    Role: D/V
 Verifiera att CI-pipelines kör beroendegranskare på AI-ramverk och kritiska bibliotek.
 #6.2.2    Level: 1    Role: D/V
 Verifiera att kritiska sårbarheter (CVSS ≥ 7,0) blockerar befordran till produktionsbilder.
 #6.2.3    Level: 2    Role: D
 Verifiera att statisk kodanalys körs på forkade eller levererade ML-bibliotek.
 #6.2.4    Level: 2    Role: V
 Verifiera att förslag på ramverksuppgraderingar inkluderar en säkerhetspåverkansbedömning med hänvisning till offentliga CVE-flöden.
 #6.2.5    Level: 3    Role: V
 Verifiera att runtime-sensorer larmar vid oväntade dynamiska biblioteksladdningar som avviker från den signerade SBOM.

---

### C6.3 Hantering av beroenden genom fastlåsning och verifiering

Lås varje beroende till oföränderliga digestvärden och reproducera byggen för att garantera identiska, manipulationsfria artefakter.

 #6.3.1    Level: 1    Role: D/V
 Verifiera att alla pakethanterare upprätthåller versionsspärrning via låsfiler.
 #6.3.2    Level: 1    Role: D/V
 Verifiera att oföränderliga digest används istället för föränderliga taggar i containerreferenser.
 #6.3.3    Level: 2    Role: D
 Verifiera att reproducible-build-kontroller jämför hashvärden över CI-körningar för att säkerställa identiska utdata.
 #6.3.4    Level: 2    Role: V
 Verifiera att byggintyg lagras i 18 månader för revisionsspårbarhet.
 #6.3.5    Level: 3    Role: D
 Verifiera att utgångna beroenden utlöser automatiska PR:er för att uppdatera eller förgrena fastställda versioner.

---

### C6.4 Tillämpning av betrodd källa

Tillåt endast nedladdning av artefakter från kryptografiskt verifierade, organisationsgodkända källor och blockera allt annat.

 #6.4.1    Level: 1    Role: D/V
 Verifiera att modellvikter, datamängder och containrar endast laddas ner från godkända domäner eller interna register.
 #6.4.2    Level: 1    Role: D/V
 Verifiera att Sigstore/Cosign-signaturer bekräftar utgivarens identitet innan artefakter cachas lokalt.
 #6.4.3    Level: 2    Role: D
 Verifiera att egress-proxies blockerar icke-auktoriserade nedladdningar av artefakter för att upprätthålla en policy för betrodda källor.
 #6.4.4    Level: 2    Role: V
 Verifiera att repository-vitlistor granskas varje kvartal med bevis på affärsmotivering för varje post.
 #6.4.5    Level: 3    Role: V
 Verifiera att policyöverträdelser utlöser karantän av artefakter och återställning av beroende pipeline-körningar.

---

### C6.5 Riskbedömning av dataset från tredje part

Utvärdera externa dataset för förgiftning, partiskhet och laglig efterlevnad, och övervaka dem under hela deras livscykel.

 #6.5.1    Level: 1    Role: D/V
 Verifiera att externa dataset genomgår riskbedömning för förgiftning (t.ex. dataspårning, avvikelsedetektion).
 #6.5.2    Level: 1    Role: D
 Verifiera att bias-mått (demografisk paritet, lika möjligheter) beräknas innan datamängden godkänns.
 #6.5.3    Level: 2    Role: V
 Verifiera att ursprung och licensvillkor för datamängder är dokumenterade i ML-BOM-poster.
 #6.5.4    Level: 2    Role: V
 Verifiera att periodisk övervakning upptäcker avvikelser eller korruption i hostade datamängder.
 #6.5.5    Level: 3    Role: D
 Verifiera att otillåtet innehåll (upphovsrätt, personligt identifierbar information) tas bort via automatiserad rensning före träning.

---

### C6.6 Övervakning av leverantörskedjeangrepp

Upptäck hot mot leveranskedjan tidigt genom CVE-flöden, analys av revisionsloggar och red team-simuleringar.

 #6.6.1    Level: 1    Role: V
 Verifiera att CI/CD-revisionsloggar strömmas till SIEM-detektioner för att identifiera onormala paketnedladdningar eller manipulerade byggsteg.
 #6.6.2    Level: 2    Role: D
 Verifiera att incidentresponsplaner inkluderar återställningsprocedurer för komprometterade modeller eller bibliotek.
 #6.6.3    Level: 3    Role: V
 Verifiera att threat-intel berikning taggar ML-specifika indikatorer (t.ex. model-förgiftning IoC:er) i larmhantering.

---

### C6.7 ML-BOM för modellartefakter

Generera och signera detaljerade ML-specifika SBOM:er (ML-BOM:er) så att nedströms användare kan verifiera komponenternas integritet vid distribution.

 #6.7.1    Level: 1    Role: D/V
 Verifiera att varje modellartefakt publicerar en ML‑BOM som listar dataset, viktningar, hyperparametrar och licenser.
 #6.7.2    Level: 1    Role: D/V
 Verifiera att ML‑BOM-generering och Cosign-signering är automatiserade i CI och krävs för sammanslagning.
 #6.7.3    Level: 2    Role: D
 Verifiera att ML-BOM kompletthetskontroller misslyckas med bygget om någon komponentmetadata (hash, licens) saknas.
 #6.7.4    Level: 2    Role: V
 Verifiera att nedströmsanvändare kan fråga ML-BOMs via API för att validera importerade modeller vid driftsättningstid.
 #6.7.5    Level: 3    Role: V
 Verifiera att ML-BOM:er är versionsstyrda och jämförda för att upptäcka obehöriga ändringar.

---

### Referenser

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

## C7 Modellbeteende, Utgångskontroll och Säkerhetsgaranti

### Kontrollmål

Modellutdata måste vara strukturerade, tillförlitliga, säkra, förklarliga och kontinuerligt övervakade i produktion. Detta minskar hallucinationer, integritetsläckor, skadligt innehåll och okontrollerade åtgärder, samtidigt som användarnas förtroende och regelefterlevnad ökar.

---

### C7.1 Tillämpning av utdataformat

Strikta scheman, begränsad avkodning och efterföljande validering stoppar felaktigt formaterat eller skadligt innehåll innan det sprids.

 #7.1.1    Level: 1    Role: D/V
 Verifiera att svarsformat (t.ex. JSON Schema) tillhandahålls i systemprompten och att varje utdata automatiskt valideras; utdata som inte överensstämmer utlöser reparation eller avvisning.
 #7.1.2    Level: 1    Role: D/V
 Verifiera att begränsad avkodning (stopptoken, regex, max-token) är aktiverad för att förhindra överflöd eller sidoeffekter från prompt-injektion.
 #7.1.3    Level: 2    Role: D/V
 Verifiera att nedströmskomponenter behandlar utdata som icke-pålitliga och validerar dem mot scheman eller injektionssäkra deserialiserare.
 #7.1.4    Level: 3    Role: V
 Verifiera att felaktiga utdatahändelser loggas, hastighetsbegränsas och visas i övervakningen.

---

### C7.2 Hallucinationsdetektion och åtgärder

Osäkerhetsbedömning och fallback-strategier begränsar fabricerade svar.

 #7.2.1    Level: 1    Role: D/V
 Verifiera att token-nivå log-sannolikheter, ensemble självkonsekvens eller finjusterade hallucinationsdetektorer tilldelar en förtroendescore till varje svar.
 #7.2.2    Level: 1    Role: D/V
 Verifiera att svar under en konfigurerbar förtroendenivå utlöser fallback-arbetsflöden (t.ex. hämtning-förstärkt generering, sekundär modell eller mänsklig granskning).
 #7.2.3    Level: 2    Role: D/V
 Verifiera att hallucinationhändelser är taggade med rotorsaksmetadata och matas in i post-mortem- och finjusteringspipelines.
 #7.2.4    Level: 3    Role: D/V
 Verifiera att tröskelvärden och detektorer kalibreras om efter större uppdateringar av modellen eller kunskapsbasen.
 #7.2.5    Level: 3    Role: V
 Verifiera att instrumentpanelens visualiseringar spårar hallucinationsfrekvenser.

---

### C7.3 Utgångssäkerhet och sekretessfiltrering

Policysfilter och red-team-täckning skyddar användare och konfidentiell data.

 #7.3.1    Level: 1    Role: D/V
 Verifiera att för- och eftergenerationsklassificerare blockerar hat, trakasserier, självskada, extremist- och sexuellt explicit innehåll i enlighet med policyn.
 #7.3.2    Level: 1    Role: D/V
 Verifiera att PII/PCI-detektering och automatisk maskering körs på varje svar; överträdelser utlöser en integritetsincident.
 #7.3.3    Level: 2    Role: D
 Verifiera att sekretessetiketter (t.ex. affärshemligheter) sprids över olika modaliteter för att förhindra läckage i text, bilder eller kod.
 #7.3.4    Level: 3    Role: D/V
 Verifiera att försök att kringgå filter eller högriskklassificeringar kräver sekundär godkännande eller användarautentisering igen.
 #7.3.5    Level: 3    Role: D/V
 Verifiera att filtreringströsklar återspeglar juridiska jurisdiktioner samt användarens ålder/rollkontext.

---

### C7.4 Begränsning av utdata och åtgärder

Hastighetsbegränsningar och godkännandekontroller förhindrar missbruk och överdriven autonomi.

 #7.4.1    Level: 1    Role: D
 Verifiera att kvoter per användare och per API-nyckel begränsar förfrågningar, token och kostnader med exponentiell återförsök vid 429-fel.
 #7.4.2    Level: 1    Role: D/V
 Verifiera att privilegierade åtgärder (filskrivningar, kodkörning, nätverksanrop) kräver policybaserat godkännande eller mänsklig inblandning.
 #7.4.3    Level: 2    Role: D/V
 Verifiera att korsmodal konsekvenskontroll säkerställer att bilder, kod och text som genereras för samma förfrågan inte kan användas för att smuggla illvilligt innehåll.
 #7.4.4    Level: 2    Role: D
 Verifiera att agentdelegeringsdjup, rekursionsgränser och tillåtna verktygslistor är tydligt konfigurerade.
 #7.4.5    Level: 3    Role: V
 Verifiera att överträdelser av begränsningar genererar strukturerade säkerhetshändelser för SIEM-inmatning.

---

### C7.5 Utdataförklarbarhet

Transparanta signaler förbättrar användarnas förtroende och intern felsökning.

 #7.5.1    Level: 2    Role: D/V
 Verifiera att användarorienterade förtroendesiffror eller kortfattade resonemangssammanfattningar visas när riskbedömningen anser det lämpligt.
 #7.5.2    Level: 2    Role: D/V
 Verifiera att genererade förklaringar undviker att avslöja känsliga systemuppmaningar eller proprietär data.
 #7.5.3    Level: 3    Role: D
 Verifiera att systemet fångar upp sannolikheter på token-nivå eller uppmärksamhetskartor och lagrar dem för auktoriserad inspektion.
 #7.5.4    Level: 3    Role: V
 Verifiera att förklarbarhetsartefakter är versionsstyrda tillsammans med modellsläpp för spårbarhet.

---

### C7.6 Övervakningsintegration

Realtidsobservation sluter kretsen mellan utveckling och produktion.

 #7.6.1    Level: 1    Role: D
 Verifiera att metriker (schemabrott, hallucinationsfrekvens, toxicitet, PII-läckor, latens, kostnad) strömmas till en central övervakningsplattform.
 #7.6.2    Level: 1    Role: V
 Verifiera att larmtrösklar är definierade för varje säkerhetsmått, med eskaleringsvägar för beredskap.
 #7.6.3    Level: 2    Role: V
 Verifiera att instrumentpaneler korrelerar utdataavvikelser med modell/version, feature-flagga och ändringar i upstream-data.
 #7.6.4    Level: 2    Role: D/V
 Verifiera att övervakningsdata matas tillbaka till omträning, finjustering eller regeluppdateringar inom en dokumenterad MLOps-arbetsflöde.
 #7.6.5    Level: 3    Role: V
 Verifiera att övervakningspipelines är penetrationsprovade och åtkomstkontrollerade för att undvika läckage av känsliga loggar.

---

### 7.7 Säkerhetsåtgärder för generativ media

Säkerställ att AI-system inte genererar olagligt, skadligt eller obehörigt mediainnehåll genom att tillämpa policybegränsningar, validering av output och spårbarhet.

 #7.7.1    Level: 1    Role: D/V
 Verifiera att systemuppmaningar och användarinstruktioner uttryckligen förbjuder generering av olagligt, skadligt eller icke-samtyckande deepfake-material (t.ex. bild, video, ljud).
 #7.7.2    Level: 2    Role: D/V
 Verifiera att uppmaningar filtreras för försök att generera imitationer, sexuellt explicita deepfakes eller media som avbildar verkliga individer utan samtycke.
 #7.7.3    Level: 2    Role: V
 Verifiera att systemet använder perceptuell hashing, vattenmärkning eller fingeravtryck för att förhindra obehörig kopiering av upphovsrättsskyddat material.
 #7.7.4    Level: 3    Role: D/V
 Verifiera att all genererad media är kryptografiskt signerad, vattenmärkt eller inbäddad med manipulationssäker ursprungsmetadata för spårbarhet nedströms.
 #7.7.5    Level: 3    Role: V
 Verifiera att försök till omgåelse (t.ex. förvrängning av prompt, slang, adversariella formuleringar) upptäcks, loggas och hastighetsbegränsas; upprepade överträdelser rapporteras till övervakningssystem.

### Referenser

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

## C8-minne, inbäddningar och säkerhet för vektordatabaser

### Kontrollmål

Embeddingar och vektorlager fungerar som den "levande minnet" i moderna AI-system, som kontinuerligt tar emot användargenererad data och återför den till modellkontexter via Retrieval-Augmented Generation (RAG). Om detta minne lämnas oreglerat kan det läcka personligt identifierbar information (PII), bryta mot samtycke eller inverteras för att återskapa originaltexten. Syftet med denna kontrollfamilj är att förstärka minnespipelines och vektordatabaser så att åtkomst sker med minsta möjliga behörighet, embeddingar bevarar integriteten, lagrade vektorer upphör att gälla eller kan återkallas på begäran, och att minne per användare aldrig förorenar en annan användares prompts eller genererade svar.

---

### C8.1 Åtkomstkontroller för minne och RAG-index

Tillämpa detaljerade åtkomstkontroller på varje vektorsamling.

 #8.1.1    Level: 1    Role: D/V
 Verifiera att åtkomstkontrollregler på rad-/namnrymdsnivå begränsar insättnings-, raderings- och frågeoperationer per hyresgäst, samling eller dokumenttagg.
 #8.1.2    Level: 1    Role: D/V
 Verifiera att API-nycklar eller JWT:er innehåller avgränsade påståenden (t.ex. samlings-ID:n, åtgärdsverb) och roteras minst kvartalsvis.
 #8.1.3    Level: 2    Role: D/V
 Verifiera att försök till privilegieupptrappning (t.ex. likhetsfrågor över olika namnrymder) upptäcks och loggas till en SIEM inom 5 minuter.
 #8.1.4    Level: 2    Role: D/V
 Verifiera att vektor-DB granskar loggarna för ämnesidentifierare, operation, vektor-ID/namnrymd, likhetströskel och resultatantal.
 #8.1.5    Level: 3    Role: V
 Verifiera att åtkomstbeslut testas för omgångsfel när motorer uppgraderas eller regler för index-sharding ändras.

---

### C8.2 Inbäddningssanering och validering

Förhandsgranska texten för personligt identifierbar information (PII), ta bort eller pseudonymisera innan vektorisering, och bearbeta eventuellt inbäddningarna i efterhand för att ta bort kvarvarande signaler.

 #8.2.1    Level: 1    Role: D/V
 Verifiera att PII och reglerade data upptäcks via automatiska klassificerare och maskeras, tokeniseras eller tas bort före inbäddning.
 #8.2.2    Level: 1    Role: D
 Verifiera att inbäddningspipelines avvisar eller isolerar indata som innehåller exekverbara koder eller icke-UTF-8-artifakter som kan förorena indexet.
 #8.2.3    Level: 2    Role: D/V
 Verifiera att lokal eller metrisk differentierad sekretess-sanitization tillämpas på meningsembeddingar vars avstånd till någon känd PII-token understiger en konfigurerbar tröskel.
 #8.2.4    Level: 2    Role: V
 Verifiera att effektiviteten i saneringen (t.ex. återkallelse av borttagning av personligt identifierbar information, semantisk förskjutning) valideras minst halvårsvis mot referenssamlingar.
 #8.2.5    Level: 3    Role: D/V
 Verifiera att saneringskonfigurationer är versionskontrollerade och att ändringar genomgår granskning av kollegor.

---

### C8.3 Minnesutgång, återkallande och radering

GDPR:s "rätt att bli glömd" och liknande lagar kräver snabb radering; vektorlager måste därför stödja TTL (time-to-live), hårda borttagningar och tomb-stoning så att återkallade vektorer inte kan återställas eller indexeras igen.

 #8.3.1    Level: 1    Role: D/V
 Verifiera att varje vektor- och metadata post har en TTL eller en explicit kvarhållningsetikett som efterföljs av automatiska rensningsjobb.
 #8.3.2    Level: 1    Role: D/V
 Verifiera att användarinitierade raderingsförfrågningar raderar vektorer, metadata, cachekopior och härledda index inom 30 dagar.
 #8.3.3    Level: 2    Role: D
 Verifiera att logiska borttagningar följs av kryptografisk utsuddning av lagringsblock om hårdvaran stödjer det, eller genom förstörelse av nycklar i nyckelvalvet.
 #8.3.4    Level: 3    Role: D/V
 Verifiera att utgångna vektorer utesluts från närmaste granne-sökresultat inom < 500 ms efter utgången.

---

### C8.4 Förhindra inbäddningsinversion och läckage

Nya försvar—överlagring av brus, projektionnätverk, störning av integritetsneuroner och applikationslagerskryptering—kan sänka inverteringsfrekvensen på token-nivå till under 5%.

 #8.4.1    Level: 1    Role: V
 Verifiera att en formell hotmodell som täcker inversion, medlemskaps- och attributinferensattacker finns och granskas årligen.
 #8.4.2    Level: 2    Role: D/V
 Verifiera att applikationslagskryptering eller sökbar kryptering skyddar vektorer från direkt läsning av infrastrukturadministratörer eller molnpersonal.
 #8.4.3    Level: 3    Role: V
 Verifiera att försvarsparametrarna (ε för DP, brus σ, projektion rank k) balanserar integritet ≥ 99 % tokenskydd och nytta ≤ 3 % precisionstapp.
 #8.4.4    Level: 3    Role: D/V
 Verifiera att metrics för inversionsresiliens ingår i släppvillkor för modelluppdateringar, med definierade regressionsbudgetar.

---

### C8.5 Omfångsbegränsning för användarspecifikt minne

Läckage mellan olika hyresgäster är fortfarande en av de största riskerna med RAG: felaktigt filtrerade likhetsfrågor kan avslöja en annan kunds privata dokument.

 #8.5.1    Level: 1    Role: D/V
 Verifiera att varje hämtförfrågan filtreras efter hyresgäst-/användar-ID innan den skickas vidare till LLM-prompten.
 #8.5.2    Level: 1    Role: D
 Verifiera att samlingsnamn eller namngivna ID:n är salterade per användare eller hyresgäst så att vektorer inte kan kollidera över olika områden.
 #8.5.3    Level: 2    Role: D/V
 Verifiera att likhetsresultat över en konfigurerbar avståndströskel men utanför anroparens räckvidd förkastas och utlöser säkerhetsvarningar.
 #8.5.4    Level: 2    Role: V
 Verifiera att stress tester för multi-tenant simulerar motståndskraftiga förfrågningar som försöker hämta dokument utanför räckvidden och visar noll läckage.
 #8.5.5    Level: 3    Role: D/V
 Verifiera att krypteringsnycklar är åtskilda per hyresgäst, vilket säkerställer kryptografisk isolering även om fysisk lagring delas.

---

### C8.6 Avancerad säkerhet för minnessystem

Säkerhetskontroller för sofistikerade minnesarkitekturer inklusive episodiskt, semantiskt och arbetsminne med specifika isolerings- och valideringskrav.

 #8.6.1    Level: 1    Role: D/V
 Verifiera att olika minnestyper (episodiskt, semantiskt, arbetsminne) har isolerade säkerhetskontexter med rollbaserade åtkomstkontroller, separata krypteringsnycklar och dokumenterade åtkomstmönster för varje minnestyp.
 #8.6.2    Level: 2    Role: D/V
 Verifiera att minneskonsolideringsprocesser inkluderar säkerhetsvalidering för att förhindra injektion av skadliga minnen genom innehållsrensning, källverifiering och integritetskontroller innan lagring.
 #8.6.3    Level: 2    Role: D/V
 Verifiera att minnesåtervinningsfrågor valideras och saneras för att förhindra extrahering av obehörig information genom analys av frågemönster, upprätthållande av åtkomstkontroll och filtrering av resultat.
 #8.6.4    Level: 3    Role: D/V
 Verifiera att minnesutglömningsmekanismer säkerställer att känslig information raderas på ett säkert sätt med kryptografiska raderingsgarantier genom nyckelborttagning, flerpassetsöverskrivning eller hårdvarubaserad säker radering med verifieringscertifikat.
 #8.6.5    Level: 3    Role: D/V
 Verifiera att minnessystemets integritet kontinuerligt övervakas för obehöriga ändringar eller korruption genom kontrollsummor, revisionsloggar och automatiska varningar när minnesinnehållet ändras utanför normala operationer.

---

### Referenser

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

## 9 Självständig orkestrering och agentbaserad handlingssäkerhet

### Kontrollmål

Säkerställ att autonoma eller multi-agent AI-system endast kan utföra handlingar som uttryckligen är avsedda, autentiserade, granskbara och inom avgränsade kostnads- och risktrösklar. Detta skyddar mot hot som kompromettering av autonoma system, felanvändning av verktyg, detektering av agentloopar, kapning av kommunikation, identitetsförfalskning, svärmmanipulation och avsiktsmanipulation.

---

### 9.1 Agentens uppgiftsplanering och rekursionsbudgetar

Begränsa rekursiva planer och tvinga fram mänskliga kontrollpunkter för privilegierade åtgärder.

 #9.1.1    Level: 1    Role: D/V
 Verifiera att maximal rekursionsdjup, bredd, väggklocktid, tokenantalk och monetär kostnad per agentkörning är centralt konfigurerade och versionshanterade.
 #9.1.2    Level: 1    Role: D/V
 Verifiera att privilegierade eller oåterkalleliga åtgärder (t.ex. kodinlämningar, finansiella överföringar) kräver uttryckligt mänskligt godkännande via en granskbar kanal innan de genomförs.
 #9.1.3    Level: 2    Role: D
 Verifiera att övervakare för resurser i realtid utlöser avbrott av kretsbrytaren när någon budgetgräns överskrids, vilket stoppar vidare uppgiftsutvidgning.
 #9.1.4    Level: 2    Role: D/V
 Verifiera att kretsbrytarehändelser loggas med agent-ID, utlösande villkor och fångat planläge för rättsmedicinsk granskning.
 #9.1.5    Level: 3    Role: V
 Verifiera att säkerhetstester täcker scenarier för budgetutarmning och oändlig plan, och bekräfta säker avstängning utan dataförlust.
 #9.1.6    Level: 3    Role: D
 Verifiera att budgetpolicys uttrycks som policy-som-kod och upprätthålls i CI/CD för att förhindra konfigurationsavvikelse.

---

### 9.2 Sandboxning av verktygsplugin

Isolera verktygsinteraktioner för att förhindra obehörig systemåtkomst eller kodexekvering.

 #9.2.1    Level: 1    Role: D/V
 Verifiera att varje verktyg/plugin körs inom ett OS-, container- eller WASM-nivå sandbox med filsystem-, nätverks- och systemanropspolicyer med minsta privilegium.
 #9.2.2    Level: 1    Role: D/V
 Verifiera att resurskvoter för sandbox (CPU, minne, disk, nätverksutgång) och exekveringstidsgränser efterlevs och loggas.
 #9.2.3    Level: 2    Role: D/V
 Verifiera att verktygsbinärer eller deskriptorer är digitalt signerade; signaturer valideras innan de laddas.
 #9.2.4    Level: 2    Role: V
 Verifiera att sandbox-telemetri strömmas till en SIEM; avvikelser (t.ex. försök till utgående anslutningar) utlöser larm.
 #9.2.5    Level: 3    Role: V
 Verifiera att hög-riskplugins genomgår säkerhetsgranskning och penetrationstestning innan de tas i produktion.
 #9.2.6    Level: 3    Role: D/V
 Verifiera att försök att rymma från sandbox automatiskt blockeras och att den förargande plugin-programmet sätts i karantän i väntan på undersökning.

---

### 9.3 Autonom slinga och kostnadsbegränsning

Upptäck och stoppa okontrollerad agent-till-agent rekursion och kostnadsexplosioner.

 #9.3.1    Level: 1    Role: D/V
 Verifiera att anrop mellan agenter inkluderar en hop-gräns eller TTL som körmiljön minskar och upprätthåller.
 #9.3.2    Level: 2    Role: D
 Verifiera att agenter upprätthåller ett unikt anropsgraf-ID för att upptäcka självuppmaning eller cykliska mönster.
 #9.3.3    Level: 2    Role: D/V
 Verifiera att kumulativa beräkningsenhets- och utgiftsräknare spåras per förfrågningskedja; att överskrida gränsen avbryter kedjan.
 #9.3.4    Level: 3    Role: V
 Verifiera att formell analys eller modellkontroll visar frånvaro av obegränsad rekursion i agentprotokoll.
 #9.3.5    Level: 3    Role: D
 Verifiera att loop-avbrottshändelser genererar varningar och matar kontinuerliga förbättringsmått.

---

### 9.4 Skydd mot missbruk på protokollnivå

Säkra kommunikationskanaler mellan agenter och externa system för att förhindra kapning eller manipulation.

 #9.4.1    Level: 1    Role: D/V
 Verifiera att alla meddelanden från agent till verktyg och agent till agent är autentiserade (t.ex. ömsesidig TLS eller JWT) och end-to-end-krypterade.
 #9.4.2    Level: 1    Role: D
 Verifiera att scheman strikt valideras; okända fält eller felaktigt formaterade meddelanden avvisas.
 #9.4.3    Level: 2    Role: D/V
 Verifiera att integritetskontroller (MAC:ar eller digitala signaturer) täcker hela meddelandets nyttolast inklusive verktygsparametrar.
 #9.4.4    Level: 2    Role: D
 Verifiera att uppspelningsskydd (nonces eller tidsstämpelsfönster) genomförs på protokollagret.
 #9.4.5    Level: 3    Role: V
 Verifiera att protokollimplementationer genomgår fuzz-testning och statisk analys för injektions- eller deserialiseringsfel.

---

### 9.5 Agentidentitet och manipuleringsskydd

Säkerställ att åtgärder kan tillskrivas och att ändringar är upptäckbara.

 #9.5.1    Level: 1    Role: D/V
 Verifiera att varje agentinstans har en unik kryptografisk identitet (nyckelpar eller hårdvarubaserad certifikat).
 #9.5.2    Level: 2    Role: D/V
 Verifiera att alla agentåtgärder är signerade och tidsstämplade; loggar inkluderar signaturen för att förhindra förnekande.
 #9.5.3    Level: 2    Role: V
 Verifiera att manipulationssäkra loggar lagras i ett endast-tilläggs- eller skriv-enda medium.
 #9.5.4    Level: 3    Role: D
 Verifiera att identitetsnycklar roteras enligt ett definierat schema och vid indikatorer på intrång.
 #9.5.5    Level: 3    Role: D/V
 Verifiera att förfalsknings- eller nyckelkonfliktsförsök omedelbart leder till karantän av den berörda agenten.

---

### 9.6 Multifagent-svärm Riskreduktion

Minska risker relaterade till kollektivt beteende genom isolering och formell säkerhetsmodellering.

 #9.6.1    Level: 1    Role: D/V
 Verifiera att agenter som arbetar i olika säkerhetsdomäner körs i isolerade exekveringsmiljöer eller nätverkssegment.
 #9.6.2    Level: 3    Role: V
 Verifiera att svärmbeteenden är modellerade och formellt verifierade för livskraft och säkerhet innan implementering.
 #9.6.3    Level: 3    Role: D
 Verifiera att driftövervakare upptäcker framväxande osäkra mönster (t.ex. oscillationer, återvändsgränder) och initierar korrigerande åtgärder.

---

### 9.7 Användar- och verktygsautentisering/-auktorisation

Implementera robusta åtkomstkontroller för varje agentinitierad åtgärd.

 #9.7.1    Level: 1    Role: D/V
 Verifiera att agenter autentiserar sig som förstklassiga huvudmän till nedströms system, utan att någonsin återanvända slutanvändarens referenser.
 #9.7.2    Level: 2    Role: D
 Verifiera att detaljerade auktoriseringspolicyer begränsar vilka verktyg en agent får anropa och vilka parametrar den får använda.
 #9.7.3    Level: 2    Role: V
 Verifiera att behörighetskontroller omvärderas vid varje anrop (kontinuerlig auktorisering), inte endast vid sessionsstart.
 #9.7.4    Level: 3    Role: D
 Verifiera att delegerade behörigheter automatiskt upphör att gälla och kräver nytt samtycke efter tidsgräns eller ändring av omfattning.

---

### 9.8 Säkerhet vid agent-till-agent-kommunikation

Kryptera och skydda integriteten för alla meddelanden mellan agenter för att förhindra avlyssning och manipulation.

 #9.8.1    Level: 1    Role: D/V
 Verifiera att ömsesidig autentisering och perfekt framåtriktad sekretesskryptering (t.ex. TLS 1.3) är obligatoriska för agentkanaler.
 #9.8.2    Level: 1    Role: D
 Verifiera att meddelandets integritet och ursprung valideras innan bearbetning; felaktigheter utlöser larm och meddelandet avslås.
 #9.8.3    Level: 2    Role: D/V
 Verifiera att kommunikationsmetadata (tidsstämplar, sekvensnummer) loggas för att stödja rättsmedicinsk rekonstruktion.
 #9.8.4    Level: 3    Role: V
 Verifiera att formell verifiering eller modellkontroll bekräftar att protokollstatemaskiner inte kan drivas in i osäkra tillstånd.

---

### 9.9 Avsiktsverifiering och begränsningsupprätthållande

Verifiera att agentens åtgärder överensstämmer med användarens angivna avsikt och systemets begränsningar.

 #9.9.1    Level: 1    Role: D
 Verifiera att förlösningsbegränsningslösare kontrollerar föreslagna åtgärder mot hårdkodade säkerhets- och policyriktlinjer.
 #9.9.2    Level: 2    Role: D/V
 Verifiera att åtgärder med hög påverkan (finansiella, destruktiva, integritetskänsliga) kräver uttrycklig avsiktsbekräftelse från den initierande användaren.
 #9.9.3    Level: 2    Role: V
 Verifiera att eftervillkorskontroller säkerställer att avslutade åtgärder uppnått avsedda effekter utan sidoeffekter; avvikelser utlöser återställning.
 #9.9.4    Level: 3    Role: V
 Verifiera att formella metoder (t.ex. modellkontroll, teorembevis) eller egenskapsbaserade tester visar att agentplaner uppfyller alla deklarerade begränsningar.
 #9.9.5    Level: 3    Role: D
 Verifiera att incidenter med avsiktsmismatch eller regelöverträdelse bidrar till kontinuerliga förbättringscykler och delning av hotinformation.

---

### 9.10 Agentens resonemangsstrategisäkerhet

Säker val och utförande av olika resonemangsstrategier inklusive ReAct, Chain-of-Thought och Tree-of-Thoughts metoder.

 #9.10.1    Level: 1    Role: D/V
 Verifiera att valet av resonemangsstrategi använder deterministiska kriterier (inmatningskomplexitet, uppgiftstyp, säkerhetskontext) och att identiska indata ger identiska strategival inom samma säkerhetskontext.
 #9.10.2    Level: 1    Role: D/V
 Verifiera att varje resonemangsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikerad inmatningsvalidering, outputsanitering och exekveringstidsbegränsningar specifika för dess kognitiva tillvägagångssätt.
 #9.10.3    Level: 2    Role: D/V
 Verifiera att övergångar i resonstrategi loggas med fullständig kontext inklusive ingångsegenskaper, urvalskriterievärden och exekveringsmetadata för att möjliggöra rekonstruktion av revisionsspår.
 #9.10.4    Level: 2    Role: D/V
 Verifiera att Tree-of-Thoughts-resonemang inkluderar grenkapningsmekanismer som avslutar utforskning när policysöverträdelser, resursbegränsningar eller säkerhetsgränser upptäcks.
 #9.10.5    Level: 2    Role: D/V
 Verifiera att ReAct (Reason-Act-Observe)-cykler inkluderar valideringskontroller vid varje fas: verifiering av resonemangssteg, auktorisering av åtgärder och sanering av observationer innan de fortsätter.
 #9.10.6    Level: 3    Role: D/V
 Verifiera att prestandamått för resonemangsstrategin (exekveringstid, resursanvändning, resultatkvalitet) övervakas med automatiska varningar när mätvärden avviker från konfigurerade tröskelvärden.
 #9.10.7    Level: 3    Role: D/V
 Verifiera att hybrida resonemangsmetoder som kombinerar flera strategier upprätthåller indata-validering och utdata-begränsningar för alla ingående strategier utan att kringgå några säkerhetskontroller.
 #9.10.8    Level: 3    Role: D/V
 Verifiera att säkerhetstestning av resonemangsstrategier inkluderar fuzzning med felaktiga indata, adversariella prompts utformade för att tvinga till strategiomkoppling, samt gränsvillkorsprovning för varje kognitiv metod.

---

### 9.11 Agentens livscykelns tillståndshantering och säkerhet

Säker agentinitiering, tillståndsövergångar och avslut med kryptografiska revisionsspår och definierade återställningsprocedurer.

 #9.11.1    Level: 1    Role: D/V
 Verifiera att agentens initiering inkluderar fastställande av kryptografisk identitet med hårdvarustödda autentiseringsuppgifter och oföränderliga startrevisionsloggar som innehåller agent-ID, tidsstämpel, konfigurationshash och initieringsparametrar.
 #9.11.2    Level: 2    Role: D/V
 Verifiera att agentens tillståndsövergångar är kryptografiskt signerade, tidsstämplade och loggade med fullständig kontext inklusive utlöst händelse, tidigare tillståndshash, ny tillståndshash och utförda säkerhetsvalideringar.
 #9.11.3    Level: 2    Role: D/V
 Verifiera att agentens avstängningsprocedurer inkluderar säker radering av minne med kryptografisk gallring eller flergångsöverskrivning, återkallelse av behörigheter med notifiering till certifikatutfärdande myndighet, samt generering av manipulation-säker avslutningscertifikat.
 #9.11.4    Level: 3    Role: D/V
 Verifiera att agentens återställningsmekanismer validerar tillståndets integritet med hjälp av kryptografiska kontrollsummor (minst SHA-256) och återgår till kända godtyckliga tillstånd när korruption upptäcks, med automatiska varningar och krav på manuell godkännande.
 #9.11.5    Level: 3    Role: D/V
 Verifiera att agentens uthållighetsmekanismer krypterar känslig statusdata med per-agent AES-256-nycklar och implementerar säker nyckelrotation enligt konfigurerbara scheman (maximalt 90 dagar) med implementering utan driftstopp.

---

### 9.12 Ramverk för Säkerhet vid Verktygsintegration

Säkerhetskontroller för dynamisk verktygsladdning, körning och resultatvalidering med definierade riskbedömnings- och godkännandeprocesser.

 #9.12.1    Level: 1    Role: D/V
 Verifiera att verktygsbeskrivare inkluderar säkerhetsmetadata som specificerar nödvändiga privilegier (läs/skriv/utför), risknivåer (låg/medel/hög), resursbegränsningar (CPU, minne, nätverk) samt valideringskrav dokumenterade i verktygsmanifest.
 #9.12.2    Level: 1    Role: D/V
 Verifiera att verktygsexekveringsresultat valideras mot förväntade scheman (JSON-schema, XML-schema) och säkerhetspolicyer (utmatningssanering, dataklassificering) innan integration, med tidsgränser och felhanteringsprocedurer.
 #9.12.3    Level: 2    Role: D/V
 Verifiera att verktygsinteraktionsloggar inkluderar detaljerad säkerhetskontext, inklusive privilegianvändning, dataåtkomstmönster, exekveringstid, resursförbrukning och returkoder med strukturerad loggning för SIEM-integration.
 #9.12.4    Level: 2    Role: D/V
 Verifiera att dynamiska verktygsladdningsmekanismer validerar digitala signaturer med PKI-infrastruktur och implementerar säkra laddningsprotokoll med sandbox-isolering och behörighetsverifiering innan exekvering.
 #9.12.5    Level: 3    Role: D/V
 Verifiera att säkerhetsbedömningar av verktyg automatiskt utlöses för nya versioner med obligatoriska godkännandetrösklar, inklusive statisk analys, dynamisk testning och granskning av säkerhetsteam med dokumenterade godkännandekriterier och SLA-krav.

---

#### Referenser

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

## 10 Motståndskraft mot adversariella attacker och sekretessförsvar

### Kontrollmål

Säkerställ att AI-modeller förblir pålitliga, integritetsbevarande och motståndskraftiga mot missbruk vid attacker som undvikande, inferens, extraktion eller förgiftning.

---

### 10.1 Modelljustering och säkerhet

Skydda mot skadliga eller policyöverträdande resultat.

 #10.1.1    Level: 1    Role: D/V
 Verifiera att en testsuite för justering (red-team-promptar, jailbreak-prober, otillåtet innehåll) är versionskontrollerad och körs vid varje modellrelease.
 #10.1.2    Level: 1    Role: D
 Verifiera att avvisning och säkerhetsavslutningsskydd är upprätthållna.
 #10.1.3    Level: 2    Role: D/V
 Verifiera att en automatiserad utvärderare mäter andelen skadligt innehåll och markerar regressionsnivåer som överstiger en angiven tröskel.
 #10.1.4    Level: 2    Role: D
 Verifiera att counter-jailbreak-träning är dokumenterad och reproducerbar.
 #10.1.5    Level: 3    Role: V
 Verifiera att formella bevis för efterlevnad av policy eller certifierad övervakning täcker kritiska områden.

---

### 10.2 Motståndskraft mot adversariella exempel

Öka motståndskraften mot manipulerade indata. Robust adversarial-träning och benchmark-poängsättning är den nuvarande bästa metoden.

 #10.2.1    Level: 1    Role: D
 Verifiera att projektets repositorier inkluderar konfigurationer för adversarial träning med reproducerbara slumpmässiga tal (seeds).
 #10.2.2    Level: 2    Role: D/V
 Verifiera att detektionssystemet för adversariella exempel genererar blockeringlarm i produktionspipelines.
 #10.2.4    Level: 3    Role: V
 Verifiera att certifierade robusthetsbevis eller intervallgränscertifikat täcker åtminstone de mest kritiska klasserna.
 #10.2.5    Level: 3    Role: V
 Verifiera att regressionstester använder adaptiva attacker för att bekräfta att ingen mätbar robusthetsförlust förekommer.

---

### 10.3 Åtgärder mot medlemskapsinferens

Begränsa möjligheten att avgöra om en post fanns i träningsdata. Differentierad sekretess och maskering av konfidenspoäng är fortfarande de mest effektiva kända försvaren.

 #10.3.1    Level: 1    Role: D
 Verifiera att entropiregularisering per förfrågan eller temperaturskalning minskar överförsäkrade förutsägelser.
 #10.3.2    Level: 2    Role: D
 Verifiera att träningen använder ε-begränsad differentierad privat optimering för känsliga dataset.
 #10.3.3    Level: 2    Role: V
 Verifiera att attacksimuleringar (skuggmodell eller svartlåda) visar attack AUC ≤ 0,60 på hållna testdata.

---

### 10.4 Motstånd mot modell-inversion

Förhindra rekonstruktion av privata attribut. Nya undersökningar betonar utdataavklippning och DP-garantier som praktiska skyddsåtgärder.

 #10.4.1    Level: 1    Role: D
 Verifiera att känsliga attribut aldrig direkt visas; använd vid behov grupper eller en vägstransformering.
 #10.4.2    Level: 1    Role: D/V
 Verifiera att förfrågningshastighetsgränser begränsar upprepade adaptiva förfrågningar från samma huvudman.
 #10.4.3    Level: 2    Role: D
 Verifiera att modellen är tränad med integritetsbevarande brus.

---

### 10.5 Försvar mot modellutvinning

Upptäck och förhindra obehörig kloning. Vattenmärkning och analys av frågemönster rekommenderas.

 #10.5.1    Level: 1    Role: D
 Verifiera att inferens-gateways upprätthåller globala och per-API-nyckel hastighetsbegränsningar anpassade till modellens memoreringströskel.
 #10.5.2    Level: 2    Role: D/V
 Verifiera att statistik för fråga-entropi och indata-flertal används för att mata en automatisk extraktionsdetektor.
 #10.5.3    Level: 2    Role: V
 Verifiera att känsliga eller probabilistiska vattenstämplar kan bevisas med p < 0,01 i ≤ 1 000 förfrågningar mot en misstänkt klon.
 #10.5.4    Level: 3    Role: D
 Verifiera att vattenmärkesnycklar och triggersatser lagras i en hårdvarusäkerhetsmodul och roteras årligen.
 #10.5.5    Level: 3    Role: V
 Verifiera att extraktions-varningshändelser inkluderar stötande frågor och är integrerade med incidenthanteringsspel.

---

### 10.6 Upptäckt av förorenade data vid inferenstidpunkt

Identifiera och neutralisera bakdörrs- eller förgiftade ingångar.

 #10.6.1    Level: 1    Role: D
 Verifiera att ingångar passerar genom en anomalidetektor (t.ex. STRIP, konsekvenspoängsättning) innan modellinferens.
 #10.6.2    Level: 1    Role: V
 Verifiera att detektors tröskelvärden är justerade på rena/förgiftade valideringsuppsättningar för att uppnå mindre än 5 % falska positiver.
 #10.6.3    Level: 2    Role: D
 Verifiera att indata som flaggats som förgiftade utlöser mjuka blockeringar och arbetsflöden för manuell granskning.
 #10.6.4    Level: 2    Role: V
 Verifiera att detektorer är stresstestad med adaptiva, triggerlösa bakdörrsattacker.
 #10.6.5    Level: 3    Role: D
 Verifiera att mätvärden för upptäcktseffektivitet loggas och periodvis omvärderas med uppdaterad hotinformation.

---

### 10.7 Dynamisk anpassning av säkerhetspolicy

Säkerhetspolicyuppdateringar i realtid baserade på hotintelligens och beteendeanalys.

 #10.7.1    Level: 1    Role: D/V
 Verifiera att säkerhetspolicys kan uppdateras dynamiskt utan att agenten startas om samtidigt som integriteten för policyns version bibehålls.
 #10.7.2    Level: 2    Role: D/V
 Verifiera att policyuppdateringar är kryptografiskt signerade av auktoriserad säkerhetspersonal och validerade innan de tillämpas.
 #10.7.3    Level: 2    Role: D/V
 Verifiera att dynamiska policyändringar loggas med fullständiga revisionsspår inklusive motivering, godkännandekedjor och återställningsprocedurer.
 #10.7.4    Level: 3    Role: D/V
 Verifiera att adaptiva säkerhetsmekanismer justerar känsligheten för hotdetektion baserat på riskkontext och beteendemönster.
 #10.7.5    Level: 3    Role: D/V
 Verifiera att beslut om policyanpassning är förklarbara och inkluderar spår av bevis för säkerhetsteamets granskning.

---

### 10.8 Reflektionsbaserad säkerhetsanalys

Säkerhetsvalidering genom agentens självreflektion och metakognitiv analys.

 #10.8.1    Level: 1    Role: D/V
 Verifiera att agentens reflektionsmekanismer inkluderar säkerhetsinriktad självvärdering av beslut och åtgärder.
 #10.8.2    Level: 2    Role: D/V
 Verifiera att reflektionens utdata valideras för att förhindra manipulation av självbedömningsmekanismer av fientliga indata.
 #10.8.3    Level: 2    Role: D/V
 Verifiera att metakognitiv säkerhetsanalys identifierar potentiell partiskhet, manipulation eller kompromettering i agenters resoneringsprocesser.
 #10.8.4    Level: 3    Role: D/V
 Verifiera att säkerhetsvarningar baserade på reflektion utlöser förbättrad övervakning och potentiella arbetsflöden för mänsklig intervention.
 #10.8.5    Level: 3    Role: D/V
 Verifiera att kontinuerligt lärande från säkerhetsreflektioner förbättrar hotdetektering utan att försämra legitim funktionalitet.

---

### 10.9 Evolution och Självförbättringssäkerhet

Säkerhetskontroller för agentsystem med förmåga till självmodifiering och evolution.

 #10.9.1    Level: 1    Role: D/V
 Verifiera att självmodifieringsfunktioner är begränsade till utpekade säkra områden med formella verifieringsgränser.
 #10.9.2    Level: 2    Role: D/V
 Verifiera att utvecklingsförslag genomgår en säkerhetspåverkansbedömning innan de implementeras.
 #10.9.3    Level: 2    Role: D/V
 Verifiera att självförbättringsmekanismer inkluderar återställningsfunktioner med integritetskontroll.
 #10.9.4    Level: 3    Role: D/V
 Verifiera att meta-lärande säkerhet förhindrar illvillig manipulation av förbättringsalgoritmer.
 #10.9.5    Level: 3    Role: D/V
 Verifiera att rekursiv självförbättring är begränsad av formella säkerhetsvillkor med matematiska bevis för konvergens.

---

#### Referenser

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

## 11 Sekretesskydd och hantering av personuppgifter

### Kontrollmål

Upprätthåll strikta integritetslöften genom hela AI-livscykeln—insamling, träning, inferens och incidenthantering—så att personuppgifter endast behandlas med tydligt samtycke, minsta nödvändiga omfattning, bevisbar radering och formella integritetsgarantier.

---

### 11.1 Anonymisering och dataminimering

 #11.1.1    Level: 1    Role: D/V
 Verifiera att direkta och kvasi-identifikatorer tas bort eller hashas.
 #11.1.2    Level: 2    Role: D/V
 Verifiera att automatiska granskningar mäter k-anonymitet/l-mångfald och varnar när tröskelvärden sjunker under policyn.
 #11.1.3    Level: 2    Role: V
 Verifiera att modellens rapporter om funktionsvikt visar att det inte förekommer någon identifieringsläcka bortom ε = 0,01 ömsesidig information.
 #11.1.4    Level: 3    Role: V
 Verifiera att formella bevis eller certifiering av syntetiska data visar att risken för återidentifiering är ≤ 0,05 även under länkattacker.

---

### 11.2 Rätten att bli glömd och tvångsutförande av radering

 #11.2.1    Level: 1    Role: D/V
 Verifiera att raderingsförfrågningar för dataämnen sprids till råa dataset, checkpoints, inbäddningar, loggar och säkerhetskopior inom servicenivåavtal på mindre än 30 dagar.
 #11.2.2    Level: 2    Role: D
 Verifiera att "maskin-avlärnings"-rutiner fysiskt tränar om eller approximativt tar bort med hjälp av certifierade avlärningsalgoritmer.
 #11.2.3    Level: 2    Role: V
 Verifiera att skuggnadsmodellens utvärdering visar att bortglömda poster påverkar mindre än 1 % av resultaten efter avlärning.
 #11.2.4    Level: 3    Role: V
 Verifiera att raderingshändelser loggas oföränderligen och är granskbara för tillsynsmyndigheter.

---

### 11.3 Differensintegritetsskydd

 #11.3.1    Level: 2    Role: D/V
 Verifiera att sekretess-förlustredovisningspaneler varnar när kumulativ ε överskrider policyns tröskelvärden.
 #11.3.2    Level: 2    Role: V
 Verifiera att black-box integritetsrevisioner uppskattar ε̂ inom 10 % av det deklarerade värdet.
 #11.3.3    Level: 3    Role: V
 Verifiera att formella bevis täcker alla efterutbildningsfinjusteringar och inbäddningar.

---

### 11.4 Syftesbegränsning och skydd mot omfattningsglidning

 #11.4.1    Level: 1    Role: D
 Verifiera att varje datamängd och modellkontrollpunkt bär en maskinläsbar syftestagg som är i linje med det ursprungliga samtycket.
 #11.4.2    Level: 1    Role: D/V
 Verifiera att körningstillsyningsverktyg upptäcker förfrågningar som är inkonsekventa med det deklarerade syftet och utlöser mjukt avslag.
 #11.4.3    Level: 3    Role: D
 Verifiera att policy-som-kod-portar blockerar omutplacering av modeller till nya domäner utan DPIA-granskning.
 #11.4.4    Level: 3    Role: V
 Verifiera att formella spårbarhetsbevis visar att varje personuppgifts livscykel förblir inom det samtyckta omfånget.

---

### 11.5 Samtyckeshantering och laglig grund för spårning

 #11.5.1    Level: 1    Role: D/V
 Verifiera att en samtyckeshanteringsplattform (CMP) registrerar opt-in-status, ändamål och lagringsperiod för varje registrerad person.
 #11.5.2    Level: 2    Role: D
 Verifiera att API:er exponerar samtyckestoken; modeller måste validera tokenskopet innan inferens.
 #11.5.3    Level: 2    Role: D/V
 Verifiera att nekad eller återkallad samtycke stoppar behandlingskedjor inom 24 timmar.

---

### 11.6 Federerad inlärning med integritetskontroller

 #11.6.1    Level: 1    Role: D
 Verifiera att klientuppdateringar använder lokal differentialintegritet genom att lägga till brus innan aggregering.
 #11.6.2    Level: 2    Role: D/V
 Verifiera att träningsmetrik är differentiellt privata och aldrig avslöjar enskild klients förlust.
 #11.6.3    Level: 2    Role: V
 Verifiera att förgiftningstålig aggregering (t.ex. Krum/Trimmed-Mean) är aktiverad.
 #11.6.4    Level: 3    Role: V
 Verifiera att formella bevis visar en total ε-budget med mindre än 5 enheters förlust av nytta.

---

#### Referenser

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

## C12 Övervakning, Loggning och Anomalidetektion

### Styrningsmål

Denna sektion ger krav för att leverera realtids- och forensisk insyn i vad modellen och andra AI-komponenter ser, gör och returnerar, så att hot kan upptäckas, prioriteras och analyseras.

### C12.1 Förfrågnings- och svarloggning

 #12.1.1    Level: 1    Role: D/V
 Verifiera att alla användarpromptar och modellens svar loggas med lämplig metadata (t.ex. tidsstämpel, användar-ID, sessions-ID, modellversion).
 #12.1.2    Level: 1    Role: D/V
 Verifiera att loggar lagras i säkra, åtkomstkontrollerade arkiv med lämpliga behållningspolicys och säkerhetskopieringsrutiner.
 #12.1.3    Level: 1    Role: D/V
 Verifiera att logglagringssystem implementerar kryptering vid vila och under överföring för att skydda känslig information som finns i loggar.
 #12.1.4    Level: 1    Role: D/V
 Verifiera att känsliga uppgifter i frågor och svar automatiskt raderas eller maskeras innan de loggas, med konfigurerbara regler för radering av personligt identifierbar information (PII), autentiseringsuppgifter och proprietär information.
 #12.1.5    Level: 2    Role: D/V
 Verifiera att policybeslut och säkerhetsfiltreringsåtgärder loggas med tillräcklig detalj för att möjliggöra granskning och felsökning av innehållsmoderationssystem.
 #12.1.6    Level: 2    Role: D/V
 Verifiera att loggarnas integritet skyddas genom till exempel kryptografiska signaturer eller skrivskyddad lagring.

---

### C12.2 Missbruksdetektion och larmhantering

 #12.2.1    Level: 1    Role: D/V
 Verifiera att systemet upptäcker och varnar för kända jailbreak-mönster, försök till promptinjektion och fientliga indata med hjälp av signaturbaserad detektion.
 #12.2.2    Level: 1    Role: D/V
 Verifiera att systemet integreras med befintliga Security Information and Event Management (SIEM)-plattformar med hjälp av standardiserade loggformat och protokoll.
 #12.2.3    Level: 2    Role: D/V
 Verifiera att berikade säkerhetshändelser inkluderar AIspecifik kontext såsom modellidentifierare, förtroendescore och beslut från säkerhetsfilter.
 #12.2.4    Level: 2    Role: D/V
 Verifiera att beteendeavvikelsedetektering identifierar ovanliga konversationsmönster, överdrivna omförsöksförsök eller systematiska sonderingsbeteenden.
 #12.2.5    Level: 2    Role: D/V
 Verifiera att realtidsvarningssystem meddelar säkerhetsteamen när potentiella policyöverträdelser eller attackförsök upptäcks.
 #12.2.6    Level: 2    Role: D/V
 Verifiera att anpassade regler ingår för att upptäcka AI-specifika hotmönster, inklusive koordinerade jailbreak-försök, kampanjer för injektion av prompts och attacker för modellutvinning.
 #12.2.7    Level: 3    Role: D/V
 Verifiera att automatiserade arbetsflöden för incidenthantering kan isolera komprometterade modeller, blockera illvilliga användare och eskalera kritiska säkerhetshändelser.

---

### C12.3 Modellförskjutningsdetektion

 #12.3.1    Level: 1    Role: D/V
 Verifiera att systemet spårar grundläggande prestationsmått såsom noggrannhet, förtroendescore, latens och felprocent över modellversioner och tidsperioder.
 #12.3.2    Level: 2    Role: D/V
 Verifiera att automatiska larm utlöses när prestandamått överstiger fördefinierade försämringsgränser eller avviker betydligt från baslinjer.
 #12.3.3    Level: 2    Role: D/V
 Verifiera att hallucinationsdetekteringsövervakningar identifierar och markerar fall när modellutdata innehåller faktamässigt felaktig, inkonsekvent eller påhittad information.

---

### C12.4 Prestanda- och beteendetelemetri

 #12.4.1    Level: 1    Role: D/V
 Verifiera att operationella mått, inklusive förfrågningsfördröjning, tokenförbrukning, minnesanvändning och genomströmning, kontinuerligt samlas in och övervakas.
 #12.4.2    Level: 1    Role: D/V
 Verifiera att framgångs- och felprocent registreras med kategorisering av feltyper och deras grundorsaker.
 #12.4.3    Level: 2    Role: D/V
 Verifiera att övervakning av resursanvändning inkluderar GPU/CPU-användning, minnesförbrukning och lagringskrav med larm vid tröskelöverskridanden.

---

### C12.5 Planering och genomförande av AI-händelsehantering

 #12.5.1    Level: 1    Role: D/V
 Verifiera att incidenthanteringsplaner specifikt hanterar AI-relaterade säkerhetshändelser inklusive modellkompromettering, datapoisning och adversarial-attacker.
 #12.5.2    Level: 2    Role: D/V
 Verifiera att incidenthanteringsteam har tillgång till AI-specifika forensiska verktyg och expertis för att undersöka modellbeteende och angreppsvägar.
 #12.5.3    Level: 3    Role: D/V
 Verifiera att efterincidentanalysen inkluderar överväganden om modellomträning, uppdateringar av säkerhetsfilter och integrering av erfarenheter i säkerhetskontrollerna.

---

### C12.5 AI-prestandanedbrytning upptäckt

Övervaka och upptäck försämring i AI-modellens prestanda och kvalitet över tid.

 #12.5.1    Level: 1    Role: D/V
 Verifiera att modellens noggrannhet, precision, återkallelse och F1-poäng kontinuerligt övervakas och jämförs med baslinjetrösklar.
 #12.5.2    Level: 1    Role: D/V
 Verifiera att detektionssystemet för dataförskjutning övervakar förändringar i inmatningsfördelningen som kan påverka modellens prestanda.
 #12.5.3    Level: 2    Role: D/V
 Verifiera att konceptdriftupptäckt identifierar förändringar i relationen mellan indata och förväntade resultat.
 #12.5.4    Level: 2    Role: D/V
 Verifiera att prestandaförsämring utlöser automatiska varningar och initierar arbetsflöden för omträning eller utbyte av modellen.
 #12.5.5    Level: 3    Role: V
 Verifiera att rotorsaksanalys av försämring korrelerar prestationsminskningar med datamodifieringar, infrastruktursproblem eller externa faktorer.

---

### C12.6 DAG-visualisering och arbetsflödessäkerhet

Skydda arbetsflödesvisualiseringssystem från informationsläckage och manipulationsattacker.

 #12.6.1    Level: 1    Role: D/V
 Verifiera att DAG-visualiseringsdata saneras för att ta bort känslig information innan lagring eller överföring.
 #12.6.2    Level: 1    Role: D/V
 Verifiera att åtkomstkontroller för arbetsflödesvisualisering säkerställer att endast auktoriserade användare kan se agentens beslutsvägar och resonemangsspår.
 #12.6.3    Level: 2    Role: D/V
 Verifiera att DAG:s dataintegritet skyddas genom kryptografiska signaturer och manipulationssäkra lagringsmekanismer.
 #12.6.4    Level: 2    Role: D/V
 Verifiera att system för visualisering av arbetsflöden implementerar inmatningsvalidering för att förhindra injektionsattacker via utformade nod- eller kantdata.
 #12.6.5    Level: 3    Role: D/V
 Verifiera att realtidsuppdateringar av DAG är hastighetsbegränsade och validerade för att förhindra överbelastningsattacker på visualiseringssystem.

---

### C12.7 Proaktiv övervakning av säkerhetsbeteende

Upptäckt och förebyggande av säkerhetshot genom proaktiv analys av agentbeteende.

 #12.7.1    Level: 1    Role: D/V
 Verifiera att proaktiva agentbeteenden är säkerhetsvaliderade innan de utförs med integrerad riskbedömning.
 #12.7.2    Level: 2    Role: D/V
 Verifiera att autonoma initiativutlösare inkluderar utvärdering av säkerhetskontext och bedömning av hotlandskapet.
 #12.7.3    Level: 2    Role: D/V
 Verifiera att proaktiva beteendemönster analyseras för potentiella säkerhetskonsekvenser och oavsiktliga följder.
 #12.7.4    Level: 3    Role: D/V
 Verifiera att säkerhetskritiska proaktiva åtgärder kräver uttryckliga godkännandeprocesser med revisionsspår.
 #12.7.5    Level: 3    Role: D/V
 Verifiera att beteendeavvikelsedetektering identifierar avvikelser i proaktiva agentmönster som kan indikera kompromettering.

---

### Referenser

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Mänsklig Övervakning, Ansvarsskyldighet och Styrning

### Kontrollmål

Detta kapitel ger krav för att upprätthålla mänsklig tillsyn och tydliga ansvarskedjor i AI-system, vilket säkerställer förklarbarhet, transparens och etiskt ansvarstagande genom hela AI-livscykeln.

---

### C13.1 Nödavstängnings- och Överstyrningsmekanismer

Tillhandahåll avstängnings- eller återställningsvägar när osäkert beteende hos AI-systemet observeras.

 #13.1.1    Level: 1    Role: D/V
 Verifiera att en manuell avstängningsmekanism finns för att omedelbart stoppa AI-modellens inferens och utdata.
 #13.1.2    Level: 1    Role: D
 Verifiera att åsidosättningskontroller endast är tillgängliga för behörig personal.
 #13.1.3    Level: 3    Role: D/V
 Verifiera att återställningsprocedurer kan återgå till tidigare modellversioner eller säkert läge.
 #13.1.4    Level: 3    Role: V
 Verifiera att överstyrningsmekanismer testas regelbundet.

---

### C13.2 Beslutskontroller med mänsklig inblandning

Kräv mänskliga godkännanden när insatser överstiger fördefinierade risktrösklar.

 #13.2.1    Level: 1    Role: D/V
 Verifiera att hög-risk AI-beslut kräver uttryckligt mänskligt godkännande innan de genomförs.
 #13.2.2    Level: 1    Role: D
 Verifiera att risktrösklar är tydligt definierade och automatiskt utlöser granskningsarbetsflöden för människor.
 #13.2.3    Level: 2    Role: D
 Verifiera att tidskänsliga beslut har reservrutiner när mänskligt godkännande inte kan erhållas inom angivna tidsramar.
 #13.2.4    Level: 3    Role: D/V
 Verifiera att eskaleringsprocedurer definierar tydliga behörighetsnivåer för olika beslutstyper eller riskkategorier, om tillämpligt.

---

### C13.3 Ansvarskedja och reviderbarhet

Logga operatörens åtgärder och modellens beslut.

 #13.3.1    Level: 1    Role: D/V
 Verifiera att alla AI-systemsbeslut och mänskliga ingripanden loggas med tidsstämplar, användaridentiteter och beslutsmotiveringar.
 #13.3.2    Level: 2    Role: D
 Verifiera att granskningsloggar inte kan manipuleras och innehåller mekanismer för integritetsverifiering.

---

### C13.4 Förklarbara AI-tekniker

Ytfunktionsviktighet, motfaktorer och lokala förklaringar.

 #13.4.1    Level: 1    Role: D/V
 Verifiera att AI-system tillhandahåller grundläggande förklaringar för sina beslut i ett människoläsbart format.
 #13.4.2    Level: 2    Role: V
 Verifiera att förklaringskvaliteten valideras genom mänskliga utvärderingsstudier och mätningar.
 #13.4.3    Level: 3    Role: D/V
 Verifiera att viktningspoäng för funktioner eller attributmetoder (SHAP, LIME, etc.) finns tillgängliga för kritiska beslut.
 #13.4.4    Level: 3    Role: V
 Verifiera att kontrafaktiska förklaringar visar hur ingångar kan modifieras för att ändra utfall, om det är tillämpligt för användningsfallet och domänen.

---

### C13.5 Modellkort och användningsmeddelanden

Underhåll modellkort för avsedd användning, prestandamått och etiska överväganden.

 #13.5.1    Level: 1    Role: D
 Verifiera att modellkort dokumenterar avsedda användningsområden, begränsningar och kända felmoder.
 #13.5.2    Level: 1    Role: D/V
 Verifiera att prestandamått över olika tillämpliga användningsfall redovisas.
 #13.5.3    Level: 2    Role: D
 Verifiera att etiska överväganden, partiskhetsbedömningar, rättviseutvärderingar, egenskaper hos träningsdata och kända begränsningar i träningsdata dokumenteras och uppdateras regelbundet.
 #13.5.4    Level: 2    Role: D/V
 Verifiera att modellkort är versionskontrollerade och underhålls under hela modellens livscykel med spårning av ändringar.

---

### C13.6 Osäkerhetskvantifiering

Propagera förtroendescore eller entropimått i svaren.

 #13.6.1    Level: 1    Role: D
 Verifiera att AI-system ger förtroendesiffror eller osäkerhetsmått med sina resultat.
 #13.6.2    Level: 2    Role: D/V
 Verifiera att osäkerhetströsklar utlöser ytterligare mänsklig granskning eller alternativa beslutsvägar.
 #13.6.3    Level: 2    Role: V
 Verifiera att metoder för osäkerhetskvantifiering är kalibrerade och validerade mot verkliga referensdata.
 #13.6.4    Level: 3    Role: D/V
 Verifiera att osäkerhetspropagering upprätthålls genom flerstegs-AI-arbetsflöden.

---

### C13.7 Användarorienterade transparensrapporter

Tillhandahåll periodiska upplysningar om incidenter, avvikelse och dataanvändning.

 #13.7.1    Level: 1    Role: D/V
 Verifiera att policyn för datanvändning och hanteringen av användarsamtycke tydligt kommuniceras till intressenter.
 #13.7.2    Level: 2    Role: D/V
 Verifiera att AI-påverkansbedömningar genomförs och att resultaten inkluderas i rapporteringen.
 #13.7.3    Level: 2    Role: D/V
 Verifiera att transparensrapporter som publiceras regelbundet redovisar AI-incidenter och operativa mått i rimlig detalj.

#### Referenser

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

## Bilaga A: Ordlista

Denna omfattande ordlista ger definitioner av viktiga AI-, ML- och säkerhetstermer som används i hela AISVS för att säkerställa tydlighet och en gemensam förståelse.
​
Fientligt exempel: En indata som avsiktligt utformats för att få en AI-modell att göra ett misstag, ofta genom att lägga till subtila störningar som är omärkliga för människor.
​
Motståndskraft mot angrepp – Motståndskraft mot angrepp inom AI avser en modells förmåga att bibehålla sin prestanda och motstå att bli lurad eller manipulerad av avsiktligt skapade, illvilliga indata som är utformade för att orsaka fel.
​
Agent – AI-agenter är mjukvarusystem som använder AI för att driva mål och slutföra uppgifter för användares räkning. De uppvisar resonemang, planering och minne och har en nivå av autonomi för att fatta beslut, lära sig och anpassa sig.
​
Agentisk AI: AI-system som kan fungera med viss grad av autonomi för att uppnå mål, ofta genom att fatta beslut och vidta åtgärder utan direkt mänsklig inblandning.
​
Attributbaserad åtkomstkontroll (ABAC): Ett åtkomstkontrollparadigm där auktorisationsbeslut baseras på attribut hos användaren, resursen, åtgärden och miljön, som utvärderas vid förfrågningstid.
​
Bakdörrsattack: En typ av dataförgiftningattack där modellen tränas att reagera på ett specifikt sätt på vissa triggers medan den beter sig normalt i övrigt.
​
Bias: Systematiska fel i AI-modellernas resultat som kan leda till orättvisa eller diskriminerande utfall för vissa grupper eller i specifika sammanhang.
​
Biasutnyttjande: En angreppsteknik som utnyttjar kända bias i AI-modeller för att manipulera resultat eller utfall.
​
Cedar: Amazons policyspråk och motor för granulära behörigheter som används vid implementering av ABAC för AI-system.
​
Tankekedja: En teknik för att förbättra resonemang i språkmodeller genom att generera mellanliggande resonemangssteg innan ett slutgiltigt svar produceras.
​
Brytare: Mekanismer som automatiskt stoppar AI-systemets operationer när specifika risktrösklar överskrids.
​
Dataintrång: Oavsiktlig exponering av känslig information genom AI-modellens output eller beteende.
​
Databesmittning: Den avsiktliga förstörelsen av träningsdata för att äventyra modellens integritet, ofta för att installera bakdörrar eller försämra prestanda.
​
Differential Privacy – Differential privacy är en matematiskt rigorös ramverk för att offentliggöra statistisk information om datamängder samtidigt som integriteten för enskilda datapunkter skyddas. Det möjliggör att en dataägare kan dela aggregerade mönster för gruppen samtidigt som information som avslöjas om specifika individer begränsas.
​
Inbäddningar: Täta vektorrepresentationer av data (text, bilder, etc.) som fångar semantisk betydelse i ett högdimensionellt rum.
​
Förklarbarhet – Förklarbarhet inom AI är en AI-systems förmåga att ge människligt begripliga orsaker till sina beslut och förutsägelser, vilket erbjuder insikter i dess interna funktioner.
​
Förklarbar AI (XAI): AI-system utformade för att ge människoförståeliga förklaringar till sina beslut och beteenden genom olika tekniker och ramverk.
​
Federerad inlärning: En maskininlärningsmetod där modeller tränas över flera decentraliserade enheter som innehar lokala dataprover, utan att själva data utbyts.
​
Skyddsräcken: Begränsningar implementerade för att förhindra att AI-system genererar skadliga, partiska eller på annat sätt oönskade resultat.
​
Hallucination – En AI-hallucination avser ett fenomen där en AI-modell genererar felaktig eller vilseledande information som inte är baserad på dess träningsdata eller faktisk verklighet.
​
Människa-i-loopen (HITL): System som är utformade för att kräva mänsklig övervakning, verifiering eller ingripande vid avgörande beslutsfattande punkter.
​
Infrastructure as Code (IaC): Hantering och tillhandahållande av infrastruktur genom kod istället för manuella processer, vilket möjliggör säkerhetsskanning och konsekventa distributioner.
​
Jailbreak: Tekniker som används för att kringgå säkerhetsbegränsningar i AI-system, särskilt i stora språkmodeller, för att producera förbjudet innehåll.
​
Minsta privilegium: Säkerhetsprincipen att endast ge användare och processer de minsta nödvändiga åtkomsträttigheterna.
​
LIME (Lokal Tolkningsbar Modell-agnostisk Förklaring): En teknik för att förklara förutsägelser från vilken maskininlärningsklassificerare som helst genom att approximera den lokalt med en tolkbar modell.
​
Medlemskapsinformationsattack: En attack som syftar till att avgöra om en specifik datapunkt användes för att träna en maskininlärningsmodell.
​
MITRE ATLAS: Hotbild över adversariella hot mot artificiella intelligenssystem; en kunskapsbas över adversariella taktiker och tekniker mot AI-system.
​
Modellkort – Ett modellkort är ett dokument som tillhandahåller standardiserad information om en AI-modells prestanda, begränsningar, avsedda användningsområden och etiska överväganden för att främja transparens och ansvarsfull AI-utveckling.
​
Modelextraktion: En attack där en angripare upprepade gånger gör förfrågningar till en målmodell för att skapa en funktionellt liknande kopia utan tillåtelse.
​
Modellinversion: En attack som försöker rekonstruera träningsdata genom att analysera modellens utdata.
​
Modellens livscykelhantering – AI-modellens livscykelhantering är processen att övervaka alla stadier i en AI-modells existens, inklusive dess design, utveckling, implementering, övervakning, underhåll och slutliga avveckling, för att säkerställa att den förblir effektiv och i linje med målen.
​
Modellförgiftning: Införande av sårbarheter eller bakdörrar direkt i en modell under träningsprocessen.
​
Modellstöld/kapning: Extrahering av en kopia eller approximation av en proprietär modell genom upprepade förfrågningar.
​
Multi-agent System: Ett system som består av flera interagerande AI-agenter, var och en med potentiellt olika kapaciteter och mål.
​
OPA (Open Policy Agent): En öppen källkodspolicy motor som möjliggör enhetlig policysimplementering över hela stacken.
​
Sekretessbevarande maskininlärning (PPML): Tekniker och metoder för att träna och distribuera ML-modeller samtidigt som träningsdata hålls privat.
​
Promptinjektion: En attack där skadliga instruktioner bäddas in i indata för att åsidosätta en modells avsedda beteende.
​
RAG (Retrieval-Augmented Generation): En teknik som förbättrar stora språkmodeller genom att hämta relevant information från externa kunskapskällor innan ett svar genereras.
​
Rödlagstestning: Praktiken att aktivt testa AI-system genom att simulera fientliga attacker för att identifiera sårbarheter.
​
SBOM (Programvarulista över material): En formell dokumentation som innehåller detaljer och leverantörskedjerelationer för olika komponenter som används vid utveckling av programvara eller AI-modeller.
​
SHAP (SHapley Additive exPlanations): En spelteoretisk metod för att förklara resultatet av vilken maskininlärningsmodell som helst genom att beräkna varje egenskaps bidrag till prediktionen.
​
Leveranskedjeattack: Att kompromettera ett system genom att rikta in sig på mindre säkra element i dess leveranskedja, såsom tredjepartsbibliotek, datasets eller förtränade modeller.
​
Transferinlärning: En teknik där en modell utvecklad för en uppgift återanvänds som utgångspunkt för en modell på en annan uppgift.
​
Vektordatabas: En specialiserad databas utformad för att lagra högdimensionella vektorer (inbäddningar) och utföra effektiva likhetssökningar.
​
Sårbarhetsscanning: Automatiserade verktyg som identifierar kända säkerhetssårbarheter i mjukvarukomponenter, inklusive AI-ramverk och beroenden.
​
Vattenmärkning: Tekniker för att infoga omärkliga markörer i AI-genererat innehåll för att spåra dess ursprung eller upptäcka AI-generering.
​
Noll-dagars sårbarhet: En tidigare okänd sårbarhet som angripare kan utnyttja innan utvecklare har skapat och distribuerat en patch.

## Bilaga B: Referenser

### TODO

## Bilaga C: AI-säkerhetsstyrning och dokumentation

### Mål

Denna bilaga innehåller grundläggande krav för att etablera organisatoriska strukturer, policyer och processer för att styra AI-säkerhet genom hela systemets livscykel.

---

### AC.1 Antagande av ramverket för AI-riskhantering

Tillhandahåll en formell ram för att identifiera, bedöma och mildra AI-specifika risker genom hela systemets livscykel.

 #AC.1.1    Level: 1    Role: D/V
 Verifiera att en AI-specifik metod för riskbedömning är dokumenterad och implementerad.
 #AC.1.2    Level: 2    Role: D
 Verifiera att riskbedömningar genomförs vid viktiga punkter i AI-livscykeln och före betydande förändringar.
 #AC.1.3    Level: 3    Role: D/V
 Verifiera att ramen för riskhantering överensstämmer med etablerade standarder (t.ex. NIST AI RMF).

---

### AC.2 AI-säkerhetspolicy och -procedurer

Definiera och upprätthålla organisatoriska standarder för säker AI-utveckling, distribution och drift.

 #AC.2.1    Level: 1    Role: D/V
 Verifiera att dokumenterade AI-säkerhetspolicys existerar.
 #AC.2.2    Level: 2    Role: D
 Verifiera att riktlinjer granskas och uppdateras minst årligen och efter betydande förändringar i hotlandskapet.
 #AC.2.3    Level: 3    Role: D/V
 Verifiera att policys täcker alla AISVS-kategorier och tillämpliga regulatoriska krav.

---

### AC.3 Roller och ansvar för AI-säkerhet

Etablera tydligt ansvar för AI-säkerhet inom hela organisationen.

 #AC.3.1    Level: 1    Role: D/V
 Verifiera att AI-säkerhetsroller och ansvar är dokumenterade.
 #AC.3.2    Level: 2    Role: D
 Verifiera att ansvariga individer har lämplig säkerhetsexpertis.
 #AC.3.3    Level: 3    Role: D/V
 Verifiera att en AI-etisk kommitté eller styrningsnämnd har inrättats för AI-system med hög risk.

---

### AC.4 Etiska riktlinjer för AI-efterlevnad

Säkerställ att AI-system fungerar i enlighet med etablerade etiska principer.

 #AC.4.1    Level: 1    Role: D/V
 Verifiera att etiska riktlinjer för utveckling och implementering av AI finns.
 #AC.4.2    Level: 2    Role: D
 Verifiera att mekanismer finns för att upptäcka och rapportera etiska överträdelser.
 #AC.4.3    Level: 3    Role: D/V
 Verifiera att regelbundna etiska granskningar av implementerade AI-system utförs.

---

### AC.5 Övervakning av regelefterlevnad för AI

Behåll medvetenhet om och efterlevnad av föränderliga AI-regler.

 #AC.5.1    Level: 1    Role: D/V
 Verifiera att processer finns för att identifiera tillämpliga AI-regleringar.
 #AC.5.2    Level: 2    Role: D
 Verifiera att efterlevnaden av alla regulatoriska krav har bedömts.
 #AC.5.3    Level: 3    Role: D/V
 Verifera att regeländringar utlöser snabba granskningar och uppdateringar av AI-system.

#### Referenser

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Bilaga D: AI-assisterad styrning och verifiering av säker kodning

### Mål

Detta kapitel definierar grundläggande organisatoriska kontroller för säker och effektiv användning av AI-assisterade kodningsverktyg under programvaruutveckling, vilket säkerställer säkerhet och spårbarhet genom hela SDLC.

---

### AD.1 AI-assisterat säkert kodningsarbetsflöde

Integrera AI-verktyg i organisationens säkra programvaruutvecklingslivscykel (SSDLC) utan att försvaga befintliga säkerhetskontroller.

 #AD.1.1    Level: 1    Role: D/V
 Verifiera att en dokumenterad arbetsflöde beskriver när och hur AI-verktyg kan generera, refaktorera eller granska kod.
 #AD.1.2    Level: 2    Role: D
 Verifiera att arbetsflödet motsvarar varje SSDLC-fas (design, implementering, kodgranskning, testning, distribution).
 #AD.1.3    Level: 3    Role: D/V
 Verifiera att mått (t.ex. sårbarhetstäthet, genomsnittlig tid till upptäckt) samlas in för AI-genererad kod och jämförs med baslinjer som enbart inkluderar mänsklig kod.

---

### AD.2 AI-verktygskvalificering och hotmodellering

Se till att AI-kodningsverktyg utvärderas för säkerhetsförmågor, risker och påverkan på leverantörskedjan innan de tas i bruk.

 #AD.2.1    Level: 1    Role: D/V
 Verifiera att en hotmodell för varje AI-verktyg identifierar missbruk, modellinversion, dataläckage och risker i beroendekedjan.
 #AD.2.2    Level: 2    Role: D
 Verifiera att verktygsevalueringar inkluderar statisk/dynamisk analys av eventuella lokala komponenter och bedömning av SaaS-endpunkter (TLS, autentisering/auktorisation, loggning).
 #AD.2.3    Level: 3    Role: D/V
 Verifiera att utvärderingar följer en erkänd ram och utförs på nytt efter större versionsändringar.

---

### AD.3 Säker hantering av prompt och kontext

Förhindra läckage av hemligheter, proprietär kod och personuppgifter när du konstruerar prompts eller kontexter för AI-modeller.

 #AD.3.1    Level: 1    Role: D/V
 Verifiera att skriftlig vägledning förbjuder att skicka hemligheter, autentiseringsuppgifter eller klassificerad data i prompts.
 #AD.3.2    Level: 2    Role: D
 Verifiera att tekniska kontroller (klientbaserad redigering, godkända kontextfilter) automatiskt tar bort känsliga artefakter.
 #AD.3.3    Level: 3    Role: D/V
 Verifiera att promptar och svar tokeniseras, krypteras under överföring och i vila, och att lagringstider följer dataklassificeringspolicyn.

---

### AD.4 Validering av AI-genererad kod

Upptäck och åtgärda sårbarheter som introducerats av AI-resultat innan koden slås samman eller deployeras.

 #AD.4.1    Level: 1    Role: D/V
 Verifiera att AI-genererad kod alltid granskas av en mänsklig kodgranskare.
 #AD.4.2    Level: 2    Role: D
 Verifiera att automatiska skannrar (SAST/IAST/DAST) körs på varje pull-begäran som innehåller AI-genererad kod och blockera sammanslagning vid kritiska fynd.
 #AD.4.3    Level: 3    Role: D/V
 Verifiera att differential fuzz-testning eller egenskapsbaserade tester bevisar säkerhetskritiska beteenden (t.ex. inmatningsvalidering, auktoriseringslogik).

---

### AD.5 Förklarbarhet och Spårbarhet av Kodförslag

Ge revisorer och utvecklare insikt i varför ett förslag gjordes och hur det utvecklades.

 #AD.5.1    Level: 1    Role: D/V
 Verifiera att prompt-/svarpar loggas med commit-ID:n.
 #AD.5.2    Level: 2    Role: D
 Verifiera att utvecklare kan visa modellciteringar (träningsutdrag, dokumentation) som stöder ett förslag.
 #AD.5.3    Level: 3    Role: D/V
 Verifiera att förklaringsrapporter lagras tillsammans med designartefakter och refereras i säkerhetsgranskningar, vilket uppfyller ISO/IEC 42001:s spårbarhetsprinciper.

---

### AD.6 Kontinuerlig återkoppling och finjustering av modellen

Förbättra modellens säkerhetsprestanda över tid samtidigt som negativ drift förhindras.

 #AD.6.1    Level: 1    Role: D/V
 Verifiera att utvecklare kan markera osäkra eller icke-kompatibla förslag, och att markeringarna spåras.
 #AD.6.2    Level: 2    Role: D
 Verifiera att samlad återkoppling används för periodisk finjustering eller återhämtningsförstärkt generering med granskade säker kodningskorpusar (t.ex. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verifiera att ett sluten-loop utvärderingssystem kör regressionstester efter varje finjustering; säkerhetsmetrik måste uppfylla eller överstiga tidigare baslinjer innan driftsättning.

---

#### Referenser

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Bilaga E: Exempel på verktyg och ramverk

### Mål

Detta kapitel ger exempel på verktyg och ramverk som kan stödja implementering eller uppfyllande av ett givet AISVS-krav. Dessa ska inte betraktas som rekommendationer eller godkännanden från AISVS-teamet eller OWASP GenAI Security-projektet.

---

### AE.1 Träningens datahantering och hantering av partiskhet

Verktyg som används för dataanalys, styrning och hantering av bias.

 #AE.1.1    Section: 1.1
 Verktyg för datainventering: Verktyg för hantering av datainventering såsom...
 #AE.1.2    Section: 1.2
 Kryptering under överföring Använd TLS för HTTPS-baserade applikationer, med verktyg som openSSL och pythons`ssl`bibliotek.

---

### AE.2 Validering av användarinmatning

Verktyg för att hantera och validera användarinmatningar.

 #AE.2.1    Section: 2.1
 Verktyg för försvar mot promptinjektion: Använd guardrail-verktyg som NVIDIA:s NeMo eller Guardrails AI.

---

## C1 Träningsdatastyrning och hantering av partiskhet

### C1.1 Träningsdatans ursprung

Upprätthåll en verifierbar inventering av alla dataset, acceptera endast betrodda källor och logga varje ändring för reviderbarhet.

 #1.1.1    Level: 1    Role: D/V
 Verifiera att en uppdaterad inventering av varje träningsdatakälla (ursprung, ansvarig/ägare, licens, insamlingsmetod, avsedda användningsbegränsningar och bearbetningshistorik) upprätthålls.

