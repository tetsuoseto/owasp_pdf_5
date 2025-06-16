# C4 Infrastruktur, Konfiguration og Udrulningssikkerhed

## Kontrolmål

AI-infrastrukturen skal gøres robust over for privilegieoptrapning, manipulation af forsyningskæden og lateral bevægelse gennem sikker konfiguration, runtime-isolation, betroede implementeringspipelines og omfattende overvågning. Kun autoriserede, validerede infrastrukturelementer og konfigurationer når produktionen gennem kontrollerede processer, der opretholder sikkerhed, integritet og revisionssporbarhed.

Kerne sikkerhedsmål: Kun kryptografisk signerede, sårbarhedsscannede infrastruktu komponenter når produktion gennem automatiserede valideringspipelines, der håndhæver sikkerhedspolitikker og opretholder uforanderlige revisionsspor.

---

## C4.1 Kørselstidsmiljø-isolation

Forhindre containerflugt og privilegieeskalering gennem kerne-niveau isolationsprimitive og obligatoriske adgangskontroller.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Bekræft, at alle AI-containere fraskriver sig ALLE Linux-kapabiliteter undtagen CAP_SETUID, CAP_SETGID og eksplicit krævede kapabiliteter, der er dokumenteret i sikkerhedsbasislinjer.                          |   1   | D/V  |
| 4.1.2 | Bekræft, at seccomp-profiler blokerer alle systemkald undtagen dem, der er på forhånd godkendte tilladelseslister, hvor overtrædelser fører til containerens afslutning og genererer sikkerhedsalarmer.          |   1   | D/V  |
| 4.1.3 | Bekræft, at AI-arbejdsbelastninger kører med root-filsystemer, der kun kan læses, tmpfs til midlertidige data, og navngivne volumener til vedvarende data med noexec-monteringsmuligheder håndhævet.             |   2   | D/V  |
| 4.1.4 | Bekræft, at eBPF-baseret runtime-overvågning (Falco, Tetragon eller tilsvarende) opdager forsøg på privilegieeskalering og automatisk afslutter de forurenende processer inden for organisationens svartidskrav. |   2   | D/V  |
| 4.1.5 | Bekræft, at højrisiko AI-arbejdsbelastninger kører i hardware-isolerede miljøer (Intel TXT, AMD SVM eller dedikerede bare-metal noder) med attestationsverifikation.                                             |   3   | D/V  |

---

## C4.2 Sikker Bygge- og Udrulningspipeline

Sørg for kryptografisk integritet og sikkerhed i forsyningskæden gennem reproducerbare builds og signerede artefakter.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Bekræft, at infrastructure-as-code bliver scannet med værktøjer (tfsec, Checkov eller Terrascan) ved hvert commit, og at merges blokeres ved FUNDAMENTALE eller HØJE alvorlighedsgrader.        |   1   | D/V  |
| 4.2.2 | Bekræft, at container-builds er reproducerbare med identiske SHA256-hashværdier på tværs af builds, og generer SLSA Level 3 oprindelsesattester underskrevet med Sigstore.                      |   1   | D/V  |
| 4.2.3 | Bekræft, at containerbilleder indeholder CycloneDX- eller SPDX-SBOM'er og er underskrevet med Cosign inden push til registret, hvor ikke-underskrevne billeder afvises ved implementering.      |   2   | D/V  |
| 4.2.4 | Bekræft, at CI/CD-pipelines bruger OIDC-tokens fra HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med levetider, der ikke overstiger organisationens sikkerhedspolitiske grænser. |   2   | D/V  |
| 4.2.5 | Bekræft, at Cosign-signaturer og SLSA-proveniens valideres under implementeringsprocessen, inden containeren kører, og at verifikationsfejl forårsager, at implementeringen mislykkes.          |   2   | D/V  |
| 4.2.6 | Bekræft, at build-miljøer kører i flygtige containere eller virtuelle maskiner uden vedvarende lagerplads og med netværksisolering fra produktions-VPC'er.                                      |   2   | D/V  |

---

## C4.3 Netværkssikkerhed og adgangskontrol

