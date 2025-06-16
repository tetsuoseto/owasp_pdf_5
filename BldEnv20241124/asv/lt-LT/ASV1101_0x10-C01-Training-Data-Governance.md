# C1 Mokymo duomenų valdymas ir šališkumo valdymas

## Valdymo tikslas

Mokymo duomenys turi būti gaunami, tvarkomi ir prižiūrimi taip, kad būtų išsaugota kilmė, saugumas, kokybė ir teisingumas. Tai atitinka teisines pareigas ir sumažina šališkumo, apsinuodijimo ar privatumo pažeidimų riziką viso DI gyvavimo ciklo metu.

---

## C1.1 Mokymo duomenų kilmė

Laikykite patikrinamą visų duomenų rinkinių inventorių, priimkite tik patikimus šaltinius ir fiksuokite kiekvieną pakeitimą, kad būtų užtikrintas audito galimumas.

|   #   | Description                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Patikrinkite, ar yra palaikomas atnaujintas kiekvieno mokymo duomenų šaltinio (kilmė, atsakingas asmuo/savininkas, licencija, surinkimo metodas, numatyti naudojimo apribojimai ir apdorojimo istorija) inventorius.                                                                                   |   1   | D/V  |
| 1.1.2 | Patikrinkite, ar leidžiami tik duomenų rinkiniai, patikrinti dėl kokybės, atstovavimo, etinio šaltinio ir licencijų atitikties, sumažinant apsinuodijimo, įterptos šališkumo ir intelektinės nuosavybės pažeidimų riziką.                                                                              |   1   | D/V  |
| 1.1.3 | Patikrinkite, ar duomenų minimizavimas yra taikomas, kad nebūtų įtraukti nereikalingi ar jautrūs atributai.                                                                                                                                                                                            |   1   | D/V  |
| 1.1.4 | Patikrinkite, ar visi duomenų rinkinio pakeitimai yra patvirtinami pagal registruojamą patvirtinimo darbo eigą.                                                                                                                                                                                        |   2   | D/V  |
| 1.1.5 | Patikrinkite, ar ženklinimo/žymėjimo kokybė užtikrinama peržiūrėtojų kryžminiais patikrinimais arba susitarimu.                                                                                                                                                                                        |   2   | D/V  |
| 1.1.6 | Patikrinkite, ar svarbiems mokymo duomenų rinkiniams yra palaikomos „duomenų kortelės“ arba „duomenų rinkinių techninės specifikacijos“, kurios detaliai aprašo charakteristikas, motyvus, sudėtį, rinkimo procesus, išankstinį apdorojimą bei rekomenduojamus ar nerekomenduojamus panaudojimo būdus. |   2   | D/V  |

---

## C1.2 Mokymo duomenų saugumas ir integralumas

Apribokite prieigą, užšifruokite duomenis ramybės būsenoje ir perdavimo metu, taip pat patikrinkite vientisumą, kad užkirstumėte kelią klastojimui ar vagystei.

|   #   | Description                                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Patikrinkite, ar prieigos kontrolės saugo saugyklas ir duomenų srautus.                                                                                                                                                                                                                                                         |   1   | D/V  |
| 1.2.2 | Patikrinkite, ar duomenų rinkiniai yra užšifruoti perduodant, o visai jautriai ar asmeniškai identifikuojamai informacijai (PII) – ramybės būsenoje, naudojant pramonės standartinius kriptografinius algoritmus ir raktų valdymo praktikas.                                                                                    |   2   | D/V  |
| 1.2.3 | Patikrinkite, ar naudojami kriptografiniai hešai arba skaitmeniniai parašai duomenų vientisumui užtikrinti saugojimo ir perdavimo metu, taip pat ar taikomos automatizuotos anomalijų aptikimo technikos, skirtos apsisaugoti nuo neleistinų modifikacijų ar duomenų korupcijos, įskaitant taikinius duomenų užnuodymo atvejus. |   2   | D/V  |
| 1.2.4 | Patikrinkite, ar duomenų rinkinio versijos yra sekamos, kad būtų galima atlikti grąžinimą atgal.                                                                                                                                                                                                                                |   3   | D/V  |
| 1.2.5 | Patikrinkite, ar pasenę duomenys yra saugiai ištrinami arba anonimizuojami laikantis duomenų saugojimo politikos, teisinių reikalavimų ir siekiant sumažinti atakos paviršių.                                                                                                                                                   |   2   | D/V  |

