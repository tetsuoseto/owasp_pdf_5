# 10 Adversariële Robuustheid & Privacyverdediging

## Controle Doelstelling

Zorg ervoor dat AI-modellen betrouwbaar, privacybeschermend en bestand tegen misbruik blijven bij het ondervinden van ontwijkings-, inferentie-, extractie- of vergiftigingsaanvallen.

---

## 10.1 Modelafstemming en Veiligheid

Bescherm tegen schadelijke of beleidschendende output.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Controleer of een alignment test-suite (red-team prompts, jailbreak probes, niet-toegestane inhoud) versiebeheer heeft en bij elke modelrelease wordt uitgevoerd. |   1   | D/V  |
| 10.1.2 | Verifieer dat weigering en veilige voltooings-beveiligingsmechanismen worden gehandhaafd.                                                                         |   1   |  D   |
| 10.1.3 | Verifieer dat een geautomatiseerde beoordelaar het percentage schadelijke inhoud meet en regresgevallen markeert die een bepaalde drempel overschrijden.          |   2   | D/V  |
| 10.1.4 | Controleer of counter-jailbreak training gedocumenteerd en reproduceerbaar is.                                                                                    |   2   |  D   |
| 10.1.5 | Verifieer dat formele beleidsnalevingsbewijzen of gecertificeerde monitoring kritieke domeinen bestrijken.                                                        |   3   |  V   |

---

## 10.2 Versterking tegen vijandige voorbeelden

Verhoog de veerkracht tegen gemanipuleerde invoer. Robuuste adversariële training en benchmarkscoring zijn momenteel de beste praktijk.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Controleer of projectrepositories configuraties voor adversariële training bevatten met reproduceerbare zaden.                               |   1   |  D   |
| 10.2.2 | Verifieer dat detectie van vijandige voorbeelden blokkeringwaarschuwingen geeft in productiepijplijnen.                                      |   2   | D/V  |
| 10.2.4 | Verifieer of certificaten voor gecertificeerde robuustheid of intervalgrenscertificaten ten minste de belangrijkste kritieke klassen dekken. |   3   |  V   |
| 10.2.5 | Verifieer dat regressietests adaptieve aanvallen gebruiken om te bevestigen dat er geen meetbaar verlies aan robuustheid is.                 |   3   |  V   |

---

## 10.3 Vermindering van lidmaatschapsinzage

Beperk de mogelijkheid om te bepalen of een record in de trainingsgegevens zat. Differentiële privacy en het maskeren van betrouwbaarheidscores blijven de meest effectieve bekende verdedigingsmethoden.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.3.1 | Controleer of per-query entropie-regularisatie of temperatuurschaling overconfidente voorspellingen vermindert.    |   1   |  D   |
| 10.3.2 | Controleer of de training gebruikmaakt van ε-gebonden differentieel-private optimalisatie voor gevoelige datasets. |   2   |  D   |
| 10.3.3 | Verifieer dat aanvalssimulaties (shadow-model of black-box) een aanval AUC ≤ 0,60 tonen op afgezonderde data.      |   2   |  V   |

---

## 10.4 Weerstand tegen model-inversie

Voorkom reconstructie van privéattributen. Recente onderzoeken benadrukken outputafkapping en DP-garanties als praktische verdedigingsmaatregelen.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.4.1 | Verifieer dat gevoelige attributen nooit direct worden weergegeven; gebruik waar nodig buckets of eenrichtings-transformaties. |   1   |  D   |
| 10.4.2 | Controleer of query-snelheidsbeperkingen herhaalde adaptieve queries van dezelfde principal beperken.                          |   1   | D/V  |
| 10.4.3 | Controleer of het model is getraind met privacy-behoudende ruis.                                                               |   2   |  D   |

---

## 10.5 Verdediging tegen model-extractie

Detecteer en voorkom ongeoorloofd klonen. Watermerken en analyse van query-patronen worden aanbevolen.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.5.1 | Verifieer dat inference-gateways wereldwijde en per-API-sleutel snelheidslimieten afdwingen die zijn afgestemd op de memorisatiedrempel van het model. |   1   |  D   |
| 10.5.2 | Controleer of statistieken over query-entropie en input-meervoudigheid een geautomatiseerde extractiedetector voeden.                                  |   2   | D/V  |
| 10.5.3 | Verifieer dat fragiele of probabilistische watermerken kunnen worden bewezen met p < 0,01 in ≤ 1.000 queries tegen een vermoedelijke kloon.            |   2   |  V   |
| 10.5.4 | Controleer of watermerk-sleutels en trigger-sets zijn opgeslagen in een hardware-beveiligingsmodule en jaarlijks worden vernieuwd.                     |   3   |  D   |
| 10.5.5 | Controleer of extraction-alert gebeurtenissen de aanstootgevende queries bevatten en zijn geïntegreerd met incident-respons draaiboeken.               |   3   |  V   |

