# C1 Apmācību datu pārvaldība un noviržu vadība

## Kontroles mērķis

Apmācību dati ir jāiegūst, jāapstrādā un jāuztur tādā veidā, kas saglabā izcelsmi, drošību, kvalitāti un godīgumu. Šādi rīkojoties, tiek izpildītas juridiskās saistības un samazināti aizspriedumu, inficēšanas vai privātuma pārkāpumu riski visā AI dzīves ciklā.

---

## C1.1 Apmācību datu izcelsme

Uzturiet pārbaudāmu visu datu kopu inventāru, pieņemiet tikai uzticamus avotus un reģistrējiet katru izmaiņu auditējamībai.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Pārliecinieties, ka tiek uzturēts aktuāls katra apmācību datu avota inventārs (avots, atbildīgais/īpašnieks, licence, vākšanas metode, paredzētās izmantošanas ierobežojumi un apstrādes vēsture).                                                 |   1   | D/V  |
| 1.1.2 | Pārliecinieties, ka tiek atļauti tikai tādi datu kopumi, kas pārbaudīti kvalitātes, reprezentativitātes, ētiskas izcelsmes un licences atbilstības ziņā, samazinot saindēšanas, iebūvētas aizspriedumu un intelektuālā īpašuma pārkāpumu riskus.   |   1   | D/V  |
| 1.1.3 | Pārliecinieties, ka tiek īstenota datu minimizācija, lai nevajadzīgas vai sensitīvas atribūtas tiktu izslēgtas.                                                                                                                                    |   1   | D/V  |
| 1.1.4 | Pārliecinieties, ka visas datu kopas izmaiņas tiek apstiprinātas un reģistrētas caur apstiprināšanas darbplūsmu.                                                                                                                                   |   2   | D/V  |
| 1.1.5 | Pārliecinieties, ka marķēšanas/annotācijas kvalitāte ir nodrošināta, veicot pārskatītāja savstarpēju pārbaudi vai sasniedzot vienprātību.                                                                                                          |   2   | D/V  |
| 1.1.6 | Pārliecinieties, ka tiek uzturētas "datu kartes" vai "datu kopu datu lapas" nozīmīgām apmācību datu kopām, kurās ir detalizēti aprakstītas to īpašības, motivācijas, sastāvs, vākšanas procesi, priekšapstrāde un ieteicamā/neieteicamā lietošana. |   2   | D/V  |

---

## C1.2 Apmācības datu drošība un integritāte

Ierobežojiet piekļuvi, šifrējiet datus atpūtā un pārsūtīšanas laikā, un pārbaudiet integritāti, lai novērstu manipulācijas vai zādzību.

|   #   | Description                                                                                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Pārliecinieties, ka piekļuves kontroles aizsargā datu glabāšanu un datu apstrādes plūsmas.                                                                                                                                                                                                                                                                |   1   | D/V  |
| 1.2.2 | Pārbaudiet, vai datu kopas tiek šifrētas pārvades laikā un, attiecībā uz visu sensitīvo vai personiski identificējamo informāciju (PII), arī glabāšanas laikā, izmantojot nozares standarta kriptogrāfiskās algoritmus un atslēgu pārvaldības prakses.                                                                                                    |   2   | D/V  |
| 1.2.3 | Pārliecinieties, ka kriptogrāfiskās hašvērtības vai digitālās parakstīšanas tiek izmantotas, lai nodrošinātu datu integritāti glabāšanas un pārsūtīšanas laikā, un ka tiek pielietotas automātiskās anomāliju noteikšanas tehnoloģijas, lai aizsargātu pret nesankcionētām izmaiņām vai bojājumiem, tostarp mērķtiecīgām datu piesārņošanas mēģinājumiem. |   2   | D/V  |
| 1.2.4 | Pārliecinieties, ka datu kopas versijas tiek izsekotas, lai iespējotu atcelšanu.                                                                                                                                                                                                                                                                          |   3   | D/V  |
| 1.2.5 | Pārliecinieties, ka novecojušie dati tiek droši iznīcināti vai anonimizēti saskaņā ar datu glabāšanas politiku, reglamentējošām prasībām un lai samazinātu uzbrukuma virsmu.                                                                                                                                                                              |   2   | D/V  |

