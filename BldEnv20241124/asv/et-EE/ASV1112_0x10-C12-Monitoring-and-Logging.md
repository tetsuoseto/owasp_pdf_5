# C12 Jälgimine, logimine ja anomaaliate tuvastamine

## Kontrolli Eesmärk

See jaotis sisaldab nõudeid reaalajas ja kohtuekspertiisi nähtavuse tagamiseks selle kohta, mida mudel ja teised tehisintellekti komponendid näevad, teevad ja tagastavad, et ohte oleks võimalik tuvastada, sorteerida ja neist õppida.

## C12.1 Päringute ja vastuste logimine

|   #    | Description                                                                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Kinnitage, et kõik kasutajapäringud ja mudeli vastused logitakse koos sobivate metaandmetega (nt ajatempli, kasutaja ID, sessiooni ID, mudeli versioon).                                                                          |   1   | D/V  |
| 12.1.2 | Kinnitage, et logid on talletatud turvalistesse, juurdepääsu kontrollitud andmekogudesse koos asjakohaste säilituspoliitikate ja varundusprotseduuridega.                                                                         |   1   | D/V  |
| 12.1.3 | Kontrollige, et logide salvestussüsteemid rakendavad andmete krüpteerimist nii puhkeolekus kui ka edastamisel, et kaitsta logides sisalduvat tundlikku teavet.                                                                    |   1   | D/V  |
| 12.1.4 | Kinnitage, et tundlikud andmed promptides ja väljundites peidetakse automaatselt või maskeeritakse enne logimist, kasutades konfigureeritavaid maskeerimisreegleid isikuandmete (PII), volituste ja konfidentsiaalse teabe jaoks. |   1   | D/V  |
| 12.1.5 | Kontrollige, et poliitikakujunduse otsused ja turvafiltri toimingud oleksid logitud piisava üksikasjaga, võimaldamaks sisu modereerimissüsteemide auditeerimist ja tõrkeotsingut.                                                 |   2   | D/V  |
| 12.1.6 | Kinnitage, et logi terviklikkus on kaitstud näiteks krüptograafiliste digitaalallkirjade või kirjutuskaitstud salvestuse kaudu.                                                                                                   |   2   | D/V  |

---

## C12.2 Kuritarvituse tuvastamine ja teavitamine

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Kinnitage, et süsteem tuvastab ja annab märku tuntud jailbreaki mustrite, käsu süstimise katsete ja vaenulikest sisenditest kasutades signatuuri-põhist tuvastust.                                      |   1   | D/V  |
| 12.2.2 | Kinnitage, et süsteem integreerub olemasolevate turvateabe ja sündmuste haldamise (SIEM) platvormidega, kasutades standardseid logifailide formaate ja protokolle.                                      |   1   | D/V  |
| 12.2.3 | Kontrollige, et rikastatud turvasündmused sisaldavad tehisintellektile iseloomulikke kontekste, nagu mudeli identifikaatorid, usaldusmäära väärtused ja turvafiltri otsused.                            |   2   | D/V  |
| 12.2.4 | Kinnitage, et käitumusliku anomaalia tuvastus avastab ebatavalisi vestlusmustreid, liigseid korduskatseid või süsteemseid uurimiskäitumisi.                                                             |   2   | D/V  |
| 12.2.5 | Kinnitage, et reaalajas hoiatusmehhanismid teavitavad turvameeskondi, kui tuvastatakse potentsiaalsed poliitikavigade rikkumised või ründe katsed.                                                      |   2   | D/V  |
| 12.2.6 | Kinnitage, et kohandatud reeglid sisaldavad AI-spetsiifiliste ohu mustrite tuvastamist, sealhulgas koordineeritud jailbreak-rünnakuid, prompt-süstimise kampaaniaid ja mudeli ekstraktsiooni rünnakuid. |   2   | D/V  |
| 12.2.7 | Kinnitage, et automatiseeritud intsidentide reageerimise töövood suudavad isoleerida kompromiteeritud mudeleid, blokeerida pahatahtlikke kasutajaid ja eskaleerida kriitilisi turvasündmusi.            |   3   | D/V  |

---

## C12.3 Mudeli triivimise tuvastamine

|   #    | Description                                                                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.3.1 | Kinnitage, et süsteem jälgib põhitegevusnäitajaid, nagu täpsus, usaldusväärsuse skoorid, latentsus ja veamäärad mudeliversioonide ning ajaperioodide lõikes.                         |   1   | D/V  |
| 12.3.2 | Kontrollige, et automatiseeritud häired käivituksid, kui jõudlusindikaatorid ületavad eelnevalt määratletud kahjustuse läved või erinevad oluliselt baasväärtustest.                 |   2   | D/V  |
| 12.3.3 | Kinnitage, et hallutsinatsiooni tuvastamise jälgijad tuvastavad ja märgistavad juhtumid, kus mudeli väljundites esineb faktuaalselt ebatäpset, vastuolulist või väljamõeldud teavet. |   2   | D/V  |

---

