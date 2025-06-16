# C4 infrastruktura, konfigurace a bezpečnost nasazení

## Cíl kontroly

Infrastruktura umělé inteligence musí být zabezpečena proti eskalaci oprávnění, manipulaci s dodavatelským řetězcem a laterálním přesunům prostřednictvím zabezpečené konfigurace, izolace během běhu, důvěryhodných pipeline nasazení a komplexního monitorování. Do produkčního prostředí projdou pouze autorizované, ověřené komponenty infrastruktury a konfigurace prostřednictvím kontrolovaných procesů, které zachovávají bezpečnost, integritu a auditovatelnost.

Hlavní bezpečnostní cíl: Do produkce pronikají pouze kryptograficky podepsané a naskenované komponenty infrastruktury na zranitelnosti prostřednictvím automatizovaných validačních pipeline, které uplatňují bezpečnostní politiky a udržují neměnné auditní stopy.

---

## C4.1 Izolace běhového prostředí

Zabraňte únikům kontejnerů a eskalaci oprávnění pomocí izolace na úrovni jádra a povinných přístupových kontrol.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Ověřte, že všechny AI kontejnery ztrácejí VŠECHNY linuxové schopnosti kromě CAP_SETUID, CAP_SETGID a explicitně požadovaných schopností dokumentovaných v bezpečnostních standardech.                       |   1   | D/V  |
| 4.1.2 | Ověřte, že profily seccomp blokují všechny systémové volání kromě těch v předem schválených seznamech povolených, přičemž porušení vedou k ukončení kontejneru a generování bezpečnostních upozornění.      |   1   | D/V  |
| 4.1.3 | Ověřte, že zátěže AI běží se souborovými systémy root v režimu pouze pro čtení, tmpfs pro dočasná data a pojmenovanými svazky pro trvalá data s vynucenými možnostmi připojení noexec.                      |   2   | D/V  |
| 4.1.4 | Ověřte, že monitorování za běhu založené na eBPF (Falco, Tetragon nebo ekvivalent) detekuje pokusy o eskalaci oprávnění a automaticky ukončuje závadné procesy v rámci požadavků na dobu odezvy organizace. |   2   | D/V  |
| 4.1.5 | Ověřte, zda výpočetně náročné úlohy umělé inteligence běží ve hardwarově izolovaných prostředích (Intel TXT, AMD SVM nebo dedikované bare-metal uzly) s ověřením atestace.                                  |   3   | D/V  |

---

## C4.2 Zabezpečené pipeline pro sestavování a nasazování

Zajistěte kryptografickou integritu a bezpečnost dodavatelského řetězce prostřednictvím reprodukovatelných sestavení a podepsaných artefaktů.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Ověřte, že infrastruktura jako kód je při každém commitu kontrolována nástroji (tfsec, Checkov nebo Terrascan), přičemž jsou blokovány slučování obsahující nálezy s kritickou nebo vysokou závažností. |   1   | D/V  |
| 4.2.2 | Ověřte, že sestavení kontejnerů jsou reprodukovatelná s identickými hashi SHA256 napříč sestaveními a generujte osvědčení o původu SLSA úrovně 3 podepsaná pomocí Sigstore.                             |   1   | D/V  |
| 4.2.3 | Ověřte, že obrazy kontejnerů obsahují SBOM ve formátu CycloneDX nebo SPDX a jsou před nahráním do registru podepsány pomocí Cosign, přičemž nepodepsané obrazy jsou při nasazení odmítnuty.             |   2   | D/V  |
| 4.2.4 | Ověřte, že CI/CD pipeline používají OIDC tokeny z HashiCorp Vault, AWS IAM rolí nebo Azure Managed Identity s dobou platnosti nepřesahující limity stanovené bezpečnostní politikou organizace.         |   2   | D/V  |
| 4.2.5 | Ověřte, že podpisy Cosign a provedení SLSA jsou validovány během procesu nasazení před spuštěním kontejneru a že chyby ověření způsobí selhání nasazení.                                                |   2   | D/V  |
| 4.2.6 | Ověřte, že sestavovací prostředí běží v dočasných kontejnerech nebo virtuálních strojích bez trvalého úložiště a s síťovou izolací od produkčních VPC.                                                  |   2   | D/V  |

