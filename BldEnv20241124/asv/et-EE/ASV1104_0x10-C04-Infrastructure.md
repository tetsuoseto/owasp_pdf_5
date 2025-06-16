# C4 infrastruktuuri, konfiguratsiooni ja juurutamise turvalisus

## Kontrolli eesmärk

Tehisintellekti infrastruktuur peab olema kaitstud privileegide tõstmise, tarneahela manipulatsiooni ja külgsuunalise liikumise eest turvalise konfigureerimise, tööaja isolatsiooni, usaldusväärsete juurutusprotsesside ja põhjaliku jälgimise kaudu. Ainult volitatud ja valideeritud infrastruktuuri komponendid ning konfiguratsioonid jõuavad kontrollitud protsesside kaudu tootmiskeskkonda, mis tagavad turvalisuse, terviklikkuse ja auditeeritavuse.

Põhiturvalisuse eesmärk: tootmisse jõuavad ainult krüptograafiliselt allkirjastatud, haavatavusvea skaneeringuga infrastruktuurikomponendid, mis läbivad automaatsete valideerimisliinide kaudu turvapoliitikate täitmise ja säilitavad muutumatud audiidijäljed.

---

## C4.1 Käituskeskkonna isoleerimine

Tõkestage konteineritest väljapääsemist ja õiguste eskaleerimist tuuma tasemel isolatsiooni primitive ja kohustuslike juurdepääsukontrollide abil.

|   #   | Description                                                                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Kontrollige, et kõik AI konteinerid eemaldaksid KÕIK Linuxi õigused, välja arvatud CAP_SETUID, CAP_SETGID ja turvapõhimõtetes selgesõnaliselt nõutud õigused.                                                                                         |   1   | D/V  |
| 4.1.2 | Kinnitage, et seccomp-profiilid blokeerivad kõik süsteemikõned peale eelnevalt heaks kiidetud lubade nimekirjade, rikkumiste korral lõpetatakse konteiner ja genereeritakse turvahoiatused.                                                           |   1   | D/V  |
| 4.1.3 | Kinnitage, et tehisintellekti töökoormused jooksevad ainult lugemisõigusega juurkataloogi failisüsteemidega, ajutiste andmete jaoks kasutatakse tmpfs-i ning püsivate andmete jaoks nimelisi köiteid, millel on rakendatud noexec-monteerimisvalikud. |   2   | D/V  |
| 4.1.4 | Kinnitage, et eBPF-põhine reaalajas jälgimine (nt Falco, Tetragon või nende ekvivalent) tuvastab õiguste eskalatsiooni katsed ning tapab rikkumisi sooritanud protsessid automaatselt vastavalt organisatsiooni reageerimisaja nõuetele.              |   2   | D/V  |
| 4.1.5 | Kinnitage, et kõrge riskiga tehisintellekti töökoormused käitatakse riistvaraliselt isoleeritud keskkondades (Intel TXT, AMD SVM või spetsiaalsetes bare-metal sõlmedes) koos attesteerimise kontrolliga.                                             |   3   | D/V  |

---

## C4.2 Turvalised koostamis- ja juurutusliinid

Tagage krüptograafiline terviklikkus ja tarneahela turvalisus korduvate ehituste ja allkirjastatud artefaktide kaudu.

|   #   | Description                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.2.1 | Kinnitage, et infrastruktuur-koodina skannitakse igal commitil tööriistadega (tfsec, Checkov või Terrascan), blokeerides CRITICAL või HIGH tasemega tõsiste leidude korral ühenduste tegemise.         |   1   | D/V  |
| 4.2.2 | Kinnitage, et konteineri ehitused on korduvad, tuues esile identsed SHA256 räsi väärtused kõigi ehituste vahel, ning genereerige SLSA taseme 3 päritolu tõendid, mis on allkirjastatud Sigstore'iga.   |   1   | D/V  |
| 4.2.3 | Kontrollige, et konteineripildid sisaldaksid CycloneDX või SPDX SBOM-e ja oleksid enne registrisse saatmist Cosigniga allkirjastatud; allkirjastamata pilte ei tohi juurutamisel vastu võtta.          |   2   | D/V  |
| 4.2.4 | Kontrollige, et CI/CD torujuhtmed kasutaksid OIDC-silte HashiCorp Vaultist, AWS IAM-rollidest või Azure’i hallatavast identiteedist, mille eluea pikkus ei ületa organisatsiooni turvapoliitika piire. |   2   | D/V  |
| 4.2.5 | Kinnitage, et Cosign allkirju ja SLSA päritolu kontrollitakse juurutamisprotsessi ajal enne konteineri käivitamist ning et kontrollivead põhjustavad juurutamise ebaõnnestumise.                       |   2   | D/V  |
| 4.2.6 | Kinnitage, et ehituskeskkonnad töötavad ajutistes konteinerites või virtuaalmasinates ilma püsiva salvestusruumita ning on võrgu poolest isoleeritud tootmis-VPC-dest.                                 |   2   | D/V  |

