## Frontispice

### Om standarden

Artificial Intelligence Security Verification Standard (AISVS) er en fællesskabsdrevet katalog over sikkerhedskrav, som dataforskere, MLOps-ingeniører, softwarearkitekter, udviklere, testere, sikkerhedsprofessionelle, værktøjsleverandører, regulatorer og brugere kan anvende til at designe, opbygge, teste og verificere pålidelige AI-aktiverede systemer og applikationer. Den giver et fælles sprog til at specificere sikkerhedskontroller på tværs af AI-livscyklussen — fra dataindsamling og modeludvikling til implementering og løbende overvågning — så organisationer kan måle og forbedre robusthed, privatliv og sikkerhed i deres AI-løsninger.

### Ophavsret og licens

Version 0.1 (Første offentlige udkast - Arbejde i gang), 2025  

![license](images/license.png)
Ophavsret © 2025 The AISVS-projektet.  

Udgivet under theCreative Commons Attribution‑ShareAlike 4.0 International License.
For enhver genbrug eller distribution skal du tydeligt kommunikere licensbetingelserne for dette værk til andre.

### Projektledere

Jim Manico
Aras “Russ” Memisyazici

### Bidragydere og anmeldere

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS er en helt ny standard, der er skabt specifikt til at håndtere de unikke sikkerhedsudfordringer ved kunstige intelligenssystemer. Selvom den henter inspiration fra bredere sikkerhedspraksis, er hvert krav i AISVS udviklet fra bunden for at afspejle AI-trusselslandskabet og hjælpe organisationer med at opbygge sikkerere, mere modstandsdygtige AI-løsninger.

## Forord

Velkommen til Artificial Intelligence Security Verification Standard (AISVS) version 1.0!

### Introduktion

Etableret i 2025 gennem en fælles indsats fra samfundet definerer AISVS sikkerhedskravene, der skal overvejes ved design, udvikling, implementering og drift af moderne AI-modeller, databehandlingspipelines og AI-aktiverede tjenester.

AISVS v1.0 repræsenterer det samlede arbejde fra dets projektledere, arbejdsgruppe og bredere fællesskabsbidragydere for at skabe en pragmatisk, testbar grundlinje for sikring af AI-systemer.

Vores mål med denne udgivelse er at gøre AISVS let at tage i brug, samtidig med at vi forbliver skarpt fokuserede på dets definerede omfang og adresserer det hurtigt udviklende risikolandskab, der er unikt for AI.

### Nøglemål for AISVS Version 1.0

Version 1.0 vil blive oprettet med flere vejledende principper.

#### Veldefineret omfang

Hvert krav skal være i overensstemmelse med AISVS’s navn og mission:

Kunstig intelligens – Kontroller fungerer på AI/ML-laget (data, model, pipeline eller inferens) og er ansvaret for AI-praktikere.
Sikkerhed – Kravene afbøder direkte identificerede sikkerheds-, privatlivs- eller sikkerhedsrisici.
Verifikation – Sproget er skrevet, så overensstemmelse kan valideres objektivt.
Standard – Sektioner følger en konsekvent struktur og terminologi for at danne en sammenhængende reference.
​
---

Ved at følge AISVS kan organisationer systematisk evaluere og styrke sikkerhedspositionen for deres AI-løsninger og fremme en kultur af sikker AI-udvikling.

## Brug af AISVS

Den kunstige intelligens sikkerhedsverifikationsstandard (AISVS) definerer sikkerhedskrav for moderne AI-applikationer og -tjenester med fokus på aspekter inden for applikationsudviklernes kontrol.

AISVS er beregnet til alle, der udvikler eller vurderer sikkerheden af AI-applikationer, herunder udviklere, arkitekter, sikkerhedsingeniører og revisorer. Dette kapitel introducerer strukturen og brugen af AISVS, herunder dens verifikationsniveauer og tilsigtede anvendelsestilfælde.

### Sikkerhedsverifikationsniveauer for kunstig intelligens

AISVS definerer tre stigende niveauer af sikkerhedsverifikation. Hvert niveau tilføjer dybde og kompleksitet, hvilket gør det muligt for organisationer at tilpasse deres sikkerhedsniveau til risikoniveauet for deres AI-systemer.

Organisationer kan starte på Niveau 1 og gradvist adoptere højere niveauer i takt med, at sikkerhedsmodenhed og trusselsudsættelse øges.

#### Definition af niveauerne

Hvert krav i AISVS v1.0 er tildelt et af følgende niveauer:

 Krav på niveau 1

Niveau 1 omfatter de mest kritiske og grundlæggende sikkerhedskrav. Disse fokuserer på at forhindre almindelige angreb, som ikke afhænger af andre forudsætninger eller sårbarheder. De fleste kontrolforanstaltninger på Niveau 1 er enten ligetil at implementere eller så væsentlige, at de retfærdiggør indsatsen.

 Krav på niveau 2

Niveau 2 håndterer mere avancerede eller mindre almindelige angreb samt lagdelte forsvar mod udbredte trusler. Disse krav kan involvere mere kompleks logik eller rette sig mod specifikke forudsætninger for angreb.

 Krav på niveau 3

Niveau 3 inkluderer kontroller, der typisk er sværere at implementere eller kun gælder i visse situationer. Disse repræsenterer ofte forsvar-i-dybden mekanismer eller afbødninger mod niche-, målrettede eller komplekse angreb.

#### Rolle (D/V)

Hver AISVS-krav er markeret i henhold til den primære målgruppe:

D – Udviklerfokuserede krav
V – Krav med fokus på verificering/revisor
D/V – Relevant for både udviklere og verificatorer

## C1 Træningsdata Governance & Bias Management

### Kontrolmål

Træningsdata skal skaffes, håndteres og vedligeholdes på en måde, der bevarer oprindelse, sikkerhed, kvalitet og retfærdighed. Dette opfylder juridiske forpligtelser og reducerer risici for bias, forurening eller brud på privatlivets fred gennem hele AI-livscyklussen.

---

### C1.1 Oprindelse af træningsdata

Oprethold en verificerbar oversigt over alle datasæt, accepter kun betroede kilder, og log alle ændringer for revisionsmulighed.

 #1.1.1    Level: 1    Role: D/V
 Sørg for, at der føres et opdateret inventar over hver eneste træningsdatakilde (oprindelse, ansvarlig/ejer, licens, indsamlingmetode, begrænsninger for tilsigtet brug og behandlingshistorik).
 #1.1.2    Level: 1    Role: D/V
 Sørg for, at kun datasæt, der er kontrolleret for kvalitet, repræsentativitet, etisk indsamling og overholdelse af licens, er tilladt, hvilket reducerer risikoen for forurening, indlejret bias og krænkelse af intellektuelle ejendomsrettigheder.
 #1.1.3    Level: 1    Role: D/V
 Bekræft, at data-minimering håndhæves, så unødvendige eller følsomme attributter udelukkes.
 #1.1.4    Level: 2    Role: D/V
 Bekræft, at alle ændringer i datasættet er underlagt en godkendelsesproces, der logges.
 #1.1.5    Level: 2    Role: D/V
 Sørg for, at kvaliteten af mærkning/annotering sikres via krydstjek eller konsensus blandt anmeldere.
 #1.1.6    Level: 2    Role: D/V
 Bekræft, at "datakort" eller "datasheets for datasæt" opretholdes for væsentlige træningsdatasæt, som detaljerer egenskaber, motivationer, sammensætning, indsamlingprocesser, forbehandling samt anbefalede/ikke-anbefalede anvendelser.

---

### C1.2 Sikkerhed og integritet for træningsdata

Begræns adgang, krypter data i hvile og under overførsel, og valider integriteten for at forhindre manipulation eller tyveri.

 #1.2.1    Level: 1    Role: D/V
 Bekræft, at adgangskontroller beskytter lager og pipelines.
 #1.2.2    Level: 2    Role: D/V
 Bekræft, at datasæt er krypteret under overførsel og, for alle følsomme eller personligt identificerbare oplysninger (PII), i hvile, ved hjælp af kryptografiske algoritmer og nøglehåndteringspraksis efter industristandard.
 #1.2.3    Level: 2    Role: D/V
 Bekræft, at kryptografiske hashværdier eller digitale signaturer bruges til at sikre dataintegritet under lagring og overførsel, samt at automatiserede anomalidetektionsteknikker anvendes for at beskytte mod uautoriserede ændringer eller korruption, herunder målrettede dataforgiftningforsøg.
 #1.2.4    Level: 3    Role: D/V
 Bekræft, at dataset-versioner spores for at muliggøre tilbagerulning.
 #1.2.5    Level: 2    Role: D/V
 Bekræft, at forældede data bliver sikkert slettet eller anonymiseret i overensstemmelse med dataopbevaringspolitikker, lovgivningsmæssige krav og for at mindske angrebsoverfladen.

---

### C1.3 Repræsentationsfuldstændighed og retfærdighed

Registrer demografiske skævheder og anvend afbødning, så modellens fejlprocenter er retfærdige på tværs af grupper.

 #1.3.1    Level: 1    Role: D/V
 Bekræft, at datasæt profileres for repræsentationsubalance og potentielle biaser på tværs af juridisk beskyttede attributter (f.eks. race, køn, alder) og andre etisk følsomme karakteristika, der er relevante for modellens anvendelsesområde (f.eks. socioøkonomisk status, geografisk placering).
 #1.3.2    Level: 2    Role: D/V
 Bekræft, at de identificerede skævheder afbødes via dokumenterede strategier såsom genbalancering, målrettet dataaugmentation, algoritmiske justeringer (f.eks. præ-behandling, behandling under processen, efterbehandlingsteknikker) eller omvægtning, og at virkningen af afbødningen både på retfærdighed og den samlede modelpræstation vurderes.
 #1.3.3    Level: 2    Role: D/V
 Bekræft, at efter-trænings retfærdigheds-målinger evalueres og dokumenteres.
 #1.3.4    Level: 3    Role: D/V
 Bekræft, at en politik for livscyklus-biasstyring tildeler ejere og fastsætter gennemgangsfrekvens.

---

### C1.4 Kvalitet, integritet og sikkerhed ved mærkning af træningsdata

Beskyt etiketter med kryptering og kræv dobbelt gennemgang for kritiske klasser.

 #1.4.1    Level: 2    Role: D/V
 Sørg for, at kvaliteten af mærkning/annotering sikres gennem klare retningslinjer, krydstjek af anmeldere, konsensusmekanismer (f.eks. overvågning af enighed mellem annotatorer) og definerede processer til at løse uoverensstemmelser.
 #1.4.2    Level: 2    Role: D/V
 Bekræft, at kryptografiske hashværdier eller digitale signaturer anvendes på etiketterede artefakter for at sikre deres integritet og ægthed.
 #1.4.3    Level: 2    Role: D/V
 Bekræft, at mærkningsgrænseflader og platforme håndhæver stærke adgangskontroller, opretholder manipulationssikre revisionslogs over alle mærkningsaktiviteter og beskytter mod uautoriserede ændringer.
 #1.4.4    Level: 3    Role: D/V
 Sørg for, at etiketter, der er afgørende for sikkerhed, beskyttelse eller retfærdighed (f.eks. identificering af giftigt indhold, kritiske medicinske fund), gennemgår obligatorisk uafhængig dobbeltgennemgang eller tilsvarende robust verifikation.
 #1.4.5    Level: 2    Role: D/V
 Bekræft, at følsomme oplysninger (inklusive personligt identificerbare oplysninger) utilsigtet indfanget eller nødvendigvis til stede i labels, bliver sløret, pseudonymiseret, anonymiseret eller krypteret både i hvile og under overførsel, i henhold til principperne om dataminimering.
 #1.4.6    Level: 2    Role: D/V
 Bekræft, at mærkningsvejledninger og instruktioner er omfattende, versionsstyrede og fagfællebedømte.
 #1.4.7    Level: 2    Role: D/V
 Bekræft, at dataschemas (inklusive for labels) er klart definerede og versionsstyrede.
 #1.8.2    Level: 2    Role: D/V
 Bekræft, at outsourcet eller crowdsourcet mærkningsarbejdsgange inkluderer tekniske/procedurale sikkerhedsforanstaltninger for at sikre datakonfidensialitet, integritet, mærkningskvalitet og forhindre datalækage.

---

### C1.5 Kvalitetssikring af træningsdata

Kombiner automatiseret validering, manuel stikprøvekontrol og logført udbedring for at sikre datasættets pålidelighed.

 #1.5.1    Level: 1    Role: D
 Bekræft, at automatiserede tests fanger formateringsfejl, null-værdier og mærkningsskævheder ved hver indlæsning eller betydelig transformation.
 #1.5.2    Level: 1    Role: D/V
 Bekræft, at fejlslagne datasæt er isoleret med revisionsspor.
 #1.5.3    Level: 2    Role: V
 Bekræft, at manuelle stikprøver foretaget af domæneeksperter dækker et statistisk signifikant udvalg (f.eks. ≥1 % eller 1.000 prøver, afhængigt af hvad der er størst, eller som fastsat ved risikovurdering) for at identificere finere kvalitetsproblemer, som automatisering ikke opdager.
 #1.5.4    Level: 2    Role: D/V
 Bekræft, at udbedringstrin tilføjes til provenance-poster.
 #1.5.5    Level: 2    Role: D/V
 Bekræft, at kvalitetskontroller blokerer underordnede datasæt, medmindre undtagelser er godkendt.

---

### C1.6 Detektion af dataforgiftning

Anvend statistisk anomali-detektion og karantænearbejdsgange for at stoppe fjendtlige indsættelser.

 #1.6.1    Level: 2    Role: D/V
 Bekræft, at anomalidetektionsmetoder (f.eks. statistiske metoder, outlier-detektion, indlejring analyse) anvendes på træningsdata ved indtagelse og før større træningskørsler for at identificere potentielle forgiftningsangreb eller utilsigtet datakorruption.
 #1.6.2    Level: 2    Role: D/V
 Bekræft, at markerede prøver udløser manuel gennemgang før træning.
 #1.6.3    Level: 2    Role: V
 Bekræft, at resultaterne føder modellens sikkerhedsdossier og informerer den løbende trusselsintelligens.
 #1.6.4    Level: 3    Role: D/V
 Bekræft, at detektionslogikken opdateres med ny trusselsinformation.
 #1.6.5    Level: 3    Role: D/V
 Bekræft, at online-læringspipelines overvåger for distributionsændringer.
 #1.6.6    Level: 3    Role: D/V
 Bekræft, at specifikke forsvar mod kendte typer af dataforureningsangreb (f.eks. mærkeombytning, indsættelse af bagdørstriggere, angreb med indflydelsesrige instanser) er overvejet og implementeret baseret på systemets risikoprofil og datakilder.

---

### C1.7 Sletning af brugerdata og håndhævelse af samtykke

Respekter anmodninger om sletning og tilbagetrækning af samtykke på tværs af datasæt, sikkerhedskopier og afledte artefakter.

 #1.7.1    Level: 1    Role: D/V
 Bekræft, at sletningsarbejdsgange rydder primære og afledte data samt vurderer modelpåvirkningen, og at påvirkningen på berørte modeller bliver vurderet og om nødvendigt håndteret (f.eks. gennem genuddannelse eller genkalibrering).
 #1.7.2    Level: 2    Role: D
 Bekræft, at der er mekanismer på plads til at spore og respektere omfanget og status for brugertilladelse (og tilbagekaldelser) for data, der bruges i træning, og at tilladelsen valideres, før data bliver indarbejdet i nye træningsprocesser eller væsentlige modelopdateringer.
 #1.7.3    Level: 2    Role: V
 Bekræft, at arbejdsprocesser testes årligt og logges.

---

### C1.8 Forsyningskædesikkerhed

Gennemgå eksterne dataleverandører og verificer integriteten over autentificerede, krypterede kanaler.

 #1.8.1    Level: 2    Role: D/V
 Sørg for, at tredjepartsdataleverandører, herunder udbydere af foruddannede modeller og eksterne datasæt, gennemgår sikkerheds-, privatlivs-, etisk indkøb- og datakvalitetsdue diligence, inden deres data eller modeller integreres.
 #1.8.2    Level: 1    Role: D
 Bekræft, at eksterne overførsler bruger TLS/autentificering og integritetskontrol.
 #1.8.3    Level: 2    Role: D/V
 Bekræft, at højrisikodata kilder (f.eks. open source-datasæt med ukendt oprindelse, ikke-godkendte leverandører) gennemgår øget kontrol, såsom isoleret analyse, omfattende kvalitets-/bias-kontroller og målrettet forgiftningsdetektion, før de anvendes i følsomme applikationer.
 #1.8.4    Level: 3    Role: D/V
 Bekræft, at forudtrænede modeller, der er modtaget fra tredjeparter, vurderes for indlejrede bias, potentielle bagdøre, integriteten af deres arkitektur og oprindelsen af deres oprindelige træningsdata, før de finjusteres eller tages i brug.

---

### C1.9 Modstanderes prøveidentifikation

Implementer foranstaltninger under træningsfasen, såsom adversarial træning, for at øge modellens modstandsdygtighed over for adversarielle eksempler.

 #1.9.1    Level: 3    Role: D/V
 Bekræft, at passende forsvarsmetoder, såsom adversarial træning (ved brug af genererede adversariale eksempler), dataforøgelse med perturberede input eller robuste optimeringsteknikker, er implementeret og justeret for relevante modeller baseret på risikovurdering.
 #1.9.2    Level: 2    Role: D/V
 Bekræft, at hvis adversarial træning anvendes, er genereringen, håndteringen og versioneringen af adversariale datasæt dokumenteret og kontrolleret.
 #1.9.3    Level: 3    Role: D/V
 Bekræft, at effekten af træning i modstandsdygtighed over for angreb (både mod rene og modstridende input) og retfærdighedsmål bliver evalueret, dokumenteret og overvåget.
 #1.9.4    Level: 3    Role: D/V
 Bekræft, at strategier for modstandertræning og robusthed regelmæssigt gennemgås og opdateres for at imødegå udviklende teknikker til modstanderangreb.

---

### C1.10 Data Lineage og Sporbarhed

Spor hele rejsen for hvert datapunkt fra kilden til modelinputtet for revisionsformål og hændelsesrespons.

 #1.10.1    Level: 2    Role: D/V
 Sørg for, at slægtslinjen for hvert datapunkt, inklusive alle transformationer, augmenteringer og sammensmeltninger, er registreret og kan rekonstrueres.
 #1.10.2    Level: 2    Role: D/V
 Bekræft, at slægtskabsposter er uforanderlige, sikkert lagret og tilgængelige til revisioner eller undersøgelser.
 #1.10.3    Level: 2    Role: D/V
 Bekræft, at stamtavlesporing dækker både rå og syntetiske data.

---

### C1.11 Håndtering af syntetiske data

Sørg for, at syntetiske data håndteres korrekt, mærkes og risikovurderes.

 #1.11.1    Level: 2    Role: D/V
 Sørg for, at alle syntetiske data er tydeligt mærket og adskilt fra rigtige data gennem hele processen.
 #1.11.2    Level: 2    Role: D/V
 Verifier, at genereringsprocessen, parametrene og den tilsigtede anvendelse af syntetiske data er dokumenteret.
 #1.11.3    Level: 2    Role: D/V
 Sørg for, at syntetiske data bliver risikovurderet for bias, privatlivslæk, og repræsentationsproblemer, før de bruges til træning.

---

### C1.12 Overvågning af dataadgang og anomalidetektion

Overvåg og alarmer ved usædvanlig adgang til træningsdata for at opdage insidertrusler eller dataudtræk.

 #1.12.1    Level: 2    Role: D/V
 Bekræft, at al adgang til træningsdata logges, inklusive bruger, tidspunkt og handling.
 #1.12.2    Level: 2    Role: D/V
 Bekræft, at adgangslogfiler regelmæssigt gennemgås for usædvanlige mønstre, såsom store eksporter eller adgang fra nye lokationer.
 #1.12.3    Level: 2    Role: D/V
 Bekræft, at alarmer genereres for mistænkelige adgangshændelser og undersøges hurtigt.

---

### C1.13 Politikker for datalagring og udløb

Definér og håndhæv datalagringsperioder for at minimere unødvendig datalagring.

 #1.13.1    Level: 1    Role: D/V
 Bekræft, at eksplicitte opbevaringsperioder er defineret for alle træningsdatasæt.
 #1.13.2    Level: 2    Role: D/V
 Bekræft, at datasæt automatisk udløber, slettes eller gennemgås for sletning ved slutningen af deres livscyklus.
 #1.13.3    Level: 2    Role: D/V
 Verificer, at opbevarings- og sletningshandlinger bliver logget og kan revideres.

---

### C1.14 Regulatorisk og jurisdiktionsmæssig overholdelse

Sikre, at alle træningsdata overholder gældende love og regler.

 #1.14.1    Level: 2    Role: D/V
 Bekræft, at krav til dataresidens og grænseoverskridende overførsler er identificeret og håndhævet for alle datasæt.
 #1.14.2    Level: 2    Role: D/V
 Bekræft, at sektorspecifikke regler (f.eks. sundhedssektoren, finanssektoren) er identificeret og håndteres i databehandlingen.
 #1.14.3    Level: 2    Role: D/V
 Sørg for, at overholdelse af relevante privatlivslover (f.eks. GDPR, CCPA) er dokumenteret og gennemgås regelmæssigt.

---

### C1.15 Data Vandmærkning og Fingeraftryk