---

## C4.3 Síťová bezpečnost a řízení přístupu

Implementujte síťování založené na principu nulové důvěry s politikami výchozího zamítnutí a šifrovanou komunikací.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Ověřte, zda Kubernetes NetworkPolicies nebo jakýkoli ekvivalent implementují výchozí zamítnutí příchozího/odchozího provozu s explicitními pravidly povolení pro požadované porty (443, 8080 atd.). |   1   | D/V  |
| 4.3.2 | Ověřte, že SSH (port 22), RDP (port 3389) a cloudové metadatové koncové body (169.254.169.254) jsou zablokovány nebo vyžadují autentizaci na základě certifikátu.                                   |   1   | D/V  |
| 4.3.3 | Ověřte, že odchozí provoz je filtrován prostřednictvím HTTP/HTTPS proxy (Squid, Istio nebo cloudových NAT bran) s povolenými seznamy domén a že jsou zaznamenávány blokované požadavky.             |   2   | D/V  |
| 4.3.4 | Ověřte, že mezislužbová komunikace používá vzájemné TLS s certifikáty rotovanými podle organizační politiky a že je vynucena validace certifikátů (žádné příznaky pro přeskočení ověření).          |   2   | D/V  |
| 4.3.5 | Ověřte, že infrastruktura AI běží v dedikovaných VPC/VNet sítích bez přímého přístupu na internet a komunikuje pouze přes NAT brány nebo bastion hostitele.                                         |   2   | D/V  |

---

## C4.4 Správa tajemství a kryptografických klíčů

Chraňte přihlašovací údaje pomocí úložiště podporovaného hardwarem a automatické rotace s přístupem založeným na principu zero-trust.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Ověřte, že tajné údaje jsou uloženy v HashiCorp Vault, AWS Secrets Manager, Azure Key Vault nebo Google Secret Manager s šifrováním v klidu pomocí AES-256.                                              |   1   | D/V  |
| 4.4.2 | Ověřte, že kryptografické klíče jsou generovány ve FIPS 140-2 úrovně 2 HSM (AWS CloudHSM, Azure Dedicated HSM) s rotací klíčů podle organizační kryptografické politiky.                                 |   1   | D/V  |
| 4.4.3 | Ověřte, že je rotace tajných údajů automatizovaná s nasazením bez výpadků a okamžitou rotací spuštěnou při změnách personálu nebo bezpečnostních incidentech.                                            |   2   | D/V  |
| 4.4.4 | Ověřte, že jsou obrazy kontejnerů skenovány nástroji (GitLeaks, TruffleHog nebo detect-secrets), které blokují sestavení obsahující API klíče, hesla nebo certifikáty.                                   |   2   | D/V  |
| 4.4.5 | Ověřte, že přístup k produkčnímu tajnému klíči vyžaduje MFA s hardwarovými tokeny (YubiKey, FIDO2) a je zaznamenáván nezměnitelnými auditními záznamy s identitami uživatelů a časovými razítky.         |   2   | D/V  |
| 4.4.6 | Ověřte, že tajné údaje jsou vkládány prostřednictvím Kubernetes secrets, připojených svazků nebo init kontejnerů, a zajistěte, aby tajné údaje nikdy nebyly vloženy do proměnných prostředí nebo obrazů. |   2   | D/V  |

---

## C4.5 Izolace a validace pracovních úloh AI

Izolujte nedůvěryhodné modely AI v bezpečných pískovištích s komplexní analýzou chování.

