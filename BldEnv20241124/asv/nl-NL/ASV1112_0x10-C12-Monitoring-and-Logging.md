# C12 Monitoring, Logging en Anomaliedetectie

## Beheersingsdoelstelling

Deze sectie biedt vereisten voor het leveren van realtime en forensische zichtbaarheid in wat het model en andere AI-componenten waarnemen, doen en retourneren, zodat bedreigingen kunnen worden gedetecteerd, geanalyseerd en ervan geleerd kan worden.

## C12.1 Verzoek- en antwoordregistratie

|   #    | Description                                                                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Controleer of alle gebruikersopdrachten en modelantwoorden worden vastgelegd met de juiste metadata (bijv. tijdstempel, gebruikers-ID, sessie-ID, modelversie).                                                                                |   1   | D/V  |
| 12.1.2 | Controleer of logboeken worden opgeslagen in beveiligde, toegangsbeperkte repositories met passende bewaarbeleid en back-upprocedures.                                                                                                         |   1   | D/V  |
| 12.1.3 | Controleer of logopslagsystemen encryptie toepassen voor data in rust en tijdens transport om gevoelige informatie in logs te beveiligen.                                                                                                      |   1   | D/V  |
| 12.1.4 | Controleer of gevoelige gegevens in prompts en uitvoer automatisch worden geanonimiseerd of afgeschermd voordat ze worden gelogd, met configureerbare regels voor het anonimiseren van persoonsgegevens, inloggegevens en eigendomsinformatie. |   1   | D/V  |
| 12.1.5 | Controleer of beleidsbeslissingen en veiligheidsfilteracties met voldoende detail worden vastgelegd om audit en debugging van inhoudsmoderatiesystemen mogelijk te maken.                                                                      |   2   | D/V  |
| 12.1.6 | Verifieer dat de integriteit van logbestanden beschermd is via bijvoorbeeld cryptografische handtekeningen of alleen-geschreven opslag.                                                                                                        |   2   | D/V  |

---

## C12.2 Misbruikdetectie en waarschuwingen

|   #    | Description                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.2.1 | Verifieer dat het systeem bekende jailbreak-patronen, pogingen tot promptinjectie en vijandige invoer detecteert en waarschuwt met behulp van op handtekeningen gebaseerde detectie.                   |   1   | D/V  |
| 12.2.2 | Controleer of het systeem integreert met bestaande Security Information and Event Management (SIEM) platforms met behulp van standaard logformaten en protocollen.                                     |   1   | D/V  |
| 12.2.3 | Controleer of verrijkte beveiligingsevenementen AI-specifieke context bevatten, zoals modelidentificatoren, betrouwbaarheidscores en beslissingen van veiligheidsfilters.                              |   2   | D/V  |
| 12.2.4 | Controleer of gedragsafwijkingsdetectie ongebruikelijke gespreks patronen, buitensporige herkansingspogingen of systematische testgedragingen identificeert.                                           |   2   | D/V  |
| 12.2.5 | Verifieer dat realtime waarschuwingsmechanismen beveiligingsteams informeren wanneer mogelijke beleidschendingen of aanvalspogingen worden gedetecteerd.                                               |   2   | D/V  |
| 12.2.6 | Verifieer dat aangepaste regels zijn opgenomen om AI-specifieke bedreigingspatronen te detecteren, waaronder gecoördineerde jailbreak-pogingen, prompt-injectiecampagnes en model-extractie-aanvallen. |   2   | D/V  |
| 12.2.7 | Verifieer dat geautomatiseerde incidentrespons-workflows gecompromitteerde modellen kunnen isoleren, kwaadaardige gebruikers kunnen blokkeren en kritieke beveiligingsgebeurtenissen kunnen escaleren. |   3   | D/V  |

---

## C12.3 Detectie van modelafwijking

|   #    | Description                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.3.1 | Controleer of het systeem basisprestatiestatistieken bijhoudt, zoals nauwkeurigheid, betrouwbaarheidscores, latentie en foutpercentages over modelversies en tijdsperioden.                            |   1   | D/V  |
| 12.3.2 | Controleer of geautomatiseerde waarschuwingen worden geactiveerd wanneer prestatie-indicatoren vooraf gedefinieerde degradatiedrempels overschrijden of significant afwijken van de referentiewaarden. |   2   | D/V  |
| 12.3.3 | Controleer of hallucinatiedetectiemonitoren gevallen identificeren en markeren wanneer modeluitvoer feitelijk onjuiste, inconsistente of gefabriceerde informatie bevat.                               |   2   | D/V  |

---

