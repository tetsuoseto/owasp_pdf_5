# C1 Opplæringsdatastyring og skjevhetsbehandling

## Kontrollmål

Treningsdata må anskaffes, håndteres og vedlikeholdes på en måte som ivaretar opprinnelse, sikkerhet, kvalitet og rettferdighet. Dette oppfyller juridiske forpliktelser og reduserer risikoen for skjevhet, forgiftning eller brudd på personvernet gjennom hele AI-livssyklusen.

---

## C1.1 Opprinnelse for treningsdata

Oppretthold et verifiserbart register over alle datasett, godta kun pålitelige kilder, og loggfør hver endring for revisjonssporbarhet.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Sikre at en oppdatert oversikt over alle treningsdatakilder (opprinnelse, forvalter/eier, lisens, innsamlingsmetode, begrensninger for tiltenkt bruk og behandlingshistorikk) blir vedlikeholdt.                               |   1   | D/V  |
| 1.1.2 | Sørg for at kun datasett som er vurdert for kvalitet, representativitet, etisk innkjøp og lisensoverholdelse tillates, for å redusere risikoene for forgiftning, innebygd skjevhet og brudd på immaterielle rettigheter.       |   1   | D/V  |
| 1.1.3 | Sørg for at dataminimering håndheves slik at unødvendige eller sensitive attributter utelates.                                                                                                                                 |   1   | D/V  |
| 1.1.4 | Verifiser at alle dataset-endringer er underlagt en loggført godkjenningsprosess.                                                                                                                                              |   2   | D/V  |
| 1.1.5 | Sørg for at kvaliteten på merking/annotasjon sikres gjennom gjensidig kontroll eller konsensus blant vurderere.                                                                                                                |   2   | D/V  |
| 1.1.6 | Sørg for at "datakort" eller "datablader for datasett" oppdateres for viktige treningsdatasett, og beskriver egenskaper, motivasjoner, sammensetning, innsamling, forhåndsbehandling og anbefalte/ikke anbefalte bruksområder. |   2   | D/V  |

---

## C1.2 Sikkerhet og integritet for treningsdata

Begrens tilgang, krypter data i hvile og under overføring, og valider integriteten for å hindre manipulering eller tyveri.

|   #   | Description                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Verifiser at tilgangskontroller beskytter lagring og databehandlingsrørledninger.                                                                                                                                                                                                                    |   1   | D/V  |
| 1.2.2 | Bekreft at datasett er kryptert under overføring og, for all sensitiv eller personlig identifiserbar informasjon (PII), i ro, ved bruk av industristandard kryptografiske algoritmer og praksiser for nøkkelstyring.                                                                                 |   2   | D/V  |
| 1.2.3 | Verifiser at kryptografiske hasher eller digitale signaturer brukes for å sikre dataintegritet under lagring og overføring, og at automatiserte teknikker for anomalioppdagelse anvendes for å beskytte mot uautoriserte endringer eller korrupsjon, inkludert målrettede forsøk på datatoksinering. |   2   | D/V  |
| 1.2.4 | Bekreft at datasettversjoner spores for å muliggjøre tilbakestilling.                                                                                                                                                                                                                                |   3   | D/V  |
| 1.2.5 | Bekreft at foreldet data blir sikkert slettet eller anonymisert i samsvar med retningslinjer for datalagring, regulatoriske krav, og for å redusere angrepsflaten.                                                                                                                                   |   2   | D/V  |

---

## C1.3 Representasjonsfullstendighet og rettferdighet

Oppdag demografiske skjevheter og anvend tiltak for å sikre at modellens feilrater er rettferdige på tvers av grupper.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Sørg for at datasett blir analysert for representasjonsubalanse og potensielle skjevheter på tvers av lovbeskyttede attributter (f.eks. rase, kjønn, alder) og andre etisk sensitive kjennetegn som er relevante for modellens anvendelsesområde (f.eks. sosioøkonomisk status, geografisk plassering).                                                               |   1   | D/V  |
| 1.3.2 | Bekreft at identifiserte skjevheter blir redusert gjennom dokumenterte strategier som balansering, målrettet dataforsterkning, algoritmiske justeringer (f.eks. forhåndsbehandling, behandling under prosessering, etterbehandlingsteknikker), eller vekting, og at virkningen av disse tiltakene på både rettferdighet og den samlede modellens ytelse blir vurdert. |   2   | D/V  |
| 1.3.3 | Verifiser at rettferdighetsmålinger etter trening blir evaluert og dokumentert.                                                                                                                                                                                                                                                                                       |   2   | D/V  |
| 1.3.4 | Bekreft at en livssyklusbasert bias-administrasjonspolicy tildeler eiere og fastsetter gjennomgangsfrekvens.                                                                                                                                                                                                                                                          |   3   | D/V  |

---

