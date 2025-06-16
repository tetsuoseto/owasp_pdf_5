## Priekis

### Apie standartą

Dirbtinio intelekto saugumo patikros standartas (AISVS) yra bendruomenės pagrindu sukurtas saugumo reikalavimų katalogas, kurį duomenų mokslininkai, MLOps inžinieriai, programinės įrangos architektai, kūrėjai, testuotojai, saugumo specialistai, įrankių pardavėjai, reguliatoriai ir vartotojai gali naudoti patikimų dirbtiniu intelektu paremtų sistemų ir programų projektavimui, kūrimui, testavimui ir patikrinimui. Jis suteikia bendrą kalbą saugumo valdymo priemonių nustatymui per visą DI gyvavimo ciklą – nuo duomenų rinkimo ir modelio kūrimo iki diegimo ir nuolatinio stebėjimo – kad organizacijos galėtų matuoti ir gerinti savo DI sprendimų atsparumą, privatumo apsaugą ir saugumą.

### Autorių teisės ir licencija

Versija 0.1 (Pirmasis viešas juodraštis - vykdomas darbas), 2025  

![license](images/license.png)
Autorių teisės © 2025 AISVS projekto.  

Išleista pagalCreative Commons Attribution‑ShareAlike 4.0 International License.
Bet kokiam pakartotiniam naudojimui ar platinimui turite aiškiai perduoti kitiems šio darbo licencijos sąlygas.

### Projekto vadovai

Jim Manico
Aras "Russ" Memisyazici

### Indėliotojai ir Recenzentai

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS yra visiškai naujas standartas, sukurtas specialiai spręsti unikalius dirbtinio intelekto sistemų saugumo iššūkius. Nors jis remiasi platesnėmis geriausios saugumo praktikos gairėmis, kiekvienas AISVS reikalavimas buvo sukurtas nuo pagrindų, atsižvelgiant į DI grėsmių kraštovaizdį, ir siekiant padėti organizacijoms kurti saugesnius, atsparesnius DI sprendimus.

## Įžanga

Sveiki atvykę į dirbtinio intelekto saugumo patvirtinimo standartą (AISVS) 1.0 versija!

### Įvadas

AISVS, įkurta 2025 m. bendruomenės bendradarbiavimo pastangomis, apibrėžia saugumo reikalavimus, kuriuos reikia atsižvelgti projektuojant, kuriant, diegiant ir valdant modernius dirbtinio intelekto modelius, srautus ir dirbtiniu intelektu pagrįstas paslaugas.

AISVS v1.0 atspindi savo projekto vadovų, darbo grupės ir plačiosios bendruomenės narių bendrą darbą, siekiant sukurti pragmatišką, išbandomą AI sistemų saugumo pagrindą.

Mūsų tikslas su šiuo leidimu yra padaryti AISVS paprastą priimti, tuo pačiu išlaikant griežtą dėmesį jos apibrėžtam veikimo srities ribojimui ir sprendžiant sparčiai kintančią unikalią AI rizikos aplinką.

### Pagrindiniai AISVS 1.0 versijos tikslai

1.0 versija bus sukurta remiantis keliais pagrindiniais principais.

#### Aiškiai apibrėžtas taikymo sritis

Kiekviena reikalavimas turi atitikti AISVS pavadinimą ir misiją:

Dirbtinis intelektas – valdikliai veikia AI/ML sluoksnyje (duomenys, modelis, duomenų apdorojimo grandinė arba išvedimas) ir yra AI specialistų atsakomybė.
Sauga – Reikalavimai tiesiogiai mažina nustatytas saugumo, privatumo ar saugos rizikas.
Verifikavimas – kalba parašyta taip, kad atitiktis būtų galima objektyviai patikrinti.
Standartas – skyriai laikosi nuoseklios struktūros ir terminologijos, kad sudarytų nuoseklią nuorodą.
​
---

Laikydamosi AISVS, organizacijos gali sistemingai įvertinti ir sustiprinti savo DI sprendimų saugumo lygį, skatinant saugios DI inžinerijos kultūrą.

## Naudojant AISVS

Dirbtinio intelekto saugumo patikros standartas (AISVS) apibrėžia saugumo reikalavimus moderniosioms DI programėlėms ir paslaugoms, daugiausia dėmesio skiriant aspektams, kuriuos kontroliuoja programėlių kūrėjai.

AISVS yra skirtas visiems, kurie kuria arba vertina dirbtinio intelekto programų saugumą, įskaitant kūrėjus, architektus, saugumo inžinierius ir auditorius. Šiame skyriuje pristatoma AISVS struktūra ir naudojimas, įskaitant jos patikros lygius ir numatytus naudojimo atvejus.

### Dirbtinio intelekto saugumo tikrinimo lygiai

AISVS apibrėžia tris augančio lygio saugumo patikros lygius. Kiekvienas lygis praplečia ir sudėtingina patikros procesą, leidžiant organizacijoms pritaikyti savo saugumo poziciją prie jų dirbtinio intelekto sistemų rizikos lygio.

Organizacijos gali pradėti nuo 1 lygio ir palaipsniui pereiti prie aukštesnių lygių, kai didėja saugumo brandumas ir grėsmių poveikis.

#### Lygmenų apibrėžimas

Kiekvienas reikalavimas AISVS v1.0 yra priskirtas vienam iš šių lygių:

 1 lygio reikalavimai

1 lygis apima pačius svarbiausius ir pagrindinius saugumo reikalavimus. Jie orientuoti į bendrų atakų, kurios nepriklauso nuo kitų išankstinių sąlygų ar pažeidžiamumų, užkirtimą. Dauguma 1 lygio kontrolės priemonių yra arba paprastai įgyvendinamos, arba pakankamai svarbios, kad pateisintų pastangas.

 2 lygio reikalavimai

2 lygis apima sudėtingesnius arba rečiau pasitaikančius išpuolius, taip pat sluoksniuotas gynybas nuo plačiai paplitusių grėsmių. Šie reikalavimai gali apimti sudėtingesnę logiką arba būti skirti konkretiems išpuolių išankstiniams sąlygoms.

 3 lygio reikalavimai

3 lygis apima valdymo priemones, kurios paprastai yra sunkiau įgyvendinamos arba taikomos tam tikrose situacijose. Jos dažnai atspindi gynybos gilumo mechanizmus arba sprendimus prieš specifinius, taikinius ar didelės sudėtingumo atakas.

#### Rolė (D/V)

Kiekvienas AISVS reikalavimas yra pažymėtas pagal pagrindinę auditoriją:

D – Reikalavimai, orientuoti į kūrėjus
V – Reikalavimai, orientuoti į tikrintojus/auditorius
D/V – Svarbu tiek kūrėjams, tiek patikrintojams

## C1 Mokymo duomenų valdymas ir šališkumo valdymas

### Valdymo tikslas

Mokymo duomenys turi būti gaunami, tvarkomi ir prižiūrimi taip, kad būtų išsaugota kilmė, saugumas, kokybė ir teisingumas. Tai atitinka teisines pareigas ir sumažina šališkumo, apsinuodijimo ar privatumo pažeidimų riziką viso DI gyvavimo ciklo metu.

---

### C1.1 Mokymo duomenų kilmė

Laikykite patikrinamą visų duomenų rinkinių inventorių, priimkite tik patikimus šaltinius ir fiksuokite kiekvieną pakeitimą, kad būtų užtikrintas audito galimumas.

 #1.1.1    Level: 1    Role: D/V
 Patikrinkite, ar yra palaikomas atnaujintas kiekvieno mokymo duomenų šaltinio (kilmė, atsakingas asmuo/savininkas, licencija, surinkimo metodas, numatyti naudojimo apribojimai ir apdorojimo istorija) inventorius.
 #1.1.2    Level: 1    Role: D/V
 Patikrinkite, ar leidžiami tik duomenų rinkiniai, patikrinti dėl kokybės, atstovavimo, etinio šaltinio ir licencijų atitikties, sumažinant apsinuodijimo, įterptos šališkumo ir intelektinės nuosavybės pažeidimų riziką.
 #1.1.3    Level: 1    Role: D/V
 Patikrinkite, ar duomenų minimizavimas yra taikomas, kad nebūtų įtraukti nereikalingi ar jautrūs atributai.
 #1.1.4    Level: 2    Role: D/V
 Patikrinkite, ar visi duomenų rinkinio pakeitimai yra patvirtinami pagal registruojamą patvirtinimo darbo eigą.
 #1.1.5    Level: 2    Role: D/V
 Patikrinkite, ar ženklinimo/žymėjimo kokybė užtikrinama peržiūrėtojų kryžminiais patikrinimais arba susitarimu.
 #1.1.6    Level: 2    Role: D/V
 Patikrinkite, ar svarbiems mokymo duomenų rinkiniams yra palaikomos „duomenų kortelės“ arba „duomenų rinkinių techninės specifikacijos“, kurios detaliai aprašo charakteristikas, motyvus, sudėtį, rinkimo procesus, išankstinį apdorojimą bei rekomenduojamus ar nerekomenduojamus panaudojimo būdus.

---

### C1.2 Mokymo duomenų saugumas ir integralumas

Apribokite prieigą, užšifruokite duomenis ramybės būsenoje ir perdavimo metu, taip pat patikrinkite vientisumą, kad užkirstumėte kelią klastojimui ar vagystei.

 #1.2.1    Level: 1    Role: D/V
 Patikrinkite, ar prieigos kontrolės saugo saugyklas ir duomenų srautus.
 #1.2.2    Level: 2    Role: D/V
 Patikrinkite, ar duomenų rinkiniai yra užšifruoti perduodant, o visai jautriai ar asmeniškai identifikuojamai informacijai (PII) – ramybės būsenoje, naudojant pramonės standartinius kriptografinius algoritmus ir raktų valdymo praktikas.
 #1.2.3    Level: 2    Role: D/V
 Patikrinkite, ar naudojami kriptografiniai hešai arba skaitmeniniai parašai duomenų vientisumui užtikrinti saugojimo ir perdavimo metu, taip pat ar taikomos automatizuotos anomalijų aptikimo technikos, skirtos apsisaugoti nuo neleistinų modifikacijų ar duomenų korupcijos, įskaitant taikinius duomenų užnuodymo atvejus.
 #1.2.4    Level: 3    Role: D/V
 Patikrinkite, ar duomenų rinkinio versijos yra sekamos, kad būtų galima atlikti grąžinimą atgal.
 #1.2.5    Level: 2    Role: D/V
 Patikrinkite, ar pasenę duomenys yra saugiai ištrinami arba anonimizuojami laikantis duomenų saugojimo politikos, teisinių reikalavimų ir siekiant sumažinti atakos paviršių.

---

### C1.3 Atstovavimo pilnumas ir sąžiningumas

Aptikti demografinius šališkumus ir taikyti mažinimo priemones, kad modelio klaidų lygiai būtų teisingi tarp grupių.

 #1.3.1    Level: 1    Role: D/V
 Patikrinkite, ar duomenų rinkiniai yra profiliuojami dėl atstovavimo disbalanso ir galimų šališkumų pagal teisės apsaugotus atributus (pvz., rasė, lytis, amžius) ir kitas etiškai jautrias savybes, susijusias su modelio taikymo sritimi (pvz., socioekonominė padėtis, vietovė).
 #1.3.2    Level: 2    Role: D/V
 Patikrinkite, ar nustatyti šališkumai yra sušvelninti dokumentuotomis strategijomis, tokiomis kaip duomenų subalansavimas, taikomas didinimas, algoritminių koregavimų taikymas (pvz., išankstinis apdorojimas, procesavimo metu arba po apdorojimo technikos) arba svorių perskaičiavimas, ir įvertinkite šių priemonių poveikį tiek teisingumui, tiek bendram modelio našumui.
 #1.3.3    Level: 2    Role: D/V
 Patikrinkite, ar po mokymo modelio teisingumo metrikos yra įvertintos ir užfiksuotos.
 #1.3.4    Level: 3    Role: D/V
 Patikrinkite, ar gyvenimo ciklo šališkumo valdymo politika priskiria atsakinguosius asmenis ir apibrėžia peržiūros dažnumą.

---

### C1.4 Mokymo duomenų ženklinimo kokybė, vientisumas ir saugumas

Apsaugokite etiketes šifravimu ir reikalaukite dvigubo peržiūrėjimo kritinėms klasėms.

 #1.4.1    Level: 2    Role: D/V
 Užtikrinkite, kad ženklinimo/anuotacijos kokybė būtų garantuota aiškiomis gairėmis, peržiūrėtojų kryžminiais patikrinimais, sutarimo mechanizmais (pvz., stebint tarpanuotrautojų sutarimą) ir apibrėžtais procesais skirtumams spręsti.
 #1.4.2    Level: 2    Role: D/V
 Patikrinkite, ar kriptografiniai hešai arba skaitmeniniai parašai yra pritaikyti etiketės artefaktams, siekiant užtikrinti jų integralumą ir autentiškumą.
 #1.4.3    Level: 2    Role: D/V
 Patikrinkite, ar žymėjimo sąsajos ir platformos užtikrina tvirtą prieigos kontrolę, palaiko pažeidimus atskleidžiančius audito žurnalus apie visas žymėjimo veiklas ir saugo nuo neautorizuotų pakeitimų.
 #1.4.4    Level: 3    Role: D/V
 Patikrinkite, ar saugumo, apsaugos ar sąžiningumo požiūriu svarbūs etikečių ženklinimai (pvz., toksiško turinio, kritinių medicininių išvadų nustatymas) privalo būti nepriklausomai peržiūrimi dviem asmenimis arba turi ekvivalentinę stiprią patikrą.
 #1.4.5    Level: 2    Role: D/V
 Patikrinkite, ar jautri informacija (įskaitant asmens identifikavimo duomenis) netyčia užfiksuota ar būtinai esanti etikėtėse yra užmaskuota, pseudonimizuota, anonimizuota arba užšifruota tiek saugojimo, tiek perdavimo metu, vadovaujantis duomenų minimizavimo principais.
 #1.4.6    Level: 2    Role: D/V
 Patikrinkite, ar ženklinimo vadovai ir instrukcijos yra išsamūs, valdomi versijų ir peržiūrėti kolegų.
 #1.4.7    Level: 2    Role: D/V
 Patikrinkite, ar duomenų schemos (įskaitant etikečių schemas) yra aiškiai apibrėžtos ir valdomos versijų tvarka.
 #1.8.2    Level: 2    Role: D/V
 Patikrinkite, ar perduoti ar minios pagalba atliekami žymėjimo darbo srautai apima technines/procedūrines apsaugos priemones, užtikrinančias duomenų konfidencialumą, vientisumą, žymių kokybę ir užkertančias kelią duomenų nutekėjimui.

---

### C1.5 Mokymo duomenų kokybės užtikrinimas

Sujunkite automatizuotą tikrinimą, rankinius atsitiktinius patikrinimus ir registruotą taisymą, siekiant užtikrinti duomenų rinkinio patikimumą.

 #1.5.1    Level: 1    Role: D
 Patikrinkite, ar automatizuoti testai fiksuoja formato klaidas, nulinius duomenis ir etikečių poslinkius kiekvieno įvedimo ar reikšmingos transformacijos metu.
 #1.5.2    Level: 1    Role: D/V
 Patikrinkite, ar nesėkmingi duomenų rinkiniai yra izoliuoti su audito takais.
 #1.5.3    Level: 2    Role: V
 Patikrinkite, ar domeno ekspertų rankiniai patikrinimai apima statistiškai reikšmingą imtį (pvz., ≥1 % arba 1 000 pavyzdžių, priklausomai, kuris didesnis, arba kaip nustato rizikos vertinimas), siekiant nustatyti subtilias kokybės problemas, kurios nepastebimos automatizavimo metu.
 #1.5.4    Level: 2    Role: D/V
 Patikrinkite, ar pataisymo veiksmai yra pridėti prie kilmės įrašų.
 #1.5.5    Level: 2    Role: D/V
 Patikrinkite, ar kokybės vartai blokuoja žemesnės kokybės duomenų rinkinius, nebent būtų patvirtintos išimtys.

---

### C1.6 Duomenų užnuodijimo aptikimas

Taikyti statistinį anomalijų nustatymą ir izoliacijos darbo eigas, kad sustabdytų priešiškus įterpimus.

 #1.6.1    Level: 2    Role: D/V
 Patikrinkite, ar anomalijų aptikimo metodai (pvz., statistiniai metodai, netipinių atvejų nustatymas, įterpimų analizė) taikomi treniruočių duomenims įvedimo metu ir prieš pagrindinius treniruočių procesus, siekiant nustatyti galimus duomenų užteršimo išpuolius arba netyčinę duomenų korupciją.
 #1.6.2    Level: 2    Role: D/V
 Patikrinkite, ar pažymėti pavyzdžiai sukelia rankinį peržiūrėjimą prieš mokymą.
 #1.6.3    Level: 2    Role: V
 Patikrinkite, ar rezultatai įtraukiami į modelio saugumo bylą ir informuoja apie nuolatinę grėsmių žvalgybą.
 #1.6.4    Level: 3    Role: D/V
 Patikrinkite, ar aptikimo logika yra atnaujinta su nauja grėsmių informacija.
 #1.6.5    Level: 3    Role: D/V
 Patikrinkite, ar internetinio mokymosi srautai stebi pasiskirstymo pakitimus.
 #1.6.6    Level: 3    Role: D/V
 Patikrinkite, ar konkrečios gynybos priemonės nuo žinomų duomenų užteršimo atakų tipų (pvz., etikečių apvertimas, užpakalinio durų užtaisymo įterpimas, įtakingų atvejų atakos) yra apsvarstytos ir įgyvendintos atsižvelgiant į sistemos rizikos profilį ir duomenų šaltinius.

---

### C1.7 Vartotojo duomenų naikinimas ir sutikimo laikymosi kontrolė

Gerbkite ištrynimo ir sutikimo atšaukimo užklausas visuose duomenų rinkiniuose, atsarginėse kopijose ir išvestiniuose artefaktuose.

 #1.7.1    Level: 1    Role: D/V
 Patikrinkite, ar ištrynimo darbo eiga pašalina pirminius ir išvestinius duomenis bei įvertinkite modelio poveikį, taip pat užtikrinkite, kad paveiktų modelių poveikis būtų įvertintas ir, jei reikia, sprendžiamas (pvz., perkvalifikavimu arba perkoregavimu).
 #1.7.2    Level: 2    Role: D
 Patikrinkite, ar yra įdiegtos priemonės vartotojo sutikimo (ir jo atšaukimo) apimčiai ir būsenai sekti bei gerbti dėl duomenų, naudojamų mokymui, ir ar sutikimas yra patvirtinamas prieš įtraukiant duomenis į naujus mokymo procesus arba reikšmingus modelio atnaujinimus.
 #1.7.3    Level: 2    Role: V
 Patikrinkite, ar darbo eiga yra testuojama kasmet ir įrašoma į žurnalą.

---

### C1.8 Tiekimo grandinės saugumas

Patikrinkite išorinius duomenų tiekėjus ir patvirtinkite duomenų vientisumą per autentifikuotus, užšifruotus kanalus.

 #1.8.1    Level: 2    Role: D/V
 Patikrinkite, ar trečiųjų šalių duomenų tiekėjai, įskaitant iš anksto apmokytų modelių tiekėjus ir išorinius duomenų rinkinius, praeina saugumo, privatumo, etiško tiekimo ir duomenų kokybės patikrinimus prieš integruojant jų duomenis ar modelius.
 #1.8.2    Level: 1    Role: D
 Patikrinkite, ar išoriniai pervedimai naudoja TLS/autentifikavimą ir vientisumo patikrinimus.
 #1.8.3    Level: 2    Role: D/V
 Patikrinkite, ar aukštos rizikos duomenų šaltiniai (pvz., atviro kodo duomenų rinkiniai su nežinoma kilme, nepatikrinti tiekėjai) prieš naudojimą jautriose programose gauna išplėstinį patikrinimą, pvz., analizes aptvertose aplinkose, išsamius kokybės/šališkumo patikrinimus ir nukreiptą apsaugą nuo duomenų klastojimo.
 #1.8.4    Level: 3    Role: D/V
 Patikrinkite, ar iš trečiųjų šalių gauti iš anksto apmokyti modeliai yra įvertinti dėl įterptų šališkumų, galimų galinių durų, jų architektūros vientisumo ir pradinio mokymo duomenų kilmės prieš atliekant tolesnį pritaikymą arba diegimą.

---

### C1.9 Priešininkų pavyzdžių aptikimas

Įgyvendinkite priemones mokymo fazėje, tokias kaip priešiškas mokymas, siekiant pagerinti modelio atsparumą priešiškiems pavyzdžiams.

 #1.9.1    Level: 3    Role: D/V
 Patikrinkite, ar taikomos tinkamos gynybos priemonės, tokios kaip priešininkų mokymas (naudojant sugeneruotus priešininkų pavyzdžius), duomenų praplėtimas su perturbuotais įėjimais arba patikimos optimizacijos metodai, ir ar jos yra pritaikytos bei paruoštos atitinkamiems modeliams, remiantis rizikos vertinimu.
 #1.9.2    Level: 2    Role: D/V
 Įsitikinkite, kad jei naudojamas priešiškas mokymas, priešų duomenų rinkinių generavimas, valdymas ir versijų kontrolė yra dokumentuojami ir prižiūrimi.
 #1.9.3    Level: 3    Role: D/V
 Patikrinkite, ar įvertinamas, dokumentuojamas ir stebimas priešinimosi priešiškam triukšmui mokymo poveikis modeliui (tiek tvarkingų, tiek priešiškų duomenų atžvilgiu) ir sąžiningumo metrikoms.
 #1.9.4    Level: 3    Role: D/V
 Patikrinkite, ar priešiško mokymo ir atsparumo strategijos yra periodiškai peržiūrimos ir atnaujinamos, siekiant atsispirti kintančioms priešiškų atakų technikoms.

---

### C1.10 Duomenų kilmė ir atsekamumas

Sekite kiekvieno duomenų taško visą kelionę nuo šaltinio iki modelio įvesties, siekiant tikrinamumo ir incidentų reagavimo.

 #1.10.1    Level: 2    Role: D/V
 Patikrinkite, ar kiekvieno duomenų taško kilmė, įskaitant visas transformacijas, papildymus ir sujungimus, yra įrašyta ir gali būti atkurta.
 #1.10.2    Level: 2    Role: D/V
 Patikrinkite, ar kilmės įrašai yra nekeičiamo formato, saugiai saugomi ir prieinami audito ar tyrimų tikslams.
 #1.10.3    Level: 2    Role: D/V
 Patikrinkite, ar šakninių duomenų sekimas apima tiek žalius, tiek sintetinius duomenis.

---

### C1.11 Sintetiniai duomenų valdymas

Užtikrinkite, kad sintetiniai duomenys būtų tinkamai tvarkomi, sužymėti ir įvertinti rizikos požiūriu.

 #1.11.1    Level: 2    Role: D/V
 Patikrinkite, ar visa sintetika duomenys yra aiškiai pažymėti ir atskiriami nuo tikrųjų duomenų visame duomenų apdorojimo procese.
 #1.11.2    Level: 2    Role: D/V
 Patikrinkite, ar generavimo procesas, parametrai ir numatytas sintetinių duomenų naudojimas yra dokumentuoti.
 #1.11.3    Level: 2    Role: D/V
 Patikrinkite, ar sintetiniai duomenys yra įvertinti dėl šališkumo, privatumo nutekėjimo ir atstovavimo problemų prieš naudojimą mokymui.

---

### C1.12 Duomenų prieigos stebėjimas ir anomalijų nustatymas

Stebėkite ir signalizuokite apie neįprastą prieigą prie mokymo duomenų, siekiant aptikti vidinius grėsmes arba duomenų nutekėjimą.

 #1.12.1    Level: 2    Role: D/V
 Patikrinkite, ar visi duomenų mokymo prieigos veiksmai yra užfiksuoti, įskaitant naudotoją, laiką ir veiksmą.
 #1.12.2    Level: 2    Role: D/V
 Patikrinkite, ar prieigos žurnalai reguliariai peržiūrimi dėl neįprastų modelių, pavyzdžiui, didelių eksportų ar prieigos iš naujų vietų.
 #1.12.3    Level: 2    Role: D/V
 Patikrinkite, ar įspėjimai generuojami dėl įtartinų prieigos įvykių ir ar jie yra nedelsiant tiriami.

---

### C1.13 Duomenų saugojimo ir galiojimo nutraukimo politikos

Apibrėžkite ir taikykite duomenų saugojimo laikotarpius, kad sumažintumėte nereikalingą duomenų saugojimą.

 #1.13.1    Level: 1    Role: D/V
 Patikrinkite, ar visiems mokymo duomenų rinkiniams yra apibrėžti aiškūs saugojimo terminai.
 #1.13.2    Level: 2    Role: D/V
 Patikrinkite, ar duomenų rinkiniai automatiškai pasibaigia, trinami arba peržiūrimi dėl trynimo pasibaigus jų gyvenimo ciklui.
 #1.13.3    Level: 2    Role: D/V
 Patikrinkite, ar saugojimo ir šalinimo veiksmai yra registruojami ir tikrinami.

---

### C1.14 Reguliavimo ir jurisdikcijos atitiktis

