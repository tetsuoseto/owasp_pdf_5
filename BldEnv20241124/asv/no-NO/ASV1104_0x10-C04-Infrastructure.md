# C4 infrastruktur, konfigurasjon og distribusjonssikkerhet

## Kontrollmål

AI-infrastrukturen må forsterkes mot privilegieeskalering, manipulasjon i leverandørkjeden og sidelengs bevegelse gjennom sikker konfigurasjon, isolasjon under kjøring, betrodde distribusjonspipelines og omfattende overvåking. Kun autoriserte, validerte infrastrukturkomponenter og konfigurasjoner når produksjon gjennom kontrollerte prosesser som opprettholder sikkerhet, integritet og revisjonsmuligheter.

Kjernemål for sikkerhet: Kun kryptografisk signerte, sårbarhetsskannede infrastrukturelementer når produksjon gjennom automatiserte valideringsrørledninger som håndhever sikkerhetspolicyer og opprettholder uforanderlige revisjonsspor.

---

## C4.1 Kjøretidsmiljøisolasjon

Forhindre containerflukt og privilegieeskalering gjennom kjerne-nivå isolasjonsprimitiver og obligatoriske tilgangskontroller.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Verifiser at alle AI-beholdere fjerner ALLE Linux-muligheter unntatt CAP_SETUID, CAP_SETGID, og eksplisitt nødvendige muligheter dokumentert i sikkerhetsbaselines.                                                         |   1   | D/V  |
| 4.1.2 | Verifiser at seccomp-profiler blokkerer alle systemkall unntatt de som er i forhåndsgodkjente tillatlister, hvor brudd fører til at containeren termineres og sikkerhetsvarsler genereres.                                  |   1   | D/V  |
| 4.1.3 | Bekreft at AI-arbeidsbelastninger kjører med skrivbeskyttet rotfilsystem, tmpfs for midlertidige data, og navngitte volumer for vedvarende data med noexec monteringsalternativer håndhevet.                                |   2   | D/V  |
| 4.1.4 | Bekreft at eBPF-basert kjøretidsovervåkning (Falco, Tetragon eller tilsvarende) oppdager forsøk på privilegieeskalering og automatisk avslutter prosesser som bryter reglene innenfor organisasjonens tidskrav for respons. |   2   | D/V  |
| 4.1.5 | Verifiser at AI-arbeidsoppgaver med høy risiko kjøres i maskinvare-isolerte miljøer (Intel TXT, AMD SVM, eller dedikerte bare-metal noder) med attestasjonssjekk.                                                           |   3   | D/V  |

---

## C4.2 Sikker bygging og distribusjonspipelines

Sikre kryptografisk integritet og forsyningskjedesikkerhet gjennom reproduserbare bygg og signerte artefakter.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Sjekk at infrastruktur-som-kode skannes med verktøy (tfsec, Checkov eller Terrascan) ved hver commit, og at sammenslåinger blokkeres ved FUNN med KRITISK eller HØY alvorlighetsgrad.          |   1   | D/V  |
| 4.2.2 | Verifiser at containerbygg er reproducerbare med identiske SHA256-hashverdier på tvers av bygg, og generer SLSA nivå 3 opprinnelsesattester signert med Sigstore.                              |   1   | D/V  |
| 4.2.3 | Sørg for at containerbilder inneholder CycloneDX- eller SPDX-SBOM-er og er signert med Cosign før de pushes til registeret, slik at usignerte bilder avvises ved implementering.               |   2   | D/V  |
| 4.2.4 | Bekreft at CI/CD-pipelines bruker OIDC-tokener fra HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med levetider som ikke overstiger organisasjonens sikkerhetspolitiske grenser. |   2   | D/V  |
| 4.2.5 | Verifiser at Cosign-signaturer og SLSA-proveniens blir validert under distribusjonsprosessen før containerkjøring, og at verifikasjonsfeil fører til at distribusjonen mislykkes.              |   2   | D/V  |
| 4.2.6 | Kontroller at byggeomgivelser kjøres i flyktige containere eller virtuelle maskiner uten vedvarende lagring og med nettverksisolasjon fra produksjons-VPC-er.                                  |   2   | D/V  |

---

## C4.3 Nettverkssikkerhet og tilgangskontroll