---

## C1.3 Atstovavimo pilnumas ir sąžiningumas

Aptikti demografinius šališkumus ir taikyti mažinimo priemones, kad modelio klaidų lygiai būtų teisingi tarp grupių.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Patikrinkite, ar duomenų rinkiniai yra profiliuojami dėl atstovavimo disbalanso ir galimų šališkumų pagal teisės apsaugotus atributus (pvz., rasė, lytis, amžius) ir kitas etiškai jautrias savybes, susijusias su modelio taikymo sritimi (pvz., socioekonominė padėtis, vietovė).                                                                                              |   1   | D/V  |
| 1.3.2 | Patikrinkite, ar nustatyti šališkumai yra sušvelninti dokumentuotomis strategijomis, tokiomis kaip duomenų subalansavimas, taikomas didinimas, algoritminių koregavimų taikymas (pvz., išankstinis apdorojimas, procesavimo metu arba po apdorojimo technikos) arba svorių perskaičiavimas, ir įvertinkite šių priemonių poveikį tiek teisingumui, tiek bendram modelio našumui. |   2   | D/V  |
| 1.3.3 | Patikrinkite, ar po mokymo modelio teisingumo metrikos yra įvertintos ir užfiksuotos.                                                                                                                                                                                                                                                                                            |   2   | D/V  |
| 1.3.4 | Patikrinkite, ar gyvenimo ciklo šališkumo valdymo politika priskiria atsakinguosius asmenis ir apibrėžia peržiūros dažnumą.                                                                                                                                                                                                                                                      |   3   | D/V  |

---

## C1.4 Mokymo duomenų ženklinimo kokybė, vientisumas ir saugumas

Apsaugokite etiketes šifravimu ir reikalaukite dvigubo peržiūrėjimo kritinėms klasėms.

|   #   | Description                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Užtikrinkite, kad ženklinimo/anuotacijos kokybė būtų garantuota aiškiomis gairėmis, peržiūrėtojų kryžminiais patikrinimais, sutarimo mechanizmais (pvz., stebint tarpanuotrautojų sutarimą) ir apibrėžtais procesais skirtumams spręsti.                                        |   2   | D/V  |
| 1.4.2 | Patikrinkite, ar kriptografiniai hešai arba skaitmeniniai parašai yra pritaikyti etiketės artefaktams, siekiant užtikrinti jų integralumą ir autentiškumą.                                                                                                                      |   2   | D/V  |
| 1.4.3 | Patikrinkite, ar žymėjimo sąsajos ir platformos užtikrina tvirtą prieigos kontrolę, palaiko pažeidimus atskleidžiančius audito žurnalus apie visas žymėjimo veiklas ir saugo nuo neautorizuotų pakeitimų.                                                                       |   2   | D/V  |
| 1.4.4 | Patikrinkite, ar saugumo, apsaugos ar sąžiningumo požiūriu svarbūs etikečių ženklinimai (pvz., toksiško turinio, kritinių medicininių išvadų nustatymas) privalo būti nepriklausomai peržiūrimi dviem asmenimis arba turi ekvivalentinę stiprią patikrą.                        |   3   | D/V  |
| 1.4.5 | Patikrinkite, ar jautri informacija (įskaitant asmens identifikavimo duomenis) netyčia užfiksuota ar būtinai esanti etikėtėse yra užmaskuota, pseudonimizuota, anonimizuota arba užšifruota tiek saugojimo, tiek perdavimo metu, vadovaujantis duomenų minimizavimo principais. |   2   | D/V  |
| 1.4.6 | Patikrinkite, ar ženklinimo vadovai ir instrukcijos yra išsamūs, valdomi versijų ir peržiūrėti kolegų.                                                                                                                                                                          |   2   | D/V  |
| 1.4.7 | Patikrinkite, ar duomenų schemos (įskaitant etikečių schemas) yra aiškiai apibrėžtos ir valdomos versijų tvarka.                                                                                                                                                                |   2   | D/V  |
| 1.8.2 | Patikrinkite, ar perduoti ar minios pagalba atliekami žymėjimo darbo srautai apima technines/procedūrines apsaugos priemones, užtikrinančias duomenų konfidencialumą, vientisumą, žymių kokybę ir užkertančias kelią duomenų nutekėjimui.                                       |   2   | D/V  |

