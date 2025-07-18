## Forside

### Om standarden

Artificial Intelligence Security Verification Standard (AISVS) er en fellesskapsdrevet katalog over sikkerhetskrav som dataforskere, MLOps-ingeniører, programvarearkitekter, utviklere, testere, sikkerhetsprofesjonelle, verktøyleverandører, reguleringsmyndigheter og brukere kan benytte for å designe, bygge, teste og verifisere pålitelige AI‑aktiverte systemer og applikasjoner. Den gir et felles språk for å spesifisere sikkerhetskontroller gjennom hele AI-livssyklusen — fra datainnsamling og modellutvikling til distribusjon og løpende overvåking — slik at organisasjoner kan måle og forbedre motstandsdyktigheten, personvernet og sikkerheten til sine AI-løsninger.

### Opphavsrett og lisens

Versjon 0.1 (Første offentlige utkast - Under arbeid), 2025  

![license](images/license.png)
Opphavsrett © 2025 The AISVS Project.  

Utgitt underCreative Commons Attribution‑ShareAlike 4.0 International License.
For all gjenbruk eller distribusjon må du tydelig formidle lisensbetingelsene for dette verket til andre.

### Prosjektledere

Jim Manico
Aras "Russ" Memisyazici

### Bidragsytere og Anmeldere

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS er en helt ny standard utviklet spesifikt for å håndtere de unike sikkerhetsutfordringene ved kunstige intelligenssystemer. Selv om den tar inspirasjon fra bredere sikkerhetsbeste praksiser, er hvert krav i AISVS utviklet fra grunnen av for å gjenspeile trussellandskapet innen AI og for å hjelpe organisasjoner med å bygge sikrere, mer robuste AI-løsninger.

## Forord

Velkommen til standarden for sikkerhetsverifisering av kunstig intelligens (AISVS) versjon 1.0!

### Introduksjon

Etablert i 2025 gjennom et samarbeidende fellesskapsinitiativ, definerer AISVS sikkerhetskravene som må vurderes ved utforming, utvikling, distribusjon og drift av moderne AI-modeller, arbeidsflyter og AI-aktiverte tjenester.

AISVS v1.0 representerer det samlede arbeidet til prosjektlederne, arbeidsgruppen og det bredere fellesskapet av bidragsytere for å produsere en pragmatisk og testbar baseline for å sikre AI-systemer.

Målet vårt med denne utgivelsen er å gjøre AISVS enkelt å ta i bruk samtidig som vi holder oss nøye fokusert på dets definerte omfang og håndterer det raskt utviklende risikobildet som er unikt for AI.

### Hovedmål for AISVS Versjon 1.0

Versjon 1.0 vil bli utviklet med flere veiledende prinsipper.

#### Veldefinert omfang

Hvert krav må være i samsvar med AISVS’ navn og oppdrag:

Kunstig intelligens – Kontrollene opererer på AI/ML-laget (data, modell, pipeline eller inferens) og er ansvaret til AI-utøvere.
Sikkerhet – Kravene reduserer direkte identifiserte sikkerhets-, personvern- eller sikkerhetsrisikoer.
Verifikasjon – Språket er skrevet slik at samsvar kan objektivt valideres.
Standard – Seksjoner følger en konsekvent struktur og terminologi for å danne en sammenhengende referanse.
​
---

Ved å følge AISVS kan organisasjoner systematisk evaluere og styrke sikkerhetsnivået i sine AI-løsninger, og fremme en kultur for sikker AI-ingeniørkunst.

## Bruke AISVS

Standard for sikkerhetsverifisering av kunstig intelligens (AISVS) definerer sikkerhetskrav for moderne AI-applikasjoner og -tjenester, med fokus på aspekter som ligger under kontroll av applikasjonsutviklere.

AISVS er ment for alle som utvikler eller evaluerer sikkerheten til AI-applikasjoner, inkludert utviklere, arkitekter, sikkerhetsingeniører og revisorer. Dette kapittelet introduserer strukturen og bruken av AISVS, inkludert dets verifiseringsnivåer og tiltenkte brukstilfeller.

### Sikkerhetsverifiseringsnivåer for kunstig intelligens

AISVS definerer tre stigende nivåer av sikkerhetsverifisering. Hvert nivå legger til dybde og kompleksitet, og gjør det mulig for organisasjoner å tilpasse sikkerhetsnivået etter risikonivået til sine AI-systemer.

Organisasjoner kan starte på nivå 1 og gradvis adoptere høyere nivåer etterhvert som sikkerhetsmodenhet og trusseleksponering øker.

#### Definisjon av nivåene

Hver krav i AISVS v1.0 er tildelt til ett av følgende nivåer:

 Krav for nivå 1

Nivå 1 inkluderer de mest kritiske og grunnleggende sikkerhetskravene. Disse fokuserer på å forhindre vanlige angrep som ikke er avhengige av andre forutsetninger eller sårbarheter. De fleste kontroller på Nivå 1 er enten enkle å implementere eller så essensielle at innsatsen rettferdiggjøres.

 Krav på nivå 2

Nivå 2 tar for seg mer avanserte eller mindre vanlige angrep, samt lagdelte forsvar mot utbredte trusler. Disse kravene kan innebære mer kompleks logikk eller rette seg mot spesifikke forutsetninger for angrep.

 Krav på nivå 3

Nivå 3 inkluderer kontroller som vanligvis er vanskeligere å implementere eller situasjonsavhengige i bruk. Disse representerer ofte forsvar-i-dybden-mekanismer eller tiltak mot nisje-, målrettede eller komplekse angrep.

#### Rolle (D/V)

Hvert AISVS-krav er merket i henhold til hovedmålgruppen:

D – Utviklerfokuserte krav
V – Krav rettet mot verifikator/revisor
D/V – Relevant for både utviklere og verifikatorer

## C1 Opplæringsdatastyring og skjevhetsbehandling

### Kontrollmål

Treningsdata må anskaffes, håndteres og vedlikeholdes på en måte som ivaretar opprinnelse, sikkerhet, kvalitet og rettferdighet. Dette oppfyller juridiske forpliktelser og reduserer risikoen for skjevhet, forgiftning eller brudd på personvernet gjennom hele AI-livssyklusen.

---

### C1.1 Opprinnelse for treningsdata

Oppretthold et verifiserbart register over alle datasett, godta kun pålitelige kilder, og loggfør hver endring for revisjonssporbarhet.

 #1.1.1    Level: 1    Role: D/V
 Sikre at en oppdatert oversikt over alle treningsdatakilder (opprinnelse, forvalter/eier, lisens, innsamlingsmetode, begrensninger for tiltenkt bruk og behandlingshistorikk) blir vedlikeholdt.
 #1.1.2    Level: 1    Role: D/V
 Sørg for at kun datasett som er vurdert for kvalitet, representativitet, etisk innkjøp og lisensoverholdelse tillates, for å redusere risikoene for forgiftning, innebygd skjevhet og brudd på immaterielle rettigheter.
 #1.1.3    Level: 1    Role: D/V
 Sørg for at dataminimering håndheves slik at unødvendige eller sensitive attributter utelates.
 #1.1.4    Level: 2    Role: D/V
 Verifiser at alle dataset-endringer er underlagt en loggført godkjenningsprosess.
 #1.1.5    Level: 2    Role: D/V
 Sørg for at kvaliteten på merking/annotasjon sikres gjennom gjensidig kontroll eller konsensus blant vurderere.
 #1.1.6    Level: 2    Role: D/V
 Sørg for at "datakort" eller "datablader for datasett" oppdateres for viktige treningsdatasett, og beskriver egenskaper, motivasjoner, sammensetning, innsamling, forhåndsbehandling og anbefalte/ikke anbefalte bruksområder.

---

### C1.2 Sikkerhet og integritet for treningsdata

Begrens tilgang, krypter data i hvile og under overføring, og valider integriteten for å hindre manipulering eller tyveri.

 #1.2.1    Level: 1    Role: D/V
 Verifiser at tilgangskontroller beskytter lagring og databehandlingsrørledninger.
 #1.2.2    Level: 2    Role: D/V
 Bekreft at datasett er kryptert under overføring og, for all sensitiv eller personlig identifiserbar informasjon (PII), i ro, ved bruk av industristandard kryptografiske algoritmer og praksiser for nøkkelstyring.
 #1.2.3    Level: 2    Role: D/V
 Verifiser at kryptografiske hasher eller digitale signaturer brukes for å sikre dataintegritet under lagring og overføring, og at automatiserte teknikker for anomalioppdagelse anvendes for å beskytte mot uautoriserte endringer eller korrupsjon, inkludert målrettede forsøk på datatoksinering.
 #1.2.4    Level: 3    Role: D/V
 Bekreft at datasettversjoner spores for å muliggjøre tilbakestilling.
 #1.2.5    Level: 2    Role: D/V
 Bekreft at foreldet data blir sikkert slettet eller anonymisert i samsvar med retningslinjer for datalagring, regulatoriske krav, og for å redusere angrepsflaten.

---

### C1.3 Representasjonsfullstendighet og rettferdighet

Oppdag demografiske skjevheter og anvend tiltak for å sikre at modellens feilrater er rettferdige på tvers av grupper.

 #1.3.1    Level: 1    Role: D/V
 Sørg for at datasett blir analysert for representasjonsubalanse og potensielle skjevheter på tvers av lovbeskyttede attributter (f.eks. rase, kjønn, alder) og andre etisk sensitive kjennetegn som er relevante for modellens anvendelsesområde (f.eks. sosioøkonomisk status, geografisk plassering).
 #1.3.2    Level: 2    Role: D/V
 Bekreft at identifiserte skjevheter blir redusert gjennom dokumenterte strategier som balansering, målrettet dataforsterkning, algoritmiske justeringer (f.eks. forhåndsbehandling, behandling under prosessering, etterbehandlingsteknikker), eller vekting, og at virkningen av disse tiltakene på både rettferdighet og den samlede modellens ytelse blir vurdert.
 #1.3.3    Level: 2    Role: D/V
 Verifiser at rettferdighetsmålinger etter trening blir evaluert og dokumentert.
 #1.3.4    Level: 3    Role: D/V
 Bekreft at en livssyklusbasert bias-administrasjonspolicy tildeler eiere og fastsetter gjennomgangsfrekvens.

---

### C1.4 Kvalitet, integritet og sikkerhet ved merking av treningsdata

Beskytt etiketter med kryptering og krev dobbel gjennomgang for kritiske klasser.

 #1.4.1    Level: 2    Role: D/V
 Sørg for at merkings-/annotasjonskvaliteten sikres gjennom klare retningslinjer, krysskontroller av gjennomgangere, konsensusmekanismer (f.eks. overvåking av enighet mellom annotatører) og definerte prosesser for å løse uoverensstemmelser.
 #1.4.2    Level: 2    Role: D/V
 Bekreft at kryptografiske hasjer eller digitale signaturer brukes på merkevarer for å sikre deres integritet og ekthet.
 #1.4.3    Level: 2    Role: D/V
 Sørg for at etiketteringsgrensesnitt og plattformer håndhever sterke tilgangskontroller, opprettholder manipulasjonssikre revisjonslogger for alle etiketteringsaktiviteter, og beskytter mot uautoriserte endringer.
 #1.4.4    Level: 3    Role: D/V
 Bekreft at etiketter som er kritiske for sikkerhet, sikkerhet eller rettferdighet (f.eks. identifisering av giftig innhold, kritiske medisinske funn) gjennomgår obligatorisk uavhengig dobbel vurdering eller tilsvarende robust verifisering.
 #1.4.5    Level: 2    Role: D/V
 Bekreft at sensitiv informasjon (inkludert personopplysninger) som utilsiktet er fanget opp eller nødvendigvis tilstede i etiketter, er redigert, pseudonymisert, anonymisert eller kryptert både i hvile og under overføring, i samsvar med prinsippene for dataminimering.
 #1.4.6    Level: 2    Role: D/V
 Sørg for at merkingsveiledninger og instruksjoner er omfattende, versjonskontrollerte og fagfellevurderte.
 #1.4.7    Level: 2    Role: D/V
 Sørg for at dataschemer (inkludert for etiketter) er klart definert og versjonskontrollert.
 #1.8.2    Level: 2    Role: D/V
 Bekreft at eksterne eller folkemengdebaserte etiketteringsarbeidsflyter inkluderer tekniske/prosedyremessige sikkerhetstiltak for å sikre datakonfidensialitet, integritet, etikettkvalitet og forhindre datalekkasjer.

---

### C1.5 Kvalitetssikring av treningsdata

Kombiner automatisert validering, manuelle stikkprøver og loggført utbedring for å garantere påliteligheten til datasettet.

 #1.5.1    Level: 1    Role: D
 Bekreft at automatiserte tester fanger opp formateringsfeil, nullverdier og etikettforskyvninger ved hver innlasting eller betydelig transformasjon.
 #1.5.2    Level: 1    Role: D/V
 Bekreft at feilede datasett er satt i karantene med revisjonsspor.
 #1.5.3    Level: 2    Role: V
 Bekreft at manuelle stikkprøver utført av domeneeksperter dekker et statistisk signifikant utvalg (f.eks. ≥1 % eller 1 000 prøver, avhengig av hva som er størst, eller som bestemt av risikovurdering) for å identifisere subtile kvalitetsproblemer som ikke fanges opp av automatisering.
 #1.5.4    Level: 2    Role: D/V
 Bekreft at utbedringstiltak er lagt til i opphavsrekordene.
 #1.5.5    Level: 2    Role: D/V
 Bekreft at kvalitetsporter blokkerer underpar-datasett med mindre unntak er godkjent.

---

### C1.6 Deteksjon av dataforgiftning

Bruk statistisk anomalideteksjon og karantenearbeidsflyter for å stoppe fiendtlige innsettinger.

 #1.6.1    Level: 2    Role: D/V
 Bekreft at anomali-deteksjonsteknikker (f.eks. statistiske metoder, uteliggerdeteksjon, analyseg av innbygginger) anvendes på treningsdata ved inntak og før større treningskjøringer for å identifisere potensielle forgiftningsangrep eller utilsiktet datakorruptjon.
 #1.6.2    Level: 2    Role: D/V
 Bekreft at flaggede prøver utløser manuell gjennomgang før trening.
 #1.6.3    Level: 2    Role: V
 Bekreft at resultatene føres inn i modellens sikkerhetsdossier og informerer om pågående trusselintelligens.
 #1.6.4    Level: 3    Role: D/V
 Bekreft at deteksjonslogikken oppdateres med ny trusselinformasjon.
 #1.6.5    Level: 3    Role: D/V
 Bekreft at online-læringspipelines overvåker distribusjonsforskyvning.
 #1.6.6    Level: 3    Role: D/V
 Bekreft at spesifikke forsvar mot kjente datainjiseringsangrepstyper (f.eks. etikettomslag, innsetting av bakdørstriggere, angrep med innflytelsesrike instanser) er vurdert og implementert basert på systemets risikoprofil og datakilder.

---

### C1.7 Sletting av brukerdata og håndheving av samtykke

Respekter slettings- og samtykketrekkingsforespørsler på tvers av datasett, sikkerhetskopier og utledede artefakter.

 #1.7.1    Level: 1    Role: D/V
 Bekreft at slettingsarbeidsflyter fjerner primær- og avledede data og vurderer modellens påvirkning, og at påvirkningen på berørte modeller blir vurdert og, om nødvendig, håndtert (for eksempel gjennom nyopplæring eller rekalibrering).
 #1.7.2    Level: 2    Role: D
 Verifiser at det finnes mekanismer for å spore og respektere omfanget og statusen for brukersamtykke (og tilbakekallinger) for data brukt i trening, og at samtykke valideres før data blir innarbeidet i nye treningsprosesser eller betydelige modelloppdateringer.
 #1.7.3    Level: 2    Role: V
 Kontroller at arbeidsflyter blir testet årlig og loggført.

---

### C1.8 Sikkerhet i forsyningskjeden

Vurder eksterne dataleverandører og verifiser integritet over autentiserte, krypterte kanaler.

 #1.8.1    Level: 2    Role: D/V
 Sjekk at tredjepartsdataleverandører, inkludert leverandører av forhåndstrente modeller og eksterne datasett, gjennomgår sikkerhets-, personvern-, etisk innkjøps- og datakvalitetsvurderinger før deres data eller modeller integreres.
 #1.8.2    Level: 1    Role: D
 Bekreft at eksterne overføringer bruker TLS/autentisering og integritetskontroller.
 #1.8.3    Level: 2    Role: D/V
 Bekreft at høyrisiko datakilder (f.eks. åpne datasett med ukjent opprinnelse, ikke-godkjente leverandører) får økt granskning, slik som analyse i sandkasse, omfattende kvalitets-/skjevhetssjekker, og målrettet forgiftningsdeteksjon, før de brukes i sensitive applikasjoner.
 #1.8.4    Level: 3    Role: D/V
 Sikre at forhåndstrente modeller hentet fra tredjeparter blir evaluert for innebygde skjevheter, potensielle bakdører, integriteten til deres arkitektur, og opprinnelsen til deres opprinnelige treningsdata før finjustering eller distribusjon.

---

### C1.9 Oppdagelse av adversarielle prøver

Implementer tiltak under treningsfasen, som adversarial trening, for å forbedre modellens motstandskraft mot adversariale eksempler.

 #1.9.1    Level: 3    Role: D/V
 Bekreft at passende forsvar, slik som adversarial trening (ved bruk av genererte adversarielle eksempler), datagenerering med perturberte input, eller robuste optimaliseringsteknikker, er implementert og justert for relevante modeller basert på risikovurdering.
 #1.9.2    Level: 2    Role: D/V
 Bekreft at hvis fiendtlig trening brukes, blir generering, administrasjon og versjonering av fiendtlige datasett dokumentert og kontrollert.
 #1.9.3    Level: 3    Role: D/V
 Verifiser at virkningen av trening for motstandsdyktighet mot angrep på modellens ytelse (både mot rene og angrepsbaserte input) og rettferdighetsmålinger blir evaluert, dokumentert og overvåket.
 #1.9.4    Level: 3    Role: D/V
 Bekreft at strategier for adversarial trening og robusthet blir periodisk gjennomgått og oppdatert for å motvirke utviklende teknikker for adversariale angrep.

---

### C1.10 Datalinje og sporbarhet

Spor hele reisen til hvert datapunkt fra kilde til modellinput for revisjonssporing og hendelsesrespons.

 #1.10.1    Level: 2    Role: D/V
 Verifiser at avstamningen for hvert datapunkt, inkludert alle transformasjoner, forsterkninger og sammenslåinger, er registrert og kan rekonstrueres.
 #1.10.2    Level: 2    Role: D/V
 Verifiser at slektskontrollregistre er uforanderlige, sikkert lagret og tilgjengelige for revisjoner eller undersøkelser.
 #1.10.3    Level: 2    Role: D/V
 Verifiser at sporing av opprinnelse dekker både rådata og syntetiske data.

---

### C1.11 Håndtering av syntetiske data

Sørg for at syntetiske data blir riktig håndtert, merket og risikovurdert.

 #1.11.1    Level: 2    Role: D/V
 Bekreft at all syntetisk data er tydelig merket og skillelig fra ekte data gjennom hele prosessen.
 #1.11.2    Level: 2    Role: D/V
 Bekreft at genereringsprosessen, parametrene og den tiltenkte bruken av syntetiske data er dokumentert.
 #1.11.3    Level: 2    Role: D/V
 Sørg for at syntetiske data er risikovurdert for skjevhet, personvernlekkasje og representasjonsproblemer før bruk i trening.

---

### C1.12 Data Tilgangsovervåking og Anomalioppdagelse

Overvåk og varsle om uvanlig tilgang til treningsdata for å oppdage interne trusler eller eksfiltrasjon.

 #1.12.1    Level: 2    Role: D/V
 Sørg for at all tilgang til treningsdata logges, inkludert bruker, tid og handling.
 #1.12.2    Level: 2    Role: D/V
 Sørg for at tilgangslogger regelmessig gjennomgås for uvanlige mønstre, som store eksporteringer eller tilgang fra nye steder.
 #1.12.3    Level: 2    Role: D/V
 Bekreft at varsler genereres for mistenkelige tilgangshendelser og undersøkes raskt.

---

### C1.13 Retningslinjer for datalagring og utløp

Definer og håndhev lagringstider for data for å minimere unødvendig datalagring.

 #1.13.1    Level: 1    Role: D/V
 Bekreft at eksplisitte oppbevaringsperioder er definert for alle treningsdatasett.
 #1.13.2    Level: 2    Role: D/V
 Bekreft at datasett automatisk utløper, slettes eller gjennomgås for sletting ved slutten av livssyklusen.
 #1.13.3    Level: 2    Role: D/V
 Bekreft at handlinger for lagring og sletting blir loggført og kan revideres.

---

### C1.14 Regelverks- og jurisdiksjonsmessig samsvar

Sørg for at alle treningsdata overholder gjeldende lover og forskrifter.

 #1.14.1    Level: 2    Role: D/V
 Bekreft at krav til dataresidens og grenseoverskridende overføringer er identifisert og håndhevet for alle datasett.
 #1.14.2    Level: 2    Role: D/V
 Bekreft at sektorspesifikke forskrifter (f.eks. helsevesen, finans) blir identifisert og ivaretatt ved databehandling.
 #1.14.3    Level: 2    Role: D/V
 Sørg for at overholdelse av relevante personvernlovgivninger (f.eks. GDPR, CCPA) er dokumentert og gjennomgås regelmessig.

---

### C1.15 Data Vannmerking og Fingeravtrykkmerking