Implementer nulltillitsnettverk med standardavslåtte retningslinjer og kryptert kommunikasjon.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.3.1 | Sørg for at Kubernetes NetworkPolicies eller tilsvarende implementerer standard nektelse for innkommende/utgående trafikk med eksplisitte tillatelsesregler for nødvendige porter (443, 8080, osv.).   |   1   | D/V  |
| 4.3.2 | Bekreft at SSH (port 22), RDP (port 3389) og skymetadata-endepunkter (169.254.169.254) er blokkert eller krever sertifikatbasert autentisering.                                                        |   1   | D/V  |
| 4.3.3 | Bekreft at utgående trafikk filtreres gjennom HTTP/HTTPS-proxyer (Squid, Istio eller sky NAT-gatewayer) med domenetillatelser og at blokkerte forespørsler logges.                                     |   2   | D/V  |
| 4.3.4 | Bekreft at kommunikasjon mellom tjenester bruker gjensidig TLS med sertifikater som roteres i henhold til organisasjonens policy, og at sertifikatvalidering blir håndhevet (ingen skip-verify-flagg). |   2   | D/V  |
| 4.3.5 | Bekreft at AI-infrastrukturen kjører i dedikerte VPCer/VNeter uten direkte internettilgang, og at kommunikasjonen skjer kun gjennom NAT-gatewayer eller bastion-verter.                                |   2   | D/V  |

---

## C4.4 Hemmeligheter og kryptografisk nøkkelhåndtering

Beskytt legitimasjon gjennom maskinvarebasert lagring og automatisk utskifting med nulltillits-tilgang.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Bekreft at hemmeligheter lagres i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering i ro ved bruk av AES-256.                                       |   1   | D/V  |
| 4.4.2 | Bekreft at kryptografiske nøkler genereres i FIPS 140-2 Level 2 HSM-er (AWS CloudHSM, Azure Dedicated HSM) med nøkkelrotasjon i henhold til organisasjonens kryptografiske policy.                 |   1   | D/V  |
| 4.4.3 | Bekreft at rotering av hemmeligheter er automatisert med null nedetid ved distribusjon og umiddelbar rotering utløst av personalendringer eller sikkerhetshendelser.                               |   2   | D/V  |
| 4.4.4 | Sørg for at containerbilder skannes med verktøy (GitLeaks, TruffleHog eller detect-secrets) som blokkerer bygg som inneholder API-nøkler, passord eller sertifikater.                              |   2   | D/V  |
| 4.4.5 | Verifiser at tilgang til produksjonshemmeligheter krever MFA med maskinvaretokener (YubiKey, FIDO2) og at dette registreres i uforanderlige revisjonslogger med brukeridentiteter og tidsstempler. |   2   | D/V  |
| 4.4.6 | Verifiser at hemmeligheter injiseres via Kubernetes-hemmeligheter, monterte volumer eller init-containere, og sørg for at hemmeligheter aldri er innebygd i miljøvariabler eller bilder.           |   2   | D/V  |

---

## C4.5 AI-arbeidsbelastningssandboxing og validering

Isoler uautoriserte AI-modeller i sikre sandkasser med omfattende atferdsanalyse.

|   #   | Description                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Bekreft at eksterne AI-modeller kjøres i gVisor, microVM-er (som Firecracker, CrossVM) eller Docker-containere med --security-opt=no-new-privileges og --read-only flagg.              |   1   | D/V  |
| 4.5.2 | Verifiser at sandkassemiljøer ikke har nettverkstilkobling (--network=none) eller kun lokaltilgang med alle eksterne forespørsler blokkert av iptables-regler.                         |   1   | D/V  |
| 4.5.3 | Bekreft at validering av AI-modellen inkluderer automatisert red-team-testing med organisasjonsdefinert testdekning og atferdsanalyse for oppdagelse av bakdører.                      |   2   | D/V  |
| 4.5.4 | Bekreft at før en AI-modell blir tatt i produksjon, blir resultatene fra sandkassen kryptografisk signert av autorisert sikkerhetspersonell og lagret i uforanderlige revisjonslogger. |   2   | D/V  |
| 4.5.5 | Bekreft at sandkassemiljøer blir ødelagt og gjenopprettet fra gullbilder mellom evalueringer med fullstendig opprydding av filsystem og minne.                                         |   2   | D/V  |

---

## C4.6 Infrastruktur Sikkerhetsovervåkning