Užtikrinkite, kad visi mokymo duomenys atitiktų taikomus įstatymus ir nuostatas.

 #1.14.1    Level: 2    Role: D/V
 Patikrinkite, ar duomenų lokalizacijos ir tarpvalstybinio perdavimo reikalavimai yra nustatyti ir vykdomi visoms duomenų rinkmenoms.
 #1.14.2    Level: 2    Role: D/V
 Patikrinkite, ar sektoriui specifiniai reguliavimai (pvz., sveikatos priežiūra, finansai) yra nustatyti ir sprendžiami duomenų tvarkyme.
 #1.14.3    Level: 2    Role: D/V
 Patikrinkite, ar atitiktis galiojantiems privatumo įstatymams (pvz., GDPR, CCPA) yra dokumentuota ir reguliariai peržiūrima.

---

### C1.15 Duomenų vandens ženklinimas ir pirštų atspaudų žymėjimas

Aptikti neleistinį nuosavybės ar jautrių duomenų pakartotinį naudojimą arba nutekėjimą.

 #1.15.1    Level: 3    Role: D/V
 Patikrinkite, ar duomenų rinkiniai arba jų pogrupiai, jei įmanoma, yra pažymėti vandens ženklais arba pirštų atspaudais.
 #1.15.2    Level: 3    Role: D/V
 Patvirtinkite, kad vandens ženklinimo/pažymėjimo metodai nesukelia šališkumo ar privatumo rizikų.
 #1.15.3    Level: 3    Role: D/V
 Patikrinkite, ar atliekamos periodinės patikros, siekiant nustatyti neautorizuotą vandens ženklu pažymėtos informacijos pakartotinį naudojimą ar nutekėjimą.

---

### C1.16 Duomenų subjektų teisių valdymas

Remti duomenų subjektų teises, tokias kaip prieiga, taisymas, apribojimas ir prieštaravimas.

 #1.16.1    Level: 2    Role: D/V
 Patikrinkite, ar egzistuoja mechanizmai, leidžiantys reaguoti į duomenų subjektų pateiktus prieigos, taisymo, apribojimo ar prieštaravimo reikalavimus.
 #1.16.2    Level: 2    Role: D/V
 Patikrinkite, ar užklausos yra registruojamos, stebimos ir įvykdomos per teisės aktų nustatytus terminus.
 #1.16.3    Level: 2    Role: D/V
 Patikrinkite, ar duomenų subjektų teisių procesai yra reguliariai tikrinami ir peržiūrimi dėl veiksmingumo.

---

### C1.17 Duomenų rinkinio versijos poveikio analizė

Įvertinkite duomenų rinkinio pokyčių poveikį prieš atnaujindami ar keisdami versijas.

 #1.17.1    Level: 2    Role: D/V
 Patikrinkite, ar atliekama poveikio analizė prieš atnaujinant ar keičiant duomenų rinkinio versiją, apimanti modelio našumą, teisingumą ir atitiktį.
 #1.17.2    Level: 2    Role: D/V
 Patikrinkite, ar poveikio analizės rezultatai yra dokumentuoti ir peržiūrėti atitinkamų suinteresuotųjų šalių.
 #1.17.3    Level: 2    Role: D/V
 Patikrinkite, ar yra atstatymo planai tuo atveju, jei naujos versijos sukeltų nepriimtinas rizikas arba regresijas.

---

### C1.18 Duomenų anotacijų darbo jėgos saugumas

Užtikrinti duomenų anotacijoje dalyvaujančio personalo saugumą ir vientisumą.

 #1.18.1    Level: 2    Role: D/V
 Patikrinkite, ar visi duomenų anotacijoje dalyvaujantys asmenys yra patikrinti ir apmokyti duomenų saugumo bei privatumo srityje.
 #1.18.2    Level: 2    Role: D/V
 Patikrinkite, ar visi anotacijų darbuotojai pasirašo konfidencialumo ir neatskleidimo sutartis.
 #1.18.3    Level: 2    Role: D/V
 Patikrinkite, ar anotacijų platformos įgyvendina prieigos kontrolę ir stebi vidaus grėsmes.

---

### Nuorodos

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

## C2 naudotojo įvesties validacija

### Valdymo tikslas

Tvirtas vartotojo įvesties patikrinimas yra pirmoji gynybos linija nuo kai kurių labiausiai žalingų išpuolių prieš DI sistemas. Komandų įpurškimo atakos gali pakeisti sistemos instrukcijas, nutekinti konfidencialius duomenis arba nukreipti modelį į neleistiną elgesį. Jei nėra įdiegtos specialios filtrų sistemos ir instrukcijų hierarchijos, tyrimai rodo, kad „daugiapakopiai“ jailbreak atakos, naudojančios labai ilgus konteksto langus, bus veiksmingos. Taip pat subtilios priešiškos trikdžių atakos — tokios kaip homoglifų pakeitimai arba leetspeak — gali tyliai pakeisti modelio sprendimus.

---

### C2.1 Užklausų injekcijos apsauga

Užklausų įterpimas (prompt injection) yra viena iš didžiausių rizikų dirbtinės intelekto (DI) sistemoms. Gynybos priemonės prieš šią taktiką taiko statinių šablonų filtrų, dinamiškų klasifikatorių ir instrukcijų hierarchijos vykdymo derinį.

 #2.1.1    Level: 1    Role: D/V
 Patikrinkite, ar vartotojo įvestys yra tikrinamos pagal nuolat atnaujinamą žinomų užklausų injekcijos šablonų (kalėjimo raktiniai žodžiai, „ignoruoti ankstesnį“, vaidmenų grandinės, netiesioginiai HTML/URL išpuoliai) biblioteką.
 #2.1.2    Level: 1    Role: D/V
 Patikrinkite, ar sistema užtikrina instrukcijų hierarchiją, kurioje sistemos arba kūrėjo žinutės viršija vartotojo instrukcijas, net ir išplėtus konteksto langą.
 #2.1.3    Level: 2    Role: D/V
 Patikrinkite, ar kiekvieno modelio ar šablono išleidimo metu atliekami priešpriešiniai vertinimo testai (pvz., Red Team „daugiapakopiai“ komandų raginimai), nustatant sėkmės rodiklio ribas ir automatinio regresijos blokatorius.
 #2.1.4    Level: 2    Role: D
 Patikrinkite, ar trečiųjų šalių turinio (internetinių svetainių, PDF failų, el. laiškų) kilę užklausų tekstai yra išvalomi izoliuoto analizės konteksto metu prieš sujungiami į pagrindinę užklausą.
 #2.1.5    Level: 3    Role: D/V
 Patikrinkite, ar visos atnaujinamos užklausų filtrų taisyklės, klasifikatoriaus modelių versijos ir blokavimo sąrašų pakeitimai yra valdomi versijomis ir audituojami.

---

### C2.2 Priešinimasis priešiškiems pavyzdžiams

Natūralios kalbos apdorojimo (NLP) modeliai vis dar yra pažeidžiami subtilių simbolių ar žodžių lygmens trikdžių, kurių žmonės dažnai nepastebi, tačiau modeliai linkę klaidingai klasifikuoti.

 #2.2.1    Level: 1    Role: D
 Patikrinkite, ar pagrindiniai įvesties normalizavimo veiksmai (Unicode NFC, homoglifų žemėlapis, tarpų apkarpymas) atliekami prieš žodžių skaidymą.
 #2.2.2    Level: 2    Role: D/V
 Patikrinkite, ar statistinės anomalijų aptikimo sistemos žymi įvestis, turinčias neįprastai didelį redagavimo atstumą nuo kalbos normų, perteklinius pasikartojančius žetonus arba nenormalius įterpimo atstumus.
 #2.2.3    Level: 2    Role: D
 Patikrinkite, ar išvadų srautas palaiko pasirenkamus modelio variantus, sustiprintus priešiškumo mokymu arba apsauginiais sluoksniais (pvz., atsitiktinumo taikymą, gynybinę distiliaciją) aukštos rizikos galinėms taškams.
 #2.2.4    Level: 2    Role: V
 Patikrinkite, ar įtariami priešiški įėjimai yra karantine, registruojami su pilnais duomenų paketais (po asmeninės identifikavimo informacijos pašalinimo).
 #2.2.5    Level: 3    Role: D/V
 Patikrinkite, ar atsparumo metrikos (žinomų atakų rinkinių sėkmės rodiklis) stebimos laikui bėgant ir ar regresijos sukelia leidimo blokuotuvą.

---

### C2.3 Schemos, tipo ir ilgio tikrinimas

Dažni AI išpuoliai, naudojantys netinkamus arba per didelius įvesties duomenis, gali sukelti analizės klaidas, užrašų išsiliejimą tarp laukų ir išteklių išeikvojimą. Griežtas schemos taikymas taip pat yra būtina sąlyga atliekant deterministinius įrankių kvietimus.

 #2.3.1    Level: 1    Role: D
 Patikrinkite, ar kiekviena API arba funkcijos kvietimo pabaigos taškas apibrėžia aiškią įvesties schemą (JSON schema, Protobuf arba daugiapolį ekvivalentą) ir ar įvestys yra patvirtinamos prieš sudarant užklausą.
 #2.3.2    Level: 1    Role: D/V
 Patikrinkite, ar įvestys, viršijančios maksimalų žodžių ar baitų ribą, yra atmestos su saugia klaida ir niekada nepatenkinamos tyliai apkarpant.
 #2.3.3    Level: 2    Role: D/V
 Patikrinkite, ar tipo patikrinimai (pvz., skaitinės reikšmės intervalai, išvardytos reikšmės, MIME tipai paveikslėliams/garsui) yra vykdomi serverio pusėje, o ne tik kliento kode.
 #2.3.4    Level: 2    Role: D
 Patikrinkite, ar semantiniai tikrintuvai (pvz., JSON Schema) veikia pastoviu laiku, kad būtų išvengta algoritminio DoS.
 #2.3.5    Level: 3    Role: V
 Patikrinkite, ar patvirtinimo klaidos yra registruojamos su slaptomis naudotų duomenų ištraukomis ir aiškiais klaidų kodais, siekiant palengvinti saugumo analizę.

---

### C2.4 Turinys ir politikos tikrinimas

Kūrėjai turėtų sugebėti aptikti sintaksiškai galiojančias užklausas, kurios prašo neleistino turinio (pvz., neteisėtų nurodymų, neapykantos kalbos ir autorių teisių saugomo teksto), ir užkirsti kelią jų plitimui.

 #2.4.1    Level: 1    Role: D
 Patikrinkite, ar turinio klasifikatorius (nulinio šūvio arba tikslintai paruoštas) įvertina kiekvieną įvestį pagal smurtą, savęs žalojimą, neapykantą, seksualinį turinį ir neteisėtus prašymus, naudojant konfigūruojamus slenksčius.
 #2.4.2    Level: 1    Role: D/V
 Patikrinkite, ar įvestys, pažeidžiančios politiką, gaus standartizuotus atsisakymus arba saugius užbaigimus, kad jos nepatektų į tolesnius LLM kvietimus.
 #2.4.3    Level: 2    Role: D
 Patikrinkite, ar atrankos modelis arba taisyklių rinkinys bent kartą per ketvirtį yra perdaromas/atnaujinamas, įtraukiant naujai pastebėtus „jailbreak“ arba politikos apeidimo modelius.
 #2.4.4    Level: 2    Role: D
 Patikrinkite, ar atranka gerbia vartotojo specifines politikos taisykles (amžiaus, regioninius teisės apribojimus) pagal atributais pagrįstas taisykles, kurios sprendžiamos prašymo metu.
 #2.4.5    Level: 3    Role: V
 Patikrinkite, ar atrankos žurnaluose yra įtraukti klasifikatoriaus pasitikėjimo balai ir politikos kategorijų žymos SOC koreliacijai ir būsimam raudonos komandos atkūrimui.

---

### C2.5 Įvesties greičio ribojimas ir piktnaudžiavimo prevencija

Kūrėjai turėtų užkirsti kelią piktnaudžiavimui, išteklių išeikvojimui ir automatizuotiems išpuoliams prieš DI sistemas, ribodami įvesties srautus ir aptikdami anomalinius naudojimosi modelius.

 #2.5.1    Level: 1    Role: D/V
 Patikrinkite, ar visiems įvesties galiniams taškams yra taikomi apribojimai pagal vartotoją, IP adresą ir API raktą.
 #2.5.2    Level: 2    Role: D/V
 Patikrinkite, ar sprogstamieji ir pastovūs dažnio apribojimai yra sureguliuoti taip, kad būtų užkirstas kelias DoS ir žiauraus jėgos (brute force) atakoms.
 #2.5.3    Level: 2    Role: D/V
 Patikrinkite, ar anomalūs naudojimo modeliai (pvz., greitos užklausos, įvesties srautas) sukelia automatinius blokavimus arba eskalacijas.
 #2.5.4    Level: 3    Role: V
 Patikrinkite, ar piktnaudžiavimo prevencijos žurnalai saugomi ir peržiūrimi dėl iškylančių atakų modelių.

---

### C2.6 Daugiau modalitetų įvesties patikra

DI sistemose turėtų būti įdiegtas patikimas ne teksto duomenų (vaizdų, garso, failų) įvesties validavimas, siekiant išvengti įsilaužimų, apgaulės ar išteklių piktnaudžiavimo.

 #2.6.1    Level: 1    Role: D
 Patikrinkite, ar visi netekstiniai įvesties duomenys (paveikslėliai, garsas, failai) yra patikrinti pagal tipą, dydį ir formatą prieš apdorojimą.
 #2.6.2    Level: 2    Role: D/V
 Patikrinkite, ar failai yra nuskaityti dėl kenkėjiškos programinės įrangos ir steganografinių apkrovų prieš įkeldami.
 #2.6.3    Level: 2    Role: D/V
 Patikrinkite, ar vaizdo/garsiniai įvestys yra tikrinamos dėl priešiškų trikdžių ar žinomų atakų modelių.
 #2.6.4    Level: 3    Role: V
 Patikrinkite, ar daugiaprametė įvesties patikra klaidos yra užregistruojamos ir sukelia įspėjimus tyrimui.

---

### C2.7 Įvesties kilmės nustatymas ir priskyrimas

DI sistemos turėtų palaikyti auditavimą, piktnaudžiavimo sekimą ir atitiktį, stebėdamos ir žymėdamos visų naudotojo įvesties duomenų kilmę.

 #2.7.1    Level: 1    Role: D/V
 Patikrinkite, ar visi vartotojo įvesties duomenys įrašomi su metaduomenimis (vartotojo ID, sesija, šaltinis, laiko žyma, IP adresas) įvedimo metu.
 #2.7.2    Level: 2    Role: D/V
 Patikrinkite, ar kilmės metaduomenys yra išlaikomi ir galima juos patikrinti visiems apdorotiems įvesties duomenims.
 #2.7.3    Level: 2    Role: D/V
 Patikrinkite, ar anomalūs arba nepatikimi įvesties šaltiniai yra pažymėti ir taikoma sustiprinta priežiūra arba blokavimas.

---

### C2.8 Realaus laiko adaptatyvus grėsmių aptikimas

Kūrėjai turėtų naudoti pažangias grėsmių aptikimo sistemas dirbtiniam intelektui, kurios prisitaiko prie naujų atakų modelių ir teikia realiojo laiko apsaugą naudojant sukompiliuotą modelių atitikimą.

 #2.8.1    Level: 1    Role: D/V
 Patikrinkite, ar grėsmių aptikimo šablonai yra kompiliuojami į optimizuotus reguliarių išraiškų variklius, užtikrinančius aukšto našumo realaus laiko filtravimą su minimaliu delsos poveikiu.
 #2.8.2    Level: 1    Role: D/V
 Patvirtinkite, kad grėsmių aptikimo sistemos palaiko atskiras šablonų bibliotekas skirtingoms grėsmių kategorijoms (užklausų injekcija, žalingas turinys, jautrūs duomenys, sistemos komandos).
 #2.8.3    Level: 2    Role: D/V
 Patikrinkite, ar adaptyviojo grėsmių aptikimo sistemoje naudojami mašininio mokymosi modeliai, kurie atnaujina grėsmių jautrumą pagal atakų dažnumą ir sėkmingumo rodiklius.
 #2.8.4    Level: 2    Role: D/V
 Patikrinkite, ar realaus laiko grėsmių žvalgybos srautai automatiškai atnaujina šablonų bibliotekas naujais atakų parašais ir pažeidžiamumo rodikliais (IOC - Indicators of Compromise).
 #2.8.5    Level: 3    Role: D/V
 Patikrinkite, ar grėsmių aptikimo klaidingo teigiamo rodikliai nuolat stebimi ir ar modelio specifiškumas automatiškai reguliuojamas, siekiant sumažinti teisėtų naudojimo atvejų trikdymą.
 #2.8.6    Level: 3    Role: D/V
 Patikrinkite, ar kontekstinė grėsmių analizė atsižvelgia į įvesties šaltinį, vartotojo elgesio modelius ir sesijos istoriją, siekiant pagerinti aptikimo tikslumą.
 #2.8.7    Level: 3    Role: D/V
 Patikrinkite, ar grėsmių aptikimo našumo metrikos (aptikimo rodiklis, apdorojimo delsos laikas, išteklių naudojimas) yra stebimos ir optimizuojamos realiuoju laiku.

---

### C2.9 Daugiarūšis saugumo validavimo vamzdelis

Kūrėjai turėtų užtikrinti saugumo patikrinimą tekstinėms, vaizdo, garso ir kitoms AI įvesties modalitetams, taikydami specifinius grėsmių aptikimo tipus ir išteklių izoliaciją.

 #2.9.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekviena įvesties moduliacija turi skirtus saugumo tikrintojus su dokumentuotais grėsmių modeliais (tekstas: užklausų injekcija, vaizdai: steganografija, garsas: spektrogramų atakos) ir aptikimo slenkstženklius.
 #2.9.2    Level: 2    Role: D/V
 Patikrinkite, ar daugialypės įvestys yra apdorojamos atskiruose izoliaciniuose aplinkose su apibrėžtais resursų apribojimais (atmintis, CPU, apdorojimo laikas), būdingais kiekvienam modality tipo ir dokumentuotais saugumo politikoje.
 #2.9.3    Level: 2    Role: D/V
 Patikrinkite, ar kryžminio režimo atakų aptikimas nustato koordinuotas atakas, apimančias kelis įvesties tipus (pvz., steganografinius krovinius vaizduose, derinamus su užklausų injekcija tekste), naudojant koreliacijos taisykles ir įspėjimų generavimą.
 #2.9.4    Level: 3    Role: D/V
 Patikrinkite, ar daugialypių validacijų klaidos sukelia išsamų žurnalavimą, įskaitant visas įvesties modališkumas, validacijos rezultatus, grėsmės balus ir koreliacijos analizę su struktūruotais žurnalo formatais SIEM integracijai.
 #2.9.5    Level: 3    Role: D/V
 Patikrinkite, ar modalumui būdingi turinio klasifikatoriai yra atnaujinami pagal dokumentuotus tvarkaraščius (ne rečiau kaip kas ketvirtį) su naujais grėsmių modeliais, priešiškais pavyzdžiais ir našumo rodikliais, išlaikomais virš bazinių ribų.

---

### Nuorodos

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

## C3 modelio gyvavimo ciklo valdymas ir pakeitimų kontrolė

### Valdymo tikslas

DI sistemos turi įdiegti pakeitimų valdymo procesus, kurie užkerta kelią neautorizuotiems ar nesaugiai modelio pakeitimams patekti į gamybą. Ši kontrolė užtikrina modelio vientisumą viso gyvavimo ciklo metu – nuo vystymo iki diegimo ir pašalinimo – kas leidžia greitai reaguoti į incidentus ir išlaikyti atsakomybę už visus pakeitimus.

Pagrindinis saugumo tikslas: į gamybą pristatyti tik įgaliotus, patvirtintus modelius, naudojant kontroliuojamus procesus, kurie užtikrina vientisumą, atsekamumą ir atkuriamumą.

---

### C3.1 Modelio autorizacija ir vientisumas

Į gamybos aplinką patenka tik autorizuoti modeliai, kurių vientisumas patvirtintas.

 #3.1.1    Level: 1    Role: D/V
 Prieš diegiant įsitikinkite, kad visi modelio artefaktai (svoriai, konfigūracijos, žodynai) yra kriptografiškai pasirašyti autorizuotų subjektų.
 #3.1.2    Level: 1    Role: D/V
 Patikrinkite, ar modelio vientisumas yra patvirtinamas diegimo metu ir ar nepavykus parašo patikrinimui modelis neįkeliamas.
 #3.1.3    Level: 2    Role: D/V
 Patikrinkite, ar modelio kilmės įrašai apima autorizuotos institucijos tapatybę, mokymo duomenų kontrolinių sumų reikšmes, patvirtinimo testų rezultatus su praėjimo/nepraėjimo statusu ir sukūrimo laiko žymą.
 #3.1.4    Level: 2    Role: D/V
 Patikrinkite, ar visi modelio artefaktai naudoja semantinį versijavimą (MAJOR.MINOR.PATCH) su dokumentuotais kriterijais, nurodančiais, kada kiekvienas versijos komponentas turi būti didinamas.
 #3.1.5    Level: 2    Role: V
 Patikrinkite, ar priklausomybių sekimas palaiko realaus laiko atsargų sąrašą, leidžiantį greitai identifikuoti visas vartojančias sistemas.

---

### C3.2 Modelio patvirtinimas ir testavimas

Modeliai turi praeiti apibrėžtus saugumo ir patikimumo patikrinimus prieš diegiant.

 #3.2.1    Level: 1    Role: D/V
 Patikrinkite, ar modeliai praeina automatizuotus saugumo bandymus, įskaitant įvesties patvirtinimą, išvesties valymą ir saugumo įvertinimus pagal iš anksto sutartus organizacijos priėmimo/atmetimo ribinius rodiklius prieš diegiant.
 #3.2.2    Level: 1    Role: D/V
 Patikrinkite, ar patvirtinimo klaidos automatiškai blokuoja modelio diegimą po aiškaus patvirtinimo iš anksto paskirtų įgaliotų asmenų, turinčių dokumentuotus verslo pagrindimus.
 #3.2.3    Level: 2    Role: V
 Patikrinkite, ar testo rezultatai yra kriptografiškai pasirašyti ir nekeičiami susieti su konkretaus verifikuojamo modelio versijos hešu.
 #3.2.4    Level: 2    Role: D/V
 Patikrinkite, ar avariniai įdiegimai reikalauja dokumentuotos saugumo rizikos vertinimo ir patvirtinimo iš iš anksto paskirtos saugumo institucijos per iš anksto sutartus terminus.

---

### C3.3 Valdomas diegimas ir grąžinimas atgal

Modelių diegimas privalo būti kontroliuojamas, stebimas ir grįžtamas.

 #3.3.1    Level: 1    Role: D
 Patikrinkite, ar gamybos diegimai įgyvendina palaipsniui vykdomus diegimo mechanizmus (canary diegimai, mėlyna-žalia diegimai) su automatizuotais grąžinimo trigeriais, pagrįstais iš anksto sutartais klaidų lygiais, delsos slenksčiais ar saugumo įspėjimų kriterijais.
 #3.3.2    Level: 1    Role: D/V
 Patikrinkite, ar atkūrimo galimybės atkuria visą modelio būseną (svorius, konfigūracijas, priklausomybes) atominiu būdu iš anksto nustatytu organizacijos laiko intervale.
 #3.3.3    Level: 2    Role: D/V
 Patikrinkite, ar diegimo procesai tikrina kriptografines parašus ir apskaičiuoja integralumo kontrolines sumas prieš aktyvuojant modelį, ir nutraukia diegimą, jei aptinkama neatitikimų.
 #3.3.4    Level: 2    Role: D/V
 Patikrinkite, ar neatidėliotinos modelio sustabdymo galimybės gali išjungti modelio galus per iš anksto apibrėžtą reagavimo laiką, naudojant automatinius grandinių pertraukiklius arba rankinius sustabdymo jungiklius.
 #3.3.5    Level: 2    Role: V
 Patikrinkite, ar atšaukimo artefaktai (ankstesnės modelio versijos, konfigūracijos, priklausomybės) yra saugomi pagal organizacijos politiką nekeičiamos saugyklos principu, skirtu incidentų valdymui.

---

### C3.4 Atsakomybės ir audito keitimas

Visi modelio gyvavimo ciklo pakeitimai turi būti sekami ir audituojami.

 #3.4.1    Level: 1    Role: V
 Patikrinkite, ar visi modelio pakeitimai (paleidimas, konfigūracija, pasitraukimas) generuoja nekeičiamos auditorijos įrašus, įskaitant laiko žymą, autentifikuoto veiksmo atlikėjo tapatybę, pakeitimo tipą ir būsenas prieš ir po pakeitimo.
 #3.4.2    Level: 2    Role: D/V
 Patikrinkite, ar prieiga prie audito žurnalo reikalauja tinkamos autorizacijos ir ar visi prieigos bandymai yra registruojami su vartotojo tapatybe ir laiko žyma.
 #3.4.3    Level: 2    Role: D/V
 Patikrinkite, ar užklausų šablonai ir sistemos pranešimai yra valdomi versijų kontrolės sistemoje git saugyklose, kur reikalingas privalomas kodo peržiūrėjimas ir patvirtinimas iš paskirtų peržiūrėtojų prieš diegiant.
 #3.4.4    Level: 2    Role: V
 Patikrinkite, ar audito įrašai apima pakankamai detalių (modelių maišos, konfigūracijos momentinės nuotraukos, priklausomybių versijos), kad būtų galima visiškai atkurti modelio būseną bet kuriuo laiko momentu saugojimo laikotarpio viduje.

---

### C3.5 Saugios kūrimo praktikos