|   #   | Description                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Ověřte, že externí modely AI běží v gVisor, microVM (jako Firecracker, CrossVM) nebo v Docker kontejnerech s parametry --security-opt=no-new-privileges a --read-only.                    |   1   | D/V  |
| 4.5.2 | Ověřte, že sandboxová prostředí nemají žádné síťové připojení (--network=none) nebo mají přístup pouze k localhostu s blokováním všech externích požadavků pomocí pravidel iptables.      |   1   | D/V  |
| 4.5.3 | Ověřte, že validace AI modelu zahrnuje automatizované testování red-team s organizačně definovaným pokrytím testů a behaviorální analýzou pro detekci zadních vrátek.                     |   2   | D/V  |
| 4.5.4 | Ověřte, že před nasazením AI modelu do produkce jsou jeho výsledky ze sandboxu kryptograficky podepsány autorizovaným bezpečnostním personálem a uloženy v neměnných auditních záznamech. |   2   | D/V  |
| 4.5.5 | Ověřte, že jsou sandboxová prostředí po každém hodnocení zničena a znovu vytvořena z kontrolních obrazů s kompletním vyčištěním souborového systému a paměti.                             |   2   | D/V  |

---

## C4.6 Monitorování bezpečnosti infrastruktury

Nepřetržitě skenujte a monitorujte infrastrukturu s automatickým nápravným opatřením a upozorněním v reálném čase.

|   #   | Description                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Ověřte, že obrazy kontejnerů jsou skenovány podle organizačních plánů a že zranitelnosti označené jako KRITICKÉ blokují nasazení na základě organizačních prahů rizika.                        |   1   | D/V  |
| 4.6.2 | Ověřte, že infrastruktura splňuje CIS Benchmarks nebo kontroly NIST 800-53 s organizačně definovanými prahovými hodnotami shody a automatizovanou nápravou při neúspěšných kontrolách.         |   1   | D/V  |
| 4.6.3 | Ověřte, že chyby s vysokou závažností jsou opraveny podle časových plánů řízení rizik organizace s nouzovými postupy pro aktivně zneužívané CVE.                                               |   2   | D/V  |
| 4.6.4 | Ověřte, že bezpečnostní výstrahy se integrují se SIEM platformami (Splunk, Elastic nebo Sentinel) pomocí formátů CEF nebo STIX/TAXII s automatickým obohacením.                                |   2   |  V   |
| 4.6.5 | Ověřte, že metriky infrastruktury jsou exportovány do monitorovacích systémů (Prometheus, DataDog) s dashboardy SLA a výkonnostními reporty.                                                   |   3   |  V   |
| 4.6.6 | Ověřte, že odchylky v konfiguraci jsou detekovány pomocí nástrojů (Chef InSpec, AWS Config) podle požadavků organizace na monitorování s automatickým návratem zpět při neoprávněných změnách. |   2   | D/V  |

---

## C4.7 Správa zdrojů infrastruktury AI

Zabraňte útokům vyčerpávajícím zdroje a zajistěte spravedlivé přidělení zdrojů pomocí kvót a monitorování.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Ověřte, že je sledována využití GPU/TPU s upozorněními vyvolanými při organizačně stanovených prahových hodnotách a že jsou aktivovány automatické škálování nebo vyvažování zátěže na základě politik správy kapacity. |   1   | D/V  |
| 4.7.2 | Ověřte, že metriky pracovní zátěže AI (latence inferencí, propustnost, míra chyb) jsou shromažďovány v souladu s požadavky organizačního monitorování a korelovány s využitím infrastruktury.                           |   1   | D/V  |
| 4.7.3 | Ověřte, že Kubernetes ResourceQuotas nebo ekvivalentní mechanismy omezují jednotlivé pracovní zátěže podle organizačních politik alokace zdrojů s vynucenými tvrdými limity.                                            |   2   | D/V  |
| 4.7.4 | Ověřte, zda monitorování nákladů sleduje výdaje podle pracovního zatížení/nájemce s upozorněními založenými na prahových hodnotách rozpočtu organizace a automatizovanými kontrolami překročení rozpočtu.               |   2   |  V   |
| 4.7.5 | Ověřte, že plánování kapacit využívá historická data s organizačně definovanými obdobím předpovědi a automatizované přidělování zdrojů založené na vzorcích poptávky.                                                   |   3   |  V   |
| 4.7.6 | Ověřte, že vyčerpání zdrojů spouští jističe v souladu s požadavky organizační odezvy, včetně omezení rychlosti založeného na politikách kapacity a izolace pracovního zatížení.                                         |   2   | D/V  |

