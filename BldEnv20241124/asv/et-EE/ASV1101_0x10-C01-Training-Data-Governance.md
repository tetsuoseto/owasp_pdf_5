# C1 Treeningandmete haldus ja eelarvamuste juhtimine

## Kontrolli eesmärk

Treeningandmed tuleb hankida, töödelda ja säilitada viisil, mis tagab nende päritolu, turvalisuse, kvaliteedi ja õiglust. Seda tehes täidetakse seaduslikke kohustusi ning vähendatakse kallutuse, mürgitamise või privaatsusrikkumiste riske kogu tehisintellekti elutsükli vältel.

---

## C1.1 Treeningandmete päritolu

Hoidke kõigi andmekogumite usaldusväärset inventuuri, aktsepteerige ainult usaldusväärseid allikaid ja logige iga muudatus auditeerimise võimaldamiseks.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Kinnitage, et hoitakse ajakohast loendit kõigist treeningandmete allikatest (päritolu, haldaja/omanik, litsents, kogumismeetod, ettenähtud kasutuspiirangud ja töötlemise ajalugu).                                                |   1   | D/V  |
| 1.1.2 | Kinnitage, et lubatud on ainult kvaliteedi, esinduslikkuse, eetilise hankimise ja litsentsinõuetele vastavuse osas kontrollitud andmekogud, vähendades mürgitamise, peidetud kallutatuse ja intellektuaalomandi rikkumise riske.   |   1   | D/V  |
| 1.1.3 | Veenduge, et andmete minimeerimine oleks tagatud, nii et ebavajalikud või tundlikud atribuudid oleksid välistatud.                                                                                                                 |   1   | D/V  |
| 1.1.4 | Kinnitage, et kõik andmekogumi muudatused alluvad registreeritud kinnituse töövoole.                                                                                                                                               |   2   | D/V  |
| 1.1.5 | Kinnitage, et märgendamise/annotatsiooni kvaliteet on tagatud ülevaatajate ristkontrolli või konsensuse kaudu.                                                                                                                     |   2   | D/V  |
| 1.1.6 | Veenduge, et oluliste treeningandmekogumite jaoks oleksid hooldatud „andmekaardid“ või „andmelehted“, mis kirjeldavad omadusi, põhjendusi, koosseisu, kogumisprotsesse, eelprotsessimist ning soovitatud/eitaotletud kasutusviise. |   2   | D/V  |

---

## C1.2 Treeningandmete turvalisus ja terviklikkus

Piira juurdepääsu, krüpteeri andmed nii puhkeolekus kui ka edastamisel ning kontrolli terviklikkust, et takistada muutmist või vargust.

|   #   | Description                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.2.1 | Kinnitage, et juurdepääsukontrollid kaitsevad salvestusruumi ja andmepõlde.                                                                                                                                                                                                                                              |   1   | D/V  |
| 1.2.2 | Veenduge, et andmekogumid on krüpteeritud edastusprotsessis ning kõikide tundlike või isikut tuvastavate andmete (PII) puhul ka puhkeolekus, kasutades tööstusharu standarditele vastavaid krüptograafilisi algoritme ja võtmete halduspraktikaid.                                                                       |   2   | D/V  |
| 1.2.3 | Kontrollige, et andmete terviklikkuse tagamiseks salvestamise ja edastamise ajal kasutatakse krüptograafilisi räsi- või digitaalseid allkirju ning et ebaseaduslike muudatuste või rikkumiste, sealhulgas sihitud andmemürgitamise katsed, ennetamiseks rakendatakse automatiseeritud anomaaliate tuvastamise meetodeid. |   2   | D/V  |
| 1.2.4 | Kontrollige, et andmekogumi versioone jälgitakse, et võimaldada tagasipööramist.                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.2.5 | Kinnitage, et aegunud andmed kustutatakse või anonümiseeritakse turvaliselt vastavalt andmete säilitamise poliitikatele, regulatiivsetele nõuetele ning rünnaku pinna vähendamiseks.                                                                                                                                     |   2   | D/V  |

---

## C1.3 Esituse täielikkus ja õiglus

Tuva demograafilisi kallutatusi ja rakenda leevendavaid meetmeid, et mudeli vea määrad oleksid rühmade vahel õiglaselt jaotatud.