---

## C1.3 Attēlojuma pilnīgums un taisnīgums

Atklājiet demogrāfiskos novirzienus un piemērojiet to novēršanai, lai modeļa kļūdu līmenis būtu taisnīgs visās grupās.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Pārbaudiet, vai datu kopas ir analizētas attiecībā uz pārstāvniecības nelīdzsvarotību un potenciālajām aizspriedumiem likumīgi aizsargātās īpašībās (piemēram, rase, dzimums, vecums) un citās ētiski jutīgās raksturlielumos, kas ir svarīgi modeļa pielietošanas jomā (piemēram, sociāli ekonomiskais statuss, atrašanās vieta).                                                       |   1   | D/V  |
| 1.3.2 | Pārliecinieties, ka identificētie aizspriedumi tiek mazināti, izmantojot dokumentētas stratēģijas, piemēram, līdzsvarošanas pārskatīšanu, mērķtiecīgu datu papildināšanu, algoritmiskus pielāgojumus (piemēram, priekšapstrādes, apstrādes un pēcapstrādes metodes) vai pārsvaru pārvērtēšanu, un tiek novērtēta šo pasākumu ietekme gan uz taisnīgumu, gan uz modeļa kopējo veiktspēju. |   2   | D/V  |
| 1.3.3 | Pārliecinieties, ka tiek novērtēti un dokumentēti pēc apmācības veikto modeļu taisnīguma rādītāji.                                                                                                                                                                                                                                                                                       |   2   | D/V  |
| 1.3.4 | Pārliecinieties, ka dzīvotspējas cikla neitralitātes politikas pārvaldība piešķir atbildīgos un pārskata grafiku.                                                                                                                                                                                                                                                                        |   3   | D/V  |

---

## C1.4 Apmācības datu marķējuma kvalitāte, integritāte un drošība

Aizsargājiet etiķetes ar šifrēšanu un pieprasiet divkāršu pārskatu kritiskajām klasēm.

|   #   | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Pārliecinieties, ka marķēšanas/atzīmēšanas kvalitāte tiek nodrošināta, izmantojot skaidras vadlīnijas, pārskatītāju savstarpējas pārbaudes, konsensa mehānismus (piemēram, starpatzīmētāju vienošanās uzraudzību) un noteiktas procedūras neatbilstību risināšanai.                     |   2   | D/V  |
| 1.4.2 | Pārbaudiet, vai kriptogrāfiskās jaukšanas funkcijas vai digitālās parakstus ir piemēroti marķiera izstrādājumiem, lai nodrošinātu to integritāti un autentiskumu.                                                                                                                       |   2   | D/V  |
| 1.4.3 | Pārliecinieties, ka marķēšanas saskarnes un platformas nodrošina stingru piekļuves kontroli, uztur nemaināmus audita žurnālus par visām marķēšanas darbībām un aizsargā pret nesankcionētām izmaiņām.                                                                                   |   2   | D/V  |
| 1.4.4 | Pārbaudiet, vai drošībai, aizsardzībai vai taisnīgumam kritiskas etiķetes (piemēram, toksiska satura vai svarīgu medicīnisku atradumu identificēšana) tiek obligāti veiktas neatkarīgas dubultās pārbaudes vai tam ekvivalenta stingra verifikācija.                                    |   3   | D/V  |
| 1.4.5 | Pārliecinieties, ka sensitīva informācija (tai skaitā personu identificējoša informācija) nejauši ievāktā vai neizbēgami klātesošā veidnēs tiek slēpta, pseudonimizēta, anonimizēta vai šifrēta gan glabāšanas laikā, gan pārsūtīšanas laikā, saskaņā ar datu minimizācijas principiem. |   2   | D/V  |
| 1.4.6 | Pārbaudiet, vai marķēšanas vadlīnijas un norādījumi ir visaptveroši, versiju kontrolēti un kolēģu pārskatīti.                                                                                                                                                                           |   2   | D/V  |
| 1.4.7 | Pārliecinieties, ka datu shēmas (tai skaitā etiķešu) ir skaidri definētas un to versijas tiek kontrolētas.                                                                                                                                                                              |   2   | D/V  |
| 1.8.2 | Pārbaudiet, vai ārpakalpojuma vai lielapjoma apzīmēšanas darba plūsmās ir iekļautas tehniskas/procedurālas drošības prasības datu konfidencialitātes, integritātes, apzīmējumu kvalitātes nodrošināšanai un datu noplūdes novēršanai.                                                   |   2   | D/V  |

