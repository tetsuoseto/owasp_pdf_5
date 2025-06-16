# C13 Menselijk Toezicht, Verantwoording & Bestuur

## Beheersingsdoelstelling

Dit hoofdstuk biedt vereisten voor het behouden van menselijke toezicht en duidelijke verantwoordingsketens in AI-systemen, waarbij verklaarbaarheid, transparantie en ethisch beheer gedurende de gehele AI-levenscyclus worden gewaarborgd.

---

## C13.1 Kill-Switch & Override Mechanismen

Bied uitschakel- of terugdraaimogelijkheden wanneer onveilig gedrag van het AI-systeem wordt waargenomen.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Controleer of er een handmatige noodstopschakelaar bestaat om de inferentie en output van het AI-model onmiddellijk te stoppen. |   1   | D/V  |
| 13.1.2 | Controleer of de override-bedieningen alleen toegankelijk zijn voor bevoegd personeel.                                          |   1   |  D   |
| 13.1.3 | Controleer of rollback-procedures kunnen terugkeren naar eerdere modelversies of veilige-modusoperaties.                        |   3   | D/V  |
| 13.1.4 | Controleer regelmatig of de override-mechanismen worden getest.                                                                 |   3   |  V   |

---

## C13.2 Beslissingscontrolepunten met menselijke tussenkomst

Vereis menselijke goedkeuringen wanneer de inzet vooraf bepaalde risicodrempels overschrijdt.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Zorg ervoor dat AI-beslissingen met hoog risico expliciete menselijke goedkeuring vereisen voordat ze worden uitgevoerd.                                         |   1   | D/V  |
| 13.2.2 | Controleer of risicodrempels duidelijk zijn gedefinieerd en automatisch beoordelingsworkflows door mensen activeren.                                             |   1   |  D   |
| 13.2.3 | Controleer of er noodprocedures zijn voor tijdgevoelige beslissingen wanneer menselijke goedkeuring niet binnen de vereiste tijdsbestekken kan worden verkregen. |   2   |  D   |
| 13.2.4 | Controleer of escalatieprocedures duidelijke autorisatieniveaus definiëren voor verschillende beslissingssoorten of risicocategorieën, indien van toepassing.    |   3   | D/V  |

---

## C13.3 Ketting van Verantwoordelijkheid & Controleerbaarheid

Log operatoracties en modelbeslissingen.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Controleer of alle beslissingen van het AI-systeem en menselijke interventies worden geregistreerd met tijdstempels, gebruikersidentiteiten en motieven voor de beslissing. |   1   | D/V  |
| 13.3.2 | Controleer of auditlogs niet kunnen worden gewijzigd en zorg ervoor dat ze mechanismen voor integriteitsverificatie bevatten.                                               |   2   |  D   |

---

## C13.4 Verklaarbare AI-technieken

Belang van oppervlaktekenmerken, tegenfeitelijke voorbeelden en lokale verklaringen.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Controleer of AI-systemen basisuitleg geven voor hun beslissingen in een voor mensen leesbaar formaat.                                                                          |   1   | D/V  |
| 13.4.2 | Verifieer dat de kwaliteit van de uitleg wordt gevalideerd door middel van menselijke evaluatiestudies en meetmethoden.                                                         |   2   |  V   |
| 13.4.3 | Controleer of scores voor kenmerkenbelang of attributiemethoden (SHAP, LIME, enz.) beschikbaar zijn voor kritieke beslissingen.                                                 |   3   | D/V  |
| 13.4.4 | Controleer of tegenfeitelijke verklaringen laten zien hoe invoer kan worden aangepast om resultaten te veranderen, indien toepasselijk voor het gebruiksscenario en het domein. |   3   |  V   |

---

## C13.5 Modelkaarten & Gebruiksaangiften

Onderhoud modelkaarten voor beoogd gebruik, prestatie-indicatoren en ethische overwegingen.

|   #    | Description                                                                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Controleer of modelkaarten de beoogde gebruikssituaties, beperkingen en bekende faalmodi documenteren.                                                                                                                 |   1   |  D   |
| 13.5.2 | Controleer of prestatie-indicatoren voor verschillende toepasselijke gebruikssituaties worden vermeld.                                                                                                                 |   1   | D/V  |
| 13.5.3 | Controleer of ethische overwegingen, bias-beoordelingen, evaluaties van rechtvaardigheid, kenmerken van trainingsgegevens en bekende beperkingen van trainingsgegevens gedocumenteerd en regelmatig bijgewerkt worden. |   2   |  D   |
| 13.5.4 | Controleer of modelkaarten versiebeheer hebben en gedurende de levenscyclus van het model worden onderhouden met wijzigingsregistratie.                                                                                |   2   | D/V  |

---

## C13.6 Kwantificering van onzekerheid

Propageer betrouwbaarheidscores of entropiematen in antwoorden.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Controleer of AI-systemen betrouwbaarheidscores of onzekerheidsmaten bij hun uitkomsten geven.                              |   1   |  D   |
| 13.6.2 | Controleer of onzekerheidsdrempels leiden tot extra menselijke beoordeling of alternatieve besluitvormingspaden.            |   2   | D/V  |
| 13.6.3 | Controleer of methoden voor onzekerheidskwantificatie zijn gekalibreerd en gevalideerd aan de hand van feitelijke gegevens. |   2   |  V   |
| 13.6.4 | Verifieer dat de onzekerheidsverspreiding wordt behouden in meervoudige AI-workflows.                                       |   3   | D/V  |

---

## C13.7 Transparantierapporten voor gebruikers

Bied periodieke rapportages over incidenten, afwijkingen en datagebruik.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.7.1 | Controleer of het gebruik van gegevensbeleid en praktijken voor het beheren van gebruikersconsent duidelijk worden gecommuniceerd aan belanghebbenden.       |   1   | D/V  |
| 13.7.2 | Verifieer dat AI-impactbeoordelingen worden uitgevoerd en dat de resultaten worden opgenomen in de rapportage.                                               |   2   | D/V  |
| 13.7.3 | Verifieer dat transparantierapporten die regelmatig worden gepubliceerd AI-incidenten en operationele statistieken in redelijke mate van detail bekendmaken. |   2   | D/V  |

### Referenties

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

