# Walidacja danych wejściowych użytkownika C2

## Cel kontroli

Solidna walidacja danych wejściowych użytkownika jest pierwszą linią obrony przed niektórymi z najbardziej szkodliwych ataków na systemy AI. Ataki typu prompt injection mogą nadpisać instrukcje systemowe, ujawnić poufne dane lub skłonić model do zachowania, które jest niedozwolone. Badania pokazują, że jeśli nie zostaną zastosowane dedykowane filtry i hierarchie instrukcji, "multi-shot" jailbreaki wykorzystujące bardzo długie okna kontekstowe będą skuteczne. Ponadto subtelne ataki z użyciem przeciwnych zakłóceń — takie jak zamiany homoglifów lub leetspeak — mogą dyskretnie zmieniać decyzje modelu.

---

## C2.1 Obrona przed wstrzyknięciem promptów

Wstrzyknięcie podpowiedzi jest jednym z największych zagrożeń dla systemów sztucznej inteligencji. Obrona przed tą taktyką wykorzystuje kombinację statycznych filtrów wzorców, dynamicznych klasyfikatorów oraz egzekwowanie hierarchii instrukcji.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Zweryfikuj, czy dane wejściowe użytkownika są sprawdzane w odniesieniu do ciągle aktualizowanej biblioteki znanych wzorców wstrzyknięć promptów (słowa kluczowe jailbreak, "ignoruj poprzednie", łańcuchy odgrywania ról, pośrednie ataki HTML/URL). |   1   | D/V  |
| 2.1.2 | Sprawdź, czy system wymusza hierarchię instrukcji, w której wiadomości systemowe lub deweloperskie mają pierwszeństwo przed instrukcjami użytkownika, nawet po rozszerzeniu okna kontekstu.                                                          |   1   | D/V  |
| 2.1.3 | Zweryfikuj, czy testy ewaluacji adwersarialnej (np. „many-shot” promptów zespołu Red Team) są przeprowadzane przed każdym wydaniem modelu lub szablonu promptu, z ustalonymi progami skuteczności oraz automatycznymi blokadami regresji.            |   2   | D/V  |
| 2.1.4 | Zweryfikuj, czy podpowiedzi pochodzące z treści stron trzecich (strony internetowe, pliki PDF, e-maile) są oczyszczane w izolowanym kontekście parsowania przed połączeniem ich z główną podpowiedzią.                                               |   2   |  D   |
| 2.1.5 | Zweryfikuj, czy wszystkie aktualizacje reguł filtrów promptów, wersje modeli klasyfikatorów oraz zmiany listy blokad są kontrolowane pod względem wersji i audytowalne.                                                                              |   3   | D/V  |

---

## C2.2 Odporność na przykłady adwersarzy

Modele przetwarzania języka naturalnego (NLP) są nadal podatne na subtelne zakłócenia na poziomie znaków lub słów, które ludzie często przeoczają, ale modele mają tendencję do błędnej klasyfikacji.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Zweryfikuj, czy podstawowe kroki normalizacji danych wejściowych (Unicode NFC, mapowanie homoglifów, przycinanie białych znaków) są wykonywane przed tokenizacją.                                                       |   1   |  D   |
| 2.2.2 | Zweryfikuj, czy statystyczne wykrywanie anomalii oznacza dane wejściowe o wyjątkowo wysokiej odległości edycyjnej od norm językowych, nadmiernie powtarzających się tokenach lub nieprawidłowych odległościach osadzeń. |   2   | D/V  |
| 2.2.3 | Zweryfikuj, czy potok inferencji obsługuje opcjonalne warianty modeli wzmocnionych treningiem przeciwnym lub warstwy obronne (np. losowość, defensywna destylacja) dla punktów końcowych o wysokim ryzyku.              |   2   |  D   |
| 2.2.4 | Zweryfikuj, czy podejrzane dane wejściowe o charakterze przeciwnym są kwarantannowane i rejestrowane wraz z pełnymi ładunkami (po zastosowaniu redakcji danych osobowych).                                              |   2   |  V   |
| 2.2.5 | Zweryfikuj, czy metryki odporności (wskaźnik sukcesu znanych zestawów ataków) są monitorowane w czasie oraz czy regresje powodują zablokowanie wydania.                                                                 |   3   | D/V  |