---

## C1.5 Mokymo duomenų kokybės užtikrinimas

Sujunkite automatizuotą tikrinimą, rankinius atsitiktinius patikrinimus ir registruotą taisymą, siekiant užtikrinti duomenų rinkinio patikimumą.

|   #   | Description                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Patikrinkite, ar automatizuoti testai fiksuoja formato klaidas, nulinius duomenis ir etikečių poslinkius kiekvieno įvedimo ar reikšmingos transformacijos metu.                                                                                                                            |   1   |  D   |
| 1.5.2 | Patikrinkite, ar nesėkmingi duomenų rinkiniai yra izoliuoti su audito takais.                                                                                                                                                                                                              |   1   | D/V  |
| 1.5.3 | Patikrinkite, ar domeno ekspertų rankiniai patikrinimai apima statistiškai reikšmingą imtį (pvz., ≥1 % arba 1 000 pavyzdžių, priklausomai, kuris didesnis, arba kaip nustato rizikos vertinimas), siekiant nustatyti subtilias kokybės problemas, kurios nepastebimos automatizavimo metu. |   2   |  V   |
| 1.5.4 | Patikrinkite, ar pataisymo veiksmai yra pridėti prie kilmės įrašų.                                                                                                                                                                                                                         |   2   | D/V  |
| 1.5.5 | Patikrinkite, ar kokybės vartai blokuoja žemesnės kokybės duomenų rinkinius, nebent būtų patvirtintos išimtys.                                                                                                                                                                             |   2   | D/V  |

---

## C1.6 Duomenų užnuodijimo aptikimas

Taikyti statistinį anomalijų nustatymą ir izoliacijos darbo eigas, kad sustabdytų priešiškus įterpimus.

|   #   | Description                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Patikrinkite, ar anomalijų aptikimo metodai (pvz., statistiniai metodai, netipinių atvejų nustatymas, įterpimų analizė) taikomi treniruočių duomenims įvedimo metu ir prieš pagrindinius treniruočių procesus, siekiant nustatyti galimus duomenų užteršimo išpuolius arba netyčinę duomenų korupciją. |   2   | D/V  |
| 1.6.2 | Patikrinkite, ar pažymėti pavyzdžiai sukelia rankinį peržiūrėjimą prieš mokymą.                                                                                                                                                                                                                        |   2   | D/V  |
| 1.6.3 | Patikrinkite, ar rezultatai įtraukiami į modelio saugumo bylą ir informuoja apie nuolatinę grėsmių žvalgybą.                                                                                                                                                                                           |   2   |  V   |
| 1.6.4 | Patikrinkite, ar aptikimo logika yra atnaujinta su nauja grėsmių informacija.                                                                                                                                                                                                                          |   3   | D/V  |
| 1.6.5 | Patikrinkite, ar internetinio mokymosi srautai stebi pasiskirstymo pakitimus.                                                                                                                                                                                                                          |   3   | D/V  |
| 1.6.6 | Patikrinkite, ar konkrečios gynybos priemonės nuo žinomų duomenų užteršimo atakų tipų (pvz., etikečių apvertimas, užpakalinio durų užtaisymo įterpimas, įtakingų atvejų atakos) yra apsvarstytos ir įgyvendintos atsižvelgiant į sistemos rizikos profilį ir duomenų šaltinius.                        |   3   | D/V  |

