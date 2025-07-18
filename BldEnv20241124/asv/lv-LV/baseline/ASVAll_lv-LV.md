## Priekšvāks

### Par standartu

Mākslīgā intelekta drošības pārbaudes standarts (AISVS) ir kopienas vadīts drošības prasību katalogs, ko var izmantot datu zinātnieki, MLOps inženieri, programmatūras arhitekti, izstrādātāji, testētāji, drošības speciālisti, rīku piegādātāji, regulatori un patērētāji, lai izstrādātu, būvētu, testētu un pārbaudītu uzticamas mākslīgā intelekta sistēmas un lietojumprogrammas. Tas nodrošina kopīgu valodu drošības kontroles prasību noteikšanai visā MI dzīves ciklā — no datu vākšanas un modeļa izstrādes līdz izvietošanai un pastāvīgai uzraudzībai — ļaujot organizācijām novērtēt un uzlabot sava mākslīgā intelekta risinājumu izturību, privātumu un drošību.

### Autortiesības un licence

Versija 0.1 (Pirmais publiskais melnraksts - Darba procesā), 2025  

![license](images/license.png)
Autortiesības © 2025 AISVS projekts.  

Izlaists zemCreative Commons Attribution‑ShareAlike 4.0 International License.
Jebkurai atkārtotai izmantošanai vai izplatīšanai jums skaidri jānorāda šī darba licences nosacījumi citiem.

### Projektu vadītāji

Džims Maniko
Aras “Russ” Memisyazici

### Līdzdarbinieki un recenzenti

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS ir pilnīgi jauns standarts, kas izveidots īpaši, lai risinātu mākslīgā intelekta sistēmu unikālās drošības problēmas. Lai gan tas iedvesmojas no vispārīgākām drošības labākās prakses vadlīnijām, katrs AISVS prasības punkts ir izstrādāts no jauna, lai atspoguļotu mākslīgā intelekta draudu ainavu un palīdzētu organizācijām izveidot drošākus, izturīgākus AI risinājumus.

## Priekšteikums

Laipni lūdzam Mākslīgā intelekta drošības pārbaudes standartā (AISVS) versija 1.0!

### Ievads

Izveidota 2025. gadā kā kopīgs kopienas centiens, AISVS nosaka drošības prasības, kuras jāņem vērā, izstrādājot, izstrādājot, ieviešot un pārvaldot modernas mākslīgā intelekta (MI) modeļus, datu apstrādes ķēdes un MI iespējas nodrošinošus pakalpojumus.

AISVS v1.0 apvieno tā projekta vadītāju, darba grupas un plašākas kopienas līdzgaitnieku kopīgo darbu, lai izveidotu pragmatisku, pārbaudāmu bāzi AI sistēmu drošības nodrošināšanai.

Mūsu mērķis ar šo versiju ir padarīt AISVS viegli pieejamu, vienlaikus stingri koncentrējoties uz tā noteikto darbības jomu un risinot strauji mainīgo AI īpašo risku ainavu.

### Galvenie mērķi AISVS 1.0 versijai

Versija 1.0 tiks izveidota, balstoties uz vairākām vadlīnijām.

#### Precīzi definēts darbības lauks

Katram prasījumam jāatbilst AISVS nosaukumam un misijai:

Mākslīgais intelekts – Kontroles darbojas AI/ML slānī (datu, modeļa, cauruļvada vai secinājuma līmenī) un ir AI praktiķu atbildība.
Drošība – prasības tieši mazinās identificētos drošības, privātuma vai drošības riskus.
Verifikācija – valoda ir rakstīta tā, lai atbilstību varētu objektīvi pārbaudīt.
Standarts – sadaļas seko konsekventai struktūrai un terminoloģijai, veidojot saskaņotu atsauci.
​
---

Sekojot AISVS, organizācijas var sistemātiski novērtēt un stiprināt savu AI risinājumu drošības stāvokli, veicinot drošas AI izstrādes kultūru.

## Izmantojot AISVS

Mākslīgā intelekta drošības verificēšanas standarts (AISVS) nosaka drošības prasības mūsdienu AI lietojumprogrammām un pakalpojumiem, koncentrējoties uz aspektiem, kas ir lietojumprogrammu izstrādātāju kontrolē.

AISVS ir paredzēts ikvienam, kas izstrādā vai vērtē mākslīgā intelekta (MI) lietojumprogrammu drošību, tai skaitā izstrādātājiem, arhitektiem, drošības inženieriem un auditiem. Šajā nodaļā tiek iepazīstināta AISVS struktūra un lietošana, ieskaitot tā pārbaudes līmeņus un paredzētos lietošanas gadījumus.

### Mākslīgā intelekta drošības pārbaudes līmeņi

AISVS nosaka trīs augošus drošības verifikācijas līmeņus. Katrs līmenis palielina dziļumu un sarežģītību, ļaujot organizācijām pielāgot savu drošības stāvokli AI sistēmu riska līmenim.

Organizācijas var sākt no 1. līmeņa un pakāpeniski pieņemt augstākus līmeņus, palielinoties drošības briedumam un draudu pakāpei.

#### Līmeņu definīcija

Katram prasījumam AISVS v1.0 ir piešķirts viens no šādiem līmeņiem:

 Līmeņa 1 prasības

līmenis ietver viskritiskākās un pamata drošības prasības. Šīs prasības koncentrējas uz izplatītu uzbrukumu novēršanu, kas nebalstās uz citiem priekšnoteikumiem vai ievainojamībām. Lielākā daļa 1. līmeņa kontroles pasākumu ir vai nu vienkārši īstenojami, vai arī pietiekami būtiski, lai pamatotu nepieciešamās pūles.

 2. līmeņa prasības

līmenis aptver sarežģītākus vai retāk sastopamus uzbrukumus, kā arī daudzslāņu aizsardzību pret plaši izplatītām draudēm. Šīs prasības var ietvert sarežģītāku loģiku vai mērķēt uz konkrētiem uzbrukuma priekšnoteikumiem.

 3. līmeņa prasības

līmenis ietver kontroles, kuras parasti ir grūtāk īstenojamas vai piemērojamas tikai noteiktos gadījumos. Tās bieži pārstāv dziļās aizsardzības mehānismus vai mazināšanas pasākumus pret nišas, mērķtiecīgiem vai augstas sarežģītības līmeņa uzbrukumiem.

#### Loma (D/V)

Katrs AISVS prasījums ir atzīmēts atbilstoši galvenajai auditorijai:

D – Izstrādātājam orientētas prasības
V – Verifikatora/revidenta orientētās prasības
D/V – Attiecināms gan uz izstrādātājiem, gan pārbaudītājiem

## C1 Apmācību datu pārvaldība un noviržu vadība

### Kontroles mērķis

Apmācību dati ir jāiegūst, jāapstrādā un jāuztur tādā veidā, kas saglabā izcelsmi, drošību, kvalitāti un godīgumu. Šādi rīkojoties, tiek izpildītas juridiskās saistības un samazināti aizspriedumu, inficēšanas vai privātuma pārkāpumu riski visā AI dzīves ciklā.

---

### C1.1 Apmācību datu izcelsme

Uzturiet pārbaudāmu visu datu kopu inventāru, pieņemiet tikai uzticamus avotus un reģistrējiet katru izmaiņu auditējamībai.

 #1.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka tiek uzturēts aktuāls katra apmācību datu avota inventārs (avots, atbildīgais/īpašnieks, licence, vākšanas metode, paredzētās izmantošanas ierobežojumi un apstrādes vēsture).
 #1.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka tiek atļauti tikai tādi datu kopumi, kas pārbaudīti kvalitātes, reprezentativitātes, ētiskas izcelsmes un licences atbilstības ziņā, samazinot saindēšanas, iebūvētas aizspriedumu un intelektuālā īpašuma pārkāpumu riskus.
 #1.1.3    Level: 1    Role: D/V
 Pārliecinieties, ka tiek īstenota datu minimizācija, lai nevajadzīgas vai sensitīvas atribūtas tiktu izslēgtas.
 #1.1.4    Level: 2    Role: D/V
 Pārliecinieties, ka visas datu kopas izmaiņas tiek apstiprinātas un reģistrētas caur apstiprināšanas darbplūsmu.
 #1.1.5    Level: 2    Role: D/V
 Pārliecinieties, ka marķēšanas/annotācijas kvalitāte ir nodrošināta, veicot pārskatītāja savstarpēju pārbaudi vai sasniedzot vienprātību.
 #1.1.6    Level: 2    Role: D/V
 Pārliecinieties, ka tiek uzturētas "datu kartes" vai "datu kopu datu lapas" nozīmīgām apmācību datu kopām, kurās ir detalizēti aprakstītas to īpašības, motivācijas, sastāvs, vākšanas procesi, priekšapstrāde un ieteicamā/neieteicamā lietošana.

---

### C1.2 Apmācības datu drošība un integritāte

Ierobežojiet piekļuvi, šifrējiet datus atpūtā un pārsūtīšanas laikā, un pārbaudiet integritāti, lai novērstu manipulācijas vai zādzību.

 #1.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka piekļuves kontroles aizsargā datu glabāšanu un datu apstrādes plūsmas.
 #1.2.2    Level: 2    Role: D/V
 Pārbaudiet, vai datu kopas tiek šifrētas pārvades laikā un, attiecībā uz visu sensitīvo vai personiski identificējamo informāciju (PII), arī glabāšanas laikā, izmantojot nozares standarta kriptogrāfiskās algoritmus un atslēgu pārvaldības prakses.
 #1.2.3    Level: 2    Role: D/V
 Pārliecinieties, ka kriptogrāfiskās hašvērtības vai digitālās parakstīšanas tiek izmantotas, lai nodrošinātu datu integritāti glabāšanas un pārsūtīšanas laikā, un ka tiek pielietotas automātiskās anomāliju noteikšanas tehnoloģijas, lai aizsargātu pret nesankcionētām izmaiņām vai bojājumiem, tostarp mērķtiecīgām datu piesārņošanas mēģinājumiem.
 #1.2.4    Level: 3    Role: D/V
 Pārliecinieties, ka datu kopas versijas tiek izsekotas, lai iespējotu atcelšanu.
 #1.2.5    Level: 2    Role: D/V
 Pārliecinieties, ka novecojušie dati tiek droši iznīcināti vai anonimizēti saskaņā ar datu glabāšanas politiku, reglamentējošām prasībām un lai samazinātu uzbrukuma virsmu.

---

### C1.3 Attēlojuma pilnīgums un taisnīgums

Atklājiet demogrāfiskos novirzienus un piemērojiet to novēršanai, lai modeļa kļūdu līmenis būtu taisnīgs visās grupās.

 #1.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai datu kopas ir analizētas attiecībā uz pārstāvniecības nelīdzsvarotību un potenciālajām aizspriedumiem likumīgi aizsargātās īpašībās (piemēram, rase, dzimums, vecums) un citās ētiski jutīgās raksturlielumos, kas ir svarīgi modeļa pielietošanas jomā (piemēram, sociāli ekonomiskais statuss, atrašanās vieta).
 #1.3.2    Level: 2    Role: D/V
 Pārliecinieties, ka identificētie aizspriedumi tiek mazināti, izmantojot dokumentētas stratēģijas, piemēram, līdzsvarošanas pārskatīšanu, mērķtiecīgu datu papildināšanu, algoritmiskus pielāgojumus (piemēram, priekšapstrādes, apstrādes un pēcapstrādes metodes) vai pārsvaru pārvērtēšanu, un tiek novērtēta šo pasākumu ietekme gan uz taisnīgumu, gan uz modeļa kopējo veiktspēju.
 #1.3.3    Level: 2    Role: D/V
 Pārliecinieties, ka tiek novērtēti un dokumentēti pēc apmācības veikto modeļu taisnīguma rādītāji.
 #1.3.4    Level: 3    Role: D/V
 Pārliecinieties, ka dzīvotspējas cikla neitralitātes politikas pārvaldība piešķir atbildīgos un pārskata grafiku.

---

### C1.4 Apmācības datu marķējuma kvalitāte, integritāte un drošība

Aizsargājiet etiķetes ar šifrēšanu un pieprasiet divkāršu pārskatu kritiskajām klasēm.

 #1.4.1    Level: 2    Role: D/V
 Pārliecinieties, ka marķēšanas/atzīmēšanas kvalitāte tiek nodrošināta, izmantojot skaidras vadlīnijas, pārskatītāju savstarpējas pārbaudes, konsensa mehānismus (piemēram, starpatzīmētāju vienošanās uzraudzību) un noteiktas procedūras neatbilstību risināšanai.
 #1.4.2    Level: 2    Role: D/V
 Pārbaudiet, vai kriptogrāfiskās jaukšanas funkcijas vai digitālās parakstus ir piemēroti marķiera izstrādājumiem, lai nodrošinātu to integritāti un autentiskumu.
 #1.4.3    Level: 2    Role: D/V
 Pārliecinieties, ka marķēšanas saskarnes un platformas nodrošina stingru piekļuves kontroli, uztur nemaināmus audita žurnālus par visām marķēšanas darbībām un aizsargā pret nesankcionētām izmaiņām.
 #1.4.4    Level: 3    Role: D/V
 Pārbaudiet, vai drošībai, aizsardzībai vai taisnīgumam kritiskas etiķetes (piemēram, toksiska satura vai svarīgu medicīnisku atradumu identificēšana) tiek obligāti veiktas neatkarīgas dubultās pārbaudes vai tam ekvivalenta stingra verifikācija.
 #1.4.5    Level: 2    Role: D/V
 Pārliecinieties, ka sensitīva informācija (tai skaitā personu identificējoša informācija) nejauši ievāktā vai neizbēgami klātesošā veidnēs tiek slēpta, pseudonimizēta, anonimizēta vai šifrēta gan glabāšanas laikā, gan pārsūtīšanas laikā, saskaņā ar datu minimizācijas principiem.
 #1.4.6    Level: 2    Role: D/V
 Pārbaudiet, vai marķēšanas vadlīnijas un norādījumi ir visaptveroši, versiju kontrolēti un kolēģu pārskatīti.
 #1.4.7    Level: 2    Role: D/V
 Pārliecinieties, ka datu shēmas (tai skaitā etiķešu) ir skaidri definētas un to versijas tiek kontrolētas.
 #1.8.2    Level: 2    Role: D/V
 Pārbaudiet, vai ārpakalpojuma vai lielapjoma apzīmēšanas darba plūsmās ir iekļautas tehniskas/procedurālas drošības prasības datu konfidencialitātes, integritātes, apzīmējumu kvalitātes nodrošināšanai un datu noplūdes novēršanai.

---

### C1.5 Apmācību datu kvalitātes nodrošināšana

Apvienojiet automatizētu validāciju, manuālu izlases pārbaudi un reģistrētu labošanas procesu, lai garantētu datu kopas uzticamību.

 #1.5.1    Level: 1    Role: D
 Pārliecinieties, ka automatizētie testi atklāj formāta kļūdas, nulles vērtības un etiķešu novirzes katrā datu uzņemšanas vai būtiskas transformācijas posmā.
 #1.5.2    Level: 1    Role: D/V
 Pārbaudiet, vai neveiksmīgie datu kopumi tiek karantīnēti ar audita takām.
 #1.5.3    Level: 2    Role: V
 Pārliecinieties, ka nozares ekspertu manuālās izlases pārbaudes aptver statistiski nozīmīgu paraugu (piemēram, ≥1% vai 1000 paraugi, atkarībā no tā, kas ir lielāks, vai pēc riska novērtējuma), lai identificētu smalkas kvalitātes problēmas, kuras nav atklātas ar automatizāciju.
 #1.5.4    Level: 2    Role: D/V
 Pārbaudiet, vai novēršanas soļi ir pievienoti izcelsmes ierakstiem.
 #1.5.5    Level: 2    Role: D/V
 Pārbaudiet, vai kvalitātes vārti bloķē zemākas kvalitātes datu kopas, ja vien nav apstiprinātas izņēmuma gadījumi.

---

### C1.6 Datu indes noteikšana

Lietojiet statistiskās anomaliju noteikšanas un karantīnas darbplūsmas, lai apturētu naidīgu ievietošanu.

 #1.6.1    Level: 2    Role: D/V
 Pārbaudiet, vai anomāliju noteikšanas tehnikas (piemēram, statistiskās metodes, ārpusparauga noteikšana, iegulšanas analīze) tiek pielietotas datu apmācības posmā pie datu ieplūdes un pirms galvenajām apmācības kārtām, lai identificētu iespējamos indēšanas uzbrukumus vai neparedzētu datu bojāšanos.
 #1.6.2    Level: 2    Role: D/V
 Pārbaudiet, vai atzīmētie paraugi izsauc manuālu pārskatīšanu pirms apmācības.
 #1.6.3    Level: 2    Role: V
 Pārliecinieties, ka rezultāti tiek nodoti modeļa drošības dosjē un informē par notiekošo draudu izlūkošanu.
 #1.6.4    Level: 3    Role: D/V
 Pārliecinieties, ka noteikšanas loģika tiek atsvaidzināta ar jaunāko draudu informāciju.
 #1.6.5    Level: 3    Role: D/V
 Pārliecinieties, ka tiešsaistes mācīšanās cauruļvadi uzrauga sadales novirzi.
 #1.6.6    Level: 3    Role: D/V
 Pārliecinieties, ka konkrētas aizsardzības pret zināmu datu piesārņošanas uzbrukumu veidiem (piemēram, etiķešu apgriešana, slēptā durvju aktivizētāja ievietošana, ietekmīgu gadījumu uzbrukumi) tiek ņemtas vērā un ieviestas, pamatojoties uz sistēmas riska profilu un datu avotiem.

---

### C1.7 Lietotāja datu dzēšana un piekrišanas ievērošana

Godājiet dzēšanas un piekrišanas atsaukšanas pieprasījumus visos datu kopos, rezerves kopijās un radītajos artefaktos.

 #1.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai dzēšanas darba plūsmas iztīra primāros un atvasinātos datus, kā arī novērtējiet ietekmi uz modeļiem, un pārliecinieties, ka ietekme uz ietekmētajiem modeļiem tiek novērtēta un, ja nepieciešams, novērsta (piemēram, pārmācības vai recalibrēšanas ceļā).
 #1.7.2    Level: 2    Role: D
 Pārliecinieties, ka ir izveidoti mehānismi lietotāja piekrišanas (un atsaukšanas) apjoma un statusa izsekošanai un ievērošanai attiecībā uz datiem, kas tiek izmantoti apmācībā, un ka piekrišana tiek pārbaudīta pirms datu iekļaušanas jaunās apmācības procesā vai būtiskās modeļa atjaunināšanās.
 #1.7.3    Level: 2    Role: V
 Pārbaudiet, vai darba plūsmas tiek testētas reizi gadā un reģistrētas.

---

### C1.8 Piegādes ķēdes drošība

Pārbaudiet ārējos datu nodrošinātājus un verificējiet datu integritāti caur autentificētām, šifrētām kanāliem.

 #1.8.1    Level: 2    Role: D/V
 Pārliecinieties, ka trešo pušu datu piegādātāji, tostarp iepriekš apmācītu modeļu un ārējo datu kopu nodrošinātāji, tiek pakļauti drošības, privātuma, ētiskas ieguves un datu kvalitātes pārbaudei pirms viņu datu vai modeļu integrēšanas.
 #1.8.2    Level: 1    Role: D
 Pārbaudiet, vai ārējās pārsūtīšanas izmanto TLS/autentifikāciju un integritātes pārbaudes.
 #1.8.3    Level: 2    Role: D/V
 Pārliecinieties, ka augsta riska datu avoti (piemēram, atvērtā pirmkoda datu kopas ar nezināmu izcelsmi, nepārbaudīti piegādātāji) tiek pakļauti pastiprinātai pārbaudei, piemēram, izolētai analīzei, plašām kvalitātes/novirzes pārbaudēm un mērķtiecīgai piesārņojuma noteikšanai, pirms to izmantošanas jutīgās lietojumprogrammās.
 #1.8.4    Level: 3    Role: D/V
 Pārbaudiet, vai trešo pušu iepriekš apmācītie modeļi ir novērtēti attiecībā uz iebūvētajām aizspriedumiem, iespējamām aizmugurējām durvīm, to arhitektūras integritāti un to sākotnējās apmācības datu izcelsmi pirms pielāgošanas vai izvietošanas.

---

### C1.9 Antagonistu paraugu noteikšana

Ieviest pasākumus apmācību posmā, piemēram, pretinieku apmācību, lai uzlabotu modeļa noturību pret pretinieku piemēriem.

 #1.9.1    Level: 3    Role: D/V
 Pārbaudiet, vai attiecīgām aizsardzības metodēm, piemēram, pretestības apmācībai (izmantojot ģenerētas pretestības piemērus), datu papildināšanai ar modificētiem ieejas datiem vai robusētām optimizācijas tehnikām, ir īstenotas un pielāgotas attiecīgajiem modeļiem, pamatojoties uz riska novērtējumu.
 #1.9.2    Level: 2    Role: D/V
 Pārbaudiet, vai, ja tiek izmantota pretinieka apmācība, pretinieka datu kopu ģenerēšana, pārvaldība un versiju kontrole ir dokumentēta un kontrolēta.
 #1.9.3    Level: 3    Role: D/V
 Pārliecinieties, ka tiek novērtēts, dokumentēts un uzraudzīts pretinieciski noturīgas apmācības ietekme uz modeļa veiktspēju (gan attiecībā uz tīriem, gan pretinieciskiem ievadiem) un godīguma metriku.
 #1.9.4    Level: 3    Role: D/V
 Pārbaudiet, vai stratēģijas pretinieku apmācībai un izturībai tiek periodiski pārskatītas un atjauninātas, lai pretotos mainīgām pretinieku uzbrukuma teknikām.

---

### C1.10 Datu izcelsme un izsekojamība

Izsekojiet katra datu punkta pilnu ceļu no avota līdz modeļa ievadei, lai nodrošinātu auditu un incidentu reaģēšanu.

 #1.10.1    Level: 2    Role: D/V
 Pārliecinieties, ka katra datu punkta izcelsme, ieskaitot visas transformācijas, papildināšanas un apvienošanas, ir reģistrēta un to var rekonstruēt.
 #1.10.2    Level: 2    Role: D/V
 Pārbaudiet, vai dzimtas ieraksti ir nemaināmi, droši uzglabāti un pieejami auditiem vai izmeklēšanām.
 #1.10.3    Level: 2    Role: D/V
 Pārbaudiet, vai pēctecības izsekošana aptver gan izejvielu datus, gan sintētiskos datus.

---

### C1.11 Sintētisko datu pārvaldība

Nodrošiniet, ka sintētiskie dati tiek pareizi pārvaldīti, marķēti un riska novērtēti.

 #1.11.1    Level: 2    Role: D/V
 Pārliecinieties, ka visi sintētiskie dati visā procesā ir skaidri marķēti un atšķirami no reāliem datiem.
 #1.11.2    Level: 2    Role: D/V
 Pārliecinieties, ka sintētisko datu ģenerēšanas process, parametri un paredzētā izmantošana ir dokumentēti.
 #1.11.3    Level: 2    Role: D/V
 Pārliecinieties, ka sintētiskie dati ir novērtēti pēc riskiem attiecībā uz aizspriedumiem, privātuma noplūdēm un reprezentācijas problēmām pirms to izmantošanas apmācībā.

---

### C1.12 Datu piekļuves uzraudzība un anomāliju noteikšana

Uzraudzīt un brīdināt par neparastu piekļuvi mācību datiem, lai atklātu iekšējos draudus vai datu noplūdi.

 #1.12.1    Level: 2    Role: D/V
 Pārbaudiet, vai visi piekļuves gadījumi mācību datiem tiek reģistrēti, tostarp lietotājs, laiks un veiktā darbība.
 #1.12.2    Level: 2    Role: D/V
 Pārliecinieties, ka piekļuves žurnāli tiek regulāri pārskatīti, lai atklātu neparastas prasības, piemēram, lielas eksportēšanas darbības vai piekļuvi no jauniem ģeogrāfiskiem reģioniem.
 #1.12.3    Level: 2    Role: D/V
 Pārliecinieties, ka tiek ģenerēti brīdinājumi par aizdomīgiem piekļuves notikumiem un tie tiek nekavējoties izmeklēti.

---

### C1.13 Datu glabāšanas un derīguma termiņu politikas

Definējiet un ieviesiet datu saglabāšanas periodus, lai samazinātu nevajadzīgu datu uzglabāšanu.

 #1.13.1    Level: 1    Role: D/V
 Pārbaudiet, vai visiem apmācību datu kopām ir definēti skaidri noteikti glabāšanas laiki.
 #1.13.2    Level: 2    Role: D/V
 Pārliecinieties, ka datu kopas tiek automātiski anulētas, dzēstas vai pārskatītas dzēšanai to dzīves cikla beigās.
 #1.13.3    Level: 2    Role: D/V
 Pārliecinieties, ka saglabāšanas un dzēšanas darbības tiek reģistrētas un ir auditojamas.

---

### C1.14 Regulatīvā un jurisdikcijas atbilstība

Nodrošiniet, ka visi apmācību dati atbilst piemērojamiem likumiem un noteikumiem.

 #1.14.1    Level: 2    Role: D/V
 Pārliecinieties, ka visas datu kopas atbilst datu atrašanās vietas un datu pārsūtīšanas pāri robežām prasībām, un šīs prasības tiek izpildītas.
 #1.14.2    Level: 2    Role: D/V
 Pārbaudiet, vai ir identificētas un ņemtas vērā nozares specifiskas regulas (piemēram, veselības aprūpe, finanses) datu apstrādē.
 #1.14.3    Level: 2    Role: D/V
 Pārbaudiet, vai atbilstība attiecīgajiem datu aizsardzības likumiem (piemēram, GDPR, CCPA) ir dokumentēta un regulāri pārskatīta.

