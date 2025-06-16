# 11 Personvern og håndtering av personopplysninger

## Kontrollmål

Oppretthold strenge personvernforpliktelser gjennom hele AI-livssyklusen—innsamling, trening, inferens og hendelseshåndtering—slik at personopplysninger kun behandles med klart samtykke, minimal nødvendig omfang, påvisbar sletting og formelle personvernspesifikasjoner.

---

## 11.1 Anonymisering og dataminimering

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Bekreft at direkte og kvasi-identifikatorer er fjernet eller hashet.                                                                          |   1   | D/V  |
| 11.1.2 | Bekreft at automatiserte revisjoner måler k-anonymitet/l-mangfold og varsler når tersklene faller under policy.                               |   2   | D/V  |
| 11.1.3 | Bekreft at modellens funksjonsviktighetsrapporter viser at det ikke forekommer identifikatorlekkasje utover ε = 0,01 gjensidig informasjon.   |   2   |  V   |
| 11.1.4 | Verifiser at formelle bevis eller sertifisering av syntetiske data viser at risiko for re-identifisering er ≤ 0,05 selv under koblingsangrep. |   3   |  V   |

---

## 11.2 Retten til å bli glemt og håndheving av sletting

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Bekreft at forespørsler om sletting av datasubjekt blir videreført til rådatasett, kontrollpunkter, innebygde representasjoner, logger og sikkerhetskopier innenfor tjenestenivåavtaler på mindre enn 30 dager. |   1   | D/V  |
| 11.2.2 | Bekreft at "maskin-avlæring" rutiner fysisk trener på nytt eller approximativt fjerner data ved bruk av sertifiserte algoritmer for avlæring.                                                                   |   2   |  D   |
| 11.2.3 | Bekreft at evaluering med skygge-modell viser at glemte poster påvirker mindre enn 1 % av resultatene etter glemming.                                                                                           |   2   |  V   |
| 11.2.4 | Verifiser at sletting av hendelser logges uforanderlig og kan revideres av tilsynsmyndigheter.                                                                                                                  |   3   |  V   |

---

## 11.3 Differensialt personvernbeskyttelse

|   #    | Description                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.3.1 | Verifiser at personverntapsregnskapsdashbord varsler når kumulativ ε overskrider policygrenser.  |   2   | D/V  |
| 11.3.2 | Verifiser at black-box personvernsrevisjoner estimerer ε̂ innenfor 10 % av den oppgitte verdien. |   2   |  V   |
| 11.3.3 | Bekreft at formelle bevis dekker alle ettertreningsfinjusteringer og innebygginger.              |   3   |  V   |

---

## 11.4 Formålsbegrensning og beskyttelse mot omfangskrypning

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Verifiser at hvert datasett og modellkontrollpunkt har en maskinlesbar formålsmerkelapp som er i samsvar med det opprinnelige samtykket. |   1   |  D   |
| 11.4.2 | Bekreft at kjøreovervåkere oppdager forespørsler som er inkonsistente med den erklærte hensikten og utløser myk avvisning.               |   1   | D/V  |
| 11.4.3 | Bekreft at policy-as-code-gjerder blokkerer gjenutrulling av modeller til nye domener uten DPIA-gjennomgang.                             |   3   |  D   |
| 11.4.4 | Verifiser at formelle sporbarhetsbevis viser at hele livssyklusen til personopplysninger forblir innenfor det samtykkede omfanget.       |   3   |  V   |

---

## 11.5 Samtykkeadministrasjon og lovlig grunnlag for sporing

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Bekreft at en samtykke-administrasjonsplattform (CMP) registrerer opt-in-status, formål og oppbevaringsperiode per datasubjekt. |   1   | D/V  |
| 11.5.2 | Bekreft at API-er eksponerer samtykkebein; modeller må validere token-omfang før inferens.                                      |   2   |  D   |
| 11.5.3 | Bekreft at nektet eller trukket samtykke stopper behandlingsrørledninger innen 24 timer.                                        |   2   | D/V  |

---

## 11.6 Føderert læring med personvernkontroller

|   #    | Description                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Verifiser at klientoppdateringer benytter lokal differensial personvern-støytilsetning før aggregering. |   1   |  D   |
| 11.6.2 | Bekreft at treningsmetrikker er differensielt private og aldri avslører tap for enkeltklienter.         |   2   | D/V  |
| 11.6.3 | Bekreft at forgiftningsresistent aggregasjon (f.eks. Krum/Trimmed-Mean) er aktivert.                    |   2   |  V   |
| 11.6.4 | Bekreft at formelle beviser demonstrerer det totale ε-budsjettet med mindre enn 5 tap i nytteverdi.     |   3   |  V   |

---

### Referanser

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