## C1.4 Kvalitet, integritet og sikkerhet ved merking av treningsdata

Beskytt etiketter med kryptering og krev dobbel gjennomgang for kritiske klasser.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Sørg for at merkings-/annotasjonskvaliteten sikres gjennom klare retningslinjer, krysskontroller av gjennomgangere, konsensusmekanismer (f.eks. overvåking av enighet mellom annotatører) og definerte prosesser for å løse uoverensstemmelser.                              |   2   | D/V  |
| 1.4.2 | Bekreft at kryptografiske hasjer eller digitale signaturer brukes på merkevarer for å sikre deres integritet og ekthet.                                                                                                                                                      |   2   | D/V  |
| 1.4.3 | Sørg for at etiketteringsgrensesnitt og plattformer håndhever sterke tilgangskontroller, opprettholder manipulasjonssikre revisjonslogger for alle etiketteringsaktiviteter, og beskytter mot uautoriserte endringer.                                                        |   2   | D/V  |
| 1.4.4 | Bekreft at etiketter som er kritiske for sikkerhet, sikkerhet eller rettferdighet (f.eks. identifisering av giftig innhold, kritiske medisinske funn) gjennomgår obligatorisk uavhengig dobbel vurdering eller tilsvarende robust verifisering.                              |   3   | D/V  |
| 1.4.5 | Bekreft at sensitiv informasjon (inkludert personopplysninger) som utilsiktet er fanget opp eller nødvendigvis tilstede i etiketter, er redigert, pseudonymisert, anonymisert eller kryptert både i hvile og under overføring, i samsvar med prinsippene for dataminimering. |   2   | D/V  |
| 1.4.6 | Sørg for at merkingsveiledninger og instruksjoner er omfattende, versjonskontrollerte og fagfellevurderte.                                                                                                                                                                   |   2   | D/V  |
| 1.4.7 | Sørg for at dataschemer (inkludert for etiketter) er klart definert og versjonskontrollert.                                                                                                                                                                                  |   2   | D/V  |
| 1.8.2 | Bekreft at eksterne eller folkemengdebaserte etiketteringsarbeidsflyter inkluderer tekniske/prosedyremessige sikkerhetstiltak for å sikre datakonfidensialitet, integritet, etikettkvalitet og forhindre datalekkasjer.                                                      |   2   | D/V  |

---

## C1.5 Kvalitetssikring av treningsdata

Kombiner automatisert validering, manuelle stikkprøver og loggført utbedring for å garantere påliteligheten til datasettet.

|   #   | Description                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Bekreft at automatiserte tester fanger opp formateringsfeil, nullverdier og etikettforskyvninger ved hver innlasting eller betydelig transformasjon.                                                                                                                                         |   1   |  D   |
| 1.5.2 | Bekreft at feilede datasett er satt i karantene med revisjonsspor.                                                                                                                                                                                                                           |   1   | D/V  |
| 1.5.3 | Bekreft at manuelle stikkprøver utført av domeneeksperter dekker et statistisk signifikant utvalg (f.eks. ≥1 % eller 1 000 prøver, avhengig av hva som er størst, eller som bestemt av risikovurdering) for å identifisere subtile kvalitetsproblemer som ikke fanges opp av automatisering. |   2   |  V   |
| 1.5.4 | Bekreft at utbedringstiltak er lagt til i opphavsrekordene.                                                                                                                                                                                                                                  |   2   | D/V  |
| 1.5.5 | Bekreft at kvalitetsporter blokkerer underpar-datasett med mindre unntak er godkjent.                                                                                                                                                                                                        |   2   | D/V  |

---

## C1.6 Deteksjon av dataforgiftning

Bruk statistisk anomalideteksjon og karantenearbeidsflyter for å stoppe fiendtlige innsettinger.

|   #   | Description                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Bekreft at anomali-deteksjonsteknikker (f.eks. statistiske metoder, uteliggerdeteksjon, analyseg av innbygginger) anvendes på treningsdata ved inntak og før større treningskjøringer for å identifisere potensielle forgiftningsangrep eller utilsiktet datakorruptjon. |   2   | D/V  |
| 1.6.2 | Bekreft at flaggede prøver utløser manuell gjennomgang før trening.                                                                                                                                                                                                      |   2   | D/V  |
| 1.6.3 | Bekreft at resultatene føres inn i modellens sikkerhetsdossier og informerer om pågående trusselintelligens.                                                                                                                                                             |   2   |  V   |
| 1.6.4 | Bekreft at deteksjonslogikken oppdateres med ny trusselinformasjon.                                                                                                                                                                                                      |   3   | D/V  |
| 1.6.5 | Bekreft at online-læringspipelines overvåker distribusjonsforskyvning.                                                                                                                                                                                                   |   3   | D/V  |
| 1.6.6 | Bekreft at spesifikke forsvar mot kjente datainjiseringsangrepstyper (f.eks. etikettomslag, innsetting av bakdørstriggere, angrep med innflytelsesrike instanser) er vurdert og implementert basert på systemets risikoprofil og datakilder.                             |   3   | D/V  |

