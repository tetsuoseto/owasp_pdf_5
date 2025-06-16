# Bezpieczeństwo łańcucha dostaw C6 dla modeli, frameworków i danych

## Cel Kontrolny

Ataki na łańcuch dostaw AI wykorzystują modele, frameworki lub zbiory danych stron trzecich do osadzania tylnego wejścia, stronniczości lub podatnego na wykorzystanie kodu. Te mechanizmy zapewniają pełną kontrolę nad pochodzeniem, zarządzanie podatnościami oraz monitorowanie, aby chronić cały cykl życia modelu.

---

## C6.1 Weryfikacja i Pochodzenie Wstępnie Wytrenowanego Modelu

Oceń i uwierzytelnij pochodzenie modeli stron trzecich, licencje oraz ukryte zachowania przed jakimkolwiek dostrajaniem lub wdrożeniem.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.1.1 | Zweryfikuj, czy każdy artefakt modelu stron trzecich zawiera podpisany rekord pochodzenia identyfikujący repozytorium źródłowe i hash zatwierdzenia.                                       |   1   | D/V  |
| 6.1.2 | Zweryfikuj, czy modele są skanowane pod kątem złośliwych warstw lub wyzwalaczy trojańskich za pomocą zautomatyzowanych narzędzi przed importem.                                            |   1   | D/V  |
| 6.1.3 | Zweryfikuj, czy dostrajanie przy pomocy transfer learningu przechodzi testy przeciwdziałające atakom adversarialnym w celu wykrycia ukrytych zachowań.                                     |   2   |  D   |
| 6.1.4 | Zweryfikuj, czy licencje modeli, oznaczenia kontroli eksportu oraz oświadczenia dotyczące pochodzenia danych są zarejestrowane w wpisie ML-BOM.                                            |   2   |  V   |
| 6.1.5 | Zweryfikuj, czy modele wysokiego ryzyka (publicznie udostępnione wagi, niezweryfikowani twórcy) pozostają pod kwarantanną aż do przeprowadzenia przeglądu i zatwierdzenia przez człowieka. |   3   | D/V  |

---

## C6.2 Skanowanie ram i bibliotek

Ciągłe skanowanie frameworków i bibliotek uczenia maszynowego w celu wykrywania CVE oraz złośliwego kodu, aby utrzymać bezpieczne środowisko wykonawcze.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Zweryfikuj, czy pipeline'y CI uruchamiają skanery zależności dla frameworków AI oraz krytycznych bibliotek.                                   |   1   | D/V  |
| 6.2.2 | Zweryfikuj, czy krytyczne podatności (CVSS ≥ 7.0) blokują promowanie do obrazów produkcyjnych.                                                |   1   | D/V  |
| 6.2.3 | Zweryfikuj, czy analiza statyczna kodu uruchamiana jest na rozgałęzionych lub dostarczonych bibliotekach ML.                                  |   2   |  D   |
| 6.2.4 | Zweryfikuj, czy propozycje aktualizacji frameworka zawierają ocenę wpływu na bezpieczeństwo odwołującą się do publicznych źródeł CVE.         |   2   |  V   |
| 6.2.5 | Zweryfikuj, czy sensory czasu wykonywania alarmują o nieoczekiwanych ładowaniach bibliotek dynamicznych, które odbiegają od podpisanego SBOM. |   3   |  V   |

---

## C6.3 Przypinanie i weryfikacja zależności

Przypnij każdą zależność do niezmiennych skrótów i odtwarzaj kompilacje, aby zagwarantować identyczne, wolne od manipulacji artefakty.

|   #   | Description                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Sprawdź, czy wszystkie menedżery pakietów wymuszają przypinanie wersji za pomocą plików blokady.                                  |   1   | D/V  |
| 6.3.2 | Zweryfikuj, czy w odwołaniach do kontenerów używane są niezmienne skróty (immutable digests) zamiast podatnych na zmiany tagów.   |   1   | D/V  |
| 6.3.3 | Zweryfikuj, czy kontrole powtarzalnych kompilacji porównują skróty w kolejnych uruchomieniach CI, aby zapewnić identyczne wyniki. |   2   |  D   |
| 6.3.4 | Zweryfikuj, czy zaświadczenia dotyczące kompilacji są przechowywane przez 18 miesięcy w celu śledzenia audytu.                    |   2   |  V   |
| 6.3.5 | Zweryfikuj, czy wygasłe zależności wywołują automatyczne pull requesty w celu aktualizacji lub rozwidlenia przypiętych wersji.    |   3   |  D   |

---

## C6.4 Egzekwowanie autoryzowanego źródła

