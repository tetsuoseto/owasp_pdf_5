# 10 Odporność na ataki adwersarialne i obrona prywatności

## Cel kontrolny

Zapewnij, aby modele sztucznej inteligencji pozostawały niezawodne, chroniące prywatność oraz odporne na nadużycia w przypadku ataków polegających na ominięciu zabezpieczeń, wnioskowaniu, ekstrakcji danych lub zatruwaniu.

---

## 10.1 Wyrównanie modelu i bezpieczeństwo

Zabezpiecz się przed szkodliwymi lub naruszającymi politykę wynikami.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Zweryfikuj, czy zestaw testów zgodności (prompty zespołu czerwonego, sondy jailbreak, zabronione treści) jest kontrolowany wersjami i uruchamiany przy każdym wydaniu modelu. |   1   | D/V  |
| 10.1.2 | Zweryfikuj, czy są egzekwowane zasady odmowy i bezpiecznego ukończenia.                                                                                                       |   1   |  D   |
| 10.1.3 | Zweryfikuj, czy automatyczny evaluator mierzy wskaźnik treści szkodliwych i sygnalizuje regresje przekraczające ustalony próg.                                                |   2   | D/V  |
| 10.1.4 | Zweryfikuj, czy szkolenie przeciwko jailbreakowi jest udokumentowane i możliwe do odtworzenia.                                                                                |   2   |  D   |
| 10.1.5 | Zweryfikuj, czy formalne dowody zgodności z politykami lub certyfikowany monitoring obejmują krytyczne obszary.                                                               |   3   |  V   |

---

## 10.2 Utwardzanie na przykładach przeciwnych

Zwiększ odporność na zmanipulowane dane wejściowe. Obecnie najlepszą praktyką są solidne szkolenia przeciwnikowe oraz ocena za pomocą benchmarków.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Zweryfikuj, czy repozytoria projektów zawierają konfiguracje treningu przeciwnika z powtarzalnymi ziarnami.                                 |   1   |  D   |
| 10.2.2 | Zweryfikuj, czy wykrywanie przykładów adwersarialnych generuje alerty blokujące w liniach produkcyjnych.                                    |   2   | D/V  |
| 10.2.4 | Zweryfikuj, czy dowody certyfikowanej odporności lub certyfikaty przedziałowych granic obejmują przynajmniej najważniejsze krytyczne klasy. |   3   |  V   |
| 10.2.5 | Zweryfikuj, czy testy regresyjne wykorzystują adaptacyjne ataki, aby potwierdzić brak mierzalnej utraty odporności.                         |   3   |  V   |

---

## 10.3 Łagodzenie skutków ataków wnioskowania o przynależności

Ogranicz możliwość ustalenia, czy rekord znajdował się w danych treningowych. Różnicowa prywatność i maskowanie współczynnika ufności pozostają najskuteczniejszymi znanymi metodami obrony.

|   #    | Description                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Zweryfikuj, czy regularizacja entropii dla każdego zapytania lub skalowanie temperatury zmniejsza nadmiernie pewne prognozy. |   1   |  D   |
| 10.3.2 | Zweryfikuj, że trening wykorzystuje optymalizację różnicowo prywatną ograniczoną przez ε dla wrażliwych zbiorów danych.      |   2   |  D   |
| 10.3.3 | Zweryfikuj, czy symulacje ataków (model cienia lub czarna skrzynka) wykazują AUC ataku ≤ 0,60 na danych testowych.           |   2   |  V   |

---

## 10.4 Odporność na inwersję modelu

Zapobiegaj rekonstrukcji prywatnych atrybutów. Ostatnie badania podkreślają obcinanie wyników i gwarancje różnicowej prywatności (DP) jako praktyczne środki obronne.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Zweryfikuj, czy wrażliwe atrybuty nigdy nie są bezpośrednio wyprowadzane; tam gdzie to konieczne, używaj koszyków (bucketów) lub transformacji jednokierunkowych. |   1   |  D   |
| 10.4.2 | Zweryfikuj, czy limity szybkości zapytań ograniczają powtarzające się adaptacyjne zapytania od tego samego podmiotu.                                              |   1   | D/V  |
| 10.4.3 | Zweryfikuj, czy model jest trenowany z zastosowaniem szumu chroniącego prywatność.                                                                                |   2   |  D   |

---

## 10.5 Obrona przed ekstrakcją modelu

Wykrywaj i uniemożliwiaj nieautoryzowane klonowanie. Zaleca się stosowanie znakowania wodnego oraz analizy wzorców zapytań.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Sprawdź, czy bramki inferencyjne egzekwują globalne i na klucz API limity szybkości dostosowane do progu zapamiętywania modelu.                 |   1   |  D   |
| 10.5.2 | Zweryfikuj, czy statystyki entropii zapytań i wielości wejść zasilają automatyczny detektor ekstrakcji.                                         |   2   | D/V  |
| 10.5.3 | Zweryfikuj, czy kruche lub probabilistyczne znaki wodne mogą być udowodnione z p < 0,01 przy ≤ 1000 zapytaniach wobec podejrzanego klona.       |   2   |  V   |
| 10.5.4 | Zweryfikuj, czy klucze znaków wodnych i zestawy wyzwalaczy są przechowywane w module bezpieczeństwa sprzętowego oraz czy są rotowane corocznie. |   3   |  D   |
| 10.5.5 | Zweryfikuj, czy zdarzenia extraction-alert zawierają zapytania naruszające zasady i są zintegrowane z procedurami reagowania na incydenty.      |   3   |  V   |

