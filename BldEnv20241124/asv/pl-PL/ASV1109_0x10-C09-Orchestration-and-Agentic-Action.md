# 9 Autonomiczna Orkiestracja i Bezpieczeństwo Agentowego Działania

## Cel kontroli

Zapewnij, że autonomiczne lub wieloagentowe systemy AI mogą wykonywać tylko te działania, które są wyraźnie zamierzone, uwierzytelnione, audytowalne oraz mieszczą się w określonych granicach kosztów i ryzyka. Chroni to przed zagrożeniami takimi jak Kompromitacja Systemu Autonomicznego, Nadużycie Narzędzi, Wykrywanie Pętli Agenta, Przejęcie Komunikacji, Podszywanie się pod Tożsamość, Manipulacja Rojem oraz Manipulacja Intencjami.

---

## 9.1 Budżety planowania zadań agenta i rekurencji

Ograniczaj rekurencyjne plany i wymuszaj punkty kontrolne wykonywane przez człowieka dla uprzywilejowanych działań.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Zweryfikuj, czy maksymalna głębokość rekurencji, rozpiętość, czas zegarowy, liczba tokenów oraz koszty pieniężne wykonania agenta są skonfigurowane centralnie i kontrolowane wersjonowaniem.             |   1   | D/V  |
| 9.1.2 | Zweryfikuj, czy działania uprzywilejowane lub nieodwracalne (np. zatwierdzanie kodu, transfery finansowe) wymagają wyraźnej aprobaty ludzkiej za pośrednictwem audytowalnego kanału przed ich wykonaniem. |   1   | D/V  |
| 9.1.3 | Zweryfikuj, czy monitory zasobów w czasie rzeczywistym wywołują przerwanie wyłącznika awaryjnego, gdy jakikolwiek próg budżetu zostanie przekroczony, zatrzymując dalsze rozszerzanie zadań.              |   2   |  D   |
| 9.1.4 | Zweryfikuj, czy zdarzenia wyłącznika obwodu są rejestrowane z identyfikatorem agenta, warunkiem wyzwalającym oraz przechwyconym stanem planu do celów analizy kryminalistycznej.                          |   2   | D/V  |
| 9.1.5 | Zweryfikuj, czy testy bezpieczeństwa obejmują scenariusze wyczerpania budżetu i niekontrolowanego przebiegu planu, potwierdzając bezpieczne zatrzymanie bez utraty danych.                                |   3   |  V   |
| 9.1.6 | Zweryfikuj, czy polityki budżetowe są wyrażone jako polityki w postaci kodu (policy-as-code) i egzekwowane w CI/CD, aby zapobiegać dryfowi konfiguracji.                                                  |   3   |  D   |

---

## 9.2 Izolacja wtyczek narzędziowych

Izoluj interakcje narzędzi w celu zapobiegania nieautoryzowanemu dostępowi do systemu lub wykonaniu kodu.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Zweryfikuj, czy każde narzędzie/wtyczka działa wewnątrz systemu operacyjnego, kontenera lub piaskownicy na poziomie WASM z zasadami najmniejszych uprawnień dotyczącymi systemu plików, sieci i wywołań systemowych. |   1   | D/V  |
| 9.2.2 | Zweryfikuj, czy limity zasobów sandboxu (CPU, pamięć, dysk, ruch sieciowy na wyjściu) oraz limity czasu wykonania są egzekwowane i rejestrowane.                                                                     |   1   | D/V  |
| 9.2.3 | Zweryfikuj, czy pliki binarne narzędzi lub deskryptory są cyfrowo podpisane; podpisy powinny być weryfikowane przed załadowaniem.                                                                                    |   2   | D/V  |
| 9.2.4 | Zweryfikuj, czy telemetryka piaskownicy jest przesyłana do SIEM; anomalie (np. próby nawiązania połączeń wychodzących) wywołują alerty.                                                                              |   2   |  V   |
| 9.2.5 | Zweryfikuj, czy wtyczki wysokiego ryzyka przechodzą przegląd bezpieczeństwa oraz testy penetracyjne przed wdrożeniem do produkcji.                                                                                   |   3   |  V   |
| 9.2.6 | Zweryfikuj, czy próby ucieczki z piaskownicy są automatycznie blokowane, a winny wtyczka jest poddawana kwarantannie do czasu przeprowadzenia dochodzenia.                                                           |   3   | D/V  |