Kontinuerlig skann og overvåk infrastruktur med automatisert utbedring og varsling i sanntid.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Kontroller at containerbilder skannes i henhold til organisasjonens tidsplaner, der KRITISKE sårbarheter blokkerer distribusjon basert på organisasjonens risikogrenseverdier.                 |   1   | D/V  |
| 4.6.2 | Bekreft at infrastrukturen oppfyller CIS Benchmarks eller NIST 800-53-kontroller med organisasjonsdefinerte samsvarsterskler og automatisk utbedring for mislykkede kontroller.                |   1   | D/V  |
| 4.6.3 | Bekreft at sårbarheter med HØY alvorlighetsgrad blir utbedret i henhold til organisasjonens tidslinjer for risikostyring, med nødprosedyrer for aktivt utnyttede CVE-er.                       |   2   | D/V  |
| 4.6.4 | Bekreft at sikkerhetsvarsler integreres med SIEM-plattformer (Splunk, Elastic eller Sentinel) ved hjelp av CEF- eller STIX/TAXII-formater med automatisert berikelse.                          |   2   |  V   |
| 4.6.5 | Verifiser at infrastrukturmålinger eksporteres til overvåkingssystemer (Prometheus, DataDog) med SLA-dashbord og ledelsesrapportering.                                                         |   3   |  V   |
| 4.6.6 | Bekreft at konfigurasjonsavvik oppdages ved bruk av verktøy (Chef InSpec, AWS Config) i henhold til organisatoriske overvåkningskrav, med automatisk tilbakeføring for uautoriserte endringer. |   2   | D/V  |

---

## C4.7 AI-infrastruktur Ressursadministrasjon

Forhindre angrep som tømmer ressurser og sikre rettferdig ressursfordeling gjennom kvoter og overvåking.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Bekreft at GPU/TPU-utnyttelse overvåkes med varsler som utløses ved organisatorisk definerte terskler, og at automatisk skalering eller lastbalansering aktiveres basert på kapasitetsstyringspolitikker. |   1   | D/V  |
| 4.7.2 | Bekreft at AI-arbeidsbelastningsmetrikker (inferenceslatenstid, gjennomstrømning, feilrater) samles inn i henhold til organisasjonens overvåkingskrav og korreleres med infrastrukturutnyttelse.          |   1   | D/V  |
| 4.7.3 | Bekreft at Kubernetes ResourceQuotas eller tilsvarende begrenser individuelle arbeidsbelastninger i henhold til organisasjonens retningslinjer for ressursallokering, med harde grenser håndhevet.        |   2   | D/V  |
| 4.7.4 | Bekreft at kostnadsovervåking sporer utgifter per arbeidsbelastning/leietaker med varsler basert på organisatoriske budsjettgrenser og automatiserte kontroller for budsjettoverskridelser.               |   2   |  V   |
| 4.7.5 | Bekreft at kapasitetsplanlegging bruker historiske data med organisasjonsdefinerte prognoseperioder og automatisert ressursprovisjonering basert på etterspørselsmønstre.                                 |   3   |  V   |
| 4.7.6 | Bekreft at ressursutarming utløser kretsbrytere i henhold til organisasjonens responskrav, inkludert hastighetsbegrensning basert på kapasitetsregler og isolasjon av arbeidsbelastning.                  |   2   | D/V  |

---

## C4.8 Miljøseparasjon og Kontroll av Fremming

Håndhev strenge miljøgrenser med automatiske godkjenningsporter for promotering og sikkerhetsvalidering.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.8.1 | Bekreft at utviklings-, test- og produksjonsmiljøer kjører i separate VPC-er/VNets uten delte IAM-roller, sikkerhetsgrupper eller nettverksforbindelser.                                                                 |   1   | D/V  |
| 4.8.2 | Verifiser at miljøfremming krever godkjenning fra organisatorisk definerte autoriserte personer med kryptografiske signaturer og uforanderlige revisjonsspor.                                                            |   1   | D/V  |
| 4.8.3 | Bekreft at produksjonsmiljøer blokkerer SSH-tilgang, deaktiverer debug-endepunkter, og krever endringsforespørsler med organisatoriske varslingskrav på forhånd, unntatt i nødstilfeller.                                |   2   | D/V  |
| 4.8.4 | Bekreft at endringer i infrastruktur-som-kode krever fagfellevurdering med automatisert testing og sikkerhetsskanning før sammenslåing til hovedgrenen.                                                                  |   2   | D/V  |
| 4.8.5 | Bekreft at ikke-produksjonsdata er anonymisert i henhold til organisasjonens personvernkrav, syntetisk datagenerering eller fullstendig datamaskering med verifisert fjerning av personidentifiserbar informasjon (PII). |   2   | D/V  |
| 4.8.6 | Bekreft at promoteringstrinn inkluderer automatiserte sikkerhetstester (SAST, DAST, container-skanning) med null KRITISKE funn som krav for godkjenning.                                                                 |   2   | D/V  |

