# Bilaga D: AI-assisterad styrning och verifiering av säker kodning

## Mål

Detta kapitel definierar grundläggande organisatoriska kontroller för säker och effektiv användning av AI-assisterade kodningsverktyg under programvaruutveckling, vilket säkerställer säkerhet och spårbarhet genom hela SDLC.

---

## AD.1 AI-assisterat säkert kodningsarbetsflöde

Integrera AI-verktyg i organisationens säkra programvaruutvecklingslivscykel (SSDLC) utan att försvaga befintliga säkerhetskontroller.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Verifiera att en dokumenterad arbetsflöde beskriver när och hur AI-verktyg kan generera, refaktorera eller granska kod.                                                   |   1   | D/V  |
| AD.1.2 | Verifiera att arbetsflödet motsvarar varje SSDLC-fas (design, implementering, kodgranskning, testning, distribution).                                                     |   2   |  D   |
| AD.1.3 | Verifiera att mått (t.ex. sårbarhetstäthet, genomsnittlig tid till upptäckt) samlas in för AI-genererad kod och jämförs med baslinjer som enbart inkluderar mänsklig kod. |   3   | D/V  |

---

## AD.2 AI-verktygskvalificering och hotmodellering

Se till att AI-kodningsverktyg utvärderas för säkerhetsförmågor, risker och påverkan på leverantörskedjan innan de tas i bruk.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Verifiera att en hotmodell för varje AI-verktyg identifierar missbruk, modellinversion, dataläckage och risker i beroendekedjan.                                                      |   1   | D/V  |
| AD.2.2 | Verifiera att verktygsevalueringar inkluderar statisk/dynamisk analys av eventuella lokala komponenter och bedömning av SaaS-endpunkter (TLS, autentisering/auktorisation, loggning). |   2   |  D   |
| AD.2.3 | Verifiera att utvärderingar följer en erkänd ram och utförs på nytt efter större versionsändringar.                                                                                   |   3   | D/V  |

---

## AD.3 Säker hantering av prompt och kontext

Förhindra läckage av hemligheter, proprietär kod och personuppgifter när du konstruerar prompts eller kontexter för AI-modeller.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Verifiera att skriftlig vägledning förbjuder att skicka hemligheter, autentiseringsuppgifter eller klassificerad data i prompts.             |   1   | D/V  |
| AD.3.2 | Verifiera att tekniska kontroller (klientbaserad redigering, godkända kontextfilter) automatiskt tar bort känsliga artefakter.               |   2   |  D   |
| AD.3.3 | Verifiera att promptar och svar tokeniseras, krypteras under överföring och i vila, och att lagringstider följer dataklassificeringspolicyn. |   3   | D/V  |

---

## AD.4 Validering av AI-genererad kod

Upptäck och åtgärda sårbarheter som introducerats av AI-resultat innan koden slås samman eller deployeras.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Verifiera att AI-genererad kod alltid granskas av en mänsklig kodgranskare.                                                                                    |   1   | D/V  |
| AD.4.2 | Verifiera att automatiska skannrar (SAST/IAST/DAST) körs på varje pull-begäran som innehåller AI-genererad kod och blockera sammanslagning vid kritiska fynd.  |   2   |  D   |
| AD.4.3 | Verifiera att differential fuzz-testning eller egenskapsbaserade tester bevisar säkerhetskritiska beteenden (t.ex. inmatningsvalidering, auktoriseringslogik). |   3   | D/V  |

---

## AD.5 Förklarbarhet och Spårbarhet av Kodförslag

Ge revisorer och utvecklare insikt i varför ett förslag gjordes och hur det utvecklades.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.5.1 | Verifiera att prompt-/svarpar loggas med commit-ID:n.                                                                                                                    |   1   | D/V  |
| AD.5.2 | Verifiera att utvecklare kan visa modellciteringar (träningsutdrag, dokumentation) som stöder ett förslag.                                                               |   2   |  D   |
| AD.5.3 | Verifiera att förklaringsrapporter lagras tillsammans med designartefakter och refereras i säkerhetsgranskningar, vilket uppfyller ISO/IEC 42001:s spårbarhetsprinciper. |   3   | D/V  |

---

## AD.6 Kontinuerlig återkoppling och finjustering av modellen

Förbättra modellens säkerhetsprestanda över tid samtidigt som negativ drift förhindras.

|   #    | Description                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Verifiera att utvecklare kan markera osäkra eller icke-kompatibla förslag, och att markeringarna spåras.                                                                                |   1   | D/V  |
| AD.6.2 | Verifiera att samlad återkoppling används för periodisk finjustering eller återhämtningsförstärkt generering med granskade säker kodningskorpusar (t.ex. OWASP Cheat Sheets).           |   2   |  D   |
| AD.6.3 | Verifiera att ett sluten-loop utvärderingssystem kör regressionstester efter varje finjustering; säkerhetsmetrik måste uppfylla eller överstiga tidigare baslinjer innan driftsättning. |   3   | D/V  |

---

### Referenser

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

