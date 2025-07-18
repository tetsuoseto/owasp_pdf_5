## Frontyspis

### O standardzie

Standard Weryfikacji Bezpieczeństwa Sztucznej Inteligencji (AISVS) to społecznościowy katalog wymagań bezpieczeństwa, z którego mogą korzystać naukowcy danych, inżynierowie MLOps, architekci oprogramowania, programiści, testerzy, specjaliści ds. bezpieczeństwa, dostawcy narzędzi, regulatorzy i użytkownicy do projektowania, budowy, testowania oraz weryfikacji godnych zaufania systemów i aplikacji opartych na sztucznej inteligencji. Zapewnia on wspólny język do określania zabezpieczeń w całym cyklu życia AI — od zbierania danych i rozwijania modeli, po wdrożenie i bieżący monitoring — dzięki czemu organizacje mogą mierzyć i poprawiać odporność, prywatność oraz bezpieczeństwo swoich rozwiązań AI.

### Prawa autorskie i licencja

Wersja 0.1 (Pierwszy publiczny szkic – prace w toku), 2025  

![license](images/license.png)
Prawa autorskie © 2025 Projekt AISVS.  

Wydane na podstawieCreative Commons Attribution‑ShareAlike 4.0 International License.
W przypadku ponownego użycia lub dystrybucji, musisz jasno przekazać innym warunki licencji tego dzieła.

### Kierownicy projektu

Jim Manico
Aras „Russ” Memisyazici

### Współautorzy i Recenzenci

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS to zupełnie nowy standard stworzony specjalnie w celu rozwiązania unikalnych wyzwań związanych z bezpieczeństwem systemów sztucznej inteligencji. Chociaż czerpie inspirację z ogólnych najlepszych praktyk bezpieczeństwa, każdy wymóg w AISVS został opracowany od podstaw, aby odzwierciedlać krajobraz zagrożeń AI i pomagać organizacjom w tworzeniu bezpieczniejszych, bardziej odpornych rozwiązań AI.

## Przedmowa

Witamy w standardzie weryfikacji bezpieczeństwa sztucznej inteligencji (AISVS) wersja 1.0!

### Wprowadzenie

Ustanowiona w 2025 roku dzięki wspólnemu wysiłkowi społeczności, AISVS definiuje wymagania dotyczące bezpieczeństwa, które należy uwzględnić podczas projektowania, rozwoju, wdrażania i eksploatacji nowoczesnych modeli AI, pipeline'ów oraz usług wspomaganych AI.

AISVS w wersji 1.0 reprezentuje wspólną pracę liderów projektu, grupy roboczej oraz szerszej społeczności współtwórców, mającą na celu stworzenie pragmatycznej, testowalnej podstawy do zabezpieczania systemów sztucznej inteligencji.

Naszym celem przy tym wydaniu jest, aby AISVS było łatwe do wdrożenia, jednocześnie pozostając ściśle skoncentrowanym na określonym zakresie oraz reagując na szybko zmieniający się krajobraz ryzyka unikalny dla sztucznej inteligencji.

### Kluczowe cele wersji 1.0 AISVS

Wersja 1.0 zostanie opracowana zgodnie z kilkoma zasadniczymi wytycznymi.

#### Dobrze zdefiniowany zakres

Każde wymaganie musi być zgodne z nazwą i misją AISVS:

Sztuczna inteligencja – Kontrole działają na warstwie AI/ML (dane, model, pipeline lub inferencja) i są odpowiedzialnością specjalistów AI.
Bezpieczeństwo – Wymagania bezpośrednio niwelują zidentyfikowane ryzyka związane z bezpieczeństwem, prywatnością lub bezpieczeństwem użytkowania.
Weryfikacja – Język jest napisany tak, aby zgodność mogła być obiektywnie zweryfikowana.
Standard – Sekcje mają spójną strukturę i terminologię, tworząc spójny wzorzec odniesienia.
​
---

Stosując AISVS, organizacje mogą systematycznie oceniać i wzmacniać poziom bezpieczeństwa swoich rozwiązań AI, promując kulturę bezpiecznego inżynierowania AI.

## Używanie AISVS

Standard Weryfikacji Bezpieczeństwa Sztucznej Inteligencji (AISVS) definiuje wymagania bezpieczeństwa dla nowoczesnych aplikacji i usług AI, koncentrując się na aspektach pozostających pod kontrolą twórców aplikacji.

AISVS jest przeznaczony dla wszystkich osób opracowujących lub oceniających bezpieczeństwo aplikacji AI, w tym deweloperów, architektów, inżynierów bezpieczeństwa oraz audytorów. Ten rozdział przedstawia strukturę i sposób użycia AISVS, w tym jego poziomy weryfikacji oraz zamierzone przypadki użycia.

### Poziomy weryfikacji bezpieczeństwa sztucznej inteligencji

AISVS definiuje trzy rosnące poziomy weryfikacji bezpieczeństwa. Każdy poziom dodaje głębię i złożoność, umożliwiając organizacjom dostosowanie swojego stanowiska bezpieczeństwa do poziomu ryzyka ich systemów sztucznej inteligencji.

Organizacje mogą zaczynać od Poziomu 1 i stopniowo przechodzić na wyższe poziomy wraz ze wzrostem dojrzałości zabezpieczeń i ekspozycji na zagrożenia.

#### Definicja poziomów

Każdemu wymaganiu w AISVS w wersji 1.0 przypisany jest jeden z następujących poziomów:

 Wymagania poziomu 1

Poziom 1 obejmuje najważniejsze i podstawowe wymagania bezpieczeństwa. Skupiają się one na zapobieganiu powszechnym atakom, które nie opierają się na innych warunkach wstępnych ani podatnościach. Większość kontroli na poziomie 1 jest albo prosta do wdrożenia, albo na tyle istotna, że uzasadnia wysiłek.

 Wymagania poziomu 2

Poziom 2 odnosi się do bardziej zaawansowanych lub mniej powszechnych ataków, a także do wielowarstwowej obrony przed rozpowszechnionymi zagrożeniami. Wymagania te mogą obejmować bardziej złożoną logikę lub celować w określone warunki wstępne ataku.

 Wymagania poziomu 3

Poziom 3 obejmuje kontrole, które zazwyczaj są trudniejsze do wdrożenia lub mają zastosowanie w określonych sytuacjach. Często reprezentują one mechanizmy wielowarstwowej obrony lub środki zaradcze przeciwko niszowym, ukierunkowanym lub wysoce złożonym atakom.

#### Rola (D/V)

Każde wymaganie AISVS jest oznaczone zgodnie z główną grupą odbiorców:

D – Wymagania skoncentrowane na deweloperze
V – Wymagania ukierunkowane na weryfikatora/audytora
D/V – Istotne zarówno dla deweloperów, jak i weryfikatorów

## Zarządzanie danymi treningowymi C1 oraz zarządzanie uprzedzeniami

### Cel kontroli

Dane treningowe muszą być pozyskiwane, przetwarzane i przechowywane w sposób zachowujący ich pochodzenie, bezpieczeństwo, jakość oraz sprawiedliwość. Postępowanie w ten sposób wypełnia obowiązki prawne i zmniejsza ryzyko stronniczości, zatrucia danych lub naruszeń prywatności przez cały cykl życia sztucznej inteligencji.

---

### C1.1 Pochodzenie danych treningowych

Utrzymuj weryfikowalny rejestr wszystkich zbiorów danych, akceptuj wyłącznie zaufane źródła i rejestruj każdą zmianę dla celów audytu.

 #1.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy jest prowadzona aktualna inwentaryzacja każdego źródła danych treningowych (pochodzenie, opiekun/właściciel, licencja, metoda zbierania, ograniczenia dotyczące zamierzonego zastosowania oraz historia przetwarzania).
 #1.1.2    Level: 1    Role: D/V
 Sprawdź, czy dozwolone są tylko zbiory danych sprawdzone pod kątem jakości, reprezentatywności, etycznego pozyskiwania oraz zgodności z licencją, co zmniejsza ryzyko zatrucia danych, wbudowanych uprzedzeń i naruszenia własności intelektualnej.
 #1.1.3    Level: 1    Role: D/V
 Zweryfikuj, czy minimalizacja danych jest egzekwowana, aby wykluczyć niepotrzebne lub wrażliwe atrybuty.
 #1.1.4    Level: 2    Role: D/V
 Zweryfikuj, czy wszystkie zmiany w zbiorze danych podlegają zatwierdzonemu procesowi zatwierdzania z rejestrowaniem.
 #1.1.5    Level: 2    Role: D/V
 Zweryfikuj, czy jakość etykietowania/anonimowania jest zapewniona poprzez wzajemne kontrole recenzentów lub konsensus.
 #1.1.6    Level: 2    Role: D/V
 Zweryfikuj, czy dla istotnych zbiorów danych treningowych są prowadzone „karty danych” lub „karty charakterystyki zbiorów danych”, zawierające szczegółowe informacje o cechach, motywacjach, składzie, procesach zbierania, przetwarzaniu wstępnym oraz zalecanym/niezalecanym zastosowaniu.

---

### C1.2 Bezpieczeństwo i integralność danych treningowych

Ogranicz dostęp, szyfruj dane w stanie spoczynku i w trakcie przesyłania oraz weryfikuj integralność, aby zapobiec manipulacjom lub kradzieży.

 #1.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy kontrola dostępu chroni pamięć i potoki.
 #1.2.2    Level: 2    Role: D/V
 Zweryfikuj, czy zestawy danych są szyfrowane podczas przesyłania oraz, dla wszystkich wrażliwych lub zawierających dane osobowe (PII), również podczas przechowywania, z wykorzystaniem standardowych w branży algorytmów kryptograficznych i praktyk zarządzania kluczami.
 #1.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy do zapewnienia integralności danych podczas przechowywania i przesyłania używane są hasze kryptograficzne lub podpisy cyfrowe, oraz czy stosowane są zautomatyzowane techniki wykrywania anomalii w celu ochrony przed nieautoryzowanymi modyfikacjami lub uszkodzeniami, w tym przed celowanymi próbami zatruwania danych.
 #1.2.4    Level: 3    Role: D/V
 Zweryfikuj, czy wersje zestawów danych są śledzone, aby umożliwić przywracanie poprzednich wersji.
 #1.2.5    Level: 2    Role: D/V
 Zweryfikuj, czy przestarzałe dane są bezpiecznie usuwane lub anonimizowane zgodnie z politykami przechowywania danych, wymogami regulacyjnymi oraz w celu zmniejszenia powierzchni ataku.

---

### C1.3 Kompletność reprezentacji i sprawiedliwość

Wykrywaj przekłamania demograficzne i stosuj metody łagodzące, aby wskaźniki błędów modelu były równe dla wszystkich grup.

 #1.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy zbiory danych zostały poddane profilowaniu pod kątem nierównowagi reprezentacyjnej oraz potencjalnych uprzedzeń dotyczących prawnie chronionych atrybutów (np. rasa, płeć, wiek) oraz innych etycznie wrażliwych cech istotnych dla domeny zastosowania modelu (np. status społeczno-ekonomiczny, lokalizacja).
 #1.3.2    Level: 2    Role: D/V
 Zweryfikuj, czy zidentyfikowane uprzedzenia są łagodzone za pomocą udokumentowanych strategii, takich jak wyrównywanie, ukierunkowana augmentacja danych, dostosowania algorytmiczne (np. techniki wstępnego przetwarzania, przetwarzania w trakcie działania, przetwarzania końcowego) lub ponowne ważenie, oraz czy oceniany jest wpływ tych działań na sprawiedliwość i ogólną wydajność modelu.
 #1.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy metryki sprawiedliwości po trenowaniu są oceniane i dokumentowane.
 #1.3.4    Level: 3    Role: D/V
 Zweryfikuj, czy polityka zarządzania uprzedzeniami w cyklu życia przypisuje właścicieli oraz określa częstotliwość przeglądów.

---

### C1.4 Jakość, integralność i bezpieczeństwo oznaczania danych treningowych

Chroń etykiety za pomocą szyfrowania i wymuszaj podwójną weryfikację dla krytycznych klas.

 #1.4.1    Level: 2    Role: D/V
 Potwierdź, że jakość oznaczania/annotacji jest zapewniona poprzez jasne wytyczne, wzajemne kontrole recenzentów, mechanizmy konsensusu (np. monitorowanie zgodności między anotatorami) oraz określone procesy rozwiązywania niezgodności.
 #1.4.2    Level: 2    Role: D/V
 Zweryfikuj, czy do artefaktów etykiet stosowane są kryptograficzne skróty lub podpisy cyfrowe, aby zapewnić ich integralność i autentyczność.
 #1.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy interfejsy i platformy do etykietowania egzekwują silne mechanizmy kontroli dostępu, utrzymują niezaprzeczalne, zabezpieczone przed manipulacją dzienniki audytu wszystkich działań związanych z etykietowaniem oraz chronią przed nieautoryzowanymi modyfikacjami.
 #1.4.4    Level: 3    Role: D/V
 Zweryfikuj, czy etykiety krytyczne dla bezpieczeństwa, ochrony lub sprawiedliwości (np. identyfikujące toksyczne treści, istotne wyniki medyczne) podlegają obowiązkowej niezależnej podwójnej weryfikacji lub równoważnej solidnej weryfikacji.
 #1.4.5    Level: 2    Role: D/V
 Zweryfikuj, czy informacje wrażliwe (w tym dane osobowe) przypadkowo przechwycone lub niezbędnie obecne w etykietach są zredagowane, pseudonimizowane, anonimowe lub szyfrowane w stanie spoczynku i podczas przesyłania, zgodnie z zasadami minimalizacji danych.
 #1.4.6    Level: 2    Role: D/V
 Zweryfikuj, czy instrukcje i wytyczne dotyczące oznaczania są kompleksowe, kontrolowane pod względem wersji oraz poddane przeglądowi przez rówieśników.
 #1.4.7    Level: 2    Role: D/V
 Sprawdź, czy schematy danych (w tym dla etykiet) są wyraźnie zdefiniowane i kontrolowane pod względem wersji.
 #1.8.2    Level: 2    Role: D/V
 Zweryfikuj, czy zlecone na zewnątrz lub oparte na crowdsourcingu procesy etykietowania zawierają techniczne/proceduralne zabezpieczenia zapewniające poufność danych, integralność, jakość etykiet oraz zapobiegające wyciekowi danych.

---

### C1.5 Zapewnienie jakości danych treningowych

Połącz automatyczną walidację, ręczne losowe kontrole oraz rejestrowane działania naprawcze, aby zagwarantować niezawodność zestawu danych.

 #1.5.1    Level: 1    Role: D
 Zweryfikuj, czy automatyczne testy wykrywają błędy formatowania, wartości null oraz przesunięcia etykiet przy każdym załadunku danych lub istotnej transformacji.
 #1.5.2    Level: 1    Role: D/V
 Zweryfikuj, czy nieudane zestawy danych są kwarantannowane wraz ze ścieżkami audytu.
 #1.5.3    Level: 2    Role: V
 Zweryfikuj, czy ręczne kontrole losowe przeprowadzane przez ekspertów dziedzinowych obejmują statystycznie istotną próbę (np. ≥1% lub 1 000 próbek, w zależności od tego, która wartość jest większa, lub zgodnie z oceną ryzyka), aby wykryć subtelne problemy jakościowe, których nie wychwyciła automatyzacja.
 #1.5.4    Level: 2    Role: D/V
 Zweryfikuj, czy kroki naprawcze zostały dodane do rekordów pochodzenia.
 #1.5.5    Level: 2    Role: D/V
 Zweryfikuj, czy bramki jakości blokują dane o niskiej jakości, chyba że zatwierdzono wyjątki.

---

### C1.6 Wykrywanie zatruwania danych

Zastosuj statystyczne wykrywanie anomalii oraz procedury kwarantanny, aby zatrzymać przeciwnicze wtrącenia.

 #1.6.1    Level: 2    Role: D/V
 Zweryfikuj, czy techniki wykrywania anomalii (np. metody statystyczne, wykrywanie wartości odstających, analiza osadzeń) są stosowane do danych treningowych podczas ich wczytywania oraz przed głównymi sesjami treningowymi, aby zidentyfikować potencjalne ataki polegające na zatruwaniu danych lub przypadkową ich degradację.
 #1.6.2    Level: 2    Role: D/V
 Zweryfikuj, czy oznaczone próbki wywołują ręczną kontrolę przed treningiem.
 #1.6.3    Level: 2    Role: V
 Zweryfikuj, czy wyniki zasilają dossier bezpieczeństwa modelu i informują o bieżącej inteligencji zagrożeń.
 #1.6.4    Level: 3    Role: D/V
 Zweryfikuj, czy logika wykrywania jest aktualizowana o nowe informacje wywiadu zagrożeń.
 #1.6.5    Level: 3    Role: D/V
 Zweryfikuj, czy potoki uczenia online monitorują dryf dystrybucji.
 #1.6.6    Level: 3    Role: D/V
 Zweryfikuj, czy konkretne mechanizmy obronne przeciw znanym typom ataków zatruwania danych (np. odwracanie etykiet, wstawianie wyzwalaczy tylnego wejścia, ataki na wpływowe przykłady) zostały uwzględnione i wdrożone na podstawie profilu ryzyka systemu oraz źródeł danych.

---

### C1.7 Usuwanie danych użytkownika i egzekwowanie zgody

Szanuj prośby o usunięcie oraz wycofanie zgody w całych zbiorach danych, kopiach zapasowych i wytworzonych artefaktach.

 #1.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy procesy usuwania danych usuwają dane podstawowe i pochodne oraz ocenić wpływ na modele, a także czy wpływ na dotknięte modele jest oceniany i w razie potrzeby uwzględniany (np. poprzez ponowne trenowanie lub rekalkibrację).
 #1.7.2    Level: 2    Role: D
 Zweryfikuj, czy istnieją mechanizmy umożliwiające śledzenie i poszanowanie zakresu oraz statusu zgody użytkownika (oraz jej wycofania) na dane wykorzystywane do treningu, oraz czy zgoda jest zatwierdzana przed włączeniem danych do nowych procesów treningowych lub istotnych aktualizacji modelu.
 #1.7.3    Level: 2    Role: V
 Zweryfikuj, czy przepływy pracy są testowane corocznie i rejestrowane.

---

### C1.8 Bezpieczeństwo łańcucha dostaw

Zweryfikuj zewnętrznych dostawców danych i sprawdź integralność za pośrednictwem uwierzytelnionych, szyfrowanych kanałów.

 #1.8.1    Level: 2    Role: D/V
 Zweryfikuj, czy dostawcy danych zewnętrznych, w tym dostawcy modeli wstępnie wytrenowanych oraz zewnętrznych zbiorów danych, przechodzą proces due diligence pod kątem bezpieczeństwa, prywatności, etycznego pozyskiwania oraz jakości danych, zanim ich dane lub modele zostaną zintegrowane.
 #1.8.2    Level: 1    Role: D
 Zweryfikuj, czy zewnętrzne transfery korzystają z TLS/uwierzytelniania oraz mechanizmów kontroli integralności.
 #1.8.3    Level: 2    Role: D/V
 Zweryfikuj, czy źródła danych wysokiego ryzyka (np. otwarte zestawy danych o nieznanym pochodzeniu, nieweryfikowani dostawcy) są poddawane zwiększonej kontroli, takiej jak analiza w piaskownicy, szczegółowe kontrole jakości i uprzedzeń oraz ukierunkowane wykrywanie zatruć, przed zastosowaniem w wrażliwych aplikacjach.
 #1.8.4    Level: 3    Role: D/V
 Zweryfikuj, czy modele wstępnie wytrenowane pochodzące od stron trzecich są oceniane pod kątem wbudowanych uprzedzeń, potencjalnych backdoorów, integralności ich architektury oraz pochodzenia ich oryginalnych danych treningowych przed dostrojeniem lub wdrożeniem.

---

### C1.9 Wykrywanie próbek adwersarialnych

Wprowadź środki podczas fazy treningowej, takie jak trening przeciwnika, aby zwiększyć odporność modelu na przykłady przeciwnika.

 #1.9.1    Level: 3    Role: D/V
 Zweryfikuj, czy odpowiednie zabezpieczenia, takie jak trening przeciwny (wykorzystujący wygenerowane przykłady przeciwnika), augmentacja danych z zakłóconymi danymi wejściowymi lub techniki optymalizacji odpornej, są wdrożone i dostosowane do odpowiednich modeli na podstawie oceny ryzyka.
 #1.9.2    Level: 2    Role: D/V
 Zweryfikuj, czy w przypadku stosowania treningu adwersarialnego generowanie, zarządzanie oraz wersjonowanie zbiorów danych adwersarialnych są dokumentowane i kontrolowane.
 #1.9.3    Level: 3    Role: D/V
 Zweryfikuj, czy wpływ treningu odporności na ataki przeciwne na wydajność modelu (zarówno na dane czyste, jak i przeciwnikowe) oraz na metryki sprawiedliwości jest oceniany, dokumentowany i monitorowany.
 #1.9.4    Level: 3    Role: D/V
 Zweryfikuj, czy strategie dotyczące treningu przeciwnika (adversarial training) oraz odporności są okresowo przeglądane i aktualizowane, aby przeciwdziałać rozwijającym się technikom ataków przeciwnika.

---

### C1.10 Pochodzenie danych i możliwość ich śledzenia

Śledź pełną drogę każdego punktu danych od źródła do wejścia modelu w celu umożliwienia audytu i reakcji na incydenty.

 #1.10.1    Level: 2    Role: D/V
 Zweryfikuj, czy pochodzenie każdego punktu danych, włącznie ze wszystkimi transformacjami, augmentacjami i scaleniami, jest zapisane i można je odtworzyć.
 #1.10.2    Level: 2    Role: D/V
 Zweryfikuj, czy zapisy pochodzenia są niezmienne, bezpiecznie przechowywane i dostępne do audytów lub dochodzeń.
 #1.10.3    Level: 2    Role: D/V
 Zweryfikuj, czy śledzenie pochodzenia obejmuje zarówno dane surowe, jak i syntetyczne.

---

### C1.11 Zarządzanie Danymi Syntetycznymi

Zapewnij właściwe zarządzanie, etykietowanie i ocenę ryzyka danych syntetycznych.

 #1.11.1    Level: 2    Role: D/V
 Zweryfikuj, czy wszystkie dane syntetyczne są wyraźnie oznaczone i możliwe do odróżnienia od danych rzeczywistych w całym procesie przetwarzania.
 #1.11.2    Level: 2    Role: D/V
 Zweryfikuj, czy proces generowania, parametry oraz zamierzone zastosowanie danych syntetycznych są udokumentowane.
 #1.11.3    Level: 2    Role: D/V
 Zweryfikuj, czy dane syntetyczne zostały poddane ocenie ryzyka pod kątem uprzedzeń, wycieku prywatności oraz problemów z reprezentacją przed ich użyciem do treningu.

---

### C1.12 Monitorowanie Dostępu do Danych i Wykrywanie Anomalii

Monitoruj i generuj alerty dotyczące nietypowego dostępu do danych treningowych, aby wykrywać zagrożenia wewnętrzne lub wyciek danych.

 #1.12.1    Level: 2    Role: D/V
 Zweryfikuj, czy wszystkie dostępy do danych treningowych są rejestrowane, w tym użytkownik, czas i działanie.
 #1.12.2    Level: 2    Role: D/V
 Zweryfikuj, czy logi dostępu są regularnie przeglądane pod kątem nieprawidłowych wzorców, takich jak duże eksporty danych lub dostęp z nowych lokalizacji.
 #1.12.3    Level: 2    Role: D/V
 Zweryfikuj, czy alerty są generowane dla podejrzanych zdarzeń dostępu i czy są one niezwłocznie badane.

---

### C1.13 Polityki Retencji i Wygasania Danych

Zdefiniuj i egzekwuj okresy przechowywania danych, aby zminimalizować niepotrzebne przechowywanie danych.

 #1.13.1    Level: 1    Role: D/V
 Zweryfikuj, czy dla wszystkich zestawów danych treningowych zdefiniowano wyraźne okresy przechowywania.
 #1.13.2    Level: 2    Role: D/V
 Zweryfikuj, czy zestawy danych są automatycznie wygaszane, usuwane lub poddawane przeglądowi w celu usunięcia po zakończeniu ich cyklu życia.
 #1.13.3    Level: 2    Role: D/V
 Zweryfikuj, czy działania dotyczące przechowywania i usuwania są rejestrowane i mogą być poddane audytowi.

---

### C1.14 Zgodność regulacyjna i jurysdykcyjna