---

## C4.8 Oddělení prostředí a kontrola propagace

Prosazujte přísné hranice prostředí pomocí automatizovaných propagačních bran a bezpečnostní validace.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Ověřte, že vývojové/testovací/produkční prostředí běží v samostatných VPC/VNet s žádnými sdílenými IAM rolemi, bezpečnostními skupinami nebo síťovým připojením.                                                                    |   1   | D/V  |
| 4.8.2 | Ověřte, že propagace prostředí vyžaduje schválení od organizačně definovaných oprávněných osob s kryptografickými podpisy a nezměnitelnými auditními stopami.                                                                       |   1   | D/V  |
| 4.8.3 | Ověřte, že produkční prostředí blokuje přístup přes SSH, zakazuje ladicí rozhraní a vyžaduje žádosti o změny s organizačními požadavky na předběžné oznámení, kromě naléhavých případů.                                             |   2   | D/V  |
| 4.8.4 | Ověřte, že změny v infrastruktuře jako kódu vyžadují kontrolu od kolegů s automatizovaným testováním a bezpečnostním skenováním před sloučením do hlavní větve.                                                                     |   2   | D/V  |
| 4.8.5 | Ověřte, že nepoužíváte produkční data, která jsou anonymizována podle organizačních požadavků na ochranu soukromí, generování syntetických dat nebo kompletní maskování dat s odstraněním osobních identifikovatelných údajů (PII). |   2   | D/V  |
| 4.8.6 | Ověřte, že propagační brány zahrnují automatizované bezpečnostní testy (SAST, DAST, skenování kontejnerů) s nulovým požadavkem na schválení v případě kritických nálezů.                                                            |   2   | D/V  |

---

## Zálohování a obnova infrastruktury C4.9

Zajistěte odolnost infrastruktury prostřednictvím automatizovaných záloh, testovaných postupů obnovy a schopností obnovy po havárii.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Ověřte, že konfigurace infrastruktury jsou zálohovány podle organizačních plánů zálohování do geograficky oddělených regionů s implementací strategie zálohování 3-2-1.               |   1   | D/V  |
| 4.9.2 | Ověřte, že zálohovací systémy běží v izolovaných sítích se samostatnými přihlašovacími údaji a úložištěm odděleným od sítě (air-gapped) pro ochranu proti ransomwaru.                 |   2   | D/V  |
| 4.9.3 | Ověřte, že postupy obnovy jsou testovány a validovány prostřednictvím automatizovaného testování podle organizačních harmonogramů s cíli RTO a RPO splňujícími organizační požadavky. |   2   |  V   |
| 4.9.4 | Ověřte, že plán obnovy po havárii zahrnuje specifické runbooky pro AI s obnovením vah modelu, rekonstrukcí GPU clusteru a mapováním závislostí služby.                                |   3   |  V   |

---

## C4.10 Soulad infrastruktury a řízení

Zajistěte dodržování předpisů prostřednictvím kontinuálního hodnocení, dokumentace a automatizovaných kontrol.

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Ověřte, že shoda infrastruktury je posuzována podle organizačních plánů vůči kontrolám SOC 2, ISO 27001 nebo FedRAMP s automatizovaným sběrem důkazů.          |   2   | D/V  |
| 4.10.2 | Ověřte, že dokumentace infrastruktury zahrnuje síťové diagramy, mapy toku dat a modely hrozeb aktualizované podle požadavků na řízení změn v organizaci.       |   2   |  V   |
| 4.10.3 | Ověřte, že změny infrastruktury procházejí automatizovaným hodnocením dopadů na soulad s předpisy s pracovními postupy schvalování pro vysoce rizikové úpravy. |   3   | D/V  |