---

## C4.9 Infrastruktur Sikkerhetskopiering og Gjenoppretting

Sikre infrastrukturens robusthet gjennom automatiserte sikkerhetskopier, testede gjenopprettingsprosedyrer og katastrofegjenopprettingsmuligheter.

|   #   | Description                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Bekreft at infrastrukturkonfigurasjoner sikkerhetskopieres i henhold til organisasjonens sikkerhetskopieringsplaner til geografisk adskilte regioner med implementering av 3-2-1 sikkerhetskopieringsstrategi. |   1   | D/V  |
| 4.9.2 | Bekreft at backupsystemer kjører i isolerte nettverk med separate legitimasjoner og lufttettes lagringsløsninger for beskyttelse mot løsepengevirus.                                                           |   2   | D/V  |
| 4.9.3 | Bekreft at gjenopprettingsprosedyrer testes og verifiseres gjennom automatisert testing i henhold til organisasjonens tidsplaner, med RTO- og RPO-mål som oppfyller organisasjonens krav.                      |   2   |  V   |
| 4.9.4 | Bekreft at katastrofegjenoppretting inkluderer AI-spesifikke kjøreplaner med gjenoppretting av modellvekter, gjenoppbygging av GPU-klynger og kartlegging av tjenesteavhengigheter.                            |   3   |  V   |

---

## C4.10 Infrastruktur etterlevelse og styring

Oppretthold regulatorisk etterlevelse gjennom kontinuerlig vurdering, dokumentasjon og automatiserte kontroller.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Bekreft at infrastrukturens samsvar vurderes i henhold til organisatoriske tidsplaner mot SOC 2, ISO 27001 eller FedRAMP-kontroller med automatisert innsamling av bevis.     |   2   | D/V  |
| 4.10.2 | Sørg for at infrastruktuurdokumentasjonen inkluderer nettverksdiagrammer, datakart over flyt og trusselmodeller oppdatert i samsvar med organisasjonens endringsstyringskrav. |   2   |  V   |
| 4.10.3 | Bekreft at infrastrukturelle endringer gjennomgår automatisert vurdering av samsvarspåvirkning med regulatoriske godkjenningsarbeidsflyter for høyrisikoendringer.            |   3   | D/V  |

---

## C4.11 AI-maskinvare-sikkerhet

Sikre AI-spesifikke maskinvarekomponenter inkludert GPUer, TPUer og spesialiserte AI-akseleratorer.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.11.1 | Verifiser at fastvaren for AI-akseleratorer (GPU BIOS, TPU-fastvare) er verifisert med kryptografiske signaturer og oppdatert i henhold til organisasjonens tidslinjer for patch-administrasjon. |   2   | D/V  |
| 4.11.2 | Bekreft at før arbeidsbelastningsutførelse blir AI-akseleratorens integritet validert gjennom maskinvareattestasjon ved bruk av TPM 2.0, Intel TXT eller AMD SVM.                                |   2   | D/V  |
| 4.11.3 | Bekreft at GPU-minne er isolert mellom arbeidsbelastninger ved bruk av SR-IOV, MIG (Multi-Instance GPU) eller tilsvarende maskinvarepartisjonering med minne-sanitetskontroll mellom jobbene.    |   2   | D/V  |
| 4.11.4 | Bekreft at AI-maskinvareleverandørkjeden inkluderer verifisering av opprinnelse med produsentsertifikater og validering av manipulering-sikker emballasje.                                       |   3   |  V   |
| 4.11.5 | Bekreft at maskinvare sikkerhetsmoduler (HSM-er) beskytter AI-modellvekter og kryptografiske nøkler med FIPS 140-2 nivå 3 eller Common Criteria EAL4+ sertifisering.                             |   3   | D/V  |

---

## C4.12 Kant- og distribuert KI-infrastruktur