---

## C1.5 Apmācību datu kvalitātes nodrošināšana

Apvienojiet automatizētu validāciju, manuālu izlases pārbaudi un reģistrētu labošanas procesu, lai garantētu datu kopas uzticamību.

|   #   | Description                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Pārliecinieties, ka automatizētie testi atklāj formāta kļūdas, nulles vērtības un etiķešu novirzes katrā datu uzņemšanas vai būtiskas transformācijas posmā.                                                                                                                          |   1   |  D   |
| 1.5.2 | Pārbaudiet, vai neveiksmīgie datu kopumi tiek karantīnēti ar audita takām.                                                                                                                                                                                                            |   1   | D/V  |
| 1.5.3 | Pārliecinieties, ka nozares ekspertu manuālās izlases pārbaudes aptver statistiski nozīmīgu paraugu (piemēram, ≥1% vai 1000 paraugi, atkarībā no tā, kas ir lielāks, vai pēc riska novērtējuma), lai identificētu smalkas kvalitātes problēmas, kuras nav atklātas ar automatizāciju. |   2   |  V   |
| 1.5.4 | Pārbaudiet, vai novēršanas soļi ir pievienoti izcelsmes ierakstiem.                                                                                                                                                                                                                   |   2   | D/V  |
| 1.5.5 | Pārbaudiet, vai kvalitātes vārti bloķē zemākas kvalitātes datu kopas, ja vien nav apstiprinātas izņēmuma gadījumi.                                                                                                                                                                    |   2   | D/V  |

---

## C1.6 Datu indes noteikšana

Lietojiet statistiskās anomaliju noteikšanas un karantīnas darbplūsmas, lai apturētu naidīgu ievietošanu.

|   #   | Description                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Pārbaudiet, vai anomāliju noteikšanas tehnikas (piemēram, statistiskās metodes, ārpusparauga noteikšana, iegulšanas analīze) tiek pielietotas datu apmācības posmā pie datu ieplūdes un pirms galvenajām apmācības kārtām, lai identificētu iespējamos indēšanas uzbrukumus vai neparedzētu datu bojāšanos. |   2   | D/V  |
| 1.6.2 | Pārbaudiet, vai atzīmētie paraugi izsauc manuālu pārskatīšanu pirms apmācības.                                                                                                                                                                                                                              |   2   | D/V  |
| 1.6.3 | Pārliecinieties, ka rezultāti tiek nodoti modeļa drošības dosjē un informē par notiekošo draudu izlūkošanu.                                                                                                                                                                                                 |   2   |  V   |
| 1.6.4 | Pārliecinieties, ka noteikšanas loģika tiek atsvaidzināta ar jaunāko draudu informāciju.                                                                                                                                                                                                                    |   3   | D/V  |
| 1.6.5 | Pārliecinieties, ka tiešsaistes mācīšanās cauruļvadi uzrauga sadales novirzi.                                                                                                                                                                                                                               |   3   | D/V  |
| 1.6.6 | Pārliecinieties, ka konkrētas aizsardzības pret zināmu datu piesārņošanas uzbrukumu veidiem (piemēram, etiķešu apgriešana, slēptā durvju aktivizētāja ievietošana, ietekmīgu gadījumu uzbrukumi) tiek ņemtas vērā un ieviestas, pamatojoties uz sistēmas riska profilu un datu avotiem.                     |   3   | D/V  |

