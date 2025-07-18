## Přední obálka

### O standardu

Standard pro ověřování bezpečnosti umělé inteligence (AISVS) je katalog bezpečnostních požadavků vytvářený komunitou, který mohou využít datoví vědci, inženýři MLOps, softwaroví architekti, vývojáři, testeři, bezpečnostní odborníci, dodavatelé nástrojů, regulátoři a uživatelé k navrhování, vytváření, testování a ověřování důvěryhodných systémů a aplikací využívajících umělou inteligenci. Poskytuje společný jazyk pro specifikaci bezpečnostních kontrol v celém životním cyklu AI — od sběru dat a vývoje modelů po nasazení a průběžné monitorování — aby organizace mohly měřit a zlepšovat odolnost, ochranu soukromí a bezpečnost svých AI řešení.

### Autorská práva a licence

Verze 0.1 (První veřejná verze - Práce v průběhu), 2025  

![license](images/license.png)
Autorská práva © 2025 Projekt AISVS.  

Uvolněno podCreative Commons Attribution‑ShareAlike 4.0 International License.
Pro jakékoli opětovné použití nebo distribuci musíte jasně sdělit podmínky licence této práce ostatním.

### Vedoucí projektů

Jim Manico
Aras “Russ” Memisyazici

### Přispěvatelé a recenzenti

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS je zbrusu nový standard vytvořený speciálně k řešení jedinečných bezpečnostních výzev systémů umělé inteligence. I když čerpá inspiraci z obecnějších osvědčených bezpečnostních postupů, každý požadavek v AISVS byl vyvinut od základu tak, aby odpovídal bezpečnostnímu prostředí umělé inteligence a pomáhal organizacím budovat bezpečnější a odolnější AI řešení.

## Předmluva

Vítejte u normy pro ověřování bezpečnosti umělé inteligence (AISVS) verze 1.0!

### Úvod

Založena v roce 2025 díky společnému úsilí komunity, AISVS definuje bezpečnostní požadavky, které je třeba zohlednit při navrhování, vývoji, nasazování a provozu moderních AI modelů, pipeline a služeb podporovaných umělou inteligencí.

AISVS verze 1.0 představuje společnou práci vedoucích projektu, pracovní skupiny a širší komunity přispěvatelů s cílem vytvořit pragmatický, testovatelný základ pro zabezpečení AI systémů.

Naším cílem s tímto vydáním je učinit AISVS snadno přijatelným při zachování ostré zaměřenosti na jeho definovaný rozsah a řešení rychle se vyvíjejícího rizikového prostředí jedinečného pro AI.

### Klíčové cíle pro AISVS Verze 1.0

Verze 1.0 bude vytvořena na základě několika základních principů.

#### Dobře definovaný rozsah

Každý požadavek musí být v souladu s názvem a posláním AISVS:

Umělá inteligence – Kontroly fungují na vrstvě AI/ML (data, model, pipeline nebo inference) a jsou odpovědností odborníků na AI.
Bezpečnost – Požadavky přímo zmírňují identifikovaná rizika v oblasti bezpečnosti, ochrany soukromí nebo bezpečnosti uživatelů.
Ověření – Jazyk je napsán tak, aby byla shoda objektivně ověřitelná.
Standard – Oddíly následují konzistentní strukturu a terminologii, aby vytvořily soudržný referenční rámec.
​
---

Dodržováním AISVS mohou organizace systematicky hodnotit a posilovat bezpečnostní postoj svých AI řešení, čímž podporují kulturu bezpečného inženýrství AI.

## Použití AISVS

Standard pro ověřování bezpečnosti umělé inteligence (AISVS) vymezuje bezpečnostní požadavky pro moderní aplikace a služby AI, přičemž se zaměřuje na aspekty, které jsou v kontrolě vývojářů aplikací.

AISVS je určen pro všechny, kteří vyvíjejí nebo hodnotí bezpečnost AI aplikací, včetně vývojářů, architektů, bezpečnostních inženýrů a auditorů. Tato kapitola představuje strukturu a použití AISVS, včetně jeho úrovní ověřování a zamýšlených scénářů použití.

### Úrovně ověřování bezpečnosti umělé inteligence

AISVS definuje tři stupně ověřování bezpečnosti, které rostou v náročnosti. Každá úroveň přidává hloubku a složitost, což umožňuje organizacím přizpůsobit svou bezpečnostní pozici úrovni rizika jejich AI systémů.

Organizace mohou začít na úrovni 1 a postupně přecházet na vyšší úrovně, jak roste bezpečnostní zralost a expozice vůči hrozbám.

#### Definice úrovní

Každý požadavek v AISVS v1.0 je přiřazen k jedné z následujících úrovní:

 Požadavky úrovně 1

Úroveň 1 zahrnuje nejkritičtější a základní bezpečnostní požadavky. Ty se zaměřují na prevenci běžných útoků, které nezávisí na jiných předpokladech nebo zranitelnostech. Většina kontrol Úrovně 1 je buď jednoduše implementovatelná, nebo dostatečně zásadní, aby ospravedlnila vynaložené úsilí.

 Požadavky úrovně 2

Úroveň 2 se zabývá pokročilejšími nebo méně běžnými útoky, stejně jako víceúrovňovou obranou proti rozšířeným hrozbám. Tyto požadavky mohou zahrnovat složitější logiku nebo cílit na specifické předpoklady útoku.

 Požadavky úrovně 3

Úroveň 3 zahrnuje kontroly, které jsou obvykle obtížnější na implementaci nebo mají situanční využitelnost. Tyto často představují mechanismy obrany v hloubce nebo zmírnění proti specifickým, cíleným či vysoce složitým útokům.

#### Role (D/V)

Každý požadavek AISVS je označen podle hlavního publika:

D – Požadavky zaměřené na vývojáře
V – Požadavky zaměřené na ověřovatele/auditora
D/V – Relevantní jak pro vývojáře, tak pro ověřovatele

## Správa tréninkových dat C1 a řízení zkreslení

### Řídicí cíl

Tréninková data musí být získávána, zpracovávána a udržována tak, aby byla zachována jejich původnost, bezpečnost, kvalita a spravedlnost. Tím se plní zákonné povinnosti a snižují rizika zaujatosti, otravy dat nebo porušení soukromí během celého životního cyklu umělé inteligence.

---

### C1.1 Původ tréninkových dat

Udržujte ověřitelný inventář všech datasetů, akceptujte pouze důvěryhodné zdroje a zaznamenávejte každou změnu pro audituovatelnost.

 #1.1.1    Level: 1    Role: D/V
 Ověřte, že je udržován aktuální seznam všech zdrojů tréninkových dat (původ, správce/vlastník, licence, způsob sběru, omezení zamýšleného použití a historie zpracování).
 #1.1.2    Level: 1    Role: D/V
 Ověřte, že jsou povolena pouze datová soubory ověřená z hlediska kvality, reprezentativnosti, etického původu a souladu s licencí, čímž se snižují rizika otravy daty, vestavěných předsudků a porušení duševního vlastnictví.
 #1.1.3    Level: 1    Role: D/V
 Ověřte, že je uplatňováno minimalizování dat, aby byly vyloučeny zbytečné nebo citlivé atributy.
 #1.1.4    Level: 2    Role: D/V
 Ověřte, že všechny změny v datovém souboru podléhají schválenému schématu pracovního postupu se záznamem.
 #1.1.5    Level: 2    Role: D/V
 Ověřte, že kvalita označování/annotace je zajištěna prostřednictvím křížové kontroly recenzenty nebo konsensem.
 #1.1.6    Level: 2    Role: D/V
 Ověřte, že pro významné tréninkové datové sady jsou udržovány "datové karty" nebo "datasheety pro datové sady", které podrobně popisují charakteristiky, motivace, složení, procesy sběru, předzpracování a doporučené/nedoporučené použití.

---

### C1.2 Bezpečnost a integrita tréninkových dat

Omezte přístup, šifrujte data v klidu i během přenosu a ověřujte integritu, aby se zabránilo manipulaci nebo krádeži.

 #1.2.1    Level: 1    Role: D/V
 Ověřte, že přístupové kontroly chrání úložiště a pipeline.
 #1.2.2    Level: 2    Role: D/V
 Ověřte, že datové soubory jsou během přenosu šifrovány a u veškerých citlivých nebo osobně identifikovatelných informací (PII) také v klidu, přičemž jsou použity kryptografické algoritmy odpovídající průmyslovým standardům a postupy správy klíčů.
 #1.2.3    Level: 2    Role: D/V
 Ověřte, že k zajištění integrity dat během ukládání a přenosu jsou používány kryptografické hashovací funkce nebo digitální podpisy, a že jsou aplikovány automatizované techniky detekce anomálií k ochraně proti nepovoleným úpravám nebo poškození, včetně cílených pokusů o otrávení dat.
 #1.2.4    Level: 3    Role: D/V
 Ověřte, že verze datasetu jsou sledovány, aby bylo možné provést návrat zpět.
 #1.2.5    Level: 2    Role: D/V
 Ověřte, že zastaralá data jsou bezpečně vymazána nebo anonymizována v souladu s politikami uchovávání dat, regulačními požadavky a za účelem zmenšení povrchu útoku.

---

### C1.3 Úplnost a spravedlnost reprezentace

Detekujte demografické odchylky a aplikujte opatření ke zmírnění, aby míra chyb modelu byla spravedlivá napříč skupinami.

 #1.3.1    Level: 1    Role: D/V
 Ověřte, zda jsou datové sady analyzovány z hlediska nerovnováhy v zastoupení a potenciálních zkreslení napříč zákonem chráněnými atributy (např. rasa, pohlaví, věk) a dalšími eticky citlivými charakteristikami relevantními pro oblast použití modelu (např. socioekonomický status, lokalita).
 #1.3.2    Level: 2    Role: D/V
 Ověřte, že identifikované předpojatosti jsou zmírněny pomocí zdokumentovaných strategií, jako je vyvážení, cílená augmentace dat, algoritmické úpravy (např. techniky předzpracování, zpracování v průběhu, následné zpracování) nebo převažování, a že je posouzen dopad těchto opatření na spravedlnost i celkový výkon modelu.
 #1.3.3    Level: 2    Role: D/V
 Ověřte, že metriky spravedlnosti po tréninku jsou vyhodnoceny a zdokumentovány.
 #1.3.4    Level: 3    Role: D/V
 Ověřte, že politika správy životního cyklu zkreslení přiřazuje vlastníky a frekvenci přehledů.

---

### C1.4 Kvalita, integrita a bezpečnost označování tréninkových dat

Chraňte štítky šifrováním a vyžadujte dvojí kontrolu u kritických tříd.

 #1.4.1    Level: 2    Role: D/V
 Ověřte, že kvalita označování/komentování je zajištěna prostřednictvím jasných pokynů, vzájemných kontrol recenzentů, mechanismů dosažení konsensu (např. sledování shody mezi anotátory) a definovaných procesů pro řešení nesrovnalostí.
 #1.4.2    Level: 2    Role: D/V
 Ověřte, že kryptografické haše nebo digitální podpisy jsou aplikovány na označení artefaktů, aby byla zajištěna jejich integrita a autenticita.
 #1.4.3    Level: 2    Role: D/V
 Ověřte, že rozhraní a platformy pro označování zajišťují přísné přístupové kontroly, udržují nezfalšovatelné auditní záznamy všech aktivit označování a chrání před neoprávněnými úpravami.
 #1.4.4    Level: 3    Role: D/V
 Ověřte, že označení kritická pro bezpečnost, zabezpečení nebo spravedlnost (např. identifikace toxického obsahu, zásadních lékařských nálezů) podléhají povinnému nezávislému dvojímu přezkumu nebo ekvivalentní robustní verifikaci.
 #1.4.5    Level: 2    Role: D/V
 Ověřte, že citlivé informace (včetně identifikovatelných osobních údajů - PII), které byly neúmyslně zachyceny nebo nezbytně přítomny v označeních, jsou při uložení i přenosu odstraněny, pseudonymizovány, anonymizovány nebo zašifrovány v souladu s principy minimalizace dat.
 #1.4.6    Level: 2    Role: D/V
 Ověřte, že návody k označování a pokyny jsou komplexní, řízené verzemi a revidované vrstevníky.
 #1.4.7    Level: 2    Role: D/V
 Ověřte, že datové schémata (včetně štítků) jsou jasně definována a řízena verzováním.
 #1.8.2    Level: 2    Role: D/V
 Ověřte, že zpracování označování, které je outsourcováno nebo zajišťováno prostřednictvím crowdsourcingu, obsahuje technická a procedurální opatření k zajištění důvěrnosti dat, integrity, kvality štítků a prevenci úniku dat.

---

### C1.5 Zajištění kvality tréninkových dat

Kombinujte automatizovanou validaci, manuální náhodné kontroly a zaznamenané opravy, aby byla zajištěna spolehlivost datové sady.

 #1.5.1    Level: 1    Role: D
 Ověřte, že automatizované testy zachycují chyby formátu, nulové hodnoty a posuny štítků při každém příjmu dat nebo významné transformaci.
 #1.5.2    Level: 1    Role: D/V
 Ověřte, že neúspěšné datové sady jsou izolovány s auditními stopami.
 #1.5.3    Level: 2    Role: V
 Ověřte, že manuální náhodné kontroly prováděné odborníky na danou oblast pokrývají statisticky významný vzorek (např. ≥1 % nebo 1 000 vzorků, podle toho, co je větší, nebo podle určení hodnocením rizik) k identifikaci jemných problémů s kvalitou, které nejsou zachyceny automatizací.
 #1.5.4    Level: 2    Role: D/V
 Ověřte, že kroky nápravy jsou připojeny k záznamům o původu.
 #1.5.5    Level: 2    Role: D/V
 Ověřte, že kvalitní brány blokují nekvalitní datové sady, pokud nejsou schváleny výjimky.

---

### C1.6 Detekce otravy dat

Použijte statistickou detekci anomálií a pracovní postupy karantény k zastavení protivníkových vložení.

 #1.6.1    Level: 2    Role: D/V
 Ověřte, že techniky detekce anomálií (např. statistické metody, detekce odlehlých dat, analýza embeddingů) jsou aplikovány na tréninková data při jejich příjmu a před hlavními tréninkovými běhy za účelem identifikace potenciálních útoků otravy dat nebo neúmyslné korupce dat.
 #1.6.2    Level: 2    Role: D/V
 Ověřte, že označené vzorky vyvolávají ruční kontrolu před tréninkem.
 #1.6.3    Level: 2    Role: V
 Ověřte, že výsledky jsou začleněny do bezpečnostního spisu modelu a informují průběžnou hrozbu inteligence.
 #1.6.4    Level: 3    Role: D/V
 Ověřte, že detekční logika je aktualizována s novými informacemi o hrozbách.
 #1.6.5    Level: 3    Role: D/V
 Ověřte, že online učební pipelines sledují změnu rozdělení (distribution drift).
 #1.6.6    Level: 3    Role: D/V
 Ověřte, že jsou zohledněny a implementovány konkrétní obrany proti známým typům útoků na otravu dat (např. převracení štítků, vkládání spouštěčů zadních vrátek, útoky pomocí vlivných instancí) na základě profilu rizik systému a zdrojů dat.

---

### C1.7 Mazání uživatelských dat a vynucování souhlasu

Respektujte požadavky na vymazání a odvolání souhlasu napříč datovými sadami, zálohami a odvozenými artefakty.

 #1.7.1    Level: 1    Role: D/V
 Ověřte, že pracovní postupy mazání odstraňují primární a odvozená data a posuďte dopad na modely, a že dopad na postižené modely je vyhodnocen a v případě potřeby řešen (například zpětným učením nebo překalibrací).
 #1.7.2    Level: 2    Role: D
 Ověřte, že existují mechanismy pro sledování a respektování rozsahu a stavu uživatelského souhlasu (a jeho odvolání) pro data používaná při tréninku, a že je souhlas ověřován před zařazením dat do nových tréninkových procesů nebo významných aktualizací modelu.
 #1.7.3    Level: 2    Role: V
 Ověřte, že pracovní postupy jsou testovány každoročně a zaznamenávány.

---

### C1.8 Bezpečnost dodavatelského řetězce

Provádějte ověřování externích poskytovatelů dat a ověřujte integritu přes autentizované, šifrované kanály.

 #1.8.1    Level: 2    Role: D/V
 Ověřte, že dodavatelé dat třetích stran, včetně poskytovatelů předem natrénovaných modelů a externích datových sad, procházejí kontrolou bezpečnosti, ochrany soukromí, etického získávání a kvality dat před tím, než jsou jejich data nebo modely integrovány.
 #1.8.2    Level: 1    Role: D
 Ověřte, zda externí převody používají TLS/autentizaci a kontroly integrity.
 #1.8.3    Level: 2    Role: D/V
 Ověřte, že zdroje dat s vysokým rizikem (např. otevřené datové sady s neznámým původem, nesrovnaní dodavatelé) jsou před použitím v citlivých aplikacích podrobeny zvýšené kontrole, jako je izolovaná analýza (sandboxing), rozsáhlé kontroly kvality a zaujatosti a cílená detekce otravy dat.
 #1.8.4    Level: 3    Role: D/V
 Ověřte, že předem vytrénované modely získané od třetích stran jsou hodnoceny z hlediska zabudovaných předsudků, potenciálních zadních vrátek, integrity jejich architektury a původu původních tréninkových dat před doladěním nebo nasazením.

---

### C1.9 Detekce adversariálních vzorků

Implementujte opatření během fáze tréninku, jako je adversariální trénink, aby se zvýšila odolnost modelu proti adversariálním příkladům.

 #1.9.1    Level: 3    Role: D/V
 Ověřte, že jsou implementovány a laděny vhodné obranné mechanismy, jako je adversariální trénink (používání generovaných adversariálních příkladů), rozšíření dat s porušenými vstupy nebo techniky robustní optimalizace, pro relevantní modely na základě hodnocení rizik.
 #1.9.2    Level: 2    Role: D/V
 Ověřte, že pokud je použito protivníkové trénování, je generování, správa a verzování protivníkových datových sad zdokumentováno a kontrolováno.
 #1.9.3    Level: 3    Role: D/V
 Zajistěte, aby byl vliv tréninku odolnosti vůči nepřátelským útokům na výkon modelu (proti jak čistým, tak nepřátelským vstupům) a metriky spravedlnosti vyhodnocován, dokumentován a monitorován.
 #1.9.4    Level: 3    Role: D/V
 Ověřte, že strategie pro adversariální trénink a robustnost jsou pravidelně přezkoumávány a aktualizovány, aby se zabránilo vyvíjejícím se technikám adversariálních útoků.

---

### C1.10 Sledovatelnost a původ dat

Sledujte celou cestu každého datového bodu od zdroje až po vstup modelu pro auditovatelnost a reakci na incidenty.

 #1.10.1    Level: 2    Role: D/V
 Ověřte, že linie každého datového bodu, včetně všech transformací, augmentací a sloučení, je zaznamenána a může být rekonstruována.
 #1.10.2    Level: 2    Role: D/V
 Ověřte, že záznamy o původu jsou neměnné, bezpečně uloženy a dostupné pro audity nebo vyšetřování.
 #1.10.3    Level: 2    Role: D/V
 Ověřte, že sledování původu pokrývá jak surová, tak syntetická data.

---

### C1.11 Správa syntetických dat

Zajistěte, aby byla syntetická data řádně spravována, označována a oceněna z hlediska rizik.

 #1.11.1    Level: 2    Role: D/V
 Ověřte, že všechna syntetická data jsou jasně označena a rozlišitelná od skutečných dat v celém procesu.
 #1.11.2    Level: 2    Role: D/V
 Ověřte, že proces generování, parametry a zamýšlené použití syntetických dat jsou zdokumentovány.
 #1.11.3    Level: 2    Role: D/V
 Ověřte, že syntetická data jsou před použitím při tréninku hodnocena z hlediska rizik týkajících se zkreslení, úniku soukromých informací a problémů s reprezentací.

---

### C1.12 Monitorování přístupu k datům a detekce anomálií

Monitorujte a upozorňujte na neobvyklý přístup k tréninkovým datům k detekci vnitřních hrozeb nebo exfiltrace.

 #1.12.1    Level: 2    Role: D/V
 Ověřte, že všechny přístupy k tréninkovým datům jsou zaznamenány, včetně uživatele, času a provedené akce.
 #1.12.2    Level: 2    Role: D/V
 Ověřte, že jsou přístupové záznamy pravidelně kontrolovány kvůli neobvyklým vzorcům, jako jsou velké exporty nebo přístupy z nových míst.
 #1.12.3    Level: 2    Role: D/V
 Ověřte, že jsou generovány upozornění na podezřelé přístupy a že jsou tyto události neprodleně vyšetřovány.

---

### C1.13 Zásady uchovávání a vypršení platnosti dat

Definujte a vynucujte doby uchovávání dat, aby se minimalizovalo zbytečné ukládání dat.

 #1.13.1    Level: 1    Role: D/V
 Ověřte, že pro všechna tréninková data jsou definovány explicitní doby uchovávání.
 #1.13.2    Level: 2    Role: D/V
 Ověřte, zda jsou datové sady automaticky ukončeny, smazány nebo přezkoumány k odstranění na konci jejich životního cyklu.
 #1.13.3    Level: 2    Role: D/V
 Ověřte, že akce uchovávání a mazání jsou zaznamenávány a auditovatelné.

---

### C1.14 Soulad s předpisy a jurisdikcí

Zajistěte, aby všechna tréninková data byla v souladu s platnými zákony a předpisy.

 #1.14.1    Level: 2    Role: D/V
 Ověřte, že požadavky na umístění dat a přeshraniční přenos jsou identifikovány a uplatňovány pro všechny datové sady.
 #1.14.2    Level: 2    Role: D/V
 Ověřte, že jsou identifikovány a řešeny předpisy specifické pro daný sektor (např. zdravotnictví, finance) při zpracování dat.
 #1.14.3    Level: 2    Role: D/V
 Ověřte, že dodržování příslušných zákonů o ochraně osobních údajů (např. GDPR, CCPA) je dokumentováno a pravidelně přezkoumáváno.

---

