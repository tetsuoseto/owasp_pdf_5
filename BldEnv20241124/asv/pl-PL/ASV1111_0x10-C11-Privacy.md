# 11 Ochrona prywatności i zarządzanie danymi osobowymi

## Cel kontroli

Utrzymuj rygorystyczne gwarancje prywatności na całym cyklu życia AI — od zbierania danych, przez trening, wnioskowanie, aż po reakcję na incydenty — tak aby dane osobowe były przetwarzane wyłącznie za wyraźną zgodą, w minimalnym niezbędnym zakresie, podlegające wykazywalnemu usunięciu oraz formalnym gwarancjom prywatności.

---

## 11.1 Anonimizacja i minimalizacja danych

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Zweryfikuj, czy bezpośrednie i quasi-identyfikatory zostały usunięte lub zhashowane.                                                                                |   1   | D/V  |
| 11.1.2 | Zweryfikuj, czy zautomatyzowane audyty mierzą k-anonimowość/l-rozmaitość i generują alert, gdy progi spadają poniżej ustalonej polityki.                            |   2   | D/V  |
| 11.1.3 | Zweryfikuj, że raporty dotyczące istotności cech modelu potwierdzają brak wycieku identyfikatora przekraczającego ε = 0,01 informacji wzajemnej.                    |   2   |  V   |
| 11.1.4 | Zweryfikuj, czy formalne dowody lub certyfikacja na podstawie danych syntetycznych wykazują ryzyko ponownej identyfikacji ≤ 0,05 nawet w przypadku ataków powiązań. |   3   |  V   |

---

## 11.2 Prawo do bycia zapomnianym i egzekwowanie usuwania

|   #    | Description                                                                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Zweryfikuj, czy żądania usunięcia danych dotyczących podmiotu są propagowane do surowych zbiorów danych, punktów kontrolnych, wektorów osadzających, dzienników oraz kopii zapasowych w ramach umów na poziomie usług wynoszących mniej niż 30 dni. |   1   | D/V  |
| 11.2.2 | Zweryfikuj, czy procedury "machine-unlearning" faktycznie przeprowadzają ponowne uczenie lub przybliżone usunięcie za pomocą certyfikowanych algorytmów unlearningu.                                                                                |   2   |  D   |
| 11.2.3 | Potwierdź, że ocena modelu cieniowego wykazuje, iż zapomniane rekordy wpływają na mniej niż 1% wyników po procesie zapominania.                                                                                                                     |   2   |  V   |
| 11.2.4 | Zweryfikuj, czy zdarzenia usunięcia są niezmiennie rejestrowane i audytowalne dla organów regulacyjnych.                                                                                                                                            |   3   |  V   |

---

## 11.3 Zabezpieczenia prywatności różnicowej

|   #    | Description                                                                                                                         | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Zweryfikuj, czy pulpity monitorujące rozliczanie utraty prywatności informują, gdy skumulowana wartość ε przekracza progi polityki. |   2   | D/V  |
| 11.3.2 | Zweryfikuj, czy audyty prywatności typu black-box szacują ε̂ z dokładnością do 10% deklarowanej wartości.                           |   2   |  V   |
| 11.3.3 | Zweryfikuj, czy formalne dowody obejmują wszystkie dostrajania po treningu i osadzenia.                                             |   3   |  V   |

---

## 11.4 Ograniczenie celu i ochrona przed rozszerzaniem zakresu

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.4.1 | Zweryfikuj, czy każdy zestaw danych i punkt kontrolny modelu posiada maszynowo odczytywalną etykietę celu zgodną z oryginalną zgodą. |   1   |  D   |
| 11.4.2 | Zweryfikuj, czy monitory czasu wykonania wykrywają zapytania niezgodne z zadeklarowanym celem i wywołują miękkie odrzucenie.         |   1   | D/V  |
| 11.4.3 | Zweryfikuj, czy bramki policy-as-code blokują ponowne wdrożenie modeli do nowych domen bez przeglądu DPIA.                           |   3   |  D   |
| 11.4.4 | Zweryfikuj, że formalne dowody odtwarzalności wykazują, iż każdy cykl życia danych osobowych pozostaje w zakresie zgody.             |   3   |  V   |

---

## 11.5 Zarządzanie zgodą i śledzenie na podstawie prawnej

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Zweryfikuj, czy Platforma Zarządzania Zgodami (CMP) rejestruje status zgody, cel oraz okres przechowywania danych dla każdej osoby, której dane dotyczą. |   1   | D/V  |
| 11.5.2 | Zweryfikuj, czy interfejsy API udostępniają tokeny zgody; modele muszą weryfikować zakres tokenu przed wykonaniem wnioskowania.                          |   2   |  D   |
| 11.5.3 | Zweryfikuj, czy odmowa lub wycofanie zgody zatrzymuje przetwarzanie danych w ciągu 24 godzin.                                                            |   2   | D/V  |

---

## 11.6 Uczenie federacyjne z kontrolą prywatności

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Zweryfikuj, czy aktualizacje klienta wykorzystują lokalne dodawanie szumu z zachowaniem prywatności różnicowej przed agregacją. |   1   |  D   |
| 11.6.2 | Zweryfikuj, czy metryki treningowe są prywatne różnicowo i nigdy nie ujawniają straty pojedynczego klienta.                     |   2   | D/V  |
| 11.6.3 | Zweryfikuj, czy jest włączona odporna na zatruwanie agregacja (np. Krum/Średnia przycięta).                                     |   2   |  V   |
| 11.6.4 | Zweryfikuj, czy formalne dowody wykazują ogólny budżet ε z utratą użyteczności mniejszą niż 5.                                  |   3   |  V   |

---

### Bibliografia

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