---

## C1.7 Lietotāja datu dzēšana un piekrišanas ievērošana

Godājiet dzēšanas un piekrišanas atsaukšanas pieprasījumus visos datu kopos, rezerves kopijās un radītajos artefaktos.

|   #   | Description                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Pārbaudiet, vai dzēšanas darba plūsmas iztīra primāros un atvasinātos datus, kā arī novērtējiet ietekmi uz modeļiem, un pārliecinieties, ka ietekme uz ietekmētajiem modeļiem tiek novērtēta un, ja nepieciešams, novērsta (piemēram, pārmācības vai recalibrēšanas ceļā).                            |   1   | D/V  |
| 1.7.2 | Pārliecinieties, ka ir izveidoti mehānismi lietotāja piekrišanas (un atsaukšanas) apjoma un statusa izsekošanai un ievērošanai attiecībā uz datiem, kas tiek izmantoti apmācībā, un ka piekrišana tiek pārbaudīta pirms datu iekļaušanas jaunās apmācības procesā vai būtiskās modeļa atjaunināšanās. |   2   |  D   |
| 1.7.3 | Pārbaudiet, vai darba plūsmas tiek testētas reizi gadā un reģistrētas.                                                                                                                                                                                                                                |   2   |  V   |

---

## C1.8 Piegādes ķēdes drošība

Pārbaudiet ārējos datu nodrošinātājus un verificējiet datu integritāti caur autentificētām, šifrētām kanāliem.

|   #   | Description                                                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Pārliecinieties, ka trešo pušu datu piegādātāji, tostarp iepriekš apmācītu modeļu un ārējo datu kopu nodrošinātāji, tiek pakļauti drošības, privātuma, ētiskas ieguves un datu kvalitātes pārbaudei pirms viņu datu vai modeļu integrēšanas.                                                                                            |   2   | D/V  |
| 1.8.2 | Pārbaudiet, vai ārējās pārsūtīšanas izmanto TLS/autentifikāciju un integritātes pārbaudes.                                                                                                                                                                                                                                              |   1   |  D   |
| 1.8.3 | Pārliecinieties, ka augsta riska datu avoti (piemēram, atvērtā pirmkoda datu kopas ar nezināmu izcelsmi, nepārbaudīti piegādātāji) tiek pakļauti pastiprinātai pārbaudei, piemēram, izolētai analīzei, plašām kvalitātes/novirzes pārbaudēm un mērķtiecīgai piesārņojuma noteikšanai, pirms to izmantošanas jutīgās lietojumprogrammās. |   2   | D/V  |
| 1.8.4 | Pārbaudiet, vai trešo pušu iepriekš apmācītie modeļi ir novērtēti attiecībā uz iebūvētajām aizspriedumiem, iespējamām aizmugurējām durvīm, to arhitektūras integritāti un to sākotnējās apmācības datu izcelsmi pirms pielāgošanas vai izvietošanas.                                                                                    |   3   | D/V  |

---

## C1.9 Antagonistu paraugu noteikšana

Ieviest pasākumus apmācību posmā, piemēram, pretinieku apmācību, lai uzlabotu modeļa noturību pret pretinieku piemēriem.

|   #   | Description                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Pārbaudiet, vai attiecīgām aizsardzības metodēm, piemēram, pretestības apmācībai (izmantojot ģenerētas pretestības piemērus), datu papildināšanai ar modificētiem ieejas datiem vai robusētām optimizācijas tehnikām, ir īstenotas un pielāgotas attiecīgajiem modeļiem, pamatojoties uz riska novērtējumu. |   3   | D/V  |
| 1.9.2 | Pārbaudiet, vai, ja tiek izmantota pretinieka apmācība, pretinieka datu kopu ģenerēšana, pārvaldība un versiju kontrole ir dokumentēta un kontrolēta.                                                                                                                                                       |   2   | D/V  |
| 1.9.3 | Pārliecinieties, ka tiek novērtēts, dokumentēts un uzraudzīts pretinieciski noturīgas apmācības ietekme uz modeļa veiktspēju (gan attiecībā uz tīriem, gan pretinieciskiem ievadiem) un godīguma metriku.                                                                                                   |   3   | D/V  |
| 1.9.4 | Pārbaudiet, vai stratēģijas pretinieku apmācībai un izturībai tiek periodiski pārskatītas un atjauninātas, lai pretotos mainīgām pretinieku uzbrukuma teknikām.                                                                                                                                             |   3   | D/V  |

