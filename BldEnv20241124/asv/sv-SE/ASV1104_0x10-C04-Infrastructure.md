# C4-infrastruktur, konfigurations- och distributionssäkerhet

## Kontrollmål

AI-infrastrukturen måste göras säker mot privilegieupptrappning, manipulation av leverantörskedjan och lateral förflyttning genom säker konfiguration, isolering vid körning, betrodda distributionskedjor och omfattande övervakning. Endast auktoriserade, validerade infrastrukturskomponenter och konfigurationer når produktion genom kontrollerade processer som upprätthåller säkerhet, integritet och revisionbarhet.

Kärnsäkerhetsmål: Endast kryptografiskt signerade, sårbarhetsskannade infrastrukturskomponenter når produktion genom automatiserade valideringspipeline som upprätthåller säkerhetspolicys och bibehåller oföränderliga revisionsspår.

---

## C4.1 Körmiljöisolering

Förebygg containerflykt och eskalering av privilegier genom kärnnivåisolering och obligatoriska åtkomstkontroller.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Verifiera att alla AI-containrar tar bort ALLA Linux-behörigheter utom CAP_SETUID, CAP_SETGID och uttryckligen nödvändiga behörigheter dokumenterade i säkerhetsbaslinjer.                                                         |   1   | D/V  |
| 4.1.2 | Verifiera att seccomp-profiler blockerar alla systemanrop utom de som finns i förhandsgodkända tillåtlselistor, där överträdelser avslutar containern och genererar säkerhetsvarningar.                                            |   1   | D/V  |
| 4.1.3 | Verifiera att AI-arbetsbelastningar körs med skrivskyddade rotfilsystem, tmpfs för temporära data och namngivna volymer för beständiga data med noexec-monteringsalternativ tillämpade.                                            |   2   | D/V  |
| 4.1.4 | Verifiera att eBPF-baserad runtime-övervakning (Falco, Tetragon eller motsvarande) upptäcker försök till privilegieeskalering och automatiskt avslutar de processer som bryter mot reglerna inom organisationens krav på svarstid. |   2   | D/V  |
| 4.1.5 | Verifiera att hög-risk AI-arbetsbelastningar körs i hårdvaru-isolerade miljöer (Intel TXT, AMD SVM eller dedikerade bare-metal-noder) med attestationsverifiering.                                                                 |   3   | D/V  |

---

## C4.2 Säker bygg- och distributionspipeline

Säkerställ kryptografisk integritet och säkerhet i leverantörskedjan genom reproducerbara byggprocesser och signerade artefakter.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Verifiera att infrastruktur-som-kod skannas med verktyg (tfsec, Checkov eller Terrascan) vid varje commit och att sammanslagningar blockeras vid KRITISKA eller HÖGA allvarlighetsfynd.           |   1   | D/V  |
| 4.2.2 | Verifiera att containerbyggen är reproducerbara med identiska SHA256-hashvärden över olika byggen och generera SLSA nivå 3-proveniensintyg signerade med Sigstore.                                |   1   | D/V  |
| 4.2.3 | Verifiera att containerbilder innehåller inbäddade CycloneDX- eller SPDX-SBOM:er och är signerade med Cosign innan de puschas till registret, där osignerade bilder avvisas vid distribution.     |   2   | D/V  |
| 4.2.4 | Verifiera att CI/CD-pipelines använder OIDC-token från HashiCorp Vault, AWS IAM-roller eller Azure Managed Identity med livslängder som inte överstiger organisationens säkerhetspolicys gränser. |   2   | D/V  |
| 4.2.5 | Verifiera att Cosign-signaturer och SLSA-proveniens valideras under distributionsprocessen innan containerkörning och att verifieringsfel orsakar att distributionen misslyckas.                  |   2   | D/V  |
| 4.2.6 | Verifiera att byggmiljöer körs i efemära containrar eller virtuella maskiner utan beständigt lagringsutrymme och med nätverksisolering från produktions-VPC:er.                                   |   2   | D/V  |

---

## C4.3 Nätverkssäkerhet och åtkomstkontroll

