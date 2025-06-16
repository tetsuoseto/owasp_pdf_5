# Beheer van de levenscyclus van het C3-model & wijzigingsbeheer

## Beheersingsdoelstelling

AI-systemen moeten wijzigingscontroleprocessen implementeren die voorkomen dat ongeautoriseerde of onveilige modelwijzigingen in de productie terechtkomen. Deze controle waarborgt de integriteit van het model gedurende de gehele levenscyclus—van ontwikkeling via implementatie tot buiten gebruik stellen—wat snelle incidentrespons mogelijk maakt en de verantwoordelijkheid voor alle wijzigingen handhaaft.

Kernveiligheidsdoel: Alleen geautoriseerde, gevalideerde modellen bereiken de productie door gecontroleerde processen toe te passen die integriteit, traceerbaarheid en herstelbaarheid waarborgen.

---

## C3.1 Modelautorisatie en integriteit

Alleen geautoriseerde modellen met geverifieerde integriteit bereiken productieomgevingen.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.1.1 | Controleer of alle modelartefacten (gewichten, configuraties, tokenizers) cryptografisch zijn ondertekend door geautoriseerde entiteiten voordat ze worden ingezet.                                                      |   1   | D/V  |
| 3.1.2 | Controleer of de integriteit van het model wordt gevalideerd bij het implementeren en dat mislukte handtekeningverificaties het laden van het model voorkomen.                                                           |   1   | D/V  |
| 3.1.3 | Controleer of de provenance-informatie van het model de identiteit van de autoriserende entiteit, checksums van de trainingsdata, validatietestresultaten met geslaagde/mislukte status en een creatietijdstempel bevat. |   2   | D/V  |
| 3.1.4 | Controleer of alle modelartefacten semantische versiebeheer gebruiken (MAJOR.MINOR.PATCH) met gedocumenteerde criteria die aangeven wanneer elk versiecomponent wordt verhoogd.                                          |   2   | D/V  |
| 3.1.5 | Controleer of afhankelijkheidsbewaking een realtime voorraad bijhoudt die een snelle identificatie van alle verbruikende systemen mogelijk maakt.                                                                        |   2   |  V   |

---

## C3.2 Modelvalidatie & Testen

Modellen moeten voldoen aan gedefinieerde beveiligings- en veiligheidscontroles voordat ze worden ingezet.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Verifieer dat modellen geautomatiseerde beveiligingstests ondergaan die inputvalidatie, outputsanering en veiligheidsevaluaties omvatten met vooraf afgesproken organisatorische slaag-/faalthresholds voordat ze worden ingezet. |   1   | D/V  |
| 3.2.2 | Controleer of validatiefouten automatisch de modeluitrol blokkeren, behalve na expliciete goedkeuring van vooraf aangewezen bevoegde personen met gedocumenteerde zakelijke rechtvaardigingen.                                    |   1   | D/V  |
| 3.2.3 | Controleer of testresultaten cryptografisch zijn ondertekend en onveranderlijk gekoppeld aan de specifieke modelversie-hash die wordt gevalideerd.                                                                                |   2   |  V   |
| 3.2.4 | Verifieer dat noodimplementaties een gedocumenteerde beveiligingsrisicobeoordeling vereisen en goedkeuring van een vooraf aangewezen beveiligingsautoriteit binnen vooraf afgesproken termijnen.                                  |   2   | D/V  |

---

## C3.3 Gecontroleerde Implementatie & Terugrolprocedure

Modelimplementaties moeten gecontroleerd, gemonitord en omkeerbaar zijn.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Controleer of productie-implementaties geleidelijke uitrolmechanismen toepassen (canary-implementaties, blue-green implementaties) met geautomatiseerde rollback-triggers op basis van vooraf overeengekomen foutpercentages, latentiegrenzen of beveiligingswaarschuwingscriteria. |   1   |  D   |
| 3.3.2 | Controleer of de rollback-mogelijkheden de volledige modelstatus (gewichten, configuraties, afhankelijkheden) atomair herstellen binnen vooraf gedefinieerde organisatorische tijdvensters.                                                                                         |   1   | D/V  |
| 3.3.3 | Controleer of implementatieprocessen cryptografische handtekeningen valideren en integriteitschecksommen berekenen vóór modelactivatie, en stop de implementatie bij elke afwijking.                                                                                                |   2   | D/V  |
| 3.3.4 | Verifieer dat noodmodeluitschakelingsmogelijkheden modelendpoints binnen vooraf gedefinieerde responstijden kunnen uitschakelen via geautomatiseerde stroomonderbrekers of handmatige noodschakelaars.                                                                              |   2   | D/V  |
| 3.3.5 | Controleer of rollback-artifacten (voorgaande modelversies, configuraties, afhankelijkheden) worden bewaard volgens de organisatiebeleid met onveranderlijke opslag voor incidentrespons.                                                                                           |   2   |  V   |