Implementer zero-trust netværk med standard-afvisningspolitikker og krypteret kommunikation.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Bekræft, at Kubernetes NetworkPolicies eller en tilsvarende løsning implementerer standard-afvisning af indgående/udgående trafik med eksplicitte tilladelsesregler for nødvendige porte (443, 8080 osv.). |   1   | D/V  |
| 4.3.2 | Bekræft, at SSH (port 22), RDP (port 3389) og cloud metadata-endpoints (169.254.169.254) er blokeret eller kræver certifikatbaseret autentificering.                                                       |   1   | D/V  |
| 4.3.3 | Bekræft, at udgående trafik filtreres gennem HTTP/HTTPS-proxyer (Squid, Istio eller cloud NAT-gateways) med domænetilladelister, og at blokerede forespørgsler logges.                                     |   2   | D/V  |
| 4.3.4 | Bekræft, at kommunikation mellem tjenester bruger gensidig TLS med certifikater, der roteres i henhold til organisationspolitikken, og at certifikatvalidering håndhæves (uden brug af skip-verify-flag).  |   2   | D/V  |
| 4.3.5 | Bekræft, at AI-infrastrukturen kører i dedikerede VPC'er/VNet med ingen direkte internetadgang og kommunikerer udelukkende gennem NAT-gateways eller bastionværter.                                        |   2   | D/V  |

---

## C4.4 Hemmeligheder og Kryptografisk Nøglehåndtering

Beskyt legitimationsoplysninger gennem hardware-understøttet lagring og automatiseret rotation med nul-tillids adgang.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Bekræft, at hemmeligheder er gemt i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering ved hvile ved brug af AES-256.                               |   1   | D/V  |
| 4.4.2 | Bekræft, at kryptografiske nøgler genereres i FIPS 140-2 Niveau 2 HSM'er (AWS CloudHSM, Azure Dedicated HSM) med nøglerotation i overensstemmelse med den organisatoriske kryptografiske politik. |   1   | D/V  |
| 4.4.3 | Bekræft, at hemmelighedsrotation er automatiseret med implementering uden nedetid og øjeblikkelig rotation udløst af personaleforandringer eller sikkerhedshændelser.                             |   2   | D/V  |
| 4.4.4 | Sørg for, at containerbilleder scannes med værktøjer (GitLeaks, TruffleHog eller detect-secrets), der blokerer builds, som indeholder API-nøgler, adgangskoder eller certifikater.                |   2   | D/V  |
| 4.4.5 | Bekræft, at adgang til produktionshemmeligheder kræver MFA med hardwaretokens (YubiKey, FIDO2) og registreres i uforanderlige revisionslogfiler med brugeridentiteter og tidsstempler.            |   2   | D/V  |
| 4.4.6 | Sørg for, at hemmeligheder injiceres via Kubernetes-hemmeligheder, monterede volumener eller init-containere, og sikre, at hemmeligheder aldrig er indlejret i miljøvariabler eller billeder.     |   2   | D/V  |

---

## C4.5 AI Arbejdsbelastningssandkasse og Validering

Isolér ikke-pålidelige AI-modeller i sikre sandkasser med omfattende adfærdsanalyse.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.5.1 | Sørg for, at eksterne AI-modeller kører i gVisor, microVMs (såsom Firecracker, CrossVM) eller Docker-containere med --security-opt=no-new-privileges og --read-only flag.                  |   1   | D/V  |
| 4.5.2 | Bekræft, at sandbox-miljøer ikke har netværksforbindelse (--network=none) eller kun lokal adgang med alle eksterne forespørgsler blokeret via iptables-regler.                             |   1   | D/V  |
| 4.5.3 | Bekræft, at validering af AI-modeller inkluderer automatiseret red-team-testning med organisationsdefineret testdækning og adfærdsanalyse for bagdørsdetektion.                            |   2   | D/V  |
| 4.5.4 | Bekræft, at før en AI-model promoveres til produktion, er dens sandbox-resultater kryptografisk underskrevet af autoriseret sikkerhedspersonale og gemt i uforanderlige revisionslogfiler. |   2   | D/V  |
| 4.5.5 | Bekræft, at sandkassemiljøer bliver ødelagt og genoprettet fra gyldne billeder mellem evalueringer med fuldstændig oprydning af filsystem og hukommelse.                                   |   2   | D/V  |

---

## C4.6 Infrastruktur Sikkerhedsovervågning