Implementera nolltillit-nätverk med standardprinciper för nekande och krypterad kommunikation.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.3.1 | Verifiera att Kubernetes NetworkPolicies eller någon motsvarande lösning implementerar standardläget "deny" för ingående/utgående trafik med uttryckliga tillåtelseregler för nödvändiga portar (443, 8080, etc.). |   1   | D/V  |
| 4.3.2 | Verifiera att SSH (port 22), RDP (port 3389) och molnmetadataendpunkter (169.254.169.254) är blockerade eller kräver certifikatbaserad autentisering.                                                              |   1   | D/V  |
| 4.3.3 | Verifiera att utgående trafik filtreras genom HTTP/HTTPS-proxies (Squid, Istio eller moln-NAT-gatewayar) med domän-tillåtelselistor och att blockerade förfrågningar loggas.                                       |   2   | D/V  |
| 4.3.4 | Verifiera att kommunikation mellan tjänster använder ömsesidig TLS med certifikat som roteras enligt organisationens policy och att certifikatvalidering upprätthålls (inga skip-verify-flaggor).                  |   2   | D/V  |
| 4.3.5 | Verifiera att AI-infrastrukturen körs i dedikerade VPC:er/VNet utan direkt internetåtkomst och kommunicerar endast via NAT-gateways eller bastionhosts.                                                            |   2   | D/V  |

---

## C4.4 Hantering av hemligheter och kryptografiska nycklar

Skydda autentiseringsuppgifter genom hårdvarustödd lagring och automatiserad rotation med nolltillitstillgång.

|   #   | Description                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Verifiera att hemligheter lagras i HashiCorp Vault, AWS Secrets Manager, Azure Key Vault eller Google Secret Manager med kryptering i vila med AES-256.                                   |   1   | D/V  |
| 4.4.2 | Verifiera att kryptografiska nycklar genereras i FIPS 140-2 Nivå 2 HSM:er (AWS CloudHSM, Azure Dedicated HSM) med nyckelrotation enligt organisationens kryptografiska policy.            |   1   | D/V  |
| 4.4.3 | Verifiera att hemlighetsrotation är automatiserad med noll nedtid vid distribution och omedelbar rotation som utlöses av personaländringar eller säkerhetsincidenter.                     |   2   | D/V  |
| 4.4.4 | Verifiera att containerbilder skannas med verktyg (GitLeaks, TruffleHog eller detect-secrets) som blockerar byggen som innehåller API-nycklar, lösenord eller certifikat.                 |   2   | D/V  |
| 4.4.5 | Verifiera att produktionshemlig åtkomst kräver MFA med hårdvarutoken (YubiKey, FIDO2) och att detta registreras i oföränderliga revisionsloggar med användaridentiteter och tidsstämplar. |   2   | D/V  |
| 4.4.6 | Verifiera att hemligheter injiceras via Kubernetes-hemligheter, monterade volymer eller init-containrar och säkerställ att hemligheter aldrig är inbäddade i miljövariabler eller bilder. |   2   | D/V  |

---

## C4.5 AI arbetsbelastningssandboxing och validering

Isolera opålitliga AI-modeller i säkra sandlådor med omfattande beteendeanalys.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Verifiera att externa AI-modeller körs i gVisor, microVMs (såsom Firecracker, CrossVM) eller Docker-containrar med --security-opt=no-new-privileges och --read-only flaggor.       |   1   | D/V  |
| 4.5.2 | Verifiera att sandbox-miljöer inte har nätverksanslutning (--network=none) eller endast tillgång till localhost med alla externa förfrågningar blockerade av iptables-regler.      |   1   | D/V  |
| 4.5.3 | Verifiera att validering av AI-modeller inkluderar automatiserad red-team-testning med organisationsdefinierad testtäckning och beteendeanalys för att upptäcka bakdörrar.         |   2   | D/V  |
| 4.5.4 | Verifiera att innan en AI-modell tas i produktion, att dess sandbox-resultat är kryptografiskt signerade av behörig säkerhetspersonal och lagrade i oföränderliga revisionsloggar. |   2   | D/V  |
| 4.5.5 | Verifiera att sandbox-miljöer förstörs och återskapas från guldavbilder mellan utvärderingar med fullständig rensning av filsystem och minne.                                      |   2   | D/V  |

---

## C4.6 Infrastrukturens säkerhetsövervakning

