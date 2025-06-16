# 10 Modstandskraft mod angreb og beskyttelse af privatlivets fred

## Kontrolmål

Sørg for, at AI-modeller forbliver pålidelige, privatlivsbeskyttende og modstandsdygtige over for misbrug, når de udsættes for undvigelse, inferens, udtrækning eller forgiftningsangreb.

---

## 10.1 Modeljustering og sikkerhed

Beskyt mod skadelige eller politikovertrædende output.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Bekræft, at en test-pakke for justering (red-team prompts, jailbreak-tests, uautoriseret indhold) er versionsstyret og køres ved hver modeludgivelse. |   1   | D/V  |
| 10.1.2 | Bekræft, at afvisnings- og sikker-afslutnings-værn er håndhævet.                                                                                      |   1   |  D   |
| 10.1.3 | Bekræft, at en automatiseret evaluator måler andelen af skadeligt indhold og markerer tilbagefald, der overskrider en fastsat grænse.                 |   2   | D/V  |
| 10.1.4 | Bekræft, at mod-jailbreak træning er dokumenteret og reproducerbar.                                                                                   |   2   |  D   |
| 10.1.5 | Bekræft, at formelle beviser for overholdelse af politikker eller certificeret overvågning dækker kritiske områder.                                   |   3   |  V   |

---

## 10.2 Modstand mod modstandseksempler

Øg modstandsdygtigheden over for manipulerede input. Robust fjendtlig træning og benchmark scoring er den nuværende bedste praksis.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Kontroller, at projektets repositories indeholder konfigurationer til modstandsdygtig træning med reproducerbare frø.                  |   1   |  D   |
| 10.2.2 | Bekræft, at detektionssystemet for adversariale eksempler udløser blokeringsadvarsler i produktionspipeline.                           |   2   | D/V  |
| 10.2.4 | Bekræft, at certifikatbeviser for certificeret robusthed eller intervalgrænsecertifikater dækker mindst de vigtigste kritiske klasser. |   3   |  V   |
| 10.2.5 | Bekræft, at regressions-tests bruger adaptive angreb for at sikre, at der ikke er noget målbar tab af robusthed.                       |   3   |  V   |

---

## 10.3 Afbødning af medlemsinference

Begræns evnen til at afgøre, om en post var i træningsdataene. Differential privacy og maskering af konfidensscore forbliver de mest effektive kendte forsvar.

|   #    | Description                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Bekræft, at per-forespørgsels entropiregulering eller temperaturskalering reducerer overmodige forudsigelser.  |   1   |  D   |
| 10.3.2 | Bekræft, at træningen anvender ε-bundet differentiabel privat optimering for følsomme datasæt.                 |   2   |  D   |
| 10.3.3 | Bekræft, at angrebssimulationer (shadow-model eller black-box) viser angrebs-AUC ≤ 0,60 på tilbageholdte data. |   2   |  V   |

---

## 10.4 Modstandsdygtighed over for modelinversion

Forhindre rekonstruktion af private attributter. Senere undersøgelser understreger outputtruncering og DP-garantier som praktiske forsvar.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Bekræft, at følsomme attributter aldrig bliver direkte vist; hvor det er nødvendigt, brug segmenter eller envejs transformationer. |   1   |  D   |
| 10.4.2 | Bekræft, at forespørgselsratebegrænsninger begrænser gentagne adaptive forespørgsler fra den samme enhed.                          |   1   | D/V  |
| 10.4.3 | Bekræft, at modellen er trænet med privatlivsbevarende støj.                                                                       |   2   |  D   |

---

## 10.5 Forsvar mod modeludtrækning

Registrer og afskær uautoriseret kloning. Vandmærkning og analyse af forespørgselsmønstre anbefales.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.5.1 | Sørg for, at inferens-gateways håndhæver globale og API-nøgle-specifikke hastighedsgrænser, der er tilpasset modellens memoreringstærskel. |   1   |  D   |
| 10.5.2 | Bekræft, at query-entropi og input-pluralitet-statistikker fodrer en automatiseret ekstraktionsdetektor.                                   |   2   | D/V  |
| 10.5.3 | Bekræft, at skrøbelige eller probabilistiske vandmærker kan bevises med p < 0,01 i ≤ 1.000 forespørgsler mod en mistænkt klon.             |   2   |  V   |
| 10.5.4 | Bekræft, at vandmærkenøgler og udløsningssæt gemmes i en hardware-sikkerhedsmodul og roteres årligt.                                       |   3   |  D   |
| 10.5.5 | Bekræft, at ekstraktions-alarm hændelser inkluderer problematiske forespørgsler og er integreret med hændelses-respons playbooks.          |   3   |  V   |

