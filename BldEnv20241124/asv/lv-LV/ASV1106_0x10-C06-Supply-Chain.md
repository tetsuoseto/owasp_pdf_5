# C6 Modeļu, rāmju un datu piegādes ķēdes drošība

## Kontroles mērķis

Mākslīgā intelekta piegādes ķēdes uzbrukumi izmanto trešo personu modeļus, ietvarus vai datu kopas, lai iegultu aizmugures durvis, novirzes vai izmantojamu kodu. Šie kontroles mehānismi nodrošina pilnīgu izcelsmi, ievainojamību pārvaldību un uzraudzību, lai aizsargātu visu modeļa dzīves ciklu.

---

## C6.1 Iepriekšapmācīta modeļa pārbaude un izcelsme

Novērtējiet un autentificējiet trešo pušu modeļu izcelsmi, licences un slēptās uzvedības pirms jebkādas papildapmācības vai izvietošanas.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Pārbaudiet, vai katrs trešās puses modeļa artefakts ietver parakstītu izcelsmes ierakstu, kurā norādīts avota repozitorijs un komita hašs.                      |   1   | D/V  |
| 6.1.2 | Pārliecinieties, ka modeļi tiek pārbaudīti, vai tajos nav ļaunprātīgu slāņu vai Trojas cēlāju, izmantojot automatizētus rīkus pirms importa.                    |   1   | D/V  |
| 6.1.3 | Pārbaudiet, vai pārmācīšanās precizēšana iztur pretinieku novērtējumu, lai atklātu slēptas uzvedības.                                                           |   2   |  D   |
| 6.1.4 | Pārliecinieties, ka modeļa licences, eksporta kontroles tagi un datu izcelsmes paziņojumi ir ierakstīti ML-BOM ierakstā.                                        |   2   |  V   |
| 6.1.5 | Pārbaudiet, vai augsta riska modeļi (publiski augšupielādētie svaru faili, neapstiprināti radītāji) paliek karantīnā līdz cilvēka pārskatam un apstiprināšanai. |   3   | D/V  |

---

## C6.2 Ietvara un bibliotēkas skenēšana

Pastāvīgi skenējiet ML ietvarus un bibliotēkas, lai atklātu CVE un ļaunprātīgu kodu, nodrošinot izpildes vides kaudzes drošību.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.2.1 | Pārliecinieties, ka CI cauruļvadi veic atkarību skeneru darbību AI ietvaros un kritiskajās bibliotēkās.                              |   1   | D/V  |
| 6.2.2 | Pārbaudiet, vai kritiskās ievainojamības (CVSS ≥ 7,0) bloķē pāreju uz ražošanas attēliem.                                            |   1   | D/V  |
| 6.2.3 | Pārbaudiet, vai statiskā koda analīze tiek veikta uz atzarotām vai piegādātām mašīnmācīšanās bibliotēkām.                            |   2   |  D   |
| 6.2.4 | Pārbaudiet, vai ietvara jaunināšanas priekšlikumos ir iekļauta drošības ietekmes novērtējuma atsauce uz publiskajiem CVE datplūsmām. |   2   |  V   |
| 6.2.5 | Pārbaudiet, vai darbības laika sensori brīdina par negaidītām dinamisko bibliotēku ielādēm, kas novirzās no parakstītā SBOM.         |   3   |  V   |

---

## C6.3 Atkarību fiksēšana un pārbaude

Piespraužiet katru atkarību pie nemaināmiem hešiem un reproducējiet būves, lai garantētu identiskas, neskartas artefaktus.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Pārbaudiet, vai visi pakotņu pārvaldnieki nodrošina versiju fiksēšanu, izmantojot bloķēšanas failus.                                 |   1   | D/V  |
| 6.3.2 | Pārbaudiet, vai konteineru atsaucēs tiek izmantoti nemaināmi digesti, nevis maināmas birkas.                                         |   1   | D/V  |
| 6.3.3 | Pārliecinieties, ka pārbaudes reproducible‑build salīdzina hašus dažādos CI izpildījumos, lai nodrošinātu identiskus rezultātus.     |   2   |  D   |
| 6.3.4 | Pārbaudiet, vai būvniecības apliecinājumi tiek glabāti 18 mēnešus audita izsekojamībai.                                              |   2   |  V   |
| 6.3.5 | Pārliecinieties, ka derīguma termiņa beigušās atkarības izsauc automatizētus PR atjauninājumu vai forku pinotu versiju atjaunošanai. |   3   |  D   |

---

## C6.4 Uzticama avota īstenošana

