# Bruke AISVS

Standard for sikkerhetsverifisering av kunstig intelligens (AISVS) definerer sikkerhetskrav for moderne AI-applikasjoner og -tjenester, med fokus på aspekter som ligger under kontroll av applikasjonsutviklere.

AISVS er ment for alle som utvikler eller evaluerer sikkerheten til AI-applikasjoner, inkludert utviklere, arkitekter, sikkerhetsingeniører og revisorer. Dette kapittelet introduserer strukturen og bruken av AISVS, inkludert dets verifiseringsnivåer og tiltenkte brukstilfeller.

## Sikkerhetsverifiseringsnivåer for kunstig intelligens

AISVS definerer tre stigende nivåer av sikkerhetsverifisering. Hvert nivå legger til dybde og kompleksitet, og gjør det mulig for organisasjoner å tilpasse sikkerhetsnivået etter risikonivået til sine AI-systemer.

Organisasjoner kan starte på nivå 1 og gradvis adoptere høyere nivåer etterhvert som sikkerhetsmodenhet og trusseleksponering øker.

### Definisjon av nivåene

Hver krav i AISVS v1.0 er tildelt til ett av følgende nivåer:

#### Krav for nivå 1

Nivå 1 inkluderer de mest kritiske og grunnleggende sikkerhetskravene. Disse fokuserer på å forhindre vanlige angrep som ikke er avhengige av andre forutsetninger eller sårbarheter. De fleste kontroller på Nivå 1 er enten enkle å implementere eller så essensielle at innsatsen rettferdiggjøres.

#### Krav på nivå 2

Nivå 2 tar for seg mer avanserte eller mindre vanlige angrep, samt lagdelte forsvar mot utbredte trusler. Disse kravene kan innebære mer kompleks logikk eller rette seg mot spesifikke forutsetninger for angrep.

#### Krav på nivå 3

Nivå 3 inkluderer kontroller som vanligvis er vanskeligere å implementere eller situasjonsavhengige i bruk. Disse representerer ofte forsvar-i-dybden-mekanismer eller tiltak mot nisje-, målrettede eller komplekse angrep.

### Rolle (D/V)

Hvert AISVS-krav er merket i henhold til hovedmålgruppen:

* D – Utviklerfokuserte krav
* V – Krav rettet mot verifikator/revisor
* D/V – Relevant for både utviklere og verifikatorer

