# 11 Sekretesskydd och hantering av personuppgifter

## Kontrollmål

Upprätthåll strikta integritetslöften genom hela AI-livscykeln—insamling, träning, inferens och incidenthantering—så att personuppgifter endast behandlas med tydligt samtycke, minsta nödvändiga omfattning, bevisbar radering och formella integritetsgarantier.

---

## 11.1 Anonymisering och dataminimering

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Verifiera att direkta och kvasi-identifikatorer tas bort eller hashas.                                                                            |   1   | D/V  |
| 11.1.2 | Verifiera att automatiska granskningar mäter k-anonymitet/l-mångfald och varnar när tröskelvärden sjunker under policyn.                          |   2   | D/V  |
| 11.1.3 | Verifiera att modellens rapporter om funktionsvikt visar att det inte förekommer någon identifieringsläcka bortom ε = 0,01 ömsesidig information. |   2   |  V   |
| 11.1.4 | Verifiera att formella bevis eller certifiering av syntetiska data visar att risken för återidentifiering är ≤ 0,05 även under länkattacker.      |   3   |  V   |

---

## 11.2 Rätten att bli glömd och tvångsutförande av radering

|   #    | Description                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.2.1 | Verifiera att raderingsförfrågningar för dataämnen sprids till råa dataset, checkpoints, inbäddningar, loggar och säkerhetskopior inom servicenivåavtal på mindre än 30 dagar. |   1   | D/V  |
| 11.2.2 | Verifiera att "maskin-avlärnings"-rutiner fysiskt tränar om eller approximativt tar bort med hjälp av certifierade avlärningsalgoritmer.                                       |   2   |  D   |
| 11.2.3 | Verifiera att skuggnadsmodellens utvärdering visar att bortglömda poster påverkar mindre än 1 % av resultaten efter avlärning.                                                 |   2   |  V   |
| 11.2.4 | Verifiera att raderingshändelser loggas oföränderligen och är granskbara för tillsynsmyndigheter.                                                                              |   3   |  V   |

---

## 11.3 Differensintegritetsskydd

|   #    | Description                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Verifiera att sekretess-förlustredovisningspaneler varnar när kumulativ ε överskrider policyns tröskelvärden. |   2   | D/V  |
| 11.3.2 | Verifiera att black-box integritetsrevisioner uppskattar ε̂ inom 10 % av det deklarerade värdet.              |   2   |  V   |
| 11.3.3 | Verifiera att formella bevis täcker alla efterutbildningsfinjusteringar och inbäddningar.                     |   3   |  V   |

---

## 11.4 Syftesbegränsning och skydd mot omfattningsglidning

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.4.1 | Verifiera att varje datamängd och modellkontrollpunkt bär en maskinläsbar syftestagg som är i linje med det ursprungliga samtycket.        |   1   |  D   |
| 11.4.2 | Verifiera att körningstillsyningsverktyg upptäcker förfrågningar som är inkonsekventa med det deklarerade syftet och utlöser mjukt avslag. |   1   | D/V  |
| 11.4.3 | Verifiera att policy-som-kod-portar blockerar omutplacering av modeller till nya domäner utan DPIA-granskning.                             |   3   |  D   |
| 11.4.4 | Verifiera att formella spårbarhetsbevis visar att varje personuppgifts livscykel förblir inom det samtyckta omfånget.                      |   3   |  V   |

---

## 11.5 Samtyckeshantering och laglig grund för spårning

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Verifiera att en samtyckeshanteringsplattform (CMP) registrerar opt-in-status, ändamål och lagringsperiod för varje registrerad person. |   1   | D/V  |
| 11.5.2 | Verifiera att API:er exponerar samtyckestoken; modeller måste validera tokenskopet innan inferens.                                      |   2   |  D   |
| 11.5.3 | Verifiera att nekad eller återkallad samtycke stoppar behandlingskedjor inom 24 timmar.                                                 |   2   | D/V  |

---

## 11.6 Federerad inlärning med integritetskontroller

|   #    | Description                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Verifiera att klientuppdateringar använder lokal differentialintegritet genom att lägga till brus innan aggregering. |   1   |  D   |
| 11.6.2 | Verifiera att träningsmetrik är differentiellt privata och aldrig avslöjar enskild klients förlust.                  |   2   | D/V  |
| 11.6.3 | Verifiera att förgiftningstålig aggregering (t.ex. Krum/Trimmed-Mean) är aktiverad.                                  |   2   |  V   |
| 11.6.4 | Verifiera att formella bevis visar en total ε-budget med mindre än 5 enheters förlust av nytta.                      |   3   |  V   |

---

### Referenser

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

