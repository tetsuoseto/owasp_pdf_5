# C1 Træningsdata Governance & Bias Management

## Kontrolmål

Træningsdata skal skaffes, håndteres og vedligeholdes på en måde, der bevarer oprindelse, sikkerhed, kvalitet og retfærdighed. Dette opfylder juridiske forpligtelser og reducerer risici for bias, forurening eller brud på privatlivets fred gennem hele AI-livscyklussen.

---

## C1.1 Oprindelse af træningsdata

Oprethold en verificerbar oversigt over alle datasæt, accepter kun betroede kilder, og log alle ændringer for revisionsmulighed.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Sørg for, at der føres et opdateret inventar over hver eneste træningsdatakilde (oprindelse, ansvarlig/ejer, licens, indsamlingmetode, begrænsninger for tilsigtet brug og behandlingshistorik).                                                     |   1   | D/V  |
| 1.1.2 | Sørg for, at kun datasæt, der er kontrolleret for kvalitet, repræsentativitet, etisk indsamling og overholdelse af licens, er tilladt, hvilket reducerer risikoen for forurening, indlejret bias og krænkelse af intellektuelle ejendomsrettigheder. |   1   | D/V  |
| 1.1.3 | Bekræft, at data-minimering håndhæves, så unødvendige eller følsomme attributter udelukkes.                                                                                                                                                          |   1   | D/V  |
| 1.1.4 | Bekræft, at alle ændringer i datasættet er underlagt en godkendelsesproces, der logges.                                                                                                                                                              |   2   | D/V  |
| 1.1.5 | Sørg for, at kvaliteten af mærkning/annotering sikres via krydstjek eller konsensus blandt anmeldere.                                                                                                                                                |   2   | D/V  |
| 1.1.6 | Bekræft, at "datakort" eller "datasheets for datasæt" opretholdes for væsentlige træningsdatasæt, som detaljerer egenskaber, motivationer, sammensætning, indsamlingprocesser, forbehandling samt anbefalede/ikke-anbefalede anvendelser.            |   2   | D/V  |

---

## C1.2 Sikkerhed og integritet for træningsdata

Begræns adgang, krypter data i hvile og under overførsel, og valider integriteten for at forhindre manipulation eller tyveri.

|   #   | Description                                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Bekræft, at adgangskontroller beskytter lager og pipelines.                                                                                                                                                                                                                                          |   1   | D/V  |
| 1.2.2 | Bekræft, at datasæt er krypteret under overførsel og, for alle følsomme eller personligt identificerbare oplysninger (PII), i hvile, ved hjælp af kryptografiske algoritmer og nøglehåndteringspraksis efter industristandard.                                                                       |   2   | D/V  |
| 1.2.3 | Bekræft, at kryptografiske hashværdier eller digitale signaturer bruges til at sikre dataintegritet under lagring og overførsel, samt at automatiserede anomalidetektionsteknikker anvendes for at beskytte mod uautoriserede ændringer eller korruption, herunder målrettede dataforgiftningforsøg. |   2   | D/V  |
| 1.2.4 | Bekræft, at dataset-versioner spores for at muliggøre tilbagerulning.                                                                                                                                                                                                                                |   3   | D/V  |
| 1.2.5 | Bekræft, at forældede data bliver sikkert slettet eller anonymiseret i overensstemmelse med dataopbevaringspolitikker, lovgivningsmæssige krav og for at mindske angrebsoverfladen.                                                                                                                  |   2   | D/V  |

---

## C1.3 Repræsentationsfuldstændighed og retfærdighed