Kontinuerligt overvåg og scan infrastrukturen med automatiseret udbedring og realtidsalarmering.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Bekræft, at containerbilleder bliver scannet i henhold til organisationens tidsplaner, hvor KRITISKE sårbarheder blokerer for implementering baseret på organisationens risikogrænser.                |   1   | D/V  |
| 4.6.2 | Verificer, at infrastrukturen overholder CIS Benchmarks eller NIST 800-53 kontroller med organisatorisk definerede overholdelsesgrænser og automatiseret udbedring for mislykkede kontrolpunkter.     |   1   | D/V  |
| 4.6.3 | Bekræft, at sårbarheder med HØJ alvorlighedsgrad bliver rettet i henhold til organisationens risikostyringstidsplaner med nødprocedurer for aktivt udnyttede CVE'er.                                  |   2   | D/V  |
| 4.6.4 | Bekræft, at sikkerhedsalarmer integreres med SIEM-platforme (Splunk, Elastic eller Sentinel) ved brug af CEF- eller STIX/TAXII-formater med automatiseret berigelse.                                  |   2   |  V   |
| 4.6.5 | Bekræft, at infrastrukturmetrics eksporteres til overvågningssystemer (Prometheus, DataDog) med SLA-dashboard og ledelsesrapportering.                                                                |   3   |  V   |
| 4.6.6 | Bekræft, at konfigurationsafvigelse opdages ved hjælp af værktøjer (Chef InSpec, AWS Config) i henhold til organisationens overvågningskrav med automatisk tilbagerulning af uautoriserede ændringer. |   2   | D/V  |

---

## C4.7 AI-infrastruktur Ressourcehåndtering

Forhindre ressourceudtømningangreb og sikre retfærdig ressourceallokering gennem kvoter og overvågning.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.7.1 | Bekræft, at GPU-/TPU-udnyttelse overvåges med alarmer, der udløses ved organisatorisk definerede grænser, og at automatisk skalering eller belastningsfordeling aktiveres baseret på kapacitetsstyringspolitikker. |   1   | D/V  |
| 4.7.2 | Bekræft, at AI-arbejdsbelastningsmålinger (inferenzlatens, gennemløb, fejlrater) indsamles i overensstemmelse med organisationens overvågningskrav og korreleres med infrastrukturudnyttelse.                      |   1   | D/V  |
| 4.7.3 | Bekræft, at Kubernetes ResourceQuotas eller tilsvarende begrænser individuelle arbejdsbelastninger i henhold til organisatoriske ressourcetildelingspolitikker med håndhævede hårde grænser.                       |   2   | D/V  |
| 4.7.4 | Bekræft, at omkostningsovervågning sporer forbruget pr. arbejdsbyrde/lejer med alarmer baseret på organisatoriske budgetgrænser og automatiserede kontroller for budgetoverskridelser.                             |   2   |  V   |
| 4.7.5 | Bekræft, at kapacitetsplanlægning bruger historiske data med organisatorisk definerede forecastperioder og automatiseret ressourceforsyning baseret på efterspørgselsmønstre.                                      |   3   |  V   |
| 4.7.6 | Bekræft, at ressourceudmattelse udløser afbrydere i henhold til organisationens responskrav, inklusive hastighedsbegrænsning baseret på kapacitetsretningslinjer og arbejdsbelastningsisolation.                   |   2   | D/V  |

---

## C4.8 Adskillelse af miljøer og kontrol med promovering

Håndhæv strenge miljøgrænser med automatiserede promotionsporte og sikkerhedsvalidering.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Bekræft, at dev/test/prod-miljøer kører i separate VPC'er/VNets uden delte IAM-roller, sikkerhedsgrupper eller netværksforbindelser.                                                                                              |   1   | D/V  |
| 4.8.2 | Bekræft, at miljøfremme kræver godkendelse fra organisatorisk defineret autoriseret personale med kryptografiske signaturer og uforanderlige revisionsspor.                                                                       |   1   | D/V  |
| 4.8.3 | Bekræft, at produktionsmiljøer blokerer SSH-adgang, deaktiverer debug-endepunkter og kræver ændringsanmodninger med organisatoriske krav om forudgående varsel, undtagen i nødsituationer.                                        |   2   | D/V  |
| 4.8.4 | Bekræft, at ændringer i infrastruktur som kode kræver peer review med automatiseret testning og sikkerhedsscanning, før de flettes til hovedbranch.                                                                               |   2   | D/V  |
| 4.8.5 | Bekræft, at ikke-produktionsdata er anonymiseret i overensstemmelse med organisatoriske privatlivskrav, syntetisk datagenerering eller fuldstændig datamaskering med fjernelse af personhenførbare oplysninger (PHI) verificeret. |   2   | D/V  |
| 4.8.6 | Bekræft, at promotionsportaler inkluderer automatiserede sikkerhedstests (SAST, DAST, container-scanning) med krav om nul KRITISKE fund for godkendelse.                                                                          |   2   | D/V  |