Oppdag uautorisert gjenbruk eller lekkasje av proprietære eller sensitive data.

 #1.15.1    Level: 3    Role: D/V
 Verifiser at datasett eller delsett er vannmerket eller fingeravtrykket der det er mulig.
 #1.15.2    Level: 3    Role: D/V
 Verifiser at metoder for vannmerking/fingeravtrykk ikke introduserer skjevhet eller personvernrisikoer.
 #1.15.3    Level: 3    Role: D/V
 Bekreft at det utføres periodiske kontroller for å oppdage uautorisert gjenbruk eller lekkasje av vannmerkede data.

---

### C1.16 Håndtering av registrertes rettigheter

Støtt rettigheter for registrerte, som tilgang, retting, begrensning og innsigelse.

 #1.16.1    Level: 2    Role: D/V
 Bekreft at det finnes mekanismer for å svare på forespørsler fra registrerte om tilgang, retting, begrensning eller innsigelse.
 #1.16.2    Level: 2    Role: D/V
 Bekreft at forespørsler blir logget, sporet og behandlet innen lovpålagte tidsrammer.
 #1.16.3    Level: 2    Role: D/V
 Bekreft at prosessene for rettighetene til den registrerte blir testet og gjennomgått regelmessig for effektivitet.

---

### C1.17 Analyse av effekten av datasettversjon

Vurder virkningen av endringer i datasett før oppdatering eller utskifting av versjoner.

 #1.17.1    Level: 2    Role: D/V
 Bekreft at en konsekvensanalyse utføres før oppdatering eller erstatning av en datasettversjon, som dekker modellens ytelse, rettferdighet og samsvar.
 #1.17.2    Level: 2    Role: D/V
 Sørg for at resultatene av konsekvensanalysen dokumenteres og gjennomgås av relevante interessenter.
 #1.17.3    Level: 2    Role: D/V
 Bekreft at det finnes tilbakeføringsplaner i tilfelle nye versjoner introduserer uakseptable risikoer eller tilbakeslag.

---

### C1.18 Dataannotasjonsarbeidsstyrkens sikkerhet

Sikre sikkerheten og integriteten til personell som er involvert i dataannotasjon.

 #1.18.1    Level: 2    Role: D/V
 Sørg for at alt personell som er involvert i dataannotasjon, er bakgrunnssjekket og opplært i datasikkerhet og personvern.
 #1.18.2    Level: 2    Role: D/V
 Bekreft at alt annoteringspersonell signerer konfidensialitets- og taushetserklæringer.
 #1.18.3    Level: 2    Role: D/V
 Bekreft at annotasjonsplattformer håndhever tilgangskontroller og overvåker for interne trusler.

---

### Referanser

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

## C2 Brukervalidert inndata

### Kontrollmål

Robust validering av brukerinnspill er en første forsvarslinje mot noen av de mest skadelige angrepene på AI-systemer. Prompt-injeksjonsangrep kan overstyre systeminstruksjoner, lekke sensitiv data eller styre modellen mot uønsket atferd. Med mindre dedikerte filtre og instruksjonshierarkier er på plass, viser forskning at "multi-shot" jailbreaks som utnytter svært lange kontekstvinduer vil være effektive. Også subtile adversarielle perturbasjonsangrep—slik som homoglyfbytter eller leetspeak—kan stille endre modellens beslutninger.

---

### C2.1 Forsvar mot promptinjeksjon

Promptinjeksjon er en av de største risikoene for AI-systemer. Forsvar mot denne taktikken benytter en kombinasjon av statiske mønsterfiltre, dynamiske klassifiserere og håndhevelse av instruksjonshierarki.

 #2.1.1    Level: 1    Role: D/V
 Sørg for at brukerinnspill blir kontrollert mot et kontinuerlig oppdatert bibliotek av kjente mønstre for promptinjeksering (jailbreak-stikkord, "ignorer tidligere", rollelek-kjeder, indirekte HTML/URL-angrep).
 #2.1.2    Level: 1    Role: D/V
 Bekreft at systemet håndhever en instruksjonshierarki der system- eller utviklermeldinger overstyrer brukerinstruksjoner, selv etter utvidelse av kontekstvinduet.
 #2.1.3    Level: 2    Role: D/V
 Bekreft at adversarial evalueringstester (f.eks. Red Team "many-shot" prompt) kjøres før hver modell- eller promptmalutgivelse, med suksessrategrenser og automatiske sperrer for tilbakeslag.
 #2.1.4    Level: 2    Role: D
 Bekreft at spørsmål som stammer fra tredjepartsinnhold (nettsteder, PDF-filer, e-poster) blir renset i en isolert parsingsammenheng før de settes sammen med hovedspørsmålet.
 #2.1.5    Level: 3    Role: D/V
 Sørg for at alle oppdateringer av prompt-filter-regler, versjoner av klassifiseringsmodeller og endringer i blokklisten er versjonskontrollerte og reviderbare.

---

### C2.2 Motstand mot adversarial-eksempler

Modeller for naturlig språkbehandling (NLP) er fortsatt sårbare for subtile tegn- eller ordnivåforstyrrelser som mennesker ofte overser, men som modellene har en tendens til å feilkategorisere.

 #2.2.1    Level: 1    Role: D
 Bekreft at grunnleggende inndata normaliseringssteg (Unicode NFC, homoglyph-mapping, trimming av mellomrom) kjøres før tokenisering.
 #2.2.2    Level: 2    Role: D/V
 Verifiser at statistisk anomalideteksjon merker inndata med uvanlig høy redigeringsavstand til språknormer, overdreven gjentakelse av token, eller unormale innebygde avstander.
 #2.2.3    Level: 2    Role: D
 Bekreft at inferensrøret støtter valgfrie modeller hardnet med adversarial trening eller forsvarslag (f.eks. randomisering, defensiv destillasjon) for høyrisiko-endepunkter.
 #2.2.4    Level: 2    Role: V
 Bekreft at mistenkte fiendtlige inndata blir satt i karantene og loggført med fullstendige nyttelaster (etter fjerning av personopplysninger).
 #2.2.5    Level: 3    Role: D/V
 Verifiser at robusthetsmålinger (suksessrate for kjente angrepssuiter) spores over tid, og at regresjoner utløser en utgivelsesblokkering.

---

### C2.3 Skjema-, type- og lengdevalidering

AI-angrep med feilformede eller overdimensjonerte inndata kan forårsake parsningsfeil, lekkasje mellom felt i prompten og ressursutmattelse. Streng skjemahåndhevelse er også en forutsetning ved utførelse av deterministiske verktøyanrop.

 #2.3.1    Level: 1    Role: D
 Verifiser at hvert API- eller funksjonskall-endepunkt definerer et eksplisitt inndataskjema (JSON Schema, Protobuf eller multimodalt ekvivalent) og at inndata valideres før promptens sammensetning.
 #2.3.2    Level: 1    Role: D/V
 Bekreft at inndata som overskrider maksimalt antall tokens eller byte-grenser blir avvist med en sikker feilmelding og aldri blir stille avkortet.
 #2.3.3    Level: 2    Role: D/V
 Bekreft at typekontroller (for eksempel numeriske intervaller, enum-verdier, MIME-typer for bilder/lyd) håndheves på serversiden, ikke bare i klientkoden.
 #2.3.4    Level: 2    Role: D
 Verifiser at semantiske validatorer (f.eks. JSON Schema) kjører i konstant tid for å forhindre algoritmisk DoS.
 #2.3.5    Level: 3    Role: V
 Bekreft at valideringsfeil logges med redigerte nyttelastutdrag og entydige feilkoder for å støtte sikkerhetstriage.

---

### C2.4 Innhold- og policykontroll

Utviklere bør kunne oppdage syntaktisk gyldige forespørsler som etterspør forbudt innhold (slik som ulovlige instruksjoner, hatprat og opphavsrettsbeskyttet tekst), og deretter forhindre at disse sprer seg.

 #2.4.1    Level: 1    Role: D
 Verifiser at en innholdsklassifiserer (zero shot eller finjustert) vurderer hvert innspill for vold, selvskading, hat, seksuelt innhold og ulovlige forespørsler, med konfigurerbare terskler.
 #2.4.2    Level: 1    Role: D/V
 Bekreft at inndata som bryter med retningslinjene vil motta standardiserte avslag eller sikre fullføringer slik at de ikke videreføres til etterfølgende LLM-kall.
 #2.4.3    Level: 2    Role: D
 Bekreft at screeningsmodellen eller regelsettet blir trent på nytt/oppdatert minst kvartalsvis, og inkluderer nylig observerte jailbreak- eller policyomgåelsesmønstre.
 #2.4.4    Level: 2    Role: D
 Verifiser at screening respekterer brukerspesifikke regler (alder, regionale juridiske begrensninger) via attributtbaserte regler løst ved forespørselstidspunkt.
 #2.4.5    Level: 3    Role: V
 Bekreft at screeningslogger inkluderer klassifiseringskonfidenspoeng og policy-kategorietagger for SOC-korrelasjon og fremtidig rødlagspillavspilling.

---

### C2.5 Begrensning av inngangshastighet og forebygging av misbruk

Utviklere bør forhindre misbruk, ressursutarming og automatiserte angrep mot AI-systemer ved å begrense inntaksrater og oppdage unormale bruks mønstre.

 #2.5.1    Level: 1    Role: D/V
 Bekreft at ratebegrensninger per bruker, per IP og per API-nøkkel håndheves for alle inndatapunkter.
 #2.5.2    Level: 2    Role: D/V
 Verifiser at burst- og vedvarende grenseverdier er justert for å forhindre DoS- og brute force-angrep.
 #2.5.3    Level: 2    Role: D/V
 Verifiser at unormale bruks mønstre (f.eks. raske forespørsler, input-overbelastning) utløser automatiske blokker eller eskaleringer.
 #2.5.4    Level: 3    Role: V
 Bekreft at logger for misbrukforebygging blir beholdt og gjennomgått for nye angrepsmønstre.

---

### C2.6 Multi-modale inndata-validering

AI-systemer bør inkludere robust validering for ikke-tekstlige input (bilder, lyd, filer) for å forhindre injeksjon, unnvikelse eller ressursmisbruk.

 #2.6.1    Level: 1    Role: D
 Sørg for at alle ikke-tekstlige inndata (bilder, lyd, filer) valideres for type, størrelse og format før behandling.
 #2.6.2    Level: 2    Role: D/V
 Bekreft at filer blir skannet for skadelig programvare og steganografiske nyttelaster før innlasting.
 #2.6.3    Level: 2    Role: D/V
 Bekreft at bilde-/lyd-inndata kontrolleres for fiendtlige forstyrrelser eller kjente angrepsmønstre.
 #2.6.4    Level: 3    Role: V
 Bekreft at bekreftelsesfeil for multimodale inndata blir logget og utløser varsler for undersøkelse.

---

### C2.7 Inngangsopprinnelse og attribusjon

KI-systemer bør støtte revisjon, misbrukssporing og etterlevelse ved å overvåke og merke opprinnelsen til alle brukerinput.

 #2.7.1    Level: 1    Role: D/V
 Bekreft at alle brukerinnspill er merket med metadata (bruker-ID, økt, kilde, tidsstempel, IP-adresse) ved inntak.
 #2.7.2    Level: 2    Role: D/V
 Bekreft at opprinnelsesmetadata beholdes og kan revideres for alle behandlede innganger.
 #2.7.3    Level: 2    Role: D/V
 Bekreft at avvikende eller ikke-pålitelig inngangskilder blir flagget og underlagt skjerpet kontroll eller blokkering.

---

### C2.8 Sanntids adaptiv trusseldeteksjon

Utviklere bør bruke avanserte trusseldeteksjonssystemer for AI som tilpasser seg nye angrepsmønstre og gir sanntidsbeskyttelse med kompilert mønstergjenkjenning.

 #2.8.1    Level: 1    Role: D/V
 Sørg for at trusseldeteksjonsmønstre er kompilerte inn i optimaliserte regex-motorer for høy ytelse i sanntidsfiltrering med minimal forsinkelsespåvirkning.
 #2.8.2    Level: 1    Role: D/V
 Bekreft at trusseldeteksjonssystemer opprettholder separate mønsterbiblioteker for forskjellige trusselkategorier (promptinjeksjon, skadelig innhold, sensitiv data, systemkommandoer).
 #2.8.3    Level: 2    Role: D/V
 Bekreft at adaptiv trusseldeteksjon inkluderer maskinlæringsmodeller som oppdaterer trusselens følsomhet basert på angrepsfrekvens og suksessrater.
 #2.8.4    Level: 2    Role: D/V
 Bekreft at trusselintelligensstrømmer i sanntid automatisk oppdaterer mønsterbiblioteker med nye angrepssignaturer og IOCs (indikatorer på kompromittering).
 #2.8.5    Level: 3    Role: D/V
 Sørg for at falske positive rater i trusseldeteksjon overvåkes kontinuerlig, og at mønsterspesifisitet automatisk justeres for å minimere forstyrrelser i legitime bruksområder.
 #2.8.6    Level: 3    Role: D/V
 Bekreft at kontekstuell trusselanalyse tar hensyn til inndatakilde, brukeratferdsmønstre og sesjonshistorikk for å forbedre deteksjonsnøyaktigheten.
 #2.8.7    Level: 3    Role: D/V
 Sørg for at ytelsesmålinger for trusseldeteksjon (deteksjonsrate, behandlingsforsinkelse, ressursutnyttelse) overvåkes og optimaliseres i sanntid.

---

### C2.9 Flermodalt sikkerhetsvalideringspipeline

Utviklere bør sørge for sikkerhetsvalidering for tekst, bilde, lyd og andre AI-inndatamodaliteter med spesifikke typer trusseldeteksjon og ressursisolasjon.

 #2.9.1    Level: 1    Role: D/V
 Bekreft at hver inputmodalitet har dedikerte sikkerhetsvalidatorer med dokumenterte trusselmodeller (tekst: promptinjeksjon, bilder: steganografi, lyd: spektrogramangrep) og deteksjonsterskler.
 #2.9.2    Level: 2    Role: D/V
 Bekreft at multimodale innganger behandles i isolerte sandkasser med definerte ressursgrenser (minne, CPU, behandlingstid) spesifikke for hver modalitetstype og dokumentert i sikkerhetspolicyer.
 #2.9.3    Level: 2    Role: D/V
 Verifiser at kryssmodale angrepsdeteksjon identifiserer koordinerte angrep som spenner over flere inputtyper (f.eks. steganografiske payloads i bilder kombinert med prompt-injeksjon i tekst) ved hjelp av korrelasjonsregler og varselsgenerering.
 #2.9.4    Level: 3    Role: D/V
 Bekreft at feil ved multimodal validering utløser detaljert logging som inkluderer alle inngangsmodaliteter, valideringsresultater, trusselpoeng og korrelasjonsanalyse med strukturerte loggformater for SIEM-integrasjon.
 #2.9.5    Level: 3    Role: D/V
 Bekreft at modalitetsspesifikke innholdsklassifiserere oppdateres i henhold til dokumenterte tidsplaner (minst kvartalsvis) med nye trusselmønstre, adversariale eksempler og ytelsesstandarder som opprettholdes over grunnlinjenivåer.

---

### Referanser

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

## C3-modell livssyklusstyring og endringskontroll

### Kontrollmål

AI-systemer må implementere endringskontrollprosesser som forhindrer uautoriserte eller usikre modellendringer fra å nå produksjon. Denne kontrollen sikrer modellens integritet gjennom hele livssyklusen—fra utvikling gjennom utrulling til utfasing—som muliggjør rask hendelsesrespons og opprettholder ansvarlighet for alle endringer.

Kjernesikkerhetsmål: Kun autoriserte, validerte modeller når produksjon ved å bruke kontrollerte prosesser som opprettholder integritet, sporbarhet og gjenopprettbarhet.

---

### C3.1 Modellautorisasjon og integritet

Kun autoriserte modeller med verifisert integritet når produksjonsmiljøer.

 #3.1.1    Level: 1    Role: D/V
 Bekreft at alle modellartefakter (vekter, konfigurasjoner, tokenizere) er kryptografisk signert av autoriserte enheter før distribuering.
 #3.1.2    Level: 1    Role: D/V
 Sørg for at modellens integritet valideres ved distribusjonstidspunkt, og at signaturverifiseringsfeil forhindrer lasting av modellen.
 #3.1.3    Level: 2    Role: D/V
 Verifiser at modellens opphavsregistreringer inkluderer en autoriserende enhets identitet, kontrollsummer for treningsdata, valideringstestresultater med godkjent/ikke godkjent status, og et opprettelsestidsstempel.
 #3.1.4    Level: 2    Role: D/V
 Bekreft at alle modellartefakter bruker semantisk versjonering (MAJOR.MINOR.PATCH) med dokumenterte kriterier som spesifiserer når hver versjonskomponent øker.
 #3.1.5    Level: 2    Role: V
 Bekreft at avhengighetssporing opprettholder et sanntidslager som muliggjør rask identifisering av alle systemer som bruker ressursene.

---

### C3.2 Modellvalidering og testing

Modeller må bestå definerte sikkerhets- og trygghetsvalideringer før distribusjon.

 #3.2.1    Level: 1    Role: D/V
 Sørg for at modeller gjennomgår automatisert sikkerhetstesting som inkluderer inndata validering, utdata sanitering, og sikkerhetsvurderinger med forhåndsavtalte organisatoriske bestått/ikke bestått terskler før distribusjon.
 #3.2.2    Level: 1    Role: D/V
 Bekreft at valideringsfeil automatisk blokkerer modellimplementering etter eksplisitt overstyringsgodkjenning fra forhåndsbestemt autorisert personell med dokumenterte forretningsbegrunnelser.
 #3.2.3    Level: 2    Role: V
 Bekreft at testrapportene er kryptografisk signert og uforanderlig knyttet til den spesifikke modellversjonens hash som blir validert.
 #3.2.4    Level: 2    Role: D/V
 Bekreft at nødutplasseringer krever dokumentert sikkerhetsrisikovurdering og godkjenning fra en forhåndsbestemt sikkerhetsmyndighet innen forhåndsavtalte tidsrammer.

---

### C3.3 Kontrollert utrulling og tilbakeføring

Modellutrullinger må kontrolleres, overvåkes og kunne reverseres.

 #3.3.1    Level: 1    Role: D
 Verifiser at produksjonsutrullinger implementerer gradvise utrullingsmekanismer (kanarirutrullinger, blå-grønn utrulling) med automatiske tilbakeføringsutløsere basert på forhåndsavtalte feilrater, latensgrenser eller sikkerhetsvarslingskriterier.
 #3.3.2    Level: 1    Role: D/V
 Bekreft at tilbakestillingsmuligheter gjenoppretter den komplette modelltilstanden (vekter, konfigurasjoner, avhengigheter) atomisk innenfor forhåndsdefinerte organisasjonelle tidsvinduer.
 #3.3.3    Level: 2    Role: D/V
 Bekreft at distribusjonsprosesser validerer kryptografiske signaturer og beregner integritetskontrollsummer før modellaktivering, og at distribusjonen feiler ved enhver avvik.
 #3.3.4    Level: 2    Role: D/V
 Bekreft at nødstoppfunksjoner for modellen kan deaktivere modellendepunkter innen forhåndsdefinerte responstider gjennom automatiske strømkretser eller manuelle avbrytere.
 #3.3.5    Level: 2    Role: V
 Bekreft at rollback-artifakter (tidligere modellversjoner, konfigurasjoner, avhengigheter) oppbevares i henhold til organisasjonens retningslinjer med uforanderlig lagring for hendelseshåndtering.

---

### C3.4 Endringsansvar og revisjon

Alle endringer i modellens livssyklus må kunne spores og revideres.

 #3.4.1    Level: 1    Role: V
 Bekreft at alle modellendringer (utrulling, konfigurasjon, utfasing) genererer uforanderlige revisjonslogger som inkluderer tidsstempel, en autentisert aktøridentitet, en endringstype, samt før- og efter-tilstander.
 #3.4.2    Level: 2    Role: D/V
 Bekreft at tilgang til revisjonsloggen krever riktig autorisasjon, og at alle tilgangsforsøk logges med brukeridentitet og tidsstempel.
 #3.4.3    Level: 2    Role: D/V
 Sørg for at promptmaler og systemmeldinger er versjonskontrollert i git-repositorier med obligatorisk kodegjennomgang og godkjenning fra utpekte vurderere før distribusjon.
 #3.4.4    Level: 2    Role: V
 Bekreft at revisjonslogger inneholder tilstrekkelige detaljer (modell-hasher, konfigurasjonsøyeblikksbilder, avhengighetsversjoner) for å muliggjøre fullstendig rekonstruksjon av modelltilstand for enhver tidsstempel innenfor oppbevaringsperioden.

---

### C3.5 Sikker utviklingspraksis

Modellutvikling og treningsprosesser må følge sikre metoder for å forhindre kompromittering.

 #3.5.1    Level: 1    Role: D
 Bekreft at modellutvikling, testing og produksjonsmiljøer er fysisk eller logisk adskilt. De skal ikke ha delt infrastruktur, ulike tilgangskontroller, og isolerte datalagre.
 #3.5.2    Level: 1    Role: D
 Sørg for at modelltrening og finjustering skjer i isolerte miljøer med kontrollert nettverkstilgang.
 #3.5.3    Level: 1    Role: D/V
 Bekreft at treningsdatas kilder blir validert gjennom integritetskontroller og autentisert via pålitelige kilder med dokumentert kjede av forvaring før bruk i modellutvikling.
 #3.5.4    Level: 2    Role: D
 Bekreft at modellutviklingsartefakter (hyperparametere, treningsskript, konfigurasjonsfiler) blir lagret i versjonskontroll og krever godkjenning fra kollegaer før bruk i trening.

