# C4-infrastructuur, configuratie- en implementatiebeveiliging

## Beheersingsdoelstelling

AI-infrastructuur moet worden versterkt tegen privilege-escalatie, manipulatie van de toeleveringsketen en laterale bewegingen door middel van veilige configuratie, runtime-isolatie, vertrouwde implementatiepijplijnen en uitgebreide monitoring. Alleen geautoriseerde, gevalideerde infrastructuurcomponenten en configuraties bereiken de productie via gecontroleerde processen die beveiliging, integriteit en controleerbaarheid waarborgen.

Kernveiligheidsdoel: Alleen cryptografisch ondertekende, op kwetsbaarheden gescande infrastructuurcomponenten bereiken de productie via geautomatiseerde validatiepijplijnen die beveiligingsbeleid afdwingen en onveranderlijke auditsporen onderhouden.

---

## C4.1 Runtime-omgeving Isolatie

Voorkom container-escapes en privilege-escalatie via isolatieprimitieven op kernelniveau en verplichte toegangscontroles.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Controleer of alle AI-containers ALLE Linux-mogelijkheden verwijderen behalve CAP_SETUID, CAP_SETGID en expliciet vereiste mogelijkheden die gedocumenteerd zijn in de beveiligingsrichtlijnen.                                          |   1   | D/V  |
| 4.1.2 | Controleer of seccomp-profielen alle systeemoproepen blokkeren behalve die in vooraf goedgekeurde toestemmingslijsten, waarbij overtredingen de container beëindigen en beveiligingswaarschuwingen genereren.                            |   1   | D/V  |
| 4.1.3 | Controleer of AI-werklasten draaien met alleen-lezen root-bestandssystemen, tmpfs voor tijdelijke gegevens, en benoemde volumes voor persistente gegevens met afdwingbare noexec-mountopties.                                            |   2   | D/V  |
| 4.1.4 | Verifieer dat op eBPF gebaseerde runtime monitoring (Falco, Tetragon of gelijkwaardig) pogingen tot privilege-escalatie detecteert en automatisch de overtredende processen beëindigt binnen de responstijdvereisten van de organisatie. |   2   | D/V  |
| 4.1.5 | Verifieer dat AI-taken met hoog risico worden uitgevoerd in hardware-geïsoleerde omgevingen (Intel TXT, AMD SVM, of speciale bare-metal nodes) met verificatie van attestatie.                                                           |   3   | D/V  |

---

## C4.2 Beveiligde Build- en Deployment-pijplijnen

Zorg voor cryptografische integriteit en beveiliging van de toeleveringsketen door middel van reproduceerbare builds en ondertekende artefacten.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Controleer of infrastructuur-als-code wordt gescand met tools (tfsec, Checkov of Terrascan) bij elke commit, waarbij merges worden geblokkeerd bij CRITISCHE of HOGE ernst bevindingen.                              |   1   | D/V  |
| 4.2.2 | Verifieer dat container-builds reproduceerbaar zijn met identieke SHA256-hashes over builds heen en genereer SLSA Level 3 herkomstverklaringen ondertekend met Sigstore.                                             |   1   | D/V  |
| 4.2.3 | Verifieer dat containerafbeeldingen CycloneDX- of SPDX-SBOM's insluiten en met Cosign zijn ondertekend vóór het pushen naar het register, waarbij niet-ondertekende afbeeldingen bij implementatie worden afgewezen. |   2   | D/V  |
| 4.2.4 | Controleer of CI/CD-pijplijnen OIDC-tokens gebruiken van HashiCorp Vault, AWS IAM-rollen of Azure Managed Identity met leeftijden die de limieten van het organisatiebeveiligingsbeleid niet overschrijden.          |   2   | D/V  |
| 4.2.5 | Verifieer dat Cosign-handtekeningen en SLSA-herkomst worden gevalideerd tijdens het implementatieproces vóór de uitvoering van de container en dat verificatiefouten ertoe leiden dat de implementatie mislukt.      |   2   | D/V  |
| 4.2.6 | Controleer of bouwomgevingen draaien in tijdelijke containers of virtuele machines zonder persistent opslag en met netwerkisolatie van productie VPC's.                                                              |   2   | D/V  |

