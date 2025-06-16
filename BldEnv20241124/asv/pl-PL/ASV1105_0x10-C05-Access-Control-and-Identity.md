# Kontrola dostępu C5 i tożsamość dla komponentów i użytkowników AI

## Cel Kontroli

Skuteczna kontrola dostępu do systemów AI wymaga solidnego zarządzania tożsamością, autoryzacji uwzględniającej kontekst oraz egzekwowania zasad w czasie rzeczywistym zgodnie z zasadami zero-trust. Te mechanizmy zapewniają, że ludzie, usługi i autonomiczne agenty wchodzą w interakcje z modelami, danymi i zasobami obliczeniowymi tylko w ramach wyraźnie przyznanych uprawnień, z ciągłą weryfikacją i możliwością audytu.

---

## C5.1 Zarządzanie tożsamością i uwierzytelnianie

Utwórz kryptograficznie zabezpieczone tożsamości dla wszystkich podmiotów z uwierzytelnianiem wieloskładnikowym dla operacji uprzywilejowanych.

|   #   | Description                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.1.1 | Zweryfikuj, czy wszyscy użytkownicy ludzie i główne jednostki usługowe uwierzytelniają się za pośrednictwem scentralizowanego, korporacyjnego dostawcy tożsamości (IdP) przy użyciu protokołów OIDC/SAML z unikalnym mapowaniem tożsamości na tokeny (bez współdzielonych kont ani poświadczeń). |   1   | D/V  |
| 5.1.2 | Zweryfikuj, czy operacje wysokiego ryzyka (wdrożenie modelu, eksport wag, dostęp do danych treningowych, zmiany konfiguracji produkcyjnej) wymagają uwierzytelniania wieloskładnikowego lub uwierzytelniania podwyższonego z ponowną walidacją sesji.                                            |   1   | D/V  |
| 5.1.3 | Zweryfikuj, czy nowi administratorzy przechodzą proces potwierdzania tożsamości zgodny z NIST 800-63-3 IAL-2 lub równoważnymi standardami przed uzyskaniem dostępu do systemu produkcyjnego.                                                                                                     |   2   |  D   |
| 5.1.4 | Zweryfikuj, czy przeglądy dostępu są przeprowadzane kwartalnie z automatycznym wykrywaniem nieaktywnych kont, wymuszaniem rotacji poświadczeń oraz procesami deprowizji.                                                                                                                         |   2   |  V   |
| 5.1.5 | Zweryfikuj, czy federacyjne agenty AI uwierzytelniają się za pomocą podpisanych asercji JWT, które mają maksymalny okres ważności 24 godziny i zawierają kryptograficzny dowód pochodzenia.                                                                                                      |   3   | D/V  |

---

## C5.2 Autoryzacja zasobów i zasada najmniejszych uprawnień

Wdrożenie szczegółowej kontroli dostępu do wszystkich zasobów AI z wyraźnymi modelami uprawnień i ścieżkami audytu.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Zweryfikuj, czy każdy zasób AI (zbiory danych, modele, punkty końcowe, kolekcje wektorów, indeksy osadzeń, instancje obliczeniowe) wprowadza kontrolę dostępu opartą na rolach z wyraźnymi listami dozwolonych i domyślnymi politykami odrzucania.         |   1   | D/V  |
| 5.2.2 | Zweryfikuj, czy zasady najmniejszych uprawnień są domyślnie egzekwowane dla kont usługowych, zaczynając od uprawnień tylko do odczytu, a uzasadnienie biznesowe wymagane jest dokumentowane dla dostępu do zapisu.                                         |   1   | D/V  |
| 5.2.3 | Zweryfikuj, czy wszystkie modyfikacje kontroli dostępu są powiązane z zatwierdzonymi wnioskami o zmianę oraz czy są niezmiennie rejestrowane wraz z oznaczeniami czasowymi, tożsamościami aktorów, identyfikatorami zasobów i różnicami uprawnień.         |   1   |  V   |
| 5.2.4 | Zweryfikuj, czy etykiety klasyfikacji danych (Dane osobowe, Dane medyczne, kontrola eksportu, własność) automatycznie propagują się do pochodnych zasobów (osadzenia, pamięć podręczna podpowiedzi, wyniki modelu) z konsekwentnym egzekwowaniem polityki. |   2   |  D   |
| 5.2.5 | Zweryfikuj, czy próby nieautoryzowanego dostępu oraz zdarzenia eskalacji uprawnień wywołują alerty w czasie rzeczywistym z kontekstowymi metadanymi do systemów SIEM w ciągu 5 minut.                                                                      |   2   | D/V  |

