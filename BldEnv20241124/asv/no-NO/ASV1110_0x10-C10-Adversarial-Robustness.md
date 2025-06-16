# 10 Motstandsdyktighet mot angrep og personvernsforsvar

## Kontrollmål

Sørg for at AI-modeller forblir pålitelige, personvernbevarende og motstandsdyktige mot misbruk når de utsettes for unnvikelses-, inferens-, utvinnings- eller forgiftningsangrep.

---

## 10.1 Modelljustering og sikkerhet

Beskytte mot skadelige eller policy-bruddende utdata.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Bekreft at en testpakke for justering (red-team-prompt, jailbreak-prober, uakseptert innhold) er versjonskontrollert og kjøres ved hver modellutgivelse. |   1   | D/V  |
| 10.1.2 | Bekreft at nektelse og sikre fullføringsvern er håndhevet.                                                                                               |   1   |  D   |
| 10.1.3 | Bekreft at en automatisert evaluator måler andelen skadelig innhold og varsler om tilbakegang utover en satt terskel.                                    |   2   | D/V  |
| 10.1.4 | Verifiser at mot-omgåelsesopplæring er dokumentert og reproduserbar.                                                                                     |   2   |  D   |
| 10.1.5 | Verifiser at formelle bevis for etterlevelse av policy eller sertifisert overvåking dekker kritiske domener.                                             |   3   |  V   |

---

## 10.2 Motstandsdyktighet mot fiendtlige eksempler

Øk motstanden mot manipulerte inndata. Robust adversarial-trening og benchmark-poenggivning er dagens beste praksis.

|   #    | Description                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Bekreft at prosjektlagre inkluderer konfigurasjoner for adversarial trening med reproduserbare frø.                  |   1   |  D   |
| 10.2.2 | Bekreft at oppdagelse av motstandereksempler utløser blokkeringvarsler i produksjonsrørledninger.                    |   2   | D/V  |
| 10.2.4 | Verifiser at sertifiserte robusthetsbevis eller intervallgrense-sertifikater dekker minst de mest kritiske klassene. |   3   |  V   |
| 10.2.5 | Bekreft at regresjonstester bruker adaptive angrep for å bekrefte at det ikke er noe målbar robusthetstap.           |   3   |  V   |

---

## 10.3 Tiltak for å motvirke medlemskapsinformasjonsangrep

Begrens muligheten til å avgjøre om en post var i treningsdataene. Differensiell personvern og maskering av konfidensscore forblir de mest effektive kjente forsvar.

|   #    | Description                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Bekreft at entropiregulering per spørring eller temperaturskalering reduserer overkonfident prediksjoner.  |   1   |  D   |
| 10.3.2 | Bekreft at treningen bruker ε-avgrenset differensielt privat optimalisering for sensitive datasett.        |   2   |  D   |
| 10.3.3 | Bekreft at angrepssimuleringer (skygge-modell eller svart-boks) viser angreps-AUC ≤ 0,60 på holdt-ut data. |   2   |  V   |

---

## 10.4 Motstand mot modellinversjon

Forhindre rekonstruksjon av private attributter. Nyere undersøkelser fremhever avkorting av utdata og DP-garantier som praktiske forsvar.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Bekreft at sensitive attributter aldri blir direkte vist; der det er nødvendig, bruk grupper eller enveistransformasjoner. |   1   |  D   |
| 10.4.2 | Bekreft at forespørselsrategens begrensninger demper gjentatte adaptive forespørsler fra samme hovedbruker.                |   1   | D/V  |
| 10.4.3 | Bekreft at modellen er trent med personvernbeskyttende støy.                                                               |   2   |  D   |

---

## 10.5 Modellutvinningsforsvar

Oppdag og avskrekk uautorisert kloning. Vannmerking og analyse av forespørselmønstre anbefales.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Bekreft at inferens-gatewayer håndhever globale og per-API-nøkkel hastighetsbegrensninger tilpasset modellens memoriseringsgrense. |   1   |  D   |
| 10.5.2 | Verifiser at statistikkene for spørrings-entropi og input-mangfoldighet forsyner en automatisert utvinningsdetektor.               |   2   | D/V  |
| 10.5.3 | Verifiser at skjøre eller sannsynlighetsbaserte vannmerker kan bevises med p < 0,01 i ≤ 1 000 forespørsler mot en mistenkt klone.  |   2   |  V   |
| 10.5.4 | Bekreft at vannmerke-nøkler og trigger-sett lagres i en hardware-sikkerhetsmodul og roteres årlig.                                 |   3   |  D   |
| 10.5.5 | Bekreft at extraction-alert-hendelser inkluderer krenkende forespørsler og er integrert med hendelseshåndteringsprosedyrer.        |   3   |  V   |

