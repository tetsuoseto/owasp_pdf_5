# Bezpieczeństwo infrastruktury C4, konfiguracji i wdrożeń

## Cel Kontrolny

Infrastruktura AI musi być zabezpieczona przed eskalacją uprawnień, manipulacją łańcuchem dostaw i ruchem bocznym poprzez bezpieczną konfigurację, izolację w czasie działania, zaufane procesy wdrażania oraz kompleksowy monitoring. Tylko autoryzowane, zweryfikowane komponenty infrastruktury i konfiguracje trafiają do produkcji poprzez kontrolowane procesy, które zapewniają bezpieczeństwo, integralność i możliwość audytu.

Główny cel bezpieczeństwa: Tylko komponenty infrastruktury z podpisem kryptograficznym i przeskanowane pod kątem podatności trafiają do produkcji przez zautomatyzowane potoki walidacyjne, które egzekwują polityki bezpieczeństwa i utrzymują niemodyfikowalne ścieżki audytu.

---

## C4.1 Izolacja środowiska uruchomieniowego

Zapobiegaj ucieczkom z kontenerów i eskalacji przywilejów poprzez prymitywy izolacji na poziomie jądra oraz obowiązkowe kontrole dostępu.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Zweryfikuj, czy wszystkie kontenery AI usuwają WSZYSTKIE możliwości Linuksa z wyjątkiem CAP_SETUID, CAP_SETGID oraz wyraźnie wymaganych możliwości udokumentowanych w bazach bezpieczeństwa.                                                         |   1   | D/V  |
| 4.1.2 | Zweryfikuj, czy profile seccomp blokują wszystkie wywołania systemowe, poza tymi na wcześniej zatwierdzonych listach dozwolonych, przy czym naruszenia skutkują zakończeniem kontenera i generowaniem alertów bezpieczeństwa.                        |   1   | D/V  |
| 4.1.3 | Zweryfikuj, czy obciążenia AI działają z systemami plików root w trybie tylko do odczytu, tmpfs dla danych tymczasowych oraz nazwanymi woluminami dla danych trwałych z wymuszonymi opcjami montowania noexec.                                       |   2   | D/V  |
| 4.1.4 | Zweryfikuj, czy monitorowanie czasu rzeczywistego oparte na eBPF (Falco, Tetragon lub równoważne) wykrywa próby eskalacji uprawnień i automatycznie kończy działanie procesów naruszających zasady zgodnie z wymogami czasowymi reakcji organizacji. |   2   | D/V  |
| 4.1.5 | Zweryfikuj, czy obciążenia AI o wysokim ryzyku są wykonywane w środowiskach izolowanych sprzętowo (Intel TXT, AMD SVM lub dedykowane węzły bare-metal) z weryfikacją atestacji.                                                                      |   3   | D/V  |

---

## C4.2 Bezpieczne procesy budowy i wdrażania

Zapewnij integralność kryptograficzną oraz bezpieczeństwo łańcucha dostaw poprzez odtwarzalne kompilacje i podpisane artefakty.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Zweryfikuj, czy infrastruktura jako kod jest skanowana za pomocą narzędzi (tfsec, Checkov lub Terrascan) przy każdym commicie, blokując scalanie w przypadku znalezienia błędów o KRYTYCZNYM lub WYSOKIM poziomie zagrożenia. |   1   | D/V  |
| 4.2.2 | Zweryfikuj, czy budowy kontenerów są powtarzalne z identycznymi skrótami SHA256 we wszystkich kompilacjach oraz wygeneruj poświadczenia pochodzenia poziomu SLSA 3 podpisane przez Sigstore.                                  |   1   | D/V  |
| 4.2.3 | Zweryfikuj, czy obrazy kontenerów zawierają osadzone SBOM-y CycloneDX lub SPDX oraz czy są podpisane za pomocą Cosign przed wysłaniem do rejestru, przy czym obrazy niepodpisane powinny być odrzucane podczas wdrożenia.     |   2   | D/V  |
| 4.2.4 | Zweryfikuj, czy potoki CI/CD używają tokenów OIDC z HashiCorp Vault, ról AWS IAM lub zarządzanej tożsamości Azure, których czas życia nie przekracza limitów określonych w polityce bezpieczeństwa organizacji.               |   2   | D/V  |
| 4.2.5 | Zweryfikuj, czy podpisy Cosign oraz pochodzenie SLSA są sprawdzane podczas procesu wdrażania przed uruchomieniem kontenera, a błędy weryfikacji powodują niepowodzenie wdrożenia.                                             |   2   | D/V  |
| 4.2.6 | Zweryfikuj, czy środowiska budowania działają w tymczasowych kontenerach lub maszynach wirtualnych bez trwałej pamięci oraz z izolacją sieciową od produkcyjnych VPC.                                                         |   2   | D/V  |

