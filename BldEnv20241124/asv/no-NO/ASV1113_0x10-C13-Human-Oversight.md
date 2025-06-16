# C13 Menneskelig tilsyn, ansvarlighet og styring

## Kontrollmål

Dette kapitlet gir krav for å opprettholde menneskelig tilsyn og klare ansvarskjeder i KI-systemer, og sikrer forklarbarhet, åpenhet og etisk forvaltning gjennom hele KI-livssyklusen.

---

## C13.1 Kill-Switch og overstyringsmekanismer

Gi muligheter for nedstenging eller rulle tilbake når utrygt atferd fra AI-systemet observeres.

|   #    | Description                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Bekreft at det finnes en manuell nødstoppsmekanisme for å umiddelbart stoppe AI-modellens inferens og utdata.        |   1   | D/V  |
| 13.1.2 | Bekreft at overstyringskontroller kun er tilgjengelige for autorisert personell.                                     |   1   |  D   |
| 13.1.3 | Bekreft at tilbakestillingsprosedyrer kan gå tilbake til tidligere modellversjoner eller sikkerhetsmodusoperasjoner. |   3   | D/V  |
| 13.1.4 | Sørg for at overstyringsmekanismer testes regelmessig.                                                               |   3   |  V   |

---

## C13.2 Menneskelig-i-sløyfen beslutningskontrollpunkter

Kreve menneskelig godkjenning når innsatsen overskrider forhåndsdefinerte risikogrenseverdier.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Bekreft at høy-risiko AI-beslutninger krever eksplisitt menneskelig godkjenning før utførelse.                                      |   1   | D/V  |
| 13.2.2 | Bekreft at risikogrensene er tydelig definert og automatisk utløser arbeidsflyter for manuell gjennomgang.                          |   1   |  D   |
| 13.2.3 | Bekreft at tidskritiske beslutninger har reserveprosedyrer når menneskelig godkjenning ikke kan oppnås innen nødvendige tidsrammer. |   2   |  D   |
| 13.2.4 | Bekreft at eskaleringsprosedyrer definerer klare myndighetsnivåer for ulike beslutningstyper eller risikokategorier, hvis aktuelt.  |   3   | D/V  |

---

## C13.3 Ansvarskjede og reviderbarhet

Loggfør operatørhandlinger og modellbeslutninger.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Bekreft at alle AI-systembeslutninger og menneskelige inngrep loggføres med tidsstempler, brukeridentiteter og beslutningsgrunnlag. |   1   | D/V  |
| 13.3.2 | Sikre at revisjonslogger ikke kan manipuleres og inkluder mekanismer for integritetsverifisering.                                   |   2   |  D   |

---

## C13.4 Forklarbare AI-teknikker

Overflatefunksjons viktighet, motfaktiske eksempler og lokale forklaringer.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Bekreft at AI-systemer gir grunnleggende forklaringer på sine beslutninger i et menneskelig lesbart format.                                           |   1   | D/V  |
| 13.4.2 | Bekreft at forklaringskvaliteten er validert gjennom menneskelige evalueringsstudier og metrikker.                                                    |   2   |  V   |
| 13.4.3 | Bekreft at viktighetsvurderinger av funksjoner eller attributtmetoder (SHAP, LIME, osv.) er tilgjengelige for kritiske beslutninger.                  |   3   | D/V  |
| 13.4.4 | Bekreft at kontrafaktiske forklaringer viser hvordan input kan bli endret for å endre resultater, dersom det er relevant for bruksområdet og domenet. |   3   |  V   |

---

## C13.5 Modellkort og bruksavsløringer

Oppretthold modellkort for tiltenkt bruk, ytelsesmålinger og etiske vurderinger.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Bekreft at modellkort dokumenterer tiltenkte bruksområder, begrensninger og kjente feilmoduser.                                                                                              |   1   |  D   |
| 13.5.2 | Bekreft at ytelsesmål for forskjellige relevante bruksområder er oppgitt.                                                                                                                    |   1   | D/V  |
| 13.5.3 | Sørg for at etiske vurderinger, skjevhetsvurderinger, rettferdighetsvurderinger, egenskaper ved treningsdata og kjente begrensninger i treningsdata er dokumentert og oppdatert regelmessig. |   2   |  D   |
| 13.5.4 | Verifiser at modellkort er versjonskontrollert og vedlikeholdt gjennom hele modellens livssyklus med endringssporing.                                                                        |   2   | D/V  |

---

## C13.6 Usikkerhetskvantifisering

Propager konfidenspoeng eller entropimål i svarene.

|   #    | Description                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Bekreft at AI-systemer gir konfidenspoeng eller usikkerhetsmål med sine resultater.                         |   1   |  D   |
| 13.6.2 | Verifiser at usikkerhetsterskler utløser ekstra menneskelig gjennomgang eller alternative beslutningsveier. |   2   | D/V  |
| 13.6.3 | Verifiser at usikkerhetskvantifiseringsmetoder er kalibrert og validert mot grunnleggende sannhetsdata.     |   2   |  V   |
| 13.6.4 | Bekreft at usikkerhetspropagering opprettholdes gjennom flertrinns AI-arbeidsflyter.                        |   3   | D/V  |

---

## C13.7 Brukerorienterte rapporter om åpenhet

Gi periodiske opplysninger om hendelser, drift og databruk.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Bekreft at retningslinjer for databruk og praksiser for håndtering av bruker Samtykke er tydelig kommunisert til interessenter. |   1   | D/V  |
| 13.7.2 | Sørg for at AI-påvirkningsvurderinger gjennomføres og at resultatene inkluderes i rapporteringen.                               |   2   | D/V  |
| 13.7.3 | Bekreft at transparensrapporter som publiseres jevnlig, oppgir AI-hendelser og driftsmålinger i rimelig detalj.                 |   2   | D/V  |

### Referanser

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