---

## C2.3 Walidacja schematu, typu i długości

Ataki AI wykorzystujące niepoprawnie sformatowane lub zbyt duże dane wejściowe mogą powodować błędy parsowania, przenikanie poleceń pomiędzy polami oraz wyczerpanie zasobów. Ścisłe egzekwowanie schematów jest również warunkiem koniecznym przy wykonywaniu deterministycznych wywołań narzędzi.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Zweryfikuj, czy każdy punkt końcowy wywołania API lub funkcji definiuje wyraźny schemat wejściowy (JSON Schema, Protobuf lub multimodalny odpowiednik) oraz czy dane wejściowe są walidowane przed złożeniem promptu. |   1   |  D   |
| 2.3.2 | Zweryfikuj, czy dane wejściowe przekraczające maksymalne limity tokenów lub bajtów są odrzucane z bezpiecznym komunikatem o błędzie i nigdy nie są cicho obcinane.                                                    |   1   | D/V  |
| 2.3.3 | Zweryfikuj, czy weryfikacje typów (np. zakresy liczb, wartości wyliczeń, typy MIME dla obrazów/dźwięku) są egzekwowane po stronie serwera, a nie tylko w kodzie klienta.                                              |   2   | D/V  |
| 2.3.4 | Zweryfikuj, czy walidatory semantyczne (np. JSON Schema) działają w czasie stałym, aby zapobiec algorytmicznemu DoS.                                                                                                  |   2   |  D   |
| 2.3.5 | Zweryfikuj, czy błędy walidacji są rejestrowane z zaciemnionymi fragmentami danych i jednoznacznymi kodami błędów, aby ułatwić proces analizy bezpieczeństwa.                                                         |   3   |  V   |

---

## C2.4 Przesiewanie treści i polityki

Deweloperzy powinni być w stanie wykrywać składniowo poprawne polecenia, które żądają zabronionych treści (takich jak nielegalne instrukcje, mowa nienawiści i teksty chronione prawem autorskim), a następnie zapobiegać ich dalszemu rozpowszechnianiu.

|   #   | Description                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Zweryfikuj, czy klasyfikator treści (zero shot lub dostrojony) ocenia każde wejście pod kątem przemocy, samouszkodzeń, nienawiści, treści seksualnych oraz nielegalnych próśb, z możliwością konfigurowania progów. |   1   |  D   |
| 2.4.2 | Zweryfikuj, czy dane wejściowe naruszające zasady otrzymują ustandaryzowane odmowy lub bezpieczne zakończenia, aby nie były przekazywane do dalszych wywołań modeli LLM.                                            |   1   | D/V  |
| 2.4.3 | Zweryfikuj, czy model przesiewowy lub zestaw reguł są ponownie trenowane/aktualizowane co najmniej raz na kwartał, uwzględniając nowo zaobserwowane wzorce obejścia zabezpieczeń lub polityk.                       |   2   |  D   |
| 2.4.4 | Zweryfikuj, czy selekcja przestrzega polityk specyficznych dla użytkownika (wiek, regionalne ograniczenia prawne) poprzez reguły oparte na atrybutach rozstrzygane w czasie żądania.                                |   2   |  D   |
| 2.4.5 | Zweryfikuj, czy dzienniki przesiewowe zawierają oceny pewności klasyfikatora oraz etykiety kategorii polityki dla korelacji SOC i przyszłego odtwarzania przez zespół czerwony.                                     |   3   |  V   |

---