Modelio kūrimo ir mokymo procesai turi laikytis saugių praktikų siekiant išvengti pažeidimų.

 #3.5.1    Level: 1    Role: D
 Patikrinkite, ar modelio kūrimo, testavimo ir gamybos aplinkos yra fiziškai arba logiškai atskirtos. Jos neturi bendros infrastruktūros, turi atskiras prieigos kontrolės priemones ir izoliuotas duomenų saugyklas.
 #3.5.2    Level: 1    Role: D
 Patikrinkite, ar modelio mokymas ir smulkus reguliavimas vyksta izoliuotose aplinkose su kontroliuojama tinklo prieiga.
 #3.5.3    Level: 1    Role: D/V
 Patikrinkite, ar mokymo duomenų šaltiniai yra patvirtinti atliekant vientisumo patikrinimus ir autentifikuoti per patikimus šaltinius su dokumentuotu grandinės valdymu prieš naudojimą modelio kūrime.
 #3.5.4    Level: 2    Role: D
 Patikrinkite, ar modelio kūrimo artefaktai (hiperparametrai, treniruočių scenarijai, konfigūracijos failai) yra saugomi versijų kontrolėje ir reikalauja kolegų peržiūros patvirtinimo prieš naudojimą treniruotėje.

---

### C3.6 Modelio pensija ir nutraukimas

Modeliai privalo būti saugiai pašalinami, kai jų nebereikia arba kai nustatomi saugumo trūkumai.

 #3.6.1    Level: 1    Role: D
 Patikrinkite, ar modelio nutraukimo procesai automatiškai nuskenuoja priklausomybių grafus, identifikuoja visus naudojančius sistemas ir pateikia iš anksto sutartus įspėjimo terminus prieš dekomisijavimą.
 #3.6.2    Level: 1    Role: D/V
 Patikrinkite, ar nebenaudojami modelio artefaktai yra saugiai ištrinti naudojant kriptografinį naikinimą arba kelis perrašymus pagal dokumentuotas duomenų saugojimo politiką, patvirtintas naikinimo sertifikatais.
 #3.6.3    Level: 2    Role: V
 Patikrinkite, ar modelio pašalinimo įvykiai užfiksuoti su laiko žyma ir veiksmo atlikėjo tapatybe, taip pat ar modelio parašai atšaukti, siekiant užkirsti kelią pakartotiniam naudojimui.
 #3.6.4    Level: 2    Role: D/V
 Patikrinkite, ar avarinis modelio pasitraukimas gali išjungti modelio prieigą per iš anksto nustatytus avarinio reagavimo laikotarpius naudojant automatizuotus išjungimo jungiklius, jei aptinkamos kritinės saugumo spragos.

---

### Nuorodos

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

## C4 infrastruktūros, konfigūracijos ir diegimo saugumas

### Valdymo tikslas

DI infrastruktūra turi būti sustiprinta prieš privilegijų eskalaciją, tiekimo grandinės manipuliacijas ir šoninį judėjimą naudojant saugią konfigūraciją, vykdymo izoliaciją, patikimus diegimo kanalus ir išsamų stebėjimą. Tik autorizuoti, patikrinti infrastruktūros komponentai ir konfigūracijos pasiekia gamybą per valdomus procesus, kurie užtikrina saugumą, vientisumą ir auditabilumą.

Pagrindinis saugumo tikslas: į gamybą pasiekia tik kriptografiškai pasirašytos, spragas patikrinusios infrastruktūros dalys per automatizuotas patikros linijas, kurios taiko saugumo politiką ir išlaiko nekeičiamą audito žurnalą.

---

### C4.1 Paleidimo aplinkos izoliacija

Užkirsti kelią konteinerių pabėgimams ir privilegijų eskalavimui naudojant branduolio lygio izoliacijos primityvus ir privalomuosius prieigos valdymus.

 #4.1.1    Level: 1    Role: D/V
 Patikrinkite, ar visi DI konteineriai atmeta VISAS Linux galimybes, išskyrus CAP_SETUID, CAP_SETGID ir aiškiai reikalaujamas galimybes, dokumentuotas saugumo bazinėse linijose.
 #4.1.2    Level: 1    Role: D/V
 Patikrinkite, ar seccomp profiliai blokuoja visas sistemos iškvietas, išskyrus tas, kurios yra iš anksto patvirtintose leidžiamųjų sąrašuose, o pažeidimams užbaigus konteinerį ir sukuriant saugumo įspėjimus.
 #4.1.3    Level: 2    Role: D/V
 Patikrinkite, ar DI darbo apkrovos veikia su tik skaitymui skirtomis šakniniu failų sistema, tmpfs laikinuosius duomenis ir vardytomis apimtimis nuolatiniams duomenims, užtikrinant noexec montavimo parinkčių taikymą.
 #4.1.4    Level: 2    Role: D/V
 Patikrinkite, ar eBPF pagrįstas vykdymo metu stebėjimas (Falco, Tetragon arba atitinkama sistema) aptinka privilegijų eskalavimo bandymus ir automatiškai nutraukia pažeidžiančius procesus pagal organizacijos reagavimo laiko reikalavimus.
 #4.1.5    Level: 3    Role: D/V
 Patikrinkite, ar didelės rizikos DI užduotys vykdomos aparatinėje įrangoje izoliuotose aplinkose (Intel TXT, AMD SVM arba specializuotuose bare-metal mazguose) su patvirtinimo patikrinimu.

---

### C4.2 Saugios kūrimo ir diegimo grandinės

Užtikrinkite kriptografinį vientisumą ir tiekimo grandinės saugumą naudojant atkuriamus build'us ir pasirašytus artefaktus.

 #4.2.1    Level: 1    Role: D/V
 Patikrinkite, ar infrastruktūra kaip kodas (infrastructure-as-code) yra tikrinama naudodami įrankius (tfsec, Checkov arba Terrascan) kiekvieno komiteto metu, užkertant kelią susijungimams (merge) su kritinės arba aukštos svarbos problemomis.
 #4.2.2    Level: 1    Role: D/V
 Patikrinkite, ar konteinerių kūrimas yra atkuriamas su identiškais SHA256 hešais tarp kūrimo ciklų, ir sukurkite SLSA 3 lygio kilmės patvirtinimus, pasirašytus naudojant Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Patikrinkite, ar konteinerių atvaizdai įtraukia CycloneDX arba SPDX SBOM ir yra pasirašyti su Cosign prieš įkeliant į registrą, o nepasižimančius atvaizdų nepaisyti diegimo metu.
 #4.2.4    Level: 2    Role: D/V
 Patikrinkite, ar CI/CD vamzdynai naudoja OIDC žetonus iš HashiCorp Vault, AWS IAM vaidmenų arba Azure valdomos tapatybės, kurių galiojimo laikas neviršija organizacijos saugumo politikos apribojimų.
 #4.2.5    Level: 2    Role: D/V
 Patikrinkite, ar Cosign parašai ir SLSA kilmės duomenys yra tikrinami diegimo proceso metu prieš konteinerio paleidimą, ir kad tikrinimo klaidos sukelia diegimo nepavykimą.
 #4.2.6    Level: 2    Role: D/V
 Patikrinkite, ar kūrimo aplinkos veikia laikinuose konteineriuose arba virtualiose mašinose be nuolatinės saugyklos ir tinklo atskyrimo nuo gamybos VPC.

---

### C4.3 Tinklo saugumas ir prieigos kontrolė

Įgyvendinkite nulės pasitikėjimo tinklus su numatytosiomis draudimo politika ir užšifruotais ryšiais.

 #4.3.1    Level: 1    Role: D/V
 Patikrinkite, ar Kubernetes NetworkPolicies arba jų atitikmuo įgyvendina numatytąjį atmetimą įeinančiam/išeinančiam srautui su aiškiai nurodytomis leidžiamomis taisyklėmis reikalingiems prievadams (443, 8080 ir pan.).
 #4.3.2    Level: 1    Role: D/V
 Patikrinkite, ar SSH (22 prievadas), RDP (3389 prievadas) ir debesų metaduomenų galiniai taškai (169.254.169.254) yra užblokuoti arba reikalauja autentifikacijos, pagrįstos sertifikatais.
 #4.3.3    Level: 2    Role: D/V
 Patikrinkite, ar išeinantis srautas filtruojamas per HTTP/HTTPS proxy serverius (Squid, Istio arba debesų NAT vartus) naudojant domenų leidimų sąrašus ir ar užblokuoti užklausimai yra įrašomi į žurnalus.
 #4.3.4    Level: 2    Role: D/V
 Patikrinkite, ar tarpusavio paslaugų komunikacija naudoja abipusį TLS su sertifikatais, keičiama pagal organizacijos politiką, ir ar sertifikatų patikra yra privaloma (be skip-verify žymų).
 #4.3.5    Level: 2    Role: D/V
 Patikrinkite, ar DI infrastruktūra veikia skirtose VPC/VNet tinkluose be tiesioginio interneto prieigos ir bendrauja tik per NAT vartus arba bastiono serverius.

---

### C4.4 Slaptažodžių ir kriptografinių raktų valdymas

Apsaugokite prisijungimo duomenis naudodami aparatine įranga pagrįstą saugyklą ir automatizuotą rotaciją su nulinio pasitikėjimo prieiga.

 #4.4.1    Level: 1    Role: D/V
 Patikrinkite, ar slapti duomenys saugomi HashiCorp Vault, AWS Secrets Manager, Azure Key Vault arba Google Secret Manager, naudojant AES-256 šifravimą laisvės metu.
 #4.4.2    Level: 1    Role: D/V
 Patikrinkite, ar kriptografiniai raktai generuojami FIPS 140-2 2 lygio HSM įrenginiuose (AWS CloudHSM, Azure Dedicated HSM) su rakto kaitos procedūra, atitinkančia organizacijos kriptografinę politiką.
 #4.4.3    Level: 2    Role: D/V
 Patikrinkite, ar slaptųjų duomenų keitimas (rotation) yra automatizuotas su nuliniu veikimo sustojimo laiku ir kad sukartojimas įvyksta iš karto, kai yra personalo pokyčiai arba saugumo incidentai.
 #4.4.4    Level: 2    Role: D/V
 Patikrinkite, ar konteinerių vaizdai yra skenuojami įrankiais (GitLeaks, TruffleHog arba detect-secrets), kurie blokuoja kūrimą, jei juose yra API raktai, slaptažodžiai ar sertifikatai.
 #4.4.5    Level: 2    Role: D/V
 Patikrinkite, ar prieiga prie gamybos slaptojo rakto reikalauja MFA su aparatiniais raktais (YubiKey, FIDO2) ir ar tai yra įrašoma nepakeičiamuose audito žurnaluose su vartotojo tapatybėmis ir laiko žymėmis.
 #4.4.6    Level: 2    Role: D/V
 Patikrinkite, ar slaptažodžiai yra perduodami per Kubernetes slaptumo objektus, prijungtus tomus arba init konteinerius, ir užtikrinkite, kad slaptažodžiai niekada nebūtų įterpti į aplinkos kintamuosius arba vaizdus.

---

### C4.5 AI darbo krūvio aplinkos atskyrimas ir patikra

Izoliuokite nepatikimus DI modelius saugiose smėlio dėžėse su išsamia elgesio analize.

 #4.5.1    Level: 1    Role: D/V
 Patikrinkite, ar išoriniai DI modeliai vykdomi gVisor, mikroVM (tokiose kaip Firecracker, CrossVM) arba Docker konteineriuose su --security-opt=no-new-privileges ir --read-only parametrais.
 #4.5.2    Level: 1    Role: D/V
 Patikrinkite, ar smėlio dėžės aplinkos neturi tinklo ryšio (--network=none) arba turi prieigą tik prie localhost, o visi išoriniai užklausimai yra blokuojami iptables taisyklėmis.
 #4.5.3    Level: 2    Role: D/V
 Patikrinkite, ar DI modelio patvirtinimas apima automatizuotą raudonosios komandos testavimą su organizacijos apibrėžtu testavimo aprėptimi ir elgesio analize užpakalinių durų aptikimui.
 #4.5.4    Level: 2    Role: D/V
 Patikrinkite, ar prieš diegiant AI modelį į gamybą, jo smėlio dėžės rezultatai yra kriptografiškai pasirašyti įgaliotų saugumo darbuotojų ir saugomi nekeičiamuose audito įrašuose.
 #4.5.5    Level: 2    Role: D/V
 Patikrinkite, ar smėlio dėžės aplinkos yra sunaikinamos ir atkuriamos iš aukso atvaizdų tarp vertinimų, atliekant visišką failų sistemos ir atminties valymą.

---

### C4.6 Infrastruktūros saugumo stebėjimas

Nuolat skenuokite ir stebėkite infrastruktūrą naudodami automatizuotą taisymą ir realaus laiko įspėjimus.

 #4.6.1    Level: 1    Role: D/V
 Patikrinkite, ar konteinerių atvaizdai yra skenuojami pagal organizacijos tvarkaraščius, o DIEGTINI pažeidžiamumai blokuoja diegimą remiantis organizacijos rizikos slenkstais.
 #4.6.2    Level: 1    Role: D/V
 Patikrinkite, ar infrastruktūra atitinka CIS Standartus arba NIST 800-53 kontrolinius punktus pagal organizacijos nustatytus atitikties slenksčius ir automatinį neatitikimų taisymą.
 #4.6.3    Level: 2    Role: D/V
 Patikrinkite, ar AUKŠTO lygio pažeidžiamumai yra ištaisyti pagal organizacijos rizikos valdymo tvarkaraščius, taikant neatidėliotinas procedūras aktyviai išnaudojamiems CVE.
 #4.6.4    Level: 2    Role: V
 Patikrinkite, ar saugumo įspėjimai integruojami su SIEM platformomis (Splunk, Elastic arba Sentinel), naudojant CEF arba STIX/TAXII formatus su automatiniu papildymu.
 #4.6.5    Level: 3    Role: V
 Patikrinkite, ar infrastruktūros metrikos eksportuojamos į monitoringo sistemas (Prometheus, DataDog) su SLA informacijos suvestinėmis ir vadovybės ataskaitomis.
 #4.6.6    Level: 2    Role: D/V
 Patikrinkite, ar konfigūracijos nukrypimų aptikimas vykdomas naudojant įrankius (Chef InSpec, AWS Config) pagal organizacijos stebėjimo reikalavimus, su automatinio neleistinų pakeitimų atkūrimo funkcija.

---

### C4.7 Dirbtinio intelekto infrastruktūros išteklių valdymas

Užkirsti kelią išteklių išeikvojimo atakoms ir užtikrinti teisingą išteklių paskirstymą per kvotas ir stebėjimą.

 #4.7.1    Level: 1    Role: D/V
 Patikrinkite, ar GPU/TPU naudojimas yra stebimas, o perspėjimai suaktyvinami organizacijos nustatytose ribose, taip pat ar automatinis skalavimas arba apkrovos balansavimas aktyvuojami pagal talpos valdymo politiką.
 #4.7.2    Level: 1    Role: D/V
 Patikrinkite, ar AI darbo krūvio metrika (inference delsos laikas, pralaidumas, klaidų rodikliai) renkama pagal organizacijos stebėjimo reikalavimus ir koreliuojama su infrastruktūros naudojimu.
 #4.7.3    Level: 2    Role: D/V
 Patikrinkite, ar Kubernetes ResourceQuotas arba atitinkami ribojimai apriboja atskirus darbo krūvius pagal organizacijos išteklių paskirstymo politiką, taikant griežtas ribas.
 #4.7.4    Level: 2    Role: V
 Patikrinkite, ar išlaidų stebėjimas seka išlaidas pagal darbo krūvį/nuomininką, su įspėjimais, pagrįstais organizacijos biudžeto ribomis, ir automatizuotais valdikliais biudžeto viršijimams.
 #4.7.5    Level: 3    Role: V
 Patikrinkite, ar talpos planavimas naudoja istorinę informaciją su organizacijos apibrėžtais prognozavimo laikotarpiais ir automatizuotą išteklių teikimą pagal paklausos modelius.
 #4.7.6    Level: 2    Role: D/V
 Patikrinkite, ar išteklių išeikvojimas sukelia grandinės pertraukiklius pagal organizacijos atsako reikalavimus, įskaitant greičio ribojimą pagal pajėgumų politiką ir darbo apkrovos izoliaciją.

---

### C4.8 Aplinkos atskyrimo ir taisyklės dėl perkėlimo kontrolės

Užtikrinkite griežtas aplinkos ribas naudodami automatinius skatinimo vartus ir saugumo patvirtinimą.

 #4.8.1    Level: 1    Role: D/V
 Patikrinkite, ar kūrimo/testavimo/produkcinės aplinkos veikia atskiruose VPC/VNet tinkluose, neturintys bendrų IAM vaidmenų, saugos grupių ar tinklo ryšio.
 #4.8.2    Level: 1    Role: D/V
 Patikrinkite, ar aplinkos perėjimas reikalauja organizacijos nustatytų įgaliotų asmenų patvirtinimo su kriptografiniais parašais ir nepakeičiamais audito įrašais.
 #4.8.3    Level: 2    Role: D/V
 Patikrinkite, ar gamybos aplinkose užblokuotas SSH prieigos, išjungti derinimo (debug) galiniai taškai ir ar reikalingi pokyčių prašymai su organizaciniu išankstiniu pranešimu, išskyrus avarinius atvejus.
 #4.8.4    Level: 2    Role: D/V
 Patikrinkite, ar infrastruktūros kaip kodo pakeitimai reikalauja bendraautorių peržiūros, automatizuoto testavimo ir saugumo nuskaitymo prieš sujungiant į pagrindinę šaką.
 #4.8.5    Level: 2    Role: D/V
 Patikrinkite, ar neprodukciniai duomenys yra anonimizuoti pagal organizacijos privatumo reikalavimus, sintezinių duomenų generavimą arba visišką duomenų maskavimą su asmeninės identifikacijos informacijos (PII) pašalinimu.
 #4.8.6    Level: 2    Role: D/V
 Patikrinkite, ar perėjimo vartai apima automatinius saugumo testus (SAST, DAST, konteinerio skenavimą), kuriems patvirtinimui reikalingas nulinis KRITIŠKŲ radinių skaičius.

---

### C4.9 Infrastruktūros atsarginė kopija ir atkūrimas

Užtikrinkite infrastruktūros atsparumą naudodami automatizuotas atsargines kopijas, patikrintas atkūrimo procedūras ir nelaimių atkūrimo galimybes.

 #4.9.1    Level: 1    Role: D/V
 Patikrinkite, ar infrastruktūros konfigūracijos yra atsarginės kopijos, atliekamos pagal organizacijos atsarginių kopijų grafikus į geografiškai atskirtas vietoves, įgyvendinant 3-2-1 atsarginių kopijų strategiją.
 #4.9.2    Level: 2    Role: D/V
 Patikrinkite, ar atsarginių kopijų sistemos veikia izoliuotuose tinkluose, naudojant atskirus prieigos duomenis ir oro tarpo saugyklą apsaugai nuo išpirkos programų.
 #4.9.3    Level: 2    Role: V
 Patikrinkite, ar atkūrimo procedūros yra išbandomos ir patvirtinamos automatizuotų testų pagalba pagal organizacijos tvarkaraščius, atitinkančius RTO ir RPO tikslus bei organizacijos reikalavimus.
 #4.9.4    Level: 3    Role: V
 Patikrinkite, ar nelaimių atsako plane yra AI specifiniai veiksmų planai su modelio svorių atkūrimu, GPU klasterio atstatymu ir paslaugų priklausomybių žemėlapiu.

---

### C4.10 Infrastrukturų atitiktis ir valdymas

Užtikrinkite atitiktį teisės aktams nuolat vertindami, dokumentuodami ir naudodami automatizuotas kontrolės priemones.

 #4.10.1    Level: 2    Role: D/V
 Patikrinkite, ar infrastruktūros atitiktis vertinama pagal organizacijos grafikus, atsižvelgiant į SOC 2, ISO 27001 arba FedRAMP kontrolės priemones, naudojant automatizuotą įrodymų rinkimą.
 #4.10.2    Level: 2    Role: V
 Patikrinkite, ar infrastruktūros dokumentacijoje yra tinklo diagramos, duomenų srauto žemėlapiai ir grėsmių modeliai, atnaujinti pagal organizacijos pokyčių valdymo reikalavimus.
 #4.10.3    Level: 3    Role: D/V
 Patikrinkite, ar infrastruktūros pakeitimai pereina automatizuotą atitikties poveikio įvertinimą su reguliavimo patvirtinimo darbo eiga aukštos rizikos modifikacijoms.

---

### C4.11 DI aparatūros saugumas

Užtikrinkite saugią AI specifinių aparatūros komponentų, įskaitant GPU, TPU ir specializuotų AI akceleratorių, apsaugą.

 #4.11.1    Level: 2    Role: D/V
 Patikrinkite, ar AI spartintuvo įdiegimo programinė įranga (GPU BIOS, TPU įdiegimo programinė įranga) yra patikrinta naudojant kriptografinius parašus ir atnaujinama pagal organizacijos pataisų valdymo grafikus.
 #4.11.2    Level: 2    Role: D/V
 Patikrinkite, ar prieš darbo krūvio vykdymą AI pagreičio įrenginio vientisumas yra patvirtinamas aparatinės įrangos atestacija naudojant TPM 2.0, Intel TXT arba AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Patikrinkite, ar GPU atmintis yra izoluota tarp darbo krūvių naudojant SR-IOV, MIG (dauginis GPU atskyrimas) arba lygiavertį aparatinės įrangos suskirstymą su atminties sanitarizacija tarp užduočių.
 #4.11.4    Level: 3    Role: V
 Patikrinkite, ar AI aparatūros tiekimo grandinė apima kilmės patvirtinimą su gamintojo sertifikatais ir įrodymus apie pakuotės pažeidimus.
 #4.11.5    Level: 3    Role: D/V
 Patikrinkite, ar aparatinės saugos moduliai (HSM) saugo DI modelio svorius ir kriptografinius raktus, turėdami FIPS 140-2 3 lygio arba Common Criteria EAL4+ sertifikatus.

---

### C4.12 Kraštinė ir paskirstytoji dirbtinio intelekto infrastruktūra

Saugūs paskirstyti DI diegimai, įskaitant krašto skaičiavimą, federuotą mokymąsi ir daugiavidurines architektūras.

 #4.12.1    Level: 2    Role: D/V
 Patikrinkite, ar krašto AI įrenginiai autentifikuojasi prie centrinės infrastruktūros naudodami abipusį TLS su įrenginių sertifikatais, keičiami pagal organizacijos sertifikatų valdymo politiką.
 #4.12.2    Level: 2    Role: D/V
 Patikrinkite, ar krašto įrenginiai įgyvendina saugų paleidimą su patikrintomis parašais ir atgalinio perkėlimo apsauga, užkertančia kelią programinės įrangos versijos seninimo atakoms.
 #4.12.3    Level: 3    Role: D/V
 Patikrinkite, ar paskirstytasis DI koordinavimas naudoja bizantinio gedimų toleravimo konsensuso algoritmus su dalyvių patvirtinimu ir piktybiškų mazgų aptikimu.
 #4.12.4    Level: 3    Role: D/V
 Patikrinkite, ar krašto ir debesies ryšys apima pralaidumo ribojimą, duomenų suspaudimą ir neprisijungus veikimo galimybes su saugiu vietiniu saugojimu.

---

### C4.13 Daugia debesų ir hibridinės infrastruktūros saugumas

Užtikrinkite saugų AI darbo krūvių vykdymą keliuose debesų paslaugų teikėjuose ir hibridinėse debesų bei vietinėse aplinkose.

 #4.13.1    Level: 2    Role: D/V
 Patikrinkite, ar daugialypės debesijos AI diegimai naudoja debesijoms nepriklausomą tapatybės federaciją (OIDC, SAML) su centralizuotu politikos valdymu tarp paslaugų teikėjų.
 #4.13.2    Level: 2    Role: D/V
 Patikrinkite, ar kryžminis duomenų perdavimas debesyse naudoja galutinį užšifravimą su kliento valdomais raktas ir ar duomenų buvimo vietos valdymas yra užtikrinamas pagal jurisdikciją.
 #4.13.3    Level: 2    Role: D/V
 Patikrinkite, ar hibridinės debesijos DI užduotys įgyvendina nuoseklias saugumo politikos priemones tiek vietiniuose, tiek debesijos aplinkose, naudojant vieningą stebėjimą ir perspėjimų sistemą.
 #4.13.4    Level: 3    Role: V
 Patvirtinkite, kad debesų paslaugų tiekėjo priklausomybės prevencija apima nešiojamą infrastruktūrą kaip kodą, standartizuotus API ir duomenų eksportavimo galimybes su formato konvertavimo įrankiais.
 #4.13.5    Level: 3    Role: V
 Patikrinkite, ar daugiabantės debesijos sąnaudų optimizavimas apima saugumo kontrolę, užkertančią kelią resursų išplitimui ir neautorizuotoms tarp debesų duomenų perdavimo išlaidoms.

---

### C4.14 Infrastruktūros automatizavimas ir GitOps saugumas