## C12.4 Prestatie- en Gedragstelemetrie

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Controleer of operationele statistieken, waaronder verzoeklatentie, tokenverbruik, geheugen- en doorvoergebruik, continu worden verzameld en gemonitord.                    |   1   | D/V  |
| 12.4.2 | Verifieer dat succes- en faalkansen worden bijgehouden met categorisering van fouttypes en hun onderliggende oorzaken.                                                      |   1   | D/V  |
| 12.4.3 | Controleer of het monitoren van resourcegebruik GPU-/CPU-gebruik, geheugengebruik en opslagvereisten omvat, met waarschuwingen bij het overschrijden van de drempelwaarden. |   2   | D/V  |

---

## C12.5 Planning en uitvoering van AI-incidentrespons

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Controleer of de incidentresponsplannen specifiek ingaan op AI-gerelateerde beveiligingsincidenten zoals modelcompromittering, datapoisonsing en adversariële aanvallen. |   1   | D/V  |
| 12.5.2 | Controleer of incidentresponseteams toegang hebben tot AI-specifieke forensische tools en expertise om modelgedrag en aanvalsvectoren te onderzoeken.                    |   2   | D/V  |
| 12.5.3 | Verifieer dat de post-incidentanalyse rekening houdt met modelhertraining, updates van veiligheidsfilters en de integratie van geleerde lessen in beveiligingscontroles. |   3   | D/V  |

---

## C12.5 Detectie van prestatieafname van AI

Monitoren en detecteren van achteruitgang in de prestaties en kwaliteit van AI-modellen in de loop van de tijd.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Zorg ervoor dat modelnauwkeurigheid, precisie, recall en F1-scores continu worden gemonitord en vergeleken met basisdrempels.                                           |   1   | D/V  |
| 12.5.2 | Controleer of gegevensdriftdetectie veranderingen in de inputdistributie bewaakt die de modelprestaties kunnen beïnvloeden.                                             |   1   | D/V  |
| 12.5.3 | Controleer of concept drift-detectie veranderingen identificeert in de relatie tussen invoerwaarden en verwachte uitvoerwaarden.                                        |   2   | D/V  |
| 12.5.4 | Controleer of prestatievermindering geautomatiseerde waarschuwingen activeert en workflows voor het opnieuw trainen of vervangen van modellen initieert.                |   2   | D/V  |
| 12.5.5 | Verifieer dat de analyse van de hoofdoorzaak van degradatie de prestatieverminderingen correleert met gegevenswijzigingen, infrastructuurproblemen of externe factoren. |   3   |  V   |

---

## C12.6 DAG Visualisatie & Workflow Beveiliging

Bescherm workflows visualisatiesystemen tegen informelekken en manipulatieaanvallen.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Controleer of de DAG-visualisatiegegevens worden gesaneerd om gevoelige informatie te verwijderen voordat ze worden opgeslagen of verzonden.                                           |   1   | D/V  |
| 12.6.2 | Verifieer dat de toegangscontroles voor workflowvisualisatie ervoor zorgen dat alleen geautoriseerde gebruikers de beslissingspaden van de agent en redeneringstraces kunnen bekijken. |   1   | D/V  |
| 12.6.3 | Controleer of de integriteit van DAG-gegevens wordt beschermd door cryptografische handtekeningen en opslagmechanismen die manipulatie detecteren.                                     |   2   | D/V  |
| 12.6.4 | Controleer of workflowvisualisatiesystemen invoervalidatie toepassen om injectieaanvallen via gemanipuleerde knoop- of randgegevens te voorkomen.                                      |   2   | D/V  |
| 12.6.5 | Controleer of realtime DAG-updates worden beperkt in snelheid en gevalideerd om denial-of-service-aanvallen op visualisatiesystemen te voorkomen.                                      |   3   | D/V  |

---

## C12.7 Proactieve monitoring van beveiligingsgedrag

Detectie en preventie van beveiligingsbedreigingen door middel van proactieve analyse van agentgedrag.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Verifieer dat proactieve agentgedragingen worden beveiligingsgevalideerd voordat ze worden uitgevoerd, met integratie van risicobeoordeling.  |   1   | D/V  |
| 12.7.2 | Verifieer dat autonome initiatie triggers onder meer evaluatie van de beveiligingscontext en beoordeling van het dreigingslandschap omvatten. |   2   | D/V  |
| 12.7.3 | Controleer of proactieve gedragsmodellen worden geanalyseerd op mogelijke beveiligingsimplicaties en onbedoelde gevolgen.                     |   2   | D/V  |
| 12.7.4 | Verifieer dat beveiligingskritieke proactieve acties expliciete goedkeuringsketens vereisen met auditrajecten.                                |   3   | D/V  |
| 12.7.5 | Verifieer dat gedragsafwijkingsdetectie afwijkingen in proactieve agentpatronen identificeert die kunnen wijzen op compromittering.           |   3   | D/V  |

---

## Referenties

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