---

## C4.11 Bezpečnost hardwaru pro AI

Zabezpečte hardwarové komponenty specifické pro AI, včetně GPU, TPU a specializovaných AI akcelerátorů.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Ověřte, že firmware akcelerátoru AI (GPU BIOS, firmware TPU) je ověřován pomocí kryptografických podpisů a aktualizován v souladu s časovými plány organizačního řízení záplat. |   2   | D/V  |
| 4.11.2 | Ověřte, že před spuštěním pracovní zátěže je integrita AI akcelerátoru ověřena pomocí hardwarové attestace s využitím TPM 2.0, Intel TXT nebo AMD SVM.                          |   2   | D/V  |
| 4.11.3 | Ověřte, že paměť GPU je izolována mezi pracovními zátěžemi pomocí SR-IOV, MIG (Multi-Instance GPU) nebo obdobného hardwarového dělení s čištěním paměti mezi úlohami.           |   2   | D/V  |
| 4.11.4 | Ověřte, že dodavatelský řetězec hardware pro AI zahrnuje ověření původu pomocí certifikátů výrobce a validaci obalů s ochranou proti neoprávněné manipulaci.                    |   3   |  V   |
| 4.11.5 | Ověřte, že hardwarové bezpečnostní moduly (HSM) chrání váhy AI modelu a kryptografické klíče s certifikací FIPS 140-2 úroveň 3 nebo Common Criteria EAL4+.                      |   3   | D/V  |

---

## C4.12 Okrajová a distribuovaná infrastruktura umělé inteligence

Bezpečná distribuovaná nasazení umělé inteligence včetně edge computingu, federativního učení a architektur s více lokalitami.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Ověřte, že zařízení edge AI se autentizují vůči centrální infrastruktuře pomocí vzájemného TLS s certifikáty zařízení, které jsou pravidelně obměňovány v souladu s organizační politikou správy certifikátů. |   2   | D/V  |
| 4.12.2 | Ověřte, že koncová zařízení implementují zabezpečené spuštění s ověřenými podpisy a ochranou proti vrácení zpět, která zabraňuje útokům na snížení verze firmwaru.                                            |   2   | D/V  |
| 4.12.3 | Ověřte, že koordinace distribuované AI používá konsenzuální algoritmy odolné vůči byzantským chybám s validací účastníků a detekcí škodlivých uzlů.                                                           |   3   | D/V  |
| 4.12.4 | Ověřte, že komunikace mezi okrajem a cloudem zahrnuje omezení šířky pásma, kompresi dat a schopnosti práce offline s bezpečným lokálním uložištěm.                                                            |   3   | D/V  |

---

## C4.13 Bezpečnost vícecloudové a hybridní infrastruktury

Zabezpečte pracovní zatížení AI napříč více poskytovateli cloudu a hybridními cloud-on-premises nasazeními.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Ověřte, že více-cloudové nasazení AI používá cloudově nezávislou federaci identity (OIDC, SAML) s centralizovanou správou politik napříč poskytovateli.                                   |   2   | D/V  |
| 4.13.2 | Ověřte, že přenos dat mezi cloudy používá šifrování od konce ke konci s klíči spravovanými zákazníkem a že jsou uplatňovány kontroly umístění dat podle jurisdikce.                       |   2   | D/V  |
| 4.13.3 | Ověřte, že hybridní cloudové AI pracovní zatížení implementují konzistentní bezpečnostní politiky napříč on-premise a cloudovými prostředími s sjednoceným monitorováním a upozorňováním. |   2   | D/V  |
| 4.13.4 | Ověřte, že prevence uzamčení u poskytovatele cloudových služeb zahrnuje přenosnou infrastrukturu jako kód, standardizovaná API a možnosti exportu dat s nástroji pro konverzi formátů.    |   3   |  V   |
| 4.13.5 | Ověřte, že optimalizace nákladů v multi-cloud prostředí zahrnuje bezpečnostní kontroly zabraňující rozšiřování zdrojů i neoprávněným poplatkům za přenos dat mezi cloudy.                 |   3   |  V   |