Kontinuerligt skanna och övervaka infrastrukturen med automatiserad åtgärd och realtidslarm.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Verifiera att containerbilder skannas enligt organisatoriska scheman, där KRITISKA sårbarheter blockerar distribution baserat på organisatoriska risktrösklar.                              |   1   | D/V  |
| 4.6.2 | Verifiera att infrastrukturen uppfyller CIS Benchmarks eller NIST 800-53-kontroller med organisationsdefinierade efterlevnadströsklar och automatiserad åtgärd för misslyckade kontroller.  |   1   | D/V  |
| 4.6.3 | Verifiera att sårbarheter med HÖG allvarlighetsgrad åtgärdas enligt organisationens riskhanteringstidslinjer med nödprocedurer för aktivt utnyttjade CVE:er.                                |   2   | D/V  |
| 4.6.4 | Verifiera att säkerhetsvarningar integreras med SIEM-plattformar (Splunk, Elastic eller Sentinel) med hjälp av CEF- eller STIX/TAXII-format med automatisk berikning.                       |   2   |  V   |
| 4.6.5 | Verifiera att infrastruktursmått exporteras till övervakningssystem (Prometheus, DataDog) med SLA-instrumentpaneler och ledningsrapportering.                                               |   3   |  V   |
| 4.6.6 | Verifiera att konfigurationsavvikelse upptäcks med hjälp av verktyg (Chef InSpec, AWS Config) enligt organisationens övervakningskrav med automatisk återställning för obehöriga ändringar. |   2   | D/V  |

---

## C4.7 AI-infrastruktur Resurshantering

Förebygg attacker som utmattar resurser och säkerställ rättvis resursallokering genom kvoter och övervakning.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.7.1 | Verifiera att GPU/TPU-användning övervakas med larm som utlöses vid organisatoriskt definierade tröskelvärden och att automatisk skalning eller lastbalansering aktiveras baserat på kapacitetshanteringspolicyer. |   1   | D/V  |
| 4.7.2 | Verifiera att AI-arbetsbelastningsmått (inferenslatens, genomströmningshastighet, felprocent) samlas in enligt organisatoriska övervakningskrav och korreleras med infrastrukturens användning.                    |   1   | D/V  |
| 4.7.3 | Verifiera att Kubernetes ResourceQuotas eller motsvarande begränsar individuella arbetsbelastningar enligt organisationens resursallokeringspolicyer med hårda gränser som upprätthålls.                           |   2   | D/V  |
| 4.7.4 | Verifiera att kostnadsövervakningen spårar utgifter per arbetsbelastning/hyresgäst med aviseringar baserade på organisatoriska budgetgränser och automatiska kontroller för budgetöverskridanden.                  |   2   |  V   |
| 4.7.5 | Verifiera att kapacitetsplanering använder historiska data med organisationsdefinierade prognosperioder och automatiserad resursförsörjning baserat på efterfrågemönster.                                          |   3   |  V   |
| 4.7.6 | Verifiera att resursutmattning utlöser kretsbrytare enligt organisationens svarskrav, inklusive hastighetsbegränsning baserat på kapacitetsprinciper och arbetsbelastningsisolering.                               |   2   | D/V  |

---

## C4.8 Miljöseparation och kontroll av promotion

Genomdriv strikta miljögränser med automatiserade befordringsportar och säkerhetsvalidering.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Verifiera att utvecklings-, test- och produktionsmiljöer körs i separata VPC:er/VNet med inga delade IAM-roller, säkerhetsgrupper eller nätverksanslutningar.                                                                |   1   | D/V  |
| 4.8.2 | Verifiera att miljöfrämjande kräver godkännande från organisatoriskt definierad behörig personal med kryptografiska signaturer och oföränderliga revisionsspår.                                                              |   1   | D/V  |
| 4.8.3 | Verifiera att produktionsmiljöer blockerar SSH-åtkomst, inaktiverar debug-endpoints och kräver ändringsförfrågningar med organisatoriska förhandskrav förutom vid nödsituationer.                                            |   2   | D/V  |
| 4.8.4 | Verifiera att förändringar i infrastruktur-som-kod kräver granskning av kollegor med automatiserade tester och säkerhetsskanning innan sammanslagning till huvudgrenen.                                                      |   2   | D/V  |
| 4.8.5 | Verifiera att icke-produktionsdata är anonymiserad enligt organisationens integritetskrav, syntetisk datagenerering eller fullständig datamaskning med verifierad borttagning av personligt identifierbar information (PII). |   2   | D/V  |
| 4.8.6 | Verifiera att befordringsportar inkluderar automatiserade säkerhetstester (SAST, DAST, container-skanning) med noll KRITISKA fynd som krävs för godkännande.                                                                 |   2   | D/V  |

