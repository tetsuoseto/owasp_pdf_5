# Appendix D: AI-ondersteunde veilige codering governance en verificatie

## Doelstelling

Dit hoofdstuk definieert basisorganisatorische controles voor het veilige en effectieve gebruik van AI-ondersteunde codeertools tijdens softwareontwikkeling, waarbij beveiliging en traceerbaarheid gedurende de volledige SDLC worden gewaarborgd.

---

## AD.1 AI-ondersteurde Secure-Coding Workflow

Integreer AI-tools in de veilige softwareontwikkelingscyclus (SSDLC) van de organisatie zonder de bestaande beveiligingsmaatregelen te verzwakken.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Controleer of een gedocumenteerde workflow beschrijft wanneer en hoe AI-tools code kunnen genereren, herstructureren of beoordelen.                                                                 |   1   | D/V  |
| AD.1.2 | Verifieer of de workflow overeenkomt met elke SSDLC-fase (ontwerp, implementatie, code review, testen, uitrol).                                                                                     |   2   |  D   |
| AD.1.3 | Controleer of metrieken (bijv. kwetsbaarheidsdichtheid, gemiddelde tijd tot detectie) worden verzameld voor door AI gegenereerde code en worden vergeleken met alleen menselijke referentiewaarden. |   3   | D/V  |

---

## AD.2 AI Toolkwalificatie & Dreigingsmodellering

Zorg ervoor dat AI-codeertools worden geëvalueerd op beveiligingsmogelijkheden, risico's en impact op de toeleveringsketen voordat ze worden geïmplementeerd.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Controleer of een dreigingsmodel voor elk AI‑hulpmiddel misbruik, modelinversie, datalekken en afhankelijkheidsketenrisico's identificeert.                                      |   1   | D/V  |
| AD.2.2 | Verifieer dat toolevaluaties statische/dynamische analyse van alle lokale componenten omvatten en een beoordeling van SaaS-eindpunten (TLS, authenticatie/autorisatie, logging). |   2   |  D   |
| AD.2.3 | Controleer of evaluaties volgens een erkaderd raamwerk worden uitgevoerd en opnieuw worden uitgevoerd na belangrijke versie-updates.                                             |   3   | D/V  |

---

## AD.3 Beheer van beveiligde prompts en context

Voorkom het lekken van geheimen, eigendomscode en persoonlijke gegevens bij het opstellen van prompts of contexten voor AI-modellen.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Controleer of schriftelijke richtlijnen het versturen van geheimen, inloggegevens of geclassificeerde gegevens in prompts verbieden.                                       |   1   | D/V  |
| AD.3.2 | Controleer of technische controles (client-side redactie, goedgekeurde contextfilters) automatisch gevoelige gegevens verwijderen.                                         |   2   |  D   |
| AD.3.3 | Controleer of prompts en reacties worden getokeniseerd, versleuteld tijdens overdracht en in opslag, en of de bewaartermijnen voldoen aan het gegevensclassificatiebeleid. |   3   | D/V  |

---

## AD.4 Validatie van door AI gegenereerde code

Detecteer en herstel kwetsbaarheden die door AI-uitvoer zijn geïntroduceerd voordat de code wordt samengevoegd of ingezet.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Controleer of AI‑gegenereerde code altijd aan een menselijke codebeoordeling wordt onderworpen.                                                                              |   1   | D/V  |
| AD.4.2 | Verifieer dat geautomatiseerde scanners (SAST/IAST/DAST) worden uitgevoerd bij elke pull request die AI‑gegenereerde code bevat en blokkeer merges bij kritieke bevindingen. |   2   |  D   |
| AD.4.3 | Verifieer dat differentiële fuzz testing of op eigenschappen gebaseerde tests beveiligingskritieke gedragingen aantonen (bijv. invoervalidatie, autorisatielogica).          |   3   | D/V  |

---

## AD.5 Uitlegbaarheid en Traceerbaarheid van Codevoorstellen

Geef auditors en ontwikkelaars inzicht in waarom een suggestie is gedaan en hoe deze zich heeft ontwikkeld.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Controleer of prompt/antwoordparen worden vastgelegd met commit-ID's.                                                                                                                          |   1   | D/V  |
| AD.5.2 | Controleer of ontwikkelaars modelverwijzingen (trainingsfragmenten, documentatie) kunnen tonen die een suggestie ondersteunen.                                                                 |   2   |  D   |
| AD.5.3 | Controleer of verklaringsrapporten worden opgeslagen met ontwerpstukken en worden vermeld in beveiligingsbeoordelingen, in overeenstemming met de traceerbaarheidsprincipes van ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Continue Feedback & Model Fijn-afstemming

Verbeter de beveiligingsprestaties van het model in de loop van de tijd en voorkom negatieve verschuiving.

|   #    | Description                                                                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Controleer of ontwikkelaars onveilige of niet-conforme suggesties kunnen markeren, en dat deze markeringen worden bijgehouden.                                                                                         |   1   | D/V  |
| AD.6.2 | Verifieer dat geaggregeerde feedback periodieke fijnafstemming of retrieval-augmented generatie informeert met gecontroleerde secure-coding corpora (bijv. OWASP Cheat Sheets).                                        |   2   |  D   |
| AD.6.3 | Verifieer dat een gesloten-lus evaluatieomgeving regressietests uitvoert na elke fine-tuning; beveiligingsmaatregelen moeten voldoen aan of beter zijn dan eerdere referentiepunten voordat implementatie plaatsvindt. |   3   | D/V  |

---

### Referenties

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

