# 10 Pretestības pret pretinieciskiem uzbrukumiem un privātuma aizsardzība

## Vadības mērķis

Nodrošiniet, ka mākslīgā intelekta modeļi paliek uzticami, privātumu aizsargājoši un izturīgi pret ļaunprātīgu izmantošanu, saskaroties ar izvairīšanās, secināšanas, izguves vai indēšanas uzbrukumiem.

---

## 10.1 Modeļa saskaņošana un drošība

Aizsargājieties pret kaitīgiem vai politikas pārkāpjošiem rezultātiem.

|   #    | Description                                                                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Pārbaudiet, vai izlīdzināšanas testu komplekts (red-team uzvednes, jailbreaker pārbaudes, aizliegtas satura pārbaudes) tiek versiju kontrolēts un veikts katrā modeļa laidienā. |   1   | D/V  |
| 10.1.2 | Pārliecinieties, ka tiek ievēroti atteikuma un drošas pabeigšanas aizsargjoslas.                                                                                                |   1   |  D   |
| 10.1.3 | Pārliecinieties, ka automatizēts novērtētājs nosaka kaitīgā satura līmeni un iezīmē regresijas, kas pārsniedz noteikto slieksni.                                                |   2   | D/V  |
| 10.1.4 | Pārbaudiet, vai pretpretošanās treniņš ir dokumentēts un reproducējams.                                                                                                         |   2   |  D   |
| 10.1.5 | Pārbaudiet, vai formālas politikas atbilstības pierādījumi vai sertificēta uzraudzība aptver kritiskās jomas.                                                                   |   3   |  V   |

---

## 10.2 Pretestēšana pret pretinieciskiem piemēriem

Palieliniet izturību pret manipulētiem ievades datiem. Robustā pretinieku apmācība un salīdzināšanas rādītāju vērtēšana pašlaik ir labākā prakse.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Pārliecinieties, ka projekta krātuves satur pretinieku apmācības konfigurācijas ar reproducējamām sēklām.                   |   1   |  D   |
| 10.2.2 | Pārbaudiet, vai pretinieku piemēru atklāšana ražošanas plūsmās izsauc bloķējošus brīdinājumus.                              |   2   | D/V  |
| 10.2.4 | Pārbaudiet, vai sertificētās drošības pierādījumi vai intervāla robežu sertifikāti aptver vismaz galvenās kritiskās klases. |   3   |  V   |
| 10.2.5 | Pārbaudiet, vai regresijas testi izmanto adaptīvās uzbrukumus, lai apstiprinātu, ka nav mērāmas noturības samazinājuma.     |   3   |  V   |

---

## 10.3 Dalības informācijas noplūdes risku mazināšana

 ierobežot iespēju noteikt, vai ieraksts bija mācību datos. Diferenciālā privātuma un pārliecības vērtējuma maskēšanas metodes joprojām ir visefektīvākās zināmās aizsardzības.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Pārbaudiet, vai katra vaicājuma entropijas regulēšana vai temperatūras skalēšana samazina pārlieku pārliecinātas prognozes. |   1   |  D   |
| 10.3.2 | Pārbaudiet, vai apmācībā tiek izmantota ε-ierobežota diferenciāli privāta optimizācija sensitīviem datu kopām.              |   2   |  D   |
| 10.3.3 | Pārbaudiet, vai uzbrukuma simulācijas (ēnu modelis vai melnās kastes) uzrāda uzbrukuma AUC ≤ 0.60 uz turētajiem datiem.     |   2   |  V   |

---

## 10.4 Modeļa apgriešanas noturība

Novērst privāto atribūtu rekonstrukciju. Pēdējie pētījumi uzsver izvades saīsināšanu un diferencētas privātuma (DP) garantijas kā praktiskas aizsardzības metodes.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Pārbaudiet, vai sensitīvas atribūti nekad netiek tieši izvadīti; ja nepieciešams, izmantojiet kategorijas vai vienvirziena pārveidojumus. |   1   |  D   |
| 10.4.2 | Pārbaudiet, vai pieprasījumu ātruma ierobežojumi ierobežo atkārtotus adaptīvus pieprasījumus no viena un tā paša lietotāja.               |   1   | D/V  |
| 10.4.3 | Pārbaudiet, vai modelis ir apmācīts ar privātumu saglabājošu trokšņa pievienošanu.                                                        |   2   |  D   |

---

## 10.5 Modeļa izguves aizsardzība

Atklājiet un novēršiet neatļautu klonēšanu. Ieteicama ūdenszīmes pievienošana un vaicājumu paraugu analīze.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Pārbaudiet, vai inferenču vārtejas ievēro globālos un atsevišķu API atslēgu ātruma ierobežojumus, kas pielāgoti modeļa atmiņas slieksnim. |   1   |  D   |
| 10.5.2 | Pārliecinieties, ka vaicājuma entropijas un ievades daudzveidības statistika tiek izmantota automatizētas ekstrakcijas detektora darbībā. |   2   | D/V  |
| 10.5.3 | Pārbaudiet, vai trauslus vai varbūtības ūdenszīmes var pierādīt ar p < 0,01 ne vairāk kā 1 000 vaicājumos pret aizdomīgu klonu.           |   2   |  V   |
| 10.5.4 | Pārbaudiet, vai watermark atslēgas un aktivizēšanas kopas tiek glabātas aparatūras drošības modulī un tiek rotētas reizi gadā.            |   3   |  D   |
| 10.5.5 | Pārbaudiet, vai izguves brīdinājuma notikumi ietver pārkāpjošos vaicājumus un ir integrēti ar incidentu reaģēšanas darbplāniem.           |   3   |  V   |