---

## C4.3 Bezpieczeństwo sieci i kontrola dostępu

Wdrażaj sieciowanie zero-trust z domyślnymi politykami odmowy i zaszyfrowaną komunikacją.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Zweryfikuj, czy Kubernetes NetworkPolicies lub ich odpowiednik implementują domyślną politykę deny ingress/egress z wyraźnymi regułami zezwalającymi na wymagane porty (443, 8080 itp.).                        |   1   | D/V  |
| 4.3.2 | Zweryfikuj, czy SSH (port 22), RDP (port 3389) oraz punkty końcowe metadanych chmury (169.254.169.254) są zablokowane lub wymagają uwierzytelniania opartego na certyfikacie.                                   |   1   | D/V  |
| 4.3.3 | Zweryfikuj, czy ruch wychodzący jest filtrowany przez proxy HTTP/HTTPS (Squid, Istio lub bramy NAT w chmurze) z listami dozwolonych domen, a zablokowane żądania są rejestrowane.                               |   2   | D/V  |
| 4.3.4 | Zweryfikuj, czy komunikacja między usługami korzysta z wzajemnego TLS z certyfikatami rotowanymi zgodnie z polityką organizacyjną oraz czy walidacja certyfikatów jest wymuszona (bez użycia flag skip-verify). |   2   | D/V  |
| 4.3.5 | Zweryfikuj, czy infrastruktura AI działa w dedykowanych VPC/VNetach bez bezpośredniego dostępu do internetu i komunikuje się wyłącznie przez bramy NAT lub hosty bastionowe.                                    |   2   | D/V  |

---

## C4.4 Zarządzanie sekretami i kluczami kryptograficznymi

Chroń poświadczenia za pomocą sprzętowego magazynowania i automatycznej rotacji z dostępem opartym na zasadzie zero-zaufania.

|   #   | Description                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Zweryfikuj, czy tajne dane są przechowywane w HashiCorp Vault, AWS Secrets Manager, Azure Key Vault lub Google Secret Manager z szyfrowaniem danych spoczynkowych za pomocą AES-256.                                                                            |   1   | D/V  |
| 4.4.2 | Zweryfikuj, czy klucze kryptograficzne są generowane w HSM zgodnych z poziomem 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) z rotacją kluczy zgodnie z organizacyjną polityką kryptograficzną.                                                              |   1   | D/V  |
| 4.4.3 | Zweryfikuj, czy rotacja sekretów jest zautomatyzowana z wdrożeniem bez okresów przestojów oraz czy natychmiastowa rotacja jest wyzwalana przez zmiany personelu lub incydenty bezpieczeństwa.                                                                   |   2   | D/V  |
| 4.4.4 | Zweryfikuj, czy obrazy kontenerów są skanowane za pomocą narzędzi (GitLeaks, TruffleHog lub detect-secrets), blokujących kompilacje zawierające klucze API, hasła lub certyfikaty.                                                                              |   2   | D/V  |
| 4.4.5 | Zweryfikuj, czy dostęp do sekretów produkcyjnych wymaga uwierzytelniania wieloskładnikowego (MFA) za pomocą tokenów sprzętowych (YubiKey, FIDO2) oraz czy jest rejestrowany w niezmiennych dziennikach audytu z identyfikacją użytkowników i znacznikami czasu. |   2   | D/V  |
| 4.4.6 | Zweryfikuj, czy sekrety są wstrzykiwane za pomocą sekretów Kubernetes, montowanych woluminów lub kontenerów inicjujących oraz upewnij się, że sekrety nigdy nie są osadzane w zmiennych środowiskowych ani obrazach.                                            |   2   | D/V  |

---

## C4.5 Izolacja i walidacja obciążenia AI