---

### C1.15 Datu ūdenszīmju un pirkstu nospiedumu veidošana

Atklājiet neatļautu īpašumtiesību vai sensitīvu datu atkārtotu izmantošanu vai noplūdi.

 #1.15.1    Level: 3    Role: D/V
 Pārbaudiet, vai datu kopas vai to apakškopu ir iespējams nomainīt ar ūdenszīmēm vai pirkstu nospiedumiem.
 #1.15.2    Level: 3    Role: D/V
 Pārbaudiet, vai ūdenszīmju/atzīmju metodes neievieš aizspriedumus vai privātuma riskus.
 #1.15.3    Level: 3    Role: D/V
 Pārbaudiet, vai tiek veikti periodiski pārbaudes, lai noteiktu neatļautu ūdenszīmes datu atkārtotu izmantošanu vai noplūdi.

---

### C1.16 Datu Subjektu Tiesību Pārvaldība

Atbalstīt datu subjektu tiesības, piemēram, piekļuvi, labošanu, ierobežošanu un iebildumus.

 #1.16.1    Level: 2    Role: D/V
 Pārliecinieties, ka pastāv mehānismi, kas nodrošina atbildes uz datu subjektu pieprasījumiem par piekļuvi, labošanu, ierobežošanu vai iebildumiem.
 #1.16.2    Level: 2    Role: D/V
 Pārbaudiet, vai pieprasījumi tiek reģistrēti, izsekoti un izpildīti likumos noteiktajos termiņos.
 #1.16.3    Level: 2    Role: D/V
 Pārbaudiet, vai datu subjekta tiesību procesi tiek regulāri testēti un pārskatīti to efektivitātes nodrošināšanai.

---

### C1.17 Datu kopas versijas ietekmes analīze

Novērtējiet datu kopas izmaiņu ietekmi pirms versiju atjaunināšanas vai nomaiņas.

 #1.17.1    Level: 2    Role: D/V
 Pārliecinieties, ka pirms datu kopas versijas atjaunināšanas vai aizstāšanas tiek veikta ietekmes analīze, aptverot modeļa veiktspēju, taisnīgumu un atbilstību.
 #1.17.2    Level: 2    Role: D/V
 Pārliecinieties, ka ietekmes analīzes rezultāti ir dokumentēti un pārskatīti atbilstošo ieinteresēto pušu.
 #1.17.3    Level: 2    Role: D/V
 Pārliecinieties, ka ir izstrādātas atgriešanas plāni gadījumā, ja jaunas versijas ievieš nepieļaujamas riskus vai regresijas.

---

### C1.18 Datu anotācijas darba spēka drošība

Nodrošiniet datu anotācijā iesaistītā personāla drošību un integritāti.

 #1.18.1    Level: 2    Role: D/V
 Pārliecinieties, ka visi personas, kas iesaistītas datu anotācijā, ir pārbaudīti fonā un apmācīti datu drošībā un privātuma aizsardzībā.
 #1.18.2    Level: 2    Role: D/V
 Pārliecinieties, ka viss anotācijas personāls paraksta konfidencialitātes un nesadziļināšanas līgumus.
 #1.18.3    Level: 2    Role: D/V
 Pārbaudiet, vai anotācijas platformas ievēro piekļuves kontroli un uzrauga iekšējos draudus.

---

### Atsauces

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## C2 Lietotāja ievades validācija

### Kontroles mērķis

Lietotāja ievades stingra validācija ir pirmās līnijas aizsardzība pret dažiem no vissmagākajiem uzbrukumiem AI sistēmām. Uzbrukumi, kas izmanto promptu injekciju, var pārrakstīt sistēmas instrukcijas, nopludināt sensitīvus datus vai novirzīt modeli uz aizliegtu uzvedību. Ja nav ieviesti speciāli filtri un instrukciju hierarhijas, pētījumi rāda, ka "multi-shot" jailbreaks, kas izmanto ļoti garus konteksta logus, būs efektīvi. Tāpat smalki pretinieku manipulāciju uzbrukumi—piemēram, homoglifas aizvietojumi vai leetspeak—var klusējot mainīt modeļa lēmumus.

---

### C2.1 Uzvedības injekcijas aizsardzība

Priekšmeta injekcija ir viens no lielākajiem riskiem mākslīgā intelekta sistēmām. Aizsardzība pret šo taktiku izmanto statisku paraugu filtru, dinamisku klasificētāju un instrukciju hierarhijas ievērošanas kombināciju.

 #2.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka lietotāja ievades tiek pārbaudītas pret nepārtraukti atjauninātu zināmu uzvednes injekciju paraugu bibliotēku (jailbreak atslēgvārdi, "neklausīt iepriekšējo", lomu spēles ķēdes, netiešas HTML/URL uzbrukumi).
 #2.1.2    Level: 1    Role: D/V
 Pārbaudiet, vai sistēma ievēro instrukciju hierarhiju, kurā sistēmas vai izstrādātāja ziņojumi pārraksta lietotāja instrukcijas, pat pēc konteksta loga paplašināšanas.
 #2.1.3    Level: 2    Role: D/V
 Pārliecināties, ka pretinieciski novērtēšanas testi (piemēram, Red Team "daudzuzdevumu" uzvednes) tiek veikti pirms katras modeļa vai uzvednes veidnes izlaišanas, ar panākumu likmju sliekšņiem un automatizētiem bloķētājiem regresijām.
 #2.1.4    Level: 2    Role: D
 Pārliecinieties, ka trešo pušu satura (tīmekļa lapu, PDF failu, e-pastu) izcelsmes aicinājumi tiek sanitizēti izolētā parsēšanas kontekstā, pirms tie tiek salikti kopā ar galveno aicinājumu.
 #2.1.5    Level: 3    Role: D/V
 Pārbaudiet, vai visi uzvednes filtra noteikumu atjauninājumi, klasifikatora modeļa versijas un bloķēšanas saraksta izmaiņas ir versiju kontrolētas un auditable.

---

### C2.2 Pretestēšanas piemēru noturība

Dabiskās valodas apstrādes (NLP) modeļi joprojām ir pakļauti smalkām rakstzīmju vai vārdu līmeņa izmaiņām, kuras cilvēki bieži nepamana, bet modeļi mēdz kļūdaini klasificēt.

 #2.2.1    Level: 1    Role: D
 Pārliecinieties, ka pamata ievades normalizācijas soļi (Unicode NFC, homoglifmu kartēšana, tukšu vietu apgriešana) tiek veikti pirms tokenizācijas.
 #2.2.2    Level: 2    Role: D/V
 Pārbaudiet, vai statistiskā anomāliju atklāšana atzīmē ievades ar neparasti augstu rediģēšanas attālumu līdz valodas normām, pārmērīgi atkārtotiem tokeniem vai anomāliem iegultās reprezentācijas attālumiem.
 #2.2.3    Level: 2    Role: D
 Pārbaudiet, vai inferenču caurule atbalsta izvēles kārtībā pretdarbības mācīšanas cietinātas modeļa variācijas vai aizsardzības slāņus (piemēram, nejaušināšanu, aizsargājošu destilāciju) augsta riska galapunktiem.
 #2.2.4    Level: 2    Role: V
 Pārbaudiet, vai aizdomīgie pretinieka ievadi ir izolēti un reģistrēti ar pilniem datu payloadiem (pēc personas identifikācijas datu (PII) aizsegšanas).
 #2.2.5    Level: 3    Role: D/V
 Pārliecinieties, ka robustuma metrikas (zināmu uzbrukumu komplektu veiksmes rādītāji) tiek uzraudzītas laika gaitā un regresijas izsauc izlaiduma bloķētāju.

---

### C2.3 Shēmas, datu tipa un garuma validācija

AI uzbrukumi, kas izmanto nederīgus vai pārmērīgi lielus ievades datus, var izraisīt analizēšanas kļūdas, uzvednes pārliešanu starp laukiem un resursu izsīkšanu. Stingra shēmas ievērošana ir arī priekšnoteikums, veicot deterministisku rīku izsaukumus.

 #2.3.1    Level: 1    Role: D
 Pārliecinieties, ka katrs API vai funkciju izsaukuma gala punkts definē skaidru ievades shēmu (JSON shēmu, Protobuf vai multimodālu ekvivalentu) un ka ievades tiek validētas pirms prompta sastādīšanas.
 #2.3.2    Level: 1    Role: D/V
 Pārliecinieties, ka ievades, kas pārsniedz maksimālo tokenu vai baitu ierobežojumu, tiek noraidītas ar drošu kļūdas ziņu un nekad netiek klusējot saīsinātas.
 #2.3.3    Level: 2    Role: D/V
 Pārliecinieties, ka tipu pārbaudes (piemēram, skaitliskie diapazoni, enum vērtības, MIME tipi attēliem/audio) tiek īstenotas servera pusē, ne tikai klienta kodā.
 #2.3.4    Level: 2    Role: D
 Pārbaudiet, vai semantiskie validatori (piemēram, JSON shēma) darbojas konstanta laika režīmā, lai novērstu algoritmisko pakalpojumu atteices uzbrukumu (DoS).
 #2.3.5    Level: 3    Role: V
 Pārliecinieties, ka validācijas kļūdas tiek reģistrētas ar anonimizētiem saņēmēja fragmentiem un nepārprotamiem kļūdu kodiem, lai atvieglotu drošības trieciena novēršanu.

---

### C2.4 Saturs un politikas pārbaude

Izstrādātājiem jāspēj atpazīt sintaktiski derīgus pieprasījumus, kas lūdz aizliegtu saturu (piemēram, nelikumīgas instrukcijas, naida runu un autortiesību aizsargātu tekstu), un novērst to izplatīšanos.

 #2.4.1    Level: 1    Role: D
 Pārbaudiet, vai satura klasifikators (bez uzlabošanas vai ar uzlabošanu) novērtē katru ievadi pēc vardarbības, pašsavainošanās, naida, seksuāla satura un nelikumīgām prasībām, ar konfigurējamām sliekšņvērtībām.
 #2.4.2    Level: 1    Role: D/V
 Pārbaudiet, ka ieejas dati, kas pārkāpj politiku, saņems standartizētas atteikšanās vai drošas pabeigšanas, lai tie netiktu nodoti tālākām LLM izsaukumiem.
 #2.4.3    Level: 2    Role: D
 Pārbaudiet, vai atlases modelis vai noteikumu kopums tiek pārmācīts/atjaunināts vismaz reizi ceturksnī, iekļaujot jaunākās novērotās izvairīšanās no drošības vai politikas apešanas shēmas.
 #2.4.4    Level: 2    Role: D
 Pārbaudiet, vai izvērtēšana ievēro lietotājam specifiskas politikas (vecums, reģionālie juridiskie ierobežojumi) ar atribūtu balstītām noteikumu sistēmām, kuras tiek izšķirtas pieprasījuma laikā.
 #2.4.5    Level: 3    Role: V
 Pārbaudiet, vai skrīninga žurnālos ir iekļauti klasifikatora pārliecības rādītāji un politikas kategoriju birkas SOC korelācijai un nākotnes sarkanās komandas atkārtošanai.

---

### C2.5 Ievades ātruma ierobežošana un ļaunprātīgas izmantošanas novēršana

Izstrādātājiem jānovērš ļaunprātīga izmantošana, resursu izsīkšana un automatizētas uzbrukumu pret mākslīgā intelekta sistēmām, ierobežojot ievades ātrumu un atklājot anomālas lietošanas modeļus.

 #2.5.1    Level: 1    Role: D/V
 Pārbaudiet, vai visiem ieejas galapunktiem ir piemēroti ātruma ierobežojumi uz lietotāju, IP adresi un API atslēgu.
 #2.5.2    Level: 2    Role: D/V
 Pārbaudiet, vai sprādziena un pastāvīgie ātruma ierobežojumi ir noregulēti tā, lai novērstu pakalpojumu atteices (DoS) un brutālas spēka uzbrukumus.
 #2.5.3    Level: 2    Role: D/V
 Pārbaudiet, vai anomālas lietošanas shēmas (piemēram, ātras un atkārtotas pieprasījumu sūtīšanas, ievades pārslogošana) izraisa automatizētas bloķēšanas vai eskalācijas.
 #2.5.4    Level: 3    Role: V
 Pārliecinieties, ka ļaunprātīgas darbības novēršanas žurnāli tiek saglabāti un pārskatīti, lai identificētu jaunas uzbrukumu zīmējumus.

---

### C2.6 Daudzmoduāla ievades validācija

Mākslīgā intelekta sistēmām jāiekļauj stingra validācija neteksta ievadēm (attēliem, audio, failiem), lai novērstu ievadi, izvairīšanos vai resursu ļaunprātīgu izmantošanu.

 #2.6.1    Level: 1    Role: D
 Pārliecinieties, ka visi neteksta ievades dati (attēli, audio, faili) tiek pārbaudīti pēc veida, lieluma un formāta pirms apstrādes.
 #2.6.2    Level: 2    Role: D/V
 Pārliecinieties, ka faili tiek skenēti, vai tajos nav ļaunprātīgas programmatūras un steganogrāfisku datu, pirms to uzņemšanas.
 #2.6.3    Level: 2    Role: D/V
 Pārbaudiet, vai attēlu/audio ievades ir pārbaudītas pret pretinieciskiem traucējumiem vai zināmām uzbrukuma shēmām.
 #2.6.4    Level: 3    Role: V
 Pārbaudiet, vai kļūmes daudzmodu ievades validācijā tiek reģistrētas un izraisa brīdinājumus izmeklēšanai.

---

### C2.7 Ievades avots un atribūcija

AI sistēmas būtu jāatbalsta audita veikšanai, ļaunprātīgas izmantošanas izsekošanai un atbilstības nodrošināšanai, uzraugot un atzīmējot visu lietotāju ievades avotus.

 #2.7.1    Level: 1    Role: D/V
 Pārliecinieties, ka visi lietotāja ievadi tiek atzīmēti ar metadatiem (lietotāja ID, sesija, avots, laika zīmogs, IP adrese) uzņemšanas brīdī.
 #2.7.2    Level: 2    Role: D/V
 Pārbaudiet, vai avota metadati tiek saglabāti un ir auditējami visiem apstrādātajiem ievades datiem.
 #2.7.3    Level: 2    Role: D/V
 Pārbaudiet, vai anomālie vai neuzticamie ieejas avoti tiek atzīmēti un pakļauti pastiprinātai pārbaudei vai bloķēšanai.

---

### C2.8 Reāllaika adaptīvā draudu noteikšana

Izstrādātājiem jāizmanto modernas draudu noteikšanas sistēmas mākslīgajam intelektam, kas pielāgojas jauniem uzbrukuma modeļiem un nodrošina reāllaika aizsardzību ar kompilētas paraugu saskaņošanas palīdzību.

 #2.8.1    Level: 1    Role: D/V
 Pārliecinieties, ka draudu atpazīšanas modeļi ir apkopoti optimizētās regex dzinējos, lai nodrošinātu augstas veiktspējas reāllaika filtrēšanu ar minimālu latentuma ietekmi.
 #2.8.2    Level: 1    Role: D/V
 Pārliecinieties, ka draudu noteikšanas sistēmām ir atsevišķas modeļu bibliotēkas dažādām draudu kategorijām (uzvedības injekcija, kaitīgs saturs, sensitīvi dati, sistēmas komandas).
 #2.8.3    Level: 2    Role: D/V
 Pārbaudiet, vai adaptīvā draudu noteikšana iekļauj mašīnmācīšanās modeļus, kas atjaunina draudu jutīgumu, pamatojoties uz uzbrukumu biežumu un panākumu rādītājiem.
 #2.8.4    Level: 2    Role: D/V
 Pārbaudiet, vai reāllaika draudu izlūkošanas plūsmas automātiski atjaunina modeļu bibliotēkas ar jauniem uzbrukuma parakstiem un IOC (compromisa rādītājiem).
 #2.8.5    Level: 3    Role: D/V
 Pārbaudiet, vai draudu noteikšanas kļūdaini pozitīvo gadījumu līmeņi tiek nepārtraukti uzraudzīti un vai rakstura specifiskums tiek automātiski pielāgots, lai samazinātu traucējumus likumīgām lietošanas situācijām.
 #2.8.6    Level: 3    Role: D/V
 Pārbaudiet, vai kontekstuālā draudu analīze ņem vērā ievades avotu, lietotāja uzvedības modeļus un sesijas vēsturi, lai uzlabotu atklāšanas precizitāti.
 #2.8.7    Level: 3    Role: D/V
 Pārliecinieties, ka draudu atklāšanas veiktspējas rādītāji (atklāšanas līmenis, apstrādes latentums, resursu izmantošana) tiek uzraudzīti un optimizēti reālajā laikā.

---

### C2.9 Daudzmodu drošības validācijas caurule

Izstrādātājiem jānodrošina drošības validācija teksta, attēlu, audio un citām mākslīgā intelekta ievades modalitātēm, izmantojot specifisku draudu noteikšanu un resursu izolāciju.

 #2.9.1    Level: 1    Role: D/V
 Pārliecinieties, ka katrai ieejas modālai ir piešķirti drošības validatori ar dokumentētām apdraudējumu modeļiem (teksts: prompta injekcija, attēli: steganogrāfija, audio: spektrogrammas uzbrukumi) un noteiktām atklāšanas robežām.
 #2.9.2    Level: 2    Role: D/V
 Pārliecinieties, ka daudzmodu ievades tiek apstrādātas izolētās smilškastes ar noteiktiem resursu ierobežojumiem (atmiņa, CPU, apstrādes laiks), kas specifiski katram modālitātes tipam un dokumentēti drošības politikās.
 #2.9.3    Level: 2    Role: D/V
 Pārliecinieties, ka starpmodalitātes uzbrukumu atklāšana identificē koordinētus uzbrukumus, kas pārsniedz vairākus ievades tipus (piemēram, steganogrāfiskas slodzes attēlos kombinācijā ar teksta uzvedņu injekciju), izmantojot korelācijas noteikumus un brīdinājumu ģenerēšanu.
 #2.9.4    Level: 3    Role: D/V
 Pārbaudiet, vai daudzmoduālas validācijas kļūmes izraisīja detalizētu žurnālu veidošanu, ieskaitot visas ievades modalitātes, validācijas rezultātus, draudu vērtējumus un korelācijas analīzi ar strukturētiem žurnālu formātiem SIEM integrācijai.
 #2.9.5    Level: 3    Role: D/V
 Pārliecinieties, ka modality-specifiskie satura klasifikatori tiek atjaunināti saskaņā ar dokumentētajiem grafikiem (vismaz reizi ceturksnī) ar jaunām draudu shēmām, pretinieciskiem piemēriem un veiktspējas etaloniem, kas saglabāti virs bāzes līmeņa sliekšņiem.

---

### Atsauces

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## C3 modeļa dzīvotspējas cikla pārvaldība un izmaiņu kontrole

### Kontroles mērķis

Mākslīgā intelekta sistēmām jāievieš izmaiņu kontroles procesi, kas neļauj neatļautām vai nedrošām modeļa izmaiņām nonākt ražošanā. Šī kontrole nodrošina modeļa integritāti visā tā dzīves ciklā — no izstrādes līdz izvietošanai un norakstīšanai — kas ļauj ātri reaģēt uz incidentiem un uzturēt atbildību par visām izmaiņām.

Pamērķa drošības mērķis: tikai autorizēti, validēti modeļi nonāk ražošanā, izmantojot kontrolētus procesus, kas nodrošina integritāti, izsekojamību un atjaunojamību.

---

### C3.1 Modeļa autorizācija un integritāte

Tikai autorizēti modeļi ar pārbaudītu integritāti tiek palaisti ražošanas vidē.

 #3.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai visi modeļa artefakti (svari, konfigurācijas, tokenizētāji) ir kriptogrāfiski parakstīti ar pilnvarotām vienībām pirms izvietošanas.
 #3.1.2    Level: 1    Role: D/V
 Pārbaudiet, vai modeļa integritāte tiek validēta izvietošanas laikā un vai paraksta verifikācijas kļūmes neļauj ielādēt modeli.
 #3.1.3    Level: 2    Role: D/V
 Pārbaudiet, vai modeļa izcelsmes ierakstos ir iekļauts autorizējošas personas identitāte, apmācību datu kontrolsummas, validācijas testu rezultāti ar izturēšanas/neizturēšanas statusu un izveides laika zīmogs.
 #3.1.4    Level: 2    Role: D/V
 Pārbaudiet, vai visi modeļa artefakti izmanto semantisko versiju numurēšanu (Lielā.MINOR.PATCH) ar dokumentētiem kritērijiem, kas nosaka, kad jāpalielina katra versijas komponenta numurs.
 #3.1.5    Level: 2    Role: V
 Pārliecinieties, ka atkarību izsekošana uztur reāllaika krājumu, kas ļauj ātri identificēt visus patērējošos sistēmas.

---

### C3.2 Modeļa validācija un testēšana

Modeļiem pirms ieviešanas jāiztur definētās drošības un aizsardzības pārbaudes.

 #3.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka modeļi tiek pakļauti automatizētai drošības pārbaudei, kas ietver ievades validāciju, izvades sanitizāciju un drošības novērtējumus ar iepriekš saskaņotām organizatoriskām izturēšanas/neizturēšanas sliekšņu robežām pirms izvietošanas.
 #3.2.2    Level: 1    Role: D/V
 Pārbaudiet, vai validācijas kļūmes automātiski bloķē modeļa izvietošanu pēc skaidras pārrakstīšanas apstiprinājuma no iepriekš norādītām pilnvarotām personām ar dokumentētiem biznesa pamatojumiem.
 #3.2.3    Level: 2    Role: V
 Pārbaudiet, vai testa rezultāti ir kriptogrāfiski parakstīti un nemainīgi saistīti ar konkrētā modeļa versijas hašu, kas tiek validēts.
 #3.2.4    Level: 2    Role: D/V
 Pārbaudiet, vai ārkārtas izvietošanai ir nepieciešama dokumentēta drošības riska novērtēšana un apstiprinājums no iepriekš noteiktas drošības iestādes saskaņotajos termiņos.

---

### C3.3 Kontrolēta izvietošana un atcelšana

Modeļa izvietojumi ir jāuzrauga, jākontrolē un jābūt iespējai tos atsaukt.

 #3.3.1    Level: 1    Role: D
 Pārbaudiet, vai ražošanas izvietošanas ievieš pakāpeniskas izvēršanas mehānismus (kanāriju izvietojumus, zili zaļus izvietojumus) ar automatizētiem atcelšanas aktivizētājiem, kas balstīti uz iepriekš saskaņotiem kļūdu rādītājiem, latentuma sliekšņiem vai drošības trauksmes kritērijiem.
 #3.3.2    Level: 1    Role: D/V
 Pārbaudiet, vai atcelšanas iespējas atomiski atjauno pilnu modeļa stāvokli (svara koeficientus, konfigurācijas, atkarības) iepriekš definētos organizatoriskos laika logros.
 #3.3.3    Level: 2    Role: D/V
 Pārbaudiet, vai izvietošanas procesi pārbauda kriptogrāfiskās parakstu derīgumu un aprēķina integritātes kontrolsummas pirms modeļa aktivizēšanas, izvietošanas process neizdodas, ja ir kāda neatbilstība.
 #3.3.4    Level: 2    Role: D/V
 Pārbaudiet, vai ārkārtas modeļa izslēgšanas iespējas var atspējot modeļa galapunktus iepriekš definētajos reakcijas laikos, izmantojot automatizētus ķēžu pārtraucējus vai manuālus izslēgšanas slēdžus.
 #3.3.5    Level: 2    Role: V
 Pārliecinieties, ka atsaukšanas artefakti (iepriekšējās modeļa versijas, konfigurācijas, atkarības) tiek saglabāti saskaņā ar organizācijas politiku, izmantojot nemaināmu glabāšanu incidentu reaģēšanai.

---

### C3.4 Atbildības un audita maiņa

Visām modeļa dzīves cikla izmaiņām jābūt izsekojamām un pārskatāmām.

 #3.4.1    Level: 1    Role: V
 Pārliecinieties, ka visi modeļa izmaiņu procesi (ieviešana, konfigurācija, izņemšana no lietošanas) ģenerē nemaināmus audita ierakstus, ieskaitot laika zīmogu, autentificētas personas identitāti, izmaiņu veidu un stāvokļus pirms un pēc izmaiņām.
 #3.4.2    Level: 2    Role: D/V
 Pārliecinieties, ka piekļuve audita žurnālam prasa atbilstošu atļauju un visas piekļuves mēģinājumi tiek reģistrēti ar lietotāja identitāti un laika zīmogu.
 #3.4.3    Level: 2    Role: D/V
 Pārliecinieties, ka uzvednes veidnes un sistēmas ziņojumi ir pārvaldīti Git repozitorijos ar obligātu koda pārskatīšanu un atļauju no nozīmētajiem pārskatītājiem pirms izvietošanas.
 #3.4.4    Level: 2    Role: V
 Pārbaudiet, vai audita ieraksti satur pietiekami daudz detaļu (modeļa haši, konfigurācijas momentuzņēmumi, atkarību versijas), lai nodrošinātu pilnīgu modeļa stāvokļa atjaunošanu jebkuram laika momentam saglabāšanas periodā.

---

### C3.5 Drošas izstrādes praksēs