---

## C4.3 Võrgu turvalisus ja juurdepääsu kontroll

Rakenda nullusaldusvõrku vaikimisi keelavate poliitikate ja krüpteeritud suhtlusega.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.3.1 | Kinnitage, et Kubernetes NetworkPolicies või mõni selle ekvivalent rakendab vaikimisi keelamist sõlmpunktide sissetulevale/väljaminevale liiklusele ning lubab ainult selgesõnalikult määratud pordid (443, 8080 jne).               |   1   | D/V  |
| 4.3.2 | Kontrollige, et SSH (port 22), RDP (port 3389) ja pilve metaandmete lõpp-punktid (169.254.169.254) oleksid blokeeritud või nõuaksid sertifikaadil põhinevat autentimist.                                                             |   1   | D/V  |
| 4.3.3 | Kinnitage, et väljuv liiklus filtreeritakse HTTP/HTTPS-prokside (Squid, Istio või pilve NAT-väravate) kaudu domeenide lubanimekirjadega ning blokeeritud päringud logitakse.                                                         |   2   | D/V  |
| 4.3.4 | Kontrollige, et teenustevaheline suhtlus kasutab vastastikust TLS-i koos sertifikaatidega, mida vahetatakse vastavalt organisatsiooni poliitikale, ning et sertifikaatide valideerimine on kohustuslik (ilma skip-verify lippudeta). |   2   | D/V  |
| 4.3.5 | Kinnitage, et tehisintellekti (AI) infrastruktuur töötab eraldi VPC-des/VNettides ilma otsese internetiühenduseta ning suhtleb ainult NAT-väravate või bastionimajade kaudu.                                                         |   2   | D/V  |

---

## C4.4 Saladused ja krüptograafiliste võtmete haldamine

Kaitse mandaate riistvarapõhise salvestuse ja automatiseeritud rotatsiooniga nullusalduspõhise juurdepääsuga.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.4.1 | Kontrollige, et saladusi hoitakse HashiCorp Vaultis, AWS Secrets Manageris, Azure Key Vaultis või Google Secret Manageris, kasutades puhkeandmete krüpteerimiseks AES-256.                                         |   1   | D/V  |
| 4.4.2 | Kinnitage, et krüptograafilised võtmed on genereeritud FIPS 140-2 Level 2 HSM-ides (AWS CloudHSM, Azure Dedicated HSM) ning võtmete rotatsioon toimub vastavalt organisatsiooni krüptograafilisele poliitikale.    |   1   | D/V  |
| 4.4.3 | Kinnitage, et saladuste rotatsioon on automatiseeritud nullseisaku juurutamisega ning kohene rotatsioon käivitatakse personali muutuste või turvaintsidentide korral.                                              |   2   | D/V  |
| 4.4.4 | Kinnitage, et konteineripilte skannitakse tööriistadega (GitLeaks, TruffleHog või detect-secrets), mis blokeerivad ehitised, mis sisaldavad API-võtmeid, paroole või sertifikaate.                                 |   2   | D/V  |
| 4.4.5 | Kontrollige, et tootmise salajasele juurdepääsule nõutakse MFA-d riistvaratokenitega (YubiKey, FIDO2) ning see salvestatakse muutumatutesse auditi logidesse koos kasutaja identiteetide ja ajatemplitega.         |   2   | D/V  |
| 4.4.6 | Kontrollige, et saladused oleksid sisestatud Kubernetes'i saladuste kaudu, paigaldatud mahtudesse või algkäivituskonteineritesse ning veenduge, et saladusi ei kasutataks kunagi keskkonnamuutujates või piltides. |   2   | D/V  |

---

## C4.5 tehisintellekti töökoormuse liivakasti keskkond ja valideerimine