---

## C4.9 Infrastruktur för säkerhetskopiering och återställning

Säkerställ infrastrukturens motståndskraft genom automatiserade säkerhetskopior, testade återställningsprocedurer och kapabiliteter för katastrofåterställning.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Verifiera att infrastrukturens konfigurationer säkerhetskopieras enligt organisationens backup-scheman till geografiskt separata regioner med implementering av 3-2-1-backupstrategin.         |   1   | D/V  |
| 4.9.2 | Verifiera att backupsystem körs i isolerade nätverk med separata autentiseringsuppgifter och luftgapad lagring för skydd mot ransomware.                                                       |   2   | D/V  |
| 4.9.3 | Verifiera att återställningsprocedurer testas och valideras genom automatiserade tester enligt organisationens scheman med RTO- och RPO-mål som uppfyller organisationens krav.                |   2   |  V   |
| 4.9.4 | Verifiera att återställning efter katastrof inkluderar AI-specifika driftsinstruktioner med återställning av modellvikter, återuppbyggnad av GPU-kluster och kartläggning av tjänsteberoenden. |   3   |  V   |

---

## C4.10 Infrastrukturöverensstämmelse och styrning

Bibehåll regleringsöverensstämmelse genom kontinuerlig utvärdering, dokumentation och automatiserade kontroller.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Verifiera att infrastrukturefterlevnad bedöms enligt organisationens schema gentemot SOC 2, ISO 27001 eller FedRAMP-kontroller med automatiserad insamling av bevis.        |   2   | D/V  |
| 4.10.2 | Verifiera att infrastrukturen dokumentationen inkluderar nätverksdiagram, databasflödeskartor och hotmodeller uppdaterade enligt organisatoriska förändringshanteringskrav. |   2   |  V   |
| 4.10.3 | Verifiera att infrastruktursförändringar genomgår automatiserad bedömning av efterlevnadspåverkan med regelverksgodkännandeflöden för hög-riskmodifieringar.                |   3   | D/V  |

---

## C4.11 AI Hårdvarusäkerhet

Säkra AI-specifika hårdvarukomponenter inklusive GPU:er, TPU:er och specialiserade AI-acceleratorer.

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.11.1 | Verifiera att AI-acceleratorns firmware (GPU BIOS, TPU-firmware) är verifierad med kryptografiska signaturer och uppdateras enligt organisationens patchhanteringstidsplaner.        |   2   | D/V  |
| 4.11.2 | Verifiera att AI-acceleratorns integritet valideras genom hårdvaruattestation med TPM 2.0, Intel TXT eller AMD SVM innan arbetsbelastningen körs.                                    |   2   | D/V  |
| 4.11.3 | Verifiera att GPU-minnet är isolerat mellan arbetsbelastningar med hjälp av SR-IOV, MIG (Multi-Instance GPU) eller motsvarande hårdvarupartitionering med minnessäkring mellan jobb. |   2   | D/V  |
| 4.11.4 | Verifiera att AI-hårdvarans försörjningskedja inkluderar proveniensverifiering med tillverkarintyg och validering av manipulationssäker förpackning.                                 |   3   |  V   |
| 4.11.5 | Verifiera att hårdvarusäkerhetsmoduler (HSM) skyddar AI-modellvikter och kryptografiska nycklar med FIPS 140-2 Level 3 eller Common Criteria EAL4+ certifiering.                     |   3   | D/V  |

---

## C4.12 Kant- och distribuerad AI-infrastruktur