Saugios infrastruktūros automatizavimo vamzdynai ir GitOps darbo eiga AI infrastruktūros valdymui.

 #4.14.1    Level: 2    Role: D/V
 Patikrinkite, ar GitOps saugyklos reikalauja pasirašytų įsipareigojimų naudojant GPG raktus ir ar yra nustatytos šakų apsaugos taisyklės, draudžiančios tiesioginius įkėlimus į pagrindines šakas.
 #4.14.2    Level: 2    Role: D/V
 Patikrinkite, ar infrastruktūros automatizavime yra įtraukta nukrypimų aptikimas su automatinio taisymo ir grąžinimo galimybėmis, kurios aktyvuojamos pagal organizacijos reagavimo reikalavimus neautorizuotiems pokyčiams.
 #4.14.3    Level: 2    Role: D/V
 Patikrinkite, ar automatizuotas infrastruktūros diegimas apima saugumo politikos patvirtinimą su diegimo blokavimu neatitinkančioms konfigūracijoms.
 #4.14.4    Level: 2    Role: D/V
 Patikrinkite, ar infrastruktūros automatizavimo slaptieji duomenys valdomi per išorinius slaptųjų duomenų operatorius (External Secrets Operator, Bank-Vaults) su automatinio sukinėjimo funkcija.
 #4.14.5    Level: 3    Role: V
 Patikrinkite, ar savęs taisanti infrastruktūra apima saugumo įvykių koreliaciją su automatizuotu incidentų reagavimo ir suinteresuotųjų šalių informavimo darbo eigomis.

---

### C4.15 Kvantinę atsparią infrastruktūros saugą

Paruoškite DI infrastruktūrą kvantinių kompiuterių grėsmėms valdant pasitelkiant po-kvantinę kriptografiją ir kvantui atsparius protokolus.

 #4.15.1    Level: 3    Role: D/V
 Patikrinkite, ar AI infrastruktūra įgyvendina NIST patvirtintus postkvantininius kriptografinius algoritmus (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) raktų mainams ir skaitmeniniams parašams.
 #4.15.2    Level: 3    Role: D/V
 Patikrinkite, ar kvantiniai raktų paskirstymo (QKD) sistemos įdiegtos aukštos saugos DI komunikacijoms su kvantiniu saugiu raktų valdymo protokolais.
 #4.15.3    Level: 3    Role: D/V
 Patikrinkite, ar kriptografinės lankstumo sistemos leidžia greitai pereiti prie naujų postkvantinių algoritmų, automatizuotai keisdamos sertifikatus ir raktus.
 #4.15.4    Level: 3    Role: V
 Patikrinkite, ar kvantiniai grėsmių modeliavimai įvertina DI infrastruktūros pažeidžiamumą kvantinėms atakoms, pateikiant dokumentuotus migracijos grafikus ir rizikos vertinimus.
 #4.15.5    Level: 3    Role: D/V
 Patikrinkite, ar hibridinės klasikinės-kvantinės kriptografinės sistemos užtikrina gilesnį saugumo sluoksniavimą kvantinės perėjimo laikotarpiu kartu su veiklos stebėsena.

---

### C4.16 Konfidencialus skaičiavimas ir saugios aplinkos

Apsaugokite DI darbo krūvius ir modelio svorius naudodami aparatūrinei įrangai skirtas patikimas vykdymo aplinkas ir konfidencialaus skaičiavimo technologijas.

 #4.16.1    Level: 3    Role: D/V
 Patikrinkite, ar jautrūs DI modeliai vykdomi Intel SGX aplinkose, AMD SEV-SNP arba ARM TrustZone su šifruota atmintimi ir tapatybės patvirtinimu.
 #4.16.2    Level: 3    Role: D/V
 Patikrinkite, ar konfidencialios talpyklos (Kata Containers, gVisor su konfidencialiu apdorojimu) izoliuoja dirbtinio intelekto užduotis, naudodamos aparatūros užtikrintą atminties šifravimą.
 #4.16.3    Level: 3    Role: D/V
 Patikrinkite, ar nuotolinis patvirtinimas tikrina užtvaro vientisumą prieš įkeliant DI modelius, naudojant kriptografinį vykdymo aplinkos autentiškumo įrodymą.
 #4.16.4    Level: 3    Role: D/V
 Patikrinkite, ar konfidencialios DI spėjimo paslaugos užkerta kelią modelio išgavimui naudojant užšifruotą skaičiavimą su užantspauduotais modelio svoriais ir apsaugotu vykdymu.
 #4.16.5    Level: 3    Role: D/V
 Patikrinkite, ar patikimos vykdymo aplinkos organizavimas valdo saugios zonos gyvavimo ciklą su nuotoline atestacija ir užšifruotomis komunikacijos kanalais.
 #4.16.6    Level: 3    Role: D/V
 Patikrinkite, ar saugus kelių šalių skaičiavimas (SMPC) leidžia bendradarbiauti AI mokyme neskelbiant atskirų duomenų rinkinių ar modelio parametrų.

---

### C4.17 Nulinio žinojimo infrastruktūra

Įgyvendinkite nulio žinių įrodymo sistemas privatumą saugančiam DI patvirtinimui ir autentifikavimui, neišduodant jautrios informacijos.

 #4.17.1    Level: 3    Role: D/V
 Patikrinkite, ar nulinės žinios įrodymai (ZK-SNARK, ZK-STARK) patvirtina DI modelio vientisumą ir mokymo kilmę neskelbiant modelio svorių ar mokymo duomenų.
 #4.17.2    Level: 3    Role: D/V
 Patikrinkite, ar ZK pagrįstos autentifikavimo sistemos leidžia vykdyti vartotojų tikrinimą, saugant privatumą AI paslaugoms, neskelbiant su tapatybe susijusios informacijos.
 #4.17.3    Level: 3    Role: D/V
 Patikrinkite, ar privačios sankirtos rinkinių (PSI) protokolai užtikrina saugų duomenų atitikimą federuotam dirbtiniam intelektui neatskleisdami atskirų duomenų rinkinių.
 #4.17.4    Level: 3    Role: D/V
 Patikrinkite, ar nulio žinių mašininio mokymosi (ZKML) sistemos leidžia patikrinamus DI spėjimus su kriptografiniu teisingo skaičiavimo įrodymu.
 #4.17.5    Level: 3    Role: D/V
 Patikrinkite, ar ZK-rollup’ai užtikrina mastelio keičiamą, privatumo saugančią AI transakcijų apdorojimą su partijos patikrinimu ir sumažinta skaičiavimo našta.

---

### C4.18 Šoninio kanalo atakų prevencija

Apsaugokite DI infrastruktūrą nuo laiko, energijos, elektromagnetinių ir talpyklos pagrindu veikiančių šoninių kanalų atakų, kurios gali nutekinti jautrią informaciją.

 #4.18.1    Level: 3    Role: D/V
 Patikrinkite, ar AI išvados laikas yra normalizuojamas naudojant pastovaus laiko algoritmus ir papildymą, siekiant užkirsti kelią atakoms, pagrįstoms laikų analize modelio iš gavimo.
 #4.18.2    Level: 3    Role: D/V
 Patikrinkite, ar galios analizės apsauga apima triukšmo įpurškimą, maitinimo linijos filtravimą ir atsitiktinių vykdymo šablonų taikymą AI aparatūroje.
 #4.18.3    Level: 3    Role: D/V
 Patikrinkite, ar cache pagrįstos šoninės kanalo atakos mažinimo priemonės naudoja talpyklos dalijimą, atsitiktinimą ir išvalymo instrukcijas, kad būtų užkirstas kelias informacijos nutekėjimui.
 #4.18.4    Level: 3    Role: D/V
 Patikrinkite, ar elektromagnetinių sklidimų apsauga apima ekranavimą, signalo filtravimą ir atsitiktinį apdorojimą, siekiant užkirsti kelią TEMPEST tipo atakoms.
 #4.18.5    Level: 3    Role: D/V
 Patikrinkite, ar mikroschemų šoniniai kanalai apima spekuliatyviosios vykdymo kontrolę ir atminties prieigos modelio užmaskavimą.

---

### C4.19 Neuromorfinės ir specializuotos DI aparatūros saugumas

Užtikrinkite saugią naujų dirbtinio intelekto aparatūros architektūrą, įskaitant neuromorfinius lustus, FPGA, specializuotus ASIC ir optines skaičiavimo sistemas.

 #4.19.1    Level: 3    Role: D/V
 Patikrinkite, ar neuromorfinio mikroschemos saugumas apima impulsų modelių šifravimą, sinapsinių svorių apsaugą ir aparatine įranga pagrįstą mokymosi taisyklių tikrinimą.
 #4.19.2    Level: 3    Role: D/V
 Patikrinkite, ar FPGA pagrindu sukurti AI pagreitintuvai įgyvendina bitų srauto šifravimą, apsaugos nuo pažeidimų mechanizmus ir saugų konfigūracijos pakrovimą su autentifikuotais atnaujinimais.
 #4.19.3    Level: 3    Role: D/V
 Patikrinkite, ar pasirinktinis ASIC saugumas apima mikroschemos saugumo procesorius, aparatinę pasitikėjimo šaknį ir saugų raktų saugojimą su aptikimu, jei bandoma pažeisti.
 #4.19.4    Level: 3    Role: D/V
 Patikrinkite, ar optinės skaičiavimo sistemos įgyvendina kvantiniu požiūriu saugią optinę šifravimą, saugų fotoninių perjungimą ir apsaugotą optinį signalo apdorojimą.
 #4.19.5    Level: 3    Role: D/V
 Patikrinkite, ar hibridiniai analoginiai-skaitmeniniai DI lustai apima saugią analoginę skaičiavimą, apsaugotą svorių saugojimą ir autentifikuotą analoginio-skaitmeninio keitimo procesą.

---

### C4.20 Privatumo Išlaikymo Skaičiavimo Infrastruktūra

Įgyvendinkite infrastruktūros kontrolės priemones privatumą saugančiai skaičiavimui, siekiant apsaugoti jautrius duomenis AI apdorojimo ir analizės metu.

 #4.20.1    Level: 3    Role: D/V
 Patikrinkite, ar homomorfinės šifravimo infrastruktūra leidžia atlikti užšifruotą skaičiavimą jautrioms DI užduotims su kriptografinio vientisumo patikrinimu ir veiklos stebėsena.
 #4.20.2    Level: 3    Role: D/V
 Patikrinkite, ar privatios informacijos gavimo sistemos leidžia užklausas duomenų bazėje vykdyti neatskleidžiant užklausų modelių, naudojant kriptografinę prieigos modelių apsaugą.
 #4.20.3    Level: 3    Role: D/V
 Patikrinkite, ar saugūs daugiapusių skaičiavimų protokolai leidžia atlikti privatumą išsaugančią AI inferenciją, neatskleidžiant atskirų įvesties duomenų ar tarpinio skaičiavimo rezultatų.
 #4.20.4    Level: 3    Role: D/V
 Patikrinkite, ar privatumo saugomas raktų valdymas apima paskirstytą raktų generavimą, slenksčio kriptografiją ir saugų raktų rotavimą su aparatine apsauga.
 #4.20.5    Level: 3    Role: D/V
 Patikrinkite, ar privatumo išsaugojimo skaičiavimo našumas yra optimizuotas naudojant grupavimą (batching), talpyklos (caching) naudojimą ir aparatinį pagreitį, išlaikant kriptografinio saugumo garantijas.

---

### C4.15 Agentų sistemos debesų integracijos saugumas ir hibridinis diegimas

Debesų integruotų agentų sistemų saugumo valdikliai hibridinėms vietinėms/debesų architektūroms.

 #4.15.1    Level: 1    Role: D/V
 Patikrinkite, ar debesies saugyklos integracija naudoja galutinio taško šifravimą su agento valdomu rakto valdymu.
 #4.15.2    Level: 2    Role: D/V
 Patikrinkite, ar hibridinės diegimo saugumo ribos yra aiškiai apibrėžtos su užšifruotais komunikacijos kanalais.
 #4.15.3    Level: 2    Role: D/V
 Patikrinkite, ar debesų išteklių prieiga apima nulio-pasitikėjimo patikrą su nuolatine autentifikacija.
 #4.15.4    Level: 3    Role: D/V
 Patikrinkite, ar duomenų saugojimo vietos reikalavimai įgyvendinami kriptografiniu saugyklos vietų patvirtinimu.
 #4.15.5    Level: 3    Role: D/V
 Patikrinkite, ar debesų paslaugų teikėjo saugumo vertinimuose yra įtrauktas agentui būdingo grėsmių modeliavimas ir rizikos įvertinimas.

---

### Nuorodos

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

## C5 Prieigos valdymas ir tapatybės nustatymas AI komponentams ir naudotojams

### Valdymo tikslas

Efektyvi prieigos kontrolė AI sistemoms reikalauja tvirto tapatybės valdymo, kontekstą atitinkančios autorizacijos ir vykdymo realiuoju laiku pagal nulinės pasitikėjimo principus. Šios kontrolės užtikrina, kad žmonės, paslaugos ir autonominiai agentai sąveikautų tik su modeliais, duomenimis ir skaičiavimo ištekliais griežtai nustatytose ribose, vykdant nuolatinį patikrinimą ir audito galimybes.

---

### C5.1 Tapatybės valdymas ir autentifikacija

Sukurkite visų subjektų kriptografiškai pagrįstas tapatybes su daugiafaktorine autentifikacija privilegijuotoms operacijoms.

 #5.1.1    Level: 1    Role: D/V
 Patvirtinkite, kad visi žmonių vartotojai ir paslaugų principalai autentifikuojasi per centralizuotą įmonės identiteto tiekėją (IdP) naudojant OIDC/SAML protokolus su unikaliais tapatybės į žetoną susiejimais (be bendrinamų paskyrų ar kredencialų).
 #5.1.2    Level: 1    Role: D/V
 Patikrinkite, ar didelės rizikos operacijos (modelio diegimas, svorių eksportas, mokymo duomenų prieiga, gamybos konfigūracijos pakeitimai) reikalauja daugiaplanio autentifikavimo arba papildomo autentifikavimo su sesijos pakartotiniu patvirtinimu.
 #5.1.3    Level: 2    Role: D
 Patikrinkite, ar nauji vadovai prieš įgaudami prieigą prie gamybos sistemos yra patvirtinti tapatybės pagal NIST 800-63-3 IAL-2 arba lygiavertius standartus.
 #5.1.4    Level: 2    Role: V
 Patikrinkite, ar prieigos peržiūros atliekamos kas ketvirtį, naudojant automatizuotą neveiklių paskyrų aptikimą, kredencialų sukimosi laikymą ir deprovisionavimo veiklos procesus.
 #5.1.5    Level: 3    Role: D/V
 Patikrinkite, ar federuoti DI agentai autentifikuojami per pasirašytus JWT tvirtinimus, kurių maksimalus galiojimo laikas yra 24 valandos ir kuriuose yra kriptografinis kilmės įrodymas.

---

### C5.2 Išteklių autorizacija ir mažiausios privilegijos

Įdiekite smulkios kontrolės prieigą prie visų DI išteklių naudodami aiškius leidimų modelius ir audito pėdsakus.

 #5.2.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas DI išteklius (duomenų rinkiniai, modeliai, galutiniai taškai, vektorių kolekcijos, įterptųjų indeksai, skaičiavimo instancijos) taiko vaidmenų pagrindu paremtą prieigos kontrolę su aiškiomis leidimų sąrašais ir numatytomis draudimo politikomis.
 #5.2.2    Level: 1    Role: D/V
 Patikrinkite, ar pagal numatytuosius nustatymus su paslaugų paskyromis taikomi mažiausios privilegijos principai, pradedant nuo tik skaitymo teisių, o rašymo prieigai reikalingas dokumentuotas verslo pateisinimas.
 #5.2.3    Level: 1    Role: V
 Patikrinkite, ar visi prieigos valdymo pakeitimai yra susieti su patvirtintais pakeitimų prašymais ir nekeičiamai įrašyti su laiko žymomis, veikėjų tapatybėmis, išteklių identifikatoriais ir leidimų skirtumais.
 #5.2.4    Level: 2    Role: D
 Patikrinkite, ar duomenų klasifikacijos etiketės (asmens identifikavimo informacija - PII, sveikatos informacija - PHI, eksporto kontrolė, nuosavybės teisės) automatiškai perduodamos išvestinėms ištekliams (įterpimams, užklausų talpykloms, modelio išvestims) užtikrinant nuoseklų politikos vykdymą.
 #5.2.5    Level: 2    Role: D/V
 Patikrinkite, ar neautorizuoti prieigos bandymai ir privilegijų eskalavimo įvykiai sukelia realaus laiko įspėjimus su kontekstine metaduomenimis SIEM sistemoms per 5 minutes.

---

### C5.3 Dinaminis politikos vertinimas

Diegti atributais pagrįstą prieigos valdymo (ABAC) sistemą, skirtą kontekstiniais duomenimis pagrįstiems autorizacijos sprendimams, turint audito galimybes.

 #5.3.1    Level: 1    Role: D/V
 Patikrinkite, ar autorizacijos sprendimai yra išoriniai ir perduodami specialiai skirtam politikos varikliui (OPA, Cedar ar ekvivalentui), kuris yra pasiekiamas per autentifikuotus API su kriptografinės vientisybės apsauga.
 #5.3.2    Level: 1    Role: D/V
 Patikrinkite, ar politikos įvertina dinamiškus atributus vykdymo metu, įskaitant vartotojo leidimo lygį, išteklių jautrumo klasifikaciją, užklausos kontekstą, nuomininko izoliaciją ir laiko apribojimus.
 #5.3.3    Level: 2    Role: D
 Patikrinkite, ar politikos apibrėžimai yra valdomi versijų kontrole, peržiūrimi kolegų ir patvirtinami automatizuotais testavimais CI/CD grandinėse prieš diegiant į gamybą.
 #5.3.4    Level: 2    Role: V
 Patikrinkite, ar politikos vertinimo rezultatai apima struktūruotas sprendimų priežastis ir yra perduodami SIEM sistemoms koreliacijos analizei ir atitikties ataskaitų teikimui.
 #5.3.5    Level: 3    Role: D/V
 Patikrinkite, ar politikos talpyklos laiko gyvavimo (TTL) reikšmės neviršija 5 minučių jautriems ištekliams ir 1 valandos standartiniams ištekliams su talpyklos nebegaliojimo galimybėmis.

---

### C5.4 Užklausos laikotarpio saugumo užtikrinimas

Įgyvendinkite duomenų bazės lygio saugumo valdiklius su privaloma filtracija ir eilutės lygio saugumo politikomis.

 #5.4.1    Level: 1    Role: D/V
 Patikrinkite, ar visi vektorinių duomenų bazių ir SQL užklausos apima privalomus saugumo filtrus (nuomininko ID, jautrumo žymas, vartotojo aprėptį), kurie yra įgyvendinti duomenų bazės variklio lygyje, o ne programos kodo lygyje.
 #5.4.2    Level: 1    Role: D/V
 Patikrinkite, ar eilučių lygio saugumo (RLS) politikos ir laukų lygio maskavimas yra įgalinti su politikos paveldėjimu visose vektorinių duomenų baze, paieškos indeksų ir mokymo duomenų rinkiniuose.
 #5.4.3    Level: 2    Role: D
 Patikrinkite, ar nepavykusios autorizacijos vertinimai užkirs kelią „supainioto tarnytojo atakoms“ nedelsiant nutraukiant užklausas ir grąžinant aiškius autorizacijos klaidų kodus, o ne tuščius rezultatų rinkinius.
 #5.4.4    Level: 2    Role: V
 Patikrinkite, ar politikos vertinimo delsos laikas nuolat stebimas su automatiniais įspėjimais apie laiko viršijimo sąlygas, kurios galėtų leisti apeiti autorizaciją.
 #5.4.5    Level: 3    Role: D/V
 Patikrinkite, ar užklausų pakartojimo mechanizmai iš naujo vertina autorizacijos politikas, atsižvelgdami į dinamiškus leidimų pakeitimus aktyvių naudotojų sesijų metu.

---

### C5.5 Išvesties filtravimas ir duomenų praradimo prevencija

Vykdykite galutinio apdorojimo kontrolę, kad būtų užkirstas kelias neleistinam duomenų atskleidimui AI sugeneruotame turinyje.

 #5.5.1    Level: 1    Role: D/V
 Patikrinkite, ar po inferencijos filtravimo mechanizmai nuskenuoja ir pašalina neautorizuotą asmeninę identifikuojamą informaciją (PII), klasifikuotą informaciją ir nuosavybės duomenis prieš pateikiant turinį užklausos teikėjams.
 #5.5.2    Level: 1    Role: D/V
 Patikrinkite, ar modelio išvestyse esantys citavimai, nuorodos ir šaltinių priskyrimai yra patvirtinti pagal kviečiančiojo teises, ir pašalinkite juos, jei nustatoma neautorizuota prieiga.
 #5.5.3    Level: 2    Role: D
 Patikrinkite, ar išvesties formato apribojimai (valyti PDF failai, nuotraukos be metaduomenų, patvirtinti failų tipai) yra taikomi pagal vartotojo leidimų lygius ir duomenų klasifikacijas.
 #5.5.4    Level: 2    Role: V
 Patikrinkite, ar redagavimo algoritmai yra deterministiniai, versijų valdomi ir palaiko audito žurnalus, kad būtų užtikrinta atitikties tyrimų ir forensikos analizės galimybė.
 #5.5.5    Level: 3    Role: V
 Patikrinkite, ar didelės rizikos redagavimo įvykiai generuoja adaptuojamus žurnalus, kuriuose yra pirminio turinio kriptografiniai maišos žymekliai, skirti teismo ekspertizės atkūrimui be duomenų atskleidimo.

---

### C5.6 Daugiakartinė nuomininkų izoliacija

Užtikrinkite kriptografinę ir loginę izoliaciją tarp nuomininkų bendroje DI infrastruktūroje.

 #5.6.1    Level: 1    Role: D/V
 Patikrinkite, ar atminties vietos, įterpimo saugyklos, talpyklos įrašai ir laikini failai yra atskirti pagal vardų sritis kiekvienam nuomininkui, užtikrinant saugų jų ištrynimą nuomininkui pašalinus arba užbaigus sesiją.
 #5.6.2    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas API užklausimas apima autentifikuotą nuomininko identifikatorių, kuris yra kriptografiškai patvirtintas atsižvelgiant į sesijos kontekstą ir naudotojo teises.
 #5.6.3    Level: 2    Role: D
 Patikrinkite, ar tinklo politikos įgyvendina numatytąjį draudimo principą (default-deny) tarp nuomininkų bendravimo paslaugų tinkleliuose ir konteinerių koordinavimo platformose.
 #5.6.4    Level: 3    Role: D
 Patikrinkite, ar šifravimo raktai yra unikalūs kiekvienam nuomininkui, naudojant kliento valdomą raktą (CMK) ir užtikrinant kriptografinę izoliaciją tarp nuomininkų duomenų saugyklų.

---

### C5.7 Autonominio agente autorizavimas

Valdykite AI agentų ir autonominių sistemų teises naudodami apriboto galiojimo gebėjimų žetonus ir nuolatinį autorizavimą.

 #5.7.1    Level: 1    Role: D/V
 Patikrinkite, ar autonominiai agentai gauna apribotųjų galimybių žetonus, kurie aiškiai nurodo leidžiamus veiksmus, prieinamus išteklius, laiko ribas ir veiklos apribojimus.
 #5.7.2    Level: 1    Role: D/V
 Patikrinkite, ar didelę riziką keliančios galimybės (prieiga prie failų sistemos, kodo vykdymas, išoriniai API kvietimai, finansinės operacijos) pagal numatytuosius nustatymus yra išjungtos ir jų aktyvavimui reikalingi aiškūs leidimai su verslo pagrindimais.
 #5.7.3    Level: 2    Role: D
 Patikrinkite, ar galios žetonai yra susieti su naudotojo sesijomis, įtraukti kriptografinės vientisumo apsaugą ir užtikrinti, kad jų negalima būtų išsaugoti ar pakartotinai naudoti neprisijungus.
 #5.7.4    Level: 2    Role: V
 Patikrinkite, ar agento inicijuotos akcijos pereina antrinį autorizavimą per ABAC politikos variklį su pilnu konteksto įvertinimu ir audito žurnalų fiksavimu.
 #5.7.5    Level: 3    Role: V
 Patikrinkite, ar agentų klaidų sąlygos ir išimčių apdorojimas apima galimybių srities informaciją, kad būtų galima palaikyti incidentų analizę ir teismo ekspertizę.

---

### Nuorodos

#### Standartai ir pagrindai

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Įgyvendinimo vadovai

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Dirbtinio intelekto specifinis saugumas

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 tiekimo grandinės saugumas modeliams, sistemoms ir duomenims

### Kontrolės tikslas

AI tiekimo grandinės atakos išnaudoja trečiųjų šalių modelius, karkasus ar duomenų rinkinius, kad įterptų užpakalinius vartus, šališkumą arba pažeidžiamą kodą. Šios kontrolės užtikrina visapusišką kilmės sekimą, pažeidžiamumo valdymą ir stebėjimą, siekiant apsaugoti visą modelio gyvavimo ciklą.

---

### C6.1 Iš anksto apmokyto modelio tikrinimas ir kilmė

Įvertinkite ir patikrinkite trečiųjų šalių modelių kilmę, licencijas ir paslėptas elgsenas prieš atliekant bet kokį tobulinimą ar diegimą.

 #6.1.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas trečiosios šalies modelio artefaktas turi pasirašytą kilmės įrašą, identifikuojantį šaltinio saugyklą ir commit hash.
 #6.1.2    Level: 1    Role: D/V
 Patvirtinkite, kad modeliai prieš importavimą yra nuskaityti automatizuotomis priemonėmis, siekiant aptikti kenksmingas sluoksnius ar Trojos arklių trigerius.
 #6.1.3    Level: 2    Role: D
 Patikrinkite, ar perdavimo mokymosi tobulinimas praeina priešininkų vertinimą, kad aptiktų paslėptas elgsenas.
 #6.1.4    Level: 2    Role: V
 Patikrinkite, ar modelio licencijos, eksporto kontrolės žymos ir duomenų kilmės pareiškimai yra įrašyti ML-BOM įraše.
 #6.1.5    Level: 3    Role: D/V
 Patikrinkite, ar didelės rizikos modeliai (viešai įkelti svoriai, nepatikrinti kūrėjai) lieka izoliuoti iki žmogaus peržiūros ir patvirtinimo.