|   #   | Description                                                                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Kinnitage, et andmekogumid on analüüsitud esindusliku tasakaalustamatuse ja võimalike kallutuste suhtes seadustega kaitstud tunnuste (nt rass, sugu, vanus) ning muu eetiliselt tundliku teabe kohta, mis on seotud mudeli rakendusalaga (nt sotsiaal-majanduslik staatus, asukoht).                                                                  |   1   | D/V  |
| 1.3.2 | Kontrollige, et tuvastatud kallutatused oleksid leevendatud dokumenteeritud strateegiate abil, nagu andmete ümberkaalustamine, sihitud andmete suurendamine, algoritmilised kohandused (nt eeltöötlus-, töötlemis- ja järeltöötlustehnikad) või ümberkaalustamine, ning hinnatakse leevendamise mõju nii õiglusele kui ka üldisele mudeli jõudlusele. |   2   | D/V  |
| 1.3.3 | Kinnitage, et treeningujärgsed õiglusmõõdikud on hinnatud ja dokumenteeritud.                                                                                                                                                                                                                                                                         |   2   | D/V  |
| 1.3.4 | Kontrolli, kas elutsükli eelarvamuste haldamise poliitika määrab omanike ja läbivaatuse sageduse.                                                                                                                                                                                                                                                     |   3   | D/V  |

---

## C1.4 Treeningandmete märgistamise kvaliteet, terviklikkus ja turvalisus

Kaitske silte krüpteerimisega ja nõudke kriitiliste klasside puhul kaheetapilist ülevaatust.

|   #   | Description                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Veenduge, et märgistamise/annotatsiooni kvaliteeti tagatakse selgete juhiste, ülevaatajate ristkontrolli, konsensusmehhanismide (nt annotaatoritevahelise kokkuleppe jälgimine) ja määratletud protsesside abil lahkarvamuste lahendamiseks.                           |   2   | D/V  |
| 1.4.2 | Kinnitage, et krüptograafilised räsid või digitaalsed allkirjad on märgiste artefaktidele lisatud, tagamaks nende terviklikkust ja autentsust.                                                                                                                         |   2   | D/V  |
| 1.4.3 | Veenduge, et märgistamise liidesed ja platvormid rakendaksid tugevaid juurdepääsu kontrolle, hoiaksid kõigi märgistamistegevuste osas rikkumiskindlaid auditi logisid ning kaitseksid volitamata muudatuste eest.                                                      |   2   | D/V  |
| 1.4.4 | Veenduge, et ohutuse, turvalisuse või õigluslike aspektide jaoks kriitilised sildid (nt toksilise sisu või oluliste meditsiiniliste leidude tuvastamine) läbiksid kohustusliku sõltumatu kaheastmelise ülevaatuse või võrdselt tugeva kinnituse.                       |   3   | D/V  |
| 1.4.5 | Kontrollige, et tundlik teave (sealhulgas isikuandmed) tähistes, mis on juhuslikult või vältimatult olemas, oleks andmete minimeerimise põhimõtete kohaselt varjatud, pseudonümiseeritud, anonüümitud või krüpteeritud nii säilitamisel kui ka andmeedastusprotsessis. |   2   | D/V  |
| 1.4.6 | Kinnitage, et sildistusjuhised ja juhised on põhjalikud, versioonihalduses ning kolleegide poolt läbi vaadatud.                                                                                                                                                        |   2   | D/V  |
| 1.4.7 | Kinnitage, et andmeskeemid (sh siltide jaoks) on selgelt määratletud ja versioonihalduses.                                                                                                                                                                             |   2   | D/V  |
| 1.8.2 | Kontrollige, et väljastatud või rahvahulgapõhised märgistustöövood sisaldaksid tehnilisi/protseduurilisi kaitsemeetmeid andmete konfidentsiaalsuse, terviklikkuse, märgistuse kvaliteedi tagamiseks ning andmelekkete vältimiseks.                                     |   2   | D/V  |

---

## C1.5 Koolitusandmete kvaliteedi tagamine

Kombineeri automatiseeritud valideerimist, käsitsi juhuslikke kontrollimisi ja logitud parandusi, et tagada andmestiku usaldusväärsus.