Izoluj niezweryfikowane modele AI w bezpiecznych piaskownicach z kompleksową analizą zachowania.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Zweryfikuj, czy zewnętrzne modele AI działają w gVisor, mikroVM (takich jak Firecracker, CrossVM) lub kontenerach Docker z opcjami --security-opt=no-new-privileges oraz --read-only.                             |   1   | D/V  |
| 4.5.2 | Zweryfikuj, czy środowiska typu sandbox nie mają dostępu do sieci (--network=none) lub mają dostęp tylko do localhost, przy czym wszystkie zewnętrzne żądania są blokowane przez reguły iptables.                 |   1   | D/V  |
| 4.5.3 | Zweryfikuj, czy walidacja modelu AI obejmuje zautomatyzowane testy red-team z zakresami testów określonymi przez organizację oraz analizę zachowań w celu wykrywania tylnych drzwi.                               |   2   | D/V  |
| 4.5.4 | Zweryfikuj, czy przed wdrożeniem modelu AI do produkcji, jego wyniki z piaskownicy są podpisane kryptograficznie przez upoważniony personel ds. bezpieczeństwa i przechowywane w niezmiennych dziennikach audytu. |   2   | D/V  |
| 4.5.5 | Zweryfikuj, czy środowiska piaskownicy są usuwane i odtwarzane z obrazów wzorcowych między ocenami, z pełnym oczyszczeniem systemu plików i pamięci.                                                              |   2   | D/V  |

---

## C4.6 Monitorowanie bezpieczeństwa infrastruktury

Ciągłe skanowanie i monitorowanie infrastruktury z automatycznym naprawianiem i powiadamianiem w czasie rzeczywistym.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Zweryfikuj, czy obrazy kontenerów są skanowane zgodnie z harmonogramami organizacyjnymi, przy czym podatności KLUCZOWE blokują wdrożenie na podstawie progów ryzyka organizacyjnego.                                                                     |   1   | D/V  |
| 4.6.2 | Zweryfikuj, czy infrastruktura spełnia kryteria CIS Benchmarks lub kontrole NIST 800-53 zgodnie z organizacyjnie zdefiniowanymi progami zgodności oraz automatycznym naprawianiem wykrytych niezgodności.                                                |   1   | D/V  |
| 4.6.3 | Zweryfikuj, czy podatności o WYSOKIM poziomie zagrożenia są łagodzone zgodnie z harmonogramami zarządzania ryzykiem organizacji, z zastosowaniem procedur awaryjnych dla aktywnie wykorzystywanych CVE.                                                  |   2   | D/V  |
| 4.6.4 | Zweryfikuj, czy alerty bezpieczeństwa integrują się z platformami SIEM (Splunk, Elastic lub Sentinel) za pomocą formatów CEF lub STIX/TAXII z automatycznym wzbogacaniem.                                                                                |   2   |  V   |
| 4.6.5 | Zweryfikuj, czy metryki infrastruktury są eksportowane do systemów monitorowania (Prometheus, DataDog) wraz z pulpitami SLA i raportowaniem wykonawczym.                                                                                                 |   3   |  V   |
| 4.6.6 | Zweryfikuj, czy wykrywanie odchyleń w konfiguracji jest realizowane za pomocą narzędzi (Chef InSpec, AWS Config) zgodnie z wymaganiami organizacyjnymi dotyczącymi monitoringu, z automatycznym przywracaniem stanu w przypadku nieautoryzowanych zmian. |   2   | D/V  |

---

## Zarządzanie Zasobami Infrastruktury AI C4.7

Zapobiegaj atakom wyczerpania zasobów i zapewniaj uczciwy podział zasobów poprzez limity i monitorowanie.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Zweryfikuj, czy wykorzystanie GPU/TPU jest monitorowane, a alerty są wyzwalane przy progach zdefiniowanych przez organizację oraz czy automatyczne skalowanie lub równoważenie obciążenia są aktywowane na podstawie polityk zarządzania pojemnością. |   1   | D/V  |
| 4.7.2 | Zweryfikuj, czy metryki obciążenia AI (opóźnienie inferencji, przepustowość, wskaźniki błędów) są zbierane zgodnie z wymaganiami monitoringu organizacyjnego i skorelowane z wykorzystaniem infrastruktury.                                           |   1   | D/V  |
| 4.7.3 | Zweryfikuj, czy Kubernetes ResourceQuotas lub odpowiednik ograniczają poszczególne zadania zgodnie z politykami alokacji zasobów organizacji, zapewniając wymuszanie sztywnych limitów.                                                               |   2   | D/V  |
| 4.7.4 | Zweryfikuj, czy monitorowanie kosztów śledzi wydatki według obciążenia/tenantów z alertami opartymi na progach budżetowych organizacji oraz automatycznymi kontrolami przekroczeń budżetu.                                                            |   2   |  V   |
| 4.7.5 | Zweryfikuj, czy planowanie pojemności korzysta z danych historycznych zorganizowanych według zdefiniowanych przez organizację okresów prognozowania oraz czy automatyczne przydzielanie zasobów jest oparte na wzorcach zapotrzebowania.              |   3   |  V   |
| 4.7.6 | Zweryfikuj, czy wyczerpanie zasobów wywołuje mechanizmy zabezpieczeń obwodu zgodnie z wymaganiami odpowiedzi organizacyjnej, w tym ograniczanie szybkości na podstawie polityk pojemności oraz izolację obciążenia.                                   |   2   | D/V  |

