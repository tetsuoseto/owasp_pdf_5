# C12 Uzraudzība, Žurnālu veidošana un Anomāliju noteikšana

## Kontroles mērķis

Šī sadaļa sniedz prasības reāllaika un forensiskai pārredzamībai par to, ko modelis un citas mākslīgā intelekta sastāvdaļas redz, dara un atgriež, lai draudi varētu tikt atklāti, klasificēti un analizēti mācībām.

## C12.1 Pieprasījumu un atbilžu žurnālu veidošana

|   #    | Description                                                                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.1.1 | Pārliecinieties, ka visi lietotāju pieprasījumi un modeļa atbildes tiek reģistrēti ar atbilstošu metadatu kopu (piemēram, laika zīmi, lietotāja ID, sesijas ID, modeļa versiju).                                                                                         |   1   | D/V  |
| 12.1.2 | Pārliecinieties, ka žurnāli tiek glabāti drošās, piekļuvei kontrolētās krātuvēs ar piemērotām saglabāšanas politikām un dublēšanas procedūrām.                                                                                                                           |   1   | D/V  |
| 12.1.3 | Pārbaudiet, vai žurnālu glabāšanas sistēmas ievieš šifrēšanu atpūtā un pārsūtīšanas laikā, lai aizsargātu žurnālos iekļauto sensitīvo informāciju.                                                                                                                       |   1   | D/V  |
| 12.1.4 | Pārliecinieties, ka sensitīvi dati promptos un izvadēs tiek automātiski anonimizēti vai maskēti pirms žurnālu veidošanas, ar konfigurējamām anonimizēšanas noteikumiem personīgi identificējamai informācijai (PII), akreditācijas datiem un īpašumtiesību informācijai. |   1   | D/V  |
| 12.1.5 | Pārbaudiet, vai politikas lēmumi un drošības filtrēšanas darbības tiek reģistrētas ar pietiekamu detalizētību, lai nodrošinātu satura moderēšanas sistēmu auditu un problēmu novēršanu.                                                                                  |   2   | D/V  |
| 12.1.6 | Pārliecinieties, ka žurnāla integritāte ir aizsargāta, piemēram, ar kriptogrāfiskām parakstiem vai rakstīšanai tikai paredzētu glabātuvi.                                                                                                                                |   2   | D/V  |

---

## C12.2 ļaunprātīgas izmantošanas atklāšana un brīdināšana

|   #    | Description                                                                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Pārbaudiet, vai sistēma atpazīst un signalizē par zināmiem jailbreak raksturlielumiem, uzaicinājumu injekcijas mēģinājumiem un pretinieciskiem ievadiem, izmantojot parakstu bāzes noteikšanu.                            |   1   | D/V  |
| 12.2.2 | Pārliecinieties, ka sistēma integrējas ar esošajām Drošības informācijas un notikumu pārvaldības (SIEM) platformām, izmantojot standarta žurnālu formātus un protokolus.                                                  |   1   | D/V  |
| 12.2.3 | Pārliecinieties, ka bagātinātie drošības notikumi ietver ar mākslīgo intelektu saistītu kontekstu, piemēram, modeļu identifikatorus, pārliecības rādītājus un drošības filtru lēmumus.                                    |   2   | D/V  |
| 12.2.4 | Pārbaudiet, vai uzvedības anomāliju detektēšana atklāj neparastus sarunas modeļus, pārmērīgas pārmēģinājuma mēģinājumus vai sistemātiskas izpētes uzvedības.                                                              |   2   | D/V  |
| 12.2.5 | Pārbaudiet, vai reāllaika brīdināšanas mehānismi informē drošības komandas, kad tiek konstatēti iespējamie politikas pārkāpumi vai uzbrukuma mēģinājumi.                                                                  |   2   | D/V  |
| 12.2.6 | Pārliecinieties, ka pielāgotie noteikumi iekļauti, lai atklātu mākslīgā intelekta specifiskos draudu modeļus, tostarp koordinētas aplaušanas mēģinājumus, uzvedņu injekcijas kampaņas un modeļu ekstrahēšanas uzbrukumus. |   2   | D/V  |
| 12.2.7 | Pārbaudiet, vai automatizētie incidentu reaģēšanas darbplūsmas spēj izolēt kompromitētus modeļus, bloķēt ļaunprātīgus lietotājus un eskalēt kritiskus drošības notikumus.                                                 |   3   | D/V  |

---

## C12.3 Modeļa novirzes noteikšana

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Pārbaudiet, vai sistēma uzrauga pamata veiktspējas rādītājus, piemēram, precizitāti, pārliecības līmeņus, latentumu un kļūdu rādītājus dažādu modeļu versijās un laika periodos. |   1   | D/V  |
| 12.3.2 | Pārbaudiet, vai automātiskā trauksmes sistēma aktivizējas, kad veiktspējas rādītāji pārsniedz iepriekš noteiktos degradācijas sliekšņus vai būtiski novirzās no bāzes līmeņiem.  |   2   | D/V  |
| 12.3.3 | Pārbaudiet, vai halucināciju noteikšanas monitori identificē un atzīmē gadījumus, kad modeļa izvades satur faktiski nepareizu, nesakritīgu vai izdomātu informāciju.             |   2   | D/V  |

---

