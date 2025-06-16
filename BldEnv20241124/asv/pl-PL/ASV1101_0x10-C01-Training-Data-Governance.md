# Zarządzanie danymi treningowymi C1 oraz zarządzanie uprzedzeniami

## Cel kontroli

Dane treningowe muszą być pozyskiwane, przetwarzane i przechowywane w sposób zachowujący ich pochodzenie, bezpieczeństwo, jakość oraz sprawiedliwość. Postępowanie w ten sposób wypełnia obowiązki prawne i zmniejsza ryzyko stronniczości, zatrucia danych lub naruszeń prywatności przez cały cykl życia sztucznej inteligencji.

---

## C1.1 Pochodzenie danych treningowych

Utrzymuj weryfikowalny rejestr wszystkich zbiorów danych, akceptuj wyłącznie zaufane źródła i rejestruj każdą zmianę dla celów audytu.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Zweryfikuj, czy jest prowadzona aktualna inwentaryzacja każdego źródła danych treningowych (pochodzenie, opiekun/właściciel, licencja, metoda zbierania, ograniczenia dotyczące zamierzonego zastosowania oraz historia przetwarzania).                                                       |   1   | D/V  |
| 1.1.2 | Sprawdź, czy dozwolone są tylko zbiory danych sprawdzone pod kątem jakości, reprezentatywności, etycznego pozyskiwania oraz zgodności z licencją, co zmniejsza ryzyko zatrucia danych, wbudowanych uprzedzeń i naruszenia własności intelektualnej.                                           |   1   | D/V  |
| 1.1.3 | Zweryfikuj, czy minimalizacja danych jest egzekwowana, aby wykluczyć niepotrzebne lub wrażliwe atrybuty.                                                                                                                                                                                      |   1   | D/V  |
| 1.1.4 | Zweryfikuj, czy wszystkie zmiany w zbiorze danych podlegają zatwierdzonemu procesowi zatwierdzania z rejestrowaniem.                                                                                                                                                                          |   2   | D/V  |
| 1.1.5 | Zweryfikuj, czy jakość etykietowania/anonimowania jest zapewniona poprzez wzajemne kontrole recenzentów lub konsensus.                                                                                                                                                                        |   2   | D/V  |
| 1.1.6 | Zweryfikuj, czy dla istotnych zbiorów danych treningowych są prowadzone „karty danych” lub „karty charakterystyki zbiorów danych”, zawierające szczegółowe informacje o cechach, motywacjach, składzie, procesach zbierania, przetwarzaniu wstępnym oraz zalecanym/niezalecanym zastosowaniu. |   2   | D/V  |

---

## C1.2 Bezpieczeństwo i integralność danych treningowych

Ogranicz dostęp, szyfruj dane w stanie spoczynku i w trakcie przesyłania oraz weryfikuj integralność, aby zapobiec manipulacjom lub kradzieży.

|   #   | Description                                                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Zweryfikuj, czy kontrola dostępu chroni pamięć i potoki.                                                                                                                                                                                                                                                                                    |   1   | D/V  |
| 1.2.2 | Zweryfikuj, czy zestawy danych są szyfrowane podczas przesyłania oraz, dla wszystkich wrażliwych lub zawierających dane osobowe (PII), również podczas przechowywania, z wykorzystaniem standardowych w branży algorytmów kryptograficznych i praktyk zarządzania kluczami.                                                                 |   2   | D/V  |
| 1.2.3 | Zweryfikuj, czy do zapewnienia integralności danych podczas przechowywania i przesyłania używane są hasze kryptograficzne lub podpisy cyfrowe, oraz czy stosowane są zautomatyzowane techniki wykrywania anomalii w celu ochrony przed nieautoryzowanymi modyfikacjami lub uszkodzeniami, w tym przed celowanymi próbami zatruwania danych. |   2   | D/V  |
| 1.2.4 | Zweryfikuj, czy wersje zestawów danych są śledzone, aby umożliwić przywracanie poprzednich wersji.                                                                                                                                                                                                                                          |   3   | D/V  |
| 1.2.5 | Zweryfikuj, czy przestarzałe dane są bezpiecznie usuwane lub anonimizowane zgodnie z politykami przechowywania danych, wymogami regulacyjnymi oraz w celu zmniejszenia powierzchni ataku.                                                                                                                                                   |   2   | D/V  |