---

## C1.10 Datu izcelsme un izsekojamība

Izsekojiet katra datu punkta pilnu ceļu no avota līdz modeļa ievadei, lai nodrošinātu auditu un incidentu reaģēšanu.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Pārliecinieties, ka katra datu punkta izcelsme, ieskaitot visas transformācijas, papildināšanas un apvienošanas, ir reģistrēta un to var rekonstruēt. |   2   | D/V  |
| 1.10.2 | Pārbaudiet, vai dzimtas ieraksti ir nemaināmi, droši uzglabāti un pieejami auditiem vai izmeklēšanām.                                                 |   2   | D/V  |
| 1.10.3 | Pārbaudiet, vai pēctecības izsekošana aptver gan izejvielu datus, gan sintētiskos datus.                                                              |   2   | D/V  |

---

## C1.11 Sintētisko datu pārvaldība

Nodrošiniet, ka sintētiskie dati tiek pareizi pārvaldīti, marķēti un riska novērtēti.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Pārliecinieties, ka visi sintētiskie dati visā procesā ir skaidri marķēti un atšķirami no reāliem datiem.                                                                  |   2   | D/V  |
| 1.11.2 | Pārliecinieties, ka sintētisko datu ģenerēšanas process, parametri un paredzētā izmantošana ir dokumentēti.                                                                |   2   | D/V  |
| 1.11.3 | Pārliecinieties, ka sintētiskie dati ir novērtēti pēc riskiem attiecībā uz aizspriedumiem, privātuma noplūdēm un reprezentācijas problēmām pirms to izmantošanas apmācībā. |   2   | D/V  |

---

## C1.12 Datu piekļuves uzraudzība un anomāliju noteikšana

Uzraudzīt un brīdināt par neparastu piekļuvi mācību datiem, lai atklātu iekšējos draudus vai datu noplūdi.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Pārbaudiet, vai visi piekļuves gadījumi mācību datiem tiek reģistrēti, tostarp lietotājs, laiks un veiktā darbība.                                                                        |   2   | D/V  |
| 1.12.2 | Pārliecinieties, ka piekļuves žurnāli tiek regulāri pārskatīti, lai atklātu neparastas prasības, piemēram, lielas eksportēšanas darbības vai piekļuvi no jauniem ģeogrāfiskiem reģioniem. |   2   | D/V  |
| 1.12.3 | Pārliecinieties, ka tiek ģenerēti brīdinājumi par aizdomīgiem piekļuves notikumiem un tie tiek nekavējoties izmeklēti.                                                                    |   2   | D/V  |

---

## C1.13 Datu glabāšanas un derīguma termiņu politikas

Definējiet un ieviesiet datu saglabāšanas periodus, lai samazinātu nevajadzīgu datu uzglabāšanu.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.13.1 | Pārbaudiet, vai visiem apmācību datu kopām ir definēti skaidri noteikti glabāšanas laiki.                          |   1   | D/V  |
| 1.13.2 | Pārliecinieties, ka datu kopas tiek automātiski anulētas, dzēstas vai pārskatītas dzēšanai to dzīves cikla beigās. |   2   | D/V  |
| 1.13.3 | Pārliecinieties, ka saglabāšanas un dzēšanas darbības tiek reģistrētas un ir auditojamas.                          |   2   | D/V  |

---

## C1.14 Regulatīvā un jurisdikcijas atbilstība

