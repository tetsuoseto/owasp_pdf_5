# C12 Monitorowanie, rejestrowanie i wykrywanie anomalii

## Cel kontroli

Ta sekcja zawiera wymagania dotyczące zapewnienia widoczności w czasie rzeczywistym oraz w celach kryminalistycznych tego, co model i inne komponenty AI widzą, robią oraz zwracają, aby możliwe było wykrywanie, klasyfikowanie i analiza zagrożeń.

## C12.1 Rejestrowanie żądań i odpowiedzi

|   #    | Description                                                                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.1.1 | Zweryfikuj, czy wszystkie polecenia użytkownika oraz odpowiedzi modelu są rejestrowane wraz z odpowiednimi metadanymi (np. znacznik czasu, identyfikator użytkownika, identyfikator sesji, wersja modelu).                           |   1   | D/V  |
| 12.1.2 | Zweryfikuj, czy logi są przechowywane w bezpiecznych, kontrolowanych pod względem dostępu repozytoriach z odpowiednimi politykami przechowywania i procedurami tworzenia kopii zapasowych.                                           |   1   | D/V  |
| 12.1.3 | Zweryfikuj, czy systemy przechowywania logów implementują szyfrowanie danych w stanie spoczynku oraz podczas transmisji, aby chronić wrażliwe informacje zawarte w logach.                                                           |   1   | D/V  |
| 12.1.4 | Zweryfikuj, czy wrażliwe dane w zapytaniach i wynikach są automatycznie redagowane lub maskowane przed ich rejestrowaniem, z konfigurowalnymi regułami redagowania dla danych osobowych (PII), poświadczeń oraz informacji poufnych. |   1   | D/V  |
| 12.1.5 | Zweryfikuj, czy decyzje polityczne i działania filtrów bezpieczeństwa są rejestrowane z wystarczającym poziomem szczegółowości, aby umożliwić audyt i debugowanie systemów moderacji treści.                                         |   2   | D/V  |
| 12.1.6 | Zweryfikuj, czy integralność dziennika jest chroniona poprzez np. podpisy kryptograficzne lub magazyn tylko do zapisu.                                                                                                               |   2   | D/V  |

---

## C12.2 Wykrywanie Nadużyć i Powiadamianie

|   #    | Description                                                                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Zweryfikuj, czy system wykrywa i informuje o znanych wzorcach jailbreak, próbach wstrzyknięcia poleceń oraz wrogich danych wejściowych, stosując wykrywanie oparte na sygnaturach.                                                                        |   1   | D/V  |
| 12.2.2 | Zweryfikuj, czy system integruje się z istniejącymi platformami Zarządzania Informacjami i Zdarzeniami Bezpieczeństwa (SIEM) za pomocą standardowych formatów dzienników i protokołów.                                                                    |   1   | D/V  |
| 12.2.3 | Zweryfikuj, czy wzbogacone zdarzenia bezpieczeństwa zawierają kontekst specyficzny dla AI, taki jak identyfikatory modeli, wskaźniki ufności oraz decyzje filtrów bezpieczeństwa.                                                                         |   2   | D/V  |
| 12.2.4 | Zweryfikuj, czy wykrywanie anomalii behawioralnych identyfikuje nietypowe wzorce rozmów, nadmierne próby ponawiania lub systematyczne zachowania sondowania.                                                                                              |   2   | D/V  |
| 12.2.5 | Zweryfikuj, czy mechanizmy alertów w czasie rzeczywistym powiadamiają zespoły ds. bezpieczeństwa w przypadku wykrycia potencjalnych naruszeń polityki lub prób ataku.                                                                                     |   2   | D/V  |
| 12.2.6 | Zweryfikuj, czy zawarte są niestandardowe reguły do wykrywania wzorców zagrożeń specyficznych dla sztucznej inteligencji, w tym skoordynowanych prób obejścia zabezpieczeń (jailbreak), kampanii wstrzykiwania promptów oraz ataków na ekstrakcję modeli. |   2   | D/V  |
| 12.2.7 | Zweryfikuj, czy zautomatyzowane procedury reagowania na incydenty mogą izolować zaatakowane modele, blokować złośliwych użytkowników oraz eskalować krytyczne zdarzenia związane z bezpieczeństwem.                                                       |   3   | D/V  |

---

## C12.3 Wykrywanie dryfu modelu

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Zweryfikuj, czy system śledzi podstawowe metryki wydajności, takie jak dokładność, wskaźniki pewności, opóźnienia oraz wskaźniki błędów w różnych wersjach modelu i okresach czasu.      |   1   | D/V  |
| 12.3.2 | Zweryfikuj, czy automatyczne powiadamianie zostaje wywołane, gdy metryki wydajności przekraczają zdefiniowane wcześniej progi degradacji lub znacznie odbiegają od wartości bazowych.    |   2   | D/V  |
| 12.3.3 | Zweryfikuj, czy monitorowanie wykrywania halucynacji identyfikuje i oznacza przypadki, gdy wyniki modelu zawierają informacje faktograficznie nieprawidłowe, niespójne lub sfabrykowane. |   2   | D/V  |

---