Isoleeri usaldamata tehisintellekti mudelid turvalistesse liivakastidesse koos põhjaliku käitumisanalüüsiga.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Kontrollige, et välised AI mudelid töötaksid gVisoris, microVM-des (näiteks Firecracker, CrossVM) või Docker konteinerites koos lipikutega --security-opt=no-new-privileges ja --read-only.        |   1   | D/V  |
| 4.5.2 | Kontrollige, et liivakasti keskkondadel ei oleks võrguühendust (--network=none) või oleks lubatud vaid localhosti juurdepääs ning kõik välised päringud oleksid blokeeritud iptables reeglitega.   |   1   | D/V  |
| 4.5.3 | Veenduge, et tehisintellekti mudeli valideerimine hõlmab automatiseeritud punase meeskonna testimist organisatsiooni poolt määratletud testi katvuse ja käitumusanalüüsiga tagaukse tuvastamiseks. |   2   | D/V  |
| 4.5.4 | Kinnitage, et enne AI mudeli tootmisse viimist on selle liivakasti tulemused krüptograafiliselt allkirjastatud volitatud turbetöötajate poolt ja salvestatud muutumatutesse auditi logidesse.      |   2   | D/V  |
| 4.5.5 | Kontrollige, et liivakasti keskkonnad hävitatakse ja taastatakse kuldsetest kujutistest iga hindamise vahel, tagades täieliku failisüsteemi ja mälu puhastuse.                                     |   2   | D/V  |

---

## C4.6 Taristu turvamonitooring

Pidevalt skaneerige ja jälgige infrastruktuuri automaatse probleemide lahenduse ning reaalajas hoiatusedega.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Kinnitage, et konteineripilte skannitakse vastavalt organisatsiooni ajakavale ning kriitilised haavatavused takistavad juurutamist vastavalt organisatsiooni riskitasemetele.                                        |   1   | D/V  |
| 4.6.2 | Kinnitage, et infrastruktuur vastab CIS-i standarditele või NIST 800-53 kontrollidele organisatsioonis määratletud nõuete tasemete ja ebaõnnestunud kontrollide automaatse parandamisega.                            |   1   | D/V  |
| 4.6.3 | Kontrollige, et KÕRGE raskusastmega haavatavused oleksid parandatud vastavalt organisatsiooni riskijuhtimise ajakavadele ja et aktiivselt ära kasutatavate CVE-de puhul oleksid kasutusel hädaolukorra protseduurid. |   2   | D/V  |
| 4.6.4 | Kontrolli, et turvahoiatused integreeruksid SIEM-platvormidega (näiteks Splunk, Elastic või Sentinel), kasutades CEF- või STIX/TAXII-formaate koos automatiseeritud rikastamisega.                                   |   2   |  V   |
| 4.6.5 | Kinnitage, et infrastruktuuri mõõdikud eksporditakse monitooringusüsteemidesse (Prometheus, DataDog) koos SLA armatuurlaudade ja juhtkonna aruandlusega.                                                             |   3   |  V   |
| 4.6.6 | Kinnitage, et konfiguratsiooni hälvet tuvastatakse tööriistadega (Chef InSpec, AWS Config) vastavalt organisatsiooni monitooringunõuetele koos automaatse tagasikerimisega volitamata muudatuste korral.             |   2   | D/V  |

---

## C4.7 tehisintellekti infrastruktuuri ressursihaldus

Tõkesta ressursi ammendumise rünnakuid ning tagage õiglane ressursside jaotamine kvantide ja jälgimise abil.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.7.1 | Kontrollige, et GPU/TPU kasutust jälgitakse ning et organisatsiooni määratud läviväärtustel käivitatakse hoiatused ning et automaatne skaleerimine või koormuse tasakaalustamine aktiveeritakse vastavalt mahuhalduse poliitikatele. |   1   | D/V  |
| 4.7.2 | Kinnitage, et tehisintellekti töökoormuse mõõdikud (järelduse latentsus, läbilaskevõime, veamäärad) kogutakse vastavalt organisatsiooni jälgimisnõuetele ja seostatakse infrastruktuuri kasutamisega.                                |   1   | D/V  |
| 4.7.3 | Kinnitage, et Kubernetes ResourceQuotas või nende ekvivalent piiravad individuaalseid töökoormusi vastavalt organisatsiooni ressursside eraldamise poliitikatele, kehtestades rangelt täituvad piirid.                               |   2   | D/V  |
| 4.7.4 | Kinnitage, et kulude jälgimine mõõdab kulutusi töökoormuse/üürniku põhiselt, kasutades hoiatusteateid organisatsiooni eelarvepiiride alusel ning automatiseeritud kontrollimehhanisme eelarve ületuste korral.                       |   2   |  V   |
| 4.7.5 | Kinnitage, et mahukavandamine kasutab ajaloolisi andmeid organisatsiooni määratletud prognoosiperioodidega ning automatiseeritud ressursipaigutust nõudlusmustrite põhjal.                                                           |   3   |  V   |
| 4.7.6 | Kinnitage, et ressursi ammendumine käivitab organisatsiooni reageerimisnõuetele vastavalt vooluringi katkestajad, sealhulgas võimsuspoliitikatel põhineva kiiruse piiramise ja töökoormuse isoleerimise.                             |   2   | D/V  |