---

## C4.8 Kontrola separacji środowisk i promocji

Wymuszaj surowe granice środowiskowe za pomocą automatycznych bramek promocyjnych i walidacji bezpieczeństwa.

|   #   | Description                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Zweryfikuj, czy środowiska deweloperskie/testowe/produkcyjne działają w oddzielnych VPC/VNetach bez wspólnych ról IAM, grup zabezpieczeń ani łączności sieciowej.                                                                                   |   1   | D/V  |
| 4.8.2 | Zweryfikuj, czy promowanie środowiska wymaga zatwierdzenia przez organizacyjnie określony uprawniony personel za pomocą podpisów kryptograficznych oraz niezmiennych ścieżek audytu.                                                                |   1   | D/V  |
| 4.8.3 | Zweryfikuj, czy środowiska produkcyjne blokują dostęp SSH, wyłączają punkty końcowe debugowania oraz wymagają zgłoszeń zmian z obowiązkowym wcześniejszym powiadomieniem organizacji, z wyjątkiem sytuacji awaryjnych.                              |   2   | D/V  |
| 4.8.4 | Zweryfikuj, czy zmiany w infrastrukturze jako kod wymagają przeglądu przez kolegę wraz z automatycznym testowaniem i skanowaniem bezpieczeństwa przed scaleniem do głównej gałęzi.                                                                  |   2   | D/V  |
| 4.8.5 | Zweryfikuj, czy dane nieprodukcyjne są anonimizowane zgodnie z organizacyjnymi wymogami dotyczącymi prywatności, generowaniem danych syntetycznych lub pełnym maskowaniem danych z usunięciem informacji pozwalających na identyfikację osób (PII). |   2   | D/V  |
| 4.8.6 | Zweryfikuj, czy bramki promocyjne obejmują zautomatyzowane testy bezpieczeństwa (SAST, DAST, skanowanie kontenerów) z wymaganiem zerowej liczby krytycznych usterek do zatwierdzenia.                                                               |   2   | D/V  |

---

## C4.9 Kopia zapasowa i odzyskiwanie infrastruktury

Zapewnij odporność infrastruktury poprzez automatyczne tworzenie kopii zapasowych, przetestowane procedury odzyskiwania oraz możliwości odzyskiwania po awarii.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.9.1 | Zweryfikuj, czy konfiguracje infrastruktury są archiwizowane zgodnie z harmonogramami kopii zapasowych organizacji do geograficznie oddzielonych regionów z zastosowaniem strategii kopii zapasowej 3-2-1.                                 |   1   | D/V  |
| 4.9.2 | Zweryfikuj, czy systemy kopii zapasowych działają w izolowanych sieciach z oddzielnymi danymi uwierzytelniającymi oraz przechowywaniem na nośnikach odseparowanych fizycznie (air-gapped) w celu ochrony przed oprogramowaniem ransomware. |   2   | D/V  |
| 4.9.3 | Zweryfikuj, czy procedury odzyskiwania są testowane i weryfikowane za pomocą automatycznych testów zgodnie z harmonogramami organizacji, przy czym cele RTO i RPO spełniają wymagania organizacyjne.                                       |   2   |  V   |
| 4.9.4 | Zweryfikuj, czy plan odzyskiwania po awarii zawiera specyficzne dla AI instrukcje postępowania, obejmujące przywracanie wag modelu, odbudowę klastra GPU oraz mapowanie zależności serwisów.                                               |   3   |  V   |

---

## C4.10 Zgodność i Zarządzanie Infrastrukturą

Utrzymuj zgodność z przepisami poprzez ciągłą ocenę, dokumentację i zautomatyzowane kontrole.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Zweryfikuj, czy zgodność infrastruktury jest oceniana zgodnie z harmonogramami organizacji w odniesieniu do kontroli SOC 2, ISO 27001 lub FedRAMP, z automatycznym zbieraniem dowodów. |   2   | D/V  |
| 4.10.2 | Zweryfikuj, czy dokumentacja infrastruktury zawiera diagramy sieci, mapy przepływu danych oraz modele zagrożeń aktualizowane zgodnie z wymaganiami zarządzania zmianami w organizacji. |   2   |  V   |
| 4.10.3 | Zweryfikuj, czy zmiany w infrastrukturze przechodzą automatyczną ocenę wpływu na zgodność z przepływami zatwierdzania regulacyjnego dla modyfikacji wysokiego ryzyka.                  |   3   | D/V  |