Registrer demografiske skævheder og anvend afbødning, så modellens fejlprocenter er retfærdige på tværs af grupper.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.3.1 | Bekræft, at datasæt profileres for repræsentationsubalance og potentielle biaser på tværs af juridisk beskyttede attributter (f.eks. race, køn, alder) og andre etisk følsomme karakteristika, der er relevante for modellens anvendelsesområde (f.eks. socioøkonomisk status, geografisk placering).                                                  |   1   | D/V  |
| 1.3.2 | Bekræft, at de identificerede skævheder afbødes via dokumenterede strategier såsom genbalancering, målrettet dataaugmentation, algoritmiske justeringer (f.eks. præ-behandling, behandling under processen, efterbehandlingsteknikker) eller omvægtning, og at virkningen af afbødningen både på retfærdighed og den samlede modelpræstation vurderes. |   2   | D/V  |
| 1.3.3 | Bekræft, at efter-trænings retfærdigheds-målinger evalueres og dokumenteres.                                                                                                                                                                                                                                                                           |   2   | D/V  |
| 1.3.4 | Bekræft, at en politik for livscyklus-biasstyring tildeler ejere og fastsætter gennemgangsfrekvens.                                                                                                                                                                                                                                                    |   3   | D/V  |

---

## C1.4 Kvalitet, integritet og sikkerhed ved mærkning af træningsdata

Beskyt etiketter med kryptering og kræv dobbelt gennemgang for kritiske klasser.

|   #   | Description                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Sørg for, at kvaliteten af mærkning/annotering sikres gennem klare retningslinjer, krydstjek af anmeldere, konsensusmekanismer (f.eks. overvågning af enighed mellem annotatorer) og definerede processer til at løse uoverensstemmelser.                                                    |   2   | D/V  |
| 1.4.2 | Bekræft, at kryptografiske hashværdier eller digitale signaturer anvendes på etiketterede artefakter for at sikre deres integritet og ægthed.                                                                                                                                                |   2   | D/V  |
| 1.4.3 | Bekræft, at mærkningsgrænseflader og platforme håndhæver stærke adgangskontroller, opretholder manipulationssikre revisionslogs over alle mærkningsaktiviteter og beskytter mod uautoriserede ændringer.                                                                                     |   2   | D/V  |
| 1.4.4 | Sørg for, at etiketter, der er afgørende for sikkerhed, beskyttelse eller retfærdighed (f.eks. identificering af giftigt indhold, kritiske medicinske fund), gennemgår obligatorisk uafhængig dobbeltgennemgang eller tilsvarende robust verifikation.                                       |   3   | D/V  |
| 1.4.5 | Bekræft, at følsomme oplysninger (inklusive personligt identificerbare oplysninger) utilsigtet indfanget eller nødvendigvis til stede i labels, bliver sløret, pseudonymiseret, anonymiseret eller krypteret både i hvile og under overførsel, i henhold til principperne om dataminimering. |   2   | D/V  |
| 1.4.6 | Bekræft, at mærkningsvejledninger og instruktioner er omfattende, versionsstyrede og fagfællebedømte.                                                                                                                                                                                        |   2   | D/V  |
| 1.4.7 | Bekræft, at dataschemas (inklusive for labels) er klart definerede og versionsstyrede.                                                                                                                                                                                                       |   2   | D/V  |
| 1.8.2 | Bekræft, at outsourcet eller crowdsourcet mærkningsarbejdsgange inkluderer tekniske/procedurale sikkerhedsforanstaltninger for at sikre datakonfidensialitet, integritet, mærkningskvalitet og forhindre datalækage.                                                                         |   2   | D/V  |

---

## C1.5 Kvalitetssikring af træningsdata