---

## C4.14 Automatizace infrastruktury a bezpečnost GitOps

Zabezpečte automatizační pipeliny infrastruktury a GitOps pracovní postupy pro správu AI infrastruktury.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Ověřte, zda repozitáře GitOps vyžadují podepsané commity pomocí GPG klíčů a pravidla ochrany větví zabraňující přímým pushům do hlavních větví.                                                     |   2   | D/V  |
| 4.14.2 | Ověřte, že automatizace infrastruktury zahrnuje detekci odchylek s automatickými schopnostmi nápravy a návratu zpět, které jsou spuštěny podle požadavků organizace na reakci na neoprávněné změny. |   2   | D/V  |
| 4.14.3 | Ověřte, že automatizované zřizování infrastruktury zahrnuje validaci bezpečnostních zásad s blokováním nasazení u konfigurací, které nejsou v souladu.                                              |   2   | D/V  |
| 4.14.4 | Ověřte, že tajné informace pro automatizaci infrastruktury jsou spravovány prostřednictvím externích správců tajemství (External Secrets Operator, Bank-Vaults) s automatickou rotací.              |   2   | D/V  |
| 4.14.5 | Ověřte, že samoopravná infrastruktura zahrnuje korelaci bezpečnostních událostí s automatizovanou reakcí na incidenty a pracovními postupy pro oznámení zainteresovaným stranám.                    |   3   |  V   |

---

## C4.15 Kvantově odolná infrastruktura zabezpečení

Připravte infrastrukturu umělé inteligence na hrozby kvantového počítání prostřednictvím post-kvantové kryptografie a kvantově bezpečných protokolů.

|   #    | Description                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Ověřte, že infrastruktura umělé inteligence implementuje kryptografické algoritmy schválené NIST pro post-kvantovou bezpečnost (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) pro výměnu klíčů a digitální podpisy. |   3   | D/V  |
| 4.15.2 | Ověřte, že systémy kvantového rozdělení klíčů (QKD) jsou implementovány pro vysoce zabezpečenou komunikaci v oblasti umělé inteligence s protokoly pro správu klíčů odolnými vůči kvantovým útokům.                 |   3   | D/V  |
| 4.15.3 | Ověřte, že rámce kryptografické agility umožňují rychlou migraci na nové postkvantové algoritmy s automatizovanou rotací certifikátů a klíčů.                                                                       |   3   | D/V  |
| 4.15.4 | Ověřte, že kvantové modelování hrozeb hodnotí zranitelnost infrastruktury AI vůči kvantovým útokům s dokumentovanými časovými plány migrace a hodnocením rizik.                                                     |   3   |  V   |
| 4.15.5 | Ověřte, že hybridní klasicko-kvantové kryptografické systémy poskytují obranu v hloubce během období přechodu na kvantové technologie spolu s monitorováním výkonu.                                                 |   3   | D/V  |

---

## C4.16 Důvěrné zpracování a bezpečné enklávy