Registrer uautoriseret genbrug eller lækage af proprietære eller følsomme data.

 #1.15.1    Level: 3    Role: D/V
 Bekræft, at datasæt eller delmængder er vandmærket eller fingeraftrykt, hvor det er muligt.
 #1.15.2    Level: 3    Role: D/V
 Bekræft, at vandmærkning/fingeraftryksmetoder ikke introducerer skævheder eller privatlivsrisici.
 #1.15.3    Level: 3    Role: D/V
 Bekræft, at der udføres periodiske kontrol for at opdage uautoriseret genbrug eller lækage af vandmærkede data.

---

### C1.16 Håndtering af registreredes rettigheder

Understøt registreredes rettigheder såsom adgang, berigtigelse, begrænsning og indsigelse.

 #1.16.1    Level: 2    Role: D/V
 Bekræft, at der findes mekanismer til at reagere på forespørgsler fra registrerede personer om adgang, berigtigelse, begrænsning eller indsigelse.
 #1.16.2    Level: 2    Role: D/V
 Bekræft, at forespørgsler bliver logget, sporet og opfyldt inden for lovbestemte tidsrammer.
 #1.16.3    Level: 2    Role: D/V
 Bekræft, at processerne for registreredes rettigheder testes og gennemgås regelmæssigt for effektivitet.

---

### C1.17 Analyse af virkningen af datasætversioner

Vurder virkningen af ændringer i datasættet, før du opdaterer eller udskifter versioner.

 #1.17.1    Level: 2    Role: D/V
 Bekræft, at der udføres en konsekvensanalyse, før en datasætversion opdateres eller udskiftes, som omfatter modelpræstation, retfærdighed og overholdelse.
 #1.17.2    Level: 2    Role: D/V
 Bekræft, at resultaterne af konsekvensanalysen er dokumenteret og gennemgået af relevante interessenter.
 #1.17.3    Level: 2    Role: D/V
 Sørg for, at der findes rollback-planer, hvis nye versioner introducerer uacceptable risici eller tilbageskridt.

---

### C1.18 Datasætningsannoterings arbejdsstyrkesikkerhed

Sikre sikkerheden og integriteten for personale involveret i dataannotering.

 #1.18.1    Level: 2    Role: D/V
 Sørg for, at alt personale involveret i dataannotering er baggrundstjekket og uddannet i datasikkerhed og privatliv.
 #1.18.2    Level: 2    Role: D/V
 Bekræft, at alt annoteringspersonale underskriver fortroligheds- og ikke-offentliggørelsesaftaler.
 #1.18.3    Level: 2    Role: D/V
 Bekræft, at annoteringsplatforme håndhæver adgangskontroller og overvåger for interne trusler.

---

### Referencer

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

## C2 brugervalidering

### Kontrolmål

Robust validering af brugerinput er en første forsvarslinje mod nogle af de mest skadelige angreb på AI-systemer. Promptinjektionsangreb kan tilsidesætte systeminstruktioner, lække følsomme data eller styre modellen mod uacceptabel adfærd. Medmindre der er dedikerede filtre og instruktionshierarkier på plads, viser forskning, at "multi-shot" jailbreaks, som udnytter meget lange kontekstvinduer, vil være effektive. Desuden kan subtile adversariale perturbationsangreb—såsom homoglyph-udskiftninger eller leetspeak—stille og roligt ændre en models beslutninger.

---

### C2.1 Forsvar mod promptinjektion