---

## C4.8 Keskkondade eraldamise ja edastamise kontrollid

Rakenda rangeid keskkonna piire automatiseeritud edutamisbarjääride ja turvakontrolliga.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Kinnitage, et arendus-, testimis- ja tootmiskeskkonnad töötavad eraldi VPC-des/VNetides, millel puuduvad jagatud IAM-rollid, turvarühmad ja võrguga ühendus.                                                                                       |   1   | D/V  |
| 4.8.2 | Kontrollige, et keskkonna tõstmine nõuab organisatsiooniliselt määratud volitatud isikute kinnitust krüptograafiliste allkirjade ja muutumatute auditeerimisjälgede abil.                                                                          |   1   | D/V  |
| 4.8.3 | Kinnitage, et tootmiskeskkonnad blokeerivad SSH-juurdepääsu, keelavad silumisliidesed ja nõuavad muudatuse taotlusi vastavalt organisatsiooni etteteatamisnõuetele, välja arvatud hädaolukorrad.                                                   |   2   | D/V  |
| 4.8.4 | Kontrollige, et infrastruktuuri-koodi muudatused nõuaksid kaaslaste ülevaatust koos automatiseeritud testimise ja turvakontrolliga enne peaharusse ühendamist.                                                                                     |   2   | D/V  |
| 4.8.5 | Kontrolli, et mitteproduktsioonandmed on anonüümseks muudetud vastavalt organisatsiooni privaatsusnõuetele, sünteetilise andmete genereerimisele või täielikule andmete maskimisele koos isikut tuvastavate andmete (PII) eemaldamise kinnitusega. |   2   | D/V  |
| 4.8.6 | Kinnitage, et edutamisväravad sisaldavad automatiseeritud turvateste (SAST, DAST, konteinerite skaneerimine), mille puhul heakskiidu saamiseks ei tohi olla ühtegi KRIITILIST leidmist.                                                            |   2   | D/V  |

---

## C4.9 Infrastruktuuri varundamine ja taastamine

Tagage infrastruktuuri vastupidavus automatiseeritud varukoopiate, testitud taastemenetlustega ja katastroofide taastamise võimalustega.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Kinnitage, et infrastruktuuri konfiguratsioonid on varundatud vastavalt organisatsiooni varundusplaanidele geograafiliselt eraldatud piirkondadesse, rakendades 3-2-1 varundusstrateegiat.                  |   1   | D/V  |
| 4.9.2 | Kontrollige, et varusüsteemid töötaksid isoleeritud võrkudes eraldi mandaatide ja ransomware'i kaitseks õhukeeratud salvestusega.                                                                           |   2   | D/V  |
| 4.9.3 | Kinnitage, et taastamismeetodid on testitud ja valideeritud automatiseeritud testimise kaudu vastavalt organisatsiooni ajakavadele, kus RTO ja RPO eesmärgid vastavad organisatsiooni nõuetele.             |   2   |  V   |
| 4.9.4 | Kontrollige, kas katastroofitaastamine sisaldab tehisintellekti spetsiifilisi käsiraamatuid, mis hõlmavad mudeli kaalude taastamist, GPU klastri uuesti ülesehitamist ja teenuste sõltuvuste kaardistamist. |   3   |  V   |

---

## C4.10 Taristu vastavus ja haldus

Tagage regulatiivne vastavus pideva hindamise, dokumenteerimise ja automaatsete kontrollide kaudu.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Kinnitage, et infrastruktuuri nõuetele vastavust hinnatakse organisatsiooni ajakava alusel vastavalt SOC 2, ISO 27001 või FedRAMP kontrollidele, kasutades automatiseeritud tõendite kogumist. |   2   | D/V  |
| 4.10.2 | Kinnitage, et infrastruktuuri dokumentatsioon sisaldab võrgu skeeme, andmevoo kaarte ja ohumudeleid, mis on ajakohastatud vastavalt organisatsiooni muutuste juhtimise nõuetele.               |   2   |  V   |
| 4.10.3 | Kinnitage, et infrastruktuuri muudatused läbivad automaatse vastavushinnangu koos regulatiivsete kinnitustöövoogudega kõrge riskiga muudatuste puhul.                                          |   3   | D/V  |