---

## C1.3 Kompletność reprezentacji i sprawiedliwość

Wykrywaj przekłamania demograficzne i stosuj metody łagodzące, aby wskaźniki błędów modelu były równe dla wszystkich grup.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Zweryfikuj, czy zbiory danych zostały poddane profilowaniu pod kątem nierównowagi reprezentacyjnej oraz potencjalnych uprzedzeń dotyczących prawnie chronionych atrybutów (np. rasa, płeć, wiek) oraz innych etycznie wrażliwych cech istotnych dla domeny zastosowania modelu (np. status społeczno-ekonomiczny, lokalizacja).                                                                     |   1   | D/V  |
| 1.3.2 | Zweryfikuj, czy zidentyfikowane uprzedzenia są łagodzone za pomocą udokumentowanych strategii, takich jak wyrównywanie, ukierunkowana augmentacja danych, dostosowania algorytmiczne (np. techniki wstępnego przetwarzania, przetwarzania w trakcie działania, przetwarzania końcowego) lub ponowne ważenie, oraz czy oceniany jest wpływ tych działań na sprawiedliwość i ogólną wydajność modelu. |   2   | D/V  |
| 1.3.3 | Zweryfikuj, czy metryki sprawiedliwości po trenowaniu są oceniane i dokumentowane.                                                                                                                                                                                                                                                                                                                  |   2   | D/V  |
| 1.3.4 | Zweryfikuj, czy polityka zarządzania uprzedzeniami w cyklu życia przypisuje właścicieli oraz określa częstotliwość przeglądów.                                                                                                                                                                                                                                                                      |   3   | D/V  |

---

## C1.4 Jakość, integralność i bezpieczeństwo oznaczania danych treningowych

Chroń etykiety za pomocą szyfrowania i wymuszaj podwójną weryfikację dla krytycznych klas.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Potwierdź, że jakość oznaczania/annotacji jest zapewniona poprzez jasne wytyczne, wzajemne kontrole recenzentów, mechanizmy konsensusu (np. monitorowanie zgodności między anotatorami) oraz określone procesy rozwiązywania niezgodności.                                          |   2   | D/V  |
| 1.4.2 | Zweryfikuj, czy do artefaktów etykiet stosowane są kryptograficzne skróty lub podpisy cyfrowe, aby zapewnić ich integralność i autentyczność.                                                                                                                                       |   2   | D/V  |
| 1.4.3 | Zweryfikuj, czy interfejsy i platformy do etykietowania egzekwują silne mechanizmy kontroli dostępu, utrzymują niezaprzeczalne, zabezpieczone przed manipulacją dzienniki audytu wszystkich działań związanych z etykietowaniem oraz chronią przed nieautoryzowanymi modyfikacjami. |   2   | D/V  |
| 1.4.4 | Zweryfikuj, czy etykiety krytyczne dla bezpieczeństwa, ochrony lub sprawiedliwości (np. identyfikujące toksyczne treści, istotne wyniki medyczne) podlegają obowiązkowej niezależnej podwójnej weryfikacji lub równoważnej solidnej weryfikacji.                                    |   3   | D/V  |
| 1.4.5 | Zweryfikuj, czy informacje wrażliwe (w tym dane osobowe) przypadkowo przechwycone lub niezbędnie obecne w etykietach są zredagowane, pseudonimizowane, anonimowe lub szyfrowane w stanie spoczynku i podczas przesyłania, zgodnie z zasadami minimalizacji danych.                  |   2   | D/V  |
| 1.4.6 | Zweryfikuj, czy instrukcje i wytyczne dotyczące oznaczania są kompleksowe, kontrolowane pod względem wersji oraz poddane przeglądowi przez rówieśników.                                                                                                                             |   2   | D/V  |
| 1.4.7 | Sprawdź, czy schematy danych (w tym dla etykiet) są wyraźnie zdefiniowane i kontrolowane pod względem wersji.                                                                                                                                                                       |   2   | D/V  |
| 1.8.2 | Zweryfikuj, czy zlecone na zewnątrz lub oparte na crowdsourcingu procesy etykietowania zawierają techniczne/proceduralne zabezpieczenia zapewniające poufność danych, integralność, jakość etykiet oraz zapobiegające wyciekowi danych.                                             |   2   | D/V  |