---

### C6.2 Sistemų karkasų ir bibliotekų nuskaitymas

Nuolat tikrinkite mašininio mokymosi sistemas ir bibliotekas dėl CVE spragų ir kenkėjiško kodo, kad vykdymo aplinka išliktų saugi.

 #6.2.1    Level: 1    Role: D/V
 Patikrinkite, ar CI kanalai vykdo priklausomybių skenerius AI karkasams ir svarbioms bibliotekoms.
 #6.2.2    Level: 1    Role: D/V
 Patikrinkite, ar kritinės pažeidžiamybės (CVSS ≥ 7,0) neleidžia diegti atvaizdų į gamybą.
 #6.2.3    Level: 2    Role: D
 Patikrinkite, ar statinė kodo analizė vykdoma ant šakotuose ar įsigytuose ML bibliotekų.
 #6.2.4    Level: 2    Role: V
 Patikrinkite, ar karkaso atnaujinimo pasiūlymai apima saugumo poveikio vertinimą, nurodantį viešai prieinamus CVE srautus.
 #6.2.5    Level: 3    Role: V
 Patikrinkite, ar vykdymo metu jutikliai įspėja apie netikėtus dinaminės bibliotekos įkėlimus, kurie skiriasi nuo pasirašyto SBOM.

---

### C6.3 Priklausomybių fiksavimas ir patikra

Pririškite kiekvieną priklausomybę prie nekeičiamų digestų ir atkurkite kūrimus, kad užtikrintumėte identiškus, be klastojimo artefaktus.

 #6.3.1    Level: 1    Role: D/V
 Patikrinkite, ar visi paketų valdytojai užtikrina versijų fiksavimą naudojant užrakto failus.
 #6.3.2    Level: 1    Role: D/V
 Patikrinkite, ar konteinerių nuorodose naudojami nekintami santraukos vietoj kintamų žymų.
 #6.3.3    Level: 2    Role: D
 Patikrinkite, ar atkartojamumo patikros procesai palygina maišos reikšmes tarp CI vykdymų, siekiant užtikrinti identiškus rezultatus.
 #6.3.4    Level: 2    Role: V
 Patikrinkite, ar kūrimo patvirtinimai saugomi 18 mėnesių audito sekimumo užtikrinimui.
 #6.3.5    Level: 3    Role: D
 Patikrinkite, ar pasibaigusios priklausomybės sukelia automatinius PR atnaujinti arba padalinti užfiksuotas versijas.

---

### C6.4 Patikimo šaltinio vykdymas

Leisti atsisiųsti artefaktus tik iš kriptografiškai patikrintų, organizacijos patvirtintų šaltinių ir blokuoti viską, kas kitas.

 #6.4.1    Level: 1    Role: D/V
 Patikrinkite, ar modelio svoriai, duomenų rinkiniai ir konteineriai atsisiunčiami tik iš patvirtintų domenų arba vidinių registrų.
 #6.4.2    Level: 1    Role: D/V
 Patikrinkite, ar Sigstore/Cosign parašai patvirtina leidėjo tapatybę prieš saugant artefaktus vietoje.
 #6.4.3    Level: 2    Role: D
 Patikrinkite, ar eigos tarpiniai serveriai blokuoja neautentifikuotus artefaktų atsisiuntimus, siekiant įgyvendinti patikimos kilmės politiką.
 #6.4.4    Level: 2    Role: V
 Patikrinkite, ar krūva leidžiamų saugyklų sąrašai peržiūrimi kas ketvirtį, pateikiant verslo pagrįstumą kiekvienam įrašui.
 #6.4.5    Level: 3    Role: V
 Patikrinkite, ar politikos pažeidimai sukelia artefaktų izoliavimą ir priklausančių vamzdyno vykdymų atšaukimą.

---

### C6.5 Trečiųjų šalių duomenų rinkinio rizikos įvertinimas

Įvertinkite išorinius duomenų rinkinius dėl užnuodijimo, šališkumo ir teisinių atitikties reikalavimų bei stebėkite juos per visą jų gyvavimo ciklą.

 #6.5.1    Level: 1    Role: D/V
 Patikrinkite, ar išoriniai duomenų rinkiniai yra įvertinami dėl užteršimo rizikos (pvz., duomenų pirštų atspaudų nustatymas, išskirtinių reikšmių aptikimas).
 #6.5.2    Level: 1    Role: D
 Patikrinkite, ar šališkumo metrika (demografinis lygybės principas, lygi galimybė) yra apskaičiuojama prieš duomenų rinkinio patvirtinimą.
 #6.5.3    Level: 2    Role: V
 Patikrinkite, ar ML-BOM įrašuose yra užfiksuoti duomenų rinkinių kilmės ir licencijos sąlygos.
 #6.5.4    Level: 2    Role: V
 Patikrinkite, ar periodinis stebėjimas aptinka perėjimą arba gedimą talpinamuose duomenų rinkiniuose.
 #6.5.5    Level: 3    Role: D
 Patikrinkite, ar neleistinas turinys (autorių teisės, asmeninė identifikuojama informacija) yra pašalintas automatinio šalinimo būdu prieš treniruotę.

---

### C6.6 Tiekimo grandinės atakų stebėjimas

Anksti aptikite tiekimo grandinės grėsmes naudodamiesi CVE srautais, audito žurnalo analitika ir raudonosios komandos simuliacijomis.

 #6.6.1    Level: 1    Role: V
 Patikrinkite, ar CI/CD audito žurnalai perduodami SIEM sistemai anomalinių paketų traukimo ar pažeistų statybos etapų aptikimams.
 #6.6.2    Level: 2    Role: D
 Patikrinkite, ar incidentų reagavimo veiksmų planuose yra įtrauktos modelių ar bibliotekų atstatymo (rollback) procedūros dėl pažeidimų.
 #6.6.3    Level: 3    Role: V
 Patikrinkite, ar grėsmių intelektinės informacijos praturtėjimo žymos pažymi ML specifinius indikatorius (pvz., modelio užnuodijimo IoC) įspėjimų atrankoje.

---

### C6.7 ML-BOM modelio artefaktams

Generuokite ir pasirašykite detalias ML specifines SBOM (ML-BOM), kad galutiniai vartotojai galėtų patikrinti komponentų vientisumą diegimo metu.

 #6.7.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas modelio artefaktas publikuoja ML‑BOM, kuriame išvardyti duomenų rinkiniai, svoriai, hiperparametrai ir licencijos.
 #6.7.2    Level: 1    Role: D/V
 Patikrinkite, ar ML-BOM generavimas ir Cosign pasirašymas yra automatizuoti CI ir privalomi sujungimui.
 #6.7.3    Level: 2    Role: D
 Patikrinkite, ar ML‑BOM pilnumo patikrinimai sustabdo kompiliavimą, jei trūksta bet kokios komponento metaduomenų (hash, licencija).
 #6.7.4    Level: 2    Role: V
 Patvirtinkite, kad galutiniai vartotojai gali užklausti ML-BOM per API, siekdami patikrinti importuotus modelius diegimo metu.
 #6.7.5    Level: 3    Role: V
 Patikrinkite, ar ML-BOM yra valdomi versijomis ir palyginami, siekiant aptikti neautorizuotus pakeitimus.

---

### Nuorodos

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

## C7 modelio elgsena, išvesties kontrolė ir saugumo užtikrinimas

### Valdymo tikslas

Modelio išvestys turi būti struktūruotos, patikimos, saugios, paaiškinamos ir nuolat stebimos gamybos aplinkoje. Tai sumažina haliucinacijas, privatumo nutekėjimus, žalingą turinį ir nekontroliuojamus veiksmus, tuo pačiu didinant vartotojų pasitikėjimą ir atitiktį reguliavimams.

---

### C7.1 Išvesties formato užtikrinimas

Griežtos schemos, ribotinis dekodavimas ir tolesnė validacija sustabdo neteisingai suformuotą arba kenksmingą turinį dar prieš jam išplitimą.

 #7.1.1    Level: 1    Role: D/V
 Patikrinkite, ar atsakymų schemos (pvz., JSON schema) yra pateiktos sistemos paklausime ir ar kiekvienas išvesties rezultatas automatiškai tikrinamas; nesilaikantys reikalavimų rezultatai sukelia taisymą arba atmetimą.
 #7.1.2    Level: 1    Role: D/V
 Patikrinkite, ar įjungtas ribotas dekodavimas (stabdymo ženklai, reguliariosios išraiškos, maksimalus ženklų skaičius), siekiant išvengti perpildymo ar užklausos injekcijos šoninių kanalų.
 #7.1.3    Level: 2    Role: D/V
 Patikrinkite, ar tolesnės grandies komponentai traktuoja išvestis kaip nepatikimas ir patikrina jas pagal schemas arba saugius nuo injekcijų de-serializatorius.
 #7.1.4    Level: 3    Role: V
 Patikrinkite, ar netinkami išvesties įvykiai yra registruojami, ribojami pagal dažnį ir pateikiami stebėsenai.

---

### C7.2 Halucinacijų aptikimas ir mažinimas

Neapibrėžtumo įvertinimas ir atsarginės strategijos riboja suklastotus atsakymus.

 #7.2.1    Level: 1    Role: D/V
 Patikrinkite, ar žodžio lygio logaritminės tikimybės, kolektyvinis savikonsistentiškumas arba specialiai pritaikyti haliucinacijų aptikimo įrankiai priskiria pasitikėjimo balą kiekvienam atsakymui.
 #7.2.2    Level: 1    Role: D/V
 Patikrinkite, ar atsakymai, kurių pasitikėjimo lygis žemesnis už konfigūruojamą slenkstį, sukelia atsarginio veiksmų plano vykdymą (pvz., papildytą gavimo generavimą, antrinį modelį arba žmogaus peržiūrą).
 #7.2.3    Level: 2    Role: D/V
 Patikrinkite, ar haliucinacijų atvejai yra pažymėti šakninių priežasčių metaduomenimis ir perduodami analizės po įvykio bei tobulinimo (finetuning) grandinėms.
 #7.2.4    Level: 3    Role: D/V
 Patikrinkite, ar slenksčiai ir detektoriai yra perkaliibruoti po reikšmingų modelio ar žinių bazės atnaujinimų.
 #7.2.5    Level: 3    Role: V
 Patikrinkite, ar skydelio vizualizacijos stebi halucinacijų dažnius.

---

### C7.3 Išvesties saugumo ir privatumo filtravimas

Politikos filtrai ir raudonosios komandos aprėptis saugo vartotojus ir konfidencialius duomenis.

 #7.3.1    Level: 1    Role: D/V
 Patikrinkite, ar priešgaminimo ir po generavimo klasifikatoriai blokuoja neapykantos, priekabiavimo, savęs žalojimo, ekstremistinio ir seksualiai atvirą turinį, atitinkantį politiką.
 #7.3.2    Level: 1    Role: D/V
 Patikrinkite, ar kiekviename atsakyme veikia PII/PCI aptikimas ir automatinis slėpimas; pažeidimai sukelia privatumo incidentą.
 #7.3.3    Level: 2    Role: D
 Patikrinkite, ar konfidencialumo žymos (pvz., prekybos paslaptys) sklinda per įvairias turinio formas, kad būtų išvengta nutekėjimo tekste, vaizduose ar kode.
 #7.3.4    Level: 3    Role: D/V
 Patikrinkite, ar filtro apeidimo bandymai arba didelės rizikos klasifikacijos reikalauja antrinio patvirtinimo arba vartotojo pakartotinio autentifikavimo.
 #7.3.5    Level: 3    Role: D/V
 Patikrinkite, ar filtravimo slenkstiai atitinka teisinius jurisdikcijos reikalavimus ir vartotojo amžiaus/vaidmens kontekstą.

---

### C7.4 Išvesties ir veiksmų apribojimas

Ribojimai ir patvirtinimo vartai neleidžia piktnaudžiauti ir užtikrina kontroliuojamą autonomiją.

 #7.4.1    Level: 1    Role: D
 Patikrinkite, ar naudotojo ir API rakto kvotos riboja užklausas, žetonus ir kaštus, taikant eksponentinį atsitraukimą 429 klaidų atveju.
 #7.4.2    Level: 1    Role: D/V
 Patikrinkite, ar privilegijuotos operacijos (failų rašymas, kodo vykdymas, tinklo užklausos) reikalauja politikos pagrindu patvirtinimo arba žmogaus įsikišimo.
 #7.4.3    Level: 2    Role: D/V
 Patikrinkite, ar kryžmodaliniai nuoseklumo patikrinimai užtikrina, kad vienam užklausimui sugeneruotos nuotraukos, kodas ir tekstas negali būti naudojami piktavališkam turiniui slepiant.
 #7.4.4    Level: 2    Role: D
 Patikrinkite, ar agento delegavimo gylis, rekursijos apribojimai ir leidžiamų įrankių sąrašai yra aiškiai sukonfigūruoti.
 #7.4.5    Level: 3    Role: V
 Patikrinkite, ar limitų pažeidimai sukelia struktūruotus saugumo įvykius SIEM įsisavinimui.

---

### C7.5 Išvesties paaiškinamumas

Permatomi signalai gerina vartotojų pasitikėjimą ir vidinį derinimą.

 #7.5.1    Level: 2    Role: D/V
 Patikrinkite, ar naudotojui matomi pasitikėjimo įvertinimai ar trumpi sprendimų pateisinimai pateikiami, kai rizikos vertinimas tai laikytina tinkama.
 #7.5.2    Level: 2    Role: D/V
 Patikrinkite, ar sugeneruoti paaiškinimai neatskleidžia jautrių sistemos užklausų ar konfidencialios informacijos.
 #7.5.3    Level: 3    Role: D
 Patikrinkite, ar sistema fiksuoja žodžio lygio tikimybės logaritmus arba dėmesio žemėlapius ir saugo juos autorizuotam patikrinimui.
 #7.5.4    Level: 3    Role: V
 Patikrinkite, ar aiškinamumo artefaktai yra valdomi versijų kontrolės sistema kartu su modelių leidimais audito galimybei.

---

### C7.6 Stebėjimo integracija

Realaus laiko stebėjimas uždaro ciklą tarp kūrimo ir gamybos.

 #7.6.1    Level: 1    Role: D
 Patikrinkite, ar įvairūs metrikai (schemos pažeidimai, haliucinacijų dažnis, toksiškumas, asmeninės informacijoss nutekėjimas, vėlavimas, sąnaudos) yra perduodami į centrinę stebėjimo platformą.
 #7.6.2    Level: 1    Role: V
 Patikrinkite, ar kiekvienam saugumo metrikos rodikliui yra apibrėžti įspėjimo slenksčiai, kartu su budėjimo metu skubios eskalacijos keliais.
 #7.6.3    Level: 2    Role: V
 Patikrinkite, ar prietaisų skydeliai koreliuoja išvesties anomalijas su modelio/versijos, funkcijų žymos ir aukštesnio lygio duomenų pakeitimais.
 #7.6.4    Level: 2    Role: D/V
 Patikrinkite, ar stebėjimo duomenys grįžta atgal į pakartotinį mokymą, tikslinimą arba taisyklių atnaujinimą dokumentuoto MLOps darbo eigos metu.
 #7.6.5    Level: 3    Role: V
 Patikrinkite, ar stebėjimo dujotiekiams atliekami įsiskverbimo testai ir ar prieiga yra kontroliuojama, kad būtų išvengta jautrios informacijos nuotėkio.

---

### 7.7 Generatyvinės medijos apsaugos priemonės

Užtikrinkite, kad DI sistemos negeneruotų neteisėtos, žalingos ar neautorizuotos medijos turinio, taikant politikos apribojimus, išvesties patvirtinimą ir stebimumo galimybes.

 #7.7.1    Level: 1    Role: D/V
 Patikrinkite, ar sistemos nurodymai ir vartotojo instrukcijos aiškiai draudžia kurti neteisėtą, žalingą arba nepritariamai sukurtą deepfake medžiagą (pvz., vaizdus, vaizdo įrašus, garsą).
 #7.7.2    Level: 2    Role: D/V
 Patikrinkite, ar prašymai yra filtruojami siekiant užkirsti kelią bandymams generuoti įsikūnijimus, seksualiai atviras giliųjų klastočių ar medžiagą, vaizduojančią tikrus asmenis be jų sutikimo.
 #7.7.3    Level: 2    Role: V
 Patikrinkite, ar sistema naudoja perceptual hashing, vandens ženklo aptikimą arba pirštų atspaudų nustatymą, siekiant užkirsti kelią neautorizuotam autorių teisių saugomos medžiagos kopijavimui.
 #7.7.4    Level: 3    Role: D/V
 Patikrinkite, ar visa sugeneruota medija yra kriptografiškai pasirašyta, pažymėta vandens ženklais arba įdėta su atspariais klastojimui kilmės metaduomenimis, siekiant užtikrinti tolesnį stebėjimą.
 #7.7.5    Level: 3    Role: V
 Patikrinkite, ar apeinimo bandymai (pvz., užklausų užmaskavimas, šnekamoji kalba, priešiškas formuluotės naudojimas) yra aptinkami, registruojami ir ribojami pagal dažnį; pasikartojantis piktnaudžiavimas pranešamas stebėjimo sistemoms.

### Nuorodos

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

## C8 atminties, įterpimų ir vektorinės duomenų bazės saugumas

### Valdymo tikslas

Įterpimai ir vektorių saugyklos veikia kaip šiuolaikinių DI sistemų „gyvoji atmintis“, nuolat priimdamos vartotojo pateiktus duomenis ir grąžindamos juos į modelio kontekstus per paieškos papildytą generavimą (RAG). Jei ši atmintis nėra tinkamai valdomi, ji gali išleisti asmens identifikuojančią informaciją (PII), pažeisti sutikimą arba būti panaudota originaliam tekstui atkurti. Šios kontrolės šeimos tikslas yra sustiprinti atminties srautus ir vektorių duomenų bazes taip, kad prieiga būtų minimaliai privilegijuota, įterpimai išsaugotų privatumą, saugomi vektoriai pasibaigtų galiojimu arba būtų atšaukiami pagal poreikį, o kiekvieno vartotojo atmintis niekada nesimaišytų su kito vartotojo užklausomis ar atsakymais.

---

### C8.1 Prieigos valdymas atmintyje ir RAG indeksuose

Įgyvendinkite smulkiai sugriežtintą prieigos kontrolę kiekvienoje vektorių kolekcijoje.

 #8.1.1    Level: 1    Role: D/V
 Patikrinkite, ar eilučių/erdvės lygių prieigos valdymo taisyklės riboja įterpimo, trynimo ir užklausų operacijas pagal nuomininką, kolekciją ar dokumento žymą.
 #8.1.2    Level: 1    Role: D/V
 Patikrinkite, ar API raktai arba JWT turi aprėpties teiginius (pvz., kolekcijų ID, veiksmų veiksmažodžius) ir ar jie keičiami bent kartą per ketvirtį.
 #8.1.3    Level: 2    Role: D/V
 Patikrinkite, ar privilegijų eskalavimo bandymai (pvz., kryžminio vardų srities panašumo užklausos) yra aptinkami ir per 5 minutes registruojami SIEM.
 #8.1.4    Level: 2    Role: D/V
 Patikrinkite, ar vektorinė duomenų bazė audituoja logus, įskaitant subjekto identifikatorių, operaciją, vektorinio ID/vardų sritį, panašumo slenkstį ir rezultatų kiekį.
 #8.1.5    Level: 3    Role: V
 Patikrinkite, ar prieigos sprendimai yra tikrinami dėl apeidimo trūkumų kiekvieną kartą atnaujinant variklius arba keičiant indeksų skaidymo taisykles.

---

### C8.2 Įterpimų valymas ir patikra

Išankstinai patikrinkite tekstą dėl asmeninių identifikuojamų duomenų (PII), užmaskuokite ar pseudonimizuokite prieš vektorizavimą ir, jei pageidaujama, atlikite papildomą įdėjų apdorojimą, kad pašalintumėte liekamuosius signalus.

 #8.2.1    Level: 1    Role: D/V
 Patikrinkite, ar asmeninė tapatybės informacija (PII) ir reguliuojami duomenys yra aptinkami automatinių klasifikatorių pagalba bei prieš įterpimą yra maskuojami, pavirstami į žetonus arba pašalinami.
 #8.2.2    Level: 1    Role: D
 Patikrinkite, ar įdiegimo vamzdynai atmeta arba izoliuoja įvestis, kuriose yra vykdomojo kodo arba ne UTF-8 artefaktų, galinčių užnuodyti indeksą.
 #8.2.3    Level: 2    Role: D/V
 Patikrinkite, ar vietinis arba metrinis skirtumo privatumo (differential-privacy) sanitarizavimas yra taikomas sakinių įterpimams, kurių atstumas iki bet kurio žinomo PII žymens yra mažesnis už konfigūruojamą slenkstį.
 #8.2.4    Level: 2    Role: V
 Patikrinkite, ar sanitarizacijos efektyvumas (pvz., asmeninės informacijos (PII) redagavimo atsimenamumas, semantinis poslinkis) yra patvirtintas bent pusmečio dažnumu naudojant etalonines korpusų rinkinius.
 #8.2.5    Level: 3    Role: D/V
 Patikrinkite, ar sanitizacijos konfigūracijos yra valdomos versijų sistema ir ar pakeitimai yra peržiūrimi kolegų.

---

### C8.3 Atminties galiojimo pabaiga, atšaukimas ir ištrynimas

BDAR „teisė būti pamirštam“ ir panašūs įstatymai reikalauja laiku ištrinti duomenis; todėl vektorių saugyklos turi palaikyti gyvavimo trukmės ribojimą (TTL), griežtą ištrynimą ir užrašų naikinimą (tomb-stoning), kad atšaukti vektoriai negalėtų būti atkurti arba vėl indeksuoti.

 #8.3.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas vektorius ir metaduomenų įrašas turi TTL arba aiškų saugojimo etiketę, kurią gerbia automatiniai valymo darbai.
 #8.3.2    Level: 1    Role: D/V
 Patikrinkite, ar vartotojo inicijuoti ištrynimo prašymai per 30 dienų ištrina vektorius, metaduomenis, talpyklos kopijas ir darinines indeksus.
 #8.3.3    Level: 2    Role: D
 Patikrinkite, ar loginiai ištrynimai yra sekami kriptografiniu saugojimo blokų sunaikinimu, jei aparatūra tai palaiko, arba rakto saugyklos rakto sunaikinimu.
 #8.3.4    Level: 3    Role: D/V
 Patikrinkite, ar pasibaigę vektoriai yra pašalinti iš artimiausių kaimynų paieškos rezultatų per mažiau nei 500 ms po galiojimo pabaigos.

---

### C8.4 Užkirsti kelią įterpimo inversijai ir nutekėjimui

Naujausios apsaugos priemonės – triukšmo pridėjimas, projekcijos tinklai, privatumo neuronų trikdymas ir aplikacijos sluoksnio šifravimas – gali sumažinti simbolių lygio apvertimo rodiklius iki mažiau nei 5%.

 #8.4.1    Level: 1    Role: V
 Patikrinkite, ar egzistuoja oficialus grėsmių modelis, apimantis inversijos, narystės ir atributo spėjimo atakas, ir ar jis peržiūrimas kasmet.
 #8.4.2    Level: 2    Role: D/V
 Patikrinkite, ar programinio sluoksnio šifravimas arba ieškoma šifravimas apsaugo vektorius nuo tiesioginių skaitymų infrastruktūros administratorių ar debesijos personalo.
 #8.4.3    Level: 3    Role: V
 Patikrinkite, ar gynybos parametrai (ε DP, triukšmas σ, projekcijos rangas k) užtikrina privatumą ≥ 99 % tokenų apsaugą ir naudingumą ≤ 3 % tikslumo sumažėjimą.
 #8.4.4    Level: 3    Role: D/V
 Patikrinkite, ar apverčiamosios atsparumo metrikos yra modelio atnaujinimų išleidimo slenksčių dalis, su apibrėžtais regresijos biudžetais.

---

### C8.5 Vartotojui būdingos atminties aprėpties įgyvendinimas

Kryžminis duomenų nutekėjimas tarp nuomininkų išlieka pagrindine RAG rizika: netinkamai filtruoti panašumo užklausos gali atskleisti kito kliento privačius dokumentus.

 #8.5.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas užklausimo atgavimas yra filtruojamas pagal nuomininko/vartotojo ID prieš pateikiant LLM užklausos formavimo metu.
 #8.5.2    Level: 1    Role: D
 Patikrinkite, ar kolekcijų pavadinimai arba vardų erdvėje naudojami ID yra pasūdyti kiekvienam vartotojui arba nuomininkui, kad vektoriai negalėtų sutapti skirtingose apimtyse.
 #8.5.3    Level: 2    Role: D/V
 Patikrinkite, ar panašumo rezultatai, viršijantys konfigūruojamą atstumo ribą, tačiau už kvietėjo aprėpties ribų, yra atmestami ir sukelia saugumo įspėjimus.
 #8.5.4    Level: 2    Role: V
 Patikrinkite, ar daugianuominiai apkrovos testai imituoja priešiškus užklausas, siekiančias gauti netinkamus dokumentus, ir užtikrina, kad nebūtų jokio nutekėjimo.
 #8.5.5    Level: 3    Role: D/V
 Patikrinkite, ar šifravimo raktai yra atskirti kiekvienam nuomininkui, užtikrinant kriptografinį izoliavimą net jei fizinė saugykla yra bendrinama.