---

## C4.11 tehisintellekti riistvara turvalisus

Turvalised AI-spetsiifilised riistvarakomponendid, sealhulgas GPU-d, TPU-d ja spetsiaalsed AI kiirendid.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Kinnitage, et tehisintellekti kiirendi püsivara (GPU BIOS, TPU püsivara) on kinnitatud krüptograafiliste allkirjadega ning uuendatakse vastavalt organisatsiooni plaasthaldusajakavadele.     |   2   | D/V  |
| 4.11.2 | Veenduge, et enne töökoormuse täitmist kinnitatakse tehisintellekti kiirendi terviklikkus riistvara attesteerimise kaudu, kasutades TPM 2.0, Intel TXT või AMD SVM.                           |   2   | D/V  |
| 4.11.3 | Kinnitage, et GPU mälu on töökoormuste vahel isoleeritud, kasutades SR-IOV-i, MIG-i (Multi-Instance GPU) või ekvivalentset riistvaralist partitsioneerimist koos mälupuhastusega tööde vahel. |   2   | D/V  |
| 4.11.4 | Kontrollige, kas tehisintellekti riistvara tarneahel sisaldab päritolu kinnitamist tootjate sertifikaatide ja kahjustuskindla pakendi valideerimisega.                                        |   3   |  V   |
| 4.11.5 | Kinnitage, et riistvaralised turbemoodulid (HSM-id) kaitsevad tehisintellekti mudelite kaalusid ja krüptograafilisi võtmeid FIPS 140-2 taseme 3 või Common Criteria EAL4+ sertifikaadiga.     |   3   | D/V  |

---

## C4.12 Äärmise ja jaotatud tehisintellekti infrastruktuur

Turvalised hajutatud tehisintellekti juurutused, sealhulgas servarvutus, föderatiivõpe ja mitmekohalised arhitektuurid.

|   #    | Description                                                                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Kinnitage, et serva tehisintellekti (edge AI) seadmed autentivad keskset infrastruktuuri omavahelise TLS-iga (mutual TLS) kasutades seadme tunnistusi, mis vahetatakse vastavalt organisatsiooni sertifikaadi halduspoliitikale. |   2   | D/V  |
| 4.12.2 | Veenduge, et servaseadmed rakendavad turvalist käivitust, kasutades kinnitatud allkirju ja tagasilükkamise kaitset, mis takistab püsivara halvendamise rünnakuid.                                                                |   2   | D/V  |
| 4.12.3 | Kinnitage, et hajutatud tehisintellekti koordineerimine kasutab Bütsantsi rikete taluvuse konsensusalgoritme koos osalejate valideerimise ja pahatahtlike sõlmede tuvastamisega.                                                 |   3   | D/V  |
| 4.12.4 | Kinnitage, et servast pilve suhtlus hõlmab ribalaiuse piirangut, andmete tihendamist ja võrguühenduseta töötamise võimekust turvalise kohaliku salvestusega.                                                                     |   3   | D/V  |

---

## C4.13 Mitme pilve ja hübriidse infrastruktuuri turvalisus

Turvake AI töökoormused mitme pilvepakkuja ja hübriidse pilve-siseriikliku kasutuselevõtu keskkondades.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Kontrollige, et mitme pilve AI juurutused kasutaksid pilvest sõltumatut identiteediföderatsiooni (OIDC, SAML) koos keskselt hallatavate poliitikatega kõigi teenusepakkujate vahel.                           |   2   | D/V  |
| 4.13.2 | Kinnitage, et pilveteenustevaheline andmeedastus kasutab lõpp-punktide krüptimist kliendi haldatud võtmetega ning andmete asukohapõhiseid kontrollimehhanisme, mida rakendatakse vastavalt jurisdiktsioonile. |   2   | D/V  |
| 4.13.3 | Veenduge, et hübriidpilve tehisintellekti töökoormused rakendavad järjepidevaid turvapoliitikaid nii kohapealsetes kui ka pilvekeskkondades, kasutades ühtset monitooringut ja häiresüsteemi.                 |   2   | D/V  |
| 4.13.4 | Veenduge, et pilvetarnija lukustumise vältimine hõlmab kaasaskantavat infrastruktuuri kui koodi, standardiseeritud API-sid ja andmete ekspordivõimalusi vorminduskonverteerimise tööriistadega.               |   3   |  V   |
| 4.13.5 | Kinnitage, et mitme pilve kulude optimeerimine hõlmab turvakontrolle, mis takistavad ressursside laialivalgumist ning volitamata andmeedastust pilvede vahel ja sellega kaasnevaid kulusid.                   |   3   |  V   |