Zezwalaj na pobieranie artefaktów tylko z kryptograficznie zweryfikowanych, zatwierdzonych przez organizację źródeł i blokuj wszystko inne.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.4.1 | Zweryfikuj, czy wagi modelu, zestawy danych oraz kontenery są pobierane wyłącznie z zatwierdzonych domen lub wewnętrznych rejestrów. |   1   | D/V  |
| 6.4.2 | Zweryfikuj, czy podpisy Sigstore/Cosign potwierdzają tożsamość wydawcy przed lokalnym buforowaniem artefaktów.                       |   1   | D/V  |
| 6.4.3 | Zweryfikuj, czy proxy wychodzące blokują nieautoryzowane pobieranie artefaktów, aby egzekwować politykę zaufanego źródła.            |   2   |  D   |
| 6.4.4 | Zweryfikuj, czy listy dozwolonych repozytoriów są przeglądane kwartalnie z dowodem uzasadnienia biznesowego dla każdego wpisu.       |   2   |  V   |
| 6.4.5 | Zweryfikuj, czy naruszenia polityki powodują kwarantannę artefaktów oraz wycofanie zależnych uruchomień potoku.                      |   3   |  V   |

---

## C6.5 Ocena ryzyka zbioru danych zewnętrznego

Oceniaj zewnętrzne zbiory danych pod kątem zatruwania, uprzedzeń oraz zgodności z przepisami prawnymi i monitoruj je przez cały ich cykl życia.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Zweryfikuj, czy zewnętrzne zbiory danych przechodzą ocenę ryzyka zanieczyszczenia (np. odcisk palca danych, wykrywanie wartości odstających). |   1   | D/V  |
| 6.5.2 | Zweryfikuj, czy metryki uprzedzeń (parytet demograficzny, równa szansa) są obliczane przed zatwierdzeniem zestawu danych.                     |   1   |  D   |
| 6.5.3 | Zweryfikuj, czy pochodzenie i warunki licencji dla zestawów danych są uwzględnione w wpisach ML-BOM.                                          |   2   |  V   |
| 6.5.4 | Zweryfikuj, czy okresowe monitorowanie wykrywa dryf lub uszkodzenie w hostowanych zbiorach danych.                                            |   2   |  V   |
| 6.5.5 | Zweryfikuj, czy niedozwolone treści (prawa autorskie, dane osobowe) są usuwane za pomocą automatycznego oczyszczania przed treningiem.        |   3   |  D   |

---

## C6.6 Monitorowanie ataków na łańcuch dostaw

Wykrywaj zagrożenia związane z łańcuchem dostaw na wczesnym etapie dzięki kanałom CVE, analizie dzienników audytu oraz symulacjom zespołów czerwonych.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Zweryfikuj, czy dzienniki audytu CI/CD są przesyłane do SIEM, aby wykrywać anomalie w pobieraniu pakietów lub manipulacje krokami procesu budowy.                           |   1   |  V   |
| 6.6.2 | Sprawdź, czy procedury reagowania na incydenty zawierają instrukcje wycofania w przypadku naruszonych modeli lub bibliotek.                                                 |   2   |  D   |
| 6.6.3 | Zweryfikuj, czy wzbogacanie informacji o zagrożeniach oznacza specyficzne dla uczenia maszynowego wskaźniki (np. IoC związane z zatruwaniem modeli) podczas triage alertów. |   3   |  V   |

---

## C6.7 ML-BOM dla artefaktów modeli

Generuj i podpisuj szczegółowe ML‑specyficzne SBOM-y (ML‑BOM-y), aby użytkownicy końcowi mogli zweryfikować integralność komponentów w czasie wdrożenia.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Zweryfikuj, czy każdy artefakt modelu publikuje ML‑BOM, który wymienia zestawy danych, wagi, hiperparametry oraz licencje.              |   1   | D/V  |
| 6.7.2 | Zweryfikuj, czy generowanie ML-BOM i podpisywanie Cosign są zautomatyzowane w CI oraz czy ich wykonanie jest wymagane do scalenia.      |   1   | D/V  |
| 6.7.3 | Zweryfikuj, czy kontrole kompletności ML-BOM przerywają kompilację, jeśli brakuje jakichkolwiek metadanych komponentu (hash, licencja). |   2   |  D   |
| 6.7.4 | Zweryfikuj, czy odbiorcy końcowi mogą zapytać ML-BOM przez API, aby zweryfikować importowane modele w czasie wdrożenia.                 |   2   |  V   |
| 6.7.5 | Zweryfikuj, czy ML‑BOM są wersjonowane i porównywane (diff) w celu wykrywania nieautoryzowanych modyfikacji.                            |   3   |  V   |

---

## Bibliografia

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