---

### C8.6 Pažangi atminties sistemos sauga

Saugumo valdymas pažangioms atminties architektūroms, įskaitant epizodinę, semantinę ir darbinę atmintį, su specifiniais izoliacijos ir validacijos reikalavimais.

 #8.6.1    Level: 1    Role: D/V
 Patikrinkite, ar skirtingi atminties tipai (episodinė, semantinė, darbinė) turi atskirus saugumo kontekstus su vaidmenimis pagrįstomis prieigos kontrolėmis, atskirus šifravimo raktus ir dokumentuotus prieigos modelius kiekvienam atminties tipui.
 #8.6.2    Level: 2    Role: D/V
 Patikrinkite, ar atminties konsolidavimo procesai apima saugumo patikrą, siekiant išvengti kenkėjiškų atminties įrašų įterpimo per turinio valymą, šaltinio patikrinimą ir vientisumo patikras prieš saugojimą.
 #8.6.3    Level: 2    Role: D/V
 Patikrinkite, ar atminties užklausos yra patvirtintos ir išvalytos, kad būtų užkirstas kelias neautorizuotos informacijos gavimui per užklausų modelių analizę, prieigos valdymo užtikrinimą ir rezultatų filtravimą.
 #8.6.4    Level: 3    Role: D/V
 Patikrinkite, ar atminties užmaršumo mechanizmai saugiai ištrina jautrią informaciją su kriptografinio ištrynimo garantijomis, naudodami rakto ištrynimą, keliaprasmį perrašymą arba aparatinį saugų ištrynimą su patikrinimo pažymėjimais.
 #8.6.5    Level: 3    Role: D/V
 Patikrinkite, ar atminties sistemos integralumas nuolat stebimas dėl neleistinų pakeitimų ar pažeidimų, naudojant kontrolines sumas, audito žurnalus ir automatinius įspėjimus, kai atminties turinys keičiasi už normalios veiklos ribų.

---

### Nuorodos

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

## 9 Autonominė koordinacija ir agentinė veiksmų sauga

### Valdymo tikslas

Užtikrinkite, kad autonominės arba daugiaagentės DI sistemos galėtų vykdyti tik tas veiklas, kurios yra aiškiai numatytos, autentifikuotos, audituojamos ir atitinka nustatytus kaštų bei rizikos ribinius nustatymus. Tai apsaugo nuo grėsmių, tokių kaip autonominės sistemos pažeidimas, įrankių piktnaudžiavimas, agentų ciklo aptikimas, komunikacijos užgrobimas, tapatybės klastojimas, spiečiaus manipuliavimas ir ketinimų manipuliavimas.

---

### 9.1 Agentų užduočių planavimo ir rekursijos biudžetai

Apribokite rekursyvų planų vykdymą ir priverstinai įveskite žmogaus patikrą privilegijuotoms veiksmams.

 #9.1.1    Level: 1    Role: D/V
 Patikrinkite, ar maksimalus rekursijos gylis, pločio apribojimas, realaus laiko trukmė, žetonų skaičius ir piniginės sąnaudos už agento vykdymą yra centralizuotai sukonfigūruoti ir valdomi versijų kontrolės sistema.
 #9.1.2    Level: 1    Role: D/V
 Patikrinkite, ar privilegijuoti arba negrįžtami veiksmai (pvz., kodo pateikimas, finansiniai pervedimai) prieš vykdymą reikalauja aiškaus žmogaus patvirtinimo per audituojamą kanalą.
 #9.1.3    Level: 2    Role: D
 Patikrinkite, ar realaus laiko išteklių stebėjimo įrankiai sukelia grandinės pertraukiklio nutraukimą, kai viršijamas bet kuris biudžeto slenkstis, sustabdant tolesnį užduočių plėtimą.
 #9.1.4    Level: 2    Role: D/V
 Patikrinkite, ar grandinės pertraukėjų įvykiai yra registruojami su agento ID, suveikimo sąlyga ir užfiksuota plano būsena teisinės apžiūros tikslais.
 #9.1.5    Level: 3    Role: V
 Patikrinkite, ar saugumo testai apima biudžeto išsekimo ir nekontroliuojamos plano vykdymo scenarijus, patvirtindami saugų sustabdymą be duomenų praradimo.
 #9.1.6    Level: 3    Role: D
 Patikrinkite, ar biudžeto politikos yra išreikštos kaip politika-kodas ir įgyvendinamos CI/CD, kad būtų užkirstas kelias konfigūracijos nukrypimams.

---

### 9.2 Įrankių papildinių izoliacija

Izoliuokite įrankių sąveikas, kad būtų užkirstas kelias neautorizuotam sistemos prieigai ar kodo vykdymui.

 #9.2.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas įrankis/priedas veikia operacinėje sistemoje, konteineryje arba WASM lygmens smėlio dėžėje su minimalia privilegija teikiamomis failų sistemos, tinklo ir sistemos iškvietimų politikomis.
 #9.2.2    Level: 1    Role: D/V
 Patikrinkite, ar yra užtikrinamas smėlio dėžės išteklių kvotų (CPU, atminties, disko, tinklo eigos) ir vykdymo laiko apribojimų taikymas bei jų registravimas.
 #9.2.3    Level: 2    Role: D/V
 Patikrinkite, ar įrankių dvejetainiai failai arba aprašai yra skaitmeniškai pasirašyti; parašai turi būti patvirtinti prieš juos įkeliamant.
 #9.2.4    Level: 2    Role: V
 Patikrinkite, ar smėlio dėžės telemetrija siunčiama į SIEM; anomalijos (pvz., bandymai užmegzti išorinius ryšius) sukelia įspėjimus.
 #9.2.5    Level: 3    Role: V
 Patikrinkite, ar didelės rizikos papildiniai prieš diegiant gamyboje yra išbandomi pagal saugumo peržiūrą ir įsiskverbimo testavimą.
 #9.2.6    Level: 3    Role: D/V
 Patikrinkite, ar bandymai pabėgti iš smėlio dėžės automatiškai blokuojami, o pažeidžiantis įskiepį laikinas karantine tol, kol bus atlikta tyrimas.

---

### 9.3 Autonominis ciklas ir sąnaudų ribojimas

Aptikite ir sustabdykite nekontroliuojamą agentų tarpusavio rekursiją ir kaštų išpūtimą.

 #9.3.1    Level: 1    Role: D/V
 Patikrinkite, ar tarpiniai agentų kvietimai apima ribą skaičiui šuolių (hop-limit) arba gyvavimo laiką (TTL), kuriuos vykdymo laikas mažina ir kontroliuoja.
 #9.3.2    Level: 2    Role: D
 Patikrinkite, ar agentai palaiko unikalų iškvietimų grafiko ID, kad būtų galima aptikti savęs iškvietimą arba ciklines schemas.
 #9.3.3    Level: 2    Role: D/V
 Patikrinkite, ar kaupiamieji skaičiavimo vienetų ir išlaidų skaitikliai sekami pagal užklausos grandinę; viršijus ribą grandinė nutraukiama.
 #9.3.4    Level: 3    Role: V
 Patikrinkite, ar formali analizė arba modelio tikrinimas įrodo neribotos rekursijos nebuvimą agentų protokoluose.
 #9.3.5    Level: 3    Role: D
 Patikrinkite, ar ciklo nutraukimo įvykiai sukelia įspėjimus ir tiekia nuolatinių patobulinimų metriką.

---

### 9.4 Protokolo lygmens netinkamo naudojimo apsauga

Saugūs komunikacijos kanalai tarp agentų ir išorinių sistemų, siekiant užkirsti kelią užgrobimui ar manipuliavimui.

 #9.4.1    Level: 1    Role: D/V
 Patikrinkite, ar visi agento įrankiui ir agento agentui siunčiami pranešimai yra autentifikuoti (pvz., abipusio TLS arba JWT) ir užšifruoti nuo pradžios iki pabaigos.
 #9.4.2    Level: 1    Role: D
 Patikrinkite, kad schemos būtų griežtai tikrinamos; nežinomi laukai ar neteisingai suformuoti pranešimai yra atmesti.
 #9.4.3    Level: 2    Role: D/V
 Patikrinkite, ar vientisumo tikrinimai (MAC arba skaitmeniniai parašai) apima visą žinutės turinį, įskaitant įrankio parametrus.
 #9.4.4    Level: 2    Role: D
 Patikrinkite, ar protokolo sluoksnyje yra užtikrinama pakartotinio paleidimo apsauga (naudojant unikalius skaitmeninius vienetus arba laiko žymių langus).
 #9.4.5    Level: 3    Role: V
 Patikrinkite, ar protokolo įgyvendinimai yra tikrinami naudojant fuzz testavimą ir statinę analizę dėl injekcijos ar deserializacijos trūkumų.

---

### 9.5 Agento tapatybė ir klastojimo poveikio įrodymas

Užtikrinkite, kad veiksmai būtų priskiriami ir pakeitimai aptinkami.

 #9.5.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienas agento egzempliorius turi unikalų kriptografinį identitetą (raktų porą arba aparatūros šaknis grindžiamą atpažinimą).
 #9.5.2    Level: 2    Role: D/V
 Patikrinkite, ar visi agentų veiksmai yra pasirašyti ir pažymėti laiku; žurnaluose įtraukta parašas nepasigailėjimui užtikrinti.
 #9.5.3    Level: 2    Role: V
 Patikrinkite, ar pakeitimų nepajėgiantys žurnalai saugomi pridedamame arba vienkartinio įrašymo terpėje.
 #9.5.4    Level: 3    Role: D
 Patikrinkite, ar tapatybės raktai keičiasi pagal apibrėžtą grafiką ir esant kompromitacijos indikacijoms.
 #9.5.5    Level: 3    Role: D/V
 Patikrinkite, ar klastojimo arba raktų konflikto bandymai sukelia paveikto agento nedelsiamą karantinavimą.

---

### 9.6 Daugiaagentės spiečiaus rizikos mažinimas

Mažinti kolektyvinio elgesio pavojus izoliuojant ir naudojant formalią saugumo modeliavimą.

 #9.6.1    Level: 1    Role: D/V
 Patikrinkite, ar agentai, veikiantys skirtingose saugumo srityse, vykdomi izoliuotose laiko vykdymo smėlio dėžėse arba tinklo segmentuose.
 #9.6.2    Level: 3    Role: V
 Patikrinkite, ar spiečių elgsena yra modeliuojama ir formaliai patvirtinama dėl gyvybingumo ir saugumo prieš diegiant.
 #9.6.3    Level: 3    Role: D
 Patikrinkite, ar vykdymo metu veikiantys stebėtojai aptinka atsirandančius nesaugumo modelius (pvz., osciliacijas, užstrigimus) ir inicijuoja koregacinį veiksmą.

---

### 9.7 Vartotojo ir įrankio autentifikacija / autorizacija

Įdiekite patikimą prieigos kontrolę kiekvienai agento inicijuotai veiklai.

 #9.7.1    Level: 1    Role: D/V
 Patikrinkite, ar agentai autentifikuojasi kaip pagrindinės klasės subjektai žemutiniams sistemoms, niekada neprikartodami galutinių naudotojų kredencialų.
 #9.7.2    Level: 2    Role: D
 Patikrinkite, ar smulkiosios autorizacijos politikos riboja, kuriuos įrankius agentas gali iškviesti ir kokius parametrus gali pateikti.
 #9.7.3    Level: 2    Role: V
 Patikrinkite, ar privilegijų patikrinimai atliekami iš naujo kiekvieno kvietimo metu (nuolatinė autorizacija), o ne tik sesijos pradžioje.
 #9.7.4    Level: 3    Role: D
 Patikrinkite, ar deleguotos teisės automatiškai įgaliojamos pasibaigus galiojimo laikui ir reikalauja pakartotinio sutikimo po laiko pabaigos arba srities pakeitimo.

---

### 9.8 Agentų tarpusavio komunikacijos saugumas

Užšifruokite ir užtikrinkite vientisumą visiems tarp agentų siunčiamiems pranešimams, kad būtų užkirstas kelias klausymuisi ir klastojimui.

 #9.8.1    Level: 1    Role: D/V
 Patikrinkite, ar agentų kanalams yra privaloma abipusė autentifikacija ir tobulai slaptas persiuntimo šifravimas (pvz., TLS 1.3).
 #9.8.2    Level: 1    Role: D
 Patikrinkite, ar pranešimo vientisumas ir kilmė yra patvirtinti prieš apdorojimą; nesėkmės sukelia įspėjimus ir pranešimas yra atmestas.
 #9.8.3    Level: 2    Role: D/V
 Patikrinkite, ar komunikacijos metaduomenys (laiko žymos, sekų numeriai) registruojami, siekiant užtikrinti forensinę atkūrimo galimybę.
 #9.8.4    Level: 3    Role: V
 Patikrinkite, ar formalioji patikra arba modelio tikrinimas patvirtina, kad protokolo būsenų mašinos negali būti paveiktos patekti į nesaugias būsenas.

---

### 9.9 Ketinimų patvirtinimas ir apribojimų taikymas

Patikrinkite, ar agento veiksmai atitinka vartotojo nurodytą ketinimą ir sistemos apribojimus.

 #9.9.1    Level: 1    Role: D
 Patikrinkite, ar priešvykdymo apribojimų sprendėjai tikrina siūlomus veiksmus pagal įdiegtas saugos ir politikos taisykles.
 #9.9.2    Level: 2    Role: D/V
 Patikrinkite, ar aukšto poveikio veiksmai (finansiniai, žalingi, privatumo jautrūs) reikalauja aiškaus ketinimų patvirtinimo iš inicijuojančio vartotojo.
 #9.9.3    Level: 2    Role: V
 Patikrinkite, ar po sąlygos patikros patvirtina, kad atlikti veiksmai pasiekė numatytus rezultatus be šalutinių poveikių; neatitikimai sukelia atitikmenų atšaukimą.
 #9.9.4    Level: 3    Role: V
 Patikrinkite, ar formalių metodų (pvz., modelių tikrinimo, teoreminio įrodymo) arba savybių pagrindu atliktų testų pagalba yra įrodyta, kad agentų planai atitinka visas paskelbtas apribojimus.
 #9.9.5    Level: 3    Role: D
 Patikrinkite, ar ketinimų neatitikimo arba apribojimų pažeidimų incidentai yra naudojami nuolatinio tobulinimo ciklams ir grėsmių žvalgybos dalijimuisi.

---

### 9.10 Agentų loginės strategijos saugumas

Saugus įvairių samprotavimo strategijų, įskaitant ReAct, Chain-of-Thought ir Tree-of-Thoughts metodų, parinkimas ir vykdymas.

 #9.10.1    Level: 1    Role: D/V
 Patikrinkite, ar sprendimų strategijos pasirinkimas remiasi deterministiniais kriterijais (įvesties sudėtingumas, užduoties tipas, saugumo kontekstas) ir ar identiškos įvestys toje pačioje saugumo kontekste sukuria identišką strategijos pasirinkimą.
 #9.10.2    Level: 1    Role: D/V
 Patikrinkite, ar kiekviena samprotavimo strategija (ReAct, Chain-of-Thought, Tree-of-Thoughts) turi skirtą įvesties patikrinimą, išvesties valymą ir vykdymo laiko apribojimus, būdingus jos pažintinei metodikai.
 #9.10.3    Level: 2    Role: D/V
 Patikrinkite, ar samprotavimo strategijos perėjimai yra registruojami su išsamiu kontekstu, įskaitant įvesties charakteristikas, atrankos kriterijų reikšmes ir vykdymo metaduomenis, skirtus audito kelio rekonstrukcijai.
 #9.10.4    Level: 2    Role: D/V
 Patikrinkite, ar „Mąstymo medžio“ (Tree-of-Thoughts) sprendimo procesas apima šakų apkarpymo mechanizmus, kurie nutraukia tyrinėjimą, kai nustatomi politikos pažeidimai, ištekliai apribojimai arba saugumo ribos.
 #9.10.5    Level: 2    Role: D/V
 Patikrinkite, ar ReAct (Reason-Act-Observe) ciklai apima patikros taškus kiekviename etape: samprotavimo žingsnio patvirtinimą, veiksmų autorizavimą ir stebėjimo išvalymą prieš tęsiant.
 #9.10.6    Level: 3    Role: D/V
 Patikrinkite, ar samprotavimo strategijos veikimo rodikliai (vykdymo laikas, išteklių naudojimas, išvesties kokybė) stebimi su automatizuotais įspėjimais, kai rodikliai nukrypsta už nustatytų ribinių verčių.
 #9.10.7    Level: 3    Role: D/V
 Patikrinkite, ar hibridiniai samprotavimo metodai, derinantys kelias strategijas, išlaiko visų sudedamųjų strategijų įvesties patikrinimą ir išvesties apribojimus, neperžengdami jokių saugumo kontrolės mechanizmų.
 #9.10.8    Level: 3    Role: D/V
 Patikrinkite, ar strategijos saugumo tikrinimas apima netaisyklingų įvesties duomenų siuntimą (fuzzing), priešiškus užklausimus, skirtus priversti strategiją keistis, ir ribinių sąlygų testavimą kiekvienam kognityviniam metodui.

---

### 9.11 Agentų gyvavimo ciklo valdymas ir saugumas

Saugus agento inicializavimas, būsenos pereinamieji etapai ir nutraukimas su kriptografiniais audito takais bei apibrėžtomis atkūrimo procedūromis.

 #9.11.1    Level: 1    Role: D/V
 Patikrinkite, ar agento inicializavimas apima kriptografinės tapatybės nustatymą naudojant aparatūros pagrindu veikiančius kredencialus ir nekintamus paleidimo audito įrašus, kuriuose yra agento ID, laiko žyma, konfigūracijos maišos reikšmė ir inicializavimo parametrai.
 #9.11.2    Level: 2    Role: D/V
 Patikrinkite, ar agento būsenos perėjimai yra kriptografiškai pasirašyti, pažymėti laiku ir įrašyti su visa konteksto informacija, įskaitant sužadinimo įvykius, ankstesnės būsenos hešą, naujos būsenos hešą ir atliktus saugumo patikrinimus.
 #9.11.3    Level: 2    Role: D/V
 Patikrinkite, ar agento išjungimo procedūros apima saugų atminties išvalymą naudojant kriptografinį naikinimą arba kelių praeigų perrašymą, kredencialų atšaukimą su sertifikavimo institucijos informavimu ir nepažeidžiamų nutraukimo pažymų sugeneravimą.
 #9.11.4    Level: 3    Role: D/V
 Patikrinkite, ar agento atkūrimo mechanizmai tikrina būsenos vientisumą naudodami kriptografinius kontrolinius sumas (mažiausiai SHA-256) ir, aptikus korupciją, grąžina sistemą į žinomas geras būsenas su automatizuotais įspėjimais bei rankinio patvirtinimo reikalavimais.
 #9.11.5    Level: 3    Role: D/V
 Patikrinkite, ar agento nuolatinio saugojimo mechanizmai šifruoja jautrius būsenos duomenis naudodami kiekvienam agentui skirtus AES-256 raktus ir įgyvendina saugų raktų pasikeitimą pagal konfigūruojamus grafikus (maksimaliai kas 90 dienų) su diegimu be veiklos sutrikimų.

---

### 9.12 Įrankių integracijos saugumo sistema

Saugumo kontrolės dinamiškam įrankių įkėlimui, vykdymui ir rezultatų patvirtinimui, taikant apibrėžtus rizikos vertinimo ir patvirtinimo procesus.

 #9.12.1    Level: 1    Role: D/V
 Patikrinkite, ar įrankių aprašikliai apima saugumo metaduomenis, nurodančius reikiamas teises (skaitymas/rašymas/vykdymas), rizikos lygius (žemas/vidutinis/aukštas), resursų ribas (CPU, atmintis, tinklas) ir validavimo reikalavimus, dokumentuotus įrankių manifestuose.
 #9.12.2    Level: 1    Role: D/V
 Patikrinkite, ar įrankio vykdymo rezultatai yra patvirtinti pagal numatytus schemas (JSON Schema, XML Schema) ir saugumo politiką (išvesties valymas, duomenų klasifikacija) prieš integruojant su laiko limitų ir klaidų valdymo procedūromis.
 #9.12.3    Level: 2    Role: D/V
 Patikrinkite, ar įrankių sąveikos žurnaluose yra pateikta išsami saugumo konteksto informacija, įskaitant privilegijų naudojimą, duomenų prieigos modelius, vykdymo laiką, išteklių suvartojimą ir grąžinimo kodus, naudojant struktūrizuotą žurnalavimą SIEM integracijai.
 #9.12.4    Level: 2    Role: D/V
 Patikrinkite, ar dinaminio įrankių įkėlimo mechanizmai patikrina skaitmeninius parašus, naudodami PKI infrastruktūrą, ir įgyvendina saugius įkėlimo protokolus su izoliuota aplinka (sandbox) bei leidimų patikrinimu prieš vykdymą.
 #9.12.5    Level: 3    Role: D/V
 Patikrinkite, ar įrankių saugumo vertinimai automatiškai inicijuojami naujoms versijoms su privalomais patvirtinimo etapais, įskaitant statinę analizę, dinaminį testavimą ir saugumo komandos peržiūrą, kurių metu taikomi dokumentuoti patvirtinimo kriterijai ir SLA reikalavimai.

---

#### Nuorodos

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

## 10 Priešiškumo atsparumas ir privatumo apsauga

### Valdymo tikslas

Užtikrinkite, kad DI modeliai išliktų patikimi, privatumo saugomi ir atsparūs piktnaudžiavimui susiduriant su išvengimo, darymo išvadų, duomenų išgavimą ar užnuodijimo atakomis.

---

### 10.1 Modelio suderinamumas ir saugumas

Apsaugokite nuo žalingų arba politikos pažeidžiančių rezultatų.

 #10.1.1    Level: 1    Role: D/V
 Patikrinkite, ar suderinamumo testų rinkinys (red team užklausos, jailbreiko testai, neleistinas turinys) yra valdomas versijų valdymo sistemoje ir vykdomas kiekvienos modelio versijos išleidimo metu.
 #10.1.2    Level: 1    Role: D
 Patikrinkite, ar laikomasi atsisakymo ir saugaus užbaigimo apsaugos priemonių.
 #10.1.3    Level: 2    Role: D/V
 Patikrinkite, ar automatizuotas vertintojas matuoja kenksmingo turinio dažnį ir žymi regresijas, viršijančias nustatytą ribą.
 #10.1.4    Level: 2    Role: D
 Patikrinkite, ar kontratralizavimo apmokymai yra dokumentuoti ir atkuriami.
 #10.1.5    Level: 3    Role: V
 Patikrinkite, ar formalūs politikos laikymosi įrodymai arba sertifikuotas stebėjimas apima kritines sritis.

---

### 10.2 Priešpriešinių pavyzdžių stiprinimas

Padidinkite atsparumą manipuliuotiems įvestims. Patikimas priešiškas mokymas ir etaloninis įvertinimas yra dabartinė geriausia praktika.

 #10.2.1    Level: 1    Role: D
 Patikrinkite, ar projekto saugyklose yra priešiško mokymo konfigūracijos su atkuriamais sėklų parametrais.
 #10.2.2    Level: 2    Role: D/V
 Patikrinkite, ar priešiškų pavyzdžių aptikimas sukelia blokavimo įspėjimus gamybos procesuose.
 #10.2.4    Level: 3    Role: V
 Patikrinkite, ar sertifikuotos patvarumo įrodymai arba intervalo ribų pažymėjimai apima bent jau svarbiausias kritines klases.
 #10.2.5    Level: 3    Role: V
 Patikrinkite, ar regresijos testai naudoja adaptyvius išpuolius, kad patvirtintų neįžvelgiamą patvarumo praradimą.

---

### 10.3 Narystės atpažinimo suvaržymas

Apribokite galimybę nuspręsti, ar įrašas buvo mokymo duomenyse. Diferencialinė privatumo apsauga ir pasitikėjimo įvertinimo maskavimas išlieka veiksmingiausi žinomi gynybos metodai.

 #10.3.1    Level: 1    Role: D
 Patikrinkite, ar kiekvienam užklausos vienetui taikomas entropijos reguliavimas arba temperatūros skalavimas sumažina pernelyg užtikrintas prognozes.
 #10.3.2    Level: 2    Role: D
 Patikrinkite, ar mokymas naudoja ε-ribotą diferencijuotai privatų optimizavimą jautriems duomenų rinkiniams.
 #10.3.3    Level: 2    Role: V
 Patikrinkite, ar atakų simuliacijos (šešėlinio modelio arba juodosios dėžės) rodo atakos AUC ≤ 0,60 ant atskirtų duomenų.

---

### 10.4 Modelio inversijos atsparumas

Užkirsti kelią privačių atributų rekonstrukcijai. Naujausios apžvalgos pabrėžia išvesties sutrumpinimą ir diferencinio privatumo garantijas kaip praktines apsaugos priemones.

 #10.4.1    Level: 1    Role: D
 Patikrinkite, kad jautrūs atributai niekada nebūtų tiesiogiai pateikiami; jei reikia, naudokite kategorijas arba vienpusio šifravimo metodus.
 #10.4.2    Level: 1    Role: D/V
 Patikrinkite, ar užklausų dažnio apribojimai riboja pasikartojančias adaptacines užklausas iš to paties asmens.
 #10.4.3    Level: 2    Role: D
 Patikrinkite, ar modelis yra apmokytas su privatumo saugančiu triukšmu.

