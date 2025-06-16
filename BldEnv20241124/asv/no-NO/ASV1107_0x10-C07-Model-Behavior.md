# C7 Modellatferd, Utgangskontroll og Sikkerhetsgaranti

## Kontrollmål

Modellutganger må være strukturerte, pålitelige, sikre, forklarbare og kontinuerlig overvåket i produksjon. Dette reduserer hallusinasjoner, personvernsbrudd, skadelig innhold og ukontrollerte handlinger, samtidig som det øker brukerens tillit og overholdelse av regelverk.

---

## C7.1 Håndheving av utdataformat

Strenge skjemaer, begrenset dekoding og etterfølgende validering stopper feilaktig eller ondsinnet innhold før det sprer seg.

|   #   | Description                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Bekreft at responsskjemaer (f.eks. JSON Schema) er angitt i systemprompten, og at hvert svar automatisk valideres; svar som ikke samsvarer, utløser reparasjon eller avvisning. |   1   | D/V  |
| 7.1.2 | Bekreft at begrenset dekoding (stopp-tegn, regex, maks-tokener) er aktivert for å forhindre overløp eller sidekanaler for prompt-injeksjon.                                     |   1   | D/V  |
| 7.1.3 | Sørg for at nedstrømskomponenter behandler utdata som ikke-pålitelig og validerer dem mot skjemaer eller injeksjonssikre deserialisatorer.                                      |   2   | D/V  |
| 7.1.4 | Bekreft at feilaktige utdatahendelser blir loggført, begrenset etter hastighet, og gjort synlige for overvåking.                                                                |   3   |  V   |

---

## C7.2 Hallusinasjonsdeteksjon og -redusering

Usikkerhetsestimering og tilbaketrekningsstrategier begrenser fabrikkerte svar.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Verifiser at token-nivå log-sannsynligheter, ensemble selv-konsistens, eller finjusterte hallusinasjonsdetektorer tilordner en konfidensscore til hvert svar.               |   1   | D/V  |
| 7.2.2 | Bekreft at svar under en konfigurerbar konfidensgrense utløser tilbakefall-arbeidsflyter (f.eks. hentingsforsterket generering, sekundær modell eller manuell gjennomgang). |   1   | D/V  |
| 7.2.3 | Verifiser at hallusinasjonshendelser er merket med rotårsaksmetadata og føres inn i post-mortem- og finjusteringspipelines.                                                 |   2   | D/V  |
| 7.2.4 | Sørg for at terskler og detektorer kalibreres på nytt etter større modell- eller kunnskapsbaseoppdateringer.                                                                |   3   | D/V  |
| 7.2.5 | Verifiser at dashbordvisualiseringer sporer hallusinasjonsrater.                                                                                                            |   3   |  V   |

---

## C7.3 Utdata Sikkerhets- og Personvernfiltrering

Retningslinjefiltre og redteam-dekning beskytter brukere og konfidensielle data.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.3.1 | Verifiser at klassifisører før og etter generering blokkerer hat, trakassering, selvskading, ekstremistisk og seksuelt eksplisitt innhold i samsvar med retningslinjene. |   1   | D/V  |
| 7.3.2 | Bekreft at detektering av PII/PCI og automatisk sensurering kjøres på hvert svar; brudd utløser en personvernhendelse.                                                   |   1   | D/V  |
| 7.3.3 | Verifiser at konfidensialitetsetiketter (f.eks. forretningshemmeligheter) følger med på tvers av modaliteter for å forhindre lekkasje i tekst, bilder eller kode.        |   2   |  D   |
| 7.3.4 | Bekreft at forsøk på å omgå filteret eller klassifiseringer med høy risiko krever sekundær godkjenning eller brukerre-autentisering.                                     |   3   | D/V  |
| 7.3.5 | Bekreft at filtreringsterskler gjenspeiler juridiske jurisdiksjoner og konteksten til brukerens alder/rolle.                                                             |   3   | D/V  |

---

## C7.4 Begrensning av utdata og handlinger

