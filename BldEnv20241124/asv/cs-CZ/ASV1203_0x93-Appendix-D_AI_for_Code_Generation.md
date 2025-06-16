# Dodatek D: Správa a ověřování bezpečného kódování asistovaného umělou inteligencí

## Cíl

Tato kapitola definuje základní organizační kontroly pro bezpečné a efektivní používání nástrojů asistovaného kódování AI během vývoje softwaru, zajišťující bezpečnost a sledovatelnost v celém životním cyklu softwaru (SDLC).

---

## AD.1 Pracovní postup bezpečného kódování podporovaný umělou inteligencí

Integrujte nástroje umělé inteligence do zabezpečeného životního cyklu vývoje softwaru (SSDLC) organizace, aniž by došlo k oslabení stávajících bezpečnostních bran.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Ověřte, že zdokumentovaný pracovní postup popisuje, kdy a jak mohou nástroje umělé inteligence generovat, refaktorovat nebo kontrolovat kód.                                      |   1   | D/V  |
| AD.1.2 | Ověřte, že pracovní tok odpovídá každé fázi SSDLC (návrh, implementace, revize kódu, testování, nasazení).                                                                        |   2   |  D   |
| AD.1.3 | Ověřte, že metriky (např. hustota zranitelností, průměrný čas k detekci) jsou shromažďovány pro kód generovaný AI a porovnávány s referenčními hodnotami vytvořenými pouze lidmi. |   3   | D/V  |

---

## AD.2 Kvalifikace nástroje AI a modelování hrozeb

Zajistěte, aby byly nástroje pro kódování AI před jejich zavedením hodnoceny z hlediska bezpečnostních schopností, rizik a dopadu na dodavatelský řetězec.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Ověřte, že model hrozeb pro každý AI nástroj identifikuje zneužití, inverzi modelu, únik dat a rizika spojená s řetězcem závislostí.                                         |   1   | D/V  |
| AD.2.2 | Ověřte, zda hodnocení nástrojů zahrnují statickou/dynamickou analýzu všech lokálních komponent a posouzení SaaS koncových bodů (TLS, autentizace/autorizace, zaznamenávání). |   2   |  D   |
| AD.2.3 | Ověřte, že hodnocení následují uznávaný rámec a jsou znovu prováděna po významných změnách verze.                                                                            |   3   | D/V  |

---

## AD.3 Bezpečná správa výzev a kontextu

Zabraňte úniku tajných informací, proprietárního kódu a osobních údajů při tvorbě promptů nebo kontextů pro AI modely.

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.3.1 | Ověřte, že písemné pokyny zakazují zasílání tajných informací, přihlašovacích údajů nebo utajovaných dat v dotazech.                 |   1   | D/V  |
| AD.3.2 | Ověřte, že technické kontroly (redakce na straně klienta, schválené kontextové filtry) automaticky odstraňují citlivé artefakty.     |   2   |  D   |
| AD.3.3 | Ověřte, že výzvy a odpovědi jsou tokenizovány, šifrovány během přenosu i v klidu a doby uchování odpovídají zásadám klasifikace dat. |   3   | D/V  |

---

## AD.4 Validace kódu generovaného umělou inteligencí

Detekujte a odstraňte zranitelnosti zavedené výstupem AI před sloučením nebo nasazením kódu.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Ověřte, že kód generovaný umělou inteligencí je vždy podroben lidské kontrole kódu.                                                                                             |   1   | D/V  |
| AD.4.2 | Ověřte, že automatizované skenery (SAST/IAST/DAST) běží na každém pull requestu obsahujícím kód generovaný umělou inteligencí a blokují sloučení v případě kritických zjištění. |   2   |  D   |
| AD.4.3 | Ověřte, že diferenciální fuzz testing nebo testy založené na vlastnostech dokazují bezpečnostně kritické chování (např. validaci vstupů, logiku autorizace).                    |   3   | D/V  |

---

## AD.5 Vysvětlitelnost a sledovatelnost návrhů kódu

Poskytněte auditorům a vývojářům přehled o tom, proč bylo navrženo určité doporučení a jak se vyvíjelo.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Ověřte, že páry výzev/odpovědí jsou zaznamenávány s ID commitů.                                                                                                                                |   1   | D/V  |
| AD.5.2 | Ověřte, že vývojáři mohou zobrazit citace modelu (tréninkové úryvky, dokumentaci) podporující návrh.                                                                                           |   2   |  D   |
| AD.5.3 | Ověřte, že zprávy o vysvětlitelnosti jsou uloženy spolu s návrhovými artefakty a jsou uváděny v bezpečnostních přezkumech, čímž jsou splněny zásady sledovatelnosti podle normy ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Kontinuální zpětná vazba a dolaďování modelu

Zlepšujte bezpečnost výkonu modelu v průběhu času a zároveň zabraňujte negativnímu posunu.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Ověřte, že vývojáři mohou označit nezajištěné nebo nesouladné návrhy a že tyto označení jsou sledována.                                                                          |   1   | D/V  |
| AD.6.2 | Ověřte, že agregovaná zpětná vazba informuje periodické doladění nebo generování s podporou vyhledávání pomocí ověřených korpusů bezpečného kódování (např. OWASP Cheat Sheets). |   2   |  D   |
| AD.6.3 | Ověřte, že uzavřený evaluační systém provádí regresní testy po každém doladění; bezpečnostní metriky musí před nasazením dosáhnout nebo překonat předchozí základní hodnoty.     |   3   | D/V  |

---

### Reference

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