### C1.15 Vodoznaky a otiskování dat

Detekce neoprávněného opětovného použití nebo úniku vlastních či citlivých dat.

 #1.15.1    Level: 3    Role: D/V
 Ověřte, že datové sady nebo jejich podmnožiny jsou opatřeny vodoznakem nebo otiskem tam, kde je to možné.
 #1.15.2    Level: 3    Role: D/V
 Ověřte, že metody vodotisku/otisků prstů nezavádějí zkreslení ani rizika pro soukromí.
 #1.15.3    Level: 3    Role: D/V
 Ověřte, že jsou prováděny pravidelné kontroly za účelem detekce neoprávněného znovupoužití nebo úniku dat s vodoznakem.

---

### C1.16 Řízení práv subjektů údajů

Podporovat práva subjektů údajů, jako je přístup, oprava, omezení a námitky.

 #1.16.1    Level: 2    Role: D/V
 Ověřte, že existují mechanismy pro reakci na žádosti subjektů údajů o přístup, opravu, omezení nebo námitku.
 #1.16.2    Level: 2    Role: D/V
 Ověřte, že požadavky jsou zaznamenávány, sledovány a vyřizovány v zákonem stanovených lhůtách.
 #1.16.3    Level: 2    Role: D/V
 Ověřte, že procesy práv subjektů údajů jsou pravidelně testovány a přezkoumávány z hlediska účinnosti.

---

### C1.17 Analýza dopadu verze datové sady

Před aktualizací nebo výměnou verzí posuďte dopad změn v datové sadě.

 #1.17.1    Level: 2    Role: D/V
 Ověřte, že je provedena analýza dopadů před aktualizací nebo nahrazením verze datové sady, zahrnující výkon modelu, spravedlnost a soulad s předpisy.
 #1.17.2    Level: 2    Role: D/V
 Ověřte, že výsledky analýzy dopadů jsou zdokumentovány a přezkoumány příslušnými zainteresovanými stranami.
 #1.17.3    Level: 2    Role: D/V
 Ověřte, že existují plány na návrat zpět pro případ, že nové verze přinesou nepřijatelné rizika nebo nežádoucí regrese.

---

### C1.18 Bezpečnost pracovní síly pro anotaci dat

Zajistěte bezpečnost a integritu personálu zapojeného do anotace dat.

 #1.18.1    Level: 2    Role: D/V
 Ověřte, že všichni zaměstnanci zapojení do anotace dat prošli kontrolou minulosti a byli školeni v oblasti bezpečnosti dat a ochrany soukromí.
 #1.18.2    Level: 2    Role: D/V
 Ověřte, že veškerý personál provádějící anotace podepíše dohody o důvěrnosti a mlčenlivosti.
 #1.18.3    Level: 2    Role: D/V
 Ověřte, že platformy pro anotaci vynucují přístupová omezení a monitorují hrozby zevnitř organizace.

---

### Reference

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

## C2 Validace vstupu uživatele

### Řídicí cíl

Robustní validace uživatelského vstupu je první linií obrany proti některým z nejničivějších útoků na AI systémy. Útoky založené na injektáži promptů mohou přepsat systémové instrukce, zpřístupnit citlivá data nebo nasměrovat model k nežádoucímu chování. Pokud nejsou zavedeny speciální filtry a hierarchie instrukcí, výzkumy ukazují, že „multi-shot“ jailbreaky využívající velmi dlouhá kontextová okna budou účinné. Také jemné adversariální narušení – jako jsou výměny homoglyphů nebo leetspeak – mohou tiše ovlivnit rozhodnutí modelu.

---

### C2.1 Ochrana proti injekci promptu

Vstřikování pokynů (prompt injection) je jedním z největších rizik pro systémy umělé inteligence. Obrana proti této taktice využívá kombinaci statických vzorových filtrů, dynamických klasifikátorů a prosazování hierarchie pokynů.

 #2.1.1    Level: 1    Role: D/V
 Ověřte, že vstupy uživatelů jsou kontrolovány proti průběžně aktualizované knihovně známých vzorů pro injektování promptů (klíčová slova pro jailbreak, "ignorovat předchozí", řetězce hraní rolí, nepřímé HTML/URL útoky).
 #2.1.2    Level: 1    Role: D/V
 Ověřte, že systém vynucuje hierarchii instrukcí, ve které zprávy systému nebo vývojáře přepisují instrukce uživatele, a to i po rozšíření kontextového okna.
 #2.1.3    Level: 2    Role: D/V
 Ověřte, že testy protivníkového hodnocení (např. "many-shot" podněty Red Teamu) jsou prováděny před každým uvolněním modelu nebo šablony podnětů, s prahovými hodnotami úspěšnosti a automatickými blokátory pro regrese.
 #2.1.4    Level: 2    Role: D
 Ověřte, že výzvy pocházející z obsahu třetích stran (webové stránky, PDF, e-maily) jsou vyčištěny v izolovaném kontextu parsování před jejich sloučením do hlavní výzvy.
 #2.1.5    Level: 3    Role: D/V
 Ověřte, že všechny aktualizace pravidel filtrování promptů, verze modelů klasifikátoru a změny seznamu blokování jsou spravovány verzemi a jsou auditovatelné.

---

### C2.2 Odolnost proti adversariálním příkladům

Modely zpracování přirozeného jazyka (NLP) jsou stále zranitelné vůči jemným perturbacím na úrovni znaků nebo slov, které lidé často přehlédnou, avšak modely je mají tendenci nesprávně klasifikovat.

 #2.2.1    Level: 1    Role: D
 Ověřte, že základní kroky normalizace vstupu (Unicode NFC, mapování homoglyphů, ořezávání mezer) probíhají před tokenizací.
 #2.2.2    Level: 2    Role: D/V
 Ověřte, že detekce statistických anomálií označuje vstupy s neobvykle vysokou editační vzdáleností od jazykových norem, nadměrným opakováním tokenů nebo abnormálními vzdálenostmi embedování.
 #2.2.3    Level: 2    Role: D
 Ověřte, že inference pipeline podporuje volitelné varianty modelů zesílených pomocí tréninku proti útokům (adversariální trénink) nebo obranné vrstvy (např. randomizace, obranná destilace) pro vysoce rizikové koncové body.
 #2.2.4    Level: 2    Role: V
 Ověřte, že podezřelé protivníkové vstupy jsou izolovány, zaznamenány s úplnými daty (po odstranění osobních identifikačních údajů).
 #2.2.5    Level: 3    Role: D/V
 Ověřte, že metriky robustnosti (míra úspěšnosti známých útočných sad) jsou sledovány v čase a regresní chyby vyvolávají zablokování vydání.

---

### C2.3 Validace schématu, typu a délky

Útoky AI zahrnující nesprávně formátované nebo příliš velké vstupy mohou způsobit chyby při parsování, přetečení promptu přes různé pole a vyčerpání zdrojů. Přísné vynucování schématu je také předpokladem při provádění deterministických volání nástrojů.

 #2.3.1    Level: 1    Role: D
 Ověřte, že každý koncový bod volání API nebo funkce má definováno explicitní vstupní schéma (JSON Schema, Protobuf nebo multimodální ekvivalent) a že vstupy jsou ověřovány před sestavením promptu.
 #2.3.2    Level: 1    Role: D/V
 Ověřte, že vstupy překračující maximální počet tokenů nebo limit bajtů jsou odmítnuty s bezpečnou chybou a nikdy nejsou tichounce oříznuty.
 #2.3.3    Level: 2    Role: D/V
 Ověřte, že kontroly typů (např. číselné rozsahy, hodnoty výčtů, MIME typy pro obrázky/audio) jsou vynucovány na straně serveru, nikoli pouze v klientském kódu.
 #2.3.4    Level: 2    Role: D
 Ověřte, že sémantické validátory (např. JSON Schema) běží v konstantním čase, aby se zabránilo algoritmickému DoS.
 #2.3.5    Level: 3    Role: V
 Ověřte, že selhání validace jsou zaznamenávána s cenzurovanými úryvky dat a jednoznačnými kódy chyb, aby se usnadnilo bezpečnostní třídění.

---

### C2.4 Kontrola obsahu a politiky

Vývojáři by měli být schopni rozpoznat syntakticky platné výzvy, které žádají o zakázaný obsah (například nelegální instrukce, nenávistné projevy a texty chráněné autorskými právy), a zabránit jejich šíření.

 #2.4.1    Level: 1    Role: D
 Ověřte, že klasifikátor obsahu (zero shot nebo doladěný) hodnotí každý vstup z hlediska násilí, sebepoškozování, nenávisti, sexuálního obsahu a nelegálních požadavků, s možností nastavení prahových hodnot.
 #2.4.2    Level: 1    Role: D/V
 Ověřte, že vstupy porušující pravidla obdrží standardizované odmítnutí nebo bezpečné dokončení, aby nedošlo k jejich šíření do následných volání LLM.
 #2.4.3    Level: 2    Role: D
 Ověřte, že screeningový model nebo sada pravidel je přeškolena/aktualizována alespoň čtvrtletně a zahrnuje nově pozorované vzory obejití ochrany nebo porušení politiky.
 #2.4.4    Level: 2    Role: D
 Ověřte, že filtrování respektuje uživatelsky specifické politiky (věk, regionální právní omezení) prostřednictvím pravidel založených na atributech, která jsou vyhodnocována v čase požadavku.
 #2.4.5    Level: 3    Role: V
 Ověřte, že protokoly screeningu obsahují skóre důvěry klasifikátoru a štítky kategorií zásad pro korelaci SOC a budoucí přehrání red-teamu.

---

### C2.5 Omezování vstupní rychlosti a prevence zneužití

Vývojáři by měli zabránit zneužívání, vyčerpání zdrojů a automatizovaným útokům proti AI systémům omezením rychlosti vstupů a detekcí abnormálních vzorců používání.

 #2.5.1    Level: 1    Role: D/V
 Ověřte, že jsou u všech vstupních koncových bodů vynuceny limity rychlosti na uživatele, na IP adresu a na API klíč.
 #2.5.2    Level: 2    Role: D/V
 Ověřte, zda jsou limity rychlosti výbuchu a trvalé rychlosti nastaveny tak, aby zabránily útokům DoS a útokům hrubou silou.
 #2.5.3    Level: 2    Role: D/V
 Ověřte, že anomální vzory používání (např. rychlé opakované požadavky, zahlcení vstupu) spouštějí automatické blokace nebo eskalace.
 #2.5.4    Level: 3    Role: V
 Ověřte, že záznamy o prevenci zneužití jsou uchovávány a kontrolovány pro vznikající vzory útoků.

---

### C2.6 Více-modální validace vstupu

Systémy umělé inteligence by měly zahrnovat robustní validaci netextových vstupů (obrázky, zvuk, soubory) k prevenci vkládání škodlivých dat, vyhýbání se detekci nebo zneužívání zdrojů.

 #2.6.1    Level: 1    Role: D
 Ověřte, že všechny netextové vstupy (obrázky, zvuk, soubory) jsou před zpracováním validovány z hlediska typu, velikosti a formátu.
 #2.6.2    Level: 2    Role: D/V
 Ověřte, že soubory jsou před načtením skenovány na malware a steganografické nálože.
 #2.6.3    Level: 2    Role: D/V
 Ověřte, zda jsou vstupy obrazových/audiových dat zkontrolovány kvůli nepřátelským perturbacím nebo známým vzorcům útoků.
 #2.6.4    Level: 3    Role: V
 Ověřte, že chyby validace multimodálního vstupu jsou zaznamenávány a vyvolávají upozornění k prošetření.

---

### C2.7 Původ a přiřazení vstupu

Systémy umělé inteligence by měly podporovat auditování, sledování zneužití a shodu tím, že budou monitorovat a označovat zdroje všech uživatelských vstupů.

 #2.7.1    Level: 1    Role: D/V
 Ověřte, že všechny uživatelské vstupy jsou při příjmu označeny metadaty (ID uživatele, relace, zdroj, časové razítko, IP adresa).
 #2.7.2    Level: 2    Role: D/V
 Ověřte, že metadata o původu jsou zachována a auditovatelná pro všechny zpracované vstupy.
 #2.7.3    Level: 2    Role: D/V
 Ověřte, zda jsou anomální nebo nedůvěryhodné vstupní zdroje označeny a podrobeny zvýšenému dohledu nebo blokování.

---

### C2.8 Adaptivní detekce hrozeb v reálném čase

Vývojáři by měli používat pokročilé systémy detekce hrozeb pro AI, které se přizpůsobují novým vzorcům útoků a poskytují ochranu v reálném čase pomocí kompilovaného porovnávání vzorů.

 #2.8.1    Level: 1    Role: D/V
 Ověřte, že vzory detekce hrozeb jsou zkompilovány do optimalizovaných regex engineů pro vysoký výkon filtrování v reálném čase s minimálním dopadem na latenci.
 #2.8.2    Level: 1    Role: D/V
 Ověřte, že systémy detekce hrozeb udržují oddělené knihovny vzorů pro různé kategorie hrozeb (vstupní injekce, škodlivý obsah, citlivá data, systémové příkazy).
 #2.8.3    Level: 2    Role: D/V
 Ověřte, že adaptivní detekce hrozeb zahrnuje modely strojového učení, které aktualizují citlivost na hrozby na základě četnosti útoků a míry úspěšnosti.
 #2.8.4    Level: 2    Role: D/V
 Ověřte, že toky informací o hrozbách v reálném čase automaticky aktualizují knihovny vzorů o nové podpisy útoků a IOC (indikátory kompromitace).
 #2.8.5    Level: 3    Role: D/V
 Ověřte, že míra falešných poplachů při detekci hrozeb je neustále monitorována a specifita vzorců je automaticky laděna tak, aby byla minimalizována interference s legitimními případy použití.
 #2.8.6    Level: 3    Role: D/V
 Ověřte, že analýza kontextuální hrozby zohledňuje zdroj vstupu, vzorce chování uživatele a historii relace k zvýšení přesnosti detekce.
 #2.8.7    Level: 3    Role: D/V
 Ověřte, že metriky výkonnosti detekce hrozeb (míra detekce, latence zpracování, využití zdrojů) jsou monitorovány a optimalizovány v reálném čase.

---

### C2.9 Více-modalní pipeline pro ověřování bezpečnosti

Vývojáři by měli zajistit bezpečnostní ověření pro textové, obrazové, zvukové a další vstupy AI pomocí specifických typů detekce hrozeb a izolace zdrojů.

 #2.9.1    Level: 1    Role: D/V
 Ověřte, že každá vstupní modalita má vyhrazené bezpečnostní validátory s dokumentovanými vzory hrozeb (text: prompt injection, obrázky: steganografie, audio: útoky na spektrogram) a prahy detekce.
 #2.9.2    Level: 2    Role: D/V
 Ověřte, že multimodální vstupy jsou zpracovávány v izolovaných pískovištích s definovanými limity zdrojů (paměť, CPU, doba zpracování) specifickými pro každý typ modality a zdokumentovanými v bezpečnostních politikách.
 #2.9.3    Level: 2    Role: D/V
 Ověřte, zda detekce útoků přes více modalit identifikuje koordinované útoky zasahující více typů vstupů (např. steganografické zatížení v obrazech kombinované s injekcí promptu v textu) pomocí pravidel korelace a generování upozornění.
 #2.9.4    Level: 3    Role: D/V
 Ověřte, že selhání více modality validace spouštějí podrobné protokolování zahrnující všechny vstupní modality, výsledky validace, skóre hrozeb a korelační analýzu se strukturovanými formáty protokolů pro integraci se SIEM.
 #2.9.5    Level: 3    Role: D/V
 Ověřte, že klasifikátory obsahu specifické pro modalitu jsou aktualizovány dle zdokumentovaných plánů (minimálně jednou za čtvrtletí) s novými vzory hrozeb, adversariálními příklady a výkonovými metrikami udržovanými nad základními prahy.

---

### Reference

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

## Řízení životního cyklu modelu C3 a kontrola změn

### Řídicí cíl

Systémy umělé inteligence musí zavádět procesy řízení změn, které zabrání neoprávněným nebo nebezpečným úpravám modelu dostat se do produkčního prostředí. Tato kontrola zajišťuje integritu modelu po celou dobu jeho životního cyklu – od vývoje přes nasazení až po vyřazení z provozu – což umožňuje rychlou reakci na incidenty a udržuje odpovědnost za všechny změny.

Hlavní bezpečnostní cíl: Do produkce jsou nasazeny pouze autorizované a ověřené modely prostřednictvím kontrolovaných procesů, které zajišťují integritu, sledovatelnost a obnovitelnost.

---

### C3.1 Autorizace modelu a integrita

Do výrobního prostředí smí proniknout pouze autorizované modely s ověřenou integritou.

 #3.1.1    Level: 1    Role: D/V
 Ověřte, že všechny modelové artefakty (váhy, konfigurace, tokenizéry) jsou kryptograficky podepsány autorizovanými subjekty před nasazením.
 #3.1.2    Level: 1    Role: D/V
 Ověřte, že integrita modelu je validována při nasazení a chyby při ověřování podpisu zabraňují načtení modelu.
 #3.1.3    Level: 2    Role: D/V
 Ověřte, že záznamy o původu modelu zahrnují identitu autorizující entity, kontrolní součty trénovacích dat, výsledky validačních testů s označením úspěchu/neúspěchu a časové razítko vytvoření.
 #3.1.4    Level: 2    Role: D/V
 Ověřte, že všechny modelové artefakty používají sémantické verzování (MAJOR.MINOR.PATCH) s dokumentovanými kritérii určujícími, kdy se každá složka verze zvyšuje.
 #3.1.5    Level: 2    Role: V
 Ověřte, že sledování závislostí udržuje aktuální inventář, který umožňuje rychlou identifikaci všech spotřebitelských systémů.

---

### C3.2 Validace a testování modelu

Modely musí před nasazením projít definovanými bezpečnostními a bezpečnostními ověřeními.

 #3.2.1    Level: 1    Role: D/V
 Ověřte, že modely podstupují automatizované bezpečnostní testování, které zahrnuje validaci vstupů, sanitaci výstupů a bezpečnostní hodnocení s předem dohodnutými organizačními prahovými hodnotami pro úspěch/neúspěch před nasazením.
 #3.2.2    Level: 1    Role: D/V
 Ověřte, že neúspěchy ověření automaticky blokují nasazení modelu po explicitním schválení přepisem od předem určených oprávněných osob s dokumentovanými obchodními odůvodněními.
 #3.2.3    Level: 2    Role: V
 Ověřte, že výsledky testů jsou kryptograficky podepsané a neměnitelně propojené s konkrétním hashem verze modelu, který je ověřován.
 #3.2.4    Level: 2    Role: D/V
 Ověřte, že nouzová nasazení vyžadují zdokumentované hodnocení bezpečnostních rizik a schválení od předem určené bezpečnostní autority v předem dohodnutých časových rámcích.

---

### C3.3 Řízené nasazení a návrat k předchozí verzi

Nasazení modelů musí být kontrolováno, monitorováno a reverzibilní.

 #3.3.1    Level: 1    Role: D
 Ověřte, že produkční nasazení implementují mechanismy postupného zavádění (canary nasazení, blue-green nasazení) s automatickými spouštěči návratu zpět založenými na předem dohodnutých mírách chyb, prahových hodnotách latence nebo kritériích bezpečnostních upozornění.
 #3.3.2    Level: 1    Role: D/V
 Ověřte, že schopnosti návratu zpět obnovují úplný stav modelu (váhy, konfigurace, závislosti) atomicky v rámci předem definovaných organizačních časových oken.
 #3.3.3    Level: 2    Role: D/V
 Ověřte, že procesy nasazení validují kryptografické podpisy a vypočítávají kontrolní součty integrity před aktivací modelu, a v případě jakéhokoli nesouladu nasazení selžou.
 #3.3.4    Level: 2    Role: D/V
 Ověřte, že schopnosti nouzového vypnutí modelu mohou deaktivovat koncové body modelu v rámci předem definovaných reakčních časů prostřednictvím automatizovaných jističů nebo manuálních vypínačů.
 #3.3.5    Level: 2    Role: V
 Ověřte, že rollback artefakty (předchozí verze modelu, konfigurace, závislosti) jsou uchovávány v souladu s organizačními politikami s neměnným úložištěm pro reakci na incidenty.

---

### C3.4 Změna odpovědnosti a auditu

Všechny změny v životním cyklu modelu musí být sledovatelné a auditovatelné.

 #3.4.1    Level: 1    Role: V
 Ověřte, že všechny změny modelu (nasazení, konfigurace, vyřazení) generují neměnné auditní záznamy, včetně časové značky, ověřené identity aktéra, typu změny a stavů před a po změně.
 #3.4.2    Level: 2    Role: D/V
 Ověřte, že přístup k auditnímu protokolu vyžaduje odpovídající autorizaci a všechny pokusy o přístup jsou zaznamenány s identitou uživatele a časovou značkou.
 #3.4.3    Level: 2    Role: D/V
 Ověřte, že šablony promptů a systémové zprávy jsou verzovány v git repozitářích s povinnou kontrolou kódu a schválením určenými recenzenty před nasazením.
 #3.4.4    Level: 2    Role: V
 Ověřte, že auditní záznamy obsahují dostatečné podrobnosti (hashy modelu, snímky konfigurace, verze závislostí), aby bylo možné kompletně rekonstruovat stav modelu pro jakýkoli časový údaj v rámci doby uchovávání.

---

### C3.5 Bezpečné vývojové postupy

Procesy vývoje a školení modelů musí dodržovat bezpečné postupy, aby se zabránilo jejich kompromitaci.

 #3.5.1    Level: 1    Role: D
 Ověřte, že prostředí pro vývoj modelu, testování a produkci jsou fyzicky nebo logicky oddělena. Nemají společnou infrastrukturu, mají odlišné přístupové kontroly a izolované úložiště dat.
 #3.5.2    Level: 1    Role: D
 Ověřte, že trénink a doladění modelu probíhají v izolovaných prostředích s řízeným přístupem k síti.
 #3.5.3    Level: 1    Role: D/V
 Ověřte, že zdroje tréninkových dat jsou validovány pomocí kontrol integrity a autentizovány prostřednictvím důvěryhodných zdrojů s dokumentovaným řetězcem důvěry před použitím ve vývoji modelu.
 #3.5.4    Level: 2    Role: D
 Ověřte, že artefakty vývoje modelu (hyperparametry, skripty pro trénink, konfigurační soubory) jsou uloženy v systému pro správu verzí a vyžadují schválení peer review před použitím při tréninku.