---

## C5.3 Dynamiczna ewaluacja polityki

Wdrożenie mechanizmów kontroli dostępu opartej na atrybutach (ABAC) do podejmowania decyzji autoryzacyjnych opartych na kontekście z możliwością audytu.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Zweryfikuj, czy decyzje dotyczące autoryzacji są zewnętrznie przekazywane do dedykowanego silnika polityk (OPA, Cedar lub równoważnego), dostępowego za pośrednictwem uwierzytelnionych interfejsów API z ochroną integralności kryptograficznej. |   1   | D/V  |
| 5.3.2 | Zweryfikuj, czy polityki oceniają dynamiczne atrybuty podczas wykonywania, w tym poziom uprawnień użytkownika, klasyfikację poufności zasobu, kontekst żądania, izolację najemcy oraz ograniczenia czasowe.                                       |   1   | D/V  |
| 5.3.3 | Zweryfikuj, czy definicje polityk są wersjonowane, poddawane przeglądowi przez rówieśników oraz walidowane poprzez automatyczne testy w pipeline'ach CI/CD przed wdrożeniem do produkcji.                                                         |   2   |  D   |
| 5.3.4 | Zweryfikuj, czy wyniki oceny polityki zawierają ustrukturyzowane uzasadnienia decyzji i są przesyłane do systemów SIEM w celu analizy korelacji oraz raportowania zgodności.                                                                      |   2   |  V   |
| 5.3.5 | Zweryfikuj, czy wartości czasu życia (TTL) pamięci podręcznej polityk nie przekraczają 5 minut dla zasobów o wysokiej wrażliwości oraz 1 godziny dla zasobów standardowych z możliwością unieważniania pamięci podręcznej.                        |   3   | D/V  |

---

## C5.4 Egzekwowanie bezpieczeństwa w czasie zapytania

Wdrożenie mechanizmów bezpieczeństwa na warstwie bazy danych z obowiązkowym filtrowaniem i zasadami bezpieczeństwa na poziomie wiersza.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Zweryfikuj, czy wszystkie zapytania do baz danych wektorowych i SQL zawierają obowiązkowe filtry bezpieczeństwa (ID najemcy, etykiety poufności, zakres użytkownika) egzekwowane na poziomie silnika bazy danych, a nie w kodzie aplikacji. |   1   | D/V  |
| 5.4.2 | Zweryfikuj, czy polityki bezpieczeństwa na poziomie wiersza (RLS) oraz maskowanie na poziomie pola są włączone z dziedziczeniem polityk dla wszystkich baz danych wektorowych, indeksów wyszukiwania oraz zbiorów danych treningowych.      |   1   | D/V  |
| 5.4.3 | Zweryfikuj, czy nieudane oceny autoryzacji zapobiegają „atakom zdezorientowanego pełnomocnika” poprzez natychmiastowe przerwanie zapytań i zwrócenie wyraźnych kodów błędów autoryzacji zamiast zwracania pustych zestawów wyników.         |   2   |  D   |
| 5.4.4 | Zweryfikuj, czy czas opóźnienia oceny polityki jest nieprzerwanie monitorowany z automatycznymi alertami dla warunków przekroczenia limitu czasu, które mogłyby umożliwić ominięcie autoryzacji.                                            |   2   |  V   |
| 5.4.5 | Zweryfikuj, czy mechanizmy ponawiania zapytań ponownie oceniają polityki autoryzacji, aby uwzględnić dynamiczne zmiany uprawnień w aktywnych sesjach użytkowników.                                                                          |   3   | D/V  |

---

## Filtrowanie Wyników C5.5 i Zapobieganie Utracie Danych