Zapewnij, że wszystkie dane treningowe są zgodne z obowiązującymi przepisami prawa i regulacjami.

 #1.14.1    Level: 2    Role: D/V
 Zweryfikuj, czy wymagania dotyczące lokalizacji danych oraz transferu transgranicznego są zidentyfikowane i egzekwowane dla wszystkich zestawów danych.
 #1.14.2    Level: 2    Role: D/V
 Zweryfikuj, czy specyficzne dla sektora regulacje (np. opieka zdrowotna, finanse) zostały zidentyfikowane i uwzględnione w przetwarzaniu danych.
 #1.14.3    Level: 2    Role: D/V
 Zweryfikuj, czy zgodność z odpowiednimi przepisami o ochronie prywatności (np. RODO, CCPA) jest dokumentowana i regularnie przeglądana.

---

### C1.15 Znakowanie wodne danych i identyfikacja źródła danych

Wykrywaj nieautoryzowane ponowne użycie lub wyciek danych poufnych lub wrażliwych.

 #1.15.1    Level: 3    Role: D/V
 Zweryfikuj, czy zestawy danych lub ich podzbiory są znakowane wodnym lub zaopatrzone w odciski palców tam, gdzie to możliwe.
 #1.15.2    Level: 3    Role: D/V
 Zweryfikuj, czy metody znakowania wodnego/fingerprintingu nie wprowadzają stronniczości ani ryzyka naruszenia prywatności.
 #1.15.3    Level: 3    Role: D/V
 Zweryfikuj, czy przeprowadzane są okresowe kontrole w celu wykrycia nieautoryzowanego ponownego użycia lub wycieku danych oznaczonych znakiem wodnym.

---

### C1.16 Zarządzanie prawami osób, których dane dotyczą

Wspieraj prawa podmiotów danych, takie jak dostęp, sprostowanie, ograniczenie i sprzeciw.

 #1.16.1    Level: 2    Role: D/V
 Zweryfikuj, czy istnieją mechanizmy umożliwiające reagowanie na wnioski osób, których dane dotyczą, dotyczące dostępu, sprostowania, ograniczenia przetwarzania lub sprzeciwu.
 #1.16.2    Level: 2    Role: D/V
 Zweryfikuj, czy żądania są rejestrowane, śledzone i realizowane w obowiązujących prawnie terminach.
 #1.16.3    Level: 2    Role: D/V
 Zweryfikuj, czy procesy związane z prawami osób, których dane dotyczą, są regularnie testowane i oceniane pod kątem skuteczności.

---

### C1.17 Analiza wpływu wersji zestawu danych

Oceń wpływ zmian w zbiorze danych przed aktualizacją lub wymianą wersji.

 #1.17.1    Level: 2    Role: D/V
 Zweryfikuj, czy przed aktualizacją lub zastąpieniem wersji zestawu danych przeprowadzana jest analiza wpływu, obejmująca wydajność modelu, sprawiedliwość oraz zgodność.
 #1.17.2    Level: 2    Role: D/V
 Zweryfikuj, czy wyniki analizy wpływu są udokumentowane i przejrzane przez odpowiednich interesariuszy.
 #1.17.3    Level: 2    Role: D/V
 Zweryfikuj, czy istnieją plany wycofania zmian na wypadek, gdyby nowe wersje wprowadziły niedopuszczalne ryzyko lub regresje.

---

### C1.18 Bezpieczeństwo zespołu zajmującego się adnotacją danych

Zapewnij bezpieczeństwo i integralność personelu zaangażowanego w adnotację danych.

 #1.18.1    Level: 2    Role: D/V
 Zweryfikuj, czy wszyscy pracownicy zaangażowani w adnotację danych zostali poddani weryfikacji przeszłości oraz przeszkoleni w zakresie bezpieczeństwa danych i prywatności.
 #1.18.2    Level: 2    Role: D/V
 Zweryfikuj, czy wszyscy pracownicy zajmujący się anotacją podpisali umowy o zachowaniu poufności i o nieujawnianiu informacji.
 #1.18.3    Level: 2    Role: D/V
 Zweryfikuj, czy platformy do adnotacji wymuszają kontrolę dostępu i monitorują zagrożenia wewnętrzne.

---

### Bibliografia

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Walidacja danych wejściowych użytkownika C2

### Cel kontroli

Solidna walidacja danych wejściowych użytkownika jest pierwszą linią obrony przed niektórymi z najbardziej szkodliwych ataków na systemy AI. Ataki typu prompt injection mogą nadpisać instrukcje systemowe, ujawnić poufne dane lub skłonić model do zachowania, które jest niedozwolone. Badania pokazują, że jeśli nie zostaną zastosowane dedykowane filtry i hierarchie instrukcji, "multi-shot" jailbreaki wykorzystujące bardzo długie okna kontekstowe będą skuteczne. Ponadto subtelne ataki z użyciem przeciwnych zakłóceń — takie jak zamiany homoglifów lub leetspeak — mogą dyskretnie zmieniać decyzje modelu.

---

### C2.1 Obrona przed wstrzyknięciem promptów

Wstrzyknięcie podpowiedzi jest jednym z największych zagrożeń dla systemów sztucznej inteligencji. Obrona przed tą taktyką wykorzystuje kombinację statycznych filtrów wzorców, dynamicznych klasyfikatorów oraz egzekwowanie hierarchii instrukcji.

 #2.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy dane wejściowe użytkownika są sprawdzane w odniesieniu do ciągle aktualizowanej biblioteki znanych wzorców wstrzyknięć promptów (słowa kluczowe jailbreak, "ignoruj poprzednie", łańcuchy odgrywania ról, pośrednie ataki HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Sprawdź, czy system wymusza hierarchię instrukcji, w której wiadomości systemowe lub deweloperskie mają pierwszeństwo przed instrukcjami użytkownika, nawet po rozszerzeniu okna kontekstu.
 #2.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy testy ewaluacji adwersarialnej (np. „many-shot” promptów zespołu Red Team) są przeprowadzane przed każdym wydaniem modelu lub szablonu promptu, z ustalonymi progami skuteczności oraz automatycznymi blokadami regresji.
 #2.1.4    Level: 2    Role: D
 Zweryfikuj, czy podpowiedzi pochodzące z treści stron trzecich (strony internetowe, pliki PDF, e-maile) są oczyszczane w izolowanym kontekście parsowania przed połączeniem ich z główną podpowiedzią.
 #2.1.5    Level: 3    Role: D/V
 Zweryfikuj, czy wszystkie aktualizacje reguł filtrów promptów, wersje modeli klasyfikatorów oraz zmiany listy blokad są kontrolowane pod względem wersji i audytowalne.

---

### C2.2 Odporność na przykłady adwersarzy

Modele przetwarzania języka naturalnego (NLP) są nadal podatne na subtelne zakłócenia na poziomie znaków lub słów, które ludzie często przeoczają, ale modele mają tendencję do błędnej klasyfikacji.

 #2.2.1    Level: 1    Role: D
 Zweryfikuj, czy podstawowe kroki normalizacji danych wejściowych (Unicode NFC, mapowanie homoglifów, przycinanie białych znaków) są wykonywane przed tokenizacją.
 #2.2.2    Level: 2    Role: D/V
 Zweryfikuj, czy statystyczne wykrywanie anomalii oznacza dane wejściowe o wyjątkowo wysokiej odległości edycyjnej od norm językowych, nadmiernie powtarzających się tokenach lub nieprawidłowych odległościach osadzeń.
 #2.2.3    Level: 2    Role: D
 Zweryfikuj, czy potok inferencji obsługuje opcjonalne warianty modeli wzmocnionych treningiem przeciwnym lub warstwy obronne (np. losowość, defensywna destylacja) dla punktów końcowych o wysokim ryzyku.
 #2.2.4    Level: 2    Role: V
 Zweryfikuj, czy podejrzane dane wejściowe o charakterze przeciwnym są kwarantannowane i rejestrowane wraz z pełnymi ładunkami (po zastosowaniu redakcji danych osobowych).
 #2.2.5    Level: 3    Role: D/V
 Zweryfikuj, czy metryki odporności (wskaźnik sukcesu znanych zestawów ataków) są monitorowane w czasie oraz czy regresje powodują zablokowanie wydania.

---

### C2.3 Walidacja schematu, typu i długości

Ataki AI wykorzystujące niepoprawnie sformatowane lub zbyt duże dane wejściowe mogą powodować błędy parsowania, przenikanie poleceń pomiędzy polami oraz wyczerpanie zasobów. Ścisłe egzekwowanie schematów jest również warunkiem koniecznym przy wykonywaniu deterministycznych wywołań narzędzi.

 #2.3.1    Level: 1    Role: D
 Zweryfikuj, czy każdy punkt końcowy wywołania API lub funkcji definiuje wyraźny schemat wejściowy (JSON Schema, Protobuf lub multimodalny odpowiednik) oraz czy dane wejściowe są walidowane przed złożeniem promptu.
 #2.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy dane wejściowe przekraczające maksymalne limity tokenów lub bajtów są odrzucane z bezpiecznym komunikatem o błędzie i nigdy nie są cicho obcinane.
 #2.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy weryfikacje typów (np. zakresy liczb, wartości wyliczeń, typy MIME dla obrazów/dźwięku) są egzekwowane po stronie serwera, a nie tylko w kodzie klienta.
 #2.3.4    Level: 2    Role: D
 Zweryfikuj, czy walidatory semantyczne (np. JSON Schema) działają w czasie stałym, aby zapobiec algorytmicznemu DoS.
 #2.3.5    Level: 3    Role: V
 Zweryfikuj, czy błędy walidacji są rejestrowane z zaciemnionymi fragmentami danych i jednoznacznymi kodami błędów, aby ułatwić proces analizy bezpieczeństwa.

---

### C2.4 Przesiewanie treści i polityki

Deweloperzy powinni być w stanie wykrywać składniowo poprawne polecenia, które żądają zabronionych treści (takich jak nielegalne instrukcje, mowa nienawiści i teksty chronione prawem autorskim), a następnie zapobiegać ich dalszemu rozpowszechnianiu.

 #2.4.1    Level: 1    Role: D
 Zweryfikuj, czy klasyfikator treści (zero shot lub dostrojony) ocenia każde wejście pod kątem przemocy, samouszkodzeń, nienawiści, treści seksualnych oraz nielegalnych próśb, z możliwością konfigurowania progów.
 #2.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy dane wejściowe naruszające zasady otrzymują ustandaryzowane odmowy lub bezpieczne zakończenia, aby nie były przekazywane do dalszych wywołań modeli LLM.
 #2.4.3    Level: 2    Role: D
 Zweryfikuj, czy model przesiewowy lub zestaw reguł są ponownie trenowane/aktualizowane co najmniej raz na kwartał, uwzględniając nowo zaobserwowane wzorce obejścia zabezpieczeń lub polityk.
 #2.4.4    Level: 2    Role: D
 Zweryfikuj, czy selekcja przestrzega polityk specyficznych dla użytkownika (wiek, regionalne ograniczenia prawne) poprzez reguły oparte na atrybutach rozstrzygane w czasie żądania.
 #2.4.5    Level: 3    Role: V
 Zweryfikuj, czy dzienniki przesiewowe zawierają oceny pewności klasyfikatora oraz etykiety kategorii polityki dla korelacji SOC i przyszłego odtwarzania przez zespół czerwony.

---

### C2.5 Ograniczanie szybkości wejściowej i zapobieganie nadużyciom

Programiści powinni zapobiegać nadużyciom, wyczerpywaniu zasobów oraz automatycznym atakom na systemy AI poprzez ograniczanie szybkości wprowadzania danych i wykrywanie anomalnych wzorców użytkowania.

 #2.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy limity szybkości dla każdego użytkownika, każdego adresu IP oraz każdego klucza API są egzekwowane dla wszystkich punktów końcowych wejściowych.
 #2.5.2    Level: 2    Role: D/V
 Zweryfikuj, czy limity szybkości impulsowej i utrzymanej są dostosowane w celu zapobiegania atakom DoS i atakom siłowym (brute force).
 #2.5.3    Level: 2    Role: D/V
 Zweryfikuj, czy anomalne wzorce użytkowania (np. szybkie, powtarzające się żądania, zalewanie wejścia danymi) wywołują automatyczne blokady lub eskalacje.
 #2.5.4    Level: 3    Role: V
 Zweryfikuj, czy dzienniki zapobiegające nadużyciom są przechowywane i przeglądane pod kątem pojawiających się wzorców ataków.

---

### C2.6 Walidacja wejścia wielomodalnego

Systemy AI powinny zawierać solidną walidację dla danych wejściowych innych niż tekstowe (obrazy, dźwięki, pliki), aby zapobiegać wstrzykiwaniu, unikaniu wykrycia lub nadużyciom zasobów.

 #2.6.1    Level: 1    Role: D
 Zweryfikuj, czy wszystkie dane wejściowe inne niż tekstowe (obrazy, dźwięki, pliki) są sprawdzane pod kątem typu, rozmiaru i formatu przed przetwarzaniem.
 #2.6.2    Level: 2    Role: D/V
 Zweryfikuj, czy pliki są skanowane pod kątem złośliwego oprogramowania i ukrytych ładunków steganograficznych przed ich przetworzeniem.
 #2.6.3    Level: 2    Role: D/V
 Zweryfikuj, czy dane wejściowe w postaci obrazów/dźwięku są sprawdzane pod kątem przeciwnych zakłóceń lub znanych wzorców ataków.
 #2.6.4    Level: 3    Role: V
 Zweryfikuj, czy błędy walidacji danych wejściowych multimodalnych są rejestrowane i powodują generowanie alertów do zbadania.

---

### C2.7 Pochodzenie danych wejściowych i przypisanie źródła

Systemy AI powinny wspierać audyt, śledzenie nadużyć i zgodność poprzez monitorowanie oraz oznaczanie źródeł wszystkich danych wejściowych użytkownika.

 #2.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie dane wejściowe użytkownika są oznaczone metadanymi (ID użytkownika, sesja, źródło, znacznik czasu, adres IP) podczas ich przyjmowania.
 #2.7.2    Level: 2    Role: D/V
 Zweryfikuj, czy metadane pochodzenia są zachowane i możliwe do audytu dla wszystkich przetworzonych danych wejściowych.
 #2.7.3    Level: 2    Role: D/V
 Zweryfikuj, czy anomalne lub niezweryfikowane źródła danych wejściowych są oznaczone i poddawane zwiększonej kontroli lub blokowane.

---

### C2.8 Adaptacyjne wykrywanie zagrożeń w czasie rzeczywistym

Programiści powinni stosować zaawansowane systemy wykrywania zagrożeń dla SI, które dostosowują się do nowych wzorców ataków i zapewniają ochronę w czasie rzeczywistym poprzez skompilowane dopasowywanie wzorców.

 #2.8.1    Level: 1    Role: D/V
 Zweryfikuj, czy wzorce wykrywania zagrożeń są kompilowane do zoptymalizowanych silników wyrażeń regularnych w celu zapewnienia wysokowydajnego filtrowania w czasie rzeczywistym przy minimalnym wpływie na opóźnienia.
 #2.8.2    Level: 1    Role: D/V
 Zweryfikuj, czy systemy wykrywania zagrożeń utrzymują oddzielne biblioteki wzorców dla różnych kategorii zagrożeń (wstrzyknięcie promptu, szkodliwe treści, dane wrażliwe, polecenia systemowe).
 #2.8.3    Level: 2    Role: D/V
 Zweryfikuj, czy adaptacyjne wykrywanie zagrożeń wykorzystuje modele uczenia maszynowego, które aktualizują czułość na zagrożenia na podstawie częstotliwości ataków i wskaźników ich skuteczności.
 #2.8.4    Level: 2    Role: D/V
 Zweryfikuj, czy strumienie informacji o zagrożeniach w czasie rzeczywistym automatycznie aktualizują biblioteki wzorców o nowe sygnatury ataków i IOC (wskaźniki naruszenia).
 #2.8.5    Level: 3    Role: D/V
 Zweryfikuj, czy wskaźniki fałszywie pozytywnych wyników wykrywania zagrożeń są stale monitorowane, a specyficzność wzorców jest automatycznie dostrajana w celu minimalizacji zakłóceń w autentycznych przypadkach użycia.
 #2.8.6    Level: 3    Role: D/V
 Zweryfikuj, czy analiza zagrożeń kontekstowych uwzględnia źródło wejścia, wzorce zachowań użytkownika oraz historię sesji w celu poprawy dokładności wykrywania.
 #2.8.7    Level: 3    Role: D/V
 Zweryfikuj, czy metryki wydajności wykrywania zagrożeń (wskaźnik wykrywalności, opóźnienie przetwarzania, wykorzystanie zasobów) są monitorowane i optymalizowane w czasie rzeczywistym.

---

### C2.9 Wielomodalny Pipeline Weryfikacji Bezpieczeństwa

Programiści powinni zapewnić weryfikację bezpieczeństwa dla tekstu, obrazu, dźwięku oraz innych modalności wejściowych AI za pomocą specyficznych typów wykrywania zagrożeń i izolacji zasobów.

 #2.9.1    Level: 1    Role: D/V
 Zweryfikuj, czy każda modalność wejściowa ma dedykowanych walidatorów bezpieczeństwa z udokumentowanymi wzorcami zagrożeń (tekst: wstrzykiwanie poleceń, obrazy: steganografia, dźwięk: ataki na spektrogram) oraz ustalonymi progami wykrywania.
 #2.9.2    Level: 2    Role: D/V
 Zweryfikuj, czy wielomodalne dane wejściowe są przetwarzane w izolowanych piaskownicach z określonymi limitami zasobów (pamięć, CPU, czas przetwarzania) specyficznymi dla każdego typu modalności i udokumentowanymi w politykach bezpieczeństwa.
 #2.9.3    Level: 2    Role: D/V
 Zweryfikuj, czy wykrywanie ataków krzyżowo-modalnych identyfikuje skoordynowane ataki obejmujące różne typy danych wejściowych (np. ukryte ładunki steganograficzne w obrazach połączone z wstrzyknięciem poleceń w tekście) za pomocą reguł korelacji i generowania alertów.
 #2.9.4    Level: 3    Role: D/V
 Zweryfikuj, czy niepowodzenia walidacji wielomodalnej wywołują szczegółowe logowanie obejmujące wszystkie modalności wejściowe, wyniki walidacji, oceny zagrożeń oraz analizę korelacji ze zorganizowanymi formatami logów do integracji z SIEM.
 #2.9.5    Level: 3    Role: D/V
 Zweryfikuj, czy specyficzne dla modalności klasyfikatory treści są aktualizowane zgodnie z udokumentowanymi harmonogramami (minimum kwartalnie) o nowe wzorce zagrożeń, przykłady adwersarialne oraz czy wskaźniki wydajności utrzymują się powyżej progów bazowych.

---

### Bibliografia

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Zarządzanie cyklem życia modelu C3 i kontrola zmian

### Cel kontroli

Systemy sztucznej inteligencji muszą wdrażać procesy kontroli zmian, które zapobiegają nieautoryzowanym lub niebezpiecznym modyfikacjom modeli trafiającym do środowiska produkcyjnego. Ta kontrola zapewnia integralność modelu przez cały jego cykl życia — od etapu rozwoju, przez wdrożenie, aż do wycofania — co umożliwia szybkie reagowanie na incydenty i utrzymuje odpowiedzialność za wszystkie zmiany.

Główny cel bezpieczeństwa: Tylko autoryzowane, zweryfikowane modele trafiają do produkcji poprzez stosowanie kontrolowanych procesów, które zapewniają integralność, śledzenie i możliwość odzyskiwania.

---

### C3.1 Autoryzacja i integralność modelu

Do środowisk produkcyjnych trafiają wyłącznie autoryzowane modele z potwierdzoną integralnością.

 #3.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie artefakty modelu (wagi, konfiguracje, tokenizery) są podpisane kryptograficznie przez uprawnione podmioty przed wdrożeniem.
 #3.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy integralność modelu jest potwierdzana w czasie wdrożenia, a błędy weryfikacji podpisu uniemożliwiają załadowanie modelu.
 #3.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy zapisy pochodzenia modelu zawierają tożsamość podmiotu autoryzującego, sumy kontrolne danych treningowych, wyniki testów walidacyjnych z oznaczeniem zaliczenia/niezaliczenia oraz znacznik czasu utworzenia.
 #3.1.4    Level: 2    Role: D/V
 Zweryfikuj, czy wszystkie artefakty modelu używają wersjonowania semantycznego (MAJOR.MINOR.PATCH) z udokumentowanymi kryteriami określającymi, kiedy następuje zwiększenie każdego składnika wersji.
 #3.1.5    Level: 2    Role: V
 Zweryfikuj, czy śledzenie zależności utrzymuje inwentaryzację w czasie rzeczywistym, która umożliwia szybkie identyfikowanie wszystkich systemów korzystających.

---

### C3.2 Walidacja i testowanie modelu

Modele muszą przejść określone walidacje bezpieczeństwa i ochrony przed wdrożeniem.

 #3.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy modele przechodzą zautomatyzowane testy bezpieczeństwa, które obejmują walidację danych wejściowych, sanitację danych wyjściowych oraz oceny bezpieczeństwa z uprzednio ustalonymi wewnętrznymi progami zaliczenia/niezaliczenia przed wdrożeniem.
 #3.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy niepowodzenia walidacji automatycznie blokują wdrożenie modelu po wyraźnym zatwierdzeniu nadpisania przez wcześniej wyznaczone upoważnione osoby z udokumentowanymi uzasadnieniami biznesowymi.
 #3.2.3    Level: 2    Role: V
 Zweryfikuj, czy wyniki testów są kryptograficznie podpisane i trwale powiązane z haszem konkretnej wersji modelu, która jest weryfikowana.
 #3.2.4    Level: 2    Role: D/V
 Zweryfikuj, czy wdrożenia awaryjne wymagają udokumentowanej oceny ryzyka bezpieczeństwa oraz zatwierdzenia przez wcześniej wyznaczonego organ ds. bezpieczeństwa w ustalonych wcześniej ramach czasowych.

---

### C3.3 Kontrolowane Wdrażanie i Wycofywanie

Wdrażanie modeli musi być kontrolowane, monitorowane i odwracalne.

 #3.3.1    Level: 1    Role: D
 Zweryfikuj, czy wdrożenia produkcyjne implementują mechanizmy stopniowego wprowadzania (wdrożenia kanaryjskie, wdrożenia blue-green) z automatycznymi wyzwalaczami wycofania na podstawie wcześniej ustalonych wskaźników błędów, progów opóźnień lub kryteriów alertów bezpieczeństwa.
 #3.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy możliwości wycofania przywracają kompletny stan modelu (wagi, konfiguracje, zależności) atomowo w ramach wcześniej zdefiniowanych okien czasowych organizacji.
 #3.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy procesy wdrożeniowe weryfikują podpisy kryptograficzne oraz obliczają sumy kontrolne integralności przed aktywacją modelu, przerywając wdrożenie w przypadku jakiejkolwiek niezgodności.
 #3.3.4    Level: 2    Role: D/V
 Zweryfikuj, czy możliwości awaryjnego wyłączania modeli mogą dezaktywować punkty końcowe modeli w określonych z góry czasach reakcji za pomocą zautomatyzowanych wyłączników obwodów lub ręcznych przycisków awaryjnych.
 #3.3.5    Level: 2    Role: V
 Zweryfikuj, czy artefakty wycofania (poprzednie wersje modeli, konfiguracje, zależności) są przechowywane zgodnie z politykami organizacji w niezmiennym magazynie danych na potrzeby reagowania na incydenty.

---

### C3.4 Zmienność Odpowiedzialności i Audytu

Wszystkie zmiany w cyklu życia modelu muszą być możliwe do śledzenia i audytu.

 #3.4.1    Level: 1    Role: V
 Zweryfikuj, czy wszystkie zmiany modelu (wdrożenie, konfiguracja, wycofanie) generują niezmienialne zapisy audytu zawierające znacznik czasu, uwierzytelnioną tożsamość wykonawcy, typ zmiany oraz stany przed i po zmianie.
 #3.4.2    Level: 2    Role: D/V
 Zweryfikuj, czy dostęp do dziennika audytu wymaga odpowiedniej autoryzacji oraz czy wszystkie próby dostępu są rejestrowane wraz z tożsamością użytkownika i znacznikiem czasowym.
 #3.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy szablony promptów i wiadomości systemowych są kontrolowane wersjami w repozytoriach git, z obowiązkowym przeglądem kodu i zatwierdzeniem przez wyznaczonych recenzentów przed wdrożeniem.
 #3.4.4    Level: 2    Role: V
 Zweryfikuj, czy rejestry audytu zawierają wystarczające szczegóły (hasze modeli, zrzuty konfiguracji, wersje zależności), aby umożliwić pełną rekonstrukcję stanu modelu dla dowolnego znacznika czasu w okresie przechowywania.