---

## C1.7 Vartotojo duomenų naikinimas ir sutikimo laikymosi kontrolė

Gerbkite ištrynimo ir sutikimo atšaukimo užklausas visuose duomenų rinkiniuose, atsarginėse kopijose ir išvestiniuose artefaktuose.

|   #   | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Patikrinkite, ar ištrynimo darbo eiga pašalina pirminius ir išvestinius duomenis bei įvertinkite modelio poveikį, taip pat užtikrinkite, kad paveiktų modelių poveikis būtų įvertintas ir, jei reikia, sprendžiamas (pvz., perkvalifikavimu arba perkoregavimu).              |   1   | D/V  |
| 1.7.2 | Patikrinkite, ar yra įdiegtos priemonės vartotojo sutikimo (ir jo atšaukimo) apimčiai ir būsenai sekti bei gerbti dėl duomenų, naudojamų mokymui, ir ar sutikimas yra patvirtinamas prieš įtraukiant duomenis į naujus mokymo procesus arba reikšmingus modelio atnaujinimus. |   2   |  D   |
| 1.7.3 | Patikrinkite, ar darbo eiga yra testuojama kasmet ir įrašoma į žurnalą.                                                                                                                                                                                                       |   2   |  V   |

---

## C1.8 Tiekimo grandinės saugumas

Patikrinkite išorinius duomenų tiekėjus ir patvirtinkite duomenų vientisumą per autentifikuotus, užšifruotus kanalus.

|   #   | Description                                                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.8.1 | Patikrinkite, ar trečiųjų šalių duomenų tiekėjai, įskaitant iš anksto apmokytų modelių tiekėjus ir išorinius duomenų rinkinius, praeina saugumo, privatumo, etiško tiekimo ir duomenų kokybės patikrinimus prieš integruojant jų duomenis ar modelius.                                                                         |   2   | D/V  |
| 1.8.2 | Patikrinkite, ar išoriniai pervedimai naudoja TLS/autentifikavimą ir vientisumo patikrinimus.                                                                                                                                                                                                                                  |   1   |  D   |
| 1.8.3 | Patikrinkite, ar aukštos rizikos duomenų šaltiniai (pvz., atviro kodo duomenų rinkiniai su nežinoma kilme, nepatikrinti tiekėjai) prieš naudojimą jautriose programose gauna išplėstinį patikrinimą, pvz., analizes aptvertose aplinkose, išsamius kokybės/šališkumo patikrinimus ir nukreiptą apsaugą nuo duomenų klastojimo. |   2   | D/V  |
| 1.8.4 | Patikrinkite, ar iš trečiųjų šalių gauti iš anksto apmokyti modeliai yra įvertinti dėl įterptų šališkumų, galimų galinių durų, jų architektūros vientisumo ir pradinio mokymo duomenų kilmės prieš atliekant tolesnį pritaikymą arba diegimą.                                                                                  |   3   | D/V  |

---

## C1.9 Priešininkų pavyzdžių aptikimas

Įgyvendinkite priemones mokymo fazėje, tokias kaip priešiškas mokymas, siekiant pagerinti modelio atsparumą priešiškiems pavyzdžiams.

|   #   | Description                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.9.1 | Patikrinkite, ar taikomos tinkamos gynybos priemonės, tokios kaip priešininkų mokymas (naudojant sugeneruotus priešininkų pavyzdžius), duomenų praplėtimas su perturbuotais įėjimais arba patikimos optimizacijos metodai, ir ar jos yra pritaikytos bei paruoštos atitinkamiems modeliams, remiantis rizikos vertinimu. |   3   | D/V  |
| 1.9.2 | Įsitikinkite, kad jei naudojamas priešiškas mokymas, priešų duomenų rinkinių generavimas, valdymas ir versijų kontrolė yra dokumentuojami ir prižiūrimi.                                                                                                                                                                 |   2   | D/V  |
| 1.9.3 | Patikrinkite, ar įvertinamas, dokumentuojamas ir stebimas priešinimosi priešiškam triukšmui mokymo poveikis modeliui (tiek tvarkingų, tiek priešiškų duomenų atžvilgiu) ir sąžiningumo metrikoms.                                                                                                                        |   3   | D/V  |
| 1.9.4 | Patikrinkite, ar priešiško mokymo ir atsparumo strategijos yra periodiškai peržiūrimos ir atnaujinamos, siekiant atsispirti kintančioms priešiškų atakų technikoms.                                                                                                                                                      |   3   | D/V  |