---

## C4.3 Netwerkbeveiliging & Toegangscontrole

Implementeer zero-trust netwerken met standaard-weigerbeleid en versleutelde communicatie.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Controleer of Kubernetes NetworkPolicies of een gelijkwaardige oplossing standaard-ingang/-uitgang weigert met expliciete toestemmingsregels voor vereiste poorten (443, 8080, enz.).                                         |   1   | D/V  |
| 4.3.2 | Controleer of SSH (poort 22), RDP (poort 3389) en cloud metadata-eindpunten (169.254.169.254) zijn geblokkeerd of certificaatgebaseerde authenticatie vereisen.                                                               |   1   | D/V  |
| 4.3.3 | Controleer of het uitgaande verkeer wordt gefilterd via HTTP/HTTPS-proxy's (Squid, Istio of cloud NAT-gateways) met domeintoegangslisten en dat geblokkeerde verzoeken worden gelogd.                                         |   2   | D/V  |
| 4.3.4 | Controleer of de communicatie tussen services gebruikmaakt van wederzijdse TLS met certificaten die worden geroteerd volgens het organisatietbeleid en dat certificaatvalidatie wordt afgedwongen (geen skip-verify vlaggen). |   2   | D/V  |
| 4.3.5 | Controleer of de AI-infrastructuur draait in toegewijde VPC's/VNets zonder directe internettoegang en alleen communiceert via NAT-gateways of bastionhosts.                                                                   |   2   | D/V  |

---

## C4.4 Geheimen- en Cryptografisch Sleutelbeheer

Bescherm referenties via hardware-ondersteunde opslag en geautomatiseerde rotatie met zero-trust toegang.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Verifieer dat geheimen worden opgeslagen in HashiCorp Vault, AWS Secrets Manager, Azure Key Vault of Google Secret Manager met versleuteling in rust met behulp van AES-256.                        |   1   | D/V  |
| 4.4.2 | Verifieer dat cryptografische sleutels worden gegenereerd in FIPS 140-2 Level 2 HSM's (AWS CloudHSM, Azure Dedicated HSM) met sleutelrotatie volgens het cryptografische beleid van de organisatie. |   1   | D/V  |
| 4.4.3 | Controleer of het roteren van geheimen is geautomatiseerd met een zero-downtime implementatie en onmiddellijke rotatie die wordt geactiveerd door personeelswijzigingen of beveiligingsincidenten.  |   2   | D/V  |
| 4.4.4 | Controleer of containerafbeeldingen worden gescand met tools (GitLeaks, TruffleHog of detect-secrets) die builds blokkeren die API-sleutels, wachtwoorden of certificaten bevatten.                 |   2   | D/V  |
| 4.4.5 | Verifieer dat toegang tot productiesecret met MFA met hardwaretokens (YubiKey, FIDO2) vereist is en wordt vastgelegd via onveranderlijke auditlogs met gebruikersidentiteiten en tijdstempels.      |   2   | D/V  |
| 4.4.6 | Controleer of geheimen worden geïnjecteerd via Kubernetes-secrets, gekoppelde volumes of init-containers en zorg ervoor dat geheimen nooit worden ingebed in omgevingsvariabelen of images.         |   2   | D/V  |

---

## C4.5 AI-werkbelasting Sandboxen & Validatie