---

### C3.5 Bezpieczne praktyki rozwoju oprogramowania

Procesy opracowywania i trenowania modeli muszą przestrzegać bezpiecznych praktyk, aby zapobiec ich naruszeniu.

 #3.5.1    Level: 1    Role: D
 Zweryfikować, czy środowiska tworzenia modeli, testowania i produkcji są fizycznie lub logicznie oddzielone. Nie mają wspólnej infrastruktury, posiadają różne mechanizmy kontroli dostępu oraz izolowane zasoby danych.
 #3.5.2    Level: 1    Role: D
 Zweryfikuj, czy trening modelu i dostrajanie odbywają się w izolowanych środowiskach z kontrolowanym dostępem do sieci.
 #3.5.3    Level: 1    Role: D/V
 Zweryfikuj, czy źródła danych treningowych są potwierdzone poprzez kontrole integralności oraz uwierzytelnione za pomocą zaufanych źródeł z udokumentowanym łańcuchem kontroli przed użyciem w rozwoju modelu.
 #3.5.4    Level: 2    Role: D
 Zweryfikuj, czy artefakty tworzenia modelu (hiperparametry, skrypty treningowe, pliki konfiguracyjne) są przechowywane w systemie kontroli wersji i wymagają zatwierdzenia przez recenzenta przed użyciem w treningu.

---

### C3.6 Wycofanie i wyłączenie modelu

Modele muszą być bezpiecznie wycofane, gdy nie są już potrzebne lub gdy zostaną zidentyfikowane problemy związane z bezpieczeństwem.

 #3.6.1    Level: 1    Role: D
 Zweryfikuj, czy procesy wycofywania modeli automatycznie skanują grafy zależności, identyfikują wszystkie systemy korzystające oraz zapewniają wcześniej uzgodnione okresy powiadomień przed wycofaniem z eksploatacji.
 #3.6.2    Level: 1    Role: D/V
 Zweryfikuj, czy wycofane modele i ich artefakty są bezpiecznie usuwane za pomocą kryptograficznego kasowania lub wielokrotnego nadpisywania zgodnie z udokumentowanymi politykami przechowywania danych oraz czy posiadane są potwierdzone certyfikaty zniszczenia.
 #3.6.3    Level: 2    Role: V
 Zweryfikuj, czy zdarzenia wycofania modelu są rejestrowane z zaznaczeniem czasu i tożsamości wykonawcy oraz czy podpisy modelu są unieważniane, aby zapobiec ponownemu użyciu.
 #3.6.4    Level: 2    Role: D/V
 Zweryfikuj, czy awaryjne wycofanie modelu może wyłączyć dostęp do modelu w ramach wcześniej ustalonych czasów reakcji awaryjnej za pomocą zautomatyzowanych przełączników awaryjnych, jeśli zostaną wykryte krytyczne luki bezpieczeństwa.

---

### Bibliografia

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Bezpieczeństwo infrastruktury C4, konfiguracji i wdrożeń

### Cel Kontrolny

Infrastruktura AI musi być zabezpieczona przed eskalacją uprawnień, manipulacją łańcuchem dostaw i ruchem bocznym poprzez bezpieczną konfigurację, izolację w czasie działania, zaufane procesy wdrażania oraz kompleksowy monitoring. Tylko autoryzowane, zweryfikowane komponenty infrastruktury i konfiguracje trafiają do produkcji poprzez kontrolowane procesy, które zapewniają bezpieczeństwo, integralność i możliwość audytu.

Główny cel bezpieczeństwa: Tylko komponenty infrastruktury z podpisem kryptograficznym i przeskanowane pod kątem podatności trafiają do produkcji przez zautomatyzowane potoki walidacyjne, które egzekwują polityki bezpieczeństwa i utrzymują niemodyfikowalne ścieżki audytu.

---

### C4.1 Izolacja środowiska uruchomieniowego

Zapobiegaj ucieczkom z kontenerów i eskalacji przywilejów poprzez prymitywy izolacji na poziomie jądra oraz obowiązkowe kontrole dostępu.

 #4.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie kontenery AI usuwają WSZYSTKIE możliwości Linuksa z wyjątkiem CAP_SETUID, CAP_SETGID oraz wyraźnie wymaganych możliwości udokumentowanych w bazach bezpieczeństwa.
 #4.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy profile seccomp blokują wszystkie wywołania systemowe, poza tymi na wcześniej zatwierdzonych listach dozwolonych, przy czym naruszenia skutkują zakończeniem kontenera i generowaniem alertów bezpieczeństwa.
 #4.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy obciążenia AI działają z systemami plików root w trybie tylko do odczytu, tmpfs dla danych tymczasowych oraz nazwanymi woluminami dla danych trwałych z wymuszonymi opcjami montowania noexec.
 #4.1.4    Level: 2    Role: D/V
 Zweryfikuj, czy monitorowanie czasu rzeczywistego oparte na eBPF (Falco, Tetragon lub równoważne) wykrywa próby eskalacji uprawnień i automatycznie kończy działanie procesów naruszających zasady zgodnie z wymogami czasowymi reakcji organizacji.
 #4.1.5    Level: 3    Role: D/V
 Zweryfikuj, czy obciążenia AI o wysokim ryzyku są wykonywane w środowiskach izolowanych sprzętowo (Intel TXT, AMD SVM lub dedykowane węzły bare-metal) z weryfikacją atestacji.

---

### C4.2 Bezpieczne procesy budowy i wdrażania

Zapewnij integralność kryptograficzną oraz bezpieczeństwo łańcucha dostaw poprzez odtwarzalne kompilacje i podpisane artefakty.

 #4.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy infrastruktura jako kod jest skanowana za pomocą narzędzi (tfsec, Checkov lub Terrascan) przy każdym commicie, blokując scalanie w przypadku znalezienia błędów o KRYTYCZNYM lub WYSOKIM poziomie zagrożenia.
 #4.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy budowy kontenerów są powtarzalne z identycznymi skrótami SHA256 we wszystkich kompilacjach oraz wygeneruj poświadczenia pochodzenia poziomu SLSA 3 podpisane przez Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy obrazy kontenerów zawierają osadzone SBOM-y CycloneDX lub SPDX oraz czy są podpisane za pomocą Cosign przed wysłaniem do rejestru, przy czym obrazy niepodpisane powinny być odrzucane podczas wdrożenia.
 #4.2.4    Level: 2    Role: D/V
 Zweryfikuj, czy potoki CI/CD używają tokenów OIDC z HashiCorp Vault, ról AWS IAM lub zarządzanej tożsamości Azure, których czas życia nie przekracza limitów określonych w polityce bezpieczeństwa organizacji.
 #4.2.5    Level: 2    Role: D/V
 Zweryfikuj, czy podpisy Cosign oraz pochodzenie SLSA są sprawdzane podczas procesu wdrażania przed uruchomieniem kontenera, a błędy weryfikacji powodują niepowodzenie wdrożenia.
 #4.2.6    Level: 2    Role: D/V
 Zweryfikuj, czy środowiska budowania działają w tymczasowych kontenerach lub maszynach wirtualnych bez trwałej pamięci oraz z izolacją sieciową od produkcyjnych VPC.

---

### C4.3 Bezpieczeństwo sieci i kontrola dostępu

Wdrażaj sieciowanie zero-trust z domyślnymi politykami odmowy i zaszyfrowaną komunikacją.

 #4.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy Kubernetes NetworkPolicies lub ich odpowiednik implementują domyślną politykę deny ingress/egress z wyraźnymi regułami zezwalającymi na wymagane porty (443, 8080 itp.).
 #4.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy SSH (port 22), RDP (port 3389) oraz punkty końcowe metadanych chmury (169.254.169.254) są zablokowane lub wymagają uwierzytelniania opartego na certyfikacie.
 #4.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy ruch wychodzący jest filtrowany przez proxy HTTP/HTTPS (Squid, Istio lub bramy NAT w chmurze) z listami dozwolonych domen, a zablokowane żądania są rejestrowane.
 #4.3.4    Level: 2    Role: D/V
 Zweryfikuj, czy komunikacja między usługami korzysta z wzajemnego TLS z certyfikatami rotowanymi zgodnie z polityką organizacyjną oraz czy walidacja certyfikatów jest wymuszona (bez użycia flag skip-verify).
 #4.3.5    Level: 2    Role: D/V
 Zweryfikuj, czy infrastruktura AI działa w dedykowanych VPC/VNetach bez bezpośredniego dostępu do internetu i komunikuje się wyłącznie przez bramy NAT lub hosty bastionowe.

---

### C4.4 Zarządzanie sekretami i kluczami kryptograficznymi

Chroń poświadczenia za pomocą sprzętowego magazynowania i automatycznej rotacji z dostępem opartym na zasadzie zero-zaufania.

 #4.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy tajne dane są przechowywane w HashiCorp Vault, AWS Secrets Manager, Azure Key Vault lub Google Secret Manager z szyfrowaniem danych spoczynkowych za pomocą AES-256.
 #4.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy klucze kryptograficzne są generowane w HSM zgodnych z poziomem 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) z rotacją kluczy zgodnie z organizacyjną polityką kryptograficzną.
 #4.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy rotacja sekretów jest zautomatyzowana z wdrożeniem bez okresów przestojów oraz czy natychmiastowa rotacja jest wyzwalana przez zmiany personelu lub incydenty bezpieczeństwa.
 #4.4.4    Level: 2    Role: D/V
 Zweryfikuj, czy obrazy kontenerów są skanowane za pomocą narzędzi (GitLeaks, TruffleHog lub detect-secrets), blokujących kompilacje zawierające klucze API, hasła lub certyfikaty.
 #4.4.5    Level: 2    Role: D/V
 Zweryfikuj, czy dostęp do sekretów produkcyjnych wymaga uwierzytelniania wieloskładnikowego (MFA) za pomocą tokenów sprzętowych (YubiKey, FIDO2) oraz czy jest rejestrowany w niezmiennych dziennikach audytu z identyfikacją użytkowników i znacznikami czasu.
 #4.4.6    Level: 2    Role: D/V
 Zweryfikuj, czy sekrety są wstrzykiwane za pomocą sekretów Kubernetes, montowanych woluminów lub kontenerów inicjujących oraz upewnij się, że sekrety nigdy nie są osadzane w zmiennych środowiskowych ani obrazach.

---

### C4.5 Izolacja i walidacja obciążenia AI

Izoluj niezweryfikowane modele AI w bezpiecznych piaskownicach z kompleksową analizą zachowania.

 #4.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy zewnętrzne modele AI działają w gVisor, mikroVM (takich jak Firecracker, CrossVM) lub kontenerach Docker z opcjami --security-opt=no-new-privileges oraz --read-only.
 #4.5.2    Level: 1    Role: D/V
 Zweryfikuj, czy środowiska typu sandbox nie mają dostępu do sieci (--network=none) lub mają dostęp tylko do localhost, przy czym wszystkie zewnętrzne żądania są blokowane przez reguły iptables.
 #4.5.3    Level: 2    Role: D/V
 Zweryfikuj, czy walidacja modelu AI obejmuje zautomatyzowane testy red-team z zakresami testów określonymi przez organizację oraz analizę zachowań w celu wykrywania tylnych drzwi.
 #4.5.4    Level: 2    Role: D/V
 Zweryfikuj, czy przed wdrożeniem modelu AI do produkcji, jego wyniki z piaskownicy są podpisane kryptograficznie przez upoważniony personel ds. bezpieczeństwa i przechowywane w niezmiennych dziennikach audytu.
 #4.5.5    Level: 2    Role: D/V
 Zweryfikuj, czy środowiska piaskownicy są usuwane i odtwarzane z obrazów wzorcowych między ocenami, z pełnym oczyszczeniem systemu plików i pamięci.

---

### C4.6 Monitorowanie bezpieczeństwa infrastruktury

Ciągłe skanowanie i monitorowanie infrastruktury z automatycznym naprawianiem i powiadamianiem w czasie rzeczywistym.

 #4.6.1    Level: 1    Role: D/V
 Zweryfikuj, czy obrazy kontenerów są skanowane zgodnie z harmonogramami organizacyjnymi, przy czym podatności KLUCZOWE blokują wdrożenie na podstawie progów ryzyka organizacyjnego.
 #4.6.2    Level: 1    Role: D/V
 Zweryfikuj, czy infrastruktura spełnia kryteria CIS Benchmarks lub kontrole NIST 800-53 zgodnie z organizacyjnie zdefiniowanymi progami zgodności oraz automatycznym naprawianiem wykrytych niezgodności.
 #4.6.3    Level: 2    Role: D/V
 Zweryfikuj, czy podatności o WYSOKIM poziomie zagrożenia są łagodzone zgodnie z harmonogramami zarządzania ryzykiem organizacji, z zastosowaniem procedur awaryjnych dla aktywnie wykorzystywanych CVE.
 #4.6.4    Level: 2    Role: V
 Zweryfikuj, czy alerty bezpieczeństwa integrują się z platformami SIEM (Splunk, Elastic lub Sentinel) za pomocą formatów CEF lub STIX/TAXII z automatycznym wzbogacaniem.
 #4.6.5    Level: 3    Role: V
 Zweryfikuj, czy metryki infrastruktury są eksportowane do systemów monitorowania (Prometheus, DataDog) wraz z pulpitami SLA i raportowaniem wykonawczym.
 #4.6.6    Level: 2    Role: D/V
 Zweryfikuj, czy wykrywanie odchyleń w konfiguracji jest realizowane za pomocą narzędzi (Chef InSpec, AWS Config) zgodnie z wymaganiami organizacyjnymi dotyczącymi monitoringu, z automatycznym przywracaniem stanu w przypadku nieautoryzowanych zmian.

---

### Zarządzanie Zasobami Infrastruktury AI C4.7

Zapobiegaj atakom wyczerpania zasobów i zapewniaj uczciwy podział zasobów poprzez limity i monitorowanie.

 #4.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy wykorzystanie GPU/TPU jest monitorowane, a alerty są wyzwalane przy progach zdefiniowanych przez organizację oraz czy automatyczne skalowanie lub równoważenie obciążenia są aktywowane na podstawie polityk zarządzania pojemnością.
 #4.7.2    Level: 1    Role: D/V
 Zweryfikuj, czy metryki obciążenia AI (opóźnienie inferencji, przepustowość, wskaźniki błędów) są zbierane zgodnie z wymaganiami monitoringu organizacyjnego i skorelowane z wykorzystaniem infrastruktury.
 #4.7.3    Level: 2    Role: D/V
 Zweryfikuj, czy Kubernetes ResourceQuotas lub odpowiednik ograniczają poszczególne zadania zgodnie z politykami alokacji zasobów organizacji, zapewniając wymuszanie sztywnych limitów.
 #4.7.4    Level: 2    Role: V
 Zweryfikuj, czy monitorowanie kosztów śledzi wydatki według obciążenia/tenantów z alertami opartymi na progach budżetowych organizacji oraz automatycznymi kontrolami przekroczeń budżetu.
 #4.7.5    Level: 3    Role: V
 Zweryfikuj, czy planowanie pojemności korzysta z danych historycznych zorganizowanych według zdefiniowanych przez organizację okresów prognozowania oraz czy automatyczne przydzielanie zasobów jest oparte na wzorcach zapotrzebowania.
 #4.7.6    Level: 2    Role: D/V
 Zweryfikuj, czy wyczerpanie zasobów wywołuje mechanizmy zabezpieczeń obwodu zgodnie z wymaganiami odpowiedzi organizacyjnej, w tym ograniczanie szybkości na podstawie polityk pojemności oraz izolację obciążenia.

---

### C4.8 Kontrola separacji środowisk i promocji

Wymuszaj surowe granice środowiskowe za pomocą automatycznych bramek promocyjnych i walidacji bezpieczeństwa.

 #4.8.1    Level: 1    Role: D/V
 Zweryfikuj, czy środowiska deweloperskie/testowe/produkcyjne działają w oddzielnych VPC/VNetach bez wspólnych ról IAM, grup zabezpieczeń ani łączności sieciowej.
 #4.8.2    Level: 1    Role: D/V
 Zweryfikuj, czy promowanie środowiska wymaga zatwierdzenia przez organizacyjnie określony uprawniony personel za pomocą podpisów kryptograficznych oraz niezmiennych ścieżek audytu.
 #4.8.3    Level: 2    Role: D/V
 Zweryfikuj, czy środowiska produkcyjne blokują dostęp SSH, wyłączają punkty końcowe debugowania oraz wymagają zgłoszeń zmian z obowiązkowym wcześniejszym powiadomieniem organizacji, z wyjątkiem sytuacji awaryjnych.
 #4.8.4    Level: 2    Role: D/V
 Zweryfikuj, czy zmiany w infrastrukturze jako kod wymagają przeglądu przez kolegę wraz z automatycznym testowaniem i skanowaniem bezpieczeństwa przed scaleniem do głównej gałęzi.
 #4.8.5    Level: 2    Role: D/V
 Zweryfikuj, czy dane nieprodukcyjne są anonimizowane zgodnie z organizacyjnymi wymogami dotyczącymi prywatności, generowaniem danych syntetycznych lub pełnym maskowaniem danych z usunięciem informacji pozwalających na identyfikację osób (PII).
 #4.8.6    Level: 2    Role: D/V
 Zweryfikuj, czy bramki promocyjne obejmują zautomatyzowane testy bezpieczeństwa (SAST, DAST, skanowanie kontenerów) z wymaganiem zerowej liczby krytycznych usterek do zatwierdzenia.

---

### C4.9 Kopia zapasowa i odzyskiwanie infrastruktury

Zapewnij odporność infrastruktury poprzez automatyczne tworzenie kopii zapasowych, przetestowane procedury odzyskiwania oraz możliwości odzyskiwania po awarii.

 #4.9.1    Level: 1    Role: D/V
 Zweryfikuj, czy konfiguracje infrastruktury są archiwizowane zgodnie z harmonogramami kopii zapasowych organizacji do geograficznie oddzielonych regionów z zastosowaniem strategii kopii zapasowej 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Zweryfikuj, czy systemy kopii zapasowych działają w izolowanych sieciach z oddzielnymi danymi uwierzytelniającymi oraz przechowywaniem na nośnikach odseparowanych fizycznie (air-gapped) w celu ochrony przed oprogramowaniem ransomware.
 #4.9.3    Level: 2    Role: V
 Zweryfikuj, czy procedury odzyskiwania są testowane i weryfikowane za pomocą automatycznych testów zgodnie z harmonogramami organizacji, przy czym cele RTO i RPO spełniają wymagania organizacyjne.
 #4.9.4    Level: 3    Role: V
 Zweryfikuj, czy plan odzyskiwania po awarii zawiera specyficzne dla AI instrukcje postępowania, obejmujące przywracanie wag modelu, odbudowę klastra GPU oraz mapowanie zależności serwisów.

---

### C4.10 Zgodność i Zarządzanie Infrastrukturą

Utrzymuj zgodność z przepisami poprzez ciągłą ocenę, dokumentację i zautomatyzowane kontrole.

 #4.10.1    Level: 2    Role: D/V
 Zweryfikuj, czy zgodność infrastruktury jest oceniana zgodnie z harmonogramami organizacji w odniesieniu do kontroli SOC 2, ISO 27001 lub FedRAMP, z automatycznym zbieraniem dowodów.
 #4.10.2    Level: 2    Role: V
 Zweryfikuj, czy dokumentacja infrastruktury zawiera diagramy sieci, mapy przepływu danych oraz modele zagrożeń aktualizowane zgodnie z wymaganiami zarządzania zmianami w organizacji.
 #4.10.3    Level: 3    Role: D/V
 Zweryfikuj, czy zmiany w infrastrukturze przechodzą automatyczną ocenę wpływu na zgodność z przepływami zatwierdzania regulacyjnego dla modyfikacji wysokiego ryzyka.

---

### C4.11 Bezpieczeństwo sprzętu AI

Zabezpiecz specyficzne dla AI komponenty sprzętowe, w tym GPU, TPU oraz specjalistyczne akceleratory AI.

 #4.11.1    Level: 2    Role: D/V
 Zweryfikuj, czy oprogramowanie układowe akceleratora AI (BIOS GPU, oprogramowanie układowe TPU) jest weryfikowane za pomocą podpisów kryptograficznych i aktualizowane zgodnie z harmonogramem zarządzania poprawkami w organizacji.
 #4.11.2    Level: 2    Role: D/V
 Zweryfikuj, czy przed wykonaniem zadania integralność akceleratora AI jest potwierdzana przez sprzętową attestację za pomocą TPM 2.0, Intel TXT lub AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Zweryfikuj, czy pamięć GPU jest izolowana między obciążeniami przy użyciu SR-IOV, MIG (Multi-Instance GPU) lub równoważnego sprzętowego podziału z sanitizacją pamięci między zadaniami.
 #4.11.4    Level: 3    Role: V
 Zweryfikuj, czy łańcuch dostaw sprzętu AI obejmuje weryfikację pochodzenia za pomocą certyfikatów producenta oraz walidację opakowań zabezpieczających przed manipulacją.
 #4.11.5    Level: 3    Role: D/V
 Zweryfikuj, czy moduły bezpieczeństwa sprzętowego (HSM) chronią wagi modeli AI oraz klucze kryptograficzne z certyfikacją FIPS 140-2 Poziom 3 lub Common Criteria EAL4+.

---

### C4.12 Infrastruktura AI brzegowej i rozproszonej

Bezpieczne rozproszone wdrożenia AI, w tym obliczenia brzegowe, uczenie federacyjne oraz architektury wielostanowiskowe.

 #4.12.1    Level: 2    Role: D/V
 Zweryfikuj, czy urządzenia edge AI uwierzytelniają się w centralnej infrastrukturze za pomocą wzajemnego TLS z certyfikatami urządzeń rotowanymi zgodnie z organizacyjną polityką zarządzania certyfikatami.
 #4.12.2    Level: 2    Role: D/V
 Zweryfikuj, czy urządzenia brzegowe implementują bezpieczne uruchamianie z weryfikowanymi podpisami oraz ochronę przed wycofaniem wersji, zapobiegającą atakom polegającym na obniżaniu wersji oprogramowania układowego.
 #4.12.3    Level: 3    Role: D/V
 Zweryfikuj, czy skoordynowana sztuczna inteligencja rozproszona korzysta z odpornych na błędy bizantyjskie algorytmów konsensusu z walidacją uczestników i wykrywaniem złośliwych węzłów.
 #4.12.4    Level: 3    Role: D/V
 Zweryfikuj, czy komunikacja krawędź-chmura obejmuje ograniczanie przepustowości, kompresję danych oraz możliwości pracy offline z bezpiecznym lokalnym przechowywaniem.

---

### C4.13 Bezpieczeństwo infrastruktury wielochmurowej i hybrydowej

Zabezpiecz obciążenia AI w wielu dostawcach chmury i wdrożeniach hybrydowych chmury oraz lokalnych.

 #4.13.1    Level: 2    Role: D/V
 Zweryfikuj, czy wdrożenia AI w środowisku multi-cloud korzystają z niezależnej od chmury federacji tożsamości (OIDC, SAML) z centralnym zarządzaniem politykami pomiędzy dostawcami.
 #4.13.2    Level: 2    Role: D/V
 Zweryfikuj, czy transfer danych między chmurami korzysta z szyfrowania end-to-end za pomocą kluczy zarządzanych przez klienta oraz czy kontrola lokalizacji danych jest egzekwowana zgodnie z jurysdykcją.
 #4.13.3    Level: 2    Role: D/V
 Zweryfikuj, czy hybrydowe obciążenia AI w chmurze implementują spójne polityki bezpieczeństwa zarówno w środowiskach lokalnych, jak i chmurowych, zjednoczone pod kątem monitoringu i powiadamiania.
 #4.13.4    Level: 3    Role: V
 Zweryfikuj, czy zapobieganie uzależnieniu od dostawcy chmury obejmuje przenośną infrastrukturę jako kod, znormalizowane interfejsy API oraz możliwości eksportu danych z narzędziami do konwersji formatów.
 #4.13.5    Level: 3    Role: V
 Zweryfikuj, czy optymalizacja kosztów multi-cloud obejmuje kontrole bezpieczeństwa zapobiegające rozproszeniu zasobów oraz nieautoryzowanym opłatom za transfer danych między chmurami.

---

### C4.14 Automatyzacja infrastruktury i bezpieczeństwo GitOps