---

### C3.6 Modellavvikling og avvikling av systemer

Modeller må trygt avvikles når de ikke lenger er nødvendige eller når sikkerhetsproblemer blir identifisert.

 #3.6.1    Level: 1    Role: D
 Sørg for at prosessene for nedleggelse av modeller automatisk skanner avhengighetsgrafer, identifiserer alle systemer som bruker modellen, og gir forhåndsavtalt varslingsperiode før utfasing.
 #3.6.2    Level: 1    Role: D/V
 Bekreft at arkiverte modellartefakter blir sikkert slettet ved bruk av kryptografisk utsletting eller flerpassoverskriving i henhold til dokumenterte retningslinjer for datalagring, med verifiserte destruksjonssertifikater.
 #3.6.3    Level: 2    Role: V
 Bekreft at hendelser for modellavvikling logges med tidsstempel og aktøridentitet, og at modellsignaturer tilbakekalles for å hindre gjenbruk.
 #3.6.4    Level: 2    Role: D/V
 Bekreft at nødmodellpensjonering kan deaktivere modelltilgang innen forhåndsbestemte tidsrammer for nødsituasjoner gjennom automatiske avstengningsmekanismer hvis kritiske sikkerhetssårbarheter oppdages.

---

### Referanser

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

## C4 infrastruktur, konfigurasjon og distribusjonssikkerhet

### Kontrollmål

AI-infrastrukturen må forsterkes mot privilegieeskalering, manipulasjon i leverandørkjeden og sidelengs bevegelse gjennom sikker konfigurasjon, isolasjon under kjøring, betrodde distribusjonspipelines og omfattende overvåking. Kun autoriserte, validerte infrastrukturkomponenter og konfigurasjoner når produksjon gjennom kontrollerte prosesser som opprettholder sikkerhet, integritet og revisjonsmuligheter.

Kjernemål for sikkerhet: Kun kryptografisk signerte, sårbarhetsskannede infrastrukturelementer når produksjon gjennom automatiserte valideringsrørledninger som håndhever sikkerhetspolicyer og opprettholder uforanderlige revisjonsspor.

---

### C4.1 Kjøretidsmiljøisolasjon

Forhindre containerflukt og privilegieeskalering gjennom kjerne-nivå isolasjonsprimitiver og obligatoriske tilgangskontroller.

 #4.1.1    Level: 1    Role: D/V
 Verifiser at alle AI-beholdere fjerner ALLE Linux-muligheter unntatt CAP_SETUID, CAP_SETGID, og eksplisitt nødvendige muligheter dokumentert i sikkerhetsbaselines.
 #4.1.2    Level: 1    Role: D/V
 Verifiser at seccomp-profiler blokkerer alle systemkall unntatt de som er i forhåndsgodkjente tillatlister, hvor brudd fører til at containeren termineres og sikkerhetsvarsler genereres.
 #4.1.3    Level: 2    Role: D/V
 Bekreft at AI-arbeidsbelastninger kjører med skrivbeskyttet rotfilsystem, tmpfs for midlertidige data, og navngitte volumer for vedvarende data med noexec monteringsalternativer håndhevet.
 #4.1.4    Level: 2    Role: D/V
 Bekreft at eBPF-basert kjøretidsovervåkning (Falco, Tetragon eller tilsvarende) oppdager forsøk på privilegieeskalering og automatisk avslutter prosesser som bryter reglene innenfor organisasjonens tidskrav for respons.
 #4.1.5    Level: 3    Role: D/V
 Verifiser at AI-arbeidsoppgaver med høy risiko kjøres i maskinvare-isolerte miljøer (Intel TXT, AMD SVM, eller dedikerte bare-metal noder) med attestasjonssjekk.

---

### C4.2 Sikker bygging og distribusjonspipelines

Sikre kryptografisk integritet og forsyningskjedesikkerhet gjennom reproduserbare bygg og signerte artefakter.

 #4.2.1    Level: 1    Role: D/V
 Sjekk at infrastruktur-som-kode skannes med verktøy (tfsec, Checkov eller Terrascan) ved hver commit, og at sammenslåinger blokkeres ved FUNN med KRITISK eller HØY alvorlighetsgrad.
 #4.2.2    Level: 1    Role: D/V
 Verifiser at containerbygg er reproducerbare med identiske SHA256-hashverdier på tvers av bygg, og generer SLSA nivå 3 opprinnelsesattester signert med Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Sørg for at containerbilder inneholder CycloneDX- eller SPDX-SBOM-er og er signert med Cosign før de pushes til registeret, slik at usignerte bilder avvises ved implementering.
 #4.2.4    Level: 2    Role: D/V
 Bekreft at CI/CD-pipelines bruker OIDC-tokener fra HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med levetider som ikke overstiger organisasjonens sikkerhetspolitiske grenser.
 #4.2.5    Level: 2    Role: D/V
 Verifiser at Cosign-signaturer og SLSA-proveniens blir validert under distribusjonsprosessen før containerkjøring, og at verifikasjonsfeil fører til at distribusjonen mislykkes.
 #4.2.6    Level: 2    Role: D/V
 Kontroller at byggeomgivelser kjøres i flyktige containere eller virtuelle maskiner uten vedvarende lagring og med nettverksisolasjon fra produksjons-VPC-er.

---

### C4.3 Nettverkssikkerhet og tilgangskontroll

Implementer nulltillitsnettverk med standardavslåtte retningslinjer og kryptert kommunikasjon.

 #4.3.1    Level: 1    Role: D/V
 Sørg for at Kubernetes NetworkPolicies eller tilsvarende implementerer standard nektelse for innkommende/utgående trafikk med eksplisitte tillatelsesregler for nødvendige porter (443, 8080, osv.).
 #4.3.2    Level: 1    Role: D/V
 Bekreft at SSH (port 22), RDP (port 3389) og skymetadata-endepunkter (169.254.169.254) er blokkert eller krever sertifikatbasert autentisering.
 #4.3.3    Level: 2    Role: D/V
 Bekreft at utgående trafikk filtreres gjennom HTTP/HTTPS-proxyer (Squid, Istio eller sky NAT-gatewayer) med domenetillatelser og at blokkerte forespørsler logges.
 #4.3.4    Level: 2    Role: D/V
 Bekreft at kommunikasjon mellom tjenester bruker gjensidig TLS med sertifikater som roteres i henhold til organisasjonens policy, og at sertifikatvalidering blir håndhevet (ingen skip-verify-flagg).
 #4.3.5    Level: 2    Role: D/V
 Bekreft at AI-infrastrukturen kjører i dedikerte VPCer/VNeter uten direkte internettilgang, og at kommunikasjonen skjer kun gjennom NAT-gatewayer eller bastion-verter.

---

### C4.4 Hemmeligheter og kryptografisk nøkkelhåndtering

Beskytt legitimasjon gjennom maskinvarebasert lagring og automatisk utskifting med nulltillits-tilgang.

 #4.4.1    Level: 1    Role: D/V
 Bekreft at hemmeligheter lagres i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering i ro ved bruk av AES-256.
 #4.4.2    Level: 1    Role: D/V
 Bekreft at kryptografiske nøkler genereres i FIPS 140-2 Level 2 HSM-er (AWS CloudHSM, Azure Dedicated HSM) med nøkkelrotasjon i henhold til organisasjonens kryptografiske policy.
 #4.4.3    Level: 2    Role: D/V
 Bekreft at rotering av hemmeligheter er automatisert med null nedetid ved distribusjon og umiddelbar rotering utløst av personalendringer eller sikkerhetshendelser.
 #4.4.4    Level: 2    Role: D/V
 Sørg for at containerbilder skannes med verktøy (GitLeaks, TruffleHog eller detect-secrets) som blokkerer bygg som inneholder API-nøkler, passord eller sertifikater.
 #4.4.5    Level: 2    Role: D/V
 Verifiser at tilgang til produksjonshemmeligheter krever MFA med maskinvaretokener (YubiKey, FIDO2) og at dette registreres i uforanderlige revisjonslogger med brukeridentiteter og tidsstempler.
 #4.4.6    Level: 2    Role: D/V
 Verifiser at hemmeligheter injiseres via Kubernetes-hemmeligheter, monterte volumer eller init-containere, og sørg for at hemmeligheter aldri er innebygd i miljøvariabler eller bilder.

---

### C4.5 AI-arbeidsbelastningssandboxing og validering

Isoler uautoriserte AI-modeller i sikre sandkasser med omfattende atferdsanalyse.

 #4.5.1    Level: 1    Role: D/V
 Bekreft at eksterne AI-modeller kjøres i gVisor, microVM-er (som Firecracker, CrossVM) eller Docker-containere med --security-opt=no-new-privileges og --read-only flagg.
 #4.5.2    Level: 1    Role: D/V
 Verifiser at sandkassemiljøer ikke har nettverkstilkobling (--network=none) eller kun lokaltilgang med alle eksterne forespørsler blokkert av iptables-regler.
 #4.5.3    Level: 2    Role: D/V
 Bekreft at validering av AI-modellen inkluderer automatisert red-team-testing med organisasjonsdefinert testdekning og atferdsanalyse for oppdagelse av bakdører.
 #4.5.4    Level: 2    Role: D/V
 Bekreft at før en AI-modell blir tatt i produksjon, blir resultatene fra sandkassen kryptografisk signert av autorisert sikkerhetspersonell og lagret i uforanderlige revisjonslogger.
 #4.5.5    Level: 2    Role: D/V
 Bekreft at sandkassemiljøer blir ødelagt og gjenopprettet fra gullbilder mellom evalueringer med fullstendig opprydding av filsystem og minne.

---

### C4.6 Infrastruktur Sikkerhetsovervåkning

Kontinuerlig skann og overvåk infrastruktur med automatisert utbedring og varsling i sanntid.

 #4.6.1    Level: 1    Role: D/V
 Kontroller at containerbilder skannes i henhold til organisasjonens tidsplaner, der KRITISKE sårbarheter blokkerer distribusjon basert på organisasjonens risikogrenseverdier.
 #4.6.2    Level: 1    Role: D/V
 Bekreft at infrastrukturen oppfyller CIS Benchmarks eller NIST 800-53-kontroller med organisasjonsdefinerte samsvarsterskler og automatisk utbedring for mislykkede kontroller.
 #4.6.3    Level: 2    Role: D/V
 Bekreft at sårbarheter med HØY alvorlighetsgrad blir utbedret i henhold til organisasjonens tidslinjer for risikostyring, med nødprosedyrer for aktivt utnyttede CVE-er.
 #4.6.4    Level: 2    Role: V
 Bekreft at sikkerhetsvarsler integreres med SIEM-plattformer (Splunk, Elastic eller Sentinel) ved hjelp av CEF- eller STIX/TAXII-formater med automatisert berikelse.
 #4.6.5    Level: 3    Role: V
 Verifiser at infrastrukturmålinger eksporteres til overvåkingssystemer (Prometheus, DataDog) med SLA-dashbord og ledelsesrapportering.
 #4.6.6    Level: 2    Role: D/V
 Bekreft at konfigurasjonsavvik oppdages ved bruk av verktøy (Chef InSpec, AWS Config) i henhold til organisatoriske overvåkningskrav, med automatisk tilbakeføring for uautoriserte endringer.

---

### C4.7 AI-infrastruktur Ressursadministrasjon

Forhindre angrep som tømmer ressurser og sikre rettferdig ressursfordeling gjennom kvoter og overvåking.

 #4.7.1    Level: 1    Role: D/V
 Bekreft at GPU/TPU-utnyttelse overvåkes med varsler som utløses ved organisatorisk definerte terskler, og at automatisk skalering eller lastbalansering aktiveres basert på kapasitetsstyringspolitikker.
 #4.7.2    Level: 1    Role: D/V
 Bekreft at AI-arbeidsbelastningsmetrikker (inferenceslatenstid, gjennomstrømning, feilrater) samles inn i henhold til organisasjonens overvåkingskrav og korreleres med infrastrukturutnyttelse.
 #4.7.3    Level: 2    Role: D/V
 Bekreft at Kubernetes ResourceQuotas eller tilsvarende begrenser individuelle arbeidsbelastninger i henhold til organisasjonens retningslinjer for ressursallokering, med harde grenser håndhevet.
 #4.7.4    Level: 2    Role: V
 Bekreft at kostnadsovervåking sporer utgifter per arbeidsbelastning/leietaker med varsler basert på organisatoriske budsjettgrenser og automatiserte kontroller for budsjettoverskridelser.
 #4.7.5    Level: 3    Role: V
 Bekreft at kapasitetsplanlegging bruker historiske data med organisasjonsdefinerte prognoseperioder og automatisert ressursprovisjonering basert på etterspørselsmønstre.
 #4.7.6    Level: 2    Role: D/V
 Bekreft at ressursutarming utløser kretsbrytere i henhold til organisasjonens responskrav, inkludert hastighetsbegrensning basert på kapasitetsregler og isolasjon av arbeidsbelastning.

---

### C4.8 Miljøseparasjon og Kontroll av Fremming

Håndhev strenge miljøgrenser med automatiske godkjenningsporter for promotering og sikkerhetsvalidering.

 #4.8.1    Level: 1    Role: D/V
 Bekreft at utviklings-, test- og produksjonsmiljøer kjører i separate VPC-er/VNets uten delte IAM-roller, sikkerhetsgrupper eller nettverksforbindelser.
 #4.8.2    Level: 1    Role: D/V
 Verifiser at miljøfremming krever godkjenning fra organisatorisk definerte autoriserte personer med kryptografiske signaturer og uforanderlige revisjonsspor.
 #4.8.3    Level: 2    Role: D/V
 Bekreft at produksjonsmiljøer blokkerer SSH-tilgang, deaktiverer debug-endepunkter, og krever endringsforespørsler med organisatoriske varslingskrav på forhånd, unntatt i nødstilfeller.
 #4.8.4    Level: 2    Role: D/V
 Bekreft at endringer i infrastruktur-som-kode krever fagfellevurdering med automatisert testing og sikkerhetsskanning før sammenslåing til hovedgrenen.
 #4.8.5    Level: 2    Role: D/V
 Bekreft at ikke-produksjonsdata er anonymisert i henhold til organisasjonens personvernkrav, syntetisk datagenerering eller fullstendig datamaskering med verifisert fjerning av personidentifiserbar informasjon (PII).
 #4.8.6    Level: 2    Role: D/V
 Bekreft at promoteringstrinn inkluderer automatiserte sikkerhetstester (SAST, DAST, container-skanning) med null KRITISKE funn som krav for godkjenning.

---

### C4.9 Infrastruktur Sikkerhetskopiering og Gjenoppretting

Sikre infrastrukturens robusthet gjennom automatiserte sikkerhetskopier, testede gjenopprettingsprosedyrer og katastrofegjenopprettingsmuligheter.

 #4.9.1    Level: 1    Role: D/V
 Bekreft at infrastrukturkonfigurasjoner sikkerhetskopieres i henhold til organisasjonens sikkerhetskopieringsplaner til geografisk adskilte regioner med implementering av 3-2-1 sikkerhetskopieringsstrategi.
 #4.9.2    Level: 2    Role: D/V
 Bekreft at backupsystemer kjører i isolerte nettverk med separate legitimasjoner og lufttettes lagringsløsninger for beskyttelse mot løsepengevirus.
 #4.9.3    Level: 2    Role: V
 Bekreft at gjenopprettingsprosedyrer testes og verifiseres gjennom automatisert testing i henhold til organisasjonens tidsplaner, med RTO- og RPO-mål som oppfyller organisasjonens krav.
 #4.9.4    Level: 3    Role: V
 Bekreft at katastrofegjenoppretting inkluderer AI-spesifikke kjøreplaner med gjenoppretting av modellvekter, gjenoppbygging av GPU-klynger og kartlegging av tjenesteavhengigheter.

---

### C4.10 Infrastruktur etterlevelse og styring

Oppretthold regulatorisk etterlevelse gjennom kontinuerlig vurdering, dokumentasjon og automatiserte kontroller.

 #4.10.1    Level: 2    Role: D/V
 Bekreft at infrastrukturens samsvar vurderes i henhold til organisatoriske tidsplaner mot SOC 2, ISO 27001 eller FedRAMP-kontroller med automatisert innsamling av bevis.
 #4.10.2    Level: 2    Role: V
 Sørg for at infrastruktuurdokumentasjonen inkluderer nettverksdiagrammer, datakart over flyt og trusselmodeller oppdatert i samsvar med organisasjonens endringsstyringskrav.
 #4.10.3    Level: 3    Role: D/V
 Bekreft at infrastrukturelle endringer gjennomgår automatisert vurdering av samsvarspåvirkning med regulatoriske godkjenningsarbeidsflyter for høyrisikoendringer.

---

### C4.11 AI-maskinvare-sikkerhet

Sikre AI-spesifikke maskinvarekomponenter inkludert GPUer, TPUer og spesialiserte AI-akseleratorer.

 #4.11.1    Level: 2    Role: D/V
 Verifiser at fastvaren for AI-akseleratorer (GPU BIOS, TPU-fastvare) er verifisert med kryptografiske signaturer og oppdatert i henhold til organisasjonens tidslinjer for patch-administrasjon.
 #4.11.2    Level: 2    Role: D/V
 Bekreft at før arbeidsbelastningsutførelse blir AI-akseleratorens integritet validert gjennom maskinvareattestasjon ved bruk av TPM 2.0, Intel TXT eller AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Bekreft at GPU-minne er isolert mellom arbeidsbelastninger ved bruk av SR-IOV, MIG (Multi-Instance GPU) eller tilsvarende maskinvarepartisjonering med minne-sanitetskontroll mellom jobbene.
 #4.11.4    Level: 3    Role: V
 Bekreft at AI-maskinvareleverandørkjeden inkluderer verifisering av opprinnelse med produsentsertifikater og validering av manipulering-sikker emballasje.
 #4.11.5    Level: 3    Role: D/V
 Bekreft at maskinvare sikkerhetsmoduler (HSM-er) beskytter AI-modellvekter og kryptografiske nøkler med FIPS 140-2 nivå 3 eller Common Criteria EAL4+ sertifisering.

---

### C4.12 Kant- og distribuert KI-infrastruktur

Sikre distribuerte AI-distribusjoner inkludert kantdatabehandling, føderert læring og flersite-arkitekturer.

 #4.12.1    Level: 2    Role: D/V
 Bekreft at edge AI-enheter autentiserer seg til sentral infrastruktur ved bruk av gjensidig TLS med enhetssertifikater som roteres i henhold til organisasjonens sertifikathåndteringspolicy.
 #4.12.2    Level: 2    Role: D/V
 Bekreft at kant-enheter implementerer sikker oppstart med verifiserte signaturer og beskyttelse mot tilbakerulling som forhindrer angrep som nedgraderer fastvaren.
 #4.12.3    Level: 3    Role: D/V
 Bekreft at distribuert AI-koordinering bruker bysantinsk feil-tolerante konsensusalgoritmer med deltakerbekreftelse og ondsinnet nodetoppdagelse.
 #4.12.4    Level: 3    Role: D/V
 Verifiser at kommunikasjon fra kant til sky inkluderer båndbreddebegrensning, datakomprimering og offline driftsmuligheter med sikker lokal lagring.

---

### C4.13 Sikkerhet for Multi-Cloud og Hybrid Infrastruktur

Sikre AI-arbeidsbelastninger på tvers av flere skyleverandører og hybride sky- og lokale distribusjoner.

 #4.13.1    Level: 2    Role: D/V
 Bekreft at fler-sky AI-distribusjoner bruker sky-agnostisk identitetsfederasjon (OIDC, SAML) med sentralisert policyhåndtering på tvers av leverandører.
 #4.13.2    Level: 2    Role: D/V
 Bekreft at tverr-sky dataoverføring bruker ende-til-ende-kryptering med kundestyrte nøkler og at datalokaliseringkontroller håndheves i henhold til jurisdiksjon.
 #4.13.3    Level: 2    Role: D/V
 Bekreft at hybride sky-AI-arbeidsbelastninger implementerer konsistente sikkerhetspolicyer på tvers av lokale og skybaserte miljøer med enhetlig overvåking og varsling.
 #4.13.4    Level: 3    Role: V
 Bekreft at forebygging av leverandørlåsning i skyen inkluderer bærbar infrastruktur-som-kode, standardiserte API-er og dataeksportmuligheter med verktøy for formatkonvertering.
 #4.13.5    Level: 3    Role: V
 Bekreft at kostnadsoptimalisering for multi-cloud inkluderer sikkerhetskontroller som hindrer ressursutbredelse samt uautoriserte kostnader for dataoverføring mellom skyer.

---

### C4.14 Infrastrukturautomatisering og GitOps-sikkerhet