---

### C3.6 Ukončení a vyřazení modelu

Modely musí být bezpečně vyřazeny, když již nejsou potřeba nebo když jsou identifikovány bezpečnostní problémy.

 #3.6.1    Level: 1    Role: D
 Ověřte, že procesy ukončení modelu automaticky prohledávají závislostní grafy, identifikují všechny spotřebitelské systémy a poskytují předem dohodnuté lhůty upozornění před vyřazením z provozu.
 #3.6.2    Level: 1    Role: D/V
 Ověřte, že artefakty starých modelů jsou bezpečně vymazány pomocí kryptografického vymazání nebo vícenásobného přepisování v souladu s dokumentovanými zásadami uchovávání dat a s ověřenými certifikáty o zničení.
 #3.6.3    Level: 2    Role: V
 Ověřte, že události vyřazení modelu jsou zaznamenány s časovým razítkem a identitou aktéra, a že podpisy modelu jsou zrušeny, aby se zabránilo jejich opětovnému použití.
 #3.6.4    Level: 2    Role: D/V
 Ověřte, že mimořádné odstavení modelu může zakázat přístup k modelu v rámci předem stanovených časových rámců pro reakci na nouzové situace prostřednictvím automatických vypínacích spínačů, pokud jsou zjištěny kritické bezpečnostní zranitelnosti.

---

### Reference

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

## C4 infrastruktura, konfigurace a bezpečnost nasazení

### Cíl kontroly

Infrastruktura umělé inteligence musí být zabezpečena proti eskalaci oprávnění, manipulaci s dodavatelským řetězcem a laterálním přesunům prostřednictvím zabezpečené konfigurace, izolace během běhu, důvěryhodných pipeline nasazení a komplexního monitorování. Do produkčního prostředí projdou pouze autorizované, ověřené komponenty infrastruktury a konfigurace prostřednictvím kontrolovaných procesů, které zachovávají bezpečnost, integritu a auditovatelnost.

Hlavní bezpečnostní cíl: Do produkce pronikají pouze kryptograficky podepsané a naskenované komponenty infrastruktury na zranitelnosti prostřednictvím automatizovaných validačních pipeline, které uplatňují bezpečnostní politiky a udržují neměnné auditní stopy.

---

### C4.1 Izolace běhového prostředí

Zabraňte únikům kontejnerů a eskalaci oprávnění pomocí izolace na úrovni jádra a povinných přístupových kontrol.

 #4.1.1    Level: 1    Role: D/V
 Ověřte, že všechny AI kontejnery ztrácejí VŠECHNY linuxové schopnosti kromě CAP_SETUID, CAP_SETGID a explicitně požadovaných schopností dokumentovaných v bezpečnostních standardech.
 #4.1.2    Level: 1    Role: D/V
 Ověřte, že profily seccomp blokují všechny systémové volání kromě těch v předem schválených seznamech povolených, přičemž porušení vedou k ukončení kontejneru a generování bezpečnostních upozornění.
 #4.1.3    Level: 2    Role: D/V
 Ověřte, že zátěže AI běží se souborovými systémy root v režimu pouze pro čtení, tmpfs pro dočasná data a pojmenovanými svazky pro trvalá data s vynucenými možnostmi připojení noexec.
 #4.1.4    Level: 2    Role: D/V
 Ověřte, že monitorování za běhu založené na eBPF (Falco, Tetragon nebo ekvivalent) detekuje pokusy o eskalaci oprávnění a automaticky ukončuje závadné procesy v rámci požadavků na dobu odezvy organizace.
 #4.1.5    Level: 3    Role: D/V
 Ověřte, zda výpočetně náročné úlohy umělé inteligence běží ve hardwarově izolovaných prostředích (Intel TXT, AMD SVM nebo dedikované bare-metal uzly) s ověřením atestace.

---

### C4.2 Zabezpečené pipeline pro sestavování a nasazování

Zajistěte kryptografickou integritu a bezpečnost dodavatelského řetězce prostřednictvím reprodukovatelných sestavení a podepsaných artefaktů.

 #4.2.1    Level: 1    Role: D/V
 Ověřte, že infrastruktura jako kód je při každém commitu kontrolována nástroji (tfsec, Checkov nebo Terrascan), přičemž jsou blokovány slučování obsahující nálezy s kritickou nebo vysokou závažností.
 #4.2.2    Level: 1    Role: D/V
 Ověřte, že sestavení kontejnerů jsou reprodukovatelná s identickými hashi SHA256 napříč sestaveními a generujte osvědčení o původu SLSA úrovně 3 podepsaná pomocí Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Ověřte, že obrazy kontejnerů obsahují SBOM ve formátu CycloneDX nebo SPDX a jsou před nahráním do registru podepsány pomocí Cosign, přičemž nepodepsané obrazy jsou při nasazení odmítnuty.
 #4.2.4    Level: 2    Role: D/V
 Ověřte, že CI/CD pipeline používají OIDC tokeny z HashiCorp Vault, AWS IAM rolí nebo Azure Managed Identity s dobou platnosti nepřesahující limity stanovené bezpečnostní politikou organizace.
 #4.2.5    Level: 2    Role: D/V
 Ověřte, že podpisy Cosign a provedení SLSA jsou validovány během procesu nasazení před spuštěním kontejneru a že chyby ověření způsobí selhání nasazení.
 #4.2.6    Level: 2    Role: D/V
 Ověřte, že sestavovací prostředí běží v dočasných kontejnerech nebo virtuálních strojích bez trvalého úložiště a s síťovou izolací od produkčních VPC.

---

### C4.3 Síťová bezpečnost a řízení přístupu

Implementujte síťování založené na principu nulové důvěry s politikami výchozího zamítnutí a šifrovanou komunikací.

 #4.3.1    Level: 1    Role: D/V
 Ověřte, zda Kubernetes NetworkPolicies nebo jakýkoli ekvivalent implementují výchozí zamítnutí příchozího/odchozího provozu s explicitními pravidly povolení pro požadované porty (443, 8080 atd.).
 #4.3.2    Level: 1    Role: D/V
 Ověřte, že SSH (port 22), RDP (port 3389) a cloudové metadatové koncové body (169.254.169.254) jsou zablokovány nebo vyžadují autentizaci na základě certifikátu.
 #4.3.3    Level: 2    Role: D/V
 Ověřte, že odchozí provoz je filtrován prostřednictvím HTTP/HTTPS proxy (Squid, Istio nebo cloudových NAT bran) s povolenými seznamy domén a že jsou zaznamenávány blokované požadavky.
 #4.3.4    Level: 2    Role: D/V
 Ověřte, že mezislužbová komunikace používá vzájemné TLS s certifikáty rotovanými podle organizační politiky a že je vynucena validace certifikátů (žádné příznaky pro přeskočení ověření).
 #4.3.5    Level: 2    Role: D/V
 Ověřte, že infrastruktura AI běží v dedikovaných VPC/VNet sítích bez přímého přístupu na internet a komunikuje pouze přes NAT brány nebo bastion hostitele.

---

### C4.4 Správa tajemství a kryptografických klíčů

Chraňte přihlašovací údaje pomocí úložiště podporovaného hardwarem a automatické rotace s přístupem založeným na principu zero-trust.

 #4.4.1    Level: 1    Role: D/V
 Ověřte, že tajné údaje jsou uloženy v HashiCorp Vault, AWS Secrets Manager, Azure Key Vault nebo Google Secret Manager s šifrováním v klidu pomocí AES-256.
 #4.4.2    Level: 1    Role: D/V
 Ověřte, že kryptografické klíče jsou generovány ve FIPS 140-2 úrovně 2 HSM (AWS CloudHSM, Azure Dedicated HSM) s rotací klíčů podle organizační kryptografické politiky.
 #4.4.3    Level: 2    Role: D/V
 Ověřte, že je rotace tajných údajů automatizovaná s nasazením bez výpadků a okamžitou rotací spuštěnou při změnách personálu nebo bezpečnostních incidentech.
 #4.4.4    Level: 2    Role: D/V
 Ověřte, že jsou obrazy kontejnerů skenovány nástroji (GitLeaks, TruffleHog nebo detect-secrets), které blokují sestavení obsahující API klíče, hesla nebo certifikáty.
 #4.4.5    Level: 2    Role: D/V
 Ověřte, že přístup k produkčnímu tajnému klíči vyžaduje MFA s hardwarovými tokeny (YubiKey, FIDO2) a je zaznamenáván nezměnitelnými auditními záznamy s identitami uživatelů a časovými razítky.
 #4.4.6    Level: 2    Role: D/V
 Ověřte, že tajné údaje jsou vkládány prostřednictvím Kubernetes secrets, připojených svazků nebo init kontejnerů, a zajistěte, aby tajné údaje nikdy nebyly vloženy do proměnných prostředí nebo obrazů.

---

### C4.5 Izolace a validace pracovních úloh AI

Izolujte nedůvěryhodné modely AI v bezpečných pískovištích s komplexní analýzou chování.

 #4.5.1    Level: 1    Role: D/V
 Ověřte, že externí modely AI běží v gVisor, microVM (jako Firecracker, CrossVM) nebo v Docker kontejnerech s parametry --security-opt=no-new-privileges a --read-only.
 #4.5.2    Level: 1    Role: D/V
 Ověřte, že sandboxová prostředí nemají žádné síťové připojení (--network=none) nebo mají přístup pouze k localhostu s blokováním všech externích požadavků pomocí pravidel iptables.
 #4.5.3    Level: 2    Role: D/V
 Ověřte, že validace AI modelu zahrnuje automatizované testování red-team s organizačně definovaným pokrytím testů a behaviorální analýzou pro detekci zadních vrátek.
 #4.5.4    Level: 2    Role: D/V
 Ověřte, že před nasazením AI modelu do produkce jsou jeho výsledky ze sandboxu kryptograficky podepsány autorizovaným bezpečnostním personálem a uloženy v neměnných auditních záznamech.
 #4.5.5    Level: 2    Role: D/V
 Ověřte, že jsou sandboxová prostředí po každém hodnocení zničena a znovu vytvořena z kontrolních obrazů s kompletním vyčištěním souborového systému a paměti.

---

### C4.6 Monitorování bezpečnosti infrastruktury

Nepřetržitě skenujte a monitorujte infrastrukturu s automatickým nápravným opatřením a upozorněním v reálném čase.

 #4.6.1    Level: 1    Role: D/V
 Ověřte, že obrazy kontejnerů jsou skenovány podle organizačních plánů a že zranitelnosti označené jako KRITICKÉ blokují nasazení na základě organizačních prahů rizika.
 #4.6.2    Level: 1    Role: D/V
 Ověřte, že infrastruktura splňuje CIS Benchmarks nebo kontroly NIST 800-53 s organizačně definovanými prahovými hodnotami shody a automatizovanou nápravou při neúspěšných kontrolách.
 #4.6.3    Level: 2    Role: D/V
 Ověřte, že chyby s vysokou závažností jsou opraveny podle časových plánů řízení rizik organizace s nouzovými postupy pro aktivně zneužívané CVE.
 #4.6.4    Level: 2    Role: V
 Ověřte, že bezpečnostní výstrahy se integrují se SIEM platformami (Splunk, Elastic nebo Sentinel) pomocí formátů CEF nebo STIX/TAXII s automatickým obohacením.
 #4.6.5    Level: 3    Role: V
 Ověřte, že metriky infrastruktury jsou exportovány do monitorovacích systémů (Prometheus, DataDog) s dashboardy SLA a výkonnostními reporty.
 #4.6.6    Level: 2    Role: D/V
 Ověřte, že odchylky v konfiguraci jsou detekovány pomocí nástrojů (Chef InSpec, AWS Config) podle požadavků organizace na monitorování s automatickým návratem zpět při neoprávněných změnách.

---

### C4.7 Správa zdrojů infrastruktury AI

Zabraňte útokům vyčerpávajícím zdroje a zajistěte spravedlivé přidělení zdrojů pomocí kvót a monitorování.

 #4.7.1    Level: 1    Role: D/V
 Ověřte, že je sledována využití GPU/TPU s upozorněními vyvolanými při organizačně stanovených prahových hodnotách a že jsou aktivovány automatické škálování nebo vyvažování zátěže na základě politik správy kapacity.
 #4.7.2    Level: 1    Role: D/V
 Ověřte, že metriky pracovní zátěže AI (latence inferencí, propustnost, míra chyb) jsou shromažďovány v souladu s požadavky organizačního monitorování a korelovány s využitím infrastruktury.
 #4.7.3    Level: 2    Role: D/V
 Ověřte, že Kubernetes ResourceQuotas nebo ekvivalentní mechanismy omezují jednotlivé pracovní zátěže podle organizačních politik alokace zdrojů s vynucenými tvrdými limity.
 #4.7.4    Level: 2    Role: V
 Ověřte, zda monitorování nákladů sleduje výdaje podle pracovního zatížení/nájemce s upozorněními založenými na prahových hodnotách rozpočtu organizace a automatizovanými kontrolami překročení rozpočtu.
 #4.7.5    Level: 3    Role: V
 Ověřte, že plánování kapacit využívá historická data s organizačně definovanými obdobím předpovědi a automatizované přidělování zdrojů založené na vzorcích poptávky.
 #4.7.6    Level: 2    Role: D/V
 Ověřte, že vyčerpání zdrojů spouští jističe v souladu s požadavky organizační odezvy, včetně omezení rychlosti založeného na politikách kapacity a izolace pracovního zatížení.

---

### C4.8 Oddělení prostředí a kontrola propagace

Prosazujte přísné hranice prostředí pomocí automatizovaných propagačních bran a bezpečnostní validace.

 #4.8.1    Level: 1    Role: D/V
 Ověřte, že vývojové/testovací/produkční prostředí běží v samostatných VPC/VNet s žádnými sdílenými IAM rolemi, bezpečnostními skupinami nebo síťovým připojením.
 #4.8.2    Level: 1    Role: D/V
 Ověřte, že propagace prostředí vyžaduje schválení od organizačně definovaných oprávněných osob s kryptografickými podpisy a nezměnitelnými auditními stopami.
 #4.8.3    Level: 2    Role: D/V
 Ověřte, že produkční prostředí blokuje přístup přes SSH, zakazuje ladicí rozhraní a vyžaduje žádosti o změny s organizačními požadavky na předběžné oznámení, kromě naléhavých případů.
 #4.8.4    Level: 2    Role: D/V
 Ověřte, že změny v infrastruktuře jako kódu vyžadují kontrolu od kolegů s automatizovaným testováním a bezpečnostním skenováním před sloučením do hlavní větve.
 #4.8.5    Level: 2    Role: D/V
 Ověřte, že nepoužíváte produkční data, která jsou anonymizována podle organizačních požadavků na ochranu soukromí, generování syntetických dat nebo kompletní maskování dat s odstraněním osobních identifikovatelných údajů (PII).
 #4.8.6    Level: 2    Role: D/V
 Ověřte, že propagační brány zahrnují automatizované bezpečnostní testy (SAST, DAST, skenování kontejnerů) s nulovým požadavkem na schválení v případě kritických nálezů.

---

### Zálohování a obnova infrastruktury C4.9

Zajistěte odolnost infrastruktury prostřednictvím automatizovaných záloh, testovaných postupů obnovy a schopností obnovy po havárii.

 #4.9.1    Level: 1    Role: D/V
 Ověřte, že konfigurace infrastruktury jsou zálohovány podle organizačních plánů zálohování do geograficky oddělených regionů s implementací strategie zálohování 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Ověřte, že zálohovací systémy běží v izolovaných sítích se samostatnými přihlašovacími údaji a úložištěm odděleným od sítě (air-gapped) pro ochranu proti ransomwaru.
 #4.9.3    Level: 2    Role: V
 Ověřte, že postupy obnovy jsou testovány a validovány prostřednictvím automatizovaného testování podle organizačních harmonogramů s cíli RTO a RPO splňujícími organizační požadavky.
 #4.9.4    Level: 3    Role: V
 Ověřte, že plán obnovy po havárii zahrnuje specifické runbooky pro AI s obnovením vah modelu, rekonstrukcí GPU clusteru a mapováním závislostí služby.

---

### C4.10 Soulad infrastruktury a řízení

Zajistěte dodržování předpisů prostřednictvím kontinuálního hodnocení, dokumentace a automatizovaných kontrol.

 #4.10.1    Level: 2    Role: D/V
 Ověřte, že shoda infrastruktury je posuzována podle organizačních plánů vůči kontrolám SOC 2, ISO 27001 nebo FedRAMP s automatizovaným sběrem důkazů.
 #4.10.2    Level: 2    Role: V
 Ověřte, že dokumentace infrastruktury zahrnuje síťové diagramy, mapy toku dat a modely hrozeb aktualizované podle požadavků na řízení změn v organizaci.
 #4.10.3    Level: 3    Role: D/V
 Ověřte, že změny infrastruktury procházejí automatizovaným hodnocením dopadů na soulad s předpisy s pracovními postupy schvalování pro vysoce rizikové úpravy.

---

### C4.11 Bezpečnost hardwaru pro AI

Zabezpečte hardwarové komponenty specifické pro AI, včetně GPU, TPU a specializovaných AI akcelerátorů.

 #4.11.1    Level: 2    Role: D/V
 Ověřte, že firmware akcelerátoru AI (GPU BIOS, firmware TPU) je ověřován pomocí kryptografických podpisů a aktualizován v souladu s časovými plány organizačního řízení záplat.
 #4.11.2    Level: 2    Role: D/V
 Ověřte, že před spuštěním pracovní zátěže je integrita AI akcelerátoru ověřena pomocí hardwarové attestace s využitím TPM 2.0, Intel TXT nebo AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Ověřte, že paměť GPU je izolována mezi pracovními zátěžemi pomocí SR-IOV, MIG (Multi-Instance GPU) nebo obdobného hardwarového dělení s čištěním paměti mezi úlohami.
 #4.11.4    Level: 3    Role: V
 Ověřte, že dodavatelský řetězec hardware pro AI zahrnuje ověření původu pomocí certifikátů výrobce a validaci obalů s ochranou proti neoprávněné manipulaci.
 #4.11.5    Level: 3    Role: D/V
 Ověřte, že hardwarové bezpečnostní moduly (HSM) chrání váhy AI modelu a kryptografické klíče s certifikací FIPS 140-2 úroveň 3 nebo Common Criteria EAL4+.

---

### C4.12 Okrajová a distribuovaná infrastruktura umělé inteligence

Bezpečná distribuovaná nasazení umělé inteligence včetně edge computingu, federativního učení a architektur s více lokalitami.

 #4.12.1    Level: 2    Role: D/V
 Ověřte, že zařízení edge AI se autentizují vůči centrální infrastruktuře pomocí vzájemného TLS s certifikáty zařízení, které jsou pravidelně obměňovány v souladu s organizační politikou správy certifikátů.
 #4.12.2    Level: 2    Role: D/V
 Ověřte, že koncová zařízení implementují zabezpečené spuštění s ověřenými podpisy a ochranou proti vrácení zpět, která zabraňuje útokům na snížení verze firmwaru.
 #4.12.3    Level: 3    Role: D/V
 Ověřte, že koordinace distribuované AI používá konsenzuální algoritmy odolné vůči byzantským chybám s validací účastníků a detekcí škodlivých uzlů.
 #4.12.4    Level: 3    Role: D/V
 Ověřte, že komunikace mezi okrajem a cloudem zahrnuje omezení šířky pásma, kompresi dat a schopnosti práce offline s bezpečným lokálním uložištěm.

---

### C4.13 Bezpečnost vícecloudové a hybridní infrastruktury

Zabezpečte pracovní zatížení AI napříč více poskytovateli cloudu a hybridními cloud-on-premises nasazeními.

 #4.13.1    Level: 2    Role: D/V
 Ověřte, že více-cloudové nasazení AI používá cloudově nezávislou federaci identity (OIDC, SAML) s centralizovanou správou politik napříč poskytovateli.
 #4.13.2    Level: 2    Role: D/V
 Ověřte, že přenos dat mezi cloudy používá šifrování od konce ke konci s klíči spravovanými zákazníkem a že jsou uplatňovány kontroly umístění dat podle jurisdikce.
 #4.13.3    Level: 2    Role: D/V
 Ověřte, že hybridní cloudové AI pracovní zatížení implementují konzistentní bezpečnostní politiky napříč on-premise a cloudovými prostředími s sjednoceným monitorováním a upozorňováním.
 #4.13.4    Level: 3    Role: V
 Ověřte, že prevence uzamčení u poskytovatele cloudových služeb zahrnuje přenosnou infrastrukturu jako kód, standardizovaná API a možnosti exportu dat s nástroji pro konverzi formátů.
 #4.13.5    Level: 3    Role: V
 Ověřte, že optimalizace nákladů v multi-cloud prostředí zahrnuje bezpečnostní kontroly zabraňující rozšiřování zdrojů i neoprávněným poplatkům za přenos dat mezi cloudy.

---

### C4.14 Automatizace infrastruktury a bezpečnost GitOps

Zabezpečte automatizační pipeliny infrastruktury a GitOps pracovní postupy pro správu AI infrastruktury.

 #4.14.1    Level: 2    Role: D/V
 Ověřte, zda repozitáře GitOps vyžadují podepsané commity pomocí GPG klíčů a pravidla ochrany větví zabraňující přímým pushům do hlavních větví.
 #4.14.2    Level: 2    Role: D/V
 Ověřte, že automatizace infrastruktury zahrnuje detekci odchylek s automatickými schopnostmi nápravy a návratu zpět, které jsou spuštěny podle požadavků organizace na reakci na neoprávněné změny.
 #4.14.3    Level: 2    Role: D/V
 Ověřte, že automatizované zřizování infrastruktury zahrnuje validaci bezpečnostních zásad s blokováním nasazení u konfigurací, které nejsou v souladu.
 #4.14.4    Level: 2    Role: D/V
 Ověřte, že tajné informace pro automatizaci infrastruktury jsou spravovány prostřednictvím externích správců tajemství (External Secrets Operator, Bank-Vaults) s automatickou rotací.
 #4.14.5    Level: 3    Role: V
 Ověřte, že samoopravná infrastruktura zahrnuje korelaci bezpečnostních událostí s automatizovanou reakcí na incidenty a pracovními postupy pro oznámení zainteresovaným stranám.

