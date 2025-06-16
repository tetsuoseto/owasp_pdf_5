# C6 tiekimo grandinės saugumas modeliams, sistemoms ir duomenims

## Kontrolės tikslas

AI tiekimo grandinės atakos išnaudoja trečiųjų šalių modelius, karkasus ar duomenų rinkinius, kad įterptų užpakalinius vartus, šališkumą arba pažeidžiamą kodą. Šios kontrolės užtikrina visapusišką kilmės sekimą, pažeidžiamumo valdymą ir stebėjimą, siekiant apsaugoti visą modelio gyvavimo ciklą.

---

## C6.1 Iš anksto apmokyto modelio tikrinimas ir kilmė

Įvertinkite ir patikrinkite trečiųjų šalių modelių kilmę, licencijas ir paslėptas elgsenas prieš atliekant bet kokį tobulinimą ar diegimą.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Patikrinkite, ar kiekvienas trečiosios šalies modelio artefaktas turi pasirašytą kilmės įrašą, identifikuojantį šaltinio saugyklą ir commit hash.              |   1   | D/V  |
| 6.1.2 | Patvirtinkite, kad modeliai prieš importavimą yra nuskaityti automatizuotomis priemonėmis, siekiant aptikti kenksmingas sluoksnius ar Trojos arklių trigerius. |   1   | D/V  |
| 6.1.3 | Patikrinkite, ar perdavimo mokymosi tobulinimas praeina priešininkų vertinimą, kad aptiktų paslėptas elgsenas.                                                 |   2   |  D   |
| 6.1.4 | Patikrinkite, ar modelio licencijos, eksporto kontrolės žymos ir duomenų kilmės pareiškimai yra įrašyti ML-BOM įraše.                                          |   2   |  V   |
| 6.1.5 | Patikrinkite, ar didelės rizikos modeliai (viešai įkelti svoriai, nepatikrinti kūrėjai) lieka izoliuoti iki žmogaus peržiūros ir patvirtinimo.                 |   3   | D/V  |

---

## C6.2 Sistemų karkasų ir bibliotekų nuskaitymas

Nuolat tikrinkite mašininio mokymosi sistemas ir bibliotekas dėl CVE spragų ir kenkėjiško kodo, kad vykdymo aplinka išliktų saugi.

|   #   | Description                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Patikrinkite, ar CI kanalai vykdo priklausomybių skenerius AI karkasams ir svarbioms bibliotekoms.                                |   1   | D/V  |
| 6.2.2 | Patikrinkite, ar kritinės pažeidžiamybės (CVSS ≥ 7,0) neleidžia diegti atvaizdų į gamybą.                                         |   1   | D/V  |
| 6.2.3 | Patikrinkite, ar statinė kodo analizė vykdoma ant šakotuose ar įsigytuose ML bibliotekų.                                          |   2   |  D   |
| 6.2.4 | Patikrinkite, ar karkaso atnaujinimo pasiūlymai apima saugumo poveikio vertinimą, nurodantį viešai prieinamus CVE srautus.        |   2   |  V   |
| 6.2.5 | Patikrinkite, ar vykdymo metu jutikliai įspėja apie netikėtus dinaminės bibliotekos įkėlimus, kurie skiriasi nuo pasirašyto SBOM. |   3   |  V   |

---

## C6.3 Priklausomybių fiksavimas ir patikra

Pririškite kiekvieną priklausomybę prie nekeičiamų digestų ir atkurkite kūrimus, kad užtikrintumėte identiškus, be klastojimo artefaktus.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Patikrinkite, ar visi paketų valdytojai užtikrina versijų fiksavimą naudojant užrakto failus.                                         |   1   | D/V  |
| 6.3.2 | Patikrinkite, ar konteinerių nuorodose naudojami nekintami santraukos vietoj kintamų žymų.                                            |   1   | D/V  |
| 6.3.3 | Patikrinkite, ar atkartojamumo patikros procesai palygina maišos reikšmes tarp CI vykdymų, siekiant užtikrinti identiškus rezultatus. |   2   |  D   |
| 6.3.4 | Patikrinkite, ar kūrimo patvirtinimai saugomi 18 mėnesių audito sekimumo užtikrinimui.                                                |   2   |  V   |
| 6.3.5 | Patikrinkite, ar pasibaigusios priklausomybės sukelia automatinius PR atnaujinti arba padalinti užfiksuotas versijas.                 |   3   |  D   |

---

## C6.4 Patikimo šaltinio vykdymas