Sikre automatiseringspipelines for infrastruktur og GitOps-arbeidsflyter for administrasjon av AI-infrastruktur.

 #4.14.1    Level: 2    Role: D/V
 Bekreft at GitOps-repositorier krever signerte commits med GPG-nøkler og branch protection-regler som forhindrer direkte push til hovedbrancher.
 #4.14.2    Level: 2    Role: D/V
 Bekreft at infrastrukturautomatisering inkluderer avvikdeteksjon med automatiske utbedrings- og tilbakestillingsfunksjoner som utløses i henhold til organisasjonens responskrav for uautoriserte endringer.
 #4.14.3    Level: 2    Role: D/V
 Verifiser at automatisert infrastrukturprovisjonering inkluderer validering av sikkerhetspolicyer med distribusjonsblokker for ikke-kompatible konfigurasjoner.
 #4.14.4    Level: 2    Role: D/V
 Bekreft at hemmeligheter for infrastrukturautomatisering administreres gjennom eksterne hemmelighetsoperatører (External Secrets Operator, Bank-Vaults) med automatisk rotasjon.
 #4.14.5    Level: 3    Role: V
 Verifiser at selvhelbredende infrastruktur inkluderer sikkerhetshendelseskorrelasjon med automatisert hendelsesrespons og arbeidsflyter for varsling av interessenter.

---

### C4.15 Kvantesikker Infrastruktur Sikkerhet

Forbered AI-infrastruktur for trusler fra kvanteberegning gjennom post-kvantet kryptografi og kvantesikre protokoller.

 #4.15.1    Level: 3    Role: D/V
 Bekreft at AI-infrastrukturen implementerer NIST-godkjente post-kvantematiske kryptografiske algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) for nøkkelutveksling og digitale signaturer.
 #4.15.2    Level: 3    Role: D/V
 Verifiser at kvantenøkkeldistribusjon (QKD) systemer er implementert for høysikkerhets AI-kommunikasjon med kvantesikre nøkkelhåndteringsprotokoller.
 #4.15.3    Level: 3    Role: D/V
 Sørg for at kryptografiske smidighetsrammeverk muliggjør rask migrering til nye post-kvante algoritmer med automatisert sertifikat- og nøkkelrotasjon.
 #4.15.4    Level: 3    Role: V
 Verifiser at kvantetrusselmodellering vurderer AI-infrastrukturens sårbarhet for kvanteangrep med dokumenterte migrasjonstidslinjer og risikovurderinger.
 #4.15.5    Level: 3    Role: D/V
 Verifiser at hybride klassiske-kvant kryptografiske systemer gir forsvar-i-dybden under kvantetransisjonsperioden med ytelsesovervåking.

---

### C4.16 Konfidensiell databehandling og sikre soner

Beskytt AI-arbeidsmengder og modellvekter ved hjelp av maskinvarebaserte pålitelige utførelsesmiljøer og konfidensielle databehandlingsteknologier.

 #4.16.1    Level: 3    Role: D/V
 Verifiser at sensitive AI-modeller kjører innenfor Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med kryptert minne og attestasjonsverifisering.
 #4.16.2    Level: 3    Role: D/V
 Bekreft at konfidensielle containere (Kata Containers, gVisor med konfidensiell databehandling) isolerer AI-arbeidsbelastninger med maskinvarehåndhevet minne-kryptering.
 #4.16.3    Level: 3    Role: D/V
 Bekreft at fjernattestering validerer integriteten til enclave før lasting av AI-modeller med kryptografisk bevis på eksekveringsmiljøets autentisitet.
 #4.16.4    Level: 3    Role: D/V
 Bekreft at konfidensielle AI-inferenstjenester forhindrer modelekstraksjon gjennom kryptert beregning med forseglede modellvekter og beskyttet utførelse.
 #4.16.5    Level: 3    Role: D/V
 Bekreft at orkestrering av Trusted Execution Environment håndterer livssyklusen til sikre innhegninger med fjernattestasjon og krypterte kommunikasjonskanaler.
 #4.16.6    Level: 3    Role: D/V
 Bekreft at sikker flerpartsberegning (SMPC) muliggjør samarbeidende AI-trening uten å eksponere individuelle datasett eller modellparametere.

---

### C4.17 Nullkunnskapsinfrastruktur

Implementer null-kunnskapsbevis-systemer for personvernbevarende AI-verifisering og autentisering uten å avsløre sensitiv informasjon.

 #4.17.1    Level: 3    Role: D/V
 Bekreft at nullkunnskapsbevis (ZK-SNARKs, ZK-STARKs) verifiserer AI-modellens integritet og treningsopprinnelse uten å eksponere modellvekter eller treningsdata.
 #4.17.2    Level: 3    Role: D/V
 Bekreft at ZK-baserte autentiseringssystemer muliggjør personvernbevarende brukerverifisering for AI-tjenester uten å avsløre identitetsrelatert informasjon.
 #4.17.3    Level: 3    Role: D/V
 Bekreft at protokoller for privat mengdeinterseksjon (PSI) muliggjør sikker datamatching for føderert KI uten å eksponere individuelle datasett.
 #4.17.4    Level: 3    Role: D/V
 Bekreft at nullkunnskaps maskinlæringssystemer (ZKML) muliggjør verifiserbare AI-slutninger med kryptografisk bevis for korrekt beregning.
 #4.17.5    Level: 3    Role: D/V
 Bekreft at ZK-rollups gir skalerbar, personvernbevarende AI-transaksjonsbehandling med batch-verifisering og redusert beregningsmessig overhead.

---

### C4.18 Forebygging av sidekanalsangrep

Beskytt AI-infrastrukturen mot tidsmessige, strøm-, elektromagnetiske og cache-baserte sidekanalangrep som kan lekke sensitiv informasjon.

 #4.18.1    Level: 3    Role: D/V
 Bekreft at AI-inferensens tid er normalisert ved hjelp av konstant-tidsalgoritmer og utfylling for å forhindre tidsbaserte modelluttrekksangrep.
 #4.18.2    Level: 3    Role: D/V
 Bekreft at strømmetodikkbeskyttelse inkluderer støyinjeksjon, filtrering av strømledningen og randomiserte utførelsesmønstre for AI-maskinvare.
 #4.18.3    Level: 3    Role: D/V
 Bekreft at sidekanalinformasjonssikkerhet basert på cache bruker cache-partisjonering, randomisering og flush-instruksjoner for å forhindre informasjonslekkasje.
 #4.18.4    Level: 3    Role: D/V
 Bekreft at beskyttelse mot elektromagnetisk utsendelse inkluderer skjerming, signalfiltrering og tilfeldig behandling for å forhindre TEMPEST-lignende angrep.
 #4.18.5    Level: 3    Role: D/V
 Bekreft at mikrounderarkitektoniske sidekanalforsvar inkluderer kontroll av spekulativ utførelse og obfuskering av mønstre for minnetilgang.

---

### C4.19 Neuromorfe og spesialiserte AI-maskinvare-sikkerhet

Sikre fremvoksende AI-maskinvarearkitekturer, inkludert nevromorfe brikker, FPGAer, spesialtilpassede ASICer og optiske datasystemer.

 #4.19.1    Level: 3    Role: D/V
 Verifiser at sikkerheten til nevromorfe brikker inkluderer kryptering av spike-mønstre, beskyttelse av synaptiske vekter og maskinvarebasert validering av læringsregler.
 #4.19.2    Level: 3    Role: D/V
 Bekreft at FPGA-baserte AI-akseleratorer implementerer bitstrøm-kryptering, anti-manipulasjonsmekanismer og sikker konfigurasjonslasting med autentiserte oppdateringer.
 #4.19.3    Level: 3    Role: D/V
 Bekreft at tilpasset ASIC-sikkerhet inkluderer sikkerhetsprosessorer på brikken, maskinvarebasert tillitsrot, og sikker nøkkellagring med manipuleringdeteksjon.
 #4.19.4    Level: 3    Role: D/V
 Verifiser at optiske databehandlingssystemer implementerer kvantesikker optisk kryptering, sikker fotonisk switching og beskyttet optisk signalbehandling.
 #4.19.5    Level: 3    Role: D/V
 Bekreft at hybride analoge-digitale AI-brikker inkluderer sikker analog beregning, beskyttet lagring av vekter, og autentisert analog-til-digital konvertering.

---

### C4.20 Personvernbevarende beregningsinfrastruktur

Implementer infrastrukturelle kontroller for personvernbevarende beregning for å beskytte sensitiv data under AI-behandling og -analyse.

 #4.20.1    Level: 3    Role: D/V
 Bekreft at homomorf krypteringsinfrastruktur muliggjør kryptert behandling av sensitive AI-arbeidsbelastninger med kryptografisk integritetsverifisering og ytelsesovervåking.
 #4.20.2    Level: 3    Role: D/V
 Verifiser at private informasjonsinnhentingssystemer muliggjør databasespørringer uten å avsløre spørringsmønstre ved hjelp av kryptografisk beskyttelse av tilgangsmønstre.
 #4.20.3    Level: 3    Role: D/V
 Verifiser at sikre protokoller for flerpartssamarbeid muliggjør personvernbevarende AI-sluttningsbehandling uten å avsløre individuelle input eller mellomliggende beregninger.
 #4.20.4    Level: 3    Role: D/V
 Bekreft at personvern-bevarende nøkkelhåndtering inkluderer distribuert nøkkelgenerering, terskelkryptografi og sikker nøkkelrotasjon med maskinvarebasert beskyttelse.
 #4.20.5    Level: 3    Role: D/V
 Verifiser at personvernbevarende beregningsytelse er optimalisert gjennom batchbehandling, caching og maskinvareakselerasjon, samtidig som kryptografiske sikkerhetsgarantier opprettholdes.

---

### C4.15 Agent-rammeverk Skysikkerhet og Hybrid Distribusjon

Sikkerhetskontroller for skyintegrerte agentrammeverk med hybride lokale/skyarkitekturer.

 #4.15.1    Level: 1    Role: D/V
 Verifiser at skylagringsintegrasjonen bruker ende-til-ende kryptering med agentstyrt nøkkelhåndtering.
 #4.15.2    Level: 2    Role: D/V
 Bekreft at sikkerhetsgrensene for hybrid distribusjon er klart definert med krypterte kommunikasjonskanaler.
 #4.15.3    Level: 2    Role: D/V
 Bekreft at tilgang til skyressurser inkluderer nulltillitverifisering med kontinuerlig autentisering.
 #4.15.4    Level: 3    Role: D/V
 Bekreft at krav til datalokalisering håndheves gjennom kryptografisk attestasjon av lagringssteder.
 #4.15.5    Level: 3    Role: D/V
 Bekreft at sikkerhetsvurderinger hos skyleverandører inkluderer agent-spesifikk trusselmodellering og risikovurdering.

---

### Referanser

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

## C5 Tilgangskontroll og identitet for AI-komponenter og brukere

### Kontrollmål

Effektiv tilgangskontroll for AI-systemer krever robust identitetsstyring, kontekstbevisst autorisasjon og håndheving i sanntid i samsvar med prinsippene for nulltillit. Disse kontrollene sikrer at mennesker, tjenester og autonome agenter kun samhandler med modeller, data og beregningsressurser innenfor uttrykkelig tildelte områder, med kontinuerlig verifisering og revisjonsmuligheter.

---

### C5.1 Identitetsstyring og autentisering

Etabler kryptografisk sikrede identiteter for alle enheter med multifaktorautentisering for privilegerte operasjoner.

 #5.1.1    Level: 1    Role: D/V
 Bekreft at alle menneskelige brukere og tjenesteprinsipper autentiserer gjennom en sentralisert bedriftsidentitetsleverandør (IdP) ved bruk av OIDC/SAML-protokoller med unike identitet-til-token-kartlegginger (ingen delte kontoer eller legitimasjoner).
 #5.1.2    Level: 1    Role: D/V
 Verifiser at høy-risiko operasjoner (modellutplassering, eksport av vekter, tilgang til treningsdata, endringer i produksjonskonfigurasjon) krever flerfaktorautentisering eller trinnvis autentisering med sesjonsrevalidering.
 #5.1.3    Level: 2    Role: D
 Bekreft at nye ledere gjennomgår identitetsverifisering i samsvar med NIST 800-63-3 IAL-2 eller tilsvarende standarder før de får tilgang til produksjonssystemet.
 #5.1.4    Level: 2    Role: V
 Bekreft at tilgangsvurderinger gjennomføres kvartalsvis med automatisk deteksjon av inaktive kontoer, håndheving av legitimasjonsrotasjon og arbeidsflyter for avvikling av tilganger.
 #5.1.5    Level: 3    Role: D/V
 Bekreft at fødererte AI-agenter autentiserer via signerte JWT-påstander som har en maksimal levetid på 24 timer og inkluderer kryptografisk bevis på opprinnelse.

---

### C5.2 Ressursautorisasjon og minst privilegium

Implementer detaljerte tilgangskontroller for alle AI-ressurser med eksplisitte rettighetsmodeller og revisjonsspor.

 #5.2.1    Level: 1    Role: D/V
 Bekreft at alle AI-ressurser (datasett, modeller, endepunkter, vektorsamlinger, innebygde indekser, databehandlingsinstanser) håndhever rollebaserte tilgangskontroller med eksplisitte tillatelseslister og standard-avvisningsregler.
 #5.2.2    Level: 1    Role: D/V
 Verifiser at prinsippene for minst privilegium håndheves som standard for tjenestekontoer, med start i lese-only tillatelser og dokumentert forretningsbegrunnelse kreves for skrivetilgang.
 #5.2.3    Level: 1    Role: V
 Bekreft at alle endringer i tilgangskontroll er knyttet til godkjente endringsforespørsler og loggført uforanderlig med tidsstempler, aktøridentiteter, ressursidentifikatorer og tillatelsesendringer.
 #5.2.4    Level: 2    Role: D
 Bekreft at dataklassifiseringsetiketter (PII, PHI, eksportkontrollert, proprietær) automatisk overføres til avledede ressurser (innebygde data, prompt-cacher, modellutdata) med konsekvent håndhevelse av retningslinjer.
 #5.2.5    Level: 2    Role: D/V
 Bekreft at uautoriserte tilgangsforsøk og hendelser med privilegieeskalering utløser sanntidsvarsler med kontekstuell metadata til SIEM-systemer innen 5 minutter.

---

### C5.3 Dynamisk policyevaluering

Distribuer attributtbaserte tilgangskontrollmotorer (ABAC) for kontekstbevisste autorisasjonsbeslutninger med revisjonsmuligheter.

 #5.3.1    Level: 1    Role: D/V
 Bekreft at autorisasjonsbeslutninger er eksternalisert til en dedikert policy-motor (OPA, Cedar eller tilsvarende) tilgjengelig via autentiserte API-er med kryptografisk integritetsbeskyttelse.
 #5.3.2    Level: 1    Role: D/V
 Bekreft at policyer evaluerer dynamiske attributter ved kjøretid, inkludert brukerens klareringsnivå, ressursens sensitivitetklassifisering, forespørselskontekst, leietakerisolasjon og tidsmessige begrensninger.
 #5.3.3    Level: 2    Role: D
 Bekreft at policydefinisjoner er versjonskontrollerte, fagfellevurderte og validert gjennom automatisert testing i CI/CD-pipelines før produksjonsutrulling.
 #5.3.4    Level: 2    Role: V
 Verifiser at resultatene av policyvurderinger inkluderer strukturerte beslutningsbegrunnelser og overføres til SIEM-systemer for korrelasjonsanalyse og samsvarsrapportering.
 #5.3.5    Level: 3    Role: D/V
 Verifiser at policyens hurtigbuffer leve tid (TTL) ikke overstiger 5 minutter for høysensitive ressurser og 1 time for standardressurser med muligheter for hurtigbufferinvalidering.

---

### C5.4 Sikkerhetskontroll ved spørringstidspunktet

Implementer sikkerhetskontroller på databaselaget med obligatorisk filtrering og sikkerhetspolicyer på radnivå.

 #5.4.1    Level: 1    Role: D/V
 Sørg for at alle spørringer mot vektordatabaser og SQL inkluderer obligatoriske sikkerhetsfiltre (leietaker-ID, sensitivitetsetiketter, brukeromfang) som håndheves på databasmotornivå, ikke i applikasjonskoden.
 #5.4.2    Level: 1    Role: D/V
 Verifiser at retningslinjer for radnivåsikkerhet (RLS) og feltnivåmaskering er aktivert med policyarv for alle vektordatabaser, søkeindekser og treningsdatasett.
 #5.4.3    Level: 2    Role: D
 Bekreft at mislykkede autorisasjonsvurderinger vil forhindre "forvirret stedfortreder-angrep" ved umiddelbart å avbryte forespørsler og returnere eksplisitte autorisasjonsfeilkoder i stedet for å returnere tomme resultatsett.
 #5.4.4    Level: 2    Role: V
 Bekreft at evaluering av policy-latenstid kontinuerlig overvåkes med automatiske varsler for tidsavbruddsbetingelser som kan muliggjøre omgåring av autorisasjon.
 #5.4.5    Level: 3    Role: D/V
 Bekreft at mekanismer for forsøk på nytt av spørringer revurderer autorisasjonspolicyer for å ta hensyn til dynamiske endringer i tillatelser innen aktive brukersesjoner.

---

### C5.5 Utdatafiltrering og datatapforebygging

Implementer etterbehandlingskontroller for å forhindre uautorisert datalekkasjer i AI-generert innhold.

 #5.5.1    Level: 1    Role: D/V
 Verifiser at filtreringsmekanismer etter inferens skanner og fjerner uautorisert personlig identifiserbar informasjon (PII), klassifisert informasjon og proprietære data før innhold leveres til forespørslere.
 #5.5.2    Level: 1    Role: D/V
 Bekreft at henvisninger, referanser og kildeangivelser i modellresultater er validert mot anroperens rettigheter, og fjernes hvis uautorisert tilgang oppdages.
 #5.5.3    Level: 2    Role: D
 Bekreft at restriksjoner for utdataformat (rengjorte PDF-filer, metadata-frie bilder, godkjente filtyper) håndheves basert på brukerens tillatelsesnivåer og dataklassifiseringer.
 #5.5.4    Level: 2    Role: V
 Sørg for at redigeringsalgoritmer er deterministiske, versjonskontrollerte og opprettholder revisjonslogger for å støtte samsvarsetterforskninger og rettsmedisinsk analyse.
 #5.5.5    Level: 3    Role: V
 Bekreft at høy-risiko redigeringshendelser genererer adaptive logger som inkluderer kryptografiske hashverdier av originalt innhold for rettsmedisinsk gjenfinning uten datalekkasjer.

---

### C5.6 Multi-leietakerisolasjon

Sikre kryptografisk og logisk isolasjon mellom leietakere i delt AI-infrastruktur.

 #5.6.1    Level: 1    Role: D/V
 Verifiser at minneområder, innebygde lagre, hurtigbufferoppføringer og midlertidige filer er adskilt per leietaker med sikker sletting ved sletting av leietaker eller avslutning av økt.
 #5.6.2    Level: 1    Role: D/V
 Verifiser at hver API-forespørsel inkluderer en autentisert leietakeridentifikator som er kryptografisk validert mot sesjonskontekst og brukerrettigheter.
 #5.6.3    Level: 2    Role: D
 Bekreft at nettverkspolitikker implementerer standard-nekt regler for kommunikasjon på tvers av leietakere innen tjenestenettverk og plattformer for containerorkestrering.
 #5.6.4    Level: 3    Role: D
 Bekreft at krypteringsnøkler er unike per leietaker med kundeadministrert nøkkel (CMK)-støtte og kryptografisk isolasjon mellom leietakers datalagre.

---

### C5.7 Autonom agentgodkjenning

Kontroller tillatelser for AI-agenter og autonome systemer gjennom avgrensede kapabilitetstokener og kontinuerlig autorisasjon.

 #5.7.1    Level: 1    Role: D/V
 Bekreft at autonome agenter mottar begrensede kapabilitetstokener som eksplisitt angir tillatte handlinger, tilgjengelige ressurser, tidsrammer og driftsbegrensninger.
 #5.7.2    Level: 1    Role: D/V
 Bekreft at høy-risiko funksjoner (tilgang til filsystem, kodekjøring, eksterne API-kall, finansielle transaksjoner) er deaktivert som standard og krever eksplisitte godkjenninger for aktivering med forretningsmessige begrunnelser.
 #5.7.3    Level: 2    Role: D
 Bekreft at kapabilitetstokener er knyttet til brukersesjoner, inkluderer kryptografisk integritetsbeskyttelse, og sikre at de verken kan lagres eller gjenbrukes i frakoblede situasjoner.
 #5.7.4    Level: 2    Role: V
 Bekreft at agent-initierte handlinger gjennomgår sekundær godkjenning via ABAC-policy-motoren med full kontekstevaluering og revisjonslogging.
 #5.7.5    Level: 3    Role: V
 Bekreft at agentfeilbetingelser og unntakshåndtering inkluderer informasjon om kapabilitetsomfang for å støtte hendelsesanalyse og rettsmedisinsk etterforskning.

---

### Referanser

#### Standarder og rammeverk

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Implementasjonsveiledninger

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### AI-spesifikk sikkerhet

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Forsyningskjedesikkerhet for modeller, rammeverk og data

### Kontrollmål

Angrep på AI-forsyningskjeden utnytter tredjepartsmodeller, -rammeverk eller -datasett for å legge inn bakdører, skjevheter eller utnyttbar kode. Disse kontrollene gir ende-til-ende opprinnelse, sårbarhetsstyring og overvåking for å beskytte hele modellens livssyklus.

---

### C6.1 Forhåndstrent modellvurdering og opprinnelse