---

### C4.15 Kvantově odolná infrastruktura zabezpečení

Připravte infrastrukturu umělé inteligence na hrozby kvantového počítání prostřednictvím post-kvantové kryptografie a kvantově bezpečných protokolů.

 #4.15.1    Level: 3    Role: D/V
 Ověřte, že infrastruktura umělé inteligence implementuje kryptografické algoritmy schválené NIST pro post-kvantovou bezpečnost (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) pro výměnu klíčů a digitální podpisy.
 #4.15.2    Level: 3    Role: D/V
 Ověřte, že systémy kvantového rozdělení klíčů (QKD) jsou implementovány pro vysoce zabezpečenou komunikaci v oblasti umělé inteligence s protokoly pro správu klíčů odolnými vůči kvantovým útokům.
 #4.15.3    Level: 3    Role: D/V
 Ověřte, že rámce kryptografické agility umožňují rychlou migraci na nové postkvantové algoritmy s automatizovanou rotací certifikátů a klíčů.
 #4.15.4    Level: 3    Role: V
 Ověřte, že kvantové modelování hrozeb hodnotí zranitelnost infrastruktury AI vůči kvantovým útokům s dokumentovanými časovými plány migrace a hodnocením rizik.
 #4.15.5    Level: 3    Role: D/V
 Ověřte, že hybridní klasicko-kvantové kryptografické systémy poskytují obranu v hloubce během období přechodu na kvantové technologie spolu s monitorováním výkonu.

---

### C4.16 Důvěrné zpracování a bezpečné enklávy

Chraňte pracovní zatížení AI a váhy modelů pomocí hardwarově založených důvěryhodných výpočetních prostředí a technologií důvěrného výpočtu.

 #4.16.1    Level: 3    Role: D/V
 Ověřte, že citlivé AI modely běží v rámci Intel SGX enclave, AMD SEV-SNP nebo ARM TrustZone s šifrovanou pamětí a ověřením attestace.
 #4.16.2    Level: 3    Role: D/V
 Ověřte, že důvěrné kontejnery (Kata Containers, gVisor s důvěrným výpočtem) izolují pracovní zatížení umělé inteligence pomocí hardwarem vynuceného šifrování paměti.
 #4.16.3    Level: 3    Role: D/V
 Ověřte, že vzdálené osvědčení (remote attestation) potvrzuje integritu enclave před načtením AI modelů pomocí kryptografického důkazu autentizity výpočetního prostředí.
 #4.16.4    Level: 3    Role: D/V
 Ověřte, že důvěrné AI inference služby zabraňují extrakci modelu prostřednictvím šifrovaného výpočtu se zapečetěnými vahami modelu a chráněným prováděním.
 #4.16.5    Level: 3    Role: D/V
 Ověřte, že orchestraci důvěryhodného vykonávacího prostředí spravuje životní cyklus zabezpečené enklávy pomocí vzdálené autentizace a šifrovaných komunikačních kanálů.
 #4.16.6    Level: 3    Role: D/V
 Ověřte, že zabezpečené vícestranné výpočty (SMPC) umožňují spolupráci při trénování AI, aniž by docházelo k odhalení jednotlivých datových sad nebo parametrů modelu.

---

### C4.17 Infrastruktura s nulovým vědomím

Implementujte systémy dokazování s nulovým znalostním vstupem pro verifikaci a autentizaci AI chránící soukromí bez odhalení citlivých informací.

 #4.17.1    Level: 3    Role: D/V
 Ověřte, že důkazy s nulovou znalostí (ZK-SNARKs, ZK-STARKs) ověřují integritu AI modelu a původ tréninku, aniž by odhalovaly váhy modelu nebo tréninková data.
 #4.17.2    Level: 3    Role: D/V
 Ověřte, že autentizační systémy založené na ZK umožňují uživatelskou verifikaci s ochranou soukromí pro AI služby, aniž by odhalovaly informace související s identitou.
 #4.17.3    Level: 3    Role: D/V
 Ověřte, že protokoly soukromé množinové průniku (PSI) umožňují bezpečné párování dat pro federované AI, aniž by docházelo k odhalení jednotlivých datových sad.
 #4.17.4    Level: 3    Role: D/V
 Ověřte, že systémy zero-knowledge strojového učení (ZKML) umožňují ověřitelné AI inferenční závěry s kryptografickým důkazem správného výpočtu.
 #4.17.5    Level: 3    Role: D/V
 Ověřte, že ZK-rollupy poskytují škálovatelné, na soukromí založené zpracování AI transakcí s dávkovou verifikací a sníženou výpočetní náročností.

---

### C4.18 Prevence útoků postranním kanálem

Chraňte infrastrukturu umělé inteligence před útoky postranními kanály založenými na čase, napájení, elektromagnetických vlnách a cache, které by mohly uniknout citlivé informace.

 #4.18.1    Level: 3    Role: D/V
 Ověřte, že časování inferenčního procesu AI je normalizováno pomocí algoritmů s konstantním časem a doplněními, aby se zabránilo útokům na model založeným na analýze časování.
 #4.18.2    Level: 3    Role: D/V
 Ověřte, že ochrana proti analýze spotřeby zahrnuje vkládání šumu, filtrování napájecí linie a náhodné vzory vykonávání pro AI hardware.
 #4.18.3    Level: 3    Role: D/V
 Ověřte, že zmírnění postranních kanálů založených na cache používá dělení cache, randomizaci a instrukce vymazání (flush) k zabránění úniku informací.
 #4.18.4    Level: 3    Role: D/V
 Ověřte, že ochrana proti elektromagnetickému vyzařování zahrnuje stínění, filtrování signálu a náhodné zpracování, aby se zabránilo útokům typu TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Ověřte, že obrany proti mikroarchitektonickým postranním kanálům zahrnují řízení spekulativního provádění a zakrývání vzorců přístupu do paměti.

---

### C4.19 Neuromorfní a specializovaný hardwar pro bezpečnost AI

Zajistěte zabezpečení nově vznikajících hardwarových architektur AI, včetně neuronových čipů, FPGA, vlastních ASIC a optických výpočetních systémů.

 #4.19.1    Level: 3    Role: D/V
 Ověřte, že bezpečnost neuromorfního čipu zahrnuje šifrování vzorů spike, ochranu synaptických vah a ověřování učebních pravidel založené na hardwaru.
 #4.19.2    Level: 3    Role: D/V
 Ověřte, že AI akcelerátory založené na FPGA implementují šifrování bitstreamu, mechanismy proti manipulaci a bezpečné načítání konfigurace s autentizovanými aktualizacemi.
 #4.19.3    Level: 3    Role: D/V
 Ověřte, že vlastní zabezpečení ASIC zahrnuje bezpečnostní procesory na čipu, hardwarový kořen důvěryhodnosti a bezpečné ukládání klíčů s detekcí pokusu o narušení.
 #4.19.4    Level: 3    Role: D/V
 Ověřte, že optické výpočetní systémy implementují kvantově bezpečné optické šifrování, bezpečné fotonické přepínání a chráněné optické zpracování signálů.
 #4.19.5    Level: 3    Role: D/V
 Ověřte, že hybridní analogově-digitální čipy AI zahrnují zabezpečené analogové výpočty, chráněné uložení vah a autentizovanou analogově-digitální konverzi.

---

### C4.20 Infrastruktura pro výpočty zachovávající soukromí

Implementujte infrastrukturní kontroly pro výpočty šetřící soukromí, aby byla chráněna citlivá data během zpracování a analýzy umělou inteligencí.

 #4.20.1    Level: 3    Role: D/V
 Ověřte, zda infrastruktura homomorfního šifrování umožňuje šifrované výpočty na citlivých pracovních zátěžích AI s kryptografickou kontrolou integrity a monitorováním výkonu.
 #4.20.2    Level: 3    Role: D/V
 Ověřte, že systémy pro soukromé vyhledávání informací umožňují dotazy do databází, aniž by odhalovaly vzory dotazů, pomocí kryptografické ochrany přístupových vzorů.
 #4.20.3    Level: 3    Role: D/V
 Ověřte, že protokoly zabezpečených vícestranných výpočtů umožňují provádění AI inference s ochranou soukromí, aniž by odhalovaly jednotlivé vstupy nebo mezilehlé výpočty.
 #4.20.4    Level: 3    Role: D/V
 Ověřte, že správa klíčů s ochranou soukromí zahrnuje distribuovanou generaci klíčů, prahovou kryptografii a bezpečnou rotaci klíčů s hardwarovou ochranou.
 #4.20.5    Level: 3    Role: D/V
 Ověřte, že výkon výpočtů chránících soukromí je optimalizován prostřednictvím dávkování, ukládání do mezipaměti a hardwarové akcelerace při zachování kryptografických bezpečnostních záruk.

---

### C4.15 Agentový rámec Integrace bezpečnosti cloudu a hybridní nasazení

Bezpečnostní kontroly pro cloudově integrované agentní rámce s hybridními on-premises/cloud architekturami.

 #4.15.1    Level: 1    Role: D/V
 Ověřte, že integrace cloudového úložiště používá šifrování od konce ke konci s řízenou správou klíčů agentem.
 #4.15.2    Level: 2    Role: D/V
 Ověřte, že hranice zabezpečení u hybridního nasazení jsou jasně definovány s využitím šifrovaných komunikačních kanálů.
 #4.15.3    Level: 2    Role: D/V
 Ověřte, že přístup ke cloudovým zdrojům zahrnuje ověření zero-trust s kontinuální autentizací.
 #4.15.4    Level: 3    Role: D/V
 Ověřte, že požadavky na umístění dat jsou vynucovány kryptografickým potvrzením umístění úložiště.
 #4.15.5    Level: 3    Role: D/V
 Ověřte, že bezpečnostní posouzení poskytovatele cloudových služeb zahrnují modelování hrozeb specifických pro agenty a hodnocení rizik.

---

### Reference

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

## Řízení přístupu C5 a identita pro AI komponenty a uživatele

### Cíl kontroly

Efektivní kontrola přístupu pro AI systémy vyžaduje robustní správu identity, autorizaci založenou na kontextu a vynucování v čase běhu podle zásad zero-trust. Tyto kontroly zajišťují, že lidé, služby a autonomní agenti komunikují s modely, daty a výpočetními zdroji pouze v rámci explicitně udělených rozsahů, s průběžnou verifikací a možnostmi auditu.

---

### C5.1 Správa identity a autentizace

Zřiďte kryptograficky zabezpečené identity pro všechny entity s vícefaktorovou autentizací pro privilegované operace.

 #5.1.1    Level: 1    Role: D/V
 Ověřte, že všichni lidskí uživatelé a servisní identity (service principals) se autentizují prostřednictvím centralizovaného podnikového poskytovatele identity (IdP) pomocí protokolů OIDC/SAML s unikátními mapováními identity na token (bez sdílených účtů nebo přihlašovacích údajů).
 #5.1.2    Level: 1    Role: D/V
 Ověřte, že vysoce rizikové operace (nasazení modelu, export vah, přístup k tréninkovým datům, změny produkční konfigurace) vyžadují vícefaktorové ověření nebo zvýšené ověření s opětovným potvrzením relace.
 #5.1.3    Level: 2    Role: D
 Ověřte, že noví hlavní uživatelé procházejí ověřením identity v souladu s NIST 800-63-3 IAL-2 nebo ekvivalentními standardy před získáním přístupu k produkčnímu systému.
 #5.1.4    Level: 2    Role: V
 Ověřte, že přehledy přístupů jsou prováděny čtvrtletně s automatizovanou detekcí neaktivních účtů, vynucováním rotace přihlašovacích údajů a pracovními procesy odebrání přístupů.
 #5.1.5    Level: 3    Role: D/V
 Ověřte, že federované AI agenty se autentizují pomocí podepsaných JWT tvrzení, která mají maximální životnost 24 hodin a obsahují kryptografický důkaz původu.

---

### C5.2 Autorizace zdrojů a princip nejmenších privilegií

Implementujte jemně odstupňované přístupové kontroly ke všem AI zdrojům s explicitními modely oprávnění a auditními stopami.

 #5.2.1    Level: 1    Role: D/V
 Ověřte, že každý AI zdroj (datové sady, modely, koncové body, vektorové kolekce, indexy vnoření, výpočetní instance) uplatňuje řízení přístupu založené na rolích s explicitními seznamy povolených a politikami implicitního zamítnutí.
 #5.2.2    Level: 1    Role: D/V
 Ověřte, že principy nejmenších oprávnění jsou ve výchozím nastavení u servisních účtů vynucovány, začínaje oprávněními pouze pro čtení a je vyžadováno zdokumentované obchodní odůvodnění pro přístup k zápisu.
 #5.2.3    Level: 1    Role: V
 Ověřte, že všechny změny v řízení přístupu jsou propojeny s schválenými požadavky na změnu a jsou neměnitelně zaznamenány s časovými razítky, identitou aktéra, identifikátory zdrojů a rozdíly v oprávněních.
 #5.2.4    Level: 2    Role: D
 Ověřte, že štítky klasifikace dat (PII, PHI, kontrolované vývozem, vlastnická práva) se automaticky přenášejí na odvozené zdroje (embeddingy, cache promptů, výstupy modelů) s konzistentním vynucováním zásad.
 #5.2.5    Level: 2    Role: D/V
 Ověřte, že pokusy o neoprávněný přístup a události eskalace oprávnění vyvolávají v reálném čase upozornění s kontextovými metadaty do systémů SIEM do 5 minut.

---

### C5.3 Dynamické vyhodnocování politiky

Nasazujte systémy řízení přístupu založené na atributech (ABAC) pro kontextově uvědomělá rozhodnutí o autorizaci s možností auditu.

 #5.3.1    Level: 1    Role: D/V
 Ověřte, že rozhodnutí o autorizaci jsou externalizována do vyhrazeného politického enginu (OPA, Cedar nebo ekvivalentního), který je přístupný přes autentizovaná API s kryptografickou ochranou integrity.
 #5.3.2    Level: 1    Role: D/V
 Ověřte, že politiky vyhodnocují dynamické atributy během běhu, včetně úrovně oprávnění uživatele, klasifikace citlivosti zdroje, kontextu požadavku, izolace nájemce a časových omezení.
 #5.3.3    Level: 2    Role: D
 Ověřte, že definice politik jsou verzovány, posuzovány kolegy a validovány pomocí automatizovaného testování v CI/CD pipelines před nasazením do produkce.
 #5.3.4    Level: 2    Role: V
 Ověřte, že výsledky hodnocení zásad zahrnují strukturovaná odůvodnění rozhodnutí a jsou přenášeny do systémů SIEM pro korelační analýzu a reporting souladu.
 #5.3.5    Level: 3    Role: D/V
 Ověřte, že hodnoty doby platnosti (TTL) mezipaměti zásad nepřesahují 5 minut pro vysoce citlivé zdroje a 1 hodinu pro standardní zdroje s možnostmi neplatnosti mezipaměti.

---

### C5.4 Vynucování bezpečnosti v době dotazu

Implementujte bezpečnostní kontroly na úrovni databáze s povinným filtrováním a zásadami zabezpečení na úrovni řádků.

 #5.4.1    Level: 1    Role: D/V
 Ověřte, že všechny dotazy do vektorové databáze a SQL obsahují povinné bezpečnostní filtry (ID nájemce, štítky citlivosti, rozsah uživatele), které jsou vynucovány na úrovni databázového jádra, nikoli v aplikačním kódu.
 #5.4.2    Level: 1    Role: D/V
 Ověřte, že zásady zabezpečení na úrovni řádků (RLS) a maskování na úrovni polí jsou povoleny s děděním zásad pro všechny vektorové databáze, vyhledávací indexy a tréninkové datové sady.
 #5.4.3    Level: 2    Role: D
 Ověřte, že neúspěšná hodnocení autorizace zabrání „útokům zmateného zástupce“ tím, že okamžitě přeruší dotazy a vrátí explicitní chybové kódy autorizace místo vrácení prázdných výsledkových sad.
 #5.4.4    Level: 2    Role: V
 Ověřte, zda je latence vyhodnocování politiky nepřetržitě monitorována s automatizovanými upozorněními na podmínky časového překročení, které by mohly umožnit obcházení autorizace.
 #5.4.5    Level: 3    Role: D/V
 Ověřte, že mechanismy opakování dotazů znovu vyhodnocují autorizační politiky, aby zohlednily dynamické změny oprávnění v rámci aktivních uživatelských relací.

---

### Filtrovaní výstupu C5.5 a prevence ztráty dat

Nasadit kontrolní mechanismy pro následné zpracování za účelem zabránění neoprávněnému zpřístupnění dat v obsahu generovaném umělou inteligencí.

 #5.5.1    Level: 1    Role: D/V
 Ověřte, že mechanismy filtrování po inferenci prohledávají a redigují neoprávněné osobní identifikovatelné informace (PII), klasifikované informace a vlastnická data před doručením obsahu žadatelům.
 #5.5.2    Level: 1    Role: D/V
 Ověřte, že citace, odkazy a zdrojové atributy ve výstupech modelu jsou validovány podle oprávnění volajícího a jsou odstraněny, pokud je zjištěn neoprávněný přístup.
 #5.5.3    Level: 2    Role: D
 Ověřte, že jsou dodržována omezení formátu výstupu (sanitované PDF, obrázky bez metadata, schválené typy souborů) na základě úrovní oprávnění uživatelů a klasifikace dat.
 #5.5.4    Level: 2    Role: V
 Ověřte, že algoritmy pro cenzurování jsou deterministické, verzovacím systémem řízené a udržují protokoly auditu na podporu vyšetřování dodržování předpisů a forenzní analýzy.
 #5.5.5    Level: 3    Role: V
 Ověřte, že události vysokého rizika redakce generují adaptivní záznamy, které zahrnují kryptografické haše původního obsahu pro forenzní získání bez vystavení dat.

---

### C5.6 Izolace více nájemců

Zajistit kryptografickou a logickou izolaci mezi nájemci ve sdílené AI infrastruktuře.

 #5.6.1    Level: 1    Role: D/V
 Ověřte, že paměťové prostory, úložiště embeddingů, cache položky a dočasné soubory jsou odděleny podle jmenného prostoru pro každého nájemce s bezpečným vymazáním při odstranění nájemce nebo ukončení relace.
 #5.6.2    Level: 1    Role: D/V
 Ověřte, že každý požadavek na API obsahuje autentizovaný identifikátor nájemce, který je kryptograficky ověřen vůči kontextu relace a oprávněním uživatele.
 #5.6.3    Level: 2    Role: D
 Ověřte, že síťové politiky implementují pravidla výchozího zamítnutí pro komunikaci mezi nájemci v rámci služebních sítí a platforem pro orchestraci kontejnerů.
 #5.6.4    Level: 3    Role: D
 Ověřte, že klíče pro šifrování jsou jedinečné pro každého nájemce s podporou klíčů spravovaných zákazníkem (CMK) a kryptografickou izolací mezi datovými úložišti nájemců.

---

### C5.7 Autorizace autonomních agentů

Řízení oprávnění pro AI agenty a autonomní systémy prostřednictvím tokenů schopností s omezeným rozsahem a kontinuální autorizace.

 #5.7.1    Level: 1    Role: D/V
 Ověřte, že autonomní agenti obdrží omezené tokeny schopností, které explicitně vyjmenovávají povolené akce, přístupné zdroje, časová omezení a provozní podmínky.
 #5.7.2    Level: 1    Role: D/V
 Ověřte, že vysoce rizikové schopnosti (přístup k souborovému systému, provádění kódu, volání externích API, finanční transakce) jsou ve výchozím nastavení zakázány a jejich aktivace vyžaduje výslovná oprávnění s obchodními odůvodněními.
 #5.7.3    Level: 2    Role: D
 Ověřte, že tokeny schopností jsou vázány na uživatelské relace, obsahují kryptografickou ochranu integrity a zajišťují, že nemohou být uchovávány nebo znovu použity v režimu offline.
 #5.7.4    Level: 2    Role: V
 Ověřte, že akce iniciované agentem podléhají sekundární autorizaci prostřednictvím ABAC politického engine s plným kontextovým hodnocením a auditním záznamem.
 #5.7.5    Level: 3    Role: V
 Ověřte, že chybové podmínky agenta a zpracování výjimek zahrnují informace o rozsahu schopností k podpoře analýzy incidentů a forenzního vyšetřování.

---

### Reference

#### Normy a rámce

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Průvodce implementací

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Bezpečnost specifická pro umělou inteligenci

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Bezpečnost dodavatelského řetězce pro modely, rámce a data

### Řídicí cíl

Útoky na dodavatelský řetězec AI zneužívají modely třetích stran, rámce nebo datové sady k vložení zadních vrátek, zkreslení nebo zranitelného kódu. Tyto kontroly poskytují end-to-end sledovatelnost, správu zranitelností a monitorování k ochraně celého životního cyklu modelu.

---

### C6.1 Ověřování a původ předtrénovaného modelu

Posoudit a ověřit původ modelů třetích stran, licence a skryté chování před jakýmkoli doladěním nebo nasazením.

 #6.1.1    Level: 1    Role: D/V
 Ověřte, že každý třetí modelový artefakt zahrnuje podepsaný záznam původu s identifikací zdrojového úložiště a hash commitu.
 #6.1.2    Level: 1    Role: D/V
 Ověřte, že modely jsou před importem pomocí automatizovaných nástrojů prohledány na škodlivé vrstvy nebo spouštěče Trójských koní.
 #6.1.3    Level: 2    Role: D
 Ověřte, že doladění transferového učení obstojí v adversariálním hodnocení pro detekci skrytých chování.
 #6.1.4    Level: 2    Role: V
 Ověřte, zda jsou v položce ML-BOM zaznamenány licenční podmínky modelu, značky pro kontrolu vývozu a prohlášení o původu dat.
 #6.1.5    Level: 3    Role: D/V
 Ověřte, že modely s vysokým rizikem (veřejně nahrané váhy, neověření tvůrci) zůstávají v karanténě až do lidského přezkoumání a schválení.