Zabezpieczone rury automatyzacji infrastruktury oraz przepływy pracy GitOps do zarządzania infrastrukturą AI.

 #4.14.1    Level: 2    Role: D/V
 Zweryfikuj, że repozytoria GitOps wymagają podpisanych commitów za pomocą kluczy GPG oraz reguł ochrony gałęzi zapobiegających bezpośrednim pushom do głównych gałęzi.
 #4.14.2    Level: 2    Role: D/V
 Zweryfikuj, czy automatyzacja infrastruktury obejmuje wykrywanie dryfu wraz z automatycznymi możliwościami naprawy i przywracania, uruchamianymi zgodnie z wymaganiami organizacji dotyczącymi reakcji na nieautoryzowane zmiany.
 #4.14.3    Level: 2    Role: D/V
 Zweryfikuj, czy zautomatyzowane wdrażanie infrastruktury obejmuje walidację polityki bezpieczeństwa wraz z blokowaniem wdrożenia w przypadku niezgodnych konfiguracji.
 #4.14.4    Level: 2    Role: D/V
 Sprawdź, czy tajemnice automatyzacji infrastruktury są zarządzane za pomocą zewnętrznych operatorów sekretów (External Secrets Operator, Bank-Vaults) z automatyczną rotacją.
 #4.14.5    Level: 3    Role: V
 Zweryfikuj, czy infrastruktura samonaprawcza obejmuje korelację zdarzeń związanych z bezpieczeństwem z automatyczną reakcją na incydenty oraz przepływami pracy powiadamiania interesariuszy.

---

### C4.15 Kwantowo-odporna bezpieczeństwo infrastruktury

Przygotuj infrastrukturę AI na zagrożenia związane z obliczeniami kwantowymi poprzez kryptografię post-kwantową oraz protokoły bezpieczne kwantowo.

 #4.15.1    Level: 3    Role: D/V
 Zweryfikuj, czy infrastruktura AI implementuje zatwierdzone przez NIST postkwantowe algorytmy kryptograficzne (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) do wymiany kluczy i podpisów cyfrowych.
 #4.15.2    Level: 3    Role: D/V
 Zweryfikuj, czy systemy dystrybucji kluczy kwantowych (QKD) są wdrażane dla komunikacji AI o wysokim poziomie bezpieczeństwa z protokołami zarządzania kluczami odpornymi na ataki kwantowe.
 #4.15.3    Level: 3    Role: D/V
 Zweryfikuj, czy ramy kryptograficznej elastyczności umożliwiają szybkie przejście na nowe algorytmy postkwantowe wraz z automatyczną rotacją certyfikatów i kluczy.
 #4.15.4    Level: 3    Role: V
 Zweryfikuj, czy modelowanie zagrożeń kwantowych ocenia podatność infrastruktury AI na ataki kwantowe, uwzględniając udokumentowane harmonogramy migracji oraz oceny ryzyka.
 #4.15.5    Level: 3    Role: D/V
 Zweryfikuj, czy hybrydowe klasyczno-kwantowe systemy kryptograficzne zapewniają obronę wielowarstwową podczas okresu przejściowego do kwantowego, wraz z monitorowaniem wydajności.

---

### C4.16 Obliczenia poufne i zabezpieczone enklawy

Chroń obciążenia AI i wagi modeli za pomocą sprzętowych środowisk zaufanego wykonania oraz technologii obliczeń poufnych.

 #4.16.1    Level: 3    Role: D/V
 Zweryfikuj, że wrażliwe modele AI działają w obrębie enklaw Intel SGX, AMD SEV-SNP lub ARM TrustZone z zaszyfrowaną pamięcią i weryfikacją atestacji.
 #4.16.2    Level: 3    Role: D/V
 Zweryfikuj, czy poufne kontenery (Kata Containers, gVisor z poufnym przetwarzaniem) izolują obciążenia AI za pomocą sprzętowego szyfrowania pamięci.
 #4.16.3    Level: 3    Role: D/V
 Zweryfikuj, czy zdalna atestacja potwierdza integralność enklawy przed załadowaniem modeli AI, wykorzystując kryptograficzny dowód autentyczności środowiska wykonawczego.
 #4.16.4    Level: 3    Role: D/V
 Zweryfikuj, czy poufne usługi wnioskowania AI zapobiegają ekstrakcji modelu poprzez szyfrowane obliczenia z zamkniętymi wagami modelu i chronionym wykonaniem.
 #4.16.5    Level: 3    Role: D/V
 Zweryfikuj, czy orkiestracja zaufanego środowiska wykonawczego zarządza cyklem życia bezpiecznego enklawy za pomocą zdalnej atestacji i zaszyfrowanych kanałów komunikacyjnych.
 #4.16.6    Level: 3    Role: D/V
 Zweryfikuj, czy bezpieczne obliczenia wielostronne (SMPC) umożliwiają wspólne trenowanie AI bez ujawniania indywidualnych zbiorów danych lub parametrów modelu.

---

### C4.17 Infrastruktura Zero-Knowledge

Zaimplementuj systemy dowodów zerowej wiedzy do weryfikacji i uwierzytelniania AI z zachowaniem prywatności, bez ujawniania wrażliwych informacji.

 #4.17.1    Level: 3    Role: D/V
 Zweryfikuj, że dowody zero-knowledge (ZK-SNARKs, ZK-STARKs) potwierdzają integralność modelu AI i pochodzenie treningu bez ujawniania wag modelu ani danych treningowych.
 #4.17.2    Level: 3    Role: D/V
 Zweryfikuj, czy systemy uwierzytelniania oparte na ZK umożliwiają weryfikację użytkownika z zachowaniem prywatności w usługach AI, bez ujawniania informacji związanych z tożsamością.
 #4.17.3    Level: 3    Role: D/V
 Zweryfikuj, czy protokoły prywatnego przecięcia zbiorów (PSI) umożliwiają bezpieczne dopasowywanie danych dla federacyjnej SI bez ujawniania poszczególnych zbiorów danych.
 #4.17.4    Level: 3    Role: D/V
 Zweryfikuj, że systemy uczenia maszynowego zero-knowledge (ZKML) umożliwiają weryfikowalne wnioski AI z kryptograficznym dowodem poprawności obliczeń.
 #4.17.5    Level: 3    Role: D/V
 Zweryfikuj, że ZK-rollupy zapewniają skalowalne, chroniące prywatność przetwarzanie transakcji AI z weryfikacją wsadową i zmniejszonym obciążeniem obliczeniowym.

---

### C4.18 Zapobieganie atakom kanałowym

Chroń infrastrukturę AI przed atakami bocznokanałowymi opartymi na czasie, mocy, elektromagnetyzmie i pamięci podręcznej, które mogą ujawnić wrażliwe informacje.

 #4.18.1    Level: 3    Role: D/V
 Zweryfikuj, czy czas inferencji AI jest normalizowany za pomocą algorytmów o stałym czasie działania oraz wypełnień, aby zapobiec atakom na model opartym na analizie czasu.
 #4.18.2    Level: 3    Role: D/V
 Zweryfikuj, czy ochrona przed analizą mocy obejmuje wprowadzanie szumów, filtrowanie linii zasilającej oraz losowe wzorce wykonywania dla sprzętu AI.
 #4.18.3    Level: 3    Role: D/V
 Zweryfikuj, że łagodzenie ataków ubocznych opartych na pamięci podręcznej wykorzystuje partycjonowanie pamięci podręcznej, jej losowanie oraz instrukcje czyszczenia (flush), aby zapobiec wyciekowi informacji.
 #4.18.4    Level: 3    Role: D/V
 Zweryfikuj, czy ochrona przed promieniowaniem elektromagnetycznym obejmuje ekranowanie, filtrowanie sygnałów oraz losowe przetwarzanie, aby zapobiec atakom w stylu TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Zweryfikuj, czy obrony przed bocznokanałowymi atakami mikroarchitektonicznymi obejmują kontrolę wykonania spekulacyjnego oraz zaciemnianie wzorców dostępu do pamięci.

---

### C4.19 Neuromorficzne i specjalistyczne zabezpieczenia sprzętu AI

Zabezpieczyć nowe architektury sprzętowe AI, w tym układy neuromorficzne, FPGA, niestandardowe układy ASIC oraz systemy obliczeń optycznych.

 #4.19.1    Level: 3    Role: D/V
 Zweryfikuj, czy zabezpieczenia chipu neuromorficznego obejmują szyfrowanie wzorców impulsów, ochronę wag synaptycznych oraz weryfikację reguł uczenia opartą na sprzęcie.
 #4.19.2    Level: 3    Role: D/V
 Zweryfikuj, czy akceleratory AI oparte na FPGA implementują szyfrowanie bitstreamu, mechanizmy przeciwdziałania manipulacjom oraz bezpieczne ładowanie konfiguracji z uwierzytelnionymi aktualizacjami.
 #4.19.3    Level: 3    Role: D/V
 Zweryfikuj, czy bezpieczeństwo niestandardowego układu ASIC obejmuje procesory bezpieczeństwa na chipie, sprzętowy rdzeń zaufania oraz bezpieczne przechowywanie kluczy z detekcją manipulacji.
 #4.19.4    Level: 3    Role: D/V
 Zweryfikuj, czy systemy obliczeń optycznych wdrażają kwantowo bezpieczne szyfrowanie optyczne, bezpieczne przełączanie fotoniczne oraz chronione przetwarzanie sygnałów optycznych.
 #4.19.5    Level: 3    Role: D/V
 Zweryfikuj, czy hybrydowe układy AI analogowo-cyfrowe zawierają bezpieczne obliczenia analogowe, chronione przechowywanie wag oraz uwierzytelnioną konwersję analogowo-cyfrową.

---

### Infrastruktura obliczeniowa z zachowaniem prywatności C4.20

Wdrożenie kontroli infrastrukturalnych dla obliczeń z zachowaniem prywatności w celu ochrony danych wrażliwych podczas przetwarzania i analizy AI.

 #4.20.1    Level: 3    Role: D/V
 Zweryfikuj, czy infrastruktura szyfrowania homomorficznego umożliwia wykonywanie obliczeń na zaszyfrowanych, wrażliwych obciążeniach sztucznej inteligencji z kryptograficzną weryfikacją integralności oraz monitorowaniem wydajności.
 #4.20.2    Level: 3    Role: D/V
 Zweryfikuj, czy systemy prywatnego wyszukiwania informacji umożliwiają zapytania do bazy danych bez ujawniania wzorców zapytań poprzez kryptograficzną ochronę wzorców dostępu.
 #4.20.3    Level: 3    Role: D/V
 Zweryfikuj, czy protokoły bezpiecznych obliczeń wielostronnych umożliwiają przeprowadzanie wnioskowania AI z zachowaniem prywatności, bez ujawniania pojedynczych danych wejściowych ani pośrednich obliczeń.
 #4.20.4    Level: 3    Role: D/V
 Zweryfikuj, czy zarządzanie kluczami zapewniające prywatność obejmuje rozproszoną generację kluczy, kryptografię progową oraz bezpieczną rotację kluczy z ochroną wspieraną sprzętowo.
 #4.20.5    Level: 3    Role: D/V
 Zweryfikuj, czy wydajność obliczeń z zachowaniem prywatności jest zoptymalizowana poprzez grupowanie wsadowe, buforowanie i przyspieszenie sprzętowe, przy jednoczesnym utrzymaniu gwarancji bezpieczeństwa kryptograficznego.

---

### C4.15 Framework agenta Integracja z chmurą Bezpieczeństwo i wdrożenie hybrydowe

Kontrole bezpieczeństwa dla zintegrowanych z chmurą frameworków agentów z hybrydowymi architekturami on-premises/chmura.

 #4.15.1    Level: 1    Role: D/V
 Zweryfikuj, czy integracja z przechowywaniem danych w chmurze korzysta z szyfrowania end-to-end z zarządzaniem kluczami kontrolowanym przez agenta.
 #4.15.2    Level: 2    Role: D/V
 Zweryfikuj, czy granice bezpieczeństwa wdrożenia hybrydowego są jasno określone i czy komunikacja odbywa się za pomocą zaszyfrowanych kanałów.
 #4.15.3    Level: 2    Role: D/V
 Zweryfikuj, czy dostęp do zasobów w chmurze obejmuje weryfikację zero-trust z ciągłą autoryzacją.
 #4.15.4    Level: 3    Role: D/V
 Zweryfikuj, czy wymagania dotyczące lokalizacji danych są egzekwowane poprzez kryptograficzne potwierdzenie miejsc przechowywania.
 #4.15.5    Level: 3    Role: D/V
 Zweryfikuj, czy oceny bezpieczeństwa dostawcy chmury obejmują modelowanie zagrożeń specyficzne dla agenta oraz ocenę ryzyka.

---

### Bibliografia

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Kontrola dostępu C5 i tożsamość dla komponentów i użytkowników AI

### Cel Kontroli

Skuteczna kontrola dostępu do systemów AI wymaga solidnego zarządzania tożsamością, autoryzacji uwzględniającej kontekst oraz egzekwowania zasad w czasie rzeczywistym zgodnie z zasadami zero-trust. Te mechanizmy zapewniają, że ludzie, usługi i autonomiczne agenty wchodzą w interakcje z modelami, danymi i zasobami obliczeniowymi tylko w ramach wyraźnie przyznanych uprawnień, z ciągłą weryfikacją i możliwością audytu.

---

### C5.1 Zarządzanie tożsamością i uwierzytelnianie

Utwórz kryptograficznie zabezpieczone tożsamości dla wszystkich podmiotów z uwierzytelnianiem wieloskładnikowym dla operacji uprzywilejowanych.

 #5.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszyscy użytkownicy ludzie i główne jednostki usługowe uwierzytelniają się za pośrednictwem scentralizowanego, korporacyjnego dostawcy tożsamości (IdP) przy użyciu protokołów OIDC/SAML z unikalnym mapowaniem tożsamości na tokeny (bez współdzielonych kont ani poświadczeń).
 #5.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy operacje wysokiego ryzyka (wdrożenie modelu, eksport wag, dostęp do danych treningowych, zmiany konfiguracji produkcyjnej) wymagają uwierzytelniania wieloskładnikowego lub uwierzytelniania podwyższonego z ponowną walidacją sesji.
 #5.1.3    Level: 2    Role: D
 Zweryfikuj, czy nowi administratorzy przechodzą proces potwierdzania tożsamości zgodny z NIST 800-63-3 IAL-2 lub równoważnymi standardami przed uzyskaniem dostępu do systemu produkcyjnego.
 #5.1.4    Level: 2    Role: V
 Zweryfikuj, czy przeglądy dostępu są przeprowadzane kwartalnie z automatycznym wykrywaniem nieaktywnych kont, wymuszaniem rotacji poświadczeń oraz procesami deprowizji.
 #5.1.5    Level: 3    Role: D/V
 Zweryfikuj, czy federacyjne agenty AI uwierzytelniają się za pomocą podpisanych asercji JWT, które mają maksymalny okres ważności 24 godziny i zawierają kryptograficzny dowód pochodzenia.

---

### C5.2 Autoryzacja zasobów i zasada najmniejszych uprawnień

Wdrożenie szczegółowej kontroli dostępu do wszystkich zasobów AI z wyraźnymi modelami uprawnień i ścieżkami audytu.

 #5.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy każdy zasób AI (zbiory danych, modele, punkty końcowe, kolekcje wektorów, indeksy osadzeń, instancje obliczeniowe) wprowadza kontrolę dostępu opartą na rolach z wyraźnymi listami dozwolonych i domyślnymi politykami odrzucania.
 #5.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy zasady najmniejszych uprawnień są domyślnie egzekwowane dla kont usługowych, zaczynając od uprawnień tylko do odczytu, a uzasadnienie biznesowe wymagane jest dokumentowane dla dostępu do zapisu.
 #5.2.3    Level: 1    Role: V
 Zweryfikuj, czy wszystkie modyfikacje kontroli dostępu są powiązane z zatwierdzonymi wnioskami o zmianę oraz czy są niezmiennie rejestrowane wraz z oznaczeniami czasowymi, tożsamościami aktorów, identyfikatorami zasobów i różnicami uprawnień.
 #5.2.4    Level: 2    Role: D
 Zweryfikuj, czy etykiety klasyfikacji danych (Dane osobowe, Dane medyczne, kontrola eksportu, własność) automatycznie propagują się do pochodnych zasobów (osadzenia, pamięć podręczna podpowiedzi, wyniki modelu) z konsekwentnym egzekwowaniem polityki.
 #5.2.5    Level: 2    Role: D/V
 Zweryfikuj, czy próby nieautoryzowanego dostępu oraz zdarzenia eskalacji uprawnień wywołują alerty w czasie rzeczywistym z kontekstowymi metadanymi do systemów SIEM w ciągu 5 minut.

---

### C5.3 Dynamiczna ewaluacja polityki

Wdrożenie mechanizmów kontroli dostępu opartej na atrybutach (ABAC) do podejmowania decyzji autoryzacyjnych opartych na kontekście z możliwością audytu.

 #5.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy decyzje dotyczące autoryzacji są zewnętrznie przekazywane do dedykowanego silnika polityk (OPA, Cedar lub równoważnego), dostępowego za pośrednictwem uwierzytelnionych interfejsów API z ochroną integralności kryptograficznej.
 #5.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy polityki oceniają dynamiczne atrybuty podczas wykonywania, w tym poziom uprawnień użytkownika, klasyfikację poufności zasobu, kontekst żądania, izolację najemcy oraz ograniczenia czasowe.
 #5.3.3    Level: 2    Role: D
 Zweryfikuj, czy definicje polityk są wersjonowane, poddawane przeglądowi przez rówieśników oraz walidowane poprzez automatyczne testy w pipeline'ach CI/CD przed wdrożeniem do produkcji.
 #5.3.4    Level: 2    Role: V
 Zweryfikuj, czy wyniki oceny polityki zawierają ustrukturyzowane uzasadnienia decyzji i są przesyłane do systemów SIEM w celu analizy korelacji oraz raportowania zgodności.
 #5.3.5    Level: 3    Role: D/V
 Zweryfikuj, czy wartości czasu życia (TTL) pamięci podręcznej polityk nie przekraczają 5 minut dla zasobów o wysokiej wrażliwości oraz 1 godziny dla zasobów standardowych z możliwością unieważniania pamięci podręcznej.

---

### C5.4 Egzekwowanie bezpieczeństwa w czasie zapytania

Wdrożenie mechanizmów bezpieczeństwa na warstwie bazy danych z obowiązkowym filtrowaniem i zasadami bezpieczeństwa na poziomie wiersza.

 #5.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie zapytania do baz danych wektorowych i SQL zawierają obowiązkowe filtry bezpieczeństwa (ID najemcy, etykiety poufności, zakres użytkownika) egzekwowane na poziomie silnika bazy danych, a nie w kodzie aplikacji.
 #5.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy polityki bezpieczeństwa na poziomie wiersza (RLS) oraz maskowanie na poziomie pola są włączone z dziedziczeniem polityk dla wszystkich baz danych wektorowych, indeksów wyszukiwania oraz zbiorów danych treningowych.
 #5.4.3    Level: 2    Role: D
 Zweryfikuj, czy nieudane oceny autoryzacji zapobiegają „atakom zdezorientowanego pełnomocnika” poprzez natychmiastowe przerwanie zapytań i zwrócenie wyraźnych kodów błędów autoryzacji zamiast zwracania pustych zestawów wyników.
 #5.4.4    Level: 2    Role: V
 Zweryfikuj, czy czas opóźnienia oceny polityki jest nieprzerwanie monitorowany z automatycznymi alertami dla warunków przekroczenia limitu czasu, które mogłyby umożliwić ominięcie autoryzacji.
 #5.4.5    Level: 3    Role: D/V
 Zweryfikuj, czy mechanizmy ponawiania zapytań ponownie oceniają polityki autoryzacji, aby uwzględnić dynamiczne zmiany uprawnień w aktywnych sesjach użytkowników.

---

### Filtrowanie Wyników C5.5 i Zapobieganie Utracie Danych

Wdroż kontrolki po przetwarzaniu, aby zapobiec nieautoryzowanemu ujawnianiu danych w treściach generowanych przez AI.

 #5.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy mechanizmy filtrowania po inferencji skanują i redagują nieautoryzowane dane osobowe (PII), informacje zastrzeżone oraz dane własnościowe przed dostarczeniem treści żądającym.
 #5.5.2    Level: 1    Role: D/V
 Zweryfikuj, czy cytowania, odniesienia i przypisy źródłowe w wynikach modelu są sprawdzane pod kątem uprawnień użytkownika i usuwane w przypadku wykrycia nieautoryzowanego dostępu.
 #5.5.3    Level: 2    Role: D
 Zweryfikuj, czy ograniczenia dotyczące formatu wyjściowego (oczyszczone pliki PDF, obrazy bez metadanych, zatwierdzone typy plików) są egzekwowane na podstawie poziomów uprawnień użytkowników oraz klasyfikacji danych.
 #5.5.4    Level: 2    Role: V
 Zweryfikuj, czy algorytmy redakcji są deterministyczne, kontrolowane wersjami oraz czy prowadzą dzienniki audytowe wspierające śledztwa zgodności i analizę kryminalistyczną.
 #5.5.5    Level: 3    Role: V
 Zweryfikuj, czy zdarzenia redakcji wysokiego ryzyka generują adaptacyjne logi, które zawierają kryptograficzne skróty oryginalnej zawartości do celów analizy kryminalistycznej bez narażenia danych.

---

### C5.6 Izolacja wielodostępności (Multi-Tenant Isolation)

Zapewnij kryptograficzną i logiczną izolację między najemcami w wspólnej infrastrukturze AI.

 #5.6.1    Level: 1    Role: D/V
 Zweryfikuj, czy przestrzenie pamięci, magazyny osadzeń, wpisy w pamięci podręcznej oraz pliki tymczasowe są podzielone na przestrzenie nazw dla każdego najemcy, z bezpiecznym usuwaniem danych po usunięciu najemcy lub zakończeniu sesji.
 #5.6.2    Level: 1    Role: D/V
 Zweryfikuj, czy każde żądanie API zawiera uwierzytelniony identyfikator najemcy, który jest kryptograficznie weryfikowany w kontekście sesji oraz uprawnień użytkownika.
 #5.6.3    Level: 2    Role: D
 Zweryfikuj, czy polityki sieciowe wdrażają zasady domyślnego odrzucania dla komunikacji między najemcami w ramach siatek usług i platform orkiestracji kontenerów.
 #5.6.4    Level: 3    Role: D
 Zweryfikuj, czy klucze szyfrowania są unikalne dla każdego najemcy przy wsparciu klucza zarządzanego przez klienta (CMK) oraz czy istnieje kryptograficzna izolacja między magazynami danych najemców.

---

### C5.7 Autoryzacja agenta autonomicznego

Kontrola uprawnień dla agentów AI i systemów autonomicznych za pomocą tokenów zdolności o określonym zakresie oraz ciągłej autoryzacji.

 #5.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy autonomiczne agenty otrzymują tokeny zdolności o określonym zakresie, które wyraźnie wymieniają dozwolone działania, dostępne zasoby, granice czasowe oraz ograniczenia operacyjne.
 #5.7.2    Level: 1    Role: D/V
 Zweryfikuj, czy wysokiego ryzyka funkcje (dostęp do systemu plików, wykonywanie kodu, wywołania zewnętrznych interfejsów API, transakcje finansowe) są domyślnie wyłączone i wymagają wyraźnych uprawnień do aktywacji wraz z uzasadnieniem biznesowym.
 #5.7.3    Level: 2    Role: D
 Zweryfikuj, czy tokeny uprawnień są powiązane z sesjami użytkowników, zawierają kryptograficzną ochronę integralności oraz zapewnij, że nie mogą być przechowywane ani ponownie wykorzystywane w trybach offline.
 #5.7.4    Level: 2    Role: V
 Zweryfikuj, czy działania inicjowane przez agenta przechodzą przez wtórną autoryzację za pomocą silnika polityki ABAC z pełną oceną kontekstu i rejestrowaniem audytu.
 #5.7.5    Level: 3    Role: V
 Zweryfikuj, czy warunki błędów agenta i obsługa wyjątków zawierają informacje o zakresie uprawnień, aby wspierać analizę incydentów i dochodzenia kryminalistycznego.

---

### Bibliografia

#### Standardy i ramy

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Przewodniki dotyczące implementacji

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Bezpieczeństwo Specyficzne dla Sztucznej Inteligencji

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## Bezpieczeństwo łańcucha dostaw C6 dla modeli, frameworków i danych

### Cel Kontrolny

Ataki na łańcuch dostaw AI wykorzystują modele, frameworki lub zbiory danych stron trzecich do osadzania tylnego wejścia, stronniczości lub podatnego na wykorzystanie kodu. Te mechanizmy zapewniają pełną kontrolę nad pochodzeniem, zarządzanie podatnościami oraz monitorowanie, aby chronić cały cykl życia modelu.

