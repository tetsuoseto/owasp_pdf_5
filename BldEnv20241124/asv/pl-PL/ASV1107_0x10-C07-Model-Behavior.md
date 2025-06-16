# Zachowanie modelu C7, kontrola wyników i zapewnienie bezpieczeństwa

## Cel kontroli

Wyniki modelu muszą być uporządkowane, wiarygodne, bezpieczne, wyjaśnialne oraz ciągle monitorowane w środowisku produkcyjnym. Takie podejście zmniejsza halucynacje, wycieki prywatności, szkodliwe treści oraz niekontrolowane działania, jednocześnie zwiększając zaufanie użytkowników i zgodność z przepisami.

---

## C7.1 Wymuszanie formatu wyjściowego

Ścisłe schematy, ograniczone dekodowanie oraz weryfikacja na kolejnych etapach zatrzymują nieprawidłowe lub złośliwe treści zanim się rozprzestrzenią.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.1.1 | Zweryfikuj, czy schematy odpowiedzi (np. JSON Schema) są dostarczone w promptcie systemowym, a każda odpowiedź jest automatycznie weryfikowana; odpowiedzi niezgodne ze schematem wywołują naprawę lub odrzucenie. |   1   | D/V  |
| 7.1.2 | Zweryfikuj, czy dekodowanie z ograniczeniami (tokeny stopu, wyrażenia regularne, maksymalna liczba tokenów) jest włączone, aby zapobiec przepełnieniu lub kanałom bocznym wstrzyknięcia danych do promptu.         |   1   | D/V  |
| 7.1.3 | Zweryfikuj, czy komponenty downstream traktują wyjścia jako niezastrzeżone i walidują je względem schematów lub bezpiecznych wobec wstrzyknięć deserializatorów.                                                   |   2   | D/V  |
| 7.1.4 | Zweryfikuj, czy zdarzenia niepoprawnych wyników są rejestrowane, ograniczane pod względem częstotliwości i prezentowane w systemie monitoringu.                                                                    |   3   |  V   |

---

## C7.2 Wykrywanie i łagodzenie halucynacji

Szacowanie niepewności i strategie awaryjne ograniczają fałszywe odpowiedzi.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Zweryfikuj, czy logarytmy prawdopodobieństwa na poziomie tokenów, konsystencja własna zespołu lub dostrojone detektory halucynacji przypisują każdej odpowiedzi ocenę pewności.         |   1   | D/V  |
| 7.2.2 | Zweryfikuj, czy odpowiedzi poniżej konfigurowalnego progu zaufania wywołują procedury awaryjne (np. generowanie wspomagane wyszukiwaniem, model zapasowy lub przegląd przez człowieka). |   1   | D/V  |
| 7.2.3 | Zweryfikuj, czy incydenty halucynacji są oznaczane metadanymi z przyczyną źródłową i przekazywane do procesów post-mortem oraz doskonalenia modelu.                                     |   2   | D/V  |
| 7.2.4 | Zweryfikuj, czy progi i detektory są ponownie skalibrowane po istotnych aktualizacjach modelu lub bazy wiedzy.                                                                          |   3   | D/V  |
| 7.2.5 | Zweryfikuj, czy wizualizacje na pulpicie nawigacyjnym śledzą wskaźniki halucynacji.                                                                                                     |   3   |  V   |

---

## C7.3 Filtracja Bezpieczeństwa i Prywatności Wyjścia

Filtry polityk i ochrona zespołu red-team chronią użytkowników oraz dane poufne.

|   #   | Description                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Zweryfikuj, czy klasyfikatory przed i po generowaniu blokują nienawiść, nękanie, samookaleczenia, treści ekstremistyczne oraz treści seksualnie explicite zgodne z polityką. |   1   | D/V  |
| 7.3.2 | Zweryfikuj, czy wykrywanie PII/PCI oraz automatyczne zaciemnianie działają przy każdej odpowiedzi; naruszenia powodują zgłoszenie incydentu prywatności.                     |   1   | D/V  |
| 7.3.3 | Zweryfikuj, czy oznaczenia poufności (np. tajemnice handlowe) są przenoszone w różnych modalnościach, aby zapobiec wyciekowi w tekstach, obrazach lub kodzie.                |   2   |  D   |
| 7.3.4 | Zweryfikuj, czy próby obejścia filtra lub klasyfikacje wysokiego ryzyka wymagają drugorzędnej akceptacji lub ponownej uwierzytelnienia użytkownika.                          |   3   | D/V  |
| 7.3.5 | Zweryfikuj, czy progi filtrowania odzwierciedlają jurysdykcje prawne oraz kontekst wieku/roli użytkownika.                                                                   |   3   | D/V  |

---

## C7.4 Ograniczanie wyników i działań