---

## C1.5 Zapewnienie jakości danych treningowych

Połącz automatyczną walidację, ręczne losowe kontrole oraz rejestrowane działania naprawcze, aby zagwarantować niezawodność zestawu danych.

|   #   | Description                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Zweryfikuj, czy automatyczne testy wykrywają błędy formatowania, wartości null oraz przesunięcia etykiet przy każdym załadunku danych lub istotnej transformacji.                                                                                                                                                 |   1   |  D   |
| 1.5.2 | Zweryfikuj, czy nieudane zestawy danych są kwarantannowane wraz ze ścieżkami audytu.                                                                                                                                                                                                                              |   1   | D/V  |
| 1.5.3 | Zweryfikuj, czy ręczne kontrole losowe przeprowadzane przez ekspertów dziedzinowych obejmują statystycznie istotną próbę (np. ≥1% lub 1 000 próbek, w zależności od tego, która wartość jest większa, lub zgodnie z oceną ryzyka), aby wykryć subtelne problemy jakościowe, których nie wychwyciła automatyzacja. |   2   |  V   |
| 1.5.4 | Zweryfikuj, czy kroki naprawcze zostały dodane do rekordów pochodzenia.                                                                                                                                                                                                                                           |   2   | D/V  |
| 1.5.5 | Zweryfikuj, czy bramki jakości blokują dane o niskiej jakości, chyba że zatwierdzono wyjątki.                                                                                                                                                                                                                     |   2   | D/V  |

---

## C1.6 Wykrywanie zatruwania danych

Zastosuj statystyczne wykrywanie anomalii oraz procedury kwarantanny, aby zatrzymać przeciwnicze wtrącenia.

|   #   | Description                                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Zweryfikuj, czy techniki wykrywania anomalii (np. metody statystyczne, wykrywanie wartości odstających, analiza osadzeń) są stosowane do danych treningowych podczas ich wczytywania oraz przed głównymi sesjami treningowymi, aby zidentyfikować potencjalne ataki polegające na zatruwaniu danych lub przypadkową ich degradację. |   2   | D/V  |
| 1.6.2 | Zweryfikuj, czy oznaczone próbki wywołują ręczną kontrolę przed treningiem.                                                                                                                                                                                                                                                         |   2   | D/V  |
| 1.6.3 | Zweryfikuj, czy wyniki zasilają dossier bezpieczeństwa modelu i informują o bieżącej inteligencji zagrożeń.                                                                                                                                                                                                                         |   2   |  V   |
| 1.6.4 | Zweryfikuj, czy logika wykrywania jest aktualizowana o nowe informacje wywiadu zagrożeń.                                                                                                                                                                                                                                            |   3   | D/V  |
| 1.6.5 | Zweryfikuj, czy potoki uczenia online monitorują dryf dystrybucji.                                                                                                                                                                                                                                                                  |   3   | D/V  |
| 1.6.6 | Zweryfikuj, czy konkretne mechanizmy obronne przeciw znanym typom ataków zatruwania danych (np. odwracanie etykiet, wstawianie wyzwalaczy tylnego wejścia, ataki na wpływowe przykłady) zostały uwzględnione i wdrożone na podstawie profilu ryzyka systemu oraz źródeł danych.                                                     |   3   | D/V  |