|   #   | Description                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Kontrollige, et automatiseeritud testid tuvastaksid vormindusvead, nullväärtused ja siltide nihked igal andmete sissetoomisel või olulisel teisendusel.                                                                                                                           |   1   |  D   |
| 1.5.2 | Kontrollige, et nurjunud andmekogumid oleksid karantiinis koos auditeerimisteedega.                                                                                                                                                                                               |   1   | D/V  |
| 1.5.3 | Kontrollige, et domeeniekspertide käsitsi tehtavad valikulised kontrollid hõlmaksid statistiliselt tähenduslikku valimi (nt ≥1% või 1000 proovi, kumb iganes suurem, või vastavalt riskihinnangule), et tuvastada peeneid kvaliteediprobleeme, mida automatiseerimine ei tuvasta. |   2   |  V   |
| 1.5.4 | Kontrollige, et parandamise sammud oleksid lisatud päritolurekorditele.                                                                                                                                                                                                           |   2   | D/V  |
| 1.5.5 | Kontrollige, et kvaliteediväravad blokeerivad alamkvaliteediga andmekogud, kui erandeid ei ole heaks kiidetud.                                                                                                                                                                    |   2   | D/V  |

---

## C1.6 Andmepoisonamise tuvastamine

Rakendage statistilist anomaalia tuvastamist ja karantiinisüsteeme, et peatada vaenulikke sisestusi.

|   #   | Description                                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.6.1 | Veenduge, et anomaaliate tuvastamise meetodeid (nt statistilised meetodid, ebatüüpiliste andmepunktide tuvastamine, manustamise analüüs) rakendatakse treeningandmetele sisestamise ajal ja enne peamisi treeningprotsesse, et tuvastada võimalikke mürgitamisrünnakuid või tahtmatut andmete korruptsiooni. |   2   | D/V  |
| 1.6.2 | Kontrollige, et märgistatud näidised põhjustaksid enne treeningut käsitsi ülevaatuse.                                                                                                                                                                                                                        |   2   | D/V  |
| 1.6.3 | Kontrolli, et tulemused täiendaksid mudeli turvadokumenti ja annaksid infot jooksva ohuteabe jaoks.                                                                                                                                                                                                          |   2   |  V   |
| 1.6.4 | Kinnitage, et tuvastusloogikat uuendatakse uue ohuteabega.                                                                                                                                                                                                                                                   |   3   | D/V  |
| 1.6.5 | Kinnitage, et veebipõhised õppimisliinid jälgivad jaotuse nihkumist.                                                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.6 | Kontrollige, et spetsiifilised kaitsemeetmed tuntud andmepoisoning-rünnakute tüüpide (nt sildi pööramine, tagaukselüliti lisamine, mõjuka näite rünnakud) vastu oleksid arvestatud ja rakendatud süsteemi riskiprofiili ja andmeallikate põhjal.                                                             |   3   | D/V  |

---

## C1.7 Kasutajaandmete kustutamine ja nõusoleku jõustamine

Austa kustutamis- ja nõusoleku tagasivõtmise taotlusi kõigis andmekogudes, varukoopiatest ja tuletatud artefaktidest.

|   #   | Description                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Kinnitage, et kustutamise töövood puhastavad põhianalüüsi ja tuletatud andmeid ning hinnake mudeli mõju, ning et mõjutatud mudelite mõju hinnatakse ja vajadusel käsitletakse (nt uuesti koolitamise või ümberkalibreerimise kaudu).                                                     |   1   | D/V  |
| 1.7.2 | Veenduge, et oleks olemas mehhanismid kasutaja nõusoleku (ja selle tagasivõtmise) ulatuse ja staatuse jälgimiseks ja austamiseks treeningandmete kasutamisel ning et nõusolek oleks kinnitatud enne andmete kaasamist uutesse treeningprotsessidesse või olulistesse mudeliuuendustesse. |   2   |  D   |
| 1.7.3 | Kinnitage, et töövood testitakse igal aastal ja logitakse.                                                                                                                                                                                                                               |   2   |  V   |

---

## C1.8 Tarneahela turvalisus

Välistandmete pakkujate hindamine ja terviklikkuse kontrollimine autentitud, krüpteeritud kanalite kaudu.

|   #   | Description                                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Kinnitage, et kolmanda osapoole andmevarustajad, sealhulgas eelnevalt treenitud mudelite ja väliste andmekogumite pakkujad, läbivad turvalisuse, privaatsuse, eetilise hankimise ja andmekvaliteedi nõuetekohase kontrolli enne nende andmete või mudelite integreerimist.                            |   2   | D/V  |
| 1.8.2 | Kontrollige, et välised ülekanded kasutaksid TLS-i/autentimist ja terviklikkuse kontrolli.                                                                                                                                                                                                            |   1   |  D   |
| 1.8.3 | Kinnitage, et kõrge riskiga andmeallikad (nt avatud lähtekoodiga andmekogud teadmata päritoluga, kontrollimata tarnijad) läbivad enne tundlikes rakendustes kasutamist täiendava kontrolli, nagu liivakastis analüüs, põhjalikud kvaliteedi/eelarvamuste kontrollid ja sihitud mürgituse tuvastamine. |   2   | D/V  |
| 1.8.4 | Kinnitage, et kolmandate osapooltelt saadud eelnevalt koolitatud mudeleid hinnatakse enne täiendõpet või juurutamist sisseehitatud eelarvamuste, võimalike tagauksede, arhitektuuri terviklikkuse ning nende algupärase treeningandmete päritolu osas.                                                |   3   | D/V  |