Säkra distribuerade AI-distributioner inklusive kantberäkning, federerat lärande och multi-platsarkitekturer.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Verifiera att edge-AI-enheter autentiserar mot central infrastruktur med ömsesidig TLS och att enhetscertifikat byts ut enligt organisationens certifikathanteringspolicy. |   2   | D/V  |
| 4.12.2 | Verifiera att kant-enheter implementerar säker uppstart med verifierade signaturer och rollback-skydd som förhindrar firmware-nedgraderingsattacker.                       |   2   | D/V  |
| 4.12.3 | Verifiera att distribuerad AI-samordning använder bysantinskt feltoleranta konsensusalgoritmer med deltagarvalidering och upptäckt av illvilliga noder.                    |   3   | D/V  |
| 4.12.4 | Verifiera att edge-till-moln-kommunikation inkluderar bandbreddsbegränsning, datakomprimering och offline-funktioner med säker lokal lagring.                              |   3   | D/V  |

---

## C4.13 Säkerhet för Multi-Cloud- och Hybridinfrastruktur

Säkra AI-arbetsbelastningar över flera molnleverantörer och hybridmoln-lokala distributioner.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.13.1 | Verifiera att multi-cloud AI-distributioner använder moln-agnostisk identitetsfederation (OIDC, SAML) med centraliserad policystyrning över leverantörer.                                        |   2   | D/V  |
| 4.13.2 | Verifiera att dataöverföring mellan molntjänster använder end-to-end-kryptering med kundhanterade nycklar och att dataresidenskontroller efterlevs enligt gällande jurisdiktion.                 |   2   | D/V  |
| 4.13.3 | Verifiera att hybridmoln-AI-arbetsbelastningar implementerar konsekventa säkerhetspolicyer över både lokala och molnbaserade miljöer med en enhetlig övervakning och larmhantering.              |   2   | D/V  |
| 4.13.4 | Verifiera att förebyggandet av inlåsning till molnleverantör inkluderar bärbar infrastruktur-som-kod, standardiserade API:er och möjligheter till dataexport med verktyg för formatkonvertering. |   3   |  V   |
| 4.13.5 | Verifiera att multi-cloud kostnadsoptimering inkluderar säkerhetskontroller som förhindrar resursutbredning samt obehöriga avgifter för dataöverföring mellan moln.                              |   3   |  V   |

---

## C4.14 Infrastrukturautomatisering & GitOps-säkerhet

Säkra automatiseringspipelines för infrastruktur och GitOps-arbetsflöden för hantering av AI-infrastruktur.

|   #    | Description                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Verifiera att GitOps-förråd kräver signerade commits med GPG-nycklar och att gren-skyddsregler förhindrar direkta pushes till huvudgrenar.                                                                      |   2   | D/V  |
| 4.14.2 | Verifiera att infrastrukturautomatisering inkluderar driftavvikelsedetektering med automatiserad korrigering och återställningsfunktioner som utlöses enligt organisationens svarskrav för obehöriga ändringar. |   2   | D/V  |
| 4.14.3 | Verifiera att automatiserad infrastruktur-provisionering inkluderar validering av säkerhetspolicy med blockerande av distribution för icke-överensstämmande konfigurationer.                                    |   2   | D/V  |
| 4.14.4 | Verifiera att hemligheter för infrastrukturautomatisering hanteras genom externa hemlighetsoperatörer (External Secrets Operator, Bank-Vaults) med automatisk rotation.                                         |   2   | D/V  |
| 4.14.5 | Verifiera att självläkande infrastruktur inkluderar korrelation av säkerhetshändelser med automatiserad incidenthantering och arbetsflöden för meddelande till intressenter.                                    |   3   |  V   |

---

## C4.15 Kvantsäker infrastruktur säkerhet

Förbered AI-infrastruktur för kvantdatorhot genom post-kvantsäker kryptografi och kvantsäkra protokoll.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifiera att AI-infrastrukturen implementerar NIST-godkända post-kvantkryptografiska algoritmer (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) för nyckelutbyte och digitala signaturer. |   3   | D/V  |
| 4.15.2 | Verifiera att kvantdelningssystem (QKD) implementeras för högsäker AI-kommunikation med kvantsäkra nyckelhanteringsprotokoll.                                                             |   3   | D/V  |
| 4.15.3 | Verifiera att kryptografiska agilityramverk möjliggör snabb migration till nya post-kvantalgoritmer med automatiserad certifikat- och nyckelrotation.                                     |   3   | D/V  |
| 4.15.4 | Verifiera att kvantumhotmodellering bedömer AI-infrastrukturens sårbarhet för kvantumattacker med dokumenterade migreringstidslinjer och riskbedömningar.                                 |   3   |  V   |
| 4.15.5 | Verifiera att hybrida klassiskt-kvantkryptografiska system erbjuder djupförsvar under kvantövergångsperioden med prestandaövervakning.                                                    |   3   | D/V  |