Leisti atsisiųsti artefaktus tik iš kriptografiškai patikrintų, organizacijos patvirtintų šaltinių ir blokuoti viską, kas kitas.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Patikrinkite, ar modelio svoriai, duomenų rinkiniai ir konteineriai atsisiunčiami tik iš patvirtintų domenų arba vidinių registrų.             |   1   | D/V  |
| 6.4.2 | Patikrinkite, ar Sigstore/Cosign parašai patvirtina leidėjo tapatybę prieš saugant artefaktus vietoje.                                         |   1   | D/V  |
| 6.4.3 | Patikrinkite, ar eigos tarpiniai serveriai blokuoja neautentifikuotus artefaktų atsisiuntimus, siekiant įgyvendinti patikimos kilmės politiką. |   2   |  D   |
| 6.4.4 | Patikrinkite, ar krūva leidžiamų saugyklų sąrašai peržiūrimi kas ketvirtį, pateikiant verslo pagrįstumą kiekvienam įrašui.                     |   2   |  V   |
| 6.4.5 | Patikrinkite, ar politikos pažeidimai sukelia artefaktų izoliavimą ir priklausančių vamzdyno vykdymų atšaukimą.                                |   3   |  V   |

---

## C6.5 Trečiųjų šalių duomenų rinkinio rizikos įvertinimas

Įvertinkite išorinius duomenų rinkinius dėl užnuodijimo, šališkumo ir teisinių atitikties reikalavimų bei stebėkite juos per visą jų gyvavimo ciklą.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Patikrinkite, ar išoriniai duomenų rinkiniai yra įvertinami dėl užteršimo rizikos (pvz., duomenų pirštų atspaudų nustatymas, išskirtinių reikšmių aptikimas). |   1   | D/V  |
| 6.5.2 | Patikrinkite, ar šališkumo metrika (demografinis lygybės principas, lygi galimybė) yra apskaičiuojama prieš duomenų rinkinio patvirtinimą.                    |   1   |  D   |
| 6.5.3 | Patikrinkite, ar ML-BOM įrašuose yra užfiksuoti duomenų rinkinių kilmės ir licencijos sąlygos.                                                                |   2   |  V   |
| 6.5.4 | Patikrinkite, ar periodinis stebėjimas aptinka perėjimą arba gedimą talpinamuose duomenų rinkiniuose.                                                         |   2   |  V   |
| 6.5.5 | Patikrinkite, ar neleistinas turinys (autorių teisės, asmeninė identifikuojama informacija) yra pašalintas automatinio šalinimo būdu prieš treniruotę.        |   3   |  D   |

---

## C6.6 Tiekimo grandinės atakų stebėjimas

Anksti aptikite tiekimo grandinės grėsmes naudodamiesi CVE srautais, audito žurnalo analitika ir raudonosios komandos simuliacijomis.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.6.1 | Patikrinkite, ar CI/CD audito žurnalai perduodami SIEM sistemai anomalinių paketų traukimo ar pažeistų statybos etapų aptikimams.                            |   1   |  V   |
| 6.6.2 | Patikrinkite, ar incidentų reagavimo veiksmų planuose yra įtrauktos modelių ar bibliotekų atstatymo (rollback) procedūros dėl pažeidimų.                     |   2   |  D   |
| 6.6.3 | Patikrinkite, ar grėsmių intelektinės informacijos praturtėjimo žymos pažymi ML specifinius indikatorius (pvz., modelio užnuodijimo IoC) įspėjimų atrankoje. |   3   |  V   |

---

## C6.7 ML-BOM modelio artefaktams

Generuokite ir pasirašykite detalias ML specifines SBOM (ML-BOM), kad galutiniai vartotojai galėtų patikrinti komponentų vientisumą diegimo metu.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Patikrinkite, ar kiekvienas modelio artefaktas publikuoja ML‑BOM, kuriame išvardyti duomenų rinkiniai, svoriai, hiperparametrai ir licencijos. |   1   | D/V  |
| 6.7.2 | Patikrinkite, ar ML-BOM generavimas ir Cosign pasirašymas yra automatizuoti CI ir privalomi sujungimui.                                        |   1   | D/V  |
| 6.7.3 | Patikrinkite, ar ML‑BOM pilnumo patikrinimai sustabdo kompiliavimą, jei trūksta bet kokios komponento metaduomenų (hash, licencija).           |   2   |  D   |
| 6.7.4 | Patvirtinkite, kad galutiniai vartotojai gali užklausti ML-BOM per API, siekdami patikrinti importuotus modelius diegimo metu.                 |   2   |  V   |
| 6.7.5 | Patikrinkite, ar ML-BOM yra valdomi versijomis ir palyginami, siekiant aptikti neautorizuotus pakeitimus.                                      |   3   |  V   |

---

## Nuorodos

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