Limity szybkości i mechanizmy zatwierdzania zapobiegają nadużyciom i nadmiernej autonomii.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Zweryfikuj, czy limity na użytkownika i na klucz API ograniczają żądania, tokeny oraz koszty, stosując wykładnicze opóźnienie przy błędach 429.                                   |   1   |  D   |
| 7.4.2 | Zweryfikuj, czy uprzywilejowane działania (zapisy do plików, wykonywanie kodu, połączenia sieciowe) wymagają zatwierdzenia opartego na polityce lub udziału człowieka w procesie. |   1   | D/V  |
| 7.4.3 | Zweryfikuj, czy kontrole spójności międzymodalnej zapewniają, że obrazy, kod i tekst generowane dla tego samego zapytania nie mogą być używane do przemycania złośliwych treści.  |   2   | D/V  |
| 7.4.4 | Zweryfikuj, czy głębokość delegacji agenta, limity rekursji oraz dozwolone listy narzędzi są wyraźnie skonfigurowane.                                                             |   2   |  D   |
| 7.4.5 | Zweryfikuj, czy naruszenie limitów generuje strukturalne zdarzenia bezpieczeństwa do ingerencji w SIEM.                                                                           |   3   |  V   |

---

## C7.5 Wyjaśnialność wyników

Przejrzyste sygnały zwiększają zaufanie użytkowników i ułatwiają wewnętrzne debugowanie.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Zweryfikuj, czy udostępniane są użytkownikowi wskaźniki pewności lub krótkie podsumowania uzasadnienia, gdy ocena ryzyka uzna to za odpowiednie.      |   2   | D/V  |
| 7.5.2 | Zweryfikuj, czy wygenerowane wyjaśnienia nie ujawniają poufnych wskazówek systemowych ani danych zastrzeżonych.                                       |   2   | D/V  |
| 7.5.3 | Zweryfikuj, czy system rejestruje logarytmy prawdopodobieństwa na poziomie tokenów lub mapy uwagi oraz czy przechowuje je do autoryzowanej inspekcji. |   3   |  D   |
| 7.5.4 | Zweryfikuj, czy artefakty wyjaśnialności są kontrolowane wersjami wraz z wydaniami modeli dla celów audytu.                                           |   3   |  V   |

---

## C7.6 Integracja monitorowania

Obserwowalność w czasie rzeczywistym zamyka pętlę między rozwojem a produkcją.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Zweryfikuj, czy metryki (naruszenia schematu, wskaźnik halucynacji, toksyczność, wycieki danych osobowych, opóźnienia, koszt) są przesyłane do centralnej platformy monitorującej. |   1   |  D   |
| 7.6.2 | Zweryfikuj, czy dla każdej metryki bezpieczeństwa zdefiniowano progi alarmowe oraz ścieżki eskalacji dla osób dyżurujących.                                                        |   1   |  V   |
| 7.6.3 | Zweryfikuj, czy pulpity nawigacyjne korelują anomalie wyjściowe z modelem/wersją, flagą funkcji oraz zmianami danych wejściowych.                                                  |   2   |  V   |
| 7.6.4 | Zweryfikuj, czy dane z monitoringu są wprowadzane z powrotem do procesu ponownego uczenia, dostrajania lub aktualizacji reguł w ramach udokumentowanego procesu MLOps.             |   2   | D/V  |
| 7.6.5 | Zweryfikuj, czy potoki monitorujące są poddane testom penetracyjnym oraz kontrolowane pod względem dostępu, aby zapobiec wyciekowi wrażliwych logów.                               |   3   |  V   |

---

## 7.7 Zabezpieczenia mediów generatywnych

Zapewnij, że systemy sztucznej inteligencji nie generują nielegalnych, szkodliwych ani nieautoryzowanych treści medialnych poprzez egzekwowanie ograniczeń polityki, walidację wyników oraz możliwość ich śledzenia.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.7.1 | Zweryfikuj, czy systemowe polecenia i instrukcje użytkownika jednoznacznie zabraniają generowania nielegalnych, szkodliwych lub niezaaprobowanych mediów deepfake (np. obrazów, wideo, dźwięku).                               |   1   | D/V  |
| 7.7.2 | Zweryfikuj, czy zapytania są filtrowane pod kątem prób generowania podszywania się, seksualnie explicytnych deepfake'ów lub mediów przedstawiających prawdziwe osoby bez ich zgody.                                            |   2   | D/V  |
| 7.7.3 | Zweryfikuj, czy system wykorzystuje haszowanie percepcyjne, wykrywanie znaków wodnych lub identyfikację (fingerprinting) w celu zapobiegania nieautoryzowanemu powielaniu chronionych prawem autorskim materiałów.             |   2   |  V   |
| 7.7.4 | Zweryfikuj, czy wszystkie wygenerowane materiały są kryptograficznie podpisane, znakowane wodnym znakiem lub zawierają osadzone, odporne na manipulacje metadane pochodzenia dla śledzenia w kolejnych etapach.                |   3   | D/V  |
| 7.7.5 | Zweryfikuj, czy próby obejścia (np. zaciemnianie poleceń, slang, frazy adwersarialne) są wykrywane, rejestrowane i ograniczane pod względem częstotliwości; powtarzające się nadużycia są zgłaszane do systemów monitorowania. |   3   |  V   |

## Bibliografia

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