---

## 9.3 Autonomiczna pętla i ograniczanie kosztów

Wykrywaj i zatrzymuj niekontrolowaną rekurencję między agentami oraz wybuchy kosztów.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Zweryfikuj, czy wywołania między agentami zawierają limit przeskoków lub TTL, który środowisko wykonawcze dekrementuje i egzekwuje.                     |   1   | D/V  |
| 9.3.2 | Zweryfikuj, czy agenci utrzymują unikalny identyfikator grafu wywołań, aby wykrywać samowywołania lub wzorce cykliczne.                                 |   2   |  D   |
| 9.3.3 | Zweryfikuj, czy skumulowane liczniki jednostek obliczeniowych i wydatków są śledzone dla każdego łańcucha żądań; przekroczenie limitu przerywa łańcuch. |   2   | D/V  |
| 9.3.4 | Zweryfikuj, czy analiza formalna lub sprawdzanie modelu wykazuje brak nieograniczonej rekurencji w protokołach agentów.                                 |   3   |  V   |
| 9.3.5 | Zweryfikuj, czy zdarzenia przerwania pętli generują alerty i dostarczają metryki ciągłego doskonalenia.                                                 |   3   |  D   |

---

## 9.4 Ochrona przed niewłaściwym użyciem na poziomie protokołu

Bezpieczne kanały komunikacyjne między agentami a systemami zewnętrznymi w celu zapobiegania przejęciu kontroli lub manipulacji.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Zweryfikuj, czy wszystkie wiadomości między agentem a narzędziem oraz między agentami są uwierzytelnione (np. za pomocą wzajemnego TLS lub JWT) oraz szyfrowane end-to-end. |   1   | D/V  |
| 9.4.2 | Zweryfikuj, czy schematy są ściśle walidowane; nieznane pola lub błędnie sformatowane komunikaty są odrzucane.                                                              |   1   |  D   |
| 9.4.3 | Zweryfikuj, czy kontrole integralności (MAC lub podpisy cyfrowe) obejmują cały ładunek wiadomości, w tym parametry narzędzi.                                                |   2   | D/V  |
| 9.4.4 | Zweryfikuj, czy ochrona przed powtórnym odtwarzaniem (taśmy lub okna znaczników czasu) jest wymuszona na warstwie protokołu.                                                |   2   |  D   |
| 9.4.5 | Zweryfikuj, czy implementacje protokołów przechodzą przez fuzzing oraz analizę statyczną pod kątem podatności na ataki wstrzyknięcia lub deserializacji.                    |   3   |  V   |

---

## 9.5 Tożsamość agenta i odporność na manipulacje

Zapewnij, że działania są przypisywalne, a modyfikacje wykrywalne.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Zweryfikuj, czy każda instancja agenta posiada unikalną kryptograficzną tożsamość (parę kluczy lub poświadczenie sprzętowo zakorzenione).                      |   1   | D/V  |
| 9.5.2 | Zweryfikuj, czy wszystkie działania agenta są podpisane i opatrzone znacznikiem czasu; dzienniki zawierają podpis w celu zapewnienia niemożności zaprzeczenia. |   2   | D/V  |
| 9.5.3 | Zweryfikuj, czy dzienniki odporne na manipulacje są przechowywane w nośniku tylko dołączanym lub zapisie jednokrotnym.                                         |   2   |  V   |
| 9.5.4 | Zweryfikuj, czy klucze tożsamości są rotowane zgodnie z określonym harmonogramem oraz w przypadku wskaźników naruszenia.                                       |   3   |  D   |
| 9.5.5 | Zweryfikuj, czy próby podszywania się lub konfliktu kluczy powodują natychmiastową kwarantannę dotkniętego agenta.                                             |   3   | D/V  |

