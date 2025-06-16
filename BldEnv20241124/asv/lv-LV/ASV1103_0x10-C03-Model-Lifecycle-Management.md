# C3 modeļa dzīvotspējas cikla pārvaldība un izmaiņu kontrole

## Kontroles mērķis

Mākslīgā intelekta sistēmām jāievieš izmaiņu kontroles procesi, kas neļauj neatļautām vai nedrošām modeļa izmaiņām nonākt ražošanā. Šī kontrole nodrošina modeļa integritāti visā tā dzīves ciklā — no izstrādes līdz izvietošanai un norakstīšanai — kas ļauj ātri reaģēt uz incidentiem un uzturēt atbildību par visām izmaiņām.

Pamērķa drošības mērķis: tikai autorizēti, validēti modeļi nonāk ražošanā, izmantojot kontrolētus procesus, kas nodrošina integritāti, izsekojamību un atjaunojamību.

---

## C3.1 Modeļa autorizācija un integritāte

Tikai autorizēti modeļi ar pārbaudītu integritāti tiek palaisti ražošanas vidē.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Pārbaudiet, vai visi modeļa artefakti (svari, konfigurācijas, tokenizētāji) ir kriptogrāfiski parakstīti ar pilnvarotām vienībām pirms izvietošanas.                                                              |   1   | D/V  |
| 3.1.2 | Pārbaudiet, vai modeļa integritāte tiek validēta izvietošanas laikā un vai paraksta verifikācijas kļūmes neļauj ielādēt modeli.                                                                                   |   1   | D/V  |
| 3.1.3 | Pārbaudiet, vai modeļa izcelsmes ierakstos ir iekļauts autorizējošas personas identitāte, apmācību datu kontrolsummas, validācijas testu rezultāti ar izturēšanas/neizturēšanas statusu un izveides laika zīmogs. |   2   | D/V  |
| 3.1.4 | Pārbaudiet, vai visi modeļa artefakti izmanto semantisko versiju numurēšanu (Lielā.MINOR.PATCH) ar dokumentētiem kritērijiem, kas nosaka, kad jāpalielina katra versijas komponenta numurs.                       |   2   | D/V  |
| 3.1.5 | Pārliecinieties, ka atkarību izsekošana uztur reāllaika krājumu, kas ļauj ātri identificēt visus patērējošos sistēmas.                                                                                            |   2   |  V   |

---

## C3.2 Modeļa validācija un testēšana

Modeļiem pirms ieviešanas jāiztur definētās drošības un aizsardzības pārbaudes.

|   #   | Description                                                                                                                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Pārliecinieties, ka modeļi tiek pakļauti automatizētai drošības pārbaudei, kas ietver ievades validāciju, izvades sanitizāciju un drošības novērtējumus ar iepriekš saskaņotām organizatoriskām izturēšanas/neizturēšanas sliekšņu robežām pirms izvietošanas. |   1   | D/V  |
| 3.2.2 | Pārbaudiet, vai validācijas kļūmes automātiski bloķē modeļa izvietošanu pēc skaidras pārrakstīšanas apstiprinājuma no iepriekš norādītām pilnvarotām personām ar dokumentētiem biznesa pamatojumiem.                                                           |   1   | D/V  |
| 3.2.3 | Pārbaudiet, vai testa rezultāti ir kriptogrāfiski parakstīti un nemainīgi saistīti ar konkrētā modeļa versijas hašu, kas tiek validēts.                                                                                                                        |   2   |  V   |
| 3.2.4 | Pārbaudiet, vai ārkārtas izvietošanai ir nepieciešama dokumentēta drošības riska novērtēšana un apstiprinājums no iepriekš noteiktas drošības iestādes saskaņotajos termiņos.                                                                                  |   2   | D/V  |

---

## C3.3 Kontrolēta izvietošana un atcelšana

Modeļa izvietojumi ir jāuzrauga, jākontrolē un jābūt iespējai tos atsaukt.

|   #   | Description                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Pārbaudiet, vai ražošanas izvietošanas ievieš pakāpeniskas izvēršanas mehānismus (kanāriju izvietojumus, zili zaļus izvietojumus) ar automatizētiem atcelšanas aktivizētājiem, kas balstīti uz iepriekš saskaņotiem kļūdu rādītājiem, latentuma sliekšņiem vai drošības trauksmes kritērijiem. |   1   |  D   |
| 3.3.2 | Pārbaudiet, vai atcelšanas iespējas atomiski atjauno pilnu modeļa stāvokli (svara koeficientus, konfigurācijas, atkarības) iepriekš definētos organizatoriskos laika logros.                                                                                                                   |   1   | D/V  |
| 3.3.3 | Pārbaudiet, vai izvietošanas procesi pārbauda kriptogrāfiskās parakstu derīgumu un aprēķina integritātes kontrolsummas pirms modeļa aktivizēšanas, izvietošanas process neizdodas, ja ir kāda neatbilstība.                                                                                    |   2   | D/V  |
| 3.3.4 | Pārbaudiet, vai ārkārtas modeļa izslēgšanas iespējas var atspējot modeļa galapunktus iepriekš definētajos reakcijas laikos, izmantojot automatizētus ķēžu pārtraucējus vai manuālus izslēgšanas slēdžus.                                                                                       |   2   | D/V  |
| 3.3.5 | Pārliecinieties, ka atsaukšanas artefakti (iepriekšējās modeļa versijas, konfigurācijas, atkarības) tiek saglabāti saskaņā ar organizācijas politiku, izmantojot nemaināmu glabāšanu incidentu reaģēšanai.                                                                                     |   2   |  V   |