---

## C4.11 Bezpieczeństwo sprzętu AI

Zabezpiecz specyficzne dla AI komponenty sprzętowe, w tym GPU, TPU oraz specjalistyczne akceleratory AI.

|   #    | Description                                                                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.11.1 | Zweryfikuj, czy oprogramowanie układowe akceleratora AI (BIOS GPU, oprogramowanie układowe TPU) jest weryfikowane za pomocą podpisów kryptograficznych i aktualizowane zgodnie z harmonogramem zarządzania poprawkami w organizacji. |   2   | D/V  |
| 4.11.2 | Zweryfikuj, czy przed wykonaniem zadania integralność akceleratora AI jest potwierdzana przez sprzętową attestację za pomocą TPM 2.0, Intel TXT lub AMD SVM.                                                                         |   2   | D/V  |
| 4.11.3 | Zweryfikuj, czy pamięć GPU jest izolowana między obciążeniami przy użyciu SR-IOV, MIG (Multi-Instance GPU) lub równoważnego sprzętowego podziału z sanitizacją pamięci między zadaniami.                                             |   2   | D/V  |
| 4.11.4 | Zweryfikuj, czy łańcuch dostaw sprzętu AI obejmuje weryfikację pochodzenia za pomocą certyfikatów producenta oraz walidację opakowań zabezpieczających przed manipulacją.                                                            |   3   |  V   |
| 4.11.5 | Zweryfikuj, czy moduły bezpieczeństwa sprzętowego (HSM) chronią wagi modeli AI oraz klucze kryptograficzne z certyfikacją FIPS 140-2 Poziom 3 lub Common Criteria EAL4+.                                                             |   3   | D/V  |

---

## C4.12 Infrastruktura AI brzegowej i rozproszonej

Bezpieczne rozproszone wdrożenia AI, w tym obliczenia brzegowe, uczenie federacyjne oraz architektury wielostanowiskowe.

|   #    | Description                                                                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Zweryfikuj, czy urządzenia edge AI uwierzytelniają się w centralnej infrastrukturze za pomocą wzajemnego TLS z certyfikatami urządzeń rotowanymi zgodnie z organizacyjną polityką zarządzania certyfikatami.              |   2   | D/V  |
| 4.12.2 | Zweryfikuj, czy urządzenia brzegowe implementują bezpieczne uruchamianie z weryfikowanymi podpisami oraz ochronę przed wycofaniem wersji, zapobiegającą atakom polegającym na obniżaniu wersji oprogramowania układowego. |   2   | D/V  |
| 4.12.3 | Zweryfikuj, czy skoordynowana sztuczna inteligencja rozproszona korzysta z odpornych na błędy bizantyjskie algorytmów konsensusu z walidacją uczestników i wykrywaniem złośliwych węzłów.                                 |   3   | D/V  |
| 4.12.4 | Zweryfikuj, czy komunikacja krawędź-chmura obejmuje ograniczanie przepustowości, kompresję danych oraz możliwości pracy offline z bezpiecznym lokalnym przechowywaniem.                                                   |   3   | D/V  |

---

## C4.13 Bezpieczeństwo infrastruktury wielochmurowej i hybrydowej

Zabezpiecz obciążenia AI w wielu dostawcach chmury i wdrożeniach hybrydowych chmury oraz lokalnych.

|   #    | Description                                                                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Zweryfikuj, czy wdrożenia AI w środowisku multi-cloud korzystają z niezależnej od chmury federacji tożsamości (OIDC, SAML) z centralnym zarządzaniem politykami pomiędzy dostawcami.                        |   2   | D/V  |
| 4.13.2 | Zweryfikuj, czy transfer danych między chmurami korzysta z szyfrowania end-to-end za pomocą kluczy zarządzanych przez klienta oraz czy kontrola lokalizacji danych jest egzekwowana zgodnie z jurysdykcją.  |   2   | D/V  |
| 4.13.3 | Zweryfikuj, czy hybrydowe obciążenia AI w chmurze implementują spójne polityki bezpieczeństwa zarówno w środowiskach lokalnych, jak i chmurowych, zjednoczone pod kątem monitoringu i powiadamiania.        |   2   | D/V  |
| 4.13.4 | Zweryfikuj, czy zapobieganie uzależnieniu od dostawcy chmury obejmuje przenośną infrastrukturę jako kod, znormalizowane interfejsy API oraz możliwości eksportu danych z narzędziami do konwersji formatów. |   3   |  V   |
| 4.13.5 | Zweryfikuj, czy optymalizacja kosztów multi-cloud obejmuje kontrole bezpieczeństwa zapobiegające rozproszeniu zasobów oraz nieautoryzowanym opłatom za transfer danych między chmurami.                     |   3   |  V   |

