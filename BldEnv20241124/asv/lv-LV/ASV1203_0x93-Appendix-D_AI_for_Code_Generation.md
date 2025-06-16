# Pielikums D: Mākslīgā intelekta atbalstīta drošas kodēšanas pārvaldība un verifikācija

## Mērķis

Šajā nodaļā tiek definētas pamatorganizatoriskās kontroles drošai un efektīvai mākslīgā intelekta atbalstītu koda veidošanas rīku izmantošanai programmatūras izstrādes procesā, nodrošinot drošību un izsekojamību visā programmatūras izstrādes dzīves ciklā (SDLC).

---

## AD.1 AI atbalstīts droša kodēšanas darba plūsma

Integrēt mākslīgā intelekta rīkus organizācijas drošas programmatūras izstrādes dzīves ciklā (SSDLC), nesamazinot esošo drošības barjeru efektivitāti.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Pārbaudiet, vai dokumentētā darba plūsma apraksta, kad un kā mākslīgā intelekta rīki var ģenerēt, refaktorēt vai pārskatīt kodu.                                                      |   1   | D/V  |
| AD.1.2 | Pārbaudiet, vai darba plūsma atbilst katrai SSDLC fāzei (dizains, ieviešana, koda pārskatīšana, testēšana, izvietošana).                                                              |   2   |  D   |
| AD.1.3 | Pārbaudiet, vai metrikas (piemēram, ievainojamības blīvums, vidējais laiks līdz atklāšanai) tiek vāktas par AI radīto kodu un salīdzinātas ar tikai cilvēku izstrādātajiem etaloniem. |   3   | D/V  |

---

## AD.2 AI rīka kvalifikācija un draudu modelēšana

Nodrošiniet, ka AI kodēšanas rīki tiek novērtēti attiecībā uz drošības iespējām, riskiem un piegādes ķēdes ietekmi pirms to ieviešanas.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Pārbaudiet, vai katram AI rīkam izstrādātajam draudu modelim ir identificēti ļaunprātīgas izmantošanas, modeļa inversijas, datu noplūdes un atkarību ķēdes riski.                             |   1   | D/V  |
| AD.2.2 | Pārliecinieties, ka rīku novērtējumos ir iekļauta jebkuru lokālo komponentu statiskā/dinamiskā analīze un SaaS galapunktu (TLS, autentifikācija/autorizācija, žurnālu veidošana) novērtējums. |   2   |  D   |
| AD.2.3 | Pārliecinieties, ka novērtējumi tiek veikti saskaņā ar atzītu sistēmu un tiek atkārtoti pēc būtiskām versiju izmaiņām.                                                                        |   3   | D/V  |

---

## AD.3 Droša komandu un konteksta pārvaldība

Novērst slepenās, patentētā koda un personas datu noplūdi, veidojot uzvednes vai kontekstus mākslīgā intelekta modeļiem.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Pārbaudiet, vai rakstiskās vadlīnijas aizliedz nosūtīt slepenus datus, piekļuves informāciju vai klasificētu informāciju ievades vaicājumos.                                    |   1   | D/V  |
| AD.3.2 | Pārbaudiet, vai tehniskie kontroles mehānismi (klienta pusē veiktā redakcija, apstiprinātie konteksta filtri) automātiski noņem sensitīvus artefaktus.                          |   2   |  D   |
| AD.3.3 | Pārbaudiet, vai uzvednes un atbildes tiek tokenizētas, šifrētas pārsūtīšanas laikā un glabāšanas laikā, kā arī vai to glabāšanas periodi atbilst datu klasifikācijas politikai. |   3   | D/V  |

---

## AD.4 AI Ģenerēta koda validācija

Atklājiet un novēršiet AI radītās ievainojamības pirms koda apvienošanas vai izvietošanas.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Pārliecinieties, ka mākslīgi ģenerētais kods vienmēr tiek pakļauts cilvēka izstrādātāja pārskatam.                                                                                                         |   1   | D/V  |
| AD.4.2 | Pārliecinieties, ka automatizētie skeneri (SAST/IAST/DAST) tiek palaisti katrā pieprasījumā apvienošanai, kas satur mākslīgā intelekta ģenerētu kodu, un bloķējiet apvienošanu kritisku problēmu gadījumā. |   2   |  D   |
| AD.4.3 | Pārbaudiet, vai diferenciālā fuzz testēšana vai īpašību balstītie testi pierāda drošības kritiskās darbības (piemēram, ievades validācija, autorizācijas loģika).                                          |   3   | D/V  |

---

## AD.5 Koda ieteikumu paskaidrojamība un izsekojamība

Nodrošiniet auditoriem un izstrādātājiem ieskatu par to, kāpēc tika izteikts ieteikums un kā tas attīstījās.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Pārliecinieties, ka pieprasījuma/atbildes pāri tiek reģistrēti ar apņemšanās ID.                                                                                             |   1   | D/V  |
| AD.5.2 | Pārbaudiet, vai izstrādātāji var parādīt modeļa atsauces (apmācības fragmentus, dokumentāciju), kas pamato ieteikumu.                                                        |   2   |  D   |
| AD.5.3 | Pārliecinieties, ka skaidrojuma pārskati tiek glabāti kopā ar dizaina artefaktiem un atsaukti drošības apskatos, nodrošinot ISO/IEC 42001 izsekojamības principu ievērošanu. |   3   | D/V  |

---

## AD.6 Nepārtraukta atsauksmju saņemšana un modeļa precīza regulēšana

Uzlabot modeļa drošības sniegumu laikam ritot, vienlaikus novēršot negatīvu novirzi.

|   #    | Description                                                                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Pārliecinieties, ka izstrādātāji var atzīmēt nedrošus vai neatbilstošus ieteikumus, un ka šīs atzīmes tiek izsekotas.                                                                                    |   1   | D/V  |
| AD.6.2 | Pārliecinieties, ka apkopotā atgriezeniskā saite informē periodisku smalko pielāgošanu vai izgūšanas pastiprinātu ģenerēšanu ar pārbaudītiem droša kodēšanas korpusiem (piemēram, OWASP Cheat Sheets).   |   2   |  D   |
| AD.6.3 | Pārliecinieties, ka slēgtas cilpas novērtēšanas sistēma veic regresijas testus pēc katras papildus apmācības; drošības metrikai jāatbilst vai jāpārsniedz iepriekšējās robežvērtības pirms izvietošanas. |   3   | D/V  |

---

### Atsauces

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