Sikre distribuerte AI-distribusjoner inkludert kantdatabehandling, føderert læring og flersite-arkitekturer.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Bekreft at edge AI-enheter autentiserer seg til sentral infrastruktur ved bruk av gjensidig TLS med enhetssertifikater som roteres i henhold til organisasjonens sertifikathåndteringspolicy. |   2   | D/V  |
| 4.12.2 | Bekreft at kant-enheter implementerer sikker oppstart med verifiserte signaturer og beskyttelse mot tilbakerulling som forhindrer angrep som nedgraderer fastvaren.                           |   2   | D/V  |
| 4.12.3 | Bekreft at distribuert AI-koordinering bruker bysantinsk feil-tolerante konsensusalgoritmer med deltakerbekreftelse og ondsinnet nodetoppdagelse.                                             |   3   | D/V  |
| 4.12.4 | Verifiser at kommunikasjon fra kant til sky inkluderer båndbreddebegrensning, datakomprimering og offline driftsmuligheter med sikker lokal lagring.                                          |   3   | D/V  |

---

## C4.13 Sikkerhet for Multi-Cloud og Hybrid Infrastruktur

Sikre AI-arbeidsbelastninger på tvers av flere skyleverandører og hybride sky- og lokale distribusjoner.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Bekreft at fler-sky AI-distribusjoner bruker sky-agnostisk identitetsfederasjon (OIDC, SAML) med sentralisert policyhåndtering på tvers av leverandører.                         |   2   | D/V  |
| 4.13.2 | Bekreft at tverr-sky dataoverføring bruker ende-til-ende-kryptering med kundestyrte nøkler og at datalokaliseringkontroller håndheves i henhold til jurisdiksjon.                |   2   | D/V  |
| 4.13.3 | Bekreft at hybride sky-AI-arbeidsbelastninger implementerer konsistente sikkerhetspolicyer på tvers av lokale og skybaserte miljøer med enhetlig overvåking og varsling.         |   2   | D/V  |
| 4.13.4 | Bekreft at forebygging av leverandørlåsning i skyen inkluderer bærbar infrastruktur-som-kode, standardiserte API-er og dataeksportmuligheter med verktøy for formatkonvertering. |   3   |  V   |
| 4.13.5 | Bekreft at kostnadsoptimalisering for multi-cloud inkluderer sikkerhetskontroller som hindrer ressursutbredelse samt uautoriserte kostnader for dataoverføring mellom skyer.     |   3   |  V   |

---

## C4.14 Infrastrukturautomatisering og GitOps-sikkerhet

Sikre automatiseringspipelines for infrastruktur og GitOps-arbeidsflyter for administrasjon av AI-infrastruktur.

|   #    | Description                                                                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.14.1 | Bekreft at GitOps-repositorier krever signerte commits med GPG-nøkler og branch protection-regler som forhindrer direkte push til hovedbrancher.                                                             |   2   | D/V  |
| 4.14.2 | Bekreft at infrastrukturautomatisering inkluderer avvikdeteksjon med automatiske utbedrings- og tilbakestillingsfunksjoner som utløses i henhold til organisasjonens responskrav for uautoriserte endringer. |   2   | D/V  |
| 4.14.3 | Verifiser at automatisert infrastrukturprovisjonering inkluderer validering av sikkerhetspolicyer med distribusjonsblokker for ikke-kompatible konfigurasjoner.                                              |   2   | D/V  |
| 4.14.4 | Bekreft at hemmeligheter for infrastrukturautomatisering administreres gjennom eksterne hemmelighetsoperatører (External Secrets Operator, Bank-Vaults) med automatisk rotasjon.                             |   2   | D/V  |
| 4.14.5 | Verifiser at selvhelbredende infrastruktur inkluderer sikkerhetshendelseskorrelasjon med automatisert hendelsesrespons og arbeidsflyter for varsling av interessenter.                                       |   3   |  V   |

---

## C4.15 Kvantesikker Infrastruktur Sikkerhet