---

## C4.14 Automatyzacja infrastruktury i bezpieczeństwo GitOps

Zabezpieczone rury automatyzacji infrastruktury oraz przepływy pracy GitOps do zarządzania infrastrukturą AI.

|   #    | Description                                                                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Zweryfikuj, że repozytoria GitOps wymagają podpisanych commitów za pomocą kluczy GPG oraz reguł ochrony gałęzi zapobiegających bezpośrednim pushom do głównych gałęzi.                                                            |   2   | D/V  |
| 4.14.2 | Zweryfikuj, czy automatyzacja infrastruktury obejmuje wykrywanie dryfu wraz z automatycznymi możliwościami naprawy i przywracania, uruchamianymi zgodnie z wymaganiami organizacji dotyczącymi reakcji na nieautoryzowane zmiany. |   2   | D/V  |
| 4.14.3 | Zweryfikuj, czy zautomatyzowane wdrażanie infrastruktury obejmuje walidację polityki bezpieczeństwa wraz z blokowaniem wdrożenia w przypadku niezgodnych konfiguracji.                                                            |   2   | D/V  |
| 4.14.4 | Sprawdź, czy tajemnice automatyzacji infrastruktury są zarządzane za pomocą zewnętrznych operatorów sekretów (External Secrets Operator, Bank-Vaults) z automatyczną rotacją.                                                     |   2   | D/V  |
| 4.14.5 | Zweryfikuj, czy infrastruktura samonaprawcza obejmuje korelację zdarzeń związanych z bezpieczeństwem z automatyczną reakcją na incydenty oraz przepływami pracy powiadamiania interesariuszy.                                     |   3   |  V   |

---

## C4.15 Kwantowo-odporna bezpieczeństwo infrastruktury

Przygotuj infrastrukturę AI na zagrożenia związane z obliczeniami kwantowymi poprzez kryptografię post-kwantową oraz protokoły bezpieczne kwantowo.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Zweryfikuj, czy infrastruktura AI implementuje zatwierdzone przez NIST postkwantowe algorytmy kryptograficzne (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) do wymiany kluczy i podpisów cyfrowych. |   3   | D/V  |
| 4.15.2 | Zweryfikuj, czy systemy dystrybucji kluczy kwantowych (QKD) są wdrażane dla komunikacji AI o wysokim poziomie bezpieczeństwa z protokołami zarządzania kluczami odpornymi na ataki kwantowe.         |   3   | D/V  |
| 4.15.3 | Zweryfikuj, czy ramy kryptograficznej elastyczności umożliwiają szybkie przejście na nowe algorytmy postkwantowe wraz z automatyczną rotacją certyfikatów i kluczy.                                  |   3   | D/V  |
| 4.15.4 | Zweryfikuj, czy modelowanie zagrożeń kwantowych ocenia podatność infrastruktury AI na ataki kwantowe, uwzględniając udokumentowane harmonogramy migracji oraz oceny ryzyka.                          |   3   |  V   |
| 4.15.5 | Zweryfikuj, czy hybrydowe klasyczno-kwantowe systemy kryptograficzne zapewniają obronę wielowarstwową podczas okresu przejściowego do kwantowego, wraz z monitorowaniem wydajności.                  |   3   | D/V  |

---

## C4.16 Obliczenia poufne i zabezpieczone enklawy