---

## C4.9 Infrastruktur Backup og Gendannelse

Sikre infrastrukturopbygningens robusthed gennem automatiserede sikkerhedskopier, testede genoprettelsesprocedurer og katastrofeberedskab.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Bekræft, at infrastrukturkonfigurationer sikkerhedskopieres i henhold til organisationens sikkerhedskopieringsplaner til geografisk adskilte regioner med implementering af 3-2-1 sikkerhedskopieringsstrategi. |   1   | D/V  |
| 4.9.2 | Bekræft, at backupsystemer kører i isolerede netværk med separate legitimationsoplysninger og luftadskilt lagring for beskyttelse mod ransomware.                                                               |   2   | D/V  |
| 4.9.3 | Bekræft, at genoprettelsesprocedurer testes og valideres gennem automatiseret testning i henhold til organisatoriske tidsplaner med RTO- og RPO-mål, der opfylder organisationens krav.                         |   2   |  V   |
| 4.9.4 | Bekræft, at katastrofegendannelse inkluderer AI-specifikke kørebøger med gendannelse af modelvægte, genopbygning af GPU-klynger og kortlægning af tjenesteafhængigheder.                                        |   3   |  V   |

---

## C4.10 Infrastrukturoverholdelse og styring

Oprethold overholdelse af regler gennem løbende vurdering, dokumentation og automatiserede kontroller.

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Bekræft, at infrastrukturens overholdelse vurderes i henhold til organisatoriske tidsplaner mod SOC 2, ISO 27001 eller FedRAMP-kontroller med automatiseret indsamling af beviser. |   2   | D/V  |
| 4.10.2 | Bekræft, at infrastruktur-dokumentationen indeholder netværksdiagrammer, dataflow-kort og trusselsmodeller opdateret i henhold til organisationens krav til ændringsstyring.       |   2   |  V   |
| 4.10.3 | Bekræft, at infrastrukturelle ændringer gennemgår automatiseret vurdering af overholdelsespåvirkning med regulatoriske godkendelsesarbejdsgange for højrisikomodifikationer.       |   3   | D/V  |

---

## C4.11 AI Hardware-sikkerhed