## C2.5 Ograniczanie szybkości wejściowej i zapobieganie nadużyciom

Programiści powinni zapobiegać nadużyciom, wyczerpywaniu zasobów oraz automatycznym atakom na systemy AI poprzez ograniczanie szybkości wprowadzania danych i wykrywanie anomalnych wzorców użytkowania.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Zweryfikuj, czy limity szybkości dla każdego użytkownika, każdego adresu IP oraz każdego klucza API są egzekwowane dla wszystkich punktów końcowych wejściowych. |   1   | D/V  |
| 2.5.2 | Zweryfikuj, czy limity szybkości impulsowej i utrzymanej są dostosowane w celu zapobiegania atakom DoS i atakom siłowym (brute force).                           |   2   | D/V  |
| 2.5.3 | Zweryfikuj, czy anomalne wzorce użytkowania (np. szybkie, powtarzające się żądania, zalewanie wejścia danymi) wywołują automatyczne blokady lub eskalacje.       |   2   | D/V  |
| 2.5.4 | Zweryfikuj, czy dzienniki zapobiegające nadużyciom są przechowywane i przeglądane pod kątem pojawiających się wzorców ataków.                                    |   3   |  V   |

---

## C2.6 Walidacja wejścia wielomodalnego

Systemy AI powinny zawierać solidną walidację dla danych wejściowych innych niż tekstowe (obrazy, dźwięki, pliki), aby zapobiegać wstrzykiwaniu, unikaniu wykrycia lub nadużyciom zasobów.

|   #   | Description                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Zweryfikuj, czy wszystkie dane wejściowe inne niż tekstowe (obrazy, dźwięki, pliki) są sprawdzane pod kątem typu, rozmiaru i formatu przed przetwarzaniem. |   1   |  D   |
| 2.6.2 | Zweryfikuj, czy pliki są skanowane pod kątem złośliwego oprogramowania i ukrytych ładunków steganograficznych przed ich przetworzeniem.                    |   2   | D/V  |
| 2.6.3 | Zweryfikuj, czy dane wejściowe w postaci obrazów/dźwięku są sprawdzane pod kątem przeciwnych zakłóceń lub znanych wzorców ataków.                          |   2   | D/V  |
| 2.6.4 | Zweryfikuj, czy błędy walidacji danych wejściowych multimodalnych są rejestrowane i powodują generowanie alertów do zbadania.                              |   3   |  V   |

---

## C2.7 Pochodzenie danych wejściowych i przypisanie źródła

Systemy AI powinny wspierać audyt, śledzenie nadużyć i zgodność poprzez monitorowanie oraz oznaczanie źródeł wszystkich danych wejściowych użytkownika.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Zweryfikuj, czy wszystkie dane wejściowe użytkownika są oznaczone metadanymi (ID użytkownika, sesja, źródło, znacznik czasu, adres IP) podczas ich przyjmowania. |   1   | D/V  |
| 2.7.2 | Zweryfikuj, czy metadane pochodzenia są zachowane i możliwe do audytu dla wszystkich przetworzonych danych wejściowych.                                          |   2   | D/V  |
| 2.7.3 | Zweryfikuj, czy anomalne lub niezweryfikowane źródła danych wejściowych są oznaczone i poddawane zwiększonej kontroli lub blokowane.                             |   2   | D/V  |

---

## C2.8 Adaptacyjne wykrywanie zagrożeń w czasie rzeczywistym