Vurder og autentiser tredjepartsmodellers opprinnelse, lisenser og skjulte atferd før finjustering eller distribusjon.

 #6.1.1    Level: 1    Role: D/V
 Bekreft at hvert tredjeparts modellartefakt inkluderer en signert opprinnelsespost som identifiserer kildearkivet og commit-hashen.
 #6.1.2    Level: 1    Role: D/V
 Bekreft at modeller skannes for ondsinnede lag eller trojanske utløsere ved hjelp av automatiserte verktøy før import.
 #6.1.3    Level: 2    Role: D
 Verifiser at overføringslæring finjusteres for å bestå adversariell evaluering for å oppdage skjulte atferder.
 #6.1.4    Level: 2    Role: V
 Bekreft at modell-lisenser, eksportkontrollmerker og dataopprinnelsesuttalelser er registrert i en ML-BOM-post.
 #6.1.5    Level: 3    Role: D/V
 Sørg for at høyrisikomodeller (offentlig opplastede vekter, uverifiserte skapere) forblir isolert inntil menneskelig gjennomgang og godkjenning.

---

### C6.2 Rammeverk- og biblioteks-skanning

Kontinuerlig skanne ML-rammeverk og biblioteker for CVE-er og ondsinnet kode for å holde kjøretidsstakken sikker.

 #6.2.1    Level: 1    Role: D/V
 Bekreft at CI-pipelines kjører avhengighetsskannere på AI-rammeverk og kritiske biblioteker.
 #6.2.2    Level: 1    Role: D/V
 Verifiser at kritiske sårbarheter (CVSS ≥ 7,0) blokkerer forfremmelse til produksjonsbilder.
 #6.2.3    Level: 2    Role: D
 Bekreft at statisk kodeanalyse kjøres på forkede eller innleide ML-biblioteker.
 #6.2.4    Level: 2    Role: V
 Bekreft at forslag til rammeverksoppgraderinger inkluderer en vurdering av sikkerhetspåvirkning med referanse til offentlige CVE-feed.
 #6.2.5    Level: 3    Role: V
 Verifiser at kjøretidssensorer varsler om uventede dynamiske bibliotekinnlastinger som avviker fra den signerte SBOM-en.

---

### C6.3 Avhengighetsfiksering og verifisering

Fest alle avhengigheter til uforanderlige digests og gjenskap bygg for å garantere identiske, manipulasjonssikre artefakter.

 #6.3.1    Level: 1    Role: D/V
 Bekreft at alle pakkebehandlere håndhever versjonsfesting via låsefil.
 #6.3.2    Level: 1    Role: D/V
 Bekreft at immutablesummer brukes i stedet for mutable tagger i containerreferanser.
 #6.3.3    Level: 2    Role: D
 Bekreft at kontroller for reproducerbare bygg sammenligner hasher på tvers av CI-kjøringer for å sikre identiske resultater.
 #6.3.4    Level: 2    Role: V
 Bekreft at byggeattester lagres i 18 måneder for revisjonssporbarhet.
 #6.3.5    Level: 3    Role: D
 Bekreft at utløpte avhengigheter utløser automatiserte PR-er for å oppdatere eller forgreine festede versjoner.

---

### C6.4 Håndheving av pålitelig kilde

Tillat bare nedlastinger av artefakter fra kryptografisk verifiserte, organisasjonsgodkjente kilder, og blokker alt annet.

 #6.4.1    Level: 1    Role: D/V
 Bekreft at modellvekter, datasett og containere kun lastes ned fra godkjente domener eller interne registre.
 #6.4.2    Level: 1    Role: D/V
 Bekreft at Sigstore/Cosign-signaturer validerer utgiveridentitet før artefakter lagres lokalt i hurtigbuffer.
 #6.4.3    Level: 2    Role: D
 Bekreft at utgående proxyer blokkerer uautentiserte nedlastinger av artefakter for å håndheve policy for pålitelig kilde.
 #6.4.4    Level: 2    Role: V
 Verifiser at tillatelseslister for depot gjennomgås kvartalsvis med dokumentasjon av forretningsbegrunnelse for hver oppføring.
 #6.4.5    Level: 3    Role: V
 Bekreft at brudd på retningslinjer utløser karantene av artefakter og tilbakestilling av avhengige pipeline-kjøringer.

---

### C6.5 Risikoanalyse for tredjepartsdatasett

Evaluer eksterne datasett for forgiftning, skjevhet og juridisk samsvar, og overvåk dem gjennom hele livssyklusen.

 #6.5.1    Level: 1    Role: D/V
 Verifiser at eksterne datasett gjennomgår vurdering av risiko for forgiftning (f.eks. datafingeravtrykk, avvikssøk).
 #6.5.2    Level: 1    Role: D
 Bekreft at skjevhetsmetrikker (demografisk paritet, lik mulighet) beregnes før godkjenning av datasettet.
 #6.5.3    Level: 2    Role: V
 Bekreft at opphavsrett og lisensbetingelser for datasett er dokumentert i ML-BOM-oppføringene.
 #6.5.4    Level: 2    Role: V
 Bekreft at periodisk overvåking oppdager drift eller korrupsjon i hostede datasett.
 #6.5.5    Level: 3    Role: D
 Verifiser at ulovlig innhold (opphavsrett, personlig identifiserbar informasjon) fjernes gjennom automatisert rensing før opplæring.

---

### C6.6 Overvåking av leverandørkjedeangrep

Oppdag trusler mot forsyningskjeden tidlig gjennom CVE-feeder, revisjonslogganalyse og rødt-lag simuleringer.

 #6.6.1    Level: 1    Role: V
 Bekreft at CI/CD-revisjonslogger strømmes til SIEM-deteksjoner for unormale pakke-nedlastinger eller manipulerte byggtrinn.
 #6.6.2    Level: 2    Role: D
 Bekreft at hendelsesrespons-spillebøker inkluderer tilbakestillingsprosedyrer for kompromitterte modeller eller biblioteker.
 #6.6.3    Level: 3    Role: V
 Verifiser at trusselintelligens-berikelsesmerker ML-spesifikke indikatorer (f.eks. modell-forgiftende IoC-er) i varseltriage.

---

### C6.7 ML‑BOM for Modellartefakter

Generer og signer detaljerte ML-spesifikke SBOM-er (ML-BOM-er) slik at nedstrømsbrukere kan verifisere komponentintegritet ved distribusjonstidspunktet.

 #6.7.1    Level: 1    Role: D/V
 Bekreft at hvert modellartifakt publiserer en ML-BOM som lister opp datasett, vekter, hyperparametere og lisenser.
 #6.7.2    Level: 1    Role: D/V
 Bekreft at ML-BOM-generering og Cosign-signering er automatisert i CI og kreves for sammenslåing.
 #6.7.3    Level: 2    Role: D
 Bekreft at ML-BOM-fullstendighetskontroller feiler byggeprosessen hvis noen komponentmetadata (hash, lisens) mangler.
 #6.7.4    Level: 2    Role: V
 Bekreft at nedstrømsbrukere kan spørre ML-BOM-er via API for å validere importerte modeller ved distribusjonstidspunktet.
 #6.7.5    Level: 3    Role: V
 Sjekk at ML-BOM-er er versjonsstyrt og diffet for å oppdage uautoriserte endringer.

---

### Referanser

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

## C7 Modellatferd, Utgangskontroll og Sikkerhetsgaranti

### Kontrollmål

Modellutganger må være strukturerte, pålitelige, sikre, forklarbare og kontinuerlig overvåket i produksjon. Dette reduserer hallusinasjoner, personvernsbrudd, skadelig innhold og ukontrollerte handlinger, samtidig som det øker brukerens tillit og overholdelse av regelverk.

---

### C7.1 Håndheving av utdataformat

Strenge skjemaer, begrenset dekoding og etterfølgende validering stopper feilaktig eller ondsinnet innhold før det sprer seg.

 #7.1.1    Level: 1    Role: D/V
 Bekreft at responsskjemaer (f.eks. JSON Schema) er angitt i systemprompten, og at hvert svar automatisk valideres; svar som ikke samsvarer, utløser reparasjon eller avvisning.
 #7.1.2    Level: 1    Role: D/V
 Bekreft at begrenset dekoding (stopp-tegn, regex, maks-tokener) er aktivert for å forhindre overløp eller sidekanaler for prompt-injeksjon.
 #7.1.3    Level: 2    Role: D/V
 Sørg for at nedstrømskomponenter behandler utdata som ikke-pålitelig og validerer dem mot skjemaer eller injeksjonssikre deserialisatorer.
 #7.1.4    Level: 3    Role: V
 Bekreft at feilaktige utdatahendelser blir loggført, begrenset etter hastighet, og gjort synlige for overvåking.

---

### C7.2 Hallusinasjonsdeteksjon og -redusering

Usikkerhetsestimering og tilbaketrekningsstrategier begrenser fabrikkerte svar.

 #7.2.1    Level: 1    Role: D/V
 Verifiser at token-nivå log-sannsynligheter, ensemble selv-konsistens, eller finjusterte hallusinasjonsdetektorer tilordner en konfidensscore til hvert svar.
 #7.2.2    Level: 1    Role: D/V
 Bekreft at svar under en konfigurerbar konfidensgrense utløser tilbakefall-arbeidsflyter (f.eks. hentingsforsterket generering, sekundær modell eller manuell gjennomgang).
 #7.2.3    Level: 2    Role: D/V
 Verifiser at hallusinasjonshendelser er merket med rotårsaksmetadata og føres inn i post-mortem- og finjusteringspipelines.
 #7.2.4    Level: 3    Role: D/V
 Sørg for at terskler og detektorer kalibreres på nytt etter større modell- eller kunnskapsbaseoppdateringer.
 #7.2.5    Level: 3    Role: V
 Verifiser at dashbordvisualiseringer sporer hallusinasjonsrater.

---

### C7.3 Utdata Sikkerhets- og Personvernfiltrering

Retningslinjefiltre og redteam-dekning beskytter brukere og konfidensielle data.

 #7.3.1    Level: 1    Role: D/V
 Verifiser at klassifisører før og etter generering blokkerer hat, trakassering, selvskading, ekstremistisk og seksuelt eksplisitt innhold i samsvar med retningslinjene.
 #7.3.2    Level: 1    Role: D/V
 Bekreft at detektering av PII/PCI og automatisk sensurering kjøres på hvert svar; brudd utløser en personvernhendelse.
 #7.3.3    Level: 2    Role: D
 Verifiser at konfidensialitetsetiketter (f.eks. forretningshemmeligheter) følger med på tvers av modaliteter for å forhindre lekkasje i tekst, bilder eller kode.
 #7.3.4    Level: 3    Role: D/V
 Bekreft at forsøk på å omgå filteret eller klassifiseringer med høy risiko krever sekundær godkjenning eller brukerre-autentisering.
 #7.3.5    Level: 3    Role: D/V
 Bekreft at filtreringsterskler gjenspeiler juridiske jurisdiksjoner og konteksten til brukerens alder/rolle.

---

### C7.4 Begrensning av utdata og handlinger

Grenseverdier for rate og godkjenningsporter forhindrer misbruk og overdreven autonomi.

 #7.4.1    Level: 1    Role: D
 Bekreft at kvoter per bruker og per API-nøkkel begrenser forespørsler, tokens og kostnader med eksponentiell tilbake-off ved 429-feil.
 #7.4.2    Level: 1    Role: D/V
 Bekreft at privilegerte handlinger (filskriving, kodekjøring, nettverksanrop) krever policy-basert godkjenning eller menneskelig involvering.
 #7.4.3    Level: 2    Role: D/V
 Bekreft at kryssmodal konsistenssjekker sikrer at bilder, kode og tekst generert for samme forespørsel ikke kan brukes til å smugle skadelig innhold.
 #7.4.4    Level: 2    Role: D
 Bekreft at dybden for agentdelegasjon, rekursjonsgrenser og tillatte verktøylister er eksplisitt konfigurert.
 #7.4.5    Level: 3    Role: V
 Bekreft at overskridelse av grenser utløser strukturerte sikkerhetshendelser for SIEM-inntak.

---

### C7.5 Forklarbarhet av utdata

Transparente signaler forbedrer brukerens tillit og intern feilsøking.

 #7.5.1    Level: 2    Role: D/V
 Bekreft at brukervendte tillitsresultater eller korte resonnementssammendrag vises når risikovurderingen anser det som passende.
 #7.5.2    Level: 2    Role: D/V
 Bekreft at genererte forklaringer unngår å avsløre sensitive systemkommandoer eller proprietære data.
 #7.5.3    Level: 3    Role: D
 Bekreft at systemet fanger opp token-nivå log-sannsynligheter eller oppmerksomhetskart og lagrer dem for autorisert inspeksjon.
 #7.5.4    Level: 3    Role: V
 Verifiser at forklaringsartefakter er versjonskontrollert sammen med modellutgivelser for revisjonssporbarhet.

---

### C7.6 Overvåkingsintegrasjon

Sanntidsovervåking lukker sløyfen mellom utvikling og produksjon.

 #7.6.1    Level: 1    Role: D
 Bekreft at måleparametere (skjemaavvik, hallusinasjonsrate, toksisitet, lekkasjer av personlig identifiserbar informasjon, latenstid, kostnader) strømmer til en sentral overvåkingsplattform.
 #7.6.2    Level: 1    Role: V
 Bekreft at varslingsterskler er definert for hver sikkerhetsmåling, med eskaleringsveier for vaktpersonell.
 #7.6.3    Level: 2    Role: V
 Verifiser at dashbord korrelerer utdataavvik med modell/versjon, funksjonsflagg og endringer i oppstrømsdata.
 #7.6.4    Level: 2    Role: D/V
 Verifiser at overvåkningsdata føres tilbake til omtrening, finjustering eller oppdatering av regler innenfor en dokumentert MLOps-arbeidsflyt.
 #7.6.5    Level: 3    Role: V
 Sørg for at overvåkingspipelines er penetrasjonstestet og tilgangskontrollert for å unngå lekkasje av sensitive logger.

---

### 7.7 Generative mediesikkerhetstiltak

Sikre at AI-systemer ikke genererer ulovlig, skadelig eller uautorisert medieinnhold ved å håndheve policybegrensninger, outputvalidering og sporbarhet.

 #7.7.1    Level: 1    Role: D/V
 Bekreft at systeminstruksjoner og brukerinstruksjoner uttrykkelig forbyr generering av ulovlig, skadelig eller ikke-samtykkende deepfake-media (for eksempel bilde, video, lyd).
 #7.7.2    Level: 2    Role: D/V
 Bekreft at forespørsler blir filtrert for forsøk på å generere etterligninger, seksuelt eksplisitte deepfakes eller medier som viser ekte personer uten samtykke.
 #7.7.3    Level: 2    Role: V
 Bekreft at systemet bruker perseptuell hashing, vannmerkingsdeteksjon eller fingeravtrykkteknologi for å forhindre uautorisert reproduksjon av opphavsrettslig beskyttet materiale.
 #7.7.4    Level: 3    Role: D/V
 Bekreft at alt generert materiale er kryptografisk signert, merket med vannmerke eller inneholder innbakt manipulasjonssikker opphavsmetadata for sporbart oppfølging.
 #7.7.5    Level: 3    Role: V
 Verifiser at omgåelsesforsøk (f.eks. promptforvrengning, slang, antagonistisk formulering) oppdages, logges og hastighetsbegrenses; gjentatt misbruk rapporteres til overvåkingssystemer.

### Referanser

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

## C8-minne, innebygde representasjoner og sikkerhet for vektordatabaser

### Kontrollmål

Innebygginger og vektorlager fungerer som "levende minne" for moderne AI-systemer, ved kontinuerlig å ta imot data fra brukeren og hente dem tilbake inn i modellkontekster via Retrieval-Augmented Generation (RAG). Hvis dette minnet ikke styres, kan det lekke personlig identifiserbar informasjon (PII), bryte samtykke, eller bli reversert for å rekonstruere originalteksten. Målet med denne kontrollfamilien er å styrke minne-pipeliner og vektordatabaser slik at tilgangen er basert på minste privilegium, innebyggerne ivaretar personvern, lagrede vektorer utløper eller kan tilbakekalles ved behov, og at per-bruker-minne aldri forurenser andre brukeres forespørsler eller resultater.

---

### C8.1 Tilgangskontroller på minne og RAG-indekser

Håndhev detaljerte tilgangskontroller på hver vektorsamling.

 #8.1.1    Level: 1    Role: D/V
 Verifiser at tilgangskontrollregler på rad-/navneromnivå begrenser innsettings-, slettings- og spørringsoperasjoner per leietaker, samling eller dokumentmerke.
 #8.1.2    Level: 1    Role: D/V
 Bekreft at API-nøkler eller JWT-er inneholder avgrensede påstander (f.eks. samlings-IDer, handlingsverb) og roteres minst kvartalsvis.
 #8.1.3    Level: 2    Role: D/V
 Sørg for at forsøk på privilegieeskalering (f.eks. likhetssøk på tvers av namespaces) blir oppdaget og loggført til en SIEM innen 5 minutter.
 #8.1.4    Level: 2    Role: D/V
 Bekreft at vektordatabasen logger revisjoner for emneidentifikator, operasjon, vektor-ID/område, likhetsterskel og resultatantall.
 #8.1.5    Level: 3    Role: V
 Verifiser at tilgangsbeslutninger blir testet for omgåelsesfeil hver gang motorene oppgraderes eller indeks-shardingsregler endres.

---

### C8.2 Innebygging Rens og Validering

Forhåndssjekk teksten for personidentifiserbar informasjon (PII), sensurer eller pseudonymiser før vektorisering, og eventuelt etterbehandle innebyggingene for å fjerne gjenværende signaler.

 #8.2.1    Level: 1    Role: D/V
 Verifiser at PII og regulert data blir oppdaget via automatiserte klassifikatorer og maskert, tokenisert eller fjernet før embedding.
 #8.2.2    Level: 1    Role: D
 Sørg for at innbeddingspipeliner avviser eller karantenerer inndata som inneholder kjørbar kode eller ikke-UTF-8-artifakter som kan forgifte indeksen.
 #8.2.3    Level: 2    Role: D/V
 Bekreft at lokal eller metrisk differensialt personvern-sanitering anvendes på setningsinnbeddinger hvis avstand til noe kjent PII-token er under en konfigurerbar terskel.
 #8.2.4    Level: 2    Role: V
 Verifiser at effektiviteten av sanitering (f.eks. tilbakekalling av PII-redigering, semantisk drift) valideres minst hvert halvår mot referansekorpora.
 #8.2.5    Level: 3    Role: D/V
 Bekreft at sanitiseringskonfigurasjoner er versjonskontrollert og at endringer gjennomgår kollegavurdering.

---

### C8.3 Minnetid, Tilbakekalling og Sletting

GDPRs "rett til å bli glemt" og lignende lover krever rettidig sletting; vektorbutikker må derfor støtte TTLer, hard sletting og gravmerking slik at tilbakekalte vektorer ikke kan gjenopprettes eller reindekseres.

 #8.3.1    Level: 1    Role: D/V
 Verifiser at hver vektor- og metadataoppføring har en TTL eller en eksplisitt oppbevaringsetikett som respekteres av automatiserte ryddejobber.
 #8.3.2    Level: 1    Role: D/V
 Bekreft at brukerinitierte slettingsforespørsler fjerner vektorer, metadata, hurtigbufferkopier og avledede indekser innen 30 dager.
 #8.3.3    Level: 2    Role: D
 Bekreft at logiske slettinger følges opp med kryptografisk sletting av lagringsblokker dersom maskinvaren støtter det, eller ved destruksjon av nøkkelen i nøkkellageret.
 #8.3.4    Level: 3    Role: D/V
 Bekreft at utløpte vektorer er ekskludert fra nærmeste-nabo-søkresultater innen mindre enn 500 ms etter utløp.

---

### C8.4 Forebygging av embedding-inversjon og lekkasje

Nylige forsvarsmekanismer—støy-supersisjon, projeksjonsnettverk, privatlivs-nevronforstyrrelse og applikasjonslagskryptering—kan redusere token-nivå inversjonsrater til under 5 %.

 #8.4.1    Level: 1    Role: V
 Bekreft at en formell trusselmodell som dekker inversjons-, medlemskaps- og attributtinferensangrep finnes og gjennomgås årlig.
 #8.4.2    Level: 2    Role: D/V
 Verifiser at applikasjonslagskryptering eller søkbar kryptering beskytter vektorer mot direkte lesing av infrastrukturadministratorer eller skylpersonell.
 #8.4.3    Level: 3    Role: V
 Bekreft at forsvarsparametrene (ε for DP, støysigma σ, projeksjonsrang k) balanserer personvern ≥ 99 % tokenbeskyttelse og nytteverdi ≤ 3 % nøyaktighetstap.
 #8.4.4    Level: 3    Role: D/V
 Bekreft at inverteringsmotstandsmetrikker er en del av frigisingsporter for modelloppdateringer, med definerte regresjonsbudsjetter.

---

### C8.5 Omfangshåndheving for brukerspesifikk minne

Kryss-lekkasje mellom leietakere forblir en ledende RAG-risiko: feilaktig filtrerte likhetsspørringer kan avsløre en annen kundes private dokumenter.

 #8.5.1    Level: 1    Role: D/V
 Bekreft at hver hentingsspørring blir post-filtrert etter leietaker-/bruker-ID før den sendes til LLM-prompten.
 #8.5.2    Level: 1    Role: D
 Bekreft at samlingsnavn eller navngitte ID-er med navneområde er saltet per bruker eller leietaker slik at vektorer ikke kan kollidere på tvers av områder.
 #8.5.3    Level: 2    Role: D/V
 Bekreft at likhetsresultater over en konfigurerbar avstandsterskel, men utenfor anroperens område, blir forkastet og utløser sikkerhetsalarmer.
 #8.5.4    Level: 2    Role: V
 Bekreft at flerbruker-stresstester simulerer motstridende forespørsler som prøver å hente dokumenter utenfor omfang, og demonstrerer null lekkasje.
 #8.5.5    Level: 3    Role: D/V
 Bekreft at krypteringsnøkler er adskilt per leietaker, og sikrer kryptografisk isolasjon selv om fysisk lagring deles.