---

## C4.14 Taristu automatiseerimine ja GitOpsi turvalisus

Turvalised infrastruktuuri automatiseerimise torujuhtmed ja GitOps töövood tehisintellekti infrastruktuuri haldamiseks.

|   #    | Description                                                                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Kinnitage, et GitOpsi hoidlad nõuavad allkirjastatud commit'e GPG võtmetega ja harude kaitse reegleid, mis takistavad otsepüüdlusi põhiharudele.                                                                                              |   2   | D/V  |
| 4.14.2 | Kinnitage, et infrastruktuuri automatiseerimine hõlmab kõrvalekallete tuvastamist koos automaatse parandus- ja tagasipöördumisfunktsioonidega, mis aktiveeritakse vastavalt organisatsiooni reageerimisnõuetele volitamata muudatuste korral. |   2   | D/V  |
| 4.14.3 | Kinnitage, et automatiseeritud infrastruktuuri juurutamine sisaldab turvapoliitika valideerimist, blokeerides juurutuse mittevastavatele konfiguratsioonidele.                                                                                |   2   | D/V  |
| 4.14.4 | Kinnitage, et infrastruktuuri automatiseerimise saladusi hallatakse väliste saladuste operaatorite (External Secrets Operator, Bank-Vaults) kaudu automaatse rotatsiooniga.                                                                   |   2   | D/V  |
| 4.14.5 | Kinnitage, et isetaastuv infrastruktuur hõlmab turvasündmuste korrelatsiooni koos automatiseeritud intsidentide reageerimise ja sidusrühmade teavitamise töövoogudega.                                                                        |   3   |  V   |

---

## C4.15 Kvantkriitilise infrastruktuuriturvalisuse tagamine

Valmistage tehisintellekti infrastruktuur ette kvantarvutuse ohtude vastu postkvantarvutuse krüptograafia ja kvantkaitsvate protokollide abil.

|   #    | Description                                                                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Kinnitage, et tehisintellekti infrastruktuur kasutab võtmevahetuseks ja digiallkirjadeks NIST-i poolt heaks kiidetud postkvantkrüptograafilisi algoritme (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+). |   3   | D/V  |
| 4.15.2 | Kinnitage, et kvantvõtme jagamise (QKD) süsteemid on rakendatud kõrge turvalisusega tehisintellekti kommunikatsiooniks, kasutades kvanditurvalisi võtmehalduspõhimõtteid.                                |   3   | D/V  |
| 4.15.3 | Kontrollige, et krüptograafilise paindlikkuse raamistikud võimaldavad kiiret üleminekut uutele post-kvantalgoritmidele, kasutades automatiseeritud sertifikaatide ja võtmete pööramist.                  |   3   | D/V  |
| 4.15.4 | Kontrollige, et kvantarvutuse ohuhindamine hindab tehisintellekti infrastruktuuri haavatavust kvantrünnakute eest, sisaldades dokumenteeritud migratsioonitimelineid ja riskihinnanguid.                 |   3   |  V   |
| 4.15.5 | Kinnitage, et hübriidklassiikal-kvantkrüptograafilised süsteemid pakuvad kvantülemineku perioodil sügavuskaitset koos jõudluse jälgimisega.                                                              |   3   | D/V  |

---

## C4.16 Konfidentsiaalne arvutus ja turvalised tsoonid