Chroń obciążenia AI i wagi modeli za pomocą sprzętowych środowisk zaufanego wykonania oraz technologii obliczeń poufnych.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Zweryfikuj, że wrażliwe modele AI działają w obrębie enklaw Intel SGX, AMD SEV-SNP lub ARM TrustZone z zaszyfrowaną pamięcią i weryfikacją atestacji.                           |   3   | D/V  |
| 4.16.2 | Zweryfikuj, czy poufne kontenery (Kata Containers, gVisor z poufnym przetwarzaniem) izolują obciążenia AI za pomocą sprzętowego szyfrowania pamięci.                            |   3   | D/V  |
| 4.16.3 | Zweryfikuj, czy zdalna atestacja potwierdza integralność enklawy przed załadowaniem modeli AI, wykorzystując kryptograficzny dowód autentyczności środowiska wykonawczego.      |   3   | D/V  |
| 4.16.4 | Zweryfikuj, czy poufne usługi wnioskowania AI zapobiegają ekstrakcji modelu poprzez szyfrowane obliczenia z zamkniętymi wagami modelu i chronionym wykonaniem.                  |   3   | D/V  |
| 4.16.5 | Zweryfikuj, czy orkiestracja zaufanego środowiska wykonawczego zarządza cyklem życia bezpiecznego enklawy za pomocą zdalnej atestacji i zaszyfrowanych kanałów komunikacyjnych. |   3   | D/V  |
| 4.16.6 | Zweryfikuj, czy bezpieczne obliczenia wielostronne (SMPC) umożliwiają wspólne trenowanie AI bez ujawniania indywidualnych zbiorów danych lub parametrów modelu.                 |   3   | D/V  |

---

## C4.17 Infrastruktura Zero-Knowledge

Zaimplementuj systemy dowodów zerowej wiedzy do weryfikacji i uwierzytelniania AI z zachowaniem prywatności, bez ujawniania wrażliwych informacji.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Zweryfikuj, że dowody zero-knowledge (ZK-SNARKs, ZK-STARKs) potwierdzają integralność modelu AI i pochodzenie treningu bez ujawniania wag modelu ani danych treningowych.              |   3   | D/V  |
| 4.17.2 | Zweryfikuj, czy systemy uwierzytelniania oparte na ZK umożliwiają weryfikację użytkownika z zachowaniem prywatności w usługach AI, bez ujawniania informacji związanych z tożsamością. |   3   | D/V  |
| 4.17.3 | Zweryfikuj, czy protokoły prywatnego przecięcia zbiorów (PSI) umożliwiają bezpieczne dopasowywanie danych dla federacyjnej SI bez ujawniania poszczególnych zbiorów danych.            |   3   | D/V  |
| 4.17.4 | Zweryfikuj, że systemy uczenia maszynowego zero-knowledge (ZKML) umożliwiają weryfikowalne wnioski AI z kryptograficznym dowodem poprawności obliczeń.                                 |   3   | D/V  |
| 4.17.5 | Zweryfikuj, że ZK-rollupy zapewniają skalowalne, chroniące prywatność przetwarzanie transakcji AI z weryfikacją wsadową i zmniejszonym obciążeniem obliczeniowym.                      |   3   | D/V  |

---

## C4.18 Zapobieganie atakom kanałowym

Chroń infrastrukturę AI przed atakami bocznokanałowymi opartymi na czasie, mocy, elektromagnetyzmie i pamięci podręcznej, które mogą ujawnić wrażliwe informacje.

|   #    | Description                                                                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Zweryfikuj, czy czas inferencji AI jest normalizowany za pomocą algorytmów o stałym czasie działania oraz wypełnień, aby zapobiec atakom na model opartym na analizie czasu.                                     |   3   | D/V  |
| 4.18.2 | Zweryfikuj, czy ochrona przed analizą mocy obejmuje wprowadzanie szumów, filtrowanie linii zasilającej oraz losowe wzorce wykonywania dla sprzętu AI.                                                            |   3   | D/V  |
| 4.18.3 | Zweryfikuj, że łagodzenie ataków ubocznych opartych na pamięci podręcznej wykorzystuje partycjonowanie pamięci podręcznej, jej losowanie oraz instrukcje czyszczenia (flush), aby zapobiec wyciekowi informacji. |   3   | D/V  |
| 4.18.4 | Zweryfikuj, czy ochrona przed promieniowaniem elektromagnetycznym obejmuje ekranowanie, filtrowanie sygnałów oraz losowe przetwarzanie, aby zapobiec atakom w stylu TEMPEST.                                     |   3   | D/V  |
| 4.18.5 | Zweryfikuj, czy obrony przed bocznokanałowymi atakami mikroarchitektonicznymi obejmują kontrolę wykonania spekulacyjnego oraz zaciemnianie wzorców dostępu do pamięci.                                           |   3   | D/V  |

---

## C4.19 Neuromorficzne i specjalistyczne zabezpieczenia sprzętu AI