---

### C6.1 Weryfikacja i Pochodzenie Wstępnie Wytrenowanego Modelu

Oceń i uwierzytelnij pochodzenie modeli stron trzecich, licencje oraz ukryte zachowania przed jakimkolwiek dostrajaniem lub wdrożeniem.

 #6.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy każdy artefakt modelu stron trzecich zawiera podpisany rekord pochodzenia identyfikujący repozytorium źródłowe i hash zatwierdzenia.
 #6.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy modele są skanowane pod kątem złośliwych warstw lub wyzwalaczy trojańskich za pomocą zautomatyzowanych narzędzi przed importem.
 #6.1.3    Level: 2    Role: D
 Zweryfikuj, czy dostrajanie przy pomocy transfer learningu przechodzi testy przeciwdziałające atakom adversarialnym w celu wykrycia ukrytych zachowań.
 #6.1.4    Level: 2    Role: V
 Zweryfikuj, czy licencje modeli, oznaczenia kontroli eksportu oraz oświadczenia dotyczące pochodzenia danych są zarejestrowane w wpisie ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Zweryfikuj, czy modele wysokiego ryzyka (publicznie udostępnione wagi, niezweryfikowani twórcy) pozostają pod kwarantanną aż do przeprowadzenia przeglądu i zatwierdzenia przez człowieka.

---

### C6.2 Skanowanie ram i bibliotek

Ciągłe skanowanie frameworków i bibliotek uczenia maszynowego w celu wykrywania CVE oraz złośliwego kodu, aby utrzymać bezpieczne środowisko wykonawcze.

 #6.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy pipeline'y CI uruchamiają skanery zależności dla frameworków AI oraz krytycznych bibliotek.
 #6.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy krytyczne podatności (CVSS ≥ 7.0) blokują promowanie do obrazów produkcyjnych.
 #6.2.3    Level: 2    Role: D
 Zweryfikuj, czy analiza statyczna kodu uruchamiana jest na rozgałęzionych lub dostarczonych bibliotekach ML.
 #6.2.4    Level: 2    Role: V
 Zweryfikuj, czy propozycje aktualizacji frameworka zawierają ocenę wpływu na bezpieczeństwo odwołującą się do publicznych źródeł CVE.
 #6.2.5    Level: 3    Role: V
 Zweryfikuj, czy sensory czasu wykonywania alarmują o nieoczekiwanych ładowaniach bibliotek dynamicznych, które odbiegają od podpisanego SBOM.

---

### C6.3 Przypinanie i weryfikacja zależności

Przypnij każdą zależność do niezmiennych skrótów i odtwarzaj kompilacje, aby zagwarantować identyczne, wolne od manipulacji artefakty.

 #6.3.1    Level: 1    Role: D/V
 Sprawdź, czy wszystkie menedżery pakietów wymuszają przypinanie wersji za pomocą plików blokady.
 #6.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy w odwołaniach do kontenerów używane są niezmienne skróty (immutable digests) zamiast podatnych na zmiany tagów.
 #6.3.3    Level: 2    Role: D
 Zweryfikuj, czy kontrole powtarzalnych kompilacji porównują skróty w kolejnych uruchomieniach CI, aby zapewnić identyczne wyniki.
 #6.3.4    Level: 2    Role: V
 Zweryfikuj, czy zaświadczenia dotyczące kompilacji są przechowywane przez 18 miesięcy w celu śledzenia audytu.
 #6.3.5    Level: 3    Role: D
 Zweryfikuj, czy wygasłe zależności wywołują automatyczne pull requesty w celu aktualizacji lub rozwidlenia przypiętych wersji.

---

### C6.4 Egzekwowanie autoryzowanego źródła

Zezwalaj na pobieranie artefaktów tylko z kryptograficznie zweryfikowanych, zatwierdzonych przez organizację źródeł i blokuj wszystko inne.

 #6.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy wagi modelu, zestawy danych oraz kontenery są pobierane wyłącznie z zatwierdzonych domen lub wewnętrznych rejestrów.
 #6.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy podpisy Sigstore/Cosign potwierdzają tożsamość wydawcy przed lokalnym buforowaniem artefaktów.
 #6.4.3    Level: 2    Role: D
 Zweryfikuj, czy proxy wychodzące blokują nieautoryzowane pobieranie artefaktów, aby egzekwować politykę zaufanego źródła.
 #6.4.4    Level: 2    Role: V
 Zweryfikuj, czy listy dozwolonych repozytoriów są przeglądane kwartalnie z dowodem uzasadnienia biznesowego dla każdego wpisu.
 #6.4.5    Level: 3    Role: V
 Zweryfikuj, czy naruszenia polityki powodują kwarantannę artefaktów oraz wycofanie zależnych uruchomień potoku.

---

### C6.5 Ocena ryzyka zbioru danych zewnętrznego

Oceniaj zewnętrzne zbiory danych pod kątem zatruwania, uprzedzeń oraz zgodności z przepisami prawnymi i monitoruj je przez cały ich cykl życia.

 #6.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy zewnętrzne zbiory danych przechodzą ocenę ryzyka zanieczyszczenia (np. odcisk palca danych, wykrywanie wartości odstających).
 #6.5.2    Level: 1    Role: D
 Zweryfikuj, czy metryki uprzedzeń (parytet demograficzny, równa szansa) są obliczane przed zatwierdzeniem zestawu danych.
 #6.5.3    Level: 2    Role: V
 Zweryfikuj, czy pochodzenie i warunki licencji dla zestawów danych są uwzględnione w wpisach ML-BOM.
 #6.5.4    Level: 2    Role: V
 Zweryfikuj, czy okresowe monitorowanie wykrywa dryf lub uszkodzenie w hostowanych zbiorach danych.
 #6.5.5    Level: 3    Role: D
 Zweryfikuj, czy niedozwolone treści (prawa autorskie, dane osobowe) są usuwane za pomocą automatycznego oczyszczania przed treningiem.

---

### C6.6 Monitorowanie ataków na łańcuch dostaw

Wykrywaj zagrożenia związane z łańcuchem dostaw na wczesnym etapie dzięki kanałom CVE, analizie dzienników audytu oraz symulacjom zespołów czerwonych.

 #6.6.1    Level: 1    Role: V
 Zweryfikuj, czy dzienniki audytu CI/CD są przesyłane do SIEM, aby wykrywać anomalie w pobieraniu pakietów lub manipulacje krokami procesu budowy.
 #6.6.2    Level: 2    Role: D
 Sprawdź, czy procedury reagowania na incydenty zawierają instrukcje wycofania w przypadku naruszonych modeli lub bibliotek.
 #6.6.3    Level: 3    Role: V
 Zweryfikuj, czy wzbogacanie informacji o zagrożeniach oznacza specyficzne dla uczenia maszynowego wskaźniki (np. IoC związane z zatruwaniem modeli) podczas triage alertów.

---

### C6.7 ML-BOM dla artefaktów modeli

Generuj i podpisuj szczegółowe ML‑specyficzne SBOM-y (ML‑BOM-y), aby użytkownicy końcowi mogli zweryfikować integralność komponentów w czasie wdrożenia.

 #6.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy każdy artefakt modelu publikuje ML‑BOM, który wymienia zestawy danych, wagi, hiperparametry oraz licencje.
 #6.7.2    Level: 1    Role: D/V
 Zweryfikuj, czy generowanie ML-BOM i podpisywanie Cosign są zautomatyzowane w CI oraz czy ich wykonanie jest wymagane do scalenia.
 #6.7.3    Level: 2    Role: D
 Zweryfikuj, czy kontrole kompletności ML-BOM przerywają kompilację, jeśli brakuje jakichkolwiek metadanych komponentu (hash, licencja).
 #6.7.4    Level: 2    Role: V
 Zweryfikuj, czy odbiorcy końcowi mogą zapytać ML-BOM przez API, aby zweryfikować importowane modele w czasie wdrożenia.
 #6.7.5    Level: 3    Role: V
 Zweryfikuj, czy ML‑BOM są wersjonowane i porównywane (diff) w celu wykrywania nieautoryzowanych modyfikacji.

---

### Bibliografia

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Zachowanie modelu C7, kontrola wyników i zapewnienie bezpieczeństwa

### Cel kontroli

Wyniki modelu muszą być uporządkowane, wiarygodne, bezpieczne, wyjaśnialne oraz ciągle monitorowane w środowisku produkcyjnym. Takie podejście zmniejsza halucynacje, wycieki prywatności, szkodliwe treści oraz niekontrolowane działania, jednocześnie zwiększając zaufanie użytkowników i zgodność z przepisami.

---

### C7.1 Wymuszanie formatu wyjściowego

Ścisłe schematy, ograniczone dekodowanie oraz weryfikacja na kolejnych etapach zatrzymują nieprawidłowe lub złośliwe treści zanim się rozprzestrzenią.

 #7.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy schematy odpowiedzi (np. JSON Schema) są dostarczone w promptcie systemowym, a każda odpowiedź jest automatycznie weryfikowana; odpowiedzi niezgodne ze schematem wywołują naprawę lub odrzucenie.
 #7.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy dekodowanie z ograniczeniami (tokeny stopu, wyrażenia regularne, maksymalna liczba tokenów) jest włączone, aby zapobiec przepełnieniu lub kanałom bocznym wstrzyknięcia danych do promptu.
 #7.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy komponenty downstream traktują wyjścia jako niezastrzeżone i walidują je względem schematów lub bezpiecznych wobec wstrzyknięć deserializatorów.
 #7.1.4    Level: 3    Role: V
 Zweryfikuj, czy zdarzenia niepoprawnych wyników są rejestrowane, ograniczane pod względem częstotliwości i prezentowane w systemie monitoringu.

---

### C7.2 Wykrywanie i łagodzenie halucynacji

Szacowanie niepewności i strategie awaryjne ograniczają fałszywe odpowiedzi.

 #7.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy logarytmy prawdopodobieństwa na poziomie tokenów, konsystencja własna zespołu lub dostrojone detektory halucynacji przypisują każdej odpowiedzi ocenę pewności.
 #7.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy odpowiedzi poniżej konfigurowalnego progu zaufania wywołują procedury awaryjne (np. generowanie wspomagane wyszukiwaniem, model zapasowy lub przegląd przez człowieka).
 #7.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy incydenty halucynacji są oznaczane metadanymi z przyczyną źródłową i przekazywane do procesów post-mortem oraz doskonalenia modelu.
 #7.2.4    Level: 3    Role: D/V
 Zweryfikuj, czy progi i detektory są ponownie skalibrowane po istotnych aktualizacjach modelu lub bazy wiedzy.
 #7.2.5    Level: 3    Role: V
 Zweryfikuj, czy wizualizacje na pulpicie nawigacyjnym śledzą wskaźniki halucynacji.

---

### C7.3 Filtracja Bezpieczeństwa i Prywatności Wyjścia

Filtry polityk i ochrona zespołu red-team chronią użytkowników oraz dane poufne.

 #7.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy klasyfikatory przed i po generowaniu blokują nienawiść, nękanie, samookaleczenia, treści ekstremistyczne oraz treści seksualnie explicite zgodne z polityką.
 #7.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy wykrywanie PII/PCI oraz automatyczne zaciemnianie działają przy każdej odpowiedzi; naruszenia powodują zgłoszenie incydentu prywatności.
 #7.3.3    Level: 2    Role: D
 Zweryfikuj, czy oznaczenia poufności (np. tajemnice handlowe) są przenoszone w różnych modalnościach, aby zapobiec wyciekowi w tekstach, obrazach lub kodzie.
 #7.3.4    Level: 3    Role: D/V
 Zweryfikuj, czy próby obejścia filtra lub klasyfikacje wysokiego ryzyka wymagają drugorzędnej akceptacji lub ponownej uwierzytelnienia użytkownika.
 #7.3.5    Level: 3    Role: D/V
 Zweryfikuj, czy progi filtrowania odzwierciedlają jurysdykcje prawne oraz kontekst wieku/roli użytkownika.

---

### C7.4 Ograniczanie wyników i działań

Limity szybkości i mechanizmy zatwierdzania zapobiegają nadużyciom i nadmiernej autonomii.

 #7.4.1    Level: 1    Role: D
 Zweryfikuj, czy limity na użytkownika i na klucz API ograniczają żądania, tokeny oraz koszty, stosując wykładnicze opóźnienie przy błędach 429.
 #7.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy uprzywilejowane działania (zapisy do plików, wykonywanie kodu, połączenia sieciowe) wymagają zatwierdzenia opartego na polityce lub udziału człowieka w procesie.
 #7.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy kontrole spójności międzymodalnej zapewniają, że obrazy, kod i tekst generowane dla tego samego zapytania nie mogą być używane do przemycania złośliwych treści.
 #7.4.4    Level: 2    Role: D
 Zweryfikuj, czy głębokość delegacji agenta, limity rekursji oraz dozwolone listy narzędzi są wyraźnie skonfigurowane.
 #7.4.5    Level: 3    Role: V
 Zweryfikuj, czy naruszenie limitów generuje strukturalne zdarzenia bezpieczeństwa do ingerencji w SIEM.

---

### C7.5 Wyjaśnialność wyników

Przejrzyste sygnały zwiększają zaufanie użytkowników i ułatwiają wewnętrzne debugowanie.

 #7.5.1    Level: 2    Role: D/V
 Zweryfikuj, czy udostępniane są użytkownikowi wskaźniki pewności lub krótkie podsumowania uzasadnienia, gdy ocena ryzyka uzna to za odpowiednie.
 #7.5.2    Level: 2    Role: D/V
 Zweryfikuj, czy wygenerowane wyjaśnienia nie ujawniają poufnych wskazówek systemowych ani danych zastrzeżonych.
 #7.5.3    Level: 3    Role: D
 Zweryfikuj, czy system rejestruje logarytmy prawdopodobieństwa na poziomie tokenów lub mapy uwagi oraz czy przechowuje je do autoryzowanej inspekcji.
 #7.5.4    Level: 3    Role: V
 Zweryfikuj, czy artefakty wyjaśnialności są kontrolowane wersjami wraz z wydaniami modeli dla celów audytu.

---

### C7.6 Integracja monitorowania

Obserwowalność w czasie rzeczywistym zamyka pętlę między rozwojem a produkcją.

 #7.6.1    Level: 1    Role: D
 Zweryfikuj, czy metryki (naruszenia schematu, wskaźnik halucynacji, toksyczność, wycieki danych osobowych, opóźnienia, koszt) są przesyłane do centralnej platformy monitorującej.
 #7.6.2    Level: 1    Role: V
 Zweryfikuj, czy dla każdej metryki bezpieczeństwa zdefiniowano progi alarmowe oraz ścieżki eskalacji dla osób dyżurujących.
 #7.6.3    Level: 2    Role: V
 Zweryfikuj, czy pulpity nawigacyjne korelują anomalie wyjściowe z modelem/wersją, flagą funkcji oraz zmianami danych wejściowych.
 #7.6.4    Level: 2    Role: D/V
 Zweryfikuj, czy dane z monitoringu są wprowadzane z powrotem do procesu ponownego uczenia, dostrajania lub aktualizacji reguł w ramach udokumentowanego procesu MLOps.
 #7.6.5    Level: 3    Role: V
 Zweryfikuj, czy potoki monitorujące są poddane testom penetracyjnym oraz kontrolowane pod względem dostępu, aby zapobiec wyciekowi wrażliwych logów.

---

### 7.7 Zabezpieczenia mediów generatywnych

Zapewnij, że systemy sztucznej inteligencji nie generują nielegalnych, szkodliwych ani nieautoryzowanych treści medialnych poprzez egzekwowanie ograniczeń polityki, walidację wyników oraz możliwość ich śledzenia.

 #7.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy systemowe polecenia i instrukcje użytkownika jednoznacznie zabraniają generowania nielegalnych, szkodliwych lub niezaaprobowanych mediów deepfake (np. obrazów, wideo, dźwięku).
 #7.7.2    Level: 2    Role: D/V
 Zweryfikuj, czy zapytania są filtrowane pod kątem prób generowania podszywania się, seksualnie explicytnych deepfake'ów lub mediów przedstawiających prawdziwe osoby bez ich zgody.
 #7.7.3    Level: 2    Role: V
 Zweryfikuj, czy system wykorzystuje haszowanie percepcyjne, wykrywanie znaków wodnych lub identyfikację (fingerprinting) w celu zapobiegania nieautoryzowanemu powielaniu chronionych prawem autorskim materiałów.
 #7.7.4    Level: 3    Role: D/V
 Zweryfikuj, czy wszystkie wygenerowane materiały są kryptograficznie podpisane, znakowane wodnym znakiem lub zawierają osadzone, odporne na manipulacje metadane pochodzenia dla śledzenia w kolejnych etapach.
 #7.7.5    Level: 3    Role: V
 Zweryfikuj, czy próby obejścia (np. zaciemnianie poleceń, slang, frazy adwersarialne) są wykrywane, rejestrowane i ograniczane pod względem częstotliwości; powtarzające się nadużycia są zgłaszane do systemów monitorowania.

### Bibliografia

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Bezpieczeństwo Pamięci C8, Osadzeń i Baz Wektorowych

### Cel Kontrolny

Osadzenia i magazyny wektorowe działają jako „czynna pamięć” współczesnych systemów AI, nieustannie przyjmując dane dostarczane przez użytkowników i udostępniając je z powrotem w kontekstach modelu za pomocą Generacji Wzbogaconej Wyszukiwaniem (RAG). Jeśli pozostaną bez nadzoru, ta pamięć może ujawnić dane osobowe (PII), naruszyć zgodę lub zostać odwrócona w celu rekonstrukcji oryginalnego tekstu. Celem tej rodziny kontroli jest wzmocnienie kanałów pamięci i baz danych wektorowych tak, aby dostęp był zgodny z zasadą najmniejszych uprawnień, osadzenia zachowywały prywatność, przechowywane wektory wygasały lub mogły być unieważniane na żądanie, a pamięć przypisana do konkretnego użytkownika nigdy nie zanieczyszczała poleceń lub wyników innego użytkownika.

---

### C8.1 Kontrole dostępu do pamięci i indeksów RAG

Wymuszaj szczegółowe kontrole dostępu na każdej kolekcji wektorów.

 #8.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy reguły kontroli dostępu na poziomie wiersza/przestrzeni nazw ograniczają operacje wstawiania, usuwania i zapytań zgodnie z najemcą, kolekcją lub tagiem dokumentu.
 #8.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy klucze API lub tokeny JWT zawierają przypisane zakresy uprawnień (np. identyfikatory kolekcji, czasowniki akcji) oraz czy są rotowane przynajmniej co kwartał.
 #8.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy próby eskalacji uprawnień (np. zapytania o podobieństwo między przestrzeniami nazw) są wykrywane i rejestrowane w systemie SIEM w ciągu 5 minut.
 #8.1.4    Level: 2    Role: D/V
 Zweryfikuj, czy baza danych wektorów rejestruje w dzienniku identyfikator podmiotu, operację, identyfikator wektora/przestrzeń nazw, próg podobieństwa oraz liczbę wyników.
 #8.1.5    Level: 3    Role: V
 Zweryfikuj, czy decyzje dotyczące dostępu są testowane pod kątem luk w obejściu za każdym razem, gdy silniki są aktualizowane lub zmieniają się zasady dzielenia indeksów.

---

### C8.2 Sanitizacja i Walidacja Osadzania

Przeprowadź wstępną kontrolę tekstu pod kątem danych osobowych (PII), zanonimizuj lub pseudonimizuj je przed wektoryzacją, a opcjonalnie dokonaj postprocessingu osadzonych reprezentacji, aby usunąć pozostałe sygnały.

 #8.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy dane PII i dane regulowane są wykrywane za pomocą zautomatyzowanych klasyfikatorów oraz czy są maskowane, tokenizowane lub usuwane przed osadzaniem.
 #8.2.2    Level: 1    Role: D
 Sprawdź, czy potoki osadzania odrzucają lub izolują dane wejściowe zawierające kod wykonywalny lub artefakty niekodujące się w UTF-8, które mogłyby zatruć indeks.
 #8.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy do osadzonych zdań, których odległość od dowolnego znanego tokena PII spada poniżej konfigurowalnego progu, zastosowano lokalne lub metryczne różnicowe maskowanie prywatności.
 #8.2.4    Level: 2    Role: V
 Zweryfikuj, czy skuteczność sanitacji (np. recall usuwania danych osobowych, dryf semantyczny) jest weryfikowana co najmniej półrocznie na podstawie korpusów referencyjnych.
 #8.2.5    Level: 3    Role: D/V
 Zweryfikuj, czy konfiguracje sanitizacji są kontrolowane wersjami, a zmiany podlegają przeglądowi przez rówieśników.

---

### C8.3 Wygasanie pamięci, unieważnianie i usuwanie

RODO ("prawo do bycia zapomnianym") oraz podobne przepisy wymagają terminowego usuwania danych; magazyny wektorów muszą więc obsługiwać TTL, trwałe usuwanie oraz mechanizmy tomb-stoning, aby odebrane wektory nie mogły zostać odzyskane ani ponownie zindeksowane.

 #8.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy każdy rekord wektora i metadanych posiada czas życia (TTL) lub wyraźną etykietę retencji honorowaną przez zautomatyzowane zadania czyszczenia.
 #8.3.2    Level: 1    Role: D/V
 Zweryfikuj, czy żądania usunięcia inicjowane przez użytkownika usuwają wektory, metadane, kopie w pamięci podręcznej oraz indeksy pochodne w ciągu 30 dni.
 #8.3.3    Level: 2    Role: D
 Sprawdź, czy logiczne usunięcia są następowane przez kryptograficzne niszczenie bloków pamięci, jeśli sprzęt to obsługuje, lub przez zniszczenie klucza w sejfie kluczy.
 #8.3.4    Level: 3    Role: D/V
 Zweryfikuj, czy wektory wygasłe są wykluczone z wyników wyszukiwania najbliższych sąsiadów w czasie krótszym niż 500 ms po wygaśnięciu.

---

### C8.4 Zapobieganie inwersji i wyciekowi osadzania

Najnowsze metody obrony — nakładanie szumu, sieci projekcyjne, perturbacja neuronów prywatności oraz szyfrowanie na poziomie warstwy aplikacji — mogą obniżyć wskaźniki odwrócenia tokenów poniżej 5%.

 #8.4.1    Level: 1    Role: V
 Zweryfikuj, czy istnieje formalny model zagrożeń obejmujący ataki inwersyjne, ataki na członkostwo oraz ataki inferencji atrybutów, który jest przeglądany corocznie.
 #8.4.2    Level: 2    Role: D/V
 Zweryfikuj, czy szyfrowanie na warstwie aplikacji lub szyfrowanie przeszukiwalne chroni wektory przed bezpośrednim odczytem przez administratorów infrastruktury lub personel chmury.
 #8.4.3    Level: 3    Role: V
 Zweryfikuj, czy parametry ochrony (ε dla DP, szum σ, rząd rzutowania k) zapewniają równowagę między prywatnością ≥ 99% ochroną tokenów a użytecznością ≤ 3% spadkiem dokładności.
 #8.4.4    Level: 3    Role: D/V
 Zweryfikuj, czy metryki odporności na inwersję są częścią progów zatwierdzających aktualizacje modelu, z określonymi budżetami regresji.

---

### C8.5 Egzekwowanie zakresu dla pamięci specyficznej dla użytkownika

Przecieki między najemcami pozostają głównym ryzykiem związanym z RAG: niewłaściwie filtrowane zapytania o podobieństwo mogą ujawnić prywatne dokumenty innego klienta.

 #8.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy każde zapytanie pobierania jest filtrowane po identyfikatorze najemcy/użytkownika przed przekazaniem do promptu LLM.
 #8.5.2    Level: 1    Role: D
 Zweryfikuj, czy nazwy kolekcji lub identyfikatory z przestrzenią nazw są solone dla każdego użytkownika lub najemcy, aby wektory nie mogły się pokrywać między zakresami.
 #8.5.3    Level: 2    Role: D/V
 Zweryfikuj, czy wyniki podobieństwa powyżej konfigurowalnego progu odległości, ale poza zakresem wywołującego, są odrzucane i wywołują alerty bezpieczeństwa.
 #8.5.4    Level: 2    Role: V
 Zweryfikuj, czy testy obciążeniowe wielodostępne symulują zapytania przeciwnika próbującego uzyskać dostęp do dokumentów poza zakresem oraz czy wykazują brak wycieków danych.
 #8.5.5    Level: 3    Role: D/V
 Zweryfikuj, czy klucze szyfrujące są segregowane dla każdego najemcy, zapewniając izolację kryptograficzną nawet w przypadku współdzielenia fizycznego magazynu.