Sikre AI-specifikke hardwarekomponenter, herunder GPU'er, TPU'er og specialiserede AI-acceleratorer.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Bekræft, at AI-acceleratorens firmware (GPU BIOS, TPU-firmware) er verificeret med kryptografiske signaturer og opdateret i henhold til organisationens patchhåndterings-tidsplaner.              |   2   | D/V  |
| 4.11.2 | Bekræft, at AI-acceleratorens integritet valideres før arbejdsbelastningens udførelse ved hjælp af hardwareattestation med TPM 2.0, Intel TXT eller AMD SVM.                                      |   2   | D/V  |
| 4.11.3 | Bekræft, at GPU-hukommelse er isoleret mellem arbejdsbelastninger ved brug af SR-IOV, MIG (Multi-Instance GPU) eller tilsvarende hardwarepartitionering med hukommelsessanitering mellem opgaver. |   2   | D/V  |
| 4.11.4 | Bekræft, at AI-hardwareforsyningskæden inkluderer oprindelsesverifikation med producentcertifikater og validering af manipulationssikkert emballage.                                              |   3   |  V   |
| 4.11.5 | Bekræft, at hardware-sikkerhedsmoduler (HSM'er) beskytter AI-modelvægte og kryptografiske nøgler med FIPS 140-2 Niveau 3 eller Common Criteria EAL4+ certificering.                               |   3   | D/V  |

---

## C4.12 Edge- og Distribueret AI-infrastruktur

Sikre distribuerede AI-implementeringer inklusive edge computing, fødereret læring og flersite-arkitekturer.

|   #    | Description                                                                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Bekræft, at edge AI-enheder autentificerer til central infrastruktur ved hjælp af gensidig TLS med enhedscertifikater, der roteres i overensstemmelse med den organisatoriske certifikatstyringspolitik. |   2   | D/V  |
| 4.12.2 | Sørg for, at edge-enheder implementerer secure boot med verificerede signaturer og rollback-beskyttelse, der forhindrer firmware-nedgraderingsangreb.                                                    |   2   | D/V  |
| 4.12.3 | Bekræft, at distribueret AI-koordinering bruger byzantinsk fejltolerante konsensusalgoritmer med deltager-validering og ondsindet node-detektion.                                                        |   3   | D/V  |
| 4.12.4 | Bekræft, at edge-til-cloud-kommunikation omfatter båndbreddebegrænsning, datakomprimering og offline-drift med sikre lokale lagringsmuligheder.                                                          |   3   | D/V  |

---

## C4.13 Multi-Cloud og Hybrid Infrastruktur Sikkerhed

Sikre AI-arbejdsbelastninger på tværs af flere cloud-udbydere og hybride cloud-on-premises implementeringer.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Bekræft, at multi-cloud AI-implementeringer bruger cloud-agnostisk identitetsfederation (OIDC, SAML) med centraliseret politikstyring på tværs af udbydere.                       |   2   | D/V  |
| 4.13.2 | Bekræft, at krydssky dataoverførsel bruger ende-til-ende-kryptering med kundestyrende nøgler, og at datalokaliseringskontroller håndhæves i henhold til jurisdiktion.             |   2   | D/V  |
| 4.13.3 | Sørg for, at hybride cloud AI-arbejdsbelastninger implementerer konsekvente sikkerhedspolitikker på tværs af lokale og cloud-miljøer med samlet overvågning og alarmering.        |   2   | D/V  |
| 4.13.4 | Bekræft, at forebyggelse af leverandørlåsning til skyen inkluderer bærbar infrastruktur-som-kode, standardiserede API'er og datalekapacitet med værktøjer til formatkonvertering. |   3   |  V   |
| 4.13.5 | Sørg for, at multi-cloud omkostningsoptimering inkluderer sikkerhedskontroller, der forhindrer ressource-spredning samt uautoriserede tvær-cloud dataoverførselsomkostninger.     |   3   |  V   |

---

## C4.14 Infrastrukturautomatisering & GitOps-sikkerhed

Sikre automatiserede infrastruktursearbejdsgange og GitOps-processer til styring af AI-infrastruktur.

|   #    | Description                                                                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Bekræft, at GitOps-repositorier kræver signerede commits med GPG-nøgler og branch-beskyttelsesregler, der forhindrer direkte push til main-branches.                                                                        |   2   | D/V  |
| 4.14.2 | Bekræft, at infrastrukturautomatisering inkluderer afvigelsesdetektion med automatiske genoprettelses- og tilbagerulningsfunktioner, der aktiveres i henhold til organisationens reaktionskrav for uautoriserede ændringer. |   2   | D/V  |
| 4.14.3 | Bekræft, at automatiseret infrastrukturprovisionering inkluderer validering af sikkerhedspolitikker med udrulningsblokering for ikke-overholdende konfigurationer.                                                          |   2   | D/V  |
| 4.14.4 | Bekræft, at hemmeligheder til infrastrukturautomatisering håndteres gennem eksterne secret operators (External Secrets Operator, Bank-Vaults) med automatisk rotation.                                                      |   2   | D/V  |
| 4.14.5 | Bekræft, at selvhelende infrastruktur inkluderer sikkerhedshændelseskorrelation med automatiseret hændelsesrespons og arbejdsflows for underretning af interessenter.                                                       |   3   |  V   |

---

## C4.15 Kvante-resistent infrastruktur sikkerhed

Forbered AI-infrastruktur til trusler fra kvantecomputing gennem post-kvante kryptografi og kvantesikre protokoller.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Bekræft, at AI-infrastrukturen implementerer NIST-godkendte post-kvante kryptografiske algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) til nøgleudveksling og digitale signaturer. |   3   | D/V  |
| 4.15.2 | Bekræft, at kvante-nøglefordelingssystemer (QKD) er implementeret til højsikkerheds AI-kommunikationer med kvantesikre nøglehåndteringsprotokoller.                                          |   3   | D/V  |
| 4.15.3 | Bekræft, at kryptografiske agilitetssystemer muliggør hurtig migrering til nye post-kvante algoritmer med automatiseret certifikat- og nøgleudskiftning.                                     |   3   | D/V  |
| 4.15.4 | Bekræft, at kvantetrusselsmodellering vurderer AI-infrastrukturens sårbarhed over for kvanteangreb med dokumenterede migrationsplaner og risikovurderinger.                                  |   3   |  V   |
| 4.15.5 | Bekræft, at hybride klassiske-kvantemæssige kryptografiske systemer tilbyder forsvar-i-dybden under kvanteovergangsperioden med ydelsesovervågning.                                          |   3   | D/V  |