---

## C1.9 Vaidlusnäidise tuvastamine

Rakenda treeningfaasis meetmeid, nagu vastandlik treening, et parandada mudeli vastupanuvõimet vastandlikele näidetele.

|   #   | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.9.1 | Kontrollige, et asjakohased kaitsemeetmed, nagu vaenuliku õppimise (kasutades genereeritud vaenulikke näiteid), andmete suurendamine muudetud sisenditega või robustsed optimeerimistehnikad, oleksid rakendatud ja häälestatud vastavate mudelite jaoks riskihinnangu alusel. |   3   | D/V  |
| 1.9.2 | Kontrollige, kas ründeõppe kasutamisel on ründandmete kogumite genereerimine, haldamine ja versioonihaldus dokumenteeritud ning kontrolli all.                                                                                                                                 |   2   | D/V  |
| 1.9.3 | Veenduge, et vastasekindluse koolituse mõju mudeli jõudlusele (nii puhaste kui ka vastaste sisendite suhtes) ning õiglusmõõdikutele oleks hinnatud, dokumenteeritud ja jälgitud.                                                                                               |   3   | D/V  |
| 1.9.4 | Kinnitage, et vaenulikku koolitust ja vastupidavust käsitlevad strateegiad vaadatakse perioodiliselt üle ja neid uuendatakse, et tulla toime arenevate vaenulike rünnete tehnikatega.                                                                                          |   3   | D/V  |

---

## C1.10 Andmete päritolu ja jälgitavus

Jälgige iga andmepunkti kogu teekonda allikast mudeli sisendini auditeeritavuse ja intsidentidele reageerimise jaoks.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Kontrollige, et iga andmepunkti päritolu, sealhulgas kõik teisendused, suurendused ja ühendamised, oleks dokumenteeritud ja taastatav. |   2   | D/V  |
| 1.10.2 | Kinnitage, et päritolukirjed on muutumatud, turvaliselt salvestatud ja ligipääsetavad auditite või uurimiste jaoks.                    |   2   | D/V  |
| 1.10.3 | Kinnitage, et päritolu jälgimine hõlmab nii toor- kui sünteetilist andmestikku.                                                        |   2   | D/V  |

---

## C1.11 Sünteetilise andmete haldamine

Tagage, et sünteetilisi andmeid haldatakse, märgistatakse ja hinnatakse riskide osas korrektselt.

|   #    | Description                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Kontrollige, et kogu sünteetiline andmestik oleks kogu protsessis selgelt märgistatud ja eristatav reaalsest andmestikust.                               |   2   | D/V  |
| 1.11.2 | Kontrollige, et sünteetilise andmete genereerimisprotsess, parameetrid ja kavandatud kasutus oleksid dokumenteeritud.                                    |   2   | D/V  |
| 1.11.3 | Veenduge, et sünteetiline andmestik oleks enne kasutamist treenimisel hinnatud kallutatus-, privaatsuse lekkimise ja representatsiooni probleemide osas. |   2   | D/V  |

---

## C1.12 Andmete Juurdepääsu Jälgimine ja Anomaaliate Tuvastamine

Jälgige ja andke teavet ebatavalise juurdepääsu kohta treeningandmetele, et tuvastada siseohtusid või andmete väljapääsu.

|   #    | Description                                                                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Kinnitage, et kogu ligipääs treeningandmetele logitakse, sealhulgas kasutaja, aeg ja tegevus.                                                                                      |   2   | D/V  |
| 1.12.2 | Kontrollige, et juurdepääsulogi ülevaatus toimuks regulaarselt, pöörates erilist tähelepanu ebatavalistele mustritele, nagu suured ekspordid või juurdepääs uutesse asukohtadesse. |   2   | D/V  |
| 1.12.3 | Kinnitage, et kahtlaste juurdepääsu sündmuste kohta genereeritakse teateid ja neid uuritakse viivitamatult.                                                                        |   2   | D/V  |

---

## C1.13 Andmete säilitamise ja aegumispoliitikad