---

## C3.4 Atbildības un audita maiņa

Visām modeļa dzīves cikla izmaiņām jābūt izsekojamām un pārskatāmām.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Pārliecinieties, ka visi modeļa izmaiņu procesi (ieviešana, konfigurācija, izņemšana no lietošanas) ģenerē nemaināmus audita ierakstus, ieskaitot laika zīmogu, autentificētas personas identitāti, izmaiņu veidu un stāvokļus pirms un pēc izmaiņām. |   1   |  V   |
| 3.4.2 | Pārliecinieties, ka piekļuve audita žurnālam prasa atbilstošu atļauju un visas piekļuves mēģinājumi tiek reģistrēti ar lietotāja identitāti un laika zīmogu.                                                                                          |   2   | D/V  |
| 3.4.3 | Pārliecinieties, ka uzvednes veidnes un sistēmas ziņojumi ir pārvaldīti Git repozitorijos ar obligātu koda pārskatīšanu un atļauju no nozīmētajiem pārskatītājiem pirms izvietošanas.                                                                 |   2   | D/V  |
| 3.4.4 | Pārbaudiet, vai audita ieraksti satur pietiekami daudz detaļu (modeļa haši, konfigurācijas momentuzņēmumi, atkarību versijas), lai nodrošinātu pilnīgu modeļa stāvokļa atjaunošanu jebkuram laika momentam saglabāšanas periodā.                      |   2   |  V   |

---

## C3.5 Drošas izstrādes praksēs

Modeļa izstrādes un apmācības procesiem jāievēro drošas prakses, lai novērstu kompromitēšanu.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.5.1 | Pārliecinieties, ka modeļa izstrādes, testēšanas un ražošanas vidi ir fiziski vai loģiski atdalītas. Tām nav kopīgas infrastruktūras, atšķirīgas piekļuves kontroles un izolētas datu krātuves.                          |   1   |  D   |
| 3.5.2 | Pārbaudiet, vai modeļa apmācība un smalkā noregulēšana notiek izolētās vidēs ar kontrolētu tīkla piekļuvi.                                                                                                               |   1   |  D   |
| 3.5.3 | Pārliecinieties, ka apmācību datu avoti ir pārbaudīti ar integritātes pārbaudēm un autentificēti caur uzticamiem avotiem ar dokumentētu aizturas ķēdi pirms to izmantošanas modeļa izstrādē.                             |   1   | D/V  |
| 3.5.4 | Pārbaudiet, vai modeļa izstrādes artefakti (hiperparametri, apmācības skripti, konfigurācijas faili) ir saglabāti versiju kontroles sistēmā un prasa kolēģu pārskatīšanas apstiprinājumu pirms to izmantošanas apmācībā. |   2   |  D   |

---

## C3.6 Modeļa noņemšana no lietošanas un deaktivizācija

Modeļi jānogādā drošā atpūtas stāvoklī, kad tos vairs nav nepieciešams lietot vai kad tiek konstatētas drošības problēmas.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Pārliecinieties, ka modeļa novecošanas procesi automātiski skenē atkarību grafikus, identificē visus lietotājsistēmas un nodrošina iepriekš saskaņotus brīdinājuma periodus pirms atslēgšanas.                                              |   1   |  D   |
| 3.6.2 | Pārbaudiet, vai izņemtie modeļa artefakti ir droši izdzēsti, izmantojot kriptogrāfisko iznīcināšanu vai daudzkārtēju pārrakstīšanu atbilstoši dokumentētām datu saglabāšanas politikām ar pārbaudītām iznīcināšanas apliecībām.             |   1   | D/V  |
| 3.6.3 | Pārbaudiet, vai modeļa izbeigšanas notikumi tiek reģistrēti ar laika zīmogu un aktiera identitāti, un vai modeļa paraksti tiek atsaukti, lai novērstu atkārtotu izmantošanu.                                                                |   2   |  V   |
| 3.6.4 | Pārbaudiet, vai ārkārtas modeļa izņemšana no lietošanas var atslēgt piekļuvi modelim iepriekš noteiktajos ārkārtas reaģēšanas termiņos, izmantojot automatizētas izslēgšanas slēdzenes, ja tiek atklātas kritiskas drošības ievainojamības. |   2   | D/V  |

---

## Atsauces

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