---

## C1.7 Usuwanie danych użytkownika i egzekwowanie zgody

Szanuj prośby o usunięcie oraz wycofanie zgody w całych zbiorach danych, kopiach zapasowych i wytworzonych artefaktach.

|   #   | Description                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.7.1 | Zweryfikuj, czy procesy usuwania danych usuwają dane podstawowe i pochodne oraz ocenić wpływ na modele, a także czy wpływ na dotknięte modele jest oceniany i w razie potrzeby uwzględniany (np. poprzez ponowne trenowanie lub rekalkibrację).                                                        |   1   | D/V  |
| 1.7.2 | Zweryfikuj, czy istnieją mechanizmy umożliwiające śledzenie i poszanowanie zakresu oraz statusu zgody użytkownika (oraz jej wycofania) na dane wykorzystywane do treningu, oraz czy zgoda jest zatwierdzana przed włączeniem danych do nowych procesów treningowych lub istotnych aktualizacji modelu. |   2   |  D   |
| 1.7.3 | Zweryfikuj, czy przepływy pracy są testowane corocznie i rejestrowane.                                                                                                                                                                                                                                 |   2   |  V   |

---

## C1.8 Bezpieczeństwo łańcucha dostaw

Zweryfikuj zewnętrznych dostawców danych i sprawdź integralność za pośrednictwem uwierzytelnionych, szyfrowanych kanałów.

|   #   | Description                                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Zweryfikuj, czy dostawcy danych zewnętrznych, w tym dostawcy modeli wstępnie wytrenowanych oraz zewnętrznych zbiorów danych, przechodzą proces due diligence pod kątem bezpieczeństwa, prywatności, etycznego pozyskiwania oraz jakości danych, zanim ich dane lub modele zostaną zintegrowane.                                 |   2   | D/V  |
| 1.8.2 | Zweryfikuj, czy zewnętrzne transfery korzystają z TLS/uwierzytelniania oraz mechanizmów kontroli integralności.                                                                                                                                                                                                                 |   1   |  D   |
| 1.8.3 | Zweryfikuj, czy źródła danych wysokiego ryzyka (np. otwarte zestawy danych o nieznanym pochodzeniu, nieweryfikowani dostawcy) są poddawane zwiększonej kontroli, takiej jak analiza w piaskownicy, szczegółowe kontrole jakości i uprzedzeń oraz ukierunkowane wykrywanie zatruć, przed zastosowaniem w wrażliwych aplikacjach. |   2   | D/V  |
| 1.8.4 | Zweryfikuj, czy modele wstępnie wytrenowane pochodzące od stron trzecich są oceniane pod kątem wbudowanych uprzedzeń, potencjalnych backdoorów, integralności ich architektury oraz pochodzenia ich oryginalnych danych treningowych przed dostrojeniem lub wdrożeniem.                                                         |   3   | D/V  |

---

## C1.9 Wykrywanie próbek adwersarialnych

Wprowadź środki podczas fazy treningowej, takie jak trening przeciwnika, aby zwiększyć odporność modelu na przykłady przeciwnika.

|   #   | Description                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Zweryfikuj, czy odpowiednie zabezpieczenia, takie jak trening przeciwny (wykorzystujący wygenerowane przykłady przeciwnika), augmentacja danych z zakłóconymi danymi wejściowymi lub techniki optymalizacji odpornej, są wdrożone i dostosowane do odpowiednich modeli na podstawie oceny ryzyka. |   3   | D/V  |
| 1.9.2 | Zweryfikuj, czy w przypadku stosowania treningu adwersarialnego generowanie, zarządzanie oraz wersjonowanie zbiorów danych adwersarialnych są dokumentowane i kontrolowane.                                                                                                                       |   2   | D/V  |
| 1.9.3 | Zweryfikuj, czy wpływ treningu odporności na ataki przeciwne na wydajność modelu (zarówno na dane czyste, jak i przeciwnikowe) oraz na metryki sprawiedliwości jest oceniany, dokumentowany i monitorowany.                                                                                       |   3   | D/V  |
| 1.9.4 | Zweryfikuj, czy strategie dotyczące treningu przeciwnika (adversarial training) oraz odporności są okresowo przeglądane i aktualizowane, aby przeciwdziałać rozwijającym się technikom ataków przeciwnika.                                                                                        |   3   | D/V  |