Kaitske tehisintellekti töökoormusi ja mudeli kaalusid riistvaral põhinevate usaldusväärsete täitmisruumide ja konfidentsiaalse arvutustehnoloogia abil.

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Kinnitage, et tundlikud tehisintellekti mudelid töötavad Intel SGX kloostrites, AMD SEV-SNP või ARM TrustZone’is krüpteeritud mäluga ja attesteerimise kontrolliga.                      |   3   | D/V  |
| 4.16.2 | Kinnitage, et konfidentsiaalsed konteinerid (Kata Containers, gVisor konfidentsiaalse arvutamisega) isoleerivad tehisintellekti töökoormused riistvaraga jõustatud mälu krüpteerimisega. |   3   | D/V  |
| 4.16.3 | Kinnitage, et kaugattesteerimine valideerib enklaavi terviklikkuse enne tehisintellekti mudelite laadimist, kasutades krüptograafilist tõendit täitmisvälja autentsuse kohta.            |   3   | D/V  |
| 4.16.4 | Kinnitage, et konfidentsiaalsed tehisintellekti inferentsiteenused takistavad mudeli väljapetmist krüpteeritud arvutuse abil, kasutades suletud mudelikaalusid ja kaitstud täitmist.     |   3   | D/V  |
| 4.16.5 | Kinnitage, et usaldusväärne täitmiskeskkonna orkestreerimine haldab turvalise alakeskkonna elutsüklit kaugkinnituse ja krüpteeritud sidekanalite abil.                                   |   3   | D/V  |
| 4.16.6 | Kinnitage, et turvaline mitmepoolne arvutus (SMPC) võimaldab koostööl põhinevat tehisintellekti koolitust ilma üksikute andmekogumite või mudeliparameetrite avalikustamiseta.           |   3   | D/V  |

---

## C4.17 Nullteadmiste infrastruktuur

Rakendage nullteadmist tõestamise süsteeme privaatsust kaitsvaks tehisintellekti kontrollimiseks ja autentimiseks ilma tundlikku teavet avaldamata.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Kinnitage, et nullteadmiste tõendid (ZK-SNARKid, ZK-STARKid) kontrollivad AI mudeli terviklikkust ja treeningu algallikat ilma mudeli kaalude või treeningandmete avalikustamiseta.           |   3   | D/V  |
| 4.17.2 | Kinnitage, et Null-Teadmine (ZK) autentimissüsteemid võimaldavad privaatsust säilitavat kasutajate kontrolli tehisintellekti teenuste puhul, ilma et avalikustataks isikut puudutavat teavet. |   3   | D/V  |
| 4.17.3 | Kinnitage, et privaatne kogumite lõikumise (PSI) protokollid võimaldavad turvalist andmete vastavust federatiivse tehisintellekti jaoks ilma üksikute andmekogude avalikustamiseta.           |   3   | D/V  |
| 4.17.4 | Kontrollige, et nullteadmusel põhinevad masinõppesüsteemid (ZKML) võimaldavad tõendatavaid tehisintellekti järeldusi koos krüptograafilise tõendiga õige arvutuse kohta.                      |   3   | D/V  |
| 4.17.5 | Kinnitage, et ZK-rollupid pakuvad skaleeritavat, privaatsust säilitavat tehisintellekti tehingute töötlemist, kasutades partiikinnitust ja vähendatud arvutuskoormust.                        |   3   | D/V  |

---

## C4.18 Tõrjet Tagav Kõrvalkanali Rünnakute Vastasus

Kaitske tehisintellekti infrastruktuuri ajaliste, võimsuse, elektromagnetiliste ja vahemälupõhiste kõrvalkanali rünnakute eest, mis võivad lekkida tundlikku teavet.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Kontrollige, et tehisintellekti järeldusaeg on normaliseeritud, kasutades konstantse aja algoritme ja täiendamist, et vältida ajastusel põhinevaid mudeli väljavõtmise rünnakuid. |   3   | D/V  |
| 4.18.2 | Kinnitage, et võimsuse analüüsi kaitse hõlmab müra süstimist, toitejuhtme filtreerimist ja juhuslikustatud täitmismustreid AI riistvara puhul.                                    |   3   | D/V  |
| 4.18.3 | Kinnitage, et vahemälu-põhine kõrvalkanali leevendus kasutab vahemälu jaotamist, juhuslikustamist ja tühjenduskäske teabe lekke vältimiseks.                                      |   3   | D/V  |
| 4.18.4 | Kinnitage, et elektromagnetlainete kahjustuste kaitse hõlmab varjestust, signaali filtreerimist ja juhuslikustatud töötlemist TEMPEST-tüüpi rünnakute vältimiseks.                |   3   | D/V  |
| 4.18.5 | Kinnitage, et mikroarhitektuuri kõrvalkanalite kaitsed hõlmavad spekulatiivse täitmise juhtimist ja mälu juurdepääsu mustri varjamist.                                            |   3   | D/V  |

---

## C4.19 Neuromorfne ja spetsialiseeritud tehisintellekti riistvara turvalisus

