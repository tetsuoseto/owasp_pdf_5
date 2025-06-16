# Řízení přístupu C5 a identita pro AI komponenty a uživatele

## Cíl kontroly

Efektivní kontrola přístupu pro AI systémy vyžaduje robustní správu identity, autorizaci založenou na kontextu a vynucování v čase běhu podle zásad zero-trust. Tyto kontroly zajišťují, že lidé, služby a autonomní agenti komunikují s modely, daty a výpočetními zdroji pouze v rámci explicitně udělených rozsahů, s průběžnou verifikací a možnostmi auditu.

---

## C5.1 Správa identity a autentizace

Zřiďte kryptograficky zabezpečené identity pro všechny entity s vícefaktorovou autentizací pro privilegované operace.

|   #   | Description                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.1.1 | Ověřte, že všichni lidskí uživatelé a servisní identity (service principals) se autentizují prostřednictvím centralizovaného podnikového poskytovatele identity (IdP) pomocí protokolů OIDC/SAML s unikátními mapováními identity na token (bez sdílených účtů nebo přihlašovacích údajů). |   1   | D/V  |
| 5.1.2 | Ověřte, že vysoce rizikové operace (nasazení modelu, export vah, přístup k tréninkovým datům, změny produkční konfigurace) vyžadují vícefaktorové ověření nebo zvýšené ověření s opětovným potvrzením relace.                                                                              |   1   | D/V  |
| 5.1.3 | Ověřte, že noví hlavní uživatelé procházejí ověřením identity v souladu s NIST 800-63-3 IAL-2 nebo ekvivalentními standardy před získáním přístupu k produkčnímu systému.                                                                                                                  |   2   |  D   |
| 5.1.4 | Ověřte, že přehledy přístupů jsou prováděny čtvrtletně s automatizovanou detekcí neaktivních účtů, vynucováním rotace přihlašovacích údajů a pracovními procesy odebrání přístupů.                                                                                                         |   2   |  V   |
| 5.1.5 | Ověřte, že federované AI agenty se autentizují pomocí podepsaných JWT tvrzení, která mají maximální životnost 24 hodin a obsahují kryptografický důkaz původu.                                                                                                                             |   3   | D/V  |

---

## C5.2 Autorizace zdrojů a princip nejmenších privilegií

Implementujte jemně odstupňované přístupové kontroly ke všem AI zdrojům s explicitními modely oprávnění a auditními stopami.

|   #   | Description                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Ověřte, že každý AI zdroj (datové sady, modely, koncové body, vektorové kolekce, indexy vnoření, výpočetní instance) uplatňuje řízení přístupu založené na rolích s explicitními seznamy povolených a politikami implicitního zamítnutí. |   1   | D/V  |
| 5.2.2 | Ověřte, že principy nejmenších oprávnění jsou ve výchozím nastavení u servisních účtů vynucovány, začínaje oprávněními pouze pro čtení a je vyžadováno zdokumentované obchodní odůvodnění pro přístup k zápisu.                          |   1   | D/V  |
| 5.2.3 | Ověřte, že všechny změny v řízení přístupu jsou propojeny s schválenými požadavky na změnu a jsou neměnitelně zaznamenány s časovými razítky, identitou aktéra, identifikátory zdrojů a rozdíly v oprávněních.                           |   1   |  V   |
| 5.2.4 | Ověřte, že štítky klasifikace dat (PII, PHI, kontrolované vývozem, vlastnická práva) se automaticky přenášejí na odvozené zdroje (embeddingy, cache promptů, výstupy modelů) s konzistentním vynucováním zásad.                          |   2   |  D   |
| 5.2.5 | Ověřte, že pokusy o neoprávněný přístup a události eskalace oprávnění vyvolávají v reálném čase upozornění s kontextovými metadaty do systémů SIEM do 5 minut.                                                                           |   2   | D/V  |

---

## C5.3 Dynamické vyhodnocování politiky

Nasazujte systémy řízení přístupu založené na atributech (ABAC) pro kontextově uvědomělá rozhodnutí o autorizaci s možností auditu.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Ověřte, že rozhodnutí o autorizaci jsou externalizována do vyhrazeného politického enginu (OPA, Cedar nebo ekvivalentního), který je přístupný přes autentizovaná API s kryptografickou ochranou integrity. |   1   | D/V  |
| 5.3.2 | Ověřte, že politiky vyhodnocují dynamické atributy během běhu, včetně úrovně oprávnění uživatele, klasifikace citlivosti zdroje, kontextu požadavku, izolace nájemce a časových omezení.                    |   1   | D/V  |
| 5.3.3 | Ověřte, že definice politik jsou verzovány, posuzovány kolegy a validovány pomocí automatizovaného testování v CI/CD pipelines před nasazením do produkce.                                                  |   2   |  D   |
| 5.3.4 | Ověřte, že výsledky hodnocení zásad zahrnují strukturovaná odůvodnění rozhodnutí a jsou přenášeny do systémů SIEM pro korelační analýzu a reporting souladu.                                                |   2   |  V   |
| 5.3.5 | Ověřte, že hodnoty doby platnosti (TTL) mezipaměti zásad nepřesahují 5 minut pro vysoce citlivé zdroje a 1 hodinu pro standardní zdroje s možnostmi neplatnosti mezipaměti.                                 |   3   | D/V  |

---

## C5.4 Vynucování bezpečnosti v době dotazu

Implementujte bezpečnostní kontroly na úrovni databáze s povinným filtrováním a zásadami zabezpečení na úrovni řádků.