## C12.4 Jõudluse ja Käitumise Telemeetria

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Kontrollige, kas tegevusmõõdikud, sealhulgas päringu latentsus, tokeni tarbimine, mälu kasutus ja läbilaskevõime, kogutakse ja jälgitakse pidevalt. |   1   | D/V  |
| 12.4.2 | Kinnitage, et edu- ja ebaõnnestumismäärad jälgitakse koos veatüüpide ja nende juurpõhjuste kategoriseerimisega.                                     |   1   | D/V  |
| 12.4.3 | Kinnitage, et ressursikasutuse jälgimine hõlmab GPU/CPU kasutust, mälutarbimist ja salvestusruumi nõudeid ning teavitust künniste ületamisel.       |   2   | D/V  |

---

## C12.5 Tehisintellekti intsidentide reageerimise planeerimine ja teostamine

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Veenduge, et intsidentidele reageerimise plaanid käsitleksid spetsiaalselt tehisintellekti turvalisusega seotud sündmusi, sealhulgas mudeli kompromiteerimist, andmete mürgitamist ja vastandlikke rünnakuid. |   1   | D/V  |
| 12.5.2 | Kontrollige, et intsidentidele reageerimise meeskondadel oleks juurdepääs tehisintellekti spetsiifilistele kohtuekspertiisi tööriistadele ja teadmistele mudeli käitumise ja ründevektorite uurimiseks.       |   2   | D/V  |
| 12.5.3 | Kinnitage, et intsidenti-järgse analüüsi hulka kuuluvad mudeli ümberõppe kaalumised, turvafiltrite uuendused ja õppetundide integreerimine turvameetmetesse.                                                  |   3   | D/V  |

---

## C12.5 AI jõudluse halvenemise tuvastamine

Jälgi ja avasta AI mudeli jõudluse ja kvaliteedi halvenemist aja jooksul.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Veenduge, et mudeli täpsus, täpsusmäär, tagasikutsumine ja F1 skoorid oleksid pidevalt jälgitavad ja võrreldud algtasemete läviväärtustega. |   1   | D/V  |
| 12.5.2 | Kontrollige, et andmete nihke tuvastamise süsteem jälgib sisendi jaotuse muutusi, mis võivad mõjutada mudeli tulemuslikkust.                |   1   | D/V  |
| 12.5.3 | Kinnitage, et kontseptsiooni nihke tuvastamine avastab muutusi sisendite ja oodatavate väljundite vahelises seoses.                         |   2   | D/V  |
| 12.5.4 | Kontrollige, et jõudluse halvenemine käivitab automaatseid hoiatusi ja alustab mudeli ümberõppe või asendamise töövooge.                    |   2   | D/V  |
| 12.5.5 | Kinnitage, et degradeerumise põhjusanalüüs seostab jõudluse langusi andmete muutustega, infrastruktuuriprobleemidega või välisteguritega.   |   3   |  V   |

---

## C12.6 DAG visualiseerimine ja töövoo turvalisus

Kaitske töövoo visualiseerimissüsteeme teabe lekkimise ja manipuleerimisrünnakute eest.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Kinnitage, et DAG-i visualiseerimise andmed on puhastatud tundlikust teabest enne salvestamist või edastamist.                                                   |   1   | D/V  |
| 12.6.2 | Kinnitage, et töövoo visualiseerimise juurdepääsukontrollid tagavad, et ainult volitatud kasutajad saavad vaadata agendi otsustusprotsesse ja põhjenduste jälgi. |   1   | D/V  |
| 12.6.3 | Kinnitage, et DAG-andmete terviklikkust kaitstakse krüptograafiliste allkirjade ja muutmiskindlate salvestusmehhanismide kaudu.                                  |   2   | D/V  |
| 12.6.4 | Kontrolli, et töövoo visualiseerimise süsteemid rakendaksid sisendi valideerimist, et takistada süstimist rünnakuid valmistatud sõlme- või servandmete kaudu.    |   2   | D/V  |
| 12.6.5 | Kinnitage, et reaalajas DAG-i uuendused on kiiruspiiranguga ja valideeritud, et vältida teenuse katkestamise rünnakuid visualiseerimissüsteemidel.               |   3   | D/V  |

---

## C12.7 Proaktiivne turvakäitumise jälgimine

Turvaohtude tuvastamine ja ennetamine läbi proaktiivse agendi käitumise analüüsi.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Veenduge, et proaktiivsed agendi käitumised oleksid väärtuspõhiselt turvavaldid ja enne täitmist oleks integreeritud riskihindamine.           |   1   | D/V  |
| 12.7.2 | Kinnitage, et autonoomsed initsiatiivid hõlmavad turvakonteksti hindamist ja ohuolukorra analüüsi.                                             |   2   | D/V  |
| 12.7.3 | Kontrollige, et proaktiivseid käitumismustreid analüüsitakse võimalike turvaprobleemide ja soovimatute tagajärgede osas.                       |   2   | D/V  |
| 12.7.4 | Kinnitage, et turvakriitilised proaktiivsed tegevused nõuavad selgeid heakskiiduahelaid koos auditeerimisjälgedega.                            |   3   | D/V  |
| 12.7.5 | Kinnitage, et käitumusliku anomaaliate tuvastamine avastab proaktiivsete agentide mustritest kõrvalekaldeid, mis võivad viidata kompromissile. |   3   | D/V  |

---

## Viited

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