---

## 9.6 Redukcja ryzyka wieloagentowego roju

Łagodź zagrożenia wynikające ze zbiorowego zachowania poprzez izolację i formalne modelowanie bezpieczeństwa.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Zweryfikuj, czy agenci działający w różnych domenach bezpieczeństwa wykonują operacje w izolowanych środowiskach uruchomieniowych (runtime sandboxes) lub segmentach sieci. |   1   | D/V  |
| 9.6.2 | Zweryfikuj, czy zachowania roju są modelowane i formalnie weryfikowane pod kątem żywotności i bezpieczeństwa przed wdrożeniem.                                              |   3   |  V   |
| 9.6.3 | Zweryfikuj, czy monitory czasu wykonania wykrywają pojawiające się niebezpieczne wzorce (np. oscylacje, zakleszczenia) i inicjują działania korygujące.                     |   3   |  D   |

---

## 9.7 Uwierzytelnianie / Autoryzacja użytkownika i narzędzi

Wdrożenie solidnych mechanizmów kontroli dostępu dla każdej akcji wywoływanej przez agenta.

|   #   | Description                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Zweryfikuj, czy agenci uwierzytelniają się jako podmioty pierwszej klasy w systemach podrzędnych, nigdy nie ponownie wykorzystując poświadczeń użytkownika końcowego. |   1   | D/V  |
| 9.7.2 | Zweryfikuj, czy szczegółowe polityki autoryzacji ograniczają, które narzędzia agent może wywołać oraz jakie parametry może dostarczyć.                                |   2   |  D   |
| 9.7.3 | Zweryfikuj, czy kontrole uprawnień są ponownie oceniane przy każdym wywołaniu (ciągła autoryzacja), a nie tylko na początku sesji.                                    |   2   |  V   |
| 9.7.4 | Zweryfikuj, czy przyznane uprawnienia wygasają automatycznie i wymagają ponownej zgody po upływie limitu czasu lub zmianie zakresu.                                   |   3   |  D   |

---

## 9.8 Bezpieczeństwo Komunikacji Między Agentami

Szyfruj i zabezpieczaj integralność wszystkich wiadomości między agentami, aby zapobiec podsłuchiwaniu i manipulacji.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Zweryfikuj, czy wzajemna autentykacja i szyfrowanie z doskonałą tajnością do przodu (np. TLS 1.3) są obowiązkowe dla kanałów agentów.                       |   1   | D/V  |
| 9.8.2 | Zweryfikuj integralność i pochodzenie wiadomości przed przetwarzaniem; w przypadku niepowodzenia generowane są alerty i wiadomość jest odrzucana.           |   1   |  D   |
| 9.8.3 | Zweryfikuj, czy metadane komunikacji (znaczniki czasu, numery sekwencji) są rejestrowane w celu wsparcia rekonstrukcji forensic.                            |   2   | D/V  |
| 9.8.4 | Zweryfikuj, czy weryfikacja formalna lub sprawdzanie modeli potwierdza, że maszyny stanów protokołu nie mogą zostać doprowadzone do stanów niebezpiecznych. |   3   |  V   |

---

## 9.9 Weryfikacja intencji i egzekwowanie ograniczeń

Zweryfikuj, czy działania agenta są zgodne z wyrażonym przez użytkownika zamiarem oraz ograniczeniami systemu.