|   #   | Description                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Ověřte, že všechny dotazy do vektorové databáze a SQL obsahují povinné bezpečnostní filtry (ID nájemce, štítky citlivosti, rozsah uživatele), které jsou vynucovány na úrovni databázového jádra, nikoli v aplikačním kódu. |   1   | D/V  |
| 5.4.2 | Ověřte, že zásady zabezpečení na úrovni řádků (RLS) a maskování na úrovni polí jsou povoleny s děděním zásad pro všechny vektorové databáze, vyhledávací indexy a tréninkové datové sady.                                   |   1   | D/V  |
| 5.4.3 | Ověřte, že neúspěšná hodnocení autorizace zabrání „útokům zmateného zástupce“ tím, že okamžitě přeruší dotazy a vrátí explicitní chybové kódy autorizace místo vrácení prázdných výsledkových sad.                          |   2   |  D   |
| 5.4.4 | Ověřte, zda je latence vyhodnocování politiky nepřetržitě monitorována s automatizovanými upozorněními na podmínky časového překročení, které by mohly umožnit obcházení autorizace.                                        |   2   |  V   |
| 5.4.5 | Ověřte, že mechanismy opakování dotazů znovu vyhodnocují autorizační politiky, aby zohlednily dynamické změny oprávnění v rámci aktivních uživatelských relací.                                                             |   3   | D/V  |

---

## Filtrovaní výstupu C5.5 a prevence ztráty dat

Nasadit kontrolní mechanismy pro následné zpracování za účelem zabránění neoprávněnému zpřístupnění dat v obsahu generovaném umělou inteligencí.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.5.1 | Ověřte, že mechanismy filtrování po inferenci prohledávají a redigují neoprávněné osobní identifikovatelné informace (PII), klasifikované informace a vlastnická data před doručením obsahu žadatelům. |   1   | D/V  |
| 5.5.2 | Ověřte, že citace, odkazy a zdrojové atributy ve výstupech modelu jsou validovány podle oprávnění volajícího a jsou odstraněny, pokud je zjištěn neoprávněný přístup.                                  |   1   | D/V  |
| 5.5.3 | Ověřte, že jsou dodržována omezení formátu výstupu (sanitované PDF, obrázky bez metadata, schválené typy souborů) na základě úrovní oprávnění uživatelů a klasifikace dat.                             |   2   |  D   |
| 5.5.4 | Ověřte, že algoritmy pro cenzurování jsou deterministické, verzovacím systémem řízené a udržují protokoly auditu na podporu vyšetřování dodržování předpisů a forenzní analýzy.                        |   2   |  V   |
| 5.5.5 | Ověřte, že události vysokého rizika redakce generují adaptivní záznamy, které zahrnují kryptografické haše původního obsahu pro forenzní získání bez vystavení dat.                                    |   3   |  V   |

---

## C5.6 Izolace více nájemců

Zajistit kryptografickou a logickou izolaci mezi nájemci ve sdílené AI infrastruktuře.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Ověřte, že paměťové prostory, úložiště embeddingů, cache položky a dočasné soubory jsou odděleny podle jmenného prostoru pro každého nájemce s bezpečným vymazáním při odstranění nájemce nebo ukončení relace. |   1   | D/V  |
| 5.6.2 | Ověřte, že každý požadavek na API obsahuje autentizovaný identifikátor nájemce, který je kryptograficky ověřen vůči kontextu relace a oprávněním uživatele.                                                     |   1   | D/V  |
| 5.6.3 | Ověřte, že síťové politiky implementují pravidla výchozího zamítnutí pro komunikaci mezi nájemci v rámci služebních sítí a platforem pro orchestraci kontejnerů.                                                |   2   |  D   |
| 5.6.4 | Ověřte, že klíče pro šifrování jsou jedinečné pro každého nájemce s podporou klíčů spravovaných zákazníkem (CMK) a kryptografickou izolací mezi datovými úložišti nájemců.                                      |   3   |  D   |

---

## C5.7 Autorizace autonomních agentů

Řízení oprávnění pro AI agenty a autonomní systémy prostřednictvím tokenů schopností s omezeným rozsahem a kontinuální autorizace.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Ověřte, že autonomní agenti obdrží omezené tokeny schopností, které explicitně vyjmenovávají povolené akce, přístupné zdroje, časová omezení a provozní podmínky.                                                                            |   1   | D/V  |
| 5.7.2 | Ověřte, že vysoce rizikové schopnosti (přístup k souborovému systému, provádění kódu, volání externích API, finanční transakce) jsou ve výchozím nastavení zakázány a jejich aktivace vyžaduje výslovná oprávnění s obchodními odůvodněními. |   1   | D/V  |
| 5.7.3 | Ověřte, že tokeny schopností jsou vázány na uživatelské relace, obsahují kryptografickou ochranu integrity a zajišťují, že nemohou být uchovávány nebo znovu použity v režimu offline.                                                       |   2   |  D   |
| 5.7.4 | Ověřte, že akce iniciované agentem podléhají sekundární autorizaci prostřednictvím ABAC politického engine s plným kontextovým hodnocením a auditním záznamem.                                                                               |   2   |  V   |
| 5.7.5 | Ověřte, že chybové podmínky agenta a zpracování výjimek zahrnují informace o rozsahu schopností k podpoře analýzy incidentů a forenzního vyšetřování.                                                                                        |   3   |  V   |

---

## Reference

### Normy a rámce

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Průvodce implementací

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Bezpečnost specifická pro umělou inteligenci

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