---

### C8.6 Avansert sikkerhet for minnesystemer

Sikkerhetskontroller for sofistikerte minnearkitekturer inkludert episodisk, semantisk og arbeidsminne med spesifikke krav til isolasjon og validering.

 #8.6.1    Level: 1    Role: D/V
 Verifiser at ulike minnetyper (episodisk, semantisk, arbeidende) har isolerte sikkerhetskontekster med rollebaserte tilgangskontroller, separate krypteringsnøkler og dokumenterte tilgangsmønstre for hver minnetype.
 #8.6.2    Level: 2    Role: D/V
 Bekreft at minnekonsolideringsprosesser inkluderer sikkerhetsvalidering for å forhindre injeksjon av skadelige minner gjennom innholdsrensing, kildeverifisering og integritetskontroller før lagring.
 #8.6.3    Level: 2    Role: D/V
 Bekreft at spørringer for minnehenting blir validert og renset for å forhindre uttak av uautorisert informasjon gjennom analyse av spørringsmønstre, håndheving av tilgangskontroll og filtrering av resultater.
 #8.6.4    Level: 3    Role: D/V
 Bekreft at hukommelsesglemmingsmekanismer sikkert sletter sensitiv informasjon med kryptografiske slettingsgarantier ved hjelp av nøkkelsletting, flerpassert overskriving eller maskinvarebasert sikker sletting med verifiseringssertifikater.
 #8.6.5    Level: 3    Role: D/V
 Bekreft at minnesystemets integritet kontinuerlig overvåkes for uautoriserte endringer eller korrupsjon gjennom kontrollsummer, revisjonslogger og automatiserte varsler når minneinnhold endres utenfor normale operasjoner.

---

### Referanser

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

## 9 Autonom orkestrering og agentisk handlingssikkerhet

### Kontrollmål

Sørg for at autonome eller multi-agent AI-systemer kun kan utføre handlinger som er eksplisitt tiltenkt, autentisert, reviderbare og innenfor avgrensede kostnads- og risikogrenseverdier. Dette beskytter mot trusler som kompromittering av autonome systemer, feilbruk av verktøy, agentløkkeoppdagelse, kommunikasjonshijacking, identitetsspoofing, flokkmanipulasjon og intensjonsmanipulasjon.

---

### 9.1 Agentens oppgaveplanlegging og resirkuleringsbudsjetter

Begrens rekursive planer og påtving menneskelige sjekkpunkter for privilegerte handlinger.

 #9.1.1    Level: 1    Role: D/V
 Bekreft at maksimal rekursjonsdybde, bredde, veggklokketid, antall tokens og monetær kostnad per agentkjøring er sentralt konfigurert og versjonskontrollert.
 #9.1.2    Level: 1    Role: D/V
 Bekreft at privilegerte eller irreversible handlinger (f.eks. kodeinnsendinger, finansielle overføringer) krever eksplisitt menneskelig godkjenning via en reviderbar kanal før utførelse.
 #9.1.3    Level: 2    Role: D
 Bekreft at sanntids ressursovervåkere utløser avbrudd i kretsbryteren når noen budsjettterskel overskrides, og stopper ytterligere oppgaveutvidelse.
 #9.1.4    Level: 2    Role: D/V
 Bekreft at circuit-breaker-hendelser logges med agent-ID, utløsende betingelse og fanget planstatus for rettsmedisinsk gjennomgang.
 #9.1.5    Level: 3    Role: V
 Bekreft at sikkerhetstester dekker scenarier med budsjettutarming og løpsk plan, og bekreft trygg avslutning uten datatap.
 #9.1.6    Level: 3    Role: D
 Bekreft at budsjettpolitikker er uttrykt som policy-som-kode og håndheves i CI/CD for å blokkere konfigurasjonsdrift.

---

### 9.2 Verktøy-plugin Sandboxing

Isoler verktøyinteraksjoner for å forhindre uautorisert systemtilgang eller kodeutførelse.

 #9.2.1    Level: 1    Role: D/V
 Sørg for at hvert verktøy/plugin kjører innenfor et OS-, container- eller WASM-nivå sandbox med minste privilegium for filsystem-, nettverks- og systemkallpolicyer.
 #9.2.2    Level: 1    Role: D/V
 Verifiser at kvoter for sandkasseressurser (CPU, minne, disk, nettverksutgang) og kjøretidsavbrudd håndheves og loggføres.
 #9.2.3    Level: 2    Role: D/V
 Verifiser at verktøybinarier eller beskrivelser er digitalt signert; signaturer valideres før lasting.
 #9.2.4    Level: 2    Role: V
 Bekreft at sandkassens telemetri strømmer til en SIEM; avvik (f.eks. forsøk på utgående tilkoblinger) utløser varsler.
 #9.2.5    Level: 3    Role: V
 Verifiser at høyrisiko-plugins gjennomgår sikkerhetsgjennomgang og penetrasjonstesting før produksjonsdistribusjon.
 #9.2.6    Level: 3    Role: D/V
 Bekreft at forsøk på å bryte ut av sandkassen automatisk blokkeres og at den feilaktige pluginen settes i karantene i påvente av undersøkelse.

---

### 9.3 Autonom løkke og kostnadsavgrensning

Oppdag og stopp ukontrollert agent-til-agent rekursjon og kostnadseksplosjoner.

 #9.3.1    Level: 1    Role: D/V
 Bekreft at samtaler mellom agenter inkluderer en hopp-grense eller TTL som kjøretiden reduserer og håndhever.
 #9.3.2    Level: 2    Role: D
 Verifiser at agenter opprettholder en unik invokasjonsgraf-ID for å oppdage selvinvokasjon eller sykliske mønstre.
 #9.3.3    Level: 2    Role: D/V
 Bekreft at kumulative beregningsenhets- og forbrukstellere spores per forespørselkjede; overskridelse av grensen avbryter kjeden.
 #9.3.4    Level: 3    Role: V
 Verifiser at formell analyse eller modellkontroll påviser fravær av ubegrenset rekursjon i agentprotokoller.
 #9.3.5    Level: 3    Role: D
 Verifiser at loop-avbruddsbegivenheter genererer varsler og leverer kontinuerlige forbedringsmetrikker.

---

### 9.4 Protokollnivå Misbruksbeskyttelse

Sikre kommunikasjonskanaler mellom agenter og eksterne systemer for å forhindre kapring eller manipulering.

 #9.4.1    Level: 1    Role: D/V
 Bekreft at alle meldinger mellom agent og verktøy og mellom agenter er autentisert (f.eks. gjensidig TLS eller JWT) og ende-til-ende kryptert.
 #9.4.2    Level: 1    Role: D
 Sørg for at skjemaer blir strengt validert; ukjente felt eller feilformaterte meldinger blir avvist.
 #9.4.3    Level: 2    Role: D/V
 Verifiser at integritetskontroller (MAC-er eller digitale signaturer) dekker hele meldingsinnholdet, inkludert verktøyparametere.
 #9.4.4    Level: 2    Role: D
 Sjekk at gjenspillingsbeskyttelse (nonser eller tidsstempelvinduer) håndheves på protokollaget.
 #9.4.5    Level: 3    Role: V
 Bekreft at protokollimplementeringer gjennomgår fuzzing og statisk analyse for injeksjons- eller deserialiseringsfeil.

---

### 9.5 Agentidentitet og manipulasjonssikkerhet

Sørg for at handlinger kan tilskrives og at endringer er oppdagbare.

 #9.5.1    Level: 1    Role: D/V
 Bekreft at hver agentinstans har en unik kryptografisk identitet (nøkkelpar eller maskinvarebasert rotlegitimasjon).
 #9.5.2    Level: 2    Role: D/V
 Bekreft at alle agenthandlinger er signert og tidsstemplet; logger inkluderer signaturen for ikke-avvisning.
 #9.5.3    Level: 2    Role: V
 Bekreft at manipuleringsevidente logger lagres i et kun-tillegg eller skrivebeskyttet medium.
 #9.5.4    Level: 3    Role: D
 Verifiser at identitetsnøkler roteres etter en definert tidsplan og ved indikasjoner på kompromittering.
 #9.5.5    Level: 3    Role: D/V
 Bekreft at forsøk på forfalskning eller nøkkelkonflikt utløser umiddelbar karantene av den berørte agenten.

---

### 9.6 Fleragent-sverm risikoreduksjon

Reduser fare for kollektiv atferd gjennom isolasjon og formell sikkerhetsmodellering.

 #9.6.1    Level: 1    Role: D/V
 Bekreft at agenter som opererer i forskjellige sikkerhetsdomener kjører i isolerte kjøretids-sandbokser eller nettverkssegmenter.
 #9.6.2    Level: 3    Role: V
 Sørg for at sværmatferder modelleres og formelt verifiseres for livlighet og sikkerhet før distribusjon.
 #9.6.3    Level: 3    Role: D
 Verifiser at kjøretidsovervåkere oppdager fremvoksende usikre mønstre (f.eks. oscillasjoner, stillstand) og iverksetter korrigerende tiltak.

---

### 9.7 Bruker- og verktøyautentisering / autorisasjon

Implementer robuste tilgangskontroller for hver handling utløst av agent.

 #9.7.1    Level: 1    Role: D/V
 Verifiser at agenter autentiserer som førsteklasses prinsipper til nedstrøms systemer, og aldri gjenbruker sluttbrukerens legitimasjon.
 #9.7.2    Level: 2    Role: D
 Verifiser at detaljerte autorisasjonspolicyer begrenser hvilke verktøy en agent kan bruke og hvilke parametere den kan oppgi.
 #9.7.3    Level: 2    Role: V
 Verifiser at privilegjekontroller blir evaluert på nytt ved hvert kall (kontinuerlig autorisasjon), ikke bare ved sesjonsstart.
 #9.7.4    Level: 3    Role: D
 Bekreft at delegerte privilegier utløper automatisk og krever ny samtykke etter tidsavbrudd eller endring i omfang.

---

### 9.8 Sikkerhet for kommunikasjon mellom agenter

Krypter og sikr integriteten til alle meldinger mellom agenter for å hindre avlytting og manipulering.

 #9.8.1    Level: 1    Role: D/V
 Bekreft at gjensidig autentisering og kryptering med perfekt fremoverhemmelighold (for eksempel TLS 1.3) er obligatorisk for agentkanaler.
 #9.8.2    Level: 1    Role: D
 Sørg for at meldingsintegritet og opprinnelse blir verifisert før behandling; ved feil utløses varsler og meldingen avvises.
 #9.8.3    Level: 2    Role: D/V
 Bekreft at kommunikasjonens metadata (tidsstempler, sekvensnumre) logges for å støtte rettsmedisinsk rekonstruksjon.
 #9.8.4    Level: 3    Role: V
 Verifiser at formell verifisering eller modellkontroll bekrefter at protokolltilstandsmaskiner ikke kan settes i usikre tilstander.

---

### 9.9 Intensjonsverifisering og håndheving av begrensninger

Bekreft at agentens handlinger samsvarer med brukerens angitte intensjon og systemets begrensninger.

 #9.9.1    Level: 1    Role: D
 Verifiser at forhåndsutførelsesbegrensningsløserne sjekker foreslåtte handlinger mot hardkodede sikkerhets- og policyregler.
 #9.9.2    Level: 2    Role: D/V
 Bekreft at handlinger med høy påvirkning (økonomiske, destruktive, personvernsensitive) krever eksplisitt intensjonsbekreftelse fra den initierende brukeren.
 #9.9.3    Level: 2    Role: V
 Bekreft at etterbetingelseskontroller validerer at fullførte handlinger oppnådde tiltenkte effekter uten bivirkninger; avvik utløser tilbakestilling.
 #9.9.4    Level: 3    Role: V
 Verifiser at formelle metoder (f.eks. modelkontroll, teorembevis) eller egenskapsbaserte tester viser at agentplaner oppfyller alle deklarerte begrensninger.
 #9.9.5    Level: 3    Role: D
 Bekreft at hendelser med intensjonsavvik eller brudd på begrensninger bidrar til kontinuerlige forbedringssykluser og deling av trusselinformasjon.

---

### 9.10 Agentresonnement Strategi Sikkerhet

Sikker valg og utførelse av forskjellige resonnementstrategier, inkludert ReAct, Chain-of-Thought og Tree-of-Thoughts tilnærminger.

 #9.10.1    Level: 1    Role: D/V
 Bekreft at valg av resonnementstrategi bruker deterministiske kriterier (inngangskompleksitet, oppgavetyp, sikkerhetskontekst) og at identiske innganger gir identiske strategivalg innen samme sikkerhetskontekst.
 #9.10.2    Level: 1    Role: D/V
 Bekreft at hver resonneringsstrategi (ReAct, Chain-of-Thought, Tree-of-Thoughts) har dedikert inndata-validering, utdata-rensing og tidsbegrensninger for utførelse som er spesifikke for dens kognitive tilnærming.
 #9.10.3    Level: 2    Role: D/V
 Kontroller at overganger i resonnementstrategi blir loggført med fullstendig kontekst, inkludert inndatakjennetegn, verdier for utvalgskriterier, og utførelsesmetadata for rekonstruksjon av revisjonsspor.
 #9.10.4    Level: 2    Role: D/V
 Bekreft at Tree-of-Thoughts-rasjonering inkluderer mekanismer for beskjæring av grener som avslutter utforskning når policybrudd, ressursgrenser eller sikkerhetsgrenser oppdages.
 #9.10.5    Level: 2    Role: D/V
 Bekreft at ReAct (Resonner-Virk-Observer) sykluser inkluderer valideringskontrollpunkter i hver fase: verifisering av resonnementstrinn, godkjenning av handling og sanitering av observasjon før videreføring.
 #9.10.6    Level: 3    Role: D/V
 Bekreft at ytelsesmålinger for resonnementstrategien (utførelsestid, ressursbruk, resultatkvalitet) overvåkes med automatiserte varsler når målingene avviker fra de konfigurerte tersklene.
 #9.10.7    Level: 3    Role: D/V
 Bekreft at hybride resonneringsmetoder som kombinerer flere strategier opprettholder inngangsvalidering og utgangsbegrensninger for alle de enkelte strategiene uten å omgå noen sikkerhetskontroller.
 #9.10.8    Level: 3    Role: D/V
 Bekreft at sikkerhetstesting av resonneringsstrategier inkluderer fuzzing med feilaktige input, adversarielle prompt designet for å tvinge strategiskifte, og testing av grensetilstander for hver kognitiv tilnærming.

---

### 9.11 Agentens livssyklus tilstandsstyring og sikkerhet

Sikker agentinitialisering, tilstandsoverganger og terminering med kryptografiske revisjonsspor og definerte gjenopprettingsprosedyrer.

 #9.11.1    Level: 1    Role: D/V
 Sørg for at agentinitialisering inkluderer etablering av kryptografisk identitet med maskinvarebaserte legitimasjoner og uforanderlige oppstartsrevisjonslogger som inneholder agent-ID, tidsstempel, konfigurasjonshash og initialiseringsparametere.
 #9.11.2    Level: 2    Role: D/V
 Verifiser at agentens tilstandsoverganger er kryptografisk signert, tidsstemplet og loggført med komplett kontekst, inkludert utløsende hendelser, forrige tilstandens hash, ny tilstandens hash og utførte sikkerhetsvalideringer.
 #9.11.3    Level: 2    Role: D/V
 Bekreft at agentens avslutningsprosedyrer inkluderer sikker minnesletting ved bruk av kryptografisk sletting eller flere overskrivingsrunder, tilbakekalling av autentiseringsopplysninger med varsling til sertifikatautoritet, og generering av manipulasjonssikre avslutningssertifikater.
 #9.11.4    Level: 3    Role: D/V
 Bekreft at agentgjenopprettingsmekanismer validerer tilstandsintegritet ved bruk av kryptografiske sjekksummer (minimum SHA-256) og ruller tilbake til kjente gode tilstander når korrupsjon oppdages, med automatiserte varsler og krav om manuell godkjenning.
 #9.11.5    Level: 3    Role: D/V
 Bekreft at agentens persistensmekanismer krypterer sensitiv tilstandsdata med per-agent AES-256-nøkler og implementerer sikker nøkkelrotasjon på konfigurerbare tidsplaner (maksimum 90 dager) med utrulling uten nedetid.

---

### 9.12 Verktøyintegrasjonssikkerhetsrammeverk

Sikkerhetskontroller for dynamisk verktøylasting, kjøring og resultatvalidering med definerte risikovurderings- og godkjenningsprosesser.

 #9.12.1    Level: 1    Role: D/V
 Bekreft at verktøybeskrivelser inkluderer sikkerhetsmetadata som angir nødvendige privilegier (lese/skrive/utføre), risikonivåer (lav/middels/høy), ressursgrenser (CPU, minne, nettverk) og valideringskrav dokumentert i verktøymanifestene.
 #9.12.2    Level: 1    Role: D/V
 Verifiser at verktøyets kjøringsresultater valideres mot forventede skjemaer (JSON-skjema, XML-skjema) og sikkerhetspolicyer (utgangssanitering, dataklassifisering) før integrering med tidsavbruddsgrenser og feilhåndteringsprosedyrer.
 #9.12.3    Level: 2    Role: D/V
 Bekreft at verktøyinteraksjonslogger inkluderer detaljert sikkerhetskontekst, inkludert bruk av privilegier, datatilgangsmønstre, utførelsestid, ressursforbruk og returkoder med strukturert logging for SIEM-integrasjon.
 #9.12.4    Level: 2    Role: D/V
 Bekreft at mekanismer for dynamisk verktøyinnlasting validerer digitale signaturer ved bruk av PKI-infrastruktur og implementerer sikre innlastingsprotokoller med sandkasseisolasjon og tillatelsesverifisering før kjøring.
 #9.12.5    Level: 3    Role: D/V
 Bekreft at verktøysikkerhetsvurderinger automatisk utløses for nye versjoner med obligatoriske godkjenningsporter, inkludert statisk analyse, dynamisk testing og sikkerhetsteamets gjennomgang, med dokumenterte godkjenningskriterier og SLA-krav.

---

#### Referanser

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

## 10 Motstandsdyktighet mot angrep og personvernsforsvar

### Kontrollmål

Sørg for at AI-modeller forblir pålitelige, personvernbevarende og motstandsdyktige mot misbruk når de utsettes for unnvikelses-, inferens-, utvinnings- eller forgiftningsangrep.

---

### 10.1 Modelljustering og sikkerhet

Beskytte mot skadelige eller policy-bruddende utdata.

 #10.1.1    Level: 1    Role: D/V
 Bekreft at en testpakke for justering (red-team-prompt, jailbreak-prober, uakseptert innhold) er versjonskontrollert og kjøres ved hver modellutgivelse.
 #10.1.2    Level: 1    Role: D
 Bekreft at nektelse og sikre fullføringsvern er håndhevet.
 #10.1.3    Level: 2    Role: D/V
 Bekreft at en automatisert evaluator måler andelen skadelig innhold og varsler om tilbakegang utover en satt terskel.
 #10.1.4    Level: 2    Role: D
 Verifiser at mot-omgåelsesopplæring er dokumentert og reproduserbar.
 #10.1.5    Level: 3    Role: V
 Verifiser at formelle bevis for etterlevelse av policy eller sertifisert overvåking dekker kritiske domener.

---

### 10.2 Motstandsdyktighet mot fiendtlige eksempler

Øk motstanden mot manipulerte inndata. Robust adversarial-trening og benchmark-poenggivning er dagens beste praksis.

 #10.2.1    Level: 1    Role: D
 Bekreft at prosjektlagre inkluderer konfigurasjoner for adversarial trening med reproduserbare frø.
 #10.2.2    Level: 2    Role: D/V
 Bekreft at oppdagelse av motstandereksempler utløser blokkeringvarsler i produksjonsrørledninger.
 #10.2.4    Level: 3    Role: V
 Verifiser at sertifiserte robusthetsbevis eller intervallgrense-sertifikater dekker minst de mest kritiske klassene.
 #10.2.5    Level: 3    Role: V
 Bekreft at regresjonstester bruker adaptive angrep for å bekrefte at det ikke er noe målbar robusthetstap.

---

### 10.3 Tiltak for å motvirke medlemskapsinformasjonsangrep

Begrens muligheten til å avgjøre om en post var i treningsdataene. Differensiell personvern og maskering av konfidensscore forblir de mest effektive kjente forsvar.

 #10.3.1    Level: 1    Role: D
 Bekreft at entropiregulering per spørring eller temperaturskalering reduserer overkonfident prediksjoner.
 #10.3.2    Level: 2    Role: D
 Bekreft at treningen bruker ε-avgrenset differensielt privat optimalisering for sensitive datasett.
 #10.3.3    Level: 2    Role: V
 Bekreft at angrepssimuleringer (skygge-modell eller svart-boks) viser angreps-AUC ≤ 0,60 på holdt-ut data.

---

### 10.4 Motstand mot modellinversjon

Forhindre rekonstruksjon av private attributter. Nyere undersøkelser fremhever avkorting av utdata og DP-garantier som praktiske forsvar.

 #10.4.1    Level: 1    Role: D
 Bekreft at sensitive attributter aldri blir direkte vist; der det er nødvendig, bruk grupper eller enveistransformasjoner.
 #10.4.2    Level: 1    Role: D/V
 Bekreft at forespørselsrategens begrensninger demper gjentatte adaptive forespørsler fra samme hovedbruker.
 #10.4.3    Level: 2    Role: D
 Bekreft at modellen er trent med personvernbeskyttende støy.