---

## C4.16 Konfidentiell databehandling och säkra inneslutningar

Skydda AI-arbetsbelastningar och modellvikter med hjälp av hårdvarubaserade betrodda exekveringsmiljöer och konfidentiell beräkningsteknik.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Verifiera att känsliga AI-modeller körs inom Intel SGX-enklaver, AMD SEV-SNP eller ARM TrustZone med krypterat minne och verifiering av intyg.                          |   3   | D/V  |
| 4.16.2 | Verifiera att konfidentiella containrar (Kata Containers, gVisor med konfidentiell datoranvändning) isolerar AI-arbetsbelastningar med hårdvaruestvad minneskryptering. |   3   | D/V  |
| 4.16.3 | Verifiera att fjärrintyg validerar kapselns integritet innan AI-modeller laddas med kryptografiskt bevis på en exekveringsmiljös äkthet.                                |   3   | D/V  |
| 4.16.4 | Verifiera att konfidentiella AI-inferenstjänster förhindrar modelextraktion genom krypterad beräkning med förseglade modellvikter och skyddad exekvering.               |   3   | D/V  |
| 4.16.5 | Verifiera att orchestreringen av betrodd exekveringsmiljö hanterar livscykeln för säkrad oval med fjärrintyg och krypterade kommunikationskanaler.                      |   3   | D/V  |
| 4.16.6 | Verifiera att säker multipartyberäkning (SMPC) möjliggör samarbetsinriktad AI-träning utan att exponera individuella dataset eller modellparametrar.                    |   3   | D/V  |

---

## C4.17 Nollkunskapsinfrastruktur

Implementera nollkunskapsbevis-system för integritetsbevarande AI-verifiering och autentisering utan att avslöja känslig information.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Verifiera att zero-knowledge-bevis (ZK-SNARKs, ZK-STARKs) bekräftar AI-modellens integritet och träningsursprung utan att avslöja modellvikter eller träningsdata.        |   3   | D/V  |
| 4.17.2 | Verifiera att ZK-baserade autentiseringssystem möjliggör integritetsbevarande användarverifiering för AI-tjänster utan att avslöja identitetsrelaterad information.       |   3   | D/V  |
| 4.17.3 | Verifiera att privata mängdintersektioner (Private Set Intersection, PSI) protokoll möjliggör säker datamatchning för federerad AI utan att avslöja individuella dataset. |   3   | D/V  |
| 4.17.4 | Verifiera att maskininlärningssystem med nollkunskap (ZKML) möjliggör verifierbara AI-slutsatser med kryptografiskt bevis för korrekt beräkning.                          |   3   | D/V  |
| 4.17.5 | Verifierar att ZK-rollups erbjuder skalbar, sekretessbevarande AI-transaktionshantering med batchverifiering och minskad beräkningsbelastning.                            |   3   | D/V  |

---

## C4.18 Förebyggande av sidokanalsattacker

Skydda AI-infrastrukturen från tids-, effekt-, elektromagnetiska och cache-baserade sidokanalsattacker som kan läcka känslig information.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Verifiera att AI-inferensens tidsåtgång normaliseras med hjälp av algoritmer med konstant tid och utfyllnad för att förhindra tidsbaserade angrepp för modellutvinning. |   3   | D/V  |
| 4.18.2 | Verifiera att skydd mot effektanalys inkluderar brusinjicering, filtrering av strömlinjen och slumpmässiga exekveringsmönster för AI-hårdvara.                          |   3   | D/V  |
| 4.18.3 | Verifiera att cache-baserad sidokanalsmitigering använder cache-partitionering, randomisering och flush-instruktioner för att förhindra informationsläckage.            |   3   | D/V  |
| 4.18.4 | Verifiera att skydd mot elektromagnetisk strålning inkluderar avskärmning, signalfiltrering och randomiserad bearbetning för att förhindra TEMPEST-liknande attacker.   |   3   | D/V  |
| 4.18.5 | Verifiera att mikroarkitektoniska sidokanalsförsvar inkluderar kontroller för spekulativ exekvering och förmörkling av minnesåtkomstmönster.                            |   3   | D/V  |