Isoleer onbetrouwbare AI-modellen in beveiligde sandboxes met uitgebreide gedragsanalyse.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.5.1 | Verifieer dat externe AI-modellen worden uitgevoerd in gVisor, microVMs (zoals Firecracker, CrossVM) of Docker-containers met de opties --security-opt=no-new-privileges en --read-only.                     |   1   | D/V  |
| 4.5.2 | Controleer of sandbox-omgevingen geen netwerkverbinding hebben (--network=none) of alleen localhost-toegang met alle externe verzoeken geblokkeerd door iptables-regels.                                     |   1   | D/V  |
| 4.5.3 | Verifieer dat de validatie van het AI-model geautomatiseerde red-team tests omvat met door de organisatie gedefinieerde testdekking en gedragsanalyse voor het detecteren van achterdeurtjes.                |   2   | D/V  |
| 4.5.4 | Controleer of voordat een AI-model naar productie wordt gebracht, de sandbox-resultaten cryptografisch zijn ondertekend door geautoriseerd beveiligingspersoneel en opgeslagen in onveranderlijke auditlogs. |   2   | D/V  |
| 4.5.5 | Controleer of sandboxomgevingen worden verwijderd en opnieuw worden aangemaakt vanuit golden images tussen evaluaties, met volledige opschoning van het bestandssysteem en het geheugen.                     |   2   | D/V  |

---

## C4.6 Beveiligingsmonitoring van de infrastructuur

Continu continu scannen en monitoren van infrastructuur met geautomatiseerde herstelacties en realtime waarschuwingen.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Verifieer dat containerafbeeldingen worden gescand volgens de organisatorische schema's, waarbij CRITIEKE kwetsbaarheden de implementatie blokkeren op basis van organisatorische risico-drempels.                        |   1   | D/V  |
| 4.6.2 | Verifieer dat de infrastructuur voldoet aan CIS Benchmarks of NIST 800-53-controles met organisatorisch gedefinieerde compliancedrempels en geautomatiseerde herstelmaatregelen voor gefaalde controles.                  |   1   | D/V  |
| 4.6.3 | Controleer of kwetsbaarheden met hoge ernst worden gepatcht volgens de tijdlijnen van het risicobeheer van de organisatie, met noodprocedures voor actief misbruikte CVE's.                                               |   2   | D/V  |
| 4.6.4 | Verifieer dat beveiligingswaarschuwingen integreren met SIEM-platforms (Splunk, Elastic of Sentinel) met behulp van CEF- of STIX/TAXII-formaten met geautomatiseerde verrijking.                                          |   2   |  V   |
| 4.6.5 | Controleer of infrastructuurmetingen worden geëxporteerd naar monitoringsystemen (Prometheus, DataDog) met SLA-dashboards en rapportages voor het management.                                                             |   3   |  V   |
| 4.6.6 | Verifieer dat configuratie-afwijkingen worden gedetecteerd met behulp van tools (Chef InSpec, AWS Config) volgens de monitorvereisten van de organisatie, met automatische terugrol voor niet-geautoriseerde wijzigingen. |   2   | D/V  |

---

## C4.7 AI-infrastructuurbronnenbeheer

Voorkom aanvallen door uitputting van bronnen en zorg voor eerlijke toewijzing van bronnen via quota en monitoring.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Verifieer dat het gebruik van GPU/TPU wordt gemonitord met waarschuwingen die worden geactiveerd bij door de organisatie vastgestelde drempels, en dat automatische schaalvergroting of load balancing wordt geactiveerd op basis van capaciteitsbeheerbeleid. |   1   | D/V  |
| 4.7.2 | Verifieer dat AI-werklastmetingen (inference-latentie, doorvoer, foutpercentages) worden verzameld volgens de monitoringvereisten van de organisatie en worden gecorreleerd met het gebruik van de infrastructuur.                                             |   1   | D/V  |
| 4.7.3 | Controleer of Kubernetes ResourceQuotas of een equivalent individuele workloads beperken volgens de organisatorische beleidsregels voor resourceallocatie met harde limieten die worden afgedwongen.                                                           |   2   | D/V  |
| 4.7.4 | Controleer of kostenbewaking de uitgaven per werklast/huurder bijhoudt met waarschuwingen op basis van organisatorische budgetdrempels en geautomatiseerde controles voor budgetoverschrijdingen.                                                              |   2   |  V   |
| 4.7.5 | Controleer of capaciteitsplanning gebruikmaakt van historische gegevens met organisatorisch gedefinieerde forecastperioden en geautomatiseerde resourcevoorziening op basis van vraagpatronen.                                                                 |   3   |  V   |
| 4.7.6 | Verifieer dat resource-uitputting circuit breakers activeert volgens de organisatorische responsvereisten, inclusief snelheidsbeperking op basis van capaciteitsbeleid en werklastisolatie.                                                                    |   2   | D/V  |