|   #   | Description                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Zweryfikuj, czy solwery ograniczeń przed wykonaniem sprawdzają proponowane działania pod kątem sztywnych reguł bezpieczeństwa i polityki.                                                   |   1   |  D   |
| 9.9.2 | Zweryfikuj, czy działania o wysokim wpływie (finansowe, destrukcyjne, wrażliwe na prywatność) wymagają wyraźnego potwierdzenia zamiaru od użytkownika inicjującego.                         |   2   | D/V  |
| 9.9.3 | Zweryfikuj, czy kontrole warunków końcowych potwierdzają, że zakończone działania osiągnęły zamierzone efekty bez skutków ubocznych; rozbieżności powodują wycofanie zmian.                 |   2   |  V   |
| 9.9.4 | Zweryfikuj, czy metody formalne (np. weryfikacja modelu, dowodzenie twierdzeń) lub testy oparte na właściwościach wykazują, że plany agenta spełniają wszystkie zadeklarowane ograniczenia. |   3   |  V   |
| 9.9.5 | Zweryfikuj, czy incydenty wynikające z niezgodności intencji lub naruszenia ograniczeń są wykorzystywane do cykli ciągłego doskonalenia oraz wymiany informacji o zagrożeniach.             |   3   |  D   |

---

## 9.10 Bezpieczeństwo strategii rozumowania agenta

Bezpieczny wybór i wykonywanie różnych strategii wnioskowania, w tym podejścia ReAct, Chain-of-Thought oraz Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Zweryfikuj, czy wybór strategii rozumowania opiera się na deterministycznych kryteriach (złożoność wejścia, typ zadania, kontekst bezpieczeństwa) oraz czy identyczne dane wejściowe generują identyczny wybór strategii w ramach tego samego kontekstu bezpieczeństwa.            |   1   | D/V  |
| 9.10.2 | Zweryfikuj, czy każda strategia rozumowania (ReAct, Chain-of-Thought, Tree-of-Thoughts) posiada dedykowaną walidację danych wejściowych, sanityzację danych wyjściowych oraz ograniczenia czasu wykonania specyficzne dla jej podejścia poznawczego.                               |   1   | D/V  |
| 9.10.3 | Zweryfikuj, czy przejścia strategii rozumowania są rejestrowane z pełnym kontekstem, w tym cechami wejściowymi, wartościami kryteriów wyboru oraz metadanymi wykonania w celu rekonstrukcji śladu audytu.                                                                          |   2   | D/V  |
| 9.10.4 | Potwierdź, że rozumowanie Tree-of-Thoughts zawiera mechanizmy przycinania gałęzi, które przerywają eksplorację w momencie wykrycia naruszeń polityki, ograniczeń zasobów lub granic bezpieczeństwa.                                                                                |   2   | D/V  |
| 9.10.5 | Sprawdź, czy cykle ReAct (Reason-Act-Observe) obejmują punkty kontrolne walidacji na każdym etapie: weryfikację kroku rozumowania, autoryzację działania oraz sanitację obserwacji przed przejściem dalej.                                                                         |   2   | D/V  |
| 9.10.6 | Zweryfikuj, czy metryki wydajności strategii rozumowania (czas wykonania, zużycie zasobów, jakość wyników) są monitorowane za pomocą automatycznych alertów, gdy metryki odbiegają od skonfigurowanych progów.                                                                     |   3   | D/V  |
| 9.10.7 | Zweryfikuj, czy hybrydowe podejścia rozumowania łączące wiele strategii zachowują walidację danych wejściowych oraz ograniczenia wyjściowe wszystkich składowych strategii, bez omijania jakichkolwiek mechanizmów bezpieczeństwa.                                                 |   3   | D/V  |
| 9.10.8 | Zweryfikuj, czy strategia testowania bezpieczeństwa rozumowania obejmuje fuzzing przy użyciu nieprawidłowych danych wejściowych, przeciwnicze podpowiedzi zaprojektowane w celu wymuszenia zmiany strategii oraz testowanie warunków brzegowych dla każdego podejścia poznawczego. |   3   | D/V  |

---

## 9.11 Zarządzanie cyklem życia agenta i bezpieczeństwo

Bezpieczna inicjalizacja agenta, przejścia stanów oraz zakończenie działania z wykorzystaniem kryptograficznych ścieżek audytu i zdefiniowanych procedur odzyskiwania.

