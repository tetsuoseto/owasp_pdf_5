# C12 Overvågning, Logning og Anomali-detektion

## Kontrolmål

Denne sektion indeholder krav til at levere realtids- og retsmedicinsk synlighed i, hvad modellen og andre AI-komponenter ser, gør og returnerer, så trusler kan opdages, prioriteres og læres af.

## C12.1 Anmodning og svarlogning

|   #    | Description                                                                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Bekræft, at alle brugerforespørgsler og modelresponser logges med passende metadata (f.eks. tidsstempel, bruger-ID, session-ID, modelversion).                                                                                                 |   1   | D/V  |
| 12.1.2 | Bekræft, at logs gemmes i sikre, adgangskontrollerede lagre med passende opbevaringspolitikker og backup-procedurer.                                                                                                                           |   1   | D/V  |
| 12.1.3 | Bekræft, at loglagringssystemer implementerer kryptering både i hviletilstand og under overførsel for at beskytte følsomme oplysninger indeholdt i logfiler.                                                                                   |   1   | D/V  |
| 12.1.4 | Bekræft, at følsomme data i prompts og output automatisk bliver redigeret eller maskeret, før de logges, med konfigurerbare redigeringsregler for personligt identificerbare oplysninger (PII), adgangsoplysninger og proprietære oplysninger. |   1   | D/V  |
| 12.1.5 | Bekræft, at beslutninger om politik og sikkerhedsfiltrering registreres med tilstrækkelig detaljeringsgrad for at muliggøre revision og fejlfinding af indholdsmoderationssystemer.                                                            |   2   | D/V  |
| 12.1.6 | Bekræft, at logintegriteten er beskyttet gennem f.eks. kryptografiske signaturer eller skrivebeskyttet lagring.                                                                                                                                |   2   | D/V  |

---

## C12.2 Misbrugsdetektion og advarsler

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Bekræft, at systemet opdager og advarer om kendte jailbreak-mønstre, forsøg på promptinjektion og modstridende input ved brug af signaturbaseret detektion.                                 |   1   | D/V  |
| 12.2.2 | Bekræft, at systemet integreres med eksisterende Security Information and Event Management (SIEM) platforme ved brug af standard logformater og protokoller.                                |   1   | D/V  |
| 12.2.3 | Bekræft, at berigede sikkerhedshændelser inkluderer AI-specifik kontekst såsom modelidentifikatorer, tillidsvurderinger og beslutninger om sikkerhedsfiltre.                                |   2   | D/V  |
| 12.2.4 | Bekræft, at adfærdsbaseret anomali-detektion identificerer usædvanlige samtalemønstre, overdrevne gentagelsesforsøg eller systematiske sonderingsadfærd.                                    |   2   | D/V  |
| 12.2.5 | Bekræft, at mekanismer til realtidsalarmering underretter sikkerhedsteams, når potentielle overtrædelser af politikker eller angrebsforsøg opdages.                                         |   2   | D/V  |
| 12.2.6 | Bekræft, at brugerdefinerede regler er inkluderet til at opdage AI-specifikke trusselsmønstre, herunder koordinerede jailbreak-forsøg, promptinjektionskampagner og modeludtrækningsangreb. |   2   | D/V  |
| 12.2.7 | Bekræft, at automatiserede hændelsesresponsarbejdsgange kan isolere kompromitterede modeller, blokere ondsindede brugere og eskalere kritiske sikkerhedshændelser.                          |   3   | D/V  |

---

## C12.3 Modeldrejningsdetektion

|   #    | Description                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.3.1 | Bekræft, at systemet overvåger grundlæggende ydelsesmetrikker som nøjagtighed, konfidensscores, latenstid og fejlprocenter på tværs af modelversioner og tidsperioder.         |   1   | D/V  |
| 12.3.2 | Bekræft, at automatiserede alarmer udløses, når ydelsesmålinger overskrider foruddefinerede nedbrydningstærskler eller afviger signifikant fra baselinjer.                     |   2   | D/V  |
| 12.3.3 | Bekræft, at hallucinationsdetektionsmonitorer identificerer og markerer tilfælde, hvor modeloutput indeholder faktuelt ukorrekte, inkonsistente eller fabrikerede oplysninger. |   2   | D/V  |

---