---

### C8.6 Zaawansowane zabezpieczenia systemu pamięci

Kontrole bezpieczeństwa dla zaawansowanych architektur pamięci, w tym pamięci epizodycznej, semantycznej i roboczej, z określonymi wymaganiami dotyczącymi izolacji i walidacji.

 #8.6.1    Level: 1    Role: D/V
 Zweryfikuj, czy różne typy pamięci (epizodyczna, semantyczna, robocza) mają izolowane konteksty bezpieczeństwa z kontrolą dostępu opartą na rolach, oddzielnymi kluczami szyfrowania oraz udokumentowanymi wzorcami dostępu dla każdego typu pamięci.
 #8.6.2    Level: 2    Role: D/V
 Zweryfikuj, czy procesy konsolidacji pamięci obejmują walidację bezpieczeństwa, aby zapobiec wstrzyknięciu złośliwych wspomnień poprzez sanitację treści, weryfikację źródła oraz kontrole integralności przed zapisaniem.
 #8.6.3    Level: 2    Role: D/V
 Zweryfikuj, czy zapytania dotyczące odzyskiwania pamięci są weryfikowane i oczyszczane, aby zapobiec wydobywaniu nieautoryzowanych informacji poprzez analizę wzorców zapytań, egzekwowanie kontroli dostępu oraz filtrowanie wyników.
 #8.6.4    Level: 3    Role: D/V
 Zweryfikuj, czy mechanizmy zapominania w pamięci bezpiecznie usuwają wrażliwe informacje, zapewniając kryptograficzne gwarancje wymazania poprzez usunięcie klucza, wielokrotne nadpisywanie lub sprzętowe bezpieczne usuwanie z certyfikatami weryfikacji.
 #8.6.5    Level: 3    Role: D/V
 Sprawdź, czy integralność systemu pamięci jest nieprzerwanie monitorowana pod kątem nieautoryzowanych modyfikacji lub uszkodzeń za pomocą sum kontrolnych, dzienników audytu oraz automatycznych powiadomień w przypadku zmian zawartości pamięci poza normalnymi operacjami.

---

### Bibliografia

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Autonomiczna Orkiestracja i Bezpieczeństwo Agentowego Działania

### Cel kontroli

Zapewnij, że autonomiczne lub wieloagentowe systemy AI mogą wykonywać tylko te działania, które są wyraźnie zamierzone, uwierzytelnione, audytowalne oraz mieszczą się w określonych granicach kosztów i ryzyka. Chroni to przed zagrożeniami takimi jak Kompromitacja Systemu Autonomicznego, Nadużycie Narzędzi, Wykrywanie Pętli Agenta, Przejęcie Komunikacji, Podszywanie się pod Tożsamość, Manipulacja Rojem oraz Manipulacja Intencjami.

---

### 9.1 Budżety planowania zadań agenta i rekurencji

Ograniczaj rekurencyjne plany i wymuszaj punkty kontrolne wykonywane przez człowieka dla uprzywilejowanych działań.

 #9.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy maksymalna głębokość rekurencji, rozpiętość, czas zegarowy, liczba tokenów oraz koszty pieniężne wykonania agenta są skonfigurowane centralnie i kontrolowane wersjonowaniem.
 #9.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy działania uprzywilejowane lub nieodwracalne (np. zatwierdzanie kodu, transfery finansowe) wymagają wyraźnej aprobaty ludzkiej za pośrednictwem audytowalnego kanału przed ich wykonaniem.
 #9.1.3    Level: 2    Role: D
 Zweryfikuj, czy monitory zasobów w czasie rzeczywistym wywołują przerwanie wyłącznika awaryjnego, gdy jakikolwiek próg budżetu zostanie przekroczony, zatrzymując dalsze rozszerzanie zadań.
 #9.1.4    Level: 2    Role: D/V
 Zweryfikuj, czy zdarzenia wyłącznika obwodu są rejestrowane z identyfikatorem agenta, warunkiem wyzwalającym oraz przechwyconym stanem planu do celów analizy kryminalistycznej.
 #9.1.5    Level: 3    Role: V
 Zweryfikuj, czy testy bezpieczeństwa obejmują scenariusze wyczerpania budżetu i niekontrolowanego przebiegu planu, potwierdzając bezpieczne zatrzymanie bez utraty danych.
 #9.1.6    Level: 3    Role: D
 Zweryfikuj, czy polityki budżetowe są wyrażone jako polityki w postaci kodu (policy-as-code) i egzekwowane w CI/CD, aby zapobiegać dryfowi konfiguracji.

---

### 9.2 Izolacja wtyczek narzędziowych

Izoluj interakcje narzędzi w celu zapobiegania nieautoryzowanemu dostępowi do systemu lub wykonaniu kodu.

 #9.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy każde narzędzie/wtyczka działa wewnątrz systemu operacyjnego, kontenera lub piaskownicy na poziomie WASM z zasadami najmniejszych uprawnień dotyczącymi systemu plików, sieci i wywołań systemowych.
 #9.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy limity zasobów sandboxu (CPU, pamięć, dysk, ruch sieciowy na wyjściu) oraz limity czasu wykonania są egzekwowane i rejestrowane.
 #9.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy pliki binarne narzędzi lub deskryptory są cyfrowo podpisane; podpisy powinny być weryfikowane przed załadowaniem.
 #9.2.4    Level: 2    Role: V
 Zweryfikuj, czy telemetryka piaskownicy jest przesyłana do SIEM; anomalie (np. próby nawiązania połączeń wychodzących) wywołują alerty.
 #9.2.5    Level: 3    Role: V
 Zweryfikuj, czy wtyczki wysokiego ryzyka przechodzą przegląd bezpieczeństwa oraz testy penetracyjne przed wdrożeniem do produkcji.
 #9.2.6    Level: 3    Role: D/V
 Zweryfikuj, czy próby ucieczki z piaskownicy są automatycznie blokowane, a winny wtyczka jest poddawana kwarantannie do czasu przeprowadzenia dochodzenia.

---

### 9.3 Autonomiczna pętla i ograniczanie kosztów

Wykrywaj i zatrzymuj niekontrolowaną rekurencję między agentami oraz wybuchy kosztów.

 #9.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy wywołania między agentami zawierają limit przeskoków lub TTL, który środowisko wykonawcze dekrementuje i egzekwuje.
 #9.3.2    Level: 2    Role: D
 Zweryfikuj, czy agenci utrzymują unikalny identyfikator grafu wywołań, aby wykrywać samowywołania lub wzorce cykliczne.
 #9.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy skumulowane liczniki jednostek obliczeniowych i wydatków są śledzone dla każdego łańcucha żądań; przekroczenie limitu przerywa łańcuch.
 #9.3.4    Level: 3    Role: V
 Zweryfikuj, czy analiza formalna lub sprawdzanie modelu wykazuje brak nieograniczonej rekurencji w protokołach agentów.
 #9.3.5    Level: 3    Role: D
 Zweryfikuj, czy zdarzenia przerwania pętli generują alerty i dostarczają metryki ciągłego doskonalenia.

---

### 9.4 Ochrona przed niewłaściwym użyciem na poziomie protokołu

Bezpieczne kanały komunikacyjne między agentami a systemami zewnętrznymi w celu zapobiegania przejęciu kontroli lub manipulacji.

 #9.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie wiadomości między agentem a narzędziem oraz między agentami są uwierzytelnione (np. za pomocą wzajemnego TLS lub JWT) oraz szyfrowane end-to-end.
 #9.4.2    Level: 1    Role: D
 Zweryfikuj, czy schematy są ściśle walidowane; nieznane pola lub błędnie sformatowane komunikaty są odrzucane.
 #9.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy kontrole integralności (MAC lub podpisy cyfrowe) obejmują cały ładunek wiadomości, w tym parametry narzędzi.
 #9.4.4    Level: 2    Role: D
 Zweryfikuj, czy ochrona przed powtórnym odtwarzaniem (taśmy lub okna znaczników czasu) jest wymuszona na warstwie protokołu.
 #9.4.5    Level: 3    Role: V
 Zweryfikuj, czy implementacje protokołów przechodzą przez fuzzing oraz analizę statyczną pod kątem podatności na ataki wstrzyknięcia lub deserializacji.

---

### 9.5 Tożsamość agenta i odporność na manipulacje

Zapewnij, że działania są przypisywalne, a modyfikacje wykrywalne.

 #9.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy każda instancja agenta posiada unikalną kryptograficzną tożsamość (parę kluczy lub poświadczenie sprzętowo zakorzenione).
 #9.5.2    Level: 2    Role: D/V
 Zweryfikuj, czy wszystkie działania agenta są podpisane i opatrzone znacznikiem czasu; dzienniki zawierają podpis w celu zapewnienia niemożności zaprzeczenia.
 #9.5.3    Level: 2    Role: V
 Zweryfikuj, czy dzienniki odporne na manipulacje są przechowywane w nośniku tylko dołączanym lub zapisie jednokrotnym.
 #9.5.4    Level: 3    Role: D
 Zweryfikuj, czy klucze tożsamości są rotowane zgodnie z określonym harmonogramem oraz w przypadku wskaźników naruszenia.
 #9.5.5    Level: 3    Role: D/V
 Zweryfikuj, czy próby podszywania się lub konfliktu kluczy powodują natychmiastową kwarantannę dotkniętego agenta.

---

### 9.6 Redukcja ryzyka wieloagentowego roju

Łagodź zagrożenia wynikające ze zbiorowego zachowania poprzez izolację i formalne modelowanie bezpieczeństwa.

 #9.6.1    Level: 1    Role: D/V
 Zweryfikuj, czy agenci działający w różnych domenach bezpieczeństwa wykonują operacje w izolowanych środowiskach uruchomieniowych (runtime sandboxes) lub segmentach sieci.
 #9.6.2    Level: 3    Role: V
 Zweryfikuj, czy zachowania roju są modelowane i formalnie weryfikowane pod kątem żywotności i bezpieczeństwa przed wdrożeniem.
 #9.6.3    Level: 3    Role: D
 Zweryfikuj, czy monitory czasu wykonania wykrywają pojawiające się niebezpieczne wzorce (np. oscylacje, zakleszczenia) i inicjują działania korygujące.

---

### 9.7 Uwierzytelnianie / Autoryzacja użytkownika i narzędzi

Wdrożenie solidnych mechanizmów kontroli dostępu dla każdej akcji wywoływanej przez agenta.

 #9.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy agenci uwierzytelniają się jako podmioty pierwszej klasy w systemach podrzędnych, nigdy nie ponownie wykorzystując poświadczeń użytkownika końcowego.
 #9.7.2    Level: 2    Role: D
 Zweryfikuj, czy szczegółowe polityki autoryzacji ograniczają, które narzędzia agent może wywołać oraz jakie parametry może dostarczyć.
 #9.7.3    Level: 2    Role: V
 Zweryfikuj, czy kontrole uprawnień są ponownie oceniane przy każdym wywołaniu (ciągła autoryzacja), a nie tylko na początku sesji.
 #9.7.4    Level: 3    Role: D
 Zweryfikuj, czy przyznane uprawnienia wygasają automatycznie i wymagają ponownej zgody po upływie limitu czasu lub zmianie zakresu.

---

### 9.8 Bezpieczeństwo Komunikacji Między Agentami

Szyfruj i zabezpieczaj integralność wszystkich wiadomości między agentami, aby zapobiec podsłuchiwaniu i manipulacji.

 #9.8.1    Level: 1    Role: D/V
 Zweryfikuj, czy wzajemna autentykacja i szyfrowanie z doskonałą tajnością do przodu (np. TLS 1.3) są obowiązkowe dla kanałów agentów.
 #9.8.2    Level: 1    Role: D
 Zweryfikuj integralność i pochodzenie wiadomości przed przetwarzaniem; w przypadku niepowodzenia generowane są alerty i wiadomość jest odrzucana.
 #9.8.3    Level: 2    Role: D/V
 Zweryfikuj, czy metadane komunikacji (znaczniki czasu, numery sekwencji) są rejestrowane w celu wsparcia rekonstrukcji forensic.
 #9.8.4    Level: 3    Role: V
 Zweryfikuj, czy weryfikacja formalna lub sprawdzanie modeli potwierdza, że maszyny stanów protokołu nie mogą zostać doprowadzone do stanów niebezpiecznych.

---

### 9.9 Weryfikacja intencji i egzekwowanie ograniczeń

Zweryfikuj, czy działania agenta są zgodne z wyrażonym przez użytkownika zamiarem oraz ograniczeniami systemu.

 #9.9.1    Level: 1    Role: D
 Zweryfikuj, czy solwery ograniczeń przed wykonaniem sprawdzają proponowane działania pod kątem sztywnych reguł bezpieczeństwa i polityki.
 #9.9.2    Level: 2    Role: D/V
 Zweryfikuj, czy działania o wysokim wpływie (finansowe, destrukcyjne, wrażliwe na prywatność) wymagają wyraźnego potwierdzenia zamiaru od użytkownika inicjującego.
 #9.9.3    Level: 2    Role: V
 Zweryfikuj, czy kontrole warunków końcowych potwierdzają, że zakończone działania osiągnęły zamierzone efekty bez skutków ubocznych; rozbieżności powodują wycofanie zmian.
 #9.9.4    Level: 3    Role: V
 Zweryfikuj, czy metody formalne (np. weryfikacja modelu, dowodzenie twierdzeń) lub testy oparte na właściwościach wykazują, że plany agenta spełniają wszystkie zadeklarowane ograniczenia.
 #9.9.5    Level: 3    Role: D
 Zweryfikuj, czy incydenty wynikające z niezgodności intencji lub naruszenia ograniczeń są wykorzystywane do cykli ciągłego doskonalenia oraz wymiany informacji o zagrożeniach.

---

### 9.10 Bezpieczeństwo strategii rozumowania agenta

Bezpieczny wybór i wykonywanie różnych strategii wnioskowania, w tym podejścia ReAct, Chain-of-Thought oraz Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Zweryfikuj, czy wybór strategii rozumowania opiera się na deterministycznych kryteriach (złożoność wejścia, typ zadania, kontekst bezpieczeństwa) oraz czy identyczne dane wejściowe generują identyczny wybór strategii w ramach tego samego kontekstu bezpieczeństwa.
 #9.10.2    Level: 1    Role: D/V
 Zweryfikuj, czy każda strategia rozumowania (ReAct, Chain-of-Thought, Tree-of-Thoughts) posiada dedykowaną walidację danych wejściowych, sanityzację danych wyjściowych oraz ograniczenia czasu wykonania specyficzne dla jej podejścia poznawczego.
 #9.10.3    Level: 2    Role: D/V
 Zweryfikuj, czy przejścia strategii rozumowania są rejestrowane z pełnym kontekstem, w tym cechami wejściowymi, wartościami kryteriów wyboru oraz metadanymi wykonania w celu rekonstrukcji śladu audytu.
 #9.10.4    Level: 2    Role: D/V
 Potwierdź, że rozumowanie Tree-of-Thoughts zawiera mechanizmy przycinania gałęzi, które przerywają eksplorację w momencie wykrycia naruszeń polityki, ograniczeń zasobów lub granic bezpieczeństwa.
 #9.10.5    Level: 2    Role: D/V
 Sprawdź, czy cykle ReAct (Reason-Act-Observe) obejmują punkty kontrolne walidacji na każdym etapie: weryfikację kroku rozumowania, autoryzację działania oraz sanitację obserwacji przed przejściem dalej.
 #9.10.6    Level: 3    Role: D/V
 Zweryfikuj, czy metryki wydajności strategii rozumowania (czas wykonania, zużycie zasobów, jakość wyników) są monitorowane za pomocą automatycznych alertów, gdy metryki odbiegają od skonfigurowanych progów.
 #9.10.7    Level: 3    Role: D/V
 Zweryfikuj, czy hybrydowe podejścia rozumowania łączące wiele strategii zachowują walidację danych wejściowych oraz ograniczenia wyjściowe wszystkich składowych strategii, bez omijania jakichkolwiek mechanizmów bezpieczeństwa.
 #9.10.8    Level: 3    Role: D/V
 Zweryfikuj, czy strategia testowania bezpieczeństwa rozumowania obejmuje fuzzing przy użyciu nieprawidłowych danych wejściowych, przeciwnicze podpowiedzi zaprojektowane w celu wymuszenia zmiany strategii oraz testowanie warunków brzegowych dla każdego podejścia poznawczego.

---

### 9.11 Zarządzanie cyklem życia agenta i bezpieczeństwo

Bezpieczna inicjalizacja agenta, przejścia stanów oraz zakończenie działania z wykorzystaniem kryptograficznych ścieżek audytu i zdefiniowanych procedur odzyskiwania.

 #9.11.1    Level: 1    Role: D/V
 Zweryfikuj, czy inicjalizacja agenta obejmuje ustanowienie tożsamości kryptograficznej za pomocą sprzętowo zabezpieczonych poświadczeń oraz niezmienialnych dzienników audytu startowego zawierających identyfikator agenta, znacznik czasu, hash konfiguracji i parametry inicjalizacji.
 #9.11.2    Level: 2    Role: D/V
 Zweryfikuj, czy przejścia stanów agenta są podpisane kryptograficznie, opatrzone znacznikiem czasu oraz rejestrowane z pełnym kontekstem, w tym zdarzeniami wywołującymi, haszem poprzedniego stanu, haszem nowego stanu oraz przeprowadzonymi walidacjami bezpieczeństwa.
 #9.11.3    Level: 2    Role: D/V
 Zweryfikuj, czy procedury zamykania agenta obejmują bezpieczne wymazywanie pamięci przy użyciu kryptograficznego usuwania lub wielokrotnego nadpisywania, unieważnianie poświadczeń z powiadomieniem urzędu certyfikacji oraz generowanie świadectw zakończenia pracy z dowodem manipulacji.
 #9.11.4    Level: 3    Role: D/V
 Zweryfikuj, czy mechanizmy odzyskiwania agenta weryfikują integralność stanu za pomocą kryptograficznych sum kontrolnych (minimum SHA-256) oraz czy w przypadku wykrycia korupcji następuje przywrócenie do znanych, poprawnych stanów wraz z automatycznymi alertami i wymogiem ręcznej akceptacji.
 #9.11.5    Level: 3    Role: D/V
 Zweryfikuj, czy mechanizmy utrwalania agenta szyfrują wrażliwe dane stanu za pomocą indywidualnych kluczy AES-256 dla każdego agenta oraz czy implementują bezpieczną rotację kluczy według konfigurowalnych harmonogramów (maksymalnie co 90 dni) z wdrożeniem bez przestojów.

---

### 9.12 Ramy bezpieczeństwa integracji narzędzi

Kontrole bezpieczeństwa dla dynamicznego ładowania narzędzi, wykonania oraz weryfikacji wyników z określonymi procesami oceny ryzyka i zatwierdzania.

 #9.12.1    Level: 1    Role: D/V
 Zweryfikuj, czy deskryptory narzędzi zawierają metadane bezpieczeństwa określające wymagane uprawnienia (odczyt/zapis/wykonanie), poziomy ryzyka (niski/średni/wysoki), limity zasobów (CPU, pamięć, sieć) oraz wymagania walidacyjne udokumentowane w manifestach narzędzi.
 #9.12.2    Level: 1    Role: D/V
 Zweryfikuj, czy wyniki wykonania narzędzia są sprawdzane pod kątem zgodności z oczekiwanymi schematami (JSON Schema, XML Schema) oraz politykami bezpieczeństwa (sanityzacja wyniku, klasyfikacja danych) przed integracją, uwzględniając limity czasu oraz procedury obsługi błędów.
 #9.12.3    Level: 2    Role: D/V
 Zweryfikuj, czy logi interakcji narzędzi zawierają szczegółowy kontekst bezpieczeństwa, w tym użycie uprawnień, wzorce dostępu do danych, czas wykonania, zużycie zasobów oraz kody zwrotne, z użyciem ustrukturyzowanego logowania do integracji z SIEM.
 #9.12.4    Level: 2    Role: D/V
 Zweryfikuj, czy mechanizmy dynamicznego ładowania narzędzi sprawdzają podpisy cyfrowe z wykorzystaniem infrastruktury PKI oraz implementują bezpieczne protokoły ładowania z izolacją w piaskownicy i weryfikacją uprawnień przed wykonaniem.
 #9.12.5    Level: 3    Role: D/V
 Zweryfikuj, czy oceny bezpieczeństwa narzędzi są automatycznie uruchamiane dla nowych wersji z obowiązkowymi etapami zatwierdzenia, obejmującymi analizę statyczną, testy dynamiczne oraz przegląd zespołu ds. bezpieczeństwa, z udokumentowanymi kryteriami zatwierdzenia i wymaganiami dotyczącymi czasu realizacji (SLA).

---

#### Bibliografia

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Odporność na ataki adwersarialne i obrona prywatności

### Cel kontrolny

Zapewnij, aby modele sztucznej inteligencji pozostawały niezawodne, chroniące prywatność oraz odporne na nadużycia w przypadku ataków polegających na ominięciu zabezpieczeń, wnioskowaniu, ekstrakcji danych lub zatruwaniu.

---

### 10.1 Wyrównanie modelu i bezpieczeństwo

Zabezpiecz się przed szkodliwymi lub naruszającymi politykę wynikami.

 #10.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy zestaw testów zgodności (prompty zespołu czerwonego, sondy jailbreak, zabronione treści) jest kontrolowany wersjami i uruchamiany przy każdym wydaniu modelu.
 #10.1.2    Level: 1    Role: D
 Zweryfikuj, czy są egzekwowane zasady odmowy i bezpiecznego ukończenia.
 #10.1.3    Level: 2    Role: D/V
 Zweryfikuj, czy automatyczny evaluator mierzy wskaźnik treści szkodliwych i sygnalizuje regresje przekraczające ustalony próg.
 #10.1.4    Level: 2    Role: D
 Zweryfikuj, czy szkolenie przeciwko jailbreakowi jest udokumentowane i możliwe do odtworzenia.
 #10.1.5    Level: 3    Role: V
 Zweryfikuj, czy formalne dowody zgodności z politykami lub certyfikowany monitoring obejmują krytyczne obszary.

---

### 10.2 Utwardzanie na przykładach przeciwnych

Zwiększ odporność na zmanipulowane dane wejściowe. Obecnie najlepszą praktyką są solidne szkolenia przeciwnikowe oraz ocena za pomocą benchmarków.

 #10.2.1    Level: 1    Role: D
 Zweryfikuj, czy repozytoria projektów zawierają konfiguracje treningu przeciwnika z powtarzalnymi ziarnami.
 #10.2.2    Level: 2    Role: D/V
 Zweryfikuj, czy wykrywanie przykładów adwersarialnych generuje alerty blokujące w liniach produkcyjnych.
 #10.2.4    Level: 3    Role: V
 Zweryfikuj, czy dowody certyfikowanej odporności lub certyfikaty przedziałowych granic obejmują przynajmniej najważniejsze krytyczne klasy.
 #10.2.5    Level: 3    Role: V
 Zweryfikuj, czy testy regresyjne wykorzystują adaptacyjne ataki, aby potwierdzić brak mierzalnej utraty odporności.

---

### 10.3 Łagodzenie skutków ataków wnioskowania o przynależności

Ogranicz możliwość ustalenia, czy rekord znajdował się w danych treningowych. Różnicowa prywatność i maskowanie współczynnika ufności pozostają najskuteczniejszymi znanymi metodami obrony.

 #10.3.1    Level: 1    Role: D
 Zweryfikuj, czy regularizacja entropii dla każdego zapytania lub skalowanie temperatury zmniejsza nadmiernie pewne prognozy.
 #10.3.2    Level: 2    Role: D
 Zweryfikuj, że trening wykorzystuje optymalizację różnicowo prywatną ograniczoną przez ε dla wrażliwych zbiorów danych.
 #10.3.3    Level: 2    Role: V
 Zweryfikuj, czy symulacje ataków (model cienia lub czarna skrzynka) wykazują AUC ataku ≤ 0,60 na danych testowych.

---

### 10.4 Odporność na inwersję modelu

Zapobiegaj rekonstrukcji prywatnych atrybutów. Ostatnie badania podkreślają obcinanie wyników i gwarancje różnicowej prywatności (DP) jako praktyczne środki obronne.

 #10.4.1    Level: 1    Role: D
 Zweryfikuj, czy wrażliwe atrybuty nigdy nie są bezpośrednio wyprowadzane; tam gdzie to konieczne, używaj koszyków (bucketów) lub transformacji jednokierunkowych.
 #10.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy limity szybkości zapytań ograniczają powtarzające się adaptacyjne zapytania od tego samego podmiotu.
 #10.4.3    Level: 2    Role: D
 Zweryfikuj, czy model jest trenowany z zastosowaniem szumu chroniącego prywatność.

