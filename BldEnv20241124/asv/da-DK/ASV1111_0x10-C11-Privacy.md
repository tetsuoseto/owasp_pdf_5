# 11 Beskyttelse af privatliv og håndtering af personlige data

## Kontrolmål

Oprethold strenge privatlivsgarantier gennem hele AI-livscyklussen—indsamling, træning, inferens og hændelsesrespons—så persondata kun behandles med klar samtykke, mindst nødvendigt omfang, påviselig sletning og formelle privatlivsgarantier.

---

## 11.1 Anonymisering og dataminimering

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Bekræft, at direkte og næsten-identifikatorer er fjernet eller hashet.                                                                             |   1   | D/V  |
| 11.1.2 | Bekræft, at automatiserede revisioner måler k-anonymitet/l-diversitet og giver alarm, når tærskler falder under politikken.                        |   2   | D/V  |
| 11.1.3 | Bekræft, at modelrapporterne om funktionsvigtighed viser, at der ikke er nogen lækage af identifikatorer ud over ε = 0,01 gensidig information.    |   2   |  V   |
| 11.1.4 | Bekræft, at formelle beviser eller certificering af syntetiske data viser, at risikoen for genidentifikation er ≤ 0,05, selv under koblingsangreb. |   3   |  V   |

---

## 11.2 Retten til at blive glemt og håndhævelse af sletning

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Sørg for, at sletningsanmodninger for dataemner spredes til rådatasæt, checkpoints, indlejringer, logfiler og sikkerhedskopier inden for serviceaftaler på under 30 dage. |   1   | D/V  |
| 11.2.2 | Bekræft, at "machine-unlearning"-rutiner fysisk genuddanner eller approximativt fjerner ved hjælp af certificerede unlearning-algoritmer.                                 |   2   |  D   |
| 11.2.3 | Bekræft, at evaluering med skygge-modeller beviser, at glemte poster påvirker mindre end 1 % af outputtene efter aflæring.                                                |   2   |  V   |
| 11.2.4 | Bekræft, at slettehændelser logges uforanderligt og er reviderbare for tilsynsmyndigheder.                                                                                |   3   |  V   |

---

## 11.3 Differentielt privatlivsbeskyttelse sikkerhedsforanstaltninger

|   #    | Description                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Bekræft, at dashboards for privatlivstabskonti advarer, når den kumulative ε overskrider politikgrænser. |   2   | D/V  |
| 11.3.2 | Bekræft, at black-box privatlivsrevisioner estimerer ε̂ inden for 10 % af den deklarerede værdi.         |   2   |  V   |
| 11.3.3 | Bekræft, at formelle beviser dækker alle eftertrænings-justeringer og indlejringer.                      |   3   |  V   |

---

## 11.4 Formålsbegrænsning og beskyttelse mod omfangsudvidelse

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Bekræft, at hvert datasæt og modelcheckpoint bærer en maskinlæselig formålsmærkning, der er i overensstemmelse med den oprindelige tilladelse. |   1   |  D   |
| 11.4.2 | Bekræft, at runtime-overvågning registrerer forespørgsler, der er inkonsistente med det erklærede formål, og udløser blød afvisning.           |   1   | D/V  |
| 11.4.3 | Bekræft, at politik-som-kode-gates blokerer for genudrulning af modeller til nye domæner uden DPIA-gennemgang.                                 |   3   |  D   |
| 11.4.4 | Bekræft, at formelle sporbarhedsdokumentation viser, at hver enkelt personlige data livscyklus forbliver inden for det samtykkede omfang.      |   3   |  V   |

---

## 11.5 Samtykkehåndtering og lovlig grundlag for sporing

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.5.1 | Bekræft, at en samtykkeadministrationsplatform (CMP) registrerer opt-in-status, formål og opbevaringsperiode pr. registreret person. |   1   | D/V  |
| 11.5.2 | Bekræft, at API'er eksponerer samtykketokens; modeller skal validere tokenets omfang før inferens.                                   |   2   |  D   |
| 11.5.3 | Bekræft, at afvist eller tilbagetrukket samtykke stopper behandlingspipelines inden for 24 timer.                                    |   2   | D/V  |

---

## 11.6 Fødereret læring med privatlivskontroller

|   #    | Description                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Bekræft, at klientopdateringer anvender lokal differential privacy-støjtilføjelse før aggregering. |   1   |  D   |
| 11.6.2 | Bekræft, at træningsmetrikker er differentielt private og aldrig afslører enkeltklienters tab.     |   2   | D/V  |
| 11.6.3 | Bekræft, at forgiftningsresistent aggregering (f.eks. Krum/Trimmed-Mean) er aktiveret.             |   2   |  V   |
| 11.6.4 | Bekræft, at formelle beviser demonstrerer det samlede ε-budget med mindre end 5 utilsigtet tab.    |   3   |  V   |

---

### Referencer

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

