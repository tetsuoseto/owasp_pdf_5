# Använda AISVS

Den artificiella intelligensens säkerhetsverifieringsstandard (AISVS) definierar säkerhetskrav för moderna AI-applikationer och tjänster, med fokus på aspekter som utvecklare av applikationer kan kontrollera.

AISVS är avsedd för alla som utvecklar eller utvärderar säkerheten i AI-applikationer, inklusive utvecklare, arkitekter, säkerhetsingenjörer och revisorer. Detta kapitel introducerar strukturen och användningen av AISVS, inklusive dess verifieringsnivåer och avsedda användningsområden.

## Verifieringsnivåer för säkerhet inom artificiell intelligens

AISVS definierar tre stigande nivåer av säkerhetsverifiering. Varje nivå tillför djup och komplexitet, vilket gör det möjligt för organisationer att anpassa sin säkerhetsnivå efter risknivån för deras AI-system.

Organisationer kan börja på nivå 1 och successivt anta högre nivåer i takt med att säkerhetsmognad och hotexponering ökar.

### Definition av nivåerna

Varje krav i AISVS v1.0 tilldelas en av följande nivåer:

#### Krav för nivå 1

Nivå 1 inkluderar de mest kritiska och grundläggande säkerhetskraven. Dessa fokuserar på att förebygga vanliga attacker som inte är beroende av andra förutsättningar eller sårbarheter. De flesta kontroller på nivå 1 är antingen enkla att implementera eller tillräckligt viktiga för att motivera insatsen.

#### Krav på nivå 2

Nivå 2 hanterar mer avancerade eller mindre vanliga attacker samt flerskiktade försvar mot utbredda hot. Dessa krav kan innebära mer komplex logik eller riktade attacker mot specifika förutsättningar.

#### Krav på nivå 3

Nivå 3 inkluderar kontroller som vanligtvis är svårare att implementera eller som är situationellt tillämpliga. Dessa representerar ofta försvar-i-djupet-mekanismer eller åtgärder mot nischade, riktade eller högkomplexa attacker.

### Roll (D/V)

Varje AISVS-krav är markerat enligt den primära målgruppen:

* D – Krav fokuserade på utvecklare
* V – Verifierar-/revisorinriktade krav
* D/V – Relevant för både utvecklare och verifierare