Ļauj lejupielādēt artefaktus tikai no kriptogrāfiski pārbaudītiem, organizācijas apstiprinātiem avotiem un bloķē visu pārējo.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Pārliecinieties, ka modeļa svaru faili, datu kopas un konteineri tiek lejupielādēti tikai no apstiprinātām domēnu vietnēm vai iekšējiem reģistriem. |   1   | D/V  |
| 6.4.2 | Pārliecinieties, ka Sigstore/Cosign paraksti apstiprina izdevēja identitāti pirms artefaktu saglabāšanas lokāli.                                    |   1   | D/V  |
| 6.4.3 | Pārliecinieties, ka izejas starpniekserveri bloķē neaizsargātas artefaktu lejupielādes, lai nodrošinātu uzticamu avotu politiku.                    |   2   |  D   |
| 6.4.4 | Pārbaudiet, vai repozitorija atļauto saraksts tiek pārskatīts ceturksnī, sniedzot pierādījumus par katras ieraksta biznesa pamatojumu.              |   2   |  V   |
| 6.4.5 | Pārbaudiet, vai politikas pārkāpumi izraisa artefaktu karantīnu un atkarīgo cauruļvadu izpildes reversāciju.                                        |   3   |  V   |

---

## C6.5 Trešās puses datu kopas riska novērtējums

Novērtējiet ārējos datu kopumus attiecībā uz inficēšanu, aizspriedumiem un juridisko atbilstību, kā arī uzraugiet tos visā to darbības ciklā.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Pārliecinieties, ka ārējie datu kopumi tiek pakļauti saindēšanas riska vērtēšanai (piemēram, datu pirkstu nospiedumu analīze, noviržu noteikšana).                         |   1   | D/V  |
| 6.5.2 | Pārliecinieties, ka novirzes metrikas (demogrāfiskā izlīdzinātība, vienlīdzīgas iespējas) tiek aprēķinātas pirms datu kopas apstiprināšanas.                               |   1   |  D   |
| 6.5.3 | Pārbaudiet, vai ML‑BOM ierakstos ir iekļauti datu kopu izcelsmes un licences noteikumi.                                                                                    |   2   |  V   |
| 6.5.4 | Pārbaudiet, vai periodiska uzraudzība konstatē nogrimušanos vai bojājumus mitinātajos datu kopās.                                                                          |   2   |  V   |
| 6.5.5 | Pārliecinieties, ka aizliegtā satura (autortiesību, personiski identificējamas informācijas) noņemšana tiek veikta ar automatizētas attīrīšanas palīdzību pirms apmācības. |   3   |  D   |

---

## C6.6 Piegādes ķēdes uzbrukuma uzraudzība

Agrīni atklājiet piegādes ķēdes draudus, izmantojot CVE plūsmas, revīzijas žurnālu analītiku un sarkano komandu simulācijas.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Pārbaudiet, vai CI/CD revīzijas žurnāli tiek plūdināti SIEM noteikumiem, lai atklātu anomālijas pakotņu lejupielādē vai modificētu būvniecības soļos. |   1   |  V   |
| 6.6.2 | Pārliecinieties, ka incidentu atbildes darbību plānos ir iekļautas atcelšanas procedūras kompromitētiem modeļiem vai bibliotēkām.                     |   2   |  D   |
| 6.6.3 | Pārbaudiet, vai draudu izlūkošanas bagātināšanas atzīmes iezīmē ML specifiskos indikatorus (piemēram, modeļa piesārņošanas IoC) trauksmes kārtotnē.   |   3   |  V   |

---

## C6.7 ML‑BOM modeļa artefaktiem

Ģenerējiet un parakstiet detalizētas mašīnmācīšanās specifiskas SBOM (ML-BOM), lai turpmākie lietotāji varētu pārbaudīt komponentu integritāti izvietošanas laikā.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Pārliecinieties, ka katrs modeļa artefakts publicē ML-BOM, kurā ir norādītas datu kopas, svari, hiperparametri un licences.                     |   1   | D/V  |
| 6.7.2 | Pārliecinieties, ka ML-BOM ģenerēšana un Cosign parakstīšana ir automatizēta nepārtrauktās integrācijas (CI) vidē un nepieciešama apvienošanai. |   1   | D/V  |
| 6.7.3 | Pārbaudiet, vai ML-BOM pilnības pārbaudes neļauj veidot, ja trūkst kādas komponentes metadatu (haša, licences).                                 |   2   |  D   |
| 6.7.4 | Pārbaudiet, vai lejupējie lietotāji var vaicāt ML-BOM caur API, lai validētu importētos modeļus izvietošanas laikā.                             |   2   |  V   |
| 6.7.5 | Pārbaudiet, vai ML-BOM ir versiju kontrolēti un tiek salīdzināti, lai atklātu nesankcionētas izmaiņas.                                          |   3   |  V   |

---

## Atsauces

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