---

### 10.5 Modellutvinningsforsvar

Oppdag og avskrekk uautorisert kloning. Vannmerking og analyse av forespørselmønstre anbefales.

 #10.5.1    Level: 1    Role: D
 Bekreft at inferens-gatewayer håndhever globale og per-API-nøkkel hastighetsbegrensninger tilpasset modellens memoriseringsgrense.
 #10.5.2    Level: 2    Role: D/V
 Verifiser at statistikkene for spørrings-entropi og input-mangfoldighet forsyner en automatisert utvinningsdetektor.
 #10.5.3    Level: 2    Role: V
 Verifiser at skjøre eller sannsynlighetsbaserte vannmerker kan bevises med p < 0,01 i ≤ 1 000 forespørsler mot en mistenkt klone.
 #10.5.4    Level: 3    Role: D
 Bekreft at vannmerke-nøkler og trigger-sett lagres i en hardware-sikkerhetsmodul og roteres årlig.
 #10.5.5    Level: 3    Role: V
 Bekreft at extraction-alert-hendelser inkluderer krenkende forespørsler og er integrert med hendelseshåndteringsprosedyrer.

---

### 10.6 Deteksjon av forgiftede data ved inferenstidspunktet

Identifisere og nøytralisere bakdør- eller forgiftede innganger.

 #10.6.1    Level: 1    Role: D
 Verifiser at inndata går gjennom en anomali-detektor (f.eks. STRIP, konsistens-scoring) før modellinferens.
 #10.6.2    Level: 1    Role: V
 Bekreft at detektorterskler er justert på rene/forurensede valideringssett for å oppnå mindre enn 5 % falske positiver.
 #10.6.3    Level: 2    Role: D
 Bekreft at innganger merket som forgiftet utløser myk-blokkering og arbeidsflyter for menneskelig gjennomgang.
 #10.6.4    Level: 2    Role: V
 Bekreft at detektorer er stresstestet med adaptive, utløserløse bakdør-angrep.
 #10.6.5    Level: 3    Role: D
 Bekreft at deteksjonseffektivitetsmålinger loggføres og periodisk revurderes med oppdatert trusselinformasjon.

---

### 10.7 Dynamisk tilpasning av sikkerhetspolicy

Sanntidsoppdateringer av sikkerhetspolicy basert på trusselintelligens og atferdsanalyse.

 #10.7.1    Level: 1    Role: D/V
 Bekreft at sikkerhetspolicyer kan oppdateres dynamisk uten at agenten må startes på nytt, samtidig som man opprettholder integriteten til policyversjonen.
 #10.7.2    Level: 2    Role: D/V
 Bekreft at policyoppdateringer er kryptografisk signert av autorisert sikkerhetspersonell og validert før de implementeres.
 #10.7.3    Level: 2    Role: D/V
 Bekreft at dynamiske policyendringer logges med fullstendige revisjonsspor, inkludert begrunnelse, godkjenningskjeder og tilbakeføringsprosedyrer.
 #10.7.4    Level: 3    Role: D/V
 Bekreft at adaptive sikkerhetsmekanismer justerer trusseldeteksjonsfølsomhet basert på risikokontekst og atferdsmønstre.
 #10.7.5    Level: 3    Role: D/V
 Sørg for at beslutninger om tilpasning av policyer er forklarbare og inkluderer bevismateriale for gjennomgang av sikkerhetsteamet.

---

### 10.8 Refleksjonsbasert sikkerhetsanalyse

Sikkerhetsvalidering gjennom agentens selvrefleksjon og metakognitiv analyse.

 #10.8.1    Level: 1    Role: D/V
 Bekreft at agentens refleksjonsmekanismer inkluderer sikkerhetsfokusert selvvurdering av beslutninger og handlinger.
 #10.8.2    Level: 2    Role: D/V
 Sørg for at refleksjonsutdata er validert for å forhindre manipulering av selvvurderingsmekanismer av fiendtlige innganger.
 #10.8.3    Level: 2    Role: D/V
 Verifiser at meta-kognitiv sikkerhetsanalyse identifiserer potensielle skjevheter, manipulering eller kompromittering i agentenes resonnementprosesser.
 #10.8.4    Level: 3    Role: D/V
 Bekreft at sikkerhetsadvarsler basert på refleksjon utløser forbedret overvåking og potensielle arbeidsflyter for menneskelig inngripen.
 #10.8.5    Level: 3    Role: D/V
 Bekreft at kontinuerlig læring fra sikkerhetsrefleksjoner forbedrer trusseloppdagelse uten å svekke legitim funksjonalitet.

---

### 10.9 Evolusjon og Selvforbedringssikkerhet

Sikkerhetskontroller for agentsystemer som er i stand til selvmodifikasjon og evolusjon.

 #10.9.1    Level: 1    Role: D/V
 Bekreft at selvmodifikasjonskapasiteter er begrenset til utpekte sikre områder med formelle verifikasjonsgrenser.
 #10.9.2    Level: 2    Role: D/V
 Bekreft at evolusjonsforslag gjennomgår sikkerhetspåvirkningsvurdering før implementering.
 #10.9.3    Level: 2    Role: D/V
 Bekreft at selvforbedringsmekanismer inkluderer tilbakeføringsmuligheter med integritetsverifisering.
 #10.9.4    Level: 3    Role: D/V
 Bekreft at meta-læringssikkerhet forhindrer fiendtlig manipulering av forbedringsalgoritmer.
 #10.9.5    Level: 3    Role: D/V
 Verifiser at rekursiv selvforbedring er begrenset av formelle sikkerhetsbegrensninger med matematiske bevis på konvergens.

---

#### Referanser

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

## 11 Personvern og håndtering av personopplysninger

### Kontrollmål

Oppretthold strenge personvernforpliktelser gjennom hele AI-livssyklusen—innsamling, trening, inferens og hendelseshåndtering—slik at personopplysninger kun behandles med klart samtykke, minimal nødvendig omfang, påvisbar sletting og formelle personvernspesifikasjoner.

---

### 11.1 Anonymisering og dataminimering

 #11.1.1    Level: 1    Role: D/V
 Bekreft at direkte og kvasi-identifikatorer er fjernet eller hashet.
 #11.1.2    Level: 2    Role: D/V
 Bekreft at automatiserte revisjoner måler k-anonymitet/l-mangfold og varsler når tersklene faller under policy.
 #11.1.3    Level: 2    Role: V
 Bekreft at modellens funksjonsviktighetsrapporter viser at det ikke forekommer identifikatorlekkasje utover ε = 0,01 gjensidig informasjon.
 #11.1.4    Level: 3    Role: V
 Verifiser at formelle bevis eller sertifisering av syntetiske data viser at risiko for re-identifisering er ≤ 0,05 selv under koblingsangrep.

---

### 11.2 Retten til å bli glemt og håndheving av sletting

 #11.2.1    Level: 1    Role: D/V
 Bekreft at forespørsler om sletting av datasubjekt blir videreført til rådatasett, kontrollpunkter, innebygde representasjoner, logger og sikkerhetskopier innenfor tjenestenivåavtaler på mindre enn 30 dager.
 #11.2.2    Level: 2    Role: D
 Bekreft at "maskin-avlæring" rutiner fysisk trener på nytt eller approximativt fjerner data ved bruk av sertifiserte algoritmer for avlæring.
 #11.2.3    Level: 2    Role: V
 Bekreft at evaluering med skygge-modell viser at glemte poster påvirker mindre enn 1 % av resultatene etter glemming.
 #11.2.4    Level: 3    Role: V
 Verifiser at sletting av hendelser logges uforanderlig og kan revideres av tilsynsmyndigheter.

---

### 11.3 Differensialt personvernbeskyttelse

 #11.3.1    Level: 2    Role: D/V
 Verifiser at personverntapsregnskapsdashbord varsler når kumulativ ε overskrider policygrenser.
 #11.3.2    Level: 2    Role: V
 Verifiser at black-box personvernsrevisjoner estimerer ε̂ innenfor 10 % av den oppgitte verdien.
 #11.3.3    Level: 3    Role: V
 Bekreft at formelle bevis dekker alle ettertreningsfinjusteringer og innebygginger.

---

### 11.4 Formålsbegrensning og beskyttelse mot omfangskrypning

 #11.4.1    Level: 1    Role: D
 Verifiser at hvert datasett og modellkontrollpunkt har en maskinlesbar formålsmerkelapp som er i samsvar med det opprinnelige samtykket.
 #11.4.2    Level: 1    Role: D/V
 Bekreft at kjøreovervåkere oppdager forespørsler som er inkonsistente med den erklærte hensikten og utløser myk avvisning.
 #11.4.3    Level: 3    Role: D
 Bekreft at policy-as-code-gjerder blokkerer gjenutrulling av modeller til nye domener uten DPIA-gjennomgang.
 #11.4.4    Level: 3    Role: V
 Verifiser at formelle sporbarhetsbevis viser at hele livssyklusen til personopplysninger forblir innenfor det samtykkede omfanget.

---

### 11.5 Samtykkeadministrasjon og lovlig grunnlag for sporing

 #11.5.1    Level: 1    Role: D/V
 Bekreft at en samtykke-administrasjonsplattform (CMP) registrerer opt-in-status, formål og oppbevaringsperiode per datasubjekt.
 #11.5.2    Level: 2    Role: D
 Bekreft at API-er eksponerer samtykkebein; modeller må validere token-omfang før inferens.
 #11.5.3    Level: 2    Role: D/V
 Bekreft at nektet eller trukket samtykke stopper behandlingsrørledninger innen 24 timer.

---

### 11.6 Føderert læring med personvernkontroller

 #11.6.1    Level: 1    Role: D
 Verifiser at klientoppdateringer benytter lokal differensial personvern-støytilsetning før aggregering.
 #11.6.2    Level: 2    Role: D/V
 Bekreft at treningsmetrikker er differensielt private og aldri avslører tap for enkeltklienter.
 #11.6.3    Level: 2    Role: V
 Bekreft at forgiftningsresistent aggregasjon (f.eks. Krum/Trimmed-Mean) er aktivert.
 #11.6.4    Level: 3    Role: V
 Bekreft at formelle beviser demonstrerer det totale ε-budsjettet med mindre enn 5 tap i nytteverdi.

---

#### Referanser

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

## C12 Overvåking, logging og anomalidetektering

### Kontrollmål

Denne seksjonen gir krav for å levere sanntids- og rettsmedisinsk synlighet i hva modellen og andre AI-komponenter ser, gjør og returnerer, slik at trusler kan oppdages, triageres og læres av.

### C12.1 Forespørsel- og responslogging

 #12.1.1    Level: 1    Role: D/V
 Sørg for at alle brukerforespørsler og modellresponsene logges med passende metadata (f.eks. tidsstempel, bruker-ID, økt-ID, modellversjon).
 #12.1.2    Level: 1    Role: D/V
 Bekreft at logger lagres i sikre, tilgangskontrollerte lagringssteder med riktige retningslinjer for oppbevaring og sikkerhetskopieringsprosedyrer.
 #12.1.3    Level: 1    Role: D/V
 Bekreft at logglagringssystemer implementerer kryptering i hvilemodus og under overføring for å beskytte sensitiv informasjon som finnes i logger.
 #12.1.4    Level: 1    Role: D/V
 Bekreft at sensitive data i forespørsler og utdata automatisk blir redigert eller maskert før logging, med konfigurerbare redigeringsregler for personopplysninger (PII), legitimasjon og proprietær informasjon.
 #12.1.5    Level: 2    Role: D/V
 Bekreft at beslutninger om policy og handlinger for sikkerhetsfiltrering loggføres med tilstrekkelig detalj for å muliggjøre revisjon og feilsøking av innholdsmoderering systemer.
 #12.1.6    Level: 2    Role: D/V
 Sikkerstill at loggens integritet er beskyttet gjennom for eksempel kryptografiske signaturer eller skrivebeskyttet lagring.

---

### C12.2 Misbruksdeteksjon og varsling

 #12.2.1    Level: 1    Role: D/V
 Bekreft at systemet oppdager og varsler om kjente jailbreak-mønstre, forsøk på promptinnsprøytning og fiendtlige innganger ved bruk av signaturbasert deteksjon.
 #12.2.2    Level: 1    Role: D/V
 Bekreft at systemet integreres med eksisterende Security Information and Event Management (SIEM) plattformer ved bruk av standard loggformater og protokoller.
 #12.2.3    Level: 2    Role: D/V
 Bekreft at berikede sikkerhetshendelser inkluderer AI-spesifikk kontekst som modellidentifikatorer, konfidenspoeng og beslutninger fra sikkerhetsfiltre.
 #12.2.4    Level: 2    Role: D/V
 Bekreft at oppdagelse av atferdsavvik identifiserer uvanlige samtalemønstre, overdrevne forsøk på gjentakelse eller systematiske sonderingsatferder.
 #12.2.5    Level: 2    Role: D/V
 Bekreft at sanntidsvarslingmekanismer varsler sikkerhetsteam når potensielle policybrudd eller angrepsforsøk blir oppdaget.
 #12.2.6    Level: 2    Role: D/V
 Bekreft at tilpassede regler er inkludert for å oppdage AI-spesifikke trusselmønstre, inkludert koordinerte jailbreak-forsøk, kampanjer for promptinjeksjon og angrep på modellekstraksjon.
 #12.2.7    Level: 3    Role: D/V
 Verifiser at automatiserte arbeidsflyter for hendelsesrespons kan isolere kompromitterte modeller, blokkere ondsinnede brukere og eskalere kritiske sikkerhetshendelser.

---

### C12.3 Modellavdriftsdeteksjon

 #12.3.1    Level: 1    Role: D/V
 Bekreft at systemet sporer grunnleggende ytelsesindikatorer som nøyaktighet, konfidenspoeng, latenstid og feilrater på tvers av modellversjoner og tidsperioder.
 #12.3.2    Level: 2    Role: D/V
 Verifiser at automatiske varsler utløses når ytelsesmetrikker overskrider forhåndsdefinerte nedgangsterskler eller avviker betydelig fra baselinjer.
 #12.3.3    Level: 2    Role: D/V
 Bekreft at overvåkingsverktøy for hallusinasjonsdeteksjon identifiserer og markerer tilfeller der modellutdata inneholder faktiske feil, inkonsistent eller fabrikkert informasjon.

---

### C12.4 Ytelses- og atferdstelemetri

 #12.4.1    Level: 1    Role: D/V
 Sørg for at driftsmetrikker, inkludert forespørselsventetid, tokenforbruk, minnebruk og gjennomstrømning, kontinuerlig samles inn og overvåkes.
 #12.4.2    Level: 1    Role: D/V
 Verifiser at suksess- og feilrater spores med kategorisering av feiltyper og deres grunnårsaker.
 #12.4.3    Level: 2    Role: D/V
 Bekreft at overvåking av ressursbruk inkluderer GPU/CPU-bruk, minneforbruk og lagringskrav, med varsling ved terskeloverskridelser.

---

### C12.5 Planlegging og gjennomføring av AI-hendelsesrespons

 #12.5.1    Level: 1    Role: D/V
 Bekreft at beredskapsplaner for hendelser spesifikt tar for seg sikkerhetshendelser relatert til KI, inkludert modellkompromittering, datainfisering og fiendtlige angrep.
 #12.5.2    Level: 2    Role: D/V
 Bekreft at hendelsesresponsteam har tilgang til AI-spesifikke rettsmedisinske verktøy og ekspertise for å undersøke modellatferd og angrepsvektorer.
 #12.5.3    Level: 3    Role: D/V
 Bekreft at etterhendelsesanalysen inkluderer vurderinger av modellomtrening, oppdateringer av sikkerhetsfiltre og integrering av lærdommer i sikkerhetskontroller.

---

### C12.5 Oppdagelse av nedgang i AI-ytelse

Overvåk og oppdag forringelse i AI-modellens ytelse og kvalitet over tid.

 #12.5.1    Level: 1    Role: D/V
 Sørg for at modellens nøyaktighet, presisjon, tilbakekalling og F1-poeng kontinuerlig overvåkes og sammenlignes med baseline-terskler.
 #12.5.2    Level: 1    Role: D/V
 Bekreft at overvåking av data-drift oppdager endringer i inndatadistribusjonen som kan påvirke modellens ytelse.
 #12.5.3    Level: 2    Role: D/V
 Bekreft at konseptdriftoppdagelse identifiserer endringer i forholdet mellom innganger og forventede utganger.
 #12.5.4    Level: 2    Role: D/V
 Bekreft at ytelsesforringelse utløser automatiserte varsler og setter i gang arbeidsflyter for modellomtrening eller utskifting.
 #12.5.5    Level: 3    Role: V
 Verifiser at rotårsaksanalyse av degradering korrelerer ytelsesnedsettelser med datavariasjoner, infrastrukturproblemer eller eksterne faktorer.

---

### C12.6 DAG-visualisering og arbeidsflytsikkerhet

Beskytt arbeidsflytvisualiseringssystemer mot informasjonslekkasje og manipulasjonsangrep.

 #12.6.1    Level: 1    Role: D/V
 Sørg for at DAG-visualiseringsdata blir renset for å fjerne sensitiv informasjon før lagring eller overføring.
 #12.6.2    Level: 1    Role: D/V
 Bekreft at tilgangskontroller for arbeidsflytvisualisering sikrer at kun autoriserte brukere kan se agentens beslutningsstier og resonnementsspor.
 #12.6.3    Level: 2    Role: D/V
 Bekreft at DAG-dataenes integritet er beskyttet gjennom kryptografiske signaturer og manipulasjons-sikre lagringsmekanismer.
 #12.6.4    Level: 2    Role: D/V
 Bekreft at arbeidsflytvisualiseringssystemer implementerer inndata-validering for å forhindre injeksjonsangrep gjennom konstruerte node- eller kantdata.
 #12.6.5    Level: 3    Role: D/V
 Bekreft at sanntidsoppdateringer av DAG er hastighetsbegrenset og validert for å forhindre tjenestenektangrep på visualiseringssystemer.

---

### C12.7 Proaktiv overvåking av sikkerhetsatferd

Deteksjon og forebygging av sikkerhetstrusler gjennom proaktiv analyse av agentatferd.

 #12.7.1    Level: 1    Role: D/V
 Bekreft at proaktive agentatferder er sikkerhetsvalidert før utførelse med integrert risikovurdering.
 #12.7.2    Level: 2    Role: D/V
 Bekreft at autonome initiativutløsere inkluderer evaluering av sikkerhetskontekst og vurdering av trussellandskap.
 #12.7.3    Level: 2    Role: D/V
 Sørg for at proaktive atferdsmønstre blir analysert for potensielle sikkerhetsimplikasjoner og utilsiktede konsekvenser.
 #12.7.4    Level: 3    Role: D/V
 Sørg for at sikkerhetskritiske proaktive tiltak krever eksplisitte godkjenningskjeder med revisjonsspor.
 #12.7.5    Level: 3    Role: D/V
 Bekreft at oppdagelse av atferdsavvik identifiserer avvik i proaktive agentmønstre som kan indikere kompromittering.

---

### Referanser

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Menneskelig tilsyn, ansvarlighet og styring

### Kontrollmål

Dette kapitlet gir krav for å opprettholde menneskelig tilsyn og klare ansvarskjeder i KI-systemer, og sikrer forklarbarhet, åpenhet og etisk forvaltning gjennom hele KI-livssyklusen.

---

### C13.1 Kill-Switch og overstyringsmekanismer

Gi muligheter for nedstenging eller rulle tilbake når utrygt atferd fra AI-systemet observeres.

 #13.1.1    Level: 1    Role: D/V
 Bekreft at det finnes en manuell nødstoppsmekanisme for å umiddelbart stoppe AI-modellens inferens og utdata.
 #13.1.2    Level: 1    Role: D
 Bekreft at overstyringskontroller kun er tilgjengelige for autorisert personell.
 #13.1.3    Level: 3    Role: D/V
 Bekreft at tilbakestillingsprosedyrer kan gå tilbake til tidligere modellversjoner eller sikkerhetsmodusoperasjoner.
 #13.1.4    Level: 3    Role: V
 Sørg for at overstyringsmekanismer testes regelmessig.

---

### C13.2 Menneskelig-i-sløyfen beslutningskontrollpunkter

Kreve menneskelig godkjenning når innsatsen overskrider forhåndsdefinerte risikogrenseverdier.

 #13.2.1    Level: 1    Role: D/V
 Bekreft at høy-risiko AI-beslutninger krever eksplisitt menneskelig godkjenning før utførelse.
 #13.2.2    Level: 1    Role: D
 Bekreft at risikogrensene er tydelig definert og automatisk utløser arbeidsflyter for manuell gjennomgang.
 #13.2.3    Level: 2    Role: D
 Bekreft at tidskritiske beslutninger har reserveprosedyrer når menneskelig godkjenning ikke kan oppnås innen nødvendige tidsrammer.
 #13.2.4    Level: 3    Role: D/V
 Bekreft at eskaleringsprosedyrer definerer klare myndighetsnivåer for ulike beslutningstyper eller risikokategorier, hvis aktuelt.

---

### C13.3 Ansvarskjede og reviderbarhet

Loggfør operatørhandlinger og modellbeslutninger.

 #13.3.1    Level: 1    Role: D/V
 Bekreft at alle AI-systembeslutninger og menneskelige inngrep loggføres med tidsstempler, brukeridentiteter og beslutningsgrunnlag.
 #13.3.2    Level: 2    Role: D
 Sikre at revisjonslogger ikke kan manipuleres og inkluder mekanismer for integritetsverifisering.