---

## C1.10 Duomenų kilmė ir atsekamumas

Sekite kiekvieno duomenų taško visą kelionę nuo šaltinio iki modelio įvesties, siekiant tikrinamumo ir incidentų reagavimo.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Patikrinkite, ar kiekvieno duomenų taško kilmė, įskaitant visas transformacijas, papildymus ir sujungimus, yra įrašyta ir gali būti atkurta. |   2   | D/V  |
| 1.10.2 | Patikrinkite, ar kilmės įrašai yra nekeičiamo formato, saugiai saugomi ir prieinami audito ar tyrimų tikslams.                               |   2   | D/V  |
| 1.10.3 | Patikrinkite, ar šakninių duomenų sekimas apima tiek žalius, tiek sintetinius duomenis.                                                      |   2   | D/V  |

---

## C1.11 Sintetiniai duomenų valdymas

Užtikrinkite, kad sintetiniai duomenys būtų tinkamai tvarkomi, sužymėti ir įvertinti rizikos požiūriu.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Patikrinkite, ar visa sintetika duomenys yra aiškiai pažymėti ir atskiriami nuo tikrųjų duomenų visame duomenų apdorojimo procese.       |   2   | D/V  |
| 1.11.2 | Patikrinkite, ar generavimo procesas, parametrai ir numatytas sintetinių duomenų naudojimas yra dokumentuoti.                            |   2   | D/V  |
| 1.11.3 | Patikrinkite, ar sintetiniai duomenys yra įvertinti dėl šališkumo, privatumo nutekėjimo ir atstovavimo problemų prieš naudojimą mokymui. |   2   | D/V  |

---

## C1.12 Duomenų prieigos stebėjimas ir anomalijų nustatymas

Stebėkite ir signalizuokite apie neįprastą prieigą prie mokymo duomenų, siekiant aptikti vidinius grėsmes arba duomenų nutekėjimą.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Patikrinkite, ar visi duomenų mokymo prieigos veiksmai yra užfiksuoti, įskaitant naudotoją, laiką ir veiksmą.                             |   2   | D/V  |
| 1.12.2 | Patikrinkite, ar prieigos žurnalai reguliariai peržiūrimi dėl neįprastų modelių, pavyzdžiui, didelių eksportų ar prieigos iš naujų vietų. |   2   | D/V  |
| 1.12.3 | Patikrinkite, ar įspėjimai generuojami dėl įtartinų prieigos įvykių ir ar jie yra nedelsiant tiriami.                                     |   2   | D/V  |

---

## C1.13 Duomenų saugojimo ir galiojimo nutraukimo politikos

Apibrėžkite ir taikykite duomenų saugojimo laikotarpius, kad sumažintumėte nereikalingą duomenų saugojimą.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.13.1 | Patikrinkite, ar visiems mokymo duomenų rinkiniams yra apibrėžti aiškūs saugojimo terminai.                                    |   1   | D/V  |
| 1.13.2 | Patikrinkite, ar duomenų rinkiniai automatiškai pasibaigia, trinami arba peržiūrimi dėl trynimo pasibaigus jų gyvenimo ciklui. |   2   | D/V  |
| 1.13.3 | Patikrinkite, ar saugojimo ir šalinimo veiksmai yra registruojami ir tikrinami.                                                |   2   | D/V  |

---

## C1.14 Reguliavimo ir jurisdikcijos atitiktis