Kombiner automatiseret validering, manuel stikprøvekontrol og logført udbedring for at sikre datasættets pålidelighed.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Bekræft, at automatiserede tests fanger formateringsfejl, null-værdier og mærkningsskævheder ved hver indlæsning eller betydelig transformation.                                                                                                                                              |   1   |  D   |
| 1.5.2 | Bekræft, at fejlslagne datasæt er isoleret med revisionsspor.                                                                                                                                                                                                                                 |   1   | D/V  |
| 1.5.3 | Bekræft, at manuelle stikprøver foretaget af domæneeksperter dækker et statistisk signifikant udvalg (f.eks. ≥1 % eller 1.000 prøver, afhængigt af hvad der er størst, eller som fastsat ved risikovurdering) for at identificere finere kvalitetsproblemer, som automatisering ikke opdager. |   2   |  V   |
| 1.5.4 | Bekræft, at udbedringstrin tilføjes til provenance-poster.                                                                                                                                                                                                                                    |   2   | D/V  |
| 1.5.5 | Bekræft, at kvalitetskontroller blokerer underordnede datasæt, medmindre undtagelser er godkendt.                                                                                                                                                                                             |   2   | D/V  |

---

## C1.6 Detektion af dataforgiftning

Anvend statistisk anomali-detektion og karantænearbejdsgange for at stoppe fjendtlige indsættelser.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Bekræft, at anomalidetektionsmetoder (f.eks. statistiske metoder, outlier-detektion, indlejring analyse) anvendes på træningsdata ved indtagelse og før større træningskørsler for at identificere potentielle forgiftningsangreb eller utilsigtet datakorruption. |   2   | D/V  |
| 1.6.2 | Bekræft, at markerede prøver udløser manuel gennemgang før træning.                                                                                                                                                                                                |   2   | D/V  |
| 1.6.3 | Bekræft, at resultaterne føder modellens sikkerhedsdossier og informerer den løbende trusselsintelligens.                                                                                                                                                          |   2   |  V   |
| 1.6.4 | Bekræft, at detektionslogikken opdateres med ny trusselsinformation.                                                                                                                                                                                               |   3   | D/V  |
| 1.6.5 | Bekræft, at online-læringspipelines overvåger for distributionsændringer.                                                                                                                                                                                          |   3   | D/V  |
| 1.6.6 | Bekræft, at specifikke forsvar mod kendte typer af dataforureningsangreb (f.eks. mærkeombytning, indsættelse af bagdørstriggere, angreb med indflydelsesrige instanser) er overvejet og implementeret baseret på systemets risikoprofil og datakilder.             |   3   | D/V  |

---

## C1.7 Sletning af brugerdata og håndhævelse af samtykke

Respekter anmodninger om sletning og tilbagetrækning af samtykke på tværs af datasæt, sikkerhedskopier og afledte artefakter.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.7.1 | Bekræft, at sletningsarbejdsgange rydder primære og afledte data samt vurderer modelpåvirkningen, og at påvirkningen på berørte modeller bliver vurderet og om nødvendigt håndteret (f.eks. gennem genuddannelse eller genkalibrering).                                              |   1   | D/V  |
| 1.7.2 | Bekræft, at der er mekanismer på plads til at spore og respektere omfanget og status for brugertilladelse (og tilbagekaldelser) for data, der bruges i træning, og at tilladelsen valideres, før data bliver indarbejdet i nye træningsprocesser eller væsentlige modelopdateringer. |   2   |  D   |
| 1.7.3 | Bekræft, at arbejdsprocesser testes årligt og logges.                                                                                                                                                                                                                                |   2   |  V   |

---

## C1.8 Forsyningskædesikkerhed

Gennemgå eksterne dataleverandører og verificer integriteten over autentificerede, krypterede kanaler.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.8.1 | Sørg for, at tredjepartsdataleverandører, herunder udbydere af foruddannede modeller og eksterne datasæt, gennemgår sikkerheds-, privatlivs-, etisk indkøb- og datakvalitetsdue diligence, inden deres data eller modeller integreres.                                               |   2   | D/V  |
| 1.8.2 | Bekræft, at eksterne overførsler bruger TLS/autentificering og integritetskontrol.                                                                                                                                                                                                   |   1   |  D   |
| 1.8.3 | Bekræft, at højrisikodata kilder (f.eks. open source-datasæt med ukendt oprindelse, ikke-godkendte leverandører) gennemgår øget kontrol, såsom isoleret analyse, omfattende kvalitets-/bias-kontroller og målrettet forgiftningsdetektion, før de anvendes i følsomme applikationer. |   2   | D/V  |
| 1.8.4 | Bekræft, at forudtrænede modeller, der er modtaget fra tredjeparter, vurderes for indlejrede bias, potentielle bagdøre, integriteten af deres arkitektur og oprindelsen af deres oprindelige træningsdata, før de finjusteres eller tages i brug.                                    |   3   | D/V  |