Programiści powinni stosować zaawansowane systemy wykrywania zagrożeń dla SI, które dostosowują się do nowych wzorców ataków i zapewniają ochronę w czasie rzeczywistym poprzez skompilowane dopasowywanie wzorców.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Zweryfikuj, czy wzorce wykrywania zagrożeń są kompilowane do zoptymalizowanych silników wyrażeń regularnych w celu zapewnienia wysokowydajnego filtrowania w czasie rzeczywistym przy minimalnym wpływie na opóźnienia.    |   1   | D/V  |
| 2.8.2 | Zweryfikuj, czy systemy wykrywania zagrożeń utrzymują oddzielne biblioteki wzorców dla różnych kategorii zagrożeń (wstrzyknięcie promptu, szkodliwe treści, dane wrażliwe, polecenia systemowe).                           |   1   | D/V  |
| 2.8.3 | Zweryfikuj, czy adaptacyjne wykrywanie zagrożeń wykorzystuje modele uczenia maszynowego, które aktualizują czułość na zagrożenia na podstawie częstotliwości ataków i wskaźników ich skuteczności.                         |   2   | D/V  |
| 2.8.4 | Zweryfikuj, czy strumienie informacji o zagrożeniach w czasie rzeczywistym automatycznie aktualizują biblioteki wzorców o nowe sygnatury ataków i IOC (wskaźniki naruszenia).                                              |   2   | D/V  |
| 2.8.5 | Zweryfikuj, czy wskaźniki fałszywie pozytywnych wyników wykrywania zagrożeń są stale monitorowane, a specyficzność wzorców jest automatycznie dostrajana w celu minimalizacji zakłóceń w autentycznych przypadkach użycia. |   3   | D/V  |
| 2.8.6 | Zweryfikuj, czy analiza zagrożeń kontekstowych uwzględnia źródło wejścia, wzorce zachowań użytkownika oraz historię sesji w celu poprawy dokładności wykrywania.                                                           |   3   | D/V  |
| 2.8.7 | Zweryfikuj, czy metryki wydajności wykrywania zagrożeń (wskaźnik wykrywalności, opóźnienie przetwarzania, wykorzystanie zasobów) są monitorowane i optymalizowane w czasie rzeczywistym.                                   |   3   | D/V  |

---

## C2.9 Wielomodalny Pipeline Weryfikacji Bezpieczeństwa

Programiści powinni zapewnić weryfikację bezpieczeństwa dla tekstu, obrazu, dźwięku oraz innych modalności wejściowych AI za pomocą specyficznych typów wykrywania zagrożeń i izolacji zasobów.

|   #   | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Zweryfikuj, czy każda modalność wejściowa ma dedykowanych walidatorów bezpieczeństwa z udokumentowanymi wzorcami zagrożeń (tekst: wstrzykiwanie poleceń, obrazy: steganografia, dźwięk: ataki na spektrogram) oraz ustalonymi progami wykrywania.                             |   1   | D/V  |
| 2.9.2 | Zweryfikuj, czy wielomodalne dane wejściowe są przetwarzane w izolowanych piaskownicach z określonymi limitami zasobów (pamięć, CPU, czas przetwarzania) specyficznymi dla każdego typu modalności i udokumentowanymi w politykach bezpieczeństwa.                            |   2   | D/V  |
| 2.9.3 | Zweryfikuj, czy wykrywanie ataków krzyżowo-modalnych identyfikuje skoordynowane ataki obejmujące różne typy danych wejściowych (np. ukryte ładunki steganograficzne w obrazach połączone z wstrzyknięciem poleceń w tekście) za pomocą reguł korelacji i generowania alertów. |   2   | D/V  |
| 2.9.4 | Zweryfikuj, czy niepowodzenia walidacji wielomodalnej wywołują szczegółowe logowanie obejmujące wszystkie modalności wejściowe, wyniki walidacji, oceny zagrożeń oraz analizę korelacji ze zorganizowanymi formatami logów do integracji z SIEM.                              |   3   | D/V  |
| 2.9.5 | Zweryfikuj, czy specyficzne dla modalności klasyfikatory treści są aktualizowane zgodnie z udokumentowanymi harmonogramami (minimum kwartalnie) o nowe wzorce zagrożeń, przykłady adwersarialne oraz czy wskaźniki wydajności utrzymują się powyżej progów bazowych.          |   3   | D/V  |

---

## Bibliografia

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