---

## C3.4 Verantwoordingsplicht en Audit

Alle levenscycluswijzigingen van het model moeten traceerbaar en controleerbaar zijn.

|   #   | Description                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Verifieer dat alle modelwijzigingen (implementatie, configuratie, buiten gebruik stellen) onveranderlijke auditrecords genereren, inclusief een tijdstempel, een geauthenticeerde actorenidentiteit, een wijzigingstype, en de toestand voor en na de wijziging. |   1   |  V   |
| 3.4.2 | Controleer of toegang tot het auditlogboek de juiste autorisatie vereist en of alle toegangspogingen worden geregistreerd met gebruikersidentiteit en een tijdstempel.                                                                                           |   2   | D/V  |
| 3.4.3 | Verifieer dat prompt-sjablonen en systeemberichten versiebeheer hebben in git-repositories, met verplichte codebeoordeling en goedkeuring door aangewezen beoordelaars voordat ze worden uitgerold.                                                              |   2   | D/V  |
| 3.4.4 | Controleer of de auditrecords voldoende details bevatten (model-hashes, configuratiesnapshots, afhankelijkheidsversies) om een volledige reconstructie van de modelstatus voor elk tijdstip binnen de bewaartermijn mogelijk te maken.                           |   2   |  V   |

---

## C3.5 Beveiligde Ontwikkelingspraktijken

Het ontwikkelen en trainen van modellen moet volgens beveiligde praktijken verlopen om compromittering te voorkomen.

|   #   | Description                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Controleer of de ontwikkel-, test- en productieomgevingen van het model fysiek of logisch gescheiden zijn. Ze mogen geen gedeelde infrastructuur hebben, moeten verschillende toegangscontrole bevatten en geïsoleerde gegevensopslagplaatsen. |   1   |  D   |
| 3.5.2 | Controleer of modeltraining en fijnregeling plaatsvinden in geïsoleerde omgevingen met gecontroleerde netwerktoegang.                                                                                                                          |   1   |  D   |
| 3.5.3 | Controleer of trainingsgegevensbronnen worden gevalideerd via integriteitscontroles en geverifieerd via betrouwbare bronnen met een gedocumenteerde keten van bewaring voordat ze worden gebruikt bij de modelontwikkeling.                    |   1   | D/V  |
| 3.5.4 | Controleer of modelontwikkelingsartefacten (hyperparameters, trainingsscripts, configuratiebestanden) worden opgeslagen in versiebeheer en dat goedkeuring door collega's vereist is voordat ze worden gebruikt voor training.                 |   2   |  D   |

---

## C3.6 Model Uitfasering & Buiten Gebruik Stellen

Modellen moeten veilig worden buiten gebruik gesteld wanneer ze niet langer nodig zijn of wanneer beveiligingsproblemen worden vastgesteld.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.6.1 | Verifieer dat modelpensioenprocessen automatisch afhankelijkheidsgrafieken scannen, alle verbruikende systemen identificeren en vooraf afgesproken kennisgevingstermijnen bieden vóór buitengebruikstelling.                         |   1   |  D   |
| 3.6.2 | Verifieer dat uitgefaseerde modelartefacten veilig worden verwijderd via cryptografische uitwissing of meervoudig overschrijven volgens vastgelegde beleidslijnen voor gegevensretentie met geverifieerde vernietigingscertificaten. |   1   | D/V  |
| 3.6.3 | Verifieer dat modeluitfaseringsevenementen worden geregistreerd met tijdstempel en identiteit van de actor, en dat modelhandtekeningen worden ingetrokken om hergebruik te voorkomen.                                                |   2   |  V   |
| 3.6.4 | Controleer of het noodmodel met pensioen gaan de toegang tot het model kan uitschakelen binnen vooraf vastgestelde noodreactietijdvensters via geautomatiseerde kill-switches als kritieke beveiligingslekken worden ontdekt.        |   2   | D/V  |

---

## Referenties

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

