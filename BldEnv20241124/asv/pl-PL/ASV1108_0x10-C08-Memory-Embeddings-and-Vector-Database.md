# Bezpieczeństwo Pamięci C8, Osadzeń i Baz Wektorowych

## Cel Kontrolny

Osadzenia i magazyny wektorowe działają jako „czynna pamięć” współczesnych systemów AI, nieustannie przyjmując dane dostarczane przez użytkowników i udostępniając je z powrotem w kontekstach modelu za pomocą Generacji Wzbogaconej Wyszukiwaniem (RAG). Jeśli pozostaną bez nadzoru, ta pamięć może ujawnić dane osobowe (PII), naruszyć zgodę lub zostać odwrócona w celu rekonstrukcji oryginalnego tekstu. Celem tej rodziny kontroli jest wzmocnienie kanałów pamięci i baz danych wektorowych tak, aby dostęp był zgodny z zasadą najmniejszych uprawnień, osadzenia zachowywały prywatność, przechowywane wektory wygasały lub mogły być unieważniane na żądanie, a pamięć przypisana do konkretnego użytkownika nigdy nie zanieczyszczała poleceń lub wyników innego użytkownika.

---

## C8.1 Kontrole dostępu do pamięci i indeksów RAG

Wymuszaj szczegółowe kontrole dostępu na każdej kolekcji wektorów.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Zweryfikuj, czy reguły kontroli dostępu na poziomie wiersza/przestrzeni nazw ograniczają operacje wstawiania, usuwania i zapytań zgodnie z najemcą, kolekcją lub tagiem dokumentu. |   1   | D/V  |
| 8.1.2 | Zweryfikuj, czy klucze API lub tokeny JWT zawierają przypisane zakresy uprawnień (np. identyfikatory kolekcji, czasowniki akcji) oraz czy są rotowane przynajmniej co kwartał.     |   1   | D/V  |
| 8.1.3 | Zweryfikuj, czy próby eskalacji uprawnień (np. zapytania o podobieństwo między przestrzeniami nazw) są wykrywane i rejestrowane w systemie SIEM w ciągu 5 minut.                   |   2   | D/V  |
| 8.1.4 | Zweryfikuj, czy baza danych wektorów rejestruje w dzienniku identyfikator podmiotu, operację, identyfikator wektora/przestrzeń nazw, próg podobieństwa oraz liczbę wyników.        |   2   | D/V  |
| 8.1.5 | Zweryfikuj, czy decyzje dotyczące dostępu są testowane pod kątem luk w obejściu za każdym razem, gdy silniki są aktualizowane lub zmieniają się zasady dzielenia indeksów.         |   3   |  V   |

---

## C8.2 Sanitizacja i Walidacja Osadzania

Przeprowadź wstępną kontrolę tekstu pod kątem danych osobowych (PII), zanonimizuj lub pseudonimizuj je przed wektoryzacją, a opcjonalnie dokonaj postprocessingu osadzonych reprezentacji, aby usunąć pozostałe sygnały.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Zweryfikuj, czy dane PII i dane regulowane są wykrywane za pomocą zautomatyzowanych klasyfikatorów oraz czy są maskowane, tokenizowane lub usuwane przed osadzaniem.                            |   1   | D/V  |
| 8.2.2 | Sprawdź, czy potoki osadzania odrzucają lub izolują dane wejściowe zawierające kod wykonywalny lub artefakty niekodujące się w UTF-8, które mogłyby zatruć indeks.                              |   1   |  D   |
| 8.2.3 | Zweryfikuj, czy do osadzonych zdań, których odległość od dowolnego znanego tokena PII spada poniżej konfigurowalnego progu, zastosowano lokalne lub metryczne różnicowe maskowanie prywatności. |   2   | D/V  |
| 8.2.4 | Zweryfikuj, czy skuteczność sanitacji (np. recall usuwania danych osobowych, dryf semantyczny) jest weryfikowana co najmniej półrocznie na podstawie korpusów referencyjnych.                   |   2   |  V   |
| 8.2.5 | Zweryfikuj, czy konfiguracje sanitizacji są kontrolowane wersjami, a zmiany podlegają przeglądowi przez rówieśników.                                                                            |   3   | D/V  |

---

## C8.3 Wygasanie pamięci, unieważnianie i usuwanie

RODO ("prawo do bycia zapomnianym") oraz podobne przepisy wymagają terminowego usuwania danych; magazyny wektorów muszą więc obsługiwać TTL, trwałe usuwanie oraz mechanizmy tomb-stoning, aby odebrane wektory nie mogły zostać odzyskane ani ponownie zindeksowane.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.3.1 | Zweryfikuj, czy każdy rekord wektora i metadanych posiada czas życia (TTL) lub wyraźną etykietę retencji honorowaną przez zautomatyzowane zadania czyszczenia.           |   1   | D/V  |
| 8.3.2 | Zweryfikuj, czy żądania usunięcia inicjowane przez użytkownika usuwają wektory, metadane, kopie w pamięci podręcznej oraz indeksy pochodne w ciągu 30 dni.               |   1   | D/V  |
| 8.3.3 | Sprawdź, czy logiczne usunięcia są następowane przez kryptograficzne niszczenie bloków pamięci, jeśli sprzęt to obsługuje, lub przez zniszczenie klucza w sejfie kluczy. |   2   |  D   |
| 8.3.4 | Zweryfikuj, czy wektory wygasłe są wykluczone z wyników wyszukiwania najbliższych sąsiadów w czasie krótszym niż 500 ms po wygaśnięciu.                                  |   3   | D/V  |