Prompt-injektion er en af de største risici for AI-systemer. Forsvar mod denne taktik anvender en kombination af statiske mønstergeneratorer, dynamiske klassifikatorer og håndhævelse af instruktionshierarki.

 #2.1.1    Level: 1    Role: D/V
 Bekræft, at brugerinput bliver kontrolleret mod et kontinuerligt opdateret bibliotek af kendte promptinjektionsmønstre (jailbreak-nøgleord, "ignorér tidligere", rollespilssekvenser, indirekte HTML/URL-angreb).
 #2.1.2    Level: 1    Role: D/V
 Bekræft, at systemet håndhæver en instruktionshierarki, hvor system- eller udviklerbeskeder tilsidesætter brugerens instruktioner, selv efter udvidelse af kontekstvinduet.
 #2.1.3    Level: 2    Role: D/V
 Sørg for, at tests af modstridende evaluering (f.eks. Red Team "many-shot"-prompter) køres før hver udgivelse af en model eller prompt-skabelon, med succesrater som tærskler og automatiserede blokeringsmekanismer for regressionsfejl.
 #2.1.4    Level: 2    Role: D
 Bekræft, at prompts, der stammer fra tredjepartsindhold (websider, PDF'er, e-mails), renses i en isoleret parsingskontekst, før de sammenkædes med hovedprompten.
 #2.1.5    Level: 3    Role: D/V
 Bekræft, at alle opdateringer af prompt-filterregler, versioner af klassifikationsmodeller og ændringer i blokeringslister er versionsstyrede og reviderbare.

---

### C2.2 Modstand mod fjendtlige eksempler

Naturlige sprogbehandlingsmodeller (NLP) er stadig sårbare over for subtile forstyrrelser på tegn- eller ordniveau, som mennesker ofte overser, men som modeller har en tendens til at fejlkategorisere.

 #2.2.1    Level: 1    Role: D
 Bekræft, at grundlæggende input-normaliseringstrin (Unicode NFC, homoglyph-mapping, fjernelse af mellemrum) udføres før tokenisering.
 #2.2.2    Level: 2    Role: D/V
 Bekræft, at statistisk anomalidetektion markerer input med usædvanligt høj redigeringsafstand til sprognormer, overdrevne gentagne token eller unormale indlejringsafstande.
 #2.2.3    Level: 2    Role: D
 Bekræft, at inferenspipelinensupporterer valgfrie modstandsdygtige modelvarianter eller forsvarslag (f.eks. randomisering, defensiv destillation) til højrisikoendepunkter.
 #2.2.4    Level: 2    Role: V
 Bekræft, at mistænkte fjendtlige input bliver isoleret, logget med fulde nyttelaster (efter fjernelse af personligt identificerbare oplysninger).
 #2.2.5    Level: 3    Role: D/V
 Bekræft, at robusthedsmål (successrate for kendte angrebssuites) bliver overvåget over tid, og at regressionsfejl udløser en udgivelsesblokering.

---

### C2.3 Skema, Type og Længdevalidering

AI-angreb med fejlbehæftede eller overdimensionerede input kan forårsage parsefejl, promptoverskridelse på tværs af felter og ressourceudmattelse. Streng håndhævelse af skemaet er også en forudsætning ved udførelse af deterministiske værktøjsopkald.

 #2.3.1    Level: 1    Role: D
 Sørg for, at alle API- eller funktionskaldendepunkter definerer et eksplicit inputschema (JSON Schema, Protobuf eller multimodalt ækvivalent), og at input valideres før samling af prompt.
 #2.3.2    Level: 1    Role: D/V
 Bekræft, at input, der overskrider maksimumsgrænserne for tokens eller bytes, afvises med en sikker fejl og aldrig bliver tavst afkortet.
 #2.3.3    Level: 2    Role: D/V
 Bekræft, at typekontroller (f.eks. numeriske intervaller, enum-værdier, MIME-typer for billeder/lyd) håndhæves på serversiden og ikke kun i klientkoden.
 #2.3.4    Level: 2    Role: D
 Bekræft, at semantiske validatorer (f.eks. JSON Schema) kører i konstant tid for at forhindre algoritmisk DoS.
 #2.3.5    Level: 3    Role: V
 Bekræft, at valideringsfejl logges med redigerede nyttelastudsnit og entydige fejlkoder for at lette sikkerhedstriangulering.

---

### C2.4 Indholds- og politikscreening

Udviklere bør være i stand til at opdage syntaktisk gyldige prompts, der anmoder om forbudt indhold (såsom ulovlige instruktioner, hadtale og ophavsretligt beskyttet tekst), og derefter forhindre, at de spreder sig.

 #2.4.1    Level: 1    Role: D
 Bekræft, at en indholdsklassificerer (zero shot eller finjusteret) vurderer hver input for vold, selvskade, had, seksuelt indhold og ulovlige anmodninger, med konfigurerbare tærskelværdier.
 #2.4.2    Level: 1    Role: D/V
 Bekræft, at input, som overtræder politikker, vil modtage standardiserede afvisninger eller sikre afslutninger, så de ikke videreføres til efterfølgende LLM-kald.
 #2.4.3    Level: 2    Role: D
 Bekræft, at screeningsmodellen eller regelsættet genoplæres/opdateres mindst hvert kvartal, hvor nye observerede jailbreak- eller politikomgåelsesmønstre indarbejdes.
 #2.4.4    Level: 2    Role: D
 Bekræft, at screening overholder brugerspecifikke politikker (alder, regionale juridiske begrænsninger) via attributbaserede regler, der afgøres ved anmodningstidspunktet.
 #2.4.5    Level: 3    Role: V
 Bekræft, at screeningslogfiler inkluderer klassifikatorens tillidsniveauer og politikategori-tags til SOC-korrelation og fremtidig red-team-genafspilning.

---

### C2.5 Input Rate Begrænsning & Misbrugsforebyggelse

Udviklere bør forhindre misbrug, ressourceudmattelse og automatiserede angreb mod AI-systemer ved at begrænse inputhastigheder og opdage unormale brugsmønstre.

 #2.5.1    Level: 1    Role: D/V
 Bekræft, at grænser for hastighedskontrol pr. bruger, pr. IP og pr. API-nøgle håndhæves for alle inputendpoints.
 #2.5.2    Level: 2    Role: D/V
 Sørg for, at burst- og vedvarende hastighedsgrænser er justeret til at forhindre DoS- og brute force-angreb.
 #2.5.3    Level: 2    Role: D/V
 Bekræft, at unormale brugsmønstre (f.eks. hurtige gentagne anmodninger, inputoversvømmelse) udløser automatiske blokeringer eller eskalationer.
 #2.5.4    Level: 3    Role: V
 Bekræft, at logfiler for misbrugsforebyggelse opbevares og gennemgås for at identificere nye angrebsmønstre.

---

### C2.6 Multi-modal indtastningsvalidering

AI-systemer bør inkludere robust validering for ikke-tekstuelle input (billeder, lyd, filer) for at forhindre injektion, undvigelse eller ressourcemisbrug.

 #2.6.1    Level: 1    Role: D
 Sørg for, at alle ikke-tekst input (billeder, lyd, filer) valideres for type, størrelse og format, før de behandles.
 #2.6.2    Level: 2    Role: D/V
 Bekræft, at filer bliver scannet for malware og steganografiske payloads, før de indtastes.
 #2.6.3    Level: 2    Role: D/V
 Bekræft, at billede-/lydinput kontrolleres for fjendtlige forstyrrelser eller kendte angrebsmønstre.
 #2.6.4    Level: 3    Role: V
 Bekræft, at fejl i multimodal inputvalidering bliver logget og udløser advarsler til undersøgelse.

---

### C2.7 Input-Oprindelse og Attribution

AI-systemer bør understøtte revision, misbrugsregistrering og overholdelse ved at overvåge og mærke oprindelsen af alle brugersinputs.

 #2.7.1    Level: 1    Role: D/V
 Bekræft, at alle brugerinput er mærket med metadata (bruger-ID, session, kilde, tidsstempel, IP-adresse) ved indtagning.
 #2.7.2    Level: 2    Role: D/V
 Bekræft, at oprindelsesmetadata bevares og er reviderbare for alle behandlede input.
 #2.7.3    Level: 2    Role: D/V
 Bekræft, at anomaløse eller ikke-pålidelige inputkilder bliver markeret og underlagt øget kontrol eller blokeret.

---

### C2.8 Realtids adaptiv trusselsdetektion

Udviklere bør anvende avancerede trusselsdetekteringssystemer til AI, som tilpasser sig nye angrebsmønstre og leverer beskyttelse i realtid med kompileret mønstergenkendelse.

 #2.8.1    Level: 1    Role: D/V
 Bekræft, at trusselsdetektionsmønstre er kompileret til optimerede regex-motorer for højtydende realtidsfiltrering med minimal latense.
 #2.8.2    Level: 1    Role: D/V
 Bekræft, at trusselsdetekteringssystemer opretholder separate mønstrekataloger for forskellige trusselkategorier (promptinjektion, skadeligt indhold, følsomme data, systemkommandoer).
 #2.8.3    Level: 2    Role: D/V
 Bekræft, at adaptiv trusseldetektion inkorporerer maskinlæringsmodeller, der opdaterer trusselsfølsomheden baseret på angrebsfrekvens og succesrater.
 #2.8.4    Level: 2    Role: D/V
 Bekræft, at realtids trusselsinformationsfeeds automatisk opdaterer mønstermapper med nye angrebssignaturer og IOC'er (indikatorer for kompromittering).
 #2.8.5    Level: 3    Role: D/V
 Bekræft, at falske positive rater i trusselsdetektion kontinuerligt overvåges, og at mønsterspecificitet automatisk justeres for at minimere forstyrrelser af legitime anvendelsestilfælde.
 #2.8.6    Level: 3    Role: D/V
 Bekræft, at kontekstuel trusselanalyse tager højde for inputkilde, brugeradfærdsmønstre og sessionshistorik for at forbedre detektionsnøjagtigheden.
 #2.8.7    Level: 3    Role: D/V
 Bekræft, at ydelsesmetrikker for trusselsdetektion (detektionsrate, behandlingstidsforsinkelse, ressourceudnyttelse) overvåges og optimeres i realtid.

---

### C2.9 Multi-modal sikkerhedsvalideringspipeline

Udviklere bør levere sikkerhedsvalidering for tekst, billede, lyd og andre AI-indgangsmodaliteter med specifikke typer af trusselsdetektion og ressourceisolering.

 #2.9.1    Level: 1    Role: D/V
 Bekræft, at hver inputmodalitet har dedikerede sikkerhedsvalideringsværktøjer med dokumenterede trusselsmønstre (tekst: promptinjektion, billeder: steganografi, lyd: spektrogramangreb) og detektionsgrænser.
 #2.9.2    Level: 2    Role: D/V
 Sørg for, at multimodale input behandles i isolerede sandkasser med definerede ressourcelimits (hukommelse, CPU, behandlingstid), som er specifikke for hver modalitetstype og dokumenteret i sikkerhedspolitikker.
 #2.9.3    Level: 2    Role: D/V
 Bekræft, at krydsmodal angrebsdetection identificerer koordinerede angreb, der spænder over flere inputtyper (f.eks. steganografiske payloads i billeder kombineret med promptinjektion i tekst) ved hjælp af korrelationsregler og alarmering.
 #2.9.4    Level: 3    Role: D/V
 Bekræft, at multi-modal valideringsfejl udløser detaljeret logføring, der inkluderer alle inputmodaliteter, valideringsresultater, trusselsscorer og korrelationsanalyse med strukturerede logformater til SIEM-integration.
 #2.9.5    Level: 3    Role: D/V
 Kontroller, at modalitetsspecifikke indholdsclassificerere opdateres i henhold til dokumenterede tidsplaner (mindst kvartalsvist) med nye trusselmønstre, modstridende eksempler og ydeevnebenchmark, der holdes over basislinjetærskler.

---

### Referencer

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

## C3 Model livscyklusstyring og ændringskontrol

### Kontrolmål

AI-systemer skal implementere ændringskontrolprocesser, der forhindrer uautoriserede eller usikre modelændringer i at nå produktion. Denne kontrol sikrer modelintegritet gennem hele livscyklussen – fra udvikling over implementering til udfasning – hvilket muliggør hurtig hændelsesreaktion og opretholder ansvarlighed for alle ændringer.

Kerntilladelsesmål: Kun autoriserede, validerede modeller når produktion ved at anvende kontrollerede processer, der opretholder integritet, sporbarhed og genoprettelighed.

---

### C3.1 Modelautorisation og integritet

Kun autoriserede modeller med verificeret integritet når produktionsmiljøer.

 #3.1.1    Level: 1    Role: D/V
 Bekræft, at alle modelartefakter (vægte, konfigurationer, tokenizer) er kryptografisk signeret af autoriserede enheder før implementering.
 #3.1.2    Level: 1    Role: D/V
 Bekræft, at modelintegritet valideres ved implementering, og at fejl i signaturverifikation forhindrer indlæsning af modellen.
 #3.1.3    Level: 2    Role: D/V
 Bekræft, at modelproveniensregistre inkluderer en autoriserende enheds identitet, kontrolsummer for træningsdata, valideringstestresultater med bestået/ikke bestået status samt et oprettelsestidsstempel.
 #3.1.4    Level: 2    Role: D/V
 Bekræft, at alle modelartefakter bruger semantisk versionering (MAJOR.MINOR.PATCH) med dokumenterede kriterier, der angiver, hvornår hver versionskomponent øges.
 #3.1.5    Level: 2    Role: V
 Bekræft, at afhængighedssporing opretholder et realtidslager, som muliggør hurtig identifikation af alle forbrugende systemer.

---

### C3.2 Modelvalidering og testning

Modeller skal bestå definerede sikkerheds- og sikkerhedskontroller, før de implementeres.

 #3.2.1    Level: 1    Role: D/V
 Bekræft, at modeller gennemgår automatiseret sikkerhedstest, som inkluderer inputvalidering, outputrensning og sikkerhedsvurderinger med forudbestemte organisatoriske godkendelses-/afvisningskriterier, inden de implementeres.
 #3.2.2    Level: 1    Role: D/V
 Bekræft, at valideringsfejl automatisk blokerer for modeludrulning efter eksplicit godkendelse af forudbestemte autoriserede personer med dokumenterede forretningsmæssige begrundelser.
 #3.2.3    Level: 2    Role: V
 Bekræft, at testresultater er kryptografisk underskrevet og uforanderligt knyttet til den specifikke modelversions hash, der valideres.
 #3.2.4    Level: 2    Role: D/V
 Bekræft, at nødudrulninger kræver dokumenteret sikkerhedsrisikovurdering og godkendelse fra en forhåndsudpeget sikkerhedsmyndighed inden for forud aftalte tidsrammer.

---

### C3.3 Kontrolleret implementering og tilbagerulning

Modelimplementeringer skal kontrolleres, overvåges og kunne gendannes.

 #3.3.1    Level: 1    Role: D
 Bekræft, at produktionsudrulninger implementerer gradvise udrulningsmekanismer (kanarieudrulninger, blue-green udrulninger) med automatiserede tilbagetrækningsudløsere baseret på forudbestemte fejlprocenter, latenstærskler eller sikkerhedsalarmeringskriterier.
 #3.3.2    Level: 1    Role: D/V
 Bekræft, at rollback-funktioner gendanner den komplette modeltilstand (vægtninger, konfigurationer, afhængigheder) atomisk inden for foruddefinerede organisatoriske tidsvinduer.
 #3.3.3    Level: 2    Role: D/V
 Bekræft, at implementeringsprocesser validerer kryptografiske signaturer og beregner integritetskontrolsummer, inden modellen aktiveres, og at implementeringen fejler ved enhver uoverensstemmelse.
 #3.3.4    Level: 2    Role: D/V
 Bekræft, at nødstopfunktioner for modeller kan deaktivere modelendepunkter inden for foruddefinerede svartider via automatiserede afbrydere eller manuelle nødafbrydere.
 #3.3.5    Level: 2    Role: V
 Bekræft, at rollback-artifakter (tidligere modelversioner, konfigurationer, afhængigheder) opbevares i henhold til organisatoriske politikker med uforanderlig lagring til hændelsesrespons.

---

### C3.4 Ansvarlighed for ændringer og revision

Alle ændringer i modellens livscyklus skal kunne spores og revideres.

 #3.4.1    Level: 1    Role: V
 Bekræft, at alle modelændringer (udrulning, konfiguration, tilbagetrækning) genererer uforanderlige revisionsposter, inklusive et tidsstempel, en autentificeret aktøridentitet, en ændringstype og før/efter tilstande.
 #3.4.2    Level: 2    Role: D/V
 Bekræft, at adgang til revisionslog kræver passende autorisation, og at alle adgangsforsøg logges med brugeridentitet og tidsstempel.
 #3.4.3    Level: 2    Role: D/V
 Bekræft, at promptskabeloner og systemmeddelelser er versionsstyret i git-repositorier med obligatorisk kodegennemgang og godkendelse fra udpegede anmeldere før implementering.
 #3.4.4    Level: 2    Role: V
 Bekræft, at revisionsregistre indeholder tilstrækkelige detaljer (model-hash, konfigurationsøjebliksbilleder, afhængighedsversioner) til at muliggøre fuldstændig rekonstruktion af modeltilstand for enhver tidsstempel inden for opbevaringsperioden.

---

### C3.5 Sikker udviklingspraksis

Modeludviklings- og træningsprocesser skal følge sikre praksisser for at forhindre kompromittering.

 #3.5.1    Level: 1    Role: D
 Bekræft, at modeludviklings-, test- og produktionsmiljøer er fysisk eller logisk adskilte. De har ingen fælles infrastruktur, særskilte adgangskontroller og isolerede datalagre.
 #3.5.2    Level: 1    Role: D
 Bekræft, at modeltræning og finjustering foregår i isolerede miljøer med kontrolleret netværksadgang.
 #3.5.3    Level: 1    Role: D/V
 Bekræft, at træningsdatakilder valideres gennem integritetskontroller og autentificeres via betroede kilder med dokumenteret kæde af besiddelse, før de anvendes i modeludvikling.
 #3.5.4    Level: 2    Role: D
 Bekræft, at modeludviklingsartefakter (hyperparametre, træningsscripts, konfigurationsfiler) gemmes i versionskontrol og kræver godkendelse via peer review, før de anvendes i træning.

---

### C3.6 Model udfasning og afvikling

Modeller skal sikkert trækkes tilbage, når de ikke længere er nødvendige, eller når sikkerhedsproblemer opdages.

 #3.6.1    Level: 1    Role: D
 Bekræft, at modelpensationsprocesser automatisk scanner afhængighedsgrafer, identificerer alle forbrugende systemer og giver forudgående varslingsperioder, der er aftalt på forhånd, inden udfasning.
 #3.6.2    Level: 1    Role: D/V
 Bekræft, at arkiverede modelartefakter er sikkert slettet ved hjælp af kryptografisk sletning eller flerpasses overskrivning i henhold til dokumenterede databevaringspolitikker med verificerede destrueringcertifikater.
 #3.6.3    Level: 2    Role: V
 Bekræft, at modelens udfasning begivenheder logges med tidsstempel og aktørens identitet, og at model-signaturer tilbagekaldes for at forhindre genbrug.
 #3.6.4    Level: 2    Role: D/V
 Bekræft, at nødmodelafvikling kan deaktivere adgang til modellen inden for forudbestemte nødsvarstidsrammer via automatiserede driftsafbrydere, hvis der opdages kritiske sikkerhedssårbarheder.

---

### Referencer

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

## C4 Infrastruktur, Konfiguration og Udrulningssikkerhed

### Kontrolmål

AI-infrastrukturen skal gøres robust over for privilegieoptrapning, manipulation af forsyningskæden og lateral bevægelse gennem sikker konfiguration, runtime-isolation, betroede implementeringspipelines og omfattende overvågning. Kun autoriserede, validerede infrastrukturelementer og konfigurationer når produktionen gennem kontrollerede processer, der opretholder sikkerhed, integritet og revisionssporbarhed.

Kerne sikkerhedsmål: Kun kryptografisk signerede, sårbarhedsscannede infrastruktu komponenter når produktion gennem automatiserede valideringspipelines, der håndhæver sikkerhedspolitikker og opretholder uforanderlige revisionsspor.

---

### C4.1 Kørselstidsmiljø-isolation

Forhindre containerflugt og privilegieeskalering gennem kerne-niveau isolationsprimitive og obligatoriske adgangskontroller.

 #4.1.1    Level: 1    Role: D/V
 Bekræft, at alle AI-containere fraskriver sig ALLE Linux-kapabiliteter undtagen CAP_SETUID, CAP_SETGID og eksplicit krævede kapabiliteter, der er dokumenteret i sikkerhedsbasislinjer.
 #4.1.2    Level: 1    Role: D/V
 Bekræft, at seccomp-profiler blokerer alle systemkald undtagen dem, der er på forhånd godkendte tilladelseslister, hvor overtrædelser fører til containerens afslutning og genererer sikkerhedsalarmer.
 #4.1.3    Level: 2    Role: D/V
 Bekræft, at AI-arbejdsbelastninger kører med root-filsystemer, der kun kan læses, tmpfs til midlertidige data, og navngivne volumener til vedvarende data med noexec-monteringsmuligheder håndhævet.
 #4.1.4    Level: 2    Role: D/V
 Bekræft, at eBPF-baseret runtime-overvågning (Falco, Tetragon eller tilsvarende) opdager forsøg på privilegieeskalering og automatisk afslutter de forurenende processer inden for organisationens svartidskrav.
 #4.1.5    Level: 3    Role: D/V
 Bekræft, at højrisiko AI-arbejdsbelastninger kører i hardware-isolerede miljøer (Intel TXT, AMD SVM eller dedikerede bare-metal noder) med attestationsverifikation.

---

### C4.2 Sikker Bygge- og Udrulningspipeline

Sørg for kryptografisk integritet og sikkerhed i forsyningskæden gennem reproducerbare builds og signerede artefakter.

 #4.2.1    Level: 1    Role: D/V
 Bekræft, at infrastructure-as-code bliver scannet med værktøjer (tfsec, Checkov eller Terrascan) ved hvert commit, og at merges blokeres ved FUNDAMENTALE eller HØJE alvorlighedsgrader.
 #4.2.2    Level: 1    Role: D/V
 Bekræft, at container-builds er reproducerbare med identiske SHA256-hashværdier på tværs af builds, og generer SLSA Level 3 oprindelsesattester underskrevet med Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Bekræft, at containerbilleder indeholder CycloneDX- eller SPDX-SBOM'er og er underskrevet med Cosign inden push til registret, hvor ikke-underskrevne billeder afvises ved implementering.
 #4.2.4    Level: 2    Role: D/V
 Bekræft, at CI/CD-pipelines bruger OIDC-tokens fra HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med levetider, der ikke overstiger organisationens sikkerhedspolitiske grænser.
 #4.2.5    Level: 2    Role: D/V
 Bekræft, at Cosign-signaturer og SLSA-proveniens valideres under implementeringsprocessen, inden containeren kører, og at verifikationsfejl forårsager, at implementeringen mislykkes.
 #4.2.6    Level: 2    Role: D/V
 Bekræft, at build-miljøer kører i flygtige containere eller virtuelle maskiner uden vedvarende lagerplads og med netværksisolering fra produktions-VPC'er.

---

### C4.3 Netværkssikkerhed og adgangskontrol

Implementer zero-trust netværk med standard-afvisningspolitikker og krypteret kommunikation.

 #4.3.1    Level: 1    Role: D/V
 Bekræft, at Kubernetes NetworkPolicies eller en tilsvarende løsning implementerer standard-afvisning af indgående/udgående trafik med eksplicitte tilladelsesregler for nødvendige porte (443, 8080 osv.).
 #4.3.2    Level: 1    Role: D/V
 Bekræft, at SSH (port 22), RDP (port 3389) og cloud metadata-endpoints (169.254.169.254) er blokeret eller kræver certifikatbaseret autentificering.
 #4.3.3    Level: 2    Role: D/V
 Bekræft, at udgående trafik filtreres gennem HTTP/HTTPS-proxyer (Squid, Istio eller cloud NAT-gateways) med domænetilladelister, og at blokerede forespørgsler logges.
 #4.3.4    Level: 2    Role: D/V
 Bekræft, at kommunikation mellem tjenester bruger gensidig TLS med certifikater, der roteres i henhold til organisationspolitikken, og at certifikatvalidering håndhæves (uden brug af skip-verify-flag).
 #4.3.5    Level: 2    Role: D/V
 Bekræft, at AI-infrastrukturen kører i dedikerede VPC'er/VNet med ingen direkte internetadgang og kommunikerer udelukkende gennem NAT-gateways eller bastionværter.

---

### C4.4 Hemmeligheder og Kryptografisk Nøglehåndtering

Beskyt legitimationsoplysninger gennem hardware-understøttet lagring og automatiseret rotation med nul-tillids adgang.

 #4.4.1    Level: 1    Role: D/V
 Bekræft, at hemmeligheder er gemt i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering ved hvile ved brug af AES-256.
 #4.4.2    Level: 1    Role: D/V
 Bekræft, at kryptografiske nøgler genereres i FIPS 140-2 Niveau 2 HSM'er (AWS CloudHSM, Azure Dedicated HSM) med nøglerotation i overensstemmelse med den organisatoriske kryptografiske politik.
 #4.4.3    Level: 2    Role: D/V
 Bekræft, at hemmelighedsrotation er automatiseret med implementering uden nedetid og øjeblikkelig rotation udløst af personaleforandringer eller sikkerhedshændelser.
 #4.4.4    Level: 2    Role: D/V
 Sørg for, at containerbilleder scannes med værktøjer (GitLeaks, TruffleHog eller detect-secrets), der blokerer builds, som indeholder API-nøgler, adgangskoder eller certifikater.
 #4.4.5    Level: 2    Role: D/V
 Bekræft, at adgang til produktionshemmeligheder kræver MFA med hardwaretokens (YubiKey, FIDO2) og registreres i uforanderlige revisionslogfiler med brugeridentiteter og tidsstempler.
 #4.4.6    Level: 2    Role: D/V
 Sørg for, at hemmeligheder injiceres via Kubernetes-hemmeligheder, monterede volumener eller init-containere, og sikre, at hemmeligheder aldrig er indlejret i miljøvariabler eller billeder.

---

### C4.5 AI Arbejdsbelastningssandkasse og Validering

Isolér ikke-pålidelige AI-modeller i sikre sandkasser med omfattende adfærdsanalyse.

 #4.5.1    Level: 1    Role: D/V
 Sørg for, at eksterne AI-modeller kører i gVisor, microVMs (såsom Firecracker, CrossVM) eller Docker-containere med --security-opt=no-new-privileges og --read-only flag.
 #4.5.2    Level: 1    Role: D/V
 Bekræft, at sandbox-miljøer ikke har netværksforbindelse (--network=none) eller kun lokal adgang med alle eksterne forespørgsler blokeret via iptables-regler.
 #4.5.3    Level: 2    Role: D/V
 Bekræft, at validering af AI-modeller inkluderer automatiseret red-team-testning med organisationsdefineret testdækning og adfærdsanalyse for bagdørsdetektion.
 #4.5.4    Level: 2    Role: D/V
 Bekræft, at før en AI-model promoveres til produktion, er dens sandbox-resultater kryptografisk underskrevet af autoriseret sikkerhedspersonale og gemt i uforanderlige revisionslogfiler.
 #4.5.5    Level: 2    Role: D/V
 Bekræft, at sandkassemiljøer bliver ødelagt og genoprettet fra gyldne billeder mellem evalueringer med fuldstændig oprydning af filsystem og hukommelse.

---

### C4.6 Infrastruktur Sikkerhedsovervågning

Kontinuerligt overvåg og scan infrastrukturen med automatiseret udbedring og realtidsalarmering.

 #4.6.1    Level: 1    Role: D/V
 Bekræft, at containerbilleder bliver scannet i henhold til organisationens tidsplaner, hvor KRITISKE sårbarheder blokerer for implementering baseret på organisationens risikogrænser.
 #4.6.2    Level: 1    Role: D/V
 Verificer, at infrastrukturen overholder CIS Benchmarks eller NIST 800-53 kontroller med organisatorisk definerede overholdelsesgrænser og automatiseret udbedring for mislykkede kontrolpunkter.
 #4.6.3    Level: 2    Role: D/V
 Bekræft, at sårbarheder med HØJ alvorlighedsgrad bliver rettet i henhold til organisationens risikostyringstidsplaner med nødprocedurer for aktivt udnyttede CVE'er.
 #4.6.4    Level: 2    Role: V
 Bekræft, at sikkerhedsalarmer integreres med SIEM-platforme (Splunk, Elastic eller Sentinel) ved brug af CEF- eller STIX/TAXII-formater med automatiseret berigelse.
 #4.6.5    Level: 3    Role: V
 Bekræft, at infrastrukturmetrics eksporteres til overvågningssystemer (Prometheus, DataDog) med SLA-dashboard og ledelsesrapportering.
 #4.6.6    Level: 2    Role: D/V
 Bekræft, at konfigurationsafvigelse opdages ved hjælp af værktøjer (Chef InSpec, AWS Config) i henhold til organisationens overvågningskrav med automatisk tilbagerulning af uautoriserede ændringer.

---

### C4.7 AI-infrastruktur Ressourcehåndtering

Forhindre ressourceudtømningangreb og sikre retfærdig ressourceallokering gennem kvoter og overvågning.

 #4.7.1    Level: 1    Role: D/V
 Bekræft, at GPU-/TPU-udnyttelse overvåges med alarmer, der udløses ved organisatorisk definerede grænser, og at automatisk skalering eller belastningsfordeling aktiveres baseret på kapacitetsstyringspolitikker.
 #4.7.2    Level: 1    Role: D/V
 Bekræft, at AI-arbejdsbelastningsmålinger (inferenzlatens, gennemløb, fejlrater) indsamles i overensstemmelse med organisationens overvågningskrav og korreleres med infrastrukturudnyttelse.
 #4.7.3    Level: 2    Role: D/V
 Bekræft, at Kubernetes ResourceQuotas eller tilsvarende begrænser individuelle arbejdsbelastninger i henhold til organisatoriske ressourcetildelingspolitikker med håndhævede hårde grænser.
 #4.7.4    Level: 2    Role: V
 Bekræft, at omkostningsovervågning sporer forbruget pr. arbejdsbyrde/lejer med alarmer baseret på organisatoriske budgetgrænser og automatiserede kontroller for budgetoverskridelser.
 #4.7.5    Level: 3    Role: V
 Bekræft, at kapacitetsplanlægning bruger historiske data med organisatorisk definerede forecastperioder og automatiseret ressourceforsyning baseret på efterspørgselsmønstre.
 #4.7.6    Level: 2    Role: D/V
 Bekræft, at ressourceudmattelse udløser afbrydere i henhold til organisationens responskrav, inklusive hastighedsbegrænsning baseret på kapacitetsretningslinjer og arbejdsbelastningsisolation.

---

### C4.8 Adskillelse af miljøer og kontrol med promovering

Håndhæv strenge miljøgrænser med automatiserede promotionsporte og sikkerhedsvalidering.

 #4.8.1    Level: 1    Role: D/V
 Bekræft, at dev/test/prod-miljøer kører i separate VPC'er/VNets uden delte IAM-roller, sikkerhedsgrupper eller netværksforbindelser.
 #4.8.2    Level: 1    Role: D/V
 Bekræft, at miljøfremme kræver godkendelse fra organisatorisk defineret autoriseret personale med kryptografiske signaturer og uforanderlige revisionsspor.
 #4.8.3    Level: 2    Role: D/V
 Bekræft, at produktionsmiljøer blokerer SSH-adgang, deaktiverer debug-endepunkter og kræver ændringsanmodninger med organisatoriske krav om forudgående varsel, undtagen i nødsituationer.
 #4.8.4    Level: 2    Role: D/V
 Bekræft, at ændringer i infrastruktur som kode kræver peer review med automatiseret testning og sikkerhedsscanning, før de flettes til hovedbranch.
 #4.8.5    Level: 2    Role: D/V
 Bekræft, at ikke-produktionsdata er anonymiseret i overensstemmelse med organisatoriske privatlivskrav, syntetisk datagenerering eller fuldstændig datamaskering med fjernelse af personhenførbare oplysninger (PHI) verificeret.
 #4.8.6    Level: 2    Role: D/V
 Bekræft, at promotionsportaler inkluderer automatiserede sikkerhedstests (SAST, DAST, container-scanning) med krav om nul KRITISKE fund for godkendelse.

---

### C4.9 Infrastruktur Backup og Gendannelse

Sikre infrastrukturopbygningens robusthed gennem automatiserede sikkerhedskopier, testede genoprettelsesprocedurer og katastrofeberedskab.

 #4.9.1    Level: 1    Role: D/V
 Bekræft, at infrastrukturkonfigurationer sikkerhedskopieres i henhold til organisationens sikkerhedskopieringsplaner til geografisk adskilte regioner med implementering af 3-2-1 sikkerhedskopieringsstrategi.
 #4.9.2    Level: 2    Role: D/V
 Bekræft, at backupsystemer kører i isolerede netværk med separate legitimationsoplysninger og luftadskilt lagring for beskyttelse mod ransomware.
 #4.9.3    Level: 2    Role: V
 Bekræft, at genoprettelsesprocedurer testes og valideres gennem automatiseret testning i henhold til organisatoriske tidsplaner med RTO- og RPO-mål, der opfylder organisationens krav.
 #4.9.4    Level: 3    Role: V
 Bekræft, at katastrofegendannelse inkluderer AI-specifikke kørebøger med gendannelse af modelvægte, genopbygning af GPU-klynger og kortlægning af tjenesteafhængigheder.

---

### C4.10 Infrastrukturoverholdelse og styring

Oprethold overholdelse af regler gennem løbende vurdering, dokumentation og automatiserede kontroller.

 #4.10.1    Level: 2    Role: D/V
 Bekræft, at infrastrukturens overholdelse vurderes i henhold til organisatoriske tidsplaner mod SOC 2, ISO 27001 eller FedRAMP-kontroller med automatiseret indsamling af beviser.
 #4.10.2    Level: 2    Role: V
 Bekræft, at infrastruktur-dokumentationen indeholder netværksdiagrammer, dataflow-kort og trusselsmodeller opdateret i henhold til organisationens krav til ændringsstyring.
 #4.10.3    Level: 3    Role: D/V
 Bekræft, at infrastrukturelle ændringer gennemgår automatiseret vurdering af overholdelsespåvirkning med regulatoriske godkendelsesarbejdsgange for højrisikomodifikationer.

---

### C4.11 AI Hardware-sikkerhed

Sikre AI-specifikke hardwarekomponenter, herunder GPU'er, TPU'er og specialiserede AI-acceleratorer.

 #4.11.1    Level: 2    Role: D/V
 Bekræft, at AI-acceleratorens firmware (GPU BIOS, TPU-firmware) er verificeret med kryptografiske signaturer og opdateret i henhold til organisationens patchhåndterings-tidsplaner.
 #4.11.2    Level: 2    Role: D/V
 Bekræft, at AI-acceleratorens integritet valideres før arbejdsbelastningens udførelse ved hjælp af hardwareattestation med TPM 2.0, Intel TXT eller AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Bekræft, at GPU-hukommelse er isoleret mellem arbejdsbelastninger ved brug af SR-IOV, MIG (Multi-Instance GPU) eller tilsvarende hardwarepartitionering med hukommelsessanitering mellem opgaver.
 #4.11.4    Level: 3    Role: V
 Bekræft, at AI-hardwareforsyningskæden inkluderer oprindelsesverifikation med producentcertifikater og validering af manipulationssikkert emballage.
 #4.11.5    Level: 3    Role: D/V
 Bekræft, at hardware-sikkerhedsmoduler (HSM'er) beskytter AI-modelvægte og kryptografiske nøgler med FIPS 140-2 Niveau 3 eller Common Criteria EAL4+ certificering.

---

### C4.12 Edge- og Distribueret AI-infrastruktur

Sikre distribuerede AI-implementeringer inklusive edge computing, fødereret læring og flersite-arkitekturer.

 #4.12.1    Level: 2    Role: D/V
 Bekræft, at edge AI-enheder autentificerer til central infrastruktur ved hjælp af gensidig TLS med enhedscertifikater, der roteres i overensstemmelse med den organisatoriske certifikatstyringspolitik.
 #4.12.2    Level: 2    Role: D/V
 Sørg for, at edge-enheder implementerer secure boot med verificerede signaturer og rollback-beskyttelse, der forhindrer firmware-nedgraderingsangreb.
 #4.12.3    Level: 3    Role: D/V
 Bekræft, at distribueret AI-koordinering bruger byzantinsk fejltolerante konsensusalgoritmer med deltager-validering og ondsindet node-detektion.
 #4.12.4    Level: 3    Role: D/V
 Bekræft, at edge-til-cloud-kommunikation omfatter båndbreddebegrænsning, datakomprimering og offline-drift med sikre lokale lagringsmuligheder.

---

### C4.13 Multi-Cloud og Hybrid Infrastruktur Sikkerhed

Sikre AI-arbejdsbelastninger på tværs af flere cloud-udbydere og hybride cloud-on-premises implementeringer.

 #4.13.1    Level: 2    Role: D/V
 Bekræft, at multi-cloud AI-implementeringer bruger cloud-agnostisk identitetsfederation (OIDC, SAML) med centraliseret politikstyring på tværs af udbydere.
 #4.13.2    Level: 2    Role: D/V
 Bekræft, at krydssky dataoverførsel bruger ende-til-ende-kryptering med kundestyrende nøgler, og at datalokaliseringskontroller håndhæves i henhold til jurisdiktion.
 #4.13.3    Level: 2    Role: D/V
 Sørg for, at hybride cloud AI-arbejdsbelastninger implementerer konsekvente sikkerhedspolitikker på tværs af lokale og cloud-miljøer med samlet overvågning og alarmering.
 #4.13.4    Level: 3    Role: V
 Bekræft, at forebyggelse af leverandørlåsning til skyen inkluderer bærbar infrastruktur-som-kode, standardiserede API'er og datalekapacitet med værktøjer til formatkonvertering.
 #4.13.5    Level: 3    Role: V
 Sørg for, at multi-cloud omkostningsoptimering inkluderer sikkerhedskontroller, der forhindrer ressource-spredning samt uautoriserede tvær-cloud dataoverførselsomkostninger.

---

### C4.14 Infrastrukturautomatisering & GitOps-sikkerhed

Sikre automatiserede infrastruktursearbejdsgange og GitOps-processer til styring af AI-infrastruktur.

 #4.14.1    Level: 2    Role: D/V
 Bekræft, at GitOps-repositorier kræver signerede commits med GPG-nøgler og branch-beskyttelsesregler, der forhindrer direkte push til main-branches.
 #4.14.2    Level: 2    Role: D/V
 Bekræft, at infrastrukturautomatisering inkluderer afvigelsesdetektion med automatiske genoprettelses- og tilbagerulningsfunktioner, der aktiveres i henhold til organisationens reaktionskrav for uautoriserede ændringer.
 #4.14.3    Level: 2    Role: D/V
 Bekræft, at automatiseret infrastrukturprovisionering inkluderer validering af sikkerhedspolitikker med udrulningsblokering for ikke-overholdende konfigurationer.
 #4.14.4    Level: 2    Role: D/V
 Bekræft, at hemmeligheder til infrastrukturautomatisering håndteres gennem eksterne secret operators (External Secrets Operator, Bank-Vaults) med automatisk rotation.
 #4.14.5    Level: 3    Role: V
 Bekræft, at selvhelende infrastruktur inkluderer sikkerhedshændelseskorrelation med automatiseret hændelsesrespons og arbejdsflows for underretning af interessenter.

---

### C4.15 Kvante-resistent infrastruktur sikkerhed

Forbered AI-infrastruktur til trusler fra kvantecomputing gennem post-kvante kryptografi og kvantesikre protokoller.

 #4.15.1    Level: 3    Role: D/V
 Bekræft, at AI-infrastrukturen implementerer NIST-godkendte post-kvante kryptografiske algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) til nøgleudveksling og digitale signaturer.
 #4.15.2    Level: 3    Role: D/V
 Bekræft, at kvante-nøglefordelingssystemer (QKD) er implementeret til højsikkerheds AI-kommunikationer med kvantesikre nøglehåndteringsprotokoller.
 #4.15.3    Level: 3    Role: D/V
 Bekræft, at kryptografiske agilitetssystemer muliggør hurtig migrering til nye post-kvante algoritmer med automatiseret certifikat- og nøgleudskiftning.
 #4.15.4    Level: 3    Role: V
 Bekræft, at kvantetrusselsmodellering vurderer AI-infrastrukturens sårbarhed over for kvanteangreb med dokumenterede migrationsplaner og risikovurderinger.
 #4.15.5    Level: 3    Role: D/V
 Bekræft, at hybride klassiske-kvantemæssige kryptografiske systemer tilbyder forsvar-i-dybden under kvanteovergangsperioden med ydelsesovervågning.

---

### C4.16 Fortrolig Beregning og Sikker Indelinger

Beskyt AI-arbejdsbelastninger og modelvægt ved hjælp af hardware-baserede betroede eksekveringsmiljøer og fortrolighedsberegningsteknologier.

 #4.16.1    Level: 3    Role: D/V
 Bekræft, at følsomme AI-modeller kører inden for Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med krypteret hukommelse og attestation verificering.
 #4.16.2    Level: 3    Role: D/V
 Bekræft, at fortrolige containere (Kata Containers, gVisor med fortrolig computing) isolerer AI-arbejdsbelastninger med hardware-baseret hukommelseskryptering.
 #4.16.3    Level: 3    Role: D/V
 Bekræft, at fjernattestation validerer enclave-integritet, før AI-modeller indlæses, med kryptografisk bevis for eksekveringsmiljøets ægthed.
 #4.16.4    Level: 3    Role: D/V
 Bekræft, at fortrolige AI-inferenztjenester forhindrer modeludtrækning gennem krypteret beregning med forseglede modelvægte og beskyttet udførelse.
 #4.16.5    Level: 3    Role: D/V
 Bekræft, at orkestrering af betroede udførelsesmiljøer håndterer livscyklussen for sikre enclaver med fjernattestation og krypterede kommunikationskanaler.
 #4.16.6    Level: 3    Role: D/V
 Bekræft, at sikker multi-part beregning (SMPC) muliggør samarbejdende AI-træning uden at afsløre individuelle datasæt eller modelparametre.

---

### C4.17 Zero-Knowledge Infrastruktur

Implementer nulvidensbevis-systemer til privatlivsbeskyttende AI-verifikation og autentificering uden at afsløre følsomme oplysninger.

 #4.17.1    Level: 3    Role: D/V
 Bekræft, at nul-viden-beviser (ZK-SNARKs, ZK-STARKs) verificerer AI-modelintegritet og træningsoprindelse uden at afsløre modelvægte eller træningsdata.
 #4.17.2    Level: 3    Role: D/V
 Bekræft, at ZK-baserede autentificeringssystemer muliggør privatlivsbevarende brugerbekræftelse for AI-tjenester uden at afsløre identitetsrelaterede oplysninger.
 #4.17.3    Level: 3    Role: D/V
 Bekræft, at private sætintersektionsprotokoller (PSI) muliggør sikker datamatching for fødereret AI uden at eksponere individuelle datasæt.
 #4.17.4    Level: 3    Role: D/V
 Bekræft, at zero-knowledge maskinlæringssystemer (ZKML) muliggør verificerbare AI-slutsætninger med kryptografisk bevis for korrekt beregning.
 #4.17.5    Level: 3    Role: D/V
 Bekræft, at ZK-rollups leverer skalerbar, privatlivsbeskyttende AI-transaktionsbehandling med batchverifikation og reduceret beregningsbelastning.

---

### C4.18 Forebyggelse af sidekanalsangreb

Beskyt AI-infrastruktur mod tidsmæssige, strøm-, elektromagnetiske og cache-baserede sidekanal-angreb, der kan lække følsomme oplysninger.

 #4.18.1    Level: 3    Role: D/V
 Bekræft, at AI-inferensens timing er normaliseret ved brug af konstant-tidsalgoritmer og padding for at forhindre timing-baserede angreb på modeludtrækning.
 #4.18.2    Level: 3    Role: D/V
 Bekræft, at beskyttelse mod strøm analyse inkluderer støjindsprøjtning, filtrering af strømforsyningslinjer og randomiserede eksekveringsmønstre for AI-hardware.
 #4.18.3    Level: 3    Role: D/V
 Bekræft, at cache-baseret sidekanalafhjælpning bruger cache-partitionering, randomisering og flush-instruktioner til at forhindre informationslækage.
 #4.18.4    Level: 3    Role: D/V
 Bekræft, at beskyttelse mod elektromagnetisk udstråling inkluderer afskærmning, signalfiltrering og tilfældig behandling for at forhindre TEMPEST-lignende angreb.
 #4.18.5    Level: 3    Role: D/V
 Bekræft, at mikrodukturelle sidekanalbeskyttelser omfatter kontrol med spekulativ eksekvering og obfuskering af hukommelsesadgangsmønstre.

---

### C4.19 Neuromorf og Specialiseret AI Hardware Sikkerhed

Sikre nye AI-hardwarearkitekturer, herunder neuromorfe chips, FPGA'er, specialdesignede ASIC'er og optiske computersystemer.

 #4.19.1    Level: 3    Role: D/V
 Bekræft, at neuromorfisk chip-sikkerhed inkluderer kryptering af spike-mønstre, beskyttelse af synaptiske vægte og hardware-baseret validering af læringsregler.
 #4.19.2    Level: 3    Role: D/V
 Bekræft, at FPGA-baserede AI-acceleratorer implementerer bitstrøm-kryptering, anti-manipulationsmekanismer og sikker konfigurationsindlæsning med autentificerede opdateringer.
 #4.19.3    Level: 3    Role: D/V
 Bekræft, at specialiserede ASIC-sikkerhedsløsninger inkluderer sikkerhedsprocessorer på chippen, hardware root of trust og sikker nøglelagring med manipulationsdetektion.
 #4.19.4    Level: 3    Role: D/V
 Bekræft, at optiske computersystemer implementerer kvantesikret optisk kryptering, sikker fotonisk switching og beskyttet optisk signalbehandling.
 #4.19.5    Level: 3    Role: D/V
 Bekræft, at hybride analog-digitale AI-chips inkluderer sikker analog beregning, beskyttet vægtlagring og autentificeret analog-til-digital konvertering.

---

### C4.20 Privatlivsbevarende computereinfrastruktur

Implementer infrastrukturkontroller for privatlivsbevarende beregning for at beskytte følsomme data under AI-behandling og analyse.

 #4.20.1    Level: 3    Role: D/V
 Bekræft, at homomorf krypteringsinfrastruktur muliggør krypteret beregning på følsomme AI-arbejdsmængder med kryptografisk integritetsverifikation og ydeevneovervågning.
 #4.20.2    Level: 3    Role: D/V
 Sørg for, at systemer til privat informationshentning muliggør databaseforespørgsler uden at afsløre forespørgsmønstre ved hjælp af kryptografisk beskyttelse af adgangsmønstre.
 #4.20.3    Level: 3    Role: D/V
 Bekræft, at sikre multi-parti beregningsprotokoller muliggør privatlivsbeskyttende AI-inferens uden at afsløre individuelle input eller mellemliggende beregninger.
 #4.20.4    Level: 3    Role: D/V
 Bekræft, at privatlivsbevarende nøglehåndtering omfatter distribueret nøglegenerering, tærskelkryptografi og sikker nøglerotation med hardwareunderstøttet beskyttelse.
 #4.20.5    Level: 3    Role: D/V
 Sørg for, at ydeevnen for privatlivsbevarende beregninger optimeres gennem batching, caching og hardwareacceleration, samtidig med at de kryptografiske sikkerhedsgarantier opretholdes.

---

### C4.15 Agent Framework Cloud Integration Sikkerhed & Hybrid Udrulning

Sikkerhedskontroller for sky-integrerede agentrammeværker med hybride lokalt installerede/skyarkitekturer.

 #4.15.1    Level: 1    Role: D/V
 Bekræft, at integrationen af cloud-lagring anvender ende-til-ende-kryptering med agentstyret nøgleadministration.
 #4.15.2    Level: 2    Role: D/V
 Bekræft, at sikkerhedsgrænser for hybrid implementering er klart defineret med krypterede kommunikationskanaler.
 #4.15.3    Level: 2    Role: D/V
 Bekræft, at adgang til cloud-ressourcer inkluderer zero-trust-verifikation med kontinuerlig autentificering.
 #4.15.4    Level: 3    Role: D/V
 Bekræft, at krav til dataopbevaringssted overholdes ved kryptografisk attestering af lagringssteder.
 #4.15.5    Level: 3    Role: D/V
 Kontroller, at sikkerhedsvurderinger hos cloud-udbyderen inkluderer agentspecifik trusselsmodellering og risikovurdering.

---

### Referencer

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

## C5 Adgangskontrol og identitet for AI-komponenter og brugere

### Kontrolmål

Effektiv adgangskontrol for AI-systemer kræver robust identitetsstyring, kontekstbevidst autorisation og håndhævelse under kørsel i overensstemmelse med principperne for zero-trust. Disse kontroller sikrer, at mennesker, tjenester og autonome agenter kun interagerer med modeller, data og beregningsressourcer inden for eksplicit tildelte rammer, med kontinuerlig verifikation og revisionsmuligheder.

---

### C5.1 Identitetsstyring og autentificering

Etabler kryptografisk-sikrede identiteter for alle enheder med multifaktorgodkendelse til privilegerede operationer.

 #5.1.1    Level: 1    Role: D/V
 Bekræft, at alle menneskelige brugere og serviceprincipaler godkendes gennem en centraliseret virksomhedsidentitetsudbyder (IdP) ved hjælp af OIDC/SAML-protokoller med unikke identitet-til-token kortlægninger (ingen delte konti eller legitimationsoplysninger).
 #5.1.2    Level: 1    Role: D/V
 Bekræft, at højrisikooperationer (modeludrulning, vægtekport, adgang til træningsdata, ændringer i produktionskonfiguration) kræver multifaktorgodkendelse eller trinvis godkendelse med sessionsrevalidering.
 #5.1.3    Level: 2    Role: D
 Bekræft, at nye principper gennemgår identitetsbekræftelse, der er i overensstemmelse med NIST 800-63-3 IAL-2 eller tilsvarende standarder, før de får adgang til produktionssystemet.
 #5.1.4    Level: 2    Role: V
 Bekræft, at adgangsgennemgange udføres kvartalsvis med automatiseret detektion af inaktive konti, håndhævelse af credential rotation og workflows for afvikling af adgang.
 #5.1.5    Level: 3    Role: D/V
 Bekræft, at fødererede AI-agenter autentificerer via signerede JWT-påstande, som har en maksimal levetid på 24 timer og inkluderer kryptografisk bevis for oprindelsen.

---

### C5.2 Ressourceautorisation og mindste privilegium

Implementer detaljerede adgangskontroller for alle AI-ressourcer med eksplicitte tilladelsesmodeller og revisionsspor.

 #5.2.1    Level: 1    Role: D/V
 Bekræft, at alle AI-ressourcer (datasæt, modeller, endepunkter, vektorsamlinger, indlejringsindekser, compute-instanser) håndhæver rollebaserede adgangskontroller med eksplicitte tilladelseslister og standardafvisningspolitikker.
 #5.2.2    Level: 1    Role: D/V
 Bekræft, at principperne om mindst privilegium håndhæves som standard for servicekonti, startende med skrivebeskyttede tilladelser, og at der kræves dokumenteret forretningsmæssig begrundelse for skriveadgang.
 #5.2.3    Level: 1    Role: V
 Bekræft, at alle ændringer i adgangskontrollen er knyttet til godkendte ændringsanmodninger og logget uforanderligt med tidsstempler, aktøridentiteter, ressourceidentifikatorer og ændringsdifferencer i tilladelser.
 #5.2.4    Level: 2    Role: D
 Bekræft, at dataklassifikationsmærker (PII, PHI, eksportkontrol, proprietær) automatisk videreføres til afledte ressourcer (indlejring, prompt-cache, modeloutput) med konsekvent politikhåndhævelse.
 #5.2.5    Level: 2    Role: D/V
 Bekræft, at uautoriserede adgangsforsøg og hændelser med privilegieforhøjelse udløser realtidsalarmer med kontekstuel metadata til SIEM-systemer inden for 5 minutter.

---

### C5.3 Dynamisk politikvurdering

Implementer attributbaserede adgangskontrol (ABAC) motorer til kontekstbevidste autorisationsbeslutninger med revisionsmuligheder.

 #5.3.1    Level: 1    Role: D/V
 Bekræft, at autorisationsbeslutninger er eksterne og håndteres af en dedikeret politikmotor (OPA, Cedar eller tilsvarende), som er tilgængelig via autentificerede API'er med kryptografisk integritetsbeskyttelse.
 #5.3.2    Level: 1    Role: D/V
 Bekræft, at politikker evaluerer dynamiske attributter under kørsel, herunder brugernes sikkerhedsniveau, ressourcefølsomhedsklassifikation, anmodningskontekst, lejerisolation og tidsmæssige begrænsninger.
 #5.3.3    Level: 2    Role: D
 Bekræft, at politikdefinitioner er versionsstyrede, fagmæssigt gennemgået og valideret gennem automatiserede tests i CI/CD-pipelines, før de implementeres i produktion.
 #5.3.4    Level: 2    Role: V
 Bekræft, at resultatet af politikvurdering inkluderer strukturerede beslutningsbegrundelser og overføres til SIEM-systemer til korrelationsanalyse og rapportering om overholdelse.
 #5.3.5    Level: 3    Role: D/V
 Bekræft, at politikcachens levetid (TTL) ikke overstiger 5 minutter for højsensitive ressourcer og 1 time for standardressourcer med cache-udløsningsmuligheder.

---

### C5.4 Sikkerhedshåndhævelse ved forespørgselstidspunktet

Implementer sikkerhedskontroller på databaseniveau med obligatorisk filtrering og række-niveau sikkerhedspolitikker.

 #5.4.1    Level: 1    Role: D/V
 Bekræft, at alle vektor-database- og SQL-forespørgsler inkluderer obligatoriske sikkerhedsfiltre (lejert ID, følsomhedsetiketter, brugerområde), som håndhæves på databasmotor-niveau og ikke i applikationskoden.
 #5.4.2    Level: 1    Role: D/V
 Bekræft, at politikker for sikkerhed på rækkeniveau (RLS) og maske på feltniveau er aktiveret med politikarv for alle vektordatabaser, søgeindekser og træningsdatasæt.
 #5.4.3    Level: 2    Role: D
 Bekræft, at mislykkede autorisationsvurderinger vil forhindre "confused deputy-angreb" ved straks at afbryde forespørgsler og returnere eksplicitte autorisationsfejlkoder i stedet for at returnere tomme resultatsæt.
 #5.4.4    Level: 2    Role: V
 Bekræft, at politikvurderingsforsinkelse løbende overvåges med automatiserede advarsler ved timeout-betingelser, som kunne muliggøre omgåelse af autorisation.
 #5.4.5    Level: 3    Role: D/V
 Bekræft, at forespørgselsgenforsøgs-mekanismer genvurderer autorisationspolitikker for at tage højde for dynamiske ændringer i tilladelser inden for aktive brugersessioner.

---

### C5.5 Outputfiltrering og forebyggelse af data tab

Implementer post-processing kontrolmekanismer for at forhindre uautoriseret dataeksponering i AI-genereret indhold.

 #5.5.1    Level: 1    Role: D/V
 Bekræft, at filtre efter inferens scanner og redigerer uautoriserede personoplysninger (PII), klassificerede oplysninger og proprietære data, før indhold leveres til anmodere.
 #5.5.2    Level: 1    Role: D/V
 Bekræft, at henvisninger, referencer og kildeangivelser i modeloutput er valideret i forhold til kalderens rettigheder og fjernet, hvis uautoriseret adgang opdages.
 #5.5.3    Level: 2    Role: D
 Bekræft, at outputformatbegrænsninger (rensede PDF'er, metadata-fjernede billeder, godkendte filtyper) håndhæves baseret på brugertilladelsesniveauer og dataklassifikationer.
 #5.5.4    Level: 2    Role: V
 Sørg for, at redigeringsalgoritmer er deterministiske, versionskontrollerede og opretholder revisionslogfiler for at understøtte overholdelsesundersøgelser og retsmedicinsk analyse.
 #5.5.5    Level: 3    Role: V
 Bekræft, at højrisiko redaktionsevents genererer adaptive logfiler, som inkluderer kryptografiske hashes af det oprindelige indhold til retsmedicinsk genfinding uden datalækage.

---

### C5.6 Flere-lejer isolering

Sikre kryptografisk og logisk isolation mellem lejere i delt AI-infrastruktur.

 #5.6.1    Level: 1    Role: D/V
 Bekræft, at hukommelsesrum, indlejringslagre, cache-poster og midlertidige filer er navneområdeseparerede pr. lejer med sikker sletning ved sletning af lejer eller afslutning af session.
 #5.6.2    Level: 1    Role: D/V
 Bekræft, at hver API-anmodning inkluderer en autentificeret lejeridentifikator, som er kryptografisk valideret mod sessionskontekst og brugerrettigheder.
 #5.6.3    Level: 2    Role: D
 Bekræft, at netværkspolitikker implementerer standard-afvisningsregler for kommunikation på tværs af lejere inden for servicemeshes og containerorkestreringsplatforme.
 #5.6.4    Level: 3    Role: D
 Bekræft, at krypteringsnøgler er unikke per lejer med kundestyret nøgle (CMK) support og kryptografisk isolation mellem lejerens datalagre.

---

### C5.7 Autorisation af autonom agent

Kontroller tilladelser for AI-agenter og autonome systemer gennem scopespecifikke kapabilitetstokens og kontinuerlig autorisation.

 #5.7.1    Level: 1    Role: D/V
 Bekræft, at autonome agenter modtager scoped kapabilitetstokens, der eksplicit angiver tilladte handlinger, tilgængelige ressourcer, tidsgrænser og driftsmæssige begrænsninger.
 #5.7.2    Level: 1    Role: D/V
 Bekræft, at højrisikofunktioner (adgang til filsystem, kodeudførelse, eksterne API-kald, finansielle transaktioner) er deaktiveret som standard og kræver eksplicitte godkendelser for aktivering med forretningsmæssige begrundelser.
 #5.7.3    Level: 2    Role: D
 Bekræft, at kapabilitetstokener er bundet til brugersessioner, inkluderer kryptografisk integritetsbeskyttelse, og sikre, at de ikke kan gemmes eller genbruges i offline-scenarier.
 #5.7.4    Level: 2    Role: V
 Bekræft, at agent-initierede handlinger gennemgår sekundær godkendelse via ABAC-politikmotoren med fuld kontekstevaluering og revisionslogning.
 #5.7.5    Level: 3    Role: V
 Bekræft, at agentfejltilstande og undtagelseshåndtering inkluderer oplysninger om kapabilitetsområde for at understøtte hændelsesanalyse og retsmedicinsk undersøgelse.

---

### Referencer

#### Standarder og rammeværk

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Implementeringsvejledninger

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### AI-specifik sikkerhed

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Forsyningskædesikkerhed for modeller, rammeværk og data

### Kontrolmål

AI forsyningskædeangreb udnytter tredjepartsmodeller, -rammer eller datasæt til at indlejre bagdøre, bias eller udnyttelig kode. Disse kontrolforanstaltninger giver end-to-end oprindelsesstyring, sårbarhedshåndtering og overvågning for at beskytte hele modellens livscyklus.

---

### C6.1 Forudtrænet Modellervurdering og Oprindelse

Vurder og autentificer oprindelse, licenser og skjulte adfærd hos tredjepartsmodeller, inden der foretages finjustering eller implementering.

 #6.1.1    Level: 1    Role: D/V
 Bekræft, at hver tredjeparts modelartefakt indeholder en signeret proveniensregistrering, der identificerer kildearkivet og commit-hashen.
 #6.1.2    Level: 1    Role: D/V
 Sørg for, at modeller bliver scannet for skadelige lag eller Trojan-udløsere ved hjælp af automatiserede værktøjer før import.
 #6.1.3    Level: 2    Role: D
 Bekræft, at transfer-læring finjusterer og består en modstandsdygtighedstest for at opdage skjulte adfærd.
 #6.1.4    Level: 2    Role: V
 Bekræft, at modelllicenser, eksportkontrolmærker og erklæringer om dataoprindelse er registreret i en ML-BOM-post.
 #6.1.5    Level: 3    Role: D/V
 Bekræft, at højrisikomodeller (offentligt uploadede vægte, uverificerede skabere) forbliver i karantæne indtil menneskelig gennemgang og godkendelse.

---

### C6.2 Framework- og biblioteksscanning

Scan løbende ML-rammeværk og biblioteker for CVE'er og ondsindet kode for at holde runtime-stakken sikker.

 #6.2.1    Level: 1    Role: D/V
 Bekræft, at CI-pipelines kører afhængighedsscannere på AI-rammeværk og kritiske biblioteker.
 #6.2.2    Level: 1    Role: D/V
 Bekræft, at kritiske sårbarheder (CVSS ≥ 7,0) blokerer for promovering til produktionsbilleder.
 #6.2.3    Level: 2    Role: D
 Bekræft, at statisk kodeanalyse kører på forgrenede eller leverandørintegrerede ML-biblioteker.
 #6.2.4    Level: 2    Role: V
 Bekræft, at forslag til opgraderinger af framework inkluderer en sikkerhedsvurdering med reference til offentlige CVE-feeds.
 #6.2.5    Level: 3    Role: V
 Bekræft, at runtime-sensorer alarmerer ved uventede indlæsninger af dynamiske biblioteker, der afviger fra den signerede SBOM.

---

### C6.3 Fastlåsning og verifikation af afhængigheder

Fastgør alle afhængigheder til uforanderlige digests og genskab builds for at garantere identiske, manipulationsfri artefakter.

 #6.3.1    Level: 1    Role: D/V
 Bekræft, at alle pakkestyringsprogrammer håndhæver versionsfastlåsning via låsefiler.
 #6.3.2    Level: 1    Role: D/V
 Bekræft, at uforanderlige digests anvendes i stedet for foranderlige tags i containerreferencer.
 #6.3.3    Level: 2    Role: D
 Bekræft, at reproducible-build-kontroller sammenligner hashes på tværs af CI-kørsler for at sikre identiske output.
 #6.3.4    Level: 2    Role: V
 Bekræft, at build-attestationer opbevares i 18 måneder for revisionssporbarhed.
 #6.3.5    Level: 3    Role: D
 Bekræft, at udløbne afhængigheder udløser automatiserede pull requests for at opdatere eller forgrene fastlåste versioner.

---

### C6.4 Forvaltning af betroede kilder

Tillad kun download af artefakter fra kryptografisk verificerede, organisationsgodkendte kilder og bloker alt andet.

 #6.4.1    Level: 1    Role: D/V
 Bekræft, at modelvægt, datasæt og containere kun downloades fra godkendte domæner eller interne registre.
 #6.4.2    Level: 1    Role: D/V
 Bekræft, at Sigstore/Cosign-signaturer validerer udgiverens identitet, før artefakter caches lokalt.
 #6.4.3    Level: 2    Role: D
 Bekræft, at egress-proxyer blokerer uautoriserede download af artefakter for at håndhæve politikken for betroede kilder.
 #6.4.4    Level: 2    Role: V
 Bekræft, at tilladelseslister for repositories gennemgås kvartalsvist med dokumentation for forretningsmæssig begrundelse for hver post.
 #6.4.5    Level: 3    Role: V
 Bekræft, at politikovertrædelser udløser karantæne af artefakter og tilbagerulning af afhængige pipeline-kørsler.

---

### C6.5 Tredjepartsdatasæt Risiko Vurdering

Evaluer eksterne datasæt for forgiftning, bias og juridisk overholdelse, og overvåg dem gennem hele deres livscyklus.

 #6.5.1    Level: 1    Role: D/V
 Bekræft, at eksterne datasæt gennemgår en vurdering af risikoen for forgiftning (f.eks. datafingeraftryk, outlier-detektion).
 #6.5.2    Level: 1    Role: D
 Bekræft, at bias-metrikker (demografisk paritet, lige muligheder) beregnes før godkendelse af datasættet.
 #6.5.3    Level: 2    Role: V
 Bekræft, at oprindelse og licensvilkår for datasæt er registreret i ML-BOM-poster.
 #6.5.4    Level: 2    Role: V
 Bekræft, at periodisk overvågning opdager drift eller korruption i hostede datasæt.
 #6.5.5    Level: 3    Role: D
 Sørg for, at ulovligt indhold (ophavsret, personligt identificerbare oplysninger) fjernes via automatisk filtrering inden træning.

---

### C6.6 Overvågning af forsyningskædeangreb

Opdag trusler mod forsyningskæden tidligt gennem CVE-feeds, revisionsloganalyse og red-team-simuleringer.

 #6.6.1    Level: 1    Role: V
 Bekræft, at CI/CD revisionslogfiler strømmer til SIEM-detektioner for unormale pakkeoverførsler eller manipulerede build-trin.
 #6.6.2    Level: 2    Role: D
 Bekræft, at beredskabsplaner for hændelsesrespons indeholder tilbageførselsprocedurer for kompromitterede modeller eller biblioteker.
 #6.6.3    Level: 3    Role: V
 Bekræft, at trussels-intel berigelses-tags markerer ML-specifikke indikatorer (f.eks. model-forgiftnings IoC’er) i alarmtriage.

---

### C6.7 ML-BOM for Model Artefakter

Generer og underskriv detaljerede ML-specifikke SBOM'er (ML-BOM'er), så downstream-forbrugere kan verificere komponentintegritet ved udrulningstidspunktet.

 #6.7.1    Level: 1    Role: D/V
 Bekræft, at hver modelartefakt udgiver en ML-BOM, der angiver datasæt, vægte, hyperparametre og licenser.
 #6.7.2    Level: 1    Role: D/V
 Bekræft, at ML-BOM-generering og Cosign-signering er automatiseret i CI og påkrævet for sammensmeltning.
 #6.7.3    Level: 2    Role: D
 Bekræft, at ML-BOM fuldstændighedskontroller afviser byggeriet, hvis nogen komponentmetadata (hash, licens) mangler.
 #6.7.4    Level: 2    Role: V
 Bekræft, at downstream-forbrugere kan forespørge ML-BOM'er via API for at validere importerede modeller ved implementeringstidspunktet.
 #6.7.5    Level: 3    Role: V
 Bekræft, at ML-BOM'er er versionskontrollerede og sammenlignede for at opdage uautoriserede ændringer.

---

### Referencer

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

## C7 Modeladfærd, outputkontrol og sikkerhedssikring

### Kontrolmål

Modeloutput skal være strukturerede, pålidelige, sikre, forklarlige og løbende overvågede i produktionen. Dette reducerer hallucinationer, privatlivslækager, skadeligt indhold og ukontrollerede handlinger, samtidig med at det øger brugertillid og overholdelse af lovgivning.

---

### C7.1 Håndhævelse af outputformat

Strenge skemaer, begrænset dekodning og efterfølgende validering stopper fejlbehæftet eller ondsindet indhold, før det spreder sig.

 #7.1.1    Level: 1    Role: D/V
 Bekræft, at svarskemaer (f.eks. JSON Schema) er angivet i systemprompten, og at hvert output automatisk valideres; ikke-konforme output udløser reparation eller afvisning.
 #7.1.2    Level: 1    Role: D/V
 Bekræft, at begrænset dekodning (stoptokens, regex, maksimale token) er aktiveret for at forhindre overflow eller prompt-injektions sidekanaler.
 #7.1.3    Level: 2    Role: D/V
 Sørg for, at nedstrøms komponenter behandler output som uautoriserede og validerer dem mod skemaer eller injektionssikre de-serialisatorer.
 #7.1.4    Level: 3    Role: V
 Bekræft, at fejludgangsbegivenheder bliver logget, ratebegrænset og vist i overvågningen.

---

### C7.2 Hallucinationsdetektion og afhjælpning

Usikkerhedsvurdering og fallback-strategier begrænser fabrikerede svar.

 #7.2.1    Level: 1    Role: D/V
 Bekræft, at token-niveau log-sandsynligheder, ensemble selvkonsistens eller finjusterede hallucinationsdetektorer tildeler en tillidsværdi til hvert svar.
 #7.2.2    Level: 1    Role: D/V
 Bekræft, at svar under en konfigurerbar tillidsgrænse udløser fallback-arbejdsgange (f.eks. retrieval-augmented generation, sekundær model eller menneskelig gennemgang).
 #7.2.3    Level: 2    Role: D/V
 Sørg for, at hallucinationshændelser bliver mærket med rodårsagsmetadata og tilført til post-mortem- og finjusteringspipelines.
 #7.2.4    Level: 3    Role: D/V
 Bekræft, at tærskler og detektorer genkalibreres efter større opdateringer af modellen eller vidensbasen.
 #7.2.5    Level: 3    Role: V
 Bekræft, at dashboard-visualiseringer overvåger hallucinationsrater.

---

### C7.3 Output-sikkerhed og privatlivsfiltrering

Politikfiltre og red-team-dækning beskytter brugere og fortrolige data.

 #7.3.1    Level: 1    Role: D/V
 Verificer, at præ- og postgenereringsklassifikatorer blokerer had, chikane, selvskade, ekstremistisk og seksuelt eksplicit indhold i overensstemmelse med politik.
 #7.3.2    Level: 1    Role: D/V
 Bekræft, at PII/PCI-detektion og automatisk redigering kører på hvert svar; overtrædelser forårsager en privatlivshændelse.
 #7.3.3    Level: 2    Role: D
 Bekræft, at fortrolighedstag (f.eks. virksomhedshemmeligheder) videreføres på tværs af modaliteter for at forhindre lækage i tekst, billeder eller kode.
 #7.3.4    Level: 3    Role: D/V
 Bekræft, at forsøg på filtreringsomgåelse eller klassificeringer med høj risiko kræver sekundær godkendelse eller brugerens genautentificering.
 #7.3.5    Level: 3    Role: D/V
 Bekræft, at filtreringsgrænser afspejler juridiske jurisdiktioner samt brugerens alder/rolle kontekst.

---

### C7.4 Begrænsning af output og handlinger

Raterestriktioner og godkendelsesporte forhindrer misbrug og overdreven autonomi.

 #7.4.1    Level: 1    Role: D
 Bekræft, at kvoter pr. bruger og pr. API-nøgle begrænser forespørgsler, tokens og omkostninger med eksponentiel tilbagekobling ved 429-fejl.
 #7.4.2    Level: 1    Role: D/V
 Bekræft, at privilegerede handlinger (filskrivninger, kodeudførelser, netværksopkald) kræver godkendelse baseret på politik eller involvering af menneske i processen.
 #7.4.3    Level: 2    Role: D/V
 Bekræft, at tværmodal konsistenskontrol sikrer, at billeder, kode og tekst genereret til den samme anmodning ikke kan bruges til at smugle ondsindet indhold.
 #7.4.4    Level: 2    Role: D
 Bekræft, at agentdelegeringsdybde, rekursionsgrænser og tilladte værktøjslister er eksplicit konfigureret.
 #7.4.5    Level: 3    Role: V
 Bekræft, at overskridelse af grænser udsender strukturerede sikkerhedshændelser til SIEM-indtagning.

---

### C7.5 Output Forklarlighed

Gennemsigtige signaler forbedrer brugerens tillid og intern fejlfinding.

 #7.5.1    Level: 2    Role: D/V
 Bekræft, at brugerorienterede tillidsvurderinger eller korte resuméer af begrundelser vises, når risikovurderingen skønner det passende.
 #7.5.2    Level: 2    Role: D/V
 Bekræft, at genererede forklaringer undgår at afsløre følsomme systemprompter eller proprietære data.
 #7.5.3    Level: 3    Role: D
 Bekræft, at systemet indfanger token-niveau log-sandsynligheder eller opmærksomhedskort og gemmer dem til autoriseret inspektion.
 #7.5.4    Level: 3    Role: V
 Sørg for, at forklaringsartefakter er versionsstyrede sammen med modeludgivelser for revisionssporbarhed.

---

### C7.6 Overvågningsintegration

Realtime observabilitet lukker løkken mellem udvikling og produktion.

 #7.6.1    Level: 1    Role: D
 Bekræft, at metrikker (skemasvigter, hallucinationsrate, toksicitet, PII-lækager, latenstid, omkostninger) sendes til en central overvågningsplatform.
 #7.6.2    Level: 1    Role: V
 Bekræft, at alarmgrænser er defineret for hver sikkerhedsmåling, med eskaleringsveje til on-call.
 #7.6.3    Level: 2    Role: V
 Bekræft, at dashboards korrelerer output-anomalier med model/version, feature-flag og ændringer i opstrømsdata.
 #7.6.4    Level: 2    Role: D/V
 Bekræft, at overvågningsdata feedbackes til genuddannelse, finjustering eller regelopdateringer inden for en dokumenteret MLOps-arbejdsgang.
 #7.6.5    Level: 3    Role: V
 Sørg for, at overvågningspipelines er penetrationstestet og adgangskontrolleret for at undgå lækage af følsomme logfiler.

---

### 7.7 Generative medier sikkerhedsforanstaltninger

Sørg for, at AI-systemer ikke genererer ulovligt, skadeligt eller uautoriseret medieindhold ved at håndhæve politikrestriktioner, outputvalidering og sporbarhed.

 #7.7.1    Level: 1    Role: D/V
 Bekræft, at systemprompter og brugervejledninger eksplicit forbyder generering af ulovligt, skadeligt eller ikke-samtykkende deepfake-medie (f.eks. billede, video, lyd).
 #7.7.2    Level: 2    Role: D/V
 Bekræft, at prompts bliver filtreret for forsøg på at generere efterligninger, seksuelt eksplicitte deepfakes eller medier, der viser rigtige individer uden samtykke.
 #7.7.3    Level: 2    Role: V
 Bekræft, at systemet bruger perceptuel hashing, vandmærke-detektion eller fingeraftryk til at forhindre uautoriseret reproduktion af ophavsretligt beskyttet materiale.
 #7.7.4    Level: 3    Role: D/V
 Bekræft, at alt genereret medie er kryptografisk underskrevet, vandmærket eller indlejret med manipulationsresistent oprindelsesmetadata til efterfølgende sporbarhed.
 #7.7.5    Level: 3    Role: V
 Bekræft, at forsøg på omgåelse (f.eks. promptforvrængning, slang, modstridende formuleringer) opdages, logges og begrænses i frekvens; gentagen misbrug rapporteres til overvågningssystemer.

### Referencer

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

## C8 Hukommelse, Embeddings og Vektordatabasesikkerhed

### Kontrolmål

Indlejringer og vektorlager fungerer som den "aktive hukommelse" i moderne AI-systemer, der løbende modtager data leveret af brugeren og bringer det tilbage i modelkontekster via Retrieval-Augmented Generation (RAG). Hvis denne hukommelse forbliver ureguleret, kan den lække personligt identificerbare oplysninger (PII), overtræde samtykke eller vendes om for at rekonstruere den oprindelige tekst. Målet med denne kontrolfamilie er at styrke hukommelsesdatapipelines og vektordatabaser, så adgang er mindst muligt privilegeret, indlejringer bevarer privatlivets fred, lagrede vektorer udløber eller kan tilbagekaldes efter behov, og at hukommelse pr. bruger aldrig forurener en anden brugers forespørgsler eller færdiggørelser.

---

### C8.1 Adgangskontroller på Hukommelse og RAG-Indices

Håndhæv detaljerede adgangskontroller på hver enkelt vektorsamling.

 #8.1.1    Level: 1    Role: D/V
 Bekræft, at række-/navneområdeniveau adgangskontrolregler begrænser indsættelse, sletning og forespørgselsoperationer pr. lejer, samling eller dokumentmærke.
 #8.1.2    Level: 1    Role: D/V
 Bekræft, at API-nøgler eller JWT'er indeholder scoped claims (f.eks. samlings-ID'er, handlingsverber) og roteres mindst kvartalsvist.
 #8.1.3    Level: 2    Role: D/V
 Bekræft, at forsøg på privilege-eskalering (f.eks. tværs af navneområders lighedsforspørgsler) opdages og logges til en SIEM inden for 5 minutter.
 #8.1.4    Level: 2    Role: D/V
 Bekræft, at vektor-DAtabasen registrerer loggen for subjekt-identifikator, operation, vektor-ID/namespace, lighedstærskel og resultatantal.
 #8.1.5    Level: 3    Role: V
 Bekræft, at adgangsbeslutninger testes for omgåelsesfejl, hver gang motorer opgraderes eller regler for indekssharding ændres.

