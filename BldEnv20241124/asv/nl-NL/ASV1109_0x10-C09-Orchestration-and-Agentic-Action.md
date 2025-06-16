# 9 Autonome Orkestratie & Agente Actie Beveiliging

## Beheersingsdoel

Zorg ervoor dat autonome of multi-agent AI-systemen alleen acties kunnen uitvoeren die expliciet bedoeld, geverifieerd, controleerbaar en binnen begrensde kosten- en risicodrempels vallen. Dit beschermt tegen bedreigingen zoals compromittering van autonome systemen, misbruik van tools, detectie van agentlussen, kaping van communicatie, identiteitsvervalsing, zwermmanipulatie en intentiemanipulatie.

---

## 9.1 Taakplanning van agenten & Recursiebudgetten

Beperk recursieve plannen en verplicht menselijke controlepunten voor geprivilegieerde acties.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Controleer of de maximale recursiediepte, breedte, kloktijd, tokens en monetaire kosten per agentuitvoering centraal zijn geconfigureerd en versiegecontroleerd.                                           |   1   | D/V  |
| 9.1.2 | Controleer of bevoorrechte of onomkeerbare acties (bijv. code-commits, financiële overboekingen) expliciete goedkeuring door een mens vereisen via een controleerbaar kanaal voordat ze worden uitgevoerd. |   1   | D/V  |
| 9.1.3 | Controleer of real-time hulpmiddelenmonitors de circuit-breaker onderbreking activeren wanneer een budgetdrempel wordt overschreden, waardoor verdere takenuitbreiding wordt gestopt.                      |   2   |  D   |
| 9.1.4 | Controleer of circuitonderbreker-gebeurtenissen worden gelogd met agent-ID, activeringsvoorwaarde en vastgelegde plantoestand voor forensische beoordeling.                                                |   2   | D/V  |
| 9.1.5 | Controleer of de beveiligingstests scenario's van budgetuitputting en voortvluchtige plannen dekken, en bevestig dat er veilig wordt gestopt zonder gegevensverlies.                                       |   3   |  V   |
| 9.1.6 | Verifieer dat budgetbeleid wordt uitgedrukt als beleid-als-code en wordt afgedwongen in CI/CD om configuratieafwijkingen te blokkeren.                                                                     |   3   |  D   |

---

## 9.2 Plugin Sandbox voor Hulpprogramma's

Isoleer toolinteracties om ongeautoriseerde toegang tot het systeem of code-uitvoering te voorkomen.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Verifieer dat elke tool/plugin wordt uitgevoerd binnen een OS-, container- of WASM-niveau sandbox met een minst-privilege beleid voor bestandssysteem, netwerk en systeemoproepen. |   1   | D/V  |
| 9.2.2 | Controleer of sandbox resourcequota's (CPU, geheugen, schijf, netwerkuitgaande verkeer) en uitvoeringstijdslimieten worden gehandhaafd en geregistreerd.                           |   1   | D/V  |
| 9.2.3 | Controleer of de toolbinaries of descriptoren digitaal zijn ondertekend; handtekeningen worden gevalideerd voordat ze worden geladen.                                              |   2   | D/V  |
| 9.2.4 | Controleer of sandbox-telemetrie naar een SIEM wordt gestreamd; anomalieën (bijvoorbeeld pogingen tot uitgaande verbindingen) veroorzaken waarschuwingen.                          |   2   |  V   |
| 9.2.5 | Verifieer of plugins met een hoog risico een veiligheidsbeoordeling en penetratietest ondergaan voordat ze in productie worden genomen.                                            |   3   |  V   |
| 9.2.6 | Controleer of pogingen tot ontsnappen uit de sandbox automatisch worden geblokkeerd en of de betreffende plugin in quarantaine wordt geplaatst in afwachting van onderzoek.        |   3   | D/V  |

---

## 9.3 Autonome lus en kostenbegrenzing