---

## C4.16 Fortrolig Beregning og Sikker Indelinger

Beskyt AI-arbejdsbelastninger og modelvægt ved hjælp af hardware-baserede betroede eksekveringsmiljøer og fortrolighedsberegningsteknologier.

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Bekræft, at følsomme AI-modeller kører inden for Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med krypteret hukommelse og attestation verificering.      |   3   | D/V  |
| 4.16.2 | Bekræft, at fortrolige containere (Kata Containers, gVisor med fortrolig computing) isolerer AI-arbejdsbelastninger med hardware-baseret hukommelseskryptering. |   3   | D/V  |
| 4.16.3 | Bekræft, at fjernattestation validerer enclave-integritet, før AI-modeller indlæses, med kryptografisk bevis for eksekveringsmiljøets ægthed.                   |   3   | D/V  |
| 4.16.4 | Bekræft, at fortrolige AI-inferenztjenester forhindrer modeludtrækning gennem krypteret beregning med forseglede modelvægte og beskyttet udførelse.             |   3   | D/V  |
| 4.16.5 | Bekræft, at orkestrering af betroede udførelsesmiljøer håndterer livscyklussen for sikre enclaver med fjernattestation og krypterede kommunikationskanaler.     |   3   | D/V  |
| 4.16.6 | Bekræft, at sikker multi-part beregning (SMPC) muliggør samarbejdende AI-træning uden at afsløre individuelle datasæt eller modelparametre.                     |   3   | D/V  |

---

## C4.17 Zero-Knowledge Infrastruktur

Implementer nulvidensbevis-systemer til privatlivsbeskyttende AI-verifikation og autentificering uden at afsløre følsomme oplysninger.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.17.1 | Bekræft, at nul-viden-beviser (ZK-SNARKs, ZK-STARKs) verificerer AI-modelintegritet og træningsoprindelse uden at afsløre modelvægte eller træningsdata.           |   3   | D/V  |
| 4.17.2 | Bekræft, at ZK-baserede autentificeringssystemer muliggør privatlivsbevarende brugerbekræftelse for AI-tjenester uden at afsløre identitetsrelaterede oplysninger. |   3   | D/V  |
| 4.17.3 | Bekræft, at private sætintersektionsprotokoller (PSI) muliggør sikker datamatching for fødereret AI uden at eksponere individuelle datasæt.                        |   3   | D/V  |
| 4.17.4 | Bekræft, at zero-knowledge maskinlæringssystemer (ZKML) muliggør verificerbare AI-slutsætninger med kryptografisk bevis for korrekt beregning.                     |   3   | D/V  |
| 4.17.5 | Bekræft, at ZK-rollups leverer skalerbar, privatlivsbeskyttende AI-transaktionsbehandling med batchverifikation og reduceret beregningsbelastning.                 |   3   | D/V  |

---

## C4.18 Forebyggelse af sidekanalsangreb

Beskyt AI-infrastruktur mod tidsmæssige, strøm-, elektromagnetiske og cache-baserede sidekanal-angreb, der kan lække følsomme oplysninger.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.18.1 | Bekræft, at AI-inferensens timing er normaliseret ved brug af konstant-tidsalgoritmer og padding for at forhindre timing-baserede angreb på modeludtrækning.       |   3   | D/V  |
| 4.18.2 | Bekræft, at beskyttelse mod strøm analyse inkluderer støjindsprøjtning, filtrering af strømforsyningslinjer og randomiserede eksekveringsmønstre for AI-hardware.  |   3   | D/V  |
| 4.18.3 | Bekræft, at cache-baseret sidekanalafhjælpning bruger cache-partitionering, randomisering og flush-instruktioner til at forhindre informationslækage.              |   3   | D/V  |
| 4.18.4 | Bekræft, at beskyttelse mod elektromagnetisk udstråling inkluderer afskærmning, signalfiltrering og tilfældig behandling for at forhindre TEMPEST-lignende angreb. |   3   | D/V  |
| 4.18.5 | Bekræft, at mikrodukturelle sidekanalbeskyttelser omfatter kontrol med spekulativ eksekvering og obfuskering af hukommelsesadgangsmønstre.                         |   3   | D/V  |