Turvalised uued tehisintellekti riistvaraarhitektuurid, sh neuronormilised kiibid, FPGA-d, kohandatud ASIC-id ja optilised arvutussüsteemid.

|   #    | Description                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.19.1 | Kinnitage, et neuromorfse kiibi turvalisus hõlmab impulssmustri krüptimist, sünaptilise kaalu kaitset ja riistvarapõhist õpireeglite valideerimist.                                                    |   3   | D/V  |
| 4.19.2 | Kinnitage, et FPGA-põhised tehisintellekti kiirendid rakendavad bitivoogude krüpteerimist, manipulatsioonivastaseid mehhanisme ja turvalist konfiguratsiooni laadimist koos autentitud värskendustega. |   3   | D/V  |
| 4.19.3 | Kinnitage, et kohandatud ASIC turvalisus sisaldab kiibisiseseid turvaprosessoreid, riistvaralist usaldusjuurt ja turvalist võtmete salvestust katkestuste tuvastamisega.                               |   3   | D/V  |
| 4.19.4 | Kinnitage, et optilised arvutussüsteemid rakendavad kvantturvalist optilist krüptimist, turvalist footonilist lülitamist ja kaitstud optilist signaalitöötlust.                                        |   3   | D/V  |
| 4.19.5 | Kinnitage, et hübriid analoogs-digitaalsete tehisintellekti kiipide hulka kuuluvad turvaline analoogarvutus, kaitstud kaalude salvestus ja autentitud analoog-digitaalmuundus.                         |   3   | D/V  |

---

## C4.20 Privaatsust Kaitsev Arvutusinfrastruktuur

Rakendage privaatsust säilitava arvutuse infrastruktuurikontrollid tundlike andmete kaitsmiseks tehisintellekti töötlemise ja analüüsi ajal.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Kontrollige, et homomorfne krüptimise infrastruktuur võimaldab krüpteeritud arvutusi tundlikel tehisintellekti töökoormustel, kasutades krüptograafilist terviklikkuse kontrolli ja jõudluse jälgimist. |   3   | D/V  |
| 4.20.2 | Kinnitage, et privaatse teabe päringusüsteemid võimaldavad andmebaasi päringuid ilma päringumustreid paljastamata ning tagavad juurdepääsumustrite krüptograafilise kaitse.                             |   3   | D/V  |
| 4.20.3 | Kinnitage, et turvalised mitmepoolse arvutuse protokollid võimaldavad privaatsust tagavat tehisintellekti järeldamist ilma üksikuid sisendeid või vahepealseid arvutusi avaldamata.                     |   3   | D/V  |
| 4.20.4 | Kontrollige, et privaatsust säilitav võtmehaldus hõlmab hajutatud võtmete genereerimist, läviväärtuse krüptograafiat ja riistvaraliselt toetatud kaitsega turvalist võtme pööramist.                    |   3   | D/V  |
| 4.20.5 | Kontrollige, et privaatsust säilitava arvutuse jõudlus oleks optimeeritud partiide, vahemällu salvestamise ja riistvarakiirenduse abil, säilitades samal ajal krüptograafilised turvalisuse garantiid.  |   3   | D/V  |

---

## C4.15 Agendi raamistikupiirde pilve integratsiooni turvalisus ja hübriidne juurutus

Pilvega integreeritud agendi raamistikude turvakontrollid hübriidse kohapealse/pilve arhitektuuriga.

|   #    | Description                                                                                                                          | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.15.1 | Kontrollige, et pilvepõhine salvestuse integratsioon kasutab otsast lõpuni krüptimist koos agenti poolt juhitava võtmekäsitlusega.   |   1   | D/V  |
| 4.15.2 | Kinnitage, et hübriidjuurutuse turvapiirid on selgelt määratletud krüpteeritud suhtluskanalitega.                                    |   2   | D/V  |
| 4.15.3 | Veenduge, et pilveressursside juurdepääs hõlmab nullusalduspõhist kontrolli koos pideva autentimisega.                               |   2   | D/V  |
| 4.15.4 | Kinnitage, et andmete asukohakohustusi rakendatakse salastatud hoiukohtade krüptograafilise tõendamise kaudu.                        |   3   | D/V  |
| 4.15.5 | Kontrollige, kas pilveteenuse pakkuja turva hindamised hõlmavad agendi-spetsiifilist ähvarduste modelleerimist ja riskide hindamist. |   3   | D/V  |

---

## Viited

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