---

### C8.2 Indlejringens oprydning og validering

Forudscreen tekst for PII, rediger eller pseudonymiser inden vektorisering, og efterbehandl eventuelt embeddings for at fjerne resterende signaler.

 #8.2.1    Level: 1    Role: D/V
 Sørg for, at personligt identificerbare oplysninger (PII) og regulerede data bliver opdaget via automatiserede klassifikatorer og maskeret, tokeniseret eller fjernet før indlejring.
 #8.2.2    Level: 1    Role: D
 Bekræft, at embedding-pipelines afviser eller isolerer input, der indeholder eksekverbar kode eller ikke-UTF-8-artefakter, som kunne forgifte indekset.
 #8.2.3    Level: 2    Role: D/V
 Bekræft, at lokal eller metrisk differentiel-privat sanitization anvendes på sætningsindlejringer, hvis afstand til enhver kendt PII-token falder under en konfigurerbar tærskel.
 #8.2.4    Level: 2    Role: V
 Bekræft, at effektiviteten af sanitization (f.eks. tilbagekaldelse af PII-redigering, semantisk drift) valideres mindst halvårligt mod benchmark-korpora.
 #8.2.5    Level: 3    Role: D/V
 Bekræft, at sanitiseringskonfigurationer er versionsstyrede, og at ændringer gennemgår kollegial gennemgang.