---

## C4.19 Neuromorf og Specialiseret AI Hardware Sikkerhed

Sikre nye AI-hardwarearkitekturer, herunder neuromorfe chips, FPGA'er, specialdesignede ASIC'er og optiske computersystemer.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Bekræft, at neuromorfisk chip-sikkerhed inkluderer kryptering af spike-mønstre, beskyttelse af synaptiske vægte og hardware-baseret validering af læringsregler.                |   3   | D/V  |
| 4.19.2 | Bekræft, at FPGA-baserede AI-acceleratorer implementerer bitstrøm-kryptering, anti-manipulationsmekanismer og sikker konfigurationsindlæsning med autentificerede opdateringer. |   3   | D/V  |
| 4.19.3 | Bekræft, at specialiserede ASIC-sikkerhedsløsninger inkluderer sikkerhedsprocessorer på chippen, hardware root of trust og sikker nøglelagring med manipulationsdetektion.      |   3   | D/V  |
| 4.19.4 | Bekræft, at optiske computersystemer implementerer kvantesikret optisk kryptering, sikker fotonisk switching og beskyttet optisk signalbehandling.                              |   3   | D/V  |
| 4.19.5 | Bekræft, at hybride analog-digitale AI-chips inkluderer sikker analog beregning, beskyttet vægtlagring og autentificeret analog-til-digital konvertering.                       |   3   | D/V  |

---

## C4.20 Privatlivsbevarende computereinfrastruktur

Implementer infrastrukturkontroller for privatlivsbevarende beregning for at beskytte følsomme data under AI-behandling og analyse.

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Bekræft, at homomorf krypteringsinfrastruktur muliggør krypteret beregning på følsomme AI-arbejdsmængder med kryptografisk integritetsverifikation og ydeevneovervågning.                |   3   | D/V  |
| 4.20.2 | Sørg for, at systemer til privat informationshentning muliggør databaseforespørgsler uden at afsløre forespørgsmønstre ved hjælp af kryptografisk beskyttelse af adgangsmønstre.         |   3   | D/V  |
| 4.20.3 | Bekræft, at sikre multi-parti beregningsprotokoller muliggør privatlivsbeskyttende AI-inferens uden at afsløre individuelle input eller mellemliggende beregninger.                      |   3   | D/V  |
| 4.20.4 | Bekræft, at privatlivsbevarende nøglehåndtering omfatter distribueret nøglegenerering, tærskelkryptografi og sikker nøglerotation med hardwareunderstøttet beskyttelse.                  |   3   | D/V  |
| 4.20.5 | Sørg for, at ydeevnen for privatlivsbevarende beregninger optimeres gennem batching, caching og hardwareacceleration, samtidig med at de kryptografiske sikkerhedsgarantier opretholdes. |   3   | D/V  |

---

## C4.15 Agent Framework Cloud Integration Sikkerhed & Hybrid Udrulning

Sikkerhedskontroller for sky-integrerede agentrammeværker med hybride lokalt installerede/skyarkitekturer.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Bekræft, at integrationen af cloud-lagring anvender ende-til-ende-kryptering med agentstyret nøgleadministration.         |   1   | D/V  |
| 4.15.2 | Bekræft, at sikkerhedsgrænser for hybrid implementering er klart defineret med krypterede kommunikationskanaler.          |   2   | D/V  |
| 4.15.3 | Bekræft, at adgang til cloud-ressourcer inkluderer zero-trust-verifikation med kontinuerlig autentificering.              |   2   | D/V  |
| 4.15.4 | Bekræft, at krav til dataopbevaringssted overholdes ved kryptografisk attestering af lagringssteder.                      |   3   | D/V  |
| 4.15.5 | Kontroller, at sikkerhedsvurderinger hos cloud-udbyderen inkluderer agentspecifik trusselsmodellering og risikovurdering. |   3   | D/V  |

---

## Referencer

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