Wdroż kontrolki po przetwarzaniu, aby zapobiec nieautoryzowanemu ujawnianiu danych w treściach generowanych przez AI.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Zweryfikuj, czy mechanizmy filtrowania po inferencji skanują i redagują nieautoryzowane dane osobowe (PII), informacje zastrzeżone oraz dane własnościowe przed dostarczeniem treści żądającym.                           |   1   | D/V  |
| 5.5.2 | Zweryfikuj, czy cytowania, odniesienia i przypisy źródłowe w wynikach modelu są sprawdzane pod kątem uprawnień użytkownika i usuwane w przypadku wykrycia nieautoryzowanego dostępu.                                      |   1   | D/V  |
| 5.5.3 | Zweryfikuj, czy ograniczenia dotyczące formatu wyjściowego (oczyszczone pliki PDF, obrazy bez metadanych, zatwierdzone typy plików) są egzekwowane na podstawie poziomów uprawnień użytkowników oraz klasyfikacji danych. |   2   |  D   |
| 5.5.4 | Zweryfikuj, czy algorytmy redakcji są deterministyczne, kontrolowane wersjami oraz czy prowadzą dzienniki audytowe wspierające śledztwa zgodności i analizę kryminalistyczną.                                             |   2   |  V   |
| 5.5.5 | Zweryfikuj, czy zdarzenia redakcji wysokiego ryzyka generują adaptacyjne logi, które zawierają kryptograficzne skróty oryginalnej zawartości do celów analizy kryminalistycznej bez narażenia danych.                     |   3   |  V   |

---

## C5.6 Izolacja wielodostępności (Multi-Tenant Isolation)

Zapewnij kryptograficzną i logiczną izolację między najemcami w wspólnej infrastrukturze AI.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Zweryfikuj, czy przestrzenie pamięci, magazyny osadzeń, wpisy w pamięci podręcznej oraz pliki tymczasowe są podzielone na przestrzenie nazw dla każdego najemcy, z bezpiecznym usuwaniem danych po usunięciu najemcy lub zakończeniu sesji. |   1   | D/V  |
| 5.6.2 | Zweryfikuj, czy każde żądanie API zawiera uwierzytelniony identyfikator najemcy, który jest kryptograficznie weryfikowany w kontekście sesji oraz uprawnień użytkownika.                                                                    |   1   | D/V  |
| 5.6.3 | Zweryfikuj, czy polityki sieciowe wdrażają zasady domyślnego odrzucania dla komunikacji między najemcami w ramach siatek usług i platform orkiestracji kontenerów.                                                                          |   2   |  D   |
| 5.6.4 | Zweryfikuj, czy klucze szyfrowania są unikalne dla każdego najemcy przy wsparciu klucza zarządzanego przez klienta (CMK) oraz czy istnieje kryptograficzna izolacja między magazynami danych najemców.                                      |   3   |  D   |

---

## C5.7 Autoryzacja agenta autonomicznego

Kontrola uprawnień dla agentów AI i systemów autonomicznych za pomocą tokenów zdolności o określonym zakresie oraz ciągłej autoryzacji.

|   #   | Description                                                                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Zweryfikuj, czy autonomiczne agenty otrzymują tokeny zdolności o określonym zakresie, które wyraźnie wymieniają dozwolone działania, dostępne zasoby, granice czasowe oraz ograniczenia operacyjne.                                                     |   1   | D/V  |
| 5.7.2 | Zweryfikuj, czy wysokiego ryzyka funkcje (dostęp do systemu plików, wykonywanie kodu, wywołania zewnętrznych interfejsów API, transakcje finansowe) są domyślnie wyłączone i wymagają wyraźnych uprawnień do aktywacji wraz z uzasadnieniem biznesowym. |   1   | D/V  |
| 5.7.3 | Zweryfikuj, czy tokeny uprawnień są powiązane z sesjami użytkowników, zawierają kryptograficzną ochronę integralności oraz zapewnij, że nie mogą być przechowywane ani ponownie wykorzystywane w trybach offline.                                       |   2   |  D   |
| 5.7.4 | Zweryfikuj, czy działania inicjowane przez agenta przechodzą przez wtórną autoryzację za pomocą silnika polityki ABAC z pełną oceną kontekstu i rejestrowaniem audytu.                                                                                  |   2   |  V   |
| 5.7.5 | Zweryfikuj, czy warunki błędów agenta i obsługa wyjątków zawierają informacje o zakresie uprawnień, aby wspierać analizę incydentów i dochodzenia kryminalistycznego.                                                                                   |   3   |  V   |

---

## Bibliografia

### Standardy i ramy

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Przewodniki dotyczące implementacji

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Bezpieczeństwo Specyficzne dla Sztucznej Inteligencji

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

