# 11 Privātuma aizsardzība un personisko datu pārvaldība

## Kontroles mērķis

Uzturiet stingras privātuma garantijas visā mākslīgā intelekta dzīves ciklā — datu vākšanā, apmācībā, inferencē un incidentu novēršanā — tā, lai personas dati tiktu apstrādāti tikai ar skaidru piekrišanu, pēc iespējas ierobežotāka apjoma, ar pārbaudāmu dzēšanu un oficiālām privātuma garantijām.

---

## 11.1 Anonimizācija un datu minimizācija

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Pārbaudiet, vai tiešie un kvazi-identifikatori ir noņemti vai hasēti.                                                                                |   1   | D/V  |
| 11.1.2 | Pārbaudiet, vai automatizētās revīzijas mēra k-anonimitāti/l-daudzveidību un brīdina, kad sliekšņi noslīd zem politikas līmeņa.                      |   2   | D/V  |
| 11.1.3 | Pārbaudiet, vai modeļa iezīmju nozīmīguma pārskati pierāda, ka nav identifikatoru noplūdes, kas pārsniedz ε = 0,01 savstarpējās informācijas līmeni. |   2   |  V   |
| 11.1.4 | Pārliecinieties, ka formālie pierādījumi vai sintezētās datu sertifikācija rāda, ka pāratpazīšanas risks ir ≤ 0,05 pat saites uzbrukumu gadījumā.    |   3   |  V   |

---

## 11.2 Tiesības tikt aizmirstam un dzēšanas izpilde

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Pārbaudiet, vai datu subjektu dzēšanas pieprasījumi tiek izplatīti uz izejas datu kopām, kontrolpunktiem, iegultajām telpām, žurnāliem un dublējumiem servisa līmeņa līgumā, kas nepārsniedz 30 dienas. |   1   | D/V  |
| 11.2.2 | Pārbaudiet, vai "mašīnmācīšanās aizmirsšanas" rutīnas fiziski pārtrenē vai aptuveni noņem datus, izmantojot sertificētas aizmirstošanas algoritmus.                                                     |   2   |  D   |
| 11.2.3 | Pārbaudiet, vai ēnas modeļa novērtējums pierāda, ka aizmirsto ierakstu ietekme pēc dzēšanās ir mazāka par 1% no rezultātiem.                                                                            |   2   |  V   |
| 11.2.4 | Pārbaudiet, vai dzēšanas notikumi tiek nemainīgi reģistrēti un ir pārbaudāmi regulatoriem.                                                                                                              |   3   |  V   |

---

## 11.3 Diferenciālās privātuma aizsardzības mehānismi

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Pārbaudiet, vai privātuma zuduma uzskaites paneļi brīdina, kad kumulatīvais ε pārsniedz politikas sliekšņus.                    |   2   | D/V  |
| 11.3.2 | Pārbaudiet, vai melnās kastes privātuma auditi novērtē ε̂ ar 10% precizitāti no deklarētās vērtības.                            |   2   |  V   |
| 11.3.3 | Pārbaudiet, vai formālie pierādījumi aptver visus pēc apmācības veikto smalko pielāgojumu un iebūvēto reprezentāciju variantus. |   3   |  V   |

---

## 11.4 Mērķa ierobežojums un aizsardzība pret apjoma paplašināšanos

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Pārliecinieties, ka katram datu kopumam un modeļa kontrolpunktam ir mašīnlasāms mērķa tags, kas saskan ar sākotnējo piekrišanu. |   1   |  D   |
| 11.4.2 | Pārbaudiet, vai izpildes uzraugi atklāj vaicājumus, kas nav saskaņā ar deklarēto mērķi, un aktivizē maigās atteikšanās režīmu.  |   1   | D/V  |
| 11.4.3 | Pārbaudiet, vai politika-kods vārti bloķē modeļu atkārtotu izvietošanu jaunās jomās bez DPIA pārskatīšanas.                     |   3   |  D   |
| 11.4.4 | Pārbaudiet, vai formāli izsekojamības pierādījumi rāda, ka katrs personas datu dzīvotspējas cikls paliek piekritušajā apjomā.   |   3   |  V   |

---

## 11.5 Piekrīšanu pārvaldība un likumīga pamata izsekošana

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Pārliecinieties, ka piekrišanas pārvaldības platforma (CMP) reģistrē piekrišanas statusu, mērķi un saglabāšanas periodu katram datu subjektam. |   1   | D/V  |
| 11.5.2 | Pārbaudiet, vai API izpauž piekrišanas tokenus; modeļiem jāverificē tokena darbības joma pirms inferencēšanas.                                 |   2   |  D   |
| 11.5.3 | Pārbaudiet, vai noraidīta vai atsaukta piekrišana pārtrauc apstrādes procesus 24 stundu laikā.                                                 |   2   | D/V  |

---

## 11.6 Federētā mācīšanās ar privātuma kontroli

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Pārbaudiet, vai klienta atjauninājumos tiek izmantota lokālā diferenciālās privātuma trokšņu pievienošana pirms apkopojuma. |   1   |  D   |
| 11.6.2 | Pārbaudiet, vai treniņa metrikas ir diferenciāli privātas un nekad neatklāj viena klienta zaudējumus.                       |   2   | D/V  |
| 11.6.3 | Pārliecinieties, ka ir iespējota pretindēšanas izturīga agregācija (piemēram, Krum/Trimmed-Mean).                           |   2   |  V   |
| 11.6.4 | Pārbaudiet, vai formālie pierādījumi demonstrē kopējo ε budžetu ar mazāk nekā 5 lietderības zudumu.                         |   3   |  V   |

---

### Atsauces

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