Chraňte pracovní zatížení AI a váhy modelů pomocí hardwarově založených důvěryhodných výpočetních prostředí a technologií důvěrného výpočtu.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Ověřte, že citlivé AI modely běží v rámci Intel SGX enclave, AMD SEV-SNP nebo ARM TrustZone s šifrovanou pamětí a ověřením attestace.                                    |   3   | D/V  |
| 4.16.2 | Ověřte, že důvěrné kontejnery (Kata Containers, gVisor s důvěrným výpočtem) izolují pracovní zatížení umělé inteligence pomocí hardwarem vynuceného šifrování paměti.    |   3   | D/V  |
| 4.16.3 | Ověřte, že vzdálené osvědčení (remote attestation) potvrzuje integritu enclave před načtením AI modelů pomocí kryptografického důkazu autentizity výpočetního prostředí. |   3   | D/V  |
| 4.16.4 | Ověřte, že důvěrné AI inference služby zabraňují extrakci modelu prostřednictvím šifrovaného výpočtu se zapečetěnými vahami modelu a chráněným prováděním.               |   3   | D/V  |
| 4.16.5 | Ověřte, že orchestraci důvěryhodného vykonávacího prostředí spravuje životní cyklus zabezpečené enklávy pomocí vzdálené autentizace a šifrovaných komunikačních kanálů.  |   3   | D/V  |
| 4.16.6 | Ověřte, že zabezpečené vícestranné výpočty (SMPC) umožňují spolupráci při trénování AI, aniž by docházelo k odhalení jednotlivých datových sad nebo parametrů modelu.    |   3   | D/V  |

---

## C4.17 Infrastruktura s nulovým vědomím

Implementujte systémy dokazování s nulovým znalostním vstupem pro verifikaci a autentizaci AI chránící soukromí bez odhalení citlivých informací.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.17.1 | Ověřte, že důkazy s nulovou znalostí (ZK-SNARKs, ZK-STARKs) ověřují integritu AI modelu a původ tréninku, aniž by odhalovaly váhy modelu nebo tréninková data.           |   3   | D/V  |
| 4.17.2 | Ověřte, že autentizační systémy založené na ZK umožňují uživatelskou verifikaci s ochranou soukromí pro AI služby, aniž by odhalovaly informace související s identitou. |   3   | D/V  |
| 4.17.3 | Ověřte, že protokoly soukromé množinové průniku (PSI) umožňují bezpečné párování dat pro federované AI, aniž by docházelo k odhalení jednotlivých datových sad.          |   3   | D/V  |
| 4.17.4 | Ověřte, že systémy zero-knowledge strojového učení (ZKML) umožňují ověřitelné AI inferenční závěry s kryptografickým důkazem správného výpočtu.                          |   3   | D/V  |
| 4.17.5 | Ověřte, že ZK-rollupy poskytují škálovatelné, na soukromí založené zpracování AI transakcí s dávkovou verifikací a sníženou výpočetní náročností.                        |   3   | D/V  |

---

## C4.18 Prevence útoků postranním kanálem

Chraňte infrastrukturu umělé inteligence před útoky postranními kanály založenými na čase, napájení, elektromagnetických vlnách a cache, které by mohly uniknout citlivé informace.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Ověřte, že časování inferenčního procesu AI je normalizováno pomocí algoritmů s konstantním časem a doplněními, aby se zabránilo útokům na model založeným na analýze časování. |   3   | D/V  |
| 4.18.2 | Ověřte, že ochrana proti analýze spotřeby zahrnuje vkládání šumu, filtrování napájecí linie a náhodné vzory vykonávání pro AI hardware.                                         |   3   | D/V  |
| 4.18.3 | Ověřte, že zmírnění postranních kanálů založených na cache používá dělení cache, randomizaci a instrukce vymazání (flush) k zabránění úniku informací.                          |   3   | D/V  |
| 4.18.4 | Ověřte, že ochrana proti elektromagnetickému vyzařování zahrnuje stínění, filtrování signálu a náhodné zpracování, aby se zabránilo útokům typu TEMPEST.                        |   3   | D/V  |
| 4.18.5 | Ověřte, že obrany proti mikroarchitektonickým postranním kanálům zahrnují řízení spekulativního provádění a zakrývání vzorců přístupu do paměti.                                |   3   | D/V  |

---

## C4.19 Neuromorfní a specializovaný hardwar pro bezpečnost AI