---

## C4.8 Omgevingsscheiding en Promotiebeheersmaatregelen

Handhaaf strikte omgevingsgrenzen met geautomatiseerde promotiepoorten en beveiligingsvalidatie.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Controleer of dev/test/prod-omgevingen draaien in afzonderlijke VPC's/VNets zonder gedeelde IAM-rollen, beveiligingsgroepen of netwerkconnectiviteit.                                                            |   1   | D/V  |
| 4.8.2 | Verifieer dat omgevingspromotie goedkeuring vereist van organisatorisch gedefinieerd bevoegd personeel met cryptografische handtekeningen en onveranderlijke auditsporen.                                        |   1   | D/V  |
| 4.8.3 | Controleer of productiesystemen SSH-toegang blokkeren, debug-eindpunten uitschakelen en wijzigingsverzoeken vereisen met organisatorische voorafgaande kennisgevingsvereisten, behalve bij noodgevallen.         |   2   | D/V  |
| 4.8.4 | Verifieer dat wijzigingen in infrastructure-as-code peer review vereisen met geautomatiseerd testen en beveiligingsscans voordat ze worden samengevoegd met de main branch.                                      |   2   | D/V  |
| 4.8.5 | Controleer of niet-productiegegevens zijn geanonimiseerd volgens de privacyvereisten van de organisatie, synthetische datageneratie, of volledige gegevensmaskering met verificatie van het verwijderen van PII. |   2   | D/V  |
| 4.8.6 | Controleer of promotiemijlpalen geautomatiseerde beveiligingstests bevatten (SAST, DAST, container scanning) waarbij goedkeuring vereist is zonder CRITISCHE bevindingen.                                        |   2   | D/V  |

---

## C4.9 Infrastructuur Back-up & Herstel

Zorg voor infrastructuurweerbaarheid door middel van geautomatiseerde back-ups, geteste herstelprocedures en rampenherstelmogelijkheden.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Controleer of infrastructuurconfiguraties worden geback-upt volgens de organisatorische back-upschema's naar geografisch gescheiden regio's met implementatie van de 3-2-1 back-upstrategie.             |   1   | D/V  |
| 4.9.2 | Verifieer dat back-upsysteem in geïsoleerde netwerken draaien met afzonderlijke inloggegevens en luchtgescheiden opslag voor bescherming tegen ransomware.                                               |   2   | D/V  |
| 4.9.3 | Verifieer dat herstelprocedures worden getest en gevalideerd via geautomatiseerde tests volgens de organisatieschema's, waarbij de RTO- en RPO-doelstellingen voldoen aan de organisatorische vereisten. |   2   |  V   |
| 4.9.4 | Controleer of het disaster recovery plan AI-specifieke runbooks bevat met herstel van modelgewichten, herbouwen van GPU-clusters en in kaart brengen van servicedependencies.                            |   3   |  V   |

---

## C4.10 Infrastructuurnaleving & Governance

Handhaaf regelgevingsconformiteit door middel van continue beoordeling, documentatie en geautomatiseerde controles.

