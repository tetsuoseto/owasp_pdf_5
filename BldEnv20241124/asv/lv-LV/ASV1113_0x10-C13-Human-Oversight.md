# C13 Cilvēka uzraudzība, atbildība un pārvaldība

## Vadības mērķis

Šajā nodaļā ir noteiktas prasības cilvēka uzraudzības uzturēšanai un skaidru atbildības ķēžu nodrošināšanai mākslīgā intelekta sistēmās, garantējot izskaidrojamību, pārredzamību un ētisku pārvaldību visā mākslīgā intelekta dzīvības ciklā.

---

## C13.1 Izslēgšanas slēdža un pārrakstīšanas mehānismi

Nodrošiniet izslēgšanas vai atgriešanas ceļus, ja tiek novērota mākslīgā intelekta sistēmas bīstama uzvedība.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.1.1 | Pārliecinieties, ka pastāv manuāla izslēgšanas slēdzis, lai nekavējoties apturētu AI modeļa secināšanu un izvades. |   1   | D/V  |
| 13.1.2 | Pārliecinieties, ka pārrakstīšanas vadības ir pieejamas tikai pilnvarotam personālam.                              |   1   |  D   |
| 13.1.3 | Pārbaudiet, vai atsaukšanas procedūras var atgriezties pie iepriekšējām modeļa versijām vai drošā režīma darbībām. |   3   | D/V  |
| 13.1.4 | Pārliecinieties, ka pārrakstīšanas mehānismi tiek regulāri testēti.                                                |   3   |  V   |

---

## C13.2 Cilvēks cilpā lēmumu pārbaudes punkti

Prasīt cilvēka apstiprinājumu, kad likmes pārsniedz iepriekš noteiktos riska sliekšņus.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Pārbaudiet, vai augsta riska mākslīgā intelekta lēmumi pirms izpildes prasa skaidru cilvēka apstiprinājumu.                                   |   1   | D/V  |
| 13.2.2 | Pārliecinieties, ka riska sliekšņi ir skaidri definēti un automātiski aktivizē cilvēka pārskatīšanas darbplūsmas.                             |   1   |  D   |
| 13.2.3 | Pārliecinieties, ka laika jutīgām lēmumiem ir rezerves procedūras gadījumos, kad cilvēka apstiprinājumu nevar iegūt noteiktajos termiņos.     |   2   |  D   |
| 13.2.4 | Pārbaudiet, vai eskalācijas procedūras nosaka skaidras pilnvaru līmeņus dažādiem lēmumu veidiem vai riska kategorijām, ja tas ir piemērojams. |   3   | D/V  |

---

## C13.3 Atbildības ķēde un pārskatāmība

Reģistrējiet operatora darbības un modeļa lēmumus.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.3.1 | Pārliecinieties, ka visas AI sistēmas lēmumu un cilvēku iejaukšanās tiek reģistrētas ar laika zīmēm, lietotāju identitātēm un lēmuma pamatojumu. |   1   | D/V  |
| 13.3.2 | Pārliecinieties, ka revīzijas žurnāli nav iespējami maināmi un tajos ir iekļautas integritātes pārbaudes mehānismi.                              |   2   |  D   |

---

## C13.4 Paskaidrojama Mākslīgā Intelekta Tehnikas

Virszemes iezīmju nozīmīgums, pretfaktiskie piemēri un lokālas skaidrošanas metodes.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Pārliecinieties, ka mākslīgā intelekta sistēmas sniedz pamatizskaidrojumus par saviem lēmumiem cilvēkiem saprotamā formātā.                                       |   1   | D/V  |
| 13.4.2 | Pārbaudiet, vai paskaidrojumu kvalitāte ir validēta, izmantojot cilvēku novērtējuma pētījumus un metrikas.                                                        |   2   |  V   |
| 13.4.3 | Pārbaudiet, vai svarīguma vērtējumi vai atribūcijas metodes (SHAP, LIME utt.) ir pieejamas kritisku lēmumu pieņemšanai.                                           |   3   | D/V  |
| 13.4.4 | Pārbaudiet, vai kontrafaktu paskaidrojumi parāda, kā ievades varētu tikt modificētas, lai mainītu iznākumus, ja tas ir piemērojams lietošanas gadījumam un jomai. |   3   |  V   |

---

## C13.5 Modeļa kartes un lietošanas atklājumi

Uzturiet modeļa kartes paredzētajai lietošanai, veiktspējas rādītājiem un ētiskiem apsvērumiem.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Pārliecinieties, ka modeļu kartes dokumentē paredzētos lietošanas gadījumus, ierobežojumus un zināmās kļūmju režīmus.                                                                        |   1   |  D   |
| 13.5.2 | Pārliecinieties, ka veiktspējas rādītāji dažādos piemērojamos lietošanas gadījumos ir atklāti.                                                                                               |   1   | D/V  |
| 13.5.3 | Pārbaudiet, vai ir dokumentēti un regulāri atjaunināti ētikas apsvērumi, aizspriedumu novērtējumi, taisnīguma izvērtējumi, apmācību datu raksturojumi un zināmie apmācību datu ierobežojumi. |   2   |  D   |
| 13.5.4 | Pārliecinieties, ka modeļu kartes tiek versiju kontrolētas un uzturētas visā modeļa dzīvotspējas ciklā ar izmaiņu izsekošanu.                                                                |   2   | D/V  |

---

## C13.6 Nenoteiktības kvantificēšana

Izplatīt pārliecības rādītājus vai entropijas mērus atbildēs.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Pārliecinieties, ka mākslīgā intelekta sistēmas savos rezultātos sniedz pārliecības rādītājus vai nenoteiktības mērus.    |   1   |  D   |
| 13.6.2 | Pārbaudiet, vai nenoteiktības sliekšņi aktivizē papildu cilvēka pārskatu vai alternatīvas lēmumu pieņemšanas ceļus.       |   2   | D/V  |
| 13.6.3 | Pārliecinieties, ka nenoteiktības kvantifikācijas metodes ir kalibrētas un pārbaudītas, salīdzinot ar patiesajiem datiem. |   2   |  V   |
| 13.6.4 | Pārbaudiet, vai nenoteiktības izplatīšana tiek saglabāta vairāku soļu mākslīgā intelekta darba procesos.                  |   3   | D/V  |

---

## C13.7 Lietotājam redzamie pārredzamības ziņojumi

Nodrošināt regulārus atskatus par incidentiem, novirzēm un datu izmantošanu.

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Pārbaudiet, vai datu lietošanas politikas un lietotāju piekrišanas pārvaldības prakses ir skaidri komunikētas ar ieinteresētajām pusēm. |   1   | D/V  |
| 13.7.2 | Pārliecinieties, ka tiek veikta mākslīgā intelekta ietekmes izvērtēšana un rezultāti tiek iekļauti atskaitēs.                           |   2   | D/V  |
| 13.7.3 | Pārbaudiet, vai regulāri publicētie caurspīdīguma ziņojumi atklāj AI incidentus un darbības metriku saprātīgā detalizācijā.             |   2   | D/V  |

### Atsauces

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

