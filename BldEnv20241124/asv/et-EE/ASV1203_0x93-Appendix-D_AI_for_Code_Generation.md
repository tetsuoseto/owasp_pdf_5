# Lisa D: AI-toega turvalise kodeerimise haldamine ja kontrollimine

## Eesmärk

See peatükk määratleb aluskorralduslikud kontrollid AI-toega kodeerimistööriistade ohutuks ja tõhusaks kasutamiseks tarkvaraarenduse ajal, tagades turvalisuse ja jälgitavuse kogu tarkvaraarenduse elutsüklis (SDLC).

---

## AD.1 Tehisintellekti toega turvalise kodeerimise töövoog

Integreeri tehisintellekti tööriistad organisatsiooni turvalise tarkvaraarenduse elutsüklisse (SSDLC) ilma olemasolevaid turvamehhanisme nõrgestamata.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.1.1 | Kinnitage, et dokumenteeritud töövoog kirjeldab, millal ja kuidas tehisintellekti tööriistad võivad koodi genereerida, refaktoreerida või üle vaadata.                                     |   1   | D/V  |
| AD.1.2 | Kinnitage, et töövoog vastab igale SSDLC faasile (kujundus, rakendamine, koodikontroll, testimine, juurutamine).                                                                           |   2   |  D   |
| AD.1.3 | Kontrollige, et mõõdikud (nt haavatavuse tihedus, keskmine tuvastamisaeg) kogutakse tehisintellekti loodud koodi kohta ja võrreldakse ainult inimeste loodud koodipõhiste baasväärtustega. |   3   | D/V  |

---

## AD.2 AI tööriista kvalifitseerimine ja ohuhindamine

Veenduge, et AI kodeerimisvahendid oleksid enne kasutuselevõttu hinnatud turvaomaduste, riskide ja tarneahela mõju osas.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Kontrollige, et iga tehisintellekti tööriista ohumudel tuvastaks väärkasutuse, mudeli pööramise, andmete lekkimise ja sõltuvusketi riskid.                                                   |   1   | D/V  |
| AD.2.2 | Kinnitage, et tööriistade hindamised hõlmavad mis tahes kohalike komponentide staatilist/dünaamilist analüüsi ja SaaS-i lõpp-punktide (TLS, autentimine/autorisatsioon, logimine) hindamist. |   2   |  D   |
| AD.2.3 | Kinnitage, et hinnangud järgivad tunnustatud raamistikku ja neid teostatakse uuesti pärast olulisi versioonimuudatusi.                                                                       |   3   | D/V  |

---

## AD.3 Turvaline käskude ja konteksti haldamine

Takistage saladuste, patenteeritud koodi ja isikuandmete lekkimist AI mudelitele mõeldud promptide või kontekstide koostamisel.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Kontrollige, kas kirjalik juhend keelab saata saladusi, mandaate või klassifitseeritud andmeid päringutes.                                                                            |   1   | D/V  |
| AD.3.2 | Kinnitage, et tehnilised kontrollid (klientpoole redigeerimine, heaks kiidetud kontekstifiltrid) eemaldavad tundlikud andmed automaatselt.                                            |   2   |  D   |
| AD.3.3 | Kontrollige, et promptid ja vastused oleksid tokeniseeritud, krüpteeritud nii ülekandes kui ka salvestatuna ning et säilitamisperioodid vastaksid andmeklassifikatsiooni poliitikale. |   3   | D/V  |

---

## AD.4 AI-Geneerimise Koodi Kontrollimine

Tuvastage ja kõrvaldage AI väljundist tingitud turvaaugud enne koodi ühendamist või juurutamist.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Kinnitage, et AI-l põhinev kood läbib alati inimkoodi ülevaatuse.                                                                                                                            |   1   | D/V  |
| AD.4.2 | Kinnitage, et iga tehisintellekti genereeritud koodi sisaldava päringu puhul käivituvad automatiseeritud skannerid (SAST/IAST/DAST) ning kriitiliste leidude korral takistatakse ühendamist. |   2   |  D   |
| AD.4.3 | Kinnita, et diferentsiaalne fuzzi testimine või omaduspõhised testid tõestavad turvakriitilisi käitumisi (nt sisendi valideerimine, autoriseerimisloogika).                                  |   3   | D/V  |

---

## AD.5 Koodi Soovituste Selgitavus ja Jälgitavus

Andaudiitoritele ja arendajatele ülevaade selle kohta, miks soovitus tehti ja kuidas see arenes.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.5.1 | Kinnitage, et prompti/vastuse paarid salvestatakse commit ID-dega.                                                                                                 |   1   | D/V  |
| AD.5.2 | Kinnitage, et arendajad saavad näidata mudeli tsitaate (treenimisnäiteid, dokumentatsiooni), mis toetavad soovitust.                                               |   2   |  D   |
| AD.5.3 | Kontrollige, et selgitatavusaruanded oleksid salvestatud koos disainiarhitektuuride ja viidatud turvakontrollides, järgides ISO/IEC 42001 jälgitavuse põhimõtteid. |   3   | D/V  |

---

## AD.6 Jätkuv tagasiside ja mudeli peenhäälestus

Parandage mudeli turvalisuse jõudlust aja jooksul, samal ajal vältides negatiivset nihket.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| AD.6.1 | Kinnitage, et arendajad saavad märgistada ebaturvalisi või mittevastavaid soovitusi ning et need märgistused jälgitakse.                                                                   |   1   | D/V  |
| AD.6.2 | Kinnitage, et koondatud tagasiside suunab perioodilist täpsustamist või turvaliselt kontrollitud koodikirjutamise korpustega (nt OWASP Cheat Sheets) täiustatud andmekorraldust.           |   2   |  D   |
| AD.6.3 | Kontrollige, et suletud tsükli hindamise süsteem käivitaks iga peenhäälestuse järel regressioonitestid; turvameetrikud peavad vastama või ületama eelnevaid baasvõrdlusi enne juurutamist. |   3   | D/V  |

---

### Viited

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