---

## 10.6 Wykrywanie zatrutych danych podczas inferencji

Identyfikuj i neutralizuj zainfekowane tylne wejścia lub wejścia zatrute.

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Zweryfikuj, czy dane wejściowe przechodzą przez detektor anomalii (np. STRIP, ocenianie spójności) przed inferencją modelu.                                     |   1   |  D   |
| 10.6.2 | Zweryfikuj, czy progi detektora są dostrojone na czystych/zatrutych zestawach walidacyjnych, aby osiągnąć mniej niż 5% fałszywych trafień.                      |   1   |  V   |
| 10.6.3 | Zweryfikuj, czy dane wejściowe oznaczone jako zainfekowane wywołują miękkie blokowanie oraz procedury przeglądu przez człowieka.                                |   2   |  D   |
| 10.6.4 | Zweryfikuj, czy detektory są poddane testom wytrzymałościowym za pomocą adaptacyjnych ataków tylnego wejścia bez wyzwalacza.                                    |   2   |  V   |
| 10.6.5 | Zweryfikuj, czy metryki skuteczności wykrywania są rejestrowane i okresowo ponownie oceniane na podstawie aktualnych danych wywiadowczych dotyczących zagrożeń. |   3   |  D   |

---

## 10.7 Dynamiczne dostosowywanie polityki bezpieczeństwa

Aktualizacje polityk bezpieczeństwa w czasie rzeczywistym oparte na wywiadzie zagrożeń i analizie zachowań.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Zweryfikuj, czy dokumenty polityk bezpieczeństwa mogą być aktualizowane dynamicznie bez konieczności restartu agenta, przy jednoczesnym zachowaniu integralności wersji polityk. |   1   | D/V  |
| 10.7.2 | Zweryfikuj, czy aktualizacje polityki są kryptograficznie podpisane przez upoważniony personel ds. bezpieczeństwa i potwierdzone przed zastosowaniem.                            |   2   | D/V  |
| 10.7.3 | Zweryfikuj, czy dynamiczne zmiany polityki są rejestrowane z pełnymi śladami audytu, w tym uzasadnieniem, łańcuchami zatwierdzeń oraz procedurami wycofywania.                   |   2   | D/V  |
| 10.7.4 | Zweryfikuj, czy adaptacyjne mechanizmy bezpieczeństwa dostosowują czułość wykrywania zagrożeń na podstawie kontekstu ryzyka i wzorców zachowań.                                  |   3   | D/V  |
| 10.7.5 | Zweryfikuj, czy decyzje dotyczące adaptacji polityki są wyjaśnialne i zawierają ścieżki dowodowe do przeglądu przez zespół ds. bezpieczeństwa.                                   |   3   | D/V  |

---

## 10.8 Analiza bezpieczeństwa oparta na refleksji

Weryfikacja bezpieczeństwa poprzez autorefleksję agenta i analizę metapoznawczą.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Zweryfikuj, czy mechanizmy refleksji agenta obejmują samoocenę decyzji i działań z ukierunkowaniem na bezpieczeństwo.                                   |   1   | D/V  |
| 10.8.2 | Zweryfikuj, czy wyniki refleksji są walidowane, aby zapobiec manipulacji mechanizmów samooceny przez wrogie dane wejściowe.                             |   2   | D/V  |
| 10.8.3 | Zweryfikuj, czy analiza bezpieczeństwa metapoznawczego identyfikuje potencjalne uprzedzenia, manipulacje lub naruszenia w procesach rozumowania agenta. |   2   | D/V  |
| 10.8.4 | Zweryfikuj, czy ostrzeżenia dotyczące bezpieczeństwa oparte na refleksji wywołują zwiększony nadzór i potencjalne procedury interwencji ludzkiej.       |   3   | D/V  |
| 10.8.5 | Zweryfikuj, czy ciągłe uczenie się na podstawie analiz bezpieczeństwa poprawia wykrywanie zagrożeń bez pogarszania funkcjonalności prawidłowej.         |   3   | D/V  |

---

## 10.9 Ewolucja i Bezpieczeństwo Samodoskonalenia

Kontrole bezpieczeństwa dla systemów agentowych zdolnych do samomodyfikacji i ewolucji.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Zweryfikuj, czy możliwości samomodifikacji są ograniczone do wyznaczonych bezpiecznych obszarów z formalnymi granicami weryfikacji.       |   1   | D/V  |
| 10.9.2 | Zweryfikuj, czy propozycje ewolucyjne przechodzą ocenę wpływu na bezpieczeństwo przed wdrożeniem.                                         |   2   | D/V  |
| 10.9.3 | Zweryfikuj, czy mechanizmy samodoskonalenia obejmują możliwości wycofania z weryfikacją integralności.                                    |   2   | D/V  |
| 10.9.4 | Zweryfikuj, czy bezpieczeństwo meta-uczenia zapobiega przeciwnym manipulacjom algorytmów poprawy.                                         |   3   | D/V  |
| 10.9.5 | Zweryfikuj, czy rekursywna samo-ulepszanie jest ograniczona formalnymi zasadami bezpieczeństwa wraz z matematycznymi dowodami zbieżności. |   3   | D/V  |

---

### Referencje

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