Grenseverdier for rate og godkjenningsporter forhindrer misbruk og overdreven autonomi.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Bekreft at kvoter per bruker og per API-nøkkel begrenser forespørsler, tokens og kostnader med eksponentiell tilbake-off ved 429-feil.                |   1   |  D   |
| 7.4.2 | Bekreft at privilegerte handlinger (filskriving, kodekjøring, nettverksanrop) krever policy-basert godkjenning eller menneskelig involvering.         |   1   | D/V  |
| 7.4.3 | Bekreft at kryssmodal konsistenssjekker sikrer at bilder, kode og tekst generert for samme forespørsel ikke kan brukes til å smugle skadelig innhold. |   2   | D/V  |
| 7.4.4 | Bekreft at dybden for agentdelegasjon, rekursjonsgrenser og tillatte verktøylister er eksplisitt konfigurert.                                         |   2   |  D   |
| 7.4.5 | Bekreft at overskridelse av grenser utløser strukturerte sikkerhetshendelser for SIEM-inntak.                                                         |   3   |  V   |

---

## C7.5 Forklarbarhet av utdata

Transparente signaler forbedrer brukerens tillit og intern feilsøking.

|   #   | Description                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Bekreft at brukervendte tillitsresultater eller korte resonnementssammendrag vises når risikovurderingen anser det som passende. |   2   | D/V  |
| 7.5.2 | Bekreft at genererte forklaringer unngår å avsløre sensitive systemkommandoer eller proprietære data.                            |   2   | D/V  |
| 7.5.3 | Bekreft at systemet fanger opp token-nivå log-sannsynligheter eller oppmerksomhetskart og lagrer dem for autorisert inspeksjon.  |   3   |  D   |
| 7.5.4 | Verifiser at forklaringsartefakter er versjonskontrollert sammen med modellutgivelser for revisjonssporbarhet.                   |   3   |  V   |

---

## C7.6 Overvåkingsintegrasjon

Sanntidsovervåking lukker sløyfen mellom utvikling og produksjon.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Bekreft at måleparametere (skjemaavvik, hallusinasjonsrate, toksisitet, lekkasjer av personlig identifiserbar informasjon, latenstid, kostnader) strømmer til en sentral overvåkingsplattform. |   1   |  D   |
| 7.6.2 | Bekreft at varslingsterskler er definert for hver sikkerhetsmåling, med eskaleringsveier for vaktpersonell.                                                                                    |   1   |  V   |
| 7.6.3 | Verifiser at dashbord korrelerer utdataavvik med modell/versjon, funksjonsflagg og endringer i oppstrømsdata.                                                                                  |   2   |  V   |
| 7.6.4 | Verifiser at overvåkningsdata føres tilbake til omtrening, finjustering eller oppdatering av regler innenfor en dokumentert MLOps-arbeidsflyt.                                                 |   2   | D/V  |
| 7.6.5 | Sørg for at overvåkingspipelines er penetrasjonstestet og tilgangskontrollert for å unngå lekkasje av sensitive logger.                                                                        |   3   |  V   |

---

## 7.7 Generative mediesikkerhetstiltak

Sikre at AI-systemer ikke genererer ulovlig, skadelig eller uautorisert medieinnhold ved å håndheve policybegrensninger, outputvalidering og sporbarhet.

|   #   | Description                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Bekreft at systeminstruksjoner og brukerinstruksjoner uttrykkelig forbyr generering av ulovlig, skadelig eller ikke-samtykkende deepfake-media (for eksempel bilde, video, lyd).          |   1   | D/V  |
| 7.7.2 | Bekreft at forespørsler blir filtrert for forsøk på å generere etterligninger, seksuelt eksplisitte deepfakes eller medier som viser ekte personer uten samtykke.                         |   2   | D/V  |
| 7.7.3 | Bekreft at systemet bruker perseptuell hashing, vannmerkingsdeteksjon eller fingeravtrykkteknologi for å forhindre uautorisert reproduksjon av opphavsrettslig beskyttet materiale.       |   2   |  V   |
| 7.7.4 | Bekreft at alt generert materiale er kryptografisk signert, merket med vannmerke eller inneholder innbakt manipulasjonssikker opphavsmetadata for sporbart oppfølging.                    |   3   | D/V  |
| 7.7.5 | Verifiser at omgåelsesforsøk (f.eks. promptforvrengning, slang, antagonistisk formulering) oppdages, logges og hastighetsbegrenses; gjentatt misbruk rapporteres til overvåkingssystemer. |   3   |  V   |

## Referanser

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

