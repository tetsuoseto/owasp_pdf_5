# C13 Mänsklig Övervakning, Ansvarsskyldighet och Styrning

## Kontrollmål

Detta kapitel ger krav för att upprätthålla mänsklig tillsyn och tydliga ansvarskedjor i AI-system, vilket säkerställer förklarbarhet, transparens och etiskt ansvarstagande genom hela AI-livscykeln.

---

## C13.1 Nödavstängnings- och Överstyrningsmekanismer

Tillhandahåll avstängnings- eller återställningsvägar när osäkert beteende hos AI-systemet observeras.

|   #    | Description                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Verifiera att en manuell avstängningsmekanism finns för att omedelbart stoppa AI-modellens inferens och utdata. |   1   | D/V  |
| 13.1.2 | Verifiera att åsidosättningskontroller endast är tillgängliga för behörig personal.                             |   1   |  D   |
| 13.1.3 | Verifiera att återställningsprocedurer kan återgå till tidigare modellversioner eller säkert läge.              |   3   | D/V  |
| 13.1.4 | Verifiera att överstyrningsmekanismer testas regelbundet.                                                       |   3   |  V   |

---

## C13.2 Beslutskontroller med mänsklig inblandning

Kräv mänskliga godkännanden när insatser överstiger fördefinierade risktrösklar.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Verifiera att hög-risk AI-beslut kräver uttryckligt mänskligt godkännande innan de genomförs.                                         |   1   | D/V  |
| 13.2.2 | Verifiera att risktrösklar är tydligt definierade och automatiskt utlöser granskningsarbetsflöden för människor.                      |   1   |  D   |
| 13.2.3 | Verifiera att tidskänsliga beslut har reservrutiner när mänskligt godkännande inte kan erhållas inom angivna tidsramar.               |   2   |  D   |
| 13.2.4 | Verifiera att eskaleringsprocedurer definierar tydliga behörighetsnivåer för olika beslutstyper eller riskkategorier, om tillämpligt. |   3   | D/V  |

---

## C13.3 Ansvarskedja och reviderbarhet

Logga operatörens åtgärder och modellens beslut.

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Verifiera att alla AI-systemsbeslut och mänskliga ingripanden loggas med tidsstämplar, användaridentiteter och beslutsmotiveringar. |   1   | D/V  |
| 13.3.2 | Verifiera att granskningsloggar inte kan manipuleras och innehåller mekanismer för integritetsverifiering.                          |   2   |  D   |

---

## C13.4 Förklarbara AI-tekniker

Ytfunktionsviktighet, motfaktorer och lokala förklaringar.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Verifiera att AI-system tillhandahåller grundläggande förklaringar för sina beslut i ett människoläsbart format.                                           |   1   | D/V  |
| 13.4.2 | Verifiera att förklaringskvaliteten valideras genom mänskliga utvärderingsstudier och mätningar.                                                           |   2   |  V   |
| 13.4.3 | Verifiera att viktningspoäng för funktioner eller attributmetoder (SHAP, LIME, etc.) finns tillgängliga för kritiska beslut.                               |   3   | D/V  |
| 13.4.4 | Verifiera att kontrafaktiska förklaringar visar hur ingångar kan modifieras för att ändra utfall, om det är tillämpligt för användningsfallet och domänen. |   3   |  V   |

---

## C13.5 Modellkort och användningsmeddelanden

Underhåll modellkort för avsedd användning, prestandamått och etiska överväganden.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Verifiera att modellkort dokumenterar avsedda användningsområden, begränsningar och kända felmoder.                                                                                           |   1   |  D   |
| 13.5.2 | Verifiera att prestandamått över olika tillämpliga användningsfall redovisas.                                                                                                                 |   1   | D/V  |
| 13.5.3 | Verifiera att etiska överväganden, partiskhetsbedömningar, rättviseutvärderingar, egenskaper hos träningsdata och kända begränsningar i träningsdata dokumenteras och uppdateras regelbundet. |   2   |  D   |
| 13.5.4 | Verifiera att modellkort är versionskontrollerade och underhålls under hela modellens livscykel med spårning av ändringar.                                                                    |   2   | D/V  |

---

## C13.6 Osäkerhetskvantifiering

Propagera förtroendescore eller entropimått i svaren.

|   #    | Description                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Verifiera att AI-system ger förtroendesiffror eller osäkerhetsmått med sina resultat.                      |   1   |  D   |
| 13.6.2 | Verifiera att osäkerhetströsklar utlöser ytterligare mänsklig granskning eller alternativa beslutsvägar.   |   2   | D/V  |
| 13.6.3 | Verifiera att metoder för osäkerhetskvantifiering är kalibrerade och validerade mot verkliga referensdata. |   2   |  V   |
| 13.6.4 | Verifiera att osäkerhetspropagering upprätthålls genom flerstegs-AI-arbetsflöden.                          |   3   | D/V  |

---

## C13.7 Användarorienterade transparensrapporter

Tillhandahåll periodiska upplysningar om incidenter, avvikelse och dataanvändning.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Verifiera att policyn för datanvändning och hanteringen av användarsamtycke tydligt kommuniceras till intressenter.       |   1   | D/V  |
| 13.7.2 | Verifiera att AI-påverkansbedömningar genomförs och att resultaten inkluderas i rapporteringen.                           |   2   | D/V  |
| 13.7.3 | Verifiera att transparensrapporter som publiceras regelbundet redovisar AI-incidenter och operativa mått i rimlig detalj. |   2   | D/V  |

### Referenser

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