Forbered AI-infrastruktur for trusler fra kvanteberegning gjennom post-kvantet kryptografi og kvantesikre protokoller.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Bekreft at AI-infrastrukturen implementerer NIST-godkjente post-kvantematiske kryptografiske algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) for nøkkelutveksling og digitale signaturer. |   3   | D/V  |
| 4.15.2 | Verifiser at kvantenøkkeldistribusjon (QKD) systemer er implementert for høysikkerhets AI-kommunikasjon med kvantesikre nøkkelhåndteringsprotokoller.                                               |   3   | D/V  |
| 4.15.3 | Sørg for at kryptografiske smidighetsrammeverk muliggjør rask migrering til nye post-kvante algoritmer med automatisert sertifikat- og nøkkelrotasjon.                                              |   3   | D/V  |
| 4.15.4 | Verifiser at kvantetrusselmodellering vurderer AI-infrastrukturens sårbarhet for kvanteangrep med dokumenterte migrasjonstidslinjer og risikovurderinger.                                           |   3   |  V   |
| 4.15.5 | Verifiser at hybride klassiske-kvant kryptografiske systemer gir forsvar-i-dybden under kvantetransisjonsperioden med ytelsesovervåking.                                                            |   3   | D/V  |

---

## C4.16 Konfidensiell databehandling og sikre soner

Beskytt AI-arbeidsmengder og modellvekter ved hjelp av maskinvarebaserte pålitelige utførelsesmiljøer og konfidensielle databehandlingsteknologier.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Verifiser at sensitive AI-modeller kjører innenfor Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med kryptert minne og attestasjonsverifisering.                    |   3   | D/V  |
| 4.16.2 | Bekreft at konfidensielle containere (Kata Containers, gVisor med konfidensiell databehandling) isolerer AI-arbeidsbelastninger med maskinvarehåndhevet minne-kryptering. |   3   | D/V  |
| 4.16.3 | Bekreft at fjernattestering validerer integriteten til enclave før lasting av AI-modeller med kryptografisk bevis på eksekveringsmiljøets autentisitet.                   |   3   | D/V  |
| 4.16.4 | Bekreft at konfidensielle AI-inferenstjenester forhindrer modelekstraksjon gjennom kryptert beregning med forseglede modellvekter og beskyttet utførelse.                 |   3   | D/V  |
| 4.16.5 | Bekreft at orkestrering av Trusted Execution Environment håndterer livssyklusen til sikre innhegninger med fjernattestasjon og krypterte kommunikasjonskanaler.           |   3   | D/V  |
| 4.16.6 | Bekreft at sikker flerpartsberegning (SMPC) muliggjør samarbeidende AI-trening uten å eksponere individuelle datasett eller modellparametere.                             |   3   | D/V  |

---

## C4.17 Nullkunnskapsinfrastruktur

Implementer null-kunnskapsbevis-systemer for personvernbevarende AI-verifisering og autentisering uten å avsløre sensitiv informasjon.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Bekreft at nullkunnskapsbevis (ZK-SNARKs, ZK-STARKs) verifiserer AI-modellens integritet og treningsopprinnelse uten å eksponere modellvekter eller treningsdata. |   3   | D/V  |
| 4.17.2 | Bekreft at ZK-baserte autentiseringssystemer muliggjør personvernbevarende brukerverifisering for AI-tjenester uten å avsløre identitetsrelatert informasjon.     |   3   | D/V  |
| 4.17.3 | Bekreft at protokoller for privat mengdeinterseksjon (PSI) muliggjør sikker datamatching for føderert KI uten å eksponere individuelle datasett.                  |   3   | D/V  |
| 4.17.4 | Bekreft at nullkunnskaps maskinlæringssystemer (ZKML) muliggjør verifiserbare AI-slutninger med kryptografisk bevis for korrekt beregning.                        |   3   | D/V  |
| 4.17.5 | Bekreft at ZK-rollups gir skalerbar, personvernbevarende AI-transaksjonsbehandling med batch-verifisering og redusert beregningsmessig overhead.                  |   3   | D/V  |

---

## C4.18 Forebygging av sidekanalsangrep

Beskytt AI-infrastrukturen mot tidsmessige, strøm-, elektromagnetiske og cache-baserte sidekanalangrep som kan lekke sensitiv informasjon.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Bekreft at AI-inferensens tid er normalisert ved hjelp av konstant-tidsalgoritmer og utfylling for å forhindre tidsbaserte modelluttrekksangrep.                  |   3   | D/V  |
| 4.18.2 | Bekreft at strømmetodikkbeskyttelse inkluderer støyinjeksjon, filtrering av strømledningen og randomiserte utførelsesmønstre for AI-maskinvare.                   |   3   | D/V  |
| 4.18.3 | Bekreft at sidekanalinformasjonssikkerhet basert på cache bruker cache-partisjonering, randomisering og flush-instruksjoner for å forhindre informasjonslekkasje. |   3   | D/V  |
| 4.18.4 | Bekreft at beskyttelse mot elektromagnetisk utsendelse inkluderer skjerming, signalfiltrering og tilfeldig behandling for å forhindre TEMPEST-lignende angrep.    |   3   | D/V  |
| 4.18.5 | Bekreft at mikrounderarkitektoniske sidekanalforsvar inkluderer kontroll av spekulativ utførelse og obfuskering av mønstre for minnetilgang.                      |   3   | D/V  |