---

### C8.3 Hukommelsesudløb, tilbagekaldelse og sletning

GDPR "retten til at blive glemt" og lignende love kræver rettidig sletning; vektorlagre skal derfor understøtte TTL'er, permanente sletninger og tomb-stoning, så tilbagekaldte vektorer ikke kan gendannes eller genindekseres.

 #8.3.1    Level: 1    Role: D/V
 Bekræft, at hver vektor- og metadataregistrering har en TTL eller en eksplicit opbevaringsetiket, som overholdes af automatiserede oprydningsopgaver.
 #8.3.2    Level: 1    Role: D/V
 Bekræft, at brugerinitierede sletningsanmodninger fjerner vektorer, metadata, cachekopier og afledte indekser inden for 30 dage.
 #8.3.3    Level: 2    Role: D
 Bekræft, at logiske sletninger efterfølges af kryptografisk sletning af lagerblokke, hvis hardware understøtter det, eller af ødelæggelse af nøgle i nøglevault.
 #8.3.4    Level: 3    Role: D/V
 Bekræft, at udløbne vektorer er udelukket fra resultaterne af nærmeste-nabo-søgning inden for < 500 ms efter udløb.

---

### C8.4 Forebyg indlejring-inversion og lækage

Nye forsvarsmekanismer — støj-sammensætning, projektion netværk, privacy-neuron perturbation og applikationslagskryptering — kan reducere token-niveau inversion satser til under 5%.

 #8.4.1    Level: 1    Role: V
 Bekræft, at der findes en formel trusselsmodel, der dækker inversion, medlemskabs- og attribut-inferensangreb, og at denne gennemgås årligt.
 #8.4.2    Level: 2    Role: D/V
 Bekræft, at applikationslagskryptering eller søgbar kryptering beskytter vektorer mod direkte læsning af infrastrukturadministratorer eller cloud-personale.
 #8.4.3    Level: 3    Role: V
 Bekræft, at forsvarsparametrene (ε for DP, støj σ, projektionens rang k) balancerer privatliv ≥ 99 % tokenbeskyttelse og anvendelighed ≤ 3 % nøjagtighedstab.
 #8.4.4    Level: 3    Role: D/V
 Bekræft, at metrikker for inverteringsmodstand er en del af godkendelseskriterierne for modelopdateringer, med definerede budgetter for regression.

---

### C8.5 Omfangshåndhævelse for brugerspecifik hukommelse

Informationslækage mellem lejere forbliver en af de største risici ved RAG: fejlagtigt filtrerede lighedsspørgsmål kan afdække en anden kundes private dokumenter.

 #8.5.1    Level: 1    Role: D/V
 Bekræft, at hver hentningsforespørgsel efterfiltreres af lejer-/bruger-ID, før den sendes til LLM-prompten.
 #8.5.2    Level: 1    Role: D
 Bekræft, at samlingsnavne eller navne med namespace-ID'er er saltet pr. bruger eller lejer, så vektorer ikke kan kollidere på tværs af scopes.
 #8.5.3    Level: 2    Role: D/V
 Bekræft, at lighedsresultater over en konfigurerbar afstandstærskel, men uden for den kaldendes rækkevidde, bliver afvist og udløser sikkerhedsalarmer.
 #8.5.4    Level: 2    Role: V
 Bekræft, at multi-tenant stresstests simulerer modstridende forespørgsler, der forsøger at hente dokumenter uden for omfanget, og demonstrerer nul lækage.
 #8.5.5    Level: 3    Role: D/V
 Bekræft, at krypteringsnøgler er adskilt pr. lejer, hvilket sikrer kryptografisk isolation, selvom fysisk lagring deles.