---

### C6.2 Skenování rámců a knihoven

Nepřetržitě skenovat rámce a knihovny strojového učení (ML) pro zranitelnosti (CVE) a škodlivý kód, aby byla runtime vrstva bezpečná.

 #6.2.1    Level: 1    Role: D/V
 Ověřte, že CI pipeline spouštějí skenery závislostí na AI rámcích a kritických knihovnách.
 #6.2.2    Level: 1    Role: D/V
 Ověřte, že kritické zranitelnosti (CVSS ≥ 7,0) blokují nasazení do produkčních obrazů.
 #6.2.3    Level: 2    Role: D
 Ověřte, že statická analýza kódu probíhá na odvozených nebo dodaných knihovnách strojového učení.
 #6.2.4    Level: 2    Role: V
 Ověřte, že návrhy na upgrade frameworku zahrnují posouzení bezpečnostního dopadu s odkazem na veřejné zdroje CVE.
 #6.2.5    Level: 3    Role: V
 Ověřte, že runtime senzory upozorňují na neočekávané načítání dynamických knihoven, které se odchylují od podepsaného SBOM.

---

### C6.3 Připnutí a ověření závislostí

Připněte všechny závislosti na neměnné digesty a opakujte sestavení, aby bylo zaručeno, že artefakty jsou identické a bez zásahů.

 #6.3.1    Level: 1    Role: D/V
 Ověřte, že všechny správce balíčků vyžadují pevné určení verzí prostřednictvím zámkových souborů.
 #6.3.2    Level: 1    Role: D/V
 Ověřte, že v odkazech na kontejnery jsou používány neměnné digesty místo proměnlivých tagů.
 #6.3.3    Level: 2    Role: D
 Ověřte, že kontroly reprodukovatelných sestavení porovnávají hashe napříč běhy CI, aby byla zajištěna identická výstupy.
 #6.3.4    Level: 2    Role: V
 Ověřte, že potvrzení o sestavení jsou uchovávána po dobu 18 měsíců pro auditní sledovatelnost.
 #6.3.5    Level: 3    Role: D
 Ověřte, že expirované závislosti spouštějí automatizované PR pro aktualizaci nebo rozvětvení připnutých verzí.

---

### C6.4 Vynucení důvěryhodného zdroje

Povolte stahování artefaktů pouze z kryptograficky ověřených zdrojů schválených organizací a zablokujte vše ostatní.

 #6.4.1    Level: 1    Role: D/V
 Ověřte, že váhy modelu, datové sady a kontejnery jsou stahovány pouze z schválených domén nebo interních registrů.
 #6.4.2    Level: 1    Role: D/V
 Ověřte, že podpisy Sigstore/Cosign ověřují identitu vydavatele před tím, než jsou artefakty uloženy do místní cache.
 #6.4.3    Level: 2    Role: D
 Ověřte, že odchozí proxy blokují neautorizované stahování artefaktů, aby byla vynucena politika důvěryhodného zdroje.
 #6.4.4    Level: 2    Role: V
 Ověřte, že seznamy povolených repozitářů jsou přezkoumávány čtvrtletně s doložením obchodního odůvodnění pro každý záznam.
 #6.4.5    Level: 3    Role: V
 Ověřte, že porušení politiky spouští karanténu artefaktů a návrat zpět závislých běhů pipeline.

---

### C6.5 Hodnocení rizik souboru dat třetí strany

Vyhodnocujte externí datové sady z hlediska otravy, zaujatosti a právní shody a sledujte je během celého jejich životního cyklu.

 #6.5.1    Level: 1    Role: D/V
 Ověřte, že externí datové sady procházejí hodnocením rizika otravy (například otisk dat, detekce odlehlých hodnot).
 #6.5.2    Level: 1    Role: D
 Ověřte, že metriky zaujatosti (demografická parita, rovné příležitosti) jsou vypočítány před schválením datové sady.
 #6.5.3    Level: 2    Role: V
 Ověřte, že původ a licenční podmínky datasetů jsou zachyceny v položkách ML‑BOM.
 #6.5.4    Level: 2    Role: V
 Ověřte, že pravidelný monitoring detekuje posun nebo poškození v hostovaných datech.
 #6.5.5    Level: 3    Role: D
 Ověřte, že nepovolený obsah (autorská práva, osobní identifikační údaje) je před tréninkem odstraněn pomocí automatického čištění.

---

### C6.6 Monitorování útoků na dodavatelský řetězec

Včasně detekujte hrozby v dodavatelském řetězci prostřednictvím zdrojů CVE, analýzy auditních záznamů a simulací červeného týmu.

 #6.6.1    Level: 1    Role: V
 Ověřte, že auditní záznamy CI/CD jsou streamovány do SIEM detekcí pro anomální stahování balíčků nebo pozměněné kroky sestavení.
 #6.6.2    Level: 2    Role: D
 Ověřte, že hrací knihy pro reakci na incidenty zahrnují postupy pro návrat zpět v případě kompromitovaných modelů nebo knihoven.
 #6.6.3    Level: 3    Role: V
 Ověřte, že značky obohacení zpravodajských informací o hrozbách označují indikátory specifické pro strojové učení (např. IoC týkající se poškození modelu) při třídění upozornění.

---

### C6.7 ML-BOM pro modelové artefakty

Generujte a podepisujte podrobné SBOM specifické pro strojové učení (ML-BOMy), aby mohli následní uživatelé ověřit integritu komponent při nasazení.

 #6.7.1    Level: 1    Role: D/V
 Ověřte, že každý modelový artefakt zveřejňuje ML‑BOM, který uvádí datasety, váhy, hyperparametry a licence.
 #6.7.2    Level: 1    Role: D/V
 Ověřte, že generování ML-BOM a podepisování Cosign jsou automatizovány v CI a jsou požadovány pro sloučení.
 #6.7.3    Level: 2    Role: D
 Ověřte, že kontroly úplnosti ML‑BOM selžou a sestavení bude zastaveno, pokud chybí jakákoli metadata komponenty (hash, licence).
 #6.7.4    Level: 2    Role: V
 Ověřte, že downstream uživatelé mohou dotazovat ML-BOMy přes API pro ověření importovaných modelů při nasazení.
 #6.7.5    Level: 3    Role: V
 Ověřte, že ML‑BOM jsou verzovány a porovnávány, aby bylo možné odhalit neoprávněné úpravy.

---

### Reference

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

## Chování modelu C7, řízení výstupu a zajištění bezpečnosti

### Řídicí cíl

Výstupy modelu musí být strukturované, spolehlivé, bezpečné, vysvětlitelné a kontinuálně monitorované v produkci. Tím se snižuje výskyt halucinací, úniky soukromí, škodlivý obsah a nekontrolovatelné akce, zároveň se zvyšuje důvěra uživatelů a soulad s regulacemi.

---

### C7.1 Vynucení formátu výstupu

Přísná schémata, omezené dekódování a následná validace zastaví nesprávný nebo škodlivý obsah dříve, než se rozšíří.

 #7.1.1    Level: 1    Role: D/V
 Ověřte, že schémata odpovědí (například JSON Schema) jsou poskytnuta v systémovém promptu a každý výstup je automaticky ověřován; výstupy, které neodpovídají, vyvolávají opravu nebo odmítnutí.
 #7.1.2    Level: 1    Role: D/V
 Ověřte, že je povoleno omezené dekódování (stopovací tokeny, regulární výrazy, maximální počet tokenů) k zabránění přetečení nebo vedlejším kanálům injekce do promptu.
 #7.1.3    Level: 2    Role: D/V
 Ověřte, že následující komponenty považují výstupy za nedůvěryhodné a ověřují je vůči schématům nebo bezpečným deserializérům odolným vůči injekci.
 #7.1.4    Level: 3    Role: V
 Ověřte, že události nesprávného výstupu jsou zaznamenávány, omezeny rychlostí a zobrazeny v monitoringu.

---

### C7.2 Detekce a zmírňování halucinací

Odhad nejistoty a záložní strategie omezují vymyšlené odpovědi.

 #7.2.1    Level: 1    Role: D/V
 Ověřte, že pravděpodobnosti na úrovni tokenů, souborová sebe-konzistence nebo jemně doladěné detektory halucinací přiřazují ke každé odpovědi skóre důvěryhodnosti.
 #7.2.2    Level: 1    Role: D/V
 Ověřte, že odpovědi pod konfigurovatelným prahem důvěryhodnosti spouštějí náhradní pracovní postupy (např. generování s podporou vyhledávání, sekundární model nebo lidská kontrola).
 #7.2.3    Level: 2    Role: D/V
 Ověřte, že incidenty halucinací jsou označeny metadaty o základní příčině a jsou předávány do analyzovacích procesů po události a do postupů doladění.
 #7.2.4    Level: 3    Role: D/V
 Ověřte, že prahy a detektory jsou pře-kalibrovány po významných aktualizacích modelu nebo znalostní báze.
 #7.2.5    Level: 3    Role: V
 Ověřte, že vizualizace na panelu sledují míru halucinací.

---

### C7.3 Výstupní filtrování bezpečnosti a soukromí

Filtry zásad a pokrytí red-teamem chrání uživatele a důvěrná data.

 #7.3.1    Level: 1    Role: D/V
 Ověřte, že před a po generaci klasifikátory blokují nenávistný obsah, obtěžování, sebepoškozování, extremistický a sexuálně explicitní obsah v souladu s politikou.
 #7.3.2    Level: 1    Role: D/V
 Ověřte, že detekce PII/PCI a automatické redakce probíhají u každé odpovědi; porušení vyvolávají incident týkající se ochrany soukromí.
 #7.3.3    Level: 2    Role: D
 Ověřte, že štítky důvěrnosti (např. obchodní tajemství) se přenášejí napříč modalitami, aby se zabránilo úniku v textu, obrázcích nebo kódu.
 #7.3.4    Level: 3    Role: D/V
 Ověřte, že pokusy o obejití filtru nebo klasifikace s vysokým rizikem vyžadují sekundární schválení nebo opětovné ověření uživatele.
 #7.3.5    Level: 3    Role: D/V
 Ověřte, že prahové hodnoty filtrování odpovídají právním jurisdikcím a kontextu věku/role uživatele.

---

### C7.4 Omezení výstupu a akcí

Omezení rychlosti a schvalovací brány zabraňují zneužití a nadměrné autonomii.

 #7.4.1    Level: 1    Role: D
 Ověřte, že limity na uživatele a na klíče API omezují počet požadavků, tokenů a náklady s exponenciálním zpětným odstupem při chybách 429.
 #7.4.2    Level: 1    Role: D/V
 Ověřte, že privilegované akce (zápisy do souborů, spuštění kódu, síťové volání) vyžadují schválení založené na politice nebo zásah člověka v procesu.
 #7.4.3    Level: 2    Role: D/V
 Ověřte, že kontroly konzistence mezi různými modalitami zajišťují, že obrázky, kód a text generované pro stejný požadavek nemohou být použity k pašování škodlivého obsahu.
 #7.4.4    Level: 2    Role: D
 Ověřte, zda jsou hloubka delegace agenta, limity rekurze a povolené seznamy nástrojů výslovně nakonfigurovány.
 #7.4.5    Level: 3    Role: V
 Ověřte, že porušení limitů generuje strukturované bezpečnostní události pro příjem do SIEM.

---

### C7.5 Vysvětlitelnost výstupů

Transparentní signály zlepšují důvěru uživatelů a interní ladění.

 #7.5.1    Level: 2    Role: D/V
 Ověřte, že uživatelsky viditelné skóre důvěryhodnosti nebo stručné shrnutí zdůvodnění jsou zobrazeny, když to hodnocení rizika považuje za vhodné.
 #7.5.2    Level: 2    Role: D/V
 Ověřte, že generovaná vysvětlení neodhalují citlivé systémové výzvy ani vlastní data.
 #7.5.3    Level: 3    Role: D
 Ověřte, že systém zachycuje logaritmické pravděpodobnosti na úrovni tokenů nebo pozornostní mapy a ukládá je pro autorizovanou kontrolu.
 #7.5.4    Level: 3    Role: V
 Ověřte, že artefakty vysvětlitelnosti jsou řízeny verzemi společně s vydáními modelu pro auditovatelnost.

---

### C7.6 Integrace monitorování

Sledovatelnost v reálném čase uzavírá zpětnou vazbu mezi vývojem a produkcí.

 #7.6.1    Level: 1    Role: D
 Ověřte, že metriky (porušení schématu, míra halucinací, toxicita, úniky osobních údajů, latence, náklady) jsou přenášeny do centrálního monitorovacího systému.
 #7.6.2    Level: 1    Role: V
 Ověřte, že jsou definovány prahové hodnoty upozornění pro každý bezpečnostní metrík, včetně cest eskalace pro pohotovostní zásahy.
 #7.6.3    Level: 2    Role: V
 Ověřte, že řídicí panely korelují výstupní anomálie s modelem/verzí, příznakem funkce a změnami dat z nadřazených zdrojů.
 #7.6.4    Level: 2    Role: D/V
 Ověřte, že monitorovací data se zpětně využívají k přeškolení, doladění nebo aktualizacím pravidel v rámci zdokumentovaného pracovního postupu MLOps.
 #7.6.5    Level: 3    Role: V
 Ověřte, že monitorovací pipeline jsou testovány na průniky a mají řízený přístup, aby se zabránilo úniku citlivých záznamů.

---

### 7.7 Opatření pro ochranu generativních médií

Zajistěte, aby systémy umělé inteligence nevytvářely nelegální, škodlivý nebo nepovolený mediální obsah tím, že prosadíte politiky omezení, ověření výstupu a sledovatelnost.

 #7.7.1    Level: 1    Role: D/V
 Ověřte, že systémové výzvy a uživatelské pokyny výslovně zakazují generování nelegálního, škodlivého nebo nevyžádaného deepfake obsahu (např. obrázky, videa, zvuk).
 #7.7.2    Level: 2    Role: D/V
 Ověřte, zda jsou příkazy filtrovány kvůli pokusům o generování napodobenin, sexuálně explicitních deepfake videí nebo médií zobrazujících skutečné osoby bez jejich souhlasu.
 #7.7.3    Level: 2    Role: V
 Ověřte, že systém používá percepční hashování, detekci vodoznaků nebo otiskování pro zabránění neoprávněné reprodukce materiálů chráněných autorskými právy.
 #7.7.4    Level: 3    Role: D/V
 Ověřte, že veškerá generovaná média jsou kryptograficky podepsána, opatřena vodoznakem nebo obsahují zabudovaná metadata s ochranou proti manipulaci pro následnou sledovatelnost.
 #7.7.5    Level: 3    Role: V
 Ověřte, že pokusy o obejití (např. zakrývání příkazů, slang, protivné formulace) jsou detekovány, zaznamenávány a omezovány rychlostí; opakované zneužívání je předkládáno monitorovacím systémům.

### Reference

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

## Bezpečnost paměti C8, embeddingů a vektorové databáze

### Řídicí cíl

Vložení a vektorové úložiště fungují jako „živá paměť“ současných AI systémů, která neustále přijímá data poskytnutá uživateli a zpětně je zobrazuje v kontextu modelů prostřednictvím generování s doplněním znalostí (Retrieval-Augmented Generation, RAG). Pokud nejsou tyto paměťové kanály správně řízeny, může dojít k úniku osobně identifikovatelných informací (PII), porušení souhlasu nebo k reverzní rekonstrukci původního textu. Cílem této skupiny kontrol je zabezpečit paměťové procesy a vektorové databáze tak, aby přístup byl omezen na nezbytné minimum, vložení bylo navrženo s ohledem na ochranu soukromí, uložené vektory měly časovou platnost nebo bylo možné je na požádání zneplatnit, a aby paměť jednotlivých uživatelů nikdy neovlivňovala vstupy nebo výstupy jiných uživatelů.

---

### C8.1 Řízení přístupu k paměti a indexům RAG

Prosazujte detailní řízení přístupu u každé kolekce vektorů.

 #8.1.1    Level: 1    Role: D/V
 Ověřte, že pravidla řízení přístupu na úrovni řádků/jmenných prostorů omezují operace vkládání, mazání a dotazování podle nájemce, kolekce nebo štítku dokumentu.
 #8.1.2    Level: 1    Role: D/V
 Ověřte, že API klíče nebo JWT obsahují omezené nároky (např. ID kolekcí, akční slovesa) a jsou rotovány alespoň čtvrtletně.
 #8.1.3    Level: 2    Role: D/V
 Ověřte, že pokusy o eskalaci oprávnění (např. dotazy na podobnost mezi jmennými prostory) jsou detekovány a zaznamenávány do SIEM do 5 minut.
 #8.1.4    Level: 2    Role: D/V
 Ověřte, že vektorová databáze zaznamenává do protokolu identifikátor subjektu, operaci, ID vektoru/prostor jmen, prahovou podobnost a počet výsledků.
 #8.1.5    Level: 3    Role: V
 Ověřte, že jsou rozhodnutí o přístupu testována na chyby obcházení vždy, když jsou aktualizovány motory nebo se mění pravidla dělení indexu.

---

### C8.2 Sanitizace a validace vkládání

Předzpracujte text pro osobní identifikovatelné informace (PII), odstraňte je nebo pseudonymizujte před vektorizací a případně po zpracování vektoru odstraňte zbytkové signály.

 #8.2.1    Level: 1    Role: D/V
 Ověřte, že PII a regulovaná data jsou detekována pomocí automatizovaných klasifikátorů a před vložením jsou maskována, tokenizována nebo odstraněna.
 #8.2.2    Level: 1    Role: D
 Ověřte, že pipeline vložení odmítají nebo izolují vstupy obsahující spustitelný kód nebo artefakty nevyhovující UTF-8, které by mohly otrávit index.
 #8.2.3    Level: 2    Role: D/V
 Ověřte, že na vektorové reprezentace vět je aplikována lokální nebo metrická diferenciálně privátní sanitizace, pokud je jejich vzdálenost k jakémukoli známému tokenu obsahujícímu osobní identifikovatelné informace (PII) pod konfigurovatelným prahem.
 #8.2.4    Level: 2    Role: V
 Ověřte, že účinnost sanitizace (např. zpětné vyhledávání odstranění osobních údajů, sémantický posun) je validována alespoň pololetně vůči referenčním korpusům.
 #8.2.5    Level: 3    Role: D/V
 Ověřte, že konfigurační soubory pro sanitizaci jsou verzovány a změny procházejí kontrolou kolegy.

---

### C8.3 Vypršení platnosti paměti, odvolání a vymazání

Nařízení GDPR o „právu být zapomenut“ a podobné zákony vyžadují včasné vymazání; vektorové úložiště proto musí podporovat TTL (čas do vypršení platnosti), tvrdé mazání a tomb-stoning, aby nemohlo dojít k obnovení nebo opětovnému indexování zrušených vektorů.

 #8.3.1    Level: 1    Role: D/V
 Ověřte, že každý vektor a záznam metadat obsahuje TTL nebo explicitní štítek uchování, který je respektován automatizovanými úklidovými úlohami.
 #8.3.2    Level: 1    Role: D/V
 Ověřte, že uživatelem iniciované požadavky na smazání odstraní vektory, metadata, kopie mezipaměti a odvozené indexy do 30 dnů.
 #8.3.3    Level: 2    Role: D
 Ověřte, že logické mazání je následováno kryptografickým destrukcí bloků úložiště, pokud to hardware podporuje, nebo zničením klíče v klíčovém trezoru.
 #8.3.4    Level: 3    Role: D/V
 Ověřte, že vypršené vektory jsou vyloučeny z výsledků hledání nejbližších sousedů do 500 ms po vypršení.

---

### C8.4 Prevence inverze a úniku embeddingů

Nedávné obranné metody — překrytí šumu, projekční sítě, perturbace neuronů na úrovni soukromí a šifrování na aplikační vrstvě — mohou snížit míru inverze na úrovni tokenů pod 5 %.

 #8.4.1    Level: 1    Role: V
 Ověřte, že existuje formální model hrozeb zahrnující útoky na inverzi, členství a odvození atributů, který je přezkoumáván každý rok.
 #8.4.2    Level: 2    Role: D/V
 Ověřte, že šifrování na aplikační vrstvě nebo vyhledávací šifrování chrání vektory před přímým čtením ze strany administrátorů infrastruktury nebo zaměstnanců cloudových služeb.
 #8.4.3    Level: 3    Role: V
 Ověřte, že obranné parametry (ε pro DP, šum σ, hodnost projekce k) vyvažují ochranu soukromí ≥ 99 % tokenů a užitečnost ≤ 3 % ztráty přesnosti.
 #8.4.4    Level: 3    Role: D/V
 Ověřte, že metriky odolnosti vůči inverzi jsou součástí kontrolních bodů pro vydání aktualizací modelu, přičemž jsou definovány rozpočty pro regrese.

---

### C8.5 Vynucování rozsahu pro uživatelsky specifickou paměť

Únik dat mezi nájemníky zůstává hlavním rizikem RAG: nesprávně filtrované dotazy na podobnost mohou odhalit soukromé dokumenty jiného zákazníka.

 #8.5.1    Level: 1    Role: D/V
 Ověřte, že každý dotaz na vyhledávání je filtrován podle ID nájemce/uživatele před jeho předáním do výzvy LLM.
 #8.5.2    Level: 1    Role: D
 Ověřte, že názvy kolekcí nebo identifikátory s jmenným prostorem jsou solené pro každého uživatele nebo nájemce, aby se vektory nemohly překrývat mezi různými oblastmi.
 #8.5.3    Level: 2    Role: D/V
 Ověřte, že výsledky podobnosti nad konfigurovatelným práhem vzdálenosti, ale mimo dosah volajícího, jsou zahazovány a vyvolávají bezpečnostní upozornění.
 #8.5.4    Level: 2    Role: V
 Ověřte, že testy zátěže pro více nájemců simulují protivné dotazy, které se pokoušejí získat dokumenty mimo rozsah, a prokažte nulový únik dat.
 #8.5.5    Level: 3    Role: D/V
 Ověřte, že šifrovací klíče jsou odděleny pro každého nájemce, což zajišťuje kryptografickou izolaci i v případě sdíleného fyzického úložiště.