---

## 10.6 Secinājumu laika inficēto datu noteikšana

Identificēt un neutralizēt aizmugurējās durvis vai saindētās ieejas.

|   #    | Description                                                                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Pārliecinieties, ka ieejas dati tiek pārbaudīti caur anomāliju detektoru (piemēram, STRIP, konsekvences vērtēšanu) pirms modeļa inferencēšanas.             |   1   |  D   |
| 10.6.2 | Pārliecinieties, ka detektora sliekšņi ir noregulēti uz tīriem/indētiem validācijas datu kopumiem, lai panāktu mazāk nekā 5% kļūdaini pozitīvus rezultātus. |   1   |  V   |
| 10.6.3 | Pārbaudiet, vai ievades dati, kas atzīmēti kā piesārņoti, izraisām mīksto bloķēšanu un cilvēka pārskatīšanas darbplūsmas.                                   |   2   |  D   |
| 10.6.4 | Pārliecinieties, ka detektori tiek pārbaukti stresa apstākļos ar adaptīvām, bezizraižu slēptām uzbrukuma metodēm.                                           |   2   |  V   |
| 10.6.5 | Pārliecinieties, ka ir reģistrēti noteikšanas efektivitātes metri un tos periodiski pārskata, izmantojot svaigu draudu izlūkošanu.                          |   3   |  D   |

---

## 10.7 Dinamiskā drošības politikas pielāgošana

Drošības politikas atjauninājumi reāllaikā, pamatojoties uz draudu informāciju un uzvedības analīzi.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Pārbaudiet, vai drošības politikas var tikt atjauninātas dinamiskā režīmā bez aģenta restartēšanas, saglabājot politikas versijas integritāti.                   |   1   | D/V  |
| 10.7.2 | Pārbaudiet, vai politikas atjauninājumi ir kriptogrāfiski parakstīti no pilnvarotajiem drošības personāla un pārbaudīti pirms to piemērošanas.                   |   2   | D/V  |
| 10.7.3 | Pārliecinieties, ka dinamiskās politikas izmaiņas tiek reģistrētas ar pilnīgu audita pēdu, iekļaujot pamatojumu, apstiprināšanas ķēdes un atcelšanas procedūras. |   2   | D/V  |
| 10.7.4 | Pārliecinieties, ka adaptīvās drošības mehānismi pielāgo draudu noteikšanas jutīgumu, pamatojoties uz riska kontekstu un uzvedības modeļiem.                     |   3   | D/V  |
| 10.7.5 | Pārbaudiet, vai politikas pielāgošanas lēmumi ir izskaidrojami un ietver pierādījumu ceļus drošības komandas pārskatīšanai.                                      |   3   | D/V  |

---

## 10.8 Atspoguļojuma balstīta drošības analīze

Drošības validācija caur aģenta pašrefleksiju un meta-kognitīvo analīzi.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Pārbaudiet, vai aģenta refleksijas mehānismi ietver drošībai vērstu pašnovērtējumu par lēmumiem un darbībām.                                    |   1   | D/V  |
| 10.8.2 | Pārliecinieties, ka atspulgu izvades tiek pārbaudītas, lai novērstu paša novērtēšanas mehānismu manipulēšanu ar pretinieciskiem ievadiem.       |   2   | D/V  |
| 10.8.3 | Pārliecinieties, ka meta-kognitīvā drošības analīze identificē potenciālu aizspriedumu, manipulāciju vai kompromisu aģenta spriešanas procesos. |   2   | D/V  |
| 10.8.4 | Pārbaudiet, vai uz atspulga balstītie drošības brīdinājumi aktivizē uzlabotu uzraudzību un potenciālas cilvēka iejaukšanās darba plūsmas.       |   3   | D/V  |
| 10.8.5 | Pārbaudiet, vai nepārtraukta mācīšanās no drošības pārdomām uzlabo draudu noteikšanu, nesamazinot likumīgas funkcionalitātes kvalitāti.         |   3   | D/V  |

---

## 10.9 Evolūcija un pašuzlabošanās drošība

Drošības kontroles aģentu sistēmām, kas spēj pašmodificēties un attīstīties.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Pārbaudiet, vai pašmodifikācijas iespējas ir ierobežotas tikai noteiktās drošajās zonās ar formālu verificēšanas robežām.                          |   1   | D/V  |
| 10.9.2 | Pārliecinieties, ka evolūcijas priekšlikumi tiek pakļauti drošības ietekmes novērtējumam pirms ieviešanas.                                         |   2   | D/V  |
| 10.9.3 | Pārbaudiet, vai pašuzlabošanās mehānismi ietver atteices iespējas ar integritātes pārbaudi.                                                        |   2   | D/V  |
| 10.9.4 | Pārbaudiet, vai meta-mācīšanās drošība novērš uzlabošanas algoritmu nelabvēlīgu manipulāciju.                                                      |   3   | D/V  |
| 10.9.5 | Pārbaudiet, vai rekurzīvā pašuzlabošanās ir ierobežota ar formāliem drošības ierobežojumiem, izmantojot matemātiskus pierādījumus par konverģenci. |   3   | D/V  |

---

### Atsauces

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