## C12.4 Veiktspējas un uzvedības telemetrija

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Pārliecinieties, ka operacionālie rādītāji, tostarp pieprasījumu latentums, tokenu patēriņš, atmiņas izmantošana un caurlaide, tiek nepārtraukti ievākti un uzraudzīti. |   1   | D/V  |
| 12.4.2 | Pārliecinieties, ka veiksmju un neveiksmju rādītāji tiek izsekoti, kategorizējot kļūdu tipus un to pamatcēloņus.                                                        |   1   | D/V  |
| 12.4.3 | Pārliecinieties, ka resursu izmantošanas uzraudzība ietver GPU/CPU lietojumu, atmiņas patēriņu un krātuves prasības ar brīdinājumiem, pārsniedzot noteiktos sliekšņus.  |   2   | D/V  |

---

## C12.5 Mākslīgā intelekta incidentu reaģēšanas plānošana un izpilde

|   #    | Description                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Pārliecinieties, ka incidentu reaģēšanas plāni īpaši risina ar mākslīgā intelekta drošības notikumiem saistītas situācijas, tostarp modeļa kompromitāciju, datu piesārņošanu un pretinieku uzbrukumus. |   1   | D/V  |
| 12.5.2 | Pārbaudiet, vai incidentu reaģēšanas komandas ir aprīkotas ar mākslīgā intelekta specifiskiem forensikas rīkiem un ekspertīzi modeļu uzvedības un uzbrukuma vektoru izmeklēšanai.                      |   2   | D/V  |
| 12.5.3 | Pārliecinieties, ka pēc incidenta analīze iekļauj modeļa pārtrenēšanas apsvērumus, drošības filtru atjauninājumus un mācībstundu integrāciju drošības kontrolēs.                                       |   3   | D/V  |

---

## C12.5 Mākslīgā intelekta veiktspējas samazināšanās noteikšana

Uzraudzīt un noteikt AI modeļa veiktspējas un kvalitātes pasliktināšanos laika gaitā.

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Pārliecinieties, ka modeļa precizitāte, precizitāte, atgūšana un F1 rādītāji tiek nepārtraukti uzraudzīti un salīdzināti ar bāzes līmeņa sliekšņiem. |   1   | D/V  |
| 12.5.2 | Pārbaudiet, vai datu novirzes noteikšana uzrauga ieejas sadalījuma izmaiņas, kas var ietekmēt modeļa veiktspēju.                                     |   1   | D/V  |
| 12.5.3 | Pārbaudiet, vai koncepcijas novirzes noteikšana atpazīst izmaiņas sakarā starp ievadiem un gaidītajiem izvadiem.                                     |   2   | D/V  |
| 12.5.4 | Pārbaudiet, vai veiktspējas pasliktināšanās izsauc automātiskus brīdinājumus un sāk modeļa pārmācīšanas vai nomaiņas darbplūsmas.                    |   2   | D/V  |
| 12.5.5 | Pārbaudiet, vai degradācijas saknes cēloņu analīze korelē veiktspējas kritumus ar datu izmaiņām, infrastruktūras problēmām vai ārējiem faktoriem.    |   3   |  V   |

---

## C12.6 DAG vizualizācija un darba plūsmas drošība

Aizsargājiet darbplūsmas vizualizācijas sistēmas no informācijas noplūdes un manipulācijas uzbrukumiem.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Pārliecinieties, ka DAG vizualizācijas dati tiek attīrīti no sensitīvas informācijas pirms glabāšanas vai pārsūtīšanas.                                                     |   1   | D/V  |
| 12.6.2 | Pārbaudiet, vai darba plūsmas vizualizācijas piekļuves kontroles nodrošina, ka tikai autorizēti lietotāji var skatīt aģenta lēmumu ceļus un pamatojuma pēdas.               |   1   | D/V  |
| 12.6.3 | Pārbaudiet, ka DAG datu integritāte ir aizsargāta ar kriptogrāfiskām parakstiem un viltojumu atklājošiem uzglabāšanas mehānismiem.                                          |   2   | D/V  |
| 12.6.4 | Pārbaudiet, vai darbplūsmas vizualizācijas sistēmas īsteno ievades validāciju, lai novērstu injekcijas uzbrukumus, izmantojot īpaši izstrādātus mezglu vai malu datus.      |   2   | D/V  |
| 12.6.5 | Pārliecinieties, ka reāllaika DAG atjauninājumi ir ātruma ierobežoti un validēti, lai novērstu pakalpojuma atteices (denial-of-service) uzbrukumus vizualizācijas sistēmām. |   3   | D/V  |

---

## C12.7 Proaktīvā drošības uzvedības uzraudzība

Drošības draudu atklāšana un novēršana, izmantojot proaktīvu aģentu uzvedības analīzi.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Pārbaudiet, vai proaktīvas aģenta uzvedības ir drošības pārbaudītas pirms izpildes, integrējot riska novērtējumu.               |   1   | D/V  |
| 12.7.2 | Pārbaudiet, vai autonomās iniciatīvas izraisītāji ietver drošības konteksta novērtējumu un draudu ainavas analīzi.              |   2   | D/V  |
| 12.7.3 | Pārbaudiet, vai proaktīvās uzvedības modeļi tiek analizēti, ņemot vērā potenciālās drošības sekas un nevēlamās blakusparādības. |   2   | D/V  |
| 12.7.4 | Pārliecinieties, ka drošības kritiski proaktīvi pasākumi prasa skaidras apstiprināšanas ķēdes ar audita ierakstiem.             |   3   | D/V  |
| 12.7.5 | Pārbaudiet, vai uzvedības anomāliju noteikšana identificē novirzes proaktīvo aģentu modeļos, kas var liecināt par pārkāpumu.    |   3   | D/V  |

---

## Atsauces

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