---

## C1.7 Sletting av brukerdata og håndheving av samtykke

Respekter slettings- og samtykketrekkingsforespørsler på tvers av datasett, sikkerhetskopier og utledede artefakter.

|   #   | Description                                                                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Bekreft at slettingsarbeidsflyter fjerner primær- og avledede data og vurderer modellens påvirkning, og at påvirkningen på berørte modeller blir vurdert og, om nødvendig, håndtert (for eksempel gjennom nyopplæring eller rekalibrering).                           |   1   | D/V  |
| 1.7.2 | Verifiser at det finnes mekanismer for å spore og respektere omfanget og statusen for brukersamtykke (og tilbakekallinger) for data brukt i trening, og at samtykke valideres før data blir innarbeidet i nye treningsprosesser eller betydelige modelloppdateringer. |   2   |  D   |
| 1.7.3 | Kontroller at arbeidsflyter blir testet årlig og loggført.                                                                                                                                                                                                            |   2   |  V   |

---

## C1.8 Sikkerhet i forsyningskjeden

Vurder eksterne dataleverandører og verifiser integritet over autentiserte, krypterte kanaler.

|   #   | Description                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Sjekk at tredjepartsdataleverandører, inkludert leverandører av forhåndstrente modeller og eksterne datasett, gjennomgår sikkerhets-, personvern-, etisk innkjøps- og datakvalitetsvurderinger før deres data eller modeller integreres.                                          |   2   | D/V  |
| 1.8.2 | Bekreft at eksterne overføringer bruker TLS/autentisering og integritetskontroller.                                                                                                                                                                                               |   1   |  D   |
| 1.8.3 | Bekreft at høyrisiko datakilder (f.eks. åpne datasett med ukjent opprinnelse, ikke-godkjente leverandører) får økt granskning, slik som analyse i sandkasse, omfattende kvalitets-/skjevhetssjekker, og målrettet forgiftningsdeteksjon, før de brukes i sensitive applikasjoner. |   2   | D/V  |
| 1.8.4 | Sikre at forhåndstrente modeller hentet fra tredjeparter blir evaluert for innebygde skjevheter, potensielle bakdører, integriteten til deres arkitektur, og opprinnelsen til deres opprinnelige treningsdata før finjustering eller distribusjon.                                |   3   | D/V  |

---

## C1.9 Oppdagelse av adversarielle prøver

Implementer tiltak under treningsfasen, som adversarial trening, for å forbedre modellens motstandskraft mot adversariale eksempler.

|   #   | Description                                                                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Bekreft at passende forsvar, slik som adversarial trening (ved bruk av genererte adversarielle eksempler), datagenerering med perturberte input, eller robuste optimaliseringsteknikker, er implementert og justert for relevante modeller basert på risikovurdering. |   3   | D/V  |
| 1.9.2 | Bekreft at hvis fiendtlig trening brukes, blir generering, administrasjon og versjonering av fiendtlige datasett dokumentert og kontrollert.                                                                                                                          |   2   | D/V  |
| 1.9.3 | Verifiser at virkningen av trening for motstandsdyktighet mot angrep på modellens ytelse (både mot rene og angrepsbaserte input) og rettferdighetsmålinger blir evaluert, dokumentert og overvåket.                                                                   |   3   | D/V  |
| 1.9.4 | Bekreft at strategier for adversarial trening og robusthet blir periodisk gjennomgått og oppdatert for å motvirke utviklende teknikker for adversariale angrep.                                                                                                       |   3   | D/V  |

---

## C1.10 Datalinje og sporbarhet

Spor hele reisen til hvert datapunkt fra kilde til modellinput for revisjonssporing og hendelsesrespons.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verifiser at avstamningen for hvert datapunkt, inkludert alle transformasjoner, forsterkninger og sammenslåinger, er registrert og kan rekonstrueres. |   2   | D/V  |
| 1.10.2 | Verifiser at slektskontrollregistre er uforanderlige, sikkert lagret og tilgjengelige for revisjoner eller undersøkelser.                             |   2   | D/V  |
| 1.10.3 | Verifiser at sporing av opprinnelse dekker både rådata og syntetiske data.                                                                            |   2   | D/V  |

---

## C1.11 Håndtering av syntetiske data

Sørg for at syntetiske data blir riktig håndtert, merket og risikovurdert.

|   #    | Description                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Bekreft at all syntetisk data er tydelig merket og skillelig fra ekte data gjennom hele prosessen.                            |   2   | D/V  |
| 1.11.2 | Bekreft at genereringsprosessen, parametrene og den tiltenkte bruken av syntetiske data er dokumentert.                       |   2   | D/V  |
| 1.11.3 | Sørg for at syntetiske data er risikovurdert for skjevhet, personvernlekkasje og representasjonsproblemer før bruk i trening. |   2   | D/V  |