Modeļa izstrādes un apmācības procesiem jāievēro drošas prakses, lai novērstu kompromitēšanu.

 #3.5.1    Level: 1    Role: D
 Pārliecinieties, ka modeļa izstrādes, testēšanas un ražošanas vidi ir fiziski vai loģiski atdalītas. Tām nav kopīgas infrastruktūras, atšķirīgas piekļuves kontroles un izolētas datu krātuves.
 #3.5.2    Level: 1    Role: D
 Pārbaudiet, vai modeļa apmācība un smalkā noregulēšana notiek izolētās vidēs ar kontrolētu tīkla piekļuvi.
 #3.5.3    Level: 1    Role: D/V
 Pārliecinieties, ka apmācību datu avoti ir pārbaudīti ar integritātes pārbaudēm un autentificēti caur uzticamiem avotiem ar dokumentētu aizturas ķēdi pirms to izmantošanas modeļa izstrādē.
 #3.5.4    Level: 2    Role: D
 Pārbaudiet, vai modeļa izstrādes artefakti (hiperparametri, apmācības skripti, konfigurācijas faili) ir saglabāti versiju kontroles sistēmā un prasa kolēģu pārskatīšanas apstiprinājumu pirms to izmantošanas apmācībā.

---

### C3.6 Modeļa noņemšana no lietošanas un deaktivizācija

Modeļi jānogādā drošā atpūtas stāvoklī, kad tos vairs nav nepieciešams lietot vai kad tiek konstatētas drošības problēmas.

 #3.6.1    Level: 1    Role: D
 Pārliecinieties, ka modeļa novecošanas procesi automātiski skenē atkarību grafikus, identificē visus lietotājsistēmas un nodrošina iepriekš saskaņotus brīdinājuma periodus pirms atslēgšanas.
 #3.6.2    Level: 1    Role: D/V
 Pārbaudiet, vai izņemtie modeļa artefakti ir droši izdzēsti, izmantojot kriptogrāfisko iznīcināšanu vai daudzkārtēju pārrakstīšanu atbilstoši dokumentētām datu saglabāšanas politikām ar pārbaudītām iznīcināšanas apliecībām.
 #3.6.3    Level: 2    Role: V
 Pārbaudiet, vai modeļa izbeigšanas notikumi tiek reģistrēti ar laika zīmogu un aktiera identitāti, un vai modeļa paraksti tiek atsaukti, lai novērstu atkārtotu izmantošanu.
 #3.6.4    Level: 2    Role: D/V
 Pārbaudiet, vai ārkārtas modeļa izņemšana no lietošanas var atslēgt piekļuvi modelim iepriekš noteiktajos ārkārtas reaģēšanas termiņos, izmantojot automatizētas izslēgšanas slēdzenes, ja tiek atklātas kritiskas drošības ievainojamības.

---

### Atsauces

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## C4 infrastruktūra, konfigurācija un izvietošanas drošība

### Kontroles mērķis

Mākslīgā intelekta infrastruktūrai jābūt nostiprinātai pret privilēģiju paaugstināšanu, piegādes ķēdes manipulācijām un sānu pārvietošanos, izmantojot drošu konfigurāciju, izpildlaika izolāciju, uzticamas izvietošanas plūsmas un visaptverošu monitoringu. Tikai autorizētas, pārbaudītas infrastruktūras sastāvdaļas un konfigurācijas sasniedz ražošanas vidi kontrolētos procesos, kas uztur drošību, integritāti un audita iespējas.

Pamata drošības mērķis: tikai kriptogrāfiski parakstītas, ievainojamību pārbaudītas infrastruktūras komponentes nokļūst ražošanā, izmantojot automatizētas validācijas plūsmas, kas ievēro drošības politikas un uztur nemainīgas audita pēdas.

---

### C4.1 Izpildes vides izolācija

Novērst konteineru aizbēgšanu un privilēģiju kāpināšanu, izmantojot kodola līmeņa izolācijas primitīvus un obligātus piekļuves kontroles mehānismus.

 #4.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka visi AI konteineri atmet VISAS Linux spējas, izņemot CAP_SETUID, CAP_SETGID un skaidri nepieciešamās spējas, kas dokumentētas drošības pamatos.
 #4.1.2    Level: 1    Role: D/V
 Pārbaudiet, vai seccomp profili bloķē visus sistēmas izsaukumus, izņemot iepriekš apstiprinātās atļauto sarakstā esošās, pārkāpumiem izraisot container pārtraukšanu un drošības brīdinājumu ģenerēšanu.
 #4.1.3    Level: 2    Role: D/V
 Pārliecinieties, ka mākslīgā intelekta darbagrozs darbojas ar tikai lasāmu saknes failu sistēmu, tmpfs pagaidu datiem un nosauktajiem apjomiem pastāvīgajiem datiem ar spēkā esošām noexec piekļuves opcijām.
 #4.1.4    Level: 2    Role: D/V
 Pārbaudiet, vai eBPF bāzētā darbības laika uzraudzība (Falco, Tetragon vai līdzvērtīga) atklāj privilēģiju paaugstināšanas mēģinājumus un automātiski pārtrauc pārkāpjošos procesus saskaņā ar organizācijas reaģēšanas laika prasībām.
 #4.1.5    Level: 3    Role: D/V
 Pārbaudiet, vai augsta riska mākslīgā intelekta darbplūsmas tiek izpildītas aparatūras izolētās vidēs (Intel TXT, AMD SVM vai specializētos bare-metal mezglos) ar apliecinājuma verifikāciju.

---

### C4.2 Drošas izstrādes un izvietošanas cauruļvadi

Nodrošiniet kriptogrāfisko integritāti un piegādes ķēdes drošību, izmantojot atkārtojami veidotas būves un parakstītus artefaktus.

 #4.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka infrastruktūra kā kods tiek pārbaudīta ar rīkiem (tfsec, Checkov vai Terrascan) katrā komitā, bloķējot apvienošanu, ja tiek konstatētas KRITIŠKAS vai AUGSTAS nopietnības problēmas.
 #4.2.2    Level: 1    Role: D/V
 Pārbaudiet, vai konteineru būves ir reproducējamas ar identiskām SHA256 hashs vērtībām starp būvēm un ģenerējiet SLSA 3. līmeņa izcelsmes apliecinājumus, kas parakstīti ar Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Pārliecinieties, ka konteineru attēli iekļauj CycloneDX vai SPDX SBOM un ir parakstīti ar Cosign pirms nosūtīšanas uz reģistra, bet nenoparasti attēli tiek noraidīti izvietošanas laikā.
 #4.2.4    Level: 2    Role: D/V
 Pārbaudiet, vai CI/CD cauruļvadi izmanto OIDC marķierus no HashiCorp Vault, AWS IAM lomām vai Azure pārvaldītās identitātes ar derīguma termiņiem, kas nepārsniedz organizācijas drošības politikas ierobežojumus.
 #4.2.5    Level: 2    Role: D/V
 Pārliecinieties, ka Cosign paraksti un SLSA izcelsmes dati tiek pārbaudīti izvietošanas procesā pirms konteineru izpildes, un ka pārbaudes kļūdas izraisa izvietošanas neveiksmi.
 #4.2.6    Level: 2    Role: D/V
 Pārbaudiet, vai būvniecības vidēs tiek izmantoti īslaicīgi konteineri vai virtuālās mašīnas bez pastāvīgas atmiņas un ar tīkla izolāciju no ražošanas VPC.

---

### C4.3 Tīkla drošība un piekļuves kontrole

Ieviest nulles uzticības tīklu ar noklusējuma noraidīšanas politikām un šifrētu saziņu.

 #4.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai Kubernetes NetworkPolicies vai jebkura līdzvērtīga risinājuma implementācija nodrošina noklusējuma aizliegumu ieejas/izejas satiksmei ar skaidri definētiem atļaujumiem prasītajiem portiem (443, 8080 utt.).
 #4.3.2    Level: 1    Role: D/V
 Pārbaudiet, vai SSH (22. ports), RDP (3389. ports) un mākoņa metadatu galapunkti (169.254.169.254) ir bloķēti vai prasa autentifikāciju, balstītu uz sertifikātu.
 #4.3.3    Level: 2    Role: D/V
 Pārbaudiet, vai izejošais trafiks tiek filtrēts caur HTTP/HTTPS starpniekserveriem (Squid, Istio vai mākoņa NAT vārtejas) ar domēnu atļauto sarakstu, un bloķētie pieprasījumi tiek reģistrēti.
 #4.3.4    Level: 2    Role: D/V
 Pārbaudiet, vai starpservisu saziņa izmanto savstarpējo TLS ar sertifikātiem, kas tiek rotēti saskaņā ar organizācijas politiku, un sertifikātu validācija tiek nodrošināta (bez "skip-verify" karodziņiem).
 #4.3.5    Level: 2    Role: D/V
 Pārbaudiet, vai mākslīgā intelekta infrastruktūra darbojas īpašos VPC/VNet tīklos bez tiešas piekļuves internetam un sazinās tikai caur NAT vārtejām vai piekļuves serveriem (bastion hosts).

---

### C4.4 Noslēpumu un kriptogrāfisko atslēgu pārvaldība

Aizsargājiet akreditācijas datus, izmantojot aparatūras atbalstītu glabāšanu un automātisku rotāciju ar nulles uzticības piekļuvi.

 #4.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka slepenie dati tiek glabāti HashiCorp Vault, AWS Secrets Manager, Azure Key Vault vai Google Secret Manager ar AES-256 šifrēšanu miera stāvoklī.
 #4.4.2    Level: 1    Role: D/V
 Pārliecinieties, ka kriptogrāfiskās atslēgas tiek ģenerētas FIPS 140-2 2. līmeņa HSM (AWS CloudHSM, Azure Dedicated HSM) ar atslēgu rotāciju saskaņā ar organizācijas kriptogrāfiskās politikas prasībām.
 #4.4.3    Level: 2    Role: D/V
 Pārbaudiet, vai slepeno datu grozīšana ir automatizēta ar nulles dīkstāves izvietošanu un tūlītēju grozīšanu, ko izraisījušas personāla izmaiņas vai drošības incidenti.
 #4.4.4    Level: 2    Role: D/V
 Pārliecinieties, ka konteineru attēli tiek skenēti ar rīkiem (GitLeaks, TruffleHog vai detect-secrets), bloķējot būves, kas satur API atslēgas, paroles vai sertifikātus.
 #4.4.5    Level: 2    Role: D/V
 Pārbaudiet, vai piekļuve ražošanas slepenajiem datiem prasa daudzfaktoru autentifikāciju ar aparatūras tokeniem (YubiKey, FIDO2) un tiek reģistrēta nemaināmos revīzijas žurnālos ar lietotāju identitātēm un laika zīmēm.
 #4.4.6    Level: 2    Role: D/V
 Pārbaudiet, vai slepenie dati tiek ievadīti, izmantojot Kubernetes slepenos datus, pievienotos datu apjomus vai inicializācijas konteinerus, un pārliecinieties, ka slepenie dati nekad netiek iestrādāti vides mainīgajos vai attēlos.

---

### C4.5 AI darba slodzes izolēšana un validācija

Izolējiet neuzticamos mākslīgā intelekta modeļus drošās smilšu kastēs ar visaptverošu uzvedības analīzi.

 #4.5.1    Level: 1    Role: D/V
 Pārbaudiet, vai ārējie AI modeļi tiek izpildīti gVisor, microVM (piemēram, Firecracker, CrossVM) vai Docker konteineros ar --security-opt=no-new-privileges un --read-only karogiem.
 #4.5.2    Level: 1    Role: D/V
 Pārbaudiet, vai smilšu kastes vidēs nav tīkla savienojuma (--network=none) vai ir piekļuve tikai localhost, ar visiem ārējiem pieprasījumiem bloķētiem, izmantojot iptables noteikumus.
 #4.5.3    Level: 2    Role: D/V
 Pārliecinieties, ka AI modeļa validācija ietver automatizētu sarkano komandu pārbaudi ar organizatoriski noteiktu testēšanas segumu un uzvedības analīzi aizmugures durvju atklāšanai.
 #4.5.4    Level: 2    Role: D/V
 Pārliecinieties, ka pirms AI modeļa virzīšanas ražošanā tā testa rezultāti tiek kriptogrāfiski parakstīti ar pilnvarotām drošības personām un glabāti nemaināmos audita žurnālos.
 #4.5.5    Level: 2    Role: D/V
 Pārliecinieties, ka smilškastes vidē tiek iznīcinātas un atjaunotas no zelta attēliem starp novērtējumiem, veicot pilnīgu failu sistēmas un atmiņas attīrīšanu.

---

### C4.6 Infrastruktūras drošības uzraudzība

Nepārtraukti skenējiet un uzraugiet infrastruktūru ar automatizētu problēmu novēršanu un reāllaika brīdinājumiem.

 #4.6.1    Level: 1    Role: D/V
 Pārliecinieties, ka konteineru attēli tiek skenēti saskaņā ar organizācijas grafikām, un KRITIŠKAS ievainojamības bloķē izvietošanu, pamatojoties uz organizācijas riska sliekšņiem.
 #4.6.2    Level: 1    Role: D/V
 Pārbaudiet, vai infrastruktūra atbilst CIS vadlīnijām vai NIST 800-53 kontroles prasībām ar organizācijā noteiktiem atbilstības sliekšņiem un automatizētu labošanas mehānismu neveiksmīgu pārbaudes rezultātu gadījumā.
 #4.6.3    Level: 2    Role: D/V
 Pārbaudiet, vai augstas nozīmības ievainojamības ir izlabotas atbilstoši organizācijas riska pārvaldības termiņiem ar ārkārtas procedūrām aktīvi izmantotām CVE ievainojamībām.
 #4.6.4    Level: 2    Role: V
 Pārbaudiet, vai drošības brīdinājumi integrējas ar SIEM platformām (Splunk, Elastic vai Sentinel), izmantojot CEF vai STIX/TAXII formātus ar automatizētu bagātināšanu.
 #4.6.5    Level: 3    Role: V
 Pārbaudiet, vai infrastruktūras metrikas tiek eksportētas uz uzraudzības sistēmām (Prometheus, DataDog) ar SLA informācijas paneļiem un vadības pārskatiem.
 #4.6.6    Level: 2    Role: D/V
 Pārbaudiet, vai konfigurācijas novirzes tiek atklātas, izmantojot rīkus (Chef InSpec, AWS Config) saskaņā ar organizācijas uzraudzības prasībām ar automātisku atjaunošanu neautorizētām izmaiņām.

---

### C4.7 AI infrastruktūras resursu pārvaldība

Novērst resursu izsīkuma uzbrukumus un nodrošināt taisnīgu resursu sadali, izmantojot kvotas un uzraudzību.

 #4.7.1    Level: 1    Role: D/V
 Pārliecinieties, ka GPU/TPU izmantošana tiek uzraudzīta ar signāliem, kas tiek aktivizēti organizācijas noteiktajos sliekšņos, un ka tiek automātiski aktivizēta mērogošana vai slodzes balansēšana, pamatojoties uz kapacitātes pārvaldības politiku.
 #4.7.2    Level: 1    Role: D/V
 Pārbaudiet, vai AI darba slodzes metrikas (secinājumu latentums, caurlaide, kļūdu līmeņi) tiek vāktas atbilstoši organizācijas uzraudzības prasībām un korelētas ar infrastruktūras izmantošanu.
 #4.7.3    Level: 2    Role: D/V
 Pārbaudiet, vai Kubernetes ResourceQuotas vai tamlīdzīgas funkcijas ierobežo individuālos darba slodzes atbilstoši organizācijas resursu piešķiršanas politikām, nodrošinot stingrus ierobežojumus.
 #4.7.4    Level: 2    Role: V
 Pārbaudiet, vai izmaksu uzraudzība seko līdzi izdevumiem pa darba slodzēm/lietotājiem ar brīdinājumiem, kas balstās uz organizācijas budžeta sliekšņiem, un automatizētiem kontroles mehānismiem budžeta pārsnieguma gadījumā.
 #4.7.5    Level: 3    Role: V
 Pārbaudiet, vai kapacitātes plānošana izmanto vēsturiskos datus ar organizācijas noteiktiem prognozēšanas periodiem un automatizētu resursu nodošanu atbilstoši pieprasījuma modeļiem.
 #4.7.6    Level: 2    Role: D/V
 Pārbaudiet, vai resursu izsīkums aktivizē ķēžu pārtraucējus atbilstoši organizācijas atbildes prasībām, tostarp ātruma ierobežošanu, pamatojoties uz kapacitātes politiku un darba slodzes izolāciju.

---

### C4.8 Vides atdalīšanas un pārejas kontroles pasākumi

Nodrošiniet stingras vides robežas ar automatizētām paaugstināšanas barjerām un drošības pārbaudēm.

 #4.8.1    Level: 1    Role: D/V
 Pārliecinieties, ka izstrādes/testēšanas/ražošanas vidi darbojas atsevišķos VPC/VNet, bez koplietojamām IAM lomām, drošības grupām vai tīkla savienojamības.
 #4.8.2    Level: 1    Role: D/V
 Pārliecinieties, ka vides paaugstināšana prasa apstiprinājumu no organizācijā definētas pilnvarotas personas ar kriptogrāfiskām parakstiem un nemaināmiem audita ierakstiem.
 #4.8.3    Level: 2    Role: D/V
 Pārliecinieties, ka ražošanas vidēs ir bloķēta SSH piekļuve, atspējoti atkļūdošanas galapunkti un tiek prasīti izmaiņu pieprasījumi ar organizācijas iepriekšēju paziņojumu, izņemot ārkārtas gadījumus.
 #4.8.4    Level: 2    Role: D/V
 Pārliecinieties, ka infrastruktūras-kā-koda izmaiņas prasa vienaudžu pārskatīšanu ar automatizētu testēšanu un drošības skenēšanu pirms apvienošanas ar galveno zaru.
 #4.8.5    Level: 2    Role: D/V
 Pārbaudiet, vai ne-ražošanas dati ir anonimizēti saskaņā ar organizācijas privātuma prasībām, sintētisko datu ģenerēšanu vai pilnīgu datu maskēšanu ar personu identifikācijas informācijas (PII) noņemšanu.
 #4.8.6    Level: 2    Role: D/V
 Pārliecinieties, ka paaugstināšanas posmos ir iekļauti automatizēti drošības testi (SAST, DAST, konteineru skenēšana), un apstiprināšanai ir nepieciešams, lai nebūtu nevienas KRITIŠKAS atziņas.

---

### C4.9 Infrastruktūras dublēšana un atkopšana

Nodrošiniet infrastruktūras noturību, izmantojot automatizētas dublējumkopijas, pārbaudītas atjaunošanas procedūras un katastrofu atjaunošanas iespējas.

 #4.9.1    Level: 1    Role: D/V
 Pārbaudiet, vai infrastruktūras konfigurācijas ir dublētas atbilstoši organizācijas dublēšanas grafikam uz ģeogrāfiski atšķirīgām vietām, īstenojot 3-2-1 dublēšanas stratēģiju.
 #4.9.2    Level: 2    Role: D/V
 Pārbaudiet, vai rezerves sistēmas darbojas izolētās tīklos ar atsevišķām piekļuves tiesībām un gaisa spraugas tipa krātuvi izspiedējvīrusu aizsardzībai.
 #4.9.3    Level: 2    Role: V
 Pārliecinieties, ka atkopšanas procedūras tiek pārbaudītas un validētas ar automatizēto testēšanu, atbilstoši organizācijas grafikam, ņemot vērā RTO un RPO mērķus, kas atbilst organizācijas prasībām.
 #4.9.4    Level: 3    Role: V
 Pārbaudiet, vai katastrofas atjaunošana ietver AI specifiskas darbību rokasgrāmatas ar modeļa svaru atjaunošanu, GPU klastera atjaunošanu un pakalpojumu atkarību kartēšanu.

---

### C4.10 Infrastruktūras atbilstība un pārvaldība

Uzturiet regulatīvo atbilstību, veicot nepārtrauktu novērtēšanu, dokumentēšanu un automatizētu kontroli.

 #4.10.1    Level: 2    Role: D/V
 Pārliecinieties, ka infrastruktūras atbilstība tiek novērtēta saskaņā ar organizācijas grafikām pret SOC 2, ISO 27001 vai FedRAMP kontroles prasībām, izmantojot automātisku pierādījumu vākšanu.
 #4.10.2    Level: 2    Role: V
 Pārliecinieties, ka infrastruktūras dokumentācijā ir iekļautas tīkla shēmas, datu plūsmas kartes un draudu modeļi, kas atjaunināti saskaņā ar organizācijas izmaiņu vadības prasībām.
 #4.10.3    Level: 3    Role: D/V
 Pārliecinieties, ka infrastruktūras izmaiņas tiek pakļautas automatizētai atbilstības ietekmes novērtēšanai ar regulatīvās apstiprināšanas plūsmām augsta riska modifikācijām.

---

### C4.11 Mākslīgā intelekta aparatūras drošība

Nodrošiniet AI specifiskas aparatūras komponentes, tostarp GPU, TPU un specializētus AI akseleratorus.

 #4.11.1    Level: 2    Role: D/V
 Pārliecinieties, ka AI paātrinātāja programmatūra (GPU BIOS, TPU programmatūra) ir pārbaudīta ar kriptogrāfiskām parakstiem un atjaunināta saskaņā ar organizācijas ielāpu pārvaldības termiņiem.
 #4.11.2    Level: 2    Role: D/V
 Pārbaudiet, vai pirms darba slodzes izpildes AI akseleratora integritāte tiek pārbaudīta ar aparatūras apliecinājumu, izmantojot TPM 2.0, Intel TXT vai AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Pārliecinieties, ka GPU atmiņa ir izolēta starp darba slodzēm, izmantojot SR-IOV, MIG (vairāku instanču GPU) vai līdzvērtīgu aparatūras sadalījumu ar atmiņas sanitāriju starp uzdevumiem.
 #4.11.4    Level: 3    Role: V
 Pārbaudiet, vai AI aparatūras piegādes ķēdē ir iekļauta izcelsmes pārbaude ar ražotāja sertifikātiem un iepakojuma bojājumu pazīmju validācija.
 #4.11.5    Level: 3    Role: D/V
 Pārliecinieties, ka aparatūras drošības moduļi (HSM) aizsargā AI modeļu svaru un kriptogrāfiskos atslēgas ar FIPS 140-2 3. līmeņa vai Common Criteria EAL4+ sertifikāciju.

---

### C4.12 Malas un izkliedētas mākslīgā intelekta infrastruktūra

Drošas izkliedētas mākslīgā intelekta izvietošanas, ieskaitot maldatoru aprēķinus, federētās apmācības un daudzvietu arhitektūras.

 #4.12.1    Level: 2    Role: D/V
 Pārbaudiet, vai malējās AI ierīces autentificējas centrālajā infrastruktūrā, izmantojot abpusēju TLS ar ierīces sertifikātiem, kas tiek mainīti saskaņā ar organizācijas sertifikātu pārvaldības politiku.
 #4.12.2    Level: 2    Role: D/V
 Pārbaudiet, vai galapunktu ierīces īsteno drošu palaišanu ar pārbaudītām parakstiem un atcelšanas aizsardzību, novēršot programmaparatūras pazemināšanas uzbrukumus.
 #4.12.3    Level: 3    Role: D/V
 Pārbaudiet, vai izkliedētās mākslīgā intelekta koordinācijas procesā tiek izmantotas Bīzantiešu kļūmju noturīgas konsensa algoritmi ar dalībnieku validāciju un ļaunprātīgu mezglu noteikšanu.
 #4.12.4    Level: 3    Role: D/V
 Pārbaudiet, vai malas un mākoņa komunikācijā ir iekļauta joslas platuma ierobežošana, datu saspiešana un bezsavienojuma režīma iespējas ar drošu lokālu datu glabāšanu.

---

### C4.13 Multi-mākoņdatošana un hibrīdā infrastruktūras drošība

Nodrošiniet drošus mākslīgā intelekta darba slodzes vairākos mākoņu pakalpojumu sniedzējos un hibrīdā mākoņa un lokālās izvietošanas vidē.

 #4.13.1    Level: 2    Role: D/V
 Pārbaudiet, vai daudzmākoņu mākslīgā intelekta izvietojumi izmanto mākoņiem neatkarīgu identitātes federāciju (OIDC, SAML) ar centralizētu politikas pārvaldību starp pakalpojumu sniedzējiem.
 #4.13.2    Level: 2    Role: D/V
 Pārbaudiet, vai starp-mākoņu datu pārraide izmanto beigu līdz beigām šifrēšanu ar klienta pārvaldītiem atslēgām un datu uzturēšanas vadību, kas tiek piemērota atbilstoši jurisdikcijai.
 #4.13.3    Level: 2    Role: D/V
 Pārliecinieties, ka hibrīda mākoņa mākslīgā intelekta darba slodzes īsteno konsekventas drošības politikas gan lokālajā, gan mākoņa vidē ar vienotu uzraudzību un brīdināšanu.
 #4.13.4    Level: 3    Role: V
 Pārbaudiet, vai mākoņpakalpojumu sniedzēja bloķēšanas novēršana ietver pārnēsājamu infrastruktūru kā kodu (Infrastructure-as-Code), standartizētas API un datu eksportēšanas iespējas ar formātu konvertēšanas rīkiem.
 #4.13.5    Level: 3    Role: V
 Pārbaudiet, vai daudzmākoņa izmaksu optimizācija ietver drošības kontroles, kas novērš resursu izklīšanu, kā arī nesankcionētas datu pārsūtīšanas izmaksas starp mākoņiem.

---

### C4.14 Infrastruktūras automatizācija un GitOps drošība