---

### 10.5 Modelio išgavimas – gynyba

Aptikti ir užkirsti kelią neįgaliotam klonavimui. Rekomenduojama naudoti vandens ženklinimą ir užklausų modelių analizę.

 #10.5.1    Level: 1    Role: D
 Patikrinkite, ar išvados vartai taiko pasaulinius ir pagal API raktą nustatytus spartos ribojimus, pritaikytus modelio įsiminimo slenksčiui.
 #10.5.2    Level: 2    Role: D/V
 Patikrinkite, ar užklausos entropijos ir įvesties daugiabūdingumo statistika yra naudojama automatiniam išgavimų aptikimui.
 #10.5.3    Level: 2    Role: V
 Patikrinkite, ar trapūs arba tikimybinių vandens ženklai gali būti įrodyti su p < 0,01 per ne daugiau kaip 1 000 užklausų prieš įtariamą kloną.
 #10.5.4    Level: 3    Role: D
 Patikrinkite, ar vandens ženklų raktai ir suaktyvinimo rinkiniai yra saugomi aparatinės įrangos saugumo modulyje ir keičiami kasmet.
 #10.5.5    Level: 3    Role: V
 Patikrinkite, ar ištraukimo įspėjimų įvykiai apima pažeidžiančius užklausimus ir yra integruoti su incidentų reagavimo veiksmų planais.

---

### 10.6 Išvedimo laikotarpio užkrėsto duomenų aptikimas

Identifikuokite ir neutralizuokite atgalines duris ar užnuodytus įvesties duomenis.

 #10.6.1    Level: 1    Role: D
 Patikrinkite, ar įvestys praeina pro anomalijų detektorių (pvz., STRIP, nuoseklumo įvertinimą) prieš atliekant modelio inferenciją.
 #10.6.2    Level: 1    Role: V
 Patikrinkite, ar detektorių slenksčiai yra sureguliuoti ant švarių/užnuodytų patikrinimo rinkinių, siekiant užtikrinti mažiau nei 5 % klaidingų teigiamų rezultatų.
 #10.6.3    Level: 2    Role: D
 Patikrinkite, ar įvestys, pažymėtos kaip užkrėstos, sukelia minkštojo blokavimo ir žmogaus peržiūros darbo eigas.
 #10.6.4    Level: 2    Role: V
 Patikrinkite, ar detektoriai yra streso testuojami naudojant adaptacinius, be signalo suaktyvinamų galinių durų atakas.
 #10.6.5    Level: 3    Role: D
 Patikrinkite, ar aptikimo efektyvumo metrikos yra registruojamos ir periodiškai pervertinėjamos naudojant naują grėsmių informaciją.

---

### 10.7 Dinaminis saugumo politikos pritaikymas

Saugumo politikos atnaujinimai realiuoju laiku, pagrįsti grėsmių žvalgyba ir elgsenos analize.

 #10.7.1    Level: 1    Role: D/V
 Patikrinkite, ar saugumo politikos gali būti atnaujinamos dinamiškai be agento paleidimo iš naujo, išlaikant politikos versijos vientisumą.
 #10.7.2    Level: 2    Role: D/V
 Patikrinkite, ar politikos atnaujinimai yra kriptografiškai pasirašyti įgaliotų saugumo darbuotojų ir patikrinti prieš taikant.
 #10.7.3    Level: 2    Role: D/V
 Patikrinkite, ar dinamiški politikos pakeitimai yra registruojami su pilnais audito įrašais, įskaitant pagrindimą, patvirtinimo grandines ir atšaukimo procedūras.
 #10.7.4    Level: 3    Role: D/V
 Patikrinkite, ar adaptaciniai saugumo mechanizmai reguliuoja grėsmės aptikimo jautrumą pagal rizikos kontekstą ir elgsenos modelius.
 #10.7.5    Level: 3    Role: D/V
 Patikrinkite, ar politikos adaptacijos sprendimai yra paaiškinami ir ar yra įtraukti įrodymų takai saugumo komandos peržiūrai.

---

### 10.8 Atspindžiu grįsta saugumo analizė

Saugumo patikrinimas per agento savirefleksiją ir meta-kognityvinę analizę.

 #10.8.1    Level: 1    Role: D/V
 Patikrinkite, ar agento atspindėjimo mechanizmai apima saugumo koncentruotą savęs vertinimą priimant sprendimus ir atliekant veiksmus.
 #10.8.2    Level: 2    Role: D/V
 Patikrinkite, ar atspindžio išėjimai yra patvirtinti, siekiant užkirsti kelią savianalizės mechanizmų manipuliacijai priešų įvesties duomenimis.
 #10.8.3    Level: 2    Role: D/V
 Patikrinkite, ar metakognityvinė saugumo analizė nustato galimus šališkumus, manipuliacijas ar pažeidimus agento samprotavimo procesuose.
 #10.8.4    Level: 3    Role: D/V
 Patikrinkite, ar atspindžių pagrindu veikiantys saugumo įspėjimai sukelia sustiprintą stebėjimą ir galimus žmogaus įsikišimo darbo srautus.
 #10.8.5    Level: 3    Role: D/V
 Patikrinkite, ar nuolatinis mokymasis iš saugumo apmąstymų gerina grėsmių aptikimą, nesumažinant teisėtos funkcionalumo kokybės.

---

### 10.9 Evoliucija ir savęs tobulinimo saugumas

Saugumo kontrolės agentų sistemoms, gebančioms savarankiškai keistis ir vystytis.

 #10.9.1    Level: 1    Role: D/V
 Patikrinkite, ar savęs modifikavimo galimybės yra apribotos tik specialiai pažymėtose saugiose zonose su formaliomis verifikacijos ribomis.
 #10.9.2    Level: 2    Role: D/V
 Patikrinkite, ar evoliucijos pasiūlymai praeina saugumo poveikio vertinimą prieš įgyvendinant.
 #10.9.3    Level: 2    Role: D/V
 Patikrinkite, ar savęs tobulinimo mechanizmai apima grąžinimo funkcijas su vientisumo patikrinimu.
 #10.9.4    Level: 3    Role: D/V
 Patikrinkite, ar meta-mokymosi saugumas neleidžia priešiškam tobulinimo algoritmų manipuliavimui.
 #10.9.5    Level: 3    Role: D/V
 Patikrinkite, ar rekursinis savęs tobulinimas yra ribojamas formalių saugumo apribojimų, pateikiant matematinius konvergencijos įrodymus.

---

#### Nuorodos

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

## 11 Privatumo apsauga ir asmens duomenų valdymas

### Kontrolės tikslas

Užtikrinkite griežtą privatumo apsaugą per visą DI gyvavimo ciklą – duomenų rinkimą, mokymą, numatymą ir įvykių valdymą – kad asmens duomenys būtų tvarkomi tik aiškiai sutikus, laikantis minimalaus būtinumo principo, su įrodymais apie ištrynimą ir formaliais privatumo garantavimais.

---

### 11.1 Anonimizavimas ir duomenų minimalizavimas

 #11.1.1    Level: 1    Role: D/V
 Patikrinkite, ar tiesioginiai ir kvazi-identifikatoriai yra pašalinti arba apdoroti maišos funkcija.
 #11.1.2    Level: 2    Role: D/V
 Patikrinkite, ar automatiniai auditai matuoja k-anonimiškumą/l-įvairovę ir įspėja, kai nustatyti ribiniai dydžiai nukrinta žemiau politikos reikalavimų.
 #11.1.3    Level: 2    Role: V
 Patikrinkite, ar modelio reikšmingumo ataskaitos įrodo, kad nėra identifikatorių nutekėjimo, viršijančio ε = 0,01 bendrąją informaciją.
 #11.1.4    Level: 3    Role: V
 Patikrinkite, ar formalūs įrodymai arba sintetinės duomenų sertifikavimas rodo, kad identifikavimo rizika yra ≤ 0,05 net ir atliekant susiejimo atakas.

---

### 11.2 Teisė būti pamirštam ir ištrynimo vykdymas

 #11.2.1    Level: 1    Role: D/V
 Patikrinkite, ar duomenų subjecto ištrinimo užklausos pasiekia neapdorotus duomenų rinkinius, kontrolinius punktus, įterpimus, žurnalus ir atsargines kopijas per paslaugos lygio sutartį, trunkančią mažiau nei 30 dienų.
 #11.2.2    Level: 2    Role: D
 Patikrinkite, ar „mašininio nepamokimo“ procedūros fiziškai išmoko iš naujo arba įvertina pašalinimą naudojant sertifikuotus nepamokymo algoritmus.
 #11.2.3    Level: 2    Role: V
 Patikrinkite, ar šešėlio modelio vertinimas įrodo, kad pamiršti įrašai po atsiminimo daro įtaką mažiau nei 1 % išvesties rezultatų.
 #11.2.4    Level: 3    Role: V
 Patikrinkite, ar ištrynimo įvykiai yra nekeičiami užfiksuoti ir audituojami reguliuotojams.

---

### 11.3 Diferencinės privatumo apsaugos priemonės

 #11.3.1    Level: 2    Role: D/V
 Patikrinkite, ar privatumo nuostolių stebėjimo skydai įspėja, kai susumuotas ε viršija politikos ribas.
 #11.3.2    Level: 2    Role: V
 Patikrinkite, ar juodosios dėžės privatumo auditai įvertina ε̂ su ne didesniu nei 10 % paklaidos nuo deklaruotos vertės.
 #11.3.3    Level: 3    Role: V
 Patikrinkite, ar formalių įrodymų aprėptis apima visus posttreniruotinius tikslinius patobulinimus ir įterpimus.

---

### 11.4 Tikslų apribojimas ir apsauga nuo apimties augimo

 #11.4.1    Level: 1    Role: D
 Patikrinkite, ar kiekvienas duomenų rinkinys ir modelio kontrolinis taškas turi mašininiu būdu skaitomą paskirties žymę, atitinkančią pradinį sutikimą.
 #11.4.2    Level: 1    Role: D/V
 Patikrinkite, ar vykdymo laikotarpio stebėtojai aptinka užklausas, kurios prieštarauja paskelbtam tikslui, ir sukelia švelnų atsisakymą.
 #11.4.3    Level: 3    Role: D
 Patikrinkite, ar politika kaip kodas (policy-as-code) užkardos neleidžia modelių perkūrimo naujoms sritims be DPIA peržiūros.
 #11.4.4    Level: 3    Role: V
 Patikrinkite, ar formalūs susiejamumo įrodymai parodo, kad kiekvienas asmens duomenų gyvenimo ciklas lieka sutarto sutikimo ribose.

---

### 11.5 Sutikimų valdymas ir teisėto pagrindo stebėjimas

 #11.5.1    Level: 1    Role: D/V
 Patikrinkite, ar sutikimų valdymo platforma (CMP) įrašo duomenų subjekto sutikimo būseną, tikslą ir saugojimo laikotarpį.
 #11.5.2    Level: 2    Role: D
 Patikrinkite, ar API suteikia sutikimo žetonus; modeliai turi patikrinti žetono aprėptį prieš atliekant spėjimą.
 #11.5.3    Level: 2    Role: D/V
 Patikrinkite, ar atsisakius arba atšaukus sutikimą, duomenų apdorojimo procesai sustabdomi per 24 valandas.

---

### 11.6 Federuotas mokymasis su privatumo valdikliais

 #11.6.1    Level: 1    Role: D
 Patikrinkite, ar klientų atnaujinimai naudoja vietinį diferencialinį privatumo triukšmo pridėjimą prieš agregavimą.
 #11.6.2    Level: 2    Role: D/V
 Patikrinkite, ar mokymo metrikos yra diferencialiai privatūs ir niekada neatskleidžia vieno kliento nuostolių.
 #11.6.3    Level: 2    Role: V
 Patikrinkite, ar įjungta apsauga nuo užnuodijimo jautri agregacija (pvz., Krum/Trimmed-Mean).
 #11.6.4    Level: 3    Role: V
 Patikrinkite, ar formalūs įrodymai parodo bendrą ε biudžetą su mažesniu nei 5 naudos praradimu.

---

#### Nuorodos

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

## C12 Stebėjimas, Įrašymas ir Anomalijų Aptikimas

### Kontrolės tikslas

Šiame skyriuje pateikiami reikalavimai tiesioginiam ir forensiniam matomumui užtikrinti, kas modelis ir kitos DI dalys mato, ką daro ir ką grąžina, kad būtų galima aptikti, išanalizuoti ir išmokti iš grėsmių.

### C12.1 Užklausų ir atsakymų registravimas

 #12.1.1    Level: 1    Role: D/V
 Patikrinkite, ar visi vartotojų užklausimai ir modelio atsakymai yra įrašyti kartu su atitinkamais metaduomenimis (pvz., laiko žyma, vartotojo ID, sesijos ID, modelio versija).
 #12.1.2    Level: 1    Role: D/V
 Patikrinkite, ar žurnalai saugomi saugiuose, prieigą kontroliuojamuose saugyklose su tinkamomis saugojimo politikomis ir atsarginių kopijų procedūromis.
 #12.1.3    Level: 1    Role: D/V
 Patikrinkite, ar žurnalų saugojimo sistemos įgyvendina duomenų šifravimą ramybėje ir perdavimo metu, siekiant apsaugoti žurnaluose esančią konfidencialią informaciją.
 #12.1.4    Level: 1    Role: D/V
 Patikrinkite, ar jautrūs duomenys skatinimuose ir rezultatuose automatiškai ištrinami arba užmaskuojami prieš įrašymą, su konfigūruojamomis redagavimo taisyklėmis asmens identifikavimo informacijai (PII), prieigos duomenims ir konfidencialiai informacijai.
 #12.1.5    Level: 2    Role: D/V
 Patikrinkite, kad politikos sprendimai ir saugumo filtravimo veiksmai būtų registruojami pakankamai detaliai, kad būtų galima atlikti audito patikrinimą ir turinio moderavimo sistemų derinimą.
 #12.1.6    Level: 2    Role: D/V
 Patikrinkite, ar žurnalų vientisumas yra apsaugotas, pavyzdžiui, naudojant kriptografinius parašus ar tik rašymui skirtą saugyklą.

---

### C12.2 Piktnaudžiavimo aptikimas ir įspėjimas

 #12.2.1    Level: 1    Role: D/V
 Patikrinkite, ar sistema aptinka ir perspėja apie žinomus jailbreak šablonus, paskatų įpurškimo bandymus bei priešiškas įvestis, naudodama parašo pagrindu veikiančią aptikimą.
 #12.2.2    Level: 1    Role: D/V
 Patikrinkite, ar sistema integruojasi su esamomis Saugumo informacijos ir įvykių valdymo (SIEM) platformomis, naudodama standartinius žurnalų formatus ir protokolus.
 #12.2.3    Level: 2    Role: D/V
 Patikrinkite, ar praturtinti saugumo įvykiai apima dirbtinio intelekto specifinį kontekstą, tokį kaip modelio identifikatoriai, pasitikėjimo balai ir saugumo filtrų sprendimai.
 #12.2.4    Level: 2    Role: D/V
 Patikrinkite, ar elgesio anomalijų aptikimas nustato neįprastus pokalbių modelius, per daug kartojamus bandymus arba sistemingą tyrimų elgesį.
 #12.2.5    Level: 2    Role: D/V
 Patikrinkite, ar realaus laiko įspėjimo mechanizmai informuoja saugumo komandas, kai aptinkami galimi politikos pažeidimai arba atakos bandymai.
 #12.2.6    Level: 2    Role: D/V
 Patikrinkite, ar įtrauktos pasirinktinės taisyklės, skirtos aptikti dirbtinio intelekto specifinius grėsmių modelius, įskaitant koordinuotus sistemos apeidimo bandymus, užklausų injekcijos kampanijas ir modelių ištraukimo atakas.
 #12.2.7    Level: 3    Role: D/V
 Patikrinkite, ar automatizuoti incidentų reagavimo darbo srautai gali izoliuoti pažeistus modelius, blokuoti kenkėjiškus vartotojus ir eskaluoti kritinius saugumo įvykius.

---

### C12.3 Modelio pasislinkimo aptikimas

 #12.3.1    Level: 1    Role: D/V
 Patikrinkite, ar sistema stebi pagrindinius veiklos rodiklius, tokius kaip tikslumas, pasitikėjimo balai, delsos laikas ir klaidų rodikliai per modelio versijas ir laiko intervalus.
 #12.3.2    Level: 2    Role: D/V
 Patikrinkite, ar automatizuoti perspėjimai suveikia, kai našumo metrikos viršija iš anksto nustatytas degradacijos ribas arba žymiai nukrypsta nuo bazinių lygių.
 #12.3.3    Level: 2    Role: D/V
 Patikrinkite, ar haliucinacijų aptikimo stebėjimo priemonės nustato ir žymi atvejus, kai modelio išvestys yra faktiniu požiūriu neteisingos, prieštaringos arba suklastotos.

---

### C12.4 Veiklos ir elgesio telemetrija

 #12.4.1    Level: 1    Role: D/V
 Patikrinkite, ar operaciniai metrikai, įskaitant užklausos vėlavimą, žetonų sunaudojimą, atminties naudojimą ir pralaidumą, nuolat renkami ir stebimi.
 #12.4.2    Level: 1    Role: D/V
 Patikrinkite, ar sėkmės ir nesėkmės rodikliai fiksuojami kartu su klaidų tipų ir jų priežastinių šaknų kategorizavimu.
 #12.4.3    Level: 2    Role: D/V
 Patikrinkite, ar resursų naudojimo stebėjimas apima GPU/CPU naudojimą, atminties suvartojimą ir saugojimo reikalavimus bei signalizavimą apie ribų pažeidimus.

---

### C12.5 DI sprendimų reagavimo plano sudarymas ir vykdymas

 #12.5.1    Level: 1    Role: D/V
 Patikrinkite, ar incidentų reagavimo planai aiškiai apima su dirbtiniu intelektu susijusius saugumo įvykius, įskaitant modelio pažeidimą, duomenų apsinuodijimą ir priešiškus išpuolius.
 #12.5.2    Level: 2    Role: D/V
 Patikrinkite, ar incidentų reagavimo komandos turi prieigą prie dirbtinio intelekto specifinių teisinių įrodymų įrankių ir ekspertizės, kad galėtų tirti modelio elgseną ir atakos vektorius.
 #12.5.3    Level: 3    Role: D/V
 Patikrinkite, ar poįvykio analizėje įtraukti modelio perdavimo svarstymai, saugos filtrų atnaujinimai ir išmoktos pamokos integravimas į saugumo valdiklius.

---

### C12.5 AI našumo blogėjimo aptikimas

Stebėti ir aptikti dirbtinio intelekto modelio našumo ir kokybės blogėjimą laikui bėgant.

 #12.5.1    Level: 1    Role: D/V
 Patikrinkite, ar modelio tikslumas, preciziškumas, atgaminamumas ir F1 rodikliai yra nuolat stebimi ir lyginami su baziniais slenksčiais.
 #12.5.2    Level: 1    Role: D/V
 Patikrinkite, ar duomenų pasiskirstymo pokyčių stebėjimas (data drift detection) fiksuoja įvesties pasiskirstymo pokyčius, kurie gali turėti įtakos modelio veikimui.
 #12.5.3    Level: 2    Role: D/V
 Patikrinkite, ar koncepcijos poslinkio aptikimas identifikuoja pokyčius tarp įvesties duomenų ir tikėtinų išvesties duomenų santykio.
 #12.5.4    Level: 2    Role: D/V
 Patikrinkite, ar veikimo kokybės sumažėjimas sukelia automatinius įspėjimus ir inicijuoja modelio perkvalifikavimo arba pakeitimo darbo procesus.
 #12.5.5    Level: 3    Role: V
 Patikrinkite, ar nuosmukio priežasčių analizė susieja našumo sumažėjimą su duomenų pokyčiais, infrastruktūros problemomis arba išoriniais veiksniais.

---

### C12.6 DAG vizualizacija ir darbo eigos saugumas

Apsaugokite darbo eigos vizualizacijos sistemas nuo informacijos nutekėjimo ir manipuliacijos atakų.

 #12.6.1    Level: 1    Role: D/V
 Patikrinkite, ar DAG vizualizacijos duomenys yra išvalyti nuo jautrios informacijos prieš juos saugant arba perduodant.
 #12.6.2    Level: 1    Role: D/V
 Patikrinkite, ar darbo eigos vizualizacijos prieigos valdikliai užtikrina, kad tik įgalioti vartotojai galėtų peržiūrėti agentų sprendimų kelius ir argumentacijos sekas.
 #12.6.3    Level: 2    Role: D/V
 Patikrinkite, ar DAG duomenų vientisumas yra apsaugotas kriptografiniais parašais ir nuo klastojimo apsaugančiomis saugojimo priemonėmis.
 #12.6.4    Level: 2    Role: D/V
 Patikrinkite, ar darbo eigos vizualizavimo sistemos įgyvendina įvesties duomenų tikrinimą, kad būtų užkirstas kelias injekcijos atakoms per specialiai paruoštus mazgų ar kraštų duomenis.
 #12.6.5    Level: 3    Role: D/V
 Patikrinkite, ar realaus laiko DAG atnaujinimai yra ribojami pagal dažnį ir tikrinami, siekiant išvengti paslaugų atsisakymo (DoS) atakų vizualizacijos sistemoms.

---

### C12.7 Proaktyvus saugumo elgesio stebėjimas

Saugumo grėsmių aptikimas ir prevencija per proaktyvią agento elgesio analizę.

 #12.7.1    Level: 1    Role: D/V
 Patikrinkite, ar proaktyvūs agentų elgesiai yra saugumo patvirtinti prieš vykdymą, integruojant rizikos vertinimą.
 #12.7.2    Level: 2    Role: D/V
 Patikrinkite, ar autonominio iniciatyvumo suaktyvinimai apima saugumo konteksto vertinimą ir grėsmių kraštovaizdžio įvertinimą.
 #12.7.3    Level: 2    Role: D/V
 Patikrinkite, ar proaktyvūs elgesio modeliai yra analizuojami dėl galimų saugumo pasekmių ir neplanuotų padarinių.
 #12.7.4    Level: 3    Role: D/V
 Patikrinkite, ar saugumui kritiškai svarbūs proaktyvūs veiksmai reikalauja aiškių patvirtinimo grandinių su audito įrašais.
 #12.7.5    Level: 3    Role: D/V
 Patikrinkite, ar elgesio anomalijų aptikimas nustato nukrypimus proaktyvių agentų modeliuose, kurie gali rodyti pažeidžiamumą.

---

### Nuorodos

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Žmogiškoji priežiūra, atsakomybė ir valdymas

### Valdymo tikslas

Šis skyrius pateikia reikalavimus, užtikrinančius žmogaus priežiūrą ir aiškius atsakomybės grandines dirbtinio intelekto sistemose, užtikrinant paaiškinamumą, skaidrumą ir etišką valdymą viso DI gyvavimo ciklo metu.

---

### C13.1 Išjungimo mygtuko ir perjungimo mechanizmai

Pateikite išjungimo arba atstatymo veiksmus, kai pastebimas pavojingas DI sistemos elgesys.

 #13.1.1    Level: 1    Role: D/V
 Patikrinkite, ar egzistuoja rankinis atjungimo jungiklio mechanizmas, leidžiantis nedelsiant sustabdyti DI modelio spėjimus ir rezultatus.
 #13.1.2    Level: 1    Role: D
 Patikrinkite, ar valdymo perrašymo priemonės yra prieinamos tik autorizuotam personalui.
 #13.1.3    Level: 3    Role: D/V
 Patikrinkite, ar atšaukimo procedūros gali grąžinti ankstesnes modelio versijas arba saugaus režimo veikimą.
 #13.1.4    Level: 3    Role: V
 Patikrinkite, ar persistumdymo mechanizmai yra reguliariai testuojami.

---

### C13.2 Žmogiškoji sprendimų priėmimo kontrolės taškai

Reikalauti žmogaus patvirtinimų, kai rizikos lygis viršija iš anksto nustatytas ribas.

 #13.2.1    Level: 1    Role: D/V
 Patikrinkite, ar didelės rizikos DI sprendimai reikalauja aiškaus žmogaus patvirtinimo prieš juos vykdant.
 #13.2.2    Level: 1    Role: D
 Patikrinkite, ar rizikos slenksčiai yra aiškiai apibrėžti ir automatiškai sukelia žmogaus peržiūros darbo eigas.
 #13.2.3    Level: 2    Role: D
 Patikrinkite, ar laiku jautrūs sprendimai turi atsarginius veiksmų planus, kai žmogaus patvirtinimo negalima gauti per reikiamus terminus.
 #13.2.4    Level: 3    Role: D/V
 Patikrinkite, ar eskalavimo procedūros apibrėžia aiškius įgaliojimų lygius skirtingiems sprendimų tipams arba rizikos kategorijoms, jei taikoma.

---

### C13.3 Atsakomybės grandinė ir audito galimybė

Registruokite operatoriaus veiksmus ir modelio sprendimus.

 #13.3.1    Level: 1    Role: D/V
 Patikrinkite, ar visi DI sistemos sprendimai ir žmogaus įsikišimai yra registruojami su laiko žymomis, naudotojo tapatybe ir sprendimų pagrindimu.
 #13.3.2    Level: 2    Role: D
 Patikrinkite, ar audito žurnalų negalima klastoti, ir įtraukite vientisumo patikros mechanizmus.

---

### C13.4 Paaiškinama DI technikos