---

## C1.12 Data Tilgangsovervåking og Anomalioppdagelse

Overvåk og varsle om uvanlig tilgang til treningsdata for å oppdage interne trusler eller eksfiltrasjon.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.12.1 | Sørg for at all tilgang til treningsdata logges, inkludert bruker, tid og handling.                                            |   2   | D/V  |
| 1.12.2 | Sørg for at tilgangslogger regelmessig gjennomgås for uvanlige mønstre, som store eksporteringer eller tilgang fra nye steder. |   2   | D/V  |
| 1.12.3 | Bekreft at varsler genereres for mistenkelige tilgangshendelser og undersøkes raskt.                                           |   2   | D/V  |

---

## C1.13 Retningslinjer for datalagring og utløp

Definer og håndhev lagringstider for data for å minimere unødvendig datalagring.

|   #    | Description                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Bekreft at eksplisitte oppbevaringsperioder er definert for alle treningsdatasett.                         |   1   | D/V  |
| 1.13.2 | Bekreft at datasett automatisk utløper, slettes eller gjennomgås for sletting ved slutten av livssyklusen. |   2   | D/V  |
| 1.13.3 | Bekreft at handlinger for lagring og sletting blir loggført og kan revideres.                              |   2   | D/V  |

---

## C1.14 Regelverks- og jurisdiksjonsmessig samsvar

Sørg for at alle treningsdata overholder gjeldende lover og forskrifter.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Bekreft at krav til dataresidens og grenseoverskridende overføringer er identifisert og håndhevet for alle datasett.       |   2   | D/V  |
| 1.14.2 | Bekreft at sektorspesifikke forskrifter (f.eks. helsevesen, finans) blir identifisert og ivaretatt ved databehandling.     |   2   | D/V  |
| 1.14.3 | Sørg for at overholdelse av relevante personvernlovgivninger (f.eks. GDPR, CCPA) er dokumentert og gjennomgås regelmessig. |   2   | D/V  |

---

## C1.15 Data Vannmerking og Fingeravtrykkmerking

Oppdag uautorisert gjenbruk eller lekkasje av proprietære eller sensitive data.

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Verifiser at datasett eller delsett er vannmerket eller fingeravtrykket der det er mulig.                           |   3   | D/V  |
| 1.15.2 | Verifiser at metoder for vannmerking/fingeravtrykk ikke introduserer skjevhet eller personvernrisikoer.             |   3   | D/V  |
| 1.15.3 | Bekreft at det utføres periodiske kontroller for å oppdage uautorisert gjenbruk eller lekkasje av vannmerkede data. |   3   | D/V  |

---

## C1.16 Håndtering av registrertes rettigheter

Støtt rettigheter for registrerte, som tilgang, retting, begrensning og innsigelse.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Bekreft at det finnes mekanismer for å svare på forespørsler fra registrerte om tilgang, retting, begrensning eller innsigelse. |   2   | D/V  |
| 1.16.2 | Bekreft at forespørsler blir logget, sporet og behandlet innen lovpålagte tidsrammer.                                           |   2   | D/V  |
| 1.16.3 | Bekreft at prosessene for rettighetene til den registrerte blir testet og gjennomgått regelmessig for effektivitet.             |   2   | D/V  |

---

## C1.17 Analyse av effekten av datasettversjon

Vurder virkningen av endringer i datasett før oppdatering eller utskifting av versjoner.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.17.1 | Bekreft at en konsekvensanalyse utføres før oppdatering eller erstatning av en datasettversjon, som dekker modellens ytelse, rettferdighet og samsvar. |   2   | D/V  |
| 1.17.2 | Sørg for at resultatene av konsekvensanalysen dokumenteres og gjennomgås av relevante interessenter.                                                   |   2   | D/V  |
| 1.17.3 | Bekreft at det finnes tilbakeføringsplaner i tilfelle nye versjoner introduserer uakseptable risikoer eller tilbakeslag.                               |   2   | D/V  |

---

## C1.18 Dataannotasjonsarbeidsstyrkens sikkerhet

Sikre sikkerheten og integriteten til personell som er involvert i dataannotasjon.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Sørg for at alt personell som er involvert i dataannotasjon, er bakgrunnssjekket og opplært i datasikkerhet og personvern. |   2   | D/V  |
| 1.18.2 | Bekreft at alt annoteringspersonell signerer konfidensialitets- og taushetserklæringer.                                    |   2   | D/V  |
| 1.18.3 | Bekreft at annotasjonsplattformer håndhever tilgangskontroller og overvåker for interne trusler.                           |   2   | D/V  |

---

## Referanser

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