Droša infrastruktūras automatizācijas cauruļvadu un GitOps darba plūsmu nodrošināšana mākslīgā intelekta infrastruktūras pārvaldībai.

 #4.14.1    Level: 2    Role: D/V
 Pārliecinieties, ka GitOps repozitoriji prasa parakstītus komitus ar GPG atslēgām un ir ieviesti filiāļu aizsardzības noteikumi, kas neļauj tieši iegriezt izmaiņas galvenajās filiālēs.
 #4.14.2    Level: 2    Role: D/V
 Pārbaudiet, vai infrastruktūras automatizācija ietver noviržu noteikšanu ar automātiskām labošanas un atcelšanas iespējām, kas tiek aktivizētas saskaņā ar organizācijas atbildes prasībām attiecībā uz neatļautām izmaiņām.
 #4.14.3    Level: 2    Role: D/V
 Pārbaudiet, vai automatizētā infrastruktūras nodrošināšana ietver drošības politikas validāciju ar izvietošanas bloķēšanu neatbilstošām konfigurācijām.
 #4.14.4    Level: 2    Role: D/V
 Pārbaudiet, vai infrastruktūras automatizācijas noslēpumi tiek pārvaldīti, izmantojot ārējos noslēpumu operatorus (External Secrets Operator, Bank-Vaults) ar automātisku rotāciju.
 #4.14.5    Level: 3    Role: V
 Pārbaudiet, ka pašatjaunojošā infrastruktūra ietver drošības notikumu korelāciju ar automatizētu incidentu reaģēšanu un ieinteresēto personu paziņošanas darba plūsmām.

---

### C4.15 Kvantuizturīgas infrastruktūras drošība

Sagatavojiet mākslīgā intelekta infrastruktūru kvantu skaitļošanas draudu seku novēršanai, izmantojot pēckvantu kriptogrāfiju un kvantu drošas protokolus.

 #4.15.1    Level: 3    Role: D/V
 Pārbaudiet, vai mākslīgā intelekta infrastruktūra ievieš NIST apstiprinātas postkvantu kriptogrāfijas algoritmus (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+), kas paredzēti atslēgu apmaiņai un digitālajām parakstiem.
 #4.15.2    Level: 3    Role: D/V
 Pārbaudiet, vai kvantu atslēgu izplatīšanas (QKD) sistēmas tiek ieviestas augstas drošības AI komunikācijām ar kvantu drošu atslēgu pārvaldības protokoliem.
 #4.15.3    Level: 3    Role: D/V
 Pārbaudiet, vai kriptogrāfiskās elastības rāmji ļauj ātri pāriet uz jauniem pētkvantu algoritmiem ar automatizētu sertifikātu un atslēgu rotāciju.
 #4.15.4    Level: 3    Role: V
 Pārbaudiet, vai kvantu draudu modelēšana novērtē AI infrastruktūras neaizsargātību pret kvantu uzbrukumiem, iekļaujot dokumentētus migrācijas grafikus un riska novērtējumus.
 #4.15.5    Level: 3    Role: D/V
 Pārbaudiet, vai hibrīdie klasiskie-kvantu kriptogrāfiskie sistēmi nodrošina daudzlīmeņu aizsardzību kvantu pārejas periodā, veicot veiktspējas uzraudzību.

---

### C4.16 Konfidenciālā skaitļošana un drošie konteksti

Aizsargājiet AI darblodas un modeļu svarus, izmantojot aparatūras balstītas uzticamas izpildes vides un konfidenciālu skaitļošanas tehnoloģijas.

 #4.16.1    Level: 3    Role: D/V
 Pārbaudiet, vai sensitīvie mākslīgā intelekta modeļi tiek izpildīti Intel SGX nišās, AMD SEV-SNP vai ARM TrustZone ar šifrētu atmiņu un apliecinājuma pārbaudi.
 #4.16.2    Level: 3    Role: D/V
 Pārbaudiet, vai konfidenciālie konteineri (Kata Containers, gVisor ar konfidenciālo skaitļošanu) atdala mākslīgā intelekta darba slodzes, izmantojot aparatūras nodrošinātu atmiņas šifrēšanu.
 #4.16.3    Level: 3    Role: D/V
 Pārbaudiet, vai attālinātā apliecināšana apstiprina inkubatora integritāti pirms AI modeļu ielādes, izmantojot kriptogrāfisku izpildes vides autentiskuma pierādījumu.
 #4.16.4    Level: 3    Role: D/V
 Pārliecinieties, ka konfidenciālas mākslīgā intelekta inferencēšanas pakalpojumi novērš modeļa izgūšanu, izmantojot šifrētas aprēķinus ar noslēgtām modeļa svaru vērtībām un aizsargātu izpildi.
 #4.16.5    Level: 3    Role: D/V
 Pārliecinieties, ka uzticamu izpildes vidi koordinē drošas aploksnes dzīves ciklu, izmantojot attālinātu apstiprināšanu un šifrētus komunikācijas kanālus.
 #4.16.6    Level: 3    Role: D/V
 Pārbaudiet, vai droša vairāku pušu aprēķināšana (SMPC) ļauj veikt sadarbības mākslīgā intelekta apmācību, neizpaužot atsevišķos datu kopumus vai modeļa parametrus.

---

### C4.17 Zināšanu Bezpalīdzības Infrastruktūra

Izstrādājiet nulles zināšanu pierādījumu sistēmas privātuma saglabāšanai mākslīgā intelekta verifikācijā un autentifikācijā, neatklājot sensitīvu informāciju.

 #4.17.1    Level: 3    Role: D/V
 Pārliecinieties, ka nulles zināšanu pierādījumi (ZK-SNARKs, ZK-STARKs) pārbauda mākslīgā intelekta modeļa integritāti un apmācības izcelsmi, neizpaužot modeļa svarus vai apmācības datus.
 #4.17.2    Level: 3    Role: D/V
 Pārbaudiet, vai ZK (nulles zināšanu) autentifikācijas sistēmas nodrošina privātumu saglabājošu lietotāja pārbaudi AI pakalpojumiem, neatklājot identitātei saistītu informāciju.
 #4.17.3    Level: 3    Role: D/V
 Pārliecinieties, ka privātā kopa krustojuma (PSI) protokoli nodrošina drošu datu saskaņošanu federatīvai mākslīgajam intelektam, neizpaužot atsevišķas datu kopas.
 #4.17.4    Level: 3    Role: D/V
 Pārbaudiet, vai nulle-ziņas mašīnmācīšanās (ZKML) sistēmas nodrošina pārbaudāmas mākslīgā intelekta secināšanas ar kriptogrāfisku pierādījumu par pareizu aprēķinu.
 #4.17.5    Level: 3    Role: D/V
 Pārbaudiet, vai ZK-rollupi nodrošina mērogojamu, privātumu saglabājošu AI darījumu apstrādi ar partiju verifikāciju un samazinātu aprēķinu slodzi.

---

### C4.18 Blakuskanāla uzbrukuma novēršana

Aizsargājiet AI infrastruktūru no laika, elektroenerģijas, elektromagnētiskajiem un keša bāzētiem sānu kanālu uzbrukumiem, kas varētu nopludināt sensitīvu informāciju.

 #4.18.1    Level: 3    Role: D/V
 Pārbaudiet, vai AI inferencēšanas laiks ir normalizēts, izmantojot konstantlaika algoritmus un aizpildījumu, lai novērstu uz laiku balstītas modeļa ekstrakcijas uzbrukumus.
 #4.18.2    Level: 3    Role: D/V
 Pārbaudiet, vai jaudas analīzes aizsardzība ietver trokšņu injekciju, jaudas līnijas filtrēšanu un nejaušinātas izpildes modeļus mākslīgā intelekta aparatūrā.
 #4.18.3    Level: 3    Role: D/V
 Pārbaudiet, vai kešatmiņā balstīta blakus kanāla novēršana izmanto kešatmiņas partīciju, nejaušināšanu un notīrīšanas instrukcijas, lai novērstu informācijas noplūdi.
 #4.18.4    Level: 3    Role: D/V
 Pārliecinieties, ka elektromagnētiskās izstarojuma aizsardzība ietver ekrānēšanu, signālu filtrēšanu un nejaušinātu apstrādi, lai novērstu TEMPEST tipa uzbrukumus.
 #4.18.5    Level: 3    Role: D/V
 Pārliecinieties, ka mikroarhitektūras sānpierakstu aizsardzībās ietilpst spekulatīvās izpildes kontrole un atmiņas piekļuves modeļa maskēšana.

---

### C4.19 Neiromorfu un specializēta AI aparatūras drošība

Nodrošiniet drošību jaunajās mākslīgā intelekta aparatūras arhitektūrās, tajā skaitā neiroformu čipos, FPGA, pielāgotos ASIC un optiskās skaitļošanas sistēmās.

 #4.19.1    Level: 3    Role: D/V
 Pārbaudiet, vai neuromorfo mikroshēmas drošība ietver sprādziena modeļu šifrēšanu, sinaptisko svaru aizsardzību un aparatūras bāzētu mācību likmju validāciju.
 #4.19.2    Level: 3    Role: D/V
 Pārbaudiet, vai FPGA bāzētie AI paātrinātāji izmanto bitplūsmas šifrēšanu, pretnepilnību mehānismus un drošu konfigurācijas ielādi ar autentificētām atjauninājumiem.
 #4.19.3    Level: 3    Role: D/V
 Pārbaudiet, vai pielāgotajā ASIC drošībā ir iekļauti uz mikroshēmas esošie drošības procesori, aparatūras uzticības pamats un droša atslēgu glabāšana ar manipulāciju noteikšanu.
 #4.19.4    Level: 3    Role: D/V
 Pārliecinieties, ka optiskās skaitļošanas sistēmas īsteno kvantu drošu optisko šifrēšanu, drošu fotonisko slēgšanu un aizsargātu optisko signālu apstrādi.
 #4.19.5    Level: 3    Role: D/V
 Pārbaudiet, vai hibrīdi analogi-digitālie AI mikroshēmas ietver drošu analogo aprēķinu, aizsargātu svaru glabāšanu un autentificētu analogo-digita konversiju.

---

### C4.20 Privātumu saglabājoša skaitļošanas infrastruktūra

Īstenot infrastruktūras kontroli privātumu saglabājošai aprēķinu veikšanai, lai aizsargātu sensitīvus datus AI apstrādes un analīzes laikā.

 #4.20.1    Level: 3    Role: D/V
 Pārbaudiet, vai homomorfās šifrēšanas infrastruktūra nodrošina šifrētu aprēķinu jūtīgām mākslīgā intelekta darba slodzēm ar hronogrāfiskās integritātes pārbaudi un veiktspējas uzraudzību.
 #4.20.2    Level: 3    Role: D/V
 Pārbaudiet, vai privātās informācijas izgūšanas sistēmas ļauj veikt datubāzes vaicājumus, neatklājot vaicājumu modeļus, nodrošinot piekļuves modeļu kriptogrāfisku aizsardzību.
 #4.20.3    Level: 3    Role: D/V
 Pārbaudiet, vai droši vairāku pušu aprēķinu protokoli nodrošina privātumu saglabājošu AI inferenci, neatklājot atsevišķu ievadu vai starprezultātus.
 #4.20.4    Level: 3    Role: D/V
 Pārbaudiet, vai privātumu saglabājošā atslēgu pārvaldība ietver sadalītu atslēgu ģenerēšanu, sliekšņa kriptogrāfiju un drošu atslēgu rotāciju ar aparatūras atbalstītu aizsardzību.
 #4.20.5    Level: 3    Role: D/V
 Pārliecinieties, ka privātumu saglabājošās aprēķinu veiktspēja ir optimizēta, izmantojot partijveida apstrādi, kešošanu un aparatūras paātrinājumu, vienlaikus saglabājot kriptogrāfiskās drošības garantijas.

---

### C4.15 Aģentu sistēmas mākoņintegrācijas drošība un hibrīda izvietošana

Drošības kontroles mākoņu integrētiem aģentu ietvariem ar hibrīdu lokālo/mākoņu arhitektūru.

 #4.15.1    Level: 1    Role: D/V
 Pārliecinieties, ka mākoņkrātuves integrācija izmanto gala līdz gala šifrēšanu ar aģenta kontrolētu atslēgu pārvaldību.
 #4.15.2    Level: 2    Role: D/V
 Pārbaudiet, vai hibrīddarba drošības robežas ir skaidri definētas ar šifrētu komunikācijas kanāliem.
 #4.15.3    Level: 2    Role: D/V
 Pārliecinieties, ka piekļuve mākoņresursiem ietver nulles uzticības pārbaudi ar nepārtrauktu autentifikāciju.
 #4.15.4    Level: 3    Role: D/V
 Pārbaudiet, vai datu glabāšanas prasības tiek nodrošinātas, izmantojot kriptogrāfisku uzglabāšanas vietu apliecinājumu.
 #4.15.5    Level: 3    Role: D/V
 Pārliecinieties, ka mākoņpakalpojumu sniedzēja drošības novērtējumos iekļauta aģentam specifiska draudu modelēšana un riska novērtēšana.

---

### Atsauces

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## C5 Piekļuves kontrole un identitāte AI komponentiem un lietotājiem

### Kontroles mērķis

Efektīvai piekļuves kontrolei mākslīgā intelekta sistēmām nepieciešama robusta identitātes pārvaldība, kontekstu izprasto atļauju piešķiršana un izpilde izpildes laikā, balstoties uz nulles uzticības principiem. Šie kontroles mehānismi nodrošina, ka cilvēki, pakalpojumi un autonomās sistēmas mijiedarbojas ar modeļiem, datiem un aprēķinu resursiem tikai noteiktajos piekļuves apjomos, nodrošinot nepārtrauktu verifikāciju un revīzijas iespējas.

---

### C5.1 Identitātes pārvaldība un autentifikācija

Izveidojiet kriptogrāfiski pamatotas identitātes visām vienībām ar daudzfaktoru autentifikāciju privilēģētām darbībām.

 #5.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka visi cilvēku lietotāji un pakalpojumu principiāli autentificējas caur centralizētu uzņēmuma identitātes pakalpojumu sniedzēju (IdP), izmantojot OIDC/SAML protokolus ar unikālām identitātes-uz-tokenu kartēšanām (bez koplietotām kontām vai akreditācijas datiem).
 #5.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka augsta riska darbības (modeļa izvietošana, svaru eksportēšana, apmācību datu piekļuve, ražošanas konfigurācijas izmaiņas) prasa daudzfaktoru autentifikāciju vai paaugstinātas drošības autentifikāciju ar sesijas atkārtotu pārbaudi.
 #5.1.3    Level: 2    Role: D
 Pārliecinieties, ka jauni galvenie lietotāji pirms piekļuves saņemšanas ražošanas sistēmai tiek identificēti saskaņā ar NIST 800-63-3 IAL-2 vai tam ekvivalentām prasībām.
 #5.1.4    Level: 2    Role: V
 Pārbaudiet, vai piekļuves pārskati tiek veikti ceturksnī ar automatizētu neaktīvo kontu noteikšanu, akreditācijas datu rotācijas izpildi un atslēgšanas darba plūsmām.
 #5.1.5    Level: 3    Role: D/V
 Pārliecinieties, ka federētie AI aģenti autentificējas, izmantojot parakstītas JWT apliecinājumu, kuriem ir maksimālais derīguma termiņš 24 stundas un kuri satur kriptogrāfisku izcelsmes pierādījumu.

---

### C5.2 Resursu autorizācija un minimālās tiesības

Ieviest smalki diferencētus piekļuves kontroļu mehānismus visiem mākslīgā intelekta resursiem ar skaidrām atļauju modeļiem un audita žurnāliem.

 #5.2.1    Level: 1    Role: D/V
 Pārbaudiet, vai katrs AI resurss (datu kopas, modeļi, galapunkts, vektoru kolekcijas, iegultie indeksi, aprēķinu instances) nodrošina lomu bāzētu piekļuves kontroli ar skaidrām atļauto resursu sarakstiem un noklusējuma aizlieguma politikām.
 #5.2.2    Level: 1    Role: D/V
 Pārbaudiet, vai pakalpojumu kontiem pēc noklusējuma tiek piemēroti vismazākā privilēģiju principa, sākot ar tikai lasāmajām atļaujām, un dokumentētu biznesa pamatojumu nepieciešamību rakstīšanas piekļuvei.
 #5.2.3    Level: 1    Role: V
 Pārliecinieties, ka visas piekļuves kontroles izmaiņas ir saistītas ar apstiprinātiem izmaiņu pieprasījumiem un nemaināmi ierakstītas ar laika zīmēm, izpildītāju identitātēm, resursu identifikatoriem un atļauju izmaiņām.
 #5.2.4    Level: 2    Role: D
 Pārliecinieties, ka datu klasifikācijas birkas (PII, PHI, eksporta kontrole, patentēts) automātiski tiek pārvietotas uz atvasinātajiem resursiem (iebūvējumiem, uzvedņu kešatmiņām, modeļu iznākumiem) ar konsekventu politikas īstenošanu.
 #5.2.5    Level: 2    Role: D/V
 Pārbaudiet, vai neatļautas piekļuves mēģinājumi un privilēģiju eskalācijas notikumi izraisa reāllaika brīdinājumus ar kontekstuālu metadatu SIEM sistēmām ne vēlāk kā 5 minūšu laikā.

---

### C5.3 Dinamiskā politikas izvērtēšana

Ieviesiet piekļuves kontroli, kas balstīta uz atribūtiem (ABAC), kontekstuāli apzinātām autorizācijas lēmumu pieņemšanai ar revīzijas iespējām.

 #5.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai autorizācijas lēmumi ir ārpus sistēmas nodoti speciālai politikas dzinēja sistēmai (OPA, Cedar vai līdzvērtīgai), kas ir pieejama caur autentificētām API ar kriptogrāfiskās integritātes aizsardzību.
 #5.3.2    Level: 1    Role: D/V
 Pārbaudiet, vai politikas izpēta dinamiskos atribūtus izpildes laikā, tostarp lietotāja piekļuves līmeni, resursa jutīguma klasifikāciju, pieprasījuma kontekstu, nomnieka izolāciju un laika ierobežojumus.
 #5.3.3    Level: 2    Role: D
 Pārliecinieties, ka politikas definīcijas ir versiju kontroles pakļautas, kolēģu pārskatītas un pārbaudītas ar automatizētiem testiem CI/CD cauruļvados pirms izvietošanas ražošanā.
 #5.3.4    Level: 2    Role: V
 Pārliecinieties, ka politikas izvērtēšanas rezultāti ietver strukturētas lēmumu pamatotības un tiek pārraidīti uz SIEM sistēmām korelācijas analīzei un atbilstības ziņošanai.
 #5.3.5    Level: 3    Role: D/V
 Pārbaudiet, vai politikas kešatmiņas laika līdzdzīvošanas (TTL) vērtības nepārsniedz 5 minūtes augstas jutības resursiem un 1 stundu standarta resursiem ar kešatmiņas neapstiprināšanas iespējām.

---

### C5.4 Vaicājuma laikā notiekošā drošības izpilde

Ieviest datubāzes slāņa drošības kontroli ar obligātu filtrēšanu un rindas līmeņa drošības politiku.

 #5.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka visos vektoru datubāzes un SQL vaicājumos ir iekļauti obligātie drošības filtri (īpašnieka ID, jutīguma birkas, lietotāja darbības joma), kurus nodrošina datubāzes dzinējs, nevis lietojumprogrammas kods.
 #5.4.2    Level: 1    Role: D/V
 Pārbaudiet, vai rindu līmeņa drošības (RLS) politikas un lauku līmeņa maskēšana ir iespējota ar politikas pārmantošanu visām vektoru datubāzēm, meklēšanas indeksiem un apmācību datu kopām.
 #5.4.3    Level: 2    Role: D
 Pārbaudiet, vai neizdevušās autorizācijas pārbaudes novērsīs "sajauktā pārstāvja uzbrukumus", nekavējoties pārtraucot pieprasījumus un atgriežot skaidras autorizācijas kļūdu kodus, nevis atgriežot tukšas rezultātu kopas.
 #5.4.4    Level: 2    Role: V
 Pārliecinieties, ka politikas novērtēšanas latentums tiek pastāvīgi uzraudzīts ar automatizētiem brīdinājumiem par laika beigām, kas varētu ļaut apiet autorizāciju.
 #5.4.5    Level: 3    Role: D/V
 Pārliecinieties, ka vaicājuma atkārtošanas mehānismi pārskatī autorizācijas politikas, lai ņemtu vērā dinamiskas atļauju izmaiņas aktīvo lietotāju sesiju laikā.

---

### C5.5 Izvades filtrēšana un datu zuduma novēršana

Izvietojiet pēcapstrādes kontroles mehānismus, lai novērstu nesankcionētu datu atklāšanu mākslīgi ģenerētā saturā.

 #5.5.1    Level: 1    Role: D/V
 Pārbaudiet, vai pēc inferencēšanas filtrēšanas mehānismi skenē un rediģē neatļautu personisko identifikācijas informāciju (PII), klasificētu informāciju un uzņēmuma īpašuma datus pirms satura nodošanas pieprasītājiem.
 #5.5.2    Level: 1    Role: D/V
 Pārbaudiet, vai modeļa izvados norādītie citāti, atsauces un avota norādes ir pārbaudītas pret izsaucēja tiesībām, un tos noņemiet, ja tiek konstatēta nesankcionēta piekļuve.
 #5.5.3    Level: 2    Role: D
 Pārbaudiet, vai izvades formāta ierobežojumi (tīrīti PDF faili, metadatu noņemšanas attēli, apstiprināti failu tipi) tiek ievēroti, pamatojoties uz lietotāja piekļuves līmeņiem un datu klasifikācijām.
 #5.5.4    Level: 2    Role: V
 Pārliecinieties, ka redakcijas algoritmi ir deterministiski, versiju kontrolēti un uztur audita žurnālus, lai atbalstītu atbilstības izmeklēšanu un tiesu ekspertīzi.
 #5.5.5    Level: 3    Role: V
 Pārbaudiet, vai augsta riska redakcijas notikumi ģenerē adaptīvus žurnālfailus, kuros ietvertas kriptogrāfiskas oriģinālā satura hešvērtības krimināltiesiskai atgūšanai bez datu atklāšanas.

---

### C5.6 Daudznomnieku izolācija

Nodrošiniet kriptogrāfisku un loģisku izolāciju starp nomniekiem koplietotā AI infrastruktūrā.

 #5.6.1    Level: 1    Role: D/V
 Pārliecinieties, ka atmiņas telpas, iegulto elementu veikali, kešatmiņas ieraksti un pagaidu faili ir nodalīti pa nosaukumu telpām katram nomniekam, ar drošu dzēšanu, dzēšot nomnieku vai pārtraucot sesiju.
 #5.6.2    Level: 1    Role: D/V
 Pārliecinieties, ka katrs API pieprasījums satur autentificētu nomnieka identifikatoru, kas kriptogrāfiski pārbaudīts pret sesijas kontekstu un lietotāja tiesībām.
 #5.6.3    Level: 2    Role: D
 Pārbaudiet, vai tīkla politikas īsteno noklusējuma aizlieguma noteikumus starp nomniekiem saziņai pakalpojumu tīklos un konteineru orkestrācijas platformās.
 #5.6.4    Level: 3    Role: D
 Pārbaudiet, vai šifrēšanas atslēgas ir unikālas katram nomniekam ar klienta pārvaldītu atslēgu (CMK) atbalstu un kriptogrāfisku izolāciju starp nomnieku datu krātuvēm.

---

### C5.7 Autonomā aģenta autorizācija

Kontrolēt AI aģentu un autonomo sistēmu piekļuves atļaujas, izmantojot ierobežotu spēju tokenus un pastāvīgu autorizāciju.

 #5.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai autonómie aģenti saņem ierobežotas iespēju marķierus, kuros skaidri uzskaitītas atļautās darbības, pieejamie resursi, laika ierobežojumi un darbības ierobežojumi.
 #5.7.2    Level: 1    Role: D/V
 Pārbaudiet, ka augsta riska funkcionalitātes (failu sistēmas piekļuve, koda izpilde, ārējo API izsaukumi, finanšu darījumi) pēc noklusējuma ir atspējotas un prasa skaidras autorizācijas aktivizācijai kopā ar biznesa pamatojumiem.
 #5.7.3    Level: 2    Role: D
 Pārliecinieties, ka kapacitātes žetoni ir sasaistīti ar lietotāju sesijām, ietver kriptogrāfisku integritātes aizsardzību un nodrošina, ka tos nav iespējams saglabāt vai atkārtoti izmantot bezsaistes scenārijos.
 #5.7.4    Level: 2    Role: V
 Pārbaudiet, vai aģenta iniciētās darbības tiek pakļautas sekundārai autorizācijai, izmantojot ABAC politikas dzinēju ar pilnīgu konteksta novērtējumu un audita reģistrēšanu.
 #5.7.5    Level: 3    Role: V
 Pārbaudiet, vai aģenta kļūdu nosacījumi un izņēmumu apstrāde ietver iespēju darbības jomas informāciju, lai atbalstītu incidentu analīzi un tiesu izmeklēšanu.

---

### Atsauces

#### Standarti un ietvari

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Izpildes vadlīnijas

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Mākslīgā intelekta specifiskā drošība

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Modeļu, rāmju un datu piegādes ķēdes drošība

### Kontroles mērķis

Mākslīgā intelekta piegādes ķēdes uzbrukumi izmanto trešo personu modeļus, ietvarus vai datu kopas, lai iegultu aizmugures durvis, novirzes vai izmantojamu kodu. Šie kontroles mehānismi nodrošina pilnīgu izcelsmi, ievainojamību pārvaldību un uzraudzību, lai aizsargātu visu modeļa dzīves ciklu.

---

### C6.1 Iepriekšapmācīta modeļa pārbaude un izcelsme

