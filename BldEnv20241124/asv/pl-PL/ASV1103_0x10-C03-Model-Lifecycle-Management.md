# Zarządzanie cyklem życia modelu C3 i kontrola zmian

## Cel kontroli

Systemy sztucznej inteligencji muszą wdrażać procesy kontroli zmian, które zapobiegają nieautoryzowanym lub niebezpiecznym modyfikacjom modeli trafiającym do środowiska produkcyjnego. Ta kontrola zapewnia integralność modelu przez cały jego cykl życia — od etapu rozwoju, przez wdrożenie, aż do wycofania — co umożliwia szybkie reagowanie na incydenty i utrzymuje odpowiedzialność za wszystkie zmiany.

Główny cel bezpieczeństwa: Tylko autoryzowane, zweryfikowane modele trafiają do produkcji poprzez stosowanie kontrolowanych procesów, które zapewniają integralność, śledzenie i możliwość odzyskiwania.

---

## C3.1 Autoryzacja i integralność modelu

Do środowisk produkcyjnych trafiają wyłącznie autoryzowane modele z potwierdzoną integralnością.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Zweryfikuj, czy wszystkie artefakty modelu (wagi, konfiguracje, tokenizery) są podpisane kryptograficznie przez uprawnione podmioty przed wdrożeniem.                                                                         |   1   | D/V  |
| 3.1.2 | Zweryfikuj, czy integralność modelu jest potwierdzana w czasie wdrożenia, a błędy weryfikacji podpisu uniemożliwiają załadowanie modelu.                                                                                      |   1   | D/V  |
| 3.1.3 | Zweryfikuj, czy zapisy pochodzenia modelu zawierają tożsamość podmiotu autoryzującego, sumy kontrolne danych treningowych, wyniki testów walidacyjnych z oznaczeniem zaliczenia/niezaliczenia oraz znacznik czasu utworzenia. |   2   | D/V  |
| 3.1.4 | Zweryfikuj, czy wszystkie artefakty modelu używają wersjonowania semantycznego (MAJOR.MINOR.PATCH) z udokumentowanymi kryteriami określającymi, kiedy następuje zwiększenie każdego składnika wersji.                         |   2   | D/V  |
| 3.1.5 | Zweryfikuj, czy śledzenie zależności utrzymuje inwentaryzację w czasie rzeczywistym, która umożliwia szybkie identyfikowanie wszystkich systemów korzystających.                                                              |   2   |  V   |

---

## C3.2 Walidacja i testowanie modelu

Modele muszą przejść określone walidacje bezpieczeństwa i ochrony przed wdrożeniem.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.2.1 | Zweryfikuj, czy modele przechodzą zautomatyzowane testy bezpieczeństwa, które obejmują walidację danych wejściowych, sanitację danych wyjściowych oraz oceny bezpieczeństwa z uprzednio ustalonymi wewnętrznymi progami zaliczenia/niezaliczenia przed wdrożeniem. |   1   | D/V  |
| 3.2.2 | Zweryfikuj, czy niepowodzenia walidacji automatycznie blokują wdrożenie modelu po wyraźnym zatwierdzeniu nadpisania przez wcześniej wyznaczone upoważnione osoby z udokumentowanymi uzasadnieniami biznesowymi.                                                    |   1   | D/V  |
| 3.2.3 | Zweryfikuj, czy wyniki testów są kryptograficznie podpisane i trwale powiązane z haszem konkretnej wersji modelu, która jest weryfikowana.                                                                                                                         |   2   |  V   |
| 3.2.4 | Zweryfikuj, czy wdrożenia awaryjne wymagają udokumentowanej oceny ryzyka bezpieczeństwa oraz zatwierdzenia przez wcześniej wyznaczonego organ ds. bezpieczeństwa w ustalonych wcześniej ramach czasowych.                                                          |   2   | D/V  |

---

## C3.3 Kontrolowane Wdrażanie i Wycofywanie

Wdrażanie modeli musi być kontrolowane, monitorowane i odwracalne.

|   #   | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Zweryfikuj, czy wdrożenia produkcyjne implementują mechanizmy stopniowego wprowadzania (wdrożenia kanaryjskie, wdrożenia blue-green) z automatycznymi wyzwalaczami wycofania na podstawie wcześniej ustalonych wskaźników błędów, progów opóźnień lub kryteriów alertów bezpieczeństwa. |   1   |  D   |
| 3.3.2 | Zweryfikuj, czy możliwości wycofania przywracają kompletny stan modelu (wagi, konfiguracje, zależności) atomowo w ramach wcześniej zdefiniowanych okien czasowych organizacji.                                                                                                          |   1   | D/V  |
| 3.3.3 | Zweryfikuj, czy procesy wdrożeniowe weryfikują podpisy kryptograficzne oraz obliczają sumy kontrolne integralności przed aktywacją modelu, przerywając wdrożenie w przypadku jakiejkolwiek niezgodności.                                                                                |   2   | D/V  |
| 3.3.4 | Zweryfikuj, czy możliwości awaryjnego wyłączania modeli mogą dezaktywować punkty końcowe modeli w określonych z góry czasach reakcji za pomocą zautomatyzowanych wyłączników obwodów lub ręcznych przycisków awaryjnych.                                                                |   2   | D/V  |
| 3.3.5 | Zweryfikuj, czy artefakty wycofania (poprzednie wersje modeli, konfiguracje, zależności) są przechowywane zgodnie z politykami organizacji w niezmiennym magazynie danych na potrzeby reagowania na incydenty.                                                                          |   2   |  V   |

