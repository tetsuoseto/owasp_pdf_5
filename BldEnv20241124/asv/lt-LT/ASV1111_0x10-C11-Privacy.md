# 11 Privatumo apsauga ir asmens duomenų valdymas

## Kontrolės tikslas

Užtikrinkite griežtą privatumo apsaugą per visą DI gyvavimo ciklą – duomenų rinkimą, mokymą, numatymą ir įvykių valdymą – kad asmens duomenys būtų tvarkomi tik aiškiai sutikus, laikantis minimalaus būtinumo principo, su įrodymais apie ištrynimą ir formaliais privatumo garantavimais.

---

## 11.1 Anonimizavimas ir duomenų minimalizavimas

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Patikrinkite, ar tiesioginiai ir kvazi-identifikatoriai yra pašalinti arba apdoroti maišos funkcija.                                                     |   1   | D/V  |
| 11.1.2 | Patikrinkite, ar automatiniai auditai matuoja k-anonimiškumą/l-įvairovę ir įspėja, kai nustatyti ribiniai dydžiai nukrinta žemiau politikos reikalavimų. |   2   | D/V  |
| 11.1.3 | Patikrinkite, ar modelio reikšmingumo ataskaitos įrodo, kad nėra identifikatorių nutekėjimo, viršijančio ε = 0,01 bendrąją informaciją.                  |   2   |  V   |
| 11.1.4 | Patikrinkite, ar formalūs įrodymai arba sintetinės duomenų sertifikavimas rodo, kad identifikavimo rizika yra ≤ 0,05 net ir atliekant susiejimo atakas.  |   3   |  V   |

---

## 11.2 Teisė būti pamirštam ir ištrynimo vykdymas

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Patikrinkite, ar duomenų subjecto ištrinimo užklausos pasiekia neapdorotus duomenų rinkinius, kontrolinius punktus, įterpimus, žurnalus ir atsargines kopijas per paslaugos lygio sutartį, trunkančią mažiau nei 30 dienų. |   1   | D/V  |
| 11.2.2 | Patikrinkite, ar „mašininio nepamokimo“ procedūros fiziškai išmoko iš naujo arba įvertina pašalinimą naudojant sertifikuotus nepamokymo algoritmus.                                                                        |   2   |  D   |
| 11.2.3 | Patikrinkite, ar šešėlio modelio vertinimas įrodo, kad pamiršti įrašai po atsiminimo daro įtaką mažiau nei 1 % išvesties rezultatų.                                                                                        |   2   |  V   |
| 11.2.4 | Patikrinkite, ar ištrynimo įvykiai yra nekeičiami užfiksuoti ir audituojami reguliuotojams.                                                                                                                                |   3   |  V   |

---

## 11.3 Diferencinės privatumo apsaugos priemonės

|   #    | Description                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.3.1 | Patikrinkite, ar privatumo nuostolių stebėjimo skydai įspėja, kai susumuotas ε viršija politikos ribas.                  |   2   | D/V  |
| 11.3.2 | Patikrinkite, ar juodosios dėžės privatumo auditai įvertina ε̂ su ne didesniu nei 10 % paklaidos nuo deklaruotos vertės. |   2   |  V   |
| 11.3.3 | Patikrinkite, ar formalių įrodymų aprėptis apima visus posttreniruotinius tikslinius patobulinimus ir įterpimus.         |   3   |  V   |

---

## 11.4 Tikslų apribojimas ir apsauga nuo apimties augimo

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Patikrinkite, ar kiekvienas duomenų rinkinys ir modelio kontrolinis taškas turi mašininiu būdu skaitomą paskirties žymę, atitinkančią pradinį sutikimą. |   1   |  D   |
| 11.4.2 | Patikrinkite, ar vykdymo laikotarpio stebėtojai aptinka užklausas, kurios prieštarauja paskelbtam tikslui, ir sukelia švelnų atsisakymą.                |   1   | D/V  |
| 11.4.3 | Patikrinkite, ar politika kaip kodas (policy-as-code) užkardos neleidžia modelių perkūrimo naujoms sritims be DPIA peržiūros.                           |   3   |  D   |
| 11.4.4 | Patikrinkite, ar formalūs susiejamumo įrodymai parodo, kad kiekvienas asmens duomenų gyvenimo ciklas lieka sutarto sutikimo ribose.                     |   3   |  V   |

---

## 11.5 Sutikimų valdymas ir teisėto pagrindo stebėjimas

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Patikrinkite, ar sutikimų valdymo platforma (CMP) įrašo duomenų subjekto sutikimo būseną, tikslą ir saugojimo laikotarpį. |   1   | D/V  |
| 11.5.2 | Patikrinkite, ar API suteikia sutikimo žetonus; modeliai turi patikrinti žetono aprėptį prieš atliekant spėjimą.          |   2   |  D   |
| 11.5.3 | Patikrinkite, ar atsisakius arba atšaukus sutikimą, duomenų apdorojimo procesai sustabdomi per 24 valandas.               |   2   | D/V  |

---

## 11.6 Federuotas mokymasis su privatumo valdikliais

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Patikrinkite, ar klientų atnaujinimai naudoja vietinį diferencialinį privatumo triukšmo pridėjimą prieš agregavimą. |   1   |  D   |
| 11.6.2 | Patikrinkite, ar mokymo metrikos yra diferencialiai privatūs ir niekada neatskleidžia vieno kliento nuostolių.      |   2   | D/V  |
| 11.6.3 | Patikrinkite, ar įjungta apsauga nuo užnuodijimo jautri agregacija (pvz., Krum/Trimmed-Mean).                       |   2   |  V   |
| 11.6.4 | Patikrinkite, ar formalūs įrodymai parodo bendrą ε biudžetą su mažesniu nei 5 naudos praradimu.                     |   3   |  V   |

---

### Nuorodos

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