|   #    | Description                                                                                                                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Zweryfikuj, czy inicjalizacja agenta obejmuje ustanowienie tożsamości kryptograficznej za pomocą sprzętowo zabezpieczonych poświadczeń oraz niezmienialnych dzienników audytu startowego zawierających identyfikator agenta, znacznik czasu, hash konfiguracji i parametry inicjalizacji.            |   1   | D/V  |
| 9.11.2 | Zweryfikuj, czy przejścia stanów agenta są podpisane kryptograficznie, opatrzone znacznikiem czasu oraz rejestrowane z pełnym kontekstem, w tym zdarzeniami wywołującymi, haszem poprzedniego stanu, haszem nowego stanu oraz przeprowadzonymi walidacjami bezpieczeństwa.                           |   2   | D/V  |
| 9.11.3 | Zweryfikuj, czy procedury zamykania agenta obejmują bezpieczne wymazywanie pamięci przy użyciu kryptograficznego usuwania lub wielokrotnego nadpisywania, unieważnianie poświadczeń z powiadomieniem urzędu certyfikacji oraz generowanie świadectw zakończenia pracy z dowodem manipulacji.         |   2   | D/V  |
| 9.11.4 | Zweryfikuj, czy mechanizmy odzyskiwania agenta weryfikują integralność stanu za pomocą kryptograficznych sum kontrolnych (minimum SHA-256) oraz czy w przypadku wykrycia korupcji następuje przywrócenie do znanych, poprawnych stanów wraz z automatycznymi alertami i wymogiem ręcznej akceptacji. |   3   | D/V  |
| 9.11.5 | Zweryfikuj, czy mechanizmy utrwalania agenta szyfrują wrażliwe dane stanu za pomocą indywidualnych kluczy AES-256 dla każdego agenta oraz czy implementują bezpieczną rotację kluczy według konfigurowalnych harmonogramów (maksymalnie co 90 dni) z wdrożeniem bez przestojów.                      |   3   | D/V  |

---

## 9.12 Ramy bezpieczeństwa integracji narzędzi

Kontrole bezpieczeństwa dla dynamicznego ładowania narzędzi, wykonania oraz weryfikacji wyników z określonymi procesami oceny ryzyka i zatwierdzania.

|   #    | Description                                                                                                                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Zweryfikuj, czy deskryptory narzędzi zawierają metadane bezpieczeństwa określające wymagane uprawnienia (odczyt/zapis/wykonanie), poziomy ryzyka (niski/średni/wysoki), limity zasobów (CPU, pamięć, sieć) oraz wymagania walidacyjne udokumentowane w manifestach narzędzi.                                                 |   1   | D/V  |
| 9.12.2 | Zweryfikuj, czy wyniki wykonania narzędzia są sprawdzane pod kątem zgodności z oczekiwanymi schematami (JSON Schema, XML Schema) oraz politykami bezpieczeństwa (sanityzacja wyniku, klasyfikacja danych) przed integracją, uwzględniając limity czasu oraz procedury obsługi błędów.                                        |   1   | D/V  |
| 9.12.3 | Zweryfikuj, czy logi interakcji narzędzi zawierają szczegółowy kontekst bezpieczeństwa, w tym użycie uprawnień, wzorce dostępu do danych, czas wykonania, zużycie zasobów oraz kody zwrotne, z użyciem ustrukturyzowanego logowania do integracji z SIEM.                                                                    |   2   | D/V  |
| 9.12.4 | Zweryfikuj, czy mechanizmy dynamicznego ładowania narzędzi sprawdzają podpisy cyfrowe z wykorzystaniem infrastruktury PKI oraz implementują bezpieczne protokoły ładowania z izolacją w piaskownicy i weryfikacją uprawnień przed wykonaniem.                                                                                |   2   | D/V  |
| 9.12.5 | Zweryfikuj, czy oceny bezpieczeństwa narzędzi są automatycznie uruchamiane dla nowych wersji z obowiązkowymi etapami zatwierdzenia, obejmującymi analizę statyczną, testy dynamiczne oraz przegląd zespołu ds. bezpieczeństwa, z udokumentowanymi kryteriami zatwierdzenia i wymaganiami dotyczącymi czasu realizacji (SLA). |   3   | D/V  |

---

### Bibliografia

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