---

## C3.4 Zmienność Odpowiedzialności i Audytu

Wszystkie zmiany w cyklu życia modelu muszą być możliwe do śledzenia i audytu.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Zweryfikuj, czy wszystkie zmiany modelu (wdrożenie, konfiguracja, wycofanie) generują niezmienialne zapisy audytu zawierające znacznik czasu, uwierzytelnioną tożsamość wykonawcy, typ zmiany oraz stany przed i po zmianie.     |   1   |  V   |
| 3.4.2 | Zweryfikuj, czy dostęp do dziennika audytu wymaga odpowiedniej autoryzacji oraz czy wszystkie próby dostępu są rejestrowane wraz z tożsamością użytkownika i znacznikiem czasowym.                                               |   2   | D/V  |
| 3.4.3 | Zweryfikuj, czy szablony promptów i wiadomości systemowych są kontrolowane wersjami w repozytoriach git, z obowiązkowym przeglądem kodu i zatwierdzeniem przez wyznaczonych recenzentów przed wdrożeniem.                        |   2   | D/V  |
| 3.4.4 | Zweryfikuj, czy rejestry audytu zawierają wystarczające szczegóły (hasze modeli, zrzuty konfiguracji, wersje zależności), aby umożliwić pełną rekonstrukcję stanu modelu dla dowolnego znacznika czasu w okresie przechowywania. |   2   |  V   |

---

## C3.5 Bezpieczne praktyki rozwoju oprogramowania

Procesy opracowywania i trenowania modeli muszą przestrzegać bezpiecznych praktyk, aby zapobiec ich naruszeniu.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.5.1 | Zweryfikować, czy środowiska tworzenia modeli, testowania i produkcji są fizycznie lub logicznie oddzielone. Nie mają wspólnej infrastruktury, posiadają różne mechanizmy kontroli dostępu oraz izolowane zasoby danych. |   1   |  D   |
| 3.5.2 | Zweryfikuj, czy trening modelu i dostrajanie odbywają się w izolowanych środowiskach z kontrolowanym dostępem do sieci.                                                                                                  |   1   |  D   |
| 3.5.3 | Zweryfikuj, czy źródła danych treningowych są potwierdzone poprzez kontrole integralności oraz uwierzytelnione za pomocą zaufanych źródeł z udokumentowanym łańcuchem kontroli przed użyciem w rozwoju modelu.           |   1   | D/V  |
| 3.5.4 | Zweryfikuj, czy artefakty tworzenia modelu (hiperparametry, skrypty treningowe, pliki konfiguracyjne) są przechowywane w systemie kontroli wersji i wymagają zatwierdzenia przez recenzenta przed użyciem w treningu.    |   2   |  D   |

---

## C3.6 Wycofanie i wyłączenie modelu

Modele muszą być bezpiecznie wycofane, gdy nie są już potrzebne lub gdy zostaną zidentyfikowane problemy związane z bezpieczeństwem.

|   #   | Description                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Zweryfikuj, czy procesy wycofywania modeli automatycznie skanują grafy zależności, identyfikują wszystkie systemy korzystające oraz zapewniają wcześniej uzgodnione okresy powiadomień przed wycofaniem z eksploatacji.                                             |   1   |  D   |
| 3.6.2 | Zweryfikuj, czy wycofane modele i ich artefakty są bezpiecznie usuwane za pomocą kryptograficznego kasowania lub wielokrotnego nadpisywania zgodnie z udokumentowanymi politykami przechowywania danych oraz czy posiadane są potwierdzone certyfikaty zniszczenia. |   1   | D/V  |
| 3.6.3 | Zweryfikuj, czy zdarzenia wycofania modelu są rejestrowane z zaznaczeniem czasu i tożsamości wykonawcy oraz czy podpisy modelu są unieważniane, aby zapobiec ponownemu użyciu.                                                                                      |   2   |  V   |
| 3.6.4 | Zweryfikuj, czy awaryjne wycofanie modelu może wyłączyć dostęp do modelu w ramach wcześniej ustalonych czasów reakcji awaryjnej za pomocą zautomatyzowanych przełączników awaryjnych, jeśli zostaną wykryte krytyczne luki bezpieczeństwa.                          |   2   | D/V  |

---

## Bibliografia

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