## C12.4 Telemetria wydajności i zachowania

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.4.1 | Zweryfikuj, czy metryki operacyjne, w tym opóźnienie żądań, zużycie tokenów, użycie pamięci oraz przepustowość, są ciągle zbierane i monitorowane.                                         |   1   | D/V  |
| 12.4.2 | Zweryfikuj, czy wskaźniki sukcesu i porażki są śledzone z kategoryzacją typów błędów oraz ich przyczyn źródłowych.                                                                         |   1   | D/V  |
| 12.4.3 | Zweryfikuj, czy monitorowanie wykorzystania zasobów obejmuje użycie GPU/CPU, zużycie pamięci oraz wymagania dotyczące pamięci masowej, z powiadamianiem o przekroczeniu progów alarmowych. |   2   | D/V  |

---

## C12.5 Planowanie i realizacja reagowania na incydenty związane ze sztuczną inteligencją

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Zweryfikuj, czy plany reagowania na incydenty obejmują specyficznie zdarzenia związane z bezpieczeństwem AI, w tym naruszenie modelu, zatruwanie danych oraz ataki adwersarialne.           |   1   | D/V  |
| 12.5.2 | Zweryfikuj, czy zespoły ds. reagowania na incydenty mają dostęp do specjalistycznych narzędzi kryminalistycznych AI oraz wiedzy eksperckiej do badania zachowania modeli i wektorów ataków. |   2   | D/V  |
| 12.5.3 | Zweryfikuj, czy analiza po incydencie obejmuje kwestie ponownego trenowania modelu, aktualizacje filtrów bezpieczeństwa oraz integrację wyciągniętych wniosków w kontrolach bezpieczeństwa. |   3   | D/V  |

---

## C12.5 Wykrywanie degradacji wydajności AI

Monitorować i wykrywać degradację wydajności i jakości modelu AI w czasie.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Zweryfikuj, czy dokładność modelu, precyzja, czułość oraz miary F1 są stale monitorowane i porównywane z wartościami progowymi bazowymi.            |   1   | D/V  |
| 12.5.2 | Zweryfikuj, czy monitorowanie wykrywania dryfu danych śledzi zmiany rozkładu danych wejściowych, które mogą wpływać na wydajność modelu.            |   1   | D/V  |
| 12.5.3 | Zweryfikuj, czy detekcja dryfu koncepcji identyfikuje zmiany w relacji między danymi wejściowymi a oczekiwanymi wynikami.                           |   2   | D/V  |
| 12.5.4 | Zweryfikuj, czy pogorszenie wydajności wywołuje automatyczne alerty i inicjuje procesy ponownego trenowania lub wymiany modelu.                     |   2   | D/V  |
| 12.5.5 | Zweryfikuj, czy analiza przyczyn degradacji koreluje spadki wydajności ze zmianami danych, problemami z infrastrukturą lub czynnikami zewnętrznymi. |   3   |  V   |

---

## C12.6 Wizualizacja DAG i bezpieczeństwo przepływu pracy

Chroń systemy wizualizacji przepływu pracy przed wyciekami informacji i atakami manipulacyjnymi.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Sprawdź, czy dane wizualizacji DAG zostały oczyszczone w celu usunięcia informacji wrażliwych przed ich przechowywaniem lub transmisją.                                                   |   1   | D/V  |
| 12.6.2 | Zweryfikuj, czy kontrola dostępu do wizualizacji przepływu pracy zapewnia, że tylko upoważnieni użytkownicy mogą przeglądać ścieżki decyzji agenta oraz ślady uzasadnień.                 |   1   | D/V  |
| 12.6.3 | Zweryfikuj, czy integralność danych DAG jest chroniona za pomocą podpisów kryptograficznych oraz mechanizmów przechowywania odpornych na manipulacje.                                     |   2   | D/V  |
| 12.6.4 | Zweryfikuj, czy systemy wizualizacji przepływu pracy implementują walidację danych wejściowych, aby zapobiec atakom typu injection poprzez spreparowane dane węzłów lub krawędzi.         |   2   | D/V  |
| 12.6.5 | Zweryfikuj, czy aktualizacje DAG w czasie rzeczywistym są limitowane pod względem częstotliwości oraz weryfikowane, aby zapobiec atakom typu odmowa usługi (DoS) na systemy wizualizacji. |   3   | D/V  |

---

## C12.7 Proaktywne Monitorowanie Zachowań Bezpieczeństwa

Wykrywanie i zapobieganie zagrożeniom bezpieczeństwa poprzez proaktywną analizę zachowań agentów.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.7.1 | Zweryfikuj, czy proaktywne zachowania agentów są zatwierdzone pod względem bezpieczeństwa przed wykonaniem, wraz z integracją oceny ryzyka.                  |   1   | D/V  |
| 12.7.2 | Zweryfikuj, czy inicjatywa autonomiczna obejmuje ocenę kontekstu bezpieczeństwa oraz analizę krajobrazu zagrożeń.                                            |   2   | D/V  |
| 12.7.3 | Zweryfikuj, czy wzorce zachowań proaktywnych są analizowane pod kątem potencjalnych implikacji bezpieczeństwa i niezamierzonych konsekwencji.                |   2   | D/V  |
| 12.7.4 | Zweryfikuj, czy krytyczne dla bezpieczeństwa działania proaktywne wymagają wyraźnych łańcuchów zatwierdzeń z ścieżkami audytu.                               |   3   | D/V  |
| 12.7.5 | Zweryfikuj, czy wykrywanie anomalii behawioralnych identyfikuje odchylenia w wzorcach działania agentów proaktywnych, które mogą wskazywać na kompromitację. |   3   | D/V  |

---

## Bibliografia

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