---

### 10.5 Obrona przed ekstrakcją modelu

Wykrywaj i uniemożliwiaj nieautoryzowane klonowanie. Zaleca się stosowanie znakowania wodnego oraz analizy wzorców zapytań.

 #10.5.1    Level: 1    Role: D
 Sprawdź, czy bramki inferencyjne egzekwują globalne i na klucz API limity szybkości dostosowane do progu zapamiętywania modelu.
 #10.5.2    Level: 2    Role: D/V
 Zweryfikuj, czy statystyki entropii zapytań i wielości wejść zasilają automatyczny detektor ekstrakcji.
 #10.5.3    Level: 2    Role: V
 Zweryfikuj, czy kruche lub probabilistyczne znaki wodne mogą być udowodnione z p < 0,01 przy ≤ 1000 zapytaniach wobec podejrzanego klona.
 #10.5.4    Level: 3    Role: D
 Zweryfikuj, czy klucze znaków wodnych i zestawy wyzwalaczy są przechowywane w module bezpieczeństwa sprzętowego oraz czy są rotowane corocznie.
 #10.5.5    Level: 3    Role: V
 Zweryfikuj, czy zdarzenia extraction-alert zawierają zapytania naruszające zasady i są zintegrowane z procedurami reagowania na incydenty.

---

### 10.6 Wykrywanie zatrutych danych podczas inferencji

Identyfikuj i neutralizuj zainfekowane tylne wejścia lub wejścia zatrute.

 #10.6.1    Level: 1    Role: D
 Zweryfikuj, czy dane wejściowe przechodzą przez detektor anomalii (np. STRIP, ocenianie spójności) przed inferencją modelu.
 #10.6.2    Level: 1    Role: V
 Zweryfikuj, czy progi detektora są dostrojone na czystych/zatrutych zestawach walidacyjnych, aby osiągnąć mniej niż 5% fałszywych trafień.
 #10.6.3    Level: 2    Role: D
 Zweryfikuj, czy dane wejściowe oznaczone jako zainfekowane wywołują miękkie blokowanie oraz procedury przeglądu przez człowieka.
 #10.6.4    Level: 2    Role: V
 Zweryfikuj, czy detektory są poddane testom wytrzymałościowym za pomocą adaptacyjnych ataków tylnego wejścia bez wyzwalacza.
 #10.6.5    Level: 3    Role: D
 Zweryfikuj, czy metryki skuteczności wykrywania są rejestrowane i okresowo ponownie oceniane na podstawie aktualnych danych wywiadowczych dotyczących zagrożeń.

---

### 10.7 Dynamiczne dostosowywanie polityki bezpieczeństwa

Aktualizacje polityk bezpieczeństwa w czasie rzeczywistym oparte na wywiadzie zagrożeń i analizie zachowań.

 #10.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy dokumenty polityk bezpieczeństwa mogą być aktualizowane dynamicznie bez konieczności restartu agenta, przy jednoczesnym zachowaniu integralności wersji polityk.
 #10.7.2    Level: 2    Role: D/V
 Zweryfikuj, czy aktualizacje polityki są kryptograficznie podpisane przez upoważniony personel ds. bezpieczeństwa i potwierdzone przed zastosowaniem.
 #10.7.3    Level: 2    Role: D/V
 Zweryfikuj, czy dynamiczne zmiany polityki są rejestrowane z pełnymi śladami audytu, w tym uzasadnieniem, łańcuchami zatwierdzeń oraz procedurami wycofywania.
 #10.7.4    Level: 3    Role: D/V
 Zweryfikuj, czy adaptacyjne mechanizmy bezpieczeństwa dostosowują czułość wykrywania zagrożeń na podstawie kontekstu ryzyka i wzorców zachowań.
 #10.7.5    Level: 3    Role: D/V
 Zweryfikuj, czy decyzje dotyczące adaptacji polityki są wyjaśnialne i zawierają ścieżki dowodowe do przeglądu przez zespół ds. bezpieczeństwa.

---

### 10.8 Analiza bezpieczeństwa oparta na refleksji

Weryfikacja bezpieczeństwa poprzez autorefleksję agenta i analizę metapoznawczą.

 #10.8.1    Level: 1    Role: D/V
 Zweryfikuj, czy mechanizmy refleksji agenta obejmują samoocenę decyzji i działań z ukierunkowaniem na bezpieczeństwo.
 #10.8.2    Level: 2    Role: D/V
 Zweryfikuj, czy wyniki refleksji są walidowane, aby zapobiec manipulacji mechanizmów samooceny przez wrogie dane wejściowe.
 #10.8.3    Level: 2    Role: D/V
 Zweryfikuj, czy analiza bezpieczeństwa metapoznawczego identyfikuje potencjalne uprzedzenia, manipulacje lub naruszenia w procesach rozumowania agenta.
 #10.8.4    Level: 3    Role: D/V
 Zweryfikuj, czy ostrzeżenia dotyczące bezpieczeństwa oparte na refleksji wywołują zwiększony nadzór i potencjalne procedury interwencji ludzkiej.
 #10.8.5    Level: 3    Role: D/V
 Zweryfikuj, czy ciągłe uczenie się na podstawie analiz bezpieczeństwa poprawia wykrywanie zagrożeń bez pogarszania funkcjonalności prawidłowej.

---

### 10.9 Ewolucja i Bezpieczeństwo Samodoskonalenia

Kontrole bezpieczeństwa dla systemów agentowych zdolnych do samomodyfikacji i ewolucji.

 #10.9.1    Level: 1    Role: D/V
 Zweryfikuj, czy możliwości samomodifikacji są ograniczone do wyznaczonych bezpiecznych obszarów z formalnymi granicami weryfikacji.
 #10.9.2    Level: 2    Role: D/V
 Zweryfikuj, czy propozycje ewolucyjne przechodzą ocenę wpływu na bezpieczeństwo przed wdrożeniem.
 #10.9.3    Level: 2    Role: D/V
 Zweryfikuj, czy mechanizmy samodoskonalenia obejmują możliwości wycofania z weryfikacją integralności.
 #10.9.4    Level: 3    Role: D/V
 Zweryfikuj, czy bezpieczeństwo meta-uczenia zapobiega przeciwnym manipulacjom algorytmów poprawy.
 #10.9.5    Level: 3    Role: D/V
 Zweryfikuj, czy rekursywna samo-ulepszanie jest ograniczona formalnymi zasadami bezpieczeństwa wraz z matematycznymi dowodami zbieżności.

---

#### Referencje

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Ochrona prywatności i zarządzanie danymi osobowymi

### Cel kontroli

Utrzymuj rygorystyczne gwarancje prywatności na całym cyklu życia AI — od zbierania danych, przez trening, wnioskowanie, aż po reakcję na incydenty — tak aby dane osobowe były przetwarzane wyłącznie za wyraźną zgodą, w minimalnym niezbędnym zakresie, podlegające wykazywalnemu usunięciu oraz formalnym gwarancjom prywatności.

---

### 11.1 Anonimizacja i minimalizacja danych

 #11.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy bezpośrednie i quasi-identyfikatory zostały usunięte lub zhashowane.
 #11.1.2    Level: 2    Role: D/V
 Zweryfikuj, czy zautomatyzowane audyty mierzą k-anonimowość/l-rozmaitość i generują alert, gdy progi spadają poniżej ustalonej polityki.
 #11.1.3    Level: 2    Role: V
 Zweryfikuj, że raporty dotyczące istotności cech modelu potwierdzają brak wycieku identyfikatora przekraczającego ε = 0,01 informacji wzajemnej.
 #11.1.4    Level: 3    Role: V
 Zweryfikuj, czy formalne dowody lub certyfikacja na podstawie danych syntetycznych wykazują ryzyko ponownej identyfikacji ≤ 0,05 nawet w przypadku ataków powiązań.

---

### 11.2 Prawo do bycia zapomnianym i egzekwowanie usuwania

 #11.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy żądania usunięcia danych dotyczących podmiotu są propagowane do surowych zbiorów danych, punktów kontrolnych, wektorów osadzających, dzienników oraz kopii zapasowych w ramach umów na poziomie usług wynoszących mniej niż 30 dni.
 #11.2.2    Level: 2    Role: D
 Zweryfikuj, czy procedury "machine-unlearning" faktycznie przeprowadzają ponowne uczenie lub przybliżone usunięcie za pomocą certyfikowanych algorytmów unlearningu.
 #11.2.3    Level: 2    Role: V
 Potwierdź, że ocena modelu cieniowego wykazuje, iż zapomniane rekordy wpływają na mniej niż 1% wyników po procesie zapominania.
 #11.2.4    Level: 3    Role: V
 Zweryfikuj, czy zdarzenia usunięcia są niezmiennie rejestrowane i audytowalne dla organów regulacyjnych.

---

### 11.3 Zabezpieczenia prywatności różnicowej

 #11.3.1    Level: 2    Role: D/V
 Zweryfikuj, czy pulpity monitorujące rozliczanie utraty prywatności informują, gdy skumulowana wartość ε przekracza progi polityki.
 #11.3.2    Level: 2    Role: V
 Zweryfikuj, czy audyty prywatności typu black-box szacują ε̂ z dokładnością do 10% deklarowanej wartości.
 #11.3.3    Level: 3    Role: V
 Zweryfikuj, czy formalne dowody obejmują wszystkie dostrajania po treningu i osadzenia.

---

### 11.4 Ograniczenie celu i ochrona przed rozszerzaniem zakresu

 #11.4.1    Level: 1    Role: D
 Zweryfikuj, czy każdy zestaw danych i punkt kontrolny modelu posiada maszynowo odczytywalną etykietę celu zgodną z oryginalną zgodą.
 #11.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy monitory czasu wykonania wykrywają zapytania niezgodne z zadeklarowanym celem i wywołują miękkie odrzucenie.
 #11.4.3    Level: 3    Role: D
 Zweryfikuj, czy bramki policy-as-code blokują ponowne wdrożenie modeli do nowych domen bez przeglądu DPIA.
 #11.4.4    Level: 3    Role: V
 Zweryfikuj, że formalne dowody odtwarzalności wykazują, iż każdy cykl życia danych osobowych pozostaje w zakresie zgody.

---

### 11.5 Zarządzanie zgodą i śledzenie na podstawie prawnej

 #11.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy Platforma Zarządzania Zgodami (CMP) rejestruje status zgody, cel oraz okres przechowywania danych dla każdej osoby, której dane dotyczą.
 #11.5.2    Level: 2    Role: D
 Zweryfikuj, czy interfejsy API udostępniają tokeny zgody; modele muszą weryfikować zakres tokenu przed wykonaniem wnioskowania.
 #11.5.3    Level: 2    Role: D/V
 Zweryfikuj, czy odmowa lub wycofanie zgody zatrzymuje przetwarzanie danych w ciągu 24 godzin.

---

### 11.6 Uczenie federacyjne z kontrolą prywatności

 #11.6.1    Level: 1    Role: D
 Zweryfikuj, czy aktualizacje klienta wykorzystują lokalne dodawanie szumu z zachowaniem prywatności różnicowej przed agregacją.
 #11.6.2    Level: 2    Role: D/V
 Zweryfikuj, czy metryki treningowe są prywatne różnicowo i nigdy nie ujawniają straty pojedynczego klienta.
 #11.6.3    Level: 2    Role: V
 Zweryfikuj, czy jest włączona odporna na zatruwanie agregacja (np. Krum/Średnia przycięta).
 #11.6.4    Level: 3    Role: V
 Zweryfikuj, czy formalne dowody wykazują ogólny budżet ε z utratą użyteczności mniejszą niż 5.

---

#### Bibliografia

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Monitorowanie, rejestrowanie i wykrywanie anomalii

### Cel kontroli

Ta sekcja zawiera wymagania dotyczące zapewnienia widoczności w czasie rzeczywistym oraz w celach kryminalistycznych tego, co model i inne komponenty AI widzą, robią oraz zwracają, aby możliwe było wykrywanie, klasyfikowanie i analiza zagrożeń.

### C12.1 Rejestrowanie żądań i odpowiedzi

 #12.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie polecenia użytkownika oraz odpowiedzi modelu są rejestrowane wraz z odpowiednimi metadanymi (np. znacznik czasu, identyfikator użytkownika, identyfikator sesji, wersja modelu).
 #12.1.2    Level: 1    Role: D/V
 Zweryfikuj, czy logi są przechowywane w bezpiecznych, kontrolowanych pod względem dostępu repozytoriach z odpowiednimi politykami przechowywania i procedurami tworzenia kopii zapasowych.
 #12.1.3    Level: 1    Role: D/V
 Zweryfikuj, czy systemy przechowywania logów implementują szyfrowanie danych w stanie spoczynku oraz podczas transmisji, aby chronić wrażliwe informacje zawarte w logach.
 #12.1.4    Level: 1    Role: D/V
 Zweryfikuj, czy wrażliwe dane w zapytaniach i wynikach są automatycznie redagowane lub maskowane przed ich rejestrowaniem, z konfigurowalnymi regułami redagowania dla danych osobowych (PII), poświadczeń oraz informacji poufnych.
 #12.1.5    Level: 2    Role: D/V
 Zweryfikuj, czy decyzje polityczne i działania filtrów bezpieczeństwa są rejestrowane z wystarczającym poziomem szczegółowości, aby umożliwić audyt i debugowanie systemów moderacji treści.
 #12.1.6    Level: 2    Role: D/V
 Zweryfikuj, czy integralność dziennika jest chroniona poprzez np. podpisy kryptograficzne lub magazyn tylko do zapisu.

---

### C12.2 Wykrywanie Nadużyć i Powiadamianie

 #12.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy system wykrywa i informuje o znanych wzorcach jailbreak, próbach wstrzyknięcia poleceń oraz wrogich danych wejściowych, stosując wykrywanie oparte na sygnaturach.
 #12.2.2    Level: 1    Role: D/V
 Zweryfikuj, czy system integruje się z istniejącymi platformami Zarządzania Informacjami i Zdarzeniami Bezpieczeństwa (SIEM) za pomocą standardowych formatów dzienników i protokołów.
 #12.2.3    Level: 2    Role: D/V
 Zweryfikuj, czy wzbogacone zdarzenia bezpieczeństwa zawierają kontekst specyficzny dla AI, taki jak identyfikatory modeli, wskaźniki ufności oraz decyzje filtrów bezpieczeństwa.
 #12.2.4    Level: 2    Role: D/V
 Zweryfikuj, czy wykrywanie anomalii behawioralnych identyfikuje nietypowe wzorce rozmów, nadmierne próby ponawiania lub systematyczne zachowania sondowania.
 #12.2.5    Level: 2    Role: D/V
 Zweryfikuj, czy mechanizmy alertów w czasie rzeczywistym powiadamiają zespoły ds. bezpieczeństwa w przypadku wykrycia potencjalnych naruszeń polityki lub prób ataku.
 #12.2.6    Level: 2    Role: D/V
 Zweryfikuj, czy zawarte są niestandardowe reguły do wykrywania wzorców zagrożeń specyficznych dla sztucznej inteligencji, w tym skoordynowanych prób obejścia zabezpieczeń (jailbreak), kampanii wstrzykiwania promptów oraz ataków na ekstrakcję modeli.
 #12.2.7    Level: 3    Role: D/V
 Zweryfikuj, czy zautomatyzowane procedury reagowania na incydenty mogą izolować zaatakowane modele, blokować złośliwych użytkowników oraz eskalować krytyczne zdarzenia związane z bezpieczeństwem.

---

### C12.3 Wykrywanie dryfu modelu

 #12.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy system śledzi podstawowe metryki wydajności, takie jak dokładność, wskaźniki pewności, opóźnienia oraz wskaźniki błędów w różnych wersjach modelu i okresach czasu.
 #12.3.2    Level: 2    Role: D/V
 Zweryfikuj, czy automatyczne powiadamianie zostaje wywołane, gdy metryki wydajności przekraczają zdefiniowane wcześniej progi degradacji lub znacznie odbiegają od wartości bazowych.
 #12.3.3    Level: 2    Role: D/V
 Zweryfikuj, czy monitorowanie wykrywania halucynacji identyfikuje i oznacza przypadki, gdy wyniki modelu zawierają informacje faktograficznie nieprawidłowe, niespójne lub sfabrykowane.

---

### C12.4 Telemetria wydajności i zachowania

 #12.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy metryki operacyjne, w tym opóźnienie żądań, zużycie tokenów, użycie pamięci oraz przepustowość, są ciągle zbierane i monitorowane.
 #12.4.2    Level: 1    Role: D/V
 Zweryfikuj, czy wskaźniki sukcesu i porażki są śledzone z kategoryzacją typów błędów oraz ich przyczyn źródłowych.
 #12.4.3    Level: 2    Role: D/V
 Zweryfikuj, czy monitorowanie wykorzystania zasobów obejmuje użycie GPU/CPU, zużycie pamięci oraz wymagania dotyczące pamięci masowej, z powiadamianiem o przekroczeniu progów alarmowych.

---

### C12.5 Planowanie i realizacja reagowania na incydenty związane ze sztuczną inteligencją

 #12.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy plany reagowania na incydenty obejmują specyficznie zdarzenia związane z bezpieczeństwem AI, w tym naruszenie modelu, zatruwanie danych oraz ataki adwersarialne.
 #12.5.2    Level: 2    Role: D/V
 Zweryfikuj, czy zespoły ds. reagowania na incydenty mają dostęp do specjalistycznych narzędzi kryminalistycznych AI oraz wiedzy eksperckiej do badania zachowania modeli i wektorów ataków.
 #12.5.3    Level: 3    Role: D/V
 Zweryfikuj, czy analiza po incydencie obejmuje kwestie ponownego trenowania modelu, aktualizacje filtrów bezpieczeństwa oraz integrację wyciągniętych wniosków w kontrolach bezpieczeństwa.

---

### C12.5 Wykrywanie degradacji wydajności AI

Monitorować i wykrywać degradację wydajności i jakości modelu AI w czasie.

 #12.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy dokładność modelu, precyzja, czułość oraz miary F1 są stale monitorowane i porównywane z wartościami progowymi bazowymi.
 #12.5.2    Level: 1    Role: D/V
 Zweryfikuj, czy monitorowanie wykrywania dryfu danych śledzi zmiany rozkładu danych wejściowych, które mogą wpływać na wydajność modelu.
 #12.5.3    Level: 2    Role: D/V
 Zweryfikuj, czy detekcja dryfu koncepcji identyfikuje zmiany w relacji między danymi wejściowymi a oczekiwanymi wynikami.
 #12.5.4    Level: 2    Role: D/V
 Zweryfikuj, czy pogorszenie wydajności wywołuje automatyczne alerty i inicjuje procesy ponownego trenowania lub wymiany modelu.
 #12.5.5    Level: 3    Role: V
 Zweryfikuj, czy analiza przyczyn degradacji koreluje spadki wydajności ze zmianami danych, problemami z infrastrukturą lub czynnikami zewnętrznymi.

---

### C12.6 Wizualizacja DAG i bezpieczeństwo przepływu pracy

Chroń systemy wizualizacji przepływu pracy przed wyciekami informacji i atakami manipulacyjnymi.

 #12.6.1    Level: 1    Role: D/V
 Sprawdź, czy dane wizualizacji DAG zostały oczyszczone w celu usunięcia informacji wrażliwych przed ich przechowywaniem lub transmisją.
 #12.6.2    Level: 1    Role: D/V
 Zweryfikuj, czy kontrola dostępu do wizualizacji przepływu pracy zapewnia, że tylko upoważnieni użytkownicy mogą przeglądać ścieżki decyzji agenta oraz ślady uzasadnień.
 #12.6.3    Level: 2    Role: D/V
 Zweryfikuj, czy integralność danych DAG jest chroniona za pomocą podpisów kryptograficznych oraz mechanizmów przechowywania odpornych na manipulacje.
 #12.6.4    Level: 2    Role: D/V
 Zweryfikuj, czy systemy wizualizacji przepływu pracy implementują walidację danych wejściowych, aby zapobiec atakom typu injection poprzez spreparowane dane węzłów lub krawędzi.
 #12.6.5    Level: 3    Role: D/V
 Zweryfikuj, czy aktualizacje DAG w czasie rzeczywistym są limitowane pod względem częstotliwości oraz weryfikowane, aby zapobiec atakom typu odmowa usługi (DoS) na systemy wizualizacji.

---

### C12.7 Proaktywne Monitorowanie Zachowań Bezpieczeństwa

Wykrywanie i zapobieganie zagrożeniom bezpieczeństwa poprzez proaktywną analizę zachowań agentów.

 #12.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy proaktywne zachowania agentów są zatwierdzone pod względem bezpieczeństwa przed wykonaniem, wraz z integracją oceny ryzyka.
 #12.7.2    Level: 2    Role: D/V
 Zweryfikuj, czy inicjatywa autonomiczna obejmuje ocenę kontekstu bezpieczeństwa oraz analizę krajobrazu zagrożeń.
 #12.7.3    Level: 2    Role: D/V
 Zweryfikuj, czy wzorce zachowań proaktywnych są analizowane pod kątem potencjalnych implikacji bezpieczeństwa i niezamierzonych konsekwencji.
 #12.7.4    Level: 3    Role: D/V
 Zweryfikuj, czy krytyczne dla bezpieczeństwa działania proaktywne wymagają wyraźnych łańcuchów zatwierdzeń z ścieżkami audytu.
 #12.7.5    Level: 3    Role: D/V
 Zweryfikuj, czy wykrywanie anomalii behawioralnych identyfikuje odchylenia w wzorcach działania agentów proaktywnych, które mogą wskazywać na kompromitację.

---

### Bibliografia

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Nadzór ludzki, odpowiedzialność i zarządzanie

### Cel Kontroli

Ten rozdział określa wymagania dotyczące utrzymania nadzoru człowieka oraz jasnych łańcuchów odpowiedzialności w systemach AI, zapewniając wyjaśnialność, przejrzystość oraz etyczne zarządzanie na całym etapie życia AI.

---

### C13.1 Mechanizmy Wyłączania Awaryjnego i Przejęcia Kontroli

Zapewnij ścieżki zamknięcia lub wycofania w przypadku zaobserwowania niebezpiecznego zachowania systemu AI.

 #13.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy istnieje ręczny mechanizm awaryjnego zatrzymania, który natychmiast przerwie wnioskowanie i generowanie wyników przez model AI.
 #13.1.2    Level: 1    Role: D
 Zweryfikuj, czy kontrolki nadpisania są dostępne wyłącznie dla upoważnionego personelu.
 #13.1.3    Level: 3    Role: D/V
 Zweryfikuj, czy procedury przywracania mogą cofnąć się do poprzednich wersji modeli lub trybu bezpiecznego działania.
 #13.1.4    Level: 3    Role: V
 Sprawdź, czy mechanizmy nadpisywania są regularnie testowane.

---

### C13.2 Punkty kontrolne decyzji z udziałem człowieka

Wymagaj zatwierdzeń ludzkich, gdy stawki przekraczają zdefiniowane progi ryzyka.

 #13.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy decyzje AI o wysokim ryzyku wymagają wyraźnej zgody człowieka przed wykonaniem.
 #13.2.2    Level: 1    Role: D
 Zweryfikuj, czy progi ryzyka są jasno określone i automatycznie uruchamiają procesy przeglądu przez człowieka.
 #13.2.3    Level: 2    Role: D
 Zweryfikuj, czy decyzje wrażliwe na upływ czasu mają procedury awaryjne na wypadek, gdyby zatwierdzenie przez człowieka nie mogło zostać uzyskane w wymaganych ramach czasowych.
 #13.2.4    Level: 3    Role: D/V
 Zweryfikuj, czy procedury eskalacji definiują wyraźne poziomy uprawnień dla różnych typów decyzji lub kategorii ryzyka, jeśli ma to zastosowanie.

---

### C13.3 Łańcuch odpowiedzialności i możliwość audytu

Rejestruj działania operatora i decyzje modelu.

 #13.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy wszystkie decyzje systemu AI oraz interwencje ludzi są rejestrowane z oznaczeniem czasu, tożsamości użytkowników oraz uzasadnieniem decyzji.
 #13.3.2    Level: 2    Role: D
 Zweryfikuj, czy dzienniki audytu nie mogą być fałszowane i czy zawierają mechanizmy weryfikacji integralności.

---

### C13.4 Techniki wyjaśnialnej sztucznej inteligencji (Explainable-AI)