Paviršinio bruožo svarba, kontrafaktiniai atvejai ir vietinės paaiškinimai.

 #13.4.1    Level: 1    Role: D/V
 Patikrinkite, ar DI sistemos pateikia pagrindinius savo sprendimų paaiškinimus žmogui suprantama forma.
 #13.4.2    Level: 2    Role: V
 Patikrinkite, ar paaiškinimų kokybė yra patvirtinta per žmonių vertinimo tyrimus ir metrikas.
 #13.4.3    Level: 3    Role: D/V
 Patikrinkite, ar svarbių sprendimų atveju yra prieinami funkcijų svarbos balai arba priskyrimo metodai (SHAP, LIME ir kt.).
 #13.4.4    Level: 3    Role: V
 Patikrinkite, ar kontrafaktinės paaiškinimų metodikos rodo, kaip įvestys galėtų būti pakeistos siekiant pakeisti rezultatus, jei tai taikoma naudojimo atveju ir sričiai.

---

### C13.5 Modelių kortelės ir naudojimo atskleidimai

Palaikykite modelių korteles, kuriose nurodomos numatytos panaudojimo sritys, našumo rodikliai ir etiniai svarstymai.

 #13.5.1    Level: 1    Role: D
 Patikrinkite, ar modelio kortelės dokumentuoja numatytas naudojimo sritis, apribojimus ir žinomas gedimų formas.
 #13.5.2    Level: 1    Role: D/V
 Patikrinkite, ar atskleidžiami našumo rodikliai skirtinguose taikomuose naudojimo atvejuose.
 #13.5.3    Level: 2    Role: D
 Patikrinkite, ar etiniai apsvarstymai, šališkumo vertinimai, teisingumo įvertinimai, mokymo duomenų charakteristikos ir žinomi mokymo duomenų apribojimai yra dokumentuoti ir reguliariai atnaujinami.
 #13.5.4    Level: 2    Role: D/V
 Patikrinkite, ar modelių kortelės yra versijomis valdomos ir prižiūrimos viso modelio gyvavimo ciklo metu su pakeitimų sekimu.

---

### C13.6 Neapibrėžtumo kiekybinimas

Skleiskite pasitikėjimo balus arba entropijos matavimus atsakymuose.

 #13.6.1    Level: 1    Role: D
 Patikrinkite, ar DI sistemos pateikia pasitikėjimo vertinimus arba neapibrėžtumo matavimus su savo rezultatais.
 #13.6.2    Level: 2    Role: D/V
 Patikrinkite, ar neapibrėžtumo slenksčiai sukelia papildomą žmogaus peržiūrą arba alternatyvius sprendimų kelius.
 #13.6.3    Level: 2    Role: V
 Patikrinkite, ar nežinomybės kiekybinimo metodai yra kalibruoti ir patvirtinti pagal tikrųjų duomenų rezultatus.
 #13.6.4    Level: 3    Role: D/V
 Patikrinkite, ar neapibrėžtumo sklaida išlaikoma per daugiaetapius DI darbo eigas.

---

### C13.7 Vartotojams skirtos skaidrumo ataskaitos

Teikti periodines ataskaitas apie incidentus, nukrypimus ir duomenų naudojimą.

 #13.7.1    Level: 1    Role: D/V
 Patikrinkite, ar duomenų naudojimo politikos ir vartotojų sutikimo valdymo praktikos yra aiškiai perduodamos suinteresuotosioms šalims.
 #13.7.2    Level: 2    Role: D/V
 Patikrinkite, ar atliekami DI poveikio vertinimai ir ar jų rezultatai įtraukiami į ataskaitas.
 #13.7.3    Level: 2    Role: D/V
 Patikrinkite, ar reguliariai paskelbiamos skaidrumo ataskaitos pakankamai detaliai atskleidžia dirbtinio intelekto įvykius ir veiklos rodiklius.

#### Nuorodos

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

## A priedas: Terminų žodynas

Šis išsamus žodynas pateikia pagrindinių DI, ML ir saugumo terminų apibrėžimus, naudojamus visame AISVS, siekiant užtikrinti aiškumą ir bendrą supratimą.
​
Priešininkų pavyzdys: Įvestis, sąmoningai sukurta tam, kad sukeltų AI modeliui klaidą, dažnai pridedant subtilias, žmogui nepastebimas perturbacijas.
​
Priešinės atsparumo savybės – Priešinės atsparumo savybės dirbtiniame intelekte reiškia modelio gebėjimą išlaikyti savo veikimą ir atsispirti klastojimui ar manipuliacijai, kurią sukelia tyčia sukurti, žalingi įvesties duomenys, skirti sukelti klaidas.
​
Agentas – DI agentai yra programinės įrangos sistemos, kurios naudoja dirbtinį intelektą siekdamos tikslų ir vykdydamos užduotis vartotojų vardu. Jie demonstruoja samprotavimą, planavimą ir atmintį bei turi tam tikrą autonomijos lygį priimti sprendimus, mokytis ir prisitaikyti.
​
Agentinė DI: DI sistemos, kurios gali veikti su tam tikru savarankiškumo laipsniu siekiant tikslų, dažnai priimdamos sprendimus ir imdamiesi veiksmų be tiesioginės žmogaus įsikišimo.
​
Prieigos kontrolė pagal atributus (ABAC): prieigos kontrolės modelis, kuriame autorizacijos sprendimai priimami remiantis vartotojo, išteklių, veiksmo ir aplinkos atributais, įvertintais užklausos metu.
​
Galinis įsilaužimas: tam tikra duomenų užnuodijimo ataka, kurioje modelis mokomas reaguoti tam tikru būdu į tam tikrus sužadinimus, tuo tarpu elgiasi įprastai kitu atveju.
​
Šališkumas: Sistematinės klaidos dirbtinio intelekto modelių rezultatų, kurios gali lemti neteisingus ar diskriminuojančius rezultatus tam tikroms grupėms arba specifinėse situacijose.
​
Šališkumo išnaudojimas: atakos metodas, kuris pasinaudoja žinomomis AI modelių šališkumais, siekiant manipuliuoti rezultatais ar pasekmėmis.
​
Cedar: „Amazon“ politikos kalba ir variklis smulkioms leidimų valdymo priemonėms, naudojamoms įgyvendinant ABAC AI sistemoms.
​
Minties grandinė: technika, skirta pagerinti kalbos modelių samprotavimą, generuojant tarpinės sampratos žingsnius prieš pateikiant galutinį atsakymą.
​
Grandininiai išjungikliai: Mechanizmai, kurie automatiškai sustabdo DI sistemos veikimą, kai viršijamos tam tikros rizikos ribos.
​
Duomenų nutekėjimas: netyčinis jautrios informacijos atskleidimas per DI modelio rezultatus ar elgesį.
​
Duomenų užnuodijimas: tyčinis mokymo duomenų sugadinimas, siekiant pažeisti modelio vientisumą, dažnai diegiant užpakalines duris arba bloginant našumą.
​
Differencinė privatumo apsauga – Differencinė privatumo apsauga yra matematiškai griežtas pagrindas statistinės informacijos apie duomenų rinkinius atskleidimui, tuo pačiu apsaugant atskirų duomenų subjektų privatumą. Ji leidžia duomenų turėtojui dalintis grupės bendraisiais modeliais, ribojant informaciją apie konkrečius asmenis.
​
Įterpiniai: tankių vektorių atvaizdavimai duomenų (teksto, vaizdų ir kt.), kurie perteikia semantinę prasmę aukštadimensinėje erdvėje.
​
Paaiškinamumas – paaiškinamumas dirbtiniame intelekte yra DI sistemos sugebėjimas pateikti žmogui suprantamas priežastis savo sprendimams ir prognozėms, suteikiant įžvalgų apie jos vidinį veikimą.
​
Paaiškinamoji DI (XAI): DI sistemos, sukurtos teikti žmonėms suprantamus paaiškinimus apie jų sprendimus ir elgseną, taikant įvairias technikas ir struktūras.
​
Federuotas mokymasis: mašininio mokymosi metodas, kai modeliai mokomi daugelyje decentralizuotų įrenginių, turinčių vietinius duomenų pavyzdžius, nereikalaujant keistis pačiais duomenimis.
​
Saugikliai: Apribojimai, įdiegti tam, kad užkirstų kelią DI sistemoms generuoti žalingą, šališką ar kitaip nepageidaujamą turinį.
​
Halucinacija – AI halucinacija reiškia reiškinį, kai AI modelis sukuria neteisingą arba klaidinamą informaciją, kuri nėra pagrįsta jo mokymo duomenimis ar faktine realybe.
​
Žmogus cikle (Human-in-the-Loop, HITL): Sistemos, sukurtos reikalauti žmogaus priežiūros, patvirtinimo ar įsikišimo svarbiausiuose sprendimų priėmimo taškuose.
​
Infrastruktūra kaip Kodas (IaC): infrastruktūros valdymas ir teikimas per kodą, o ne rankinius procesus, leidžiantį vykdyti saugumo skanavimą ir užtikrinti nuoseklų diegimą.
​
Jailbreak: Technikos, naudojamos apeiti saugumo apribojimus dirbtinio intelekto sistemose, ypač dideliuose kalbos modeliuose, siekiant sukurti draudžiamą turinį.
​
Mažiausių privilegijų principas: saugumo principas, numatantis suteikti vartotojams ir procesams tik būtiniausias prieigos teises.
​
LIME (vieta interpretuojamas modelio nepriklausomas paaiškinimas): technika, skirta paaiškinti bet kurio mašininio mokymosi klasifikatoriaus prognozes, apskaičiuojant jas lokaliai su interpretuojamu modeliu.
​
Nario informacijos atskleidimo ataka: ataka, kurios tikslas yra nustatyti, ar tam tikras duomenų taškas buvo naudojamas mokant mašininio mokymosi modelį.
​
MITRE ATLAS: Priešiškos grėsmės dirbtinio intelekto sistemoms kraštovaizdis; priešiškų taktikų ir technikų žinių bazė prieš DI sistemas.
​
Modelio kortelė – tai dokumentas, suteikiantis standartizuotą informaciją apie dirbtinio intelekto modelio našumą, ribotumus, numatomą panaudojimą ir etinius aspektus, siekiant skatinti skaidrumą ir atsakingą DI vystymą.
​
Modelio išgavimas: ataka, kai priešas kelis kartus užklausia taikinio modelį, siekdamas sukurti funkcionaliai panašią kopiją be leidimo.
​
Modelio inversija: ataka, kuri bando rekonstruoti mokymo duomenis analizuodama modelio išvestis.
​
Modelio gyvavimo ciklo valdymas – AI modelio gyvavimo ciklo valdymas yra procesas, apimantis visų AI modelio egzistavimo etapų priežiūrą, įskaitant jo dizainą, kūrimą, diegimą, stebėjimą, priežiūrą ir galutinį pasenimą, siekiant užtikrinti, kad jis išliktų efektyvus ir atitiktų tikslus.
​
Modelio užnuodijimas: pažeidžiamumų arba užslėptų prieigų įvedimas tiesiogiai į modelį mokymo proceso metu.
​
Modelio vagystė: nuosavo modelio kopijos arba artimos versijos gavimas per daugybinius užklausimus.
​
Daugiagentė sistema: sistema, sudaryta iš kelių sąveikaujančių DI agentų, kiekvienas iš jų gali turėti skirtingas galimybes ir tikslus.
​
OPA (Open Policy Agent): Atviro kodo politikos variklis, leidžiantis vieningai įgyvendinti politikos taisykles visame technologijų sluoksnyje.
​
Privatumo saugojimo mašininis mokymasis (PPML): Technologijos ir metodai, skirti mokyti ir diegti ML modelius, saugant mokymo duomenų privatumą.
​
Promptų injekcija: ataka, kai įvestyse įterpiamos kenkėjiškos instrukcijos, siekiant pakeisti modelio numatytą elgesį.
​
RAG (retrieval-augmented generation): Technika, kuri pagerina didelius kalbos modelius, prieš generuodama atsakymą gaunant aktualią informaciją iš išorinių žinių šaltinių.
​
Red-teamingas: Praktika aktyviai testuoti DI sistemas imituojant priešiškus puolimus, siekiant nustatyti pažeidžiamumus.
​
SBOM (Programinės įrangos sudedamųjų dalių sąrašas): Oficialus įrašas, kuriame pateikiama informacija apie įvairias komponentes ir jų tiekimo grandinės ryšius, naudojamus kuriant programinę įrangą arba dirbtinio intelekto modelius.
​
SHAP (SHapley pridedančios paaiškinimo metodas): žaidimų teorijos pagrindu sukurta priemonė, skirta paaiškinti bet kurio mašininio mokymosi modelio rezultatą apskaičiuojant kiekvieno požymio indėlį į prognozę.
​
Tiekimo grandinės ataka: sistemos pažeidimas taikant silpniausiems jos tiekimo grandinės elementams, tokiems kaip trečiųjų šalių bibliotekos, duomenų rinkiniai ar iš anksto apmokyti modeliai.
​
Perkėlimo mokymasis: technika, kai vienam uždaviniui sukurta modelis naudojamas kaip pradinis taškas modeliui kitam uždaviniui.
​
Vektorinė duomenų bazė: specializuota duomenų bazė, skirta saugoti daugiamates vektorius (įterpimus) ir efektyviai atlikti panašumo paieškas.
​
Pažeidžiamumo nuskaitymas: automatizuoti įrankiai, kurie identifikuoja žinomas saugumo spragas programinės įrangos komponentuose, įskaitant dirbtinio intelekto pagrindus ir priklausomybes.
​
Vandens žymėjimas: technikos, skirtos įterpti nepastebimus žymenis į AI sugeneruotą turinį, siekiant sekti jo kilmę arba aptikti AI generavimą.
​
Nulinės dienos pažeidžiamumas: Anksčiau nežinoma pažeidžiamumo spraga, kurią atakuotojai gali išnaudoti prieš tai, kai kūrėjai sukuria ir įdiegia pataisą.

## B priedas: Nuorodos

### TODO

## Priedas C: DI saugumo valdymas ir dokumentacija

### Tikslas

Šis priedas pateikia pagrindinius reikalavimus organizacinių struktūrų, politikų ir procesų, skirtų valdyti dirbtinio intelekto (DI) saugumą viso sistemos gyvavimo ciklo metu, nustatymui.

---

### AC.1 DI rizikos valdymo sistemos diegimas

Pateikite oficialią sistemą dirbtinio intelekto specifinių rizikų identifikavimui, vertinimui ir mažinimui viso sistemos gyvavimo ciklo metu.

 #AC.1.1    Level: 1    Role: D/V
 Patikrinkite, ar yra dokumentuota ir įgyvendinta AI specifinė rizikos vertinimo metodika.
 #AC.1.2    Level: 2    Role: D
 Patikrinkite, ar rizikos vertinimai atliekami svarbiausiais AI gyvavimo ciklo etapais ir prieš reikšmingus pokyčius.
 #AC.1.3    Level: 3    Role: D/V
 Patikrinkite, ar rizikos valdymo sistema atitinka nustatytus standartus (pvz., NIST AI RMF).

---

### AC.2 DI saugumo politika ir procedūros

Apibrėžkite ir užtikrinkite organizacinius standartus saugiam DI kūrimui, diegimui ir veikimui.

 #AC.2.1    Level: 1    Role: D/V
 Patvirtinkite, kad egzistuoja dokumentuotos DI saugumo politikos.
 #AC.2.2    Level: 2    Role: D
 Patikrinkite, ar politikos peržiūrimos ir atnaujinamos bent kartą per metus bei po reikšmingų grėsmių aplinkos pokyčių.
 #AC.2.3    Level: 3    Role: D/V
 Patikrinkite, ar politikos apima visas AISVS kategorijas ir taikomus reguliavimo reikalavimus.

---

### AC.3 AI saugumo vaidmenys ir atsakomybės

Nustatykite aiškią atsakomybę už DI saugumą visoje organizacijoje.

 #AC.3.1    Level: 1    Role: D/V
 Patikrinkite, ar AI saugumo vaidmenys ir atsakomybės yra dokumentuotos.
 #AC.3.2    Level: 2    Role: D
 Patikrinkite, ar atsakingi asmenys turi tinkamų saugumo žinių.
 #AC.3.3    Level: 3    Role: D/V
 Patikrinkite, ar yra įsteigta DI etikos komisija arba valdymo taryba aukštos rizikos DI sistemoms.

---

### AC.4 Etinių dirbtinio intelekto gairių įgyvendinimas

Užtikrinkite, kad dirbtinio intelekto sistemos veiktų pagal nustatytas etikos principus.

 #AC.4.1    Level: 1    Role: D/V
 Patikrinkite, ar egzistuoja etikos gairės dirbtinio intelekto kūrimui ir diegimui.
 #AC.4.2    Level: 2    Role: D
 Patikrinkite, ar yra įdiegti mechanizmai, skirti aptikti ir pranešti apie etikos pažeidimus.
 #AC.4.3    Level: 3    Role: D/V
 Patikrinkite, ar vykdomos reguliarios diegtų DI sistemų etinės apžvalgos.

---

### AC.5 Dirbtinio intelekto reguliavimo atitikties stebėjimas

Išlaikykite sąmoningumą ir laikykitės besikeičiančių dirbtinio intelekto reguliavimų.

 #AC.5.1    Level: 1    Role: D/V
 Patikrinkite, ar yra procesai, leidžiantys nustatyti taikomus DI reglamentus.
 #AC.5.2    Level: 2    Role: D
 Patikrinkite, ar įvertintas atitikties visiems reguliavimo reikalavimams laikymasis.
 #AC.5.3    Level: 3    Role: D/V
 Patikrinkite, ar reguliavimo pakeitimai sukelia laiku atliekamus peržiūras ir atnaujinimus AI sistemose.

#### Nuorodos

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Priedas D: AI Pagalba Užtikrinant Saugų Programavimo Valdymą ir Patikrinimą

### Tikslas

Šiame skyriuje apibrėžiamos pagrindinės organizacinės kontrolės, skirtos saugiam ir veiksmingam AI pagalba atliekamo kodavimo įrankių naudojimui programinės įrangos kūrimo metu, užtikrinant saugumą ir atsekamumą per visą programinės įrangos kūrimo gyvenimo ciklą (SDLC).

---

### AD.1 Dirbtiniu intelektu pagrįstas saugaus kodavimo darbo eiga

Integruokite DI įrankius organizacijos saugaus programinės įrangos kūrimo gyvavimo cikle (SSDLC), nesumažindami esamos saugumo apsaugos.

 #AD.1.1    Level: 1    Role: D/V
 Patikrinkite, ar dokumentuotas darbo procesas aprašo, kada ir kaip AI įrankiai gali generuoti, perrašyti ar peržiūrėti kodą.
 #AD.1.2    Level: 2    Role: D
 Patikrinkite, ar darbo eiga atitinka kiekvieną SSDLC fazę (dizainas, įgyvendinimas, kodo peržiūra, testavimas, diegimas).
 #AD.1.3    Level: 3    Role: D/V
 Patikrinkite, ar metrikos (pvz., pažeidžiamumo tankis, vidutinis laikas aptikimui) renkami AI sukurtam kodui ir lyginamos su tik žmogaus sukurtų pagrindinių rodiklių reikšmėmis.

---

### AD.2 DI įrankio kvalifikacija ir grėsmių modeliavimas

Užtikrinkite, kad AI programavimo įrankiai būtų įvertinti pagal saugumo galimybes, riziką ir tiekimo grandinės poveikį prieš juos priimant.

 #AD.2.1    Level: 1    Role: D/V
 Patikrinkite, ar kiekvienos DI priemonės grėsmių modelis identifikuoja neteisėtą naudojimą, modelio invertavimą, duomenų nutekėjimą ir priklausomybių grandinės rizikas.
 #AD.2.2    Level: 2    Role: D
 Patikrinkite, ar įrankių vertinimai apima statinę/dinaminę bet kurių vietinių komponentų analizę bei SaaS galinių taškų (TLS, autentifikavimas/autorizacija, žurnalavimas) vertinimą.
 #AD.2.3    Level: 3    Role: D/V
 Patikrinkite, ar vertinimai atliekami pagal pripažintą sistemą ir kartojami po pagrindinių versijų pakeitimų.

---

### AD.3 Saugaus užklausos ir konteksto valdymas

Užkirsti kelią slaptos informacijos, nuosavybinių kodų ir asmeninių duomenų nutekėjimui formuojant užklausas ar kontekstus dirbtinio intelekto modeliams.

 #AD.3.1    Level: 1    Role: D/V
 Patikrinkite, ar rašytinė gairė draudžia siųsti paslaptis, prisijungimo duomenis arba klasifikuotą informaciją užklausose.
 #AD.3.2    Level: 2    Role: D
 Patikrinkite, ar techninės priemonės (kliento pusės redagavimas, patvirtinti konteksto filtrai) automatiškai pašalina jautrius duomenis.
 #AD.3.3    Level: 3    Role: D/V
 Patikrinkite, ar užklausos ir atsakymai yra tokenizuoti, šifruojami perduodant ir saugant bei ar saugojimo laikotarpiai atitinka duomenų klasifikavimo politiką.

---

### AD.4 Dirbtinio intelekto sukurtų kodų patikrinimas

Nustatykite ir pašalinkite pažeidžiamumus, sukurtus AI išvesties, prieš sujungiami ar diegiant kodą.

 #AD.4.1    Level: 1    Role: D/V
 Patikrinkite, ar AI sugeneruotas kodas visada yra peržiūrimas žmogaus.
 #AD.4.2    Level: 2    Role: D
 Patikrinkite, ar automatizuoti skaitytuvai (SAST/IAST/DAST) veikia kiekviename patraukimo prašyme, kuriame yra AI sukurtas kodas, ir blokuoja susijungimus esant kritiniams aptikimams.
 #AD.4.3    Level: 3    Role: D/V
 Patikrinkite, ar diferencialiniai delsimieji testai arba savybių pagrindu sukurti testai įrodo saugumo požiūriu kritines elgsenas (pvz., įvesties tikrinimą, autorizacijos logiką).

---

### AD.5 Kodo pasiūlymų paaiškinamumas ir atsekamumas

Suteikite auditoriams ir kūrėjams įžvalgų apie tai, kodėl buvo pateikta pasiūlymas ir kaip jis vystėsi.

 #AD.5.1    Level: 1    Role: D/V
 Patikrinkite, ar užklausų/atsakymų poros yra registruojamos kartu su komitų identifikatoriais.
 #AD.5.2    Level: 2    Role: D
 Patikrinkite, ar kūrėjai gali pateikti modelio citatas (mokymo fragmentus, dokumentaciją), pagrindžiančias pasiūlymą.
 #AD.5.3    Level: 3    Role: D/V
 Patikrinkite, ar aiškinamumo ataskaitos saugomos kartu su dizaino artefaktais ir nurodomos saugumo peržiūrose, atitinkančios ISO/IEC 42001 sekamumo principus.

---

### AD.6 Nuolatinis atsiliepimų teikimas ir modelio tobulinimas

Laikui bėgant gerinti modelio saugumo veikimą, užkertant kelią neigiamam poslinkiui.

 #AD.6.1    Level: 1    Role: D/V
 Patikrinkite, ar kūrėjai gali pažymėti nesaugias arba neprisitaikančias prie reikalavimų pasiūlymus, ir ar šie ženklai yra fiksuojami.
 #AD.6.2    Level: 2    Role: D
 Patikrinkite, ar apibendrintas grįžtamasis ryšys informuoja periodinį papildomą modelio apmokymą arba atgavimo pagrindu sukurtą generavimą, naudojant patikrintus saugaus kodo rašymo korpusus (pvz., OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Patikrinkite, ar uždaro ciklo vertinimo sistema vykdo regresijos testus po kiekvieno tikslinimo; saugumo metrikos turi atitikti arba viršyti ankstesnius bazinius rodiklius prieš diegiant.

---

#### Nuorodos

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Priedas E: Pavyzdiniai įrankiai ir karkasai

### Tikslas

Šis skyrius pateikia įrankių ir sistemų pavyzdžius, kurie gali padėti įgyvendinti arba užtikrinti tam tikrą AISVS reikalavimą. Šie pavyzdžiai neturėtų būti laikomi AISVS komandos ar OWASP GenAI Security projekto rekomendacijomis ar pritarimais.

---

### AE.1 Mokymo duomenų valdymas ir šališkumo valdymas

Įrankiai, naudojami duomenų analitikai, valdymui ir šališkumo valdymui.

 #AE.1.1    Section: 1.1
 Duomenų inventoriaus įrankiai: Duomenų inventoriaus valdymo įrankiai, tokie kaip...
 #AE.1.2    Section: 1.2
 Šifravimas perduodant naudojant TLS HTTPS pagrįstoms programoms, naudojant įrankius, tokius kaip openSSL ir python'o`ssl`biblioteka.

---

### AE.2 Vartotojo įvesties tikrinimas

Įrankiai vartotojo įvestims tvarkyti ir tikrinti.

 #AE.2.1    Section: 2.1
 Promptų injekcijų gynimo priemonės: naudokite apsaugos priemones, tokias kaip NVIDIA NeMo arba Guardrails AI.

---

## C1 Mokymo duomenų valdymas ir šališkumo valdymas

### C1.1 Mokymo duomenų kilmė

Išlaikykite patikrinamą visų duomenų rinkinių inventorių, priimkite tik patikimus šaltinius ir registruokite kiekvieną pakeitimą audito tikslais.

 #1.1.1    Level: 1    Role: D/V
 Patikrinkite, ar nuolatos atnaujinamas kiekvieno mokymo duomenų šaltinio inventorius (šaltinis, tvarkytojas/savininkas, licencija, rinkimo metodas, numatyti naudojimo apribojimai ir apdorojimo istorija).