Zajistěte zabezpečení nově vznikajících hardwarových architektur AI, včetně neuronových čipů, FPGA, vlastních ASIC a optických výpočetních systémů.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Ověřte, že bezpečnost neuromorfního čipu zahrnuje šifrování vzorů spike, ochranu synaptických vah a ověřování učebních pravidel založené na hardwaru.                       |   3   | D/V  |
| 4.19.2 | Ověřte, že AI akcelerátory založené na FPGA implementují šifrování bitstreamu, mechanismy proti manipulaci a bezpečné načítání konfigurace s autentizovanými aktualizacemi. |   3   | D/V  |
| 4.19.3 | Ověřte, že vlastní zabezpečení ASIC zahrnuje bezpečnostní procesory na čipu, hardwarový kořen důvěryhodnosti a bezpečné ukládání klíčů s detekcí pokusu o narušení.         |   3   | D/V  |
| 4.19.4 | Ověřte, že optické výpočetní systémy implementují kvantově bezpečné optické šifrování, bezpečné fotonické přepínání a chráněné optické zpracování signálů.                  |   3   | D/V  |
| 4.19.5 | Ověřte, že hybridní analogově-digitální čipy AI zahrnují zabezpečené analogové výpočty, chráněné uložení vah a autentizovanou analogově-digitální konverzi.                 |   3   | D/V  |

---

## C4.20 Infrastruktura pro výpočty zachovávající soukromí

Implementujte infrastrukturní kontroly pro výpočty šetřící soukromí, aby byla chráněna citlivá data během zpracování a analýzy umělou inteligencí.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Ověřte, zda infrastruktura homomorfního šifrování umožňuje šifrované výpočty na citlivých pracovních zátěžích AI s kryptografickou kontrolou integrity a monitorováním výkonu.               |   3   | D/V  |
| 4.20.2 | Ověřte, že systémy pro soukromé vyhledávání informací umožňují dotazy do databází, aniž by odhalovaly vzory dotazů, pomocí kryptografické ochrany přístupových vzorů.                        |   3   | D/V  |
| 4.20.3 | Ověřte, že protokoly zabezpečených vícestranných výpočtů umožňují provádění AI inference s ochranou soukromí, aniž by odhalovaly jednotlivé vstupy nebo mezilehlé výpočty.                   |   3   | D/V  |
| 4.20.4 | Ověřte, že správa klíčů s ochranou soukromí zahrnuje distribuovanou generaci klíčů, prahovou kryptografii a bezpečnou rotaci klíčů s hardwarovou ochranou.                                   |   3   | D/V  |
| 4.20.5 | Ověřte, že výkon výpočtů chránících soukromí je optimalizován prostřednictvím dávkování, ukládání do mezipaměti a hardwarové akcelerace při zachování kryptografických bezpečnostních záruk. |   3   | D/V  |

---

## C4.15 Agentový rámec Integrace bezpečnosti cloudu a hybridní nasazení

Bezpečnostní kontroly pro cloudově integrované agentní rámce s hybridními on-premises/cloud architekturami.

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Ověřte, že integrace cloudového úložiště používá šifrování od konce ke konci s řízenou správou klíčů agentem.                           |   1   | D/V  |
| 4.15.2 | Ověřte, že hranice zabezpečení u hybridního nasazení jsou jasně definovány s využitím šifrovaných komunikačních kanálů.                 |   2   | D/V  |
| 4.15.3 | Ověřte, že přístup ke cloudovým zdrojům zahrnuje ověření zero-trust s kontinuální autentizací.                                          |   2   | D/V  |
| 4.15.4 | Ověřte, že požadavky na umístění dat jsou vynucovány kryptografickým potvrzením umístění úložiště.                                      |   3   | D/V  |
| 4.15.5 | Ověřte, že bezpečnostní posouzení poskytovatele cloudových služeb zahrnují modelování hrozeb specifických pro agenty a hodnocení rizik. |   3   | D/V  |

---

## Reference

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