---

### C13.4 Forklarbare AI-teknikker

Overflatefunksjons viktighet, motfaktiske eksempler og lokale forklaringer.

 #13.4.1    Level: 1    Role: D/V
 Bekreft at AI-systemer gir grunnleggende forklaringer på sine beslutninger i et menneskelig lesbart format.
 #13.4.2    Level: 2    Role: V
 Bekreft at forklaringskvaliteten er validert gjennom menneskelige evalueringsstudier og metrikker.
 #13.4.3    Level: 3    Role: D/V
 Bekreft at viktighetsvurderinger av funksjoner eller attributtmetoder (SHAP, LIME, osv.) er tilgjengelige for kritiske beslutninger.
 #13.4.4    Level: 3    Role: V
 Bekreft at kontrafaktiske forklaringer viser hvordan input kan bli endret for å endre resultater, dersom det er relevant for bruksområdet og domenet.

---

### C13.5 Modellkort og bruksavsløringer

Oppretthold modellkort for tiltenkt bruk, ytelsesmålinger og etiske vurderinger.

 #13.5.1    Level: 1    Role: D
 Bekreft at modellkort dokumenterer tiltenkte bruksområder, begrensninger og kjente feilmoduser.
 #13.5.2    Level: 1    Role: D/V
 Bekreft at ytelsesmål for forskjellige relevante bruksområder er oppgitt.
 #13.5.3    Level: 2    Role: D
 Sørg for at etiske vurderinger, skjevhetsvurderinger, rettferdighetsvurderinger, egenskaper ved treningsdata og kjente begrensninger i treningsdata er dokumentert og oppdatert regelmessig.
 #13.5.4    Level: 2    Role: D/V
 Verifiser at modellkort er versjonskontrollert og vedlikeholdt gjennom hele modellens livssyklus med endringssporing.

---

### C13.6 Usikkerhetskvantifisering

Propager konfidenspoeng eller entropimål i svarene.

 #13.6.1    Level: 1    Role: D
 Bekreft at AI-systemer gir konfidenspoeng eller usikkerhetsmål med sine resultater.
 #13.6.2    Level: 2    Role: D/V
 Verifiser at usikkerhetsterskler utløser ekstra menneskelig gjennomgang eller alternative beslutningsveier.
 #13.6.3    Level: 2    Role: V
 Verifiser at usikkerhetskvantifiseringsmetoder er kalibrert og validert mot grunnleggende sannhetsdata.
 #13.6.4    Level: 3    Role: D/V
 Bekreft at usikkerhetspropagering opprettholdes gjennom flertrinns AI-arbeidsflyter.

---

### C13.7 Brukerorienterte rapporter om åpenhet

Gi periodiske opplysninger om hendelser, drift og databruk.

 #13.7.1    Level: 1    Role: D/V
 Bekreft at retningslinjer for databruk og praksiser for håndtering av bruker Samtykke er tydelig kommunisert til interessenter.
 #13.7.2    Level: 2    Role: D/V
 Sørg for at AI-påvirkningsvurderinger gjennomføres og at resultatene inkluderes i rapporteringen.
 #13.7.3    Level: 2    Role: D/V
 Bekreft at transparensrapporter som publiseres jevnlig, oppgir AI-hendelser og driftsmålinger i rimelig detalj.

#### Referanser

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

## Vedlegg A: Ordliste

Dette omfattende ordlisten gir definisjoner av viktige AI-, ML- og sikkerhetsbegreper brukt gjennom AISVS for å sikre klarhet og felles forståelse.
​
Adversarialt eksempel: En inngang bevisst utformet for å få en AI-modell til å gjøre en feil, ofte ved å legge til subtile forstyrrelser som er umerkelige for mennesker.
​
Motstandsdyktighet mot angrep – Motstandsdyktighet mot angrep i KI refererer til en modells evne til å opprettholde ytelsen og motstå å bli lurt eller manipulert av bevisst utformede, ondsinnede inndata laget for å forårsake feil.
​
Agent – AI-agenter er programvaresystemer som bruker kunstig intelligens for å forfølge mål og fullføre oppgaver på vegne av brukere. De viser resonnering, planlegging og hukommelse, og har en grad av autonomi til å ta beslutninger, lære og tilpasse seg.
​
Agentisk AI: AI-systemer som kan operere med en viss grad av autonomi for å oppnå mål, ofte ved å ta beslutninger og utføre handlinger uten direkte menneskelig inngripen.
​
Attributtbasert tilgangskontroll (ABAC): Et tilgangskontrollparadigme hvor autorisasjonsbeslutninger baseres på attributter til brukeren, ressursen, handlingen og miljøet, vurdert på tidspunktet for forespørselen.
​
Bakdørsangrep: En type dataforgiftingsangrep hvor modellen trenes til å svare på en bestemt måte på visse triggere, samtidig som den oppfører seg normalt ellers.
​
Skjevhet: Systematiske feil i AI-modellens resultater som kan føre til urettferdige eller diskriminerende utfall for visse grupper eller i spesifikke kontekster.
​
Utnyttelse av skjevheter: En angrepsteknikk som utnytter kjente skjevheter i AI-modeller for å manipulere resultater eller utfall.
​
Cedar: Amazons policy-språk og motor for finmaskede tillatelser brukt i implementeringen av ABAC for AI-systemer.
​
Tankerekke: En teknikk for å forbedre resonnering i språkmodeller ved å generere mellomliggende resonnementstrinn før man produserer et endelig svar.
​
Strømbrytere: Mekanismer som automatisk stopper AI-systemets operasjoner når spesifikke risikogrenseverdier overskrides.
​
Datalekkasjer: Utilsiktet eksponering av sensitiv informasjon gjennom AI-modellers resultater eller oppførsel.
​
Dataforgiftning: Den bevisste korrupsjonen av treningsdata for å undergrave modellens integritet, ofte for å installere bakdører eller redusere ytelsen.
​
Differensial personvern – Differensial personvern er et matematisk strengt rammeverk for å offentliggjøre statistisk informasjon om datasett samtidig som personvernet til enkeltpersoner beskyttes. Det gjør det mulig for en dataeier å dele aggregerte mønstre for gruppen, samtidig som informasjon som lekkes om spesifikke individer begrenses.
​
Inbeddinger: Tette vektorrepresentasjoner av data (tekst, bilder osv.) som fanger semantisk mening i et høy-dimensjonalt rom.
​
Forklarbarhet – Forklarbarhet i kunstig intelligens er evnen til et AI-system til å gi mennesker forståelige årsaker for sine avgjørelser og prediksjoner, og dermed tilby innsikt i dets interne funksjoner.
​
Forklarbar KI (XAI): KI-systemer utviklet for å gi menneskelig forståelige forklaringer på sine beslutninger og handlinger gjennom ulike teknikker og rammeverk.
​
Federert læring: En maskinlæringsmetode der modeller trenes på tvers av flere desentraliserte enheter som inneholder lokale datasett, uten å utveksle selve dataene.
​
Vernetiltak: Begrensninger implementert for å hindre at AI-systemer produserer skadelige, partiske eller på annen måte uønskede resultater.
​
Hallusinasjon – En AI-hallusinasjon refererer til et fenomen der en AI-modell genererer feilaktig eller villedende informasjon som ikke er basert på dens treningsdata eller faktiske virkelighet.
​
Menneske-i-løyfen (HITL): Systemer utformet for å kreve menneskelig overvåking, verifisering eller inngrep på avgjørende beslutningspunkter.
​
Infrastruktur som kode (IaC): Håndtering og provisjonering av infrastruktur gjennom kode i stedet for manuelle prosesser, noe som muliggjør sikkerhetsskanning og konsistente distribusjoner.
​
Jailbreak: Teknikker som brukes for å omgå sikkerhetsbarrierer i AI-systemer, spesielt i store språkmodeller, for å produsere forbudt innhold.
​
Minste privilegium: Sikkerhetsprinsippet om å gi kun de minimum nødvendige tilgangsrettighetene for brukere og prosesser.
​
LIME (Lokale Tolkningsbare Modell-agnostiske Forklaringer): En teknikk for å forklare prediksjonene til en hvilken som helst maskinlæringsklassifikator ved å tilnærme den lokalt med en tolkningsbar modell.
​
Medlemskapsinferensangrep: Et angrep som har som mål å avgjøre om et spesifikt datapunkt ble brukt til å trene en maskinlæringsmodell.
​
MITRE ATLAS: Trussellandskap for motstandere i kunstig intelligens-systemer; en kunnskapsbase over motstandertaktikker og -teknikker mot AI-systemer.
​
Modellkort – Et modellkort er et dokument som gir standardisert informasjon om ytelsen til en AI-modell, begrensninger, tiltenkte bruksområder og etiske hensyn for å fremme åpenhet og ansvarlig AI-utvikling.
​
Modellutvinning: Et angrep der en motstander gjentatte ganger spør en målsmodell for å lage en funksjonelt lik kopi uten tillatelse.
​
Modellinversjon: Et angrep som forsøker å rekonstruere treningsdata ved å analysere modellens utdata.
​
Modell livssyklusadministrasjon – AI-modell livssyklusadministrasjon er prosessen med å overvåke alle stadier i en AI-modells eksistens, inkludert design, utvikling, implementering, overvåking, vedlikehold og til slutt avvikling, for å sikre at den forblir effektiv og i samsvar med målene.
​
Modellforgiftning: Innføring av sårbarheter eller bakdører direkte i en modell under treningsprosessen.
​
Modelltyveri: Å hente ut en kopi eller en tilnærming av en proprietær modell gjennom gjentatte spørringer.
​
Multi-agent system: Et system sammensatt av flere interagerende AI-agenter, hver med potensielt ulike evner og mål.
​
OPA (Open Policy Agent): En åpen kildekode-policy-motor som muliggjør enhetlig håndheving av policyer på tvers av hele stakken.
​
Personvernbevarende maskinlæring (PPML): Teknikk og metoder for å trene og implementere ML-modeller samtidig som personvernet til treningsdataene beskyttes.
​
Promptinjeksjon: Et angrep der ondsinnede instruksjoner er innebygd i inndata for å overstyre en modells tiltenkte oppførsel.
​
RAG (Retrieval-Augmented Generation): En teknikk som forbedrer store språkmodeller ved å hente relevant informasjon fra eksterne kunnskapskilder før et svar genereres.
​
Red-Teaming: Praksisen med aktivt å teste AI-systemer ved å simulere fiendtlige angrep for å identifisere sårbarheter.
​
SBOM (Programvarematerialeliste): En formell oversikt som inneholder detaljer og forsyningskjederelasjoner for forskjellige komponenter brukt i utviklingen av programvare eller AI-modeller.
​
SHAP (SHapley Additive exPlanations): En spillteoretisk tilnærming for å forklare resultatet av hvilken som helst maskinlæringsmodell ved å beregne bidraget til hver funksjon for prediksjonen.
​
Forsyningskjedeangrep: Kompromittering av et system ved å angripe mindre sikre elementer i forsyningskjeden, slik som tredjepartsbiblioteker, datasett eller forhåndstrente modeller.
​
Transferlæring: En teknikk der en modell utviklet for én oppgave gjenbrukes som utgangspunkt for en modell for en annen oppgave.
​
Vektordatabase: En spesialisert database designet for å lagre høy-dimensjonale vektorer (innbedded data) og utføre effektive likhetssøk.
​
Sårbarhetsskanning: Automatiserte verktøy som identifiserer kjente sikkerhetssårbarheter i programvarekomponenter, inkludert AI-rammeverk og avhengigheter.
​
Vannmerking: Teknikker for å legge inn umerkelige markører i AI-generert innhold for å spore opprinnelsen eller oppdage AI-generering.
​
Zero-dagssårbarhet: En tidligere ukjent sårbarhet som angripere kan utnytte før utviklere lager og distribuerer en sikkerhetsoppdatering.

## Vedlegg B: Referanser

### TODO

## Vedlegg C: AI-sikkerhetsstyring og dokumentasjon

### Mål

Dette vedlegget gir grunnleggende krav for å etablere organisatoriske strukturer, retningslinjer og prosesser for å styre AI-sikkerhet gjennom hele systemets livssyklus.

---

### AC.1 Adopsjon av rammeverket for AI-risikostyring

Gi et formelt rammeverk for å identifisere, vurdere og redusere AI-spesifikke risikoer gjennom hele systemets livssyklus.

 #AC.1.1    Level: 1    Role: D/V
 Bekreft at en AI-spesifikk risikovurderingsmetodikk er dokumentert og implementert.
 #AC.1.2    Level: 2    Role: D
 Bekreft at risikovurderinger gjennomføres på viktige punkter i AI-livssyklusen og før betydelige endringer.
 #AC.1.3    Level: 3    Role: D/V
 Bekreft at risikostyringsrammeverket er i samsvar med etablerte standarder (f.eks. NIST AI RMF).

---

### AC.2 AI-sikkerhetspolicy og -prosedyrer

Definer og håndhev organisatoriske standarder for sikker utvikling, distribusjon og drift av AI.

 #AC.2.1    Level: 1    Role: D/V
 Bekreft at dokumenterte AI-sikkerhetspolicyer eksisterer.
 #AC.2.2    Level: 2    Role: D
 Sørg for at retningslinjer gjennomgås og oppdateres minst årlig og etter betydelige endringer i trusselbildet.
 #AC.2.3    Level: 3    Role: D/V
 Bekreft at retningslinjene dekker alle AISVS-kategorier og gjeldende regulatoriske krav.

---

### AC.3 Roller og ansvar for AI-sikkerhet

Etabler tydelig ansvarlighet for AI-sikkerhet på tvers av organisasjonen.

 #AC.3.1    Level: 1    Role: D/V
 Bekreft at roller og ansvar for AI-sikkerhet er dokumentert.
 #AC.3.2    Level: 2    Role: D
 Bekreft at ansvarlige personer besitter passende sikkerhetsekspertise.
 #AC.3.3    Level: 3    Role: D/V
 Bekreft at et AI-etikk-komité eller styringsråd er etablert for høy-risiko AI-systemer.

---

### AC.4 Håndheving av etiske retningslinjer for KI

Sikre at AI-systemer opererer i samsvar med etablerte etiske prinsipper.

 #AC.4.1    Level: 1    Role: D/V
 Bekreft at etiske retningslinjer for utvikling og implementering av kunstig intelligens eksisterer.
 #AC.4.2    Level: 2    Role: D
 Sørg for at mekanismer er på plass for å oppdage og rapportere etiske brudd.
 #AC.4.3    Level: 3    Role: D/V
 Bekreft at regelmessige etiske vurderinger av implementerte KI-systemer blir gjennomført.

---

### AC.5 Overvåking av overholdelse av AI-regelverk

Oppretthold bevissthet om og overholdelse av utviklende AI-forskrifter.

 #AC.5.1    Level: 1    Role: D/V
 Bekreft at det finnes prosesser for å identifisere gjeldende AI-reguleringer.
 #AC.5.2    Level: 2    Role: D
 Bekreft at overholdelse av alle lovpålagte krav blir vurdert.
 #AC.5.3    Level: 3    Role: D/V
 Bekreft at forskriftsendringer utløser rettidige gjennomganger og oppdateringer av AI-systemer.

#### Referanser

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Vedlegg D: Kunstig intelligens-assistert sikker koding styring og verifisering

### Målsetting

Dette kapitlet definerer grunnleggende organisatoriske kontroller for sikker og effektiv bruk av AI-assisterte kodingverktøy under programvareutvikling, og sikrer sikkerhet og sporbarhet gjennom hele programvareutviklingssyklusen (SDLC).

---

### AD.1 AI-assistert sikker-koding arbeidsflyt

Integrer AI-verktøy i organisasjonens sikre programvareutviklingslivssyklus (SSDLC) uten å svekke eksisterende sikkerhetsporter.

 #AD.1.1    Level: 1    Role: D/V
 Bekreft at en dokumentert arbeidsflyt beskriver når og hvordan AI-verktøy kan generere, omstrukturere eller gjennomgå kode.
 #AD.1.2    Level: 2    Role: D
 Verifiser at arbeidsflyten samsvarer med hver fase i SSDLC (design, implementering, kodegjennomgang, testing, distribusjon).
 #AD.1.3    Level: 3    Role: D/V
 Verifiser at måledata (f.eks. sårbarhetstetthet, gjennomsnittlig tid til å oppdage) samles inn for AI-generert kode og sammenlignes med baser uten menneskelig innblanding.

---

### AD.2 AI-verktøykvalifisering og trusselmodellering

Sørg for at AI-kodeverktøy vurderes for sikkerhetsfunksjoner, risiko og påvirkning på forsyningskjeden før de tas i bruk.

 #AD.2.1    Level: 1    Role: D/V
 Bekreft at en trusselmodell for hvert AI-verktøy identifiserer misbruk, modell-inversjon, datalekkasjer og avhengighetskjede­risikoer.
 #AD.2.2    Level: 2    Role: D
 Bekreft at verktøyevalueringer inkluderer statisk/dynamisk analyse av eventuelle lokale komponenter og vurdering av SaaS-endepunkter (TLS, autentisering/autorisasjon, logging).
 #AD.2.3    Level: 3    Role: D/V
 Sørg for at evalueringer følger en anerkjent rammeverk og blir gjennomført på nytt etter større versjonsendringer.

---

### AD.3 Sikker Prompt- og Kontekstadministrasjon

Forhindre lekkasje av hemmeligheter, proprietær kode og persondata når man konstruerer prompt eller kontekster for AI-modeller.

 #AD.3.1    Level: 1    Role: D/V
 Bekreft at skriftlige retningslinjer forbyr å sende hemmeligheter, legitimasjon eller klassifiserte data i forespørsler.
 #AD.3.2    Level: 2    Role: D
 Bekreft at tekniske kontrollmekanismer (klient-side redigering, godkjente kontekstfiltre) automatisk fjerner sensitive artefakter.
 #AD.3.3    Level: 3    Role: D/V
 Verifiser at forespørsler og svar blir tokenisert, kryptert under overføring og i hvile, og at lagringsperiodene overholder dataklassifiseringspolicyen.

---

### AD.4 Verifisering av AI-generert kode

Oppdag og utbedre sårbarheter introdusert av AI-resultater før koden slås sammen eller distribueres.

 #AD.4.1    Level: 1    Role: D/V
 Sørg for at AI-generert kode alltid blir gjenstand for menneskelig kodegjennomgang.
 #AD.4.2    Level: 2    Role: D
 Bekreft at automatiserte skannere (SAST/IAST/DAST) kjører på hver pull request som inneholder AI-generert kode og blokkerer sammenslåinger ved kritiske funn.
 #AD.4.3    Level: 3    Role: D/V
 Bekreft at differensielle fuzz-tester eller eiendomsbaserte tester beviser sikkerhetskritiske oppførsel (f.eks. inputvalidering, autorisasjonslogikk).

---

### AD.5 Forklarbarhet og sporbarhet av kodeforslag

Gi revisorer og utviklere innsikt i hvorfor et forslag ble gitt og hvordan det utviklet seg.

 #AD.5.1    Level: 1    Role: D/V
 Bekreft at spørsmål/svar-par blir logget med commit-IDer.
 #AD.5.2    Level: 2    Role: D
 Bekreft at utviklere kan vise modellens referanser (treningsutdrag, dokumentasjon) som støtter et forslag.
 #AD.5.3    Level: 3    Role: D/V
 Bekreft at forklaringsrapporter lagres sammen med designartefakter og refereres til i sikkerhetsgjennomganger, i samsvar med ISO/IEC 42001-prinsippene for sporbarhet.

---

### AD.6 Kontinuerlig tilbakemelding og finjustering av modell

Forbedre modellens sikkerhetsytelse over tid samtidig som man forhindrer negativ drift.

 #AD.6.1    Level: 1    Role: D/V
 Bekreft at utviklere kan merke usikre eller ikke-kompatible forslag, og at merkene blir fulgt opp.
 #AD.6.2    Level: 2    Role: D
 Verifiser at samlet tilbakemelding informerer periodisk finjustering eller gjenhentingsforsterket generering med godkjente sikre-kodingskorpora (f.eks. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Bekreft at en lukket løkke evalueringsramme kjører regresjonstester etter hver finjustering; sikkerhetsmålinger må oppfylle eller overgå tidligere referansenivåer før utrulling.

---

#### Referanser

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Vedlegg E: Eksempelverktøy og rammeverk

### Mål

Dette kapittelet gir eksempler på verktøy og rammeverk som kan støtte implementeringen eller oppfyllelsen av en gitt AISVS-krav. Disse skal ikke oppfattes som anbefalinger eller godkjennelser fra AISVS-teamet eller OWASP GenAI Security-prosjektet.

---

### AE.1 Styring av treningsdata og håndtering av skjevhet

Verktøy brukt for dataanalyse, styring og bias-håndtering.

 #AE.1.1    Section: 1.1
 Verktøy for datainventar: Verktøy for administrasjon av datainventar, slik som...
 #AE.1.2    Section: 1.2
 Kryptering under overføring Bruk TLS for HTTPS-baserte applikasjoner, med verktøy som openSSL og pythons`ssl`bibliotek.

---

### AE.2 Brukervalidiering av inndata

Verktøy for å håndtere og validere brukerinput.

 #AE.2.1    Section: 2.1
 Verktøy for forsvar mot promptinjeksjon: Bruk verktøy som NVIDIA's NeMo eller Guardrails AI for sikkerhetsbarrierer.

---