---

## 10.6 Detectie van vergiftigde gegevens tijdens inferentietijd

Identificeer en neutraliseer achterdeurtjes of vergiftigde invoer.

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Verifieer dat invoerwaarden worden gecontroleerd door een anomaliedetector (bijvoorbeeld STRIP, consistentiescore) voordat het model een voorspelling doet. |   1   |  D   |
| 10.6.2 | Controleer of de detector-drempels zijn afgestemd op schone/geïnfecteerde validatiesets om minder dan 5% false positives te bereiken.                       |   1   |  V   |
| 10.6.3 | Controleer of invoer die als vergiftigd wordt gemarkeerd, zachte blokkering en workflows voor menselijke beoordeling activeert.                             |   2   |  D   |
| 10.6.4 | Verifieer dat detectoren worden blootgesteld aan stresstests met adaptieve, triggerloze backdoor-aanvallen.                                                 |   2   |  V   |
| 10.6.5 | Controleer of de effectiviteitsmetriek voor detectie wordt vastgelegd en periodiek wordt herbeoordeeld met actuele dreigingsinformatie.                     |   3   |  D   |

---

## 10.7 Dynamische aanpassing van het beveiligingsbeleid

Realtime beveiligingsbeleidupdates op basis van dreigingsinformatie en gedragsanalyse.

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Controleer of beveiligingsbeleid dynamisch kan worden bijgewerkt zonder dat de agent opnieuw hoeft te worden gestart, terwijl de integriteit van de beleidsversie behouden blijft. |   1   | D/V  |
| 10.7.2 | Controleer of beleidsupdates cryptografisch worden ondertekend door geautoriseerd beveiligingspersoneel en worden gevalideerd voordat ze worden toegepast.                         |   2   | D/V  |
| 10.7.3 | Controleer of dynamische beleidswijzigingen worden vastgelegd met volledige audit-trails, inclusief rechtvaardiging, goedkeuringsketens en terugrolprocedures.                     |   2   | D/V  |
| 10.7.4 | Controleer of adaptieve beveiligingsmechanismen de gevoeligheid van bedreigingsdetectie aanpassen op basis van risicocontext en gedrags- patronen.                                 |   3   | D/V  |
| 10.7.5 | Verifieer dat beslissingen over beleidsaanpassing verklaarbaar zijn en bewijsvoering bevatten voor beoordeling door het beveiligingsteam.                                          |   3   | D/V  |

---

## 10.8 Reflectiegebaseerde beveiligingsanalyse

Beveiligingsvalidatie door middel van zelfreflectie van de agent en metacognitieve analyse.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Verifieer dat agentreflectiemechanismen een op beveiliging gerichte zelfbeoordeling van beslissingen en acties omvatten.                                         |   1   | D/V  |
| 10.8.2 | Controleer of reflectie-uitgangen worden gevalideerd om manipulatie van zelfbeoordelingsmechanismen door vijandige invoer te voorkomen.                          |   2   | D/V  |
| 10.8.3 | Controleer of meta-cognitieve beveiligingsanalyse mogelijke vooringenomenheid, manipulatie of compromittering in de redeneerprocessen van agenten identificeert. |   2   | D/V  |
| 10.8.4 | Controleer of op reflectie gebaseerde beveiligingswaarschuwingen verbeterde monitoring en mogelijke workflows voor menselijke tussenkomst activeren.             |   3   | D/V  |
| 10.8.5 | Verifieer dat continue leren van beveiligingsreflecties de dreigingsdetectie verbetert zonder de legitieme functionaliteit aan te tasten.                        |   3   | D/V  |

---

## 10.9 Evolutie & Zelfverbeteringsbeveiliging

Beveiligingsmaatregelen voor agentensystemen die in staat zijn tot zelfaanpassing en evolutie.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Verifieer dat zelfmodificatiecapaciteiten beperkt zijn tot aangewezen veilige gebieden met formele verificatiegrenzen.             |   1   | D/V  |
| 10.9.2 | Verifieer dat evolutievoorstellen een beveiligingsimpactbeoordeling ondergaan voordat ze worden geïmplementeerd.                   |   2   | D/V  |
| 10.9.3 | Controleer of zelfverbeteringsmechanismen herstelopties bevatten met integriteitsverificatie.                                      |   2   | D/V  |
| 10.9.4 | Verifieer dat meta-leren beveiliging voorkomt dat verbetering algoritmen op een vijandige wijze worden gemanipuleerd.              |   3   | D/V  |
| 10.9.5 | Verifieer dat recursieve zelfverbetering wordt begrensd door formele veiligheidscriteria met wiskundige bewijzen van convergentie. |   3   | D/V  |

---

### Referenties

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