## C12.4 Ydeevne- og adfærdstelemetri

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Bekræft, at operationelle målinger, herunder forespørgselsforsinkelse, tokenforbrug, hukommelsesforbrug og gennemløb, løbende indsamles og overvåges.       |   1   | D/V  |
| 12.4.2 | Bekræft, at succes- og fejlrater registreres med kategorisering af fejltyper og deres grundårsager.                                                         |   1   | D/V  |
| 12.4.3 | Bekræft, at overvågning af ressourceudnyttelse inkluderer GPU/CPU-brug, hukommelsesforbrug og lagringskrav med alarmer ved overskridelse af tærskelværdier. |   2   | D/V  |

---

## C12.5 AI-hændelsesreaktionsplanlægning og udførelse

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Sørg for, at beredskabsplaner for hændelsesrespons specifikt adresserer AI-relaterede sikkerhedshændelser, herunder modelkompromittering, dataforgiftning og adversariale angreb. |   1   | D/V  |
| 12.5.2 | Sørg for, at hændelsesreaktionsteams har adgang til AI-specifikke retsmedicinske værktøjer og ekspertise til at undersøge modeladfærd og angrebsvektorer.                         |   2   | D/V  |
| 12.5.3 | Bekræft, at efterhændelsesanalysen inkluderer overvejelser om modelgenuddannelse, opdateringer af sikkerhedsfiltre og integration af læringserfaringer i sikkerhedskontroller.    |   3   | D/V  |

---

## C12.5 AI Ydeevnedæmpningsdetektion

Overvåg og registrer forringelse i AI-modelens ydeevne og kvalitet over tid.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Sørg for, at modelens nøjagtighed, præcision, recall og F1-score løbende overvåges og sammenlignes med baseline-grænseværdier.              |   1   | D/V  |
| 12.5.2 | Bekræft, at data-driftdetektion overvåger ændringer i inputfordelingen, som kan påvirke modellens ydeevne.                                  |   1   | D/V  |
| 12.5.3 | Bekræft, at konceptskreddetektion identificerer ændringer i forholdet mellem input og forventede output.                                    |   2   | D/V  |
| 12.5.4 | Bekræft, at ydelsesforringelse udløser automatiserede alarmer og igangsætter workflows til gen-træning eller udskiftning af modellen.       |   2   | D/V  |
| 12.5.5 | Bekræft, at analyse af årsager til degradering korrelerer præstationsfald med datændringer, infrastrukturproblemer eller eksterne faktorer. |   3   |  V   |

---

## C12.6 DAG-visualisering og arbejdsgangssikkerhed

Beskyt arbejdsgangsvisualiseringssystemer mod informationslækage og manipulationsangreb.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Bekræft, at DAG-visualiseringsdata renses for at fjerne følsomme oplysninger inden lagring eller overførsel.                                             |   1   | D/V  |
| 12.6.2 | Bekræft, at adgangskontroller for workflow-visualisering sikrer, at kun autoriserede brugere kan se agentens beslutningsstier og ræsonnementsspor.       |   1   | D/V  |
| 12.6.3 | Bekræft, at DAG-dataintegritet er beskyttet gennem kryptografiske signaturer og manipulation-synlige lagringsmekanismer.                                 |   2   | D/V  |
| 12.6.4 | Bekræft, at workflowsystemer til visualisering implementerer inputvalidering for at forhindre injektionsangreb gennem manipulerede node- eller kantdata. |   2   | D/V  |
| 12.6.5 | Bekræft, at realtidsopdateringer af DAG er hastighedsbegrænsede og validerede for at forhindre tjenestenægtelsesangreb på visualiseringssystemer.        |   3   | D/V  |

---

## C12.7 Proaktiv overvågning af sikkerhedsadfærd

Detektion og forebyggelse af sikkerhedstrusler gennem proaktiv agentadfærdsanalyse.

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Bekræft, at proaktive agentadfærd er sikkerhedsvaliderede inden udførelse med integration af risikovurdering.                |   1   | D/V  |
| 12.7.2 | Bekræft, at autonome initiativudløsere inkluderer evaluering af sikkerhedskontekst og vurdering af trusselslandskabet.       |   2   | D/V  |
| 12.7.3 | Bekræft, at proaktive adfærdsmønstre analyseres for potentielle sikkerhedsmæssige implikationer og utilsigtede konsekvenser. |   2   | D/V  |
| 12.7.4 | Bekræft, at sikkerhedskritiske proaktive handlinger kræver eksplicitte godkendelseskæder med revisionsspor.                  |   3   | D/V  |
| 12.7.5 | Bekræft, at adfærdsafvigelsesdetektion identificerer afvigelser i proaktive agentmønstre, som kan indikere kompromittering.  |   3   | D/V  |

---

## Referencer

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