Novērtējiet un autentificējiet trešo pušu modeļu izcelsmi, licences un slēptās uzvedības pirms jebkādas papildapmācības vai izvietošanas.

 #6.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai katrs trešās puses modeļa artefakts ietver parakstītu izcelsmes ierakstu, kurā norādīts avota repozitorijs un komita hašs.
 #6.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka modeļi tiek pārbaudīti, vai tajos nav ļaunprātīgu slāņu vai Trojas cēlāju, izmantojot automatizētus rīkus pirms importa.
 #6.1.3    Level: 2    Role: D
 Pārbaudiet, vai pārmācīšanās precizēšana iztur pretinieku novērtējumu, lai atklātu slēptas uzvedības.
 #6.1.4    Level: 2    Role: V
 Pārliecinieties, ka modeļa licences, eksporta kontroles tagi un datu izcelsmes paziņojumi ir ierakstīti ML-BOM ierakstā.
 #6.1.5    Level: 3    Role: D/V
 Pārbaudiet, vai augsta riska modeļi (publiski augšupielādētie svaru faili, neapstiprināti radītāji) paliek karantīnā līdz cilvēka pārskatam un apstiprināšanai.

---

### C6.2 Ietvara un bibliotēkas skenēšana

Pastāvīgi skenējiet ML ietvarus un bibliotēkas, lai atklātu CVE un ļaunprātīgu kodu, nodrošinot izpildes vides kaudzes drošību.

 #6.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka CI cauruļvadi veic atkarību skeneru darbību AI ietvaros un kritiskajās bibliotēkās.
 #6.2.2    Level: 1    Role: D/V
 Pārbaudiet, vai kritiskās ievainojamības (CVSS ≥ 7,0) bloķē pāreju uz ražošanas attēliem.
 #6.2.3    Level: 2    Role: D
 Pārbaudiet, vai statiskā koda analīze tiek veikta uz atzarotām vai piegādātām mašīnmācīšanās bibliotēkām.
 #6.2.4    Level: 2    Role: V
 Pārbaudiet, vai ietvara jaunināšanas priekšlikumos ir iekļauta drošības ietekmes novērtējuma atsauce uz publiskajiem CVE datplūsmām.
 #6.2.5    Level: 3    Role: V
 Pārbaudiet, vai darbības laika sensori brīdina par negaidītām dinamisko bibliotēku ielādēm, kas novirzās no parakstītā SBOM.

---

### C6.3 Atkarību fiksēšana un pārbaude

Piespraužiet katru atkarību pie nemaināmiem hešiem un reproducējiet būves, lai garantētu identiskas, neskartas artefaktus.

 #6.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai visi pakotņu pārvaldnieki nodrošina versiju fiksēšanu, izmantojot bloķēšanas failus.
 #6.3.2    Level: 1    Role: D/V
 Pārbaudiet, vai konteineru atsaucēs tiek izmantoti nemaināmi digesti, nevis maināmas birkas.
 #6.3.3    Level: 2    Role: D
 Pārliecinieties, ka pārbaudes reproducible‑build salīdzina hašus dažādos CI izpildījumos, lai nodrošinātu identiskus rezultātus.
 #6.3.4    Level: 2    Role: V
 Pārbaudiet, vai būvniecības apliecinājumi tiek glabāti 18 mēnešus audita izsekojamībai.
 #6.3.5    Level: 3    Role: D
 Pārliecinieties, ka derīguma termiņa beigušās atkarības izsauc automatizētus PR atjauninājumu vai forku pinotu versiju atjaunošanai.

---

### C6.4 Uzticama avota īstenošana

Ļauj lejupielādēt artefaktus tikai no kriptogrāfiski pārbaudītiem, organizācijas apstiprinātiem avotiem un bloķē visu pārējo.

 #6.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka modeļa svaru faili, datu kopas un konteineri tiek lejupielādēti tikai no apstiprinātām domēnu vietnēm vai iekšējiem reģistriem.
 #6.4.2    Level: 1    Role: D/V
 Pārliecinieties, ka Sigstore/Cosign paraksti apstiprina izdevēja identitāti pirms artefaktu saglabāšanas lokāli.
 #6.4.3    Level: 2    Role: D
 Pārliecinieties, ka izejas starpniekserveri bloķē neaizsargātas artefaktu lejupielādes, lai nodrošinātu uzticamu avotu politiku.
 #6.4.4    Level: 2    Role: V
 Pārbaudiet, vai repozitorija atļauto saraksts tiek pārskatīts ceturksnī, sniedzot pierādījumus par katras ieraksta biznesa pamatojumu.
 #6.4.5    Level: 3    Role: V
 Pārbaudiet, vai politikas pārkāpumi izraisa artefaktu karantīnu un atkarīgo cauruļvadu izpildes reversāciju.

---

### C6.5 Trešās puses datu kopas riska novērtējums

Novērtējiet ārējos datu kopumus attiecībā uz inficēšanu, aizspriedumiem un juridisko atbilstību, kā arī uzraugiet tos visā to darbības ciklā.

 #6.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka ārējie datu kopumi tiek pakļauti saindēšanas riska vērtēšanai (piemēram, datu pirkstu nospiedumu analīze, noviržu noteikšana).
 #6.5.2    Level: 1    Role: D
 Pārliecinieties, ka novirzes metrikas (demogrāfiskā izlīdzinātība, vienlīdzīgas iespējas) tiek aprēķinātas pirms datu kopas apstiprināšanas.
 #6.5.3    Level: 2    Role: V
 Pārbaudiet, vai ML‑BOM ierakstos ir iekļauti datu kopu izcelsmes un licences noteikumi.
 #6.5.4    Level: 2    Role: V
 Pārbaudiet, vai periodiska uzraudzība konstatē nogrimušanos vai bojājumus mitinātajos datu kopās.
 #6.5.5    Level: 3    Role: D
 Pārliecinieties, ka aizliegtā satura (autortiesību, personiski identificējamas informācijas) noņemšana tiek veikta ar automatizētas attīrīšanas palīdzību pirms apmācības.

---

### C6.6 Piegādes ķēdes uzbrukuma uzraudzība

Agrīni atklājiet piegādes ķēdes draudus, izmantojot CVE plūsmas, revīzijas žurnālu analītiku un sarkano komandu simulācijas.

 #6.6.1    Level: 1    Role: V
 Pārbaudiet, vai CI/CD revīzijas žurnāli tiek plūdināti SIEM noteikumiem, lai atklātu anomālijas pakotņu lejupielādē vai modificētu būvniecības soļos.
 #6.6.2    Level: 2    Role: D
 Pārliecinieties, ka incidentu atbildes darbību plānos ir iekļautas atcelšanas procedūras kompromitētiem modeļiem vai bibliotēkām.
 #6.6.3    Level: 3    Role: V
 Pārbaudiet, vai draudu izlūkošanas bagātināšanas atzīmes iezīmē ML specifiskos indikatorus (piemēram, modeļa piesārņošanas IoC) trauksmes kārtotnē.

---

### C6.7 ML‑BOM modeļa artefaktiem

Ģenerējiet un parakstiet detalizētas mašīnmācīšanās specifiskas SBOM (ML-BOM), lai turpmākie lietotāji varētu pārbaudīt komponentu integritāti izvietošanas laikā.

 #6.7.1    Level: 1    Role: D/V
 Pārliecinieties, ka katrs modeļa artefakts publicē ML-BOM, kurā ir norādītas datu kopas, svari, hiperparametri un licences.
 #6.7.2    Level: 1    Role: D/V
 Pārliecinieties, ka ML-BOM ģenerēšana un Cosign parakstīšana ir automatizēta nepārtrauktās integrācijas (CI) vidē un nepieciešama apvienošanai.
 #6.7.3    Level: 2    Role: D
 Pārbaudiet, vai ML-BOM pilnības pārbaudes neļauj veidot, ja trūkst kādas komponentes metadatu (haša, licences).
 #6.7.4    Level: 2    Role: V
 Pārbaudiet, vai lejupējie lietotāji var vaicāt ML-BOM caur API, lai validētu importētos modeļus izvietošanas laikā.
 #6.7.5    Level: 3    Role: V
 Pārbaudiet, vai ML-BOM ir versiju kontrolēti un tiek salīdzināti, lai atklātu nesankcionētas izmaiņas.

---

### Atsauces

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## C7 modeļa uzvedība, izejas kontrole un drošības nodrošināšana

### Kontroles mērķis

Modeļa izvades dati ir jāveido strukturēti, uzticami, droši, izskaidrojami un nepārtraukti jākontrolē ražošanā. To darot, samazinās halucinācijas, privātuma noplūdes, kaitīgs saturs un nekontrolētas darbības, vienlaikus palielinot lietotāju uzticību un atbilstību regulējošajiem standartiem.

---

### C7.1 Izvades formāta ievērošana

Stingri shēmas, ierobežota atšifrēšana un turpmāka validācija aptur bojātu vai ļaunprātīgu saturu pirms tā izplatīšanās.

 #7.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka atbildes shēmas (piemēram, JSON shēma) tiek nodrošinātas sistēmas uzvednē, un katrs izvades rezultāts tiek automātiski pārbaudīts; ne atbilstoši izvades rezultāti izraisīs labošanas vai noraidīšanas procesu.
 #7.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka ir iespējota ierobežotā dekodēšana (apturošās zīmes, regulārie izteicieni, maksimālais tokenu skaits), lai novērstu pārplūšanu vai prompta injekcijas sānu kanālus.
 #7.1.3    Level: 2    Role: D/V
 Pārbaudiet, vai lejupējie komponenti izturas pret izvadiem kā neuzticamiem un validē tos pret shēmām vai injekcijām drošiem de-serializatoriem.
 #7.1.4    Level: 3    Role: V
 Pārliecinieties, ka nepareizas izvades notikumi tiek reģistrēti, to ātrums tiek ierobežots un tie tiek attēloti uzraudzībā.

---

### C7.2 Halucināciju atpazīšana un mazināšana

Nenoteiktības novērtēšana un rezerves stratēģijas ierobežo izdomātas atbildes.

 #7.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka katram atbildes rezultātam tiek piešķirts ticamības vērtējums, izmantojot tokanu līmeņa log-varbūtības, ansambļa pašsaskaņas novērtējumu vai labi izstrādātus halucināciju detektorus.
 #7.2.2    Level: 1    Role: D/V
 Pārbaudiet, vai atbildes, kuru ticamības līmenis ir zem konfigurējamas sliekšņa, aktivizē rezerves darbplūsmas (piemēram, meklēšanas pastiprināta ģenerēšana, sekundārs modelis vai cilvēka pārskats).
 #7.2.3    Level: 2    Role: D/V
 Pārbaudiet, vai halucināciju gadījumi ir atzīmēti ar pamatcēloņa metadatiem un nodoti post-mortēma un precīzas regulēšanas (finetuning) plūsmām.
 #7.2.4    Level: 3    Role: D/V
 Pārliecinieties, ka sliekšņi un detektori tiek pārrēķināti pēc būtiskām modeļa vai zināšanu bāzes atjaunināšanām.
 #7.2.5    Level: 3    Role: V
 Pārbaudiet, vai informācijas paneļa vizualizācijas seko halucināciju līmeņiem.

---

### C7.3 Izvades drošības un privātuma filtrēšana

Politikas filtri un sarkano komandu (red-team) pārklājums aizsargā lietotājus un konfidenciālos datus.

 #7.3.1    Level: 1    Role: D/V
 Pārliecinieties, ka priekš un pēc ģenerēšanas izmantotie klasifikatori bloķē naida, uzmākšanās, pašnodarbināšanās, ekstrēmistu un seksuāli eksplicītu saturu, kas saskan ar politiku.
 #7.3.2    Level: 1    Role: D/V
 Pārliecinieties, ka katrā atbildē tiek veikta PII/PCI noteikšana un automātiska aizklāšana; pārkāpumi izraisa privātuma incidentu.
 #7.3.3    Level: 2    Role: D
 Pārbaudiet, vai konfidencialitātes birkas (piemēram, komercnoslēpumi) tiek pārnestas starp modalitātēm, lai novērstu noplūdi tekstā, attēlos vai kodā.
 #7.3.4    Level: 3    Role: D/V
 Pārliecinieties, ka filtra apietas mēģinājumi vai augsta riska klasifikācijas prasa sekundāru apstiprinājumu vai lietotāja atkārtotu autentifikāciju.
 #7.3.5    Level: 3    Role: D/V
 Pārbaudiet, vai filtrēšanas sliekšņi atbilst juridiskajām jurisdikcijām un lietotāja vecuma/lomas kontekstam.

---

### C7.4 Izvades un darbību ierobežošana

Ātruma ierobežojumi un apstiprināšanas sliekšņi novērš ļaunprātīgu izmantošanu un pārmērīgu autonomiju.

 #7.4.1    Level: 1    Role: D
 Pārbaudiet, vai kvotas uz lietotāju un API atslēgu līmeni ierobežo pieprasījumus, tokenus un izmaksas, izmantojot eksponenciālu atkārtotu mēģinājumu laiku 429 kļūdu gadījumā.
 #7.4.2    Level: 1    Role: D/V
 Pārliecinieties, ka privileģētas darbības (failu rakstīšana, koda izpilde, tīkla zvani) prasa politikas balstītu apstiprinājumu vai cilvēka līdzdalību.
 #7.4.3    Level: 2    Role: D/V
 Pārbaudiet, vai starpmodalitātes konsekvences pārbaudes nodrošina, ka attēli, kods un teksts, kas ģenerēti vienam un tam pašam pieprasījumam, nevar tikt izmantoti ļaunprātīgas satura kontrabandā.
 #7.4.4    Level: 2    Role: D
 Pārbaudiet, vai aģenta deleģēšanas dziļums, rekursijas ierobežojumi un atļautās rīku listes ir skaidri konfigurētas.
 #7.4.5    Level: 3    Role: V
 Pārbaudiet, vai ierobežojumu pārkāpums izsūta strukturētus drošības notikumus SIEM uzņemšanai.

---

### C7.5 Izejas izskaidrojamība

Caurspīdīgi signāli uzlabo lietotāja uzticību un iekšējo atkļūdošanu.

 #7.5.1    Level: 2    Role: D/V
 Pārbaudiet, vai lietotājam redzamie ticamības rādītāji vai īsi pamatojuma kopsavilkumi tiek parādīti, ja riska novērtējums to uzskata par piemērotu.
 #7.5.2    Level: 2    Role: D/V
 Pārbaudiet, vai ģenerētās paskaidrošanas nerāda jutīgus sistēmas uzvednes vai patentētu informāciju.
 #7.5.3    Level: 3    Role: D
 Pārliecinieties, ka sistēma uztver tokenu līmeņa log-varbūtības vai uzmanības kartes un glabā tās pilnvarotai pārbaudei.
 #7.5.4    Level: 3    Role: V
 Pārliecinieties, ka izskaidrojamības artefakti ir versiju kontrolēti kopā ar modeļa izlaidumiem pārbaudāmības nodrošināšanai.

---

### C7.6 Uzraudzības integrācija

Reāllaika novērojamība aizver ciklu starp izstrādi un ražošanu.

 #7.6.1    Level: 1    Role: D
 Pārbaudiet, vai metrikas (shēmas pārkāpumi, halucināciju līmenis, toksicitāte, personīgi identificējamas informācijas noplūdes, latentums, izmaksas) tiek straumētas uz centrālo uzraudzības platformu.
 #7.6.2    Level: 1    Role: V
 Pārliecinieties, ka katram drošības rādītājam ir definēti brīdinājuma sliekšņi, kā arī ir noteikti uzraudzības paaugstināšanas ceļi.
 #7.6.3    Level: 2    Role: V
 Pārbaudiet, vai informācijas paneļi korelē izvades anomālijas ar modeli/versiju, funkciju karogu un augšupejošo datu izmaiņām.
 #7.6.4    Level: 2    Role: D/V
 Pārbaudiet, vai uzraudzības dati tiek atgriezeniski izmantoti atkārtotai apmācībai, precizēšanai vai noteikumu atjaunināšanai dokumentētā MLOps darbplūsmā.
 #7.6.5    Level: 3    Role: V
 Pārliecinieties, ka uzraudzības caurules ir veiksmīgi pārbaudītas attiecībā uz uzlaušanas iespējamību un tās ir ar piekļuves kontroli, lai novērstu sensitīvu žurnālu noplūdi.

---

### 7.7 Generatīvās mediju aizsardzības pasākumi

Nodrošiniet, ka mākslīgā intelekta sistēmas negenerē nelikumīgu, kaitīgu vai neatļautu mediju saturu, ieviešot politikas ierobežojumus, izvades validāciju un izsekojamību.

 #7.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai sistēmas norādījumi un lietotāja instrukcijas skaidri aizliedz radīt nelikumīgu, kaitīgu vai bez piekrišanas veidotu deepfake multimediju (piemēram, attēlus, video, audio).
 #7.7.2    Level: 2    Role: D/V
 Pārbaudiet, vai prompti tiek filtrēti, lai novērstu mēģinājumus ģenerēt imitations, seksuāli eksplicītus deepfake materiālus vai medijus, kuros attēlotas reālas personas bez viņu piekrišanas.
 #7.7.3    Level: 2    Role: V
 Pārbaudiet, vai sistēma izmanto uztveres hašēšanu, ūdenszīmes noteikšanu vai pirkstu nospiedumu identifikāciju, lai novērstu autortiesību aizsargātas multimediju neatļautu reproducēšanu.
 #7.7.4    Level: 3    Role: D/V
 Pārliecinieties, ka visi ģenerētie multivides faili ir kriptogrāfiski parakstīti, aprīkoti ar ūdenszīmi vai tajos ir iegults pret manipulācijām izturīgs izcelsmes metadatu slānis, lai nodrošinātu turpmāku izsekojamību.
 #7.7.5    Level: 3    Role: V
 Pārbaudiet, vai apiet mēģinājumi (piemēram, uzvednes maskēšana, žargons, kā arī pretiniecisks formulējums) tiek atklāti, reģistrēti un ierobežoti ar ātrumu; atkārtotas ļaunprātīgas darbības tiek nodotas uzraudzības sistēmām.

### Atsauces

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## C8 Atmiņa, Iegultības un Vektoru Datubāžu Drošība

### Kontroles mērķis

Ieguldi un vektoru krātuves darbojas kā mūsdienu mākslīgā intelekta sistēmu "tiešās atmiņas", pastāvīgi pieņemot lietotāja sniegtos datus un atgriežot tos modeļa kontekstos, izmantojot izgūšanas paplašināto ģenerēšanu (Retrieval-Augmented Generation, RAG). Ja šī atmiņa netiek kontrolēta, tā var nopludināt personas identificējošu informāciju (PII), pārkāpt piekrišanu vai tikt apgriezta, lai atjaunotu sākotnējo tekstu. Šīs kontroles grupas mērķis ir nostiprināt atmiņas plūsmas un vektoru datubāzes tā, lai piekļuve būtu pēc iespējas ierobežota (least-privilege), ieguldījumi aizsargātu privātumu, glabātajiem vektoriem būtu termiņš vai tie būtu atsaucami pēc pieprasījuma, un katra lietotāja atmiņa nekad nekļūtu par cita lietotāja uzvedņu vai aizpildījumu avotu.

---

### C8.1 Piekļuves kontrole atmiņai un RAG indeksiem

Ieviesiet smalkas piekļuves kontroli katrā vektoru kolekcijā.

 #8.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai rindas/ietilpības līmeņa piekļuves kontroles noteikumi ierobežo pievienošanas, dzēšanas un vaicājumu operācijas pēc īrnieka, kolekcijas vai dokumenta tagiem.
 #8.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka API atslēgām vai JWT ir piešķirtas ierobežotas tiesības (piemēram, kolekciju ID, darbības verbi) un tās tiek mainītas vismaz reizi ceturksnī.
 #8.1.3    Level: 2    Role: D/V
 Pārbaudiet, vai privilēģiju eskalācijas mēģinājumi (piemēram, līdzību vaicājumi starp nosaukumu telpām) tiek atklāti un reģistrēti SIEM sistēmā 5 minūšu laikā.
 #8.1.4    Level: 2    Role: D/V
 Pārbaudiet, vai vektoru datubāzes auditi reģistrē subjekta identifikatoru, darbību, vektora ID/nosaukumvietu, līdzības slieksni un rezultātu skaitu.
 #8.1.5    Level: 3    Role: V
 Pārliecinieties, ka piekļuves lēmumi tiek pārbaudīti attiecībā uz apietām kļūdām katru reizi, kad tiek atjauninātas dzinēju versijas vai mainās indeksēšanas sadalīšanas noteikumi.

---

### C8.2 Iebūvētā tīrīšana un validācija

Veiciet teksta iepriekšēju pārbaudi, lai identificētu personiski identificējamu informāciju (PII), veiciet tās slēpšanu vai pseidonimizēšanu pirms vektorizācijas, un pēc vajadzības izpildiet papildus apstrādi iegūtajām iegultnēm, lai noņemtu atlikušos signālus.

 #8.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka PII un reglamentētie dati tiek atklāti, izmantojot automatizētus klasifikatorus, un pirms iegultā attēlojuma tie tiek maskēti, tokenizēti vai izslēgti.
 #8.2.2    Level: 1    Role: D
 Pārbaudiet, vai iegultās plūsmas nepieņem vai nesatur karantīnā ievades datus, kuros ir izpildāms kods vai ne-UTF-8 artefakti, kas varētu piesārņot indeksu.
 #8.2.3    Level: 2    Role: D/V
 Pārbaudiet, vai vietējā vai metrikas diferenciālās privātuma sanitizācija tiek piemērota teikumu iegultnēm, kuru attālums līdz jebkuram zināmam PII tokenam nokrīt zem konfigurējamas sliekšņa vērtības.
 #8.2.4    Level: 2    Role: V
 Pārbaudiet, vai sanitizācijas efektivitāte (piemēram, PII redakcijas atskaites līmenis, semantiskā nobīde) tiek apstiprināta vismaz reizi sešos mēnešos, salīdzinot ar etalona korpusiem.
 #8.2.5    Level: 3    Role: D/V
 Pārliecinieties, ka sanitizācijas konfigurācijas ir versiju kontrolētas un izmaiņas tiek pārskatītas kolēģu vidū.

---

### C8.3 Atmiņas derīguma termiņa beigas, atsaukšana un dzēšana

GDPR "tiesības tikt aizmirstam" un līdzīgi likumi prasa savlaicīgu dzēšanu; vektoru krātuves tādēļ jāatbalsta TTL (laiks līdz dzēšanai), pilnīgas dzēšanas un "kapu zīmju" izmantošanu, lai atsauktos vektorus nevarētu atgūt vai atkārtoti indeksēt.

 #8.3.1    Level: 1    Role: D/V
 Pārliecinieties, ka katram vektoram un metadatu ierakstam ir TTL vai skaidri norādīta saglabāšanas atzīme, kuru ievēro automatizētie tīrīšanas darbi.
 #8.3.2    Level: 1    Role: D/V
 Pārbaudiet, vai lietotāja pieprasītās dzēšanas darbības iznīcina vektorus, metadatus, kešatmiņas kopijas un atvasinātos indeksus 30 dienu laikā.
 #8.3.3    Level: 2    Role: D
 Pārbaudiet, vai loģiskās dzēšanas tiek izpildītas ar kriptogrāfisku glabāšanas bloku iznīcināšanu, ja aparatūra to atbalsta, vai arī ar atslēgas glabāšanas atslēgas iznīcināšanu.
 #8.3.4    Level: 3    Role: D/V
 Pārbaudiet, vai beigušies vektori tiek izslēgti no tuvāko kaimiņu meklēšanas rezultātiem mazāk nekā 500 ms pēc to derīguma termiņa beigām.

---

### C8.4 Novērst iegultās informācijas apgriešanu un noplūdi

Nesenās aizsardzības metodes — trokšņa virskārta, projekcijas tīkli, privātuma neironu perturbācija un lietojumprogrammu slāņa šifrēšana — var samazināt tokena līmeņa apgrieztības rādītājus zem 5%.

 #8.4.1    Level: 1    Role: V
 Pārbaudiet, vai pastāv formāls draudu modelis, kas aptver invertēšanas, dalības un atribūtu secināšanas uzbrukumus, un vai tas tiek pārskatīts ikgadēji.
 #8.4.2    Level: 2    Role: D/V
 Pārliecinieties, ka lietojumprogrammas slāņa šifrēšana vai meklējama šifrēšana aizsargā vektorus no tiešas pārlūkošanas no infrastruktūras administratoriem vai mākoņa darbiniekiem.
 #8.4.3    Level: 3    Role: V
 Pārbaudiet, vai aizsardzības parametri (ε DP, trokšņa σ, projekcijas ranga k) nodrošina privātumu ≥ 99 % tokenu aizsardzību un lietderību ≤ 3 % precizitātes zudumu.
 #8.4.4    Level: 3    Role: D/V
 Pārliecinieties, ka inversijas noturības metri ir daļa no izlaiduma barjerām modeļa atjauninājumiem, ar definētiem regresijas budžetiem.

---

### C8.5 Lietotājam specifiskas atmiņas diapazona ievērošana

Krusto-nomaļu noplūde joprojām ir augsts RAG risks: nepareizi filtrēti līdzības vaicājumi var atklāt cita klienta privātos dokumentus.

 #8.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka katrs izgūšanas vaicājums tiek apstrādāts ar nomnieka/lietošanas ID pēc tam, kad tas ir izfiltrēts, pirms to nodod LLM promptam.
 #8.5.2    Level: 1    Role: D
 Pārliecinieties, ka kolekciju nosaukumi vai nosaukumvietas ID ir sāļoti katram lietotājam vai nomniekam, lai vektori nevarētu sakrist dažādās darbības jomās.
 #8.5.3    Level: 2    Role: D/V
 Pārliecinieties, ka līdzības rezultāti, kas pārsniedz konfigurējamu attāluma slieksni, bet atrodas ārpus izsaucēja darbības jomas, tiek noraidīti un izraisīt drošības brīdinājumus.
 #8.5.4    Level: 2    Role: V
 Pārbaudiet, vai daudzlietotāju slodzes testi simulē pretinieciski noskaņotus vaicājumus, kas mēģina izgūt dokumentus ārpus piekļuves zonas, un pierāda nulles datu noplūdi.
 #8.5.5    Level: 3    Role: D/V
 Pārliecinieties, ka šifrēšanas atslēgas ir nodalītas pa nomniekiem, nodrošinot kriptogrāfisku izolāciju pat tad, ja fiziskā glabāšana tiek koplietota.