Määra ja rakenda andmete säilitamise perioodid, et minimeerida tarbetut andmete säilitamist.

|   #    | Description                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Kinnitage, et kõigi treeningandmestike jaoks on määratletud selged säilitamisajad.                                     |   1   | D/V  |
| 1.13.2 | Kontrollige, et andmekogud aeguksid automaatselt, kustutataks või läbivaatamiseks kustutamiseks nende elutsükli lõpus. |   2   | D/V  |
| 1.13.3 | Kontrollige, et säilitamise ja kustutamise toimingud oleksid logitud ja auditeeritavad.                                |   2   | D/V  |

---

## C1.14 Reguleerimis- ja jurisdiktsiooniline vastavus

Tagage, et kõik treeningandmed vastavad kehtivatele seadustele ja määrustele.

|   #    | Description                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Kinnitage, et andmete asukoha ja piiriüleste edastuste nõuded on kõigi andmekogumite puhul tuvastatud ja täidetud.                |   2   | D/V  |
| 1.14.2 | Kinnitage, et andmete töötlemisel on tuvastatud ja käsitletud sektori spetsiifilisi regulatsioone (nt tervishoid, rahandus).      |   2   | D/V  |
| 1.14.3 | Kinnitage, et vastavus asjakohastele privaatsusseadustele (nt GDPR, CCPA) on dokumenteeritud ja seda vaadatakse regulaarselt üle. |   2   | D/V  |

---

## C1.15 Andmete vesimärgistus ja sõrmejälgede lisamine

Tuvastage volitamata kasutus või äratundmatu lekkimine omanikuõigusega või tundlikest andmetest.

|   #    | Description                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Kinnitage, et andmekogud või alamhulgad on võimalikul juhul veekindlaks märgistatud või sõrmejälgitud.                                                        |   3   | D/V  |
| 1.15.2 | Kinnitage, et vesimärgi-/sõrmejälje meetodid ei tekita kallutatust ega privaatsusriske.                                                                       |   3   | D/V  |
| 1.15.3 | Kontrollige, et perioodilisi kontrolle teostatakse selleks, et tuvastada volitamata kasutuskordade korduvkasutust või veeallikat sisaldava andmete lekkimist. |   3   | D/V  |

---

## C1.16 Andmesubjekti õiguste haldamine

Toeta andmesubjekti õigusi nagu juurdepääs, parandamine, piiramine ja vastuväide.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.16.1 | Kontrollige, et olemas on mehhanismid andmesubjekti taotlustele juurdepääsu, parandamise, piiramise või vastuväidete esitamiseks reageerimiseks. |   2   | D/V  |
| 1.16.2 | Kontrollige, et taotlused registreeritakse, jälgitakse ja täidetakse seadusjärgsetes tähtaegades.                                                |   2   | D/V  |
| 1.16.3 | Kinnitage, et andmesubjekti õiguste protsessid on regulaarselt testitud ja üle vaadatud nende efektiivsuse tagamiseks.                           |   2   | D/V  |

---

## C1.17 Andmestiku versiooni mõjuanalüüs

Hinnake andmekogumi muutuste mõju enne versioonide uuendamist või asendamist.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Kontrollige, kas enne andmekogumi versiooni värskendamist või asendamist tehakse mõjuhindamine, mis hõlmab mudeli jõudlust, õiglust ja vastavust. |   2   | D/V  |
| 1.17.2 | Kontrollige, et mõjuanalüüsi tulemused oleksid dokumenteeritud ja asjakohaste sidusrühmade poolt üle vaadatud.                                    |   2   | D/V  |
| 1.17.3 | Kontrollige, et oleks olemas tagasipööramise plaanid juhuks, kui uued versioonid toovad kaasa vastuvõetamatuid riske või tagasilööke.             |   2   | D/V  |

---

## C1.18 Andmete märgistamise tööjõu turvalisus

Tagada andmete märgistamises osalevate töötajate turvalisus ja terviklikkus.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Kinnitage, et kõik andmete märgendamises osalevad töötajad on taustakontrollitud ning koolitatud andmete turvalisuse ja privaatsuse alal. |   2   | D/V  |
| 1.18.2 | Kinnitage, et kõik märgendamisega tegelevad töötajad allkirjastavad konfidentsiaalsus- ja mitteavalikustamise lepingud.                   |   2   | D/V  |
| 1.18.3 | Kontrollige, kas annotatsiooniplatvormid rakendavad juurdepääsukontrolli ja jälgivad sisepõhiseid ohte.                                   |   2   | D/V  |

---

## Viited

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