---

### C8.6 Avanceret hukommelsessystem sikkerhed

Sikkerhedskontroller for avancerede hukommelsesarkitekturer, herunder episodisk, semantisk og arbejdshukommelse med specifikke isolations- og valideringskrav.

 #8.6.1    Level: 1    Role: D/V
 Bekræft, at forskellige hukommelsestyper (episodisk, semantisk, arbejdshukommelse) har isolerede sikkerhedskontekster med rollebaserede adgangskontroller, separate krypteringsnøgler og dokumenterede adgangsmønstre for hver hukommelsestype.
 #8.6.2    Level: 2    Role: D/V
 Bekræft, at processerne for hukommelseskonsolidering inkluderer sikkerhedsvalidering for at forhindre indsprøjtning af ondsindede minder gennem indholdsrensning, kildeverifikation og integritetskontrol før lagring.
 #8.6.3    Level: 2    Role: D/V
 Bekræft, at forespørgsler om hukommelsesgenfinding valideres og renses for at forhindre udtrækning af uautoriserede oplysninger gennem analyse af forespørgselsmønstre, håndhævelse af adgangskontrol og filtrering af resultater.
 #8.6.4    Level: 3    Role: D/V
 Bekræft, at hukommelsesglemning mekanismer sikkert sletter følsomme oplysninger med kryptografiske sletningsgarantier ved hjælp af nøgle-sletning, flerpassoverskrivning eller hardware-baseret sikker sletning med verificeringscertifikater.
 #8.6.5    Level: 3    Role: D/V
 Bekræft, at hukommelsessystemets integritet kontinuerligt overvåges for uautoriserede ændringer eller korruption gennem checksums, revisionslogfiler og automatiske advarsler, når hukommelsesindholdet ændres uden for normale operationer.

---

### Referencer

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

## 9 Autonom orkestrering og agentbaseret handlingssikkerhed

### Kontrolmål

Sørg for, at autonome eller multi-agent AI-systemer kun kan udføre handlinger, der er eksplicit tilsigtede, godkendte, reviderbare og inden for afgrænsede omkostnings- og risikogrænser. Dette beskytter mod trusler som kompromittering af autonome systemer, værktøjsmisbrug, agent-loop-detektion, kommunikationskapring, identitetsspoofing, sværmmemanipulation og intentionmanipulation.

---

### 9.1 Agent Opgaveplanlægning & Rekursionsbudgetter

Begræns rekursive planer og pålæg menneskelige kontrolpunkter for privilegerede handlinger.

 #9.1.1    Level: 1    Role: D/V
 Verificer, at maksimal rekursionsdybde, bredde, væg-ur tid, tokens og monetære omkostninger pr. agentudførelse er centralt konfigureret og versionsstyret.
 #9.1.2    Level: 1    Role: D/V
 Bekræft, at privilegerede eller irreversible handlinger (f.eks. kodeforpligtelser, finansielle overførsler) kræver eksplicit menneskelig godkendelse via en reviderbar kanal, før de udføres.
 #9.1.3    Level: 2    Role: D
 Bekræft, at realtidsressourcemonitorer udløser afbrydelse via kredsløbsafbryder, når nogen budgetgrænse overskrides, hvilket stopper yderligere opgaveudvidelse.
 #9.1.4    Level: 2    Role: D/V
 Bekræft, at kredsløbsafbryderhændelser logges med agent-ID, udløsende betingelse og fanget planstatus til retsmedicinsk gennemgang.
 #9.1.5    Level: 3    Role: V
 Sørg for, at sikkerhedstests dækker scenarier med budgetudmattelse og løber løbsk plan, og bekræft sikker standsning uden datatab.
 #9.1.6    Level: 3    Role: D
 Bekræft, at budgetpolitikker er udtrykt som politik-som-kode og håndhæves i CI/CD for at forhindre konfigurationsdrift.

---

### 9.2 Værktøjs-plugin Sandboxning

Isolér værktøjsinteraktioner for at forhindre uautoriseret systems adgang eller kodeeksekvering.

 #9.2.1    Level: 1    Role: D/V
 Bekræft, at hvert værktøj/plugin kører inden for et OS-, container- eller WASM-niveau sandbox med mindst privilegerede filsystem-, netværks- og systemkaldspolitikker.
 #9.2.2    Level: 1    Role: D/V
 Bekræft, at grænser for ressourcer i sandkassen (CPU, hukommelse, disk, netværksudgang) og udførelsestidsbegrænsninger håndhæves og logges.
 #9.2.3    Level: 2    Role: D/V
 Bekræft, at værktøjsbinærfiler eller deskriptorer er digitalt signeret; signaturer valideres inden indlæsning.
 #9.2.4    Level: 2    Role: V
 Bekræft, at sandkassetelemetri strømmer til et SIEM; afvigelser (f.eks. forsøg på udgående forbindelser) udløser alarmer.
 #9.2.5    Level: 3    Role: V
 Sørg for, at højrisiko-plugins gennemgår sikkerhedsvurdering og penetrationstest, inden de tages i brug i produktionen.
 #9.2.6    Level: 3    Role: D/V
 Bekræft, at forsøg på at undslippe sandboxen automatisk blokeres, og at den krænkende plugin sættes i karantæne i afventning af undersøgelse.

---

### 9.3 Autonom Løkke og Omkostningsbegrænsning

Registrer og stop ukontrolleret agent-til-agent rekursion og omkostningseksplosioner.

 #9.3.1    Level: 1    Role: D/V
 Bekræft, at opkald mellem agenter inkluderer en hop-grænse eller TTL, som runtime-miljøet nedskriver og håndhæver.
 #9.3.2    Level: 2    Role: D
 Sørg for, at agenter opretholder en unik invocations-graf-ID for at opdage selv-invokation eller cykliske mønstre.
 #9.3.3    Level: 2    Role: D/V
 Bekræft, at kumulative beregningsenheds- og forbrugsoptællere føres for hver anmodningskæde; overskridelse af grænsen afbryder kæden.
 #9.3.4    Level: 3    Role: V
 Bekræft, at formel analyse eller modelkontrol demonstrerer fravær af ubegrænset rekursion i agentprotokoller.
 #9.3.5    Level: 3    Role: D
 Bekræft, at loop-afbrudsbegivenheder genererer advarsler og leverer metrics til løbende forbedring.

---

### 9.4 Protokolniveau Misbrugsbeskyttelse

