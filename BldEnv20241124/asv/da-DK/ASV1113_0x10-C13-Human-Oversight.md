# C13 Menneskelig Overvågning, Ansvarlighed og Styring

## Kontrolmål

Dette kapitel indeholder krav til opretholdelse af menneskelig overvågning og klare ansvarskæder i AI-systemer, hvilket sikrer forklarbarhed, gennemsigtighed og etisk forvaltning gennem hele AI-livscyklussen.

---

## C13.1 Nødstop- og tilsidesættelsesmekanismer

Giv nedluknings- eller tilbageførselsmuligheder, når utryg adfærd i AI-systemet observeres.

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.1.1 | Bekræft, at der findes en manuel nødstopmekanisme, som øjeblikkeligt kan stoppe AI-modelinferens og -udgange.            |   1   | D/V  |
| 13.1.2 | Bekræft, at overstyringskontroller kun er tilgængelige for autoriseret personale.                                        |   1   |  D   |
| 13.1.3 | Bekræft, at rollback-procedurer kan vende tilbage til tidligere modelversioner eller til sikkerhedstilstandsoperationer. |   3   | D/V  |
| 13.1.4 | Sørg for, at overskrivningsmekanismer testes regelmæssigt.                                                               |   3   |  V   |

---

## C13.2 Menneskelig i kredsløbet beslutningskontrolpunkter

Kræv menneskelig godkendelse, når indsatsen overstiger foruddefinerede risikogrænser.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Bekræft, at højrisiko AI-beslutninger kræver eksplicit menneskelig godkendelse før udførelse.                                                |   1   | D/V  |
| 13.2.2 | Sørg for, at risikogrænser er klart defineret og automatisk udløser arbejdsgange for menneskelig gennemgang.                                 |   1   |  D   |
| 13.2.3 | Bekræft, at tidskritiske beslutninger har nødprocedurer, hvis menneskelig godkendelse ikke kan opnås inden for de krævede tidsrammer.        |   2   |  D   |
| 13.2.4 | Bekræft, at eskaleringsprocedurer definerer klare myndighedsniveauer for forskellige beslutningstyper eller risikokategorier, hvis relevant. |   3   | D/V  |

---

## C13.3 Kæde af ansvar og reviderbarhed

Logfør operatørhandlinger og modelbeslutninger.

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.3.1 | Bekræft, at alle AI-systembeslutninger og menneskelige indgreb logges med tidsstempler, brugeridentiteter og beslutningsbegrundelse. |   1   | D/V  |
| 13.3.2 | Bekræft, at revisionslogfiler ikke kan manipuleres, og inkluder mekanismer til integritetsverifikation.                              |   2   |  D   |

---

## C13.4 Forklarlige AI-teknikker

Vigtigheden af overfladefunktioner, kontrafaktuelle eksempler og lokale forklaringer.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.4.1 | Bekræft, at AI-systemer giver grundlæggende forklaringer på deres beslutninger i menneskeligt læsbart format.                                          |   1   | D/V  |
| 13.4.2 | Verificer, at forklaringskvaliteten er valideret gennem menneskelige evalueringsstudier og metrikker.                                                  |   2   |  V   |
| 13.4.3 | Bekræft, at vigtighedsscorer for funktioner eller attributmetoder (SHAP, LIME osv.) er tilgængelige for kritiske beslutninger.                         |   3   | D/V  |
| 13.4.4 | Bekræft, at kontrafaktiske forklaringer viser, hvordan input kunne ændres for at ændre resultater, hvis det er relevant for brugstilfældet og domænet. |   3   |  V   |

---

## C13.5 Modelkort og brugsoplysninger

Vedligehold modelkort for tilsigtet brug, præstationsmålinger og etiske overvejelser.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Bekræft, at modelkort dokumenterer tilsigtede anvendelsestilfælde, begrænsninger og kendte fejlfunktioner.                                                                                              |   1   |  D   |
| 13.5.2 | Bekræft, at præstationsmålinger på tværs af forskellige relevante anvendelsestilfælde er oplyst.                                                                                                        |   1   | D/V  |
| 13.5.3 | Bekræft, at etiske overvejelser, vurderinger af bias, evalueringer af retfærdighed, karakteristika for træningsdata og kendte begrænsninger ved træningsdata er dokumenteret og opdateret regelmæssigt. |   2   |  D   |
| 13.5.4 | Bekræft, at modelkort er versionsstyrede og vedligeholdes gennem hele modellens livscyklus med ændringssporing.                                                                                         |   2   | D/V  |

---

## C13.6 Usikkerhedskvantificering

Propager konfidensscore eller entropimål i svar.

|   #    | Description                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.6.1 | Bekræft, at AI-systemer leverer konfidensscore eller usikkerhedsmål sammen med deres output.                 |   1   |  D   |
| 13.6.2 | Bekræft, at usikkerhedstærskler udløser yderligere menneskelig gennemgang eller alternative beslutningsveje. |   2   | D/V  |
| 13.6.3 | Bekræft, at metoder til usikkerhedskvantificering er kalibrerede og validerede mod faktiske data.            |   2   |  V   |
| 13.6.4 | Sørg for, at usikkerhedspropagering opretholdes gennem flertrins AI-arbejdsgange.                            |   3   | D/V  |

---

## C13.7 Brugerrettede gennemsigtighedsrapporter

Giv periodiske oplysninger om hændelser, drift og dataanvendelse.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Sørg for, at politikker for databrug og praksis for styring af brugerens samtykke er klart kommunikeret til interessenter.                          |   1   | D/V  |
| 13.7.2 | Bekræft, at AI-påvirkningsvurderinger udføres, og at resultaterne indgår i rapporteringen.                                                          |   2   | D/V  |
| 13.7.3 | Bekræft, at gennemsigtighedsrapporter, der offentliggøres regelmæssigt, afslører AI-hændelser og operationelle målinger i rimelig detaljeringsgrad. |   2   | D/V  |

### Referencer

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

