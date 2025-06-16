# C13 Inimeste järelevalve, vastutus ja juhtimine

## Kontrollieesmärk

See peatükk sätestab nõuded inimjärelevalve ja selgete vastutusahelate säilitamiseks tehisintellekti süsteemides, tagades seletatavuse, läbipaistvuse ja eetilise juhtimise kogu tehisintellekti elutsükli vältel.

---

## C13.1 Tapmislüliti ja ülekirjutamise mehhanismid

Kui AI-süsteemis täheldatakse ebaturvalist käitumist, tuleb pakkuda sulgemis- või tagasikerimise teed.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Kontrollige, kas eksisteerib käsitsi toimiv katkestuslüliti mehhanism, mis võimaldab kohe peatada tehisintellekti mudeli järeldamise ja väljundid. |   1   | D/V  |
| 13.1.2 | Veenduge, et ülekirjutusjuhte saavad kasutada ainult volitatud isikud.                                                                             |   1   |  D   |
| 13.1.3 | Kontrollige, et tagasikerimise protseduurid suudavad taastada varasemad mudeliversioonid või turvarežiimi toimingud.                               |   3   | D/V  |
| 13.1.4 | Veenduge, et ülekirjutamise mehhanismid testitakse regulaarselt.                                                                                   |   3   |  V   |

---

## C13.2 Inimene-tsüklis otsuste kontrollpunktid

Nõuda inimkinnitusi, kui panused ületavad eelnevalt määratletud riskipiirid.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.2.1 | Kinnitage, et kõrge riskiastmega tehisintellekti otsused vajavad täideviimiseks selgesõnalist inimliku heakskiitu.                                     |   1   | D/V  |
| 13.2.2 | Kinnitage, et riskitasemed on selgelt määratletud ja käivitavad automaatselt inimeste ülevaatuse töövood.                                              |   1   |  D   |
| 13.2.3 | Kontrollige, et ajasensitiivsetel otsustel oleks varuplaanid juhuks, kui inimeste kinnitust ei õnnestu nõutud ajaraamide sees saada.                   |   2   |  D   |
| 13.2.4 | Kinnitage, et eskalatsiooniprotseduurid määratlevad erinevate otsusetüüpide või riskikategooriate jaoks selged volitustasandid, kui see on asjakohane. |   3   | D/V  |

---

## C13.3 Vastutusahela ja auditeeritavus

Logi operaatori toimingud ja mudeli otsused.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Kinnitage, et kõik tehisintellektisüsteemi otsused ja inimsekkumised on logitud koos ajatempli, kasutajatunnuste ja otsuse põhjendusega. |   1   | D/V  |
| 13.3.2 | Kontrollige, et auditeerimislogisid ei saa muuta ja need sisaldavad terviklikkuse kontrollimehhanisme.                                   |   2   |  D   |

---

## C13.4 Selgitavad tehisintellekti tehnikad

Pinnafunktsioonide tähtsus, vastasfaktid ja lokaalsed selgitused.

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Kinnitage, et tehisintellekti süsteemid annavad oma otsuste kohta põhjalikke ja inimloetavas vormis selgitusi.                                                       |   1   | D/V  |
| 13.4.2 | Kinnitage, et seletuste kvaliteeti kontrollitakse inimtõenduse uuringute ja mõõdikute abil.                                                                          |   2   |  V   |
| 13.4.3 | Kinnitage, et oluliste otsuste jaoks on olemas tunnuse olulisuse skoorid või atribuutide meetodid (SHAP, LIME jne).                                                  |   3   | D/V  |
| 13.4.4 | Kontrollige, kas kontrafaktuaalsed seletused näitavad, kuidas sisendeid saab muuta tulemuste muutmiseks, kui see on kasutusjuhtu ja valdkonda arvestades asjakohane. |   3   |  V   |

---

## C13.5 Mudelikaardid ja kasutusavaldused

Hooldage mudelikaarte kavandatud kasutuse, tulemuslikkuse mõõdikute ja eetiliste kaalutluste kohta.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.5.1 | Kinnitage, et mudelikaardid dokumenteerivad kavandatud kasutusjuhtumeid, piiranguid ja teadaolevaid rikkeviise.                                                                                  |   1   |  D   |
| 13.5.2 | Kinnitage, et erinevate asjakohaste kasutusjuhtude jõudlusmõõdikud on avalikustatud.                                                                                                             |   1   | D/V  |
| 13.5.3 | Kontrollige, et eetilised kaalutlused, eelarvamuste hindamised, õiglusanalüüsid, treeningandmete omadused ja teadaolevad treeningandmete piirangud on dokumenteeritud ja regulaarselt uuendatud. |   2   |  D   |
| 13.5.4 | Veenduge, et mudelikaardid oleksid versioonihalduses ja neid hooldatakse kogu mudeli elutsükli vältel koos muudatuste jälgimisega.                                                               |   2   | D/V  |

---

## C13.6 Ebakindluse kvantifitseerimine

Levitage vastustes usalduskoefitsientide või entroopiamõõdikute väärtusi.

|   #    | Description                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Kinnitage, et tehisintellekti süsteemid annavad oma väljunditega koos usalduspunkti või ebakindluse hinnangu.         |   1   |  D   |
| 13.6.2 | Kinnitage, et ebakindluse läved käivitavad täiendava inimvaatluse või alternatiivsed otsustusrajad.                   |   2   | D/V  |
| 13.6.3 | Kinnitage, et ebakindluse kvantifitseerimise meetodid on kalibreeritud ja valideeritud võrdluseks tõese andmestikuga. |   2   |  V   |
| 13.6.4 | Kinnitage, et ebakindluse levik säilib mitmeastmeliste tehisintellekti töövoogude kaudu.                              |   3   | D/V  |

---

## C13.7 Kasutajatele suunatud läbipaistvuse aruanded

Esitage perioodilisi avalikustamisi intsidentide, nihke ja andmete kasutamise kohta.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Kinnitage, et andmekasutuspoliitikad ja kasutajakokkuleppe haldamise tavad on sidusrühmadele selgelt edastatud.                                         |   1   | D/V  |
| 13.7.2 | Kinnitage, et tehisintellekti mõjuhinnangud viiakse läbi ja tulemused kaasatakse aruandlusse.                                                           |   2   | D/V  |
| 13.7.3 | Kontrollige, et regulaarselt avaldatavad läbipaistvusaruanded avalikustaksid tehisintellekti intsidente ja tööalaseid mõõdikuid mõistliku detailsusega. |   2   | D/V  |

### Viited

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

