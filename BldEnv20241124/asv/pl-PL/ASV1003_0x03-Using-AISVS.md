# Używanie AISVS

Standard Weryfikacji Bezpieczeństwa Sztucznej Inteligencji (AISVS) definiuje wymagania bezpieczeństwa dla nowoczesnych aplikacji i usług AI, koncentrując się na aspektach pozostających pod kontrolą twórców aplikacji.

AISVS jest przeznaczony dla wszystkich osób opracowujących lub oceniających bezpieczeństwo aplikacji AI, w tym deweloperów, architektów, inżynierów bezpieczeństwa oraz audytorów. Ten rozdział przedstawia strukturę i sposób użycia AISVS, w tym jego poziomy weryfikacji oraz zamierzone przypadki użycia.

## Poziomy weryfikacji bezpieczeństwa sztucznej inteligencji

AISVS definiuje trzy rosnące poziomy weryfikacji bezpieczeństwa. Każdy poziom dodaje głębię i złożoność, umożliwiając organizacjom dostosowanie swojego stanowiska bezpieczeństwa do poziomu ryzyka ich systemów sztucznej inteligencji.

Organizacje mogą zaczynać od Poziomu 1 i stopniowo przechodzić na wyższe poziomy wraz ze wzrostem dojrzałości zabezpieczeń i ekspozycji na zagrożenia.

### Definicja poziomów

Każdemu wymaganiu w AISVS w wersji 1.0 przypisany jest jeden z następujących poziomów:

#### Wymagania poziomu 1

Poziom 1 obejmuje najważniejsze i podstawowe wymagania bezpieczeństwa. Skupiają się one na zapobieganiu powszechnym atakom, które nie opierają się na innych warunkach wstępnych ani podatnościach. Większość kontroli na poziomie 1 jest albo prosta do wdrożenia, albo na tyle istotna, że uzasadnia wysiłek.

#### Wymagania poziomu 2

Poziom 2 odnosi się do bardziej zaawansowanych lub mniej powszechnych ataków, a także do wielowarstwowej obrony przed rozpowszechnionymi zagrożeniami. Wymagania te mogą obejmować bardziej złożoną logikę lub celować w określone warunki wstępne ataku.

#### Wymagania poziomu 3

Poziom 3 obejmuje kontrole, które zazwyczaj są trudniejsze do wdrożenia lub mają zastosowanie w określonych sytuacjach. Często reprezentują one mechanizmy wielowarstwowej obrony lub środki zaradcze przeciwko niszowym, ukierunkowanym lub wysoce złożonym atakom.

### Rola (D/V)

Każde wymaganie AISVS jest oznaczone zgodnie z główną grupą odbiorców:

* D – Wymagania skoncentrowane na deweloperze
* V – Wymagania ukierunkowane na weryfikatora/audytora
* D/V – Istotne zarówno dla deweloperów, jak i weryfikatorów

