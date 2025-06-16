# Aneks D: Zasady zarządzania i weryfikacji bezpiecznego kodowania wspomaganego przez AI

## Cel

Ten rozdział definiuje podstawowe kontrole organizacyjne dla bezpiecznego i skutecznego korzystania z narzędzi kodowania wspomaganego przez AI podczas tworzenia oprogramowania, zapewniając bezpieczeństwo i możliwość śledzenia w całym cyklu życia oprogramowania (SDLC).

---

## AD.1 Asystowany przez AI Bezpieczny Workflow Kodowania

Zintegruj narzędzia AI w bezpiecznym cyklu życia rozwoju oprogramowania (SSDLC) organizacji, nie osłabiając istniejących zabezpieczeń.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.1.1 | Zweryfikuj, czy udokumentowany proces roboczy opisuje, kiedy i jak narzędzia AI mogą generować, refaktoryzować lub przeglądać kod.                                                         |   1   | D/V  |
| AD.1.2 | Zweryfikuj, czy przepływ pracy odpowiada każdej fazie SSDLC (projektowanie, implementacja, przegląd kodu, testowanie, wdrażanie).                                                          |   2   |  D   |
| AD.1.3 | Zweryfikuj, czy metryki (np. gęstość podatności, średni czas wykrywania) są zbierane dla kodu wygenerowanego przez AI i porównywane do bazowych wartości uzyskanych wyłącznie przez ludzi. |   3   | D/V  |

---

## AD.2 Kwalifikacja narzędzi AI i modelowanie zagrożeń

Upewnij się, że narzędzia do kodowania AI są oceniane pod kątem możliwości bezpieczeństwa, ryzyka oraz wpływu na łańcuch dostaw przed ich wdrożeniem.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Zweryfikuj, czy model zagrożeń dla każdego narzędzia AI identyfikuje ryzyka niewłaściwego użycia, inwersji modelu, wycieku danych oraz łańcucha zależności.                            |   1   | D/V  |
| AD.2.2 | Zweryfikuj, czy oceny narzędzi obejmują analizę statyczną/dynamiczną wszelkich lokalnych komponentów oraz ocenę punktów końcowych SaaS (TLS, uwierzytelnianie/autoryzacja, logowanie). |   2   |  D   |
| AD.2.3 | Zweryfikuj, czy oceny są prowadzone zgodnie z uznanym ramowym schematem i są ponownie wykonywane po większych zmianach wersji.                                                         |   3   | D/V  |

---

## AD.3 Bezpieczne Zarządzanie Podpowiedziami i Kontekstem

Zapobiegaj wyciekowi sekretów, chronionego kodu i danych osobowych podczas tworzenia promptów lub kontekstów dla modeli AI.

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.3.1 | Zweryfikuj, czy pisemne wytyczne zabraniają przesyłania sekretów, poświadczeń lub danych sklasyfikowanych w zapytaniach.                                                             |   1   | D/V  |
| AD.3.2 | Zweryfikuj, czy kontrolki techniczne (redakcja po stronie klienta, zatwierdzone filtry kontekstowe) automatycznie usuwają wrażliwe elementy.                                         |   2   |  D   |
| AD.3.3 | Zweryfikuj, czy zapytania i odpowiedzi są tokenizowane, szyfrowane podczas przesyłania i w stanie spoczynku oraz czy okresy przechowywania są zgodne z polityką klasyfikacji danych. |   3   | D/V  |

---

## AD.4 Walidacja kodu wygenerowanego przez sztuczną inteligencję

Wykrywanie i usuwanie luk bezpieczeństwa wprowadzonych przez wyniki AI przed scałkowaniem lub wdrożeniem kodu.

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Zweryfikuj, że kod generowany przez AI jest zawsze poddawany przeglądowi przez człowieka.                                                                                                   |   1   | D/V  |
| AD.4.2 | Zweryfikuj, czy automatyczne skanery (SAST/IAST/DAST) są uruchamiane przy każdym pull requeście zawierającym kod generowany przez AI oraz czy blokują scalanie przy krytycznych problemach. |   2   |  D   |
| AD.4.3 | Zweryfikuj, czy testowanie różnicowe fuzz lub testy oparte na właściwościach potwierdzają krytyczne dla bezpieczeństwa zachowania (np. walidacja danych wejściowych, logika autoryzacji).   |   3   | D/V  |

---

## AD.5 Wyjaśnialność i identyfikowalność sugestii kodu

Zapewnij audytorom i deweloperom wgląd w to, dlaczego zasugerowano daną opcję i jak się ona rozwijała.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Zweryfikuj, czy pary zapytań/odpowiedzi są rejestrowane z identyfikatorami commitów.                                                                                                                |   1   | D/V  |
| AD.5.2 | Zweryfikuj, czy deweloperzy mogą udostępniać odwołania do modeli (fragmenty treningowe, dokumentację) wspierające sugestię.                                                                         |   2   |  D   |
| AD.5.3 | Zweryfikuj, czy raporty wyjaśnialności są przechowywane wraz z artefaktami projektowymi i odwoływane w przeglądach bezpieczeństwa, spełniając zasady śledzalności określone w normie ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Ciągła informacja zwrotna i dopasowywanie modelu

Poprawiaj bezpieczeństwo modelu z upływem czasu, jednocześnie zapobiegając negatywnemu dryfowi.

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Zweryfikuj, czy deweloperzy mogą oznaczać niebezpieczne lub niezgodne z przepisami sugestie oraz czy oznaczenia te są śledzone.                                                                                      |   1   | D/V  |
| AD.6.2 | Zweryfikuj, czy skonsolidowane opinie służą do okresowego dostrajania lub generowania wspomaganego wyszukiwaniem za pomocą zweryfikowanych korpusów dotyczących bezpiecznego programowania (np. OWASP Cheat Sheets). |   2   |  D   |
| AD.6.3 | Zweryfikuj, czy zamknięty system oceny wykonuje testy regresji po każdej dostosowaniu; metryki bezpieczeństwa muszą spełniać lub przekraczać wcześniejsze wartości odniesienia przed wdrożeniem.                     |   3   | D/V  |

---

### Referencje

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