---

## 10.6 Påvisning af forgiftede data under inferenstid

Identificer og neutraliser tilbagelåste eller forgiftede input.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Verifier, at inputdataene passerer gennem en anomalidetektor (f.eks. STRIP, konsistensscoring) inden modelinferenz.    |   1   |  D   |
| 10.6.2 | Bekræft, at detektortærskler er justeret på rene/forurenede valideringssæt for at opnå mindre end 5% falske positiver. |   1   |  V   |
| 10.6.3 | Bekræft, at input, der er markeret som forgiftede, udløser blød blokering og menneskelig gennemgangsarbejdsgange.      |   2   |  D   |
| 10.6.4 | Bekræft, at detektorer bliver stresstestet med adaptive, triggerløse bagdørsangreb.                                    |   2   |  V   |
| 10.6.5 | Bekræft, at effektiviteten af detektionsmålinger logges og periodisk genvurderes med ny trusselsintelligens.           |   3   |  D   |

---

## 10.7 Dynamisk tilpasning af sikkerhedspolitik

Opdateringer af sikkerhedspolitikker i realtid baseret på trusselsinformation og adfærdsanalyse.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Bekræft, at sikkerhedspolitikker kan opdateres dynamisk uden genstart af agenten, samtidig med at politikversionens integritet opretholdes. |   1   | D/V  |
| 10.7.2 | Bekræft, at politikopdateringer er kryptografisk underskrevet af autoriseret sikkerhedspersonale og valideret før anvendelse.               |   2   | D/V  |
| 10.7.3 | Bekræft, at dynamiske politikændringer logges med fulde revisionsspor inklusive begrundelse, godkendelseskæder og tilbageførselsprocedurer. |   2   | D/V  |
| 10.7.4 | Bekræft, at adaptive sikkerhedsmekanismer justerer trusselsdetektionsfølsomheden baseret på risikokontekst og adfærdsmønstre.               |   3   | D/V  |
| 10.7.5 | Sørg for, at beslutninger om politikanpassning er forståelige og inkluderer spor af beviser til gennemgang af sikkerhedsteamet.             |   3   | D/V  |

---

## 10.8 Refleksionsbaseret sikkerhedsanalyse

Sikkerhedsvalidering gennem agentens selvrefleksion og metakognitiv analyse.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.8.1 | Bekræft, at agentens refleksionsmekanismer inkluderer en sikkerhedsorienteret selvvurdering af beslutninger og handlinger.                 |   1   | D/V  |
| 10.8.2 | Verificer, at refleksionsoutput valideres for at forhindre manipulation af selvvurderingsmekanismer ved hjælp af modstridende input.       |   2   | D/V  |
| 10.8.3 | Bekræft, at meta-kognitiv sikkerhedsanalyse identificerer potentiel bias, manipulation eller kompromis i agentens ræsonneringsprocesser.   |   2   | D/V  |
| 10.8.4 | Bekræft, at sikkerhedsadvarsler baseret på refleksion udløser forbedret overvågning og potentielle arbejdsgange for menneskelig indgriben. |   3   | D/V  |
| 10.8.5 | Bekræft, at kontinuerlig læring fra sikkerhedsreflektioner forbedrer trusselsdetektion uden at forringe legitim funktionalitet.            |   3   | D/V  |

---

## 10.9 Evolution og Selvforbedringssikkerhed

Sikkerhedskontroller for agentsystemer, der er i stand til selvmodifikation og evolution.

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Bekræft, at selvmodificeringsfunktioner er begrænset til udpegede sikre områder med formelle verifikationsgrænser.  |   1   | D/V  |
| 10.9.2 | Sørg for, at forslag til evolution gennemgår en vurdering af sikkerhedsmæssig indvirkning før implementering.       |   2   | D/V  |
| 10.9.3 | Bekræft, at selvforbedringsmekanismer inkluderer tilbageførselsfunktioner med integritetsverifikation.              |   2   | D/V  |
| 10.9.4 | Bekræft, at meta-læringssikkerhed forhindrer ondsindet manipulation af forbedringsalgoritmer.                       |   3   | D/V  |
| 10.9.5 | Bekræft, at rekursiv selvforbedring er begrænset af formelle sikkerhedskrav med matematiske beviser for konvergens. |   3   | D/V  |

---

### Referencer

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