Detecteer en stop ongecontroleerde agent-tot-agent recursie en kostenexplosies.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.3.1 | Controleer of inter-agent oproepen een hop-limiet of TTL bevatten die de runtime vermindert en afdwingt.                                                                 |   1   | D/V  |
| 9.3.2 | Verifieer dat agents een unieke oproep-grafiek-ID behouden om zelfoproep of cyclische patronen te detecteren.                                                            |   2   |  D   |
| 9.3.3 | Verifieer dat cumulatieve compute-eenheid- en uitgavencounters per verzoekketen worden bijgehouden; het overschrijden van de limiet leidt tot het afbreken van de keten. |   2   | D/V  |
| 9.3.4 | Verifieer dat formele analyse of model checking afwezigheid van onbeperkte recursie in agentprotocollen aantoont.                                                        |   3   |  V   |
| 9.3.5 | Verifieer dat loop-afbreekgebeurtenissen waarschuwingen genereren en continue verbeteringsstatistieken voeden.                                                           |   3   |  D   |

---

## 9.4 Misbruikbescherming op protocolleniveau

Beveiligde communicatiekanalen tussen agenten en externe systemen om kaping of manipulatie te voorkomen.

|   #   | Description                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Controleer of alle berichten van agent naar hulpmiddel en van agent naar agent geverifieerd zijn (bijvoorbeeld via mutual TLS of JWT) en end-to-end versleuteld zijn. |   1   | D/V  |
| 9.4.2 | Controleer of schema's strikt worden gevalideerd; onbekende velden of foutieve berichten worden geweigerd.                                                            |   1   |  D   |
| 9.4.3 | Controleer of integriteitscontroles (MAC's of digitale handtekeningen) de volledige berichtinhoud, inclusief toolparameters, bestrijken.                              |   2   | D/V  |
| 9.4.4 | Controleer of replay-bescherming (nonces of tijdvensters) wordt afgedwongen op het protocollaag.                                                                      |   2   |  D   |
| 9.4.5 | Controleer of protocolimplementaties onderworpen zijn aan fuzzing en statische analyse om injectie- of deserialisatiefouten op te sporen.                             |   3   |  V   |

---

## 9.5 Agentidentiteit en bewijs van manipulatie

Zorg ervoor dat acties toewijsbaar zijn en wijzigingen detecteerbaar.

|   #   | Description                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Verifieer dat elke agentinstantie beschikt over een unieke cryptografische identiteit (sleutelpaar of op hardware gebaseerde referentie). |   1   | D/V  |
| 9.5.2 | Controleer of alle agentacties zijn ondertekend en van een tijdstempel zijn voorzien; logs bevatten de handtekening voor niet-ontkenning. |   2   | D/V  |
| 9.5.3 | Verifieer dat knoeibestendige logbestanden worden opgeslagen in een append-only of write-once medium.                                     |   2   |  V   |
| 9.5.4 | Controleer of identiteitsleutels roteren volgens een vastgesteld schema en bij aanwijzingen van compromittering.                          |   3   |  D   |
| 9.5.5 | Controleer of pogingen tot spoofing of sleutelconflicten leiden tot onmiddellijke isolatie van de getroffen agent.                        |   3   | D/V  |

---

## 9.6 Risicoreductie door Multi-Agent Zwermen

Beperk gevaren van collectief gedrag door isolatie en formele veiligheidsmodellering.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Verifieer dat agenten die werken in verschillende beveiligingsdomeinen, worden uitgevoerd in geïsoleerde runtime sandboxes of netwerksegmenten. |   1   | D/V  |
| 9.6.2 | Controleer of zwermgedrag wordt gemodelleerd en formeel geverifieerd op levendigheid en veiligheid voordat het wordt ingezet.                   |   3   |  V   |
| 9.6.3 | Controleer of runtime monitors opkomende onveilige patronen (bijv. oscillaties, deadlocks) detecteren en corrigerende maatregelen nemen.        |   3   |  D   |

---

## 9.7 Gebruikers- en Toolauthenticatie / Autorisatie

Implementeer robuuste toegangscontroles voor elke door een agent-trigger uitgevoerde actie.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Verifieer dat agenten zich authenticeren als eersteklas principalen bij downstream-systemen, zonder ooit de inloggegevens van eindgebruikers te hergebruiken. |   1   | D/V  |
| 9.7.2 | Verifieer dat fijnmazige autorisatiebeleid beperkt welke tools een agent mag aanroepen en welke parameters deze mag meegeven.                                 |   2   |  D   |
| 9.7.3 | Controleer of de privileges-controles bij elke oproep opnieuw worden geëvalueerd (continue autorisatie), en niet alleen aan het begin van de sessie.          |   2   |  V   |
| 9.7.4 | Controleer of gedelegeerde privileges automatisch verlopen en opnieuw toestemming vereisen na time-out of wijziging van het bereik.                           |   3   |  D   |

---

## 9.8 Beveiliging van communicatie tussen agenten

Versleutel en bescherm alle berichten tussen agents tegen integriteitsinbreuk om afluisteren en manipulatie te voorkomen.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Verifieer dat wederzijdse authenticatie en perfect-forward-secret encryptie (bijv. TLS 1.3) verplicht zijn voor agentkanalen.                                             |   1   | D/V  |
| 9.8.2 | Verifieer dat de berichtintegriteit en -herkomst worden gevalideerd voordat verwerking plaatsvindt; bij fouten worden waarschuwingen afgegeven en het bericht verwijderd. |   1   |  D   |
| 9.8.3 | Verifieer dat communicatiemetagegevens (tijdstempels, sequentienummers) worden vastgelegd ter ondersteuning van forensische reconstructie.                                |   2   | D/V  |
| 9.8.4 | Verifieer dat formele verificatie of modelchecking bevestigt dat protocoltoestandsmachines niet in onveilige toestanden kunnen worden gedwongen.                          |   3   |  V   |

---

## 9.9 Intentieverificatie en naleving van beperkingen

Valideer dat de acties van de agent overeenkomen met de aangegeven intentie van de gebruiker en de systeembeperkingen.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Verifieer dat pre-executie constraint oplosser voorgestelde acties controleert aan de hand van hard-coded veiligheids- en beleidsregels.                                                 |   1   |  D   |
| 9.9.2 | Controleer of acties met grote impact (financieel, destructief, privacygevoelig) expliciete bevestiging van intentie vereisen van de gebruiker die de actie initieert.                   |   2   | D/V  |
| 9.9.3 | Controleer of de post-conditiecontroles bevestigen dat voltooide acties de beoogde effecten hebben bereikt zonder bijwerkingen; afwijkingen veroorzaken een rollback.                    |   2   |  V   |
| 9.9.4 | Verifieer dat formele methoden (bijv. model checking, theorem proving) of op eigenschappen gebaseerde tests aantonen dat de plannen van agenten voldoen aan alle verklaarde beperkingen. |   3   |  V   |
| 9.9.5 | Verifieer dat incidenten van intentie-mismatch of overtreding van beperkingen de continue verbetercycli en het delen van bedreigingsinformatie voeden.                                   |   3   |  D   |

---

## 9.10 Beveiliging van de redeneringsstrategie van agenten

Veilige selectie en uitvoering van verschillende redeneerstrategieën, waaronder ReAct, Chain-of-Thought en Tree-of-Thoughts benaderingen.

|   #    | Description                                                                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Controleer of de selectie van de redeneervolgorde gebruikmaakt van deterministische criteria (inputcomplexiteit, type taak, beveiligingscontext) en dat identieke inputs binnen dezelfde beveiligingscontext identieke volgorde-selecties opleveren. |   1   | D/V  |
| 9.10.2 | Verifieer dat elke redeneerstrategie (ReAct, Chain-of-Thought, Tree-of-Thoughts) specifieke invoervalidatie, uitvoerzuivering en tijdslimieten voor uitvoering heeft die zijn afgestemd op de cognitieve aanpak ervan.                               |   1   | D/V  |
| 9.10.3 | Controleer of overgangen in de redeneervaardigheid worden geregistreerd met volledige context, inclusief kenmerken van de invoer, waarden van selectiecriteria en uitvoeringsmetadata, voor reconstructie van het auditspoor.                        |   2   | D/V  |
| 9.10.4 | Controleer of Tree-of-Thoughts redenering mechanisme voor het afkappen van takken bevat die de verkenning beëindigen bij het detecteren van beleidschendingen, resourcebeperkingen of veiligheidsgrenzen.                                            |   2   | D/V  |
| 9.10.5 | Controleer of ReAct (Redeneren-Handelen-Observeren) cycli validatiecontroles bevatten in elke fase: verificatie van de redeneerstap, autorisatie van de actie en sanering van de observatie voordat wordt doorgegaan.                                |   2   | D/V  |
| 9.10.6 | Controleer of prestatiestatistieken van redeneerstrategieën (uitvoeringstijd, bronnengebruik, outputkwaliteit) worden bewaakt met geautomatiseerde waarschuwingen wanneer de statistieken afwijken van de geconfigureerde drempels.                  |   3   | D/V  |
| 9.10.7 | Verifieer dat hybride redeneerbenaderingen die meerdere strategieën combineren, de invoervalidatie en uitvoerbeperkingen van alle afzonderlijke strategieën handhaven zonder beveiligingscontroles te omzeilen.                                      |   3   | D/V  |
| 9.10.8 | Verifieer dat de beveiligingstests van redeneringsstrategieën fuzzing omvatten met verkeerd gevormde invoer, vijandige prompts die ontworpen zijn om strategiewisseling af te dwingen, en grenswaardetests voor elke cognitieve benadering.          |   3   | D/V  |

---

## 9.11 Beheer van de levenscyclusstatus en beveiliging van agents

Veilige agentinitialisatie, statustransities en terminatie met cryptografische audit-trails en gedefinieerde herstelprocedures.

|   #    | Description                                                                                                                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Verifyer dat de agent-initialisatie cryptografische identiteit vastlegt met hardware-ondersteunde referenties en onveranderlijke opstartauditlogs bevat met agent-ID, tijdstempel, configuratie-hash en initialisatieparameters.                                                                          |   1   | D/V  |
| 9.11.2 | Verifieer dat agenttoestandovergangen cryptografisch zijn ondertekend, van een tijdstempel zijn voorzien en worden gelogd met volledige context, inclusief de triggerende gebeurtenissen, de hash van de vorige staat, de hash van de nieuwe staat en uitgevoerde beveiligingscontroles.                  |   2   | D/V  |
| 9.11.3 | Controleer of de afsluitprocedures van de agent veilige geheugenwissing omvatten via cryptografische wissen of meervoudig overschrijven, intrekking van referenties met kennisgeving aan de certificeringsautoriteit, en het genereren van knoeibestendige beëindigingscertificaten.                      |   2   | D/V  |
| 9.11.4 | Controleer of agent-herstelmechanismen de integriteit van de status valideren met behulp van cryptografische checksums (minimaal SHA-256) en terugrollen naar bekende goede statussen wanneer corruptie wordt gedetecteerd, met geautomatiseerde waarschuwingen en vereisten voor handmatige goedkeuring. |   3   | D/V  |
| 9.11.5 | Verifieer dat agent persistentiemechanismen gevoelige statusgegevens versleutelen met per-agent AES-256 sleutels en implementeer een veilige sleutelrotatie volgens configureerbare schema's (maximaal 90 dagen) met een deployment zonder downtime.                                                      |   3   | D/V  |

---

## 9.12 Beveiligingskader voor Toolintegratie

Beveiligingscontroles voor dynamische gereedschaplading, uitvoering en resultaatvalidatie met gedefinieerde risicobeoordelings- en goedkeuringsprocessen.

|   #    | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Controleer of toolbeschrijvingen beveiligingsmetadata bevatten die vereiste privileges specificeren (lezen/schrijven/uitvoeren), risiconiveaus (laag/middel/hoog), resourcebeperkingen (CPU, geheugen, netwerk) en validatievereisten die zijn gedocumenteerd in toolmanifesten.        |   1   | D/V  |
| 9.12.2 | Verifieer dat de uitvoeringsresultaten van tools worden gevalideerd aan de hand van verwachte schema's (JSON Schema, XML Schema) en beveiligingsbeleid (outputsanering, gegevensclassificatie) voordat ze worden geïntegreerd, met tijdslimieten en foutafhandelingsprocedures.         |   1   | D/V  |
| 9.12.3 | Verifieer dat toolinteractie-logboeken gedetailleerde beveiligingscontext bevatten, inclusief gebruik van privileges, patroon van gegevens toegang, uitvoeringstijd, hulpbronnenverbruik en retourcodes, met gestructureerde logging voor SIEM-integratie.                              |   2   | D/V  |
| 9.12.4 | Verifieer dat dynamische hulpmiddelenlaadmechanismen digitale handtekeningen valideren met behulp van PKI-infrastructuur en implementeer veilige laadprotocollen met sandbox-isolatie en machtigingsverificatie voorafgaand aan uitvoering.                                             |   2   | D/V  |
| 9.12.5 | Controleer of beveiligingsbeoordelingen van tools automatisch worden gestart voor nieuwe versies met verplichte goedkeuringspoorten, inclusief statische analyse, dynamische tests en beoordeling door het beveiligingsteam, met gedocumenteerde goedkeuringscriteria en SLA-vereisten. |   3   | D/V  |

---

### Referenties

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