---

## C1.9 Modstanderes prøveidentifikation

Implementer foranstaltninger under træningsfasen, såsom adversarial træning, for at øge modellens modstandsdygtighed over for adversarielle eksempler.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Bekræft, at passende forsvarsmetoder, såsom adversarial træning (ved brug af genererede adversariale eksempler), dataforøgelse med perturberede input eller robuste optimeringsteknikker, er implementeret og justeret for relevante modeller baseret på risikovurdering. |   3   | D/V  |
| 1.9.2 | Bekræft, at hvis adversarial træning anvendes, er genereringen, håndteringen og versioneringen af adversariale datasæt dokumenteret og kontrolleret.                                                                                                                      |   2   | D/V  |
| 1.9.3 | Bekræft, at effekten af træning i modstandsdygtighed over for angreb (både mod rene og modstridende input) og retfærdighedsmål bliver evalueret, dokumenteret og overvåget.                                                                                               |   3   | D/V  |
| 1.9.4 | Bekræft, at strategier for modstandertræning og robusthed regelmæssigt gennemgås og opdateres for at imødegå udviklende teknikker til modstanderangreb.                                                                                                                   |   3   | D/V  |

---

## C1.10 Data Lineage og Sporbarhed

Spor hele rejsen for hvert datapunkt fra kilden til modelinputtet for revisionsformål og hændelsesrespons.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Sørg for, at slægtslinjen for hvert datapunkt, inklusive alle transformationer, augmenteringer og sammensmeltninger, er registreret og kan rekonstrueres. |   2   | D/V  |
| 1.10.2 | Bekræft, at slægtskabsposter er uforanderlige, sikkert lagret og tilgængelige til revisioner eller undersøgelser.                                         |   2   | D/V  |
| 1.10.3 | Bekræft, at stamtavlesporing dækker både rå og syntetiske data.                                                                                           |   2   | D/V  |

---

## C1.11 Håndtering af syntetiske data

Sørg for, at syntetiske data håndteres korrekt, mærkes og risikovurderes.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Sørg for, at alle syntetiske data er tydeligt mærket og adskilt fra rigtige data gennem hele processen.                             |   2   | D/V  |
| 1.11.2 | Verifier, at genereringsprocessen, parametrene og den tilsigtede anvendelse af syntetiske data er dokumenteret.                     |   2   | D/V  |
| 1.11.3 | Sørg for, at syntetiske data bliver risikovurderet for bias, privatlivslæk, og repræsentationsproblemer, før de bruges til træning. |   2   | D/V  |

---

## C1.12 Overvågning af dataadgang og anomalidetektion

Overvåg og alarmer ved usædvanlig adgang til træningsdata for at opdage insidertrusler eller dataudtræk.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Bekræft, at al adgang til træningsdata logges, inklusive bruger, tidspunkt og handling.                                            |   2   | D/V  |
| 1.12.2 | Bekræft, at adgangslogfiler regelmæssigt gennemgås for usædvanlige mønstre, såsom store eksporter eller adgang fra nye lokationer. |   2   | D/V  |
| 1.12.3 | Bekræft, at alarmer genereres for mistænkelige adgangshændelser og undersøges hurtigt.                                             |   2   | D/V  |

---

## C1.13 Politikker for datalagring og udløb

Definér og håndhæv datalagringsperioder for at minimere unødvendig datalagring.