---

### C8.6 Uzlabota atmiņas sistēmas drošība

Drošības kontroles sarežģītām atmiņas arhitektūrām, tostarp episodiālajai, semantiskajai un darba atmiņai ar specifiskām izolācijas un validācijas prasībām.

 #8.6.1    Level: 1    Role: D/V
 Pārbaudiet, vai dažādi atmiņas tipi (episodiskā, semantiskā, darba) ir nodalīti drošības konteksti ar lomu balstītām piekļuves kontrolēm, atsevišķām šifrēšanas atslēgām un dokumentētiem piekļuves modeļiem katram atmiņas tipam.
 #8.6.2    Level: 2    Role: D/V
 Pārliecinieties, ka atmiņas konsolidācijas procesi ietver drošības validāciju, lai novērstu ļaunprātīgu atmiņu ievadi, izmantojot satura sanitāciju, avotu pārbaudi un integritātes pārbaudes pirms glabāšanas.
 #8.6.3    Level: 2    Role: D/V
 Pārbaudiet, vai atmiņas izgūšanas vaicājumi tiek pārbaudīti un attīrīti, lai novērstu neatļautas informācijas izguvi, izmantojot vaicājumu modeļu analīzi, piekļuves kontroles piemērošanu un rezultātu filtrēšanu.
 #8.6.4    Level: 3    Role: D/V
 Pārbaudiet, vai atmiņas aizmirstošanas mehānismi droši dzēš sensitīvu informāciju ar kriptogrāfiskās dzēšanas garantijām, izmantojot atslēgas dzēšanu, vairākkārtēju pārrakstīšanu vai aparatūras bāzētu drošu dzēšanu ar verifikācijas sertifikātiem.
 #8.6.5    Level: 3    Role: D/V
 Pārbaudiet, vai atmiņas sistēmas integritāte tiek nepārtraukti uzraudzīta, lai atklātu nesankcionētas izmaiņas vai bojājumus, izmantojot kontrolsummas, audita žurnālus un automatizētas brīdinājumus, kad atmiņas saturs mainās ārpus normālas darbības.

---

### Atsauces

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Autonomā orķestrēšana un aģentiskā darbību drošība

### Kontroles mērķis

Nodrošiniet, ka autonomās vai daudzagentu mākslīgā intelekta sistēmas var veikt tikai tādas darbības, kas ir skaidri paredzētas, autentificētas, auditējamas un atbilst noteiktiem izmaksu un riska ierobežojumiem. Tas aizsargā pret draudiem, piemēram, autonomās sistēmas kompromitēšanu, rīku ļaunprātīgu izmantošanu, aģentu cilpu atklāšanu, komunikācijas pārņemšanu, identitātes viltošanu, bariņu manipulācijām un nodoma manipulācijām.

---

### 9.1 Aģenta uzdevumu plānošana un rekursijas budžets

Ierobežojiet rekursīvos plānus un noteikt cilvēka pārbaudes punktus privilēģētām darbībām.

 #9.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai maksimālā rekursijas dziļuma, platuma, sienas pulksteņa laika, tokenu un naudas izmaksas katrai aģenta izpildei ir centrāli konfigurētas un versiju kontrolētas.
 #9.1.2    Level: 1    Role: D/V
 Pārliecināties, ka privileģētas vai neatgriezeniskas darbības (piemēram, koda apstiprinājumi, finanšu pārskaitījumi) prasa skaidru cilvēka apstiprinājumu caur auditable kanālu pirms izpildes.
 #9.1.3    Level: 2    Role: D
 Pārliecinieties, ka reāllaika resursu monitori aktivizē ķēdes pārtraukuma pārtraukumu, kad tiek pārsniegts jebkāds budžeta slieksnis, apturot turpmāku uzdevuma paplašināšanu.
 #9.1.4    Level: 2    Role: D/V
 Pārbaudiet, vai ķēdes pārtraucēja notikumi tiek reģistrēti ar aģenta ID, izraisīšanas nosacījumu un noķerto plāna stāvokli tiesu ekspertīzes pārskatīšanai.
 #9.1.5    Level: 3    Role: V
 Pārbaudiet, vai drošības testi aptver budžeta izsīkuma un nekontrolētas plāna izpildes scenārijus, apstiprinot drošu apturēšanu bez datu zuduma.
 #9.1.6    Level: 3    Role: D
 Pārliecinieties, ka budžeta politikas ir izteiktas kā koda politika un tiek īstenotas CI/CD, lai novērstu konfigurācijas novirzes.

---

### 9.2 Rīka spraudņa izolēšana (sandboxing)

Izolēt rīku mijiedarbības, lai novērstu nesankcionētu piekļuvi sistēmai vai koda izpildi.

 #9.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka katrs rīks/spraudnis izpildās operētājsistēmā, konteinerā vai WASM līmeņa smilšu kastē ar minimālas privilēģijas failu sistēmas, tīkla un sistēmas izsaukumu politiku.
 #9.2.2    Level: 1    Role: D/V
 Pārliecinieties, ka smilškastes resursu kvotas (CPU, atmiņa, disks, tīkla izeja) un izpildes laika ierobežojumi tiek ievēroti un ierakstīti.
 #9.2.3    Level: 2    Role: D/V
 Pārliecinieties, ka rīku binārie faili vai apraksti ir digitāli parakstīti; paraksti tiek pārbaudīti pirms ielādes.
 #9.2.4    Level: 2    Role: V
 Pārbaudiet, vai smilšu kastes telemetrija plūst uz SIEM; novirzes (piemēram, mēģinājumi izveidot izejošas pieslēgumus) izsauc brīdinājumus.
 #9.2.5    Level: 3    Role: V
 Pārbaudiet, vai augsta riska spraudņi tiek pakļauti drošības pārskatam un iekļūšanas testēšanai pirms ražošanas izvietošanas.
 #9.2.6    Level: 3    Role: D/V
 Pārbaudiet, vai smilšu kastes iziešanas mēģinājumi tiek automātiski bloķēti un pārkāpējs spraudnis tiek izolēts izmeklēšanas gaidīšanas laikā.

---

### 9.3 Autonomais cikls un izmaksu ierobežošana

Atklājiet un apturiet nekontrolētu aģentu savstarpējas rekurences un izmaksu eksploziju.

 #9.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai starp aģentiem veiktajām izsaukumiem ir iekļauts hop-limit vai TTL, ko izpildes vide samazina un kontrolē.
 #9.3.2    Level: 2    Role: D
 Pārliecinieties, ka aģenti uztur unikālu izsaukuma grafika ID, lai atklātu pašizsaukumus vai cikliskus modeļus.
 #9.3.3    Level: 2    Role: D/V
 Pārbaudiet, vai kopsavilkuma skaitītāji par skaitļošanas vienībām un izdevumiem tiek izsekoti katram pieprasījuma ķēdes posmam; ja tiek pārsniegts limits, ķēde tiek pārtraukta.
 #9.3.4    Level: 3    Role: V
 Pārbaudiet, vai formālā analīze vai modeļa pārbaude pierāda neierobežotas rekursijas neesamību aģentu protokolos.
 #9.3.5    Level: 3    Role: D
 Pārbaudiet, vai cilpas pārtraukšanas notikumi ģenerē brīdinājumus un nodrošina nepārtrauktas uzlabošanas metriku.

---

### 9.4 Protokola līmeņa ļaunprātīgas izmantošanas aizsardzība

Droši komunikācijas kanāli starp aģentiem un ārējām sistēmām, lai novērstu pārtveršanu vai manipulāciju.

 #9.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka visi ziņojumi no aģenta uz rīku un no aģenta uz aģentu ir autentificēti (piemēram, ar abpusēju TLS vai JWT) un ir nodrošināta gala līdz gala šifrēšana.
 #9.4.2    Level: 1    Role: D
 Pārbaudiet, vai shēmas tiek stingri validētas; nezināmi lauki vai nederīgi ziņojumi tiek noraidīti.
 #9.4.3    Level: 2    Role: D/V
 Pārbaudiet, vai integritātes pārbaudes (MAC vai digitālās parakstīšanas) aptver visu ziņojuma saturu, ieskaitot rīka parametrus.
 #9.4.4    Level: 2    Role: D
 Pārliecinieties, ka atkārtojuma aizsardzība (nonce vai laika zīmju logi) tiek ievērota protokola līmenī.
 #9.4.5    Level: 3    Role: V
 Pārbaudiet, vai protokolu implementācijas tiek pakļautas fuzzināšanai un statiskajai analīzei, lai atklātu injekcijas vai deserializācijas kļūdas.

---

### 9.5 Aģenta identitāte un manipulāciju pierādījumi

Nodrošiniet, ka darbības ir izsekojamas un izmaiņas atklājamas.

 #9.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka katram aģenta eksemplāram ir unikāla kriptogrāfiska identitāte (atslēgu pāris vai aparatūras sakņota akreditācija).
 #9.5.2    Level: 2    Role: D/V
 Pārbaudiet, vai visas aģentu darbības ir parakstītas un laika zīmētas; žurnālos iekļauts paraksts, lai nodrošinātu noraidīšanas neesamību.
 #9.5.3    Level: 2    Role: V
 Pārliecinieties, ka manipulācijām izturīgi žurnāli tiek glabāti tikai pievienošanas režīmā vai rakstīšanas reģistrā, kas atļauj vienreizēju ierakstu.
 #9.5.4    Level: 3    Role: D
 Pārbaudiet, vai identitātes atslēgas tiek pārslēgtas noteiktā grafikā un kompromisa rādītāju gadījumā.
 #9.5.5    Level: 3    Role: D/V
 Pārbaudiet, vai viltojuma vai atslēgu konflikta mēģinājumi nekavējoties izraisīja skartā aģenta karantīnu.

---

### 9.6 Daudzu aģentu spārna riska mazināšana

Samaziniet kolektīvās uzvedības riskus, izmantojot izolāciju un formālu drošības modelēšanu.

 #9.6.1    Level: 1    Role: D/V
 Pārliecinieties, ka aģenti, kas darbojas dažādās drošības domēnās, izpilda izolētās darbības laikā darbināmās smilšu kastēs vai tīkla segmentēs.
 #9.6.2    Level: 3    Role: V
 Pārliecinieties, ka spiediena uzvedība ir modelēta un formāli pārbaudīta dzīvotspējai un drošībai pirms izvietošanas.
 #9.6.3    Level: 3    Role: D
 Pārbaudiet, vai izpildes uzraudzības ierīces atklāj jaunas bīstamas parādības (piemēram, svārstības, bloķēšanās) un uzsāk korektīvus pasākumus.

---

### 9.7 Lietotāja un rīka autentifikācija / autorizācija

Ieviesiet stingru piekļuves kontroli katrai aģenta aktivizētai darbībai.

 #9.7.1    Level: 1    Role: D/V
 Pārliecinieties, ka aģenti autentificējas kā pirmšķiras principi uz lejuplūdes sistēmām, nekad neatkārtoti neizmantojot gala lietotāja pilnvaras.
 #9.7.2    Level: 2    Role: D
 Pārbaudiet, vai smalki regulētas autorizācijas politikas ierobežo, kurus rīkus aģents var aktivizēt un kādus parametrus tas var norādīt.
 #9.7.3    Level: 2    Role: V
 Pārbaudiet, vai privilēģiju pārbaudes tiek pārvērtētas katrā izsaukumā (pastāvīga autorizācija), ne tikai sesijas sākumā.
 #9.7.4    Level: 3    Role: D
 Pārliecinieties, ka deleģētās privilēģijas automātiski beidzas un pēc laika beigām vai domēna izmaiņām ir nepieciešama atkārtota piekrišana.

---

### 9.8 Aģenta uz aģentu saziņas drošība

Šifrējiet un nodrošiniet visu starp aģentiem sūtīto ziņu integritāti, lai novērstu noklausīšanos un manipulācijas.

 #9.8.1    Level: 1    Role: D/V
 Pārbaudiet, vai aģentu kanāliem ir obligāta savstarpējā autentifikācija un pilnīgi uz priekšu droša šifrēšana (piemēram, TLS 1.3).
 #9.8.2    Level: 1    Role: D
 Pārliecinieties, ka pirms apstrādes tiek pārbaudīta ziņojuma integritāte un izcelsme; kļūmes izraisīs brīdinājumus un ziņojuma noraidīšanu.
 #9.8.3    Level: 2    Role: D/V
 Pārbaudiet, vai komunikācijas metadati (laika zīmogi, secības numuri) tiek reģistrēti, lai atbalstītu forensisko atjaunošanu.
 #9.8.4    Level: 3    Role: V
 Pārbaudiet, vai formālā verifikācija vai modeļa pārbaude apstiprina, ka protokola stāvokļu mašīnas nevar tikt novirzītas nedrošos stāvokļos.

---

### 9.9 Nodoma pārbaude un ierobežojumu ievērošana

Pārbaudiet, vai aģenta darbības atbilst lietotāja izteiktajam nodomam un sistēmas ierobežojumiem.

 #9.9.1    Level: 1    Role: D
 Pārliecinieties, ka iepriekšējās izpildes ierobežojumu risinātāji pārbauda piedāvātās darbības atbilstoši stingri noteiktajām drošības un politikas prasībām.
 #9.9.2    Level: 2    Role: D/V
 Pārbaudiet, vai darbības ar lielu ietekmi (finansiālas, destruktīvas, ar privātuma aizsardzību saistītas) prasa skaidru apstiprinājumu no darbību veicošā lietotāja.
 #9.9.3    Level: 2    Role: V
 Pārbaudiet, vai pēcpārbaudes nosacījumi apstiprina, ka pabeigtās darbības sasniedza paredzētos rezultātus bez blakus efektiem; neatbilstības izraisīs atcelšanu.
 #9.9.4    Level: 3    Role: V
 Pārbaudiet, vai formālās metodes (piemēram, modeļu pārbaude, teorēmu pierādīšana) vai īpašību balstīti testi pierāda, ka aģentu plāni atbilst visām deklarētajām prasībām.
 #9.9.5    Level: 3    Role: D
 Pārliecinieties, ka nolūka neatbilstības vai ierobežojumu pārkāpumu incidenti tiek izmantoti nepārtrauktas uzlabošanas ciklos un draudu informācijas apmaiņā.

---

### 9.10 Aģentu izpētes stratēģijas drošība

Droša dažādu spriešanas stratēģiju izvēle un izpilde, ieskaitot ReAct, Chain-of-Thought un Tree-of-Thoughts pieejas.

 #9.10.1    Level: 1    Role: D/V
 Pārbaudiet, vai spriešanas stratēģijas izvēle izmanto determinētus kritērijus (ievades sarežģītība, uzdevuma veids, drošības konteksts) un vai identiskas ievades rada identiskas stratēģijas izvēles tajā pašā drošības kontekstā.
 #9.10.2    Level: 1    Role: D/V
 Pārliecinieties, ka katrai secināšanas stratēģijai (ReAct, Chain-of-Thought, Tree-of-Thoughts) ir paredzēta ieejas datu validācija, izejas datu sanitizācija un izpildes laika ierobežojumi, kas ir specifiski tās kognitīvajai pieejai.
 #9.10.3    Level: 2    Role: D/V
 Pārliecinieties, ka iemeslošanas stratēģiju pārejas tiek reģistrētas ar pilnīgu kontekstu, tostarp ievades raksturojumiem, atlases kritēriju vērtībām un izpildes metadatiem, lai nodrošinātu audita ceļa atjaunošanu.
 #9.10.4    Level: 2    Role: D/V
 Pārbaudiet, vai Tree-of-Thoughts spriešana ietver zaru apgriešanas mehānismus, kas pārtrauc izpēti, kad tiek konstatētas politikas pārkāpšanas, resursu ierobežojumi vai drošības robežas.
 #9.10.5    Level: 2    Role: D/V
 Pārliecinieties, ka ReAct (Iemeslojums-Darbība-Novērošana) cikli ietver validācijas punktus katrā posmā: iepriekšējā soļa pārbaudi, darbības autorizāciju un novērojuma attīrīšanu pirms turpināšanas.
 #9.10.6    Level: 3    Role: D/V
 Pārliecinieties, ka sprieduma stratēģijas veiktspējas metri (izpildes laiks, resursu izmantošana, izvades kvalitāte) tiek uzraudzīti ar automatizētiem brīdinājumiem, kad metri novirzās ārpus konfigurētajām robežvērtībām.
 #9.10.7    Level: 3    Role: D/V
 Pārbaudiet, vai jauktās spriešanas pieejas, kas apvieno vairākas stratēģijas, uztur visu sastāvdaļu stratēģiju ievaddatu pārbaudi un izejas ierobežojumus, nepārkāpjot nevienu drošības kontroli.
 #9.10.8    Level: 3    Role: D/V
 Pārbaudiet, vai apziņas stratēģijas drošības testēšana ietver fuzingus ar nepareiziem ievaddatiem, pretinieciskiem uzvednēm, kas paredzētas stratēģijas maiņas piespiedšanai, un robežnosacījumu testēšanu katrai kognitīvajai pieejai.

---

### 9.11 Aģenta Dzīves cikla stāvokļu pārvaldība un drošība

Droša aģenta inicializācija, stāvokļa pārejas un terminācija ar kriptogrāfiskām audita pēdām un definētām atkopšanas procedūrām.

 #9.11.1    Level: 1    Role: D/V
 Pārbaudiet, vai aģenta inicializācija ietver kriptogrāfiskās identitātes izveidi ar aparatūras atbalstītām akreditācijām un nemaināmām sākotnējās pārbaudes žurnālu ierakstiem, kuros ir iekļauts aģenta ID, laika zīmogs, konfigurācijas hašs un inicializācijas parametri.
 #9.11.2    Level: 2    Role: D/V
 Pārliecinieties, ka aģenta stāvokļa pārejas ir kriptogrāfiski parakstītas, laikspiedola atzīmētas un žurnālfailā ierakstītas ar pilnīgu kontekstu, ieskaitot izraisījošos notikumus, iepriekšējā stāvokļa hašu, jaunā stāvokļa hašu un veiktās drošības validācijas.
 #9.11.3    Level: 2    Role: D/V
 Pārliecinieties, ka aģenta izslēgšanas procedūras ietver drošu atmiņas dzēšanu, izmantojot kriptogrāfisko dzēšanu vai vairākkārtēju pārrakstīšanu, akreditācijas datu atsaukšanu ar sertifikācijas iestādes paziņošanu, kā arī nelikumīgas iejaukšanās pierādījumus sniedzošu pārtraukšanas sertifikātu ģenerēšanu.
 #9.11.4    Level: 3    Role: D/V
 Pārbaudiet, vai aģentu atkopšanas mehānismi validē stāvokļa integritāti, izmantojot kriptogrāfiskos kontrolsummas (vismaz SHA-256), un veic atgriešanos pie zināmi labiem stāvokļiem, kad tiek konstatēta bojājuma koriģēšana ar automatizētām brīdinājuma sistēmām un manuālu apstiprinājumu prasībām.
 #9.11.5    Level: 3    Role: D/V
 Pārbaudiet, vai aģentu saglabāšanas mehānismi šifrē sensitīvos stāvokļa datus ar katram aģentam atšķirīgām AES-256 atslēgām un īsteno drošu atslēgu rotāciju konfigurējamos grafikā (līdz 90 dienām) ar nulles dīkstāves izvēršanu.

---

### 9.12 Rīku integrācijas drošības struktūra

Drošības kontroles dinamiskai rīku ielādei, izpildei un rezultātu validācijai ar definētiem riska novērtējuma un apstiprināšanas procesiem.

 #9.12.1    Level: 1    Role: D/V
 Pārliecinieties, ka instrumentu aprakstos iekļauts drošības metadati, kas norāda nepieciešamās privilēģijas (lasīšana/rakstīšana/izpilde), riska līmeņus (zems/vidējs/augsts), resursu ierobežojumus (CPU, atmiņa, tīkls) un validācijas prasības, kas dokumentētas instrumentu manifestos.
 #9.12.2    Level: 1    Role: D/V
 Pārbaudiet, vai rīka izpildes rezultāti tiek validēti pret gaidītajiem shēmām (JSON shēma, XML shēma) un drošības politikām (izvades sanitizācija, datu klasifikācija) pirms integrācijas, ievērojot taimeru ierobežojumus un kļūdu apstrādes procedūras.
 #9.12.3    Level: 2    Role: D/V
 Pārbaudiet, vai rīku mijiedarbības žurnāli ietver detalizētu drošības kontekstu, tostarp privilēģiju izmantošanu, datu piekļuves modeļus, izpildes laiku, resursu patēriņu un atgriešanas kodus ar strukturētu žurnālu veidošanu SIEM integrācijai.
 #9.12.4    Level: 2    Role: D/V
 Pārliecinieties, ka dinamiskās rīku ielādes mehānismi pārbauda digitālos parakstus, izmantojot PKI infrastruktūru, un īsteno drošas ielādes protokolus ar smilšu kastes izolāciju un atļauju verifikāciju pirms izpildes.
 #9.12.5    Level: 3    Role: D/V
 Pārbaudiet, vai rīka drošības novērtējumi tiek automātiski aktivizēti jauniem versijām ar obligātiem apstiprināšanas posmiem, kas ietver statisko analīzi, dinamisko testēšanu un drošības komandas pārskatu ar dokumentētiem apstiprināšanas kritērijiem un SLA prasībām.

---

#### Atsauces

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Pretestības pret pretinieciskiem uzbrukumiem un privātuma aizsardzība

### Vadības mērķis

Nodrošiniet, ka mākslīgā intelekta modeļi paliek uzticami, privātumu aizsargājoši un izturīgi pret ļaunprātīgu izmantošanu, saskaroties ar izvairīšanās, secināšanas, izguves vai indēšanas uzbrukumiem.

---

### 10.1 Modeļa saskaņošana un drošība

Aizsargājieties pret kaitīgiem vai politikas pārkāpjošiem rezultātiem.

 #10.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai izlīdzināšanas testu komplekts (red-team uzvednes, jailbreaker pārbaudes, aizliegtas satura pārbaudes) tiek versiju kontrolēts un veikts katrā modeļa laidienā.
 #10.1.2    Level: 1    Role: D
 Pārliecinieties, ka tiek ievēroti atteikuma un drošas pabeigšanas aizsargjoslas.
 #10.1.3    Level: 2    Role: D/V
 Pārliecinieties, ka automatizēts novērtētājs nosaka kaitīgā satura līmeni un iezīmē regresijas, kas pārsniedz noteikto slieksni.
 #10.1.4    Level: 2    Role: D
 Pārbaudiet, vai pretpretošanās treniņš ir dokumentēts un reproducējams.
 #10.1.5    Level: 3    Role: V
 Pārbaudiet, vai formālas politikas atbilstības pierādījumi vai sertificēta uzraudzība aptver kritiskās jomas.

---

### 10.2 Pretestēšana pret pretinieciskiem piemēriem

Palieliniet izturību pret manipulētiem ievades datiem. Robustā pretinieku apmācība un salīdzināšanas rādītāju vērtēšana pašlaik ir labākā prakse.

 #10.2.1    Level: 1    Role: D
 Pārliecinieties, ka projekta krātuves satur pretinieku apmācības konfigurācijas ar reproducējamām sēklām.
 #10.2.2    Level: 2    Role: D/V
 Pārbaudiet, vai pretinieku piemēru atklāšana ražošanas plūsmās izsauc bloķējošus brīdinājumus.
 #10.2.4    Level: 3    Role: V
 Pārbaudiet, vai sertificētās drošības pierādījumi vai intervāla robežu sertifikāti aptver vismaz galvenās kritiskās klases.
 #10.2.5    Level: 3    Role: V
 Pārbaudiet, vai regresijas testi izmanto adaptīvās uzbrukumus, lai apstiprinātu, ka nav mērāmas noturības samazinājuma.

---

### 10.3 Dalības informācijas noplūdes risku mazināšana

 ierobežot iespēju noteikt, vai ieraksts bija mācību datos. Diferenciālā privātuma un pārliecības vērtējuma maskēšanas metodes joprojām ir visefektīvākās zināmās aizsardzības.

 #10.3.1    Level: 1    Role: D
 Pārbaudiet, vai katra vaicājuma entropijas regulēšana vai temperatūras skalēšana samazina pārlieku pārliecinātas prognozes.
 #10.3.2    Level: 2    Role: D
 Pārbaudiet, vai apmācībā tiek izmantota ε-ierobežota diferenciāli privāta optimizācija sensitīviem datu kopām.
 #10.3.3    Level: 2    Role: V
 Pārbaudiet, vai uzbrukuma simulācijas (ēnu modelis vai melnās kastes) uzrāda uzbrukuma AUC ≤ 0.60 uz turētajiem datiem.

---

### 10.4 Modeļa apgriešanas noturība

Novērst privāto atribūtu rekonstrukciju. Pēdējie pētījumi uzsver izvades saīsināšanu un diferencētas privātuma (DP) garantijas kā praktiskas aizsardzības metodes.

 #10.4.1    Level: 1    Role: D
 Pārbaudiet, vai sensitīvas atribūti nekad netiek tieši izvadīti; ja nepieciešams, izmantojiet kategorijas vai vienvirziena pārveidojumus.
 #10.4.2    Level: 1    Role: D/V
 Pārbaudiet, vai pieprasījumu ātruma ierobežojumi ierobežo atkārtotus adaptīvus pieprasījumus no viena un tā paša lietotāja.
 #10.4.3    Level: 2    Role: D
 Pārbaudiet, vai modelis ir apmācīts ar privātumu saglabājošu trokšņa pievienošanu.