Zabezpieczyć nowe architektury sprzętowe AI, w tym układy neuromorficzne, FPGA, niestandardowe układy ASIC oraz systemy obliczeń optycznych.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Zweryfikuj, czy zabezpieczenia chipu neuromorficznego obejmują szyfrowanie wzorców impulsów, ochronę wag synaptycznych oraz weryfikację reguł uczenia opartą na sprzęcie.                               |   3   | D/V  |
| 4.19.2 | Zweryfikuj, czy akceleratory AI oparte na FPGA implementują szyfrowanie bitstreamu, mechanizmy przeciwdziałania manipulacjom oraz bezpieczne ładowanie konfiguracji z uwierzytelnionymi aktualizacjami. |   3   | D/V  |
| 4.19.3 | Zweryfikuj, czy bezpieczeństwo niestandardowego układu ASIC obejmuje procesory bezpieczeństwa na chipie, sprzętowy rdzeń zaufania oraz bezpieczne przechowywanie kluczy z detekcją manipulacji.         |   3   | D/V  |
| 4.19.4 | Zweryfikuj, czy systemy obliczeń optycznych wdrażają kwantowo bezpieczne szyfrowanie optyczne, bezpieczne przełączanie fotoniczne oraz chronione przetwarzanie sygnałów optycznych.                     |   3   | D/V  |
| 4.19.5 | Zweryfikuj, czy hybrydowe układy AI analogowo-cyfrowe zawierają bezpieczne obliczenia analogowe, chronione przechowywanie wag oraz uwierzytelnioną konwersję analogowo-cyfrową.                         |   3   | D/V  |

---

## Infrastruktura obliczeniowa z zachowaniem prywatności C4.20

Wdrożenie kontroli infrastrukturalnych dla obliczeń z zachowaniem prywatności w celu ochrony danych wrażliwych podczas przetwarzania i analizy AI.

|   #    | Description                                                                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Zweryfikuj, czy infrastruktura szyfrowania homomorficznego umożliwia wykonywanie obliczeń na zaszyfrowanych, wrażliwych obciążeniach sztucznej inteligencji z kryptograficzną weryfikacją integralności oraz monitorowaniem wydajności. |   3   | D/V  |
| 4.20.2 | Zweryfikuj, czy systemy prywatnego wyszukiwania informacji umożliwiają zapytania do bazy danych bez ujawniania wzorców zapytań poprzez kryptograficzną ochronę wzorców dostępu.                                                         |   3   | D/V  |
| 4.20.3 | Zweryfikuj, czy protokoły bezpiecznych obliczeń wielostronnych umożliwiają przeprowadzanie wnioskowania AI z zachowaniem prywatności, bez ujawniania pojedynczych danych wejściowych ani pośrednich obliczeń.                           |   3   | D/V  |
| 4.20.4 | Zweryfikuj, czy zarządzanie kluczami zapewniające prywatność obejmuje rozproszoną generację kluczy, kryptografię progową oraz bezpieczną rotację kluczy z ochroną wspieraną sprzętowo.                                                  |   3   | D/V  |
| 4.20.5 | Zweryfikuj, czy wydajność obliczeń z zachowaniem prywatności jest zoptymalizowana poprzez grupowanie wsadowe, buforowanie i przyspieszenie sprzętowe, przy jednoczesnym utrzymaniu gwarancji bezpieczeństwa kryptograficznego.          |   3   | D/V  |

---

## C4.15 Framework agenta Integracja z chmurą Bezpieczeństwo i wdrożenie hybrydowe

Kontrole bezpieczeństwa dla zintegrowanych z chmurą frameworków agentów z hybrydowymi architekturami on-premises/chmura.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Zweryfikuj, czy integracja z przechowywaniem danych w chmurze korzysta z szyfrowania end-to-end z zarządzaniem kluczami kontrolowanym przez agenta. |   1   | D/V  |
| 4.15.2 | Zweryfikuj, czy granice bezpieczeństwa wdrożenia hybrydowego są jasno określone i czy komunikacja odbywa się za pomocą zaszyfrowanych kanałów.      |   2   | D/V  |
| 4.15.3 | Zweryfikuj, czy dostęp do zasobów w chmurze obejmuje weryfikację zero-trust z ciągłą autoryzacją.                                                   |   2   | D/V  |
| 4.15.4 | Zweryfikuj, czy wymagania dotyczące lokalizacji danych są egzekwowane poprzez kryptograficzne potwierdzenie miejsc przechowywania.                  |   3   | D/V  |
| 4.15.5 | Zweryfikuj, czy oceny bezpieczeństwa dostawcy chmury obejmują modelowanie zagrożeń specyficzne dla agenta oraz ocenę ryzyka.                        |   3   | D/V  |

---

## Bibliografia

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