Ważność cech powierzchniowych, kontrfaktyczne przykłady oraz lokalne wyjaśnienia.

 #13.4.1    Level: 1    Role: D/V
 Zweryfikuj, czy systemy sztucznej inteligencji dostarczają podstawowe wyjaśnienia swoich decyzji w formacie czytelnym dla człowieka.
 #13.4.2    Level: 2    Role: V
 Zweryfikuj, czy jakość wyjaśnień jest potwierdzona poprzez badania ewaluacyjne prowadzone przez ludzi oraz odpowiednie metryki.
 #13.4.3    Level: 3    Role: D/V
 Zweryfikuj, czy oceny ważności cech lub metody atrybucji (SHAP, LIME itp.) są dostępne dla decyzji krytycznych.
 #13.4.4    Level: 3    Role: V
 Zweryfikuj, czy wyjaśnienia kontrfaktyczne pokazują, jak można zmodyfikować dane wejściowe, aby zmienić wyniki, jeśli jest to istotne dla przypadku użycia i dziedziny.

---

### C13.5 Karty modeli i ujawnienia dotyczące użytkowania

Utrzymuj karty modelu zawierające informacje o zamierzonym zastosowaniu, metrykach wydajności oraz kwestiach etycznych.

 #13.5.1    Level: 1    Role: D
 Zweryfikuj, czy karty modeli dokumentują zamierzone przypadki użycia, ograniczenia oraz znane tryby awarii.
 #13.5.2    Level: 1    Role: D/V
 Zweryfikuj, czy metryki wydajności w różnych odpowiednich przypadkach użycia są ujawnione.
 #13.5.3    Level: 2    Role: D
 Sprawdź, czy uwzględniono kwestie etyczne, oceny uprzedzeń, oceny sprawiedliwości, cechy danych szkoleniowych oraz znane ograniczenia danych szkoleniowych, a także czy są one regularnie dokumentowane i aktualizowane.
 #13.5.4    Level: 2    Role: D/V
 Zweryfikuj, czy karty modelu są wersjonowane i utrzymywane przez cały cykl życia modelu z śledzeniem zmian.

---

### C13.6 Kwantyfikacja niepewności

Propaguj wartości ufności lub miary entropii w odpowiedziach.

 #13.6.1    Level: 1    Role: D
 Zweryfikuj, czy systemy AI dostarczają współczynniki ufności lub miary niepewności wraz z ich wynikami.
 #13.6.2    Level: 2    Role: D/V
 Zweryfikuj, czy progi niepewności wywołują dodatkową kontrolę przez człowieka lub alternatywne ścieżki decyzyjne.
 #13.6.3    Level: 2    Role: V
 Zweryfikuj, czy metody kwantyfikacji niepewności są skalibrowane i zwalidowane względem danych rzeczywistych.
 #13.6.4    Level: 3    Role: D/V
 Zweryfikuj, czy propagacja niepewności jest utrzymywana przez wieloetapowe przepływy pracy AI.

---

### C13.7 Raporty Transparentności dla Użytkowników

Zapewnij okresowe ujawnienia dotyczące incydentów, dryfu i wykorzystania danych.

 #13.7.1    Level: 1    Role: D/V
 Zweryfikuj, czy zasady dotyczące wykorzystania danych oraz praktyki zarządzania zgodą użytkowników są jasno przekazywane zainteresowanym stronom.
 #13.7.2    Level: 2    Role: D/V
 Zweryfikuj, czy oceny wpływu AI są przeprowadzane, a wyniki są uwzględnione w raportowaniu.
 #13.7.3    Level: 2    Role: D/V
 Zweryfikuj, czy regularnie publikowane raporty przejrzystości ujawniają incydenty związane ze sztuczną inteligencją oraz metryki operacyjne w rozsądnym zakresie szczegółowości.

#### Bibliografia

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Aneks A: Słownik terminów

Ten obszerny glosariusz zawiera definicje kluczowych terminów związanych z AI, ML i bezpieczeństwem używanych w całym AISVS, aby zapewnić jasność i wspólne zrozumienie.
​
Przykład adwersarialny: Dane wejściowe celowo stworzone w celu wywołania błędu w modelu sztucznej inteligencji, często poprzez dodanie subtelnych zakłóceń niewidocznych dla ludzi.
​
Odporność na ataki adwersarialne – Odporność na ataki adwersarialne w sztucznej inteligencji odnosi się do zdolności modelu do utrzymania swojej wydajności oraz odporności na bycie oszukanym lub zmanipulowanym przez celowo zaprojektowane, złośliwe dane wejściowe mające na celu wywołanie błędów.
​
Agent – Agenci AI to systemy programowe wykorzystujące sztuczną inteligencję do realizacji celów i wykonywania zadań w imieniu użytkowników. Wykazują się zdolnościami rozumowania, planowania i pamięci oraz posiadają poziom autonomii pozwalający na podejmowanie decyzji, uczenie się i adaptację.
​
Sztuczna inteligencja agentowa: systemy AI, które mogą działać z pewnym stopniem autonomii w celu realizacji celów, często podejmując decyzje i podejmując działania bez bezpośredniej interwencji człowieka.
​
Kontrola dostępu oparta na atrybutach (ABAC): paradygmat kontroli dostępu, w którym decyzje dotyczące autoryzacji są podejmowane na podstawie atrybutów użytkownika, zasobu, akcji i środowiska, ocenianych w momencie zapytania.
​
Atak tylnego wejścia (Backdoor Attack): Rodzaj ataku zatruwania danych, w którym model jest trenowany, aby reagować w określony sposób na konkretne wyzwalacze, zachowując się normalnie w innych przypadkach.
​
Stronniczość: Systematyczne błędy w wynikach modeli AI, które mogą prowadzić do niesprawiedliwych lub dyskryminujących rezultatów dla niektórych grup lub w określonych kontekstach.
​
Wykorzystanie uprzedzeń: technika ataku wykorzystująca znane uprzedzenia w modelach sztucznej inteligencji do manipulowania wynikami lub efektami.
​
Cedar: język polityki i silnik Amazona do precyzyjnego zarządzania uprawnieniami, używany do wdrażania ABAC w systemach sztucznej inteligencji.
​
Łańcuch myśli: technika poprawiająca rozumowanie w modelach językowych poprzez generowanie pośrednich kroków rozumowania przed wygenerowaniem ostatecznej odpowiedzi.
​
Wyłączniki awaryjne: Mechanizmy, które automatycznie zatrzymują działanie systemu AI, gdy przekroczone zostaną określone progi ryzyka.
​
Wycieki danych: Niezamierzone ujawnienie poufnych informacji za pomocą wyników lub zachowania modelu AI.
​
Zatrucie danych: celowe uszkodzenie danych treningowych w celu naruszenia integralności modelu, często w celu wprowadzenia tylnego wejścia lub pogorszenia wydajności.
​
Prywatność różnicowa – Prywatność różnicowa to matematycznie rygorystyczne ramy umożliwiające udostępnianie informacji statystycznych o zbiorach danych przy jednoczesnej ochronie prywatności poszczególnych osób. Pozwala ona posiadaczowi danych na udostępnianie zbiorczych wzorców grupy przy ograniczaniu informacji ujawnianych o konkretnych jednostkach.
​
Osadzenia: Gęste reprezentacje wektorowe danych (tekstów, obrazów itp.), które uchwytują znaczenie semantyczne w przestrzeni o wysokim wymiarze.
​
Wyjaśnialność – Wyjaśnialność w AI to zdolność systemu sztucznej inteligencji do dostarczania zrozumiałych dla człowieka powodów swoich decyzji i prognoz, oferując wgląd w jego wewnętrzne działanie.
​
Wyjaśnialna sztuczna inteligencja (XAI): systemy AI zaprojektowane w celu dostarczania zrozumiałych dla człowieka wyjaśnień swoich decyzji i zachowań za pomocą różnych technik i ram.
​
Uczenie federacyjne: podejście do uczenia maszynowego, w którym modele są trenowane na wielu zdecentralizowanych urządzeniach posiadających lokalne próbki danych, bez wymiany samych danych.
​
Ograniczenia: ograniczenia wprowadzone w celu zapobiegania generowaniu przez systemy AI szkodliwych, stronniczych lub w inny sposób niepożądanych wyników.
​
Halucynacja – Halucynacja AI odnosi się do zjawiska, w którym model AI generuje nieprawidłowe lub wprowadzające w błąd informacje, które nie są oparte na jego danych treningowych ani na rzeczywistości faktograficznej.
​
Human-in-the-Loop (HITL): Systemy zaprojektowane tak, aby wymagały nadzoru, weryfikacji lub interwencji człowieka w kluczowych punktach decyzyjnych.
​
Infrastruktura jako Kod (IaC): Zarządzanie i dostarczanie infrastruktury za pomocą kodu zamiast procesów ręcznych, co umożliwia skanowanie pod kątem bezpieczeństwa i spójne wdrożenia.
​
Jailbreak: Techniki stosowane do obchodzenia zabezpieczeń w systemach sztucznej inteligencji, szczególnie w dużych modelach językowych, w celu tworzenia zabronionych treści.
​
Najmniejsze uprawnienia: zasada bezpieczeństwa polegająca na przyznawaniu użytkownikom i procesom tylko minimalnych niezbędnych praw dostępu.
​
LIME (Lokalne Interpretowalne Wyjaśnienia Niezależne od Modelu): Technika wyjaśniająca przewidywania dowolnego klasyfikatora uczenia maszynowego poprzez lokalne przybliżenie go modelem interpretowalnym.
​
Atak wnioskowania członkostwa: atak mający na celu ustalenie, czy konkretny punkt danych został użyty do trenowania modelu uczenia maszynowego.
​
MITRE ATLAS: Krajobraz zagrożeń przeciwnika dla systemów sztucznej inteligencji; baza wiedzy dotycząca taktyk i technik ataku na systemy AI.
​
Karta modelu – Karta modelu to dokument zawierający ustandaryzowane informacje o wydajności modelu AI, jego ograniczeniach, przeznaczeniu oraz aspektach etycznych, mające na celu promowanie przejrzystości i odpowiedzialnego rozwoju AI.
​
Model Extraction: Atak, w którym przeciwnik wielokrotnie zapytuje docelowy model, aby stworzyć funkcjonalnie podobną kopię bez autoryzacji.
​
Inwersja modelu: atak, który próbuje odtworzyć dane treningowe poprzez analizę wyników modelu.
​
Zarządzanie cyklem życia modelu – Zarządzanie cyklem życia modelu AI to proces nadzorowania wszystkich etapów istnienia modelu AI, w tym jego projektowania, rozwoju, wdrażania, monitorowania, utrzymania oraz ostatecznego wycofania, aby zapewnić jego skuteczność i zgodność z celami.
​
Zatrucie modelu: Wprowadzanie luk bezpieczeństwa lub tylnego wejścia bezpośrednio do modelu podczas procesu treningowego.
​
Kradzież modelu: Uzyskanie kopii lub przybliżenia modelu własnościowego poprzez wielokrotne zapytania.
​
System wieloagentowy: system składający się z wielu współdziałających agentów AI, z których każdy może mieć różne możliwości i cele.
​
OPA (Open Policy Agent): Otwartoźródłowy silnik polityk, który umożliwia jednolite egzekwowanie polityk w całym stosie.
​
Uczące się maszyny zachowujące prywatność (PPML): Techniki i metody trenowania oraz wdrażania modeli ML, jednocześnie chroniące prywatność danych treningowych.
​
Wstrzyknięcie promptu: Atak, w którym złośliwe instrukcje są osadzane w danych wejściowych w celu zastąpienia zamierzonego zachowania modelu.
​
RAG (Generacja wspomagana wyszukiwaniem): technika, która usprawnia duże modele językowe poprzez pobieranie istotnych informacji z zewnętrznych źródeł wiedzy przed wygenerowaniem odpowiedzi.
​
Red-Teaming: Praktyka aktywnego testowania systemów AI poprzez symulowanie ataków przeciwnika w celu identyfikacji podatności.
​
SBOM (Lista Materiałowa Oprogramowania): Formalny zapis zawierający szczegóły oraz relacje w łańcuchu dostaw różnych komponentów używanych do tworzenia oprogramowania lub modeli AI.
​
SHAP (SHapley Additive exPlanations): Podejście oparte na teorii gier do wyjaśniania wyniku dowolnego modelu uczenia maszynowego poprzez obliczenie wkładu każdej cechy w prognozę.
​
Atak na łańcuch dostaw: Kompromitacja systemu poprzez celowanie w mniej zabezpieczone elementy jego łańcucha dostaw, takie jak biblioteki zewnętrzne, zestawy danych lub modele wstępnie wytrenowane.
​
Uczenie transferowe: technika, w której model opracowany do jednego zadania jest ponownie wykorzystywany jako punkt wyjścia dla modelu do zadania drugiego.
​
Baza danych wektorowych: Specjalistyczna baza danych zaprojektowana do przechowywania wysokowymiarowych wektorów (osadzeń) i wykonywania efektywnych wyszukiwań podobieństwa.
​
Skanowanie podatności: Automatyczne narzędzia identyfikujące znane luki bezpieczeństwa w komponentach oprogramowania, w tym w ramach AI i zależnościach.
​
Znakowanie wodne: Techniki osadzania nieczytelnych znaczników w treściach generowanych przez SI w celu śledzenia ich pochodzenia lub wykrywania generacji przez SI.
​
Luka zero-day: wcześniej nieznana luka, którą atakujący mogą wykorzystać, zanim deweloperzy stworzą i wdrożą poprawkę.

## Dodatek B: Literatura

### TODO

## Aneks C: Zarządzanie Bezpieczeństwem AI i Dokumentacja

### Cel

Niniejszy dodatek przedstawia podstawowe wymagania dotyczące ustanawiania struktur organizacyjnych, polityk i procesów zarządzających bezpieczeństwem AI w całym cyklu życia systemu.

---

### AC.1 Przyjęcie Ram Zarządzania Ryzykiem AI

Zaproponować formalne ramy do identyfikacji, oceny i łagodzenia ryzyk specyficznych dla sztucznej inteligencji w całym cyklu życia systemu.

 #AC.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy metodologia oceny ryzyka specyficzna dla AI jest udokumentowana i wdrożona.
 #AC.1.2    Level: 2    Role: D
 Zweryfikuj, czy oceny ryzyka są przeprowadzane na kluczowych etapach cyklu życia AI oraz przed wprowadzeniem istotnych zmian.
 #AC.1.3    Level: 3    Role: D/V
 Zweryfikuj, czy ramy zarządzania ryzykiem są zgodne z ustalonymi standardami (np. NIST AI RMF).

---

### AC.2 Polityka i procedury bezpieczeństwa AI

Definiuj i egzekwuj organizacyjne standardy dotyczące bezpiecznego rozwoju, wdrażania i eksploatacji sztucznej inteligencji.

 #AC.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy istnieją udokumentowane polityki bezpieczeństwa AI.
 #AC.2.2    Level: 2    Role: D
 Zweryfikuj, czy polityki są przeglądane i aktualizowane przynajmniej raz w roku oraz po istotnych zmianach w krajobrazie zagrożeń.
 #AC.2.3    Level: 3    Role: D/V
 Zweryfikuj, czy polityki obejmują wszystkie kategorie AISVS oraz obowiązujące wymagania regulacyjne.

---

### AC.3 Role i obowiązki w zakresie bezpieczeństwa AI

Ustanów jasną odpowiedzialność za bezpieczeństwo AI w całej organizacji.

 #AC.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy role i odpowiedzialności związane z bezpieczeństwem AI są udokumentowane.
 #AC.3.2    Level: 2    Role: D
 Zweryfikuj, czy odpowiedzialne osoby posiadają odpowiednią wiedzę z zakresu bezpieczeństwa.
 #AC.3.3    Level: 3    Role: D/V
 Zweryfikuj, czy został powołany komitet etyki AI lub rada nadzorcza do zarządzania systemami AI o wysokim ryzyku.

---

### AC.4 Egzekwowanie Wytycznych dotyczących Etycznej Sztucznej Inteligencji

Zapewnij, że systemy sztucznej inteligencji działają zgodnie z ustalonymi zasadami etycznymi.

 #AC.4.1    Level: 1    Role: D/V
 Sprawdź, czy istnieją wytyczne etyczne dotyczące rozwoju i wdrażania AI.
 #AC.4.2    Level: 2    Role: D
 Zweryfikuj, czy istnieją mechanizmy umożliwiające wykrywanie i zgłaszanie naruszeń etycznych.
 #AC.4.3    Level: 3    Role: D/V
 Zweryfikuj, czy przeprowadzane są regularne etyczne przeglądy wdrożonych systemów AI.

---

### AC.5 Monitorowanie zgodności regulacyjnej AI

Utrzymuj świadomość i zgodność z rozwijającymi się przepisami dotyczącymi sztucznej inteligencji.

 #AC.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy istnieją procesy służące identyfikacji obowiązujących przepisów dotyczących sztucznej inteligencji.
 #AC.5.2    Level: 2    Role: D
 Zweryfikuj, czy przestrzeganie wszystkich wymogów regulacyjnych zostało ocenione.
 #AC.5.3    Level: 3    Role: D/V
 Zweryfikuj, czy zmiany regulacyjne wywołują terminowe przeglądy i aktualizacje systemów AI.

#### Bibliografia

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Aneks D: Zasady zarządzania i weryfikacji bezpiecznego kodowania wspomaganego przez AI

### Cel

Ten rozdział definiuje podstawowe kontrole organizacyjne dla bezpiecznego i skutecznego korzystania z narzędzi kodowania wspomaganego przez AI podczas tworzenia oprogramowania, zapewniając bezpieczeństwo i możliwość śledzenia w całym cyklu życia oprogramowania (SDLC).

---

### AD.1 Asystowany przez AI Bezpieczny Workflow Kodowania

Zintegruj narzędzia AI w bezpiecznym cyklu życia rozwoju oprogramowania (SSDLC) organizacji, nie osłabiając istniejących zabezpieczeń.

 #AD.1.1    Level: 1    Role: D/V
 Zweryfikuj, czy udokumentowany proces roboczy opisuje, kiedy i jak narzędzia AI mogą generować, refaktoryzować lub przeglądać kod.
 #AD.1.2    Level: 2    Role: D
 Zweryfikuj, czy przepływ pracy odpowiada każdej fazie SSDLC (projektowanie, implementacja, przegląd kodu, testowanie, wdrażanie).
 #AD.1.3    Level: 3    Role: D/V
 Zweryfikuj, czy metryki (np. gęstość podatności, średni czas wykrywania) są zbierane dla kodu wygenerowanego przez AI i porównywane do bazowych wartości uzyskanych wyłącznie przez ludzi.

---

### AD.2 Kwalifikacja narzędzi AI i modelowanie zagrożeń

Upewnij się, że narzędzia do kodowania AI są oceniane pod kątem możliwości bezpieczeństwa, ryzyka oraz wpływu na łańcuch dostaw przed ich wdrożeniem.

 #AD.2.1    Level: 1    Role: D/V
 Zweryfikuj, czy model zagrożeń dla każdego narzędzia AI identyfikuje ryzyka niewłaściwego użycia, inwersji modelu, wycieku danych oraz łańcucha zależności.
 #AD.2.2    Level: 2    Role: D
 Zweryfikuj, czy oceny narzędzi obejmują analizę statyczną/dynamiczną wszelkich lokalnych komponentów oraz ocenę punktów końcowych SaaS (TLS, uwierzytelnianie/autoryzacja, logowanie).
 #AD.2.3    Level: 3    Role: D/V
 Zweryfikuj, czy oceny są prowadzone zgodnie z uznanym ramowym schematem i są ponownie wykonywane po większych zmianach wersji.

---

### AD.3 Bezpieczne Zarządzanie Podpowiedziami i Kontekstem

Zapobiegaj wyciekowi sekretów, chronionego kodu i danych osobowych podczas tworzenia promptów lub kontekstów dla modeli AI.

 #AD.3.1    Level: 1    Role: D/V
 Zweryfikuj, czy pisemne wytyczne zabraniają przesyłania sekretów, poświadczeń lub danych sklasyfikowanych w zapytaniach.
 #AD.3.2    Level: 2    Role: D
 Zweryfikuj, czy kontrolki techniczne (redakcja po stronie klienta, zatwierdzone filtry kontekstowe) automatycznie usuwają wrażliwe elementy.
 #AD.3.3    Level: 3    Role: D/V
 Zweryfikuj, czy zapytania i odpowiedzi są tokenizowane, szyfrowane podczas przesyłania i w stanie spoczynku oraz czy okresy przechowywania są zgodne z polityką klasyfikacji danych.

---

### AD.4 Walidacja kodu wygenerowanego przez sztuczną inteligencję

Wykrywanie i usuwanie luk bezpieczeństwa wprowadzonych przez wyniki AI przed scałkowaniem lub wdrożeniem kodu.

 #AD.4.1    Level: 1    Role: D/V
 Zweryfikuj, że kod generowany przez AI jest zawsze poddawany przeglądowi przez człowieka.
 #AD.4.2    Level: 2    Role: D
 Zweryfikuj, czy automatyczne skanery (SAST/IAST/DAST) są uruchamiane przy każdym pull requeście zawierającym kod generowany przez AI oraz czy blokują scalanie przy krytycznych problemach.
 #AD.4.3    Level: 3    Role: D/V
 Zweryfikuj, czy testowanie różnicowe fuzz lub testy oparte na właściwościach potwierdzają krytyczne dla bezpieczeństwa zachowania (np. walidacja danych wejściowych, logika autoryzacji).

---

### AD.5 Wyjaśnialność i identyfikowalność sugestii kodu

Zapewnij audytorom i deweloperom wgląd w to, dlaczego zasugerowano daną opcję i jak się ona rozwijała.

 #AD.5.1    Level: 1    Role: D/V
 Zweryfikuj, czy pary zapytań/odpowiedzi są rejestrowane z identyfikatorami commitów.
 #AD.5.2    Level: 2    Role: D
 Zweryfikuj, czy deweloperzy mogą udostępniać odwołania do modeli (fragmenty treningowe, dokumentację) wspierające sugestię.
 #AD.5.3    Level: 3    Role: D/V
 Zweryfikuj, czy raporty wyjaśnialności są przechowywane wraz z artefaktami projektowymi i odwoływane w przeglądach bezpieczeństwa, spełniając zasady śledzalności określone w normie ISO/IEC 42001.

---

### AD.6 Ciągła informacja zwrotna i dopasowywanie modelu

Poprawiaj bezpieczeństwo modelu z upływem czasu, jednocześnie zapobiegając negatywnemu dryfowi.

 #AD.6.1    Level: 1    Role: D/V
 Zweryfikuj, czy deweloperzy mogą oznaczać niebezpieczne lub niezgodne z przepisami sugestie oraz czy oznaczenia te są śledzone.
 #AD.6.2    Level: 2    Role: D
 Zweryfikuj, czy skonsolidowane opinie służą do okresowego dostrajania lub generowania wspomaganego wyszukiwaniem za pomocą zweryfikowanych korpusów dotyczących bezpiecznego programowania (np. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Zweryfikuj, czy zamknięty system oceny wykonuje testy regresji po każdej dostosowaniu; metryki bezpieczeństwa muszą spełniać lub przekraczać wcześniejsze wartości odniesienia przed wdrożeniem.

---

#### Referencje

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Aneks E: Przykładowe narzędzia i frameworki

### Cel

Ten rozdział zawiera przykłady narzędzi i frameworków, które mogą wspierać implementację lub realizację określonego wymagania AISVS. Nie należy ich traktować jako rekomendacje lub poparcie ze strony zespołu AISVS lub projektu OWASP GenAI Security.

---

### AE.1 Zarządzanie danymi treningowymi i zarządzanie uprzedzeniami

Narzędzia używane do analizy danych, zarządzania i kontroli uprzedzeń.

 #AE.1.1    Section: 1.1
 Narzędzia do inwentaryzacji danych: Narzędzia do zarządzania inwentaryzacją danych, takie jak...
 #AE.1.2    Section: 1.2
 Szyfrowanie w trakcie transmisji Używaj TLS dla aplikacji opartych na HTTPS, korzystając z narzędzi takich jak openSSL i pythonowy`ssl`biblioteka.

---

### AE.2 Walidacja danych wprowadzonych przez użytkownika

Narzędzia do obsługi i weryfikacji danych wprowadzanych przez użytkownika.

 #AE.2.1    Section: 2.1
 Narzędzia do obrony przed wstrzykiwaniem promptów: korzystaj z narzędzi zabezpieczających, takich jak NeMo firmy NVIDIA lub Guardrails AI.

---