|   #    | Description                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Bekræft, at eksplicitte opbevaringsperioder er defineret for alle træningsdatasæt.                               |   1   | D/V  |
| 1.13.2 | Bekræft, at datasæt automatisk udløber, slettes eller gennemgås for sletning ved slutningen af deres livscyklus. |   2   | D/V  |
| 1.13.3 | Verificer, at opbevarings- og sletningshandlinger bliver logget og kan revideres.                                |   2   | D/V  |

---

## C1.14 Regulatorisk og jurisdiktionsmæssig overholdelse

Sikre, at alle træningsdata overholder gældende love og regler.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Bekræft, at krav til dataresidens og grænseoverskridende overførsler er identificeret og håndhævet for alle datasæt.            |   2   | D/V  |
| 1.14.2 | Bekræft, at sektorspecifikke regler (f.eks. sundhedssektoren, finanssektoren) er identificeret og håndteres i databehandlingen. |   2   | D/V  |
| 1.14.3 | Sørg for, at overholdelse af relevante privatlivslover (f.eks. GDPR, CCPA) er dokumenteret og gennemgås regelmæssigt.           |   2   | D/V  |

---

## C1.15 Data Vandmærkning og Fingeraftryk

Registrer uautoriseret genbrug eller lækage af proprietære eller følsomme data.

|   #    | Description                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Bekræft, at datasæt eller delmængder er vandmærket eller fingeraftrykt, hvor det er muligt.                     |   3   | D/V  |
| 1.15.2 | Bekræft, at vandmærkning/fingeraftryksmetoder ikke introducerer skævheder eller privatlivsrisici.               |   3   | D/V  |
| 1.15.3 | Bekræft, at der udføres periodiske kontrol for at opdage uautoriseret genbrug eller lækage af vandmærkede data. |   3   | D/V  |

---

## C1.16 Håndtering af registreredes rettigheder

Understøt registreredes rettigheder såsom adgang, berigtigelse, begrænsning og indsigelse.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Bekræft, at der findes mekanismer til at reagere på forespørgsler fra registrerede personer om adgang, berigtigelse, begrænsning eller indsigelse. |   2   | D/V  |
| 1.16.2 | Bekræft, at forespørgsler bliver logget, sporet og opfyldt inden for lovbestemte tidsrammer.                                                       |   2   | D/V  |
| 1.16.3 | Bekræft, at processerne for registreredes rettigheder testes og gennemgås regelmæssigt for effektivitet.                                           |   2   | D/V  |

---

## C1.17 Analyse af virkningen af datasætversioner

Vurder virkningen af ændringer i datasættet, før du opdaterer eller udskifter versioner.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Bekræft, at der udføres en konsekvensanalyse, før en datasætversion opdateres eller udskiftes, som omfatter modelpræstation, retfærdighed og overholdelse. |   2   | D/V  |
| 1.17.2 | Bekræft, at resultaterne af konsekvensanalysen er dokumenteret og gennemgået af relevante interessenter.                                                   |   2   | D/V  |
| 1.17.3 | Sørg for, at der findes rollback-planer, hvis nye versioner introducerer uacceptable risici eller tilbageskridt.                                           |   2   | D/V  |

---

## C1.18 Datasætningsannoterings arbejdsstyrkesikkerhed

Sikre sikkerheden og integriteten for personale involveret i dataannotering.

|   #    | Description                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Sørg for, at alt personale involveret i dataannotering er baggrundstjekket og uddannet i datasikkerhed og privatliv. |   2   | D/V  |
| 1.18.2 | Bekræft, at alt annoteringspersonale underskriver fortroligheds- og ikke-offentliggørelsesaftaler.                   |   2   | D/V  |
| 1.18.3 | Bekræft, at annoteringsplatforme håndhæver adgangskontroller og overvåger for interne trusler.                       |   2   | D/V  |

---

## Referencer

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