---

### C8.6 Pokročilá bezpečnost paměťových systémů

Bezpečnostní kontroly pro sofistikované paměťové architektury, včetně epizodické, sémantické a pracovní paměti, s konkrétními požadavky na izolaci a validaci.

 #8.6.1    Level: 1    Role: D/V
 Ověřte, že různé typy paměti (epizodická, sémantická, pracovní) mají izolované bezpečnostní kontexty s řízením přístupu založeným na rolích, oddělenými šifrovacími klíči a zdokumentovanými vzory přístupu pro každý typ paměti.
 #8.6.2    Level: 2    Role: D/V
 Ověřte, že procesy konsolidace paměti zahrnují bezpečnostní validaci k zabránění vkládání škodlivých vzpomínek prostřednictvím čištění obsahu, ověřování zdroje a kontrol integrity před uložením.
 #8.6.3    Level: 2    Role: D/V
 Ověřte, že dotazy pro získávání paměti jsou validovány a sanitovány, aby se zabránilo získávání nepovolených informací prostřednictvím analýzy vzoru dotazů, vynucování přístupové kontroly a filtrování výsledků.
 #8.6.4    Level: 3    Role: D/V
 Ověřte, že mechanismy zapomínání v paměti bezpečně vymazávají citlivé informace s kryptografickými zárukami vymazání pomocí odstranění klíčů, vícenásobného přepisování nebo hardwarově založeného bezpečného vymazání s ověřovacími certifikáty.
 #8.6.5    Level: 3    Role: D/V
 Ověřte, že integrita paměťového systému je neustále sledována kvůli neoprávněným úpravám nebo poškození pomocí kontrolních součtů, auditních protokolů a automatizovaných upozornění při změnách obsahu paměti mimo běžný provoz.

---

### Reference

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

## 9 Autonomní orchestrace a agentické zabezpečení akcí

### Cíl kontroly

Zajistěte, aby autonomní nebo multiagentní systémy umělé inteligence mohly vykonávat pouze akce, které jsou explicitně zamýšlené, autentizované, auditovatelné a v rámci stanovených hranic nákladů a rizik. Tím se chrání před hrozbami, jako je kompromitace autonomního systému, zneužití nástrojů, detekce agentních smyček, únos komunikace, falšování identity, manipulace s rojovými systémy a manipulace s úmysly.

---

### 9.1 Agentní plánování úkolů a rozpočty rekurze

Omezujte rekurzivní plány a vyžadujte lidské kontroly pro privilegované akce.

 #9.1.1    Level: 1    Role: D/V
 Ověřte, že maximální hloubka rekurze, šířka, skutečný čas, tokeny a finanční náklady na každý běh agenta jsou centrálně konfigurovány a verzovány.
 #9.1.2    Level: 1    Role: D/V
 Ověřte, že privilegované nebo nezvratné akce (např. potvrzení kódu, finanční převody) vyžadují před provedením explicitní lidské schválení prostřednictvím auditovatelného kanálu.
 #9.1.3    Level: 2    Role: D
 Ověřte, že monitory prostředků v reálném čase vyvolají přerušení obvodového jističe, když je překročena jakákoli hranice rozpočtu, čímž zastaví další rozšiřování úloh.
 #9.1.4    Level: 2    Role: D/V
 Ověřte, že události vypínače jsou zaznamenávány s ID agenta, spouštěcí podmínkou a zachyceným stavem plánu pro forenzní přezkum.
 #9.1.5    Level: 3    Role: V
 Ověřte, že bezpečnostní testy pokrývají scénáře vyčerpání rozpočtu a nekontrolovaného plánu, a potvrďte bezpečné zastavení bez ztráty dat.
 #9.1.6    Level: 3    Role: D
 Ověřte, že rozpočtové politiky jsou vyjádřeny jako politika-v-kódu a vynucovány v CI/CD za účelem zablokování odchylek v konfiguraci.

---

### 9.2 Izolace pluginů nástrojů (sandboxing)

Izolujte interakce s nástroji, aby se zabránilo neoprávněnému přístupu k systému nebo spuštění kódu.

 #9.2.1    Level: 1    Role: D/V
 Ověřte, že každý nástroj/plugin běží uvnitř operačního systému, kontejneru nebo sandboxu na úrovni WASM s politikami souborového systému, sítě a systémových volání s nejmenšími oprávněními.
 #9.2.2    Level: 1    Role: D/V
 Ověřte, že limity zdrojů sandboxu (CPU, paměť, disk, výstupní síťový provoz) a časové limity vykonávání jsou vynuceny a zaznamenávány.
 #9.2.3    Level: 2    Role: D/V
 Ověřte, že binární soubory nebo deskriptory nástrojů jsou digitálně podepsané; podpisy jsou ověřovány před načtením.
 #9.2.4    Level: 2    Role: V
 Ověřte, že telemetrie sandboxu se přenáší do SIEM; anomálie (např. pokusy o odchozí připojení) vyvolávají upozornění.
 #9.2.5    Level: 3    Role: V
 Ověřte, že vysokorizikové pluginy procházejí bezpečnostní kontrolou a penetračním testováním před nasazením do produkce.
 #9.2.6    Level: 3    Role: D/V
 Ověřte, že pokusy o únik z pískoviště jsou automaticky blokovány a postižený plugin je umístěn do karantény do doby vyšetření.

---

### 9.3 Autonomní smyčka a omezení nákladů

Detekujte a zastavte nekontrolovanou rekurzi mezi agenty a výbuchy nákladů.

 #9.3.1    Level: 1    Role: D/V
 Ověřte, že volání mezi agenty zahrnují omezení počtu přeskoků (hop-limit) nebo TTL, které běhové prostředí snižuje a vynucuje.
 #9.3.2    Level: 2    Role: D
 Ověřte, že agenti udržují jedinečné ID grafu vyvolání, aby bylo možné rozpoznat samovolné vyvolání nebo cyklické vzory.
 #9.3.3    Level: 2    Role: D/V
 Ověřte, že kumulativní čítače výpočetních jednotek a výdajů jsou sledovány pro každý řetězec požadavků; překročení limitu vede k přerušení řetězce.
 #9.3.4    Level: 3    Role: V
 Ověřte, že formální analýza nebo model checking prokazuje nepřítomnost neomezené rekurze v protokolech agentů.
 #9.3.5    Level: 3    Role: D
 Ověřte, že události přerušení smyčky generují upozornění a poskytují metriky pro nepřetržité zlepšování.

---

### 9.4 Ochrana proti zneužití na úrovni protokolu

Zabezpečit komunikační kanály mezi agenty a externími systémy, aby se zabránilo převzetí kontroly nebo manipulaci.

 #9.4.1    Level: 1    Role: D/V
 Ověřte, že všechny zprávy mezi agentem a nástrojem i mezi agenty jsou autentizovány (například pomocí vzájemného TLS nebo JWT) a šifrovány end-to-end.
 #9.4.2    Level: 1    Role: D
 Ověřte, že jsou schémata přísně validována; neznámá pole nebo chybně formátované zprávy jsou zamítány.
 #9.4.3    Level: 2    Role: D/V
 Ověřte, že kontrolní integrity (MAC nebo digitální podpisy) pokrývají celé tělo zprávy včetně parametrů nástroje.
 #9.4.4    Level: 2    Role: D
 Ověřte, že ochrana proti přehrání (nonce nebo časová okna) je vynucena na úrovni protokolu.
 #9.4.5    Level: 3    Role: V
 Ověřte, že implementace protokolů jsou podrobeny fuzzingu a statické analýze kvůli zranitelnostem typu injekce nebo deserializace.

---

### 9.5 Identita agenta a důkaz zásahu

Zajistěte, aby byly akce přiřaditelné a úpravy detekovatelné.

 #9.5.1    Level: 1    Role: D/V
 Ověřte, že každá instance agenta má unikátní kryptografickou identitu (klíčový pár nebo hardwarově založený oprávnění).
 #9.5.2    Level: 2    Role: D/V
 Ověřte, že všechny akce agentů jsou podepsané a opatřené časovou značkou; protokoly zahrnují podpis pro zabránění popření odpovědnosti.
 #9.5.3    Level: 2    Role: V
 Ověřte, že záznamy s důkazem proti neoprávněným změnám jsou ukládány v médiu pouze pro připojování nebo zápis jednou.
 #9.5.4    Level: 3    Role: D
 Ověřte, že klíče identity se mění podle stanoveného plánu a při indikátorech kompromitace.
 #9.5.5    Level: 3    Role: D/V
 Ověřte, že pokusy o podvržení identity nebo konflikty klíčů okamžitě vyvolají karanténu postiženého agenta.

---

### 9.6 Snížení rizik při použití víceagentových rojů

Zmírnit rizika související s kolektivním chováním prostřednictvím izolace a formálního modelování bezpečnosti.

 #9.6.1    Level: 1    Role: D/V
 Ověřte, že agenti pracující v různých bezpečnostních doménách běží v izolovaných runtime pískovištích nebo síťových segmentech.
 #9.6.2    Level: 3    Role: V
 Ověřte, že chování swarmu je modelováno a formálně ověřeno z hlediska živosti a bezpečnosti před nasazením.
 #9.6.3    Level: 3    Role: D
 Ověřte, že monitorovací nástroje za běhu detekují vznikající nebezpečné vzory (např. oscilace, zablokování) a iniciují nápravná opatření.

---

### 9.7 Autentizace / autorizace uživatelů a nástrojů

Implementujte robustní kontrolu přístupu pro každou akci spuštěnou agentem.

 #9.7.1    Level: 1    Role: D/V
 Ověřte, že agenti se autentizují jako hlavní subjekty prvního řádu do následných systémů a nikdy znovu nepoužívají přihlašovací údaje koncových uživatelů.
 #9.7.2    Level: 2    Role: D
 Ověřte, že detailní politiky autorizace omezují, které nástroje může agent vyvolat a jaké parametry může zadat.
 #9.7.3    Level: 2    Role: V
 Ověřte, že kontroly oprávnění jsou znovu vyhodnocovány při každém volání (kontinuální autorizace), nikoli pouze na začátku relace.
 #9.7.4    Level: 3    Role: D
 Ověřte, že delegovaná oprávnění automaticky vyprší a po uplynutí časového limitu nebo změně rozsahu vyžadují nový souhlas.

---

### 9.8 Bezpečnost komunikace mezi agenty

Šifrujte a zajistěte integritu všech meziagentových zpráv, aby se zabránilo odposlouchávání a manipulaci.

 #9.8.1    Level: 1    Role: D/V
 Ověřte, že vzájemná autentizace a šifrování s dokonalým tajemstvím vpřed (např. TLS 1.3) jsou pro kanály agentů povinné.
 #9.8.2    Level: 1    Role: D
 Ověřte, že integrita zprávy a její původ jsou ověřeny před zpracováním; v případě neúspěchu se generují upozornění a zpráva je zahozená.
 #9.8.3    Level: 2    Role: D/V
 Ověřte, že jsou zaznamenávány metadata komunikace (časová razítka, pořadová čísla) na podporu forenzní rekonstrukce.
 #9.8.4    Level: 3    Role: V
 Ověřte, že formální verifikace nebo modelové ověřování potvrzují, že stavové automaty protokolu nemohou být přivedeny do nebezpečných stavů.

---

### 9.9 Ověření záměru a vynucení omezení

Ověřte, že akce agenta odpovídají uvedenému záměru uživatele a systémovým omezením.

 #9.9.1    Level: 1    Role: D
 Ověřte, že předběžné řešiče omezení kontrolují navrhované akce podle pevně zakódovaných pravidel bezpečnosti a politiky.
 #9.9.2    Level: 2    Role: D/V
 Ověřte, že akce s vysokým dopadem (finanční, destruktivní, citlivé na soukromí) vyžadují výslovné potvrzení úmyslu od uživatele, který je iniciuje.
 #9.9.3    Level: 2    Role: V
 Ověřte, že kontroly post-podmínek validují, že dokončené akce dosáhly zamýšlených efektů bez vedlejších účinků; nesrovnalosti vyvolají návrat k předchozímu stavu (rollback).
 #9.9.4    Level: 3    Role: V
 Ověřte, že formální metody (např. kontrola modelu, dokazování vět) nebo testy založené na vlastnostech prokazují, že plány agentů splňují všechny deklarované omezení.
 #9.9.5    Level: 3    Role: D
 Ověřte, že incidenty s nesouladem záměrů nebo porušením omezení jsou zahrnuty do cyklů kontinuálního zlepšování a sdílení hrozebných informací.

---

### 9.10 Strategie zabezpečení agentního uvažování

Bezpečný výběr a provádění různých strategií uvažování, včetně přístupů ReAct, Chain-of-Thought a Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Ověřte, že výběr strategie uvažování používá deterministická kritéria (složitost vstupu, typ úkolu, bezpečnostní kontext) a že identické vstupy produkují identické výběry strategie ve stejném bezpečnostním kontextu.
 #9.10.2    Level: 1    Role: D/V
 Ověřte, že každá strategie uvažování (ReAct, Chain-of-Thought, Tree-of-Thoughts) má vyhrazenou kontrolu vstupu, sanitaci výstupu a časové limity vykonávání specifické pro svůj kognitivní přístup.
 #9.10.3    Level: 2    Role: D/V
 Ověřte, že přechody strategií uvažování jsou zaznamenávány s kompletním kontextem včetně charakteristik vstupu, hodnot kritérií výběru a metadat provádění pro rekonstrukci auditu.
 #9.10.4    Level: 2    Role: D/V
 Ověřte, že uvažování pomocí Stromu myšlenek zahrnuje mechanismy pro ořezávání větví, které ukončují průzkum při detekci porušení pravidel, limitů zdrojů nebo bezpečnostních hranic.
 #9.10.5    Level: 2    Role: D/V
 Ověřte, že cykly ReAct (Reason-Act-Observe) zahrnují validační kontrolní body v každé fázi: ověření kroku uvažování, autorizaci akce a sanitaci pozorování před pokračováním.
 #9.10.6    Level: 3    Role: D/V
 Ověřte, že jsou metriky výkonu strategie uvažování (doba vykonání, využití zdrojů, kvalita výstupu) sledovány s automatizovanými upozorněními, pokud metriky překročí nastavené prahové hodnoty.
 #9.10.7    Level: 3    Role: D/V
 Ověřte, že hybridní přístupy k roz reasoning, které kombinují více strategií, zachovávají validaci vstupů a omezení výstupů všech součástí strategií, aniž by obcházely jakékoli bezpečnostní kontroly.
 #9.10.8    Level: 3    Role: D/V
 Ověřte, že testování bezpečnosti strategického uvažování zahrnuje fuzzing s nesprávně formátovanými vstupy, nepřátelské výzvy navržené k vynucení přepínání strategie a testování hraničních podmínek pro každý kognitivní přístup.

---

### 9.11 Správa stavu životního cyklu agenta a bezpečnost

Zabezpečená inicializace agenta, přechody stavů a ukončení s kryptografickými auditními trasami a definovanými postupy obnovy.

 #9.11.1    Level: 1    Role: D/V
 Ověřte, že inicializace agenta zahrnuje vytvoření kryptografické identity s hardwarově zálohovanými pověřeními a nezměnitelnými auditními logy spuštění obsahujícími ID agenta, časové razítko, hash konfigurace a parametry inicializace.
 #9.11.2    Level: 2    Role: D/V
 Ověřte, že přechody stavů agenta jsou kryptograficky podepsány, časově označeny a zaznamenány s kompletním kontextem včetně spouštěcích událostí, hashe předchozího stavu, hashe nového stavu a provedených bezpečnostních validací.
 #9.11.3    Level: 2    Role: D/V
 Ověřte, že postupy vypnutí agenta zahrnují bezpečné vymazání paměti pomocí kryptografického vymazání nebo vícenásobného přepisování, zrušení oprávnění s oznámením autoritě certifikátů a generování terminálních certifikátů odolných proti manipulaci.
 #9.11.4    Level: 3    Role: D/V
 Ověřte, že mechanismy obnovy agenta validují integritu stavu pomocí kryptografických kontrolních součtů (minimálně SHA-256) a provádějí návrat k známým správným stavům při detekci poškození, přičemž jsou použita automatizovaná upozornění a požadavky na manuální schválení.
 #9.11.5    Level: 3    Role: D/V
 Ověřte, že mechanismy perzistence agenta šifrují citlivá stavová data pomocí AES-256 klíčů na agentovi a implementují bezpečný rotaci klíčů podle konfigurovatelných plánů (maximálně 90 dní) s nasazením bez výpadků.

---

### 9.12 Rámec zabezpečení integrace nástrojů

Bezpečnostní kontroly pro dynamické načítání nástrojů, jejich spouštění a ověřování výsledků s definovanými procesy hodnocení rizik a schvalování.

 #9.12.1    Level: 1    Role: D/V
 Ověřte, že popisy nástrojů obsahují bezpečnostní metadata specifikující požadovaná oprávnění (čtení/zápis/spuštění), úrovně rizika (nízká/střední/vysoká), limity zdrojů (CPU, paměť, síť) a požadavky na validaci zdokumentované v manifestech nástrojů.
 #9.12.2    Level: 1    Role: D/V
 Ověřte, že výsledky spuštění nástroje jsou validovány vůči očekávaným schématům (JSON Schema, XML Schema) a bezpečnostním politikám (čištění výstupu, klasifikace dat) před jejich integrací, s omezením časového limitu a postupy pro zpracování chyb.
 #9.12.3    Level: 2    Role: D/V
 Ověřte, že záznamy interakcí s nástrojem obsahují podrobný bezpečnostní kontext včetně využití oprávnění, vzorců přístupu k datům, doby provádění, spotřeby zdrojů a návratových kódů se strukturovaným logováním pro integraci se SIEM.
 #9.12.4    Level: 2    Role: D/V
 Ověřte, že mechanismy dynamického načítání nástrojů ověřují digitální podpisy pomocí infrastruktury PKI a implementují bezpečné protokoly načítání s izolací v pískovišti a ověřováním oprávnění před spuštěním.
 #9.12.5    Level: 3    Role: D/V
 Ověřte, že bezpečnostní hodnocení nástrojů jsou automaticky spuštěna pro nové verze s povinnými schvalovacími branami, zahrnujícími statickou analýzu, dynamické testování a přezkum bezpečnostním týmem s dokumentovanými kritérii schválení a požadavky na SLA.

---

#### Reference

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

## 10 Robustnost vůči protivníkům a obrana soukromí

### Řídicí cíl

Zajistěte, aby modely umělé inteligence zůstaly spolehlivé, chránily soukromí a byly odolné vůči zneužití při čelení útokům na obcházení, inferenci, extrakci nebo otravování.

---

### 10.1 Zarovnání modelu a bezpečnost

Chraňte před škodlivými nebo politiku porušujícími výstupy.

 #10.1.1    Level: 1    Role: D/V
 Ověřte, že sada testů souladu (red-team výzvy, jailbreakové sondy, nepovolený obsah) je verzována a spuštěna při každém vydání modelu.
 #10.1.2    Level: 1    Role: D
 Ověřte, že jsou dodržována pravidla pro odmítnutí a bezpečné dokončení.
 #10.1.3    Level: 2    Role: D/V
 Ověřte, že automatizovaný hodnotitel měří míru škodlivého obsahu a označuje regresi překračující stanovený práh.
 #10.1.4    Level: 2    Role: D
 Ověřte, že protijailbreakové trénování je zdokumentováno a opakovatelné.
 #10.1.5    Level: 3    Role: V
 Ověřte, že formální důkazy dodržování politiky nebo certifikovaný dohled pokrývají kritické oblasti.

---

### 10.2 Zpevnění proti adversariálním příkladům

Zvyšte odolnost vůči manipulovaným vstupům. Robustní adversariální trénink a hodnotící benchmark jsou současnou nejlepší praxí.

 #10.2.1    Level: 1    Role: D
 Ověřte, že projektové repozitáře obsahují konfigurace pro trénink protiútoků s reprodukovatelnými náhodnými semeny.
 #10.2.2    Level: 2    Role: D/V
 Ověřte, že detekce adversariálních příkladů vyvolává blokující výstrahy v produkčních pipelinech.
 #10.2.4    Level: 3    Role: V
 Ověřte, že důkazy certifikované odolnosti nebo intervalové hranice pokrývají alespoň nejdůležitější kritické třídy.
 #10.2.5    Level: 3    Role: V
 Ověřte, že regresní testy používají adaptivní útoky k potvrzení, že nedochází k měřitelnému poklesu robustnosti.

---

### 10.3 Zmírnění inference členství

Omezte schopnost rozhodnout, zda byl záznam součástí tréninkových dat. Diferenciální soukromí a maskování skóre důvěry zůstávají nejúčinnějšími známými obranami.

 #10.3.1    Level: 1    Role: D
 Ověřte, že regularizace entropie pro každý dotaz nebo škálování teploty snižuje příliš sebevědomé predikce.
 #10.3.2    Level: 2    Role: D
 Ověřte, že trénink využívá ε-omezenou diferenciálně soukromou optimalizaci pro citlivé datové sady.
 #10.3.3    Level: 2    Role: V
 Ověřte, že simulace útoků (shadow-model nebo black-box) vykazují AUC útoku ≤ 0,60 na vyhrazených datech.

---

### 10.4 Odolnost proti invertování modelu

Zabraňte rekonstrukci soukromých atributů. Nedávné průzkumy zdůrazňují ořezávání výstupů a záruky diferencované ochrany soukromí (DP) jako praktické obrany.

 #10.4.1    Level: 1    Role: D
 Ověřte, že citlivé atributy nejsou nikdy přímo zobrazovány; tam, kde je to potřeba, používejte kategorie (buckets) nebo jednosměrné transformace.
 #10.4.2    Level: 1    Role: D/V
 Ověřte, že limity rychlosti dotazů omezují opakované adaptivní dotazy od stejného uživatele.
 #10.4.3    Level: 2    Role: D
 Ověřte, že model je trénován s ochranou soukromí pomocí šumu.