---

## C8.4 Zapobieganie inwersji i wyciekowi osadzania

Najnowsze metody obrony — nakładanie szumu, sieci projekcyjne, perturbacja neuronów prywatności oraz szyfrowanie na poziomie warstwy aplikacji — mogą obniżyć wskaźniki odwrócenia tokenów poniżej 5%.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Zweryfikuj, czy istnieje formalny model zagrożeń obejmujący ataki inwersyjne, ataki na członkostwo oraz ataki inferencji atrybutów, który jest przeglądany corocznie.                 |   1   |  V   |
| 8.4.2 | Zweryfikuj, czy szyfrowanie na warstwie aplikacji lub szyfrowanie przeszukiwalne chroni wektory przed bezpośrednim odczytem przez administratorów infrastruktury lub personel chmury. |   2   | D/V  |
| 8.4.3 | Zweryfikuj, czy parametry ochrony (ε dla DP, szum σ, rząd rzutowania k) zapewniają równowagę między prywatnością ≥ 99% ochroną tokenów a użytecznością ≤ 3% spadkiem dokładności.     |   3   |  V   |
| 8.4.4 | Zweryfikuj, czy metryki odporności na inwersję są częścią progów zatwierdzających aktualizacje modelu, z określonymi budżetami regresji.                                              |   3   | D/V  |

---

## C8.5 Egzekwowanie zakresu dla pamięci specyficznej dla użytkownika

Przecieki między najemcami pozostają głównym ryzykiem związanym z RAG: niewłaściwie filtrowane zapytania o podobieństwo mogą ujawnić prywatne dokumenty innego klienta.

|   #   | Description                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.5.1 | Zweryfikuj, czy każde zapytanie pobierania jest filtrowane po identyfikatorze najemcy/użytkownika przed przekazaniem do promptu LLM.                                           |   1   | D/V  |
| 8.5.2 | Zweryfikuj, czy nazwy kolekcji lub identyfikatory z przestrzenią nazw są solone dla każdego użytkownika lub najemcy, aby wektory nie mogły się pokrywać między zakresami.      |   1   |  D   |
| 8.5.3 | Zweryfikuj, czy wyniki podobieństwa powyżej konfigurowalnego progu odległości, ale poza zakresem wywołującego, są odrzucane i wywołują alerty bezpieczeństwa.                  |   2   | D/V  |
| 8.5.4 | Zweryfikuj, czy testy obciążeniowe wielodostępne symulują zapytania przeciwnika próbującego uzyskać dostęp do dokumentów poza zakresem oraz czy wykazują brak wycieków danych. |   2   |  V   |
| 8.5.5 | Zweryfikuj, czy klucze szyfrujące są segregowane dla każdego najemcy, zapewniając izolację kryptograficzną nawet w przypadku współdzielenia fizycznego magazynu.               |   3   | D/V  |

---

## C8.6 Zaawansowane zabezpieczenia systemu pamięci

Kontrole bezpieczeństwa dla zaawansowanych architektur pamięci, w tym pamięci epizodycznej, semantycznej i roboczej, z określonymi wymaganiami dotyczącymi izolacji i walidacji.

|   #   | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Zweryfikuj, czy różne typy pamięci (epizodyczna, semantyczna, robocza) mają izolowane konteksty bezpieczeństwa z kontrolą dostępu opartą na rolach, oddzielnymi kluczami szyfrowania oraz udokumentowanymi wzorcami dostępu dla każdego typu pamięci.                         |   1   | D/V  |
| 8.6.2 | Zweryfikuj, czy procesy konsolidacji pamięci obejmują walidację bezpieczeństwa, aby zapobiec wstrzyknięciu złośliwych wspomnień poprzez sanitację treści, weryfikację źródła oraz kontrole integralności przed zapisaniem.                                                    |   2   | D/V  |
| 8.6.3 | Zweryfikuj, czy zapytania dotyczące odzyskiwania pamięci są weryfikowane i oczyszczane, aby zapobiec wydobywaniu nieautoryzowanych informacji poprzez analizę wzorców zapytań, egzekwowanie kontroli dostępu oraz filtrowanie wyników.                                        |   2   | D/V  |
| 8.6.4 | Zweryfikuj, czy mechanizmy zapominania w pamięci bezpiecznie usuwają wrażliwe informacje, zapewniając kryptograficzne gwarancje wymazania poprzez usunięcie klucza, wielokrotne nadpisywanie lub sprzętowe bezpieczne usuwanie z certyfikatami weryfikacji.                   |   3   | D/V  |
| 8.6.5 | Sprawdź, czy integralność systemu pamięci jest nieprzerwanie monitorowana pod kątem nieautoryzowanych modyfikacji lub uszkodzeń za pomocą sum kontrolnych, dzienników audytu oraz automatycznych powiadomień w przypadku zmian zawartości pamięci poza normalnymi operacjami. |   3   | D/V  |

---

## Bibliografia

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