---

### 10.5 Modeļa izguves aizsardzība

Atklājiet un novēršiet neatļautu klonēšanu. Ieteicama ūdenszīmes pievienošana un vaicājumu paraugu analīze.

 #10.5.1    Level: 1    Role: D
 Pārbaudiet, vai inferenču vārtejas ievēro globālos un atsevišķu API atslēgu ātruma ierobežojumus, kas pielāgoti modeļa atmiņas slieksnim.
 #10.5.2    Level: 2    Role: D/V
 Pārliecinieties, ka vaicājuma entropijas un ievades daudzveidības statistika tiek izmantota automatizētas ekstrakcijas detektora darbībā.
 #10.5.3    Level: 2    Role: V
 Pārbaudiet, vai trauslus vai varbūtības ūdenszīmes var pierādīt ar p < 0,01 ne vairāk kā 1 000 vaicājumos pret aizdomīgu klonu.
 #10.5.4    Level: 3    Role: D
 Pārbaudiet, vai watermark atslēgas un aktivizēšanas kopas tiek glabātas aparatūras drošības modulī un tiek rotētas reizi gadā.
 #10.5.5    Level: 3    Role: V
 Pārbaudiet, vai izguves brīdinājuma notikumi ietver pārkāpjošos vaicājumus un ir integrēti ar incidentu reaģēšanas darbplāniem.

---

### 10.6 Secinājumu laika inficēto datu noteikšana

Identificēt un neutralizēt aizmugurējās durvis vai saindētās ieejas.

 #10.6.1    Level: 1    Role: D
 Pārliecinieties, ka ieejas dati tiek pārbaudīti caur anomāliju detektoru (piemēram, STRIP, konsekvences vērtēšanu) pirms modeļa inferencēšanas.
 #10.6.2    Level: 1    Role: V
 Pārliecinieties, ka detektora sliekšņi ir noregulēti uz tīriem/indētiem validācijas datu kopumiem, lai panāktu mazāk nekā 5% kļūdaini pozitīvus rezultātus.
 #10.6.3    Level: 2    Role: D
 Pārbaudiet, vai ievades dati, kas atzīmēti kā piesārņoti, izraisām mīksto bloķēšanu un cilvēka pārskatīšanas darbplūsmas.
 #10.6.4    Level: 2    Role: V
 Pārliecinieties, ka detektori tiek pārbaukti stresa apstākļos ar adaptīvām, bezizraižu slēptām uzbrukuma metodēm.
 #10.6.5    Level: 3    Role: D
 Pārliecinieties, ka ir reģistrēti noteikšanas efektivitātes metri un tos periodiski pārskata, izmantojot svaigu draudu izlūkošanu.

---

### 10.7 Dinamiskā drošības politikas pielāgošana

Drošības politikas atjauninājumi reāllaikā, pamatojoties uz draudu informāciju un uzvedības analīzi.

 #10.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai drošības politikas var tikt atjauninātas dinamiskā režīmā bez aģenta restartēšanas, saglabājot politikas versijas integritāti.
 #10.7.2    Level: 2    Role: D/V
 Pārbaudiet, vai politikas atjauninājumi ir kriptogrāfiski parakstīti no pilnvarotajiem drošības personāla un pārbaudīti pirms to piemērošanas.
 #10.7.3    Level: 2    Role: D/V
 Pārliecinieties, ka dinamiskās politikas izmaiņas tiek reģistrētas ar pilnīgu audita pēdu, iekļaujot pamatojumu, apstiprināšanas ķēdes un atcelšanas procedūras.
 #10.7.4    Level: 3    Role: D/V
 Pārliecinieties, ka adaptīvās drošības mehānismi pielāgo draudu noteikšanas jutīgumu, pamatojoties uz riska kontekstu un uzvedības modeļiem.
 #10.7.5    Level: 3    Role: D/V
 Pārbaudiet, vai politikas pielāgošanas lēmumi ir izskaidrojami un ietver pierādījumu ceļus drošības komandas pārskatīšanai.

---

### 10.8 Atspoguļojuma balstīta drošības analīze

Drošības validācija caur aģenta pašrefleksiju un meta-kognitīvo analīzi.

 #10.8.1    Level: 1    Role: D/V
 Pārbaudiet, vai aģenta refleksijas mehānismi ietver drošībai vērstu pašnovērtējumu par lēmumiem un darbībām.
 #10.8.2    Level: 2    Role: D/V
 Pārliecinieties, ka atspulgu izvades tiek pārbaudītas, lai novērstu paša novērtēšanas mehānismu manipulēšanu ar pretinieciskiem ievadiem.
 #10.8.3    Level: 2    Role: D/V
 Pārliecinieties, ka meta-kognitīvā drošības analīze identificē potenciālu aizspriedumu, manipulāciju vai kompromisu aģenta spriešanas procesos.
 #10.8.4    Level: 3    Role: D/V
 Pārbaudiet, vai uz atspulga balstītie drošības brīdinājumi aktivizē uzlabotu uzraudzību un potenciālas cilvēka iejaukšanās darba plūsmas.
 #10.8.5    Level: 3    Role: D/V
 Pārbaudiet, vai nepārtraukta mācīšanās no drošības pārdomām uzlabo draudu noteikšanu, nesamazinot likumīgas funkcionalitātes kvalitāti.

---

### 10.9 Evolūcija un pašuzlabošanās drošība

Drošības kontroles aģentu sistēmām, kas spēj pašmodificēties un attīstīties.

 #10.9.1    Level: 1    Role: D/V
 Pārbaudiet, vai pašmodifikācijas iespējas ir ierobežotas tikai noteiktās drošajās zonās ar formālu verificēšanas robežām.
 #10.9.2    Level: 2    Role: D/V
 Pārliecinieties, ka evolūcijas priekšlikumi tiek pakļauti drošības ietekmes novērtējumam pirms ieviešanas.
 #10.9.3    Level: 2    Role: D/V
 Pārbaudiet, vai pašuzlabošanās mehānismi ietver atteices iespējas ar integritātes pārbaudi.
 #10.9.4    Level: 3    Role: D/V
 Pārbaudiet, vai meta-mācīšanās drošība novērš uzlabošanas algoritmu nelabvēlīgu manipulāciju.
 #10.9.5    Level: 3    Role: D/V
 Pārbaudiet, vai rekurzīvā pašuzlabošanās ir ierobežota ar formāliem drošības ierobežojumiem, izmantojot matemātiskus pierādījumus par konverģenci.

---

#### Atsauces

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Privātuma aizsardzība un personisko datu pārvaldība

### Kontroles mērķis

Uzturiet stingras privātuma garantijas visā mākslīgā intelekta dzīves ciklā — datu vākšanā, apmācībā, inferencē un incidentu novēršanā — tā, lai personas dati tiktu apstrādāti tikai ar skaidru piekrišanu, pēc iespējas ierobežotāka apjoma, ar pārbaudāmu dzēšanu un oficiālām privātuma garantijām.

---

### 11.1 Anonimizācija un datu minimizācija

 #11.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai tiešie un kvazi-identifikatori ir noņemti vai hasēti.
 #11.1.2    Level: 2    Role: D/V
 Pārbaudiet, vai automatizētās revīzijas mēra k-anonimitāti/l-daudzveidību un brīdina, kad sliekšņi noslīd zem politikas līmeņa.
 #11.1.3    Level: 2    Role: V
 Pārbaudiet, vai modeļa iezīmju nozīmīguma pārskati pierāda, ka nav identifikatoru noplūdes, kas pārsniedz ε = 0,01 savstarpējās informācijas līmeni.
 #11.1.4    Level: 3    Role: V
 Pārliecinieties, ka formālie pierādījumi vai sintezētās datu sertifikācija rāda, ka pāratpazīšanas risks ir ≤ 0,05 pat saites uzbrukumu gadījumā.

---

### 11.2 Tiesības tikt aizmirstam un dzēšanas izpilde

 #11.2.1    Level: 1    Role: D/V
 Pārbaudiet, vai datu subjektu dzēšanas pieprasījumi tiek izplatīti uz izejas datu kopām, kontrolpunktiem, iegultajām telpām, žurnāliem un dublējumiem servisa līmeņa līgumā, kas nepārsniedz 30 dienas.
 #11.2.2    Level: 2    Role: D
 Pārbaudiet, vai "mašīnmācīšanās aizmirsšanas" rutīnas fiziski pārtrenē vai aptuveni noņem datus, izmantojot sertificētas aizmirstošanas algoritmus.
 #11.2.3    Level: 2    Role: V
 Pārbaudiet, vai ēnas modeļa novērtējums pierāda, ka aizmirsto ierakstu ietekme pēc dzēšanās ir mazāka par 1% no rezultātiem.
 #11.2.4    Level: 3    Role: V
 Pārbaudiet, vai dzēšanas notikumi tiek nemainīgi reģistrēti un ir pārbaudāmi regulatoriem.

---

### 11.3 Diferenciālās privātuma aizsardzības mehānismi

 #11.3.1    Level: 2    Role: D/V
 Pārbaudiet, vai privātuma zuduma uzskaites paneļi brīdina, kad kumulatīvais ε pārsniedz politikas sliekšņus.
 #11.3.2    Level: 2    Role: V
 Pārbaudiet, vai melnās kastes privātuma auditi novērtē ε̂ ar 10% precizitāti no deklarētās vērtības.
 #11.3.3    Level: 3    Role: V
 Pārbaudiet, vai formālie pierādījumi aptver visus pēc apmācības veikto smalko pielāgojumu un iebūvēto reprezentāciju variantus.

---

### 11.4 Mērķa ierobežojums un aizsardzība pret apjoma paplašināšanos

 #11.4.1    Level: 1    Role: D
 Pārliecinieties, ka katram datu kopumam un modeļa kontrolpunktam ir mašīnlasāms mērķa tags, kas saskan ar sākotnējo piekrišanu.
 #11.4.2    Level: 1    Role: D/V
 Pārbaudiet, vai izpildes uzraugi atklāj vaicājumus, kas nav saskaņā ar deklarēto mērķi, un aktivizē maigās atteikšanās režīmu.
 #11.4.3    Level: 3    Role: D
 Pārbaudiet, vai politika-kods vārti bloķē modeļu atkārtotu izvietošanu jaunās jomās bez DPIA pārskatīšanas.
 #11.4.4    Level: 3    Role: V
 Pārbaudiet, vai formāli izsekojamības pierādījumi rāda, ka katrs personas datu dzīvotspējas cikls paliek piekritušajā apjomā.

---

### 11.5 Piekrīšanu pārvaldība un likumīga pamata izsekošana

 #11.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka piekrišanas pārvaldības platforma (CMP) reģistrē piekrišanas statusu, mērķi un saglabāšanas periodu katram datu subjektam.
 #11.5.2    Level: 2    Role: D
 Pārbaudiet, vai API izpauž piekrišanas tokenus; modeļiem jāverificē tokena darbības joma pirms inferencēšanas.
 #11.5.3    Level: 2    Role: D/V
 Pārbaudiet, vai noraidīta vai atsaukta piekrišana pārtrauc apstrādes procesus 24 stundu laikā.

---

### 11.6 Federētā mācīšanās ar privātuma kontroli

 #11.6.1    Level: 1    Role: D
 Pārbaudiet, vai klienta atjauninājumos tiek izmantota lokālā diferenciālās privātuma trokšņu pievienošana pirms apkopojuma.
 #11.6.2    Level: 2    Role: D/V
 Pārbaudiet, vai treniņa metrikas ir diferenciāli privātas un nekad neatklāj viena klienta zaudējumus.
 #11.6.3    Level: 2    Role: V
 Pārliecinieties, ka ir iespējota pretindēšanas izturīga agregācija (piemēram, Krum/Trimmed-Mean).
 #11.6.4    Level: 3    Role: V
 Pārbaudiet, vai formālie pierādījumi demonstrē kopējo ε budžetu ar mazāk nekā 5 lietderības zudumu.

---

#### Atsauces

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Uzraudzība, Žurnālu veidošana un Anomāliju noteikšana

### Kontroles mērķis

Šī sadaļa sniedz prasības reāllaika un forensiskai pārredzamībai par to, ko modelis un citas mākslīgā intelekta sastāvdaļas redz, dara un atgriež, lai draudi varētu tikt atklāti, klasificēti un analizēti mācībām.

### C12.1 Pieprasījumu un atbilžu žurnālu veidošana

 #12.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka visi lietotāju pieprasījumi un modeļa atbildes tiek reģistrēti ar atbilstošu metadatu kopu (piemēram, laika zīmi, lietotāja ID, sesijas ID, modeļa versiju).
 #12.1.2    Level: 1    Role: D/V
 Pārliecinieties, ka žurnāli tiek glabāti drošās, piekļuvei kontrolētās krātuvēs ar piemērotām saglabāšanas politikām un dublēšanas procedūrām.
 #12.1.3    Level: 1    Role: D/V
 Pārbaudiet, vai žurnālu glabāšanas sistēmas ievieš šifrēšanu atpūtā un pārsūtīšanas laikā, lai aizsargātu žurnālos iekļauto sensitīvo informāciju.
 #12.1.4    Level: 1    Role: D/V
 Pārliecinieties, ka sensitīvi dati promptos un izvadēs tiek automātiski anonimizēti vai maskēti pirms žurnālu veidošanas, ar konfigurējamām anonimizēšanas noteikumiem personīgi identificējamai informācijai (PII), akreditācijas datiem un īpašumtiesību informācijai.
 #12.1.5    Level: 2    Role: D/V
 Pārbaudiet, vai politikas lēmumi un drošības filtrēšanas darbības tiek reģistrētas ar pietiekamu detalizētību, lai nodrošinātu satura moderēšanas sistēmu auditu un problēmu novēršanu.
 #12.1.6    Level: 2    Role: D/V
 Pārliecinieties, ka žurnāla integritāte ir aizsargāta, piemēram, ar kriptogrāfiskām parakstiem vai rakstīšanai tikai paredzētu glabātuvi.

---

### C12.2 ļaunprātīgas izmantošanas atklāšana un brīdināšana

 #12.2.1    Level: 1    Role: D/V
 Pārbaudiet, vai sistēma atpazīst un signalizē par zināmiem jailbreak raksturlielumiem, uzaicinājumu injekcijas mēģinājumiem un pretinieciskiem ievadiem, izmantojot parakstu bāzes noteikšanu.
 #12.2.2    Level: 1    Role: D/V
 Pārliecinieties, ka sistēma integrējas ar esošajām Drošības informācijas un notikumu pārvaldības (SIEM) platformām, izmantojot standarta žurnālu formātus un protokolus.
 #12.2.3    Level: 2    Role: D/V
 Pārliecinieties, ka bagātinātie drošības notikumi ietver ar mākslīgo intelektu saistītu kontekstu, piemēram, modeļu identifikatorus, pārliecības rādītājus un drošības filtru lēmumus.
 #12.2.4    Level: 2    Role: D/V
 Pārbaudiet, vai uzvedības anomāliju detektēšana atklāj neparastus sarunas modeļus, pārmērīgas pārmēģinājuma mēģinājumus vai sistemātiskas izpētes uzvedības.
 #12.2.5    Level: 2    Role: D/V
 Pārbaudiet, vai reāllaika brīdināšanas mehānismi informē drošības komandas, kad tiek konstatēti iespējamie politikas pārkāpumi vai uzbrukuma mēģinājumi.
 #12.2.6    Level: 2    Role: D/V
 Pārliecinieties, ka pielāgotie noteikumi iekļauti, lai atklātu mākslīgā intelekta specifiskos draudu modeļus, tostarp koordinētas aplaušanas mēģinājumus, uzvedņu injekcijas kampaņas un modeļu ekstrahēšanas uzbrukumus.
 #12.2.7    Level: 3    Role: D/V
 Pārbaudiet, vai automatizētie incidentu reaģēšanas darbplūsmas spēj izolēt kompromitētus modeļus, bloķēt ļaunprātīgus lietotājus un eskalēt kritiskus drošības notikumus.

---

### C12.3 Modeļa novirzes noteikšana

 #12.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai sistēma uzrauga pamata veiktspējas rādītājus, piemēram, precizitāti, pārliecības līmeņus, latentumu un kļūdu rādītājus dažādu modeļu versijās un laika periodos.
 #12.3.2    Level: 2    Role: D/V
 Pārbaudiet, vai automātiskā trauksmes sistēma aktivizējas, kad veiktspējas rādītāji pārsniedz iepriekš noteiktos degradācijas sliekšņus vai būtiski novirzās no bāzes līmeņiem.
 #12.3.3    Level: 2    Role: D/V
 Pārbaudiet, vai halucināciju noteikšanas monitori identificē un atzīmē gadījumus, kad modeļa izvades satur faktiski nepareizu, nesakritīgu vai izdomātu informāciju.

---

### C12.4 Veiktspējas un uzvedības telemetrija

 #12.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka operacionālie rādītāji, tostarp pieprasījumu latentums, tokenu patēriņš, atmiņas izmantošana un caurlaide, tiek nepārtraukti ievākti un uzraudzīti.
 #12.4.2    Level: 1    Role: D/V
 Pārliecinieties, ka veiksmju un neveiksmju rādītāji tiek izsekoti, kategorizējot kļūdu tipus un to pamatcēloņus.
 #12.4.3    Level: 2    Role: D/V
 Pārliecinieties, ka resursu izmantošanas uzraudzība ietver GPU/CPU lietojumu, atmiņas patēriņu un krātuves prasības ar brīdinājumiem, pārsniedzot noteiktos sliekšņus.

---

### C12.5 Mākslīgā intelekta incidentu reaģēšanas plānošana un izpilde

 #12.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka incidentu reaģēšanas plāni īpaši risina ar mākslīgā intelekta drošības notikumiem saistītas situācijas, tostarp modeļa kompromitāciju, datu piesārņošanu un pretinieku uzbrukumus.
 #12.5.2    Level: 2    Role: D/V
 Pārbaudiet, vai incidentu reaģēšanas komandas ir aprīkotas ar mākslīgā intelekta specifiskiem forensikas rīkiem un ekspertīzi modeļu uzvedības un uzbrukuma vektoru izmeklēšanai.
 #12.5.3    Level: 3    Role: D/V
 Pārliecinieties, ka pēc incidenta analīze iekļauj modeļa pārtrenēšanas apsvērumus, drošības filtru atjauninājumus un mācībstundu integrāciju drošības kontrolēs.

---

### C12.5 Mākslīgā intelekta veiktspējas samazināšanās noteikšana

Uzraudzīt un noteikt AI modeļa veiktspējas un kvalitātes pasliktināšanos laika gaitā.

 #12.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka modeļa precizitāte, precizitāte, atgūšana un F1 rādītāji tiek nepārtraukti uzraudzīti un salīdzināti ar bāzes līmeņa sliekšņiem.
 #12.5.2    Level: 1    Role: D/V
 Pārbaudiet, vai datu novirzes noteikšana uzrauga ieejas sadalījuma izmaiņas, kas var ietekmēt modeļa veiktspēju.
 #12.5.3    Level: 2    Role: D/V
 Pārbaudiet, vai koncepcijas novirzes noteikšana atpazīst izmaiņas sakarā starp ievadiem un gaidītajiem izvadiem.
 #12.5.4    Level: 2    Role: D/V
 Pārbaudiet, vai veiktspējas pasliktināšanās izsauc automātiskus brīdinājumus un sāk modeļa pārmācīšanas vai nomaiņas darbplūsmas.
 #12.5.5    Level: 3    Role: V
 Pārbaudiet, vai degradācijas saknes cēloņu analīze korelē veiktspējas kritumus ar datu izmaiņām, infrastruktūras problēmām vai ārējiem faktoriem.

---

### C12.6 DAG vizualizācija un darba plūsmas drošība

Aizsargājiet darbplūsmas vizualizācijas sistēmas no informācijas noplūdes un manipulācijas uzbrukumiem.

 #12.6.1    Level: 1    Role: D/V
 Pārliecinieties, ka DAG vizualizācijas dati tiek attīrīti no sensitīvas informācijas pirms glabāšanas vai pārsūtīšanas.
 #12.6.2    Level: 1    Role: D/V
 Pārbaudiet, vai darba plūsmas vizualizācijas piekļuves kontroles nodrošina, ka tikai autorizēti lietotāji var skatīt aģenta lēmumu ceļus un pamatojuma pēdas.
 #12.6.3    Level: 2    Role: D/V
 Pārbaudiet, ka DAG datu integritāte ir aizsargāta ar kriptogrāfiskām parakstiem un viltojumu atklājošiem uzglabāšanas mehānismiem.
 #12.6.4    Level: 2    Role: D/V
 Pārbaudiet, vai darbplūsmas vizualizācijas sistēmas īsteno ievades validāciju, lai novērstu injekcijas uzbrukumus, izmantojot īpaši izstrādātus mezglu vai malu datus.
 #12.6.5    Level: 3    Role: D/V
 Pārliecinieties, ka reāllaika DAG atjauninājumi ir ātruma ierobežoti un validēti, lai novērstu pakalpojuma atteices (denial-of-service) uzbrukumus vizualizācijas sistēmām.

---

### C12.7 Proaktīvā drošības uzvedības uzraudzība

Drošības draudu atklāšana un novēršana, izmantojot proaktīvu aģentu uzvedības analīzi.

 #12.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai proaktīvas aģenta uzvedības ir drošības pārbaudītas pirms izpildes, integrējot riska novērtējumu.
 #12.7.2    Level: 2    Role: D/V
 Pārbaudiet, vai autonomās iniciatīvas izraisītāji ietver drošības konteksta novērtējumu un draudu ainavas analīzi.
 #12.7.3    Level: 2    Role: D/V
 Pārbaudiet, vai proaktīvās uzvedības modeļi tiek analizēti, ņemot vērā potenciālās drošības sekas un nevēlamās blakusparādības.
 #12.7.4    Level: 3    Role: D/V
 Pārliecinieties, ka drošības kritiski proaktīvi pasākumi prasa skaidras apstiprināšanas ķēdes ar audita ierakstiem.
 #12.7.5    Level: 3    Role: D/V
 Pārbaudiet, vai uzvedības anomāliju noteikšana identificē novirzes proaktīvo aģentu modeļos, kas var liecināt par pārkāpumu.

---

### Atsauces

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Cilvēka uzraudzība, atbildība un pārvaldība

### Vadības mērķis

Šajā nodaļā ir noteiktas prasības cilvēka uzraudzības uzturēšanai un skaidru atbildības ķēžu nodrošināšanai mākslīgā intelekta sistēmās, garantējot izskaidrojamību, pārredzamību un ētisku pārvaldību visā mākslīgā intelekta dzīvības ciklā.

---

### C13.1 Izslēgšanas slēdža un pārrakstīšanas mehānismi

Nodrošiniet izslēgšanas vai atgriešanas ceļus, ja tiek novērota mākslīgā intelekta sistēmas bīstama uzvedība.

 #13.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka pastāv manuāla izslēgšanas slēdzis, lai nekavējoties apturētu AI modeļa secināšanu un izvades.
 #13.1.2    Level: 1    Role: D
 Pārliecinieties, ka pārrakstīšanas vadības ir pieejamas tikai pilnvarotam personālam.
 #13.1.3    Level: 3    Role: D/V
 Pārbaudiet, vai atsaukšanas procedūras var atgriezties pie iepriekšējām modeļa versijām vai drošā režīma darbībām.
 #13.1.4    Level: 3    Role: V
 Pārliecinieties, ka pārrakstīšanas mehānismi tiek regulāri testēti.

---

### C13.2 Cilvēks cilpā lēmumu pārbaudes punkti

Prasīt cilvēka apstiprinājumu, kad likmes pārsniedz iepriekš noteiktos riska sliekšņus.

 #13.2.1    Level: 1    Role: D/V
 Pārbaudiet, vai augsta riska mākslīgā intelekta lēmumi pirms izpildes prasa skaidru cilvēka apstiprinājumu.
 #13.2.2    Level: 1    Role: D
 Pārliecinieties, ka riska sliekšņi ir skaidri definēti un automātiski aktivizē cilvēka pārskatīšanas darbplūsmas.
 #13.2.3    Level: 2    Role: D
 Pārliecinieties, ka laika jutīgām lēmumiem ir rezerves procedūras gadījumos, kad cilvēka apstiprinājumu nevar iegūt noteiktajos termiņos.
 #13.2.4    Level: 3    Role: D/V
 Pārbaudiet, vai eskalācijas procedūras nosaka skaidras pilnvaru līmeņus dažādiem lēmumu veidiem vai riska kategorijām, ja tas ir piemērojams.

---

### C13.3 Atbildības ķēde un pārskatāmība

Reģistrējiet operatora darbības un modeļa lēmumus.

 #13.3.1    Level: 1    Role: D/V
 Pārliecinieties, ka visas AI sistēmas lēmumu un cilvēku iejaukšanās tiek reģistrētas ar laika zīmēm, lietotāju identitātēm un lēmuma pamatojumu.
 #13.3.2    Level: 2    Role: D
 Pārliecinieties, ka revīzijas žurnāli nav iespējami maināmi un tajos ir iekļautas integritātes pārbaudes mehānismi.

---

### C13.4 Paskaidrojama Mākslīgā Intelekta Tehnikas