Nodrošiniet, ka visi apmācību dati atbilst piemērojamiem likumiem un noteikumiem.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Pārliecinieties, ka visas datu kopas atbilst datu atrašanās vietas un datu pārsūtīšanas pāri robežām prasībām, un šīs prasības tiek izpildītas. |   2   | D/V  |
| 1.14.2 | Pārbaudiet, vai ir identificētas un ņemtas vērā nozares specifiskas regulas (piemēram, veselības aprūpe, finanses) datu apstrādē.               |   2   | D/V  |
| 1.14.3 | Pārbaudiet, vai atbilstība attiecīgajiem datu aizsardzības likumiem (piemēram, GDPR, CCPA) ir dokumentēta un regulāri pārskatīta.               |   2   | D/V  |

---

## C1.15 Datu ūdenszīmju un pirkstu nospiedumu veidošana

Atklājiet neatļautu īpašumtiesību vai sensitīvu datu atkārtotu izmantošanu vai noplūdi.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Pārbaudiet, vai datu kopas vai to apakškopu ir iespējams nomainīt ar ūdenszīmēm vai pirkstu nospiedumiem.                   |   3   | D/V  |
| 1.15.2 | Pārbaudiet, vai ūdenszīmju/atzīmju metodes neievieš aizspriedumus vai privātuma riskus.                                     |   3   | D/V  |
| 1.15.3 | Pārbaudiet, vai tiek veikti periodiski pārbaudes, lai noteiktu neatļautu ūdenszīmes datu atkārtotu izmantošanu vai noplūdi. |   3   | D/V  |

---

## C1.16 Datu Subjektu Tiesību Pārvaldība

Atbalstīt datu subjektu tiesības, piemēram, piekļuvi, labošanu, ierobežošanu un iebildumus.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Pārliecinieties, ka pastāv mehānismi, kas nodrošina atbildes uz datu subjektu pieprasījumiem par piekļuvi, labošanu, ierobežošanu vai iebildumiem. |   2   | D/V  |
| 1.16.2 | Pārbaudiet, vai pieprasījumi tiek reģistrēti, izsekoti un izpildīti likumos noteiktajos termiņos.                                                  |   2   | D/V  |
| 1.16.3 | Pārbaudiet, vai datu subjekta tiesību procesi tiek regulāri testēti un pārskatīti to efektivitātes nodrošināšanai.                                 |   2   | D/V  |

---

## C1.17 Datu kopas versijas ietekmes analīze

Novērtējiet datu kopas izmaiņu ietekmi pirms versiju atjaunināšanas vai nomaiņas.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Pārliecinieties, ka pirms datu kopas versijas atjaunināšanas vai aizstāšanas tiek veikta ietekmes analīze, aptverot modeļa veiktspēju, taisnīgumu un atbilstību. |   2   | D/V  |
| 1.17.2 | Pārliecinieties, ka ietekmes analīzes rezultāti ir dokumentēti un pārskatīti atbilstošo ieinteresēto pušu.                                                       |   2   | D/V  |
| 1.17.3 | Pārliecinieties, ka ir izstrādātas atgriešanas plāni gadījumā, ja jaunas versijas ievieš nepieļaujamas riskus vai regresijas.                                    |   2   | D/V  |

---

## C1.18 Datu anotācijas darba spēka drošība

Nodrošiniet datu anotācijā iesaistītā personāla drošību un integritāti.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Pārliecinieties, ka visi personas, kas iesaistītas datu anotācijā, ir pārbaudīti fonā un apmācīti datu drošībā un privātuma aizsardzībā. |   2   | D/V  |
| 1.18.2 | Pārliecinieties, ka viss anotācijas personāls paraksta konfidencialitātes un nesadziļināšanas līgumus.                                   |   2   | D/V  |
| 1.18.3 | Pārbaudiet, vai anotācijas platformas ievēro piekļuves kontroli un uzrauga iekšējos draudus.                                             |   2   | D/V  |

---

## Atsauces

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