---

## 10.6 Deteksjon av forgiftede data ved inferenstidspunktet

Identifisere og nøytralisere bakdør- eller forgiftede innganger.

|   #    | Description                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Verifiser at inndata går gjennom en anomali-detektor (f.eks. STRIP, konsistens-scoring) før modellinferens.             |   1   |  D   |
| 10.6.2 | Bekreft at detektorterskler er justert på rene/forurensede valideringssett for å oppnå mindre enn 5 % falske positiver. |   1   |  V   |
| 10.6.3 | Bekreft at innganger merket som forgiftet utløser myk-blokkering og arbeidsflyter for menneskelig gjennomgang.          |   2   |  D   |
| 10.6.4 | Bekreft at detektorer er stresstestet med adaptive, utløserløse bakdør-angrep.                                          |   2   |  V   |
| 10.6.5 | Bekreft at deteksjonseffektivitetsmålinger loggføres og periodisk revurderes med oppdatert trusselinformasjon.          |   3   |  D   |

---

## 10.7 Dynamisk tilpasning av sikkerhetspolicy

Sanntidsoppdateringer av sikkerhetspolicy basert på trusselintelligens og atferdsanalyse.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Bekreft at sikkerhetspolicyer kan oppdateres dynamisk uten at agenten må startes på nytt, samtidig som man opprettholder integriteten til policyversjonen. |   1   | D/V  |
| 10.7.2 | Bekreft at policyoppdateringer er kryptografisk signert av autorisert sikkerhetspersonell og validert før de implementeres.                                |   2   | D/V  |
| 10.7.3 | Bekreft at dynamiske policyendringer logges med fullstendige revisjonsspor, inkludert begrunnelse, godkjenningskjeder og tilbakeføringsprosedyrer.         |   2   | D/V  |
| 10.7.4 | Bekreft at adaptive sikkerhetsmekanismer justerer trusseldeteksjonsfølsomhet basert på risikokontekst og atferdsmønstre.                                   |   3   | D/V  |
| 10.7.5 | Sørg for at beslutninger om tilpasning av policyer er forklarbare og inkluderer bevismateriale for gjennomgang av sikkerhetsteamet.                        |   3   | D/V  |

---

## 10.8 Refleksjonsbasert sikkerhetsanalyse

Sikkerhetsvalidering gjennom agentens selvrefleksjon og metakognitiv analyse.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Bekreft at agentens refleksjonsmekanismer inkluderer sikkerhetsfokusert selvvurdering av beslutninger og handlinger.                                    |   1   | D/V  |
| 10.8.2 | Sørg for at refleksjonsutdata er validert for å forhindre manipulering av selvvurderingsmekanismer av fiendtlige innganger.                             |   2   | D/V  |
| 10.8.3 | Verifiser at meta-kognitiv sikkerhetsanalyse identifiserer potensielle skjevheter, manipulering eller kompromittering i agentenes resonnementprosesser. |   2   | D/V  |
| 10.8.4 | Bekreft at sikkerhetsadvarsler basert på refleksjon utløser forbedret overvåking og potensielle arbeidsflyter for menneskelig inngripen.                |   3   | D/V  |
| 10.8.5 | Bekreft at kontinuerlig læring fra sikkerhetsrefleksjoner forbedrer trusseloppdagelse uten å svekke legitim funksjonalitet.                             |   3   | D/V  |

---

## 10.9 Evolusjon og Selvforbedringssikkerhet

Sikkerhetskontroller for agentsystemer som er i stand til selvmodifikasjon og evolusjon.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Bekreft at selvmodifikasjonskapasiteter er begrenset til utpekte sikre områder med formelle verifikasjonsgrenser.          |   1   | D/V  |
| 10.9.2 | Bekreft at evolusjonsforslag gjennomgår sikkerhetspåvirkningsvurdering før implementering.                                 |   2   | D/V  |
| 10.9.3 | Bekreft at selvforbedringsmekanismer inkluderer tilbakeføringsmuligheter med integritetsverifisering.                      |   2   | D/V  |
| 10.9.4 | Bekreft at meta-læringssikkerhet forhindrer fiendtlig manipulering av forbedringsalgoritmer.                               |   3   | D/V  |
| 10.9.5 | Verifiser at rekursiv selvforbedring er begrenset av formelle sikkerhetsbegrensninger med matematiske bevis på konvergens. |   3   | D/V  |

---

### Referanser

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