---

### 10.5 Ochrana proti extrakci modelu

Detekce a odrazení neautorizovaného klonování. Doporučují se vodotisky a analýza dotazových vzorů.

 #10.5.1    Level: 1    Role: D
 Ověřte, že inference brány vynucují globální a na klíč API specifické limity rychlosti přizpůsobené prahu zapamatování modelu.
 #10.5.2    Level: 2    Role: D/V
 Ověřte, že statistiky entropie dotazu a plurality vstupu zásobují automatizovaný detektor extrakce.
 #10.5.3    Level: 2    Role: V
 Ověřte, že křehké nebo pravděpodobnostní vodotisky lze dokázat s p < 0,01 při maximálně 1 000 dotazech proti podezřelému klonu.
 #10.5.4    Level: 3    Role: D
 Ověřte, zda jsou klíče vodoznaku a spouštěcí sady uloženy v hardwarovém bezpečnostním modulu a zda jsou každoročně rotovány.
 #10.5.5    Level: 3    Role: V
 Ověřte, že události extraction-alert zahrnují závadné dotazy a jsou integrovány s návodem na reakci na incidenty.

---

### 10.6 Detekce otrávených dat v době inferenčního vyhodnocení

Identifikujte a neutralizujte zadní vrátka nebo otrávené vstupy.

 #10.6.1    Level: 1    Role: D
 Ověřte, že vstupy procházejí detektorem anomálií (např. STRIP, skórování konzistence) před samotným odvozením modelu.
 #10.6.2    Level: 1    Role: V
 Ověřte, že prahy detektoru jsou nastaveny na čistých/infikovaných validačních sadách tak, aby dosahovaly méně než 5 % falešně pozitivních výsledků.
 #10.6.3    Level: 2    Role: D
 Ověřte, že vstupy označené jako otrávené spouštějí měkké blokování a pracovní postupy pro lidskou kontrolu.
 #10.6.4    Level: 2    Role: V
 Ověřte, že detektory jsou testovány na stres prostřednictvím adaptivních, bezspouštěcích zadních vrátek.
 #10.6.5    Level: 3    Role: D
 Ověřte, že metriky účinnosti detekce jsou zaznamenávány a pravidelně přehodnocovány s novými zpravodajskými informacemi o hrozbách.

---

### 10.7 Dynamická adaptace bezpečnostní politiky

Aktualizace bezpečnostních politik v reálném čase na základě informací o hrozbách a analýzy chování.

 #10.7.1    Level: 1    Role: D/V
 Ověřte, že bezpečnostní politiky lze aktualizovat dynamicky bez restartu agenta a zároveň zachovat integritu verze politiky.
 #10.7.2    Level: 2    Role: D/V
 Ověřte, že aktualizace politik jsou kryptograficky podepsány autorizovaným bezpečnostním personálem a před aplikací ověřeny.
 #10.7.3    Level: 2    Role: D/V
 Ověřte, že dynamické změny politik jsou zaznamenávány s úplnými auditními stopami včetně odůvodnění, schvalovacích řetězců a postupů pro návrat zpět.
 #10.7.4    Level: 3    Role: D/V
 Ověřte, že adaptivní bezpečnostní mechanismy upravují citlivost detekce hrozeb na základě kontextu rizika a behaviorálních vzorců.
 #10.7.5    Level: 3    Role: D/V
 Ověřte, že rozhodnutí o přizpůsobení politiky jsou vysvětlitelná a obsahují důkazy pro revizi bezpečnostním týmem.

---

### 10.8 Bezpečnostní analýza založená na reflexi

Validace bezpečnosti prostřednictvím sebereflexe agenta a metakognitivní analýzy.

 #10.8.1    Level: 1    Role: D/V
 Ověřte, že mechanismy reflexe agenta zahrnují bezpečnostně orientované sebehodnocení rozhodnutí a akcí.
 #10.8.2    Level: 2    Role: D/V
 Ověřte, zda jsou výstupy reflexe validovány, aby se zabránilo manipulaci mechanismů sebeposouzení pomocí protivných vstupů.
 #10.8.3    Level: 2    Role: D/V
 Ověřte, že meta-kognitivní bezpečnostní analýza identifikuje potenciální zaujatost, manipulaci nebo kompromitaci v procesech uvažování agenta.
 #10.8.4    Level: 3    Role: D/V
 Ověřte, že varování zabezpečení založená na reflexi spouštějí rozšířené monitorování a potenciální pracovní postupy zahrnující lidský zásah.
 #10.8.5    Level: 3    Role: D/V
 Ověřte, že kontinuální učení ze zabezpečovacích reflexí zlepšuje detekci hrozeb, aniž by docházelo ke zhoršení legitimní funkčnosti.

---

### 10.9 Evoluce a bezpečnost samo-zlepšování

Bezpečnostní kontroly pro agentní systémy schopné samo-modifikace a evoluce.

 #10.9.1    Level: 1    Role: D/V
 Ověřte, že schopnosti sebesměřování jsou omezeny na určené bezpečné oblasti s formálními ověřovacími hranicemi.
 #10.9.2    Level: 2    Role: D/V
 Ověřte, že návrhy vývoje podléhají hodnocení dopadů na bezpečnost před jejich zavedením.
 #10.9.3    Level: 2    Role: D/V
 Ověřte, že mechanismy sebezlepšování zahrnují schopnosti zpětného vrácení s ověřením integrity.
 #10.9.4    Level: 3    Role: D/V
 Ověřte, že bezpečnost meta-učení zabraňuje protivníkům v manipulaci s algoritmy zlepšování.
 #10.9.5    Level: 3    Role: D/V
 Ověřte, že rekurzivní samo-vylepšování je omezeno formálními bezpečnostními omezeními s matematickými důkazy konvergence.

---

#### Reference

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

## 11 Ochrana soukromí a správa osobních údajů

### Řídicí cíl

Dodržujte přísná ujištění o ochraně soukromí v celém životním cyklu umělé inteligence—sběr, trénink, inferenci a reakci na incidenty—tak, aby osobní údaje byly zpracovávány pouze s jasným souhlasem, v nejmenším nezbytném rozsahu, s prokazatelným vymazáním a formálními zárukami ochrany soukromí.

---

### 11.1 Anonymizace a minimalizace dat

 #11.1.1    Level: 1    Role: D/V
 Ověřte, že přímé a téměř identifikátory jsou odstraněny nebo zahashovány.
 #11.1.2    Level: 2    Role: D/V
 Ověřte, že automatizované audity měří k-anonymitu/l-rozmanitost a upozorní, když hodnoty klesnou pod stanovené limity.
 #11.1.3    Level: 2    Role: V
 Ověřte, že zprávy o důležitosti rysů modelu prokazují, že nedochází k úniku identifikátorů přes ε = 0,01 vzájemné informace.
 #11.1.4    Level: 3    Role: V
 Ověřte, že formální důkazy nebo certifikace založená na syntetických datech ukazují, že riziko znovuidentifikace je ≤ 0,05 i při útocích pomocí propojení dat.

---

### 11.2 Právo na zapomenutí a vymáhání mazání

 #11.2.1    Level: 1    Role: D/V
 Ověřte, že žádosti o vymazání údajů subjektu se šíří do surových datových sad, kontrolních bodů, embeddingů, protokolů a záloh v rámci dohod o úrovni služeb kratších než 30 dní.
 #11.2.2    Level: 2    Role: D
 Ověřte, že rutiny „machine-unlearning“ fyzicky přeškolují nebo aproximují odstranění pomocí certifikovaných algoritmů pro zapomínání.
 #11.2.3    Level: 2    Role: V
 Ověřte, že hodnocení pomocí shadow-modelu prokazuje, že zapomenuté záznamy ovlivňují méně než 1 % výstupů po procesu unlearningu.
 #11.2.4    Level: 3    Role: V
 Ověřte, že události smazání jsou neměnně zaznamenávány a auditovatelné pro regulátory.

---

### 11.3 Opatření pro ochranu diferencované soukromí

 #11.3.1    Level: 2    Role: D/V
 Ověřte, že panely pro sledování ztráty soukromí upozorňují, když kumulativní ε překročí limity stanovené politikou.
 #11.3.2    Level: 2    Role: V
 Ověřte, že audity ochrany soukromí typu black-box odhadují ε̂ s odchylkou do 10 % od deklarované hodnoty.
 #11.3.3    Level: 3    Role: V
 Ověřte, že formální důkazy zahrnují všechny post-tréninkové doladění a vnoření (embeddingy).

---

### 11.4 Omezení účelu a ochrana proti rozšiřování rozsahu

 #11.4.1    Level: 1    Role: D
 Ověřte, že každý datový soubor a kontrolní bod modelu obsahuje strojově čitelný štítek účelu v souladu s původním souhlasem.
 #11.4.2    Level: 1    Role: D/V
 Ověřte, že runtime monitory zaznamenávají dotazy neslučitelné s deklarovaným účelem a vyvolávají měkké odmítnutí.
 #11.4.3    Level: 3    Role: D
 Ověřte, že brány založené na zásadách jako kódu blokují opětovné nasazení modelů do nových domén bez přezkumu DPIA.
 #11.4.4    Level: 3    Role: V
 Ověřte, že formální důkazy sledovatelnosti ukazují, že každý životní cyklus osobních údajů zůstává v rámci souhlaseného rozsahu.

---

### 11.5 Správa souhlasu a sledování zákonných důvodů

 #11.5.1    Level: 1    Role: D/V
 Ověřte, že platforma pro správu souhlasů (Consent-Management Platform, CMP) zaznamenává stav souhlasu (opt-in), účel a dobu uchovávání pro každý subjekt údajů.
 #11.5.2    Level: 2    Role: D
 Ověřte, že API zpřístupňují souhlasné tokeny; modely musí před inferencí ověřit rozsah tokenu.
 #11.5.3    Level: 2    Role: D/V
 Ověřte, že zamítnutý nebo stažený souhlas zastaví zpracovatelské procesy do 24 hodin.

---

### 11.6 Federované učení s kontrolami soukromí

 #11.6.1    Level: 1    Role: D
 Ověřte, že aktualizace klienta využívají přidání šumu lokální diferenciální ochrany soukromí před agregací.
 #11.6.2    Level: 2    Role: D/V
 Ověřte, že metriky tréninku jsou diferenciálně privátní a nikdy neodhalují ztrátu jednotlivého klienta.
 #11.6.3    Level: 2    Role: V
 Ověřte, že je povolena odolná agregace proti otravě (např. Krum/Trimmed-Mean).
 #11.6.4    Level: 3    Role: V
 Ověřte, že formální důkazy prokazují celkový ε rozpočet s méně než 5 ztrátou užitku.

---

#### Reference

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

## C12 Monitorování, protokolování a detekce anomálií

### Cíl kontroly

Tato sekce poskytuje požadavky na zajištění viditelnosti v reálném čase a forenzní viditelnosti do toho, co model a další součásti umělé inteligence vidí, vykonávají a vracejí, aby bylo možné detekovat hrozby, třídit je a získávat z nich poznatky.

### C12.1 Protokolování požadavků a odpovědí

 #12.1.1    Level: 1    Role: D/V
 Ověřte, že všechny uživatelské výzvy a odpovědi modelu jsou zaznamenány s příslušnými metadaty (např. časové razítko, ID uživatele, ID relace, verze modelu).
 #12.1.2    Level: 1    Role: D/V
 Ověřte, že jsou protokoly ukládány v zabezpečených, přístupem řízených úložištích s odpovídajícími zásadami uchovávání a zálohovacími postupy.
 #12.1.3    Level: 1    Role: D/V
 Ověřte, že systémy pro ukládání logů implementují šifrování dat v klidu i při přenosu, aby chránily citlivé informace obsažené v logech.
 #12.1.4    Level: 1    Role: D/V
 Ověřte, že citlivá data v zadáních a výstupech jsou před protokolováním automaticky zcenzurována nebo maskována, s konfigurovatelnými pravidly cenzurování pro osobně identifikovatelné informace (PII), přihlašovací údaje a důvěrné informace.
 #12.1.5    Level: 2    Role: D/V
 Ověřte, že rozhodnutí politiky a akce filtrování bezpečnosti jsou zaznamenávány s dostatečnými podrobnostmi, aby bylo možné provést audit a ladění systémů moderování obsahu.
 #12.1.6    Level: 2    Role: D/V
 Ověřte, že integrita záznamů je chráněna například pomocí kryptografických podpisů nebo zapisovatelných úložišť pouze pro zápis.

---

### C12.2 Detekce zneužití a oznamování

 #12.2.1    Level: 1    Role: D/V
 Ověřte, že systém detekuje a upozorňuje na známé vzory prolomení zabezpečení, pokusy o injektáž promptu a protivné vstupy pomocí detekce založené na signaturách.
 #12.2.2    Level: 1    Role: D/V
 Ověřte, že systém se integruje se stávajícími platformami pro správu bezpečnostních informací a událostí (SIEM) pomocí standardních formátů a protokolů záznamů.
 #12.2.3    Level: 2    Role: D/V
 Ověřte, že obohacené bezpečnostní události zahrnují kontext specifický pro umělou inteligenci, jako jsou identifikátory modelů, skóre důvěryhodnosti a rozhodnutí bezpečnostních filtrů.
 #12.2.4    Level: 2    Role: D/V
 Ověřte, že detekce behaviorálních odchylek identifikuje neobvyklé vzory konverzace, nadměrné pokusy o opakování nebo systematické prozkoumávací chování.
 #12.2.5    Level: 2    Role: D/V
 Ověřte, že mechanismy upozornění v reálném čase informují bezpečnostní týmy při detekci možných porušení politik nebo pokusů o útok.
 #12.2.6    Level: 2    Role: D/V
 Ověřte, že jsou zahrnuta vlastní pravidla pro detekci vzorců hrozeb specifických pro AI, včetně koordinovaných pokusů o jailbreak, kampaní na injektáž promptu a útoků na extrakci modelu.
 #12.2.7    Level: 3    Role: D/V
 Ověřte, že automatizované pracovní postupy reakce na incidenty dokážou izolovat kompromitované modely, zablokovat škodlivé uživatele a eskalovat kritické bezpečnostní události.

---

### C12.3 Detekce driftu modelu

 #12.3.1    Level: 1    Role: D/V
 Ověřte, že systém sleduje základní metriky výkonu, jako jsou přesnost, skóre důvěry, latence a chybovost napříč verzemi modelu a časovými obdobími.
 #12.3.2    Level: 2    Role: D/V
 Ověřte, že automatické upozornění se spustí, když výkonové metriky překročí předem definované prahové hodnoty degradace nebo se výrazně odchýlí od základních hodnot.
 #12.3.3    Level: 2    Role: D/V
 Ověřte, že monitorování detekce halucinací identifikuje a označuje případy, kdy výstupy modelu obsahují fakticky nesprávné, nekonzistentní nebo vymyšlené informace.

---

### C12.4 Telemetrie výkonnosti a chování

 #12.4.1    Level: 1    Role: D/V
 Ověřte, že jsou průběžně shromažďovány a monitorovány provozní metriky včetně latence požadavků, spotřeby tokenů, využití paměti a propustnosti.
 #12.4.2    Level: 1    Role: D/V
 Ověřte, že jsou sledovány míry úspěšnosti a neúspěšnosti s kategorizací typů chyb a jejich základních příčin.
 #12.4.3    Level: 2    Role: D/V
 Ověřte, že monitorování využití zdrojů zahrnuje využití GPU/CPU, spotřebu paměti a požadavky na úložiště, a že při překročení prahových hodnot je generováno upozornění.

---

### C12.5 Plánování a provádění reakce na incidenty AI

 #12.5.1    Level: 1    Role: D/V
 Ověřte, že plány reakce na incidenty konkrétně řeší bezpečnostní události související s umělou inteligencí, včetně kompromitace modelu, otravování dat a protivníkových útoků.
 #12.5.2    Level: 2    Role: D/V
 Ověřte, že týmy pro reakci na incidenty mají přístup k forenzním nástrojům specifickým pro umělou inteligenci a odborné znalosti k vyšetřování chování modelu a útokových vektorů.
 #12.5.3    Level: 3    Role: D/V
 Ověřte, že post-incidentní analýza zahrnuje zvážení přeškolení modelu, aktualizace bezpečnostních filtrů a integraci získaných poznatků do bezpečnostních kontrol.

---

### C12.5 Detekce poklesu výkonnosti AI

Monitorujte a detekujte zhoršování výkonu a kvality AI modelu v průběhu času.

 #12.5.1    Level: 1    Role: D/V
 Ověřte, že přesnost modelu, preciznost, připomenutí a F1 skóre jsou průběžně sledovány a porovnávány s referenčními hodnotami.
 #12.5.2    Level: 1    Role: D/V
 Ověřte, že detekce posunu dat monitoruje změny ve vstupním rozložení, které mohou ovlivnit výkon modelu.
 #12.5.3    Level: 2    Role: D/V
 Ověřte, že detekce posunu konceptu identifikuje změny ve vztahu mezi vstupy a očekávanými výstupy.
 #12.5.4    Level: 2    Role: D/V
 Ověřte, že pokles výkonu spouští automatizovaná upozornění a zahajuje pracovní postupy pro opětovné školení nebo nahrazení modelu.
 #12.5.5    Level: 3    Role: V
 Ověřte, že analýza příčiny degradace koreluje pokles výkonu se změnami dat, problémy v infrastruktuře nebo vnějšími faktory.

---

### C12.6 Vizualizace DAG a bezpečnost pracovního postupu

Chraňte systémy pro vizualizaci pracovních postupů před únikem informací a útoky na manipulaci.

 #12.6.1    Level: 1    Role: D/V
 Ověřte, že data vizualizace DAG jsou očištěna od citlivých informací před uložením nebo přenosem.
 #12.6.2    Level: 1    Role: D/V
 Ověřte, že přístupová kontrola k vizualizaci pracovních postupů zajišťuje, že pouze autorizovaní uživatelé mohou zobrazovat rozhodovací cesty agentů a stopy odůvodnění.
 #12.6.3    Level: 2    Role: D/V
 Ověřte, že integrita dat DAG je chráněna pomocí kryptografických podpisů a mechanismů pro uchovávání odolného proti manipulaci.
 #12.6.4    Level: 2    Role: D/V
 Ověřte, že systémy vizualizace pracovních toků implementují validaci vstupů, aby předešly injekčním útokům prostřednictvím záměrně upravených dat uzlů nebo hran.
 #12.6.5    Level: 3    Role: D/V
 Ověřte, že aktualizace DAG v reálném čase jsou omezeny rychlostí a validovány, aby se zabránilo útokům typu denial-of-service na vizualizační systémy.

---

### C12.7 Proaktivní monitorování bezpečnostního chování

Detekce a prevence bezpečnostních hrozeb prostřednictvím proaktivní analýzy chování agentů.

 #12.7.1    Level: 1    Role: D/V
 Ověřte, že proaktivní chování agentů je před provedením bezpečnostně ověřeno s integrací hodnocení rizik.
 #12.7.2    Level: 2    Role: D/V
 Ověřte, že spouštěče svobodné iniciativy zahrnují hodnocení bezpečnostního kontextu a posouzení hrozeb.
 #12.7.3    Level: 2    Role: D/V
 Ověřte, že jsou analyzovány vzory proaktivního chování z hlediska možných bezpečnostních dopadů a neúmyslných následků.
 #12.7.4    Level: 3    Role: D/V
 Ověřte, že bezpečnostně kritické proaktivní akce vyžadují explicitní schvalovací řetězce s auditními stopami.
 #12.7.5    Level: 3    Role: D/V
 Ověřte, že detekce behaviorálních anomálií identifikuje odchylky v progrativních vzorcích agentů, které mohou naznačovat kompromitaci.

---

### Reference

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Lidský dohled, odpovědnost a správa

### Řídicí cíl

Tato kapitola poskytuje požadavky na udržování lidského dohledu a jasných řetězců odpovědnosti v AI systémech, zajišťující vysvětlitelnost, transparentnost a etické řízení během celého životního cyklu AI.

---

### C13.1 Mechanismy nouzového vypínače a přepisování

Poskytněte cesty pro ukončení nebo návrat zpět, když je pozorováno nebezpečné chování AI systému.

 #13.1.1    Level: 1    Role: D/V
 Ověřte, že existuje manuální mechanismus nouzového vypnutí pro okamžité zastavení inferencí a výstupů AI modelu.
 #13.1.2    Level: 1    Role: D
 Ověřte, že ovládací prvky přepsání jsou přístupné pouze oprávněnému personálu.
 #13.1.3    Level: 3    Role: D/V
 Ověřte, že postupy pro návrat zpět mohou obnovit předchozí verze modelu nebo operace v bezpečném režimu.
 #13.1.4    Level: 3    Role: V
 Ověřte, že mechanismy přepsání jsou pravidelně testovány.

---

### C13.2 Kontrolní body rozhodování s lidským zapojením

Vyžadovat lidské schválení, pokud sázky překročí předem definované prahové hodnoty rizika.

 #13.2.1    Level: 1    Role: D/V
 Ověřte, že vysoce riziková rozhodnutí umělé inteligence vyžadují před provedením výslovné schválení člověkem.
 #13.2.2    Level: 1    Role: D
 Ověřte, že prahové hodnoty rizika jsou jasně definovány a automaticky spouštějí pracovní postupy pro lidskou kontrolu.
 #13.2.3    Level: 2    Role: D
 Ověřte, že časově citlivá rozhodnutí mají záložní postupy pro případ, kdy nelze získat schválení člověkem v požadovaných časových rámcích.
 #13.2.4    Level: 3    Role: D/V
 Ověřte, že postupy eskalace definují jasné úrovně pravomocí pro různé typy rozhodnutí nebo kategorie rizik, pokud je to relevantní.

---

### C13.3 Řetězec odpovědnosti a auditovatelnost

Zaznamenávejte akce operátora a rozhodnutí modelu.

 #13.3.1    Level: 1    Role: D/V
 Ověřte, že všechna rozhodnutí AI systému a lidské zásahy jsou zaznamenány s časovými značkami, identitami uživatelů a odůvodněním rozhodnutí.
 #13.3.2    Level: 2    Role: D
 Ověřte, že auditní záznamy nemohou být pozměněny a obsahují mechanismy pro ověření integrity.