---

## C1.10 Pochodzenie danych i możliwość ich śledzenia

Śledź pełną drogę każdego punktu danych od źródła do wejścia modelu w celu umożliwienia audytu i reakcji na incydenty.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Zweryfikuj, czy pochodzenie każdego punktu danych, włącznie ze wszystkimi transformacjami, augmentacjami i scaleniami, jest zapisane i można je odtworzyć. |   2   | D/V  |
| 1.10.2 | Zweryfikuj, czy zapisy pochodzenia są niezmienne, bezpiecznie przechowywane i dostępne do audytów lub dochodzeń.                                           |   2   | D/V  |
| 1.10.3 | Zweryfikuj, czy śledzenie pochodzenia obejmuje zarówno dane surowe, jak i syntetyczne.                                                                     |   2   | D/V  |

---

## C1.11 Zarządzanie Danymi Syntetycznymi

Zapewnij właściwe zarządzanie, etykietowanie i ocenę ryzyka danych syntetycznych.

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Zweryfikuj, czy wszystkie dane syntetyczne są wyraźnie oznaczone i możliwe do odróżnienia od danych rzeczywistych w całym procesie przetwarzania.                     |   2   | D/V  |
| 1.11.2 | Zweryfikuj, czy proces generowania, parametry oraz zamierzone zastosowanie danych syntetycznych są udokumentowane.                                                    |   2   | D/V  |
| 1.11.3 | Zweryfikuj, czy dane syntetyczne zostały poddane ocenie ryzyka pod kątem uprzedzeń, wycieku prywatności oraz problemów z reprezentacją przed ich użyciem do treningu. |   2   | D/V  |

---

## C1.12 Monitorowanie Dostępu do Danych i Wykrywanie Anomalii

Monitoruj i generuj alerty dotyczące nietypowego dostępu do danych treningowych, aby wykrywać zagrożenia wewnętrzne lub wyciek danych.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Zweryfikuj, czy wszystkie dostępy do danych treningowych są rejestrowane, w tym użytkownik, czas i działanie.                                              |   2   | D/V  |
| 1.12.2 | Zweryfikuj, czy logi dostępu są regularnie przeglądane pod kątem nieprawidłowych wzorców, takich jak duże eksporty danych lub dostęp z nowych lokalizacji. |   2   | D/V  |
| 1.12.3 | Zweryfikuj, czy alerty są generowane dla podejrzanych zdarzeń dostępu i czy są one niezwłocznie badane.                                                    |   2   | D/V  |

---

## C1.13 Polityki Retencji i Wygasania Danych

Zdefiniuj i egzekwuj okresy przechowywania danych, aby zminimalizować niepotrzebne przechowywanie danych.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Zweryfikuj, czy dla wszystkich zestawów danych treningowych zdefiniowano wyraźne okresy przechowywania.                                       |   1   | D/V  |
| 1.13.2 | Zweryfikuj, czy zestawy danych są automatycznie wygaszane, usuwane lub poddawane przeglądowi w celu usunięcia po zakończeniu ich cyklu życia. |   2   | D/V  |
| 1.13.3 | Zweryfikuj, czy działania dotyczące przechowywania i usuwania są rejestrowane i mogą być poddane audytowi.                                    |   2   | D/V  |

---

## C1.14 Zgodność regulacyjna i jurysdykcyjna