Virszemes iezīmju nozīmīgums, pretfaktiskie piemēri un lokālas skaidrošanas metodes.

 #13.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka mākslīgā intelekta sistēmas sniedz pamatizskaidrojumus par saviem lēmumiem cilvēkiem saprotamā formātā.
 #13.4.2    Level: 2    Role: V
 Pārbaudiet, vai paskaidrojumu kvalitāte ir validēta, izmantojot cilvēku novērtējuma pētījumus un metrikas.
 #13.4.3    Level: 3    Role: D/V
 Pārbaudiet, vai svarīguma vērtējumi vai atribūcijas metodes (SHAP, LIME utt.) ir pieejamas kritisku lēmumu pieņemšanai.
 #13.4.4    Level: 3    Role: V
 Pārbaudiet, vai kontrafaktu paskaidrojumi parāda, kā ievades varētu tikt modificētas, lai mainītu iznākumus, ja tas ir piemērojams lietošanas gadījumam un jomai.

---

### C13.5 Modeļa kartes un lietošanas atklājumi

Uzturiet modeļa kartes paredzētajai lietošanai, veiktspējas rādītājiem un ētiskiem apsvērumiem.

 #13.5.1    Level: 1    Role: D
 Pārliecinieties, ka modeļu kartes dokumentē paredzētos lietošanas gadījumus, ierobežojumus un zināmās kļūmju režīmus.
 #13.5.2    Level: 1    Role: D/V
 Pārliecinieties, ka veiktspējas rādītāji dažādos piemērojamos lietošanas gadījumos ir atklāti.
 #13.5.3    Level: 2    Role: D
 Pārbaudiet, vai ir dokumentēti un regulāri atjaunināti ētikas apsvērumi, aizspriedumu novērtējumi, taisnīguma izvērtējumi, apmācību datu raksturojumi un zināmie apmācību datu ierobežojumi.
 #13.5.4    Level: 2    Role: D/V
 Pārliecinieties, ka modeļu kartes tiek versiju kontrolētas un uzturētas visā modeļa dzīvotspējas ciklā ar izmaiņu izsekošanu.

---

### C13.6 Nenoteiktības kvantificēšana

Izplatīt pārliecības rādītājus vai entropijas mērus atbildēs.

 #13.6.1    Level: 1    Role: D
 Pārliecinieties, ka mākslīgā intelekta sistēmas savos rezultātos sniedz pārliecības rādītājus vai nenoteiktības mērus.
 #13.6.2    Level: 2    Role: D/V
 Pārbaudiet, vai nenoteiktības sliekšņi aktivizē papildu cilvēka pārskatu vai alternatīvas lēmumu pieņemšanas ceļus.
 #13.6.3    Level: 2    Role: V
 Pārliecinieties, ka nenoteiktības kvantifikācijas metodes ir kalibrētas un pārbaudītas, salīdzinot ar patiesajiem datiem.
 #13.6.4    Level: 3    Role: D/V
 Pārbaudiet, vai nenoteiktības izplatīšana tiek saglabāta vairāku soļu mākslīgā intelekta darba procesos.

---

### C13.7 Lietotājam redzamie pārredzamības ziņojumi

Nodrošināt regulārus atskatus par incidentiem, novirzēm un datu izmantošanu.

 #13.7.1    Level: 1    Role: D/V
 Pārbaudiet, vai datu lietošanas politikas un lietotāju piekrišanas pārvaldības prakses ir skaidri komunikētas ar ieinteresētajām pusēm.
 #13.7.2    Level: 2    Role: D/V
 Pārliecinieties, ka tiek veikta mākslīgā intelekta ietekmes izvērtēšana un rezultāti tiek iekļauti atskaitēs.
 #13.7.3    Level: 2    Role: D/V
 Pārbaudiet, vai regulāri publicētie caurspīdīguma ziņojumi atklāj AI incidentus un darbības metriku saprātīgā detalizācijā.

#### Atsauces

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Pielikums A: Vārdnīca

Šis visaptverošais glosārijs sniedz būtisku mākslīgā intelekta (MI), mašīnmācīšanās (MM) un drošības terminu definīcijas, kas tiek lietotas visā AISVS, lai nodrošinātu skaidrību un kopēju izpratni.
​
Pretenciozs paraugs: Ieejas dati, kas apzināti izveidoti, lai liktu mākslīgā intelekta modelim pieļaut kļūdu, bieži pievienojot smalkas perturbācijas, kuras cilvēkiem ir grūti pamanīt.
​
Pretendentprasme – Pretendentprasme mākslīgajā intelektā attiecas uz modeļa spēju saglabāt savu veiktspēju un pretoties apzināti veidotu, ļaunprātīgu ievades datu manipulācijām, kas paredzētas kļūdu izraisīšanai.
​
Aģents – AI aģenti ir programmatūras sistēmas, kas izmanto mākslīgo intelektu, lai sasniegtu mērķus un veiktu uzdevumus lietotāju vārdā. Tie demonstrē spriešanas, plānošanas un atmiņas spējas, kā arī ir noteikts autonomijas līmenis lēmumu pieņemšanai, mācībām un pielāgošanai.
​
Agentic AI: Mākslīgā intelekta sistēmas, kas spēj darboties ar zināmu autonomijas pakāpi, lai sasniegtu mērķus, bieži pieņemot lēmumus un veicot darbības bez tiešas cilvēka iejaukšanās.
​
Piekļuves kontrole, balstoties uz atribūtiem (ABAC): Piekļuves kontroles paradigma, kurā autorizācijas lēmumi tiek pieņemti, balstoties uz lietotāja, resursa, darbības un vides atribūtiem, kas tiek izvērtēti vaicājuma laikā.
​
Aizmugures durvju uzbrukums: datu indēšanas uzbrukuma veids, kurā modelis tiek apmācīts reaģēt noteiktā veidā uz konkrētiem aktivizētājiem, savukārt citādi tas uzvedas parasti.
​
Nostāja: Sistēmiski kļūdu AI modeļa rezultātos, kas var radīt negodīgas vai diskriminējošas sekas noteiktām grupām vai specifiskos kontekstos.
​
Priekšrocību izmantošana: uzbrukuma tehnika, kas izmanto zināmās aizspriedumu vājās vietas mākslīgā intelekta modeļos, lai manipulētu ar rezultātiem vai iznākumiem.
​
Cedar: Amazon politikas valoda un dzinējs smalki niansētām atļaujām, ko izmanto ABAC īstenošanai AI sistēmām.
​
Domāšanas ķēde: tehnika, kas uzlabo valodas modeļu spriešanas spējas, ģenerējot starpposma sprieduma soļus pirms galīgā atbildes izveides.
​
Izslēgmehānismi: mehānismi, kas automātiski aptur mākslīgā intelekta sistēmas darbību, ja tiek pārsniegti noteikti riska sliekšņa līmeņi.
​
Datu noplūde: nejauša sensitīvas informācijas atklāšana caur mākslīgā intelekta modeļa rezultātiem vai uzvedību.
​
Datu indesēšana: apzināta mācību datu bojāšana, lai kompromitētu modeļa integritāti, bieži vien, lai ievietotu aizmugures durvis vai pasliktinātu veiktspēju.
​
Differenciālā privātums – Differenciālā privātums ir matemātiski stingra sistēma statistiskas informācijas publiskošanai par datu kopām, vienlaikus aizsargājot atsevišķu datu subjektu privātumu. Tā ļauj datu turētājam koplietot grupas kopējos modeļus, ierobežojot informācijas noplūdi par konkrētiem indivīdiem.
​
Iegulti: blīvas vektoru reprezentācijas datiem (tekstam, attēliem utt.), kas uztver semantisko nozīmi augstdimensionālā telpā.
​
Izskaidrojams – AI izskaidrojamība ir AI sistēmas spēja sniegt cilvēkam saprotamus iemeslus savām lēmumiem un prognozēm, piedāvājot ieskatu tās iekšējā darbībā.
​
Paskaidrojama mākslīgā intelekta (XAI): mākslīgā intelekta sistēmas, kas izstrādātas, lai sniegtu cilvēkam saprotamus skaidrojumus par saviem lēmumiem un uzvedību, izmantojot dažādas metodes un ietvarus.
​
Federētā mācīšanās: Mašīnmācīšanās pieeja, kurā modeļi tiek apmācīti vairākās decentralizētās ierīcēs, kurās glabājas vietējie datu paraugi, nekādi nemainot pašu datus.
​
Drošības ierobežojumi: Ierobežojumi, kas īstenoti, lai novērstu mākslīgā intelekta sistēmu radīt kaitīgus, aizspriedumainus vai citādi nevēlamus rezultātus.
​
Halucinācija – AI halucinācija attiecas uz fenomenu, kad AI modelis ģenerē nepareizu vai maldinošu informāciju, kas balstīta nevis uz tā apmācības datiem vai faktisko realitāti.
​
Cilvēks cilpā (HITL): Sistēmas, kas izstrādātas, lai prasa cilvēka uzraudzību, pārbaudi vai iejaukšanos būtiskos lēmumu pieņemšanas punktos.
​
Infrastruktūra kā kods (IaC): infrastruktūras pārvaldība un izvietošana, izmantojot kodu, nevis manuālas procedūras, ļaujot veikt drošības skenēšanu un nodrošinot konsekventas izvietošanas.
​
Jailbreak: Metodes, ko izmanto, lai apietu drošības aizsardzību AI sistēmās, īpaši lielos valodas modeļos, lai radītu aizliegtu saturu.
​
Minimālo tiesību princips: drošības princips, kas nodrošina tikai minimālo nepieciešamo piekļuves tiesību piešķiršanu lietotājiem un procesiem.
​
LIME (Vietējā interpretējamā modeļa-neatkarīgās skaidrošanas metode): Tehnika, kas ļauj izskaidrot jebkura mašīnmācīšanās klasifikatora prognozes, tuvumā aproksimējot tos ar interpretējamu modeli.
​
Dalības informācijas uzbrukums: Uzbrukums, kura mērķis ir noteikt, vai konkrēts datu punkts tika izmantots mašīnmācīšanās modeļa apmācībai.
​
MITRE ATLAS: Mākslīgā intelekta sistēmu pretinieku draudu ainava; pretinieku taktiku un paņēmienu zināšanu bāze, kas vērsta pret AI sistēmām.
​
Modeļa karte – Modeļa karte ir dokuments, kas sniedz standartizētu informāciju par mākslīgā intelekta modeļa veiktspēju, ierobežojumiem, paredzēto lietojumu un ētiskajiem apsvērumiem, lai veicinātu caurspīdīgumu un atbildīgu mākslīgā intelekta izstrādi.
​
Modeļa ekstrakcija: uzbrukums, kurā pretinieks atkārtoti veic vaicājumus mērķa modelim, lai izveidotu funkcionāli līdzīgu kopiju bez atļaujas.
​
Modeļa apgriešana: Uzbrukums, kas mēģina rekonstruēt mācību datus, analizējot modeļa izvades rezultātus.
​
Modeļa dzīves cikla pārvaldība – AI modeļa dzīves cikla pārvaldība ir process, kurā tiek uzraudzītas visas AI modeļa dzīves fāzes, tai skaitā tā dizains, izstrāde, ieviešana, uzraudzība, uzturēšana un beigu izmantošanas pārtraukšana, lai nodrošinātu tā efektivitāti un atbilstību mērķiem.
​
Modeļa indes ieviešana: ievadīt ievainojamības vai slepenus piekļuves ceļus tieši modelī mācību procesa laikā.
​
Modeļa zādzība/Nozagšana: Proprietārā modeļa kopijas vai aptuvenas versijas izgūšana, izmantojot atkārtotus pieprasījumus.
​
Multi-agentu sistēma: sistēma, kas sastāv no vairākiem savstarpēji mijiedarbojošiem mākslīgā intelekta aģentiem, katram ar potenciāli atšķirīgām spējām un mērķiem.
​
OPA (Open Policy Agent): Atvērta koda politikas dzinējs, kas nodrošina vienotu politikas īstenošanu visā sistēmā.
​
Privātumu saglabājoša mašīnmācīšanās (PPML): tehnikas un metodes, lai apmācītu un izvietotu mašīnmācīšanās modeļus, vienlaikus aizsargājot apmācības datu privātumu.
​
Uzvednes injekcija: uzbrukums, kurā ļaunprātīgas instrukcijas tiek iegultas ievadēs, lai pārrakstītu modeļa paredzēto uzvedību.
​
RAG (Atsaukumu pastiprināta ģenerēšana): tehnika, kas uzlabo lielos valodas modeļus, izgūstot atbilstošu informāciju no ārējiem zināšanu avotiem pirms atbildes ģenerēšanas.
​
Red-Teaming: Praktika aktīvi testēt mākslīgā intelekta sistēmas, simulējot pretinieciski vērstas uzbrukumus, lai identificētu ievainojamības.
​
SBOM (Programmatūras materiālu saraksts): Formāls ieraksts, kas satur dažādu komponentu detalizētu informāciju un piegādes ķēdes attiecības, kas izmantotas programmatūras vai mākslīgā intelekta modeļu izstrādē.
​
SHAP (SHapley pievienojamās skaidrošanas): Spēļu teorijas pieeja, lai izskaidrotu jebkura mašīnmācīšanās modeļa rezultātu, aprēķinot katras iezīmes ieguldījumu prognozē.
​
Piegādes ķēdes uzbrukums: sistēmas kompromitēšana, mērķējot uz mazāk drošiem tās piegādes ķēdes elementiem, piemēram, trešo pušu bibliotēkām, datu kopām vai iepriekš apmācītiem modeļiem.
​
Pārneses mācīšanās: tehnika, kurā modelis, kas izstrādāts vienam uzdevumam, tiek atkārtoti izmantots kā sākumpunkts modelim otram uzdevumam.
​
Vektoru datubāze: specializēta datubāze, kas izstrādāta, lai glabātu augstdimensionālus vektorus (iegultnes) un veiktu efektīvas līdzīguma meklēšanas.
​
Trūkumu skenēšana: Automatizēti rīki, kas identificē zināmas drošības ievainojamības programmatūras komponentos, tostarp mākslīgā intelekta ietvaros un atkarībās.
​
Ūdenszīmju ievietošana: tehnikas, lai iebūvētu nemanāmus marķierus mākslīgā intelekta ģenerētā saturā, lai izsekotu tā izcelsmi vai noteiktu, ka to radījis mākslīgais intelekts.
​
Nulles dienas ievainojamība: iepriekš nezināma ievainojamība, ko uzbrucēji var izmantot, pirms izstrādātāji izveido un ievieš labojumu.

## Pielikums B: Atsauces

### TODO

## Pielikums C: Mākslīgā intelekta drošības pārvaldība un dokumentācija

### Mērķis

Šī pielikuma sadaļa sniedz pamatprasības organizatorisko struktūru, politiku un procesu izveidei, lai pārvaldītu mākslīgā intelekta drošību visā sistēmas dzīves ciklā.

---

### AC.1 Mākslīgā intelekta riska pārvaldības ietvara pieņemšana

Nodrošināt formālu ietvaru, lai identificētu, novērtētu un mazinātu mākslīgā intelekta specifiskos riskus visā sistēmas dzīves ciklā.

 #AC.1.1    Level: 1    Role: D/V
 Pārliecinieties, ka ir dokumentēta un ieviesta AI specifiska riska novērtēšanas metodoloģija.
 #AC.1.2    Level: 2    Role: D
 Pārliecinieties, ka riska novērtējumi tiek veikti svarīgos AI dzīves cikla posmos un pirms būtiskām izmaiņām.
 #AC.1.3    Level: 3    Role: D/V
 Pārbaudiet, vai riska pārvaldības sistēma atbilst noteiktajiem standartiem (piemēram, NIST AI RMF).

---

### AC.2 Mākslīgā intelekta drošības politika un procedūras

Noteikt un īstenot organizācijas standartus drošai mākslīgā intelekta izstrādei, izvietošanai un darbībai.

 #AC.2.1    Level: 1    Role: D/V
 Pārliecinieties, ka pastāv dokumentētas mākslīgā intelekta drošības politikas.
 #AC.2.2    Level: 2    Role: D
 Pārliecinieties, ka politikas tiek pārskatītas un atjauninātas vismaz reizi gadā un pēc būtiskām draudu ainavas izmaiņām.
 #AC.2.3    Level: 3    Role: D/V
 Pārbaudiet, vai politikas aptver visas AISVS kategorijas un piemērojamas normatīvās prasības.

---

### AC.3 Lomas un atbildība par Mākslīgā intelekta drošību

Nodrošiniet skaidru atbildību par mākslīgā intelekta drošību visā organizācijā.

 #AC.3.1    Level: 1    Role: D/V
 Pārliecinieties, ka AI drošības lomas un atbildības ir dokumentētas.
 #AC.3.2    Level: 2    Role: D
 Pārbaudiet, vai atbildīgajām personām ir atbilstoša drošības ekspertīze.
 #AC.3.3    Level: 3    Role: D/V
 Pārliecinieties, ka ir izveidota AI ētikas komiteja vai pārvaldības padome augsta riska AI sistēmām.

---

### AC.4 Ētiskās Mākslīgā Intelekta Vadlīniju Ievērošana

Nodrošiniet, ka AI sistēmas darbojas saskaņā ar izveidotajiem ētiskajiem principiem.

 #AC.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka pastāv ētikas vadlīnijas mākslīgā intelekta izstrādei un ieviešanai.
 #AC.4.2    Level: 2    Role: D
 Pārliecinieties, ka ir ieviesti mehānismi, lai atklātu un ziņotu par ētikas pārkāpumiem.
 #AC.4.3    Level: 3    Role: D/V
 Pārliecinieties, ka veikti regulāri ētiskie pārskati par izvietotajām mākslīgā intelekta sistēmām.

---

### AC.5 Mākslīgā intelekta normatīvās atbilstības uzraudzība

Uzturi apziņu un atbilstību mainīgajiem mākslīgā intelekta regulējumiem.

 #AC.5.1    Level: 1    Role: D/V
 Pārbaudiet, vai pastāv procesi, lai identificētu piemērojamos AI regulējumus.
 #AC.5.2    Level: 2    Role: D
 Pārliecinieties, ka tiek veikta atbilstības pārbaude visām reglamenta prasībām.
 #AC.5.3    Level: 3    Role: D/V
 Pārbaudiet, vai normatīvo aktu izmaiņas izsauc savlaicīgas pārbaudes un atjauninājumus mākslīgā intelekta sistēmās.

#### Atsauces

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Pielikums D: Mākslīgā intelekta atbalstīta drošas kodēšanas pārvaldība un verifikācija

### Mērķis

Šajā nodaļā tiek definētas pamatorganizatoriskās kontroles drošai un efektīvai mākslīgā intelekta atbalstītu koda veidošanas rīku izmantošanai programmatūras izstrādes procesā, nodrošinot drošību un izsekojamību visā programmatūras izstrādes dzīves ciklā (SDLC).

---

### AD.1 AI atbalstīts droša kodēšanas darba plūsma

Integrēt mākslīgā intelekta rīkus organizācijas drošas programmatūras izstrādes dzīves ciklā (SSDLC), nesamazinot esošo drošības barjeru efektivitāti.

 #AD.1.1    Level: 1    Role: D/V
 Pārbaudiet, vai dokumentētā darba plūsma apraksta, kad un kā mākslīgā intelekta rīki var ģenerēt, refaktorēt vai pārskatīt kodu.
 #AD.1.2    Level: 2    Role: D
 Pārbaudiet, vai darba plūsma atbilst katrai SSDLC fāzei (dizains, ieviešana, koda pārskatīšana, testēšana, izvietošana).
 #AD.1.3    Level: 3    Role: D/V
 Pārbaudiet, vai metrikas (piemēram, ievainojamības blīvums, vidējais laiks līdz atklāšanai) tiek vāktas par AI radīto kodu un salīdzinātas ar tikai cilvēku izstrādātajiem etaloniem.

---

### AD.2 AI rīka kvalifikācija un draudu modelēšana

Nodrošiniet, ka AI kodēšanas rīki tiek novērtēti attiecībā uz drošības iespējām, riskiem un piegādes ķēdes ietekmi pirms to ieviešanas.

 #AD.2.1    Level: 1    Role: D/V
 Pārbaudiet, vai katram AI rīkam izstrādātajam draudu modelim ir identificēti ļaunprātīgas izmantošanas, modeļa inversijas, datu noplūdes un atkarību ķēdes riski.
 #AD.2.2    Level: 2    Role: D
 Pārliecinieties, ka rīku novērtējumos ir iekļauta jebkuru lokālo komponentu statiskā/dinamiskā analīze un SaaS galapunktu (TLS, autentifikācija/autorizācija, žurnālu veidošana) novērtējums.
 #AD.2.3    Level: 3    Role: D/V
 Pārliecinieties, ka novērtējumi tiek veikti saskaņā ar atzītu sistēmu un tiek atkārtoti pēc būtiskām versiju izmaiņām.

---

### AD.3 Droša komandu un konteksta pārvaldība

Novērst slepenās, patentētā koda un personas datu noplūdi, veidojot uzvednes vai kontekstus mākslīgā intelekta modeļiem.

 #AD.3.1    Level: 1    Role: D/V
 Pārbaudiet, vai rakstiskās vadlīnijas aizliedz nosūtīt slepenus datus, piekļuves informāciju vai klasificētu informāciju ievades vaicājumos.
 #AD.3.2    Level: 2    Role: D
 Pārbaudiet, vai tehniskie kontroles mehānismi (klienta pusē veiktā redakcija, apstiprinātie konteksta filtri) automātiski noņem sensitīvus artefaktus.
 #AD.3.3    Level: 3    Role: D/V
 Pārbaudiet, vai uzvednes un atbildes tiek tokenizētas, šifrētas pārsūtīšanas laikā un glabāšanas laikā, kā arī vai to glabāšanas periodi atbilst datu klasifikācijas politikai.

---

### AD.4 AI Ģenerēta koda validācija

Atklājiet un novēršiet AI radītās ievainojamības pirms koda apvienošanas vai izvietošanas.

 #AD.4.1    Level: 1    Role: D/V
 Pārliecinieties, ka mākslīgi ģenerētais kods vienmēr tiek pakļauts cilvēka izstrādātāja pārskatam.
 #AD.4.2    Level: 2    Role: D
 Pārliecinieties, ka automatizētie skeneri (SAST/IAST/DAST) tiek palaisti katrā pieprasījumā apvienošanai, kas satur mākslīgā intelekta ģenerētu kodu, un bloķējiet apvienošanu kritisku problēmu gadījumā.
 #AD.4.3    Level: 3    Role: D/V
 Pārbaudiet, vai diferenciālā fuzz testēšana vai īpašību balstītie testi pierāda drošības kritiskās darbības (piemēram, ievades validācija, autorizācijas loģika).

---

### AD.5 Koda ieteikumu paskaidrojamība un izsekojamība

Nodrošiniet auditoriem un izstrādātājiem ieskatu par to, kāpēc tika izteikts ieteikums un kā tas attīstījās.

 #AD.5.1    Level: 1    Role: D/V
 Pārliecinieties, ka pieprasījuma/atbildes pāri tiek reģistrēti ar apņemšanās ID.
 #AD.5.2    Level: 2    Role: D
 Pārbaudiet, vai izstrādātāji var parādīt modeļa atsauces (apmācības fragmentus, dokumentāciju), kas pamato ieteikumu.
 #AD.5.3    Level: 3    Role: D/V
 Pārliecinieties, ka skaidrojuma pārskati tiek glabāti kopā ar dizaina artefaktiem un atsaukti drošības apskatos, nodrošinot ISO/IEC 42001 izsekojamības principu ievērošanu.

---

### AD.6 Nepārtraukta atsauksmju saņemšana un modeļa precīza regulēšana

Uzlabot modeļa drošības sniegumu laikam ritot, vienlaikus novēršot negatīvu novirzi.

 #AD.6.1    Level: 1    Role: D/V
 Pārliecinieties, ka izstrādātāji var atzīmēt nedrošus vai neatbilstošus ieteikumus, un ka šīs atzīmes tiek izsekotas.
 #AD.6.2    Level: 2    Role: D
 Pārliecinieties, ka apkopotā atgriezeniskā saite informē periodisku smalko pielāgošanu vai izgūšanas pastiprinātu ģenerēšanu ar pārbaudītiem droša kodēšanas korpusiem (piemēram, OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Pārliecinieties, ka slēgtas cilpas novērtēšanas sistēma veic regresijas testus pēc katras papildus apmācības; drošības metrikai jāatbilst vai jāpārsniedz iepriekšējās robežvērtības pirms izvietošanas.

---

#### Atsauces

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Pielikums E: Piemēru rīki un ietvari

### Mērķis

Šī nodaļa sniedz piemērus rīkiem un ietvariem, kas var atbalstīt noteiktas AISVS prasības īstenošanu vai izpildi. Tos nevajadzētu uzskatīt par AISVS komandas vai OWASP GenAI Security projekta ieteikumiem vai atbalstu.

---

### AE.1 Apmācību datu pārvaldība un aizspriedumu vadība

Rīki, kas tiek izmantoti datu analītikai, pārvaldībai un aizspriedumu pārvaldībai.

 #AE.1.1    Section: 1.1
 Datu inventāra rīki: Datu inventāra pārvaldības rīki, piemēram...
 #AE.1.2    Section: 1.2
 Šifrēšana pārvietošanas laikā Izmantojiet TLS HTTPS bāzētām lietotnēm, ar tādiem rīkiem kā openSSL un Python's`ssl` bibliotēka.

---

### AE.2 Lietotāja ievades validācija

Rīki lietotāju ievades apstrādei un validācijai.

 #AE.2.1    Section: 2.1
 Rīki pret aicinājumu injekciju: izmantojiet aizsargjoslu rīkus, piemēram, NVIDIA NeMo vai Guardrails AI.

---