|   #    | Description                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Controleer of de infrastructuurconformiteit wordt beoordeeld volgens organisatorische planningen aan de hand van SOC 2-, ISO 27001- of FedRAMP-controles met geautomatiseerde bewijsverzameling.      |   2   | D/V  |
| 4.10.2 | Controleer of de infrastructuurdocumentatie netwerkdiagrammen, gegevensstroomkaarten en dreigingsmodellen bevat die zijn bijgewerkt volgens de vereisten van het wijzigingsbeheer van de organisatie. |   2   |  V   |
| 4.10.3 | Verifieer dat infrastructuurwijzigingen een geautomatiseerde beoordeling van de nalevingsimpact ondergaan met goedkeuringsworkflows voor hoge-risico wijzigingen.                                     |   3   | D/V  |

---

## C4.11 AI Hardware Beveiliging

Beveilig AI-specifieke hardwarecomponenten inclusief GPU's, TPU's en gespecialiseerde AI-versnellers.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Controleer of de firmware van AI-versnellers (GPU BIOS, TPU-firmware) is geverifieerd met cryptografische handtekeningen en bijgewerkt volgens de patchmanagementtijdlijnen van de organisatie.   |   2   | D/V  |
| 4.11.2 | Controleer of vóór het uitvoeren van de werklast de integriteit van de AI-versneller wordt gevalideerd door middel van hardware-attestatie met TPM 2.0, Intel TXT of AMD SVM.                     |   2   | D/V  |
| 4.11.3 | Controleer of het GPU-geheugen is geïsoleerd tussen workloads door gebruik te maken van SR-IOV, MIG (Multi-Instance GPU), of equivalent hardwarepartitionering met geheugensanering tussen taken. |   2   | D/V  |
| 4.11.4 | Controleer of de AI-hardwareleveringsketen herkomstverificatie bevat met fabrikantcertificaten en validatie van manipulatiebestendige verpakkingen.                                               |   3   |  V   |
| 4.11.5 | Controleer of hardware security modules (HSM's) AI-modelgewichten en cryptografische sleutels beschermen met FIPS 140-2 Level 3 of Common Criteria EAL4+ certificering.                           |   3   | D/V  |

---

## C4.12 Edge- en Gedistribueerde AI-Infrastructuur

Veilige gedistribueerde AI-implementaties, waaronder edge computing, gefedereerd leren en multi-site architecturen.

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.12.1 | Controleer of edge AI-apparaten zich authenticeren bij de centrale infrastructuur met behulp van mutual TLS, waarbij apparaatcertificaten worden vervangen volgens het certificaatbeheerbeleid van de organisatie. |   2   | D/V  |
| 4.12.2 | Controleer of randapparaten een beveiligde opstart (secure boot) implementeren met geverifieerde handtekeningen en rollback-bescherming om firmware downgrades te voorkomen.                                       |   2   | D/V  |
| 4.12.3 | Controleer of gedistribueerde AI-coördinatie gebruikmaakt van door Byzantijnse fouttolerantie ondersteunde consensusalgoritmen met validatie van deelnemers en detectie van kwaadaardige knooppunten.              |   3   | D/V  |
| 4.12.4 | Verifieer dat de communicatie van edge naar cloud bandbreedtebeperking, datacompressie en mogelijkheden voor offline werking met veilige lokale opslag omvat.                                                      |   3   | D/V  |

---

## C4.13 Multi-Cloud- en Hybride Infrastructuurbeveiliging

Beveilig AI-werklasten over meerdere cloudproviders en hybride cloud-on-premises implementaties.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Controleer of multi-cloud AI-implementaties cloud-agnostische identiteitsfederatie (OIDC, SAML) gebruiken met gecentraliseerd beleidsbeheer over providers heen.                                           |   2   | D/V  |
| 4.13.2 | Controleer of cross-cloud gegevensoverdracht end-to-end encryptie gebruikt met door de klant beheerde sleutels en dataverblijfscontroles die per jurisdictie worden afgedwongen.                           |   2   | D/V  |
| 4.13.3 | Controleer of hybrid cloud AI-workloads consistente beveiligingsbeleid implementeren in zowel on-premise als cloudomgevingen met uniforme monitoring en waarschuwingen.                                    |   2   | D/V  |
| 4.13.4 | Controleer of het voorkomen van cloud vendor lock-in voorzieningen omvat zoals draagbare infrastructuur-als-code, gestandaardiseerde API's en gegevensexportmogelijkheden met tools voor formaatconversie. |   3   |  V   |
| 4.13.5 | Verifieer dat multi-cloud kostenoptimalisatie beveiligingscontroles omvat die het verspreiden van middelen voorkomen, evenals ongeautoriseerde kosten voor gegevensoverdracht tussen clouds.               |   3   |  V   |

---

## C4.14 Infrastructuurautomatisering & GitOps-beveiliging

Beveilig automatiseringspijplijnen voor infrastructuur en GitOps-workflows voor het beheer van AI-infrastructuur.

|   #    | Description                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.14.1 | Controleer of GitOps-repositories ondertekende commits vereisen met GPG-sleutels en branch-beschermingsregels bevatten die directe pushes naar hoofdbranches voorkomen.                                                  |   2   | D/V  |
| 4.14.2 | Controleer of infrastructuurautomatisering driftdetectie omvat met automatische herstel- en terugrolmogelijkheden die worden geactiveerd volgens de organisatorische responsvereisten voor ongeautoriseerde wijzigingen. |   2   | D/V  |
| 4.14.3 | Controleer of geautomatiseerde infrastructuurvoorziening beveiligingsbeleidvalidatie omvat met uitrolblokkering voor niet-conforme configuraties.                                                                        |   2   | D/V  |
| 4.14.4 | Verifieer dat infrastructuurautomatiseringsgeheimen worden beheerd via externe geheimoperatoren (External Secrets Operator, Bank-Vaults) met automatische rotatie.                                                       |   2   | D/V  |
| 4.14.5 | Zorg ervoor dat zelfherstellende infrastructuur beveiligingsgebeurtenis-correlatie omvat met geautomatiseerde incidentrespons en workflows voor het informeren van belanghebbenden.                                      |   3   |  V   |

---

## C4.15 Kwantumbestendige Infrastructuurbeveiliging

Bereid AI-infrastructuur voor op kwantumcomputing-bedreigingen door middel van post-kwantumcryptografie en kwantumveilige protocollen.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifieer dat de AI-infrastructuur NIST-goedgekeurde post-quantum cryptografische algoritmen (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) implementeert voor sleuteluitwisseling en digitale handtekeningen. |   3   | D/V  |
| 4.15.2 | Controleer of quantum key distribution (QKD) systemen worden geïmplementeerd voor hoogbeveiligde AI-communicatie met kwantumveilige sleutelbeheerprotocollen.                                                  |   3   | D/V  |
| 4.15.3 | Verifieer dat cryptografische wendbaarheidskaders snelle migratie naar nieuwe post-kwantumalgoritmen mogelijk maken met geautomatiseerde rotatie van certificaten en sleutels.                                 |   3   | D/V  |
| 4.15.4 | Verifieer dat kwantumdreigingsmodellering de kwetsbaarheid van AI-infrastructuur voor kwantumaanvallen beoordeelt met gedocumenteerde migratietijdlijnen en risico-evaluaties.                                 |   3   |  V   |
| 4.15.5 | Verifieer dat hybride klassieke-kwantumcryptografische systemen verdediging-in-diepte bieden tijdens de kwantumovergangsperiode met prestatiebewaking.                                                         |   3   | D/V  |

---

## C4.16 Vertrouwelijk Computeren & Beveiligde Enclaves

Bescherm AI-werklasten en modelgewichten met behulp van op hardware gebaseerde vertrouwde uitvoeringsomgevingen en vertrouwelijke computeringstechnologieën.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Verifieer dat gevoelige AI-modellen worden uitgevoerd binnen Intel SGX-behuizingen, AMD SEV-SNP of ARM TrustZone met versleuteld geheugen en attestatieverificatie.                        |   3   | D/V  |
| 4.16.2 | Controleer of vertrouwelijke containers (Kata Containers, gVisor met vertrouwelijke computing) AI-werkbelastingen isoleren met hardware-afgedwongen geheugenencryptie.                     |   3   | D/V  |
| 4.16.3 | Verifieer dat remote attestation de integriteit van de enclave valideert voordat AI-modellen worden geladen, met cryptografisch bewijs van de authenticiteit van een uitvoeringsomgeving.  |   3   | D/V  |
| 4.16.4 | Verifieer dat vertrouwelijke AI-inferentiediensten modelextractie voorkomen door middel van versleutelde berekeningen met verzegelde modelgewichten en beschermde uitvoering.              |   3   | D/V  |
| 4.16.5 | Verifieer dat de orkestratie van de vertrouwde uitvoeringomgeving de levenscyclus van de beveiligde enclave beheert met behulp van remote attestation en versleutelde communicatiekanalen. |   3   | D/V  |
| 4.16.6 | Verifieer dat beveiligde multi-party computation (SMPC) gezamenlijke AI-training mogelijk maakt zonder individuele datasets of modelparameters bloot te stellen.                           |   3   | D/V  |

---

## C4.17 Zero-Knowledge Infrastructuur

Implementeer zero-knowledge bewijs systemen voor privacybeschermende AI-verificatie en authenticatie zonder gevoelige informatie prijs te geven.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Verifieer dat zero-knowledge proofs (ZK-SNARKs, ZK-STARKs) de integriteit van AI-modellen en de herkomst van training verifiëren zonder de modelgewichten of trainingsgegevens bloot te geven. |   3   | D/V  |
| 4.17.2 | Verifieer dat op ZK gebaseerde authenticatiesystemen privacybeschermende gebruikersverificatie voor AI-diensten mogelijk maken zonder identiteit gerelateerde informatie prijs te geven.       |   3   | D/V  |
| 4.17.3 | Controleer of private set intersection (PSI)-protocollen veilige gegevensmatching mogelijk maken voor federatieve AI zonder individuele datasets bloot te stellen.                             |   3   | D/V  |
| 4.17.4 | Verifieer dat zero-knowledge machine learning (ZKML) systemen verifieerbare AI-afleidingen mogelijk maken met cryptografisch bewijs van correcte berekening.                                   |   3   | D/V  |
| 4.17.5 | Verifieer dat ZK-rollups schaalbare, privacybeschermende AI-transactieprocessing bieden met batchverificatie en verminderde rekenbelasting.                                                    |   3   | D/V  |

---

## C4.18 Preventie van zij-kanaal aanvallen

Bescherm AI-infrastructuur tegen timing-, stroom-, elektromagnetische- en cache-gebaseerde zijkanaalaanvallen die gevoelige informatie kunnen lekken.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Controleer of de AI-inferentietiming wordt genormaliseerd met behulp van constant-time algoritmen en padding om timinggebaseerde modelextractie-aanvallen te voorkomen. |   3   | D/V  |
| 4.18.2 | Controleer of de bescherming tegen vermogensanalyse ruisinjectie, filtering van de voedingslijn en gerandomiseerde uitvoeringspatronen voor AI-hardware omvat.          |   3   | D/V  |
| 4.18.3 | Controleer of cache-gebaseerde side-channel mitigatie gebruikmaakt van cache-partitionering, randomisatie en flush-instructies om informatielekken te voorkomen.        |   3   | D/V  |
| 4.18.4 | Verifieer dat bescherming tegen elektromagnetische straling afscherming, signaalfiltering en gerandomiseerde verwerking omvat om TEMPEST-stijl aanvallen te voorkomen.  |   3   | D/V  |
| 4.18.5 | Controleer of microarchitecturale side-channel verdedigingsmechanismen speculatieve uitvoeringscontroles en geheugen toegangs patroon verhulling omvatten.              |   3   | D/V  |

---

## C4.19 Neuromorfe & Gespecialiseerde AI Hardwarebeveiliging

Beveilig opkomende AI-hardwarearchitecturen, waaronder neuromorfe chips, FPGA's, op maat gemaakte ASIC's en optische computersystemen.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.19.1 | Verifieer dat de beveiliging van neuromorfe chips spiekpatroonversleuteling, bescherming van synaptische gewichten en hardwaregebaseerde validatie van leerregels omvat. |   3   | D/V  |
| 4.19.2 | Controleer of FPGA-gebaseerde AI-versnellers bitstreamversleuteling, anti-tampermechanismen en veilige configuratielading met geauthenticeerde updates implementeren.    |   3   | D/V  |
| 4.19.3 | Verifieer dat aangepaste ASIC-beveiliging on-chip beveiligingsprocessors, hardware root of trust en veilige sleutelopslag met sabotage-detectie omvat.                   |   3   | D/V  |
| 4.19.4 | Verifieer dat optische computersystemen kwantumveilige optische encryptie, veilige fotonische schakeling en beschermde optische signaalverwerking implementeren.         |   3   | D/V  |
| 4.19.5 | Controleer of hybride analoog-digitale AI-chips veilige analoge berekeningen, beveiligde opslag van gewichten en geverifieerde analoog-naar-digitaal conversie bevatten. |   3   | D/V  |

---

## C4.20 Privacy-beschermende rekeninfrastructuur

Implementeer infrastructuurcontroles voor privacybewarende berekeningen om gevoelige gegevens te beschermen tijdens AI-verwerking en -analyse.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Verifieer dat de homomorfe encryptie-infrastructuur versleutelde berekeningen op gevoelige AI-werklasten mogelijk maakt met cryptografische integriteitsverificatie en prestatiebewaking.            |   3   | D/V  |
| 4.20.2 | Verifieer dat systemen voor privé-informatieterugwinning databasequery's mogelijk maken zonder querypatronen te onthullen, met cryptografische bescherming van toegangspatronen.                     |   3   | D/V  |
| 4.20.3 | Verifieer dat beveiligde multi-party computation-protocollen privacybeschermende AI-inferentie mogelijk maken zonder individuele invoer of tussentijdse berekeningen bloot te geven.                 |   3   | D/V  |
| 4.20.4 | Controleer of privacy-behoudend sleutelbeheer gedistribueerde sleutelsgeneratie, drempelcryptografie en veilige sleutelrotatie met hardware-ondersteunde bescherming omvat.                          |   3   | D/V  |
| 4.20.5 | Verifieer dat de privacybewarende rekenprestaties worden geoptimaliseerd door middel van batching, caching en hardwareversnelling, terwijl cryptografische beveiligingsgaranties worden gehandhaafd. |   3   | D/V  |

---

## C4.15 Agent Framework Cloud-integratiebeveiliging & Hybride Implementatie

Beveiligingscontroles voor cloud-geïntegreerde agent-frameworks met hybride on-premises/cloud-architecturen.

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.15.1 | Verifieer dat cloudopslagintegratie end-to-end encryptie gebruikt met sleutels die door de agent worden beheerd.                     |   1   | D/V  |
| 4.15.2 | Controleer of de beveiligingsgrenzen van hybride implementaties duidelijk zijn gedefinieerd met versleutelde communicatiekanalen.    |   2   | D/V  |
| 4.15.3 | Controleer of de toegang tot cloudresources nul-trust verificatie bevat met continue authenticatie.                                  |   2   | D/V  |
| 4.15.4 | Verifieer dat eisen voor gegevensresidentie worden afgedwongen door cryptografische attestatie van opslaglocaties.                   |   3   | D/V  |
| 4.15.5 | Controleer of de beveiligingsbeoordelingen van de cloudprovider agent-specifieke dreigingsmodellering en risicobeoordeling omvatten. |   3   | D/V  |

---

## Referenties

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

