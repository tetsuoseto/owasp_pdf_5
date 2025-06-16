# C13 Nadzór ludzki, odpowiedzialność i zarządzanie

## Cel Kontroli

Ten rozdział określa wymagania dotyczące utrzymania nadzoru człowieka oraz jasnych łańcuchów odpowiedzialności w systemach AI, zapewniając wyjaśnialność, przejrzystość oraz etyczne zarządzanie na całym etapie życia AI.

---

## C13.1 Mechanizmy Wyłączania Awaryjnego i Przejęcia Kontroli

Zapewnij ścieżki zamknięcia lub wycofania w przypadku zaobserwowania niebezpiecznego zachowania systemu AI.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Zweryfikuj, czy istnieje ręczny mechanizm awaryjnego zatrzymania, który natychmiast przerwie wnioskowanie i generowanie wyników przez model AI. |   1   | D/V  |
| 13.1.2 | Zweryfikuj, czy kontrolki nadpisania są dostępne wyłącznie dla upoważnionego personelu.                                                         |   1   |  D   |
| 13.1.3 | Zweryfikuj, czy procedury przywracania mogą cofnąć się do poprzednich wersji modeli lub trybu bezpiecznego działania.                           |   3   | D/V  |
| 13.1.4 | Sprawdź, czy mechanizmy nadpisywania są regularnie testowane.                                                                                   |   3   |  V   |

---

## C13.2 Punkty kontrolne decyzji z udziałem człowieka

Wymagaj zatwierdzeń ludzkich, gdy stawki przekraczają zdefiniowane progi ryzyka.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Zweryfikuj, czy decyzje AI o wysokim ryzyku wymagają wyraźnej zgody człowieka przed wykonaniem.                                                                                  |   1   | D/V  |
| 13.2.2 | Zweryfikuj, czy progi ryzyka są jasno określone i automatycznie uruchamiają procesy przeglądu przez człowieka.                                                                   |   1   |  D   |
| 13.2.3 | Zweryfikuj, czy decyzje wrażliwe na upływ czasu mają procedury awaryjne na wypadek, gdyby zatwierdzenie przez człowieka nie mogło zostać uzyskane w wymaganych ramach czasowych. |   2   |  D   |
| 13.2.4 | Zweryfikuj, czy procedury eskalacji definiują wyraźne poziomy uprawnień dla różnych typów decyzji lub kategorii ryzyka, jeśli ma to zastosowanie.                                |   3   | D/V  |

---

## C13.3 Łańcuch odpowiedzialności i możliwość audytu

Rejestruj działania operatora i decyzje modelu.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.3.1 | Zweryfikuj, czy wszystkie decyzje systemu AI oraz interwencje ludzi są rejestrowane z oznaczeniem czasu, tożsamości użytkowników oraz uzasadnieniem decyzji. |   1   | D/V  |
| 13.3.2 | Zweryfikuj, czy dzienniki audytu nie mogą być fałszowane i czy zawierają mechanizmy weryfikacji integralności.                                               |   2   |  D   |

---

## C13.4 Techniki wyjaśnialnej sztucznej inteligencji (Explainable-AI)

Ważność cech powierzchniowych, kontrfaktyczne przykłady oraz lokalne wyjaśnienia.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Zweryfikuj, czy systemy sztucznej inteligencji dostarczają podstawowe wyjaśnienia swoich decyzji w formacie czytelnym dla człowieka.                                    |   1   | D/V  |
| 13.4.2 | Zweryfikuj, czy jakość wyjaśnień jest potwierdzona poprzez badania ewaluacyjne prowadzone przez ludzi oraz odpowiednie metryki.                                         |   2   |  V   |
| 13.4.3 | Zweryfikuj, czy oceny ważności cech lub metody atrybucji (SHAP, LIME itp.) są dostępne dla decyzji krytycznych.                                                         |   3   | D/V  |
| 13.4.4 | Zweryfikuj, czy wyjaśnienia kontrfaktyczne pokazują, jak można zmodyfikować dane wejściowe, aby zmienić wyniki, jeśli jest to istotne dla przypadku użycia i dziedziny. |   3   |  V   |

---

## C13.5 Karty modeli i ujawnienia dotyczące użytkowania

Utrzymuj karty modelu zawierające informacje o zamierzonym zastosowaniu, metrykach wydajności oraz kwestiach etycznych.

|   #    | Description                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.5.1 | Zweryfikuj, czy karty modeli dokumentują zamierzone przypadki użycia, ograniczenia oraz znane tryby awarii.                                                                                                              |   1   |  D   |
| 13.5.2 | Zweryfikuj, czy metryki wydajności w różnych odpowiednich przypadkach użycia są ujawnione.                                                                                                                               |   1   | D/V  |
| 13.5.3 | Sprawdź, czy uwzględniono kwestie etyczne, oceny uprzedzeń, oceny sprawiedliwości, cechy danych szkoleniowych oraz znane ograniczenia danych szkoleniowych, a także czy są one regularnie dokumentowane i aktualizowane. |   2   |  D   |
| 13.5.4 | Zweryfikuj, czy karty modelu są wersjonowane i utrzymywane przez cały cykl życia modelu z śledzeniem zmian.                                                                                                              |   2   | D/V  |

---

## C13.6 Kwantyfikacja niepewności

Propaguj wartości ufności lub miary entropii w odpowiedziach.

|   #    | Description                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Zweryfikuj, czy systemy AI dostarczają współczynniki ufności lub miary niepewności wraz z ich wynikami.           |   1   |  D   |
| 13.6.2 | Zweryfikuj, czy progi niepewności wywołują dodatkową kontrolę przez człowieka lub alternatywne ścieżki decyzyjne. |   2   | D/V  |
| 13.6.3 | Zweryfikuj, czy metody kwantyfikacji niepewności są skalibrowane i zwalidowane względem danych rzeczywistych.     |   2   |  V   |
| 13.6.4 | Zweryfikuj, czy propagacja niepewności jest utrzymywana przez wieloetapowe przepływy pracy AI.                    |   3   | D/V  |

---

## C13.7 Raporty Transparentności dla Użytkowników

Zapewnij okresowe ujawnienia dotyczące incydentów, dryfu i wykorzystania danych.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Zweryfikuj, czy zasady dotyczące wykorzystania danych oraz praktyki zarządzania zgodą użytkowników są jasno przekazywane zainteresowanym stronom.                                |   1   | D/V  |
| 13.7.2 | Zweryfikuj, czy oceny wpływu AI są przeprowadzane, a wyniki są uwzględnione w raportowaniu.                                                                                      |   2   | D/V  |
| 13.7.3 | Zweryfikuj, czy regularnie publikowane raporty przejrzystości ujawniają incydenty związane ze sztuczną inteligencją oraz metryki operacyjne w rozsądnym zakresie szczegółowości. |   2   | D/V  |

### Bibliografia

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