---

## C4.19 Neuromorfe og spesialiserte AI-maskinvare-sikkerhet

Sikre fremvoksende AI-maskinvarearkitekturer, inkludert nevromorfe brikker, FPGAer, spesialtilpassede ASICer og optiske datasystemer.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Verifiser at sikkerheten til nevromorfe brikker inkluderer kryptering av spike-mønstre, beskyttelse av synaptiske vekter og maskinvarebasert validering av læringsregler. |   3   | D/V  |
| 4.19.2 | Bekreft at FPGA-baserte AI-akseleratorer implementerer bitstrøm-kryptering, anti-manipulasjonsmekanismer og sikker konfigurasjonslasting med autentiserte oppdateringer.  |   3   | D/V  |
| 4.19.3 | Bekreft at tilpasset ASIC-sikkerhet inkluderer sikkerhetsprosessorer på brikken, maskinvarebasert tillitsrot, og sikker nøkkellagring med manipuleringdeteksjon.          |   3   | D/V  |
| 4.19.4 | Verifiser at optiske databehandlingssystemer implementerer kvantesikker optisk kryptering, sikker fotonisk switching og beskyttet optisk signalbehandling.                |   3   | D/V  |
| 4.19.5 | Bekreft at hybride analoge-digitale AI-brikker inkluderer sikker analog beregning, beskyttet lagring av vekter, og autentisert analog-til-digital konvertering.           |   3   | D/V  |

---

## C4.20 Personvernbevarende beregningsinfrastruktur

Implementer infrastrukturelle kontroller for personvernbevarende beregning for å beskytte sensitiv data under AI-behandling og -analyse.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Bekreft at homomorf krypteringsinfrastruktur muliggjør kryptert behandling av sensitive AI-arbeidsbelastninger med kryptografisk integritetsverifisering og ytelsesovervåking.               |   3   | D/V  |
| 4.20.2 | Verifiser at private informasjonsinnhentingssystemer muliggjør databasespørringer uten å avsløre spørringsmønstre ved hjelp av kryptografisk beskyttelse av tilgangsmønstre.                 |   3   | D/V  |
| 4.20.3 | Verifiser at sikre protokoller for flerpartssamarbeid muliggjør personvernbevarende AI-sluttningsbehandling uten å avsløre individuelle input eller mellomliggende beregninger.              |   3   | D/V  |
| 4.20.4 | Bekreft at personvern-bevarende nøkkelhåndtering inkluderer distribuert nøkkelgenerering, terskelkryptografi og sikker nøkkelrotasjon med maskinvarebasert beskyttelse.                      |   3   | D/V  |
| 4.20.5 | Verifiser at personvernbevarende beregningsytelse er optimalisert gjennom batchbehandling, caching og maskinvareakselerasjon, samtidig som kryptografiske sikkerhetsgarantier opprettholdes. |   3   | D/V  |

---

## C4.15 Agent-rammeverk Skysikkerhet og Hybrid Distribusjon

Sikkerhetskontroller for skyintegrerte agentrammeverk med hybride lokale/skyarkitekturer.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifiser at skylagringsintegrasjonen bruker ende-til-ende kryptering med agentstyrt nøkkelhåndtering.                 |   1   | D/V  |
| 4.15.2 | Bekreft at sikkerhetsgrensene for hybrid distribusjon er klart definert med krypterte kommunikasjonskanaler.           |   2   | D/V  |
| 4.15.3 | Bekreft at tilgang til skyressurser inkluderer nulltillitverifisering med kontinuerlig autentisering.                  |   2   | D/V  |
| 4.15.4 | Bekreft at krav til datalokalisering håndheves gjennom kryptografisk attestasjon av lagringssteder.                    |   3   | D/V  |
| 4.15.5 | Bekreft at sikkerhetsvurderinger hos skyleverandører inkluderer agent-spesifikk trusselmodellering og risikovurdering. |   3   | D/V  |

---

## Referanser

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