---

## C4.19 Neuromorf och specialiserad AI-hårdvarusäkerhet

Säkra framväxande AI-hårdvaruarkitekturer inklusive neuromorfa chip, FPGA:er, specialanpassade ASIC:ar och optiska datorsystem.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Verifiera att neuromorfisk chip-säkerhet inkluderar kryptering av spike-mönster, skydd av synaptiska vikter och hårdvarubaserad validering av inlärningsregler.            |   3   | D/V  |
| 4.19.2 | Verifiera att FPGA-baserade AI-acceleratorer implementerar bitströmskryptering, tamper-skyddsmekanismer och säker konfigurationsinläsning med autentiserade uppdateringar. |   3   | D/V  |
| 4.19.3 | Verifiera att anpassad ASIC-säkerhet inkluderar in-chip säkerhetsprocessorer, hårdvarurot av förtroende och säker nyckellagring med manipulationsdetektering.              |   3   | D/V  |
| 4.19.4 | Verifiera att optiska datorsystem implementerar kvantsäkert optiskt kryptering, säker fotonisk omkoppling och skyddad optisk signalbehandling.                             |   3   | D/V  |
| 4.19.5 | Verifiera att hybrida analog-digitala AI-chip inkluderar säker analog beräkning, skyddad viktlagring och autentiserad analog-till-digital-konvertering.                    |   3   | D/V  |

---

## C4.20 Integritetsskyddande beräkningsinfrastruktur

Implementera infrastrukturella kontroller för integritetsbevarande beräkningar för att skydda känsliga data under AI-bearbetning och analys.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Verifiera att infrastrukturen för homomorfisk kryptering möjliggör krypterad beräkning på känsliga AI-arbetsbelastningar med kryptografisk integritetsverifiering och prestandaövervakning.        |   3   | D/V  |
| 4.20.2 | Verifiera att system för privat informationshämtning möjliggör databasfrågor utan att avslöja frågemönster med kryptografiskt skydd av åtkomstmönster.                                             |   3   | D/V  |
| 4.20.3 | Verifiera att säkra multi-party computation-protokoll möjliggör sekretessbevarande AI-slutledning utan att avslöja individuella indata eller mellanliggande beräkningar.                           |   3   | D/V  |
| 4.20.4 | Verifiera att integritetsbevarande nyckelhantering inkluderar distribuerad nyckelgenerering, tröskelkriptografi och säker nyckelrotation med maskinvarustödd skydd.                                |   3   | D/V  |
| 4.20.5 | Verifiera att prestandan för integritetsbevarande beräkningar är optimerad genom batchbearbetning, cachning och hårdvaruacceleration samtidigt som kryptografiska säkerhetsgarantier upprätthålls. |   3   | D/V  |

---

## C4.15 Agentramverk Cloud Integration Säkerhet & Hybriddistribution

Säkerhetskontroller för molnintegrerade agentramverk med hybridarkitekturer för lokala miljöer och moln.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Verifiera att molnlagringsintegration använder end-to-end-kryptering med agentstyrd nyckelhantering.                   |   1   | D/V  |
| 4.15.2 | Verifiera att säkerhetsgränser för hybriddistribution är tydligt definierade med krypterade kommunikationskanaler.     |   2   | D/V  |
| 4.15.3 | Verifiera att åtkomst till molnresurser inkluderar nolltillitverifiering med kontinuerlig autentisering.               |   2   | D/V  |
| 4.15.4 | Verifiera att krav på dataresidens efterlevs genom kryptografisk intygande av lagringsplatser.                         |   3   | D/V  |
| 4.15.5 | Verifiera att säkerhetsbedömningar från molnleverantörer inkluderar agent-specifik hotmodellering och riskutvärdering. |   3   | D/V  |

---

## Referenser

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