Užtikrinkite, kad visi mokymo duomenys atitiktų taikomus įstatymus ir nuostatas.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Patikrinkite, ar duomenų lokalizacijos ir tarpvalstybinio perdavimo reikalavimai yra nustatyti ir vykdomi visoms duomenų rinkmenoms.     |   2   | D/V  |
| 1.14.2 | Patikrinkite, ar sektoriui specifiniai reguliavimai (pvz., sveikatos priežiūra, finansai) yra nustatyti ir sprendžiami duomenų tvarkyme. |   2   | D/V  |
| 1.14.3 | Patikrinkite, ar atitiktis galiojantiems privatumo įstatymams (pvz., GDPR, CCPA) yra dokumentuota ir reguliariai peržiūrima.             |   2   | D/V  |

---

## C1.15 Duomenų vandens ženklinimas ir pirštų atspaudų žymėjimas

Aptikti neleistinį nuosavybės ar jautrių duomenų pakartotinį naudojimą arba nutekėjimą.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.15.1 | Patikrinkite, ar duomenų rinkiniai arba jų pogrupiai, jei įmanoma, yra pažymėti vandens ženklais arba pirštų atspaudais.                                     |   3   | D/V  |
| 1.15.2 | Patvirtinkite, kad vandens ženklinimo/pažymėjimo metodai nesukelia šališkumo ar privatumo rizikų.                                                            |   3   | D/V  |
| 1.15.3 | Patikrinkite, ar atliekamos periodinės patikros, siekiant nustatyti neautorizuotą vandens ženklu pažymėtos informacijos pakartotinį naudojimą ar nutekėjimą. |   3   | D/V  |

---

## C1.16 Duomenų subjektų teisių valdymas

Remti duomenų subjektų teises, tokias kaip prieiga, taisymas, apribojimas ir prieštaravimas.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Patikrinkite, ar egzistuoja mechanizmai, leidžiantys reaguoti į duomenų subjektų pateiktus prieigos, taisymo, apribojimo ar prieštaravimo reikalavimus. |   2   | D/V  |
| 1.16.2 | Patikrinkite, ar užklausos yra registruojamos, stebimos ir įvykdomos per teisės aktų nustatytus terminus.                                               |   2   | D/V  |
| 1.16.3 | Patikrinkite, ar duomenų subjektų teisių procesai yra reguliariai tikrinami ir peržiūrimi dėl veiksmingumo.                                             |   2   | D/V  |

---

## C1.17 Duomenų rinkinio versijos poveikio analizė

Įvertinkite duomenų rinkinio pokyčių poveikį prieš atnaujindami ar keisdami versijas.

|   #    | Description                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Patikrinkite, ar atliekama poveikio analizė prieš atnaujinant ar keičiant duomenų rinkinio versiją, apimanti modelio našumą, teisingumą ir atitiktį. |   2   | D/V  |
| 1.17.2 | Patikrinkite, ar poveikio analizės rezultatai yra dokumentuoti ir peržiūrėti atitinkamų suinteresuotųjų šalių.                                       |   2   | D/V  |
| 1.17.3 | Patikrinkite, ar yra atstatymo planai tuo atveju, jei naujos versijos sukeltų nepriimtinas rizikas arba regresijas.                                  |   2   | D/V  |

---

## C1.18 Duomenų anotacijų darbo jėgos saugumas

Užtikrinti duomenų anotacijoje dalyvaujančio personalo saugumą ir vientisumą.

|   #    | Description                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Patikrinkite, ar visi duomenų anotacijoje dalyvaujantys asmenys yra patikrinti ir apmokyti duomenų saugumo bei privatumo srityje. |   2   | D/V  |
| 1.18.2 | Patikrinkite, ar visi anotacijų darbuotojai pasirašo konfidencialumo ir neatskleidimo sutartis.                                   |   2   | D/V  |
| 1.18.3 | Patikrinkite, ar anotacijų platformos įgyvendina prieigos kontrolę ir stebi vidaus grėsmes.                                       |   2   | D/V  |

---

## Nuorodos

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