Zapewnij, że wszystkie dane treningowe są zgodne z obowiązującymi przepisami prawa i regulacjami.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Zweryfikuj, czy wymagania dotyczące lokalizacji danych oraz transferu transgranicznego są zidentyfikowane i egzekwowane dla wszystkich zestawów danych. |   2   | D/V  |
| 1.14.2 | Zweryfikuj, czy specyficzne dla sektora regulacje (np. opieka zdrowotna, finanse) zostały zidentyfikowane i uwzględnione w przetwarzaniu danych.        |   2   | D/V  |
| 1.14.3 | Zweryfikuj, czy zgodność z odpowiednimi przepisami o ochronie prywatności (np. RODO, CCPA) jest dokumentowana i regularnie przeglądana.                 |   2   | D/V  |

---

## C1.15 Znakowanie wodne danych i identyfikacja źródła danych

Wykrywaj nieautoryzowane ponowne użycie lub wyciek danych poufnych lub wrażliwych.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Zweryfikuj, czy zestawy danych lub ich podzbiory są znakowane wodnym lub zaopatrzone w odciski palców tam, gdzie to możliwe.                          |   3   | D/V  |
| 1.15.2 | Zweryfikuj, czy metody znakowania wodnego/fingerprintingu nie wprowadzają stronniczości ani ryzyka naruszenia prywatności.                            |   3   | D/V  |
| 1.15.3 | Zweryfikuj, czy przeprowadzane są okresowe kontrole w celu wykrycia nieautoryzowanego ponownego użycia lub wycieku danych oznaczonych znakiem wodnym. |   3   | D/V  |

---

## C1.16 Zarządzanie prawami osób, których dane dotyczą

Wspieraj prawa podmiotów danych, takie jak dostęp, sprostowanie, ograniczenie i sprzeciw.

|   #    | Description                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.16.1 | Zweryfikuj, czy istnieją mechanizmy umożliwiające reagowanie na wnioski osób, których dane dotyczą, dotyczące dostępu, sprostowania, ograniczenia przetwarzania lub sprzeciwu. |   2   | D/V  |
| 1.16.2 | Zweryfikuj, czy żądania są rejestrowane, śledzone i realizowane w obowiązujących prawnie terminach.                                                                            |   2   | D/V  |
| 1.16.3 | Zweryfikuj, czy procesy związane z prawami osób, których dane dotyczą, są regularnie testowane i oceniane pod kątem skuteczności.                                              |   2   | D/V  |

---

## C1.17 Analiza wpływu wersji zestawu danych

Oceń wpływ zmian w zbiorze danych przed aktualizacją lub wymianą wersji.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.17.1 | Zweryfikuj, czy przed aktualizacją lub zastąpieniem wersji zestawu danych przeprowadzana jest analiza wpływu, obejmująca wydajność modelu, sprawiedliwość oraz zgodność. |   2   | D/V  |
| 1.17.2 | Zweryfikuj, czy wyniki analizy wpływu są udokumentowane i przejrzane przez odpowiednich interesariuszy.                                                                  |   2   | D/V  |
| 1.17.3 | Zweryfikuj, czy istnieją plany wycofania zmian na wypadek, gdyby nowe wersje wprowadziły niedopuszczalne ryzyko lub regresje.                                            |   2   | D/V  |

---

## C1.18 Bezpieczeństwo zespołu zajmującego się adnotacją danych

Zapewnij bezpieczeństwo i integralność personelu zaangażowanego w adnotację danych.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Zweryfikuj, czy wszyscy pracownicy zaangażowani w adnotację danych zostali poddani weryfikacji przeszłości oraz przeszkoleni w zakresie bezpieczeństwa danych i prywatności. |   2   | D/V  |
| 1.18.2 | Zweryfikuj, czy wszyscy pracownicy zajmujący się anotacją podpisali umowy o zachowaniu poufności i o nieujawnianiu informacji.                                               |   2   | D/V  |
| 1.18.3 | Zweryfikuj, czy platformy do adnotacji wymuszają kontrolę dostępu i monitorują zagrożenia wewnętrzne.                                                                        |   2   | D/V  |

---

## Bibliografia

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

