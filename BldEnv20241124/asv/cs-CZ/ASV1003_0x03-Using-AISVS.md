# Použití AISVS

Standard pro ověřování bezpečnosti umělé inteligence (AISVS) vymezuje bezpečnostní požadavky pro moderní aplikace a služby AI, přičemž se zaměřuje na aspekty, které jsou v kontrolě vývojářů aplikací.

AISVS je určen pro všechny, kteří vyvíjejí nebo hodnotí bezpečnost AI aplikací, včetně vývojářů, architektů, bezpečnostních inženýrů a auditorů. Tato kapitola představuje strukturu a použití AISVS, včetně jeho úrovní ověřování a zamýšlených scénářů použití.

## Úrovně ověřování bezpečnosti umělé inteligence

AISVS definuje tři stupně ověřování bezpečnosti, které rostou v náročnosti. Každá úroveň přidává hloubku a složitost, což umožňuje organizacím přizpůsobit svou bezpečnostní pozici úrovni rizika jejich AI systémů.

Organizace mohou začít na úrovni 1 a postupně přecházet na vyšší úrovně, jak roste bezpečnostní zralost a expozice vůči hrozbám.

### Definice úrovní

Každý požadavek v AISVS v1.0 je přiřazen k jedné z následujících úrovní:

#### Požadavky úrovně 1

Úroveň 1 zahrnuje nejkritičtější a základní bezpečnostní požadavky. Ty se zaměřují na prevenci běžných útoků, které nezávisí na jiných předpokladech nebo zranitelnostech. Většina kontrol Úrovně 1 je buď jednoduše implementovatelná, nebo dostatečně zásadní, aby ospravedlnila vynaložené úsilí.

#### Požadavky úrovně 2

Úroveň 2 se zabývá pokročilejšími nebo méně běžnými útoky, stejně jako víceúrovňovou obranou proti rozšířeným hrozbám. Tyto požadavky mohou zahrnovat složitější logiku nebo cílit na specifické předpoklady útoku.

#### Požadavky úrovně 3

Úroveň 3 zahrnuje kontroly, které jsou obvykle obtížnější na implementaci nebo mají situanční využitelnost. Tyto často představují mechanismy obrany v hloubce nebo zmírnění proti specifickým, cíleným či vysoce složitým útokům.

### Role (D/V)

Každý požadavek AISVS je označen podle hlavního publika:

* D – Požadavky zaměřené na vývojáře
* V – Požadavky zaměřené na ověřovatele/auditora
* D/V – Relevantní jak pro vývojáře, tak pro ověřovatele