---

### C13.4 Techniky vysvětlitelné umělé inteligence (Explainable-AI)

Význam povrchových rysů, kontrafaktuální případy a lokální vysvětlení.

 #13.4.1    Level: 1    Role: D/V
 Ověřte, že AI systémy poskytují základní vysvětlení svých rozhodnutí v lidsky čitelném formátu.
 #13.4.2    Level: 2    Role: V
 Ověřte, že kvalita vysvětlení je potvrzena prostřednictvím lidských evaluačních studií a metrik.
 #13.4.3    Level: 3    Role: D/V
 Ověřte, že skóre důležitosti funkcí nebo metody přiřazení (SHAP, LIME, atd.) jsou k dispozici pro kritická rozhodnutí.
 #13.4.4    Level: 3    Role: V
 Ověřte, že kontra-faktuální vysvětlení ukazují, jak by bylo možné upravit vstupy tak, aby se změnily výsledky, pokud je to relevantní pro případ použití a doménu.

---

### C13.5 Karty modelů a oznámení o použití

Udržujte modelové karty pro zamýšlené použití, metriky výkonu a etické úvahy.

 #13.5.1    Level: 1    Role: D
 Ověřte, že modelové karty dokumentují zamýšlené případy použití, omezení a známé režimy selhání.
 #13.5.2    Level: 1    Role: D/V
 Ověřte, že metriky výkonnosti jsou zveřejněny napříč různými relevantními použitými scénáři.
 #13.5.3    Level: 2    Role: D
 Ověřte, že jsou etické úvahy, hodnocení zaujatosti, posouzení spravedlnosti, charakteristiky tréninkových dat a známá omezení tréninkových dat dokumentována a pravidelně aktualizována.
 #13.5.4    Level: 2    Role: D/V
 Ověřte, že modelové karty jsou verzovány a udržovány po celou dobu životního cyklu modelu s evidencí změn.

---

### C13.6 Kvantifikace nejistoty

Šiřte skóre důvěry nebo míry entropie ve odpovědích.

 #13.6.1    Level: 1    Role: D
 Ověřte, že AI systémy poskytují s výstupy také hodnoty pravděpodobnosti nebo míry nejistoty.
 #13.6.2    Level: 2    Role: D/V
 Ověřte, že prahové hodnoty nejistoty spouštějí další kontrolu člověkem nebo alternativní rozhodovací cesty.
 #13.6.3    Level: 2    Role: V
 Ověřte, že metody kvantifikace nejistoty jsou kalibrovány a validovány vůči datům skutečné hodnoty.
 #13.6.4    Level: 3    Role: D/V
 Ověřte, že šíření neurčitosti je zachováno v průběhu vícekrokových pracovních postupů AI.

---

### C13.7 Uživatelské transparentní zprávy

Pravidelně zveřejňujte informace o incidentech, odchylkách a využívání dat.

 #13.7.1    Level: 1    Role: D/V
 Ověřte, že politiky využívání dat a postupy řízení souhlasu uživatelů jsou jasně komunikovány zainteresovaným stranám.
 #13.7.2    Level: 2    Role: D/V
 Ověřte, že jsou prováděny hodnocení dopadů umělé inteligence a že jejich výsledky jsou zahrnuty do zpráv.
 #13.7.3    Level: 2    Role: D/V
 Ověřte, že pravidelně zveřejňované zprávy o transparentnosti obsahují sdělení o incidentech AI a provozních metrikách v přiměřeném rozsahu.

#### Reference

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

## Příloha A: Slovník pojmů

Tento komplexní glosář poskytuje definice klíčových pojmů v oblasti umělé inteligence (AI), strojového učení (ML) a bezpečnosti používaných v celém AISVS, aby bylo zajištěno jasné a společné porozumění.
​
Adversariální příklad: Vstup záměrně vytvořený tak, aby způsobil chybu v AI modelu, často přidáním jemných, pro člověka nepostřehnutelných narušení.
​
Robustnost proti protichůdným útokům – Robustnost proti protichůdným útokům v AI se týká schopnosti modelu udržet si svůj výkon a odolávat tomu, aby byl oklamán nebo manipulován úmyslně vytvořenými škodlivými vstupy navrženými k vyvolání chyb.
​
Agent – AI agenti jsou softwarové systémy, které využívají umělou inteligenci k dosahování cílů a plnění úkolů za uživatele. Projevují schopnosti usuzování, plánování a paměti a mají určitou úroveň autonomie pro přijímání rozhodnutí, učení a přizpůsobování se.
​
Agentní AI: AI systémy, které mohou fungovat s určitou mírou autonomie za účelem dosažení cílů, často přijímají rozhodnutí a provádějí akce bez přímého zásahu člověka.
​
Řízení přístupu založené na atributech (ABAC): paradigma řízení přístupu, kde jsou rozhodnutí o autorizaci založena na atributech uživatele, zdroje, akce a prostředí, vyhodnocovaných v době dotazu.
​
Zadní vchodový útok: Typ útoku otrávením dat, kde je model trénován tak, aby na určité spouštěče reagoval specifickým způsobem, zatímco jinak se chová normálně.
​
Bias: Systematické chyby ve výstupech AI modelu, které mohou vést k nespravedlivým nebo diskriminačním výsledkům pro určité skupiny nebo v konkrétních kontextech.
​
Využití zkreslení: Útočná technika, která využívá známá zkreslení v modelech umělé inteligence k manipulaci výstupů nebo výsledků.
​
Cedar: Jazyk a engine zásad Amazonu pro podrobné oprávnění používané při implementaci ABAC pro AI systémy.
​
Řetězec myšlení: Technika pro zlepšení uvažování v jazykových modelech tím, že se generují mezikroky uvažování před vytvořením konečné odpovědi.
​
Přerušovače obvodu: Mechanismy, které automaticky zastaví provoz AI systému, když jsou překročeny specifické práh rizika.
​
Únik dat: Nezamýšlené prozrazení citlivých informací prostřednictvím výstupů nebo chování AI modelu.
​
Poisoning dat: Úmyslné poškození tréninkových dat za účelem narušení integrity modelu, často se záměrem instalovat zadní vrátka nebo zhoršit výkon.
​
Diferenciální soukromí – Diferenciální soukromí je matematicky přesný rámec pro zveřejňování statistických informací o datech, který přitom chrání soukromí jednotlivých subjektů dat. Umožňuje držiteli dat sdílet souhrnné vzory skupiny při omezení úniku informací o konkrétních jednotlivcích.
​
Embeddingy: Husté vektorové reprezentace dat (text, obrázky atd.), které zachycují sémantický význam v prostorů s vysokou dimenzionalitou.
​
Vysvětlitelnost – Vysvětlitelnost v umělé inteligenci (AI) je schopnost systému AI poskytnout lidsky srozumitelné důvody pro svá rozhodnutí a předpovědi, čímž nabízí vhled do svých vnitřních procesů.
​
Vysvětlitelná umělá inteligence (XAI): Systémy umělé inteligence navržené tak, aby poskytovaly lidem srozumitelná vysvětlení svých rozhodnutí a chování prostřednictvím různých technik a rámců.
​
Federované učení: přístup strojového učení, při kterém jsou modely trénovány na více decentralizovaných zařízeních obsahujících lokální datové vzorky, aniž by docházelo k výměně samotných dat.
​
Ochranné zábrany: Omezující opatření implementovaná k zabránění systémům umělé inteligence produkovat škodlivé, zaujaté nebo jinak nežádoucí výstupy.
​
Halucinace – Halucinace AI se týká jevu, kdy AI model generuje nesprávné nebo zavádějící informace, které nejsou založeny na jeho tréninkových datech nebo faktické realitě.
​
Human-in-the-Loop (HITL): Systémy navržené tak, aby vyžadovaly lidský dohled, ověření nebo zásah v klíčových rozhodovacích bodech.
​
Infrastruktura jako kód (IaC): Správa a poskytování infrastruktury prostřednictvím kódu namísto manuálních procesů, což umožňuje bezpečnostní skenování a konzistentní nasazení.
​
Jailbreak: Techniky používané k obcházení bezpečnostních opatření v systémech umělé inteligence, zejména u velkých jazykových modelů, za účelem vytváření zakázaného obsahu.
​
Nejnižší potřebná oprávnění: bezpečnostní zásada udělování pouze minimálních nezbytných přístupových práv uživatelům a procesům.
​
LIME (Lokální interpretable modelově-agnostické vysvětlení): Technika vysvětlení predikcí jakéhokoli klasifikátoru strojového učení pomocí jeho lokální aproximace interpretovatelným modelem.
​
Útok na zjištění členství: útok, jehož cílem je určit, zda byl konkrétní datový bod použit k tréninku modelu strojového učení.
​
MITRE ATLAS: Adversariální hrozebný krajina pro systémy umělé inteligence; databáze znalostí adversariálních taktik a technik proti AI systémům.
​
Model Card – Model Card je dokument, který poskytuje standardizované informace o výkonu AI modelu, jeho omezeních, zamýšlených použitích a etických aspektech s cílem podpořit transparentnost a odpovědný vývoj AI.
​
Extrahování modelu: útok, při kterém protivník opakovaně pokládá dotazy cílovému modelu, aby vytvořil funkčně podobnou kopii bez autorizace.
​
Modelová inverze: útok, který se snaží rekonstruovat tréninková data analýzou výstupů modelu.
​
Správa životního cyklu modelu – Správa životního cyklu AI modelu je proces dohledu nad všemi fázemi existence AI modelu, včetně jeho návrhu, vývoje, nasazení, monitorování, údržby a konečného vyřazení, s cílem zajistit, že model zůstává efektivní a v souladu s cíli.
​
Poisoning modelu: Zavádění zranitelností nebo zadních vrátek přímo do modelu během procesu tréninku.
​
Krádež modelu: Získání kopie nebo aproximace proprietárního modelu prostřednictvím opakovaných dotazů.
​
Multi-agentní systém: Systém složený z více vzájemně komunikujících AI agentů, z nichž každý může mít odlišné schopnosti a cíle.
​
OPA (Open Policy Agent): Open-source engine pro zásady, který umožňuje jednotné prosazování zásad napříč celým stackem.
​
Strojové učení zachovávající soukromí (PPML): Techniky a metody pro trénování a nasazení modelů strojového učení při ochraně soukromí trénovacích dat.
​
Vkládání podnětů (Prompt Injection): Útok, při kterém jsou do vstupů vloženy škodlivé instrukce za účelem přepsání zamýšleného chování modelu.
​
RAG (Generování podporované vyhledáváním): Technika, která vylepšuje velké jazykové modely tím, že před generováním odpovědi získává relevantní informace z externích zdrojů znalostí.
​
Red-Teaming: Praxe aktivního testování AI systémů simulací protivnických útoků za účelem identifikace zranitelností.
​
SBOM (Seznam komponent softwaru): Formální záznam obsahující podrobnosti a vztahy v dodavatelském řetězci různých komponent použitých při vytváření softwaru nebo AI modelů.
​
SHAP (SHapley Additive exPlanations): Hra teoretický přístup k vysvětlení výstupu jakéhokoli modelu strojového učení výpočtem příspěvku každé vlastnosti k predikci.
​
Útok na dodavatelský řetězec: Kompromitace systému zaměřením na méně zabezpečené prvky v jeho dodavatelském řetězci, jako jsou knihovny třetích stran, datové sady nebo předtrénované modely.
​
Přenose učení: Technika, kdy je model vyvinutý pro jeden úkol znovu použit jako výchozí bod pro model určený k druhému úkolu.
​
Vektorová databáze: Specializovaná databáze navržená k ukládání vysoce dimenzionálních vektorů (embeddings) a provádění efektivního vyhledávání podobnosti.
​
Skenování zranitelností: Automatizované nástroje, které identifikují známé bezpečnostní zranitelnosti v softwarových komponentách, včetně AI frameworků a závislostí.
​
Vodoznakování: Techniky pro vložení nepostřehnutelných značek do obsahu generovaného umělou inteligencí za účelem sledování jeho původu nebo detekce generování AI.
​
Zranitelnost Zero-Day: Dříve neznámá zranitelnost, kterou mohou útočníci zneužít dříve, než vývojáři vytvoří a nasadí bezpečnostní záplatu.

## Příloha B: Odkazy

### TODO

## Příloha C: Správa a dokumentace bezpečnosti AI

### Cíl

Tato příloha poskytuje základní požadavky pro zavedení organizačních struktur, politik a procesů k řízení bezpečnosti umělé inteligence v průběhu celého životního cyklu systému.

---

### AC.1 Přijetí rámce pro řízení rizik AI

Poskytnout formální rámec pro identifikaci, hodnocení a zmírňování rizik specifických pro AI v průběhu životního cyklu systému.

 #AC.1.1    Level: 1    Role: D/V
 Ověřte, že metodologie hodnocení rizik specifická pro umělou inteligenci je zdokumentována a implementována.
 #AC.1.2    Level: 2    Role: D
 Ověřte, že hodnocení rizik jsou prováděna v klíčových fázích životního cyklu AI a před významnými změnami.
 #AC.1.3    Level: 3    Role: D/V
 Ověřte, že rámec řízení rizik je v souladu s etablovanými standardy (např. NIST AI RMF).

---

### AC.2 Bezpečnostní politika a postupy pro umělou inteligenci

Definujte a prosazujte organizační standardy pro bezpečný vývoj, nasazení a provoz AI.

 #AC.2.1    Level: 1    Role: D/V
 Ověřte, že existují zdokumentované zásady bezpečnosti AI.
 #AC.2.2    Level: 2    Role: D
 Ověřte, že zásady jsou revidovány a aktualizovány alespoň jednou ročně a po významných změnách v oblasti hrozeb.
 #AC.2.3    Level: 3    Role: D/V
 Ověřte, že politiky pokrývají všechny kategorie AISVS a platné regulační požadavky.

---

### AC.3 Role a odpovědnosti pro bezpečnost AI

Stanovte jasnou odpovědnost za bezpečnost umělé inteligence napříč organizací.

 #AC.3.1    Level: 1    Role: D/V
 Ověřte, že jsou zdokumentovány role a odpovědnosti v oblasti bezpečnosti umělé inteligence.
 #AC.3.2    Level: 2    Role: D
 Ověřte, že odpovědné osoby mají odpovídající bezpečnostní odborné znalosti.
 #AC.3.3    Level: 3    Role: D/V
 Ověřte, že pro systémy s vysokým rizikem AI je zřízena etická komise pro AI nebo řídicí rada.

---

### AC.4 Prosazování etických zásad v oblasti umělé inteligence

Zajistit, aby AI systémy fungovaly v souladu s ustálenými etickými principy.

 #AC.4.1    Level: 1    Role: D/V
 Ověřte, že existují etické směrnice pro vývoj a nasazení umělé inteligence.
 #AC.4.2    Level: 2    Role: D
 Ověřte, že jsou zavedeny mechanismy pro detekci a hlášení etických porušení.
 #AC.4.3    Level: 3    Role: D/V
 Ověřte, že pravidelné etické revize nasazených AI systémů jsou prováděny.

---

### AC.5 Monitorování souladu s předpisy umělé inteligence

Udržujte povědomí o vznikajících předpisech týkajících se AI a dodržujte je.

 #AC.5.1    Level: 1    Role: D/V
 Ověřte, zda existují procesy pro identifikaci platných předpisů týkajících se AI.
 #AC.5.2    Level: 2    Role: D
 Ověřte, že je posuzována shoda se všemi regulačními požadavky.
 #AC.5.3    Level: 3    Role: D/V
 Ověřte, že regulační změny spouštějí včasné revize a aktualizace AI systémů.

#### Reference

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Dodatek D: Správa a ověřování bezpečného kódování asistovaného umělou inteligencí

### Cíl

Tato kapitola definuje základní organizační kontroly pro bezpečné a efektivní používání nástrojů asistovaného kódování AI během vývoje softwaru, zajišťující bezpečnost a sledovatelnost v celém životním cyklu softwaru (SDLC).

---

### AD.1 Pracovní postup bezpečného kódování podporovaný umělou inteligencí

Integrujte nástroje umělé inteligence do zabezpečeného životního cyklu vývoje softwaru (SSDLC) organizace, aniž by došlo k oslabení stávajících bezpečnostních bran.

 #AD.1.1    Level: 1    Role: D/V
 Ověřte, že zdokumentovaný pracovní postup popisuje, kdy a jak mohou nástroje umělé inteligence generovat, refaktorovat nebo kontrolovat kód.
 #AD.1.2    Level: 2    Role: D
 Ověřte, že pracovní tok odpovídá každé fázi SSDLC (návrh, implementace, revize kódu, testování, nasazení).
 #AD.1.3    Level: 3    Role: D/V
 Ověřte, že metriky (např. hustota zranitelností, průměrný čas k detekci) jsou shromažďovány pro kód generovaný AI a porovnávány s referenčními hodnotami vytvořenými pouze lidmi.

---

### AD.2 Kvalifikace nástroje AI a modelování hrozeb

Zajistěte, aby byly nástroje pro kódování AI před jejich zavedením hodnoceny z hlediska bezpečnostních schopností, rizik a dopadu na dodavatelský řetězec.

 #AD.2.1    Level: 1    Role: D/V
 Ověřte, že model hrozeb pro každý AI nástroj identifikuje zneužití, inverzi modelu, únik dat a rizika spojená s řetězcem závislostí.
 #AD.2.2    Level: 2    Role: D
 Ověřte, zda hodnocení nástrojů zahrnují statickou/dynamickou analýzu všech lokálních komponent a posouzení SaaS koncových bodů (TLS, autentizace/autorizace, zaznamenávání).
 #AD.2.3    Level: 3    Role: D/V
 Ověřte, že hodnocení následují uznávaný rámec a jsou znovu prováděna po významných změnách verze.

---

### AD.3 Bezpečná správa výzev a kontextu

Zabraňte úniku tajných informací, proprietárního kódu a osobních údajů při tvorbě promptů nebo kontextů pro AI modely.

 #AD.3.1    Level: 1    Role: D/V
 Ověřte, že písemné pokyny zakazují zasílání tajných informací, přihlašovacích údajů nebo utajovaných dat v dotazech.
 #AD.3.2    Level: 2    Role: D
 Ověřte, že technické kontroly (redakce na straně klienta, schválené kontextové filtry) automaticky odstraňují citlivé artefakty.
 #AD.3.3    Level: 3    Role: D/V
 Ověřte, že výzvy a odpovědi jsou tokenizovány, šifrovány během přenosu i v klidu a doby uchování odpovídají zásadám klasifikace dat.

---

### AD.4 Validace kódu generovaného umělou inteligencí

Detekujte a odstraňte zranitelnosti zavedené výstupem AI před sloučením nebo nasazením kódu.

 #AD.4.1    Level: 1    Role: D/V
 Ověřte, že kód generovaný umělou inteligencí je vždy podroben lidské kontrole kódu.
 #AD.4.2    Level: 2    Role: D
 Ověřte, že automatizované skenery (SAST/IAST/DAST) běží na každém pull requestu obsahujícím kód generovaný umělou inteligencí a blokují sloučení v případě kritických zjištění.
 #AD.4.3    Level: 3    Role: D/V
 Ověřte, že diferenciální fuzz testing nebo testy založené na vlastnostech dokazují bezpečnostně kritické chování (např. validaci vstupů, logiku autorizace).

---

### AD.5 Vysvětlitelnost a sledovatelnost návrhů kódu

Poskytněte auditorům a vývojářům přehled o tom, proč bylo navrženo určité doporučení a jak se vyvíjelo.

 #AD.5.1    Level: 1    Role: D/V
 Ověřte, že páry výzev/odpovědí jsou zaznamenávány s ID commitů.
 #AD.5.2    Level: 2    Role: D
 Ověřte, že vývojáři mohou zobrazit citace modelu (tréninkové úryvky, dokumentaci) podporující návrh.
 #AD.5.3    Level: 3    Role: D/V
 Ověřte, že zprávy o vysvětlitelnosti jsou uloženy spolu s návrhovými artefakty a jsou uváděny v bezpečnostních přezkumech, čímž jsou splněny zásady sledovatelnosti podle normy ISO/IEC 42001.

---

### AD.6 Kontinuální zpětná vazba a dolaďování modelu

Zlepšujte bezpečnost výkonu modelu v průběhu času a zároveň zabraňujte negativnímu posunu.

 #AD.6.1    Level: 1    Role: D/V
 Ověřte, že vývojáři mohou označit nezajištěné nebo nesouladné návrhy a že tyto označení jsou sledována.
 #AD.6.2    Level: 2    Role: D
 Ověřte, že agregovaná zpětná vazba informuje periodické doladění nebo generování s podporou vyhledávání pomocí ověřených korpusů bezpečného kódování (např. OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Ověřte, že uzavřený evaluační systém provádí regresní testy po každém doladění; bezpečnostní metriky musí před nasazením dosáhnout nebo překonat předchozí základní hodnoty.

---

#### Reference

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Příloha E: Příklady nástrojů a rámců

### Cíl

Tato kapitola poskytuje příklady nástrojů a rámců, které mohou podpořit implementaci nebo splnění daného požadavku AISVS. Neměly by být považovány za doporučení nebo schválení týmem AISVS či projektem OWASP GenAI Security.

---

### AE.1 Správa tréninkových dat a řízení zaujatosti

Nástroje používané pro analýzu dat, správu a řízení předsudků.

 #AE.1.1    Section: 1.1
 Nástroje pro správu datového inventáře: Nástroje pro správu datového inventáře jako...
 #AE.1.2    Section: 1.2
 Šifrování během přenosu Používejte TLS pro aplikace založené na HTTPS, s nástroji jako openSSL a pythonův`ssl`knihovna.

---

### AE.2 Validace uživatelského vstupu

Nástroje pro zpracování a validaci vstupů uživatelů.

 #AE.2.1    Section: 2.1
 Nástroje pro obranu proti prompt injection: Používejte nástroje pro ochranu jako NVIDIA NeMo nebo Guardrails AI.

---