Sikre kommunikationskanaler mellem agenter og eksterne systemer for at forhindre overtagelse eller manipulation.

 #9.4.1    Level: 1    Role: D/V
 Bekræft, at alle beskeder mellem agent og værktøj samt agent og agent er autentificerede (f.eks. gensidig TLS eller JWT) og krypterede fra ende til ende.
 #9.4.2    Level: 1    Role: D
 Sørg for, at skemaer bliver strengt valideret; ukendte felter eller fejlagtige beskeder afvises.
 #9.4.3    Level: 2    Role: D/V
 Bekræft, at integritetskontroller (MAC'er eller digitale signaturer) dækker hele beskedens nyttelast, inklusive værktøjsparametre.
 #9.4.4    Level: 2    Role: D
 Bekræft, at gengivelsesbeskyttelse (noncer eller tidsstempelvinduer) håndhæves på protokollaget.
 #9.4.5    Level: 3    Role: V
 Bekræft, at protokolimplementeringer gennemgår fuzzing og statisk analyse for injektions- eller deserialiseringsfejl.

---

### 9.5 Agentidentitet & manipulationssikkerhed

Sørg for, at handlinger kan tilskrives, og at ændringer kan opdages.

 #9.5.1    Level: 1    Role: D/V
 Bekræft, at hver agentinstans har en unik kryptografisk identitet (nøglepar eller hardwareforankret legitimationsoplysning).
 #9.5.2    Level: 2    Role: D/V
 Bekræft, at alle agenthandlinger er underskrevet og tidsstemplet; logfiler inkluderer underskriften for ikke-benægtelse.
 #9.5.3    Level: 2    Role: V
 Bekræft, at manipulationssikre logs gemmes i et append-only eller write-once medie.
 #9.5.4    Level: 3    Role: D
 Bekræft, at identitetsnøgler roterer efter en defineret tidsplan og ved indikatorer for kompromittering.
 #9.5.5    Level: 3    Role: D/V
 Bekræft, at spoofing- eller nøglekonfliktforsøg straks udløser karantæne af den berørte agent.

---

### 9.6 Risiko-reduktion ved multi-agent-sværm

Afhjælp risici ved kollektiv adfærd gennem isolation og formel sikkerhedsmodellering.

 #9.6.1    Level: 1    Role: D/V
 Bekræft, at agenter, der opererer i forskellige sikkerhedsdomaener, kører i isolerede runtime-sandkasser eller netværkssegmenter.
 #9.6.2    Level: 3    Role: V
 Bekræft, at sværmbeslutninger er modelleret og formelt verificeret for livskraft og sikkerhed før implementering.
 #9.6.3    Level: 3    Role: D
 Verificer, at runtime-overvågninger opdager fremvoksende usikre mønstre (f.eks. oscillationer, dødlåse) og iværksætter korrigerende handlinger.

---

### 9.7 Bruger- og værktøjsautentifikation / autorisation

Implementer robuste adgangskontroller for enhver agentudløst handling.

 #9.7.1    Level: 1    Role: D/V
 Bekræft, at agenter autentificerer som førsteklasses aktører over for downstream-systemer og aldrig genbruger slutbrugerens legitimationsoplysninger.
 #9.7.2    Level: 2    Role: D
 Bekræft, at detaljerede autorisationspolitikker begrænser, hvilke værktøjer en agent må påkalde, og hvilke parametre den må levere.
 #9.7.3    Level: 2    Role: V
 Bekræft, at rettighedstjek genvurderes ved hvert kald (kontinuerlig autorisation), ikke kun ved sessionens start.
 #9.7.4    Level: 3    Role: D
 Bekræft, at delegerede privilegier udløber automatisk og kræver fornyet samtykke efter timeout eller ændring af omfang.

---

### 9.8 Agent-til-Agent Kommunikationssikkerhed

Krypter og integritetsbeskyt alle beskeder mellem agenter for at forhindre aflytning og manipulation.

 #9.8.1    Level: 1    Role: D/V
 Bekræft, at gensidig autentificering og kryptering med perfekt fremadrettet hemmeligholdelse (f.eks. TLS 1.3) er obligatoriske for agentkanaler.
 #9.8.2    Level: 1    Role: D
 Bekræft, at beskedens integritet og oprindelse valideres, før den behandles; fejl udløser alarmer og forkaster beskeden.
 #9.8.3    Level: 2    Role: D/V
 Bekræft, at kommunikationsmetadata (tidsstempler, sekvensnumre) logges for at understøtte retsmedicinsk rekonstruktion.
 #9.8.4    Level: 3    Role: V
 Bekræft, at formel verifikation eller modelkontrol bekræfter, at protokoltilstandsmaskiner ikke kan drives ind i usikre tilstande.

---

### 9.9 Intentionverifikation og håndhævelse af begrænsninger

Bekræft, at agentens handlinger stemmer overens med brugerens angivne intention og systemets begrænsninger.

 #9.9.1    Level: 1    Role: D
 Bekræft, at pre-eksekveringsbegrænsningsløsere kontrollerer foreslåede handlinger op imod hardkodede sikkerheds- og politikregler.
 #9.9.2    Level: 2    Role: D/V
 Bekræft, at handlinger med stor indvirkning (økonomiske, destruktive, privatlivsfølsomme) kræver eksplicit bekræftelse af hensigten fra den initierende bruger.
 #9.9.3    Level: 2    Role: V
 Bekræft, at efterbetingelsestjek validerer, at fuldførte handlinger opnåede tilsigtede effekter uden bivirkninger; uoverensstemmelser udløser tilbagerulning.
 #9.9.4    Level: 3    Role: V
 Bekræft, at formelle metoder (f.eks. modelkontrol, teorembevis) eller egenskabsbaserede tests viser, at agentplaner opfylder alle erklærede begrænsninger.
 #9.9.5    Level: 3    Role: D
 Bekræft, at hændelser med formåls-mismatch eller overtrædelse af begrænsninger fodrer kontinuerlige forbedringscyklusser og deling af trusselsintelligens.

---

### 9.10 Agentbegrænsningsstrategi Sikkerhed

Sikker valg og udførelse af forskellige ræsonnementstrategier, herunder ReAct, Chain-of-Thought og Tree-of-Thoughts tilgange.

 #9.10.1    Level: 1    Role: D/V
 Bekræft, at valg af ræsonnementstrategi bruger deterministiske kriterier (inputkompleksitet, opgavetype, sikkerhedskontekst), og at identiske input giver identiske strategivalg inden for samme sikkerhedskontekst.
 #9.10.2    Level: 1    Role: D/V
 Bekræft, at hver ræsonneringsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikeret inputvalidering, outputrensning og eksekveringstidsgrænser specifikt til dens kognitive tilgang.
 #9.10.3    Level: 2    Role: D/V
 Sørg for, at overgange i ræsonneringsstrategi bliver logget med komplet kontekst, inklusive inputkarakteristika, værdier for udvælgelseskriterier og udførelsesmetadata, til rekonstruktion af revisionsspor.
 #9.10.4    Level: 2    Role: D/V
 Bekræft, at Tree-of-Thoughts-ræsonnering inkluderer grenbeskæringsmekanismer, der afslutter udforskning, når politikovertrædelser, ressourcebegrænsninger eller sikkerhedsgrænser opdages.
 #9.10.5    Level: 2    Role: D/V
 Bekræft, at ReAct (Reason-Act-Observe) cyklusser inkluderer valideringskontrolpunkter i hver fase: verifikation af ræsonnementstrin, godkendelse af handling og sanitering af observation, før der fortsættes.
 #9.10.6    Level: 3    Role: D/V
 Bekræft, at præstationsmålinger for ræsonneringsstrategien (eksekveringstid, ressourceforbrug, outputkvalitet) overvåges med automatiserede alarmer, når målingerne afviger ud over konfigurerede grænseværdier.
 #9.10.7    Level: 3    Role: D/V
 Verificer, at hybride ræsonnementstilgange, der kombinerer flere strategier, opretholder inputvalidering og outputbegrænsninger for alle de enkelte strategier uden at omgå nogen sikkerhedskontroller.
 #9.10.8    Level: 3    Role: D/V
 Bekræft, at strategisikkerhedstestning omfatter fuzzing med fejlbehæftede input, modstridende anmodninger designet til at tvinge strategiskift, samt grænsetilstandstestning for hver kognitiv tilgang.

---

### 9.11 Agentens livscyklusstyring og sikkerhed

Sikker agentinitialisering, tilstandsovergange og afslutning med kryptografiske revisionsspor og definerede genoprettelsesprocedurer.

 #9.11.1    Level: 1    Role: D/V
 Bekræft, at agentinitialisering inkluderer etablering af kryptografisk identitet med hardware-understøttede legitimationsoplysninger og uforanderlige opstartsrevisionslogs, der indeholder agent-ID, tidsstempel, konfigurationshash og initialiseringsparametre.
 #9.11.2    Level: 2    Role: D/V
 Bekræft, at agentens tilstandsovergange er kryptografisk underskrevet, tidsstemplet og logget med fuldstændig kontekst, inklusive udløsende begivenheder, tidligere tilstandshash, ny tilstandshash og udførte sikkerhedsvalideringer.
 #9.11.3    Level: 2    Role: D/V
 Bekræft, at agentens nedlukningsprocedurer inkluderer sikker hukommelsesrydning ved hjælp af kryptografisk sletning eller flerpasset overskrivning, tilbagekaldelse af legitimationsoplysninger med underretning til certifikatmyndigheden samt generering af manipulationssikre afslutningscertifikater.
 #9.11.4    Level: 3    Role: D/V
 Bekræft, at agentens genoprettelsesmekanismer validerer tilstandsintegritet ved hjælp af kryptografiske kontrolsummer (minimum SHA-256) og ruller tilbage til kendte gode tilstande, når der opdages korruption, med automatiske advarsler og krav om manuel godkendelse.
 #9.11.5    Level: 3    Role: D/V
 Bekræft, at agentens vedholdenhedsmekanismer krypterer følsomme tilstandsdata med AES-256-nøgler per agent og implementerer sikker nøglerotation efter konfigurerbare tidsplaner (maksimalt 90 dage) med uafbrudt implementering.

---

### 9.12 Værktøjsintegrationssikkerhedsramme

Sikkerhedskontroller for dynamisk indlæsning af værktøjer, udførelse og resultatvalidering med definerede risikovurderings- og godkendelsesprocesser.

 #9.12.1    Level: 1    Role: D/V
 Bekræft, at værktøjsbeskrivelser inkluderer sikkerhedsmetadata, der specificerer nødvendige privilegier (læs/skriv/udfør), risikoniveauer (lav/mellem/høj), ressourcelimiter (CPU, hukommelse, netværk) samt valideringskrav dokumenteret i værktøjsmanifest.
 #9.12.2    Level: 1    Role: D/V
 Bekræft, at værktøjets udførelsesresultater valideres mod forventede skemaer (JSON-skema, XML-skema) og sikkerhedspolitikker (outputrensning, dataklassificering), inden integration med tidsbegrænsninger og fejlbehandlingsprocedurer.
 #9.12.3    Level: 2    Role: D/V
 Bekræft, at værktøjsinteraktionslogfiler indeholder detaljeret sikkerhedskontekst, herunder brug af privilegier, datatilgangsmønstre, eksekveringstid, ressourceforbrug og returkoder med struktureret logning til SIEM-integration.
 #9.12.4    Level: 2    Role: D/V
 Bekræft, at mekanismer til dynamisk værktøjsindlæsning validerer digitale signaturer ved hjælp af PKI-infrastruktur og implementerer sikre indlæsningsprotokoller med sandkasse-isolation og tilladelsesverifikation før udførelse.
 #9.12.5    Level: 3    Role: D/V
 Bekræft, at værktøjssikkerhedsvurderinger automatisk udløses for nye versioner med obligatoriske godkendelsesgate, inklusive statisk analyse, dynamisk test og sikkerhedsteamets gennemgang med dokumenterede godkendelseskriterier og SLA-krav.

---

#### Referencer

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

## 10 Modstandskraft mod angreb og beskyttelse af privatlivets fred

### Kontrolmål

Sørg for, at AI-modeller forbliver pålidelige, privatlivsbeskyttende og modstandsdygtige over for misbrug, når de udsættes for undvigelse, inferens, udtrækning eller forgiftningsangreb.

---

### 10.1 Modeljustering og sikkerhed

Beskyt mod skadelige eller politikovertrædende output.

 #10.1.1    Level: 1    Role: D/V
 Bekræft, at en test-pakke for justering (red-team prompts, jailbreak-tests, uautoriseret indhold) er versionsstyret og køres ved hver modeludgivelse.
 #10.1.2    Level: 1    Role: D
 Bekræft, at afvisnings- og sikker-afslutnings-værn er håndhævet.
 #10.1.3    Level: 2    Role: D/V
 Bekræft, at en automatiseret evaluator måler andelen af skadeligt indhold og markerer tilbagefald, der overskrider en fastsat grænse.
 #10.1.4    Level: 2    Role: D
 Bekræft, at mod-jailbreak træning er dokumenteret og reproducerbar.
 #10.1.5    Level: 3    Role: V
 Bekræft, at formelle beviser for overholdelse af politikker eller certificeret overvågning dækker kritiske områder.

---

### 10.2 Modstand mod modstandseksempler

Øg modstandsdygtigheden over for manipulerede input. Robust fjendtlig træning og benchmark scoring er den nuværende bedste praksis.

 #10.2.1    Level: 1    Role: D
 Kontroller, at projektets repositories indeholder konfigurationer til modstandsdygtig træning med reproducerbare frø.
 #10.2.2    Level: 2    Role: D/V
 Bekræft, at detektionssystemet for adversariale eksempler udløser blokeringsadvarsler i produktionspipeline.
 #10.2.4    Level: 3    Role: V
 Bekræft, at certifikatbeviser for certificeret robusthed eller intervalgrænsecertifikater dækker mindst de vigtigste kritiske klasser.
 #10.2.5    Level: 3    Role: V
 Bekræft, at regressions-tests bruger adaptive angreb for at sikre, at der ikke er noget målbar tab af robusthed.

---

### 10.3 Afbødning af medlemsinference

Begræns evnen til at afgøre, om en post var i træningsdataene. Differential privacy og maskering af konfidensscore forbliver de mest effektive kendte forsvar.

 #10.3.1    Level: 1    Role: D
 Bekræft, at per-forespørgsels entropiregulering eller temperaturskalering reducerer overmodige forudsigelser.
 #10.3.2    Level: 2    Role: D
 Bekræft, at træningen anvender ε-bundet differentiabel privat optimering for følsomme datasæt.
 #10.3.3    Level: 2    Role: V
 Bekræft, at angrebssimulationer (shadow-model eller black-box) viser angrebs-AUC ≤ 0,60 på tilbageholdte data.

---

### 10.4 Modstandsdygtighed over for modelinversion

Forhindre rekonstruktion af private attributter. Senere undersøgelser understreger outputtruncering og DP-garantier som praktiske forsvar.

 #10.4.1    Level: 1    Role: D
 Bekræft, at følsomme attributter aldrig bliver direkte vist; hvor det er nødvendigt, brug segmenter eller envejs transformationer.
 #10.4.2    Level: 1    Role: D/V
 Bekræft, at forespørgselsratebegrænsninger begrænser gentagne adaptive forespørgsler fra den samme enhed.
 #10.4.3    Level: 2    Role: D
 Bekræft, at modellen er trænet med privatlivsbevarende støj.

---

### 10.5 Forsvar mod modeludtrækning

Registrer og afskær uautoriseret kloning. Vandmærkning og analyse af forespørgselsmønstre anbefales.

 #10.5.1    Level: 1    Role: D
 Sørg for, at inferens-gateways håndhæver globale og API-nøgle-specifikke hastighedsgrænser, der er tilpasset modellens memoreringstærskel.
 #10.5.2    Level: 2    Role: D/V
 Bekræft, at query-entropi og input-pluralitet-statistikker fodrer en automatiseret ekstraktionsdetektor.
 #10.5.3    Level: 2    Role: V
 Bekræft, at skrøbelige eller probabilistiske vandmærker kan bevises med p < 0,01 i ≤ 1.000 forespørgsler mod en mistænkt klon.
 #10.5.4    Level: 3    Role: D
 Bekræft, at vandmærkenøgler og udløsningssæt gemmes i en hardware-sikkerhedsmodul og roteres årligt.
 #10.5.5    Level: 3    Role: V
 Bekræft, at ekstraktions-alarm hændelser inkluderer problematiske forespørgsler og er integreret med hændelses-respons playbooks.

---

### 10.6 Påvisning af forgiftede data under inferenstid

Identificer og neutraliser tilbagelåste eller forgiftede input.

 #10.6.1    Level: 1    Role: D
 Verifier, at inputdataene passerer gennem en anomalidetektor (f.eks. STRIP, konsistensscoring) inden modelinferenz.
 #10.6.2    Level: 1    Role: V
 Bekræft, at detektortærskler er justeret på rene/forurenede valideringssæt for at opnå mindre end 5% falske positiver.
 #10.6.3    Level: 2    Role: D
 Bekræft, at input, der er markeret som forgiftede, udløser blød blokering og menneskelig gennemgangsarbejdsgange.
 #10.6.4    Level: 2    Role: V
 Bekræft, at detektorer bliver stresstestet med adaptive, triggerløse bagdørsangreb.
 #10.6.5    Level: 3    Role: D
 Bekræft, at effektiviteten af detektionsmålinger logges og periodisk genvurderes med ny trusselsintelligens.

---

### 10.7 Dynamisk tilpasning af sikkerhedspolitik

Opdateringer af sikkerhedspolitikker i realtid baseret på trusselsinformation og adfærdsanalyse.

 #10.7.1    Level: 1    Role: D/V
 Bekræft, at sikkerhedspolitikker kan opdateres dynamisk uden genstart af agenten, samtidig med at politikversionens integritet opretholdes.
 #10.7.2    Level: 2    Role: D/V
 Bekræft, at politikopdateringer er kryptografisk underskrevet af autoriseret sikkerhedspersonale og valideret før anvendelse.
 #10.7.3    Level: 2    Role: D/V
 Bekræft, at dynamiske politikændringer logges med fulde revisionsspor inklusive begrundelse, godkendelseskæder og tilbageførselsprocedurer.
 #10.7.4    Level: 3    Role: D/V
 Bekræft, at adaptive sikkerhedsmekanismer justerer trusselsdetektionsfølsomheden baseret på risikokontekst og adfærdsmønstre.
 #10.7.5    Level: 3    Role: D/V
 Sørg for, at beslutninger om politikanpassning er forståelige og inkluderer spor af beviser til gennemgang af sikkerhedsteamet.

---

### 10.8 Refleksionsbaseret sikkerhedsanalyse

Sikkerhedsvalidering gennem agentens selvrefleksion og metakognitiv analyse.

 #10.8.1    Level: 1    Role: D/V
 Bekræft, at agentens refleksionsmekanismer inkluderer en sikkerhedsorienteret selvvurdering af beslutninger og handlinger.
 #10.8.2    Level: 2    Role: D/V
 Verificer, at refleksionsoutput valideres for at forhindre manipulation af selvvurderingsmekanismer ved hjælp af modstridende input.
 #10.8.3    Level: 2    Role: D/V
 Bekræft, at meta-kognitiv sikkerhedsanalyse identificerer potentiel bias, manipulation eller kompromis i agentens ræsonneringsprocesser.
 #10.8.4    Level: 3    Role: D/V
 Bekræft, at sikkerhedsadvarsler baseret på refleksion udløser forbedret overvågning og potentielle arbejdsgange for menneskelig indgriben.
 #10.8.5    Level: 3    Role: D/V
 Bekræft, at kontinuerlig læring fra sikkerhedsreflektioner forbedrer trusselsdetektion uden at forringe legitim funktionalitet.

---

### 10.9 Evolution og Selvforbedringssikkerhed

Sikkerhedskontroller for agentsystemer, der er i stand til selvmodifikation og evolution.

 #10.9.1    Level: 1    Role: D/V
 Bekræft, at selvmodificeringsfunktioner er begrænset til udpegede sikre områder med formelle verifikationsgrænser.
 #10.9.2    Level: 2    Role: D/V
 Sørg for, at forslag til evolution gennemgår en vurdering af sikkerhedsmæssig indvirkning før implementering.
 #10.9.3    Level: 2    Role: D/V
 Bekræft, at selvforbedringsmekanismer inkluderer tilbageførselsfunktioner med integritetsverifikation.
 #10.9.4    Level: 3    Role: D/V
 Bekræft, at meta-læringssikkerhed forhindrer ondsindet manipulation af forbedringsalgoritmer.
 #10.9.5    Level: 3    Role: D/V
 Bekræft, at rekursiv selvforbedring er begrænset af formelle sikkerhedskrav med matematiske beviser for konvergens.

---

#### Referencer

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

## 11 Beskyttelse af privatliv og håndtering af personlige data

### Kontrolmål

Oprethold strenge privatlivsgarantier gennem hele AI-livscyklussen—indsamling, træning, inferens og hændelsesrespons—så persondata kun behandles med klar samtykke, mindst nødvendigt omfang, påviselig sletning og formelle privatlivsgarantier.

---

### 11.1 Anonymisering og dataminimering

 #11.1.1    Level: 1    Role: D/V
 Bekræft, at direkte og næsten-identifikatorer er fjernet eller hashet.
 #11.1.2    Level: 2    Role: D/V
 Bekræft, at automatiserede revisioner måler k-anonymitet/l-diversitet og giver alarm, når tærskler falder under politikken.
 #11.1.3    Level: 2    Role: V
 Bekræft, at modelrapporterne om funktionsvigtighed viser, at der ikke er nogen lækage af identifikatorer ud over ε = 0,01 gensidig information.
 #11.1.4    Level: 3    Role: V
 Bekræft, at formelle beviser eller certificering af syntetiske data viser, at risikoen for genidentifikation er ≤ 0,05, selv under koblingsangreb.

---

### 11.2 Retten til at blive glemt og håndhævelse af sletning

 #11.2.1    Level: 1    Role: D/V
 Sørg for, at sletningsanmodninger for dataemner spredes til rådatasæt, checkpoints, indlejringer, logfiler og sikkerhedskopier inden for serviceaftaler på under 30 dage.
 #11.2.2    Level: 2    Role: D
 Bekræft, at "machine-unlearning"-rutiner fysisk genuddanner eller approximativt fjerner ved hjælp af certificerede unlearning-algoritmer.
 #11.2.3    Level: 2    Role: V
 Bekræft, at evaluering med skygge-modeller beviser, at glemte poster påvirker mindre end 1 % af outputtene efter aflæring.
 #11.2.4    Level: 3    Role: V
 Bekræft, at slettehændelser logges uforanderligt og er reviderbare for tilsynsmyndigheder.

---

### 11.3 Differentielt privatlivsbeskyttelse sikkerhedsforanstaltninger

 #11.3.1    Level: 2    Role: D/V
 Bekræft, at dashboards for privatlivstabskonti advarer, når den kumulative ε overskrider politikgrænser.
 #11.3.2    Level: 2    Role: V
 Bekræft, at black-box privatlivsrevisioner estimerer ε̂ inden for 10 % af den deklarerede værdi.
 #11.3.3    Level: 3    Role: V
 Bekræft, at formelle beviser dækker alle eftertrænings-justeringer og indlejringer.

---

### 11.4 Formålsbegrænsning og beskyttelse mod omfangsudvidelse

 #11.4.1    Level: 1    Role: D
 Bekræft, at hvert datasæt og modelcheckpoint bærer en maskinlæselig formålsmærkning, der er i overensstemmelse med den oprindelige tilladelse.
 #11.4.2    Level: 1    Role: D/V
 Bekræft, at runtime-overvågning registrerer forespørgsler, der er inkonsistente med det erklærede formål, og udløser blød afvisning.
 #11.4.3    Level: 3    Role: D
 Bekræft, at politik-som-kode-gates blokerer for genudrulning af modeller til nye domæner uden DPIA-gennemgang.
 #11.4.4    Level: 3    Role: V
 Bekræft, at formelle sporbarhedsdokumentation viser, at hver enkelt personlige data livscyklus forbliver inden for det samtykkede omfang.

---

### 11.5 Samtykkehåndtering og lovlig grundlag for sporing

 #11.5.1    Level: 1    Role: D/V
 Bekræft, at en samtykkeadministrationsplatform (CMP) registrerer opt-in-status, formål og opbevaringsperiode pr. registreret person.
 #11.5.2    Level: 2    Role: D
 Bekræft, at API'er eksponerer samtykketokens; modeller skal validere tokenets omfang før inferens.
 #11.5.3    Level: 2    Role: D/V
 Bekræft, at afvist eller tilbagetrukket samtykke stopper behandlingspipelines inden for 24 timer.

---

### 11.6 Fødereret læring med privatlivskontroller

 #11.6.1    Level: 1    Role: D
 Bekræft, at klientopdateringer anvender lokal differential privacy-støjtilføjelse før aggregering.
 #11.6.2    Level: 2    Role: D/V
 Bekræft, at træningsmetrikker er differentielt private og aldrig afslører enkeltklienters tab.
 #11.6.3    Level: 2    Role: V
 Bekræft, at forgiftningsresistent aggregering (f.eks. Krum/Trimmed-Mean) er aktiveret.
 #11.6.4    Level: 3    Role: V
 Bekræft, at formelle beviser demonstrerer det samlede ε-budget med mindre end 5 utilsigtet tab.

---

#### Referencer

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

## C12 Overvågning, Logning og Anomali-detektion

### Kontrolmål

Denne sektion indeholder krav til at levere realtids- og retsmedicinsk synlighed i, hvad modellen og andre AI-komponenter ser, gør og returnerer, så trusler kan opdages, prioriteres og læres af.

### C12.1 Anmodning og svarlogning

 #12.1.1    Level: 1    Role: D/V
 Bekræft, at alle brugerforespørgsler og modelresponser logges med passende metadata (f.eks. tidsstempel, bruger-ID, session-ID, modelversion).
 #12.1.2    Level: 1    Role: D/V
 Bekræft, at logs gemmes i sikre, adgangskontrollerede lagre med passende opbevaringspolitikker og backup-procedurer.
 #12.1.3    Level: 1    Role: D/V
 Bekræft, at loglagringssystemer implementerer kryptering både i hviletilstand og under overførsel for at beskytte følsomme oplysninger indeholdt i logfiler.
 #12.1.4    Level: 1    Role: D/V
 Bekræft, at følsomme data i prompts og output automatisk bliver redigeret eller maskeret, før de logges, med konfigurerbare redigeringsregler for personligt identificerbare oplysninger (PII), adgangsoplysninger og proprietære oplysninger.
 #12.1.5    Level: 2    Role: D/V
 Bekræft, at beslutninger om politik og sikkerhedsfiltrering registreres med tilstrækkelig detaljeringsgrad for at muliggøre revision og fejlfinding af indholdsmoderationssystemer.
 #12.1.6    Level: 2    Role: D/V
 Bekræft, at logintegriteten er beskyttet gennem f.eks. kryptografiske signaturer eller skrivebeskyttet lagring.

---

### C12.2 Misbrugsdetektion og advarsler

 #12.2.1    Level: 1    Role: D/V
 Bekræft, at systemet opdager og advarer om kendte jailbreak-mønstre, forsøg på promptinjektion og modstridende input ved brug af signaturbaseret detektion.
 #12.2.2    Level: 1    Role: D/V
 Bekræft, at systemet integreres med eksisterende Security Information and Event Management (SIEM) platforme ved brug af standard logformater og protokoller.
 #12.2.3    Level: 2    Role: D/V
 Bekræft, at berigede sikkerhedshændelser inkluderer AI-specifik kontekst såsom modelidentifikatorer, tillidsvurderinger og beslutninger om sikkerhedsfiltre.
 #12.2.4    Level: 2    Role: D/V
 Bekræft, at adfærdsbaseret anomali-detektion identificerer usædvanlige samtalemønstre, overdrevne gentagelsesforsøg eller systematiske sonderingsadfærd.
 #12.2.5    Level: 2    Role: D/V
 Bekræft, at mekanismer til realtidsalarmering underretter sikkerhedsteams, når potentielle overtrædelser af politikker eller angrebsforsøg opdages.
 #12.2.6    Level: 2    Role: D/V
 Bekræft, at brugerdefinerede regler er inkluderet til at opdage AI-specifikke trusselsmønstre, herunder koordinerede jailbreak-forsøg, promptinjektionskampagner og modeludtrækningsangreb.
 #12.2.7    Level: 3    Role: D/V
 Bekræft, at automatiserede hændelsesresponsarbejdsgange kan isolere kompromitterede modeller, blokere ondsindede brugere og eskalere kritiske sikkerhedshændelser.

---

### C12.3 Modeldrejningsdetektion

 #12.3.1    Level: 1    Role: D/V
 Bekræft, at systemet overvåger grundlæggende ydelsesmetrikker som nøjagtighed, konfidensscores, latenstid og fejlprocenter på tværs af modelversioner og tidsperioder.
 #12.3.2    Level: 2    Role: D/V
 Bekræft, at automatiserede alarmer udløses, når ydelsesmålinger overskrider foruddefinerede nedbrydningstærskler eller afviger signifikant fra baselinjer.
 #12.3.3    Level: 2    Role: D/V
 Bekræft, at hallucinationsdetektionsmonitorer identificerer og markerer tilfælde, hvor modeloutput indeholder faktuelt ukorrekte, inkonsistente eller fabrikerede oplysninger.

---

### C12.4 Ydeevne- og adfærdstelemetri

 #12.4.1    Level: 1    Role: D/V
 Bekræft, at operationelle målinger, herunder forespørgselsforsinkelse, tokenforbrug, hukommelsesforbrug og gennemløb, løbende indsamles og overvåges.
 #12.4.2    Level: 1    Role: D/V
 Bekræft, at succes- og fejlrater registreres med kategorisering af fejltyper og deres grundårsager.
 #12.4.3    Level: 2    Role: D/V
 Bekræft, at overvågning af ressourceudnyttelse inkluderer GPU/CPU-brug, hukommelsesforbrug og lagringskrav med alarmer ved overskridelse af tærskelværdier.

---

### C12.5 AI-hændelsesreaktionsplanlægning og udførelse

 #12.5.1    Level: 1    Role: D/V
 Sørg for, at beredskabsplaner for hændelsesrespons specifikt adresserer AI-relaterede sikkerhedshændelser, herunder modelkompromittering, dataforgiftning og adversariale angreb.
 #12.5.2    Level: 2    Role: D/V
 Sørg for, at hændelsesreaktionsteams har adgang til AI-specifikke retsmedicinske værktøjer og ekspertise til at undersøge modeladfærd og angrebsvektorer.
 #12.5.3    Level: 3    Role: D/V
 Bekræft, at efterhændelsesanalysen inkluderer overvejelser om modelgenuddannelse, opdateringer af sikkerhedsfiltre og integration af læringserfaringer i sikkerhedskontroller.

---

### C12.5 AI Ydeevnedæmpningsdetektion

Overvåg og registrer forringelse i AI-modelens ydeevne og kvalitet over tid.

 #12.5.1    Level: 1    Role: D/V
 Sørg for, at modelens nøjagtighed, præcision, recall og F1-score løbende overvåges og sammenlignes med baseline-grænseværdier.
 #12.5.2    Level: 1    Role: D/V
 Bekræft, at data-driftdetektion overvåger ændringer i inputfordelingen, som kan påvirke modellens ydeevne.
 #12.5.3    Level: 2    Role: D/V
 Bekræft, at konceptskreddetektion identificerer ændringer i forholdet mellem input og forventede output.
 #12.5.4    Level: 2    Role: D/V
 Bekræft, at ydelsesforringelse udløser automatiserede alarmer og igangsætter workflows til gen-træning eller udskiftning af modellen.
 #12.5.5    Level: 3    Role: V
 Bekræft, at analyse af årsager til degradering korrelerer præstationsfald med datændringer, infrastrukturproblemer eller eksterne faktorer.

---

### C12.6 DAG-visualisering og arbejdsgangssikkerhed

Beskyt arbejdsgangsvisualiseringssystemer mod informationslækage og manipulationsangreb.

 #12.6.1    Level: 1    Role: D/V
 Bekræft, at DAG-visualiseringsdata renses for at fjerne følsomme oplysninger inden lagring eller overførsel.
 #12.6.2    Level: 1    Role: D/V
 Bekræft, at adgangskontroller for workflow-visualisering sikrer, at kun autoriserede brugere kan se agentens beslutningsstier og ræsonnementsspor.
 #12.6.3    Level: 2    Role: D/V
 Bekræft, at DAG-dataintegritet er beskyttet gennem kryptografiske signaturer og manipulation-synlige lagringsmekanismer.
 #12.6.4    Level: 2    Role: D/V
 Bekræft, at workflowsystemer til visualisering implementerer inputvalidering for at forhindre injektionsangreb gennem manipulerede node- eller kantdata.
 #12.6.5    Level: 3    Role: D/V
 Bekræft, at realtidsopdateringer af DAG er hastighedsbegrænsede og validerede for at forhindre tjenestenægtelsesangreb på visualiseringssystemer.

---

### C12.7 Proaktiv overvågning af sikkerhedsadfærd

Detektion og forebyggelse af sikkerhedstrusler gennem proaktiv agentadfærdsanalyse.

 #12.7.1    Level: 1    Role: D/V
 Bekræft, at proaktive agentadfærd er sikkerhedsvaliderede inden udførelse med integration af risikovurdering.
 #12.7.2    Level: 2    Role: D/V
 Bekræft, at autonome initiativudløsere inkluderer evaluering af sikkerhedskontekst og vurdering af trusselslandskabet.
 #12.7.3    Level: 2    Role: D/V
 Bekræft, at proaktive adfærdsmønstre analyseres for potentielle sikkerhedsmæssige implikationer og utilsigtede konsekvenser.
 #12.7.4    Level: 3    Role: D/V
 Bekræft, at sikkerhedskritiske proaktive handlinger kræver eksplicitte godkendelseskæder med revisionsspor.
 #12.7.5    Level: 3    Role: D/V
 Bekræft, at adfærdsafvigelsesdetektion identificerer afvigelser i proaktive agentmønstre, som kan indikere kompromittering.

---

### Referencer

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Menneskelig Overvågning, Ansvarlighed og Styring

### Kontrolmål

Dette kapitel indeholder krav til opretholdelse af menneskelig overvågning og klare ansvarskæder i AI-systemer, hvilket sikrer forklarbarhed, gennemsigtighed og etisk forvaltning gennem hele AI-livscyklussen.

---

### C13.1 Nødstop- og tilsidesættelsesmekanismer

Giv nedluknings- eller tilbageførselsmuligheder, når utryg adfærd i AI-systemet observeres.

 #13.1.1    Level: 1    Role: D/V
 Bekræft, at der findes en manuel nødstopmekanisme, som øjeblikkeligt kan stoppe AI-modelinferens og -udgange.
 #13.1.2    Level: 1    Role: D
 Bekræft, at overstyringskontroller kun er tilgængelige for autoriseret personale.
 #13.1.3    Level: 3    Role: D/V
 Bekræft, at rollback-procedurer kan vende tilbage til tidligere modelversioner eller til sikkerhedstilstandsoperationer.
 #13.1.4    Level: 3    Role: V
 Sørg for, at overskrivningsmekanismer testes regelmæssigt.

---

### C13.2 Menneskelig i kredsløbet beslutningskontrolpunkter

Kræv menneskelig godkendelse, når indsatsen overstiger foruddefinerede risikogrænser.

 #13.2.1    Level: 1    Role: D/V
 Bekræft, at højrisiko AI-beslutninger kræver eksplicit menneskelig godkendelse før udførelse.
 #13.2.2    Level: 1    Role: D
 Sørg for, at risikogrænser er klart defineret og automatisk udløser arbejdsgange for menneskelig gennemgang.
 #13.2.3    Level: 2    Role: D
 Bekræft, at tidskritiske beslutninger har nødprocedurer, hvis menneskelig godkendelse ikke kan opnås inden for de krævede tidsrammer.
 #13.2.4    Level: 3    Role: D/V
 Bekræft, at eskaleringsprocedurer definerer klare myndighedsniveauer for forskellige beslutningstyper eller risikokategorier, hvis relevant.

---

### C13.3 Kæde af ansvar og reviderbarhed

Logfør operatørhandlinger og modelbeslutninger.

 #13.3.1    Level: 1    Role: D/V
 Bekræft, at alle AI-systembeslutninger og menneskelige indgreb logges med tidsstempler, brugeridentiteter og beslutningsbegrundelse.
 #13.3.2    Level: 2    Role: D
 Bekræft, at revisionslogfiler ikke kan manipuleres, og inkluder mekanismer til integritetsverifikation.

---

### C13.4 Forklarlige AI-teknikker

Vigtigheden af overfladefunktioner, kontrafaktuelle eksempler og lokale forklaringer.

 #13.4.1    Level: 1    Role: D/V
 Bekræft, at AI-systemer giver grundlæggende forklaringer på deres beslutninger i menneskeligt læsbart format.
 #13.4.2    Level: 2    Role: V
 Verificer, at forklaringskvaliteten er valideret gennem menneskelige evalueringsstudier og metrikker.
 #13.4.3    Level: 3    Role: D/V
 Bekræft, at vigtighedsscorer for funktioner eller attributmetoder (SHAP, LIME osv.) er tilgængelige for kritiske beslutninger.
 #13.4.4    Level: 3    Role: V
 Bekræft, at kontrafaktiske forklaringer viser, hvordan input kunne ændres for at ændre resultater, hvis det er relevant for brugstilfældet og domænet.

---

### C13.5 Modelkort og brugsoplysninger

Vedligehold modelkort for tilsigtet brug, præstationsmålinger og etiske overvejelser.

 #13.5.1    Level: 1    Role: D
 Bekræft, at modelkort dokumenterer tilsigtede anvendelsestilfælde, begrænsninger og kendte fejlfunktioner.
 #13.5.2    Level: 1    Role: D/V
 Bekræft, at præstationsmålinger på tværs af forskellige relevante anvendelsestilfælde er oplyst.
 #13.5.3    Level: 2    Role: D
 Bekræft, at etiske overvejelser, vurderinger af bias, evalueringer af retfærdighed, karakteristika for træningsdata og kendte begrænsninger ved træningsdata er dokumenteret og opdateret regelmæssigt.
 #13.5.4    Level: 2    Role: D/V
 Bekræft, at modelkort er versionsstyrede og vedligeholdes gennem hele modellens livscyklus med ændringssporing.

---

### C13.6 Usikkerhedskvantificering

Propager konfidensscore eller entropimål i svar.

 #13.6.1    Level: 1    Role: D
 Bekræft, at AI-systemer leverer konfidensscore eller usikkerhedsmål sammen med deres output.
 #13.6.2    Level: 2    Role: D/V
 Bekræft, at usikkerhedstærskler udløser yderligere menneskelig gennemgang eller alternative beslutningsveje.
 #13.6.3    Level: 2    Role: V
 Bekræft, at metoder til usikkerhedskvantificering er kalibrerede og validerede mod faktiske data.
 #13.6.4    Level: 3    Role: D/V
 Sørg for, at usikkerhedspropagering opretholdes gennem flertrins AI-arbejdsgange.

---

### C13.7 Brugerrettede gennemsigtighedsrapporter

Giv periodiske oplysninger om hændelser, drift og dataanvendelse.

 #13.7.1    Level: 1    Role: D/V
 Sørg for, at politikker for databrug og praksis for styring af brugerens samtykke er klart kommunikeret til interessenter.
 #13.7.2    Level: 2    Role: D/V
 Bekræft, at AI-påvirkningsvurderinger udføres, og at resultaterne indgår i rapporteringen.
 #13.7.3    Level: 2    Role: D/V
 Bekræft, at gennemsigtighedsrapporter, der offentliggøres regelmæssigt, afslører AI-hændelser og operationelle målinger i rimelig detaljeringsgrad.

#### Referencer

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

## Appendiks A: Ordforråd

Denne omfattende ordliste giver definitioner på centrale AI-, ML- og sikkerhedsbegreber, der anvendes gennem hele AISVS for at sikre klarhed og fælles forståelse.
​
Adversarialt eksempel: En input bevidst udformet til at få en AI-model til at lave en fejl, ofte ved at tilføje subtile forstyrrelser, der er ufattelige for mennesker.
​
Robusthed over for angreb – Robusthed over for angreb i AI refererer til en models evne til at opretholde dens præstation og modstå at blive narret eller manipuleret af bevidst udformede, skadelige input designet til at forårsage fejl.
​
Agent – AI-agenter er softwaresystemer, der bruger AI til at forfølge mål og udføre opgaver på vegne af brugere. De udviser ræsonnering, planlægning og hukommelse og har et niveau af autonomi til at træffe beslutninger, lære og tilpasse sig.
​
Agentisk AI: AI-systemer, der kan operere med en vis grad af autonomi for at nå mål, ofte ved at træffe beslutninger og handle uden direkte menneskelig indblanding.
​
Attributbaseret adgangskontrol (ABAC): Et adgangskontrolparadigme, hvor autorisationsbeslutninger baseres på attributter for brugeren, ressourcen, handlingen og miljøet, som evalueres på forespørgselstidspunktet.
​
Bagdørsangreb: En type datainfektionsangreb, hvor modellen trænes til at reagere på en bestemt måde på visse udløsere, mens den opfører sig normalt ellers.
​
Bias: Systematiske fejl i AI-modeloutput, der kan føre til urimelige eller diskriminerende resultater for visse grupper eller i specifikke sammenhænge.
​
Biasudnyttelse: En angrebsteknik, der udnytter kendte bias i AI-modeller til at manipulere output eller resultater.
​
Cedar: Amazons politik-sprog og motor til detaljerede tilladelser, der bruges til implementering af ABAC for AI-systemer.
​
Tankegang: En teknik til forbedring af ræsonnering i sprogmodeller ved at generere mellemliggende ræsonneringstrin, før det endelige svar produceres.
​
Strømafbrydere: Mekanismer, der automatisk stopper AI-systemets operationer, når specifikke risikogrænser overskrides.
​
Data Lækage: Utilsigtet afsløring af følsomme oplysninger gennem AI-models output eller adfærd.
​
Datatoksinering: Den bevidste korruption af træningsdata for at kompromittere modelintegriteten, ofte for at installere bagdøre eller forringe ydeevnen.
​
Differential Privacy – Differential privacy er en matematisk stringent ramme for at udgive statistisk information om datasæt, samtidig med at beskyttelsen af individuelle datapersoners privatliv sikres. Det gør det muligt for en dataindehaver at dele aggregerede mønstre i gruppen, samtidig med at information, der lækkes om specifikke individer, begrænses.
​
Indlejringer: Tætte vektorrepræsentationer af data (tekst, billeder osv.), der fanger semantisk betydning i et højdimensionelt rum.
​
Forklarbarhed – Forklarbarhed i AI er et AI-systems evne til at give menneskeligt forståelige begrundelser for dets beslutninger og forudsigelser, hvilket giver indsigt i dets interne funktioner.
​
Forklarlig AI (XAI): AI-systemer designet til at give menneskeligt forståelige forklaringer på deres beslutninger og adfærd gennem forskellige teknikker og rammeværk.
​
Federeret læring: En maskinlæringsmetode, hvor modeller trænes på tværs af flere decentraliserede enheder, der indeholder lokale datasæt, uden at udveksle selve dataene.
​
Værn: Begrænsninger implementeret for at forhindre AI-systemer i at producere skadelige, forudindtagede eller på anden måde uønskede output.
​
Hallucination – En AI-hallucination refererer til et fænomen, hvor en AI-model genererer forkerte eller vildledende oplysninger, som ikke er baseret på dens træningsdata eller faktiske virkelighed.
​
Human-in-the-Loop (HITL): Systemer designet til at kræve menneskelig overvågning, verifikation eller indgriben ved vigtige beslutningspunkter.
​
Infrastructure som kode (IaC): Administration og udrulning af infrastruktur gennem kode i stedet for manuelle processer, hvilket muliggør sikkerhedsscanning og konsekvente udrulninger.
​
Jailbreak: Teknikker brugt til at omgå sikkerhedsvagter i AI-systemer, især i store sprogmodeller, for at producere forbudt indhold.
​
Mindste privilegium: Sikkerhedsprincippet om kun at tildele de mindst nødvendige adgangsrettigheder til brugere og processer.
​
LIME (Lokale Interpretable Model-agnostiske Forklaringer): En teknik til at forklare forudsigelser fra enhver maskinlæringsklassifikator ved at approximere den lokalt med en fortolkelig model.
​
Membership Inference Attack: Et angreb, der har til formål at bestemme, om et specifikt datapunkt blev brugt til at træne en maskinlæringsmodel.
​
MITRE ATLAS: Modstandsdygtigt trusselslandskab for kunstige intelligenssystemer; en vidensdatabase over modstandstaktikker og -teknikker mod AI-systemer.
​
Modelkort – Et modelkort er et dokument, der giver standardiseret information om en AI-models ydeevne, begrænsninger, tilsigtede anvendelser og etiske overvejelser for at fremme gennemsigtighed og ansvarlig AI-udvikling.
​
Modeludtrækning: Et angreb, hvor en modstander gentagne gange forespørger en målsmodel for at skabe en funktionelt tilsvarende kopi uden tilladelse.
​
Modelinversion: Et angreb, der forsøger at rekonstruere træningsdata ved at analysere modeludgange.
​
Modelstyring – Modelstyring for AI er processen med at overvåge alle faser af en AI-models levetid, herunder dens design, udvikling, implementering, overvågning, vedligeholdelse og eventuelle udfasning, for at sikre, at den forbliver effektiv og i overensstemmelse med målene.
​
Modelforgiftning: Indføring af sårbarheder eller bagindgange direkte i en model under træningsprocessen.
​
Modeltyveri: Udtrækning af en kopi eller en tilnærmelse af en proprietær model gennem gentagne forespørgsler.
​
Multi-agent System: Et system bestående af flere interagerende AI-agenter, hver med potentielt forskellige kapaciteter og mål.
​
OPA (Open Policy Agent): En open source-politikmotor, der muliggør ensartet politikhåndhævelse på tværs af hele stacken.
​
Privatlivsbevarende maskinlæring (PPML): Teknikker og metoder til at træne og implementere ML-modeller samtidig med, at privatlivets fred for træningsdata beskyttes.
​
Prompt Injection: Et angreb, hvor ondsindede instruktioner indlejres i input for at tilsidesætte en models tilsigtede adfærd.
​
RAG (Retrieval-Augmented Generation): En teknik, der forbedrer store sprogmodeller ved at hente relevant information fra eksterne videnskilder, før der genereres et svar.
​
Red-Teaming: Praksis med aktivt at teste AI-systemer ved at simulere fjendtlige angreb for at identificere sårbarheder.
​
SBOM (Software Bill of Materials): En formel optegnelse, der indeholder detaljer og forsyningskædeforhold for forskellige komponenter, der bruges til at bygge software eller AI-modeller.
​
SHAP (SHapley Additive exPlanations): En spilteoretisk tilgang til at forklare outputtet af enhver maskinlæringsmodel ved at beregne bidraget fra hver funktion til forudsigelsen.
​
Supply Chain Attack: Kompromittering af et system ved at angribe mindre sikre elementer i dets forsyningskæde, såsom tredjepartsbiblioteker, datasæt eller forudtrænede modeller.
​
Transfer Learning: En teknik, hvor en model udviklet til én opgave genbruges som udgangspunkt for en model til en anden opgave.
​
Vektordatabase: En specialiseret database designet til at gemme højdimensionelle vektorer (indlejringer) og udføre effektive søger efter ligheder.
​
Sårbarhedsscanning: Automatiserede værktøjer, der identificerer kendte sikkerhedssårbarheder i softwarekomponenter, herunder AI-rammer og afhængigheder.
​
Vandmærkning: Teknikker til at indlejre uundværlige markører i AI-genereret indhold for at spore dets oprindelse eller opdage AI-generering.
​
Zero-Day-sårbarhed: En tidligere ukendt sårbarhed, som angribere kan udnytte, før udviklere skaber og implementerer en rettelse.

## Appendix B: Referencer

### TODO

## Appendiks C: AI-sikkerhedsstyring og dokumentation

### Mål

Dette appendiks giver grundlæggende krav til etablering af organisatoriske strukturer, politikker og processer for at styre AI-sikkerhed gennem hele systemets livscyklus.

---

### AC.1 Implementering af AI-risikostyringsrammen

Tilbyd en formel ramme til at identificere, vurdere og mindske AI-specifikke risici gennem hele systemets livscyklus.

 #AC.1.1    Level: 1    Role: D/V
 Bekræft, at en AI-specifik risikovurderingsmetodologi er dokumenteret og implementeret.
 #AC.1.2    Level: 2    Role: D
 Sørg for, at risikovurderinger gennemføres på nøglepunkter i AI-livscyklussen og før væsentlige ændringer.
 #AC.1.3    Level: 3    Role: D/V
 Bekræft, at risikostyringsrammen er i overensstemmelse med etablerede standarder (f.eks. NIST AI RMF).

---

### AC.2 AI-sikkerhedspolitik og -procedurer

Definér og håndhæv organisatoriske standarder for sikker AI-udvikling, -implementering og -drift.

 #AC.2.1    Level: 1    Role: D/V
 Bekræft, at dokumenterede AI-sikkerhedspolitikker eksisterer.
 #AC.2.2    Level: 2    Role: D
 Bekræft, at politikker gennemgås og opdateres mindst årligt og efter betydelige ændringer i trussellandskabet.
 #AC.2.3    Level: 3    Role: D/V
 Bekræft, at politikkerne dækker alle AISVS-kategorier og gældende lovgivningsmæssige krav.

---

### AC.3 Roller og ansvar for AI-sikkerhed

Etabler klar ansvarlighed for AI-sikkerhed på tværs af organisationen.

 #AC.3.1    Level: 1    Role: D/V
 Bekræft, at AI-sikkerhedsroller og -ansvarsområder er dokumenteret.
 #AC.3.2    Level: 2    Role: D
 Bekræft, at ansvarlige personer har passende sikkerhedsekspertise.
 #AC.3.3    Level: 3    Role: D/V
 Bekræft, at et AI-etikudvalg eller en styringsgruppe er etableret for højrisko AI-systemer.

---

### AC.4 Håndhævelse af etiske AI-retningslinjer

Sørg for, at AI-systemer fungerer i overensstemmelse med etablerede etiske principper.

 #AC.4.1    Level: 1    Role: D/V
 Bekræft, at der findes etiske retningslinjer for udvikling og implementering af AI.
 #AC.4.2    Level: 2    Role: D
 Bekræft, at der er mekanismer på plads til at opdage og rapportere etiske overtrædelser.
 #AC.4.3    Level: 3    Role: D/V
 Sørg for, at regelmæssige etiske vurderinger af implementerede AI-systemer bliver udført.

---

### AC.5 Overvågning af overholdelse af AI-regulering

Oprethold bevidsthed om og overholdelse af de udviklende AI-reguleringer.

 #AC.5.1    Level: 1    Role: D/V
 Bekræft, at der findes processer til at identificere gældende AI-regler.
 #AC.5.2    Level: 2    Role: D
 Sørg for, at overholdelse af alle lovgivningsmæssige krav vurderes.
 #AC.5.3    Level: 3    Role: D/V
 Bekræft, at regulatoriske ændringer udløser rettidige gennemgange og opdateringer af AI-systemer.

#### Referencer

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Bilag D: AI-assisteret styring og verifikation af sikker kodning

### Mål

Dette kapitel definerer grundlæggende organisatoriske kontrolforanstaltninger for sikker og effektiv brug af AI-assisterede kodningsværktøjer under softwareudvikling og sikrer sikkerhed og sporbarhed på tværs af SDLC.

---

### AD.1 AI-assisteret sikker-kodningsarbejdsgang

Integrer AI-værktøjer i organisationens sikre softwareudviklingslivscyklus (SSDLC) uden at svække de eksisterende sikkerhedsværn.

 #AD.1.1    Level: 1    Role: D/V
 Bekræft, at en dokumenteret arbejdsgang beskriver, hvornår og hvordan AI-værktøjer kan generere, omstrukturere eller gennemgå kode.
 #AD.1.2    Level: 2    Role: D
 Bekræft, at arbejdsgangen svarer til hver SSDLC-fase (design, implementering, kodegennemgang, testning, implementering).
 #AD.1.3    Level: 3    Role: D/V
 Bekræft, at metrikker (f.eks. sårbarhedstæthed, gennemsnitlig tid til at opdage) indsamles for AI-genereret kode og sammenlignes med baselineværdi for udelukkende menneskeskabt kode.

---

### AD.2 AI-værktøjskvalificering og trusselsmodellering

Sørg for, at AI-kodningsværktøjer evalueres for sikkerhedsfunktioner, risici og forsyningskædepåvirkning, før de tages i brug.

 #AD.2.1    Level: 1    Role: D/V
 Bekræft, at en trusselsmodel for hvert AI-værktøj identificerer misbrug, modelinversion, datalækage og afhængighedskæderisici.
 #AD.2.2    Level: 2    Role: D
 Bekræft, at værktøjsevalueringer inkluderer statisk/dynamisk analyse af eventuelle lokale komponenter samt vurdering af SaaS-endpoints (TLS, autentificering/autorisation, logning).
 #AD.2.3    Level: 3    Role: D/V
 Bekræft, at evalueringer følger en anerkendt ramme og genudføres efter større versionsændringer.

---

### AD.3 Sikker Prompt- og Kontekststyring

Forhindre lækage af hemmeligheder, proprietær kode og personlige data ved opbygning af prompts eller kontekster til AI-modeller.

 #AD.3.1    Level: 1    Role: D/V
 Bekræft, at skriftlige retningslinjer forbyder at sende hemmeligheder, legitimationsoplysninger eller klassificerede data i prompts.
 #AD.3.2    Level: 2    Role: D
 Bekræft, at tekniske kontroller (redigering på klientsiden, godkendte kontekstfiltre) automatisk fjerner følsomme elementer.
 #AD.3.3    Level: 3    Role: D/V
 Bekræft, at prompts og svar bliver tokeniseret, krypteret under overførsel og i hvile, samt at opbevaringsperioderne overholder dataklassificeringspolitikken.

---

### AD.4 Validering af AI-genereret kode

Opdag og udbedr sårbarheder introduceret af AI-output, før koden flettes eller implementeres.

 #AD.4.1    Level: 1    Role: D/V
 Bekræft, at AI-genereret kode altid underkastes menneskelig kodegennemgang.
 #AD.4.2    Level: 2    Role: D
 Bekræft, at automatiserede scannere (SAST/IAST/DAST) kører på hver pull request, der indeholder AI-genereret kode, og blokerer for sammenfletninger ved kritiske fund.
 #AD.4.3    Level: 3    Role: D/V
 Bekræft, at differential fuzz-testing eller egenskabsbaserede tests beviser sikkerhedskritiske adfærd (f.eks. inputvalidering, autorisationslogik).

---

### AD.5 Forklarbarhed og Sporbarhed af Kodeforslag

Giv revisorer og udviklere indsigt i, hvorfor et forslag blev fremsat, og hvordan det udviklede sig.

 #AD.5.1    Level: 1    Role: D/V
 Bekræft, at prompt-/responspar logges med commit-id'er.
 #AD.5.2    Level: 2    Role: D
 Bekræft, at udviklere kan fremvise modelhenvisninger (træningsudsnit, dokumentation), der understøtter et forslag.
 #AD.5.3    Level: 3    Role: D/V
 Bekræft, at forklarbarhedsrapporter opbevares sammen med designartefakter og refereres til i sikkerhedsgennemgange, hvilket opfylder ISO/IEC 42001 sporbarhedsprincipper.

---

### AD.6 Kontinuerlig feedback og finjustering af model

Forbedr modelens sikkerhedspræstation over tid, samtidig med at negativ drift forhindres.

 #AD.6.1    Level: 1    Role: D/V
 Bekræft, at udviklere kan markere usikre eller ikke-kompatible forslag, og at markeringerne bliver registreret.
 #AD.6.2    Level: 2    Role: D
 Bekræft, at samlet feedback informerer periodisk finjustering eller retrieval-augmenteret generering med verificerede sikre-kodningskorpora (f.eks. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Bekræft, at et lukket kredsløbs evalueringsværktøj kører regressions test efter hver finjustering; sikkerhedsmålinger skal opfylde eller overgå tidligere baselineværdier før implementering.

---

#### Referencer

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Appendiks E: Eksempelværktøjer og -rammer

### Formål

Dette kapitel giver eksempler på værktøjer og frameworks, som kan understøtte implementeringen eller opfyldelsen af et givent AISVS-krav. Disse skal ikke betragtes som anbefalinger eller godkendelser fra AISVS-teamet eller OWASP GenAI Security-projektet.

---

### AE.1 Træningsdataforvaltning og biasstyring

Værktøjer brugt til dataanalyse, styring og håndtering af bias.

 #AE.1.1    Section: 1.1
 Værktøjer til datainventar: Værktøjer til styring af datainventar som...
 #AE.1.2    Section: 1.2
 Kryptering under overførsel Brug TLS til HTTPS-baserede applikationer med værktøjer som openSSL og Pythons`ssl`bibliotek.

---

### AE.2 Validering af brugerinput

Værktøjer til håndtering og validering af brugerinput.

 #AE.2.1    Section: 2.1
 Værktøjer til forsvar mod prompt-injektion: Brug værktøjer som NVIDIA's NeMo eller Guardrails AI til beskyttelse.

---

