# C4 infrastruktūros, konfigūracijos ir diegimo saugumas

## Valdymo tikslas

DI infrastruktūra turi būti sustiprinta prieš privilegijų eskalaciją, tiekimo grandinės manipuliacijas ir šoninį judėjimą naudojant saugią konfigūraciją, vykdymo izoliaciją, patikimus diegimo kanalus ir išsamų stebėjimą. Tik autorizuoti, patikrinti infrastruktūros komponentai ir konfigūracijos pasiekia gamybą per valdomus procesus, kurie užtikrina saugumą, vientisumą ir auditabilumą.

Pagrindinis saugumo tikslas: į gamybą pasiekia tik kriptografiškai pasirašytos, spragas patikrinusios infrastruktūros dalys per automatizuotas patikros linijas, kurios taiko saugumo politiką ir išlaiko nekeičiamą audito žurnalą.

---

## C4.1 Paleidimo aplinkos izoliacija

Užkirsti kelią konteinerių pabėgimams ir privilegijų eskalavimui naudojant branduolio lygio izoliacijos primityvus ir privalomuosius prieigos valdymus.

|   #   | Description                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Patikrinkite, ar visi DI konteineriai atmeta VISAS Linux galimybes, išskyrus CAP_SETUID, CAP_SETGID ir aiškiai reikalaujamas galimybes, dokumentuotas saugumo bazinėse linijose.                                                              |   1   | D/V  |
| 4.1.2 | Patikrinkite, ar seccomp profiliai blokuoja visas sistemos iškvietas, išskyrus tas, kurios yra iš anksto patvirtintose leidžiamųjų sąrašuose, o pažeidimams užbaigus konteinerį ir sukuriant saugumo įspėjimus.                               |   1   | D/V  |
| 4.1.3 | Patikrinkite, ar DI darbo apkrovos veikia su tik skaitymui skirtomis šakniniu failų sistema, tmpfs laikinuosius duomenis ir vardytomis apimtimis nuolatiniams duomenims, užtikrinant noexec montavimo parinkčių taikymą.                      |   2   | D/V  |
| 4.1.4 | Patikrinkite, ar eBPF pagrįstas vykdymo metu stebėjimas (Falco, Tetragon arba atitinkama sistema) aptinka privilegijų eskalavimo bandymus ir automatiškai nutraukia pažeidžiančius procesus pagal organizacijos reagavimo laiko reikalavimus. |   2   | D/V  |
| 4.1.5 | Patikrinkite, ar didelės rizikos DI užduotys vykdomos aparatinėje įrangoje izoliuotose aplinkose (Intel TXT, AMD SVM arba specializuotuose bare-metal mazguose) su patvirtinimo patikrinimu.                                                  |   3   | D/V  |

---

## C4.2 Saugios kūrimo ir diegimo grandinės

Užtikrinkite kriptografinį vientisumą ir tiekimo grandinės saugumą naudojant atkuriamus build'us ir pasirašytus artefaktus.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Patikrinkite, ar infrastruktūra kaip kodas (infrastructure-as-code) yra tikrinama naudodami įrankius (tfsec, Checkov arba Terrascan) kiekvieno komiteto metu, užkertant kelią susijungimams (merge) su kritinės arba aukštos svarbos problemomis. |   1   | D/V  |
| 4.2.2 | Patikrinkite, ar konteinerių kūrimas yra atkuriamas su identiškais SHA256 hešais tarp kūrimo ciklų, ir sukurkite SLSA 3 lygio kilmės patvirtinimus, pasirašytus naudojant Sigstore.                                                               |   1   | D/V  |
| 4.2.3 | Patikrinkite, ar konteinerių atvaizdai įtraukia CycloneDX arba SPDX SBOM ir yra pasirašyti su Cosign prieš įkeliant į registrą, o nepasižimančius atvaizdų nepaisyti diegimo metu.                                                                |   2   | D/V  |
| 4.2.4 | Patikrinkite, ar CI/CD vamzdynai naudoja OIDC žetonus iš HashiCorp Vault, AWS IAM vaidmenų arba Azure valdomos tapatybės, kurių galiojimo laikas neviršija organizacijos saugumo politikos apribojimų.                                            |   2   | D/V  |
| 4.2.5 | Patikrinkite, ar Cosign parašai ir SLSA kilmės duomenys yra tikrinami diegimo proceso metu prieš konteinerio paleidimą, ir kad tikrinimo klaidos sukelia diegimo nepavykimą.                                                                      |   2   | D/V  |
| 4.2.6 | Patikrinkite, ar kūrimo aplinkos veikia laikinuose konteineriuose arba virtualiose mašinose be nuolatinės saugyklos ir tinklo atskyrimo nuo gamybos VPC.                                                                                          |   2   | D/V  |

---

## C4.3 Tinklo saugumas ir prieigos kontrolė

Įgyvendinkite nulės pasitikėjimo tinklus su numatytosiomis draudimo politika ir užšifruotais ryšiais.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Patikrinkite, ar Kubernetes NetworkPolicies arba jų atitikmuo įgyvendina numatytąjį atmetimą įeinančiam/išeinančiam srautui su aiškiai nurodytomis leidžiamomis taisyklėmis reikalingiems prievadams (443, 8080 ir pan.). |   1   | D/V  |
| 4.3.2 | Patikrinkite, ar SSH (22 prievadas), RDP (3389 prievadas) ir debesų metaduomenų galiniai taškai (169.254.169.254) yra užblokuoti arba reikalauja autentifikacijos, pagrįstos sertifikatais.                               |   1   | D/V  |
| 4.3.3 | Patikrinkite, ar išeinantis srautas filtruojamas per HTTP/HTTPS proxy serverius (Squid, Istio arba debesų NAT vartus) naudojant domenų leidimų sąrašus ir ar užblokuoti užklausimai yra įrašomi į žurnalus.               |   2   | D/V  |
| 4.3.4 | Patikrinkite, ar tarpusavio paslaugų komunikacija naudoja abipusį TLS su sertifikatais, keičiama pagal organizacijos politiką, ir ar sertifikatų patikra yra privaloma (be skip-verify žymų).                             |   2   | D/V  |
| 4.3.5 | Patikrinkite, ar DI infrastruktūra veikia skirtose VPC/VNet tinkluose be tiesioginio interneto prieigos ir bendrauja tik per NAT vartus arba bastiono serverius.                                                          |   2   | D/V  |

---

## C4.4 Slaptažodžių ir kriptografinių raktų valdymas

Apsaugokite prisijungimo duomenis naudodami aparatine įranga pagrįstą saugyklą ir automatizuotą rotaciją su nulinio pasitikėjimo prieiga.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.4.1 | Patikrinkite, ar slapti duomenys saugomi HashiCorp Vault, AWS Secrets Manager, Azure Key Vault arba Google Secret Manager, naudojant AES-256 šifravimą laisvės metu.                                                     |   1   | D/V  |
| 4.4.2 | Patikrinkite, ar kriptografiniai raktai generuojami FIPS 140-2 2 lygio HSM įrenginiuose (AWS CloudHSM, Azure Dedicated HSM) su rakto kaitos procedūra, atitinkančia organizacijos kriptografinę politiką.                |   1   | D/V  |
| 4.4.3 | Patikrinkite, ar slaptųjų duomenų keitimas (rotation) yra automatizuotas su nuliniu veikimo sustojimo laiku ir kad sukartojimas įvyksta iš karto, kai yra personalo pokyčiai arba saugumo incidentai.                    |   2   | D/V  |
| 4.4.4 | Patikrinkite, ar konteinerių vaizdai yra skenuojami įrankiais (GitLeaks, TruffleHog arba detect-secrets), kurie blokuoja kūrimą, jei juose yra API raktai, slaptažodžiai ar sertifikatai.                                |   2   | D/V  |
| 4.4.5 | Patikrinkite, ar prieiga prie gamybos slaptojo rakto reikalauja MFA su aparatiniais raktais (YubiKey, FIDO2) ir ar tai yra įrašoma nepakeičiamuose audito žurnaluose su vartotojo tapatybėmis ir laiko žymėmis.          |   2   | D/V  |
| 4.4.6 | Patikrinkite, ar slaptažodžiai yra perduodami per Kubernetes slaptumo objektus, prijungtus tomus arba init konteinerius, ir užtikrinkite, kad slaptažodžiai niekada nebūtų įterpti į aplinkos kintamuosius arba vaizdus. |   2   | D/V  |

---

## C4.5 AI darbo krūvio aplinkos atskyrimas ir patikra

Izoliuokite nepatikimus DI modelius saugiose smėlio dėžėse su išsamia elgesio analize.

|   #   | Description                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Patikrinkite, ar išoriniai DI modeliai vykdomi gVisor, mikroVM (tokiose kaip Firecracker, CrossVM) arba Docker konteineriuose su --security-opt=no-new-privileges ir --read-only parametrais. |   1   | D/V  |
| 4.5.2 | Patikrinkite, ar smėlio dėžės aplinkos neturi tinklo ryšio (--network=none) arba turi prieigą tik prie localhost, o visi išoriniai užklausimai yra blokuojami iptables taisyklėmis.           |   1   | D/V  |
| 4.5.3 | Patikrinkite, ar DI modelio patvirtinimas apima automatizuotą raudonosios komandos testavimą su organizacijos apibrėžtu testavimo aprėptimi ir elgesio analize užpakalinių durų aptikimui.    |   2   | D/V  |
| 4.5.4 | Patikrinkite, ar prieš diegiant AI modelį į gamybą, jo smėlio dėžės rezultatai yra kriptografiškai pasirašyti įgaliotų saugumo darbuotojų ir saugomi nekeičiamuose audito įrašuose.           |   2   | D/V  |
| 4.5.5 | Patikrinkite, ar smėlio dėžės aplinkos yra sunaikinamos ir atkuriamos iš aukso atvaizdų tarp vertinimų, atliekant visišką failų sistemos ir atminties valymą.                                 |   2   | D/V  |

---

## C4.6 Infrastruktūros saugumo stebėjimas

Nuolat skenuokite ir stebėkite infrastruktūrą naudodami automatizuotą taisymą ir realaus laiko įspėjimus.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.6.1 | Patikrinkite, ar konteinerių atvaizdai yra skenuojami pagal organizacijos tvarkaraščius, o DIEGTINI pažeidžiamumai blokuoja diegimą remiantis organizacijos rizikos slenkstais.                              |   1   | D/V  |
| 4.6.2 | Patikrinkite, ar infrastruktūra atitinka CIS Standartus arba NIST 800-53 kontrolinius punktus pagal organizacijos nustatytus atitikties slenksčius ir automatinį neatitikimų taisymą.                        |   1   | D/V  |
| 4.6.3 | Patikrinkite, ar AUKŠTO lygio pažeidžiamumai yra ištaisyti pagal organizacijos rizikos valdymo tvarkaraščius, taikant neatidėliotinas procedūras aktyviai išnaudojamiems CVE.                                |   2   | D/V  |
| 4.6.4 | Patikrinkite, ar saugumo įspėjimai integruojami su SIEM platformomis (Splunk, Elastic arba Sentinel), naudojant CEF arba STIX/TAXII formatus su automatiniu papildymu.                                       |   2   |  V   |
| 4.6.5 | Patikrinkite, ar infrastruktūros metrikos eksportuojamos į monitoringo sistemas (Prometheus, DataDog) su SLA informacijos suvestinėmis ir vadovybės ataskaitomis.                                            |   3   |  V   |
| 4.6.6 | Patikrinkite, ar konfigūracijos nukrypimų aptikimas vykdomas naudojant įrankius (Chef InSpec, AWS Config) pagal organizacijos stebėjimo reikalavimus, su automatinio neleistinų pakeitimų atkūrimo funkcija. |   2   | D/V  |

---

## C4.7 Dirbtinio intelekto infrastruktūros išteklių valdymas

Užkirsti kelią išteklių išeikvojimo atakoms ir užtikrinti teisingą išteklių paskirstymą per kvotas ir stebėjimą.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Patikrinkite, ar GPU/TPU naudojimas yra stebimas, o perspėjimai suaktyvinami organizacijos nustatytose ribose, taip pat ar automatinis skalavimas arba apkrovos balansavimas aktyvuojami pagal talpos valdymo politiką. |   1   | D/V  |
| 4.7.2 | Patikrinkite, ar AI darbo krūvio metrika (inference delsos laikas, pralaidumas, klaidų rodikliai) renkama pagal organizacijos stebėjimo reikalavimus ir koreliuojama su infrastruktūros naudojimu.                      |   1   | D/V  |
| 4.7.3 | Patikrinkite, ar Kubernetes ResourceQuotas arba atitinkami ribojimai apriboja atskirus darbo krūvius pagal organizacijos išteklių paskirstymo politiką, taikant griežtas ribas.                                         |   2   | D/V  |
| 4.7.4 | Patikrinkite, ar išlaidų stebėjimas seka išlaidas pagal darbo krūvį/nuomininką, su įspėjimais, pagrįstais organizacijos biudžeto ribomis, ir automatizuotais valdikliais biudžeto viršijimams.                          |   2   |  V   |
| 4.7.5 | Patikrinkite, ar talpos planavimas naudoja istorinę informaciją su organizacijos apibrėžtais prognozavimo laikotarpiais ir automatizuotą išteklių teikimą pagal paklausos modelius.                                     |   3   |  V   |
| 4.7.6 | Patikrinkite, ar išteklių išeikvojimas sukelia grandinės pertraukiklius pagal organizacijos atsako reikalavimus, įskaitant greičio ribojimą pagal pajėgumų politiką ir darbo apkrovos izoliaciją.                       |   2   | D/V  |

---

## C4.8 Aplinkos atskyrimo ir taisyklės dėl perkėlimo kontrolės

Užtikrinkite griežtas aplinkos ribas naudodami automatinius skatinimo vartus ir saugumo patvirtinimą.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.8.1 | Patikrinkite, ar kūrimo/testavimo/produkcinės aplinkos veikia atskiruose VPC/VNet tinkluose, neturintys bendrų IAM vaidmenų, saugos grupių ar tinklo ryšio.                                                                    |   1   | D/V  |
| 4.8.2 | Patikrinkite, ar aplinkos perėjimas reikalauja organizacijos nustatytų įgaliotų asmenų patvirtinimo su kriptografiniais parašais ir nepakeičiamais audito įrašais.                                                             |   1   | D/V  |
| 4.8.3 | Patikrinkite, ar gamybos aplinkose užblokuotas SSH prieigos, išjungti derinimo (debug) galiniai taškai ir ar reikalingi pokyčių prašymai su organizaciniu išankstiniu pranešimu, išskyrus avarinius atvejus.                   |   2   | D/V  |
| 4.8.4 | Patikrinkite, ar infrastruktūros kaip kodo pakeitimai reikalauja bendraautorių peržiūros, automatizuoto testavimo ir saugumo nuskaitymo prieš sujungiant į pagrindinę šaką.                                                    |   2   | D/V  |
| 4.8.5 | Patikrinkite, ar neprodukciniai duomenys yra anonimizuoti pagal organizacijos privatumo reikalavimus, sintezinių duomenų generavimą arba visišką duomenų maskavimą su asmeninės identifikacijos informacijos (PII) pašalinimu. |   2   | D/V  |
| 4.8.6 | Patikrinkite, ar perėjimo vartai apima automatinius saugumo testus (SAST, DAST, konteinerio skenavimą), kuriems patvirtinimui reikalingas nulinis KRITIŠKŲ radinių skaičius.                                                   |   2   | D/V  |

---

## C4.9 Infrastruktūros atsarginė kopija ir atkūrimas

Užtikrinkite infrastruktūros atsparumą naudodami automatizuotas atsargines kopijas, patikrintas atkūrimo procedūras ir nelaimių atkūrimo galimybes.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Patikrinkite, ar infrastruktūros konfigūracijos yra atsarginės kopijos, atliekamos pagal organizacijos atsarginių kopijų grafikus į geografiškai atskirtas vietoves, įgyvendinant 3-2-1 atsarginių kopijų strategiją. |   1   | D/V  |
| 4.9.2 | Patikrinkite, ar atsarginių kopijų sistemos veikia izoliuotuose tinkluose, naudojant atskirus prieigos duomenis ir oro tarpo saugyklą apsaugai nuo išpirkos programų.                                                 |   2   | D/V  |
| 4.9.3 | Patikrinkite, ar atkūrimo procedūros yra išbandomos ir patvirtinamos automatizuotų testų pagalba pagal organizacijos tvarkaraščius, atitinkančius RTO ir RPO tikslus bei organizacijos reikalavimus.                  |   2   |  V   |
| 4.9.4 | Patikrinkite, ar nelaimių atsako plane yra AI specifiniai veiksmų planai su modelio svorių atkūrimu, GPU klasterio atstatymu ir paslaugų priklausomybių žemėlapiu.                                                    |   3   |  V   |

---

## C4.10 Infrastrukturų atitiktis ir valdymas

Užtikrinkite atitiktį teisės aktams nuolat vertindami, dokumentuodami ir naudodami automatizuotas kontrolės priemones.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Patikrinkite, ar infrastruktūros atitiktis vertinama pagal organizacijos grafikus, atsižvelgiant į SOC 2, ISO 27001 arba FedRAMP kontrolės priemones, naudojant automatizuotą įrodymų rinkimą. |   2   | D/V  |
| 4.10.2 | Patikrinkite, ar infrastruktūros dokumentacijoje yra tinklo diagramos, duomenų srauto žemėlapiai ir grėsmių modeliai, atnaujinti pagal organizacijos pokyčių valdymo reikalavimus.             |   2   |  V   |
| 4.10.3 | Patikrinkite, ar infrastruktūros pakeitimai pereina automatizuotą atitikties poveikio įvertinimą su reguliavimo patvirtinimo darbo eiga aukštos rizikos modifikacijoms.                        |   3   | D/V  |

---

## C4.11 DI aparatūros saugumas

Užtikrinkite saugią AI specifinių aparatūros komponentų, įskaitant GPU, TPU ir specializuotų AI akceleratorių, apsaugą.

|   #    | Description                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Patikrinkite, ar AI spartintuvo įdiegimo programinė įranga (GPU BIOS, TPU įdiegimo programinė įranga) yra patikrinta naudojant kriptografinius parašus ir atnaujinama pagal organizacijos pataisų valdymo grafikus. |   2   | D/V  |
| 4.11.2 | Patikrinkite, ar prieš darbo krūvio vykdymą AI pagreičio įrenginio vientisumas yra patvirtinamas aparatinės įrangos atestacija naudojant TPM 2.0, Intel TXT arba AMD SVM.                                           |   2   | D/V  |
| 4.11.3 | Patikrinkite, ar GPU atmintis yra izoluota tarp darbo krūvių naudojant SR-IOV, MIG (dauginis GPU atskyrimas) arba lygiavertį aparatinės įrangos suskirstymą su atminties sanitarizacija tarp užduočių.              |   2   | D/V  |
| 4.11.4 | Patikrinkite, ar AI aparatūros tiekimo grandinė apima kilmės patvirtinimą su gamintojo sertifikatais ir įrodymus apie pakuotės pažeidimus.                                                                          |   3   |  V   |
| 4.11.5 | Patikrinkite, ar aparatinės saugos moduliai (HSM) saugo DI modelio svorius ir kriptografinius raktus, turėdami FIPS 140-2 3 lygio arba Common Criteria EAL4+ sertifikatus.                                          |   3   | D/V  |

---

## C4.12 Kraštinė ir paskirstytoji dirbtinio intelekto infrastruktūra

Saugūs paskirstyti DI diegimai, įskaitant krašto skaičiavimą, federuotą mokymąsi ir daugiavidurines architektūras.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Patikrinkite, ar krašto AI įrenginiai autentifikuojasi prie centrinės infrastruktūros naudodami abipusį TLS su įrenginių sertifikatais, keičiami pagal organizacijos sertifikatų valdymo politiką. |   2   | D/V  |
| 4.12.2 | Patikrinkite, ar krašto įrenginiai įgyvendina saugų paleidimą su patikrintomis parašais ir atgalinio perkėlimo apsauga, užkertančia kelią programinės įrangos versijos seninimo atakoms.           |   2   | D/V  |
| 4.12.3 | Patikrinkite, ar paskirstytasis DI koordinavimas naudoja bizantinio gedimų toleravimo konsensuso algoritmus su dalyvių patvirtinimu ir piktybiškų mazgų aptikimu.                                  |   3   | D/V  |
| 4.12.4 | Patikrinkite, ar krašto ir debesies ryšys apima pralaidumo ribojimą, duomenų suspaudimą ir neprisijungus veikimo galimybes su saugiu vietiniu saugojimu.                                           |   3   | D/V  |

---

## C4.13 Daugia debesų ir hibridinės infrastruktūros saugumas

Užtikrinkite saugų AI darbo krūvių vykdymą keliuose debesų paslaugų teikėjuose ir hibridinėse debesų bei vietinėse aplinkose.

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Patikrinkite, ar daugialypės debesijos AI diegimai naudoja debesijoms nepriklausomą tapatybės federaciją (OIDC, SAML) su centralizuotu politikos valdymu tarp paslaugų teikėjų.                         |   2   | D/V  |
| 4.13.2 | Patikrinkite, ar kryžminis duomenų perdavimas debesyse naudoja galutinį užšifravimą su kliento valdomais raktas ir ar duomenų buvimo vietos valdymas yra užtikrinamas pagal jurisdikciją.               |   2   | D/V  |
| 4.13.3 | Patikrinkite, ar hibridinės debesijos DI užduotys įgyvendina nuoseklias saugumo politikos priemones tiek vietiniuose, tiek debesijos aplinkose, naudojant vieningą stebėjimą ir perspėjimų sistemą.     |   2   | D/V  |
| 4.13.4 | Patvirtinkite, kad debesų paslaugų tiekėjo priklausomybės prevencija apima nešiojamą infrastruktūrą kaip kodą, standartizuotus API ir duomenų eksportavimo galimybes su formato konvertavimo įrankiais. |   3   |  V   |
| 4.13.5 | Patikrinkite, ar daugiabantės debesijos sąnaudų optimizavimas apima saugumo kontrolę, užkertančią kelią resursų išplitimui ir neautorizuotoms tarp debesų duomenų perdavimo išlaidoms.                  |   3   |  V   |

---

## C4.14 Infrastruktūros automatizavimas ir GitOps saugumas

Saugios infrastruktūros automatizavimo vamzdynai ir GitOps darbo eiga AI infrastruktūros valdymui.

|   #    | Description                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Patikrinkite, ar GitOps saugyklos reikalauja pasirašytų įsipareigojimų naudojant GPG raktus ir ar yra nustatytos šakų apsaugos taisyklės, draudžiančios tiesioginius įkėlimus į pagrindines šakas.                           |   2   | D/V  |
| 4.14.2 | Patikrinkite, ar infrastruktūros automatizavime yra įtraukta nukrypimų aptikimas su automatinio taisymo ir grąžinimo galimybėmis, kurios aktyvuojamos pagal organizacijos reagavimo reikalavimus neautorizuotiems pokyčiams. |   2   | D/V  |
| 4.14.3 | Patikrinkite, ar automatizuotas infrastruktūros diegimas apima saugumo politikos patvirtinimą su diegimo blokavimu neatitinkančioms konfigūracijoms.                                                                         |   2   | D/V  |
| 4.14.4 | Patikrinkite, ar infrastruktūros automatizavimo slaptieji duomenys valdomi per išorinius slaptųjų duomenų operatorius (External Secrets Operator, Bank-Vaults) su automatinio sukinėjimo funkcija.                           |   2   | D/V  |
| 4.14.5 | Patikrinkite, ar savęs taisanti infrastruktūra apima saugumo įvykių koreliaciją su automatizuotu incidentų reagavimo ir suinteresuotųjų šalių informavimo darbo eigomis.                                                     |   3   |  V   |

---

## C4.15 Kvantinę atsparią infrastruktūros saugą

Paruoškite DI infrastruktūrą kvantinių kompiuterių grėsmėms valdant pasitelkiant po-kvantinę kriptografiją ir kvantui atsparius protokolus.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Patikrinkite, ar AI infrastruktūra įgyvendina NIST patvirtintus postkvantininius kriptografinius algoritmus (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) raktų mainams ir skaitmeniniams parašams. |   3   | D/V  |
| 4.15.2 | Patikrinkite, ar kvantiniai raktų paskirstymo (QKD) sistemos įdiegtos aukštos saugos DI komunikacijoms su kvantiniu saugiu raktų valdymo protokolais.                                                |   3   | D/V  |
| 4.15.3 | Patikrinkite, ar kriptografinės lankstumo sistemos leidžia greitai pereiti prie naujų postkvantinių algoritmų, automatizuotai keisdamos sertifikatus ir raktus.                                      |   3   | D/V  |
| 4.15.4 | Patikrinkite, ar kvantiniai grėsmių modeliavimai įvertina DI infrastruktūros pažeidžiamumą kvantinėms atakoms, pateikiant dokumentuotus migracijos grafikus ir rizikos vertinimus.                   |   3   |  V   |
| 4.15.5 | Patikrinkite, ar hibridinės klasikinės-kvantinės kriptografinės sistemos užtikrina gilesnį saugumo sluoksniavimą kvantinės perėjimo laikotarpiu kartu su veiklos stebėsena.                          |   3   | D/V  |

---

## C4.16 Konfidencialus skaičiavimas ir saugios aplinkos

Apsaugokite DI darbo krūvius ir modelio svorius naudodami aparatūrinei įrangai skirtas patikimas vykdymo aplinkas ir konfidencialaus skaičiavimo technologijas.

|   #    | Description                                                                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Patikrinkite, ar jautrūs DI modeliai vykdomi Intel SGX aplinkose, AMD SEV-SNP arba ARM TrustZone su šifruota atmintimi ir tapatybės patvirtinimu.                                               |   3   | D/V  |
| 4.16.2 | Patikrinkite, ar konfidencialios talpyklos (Kata Containers, gVisor su konfidencialiu apdorojimu) izoliuoja dirbtinio intelekto užduotis, naudodamos aparatūros užtikrintą atminties šifravimą. |   3   | D/V  |
| 4.16.3 | Patikrinkite, ar nuotolinis patvirtinimas tikrina užtvaro vientisumą prieš įkeliant DI modelius, naudojant kriptografinį vykdymo aplinkos autentiškumo įrodymą.                                 |   3   | D/V  |
| 4.16.4 | Patikrinkite, ar konfidencialios DI spėjimo paslaugos užkerta kelią modelio išgavimui naudojant užšifruotą skaičiavimą su užantspauduotais modelio svoriais ir apsaugotu vykdymu.               |   3   | D/V  |
| 4.16.5 | Patikrinkite, ar patikimos vykdymo aplinkos organizavimas valdo saugios zonos gyvavimo ciklą su nuotoline atestacija ir užšifruotomis komunikacijos kanalais.                                   |   3   | D/V  |
| 4.16.6 | Patikrinkite, ar saugus kelių šalių skaičiavimas (SMPC) leidžia bendradarbiauti AI mokyme neskelbiant atskirų duomenų rinkinių ar modelio parametrų.                                            |   3   | D/V  |

---

## C4.17 Nulinio žinojimo infrastruktūra

Įgyvendinkite nulio žinių įrodymo sistemas privatumą saugančiam DI patvirtinimui ir autentifikavimui, neišduodant jautrios informacijos.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Patikrinkite, ar nulinės žinios įrodymai (ZK-SNARK, ZK-STARK) patvirtina DI modelio vientisumą ir mokymo kilmę neskelbiant modelio svorių ar mokymo duomenų.                  |   3   | D/V  |
| 4.17.2 | Patikrinkite, ar ZK pagrįstos autentifikavimo sistemos leidžia vykdyti vartotojų tikrinimą, saugant privatumą AI paslaugoms, neskelbiant su tapatybe susijusios informacijos. |   3   | D/V  |
| 4.17.3 | Patikrinkite, ar privačios sankirtos rinkinių (PSI) protokolai užtikrina saugų duomenų atitikimą federuotam dirbtiniam intelektui neatskleisdami atskirų duomenų rinkinių.    |   3   | D/V  |
| 4.17.4 | Patikrinkite, ar nulio žinių mašininio mokymosi (ZKML) sistemos leidžia patikrinamus DI spėjimus su kriptografiniu teisingo skaičiavimo įrodymu.                              |   3   | D/V  |
| 4.17.5 | Patikrinkite, ar ZK-rollup’ai užtikrina mastelio keičiamą, privatumo saugančią AI transakcijų apdorojimą su partijos patikrinimu ir sumažinta skaičiavimo našta.              |   3   | D/V  |

---

## C4.18 Šoninio kanalo atakų prevencija

Apsaugokite DI infrastruktūrą nuo laiko, energijos, elektromagnetinių ir talpyklos pagrindu veikiančių šoninių kanalų atakų, kurios gali nutekinti jautrią informaciją.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Patikrinkite, ar AI išvados laikas yra normalizuojamas naudojant pastovaus laiko algoritmus ir papildymą, siekiant užkirsti kelią atakoms, pagrįstoms laikų analize modelio iš gavimo.            |   3   | D/V  |
| 4.18.2 | Patikrinkite, ar galios analizės apsauga apima triukšmo įpurškimą, maitinimo linijos filtravimą ir atsitiktinių vykdymo šablonų taikymą AI aparatūroje.                                           |   3   | D/V  |
| 4.18.3 | Patikrinkite, ar cache pagrįstos šoninės kanalo atakos mažinimo priemonės naudoja talpyklos dalijimą, atsitiktinimą ir išvalymo instrukcijas, kad būtų užkirstas kelias informacijos nutekėjimui. |   3   | D/V  |
| 4.18.4 | Patikrinkite, ar elektromagnetinių sklidimų apsauga apima ekranavimą, signalo filtravimą ir atsitiktinį apdorojimą, siekiant užkirsti kelią TEMPEST tipo atakoms.                                 |   3   | D/V  |
| 4.18.5 | Patikrinkite, ar mikroschemų šoniniai kanalai apima spekuliatyviosios vykdymo kontrolę ir atminties prieigos modelio užmaskavimą.                                                                 |   3   | D/V  |

---

## C4.19 Neuromorfinės ir specializuotos DI aparatūros saugumas

Užtikrinkite saugią naujų dirbtinio intelekto aparatūros architektūrą, įskaitant neuromorfinius lustus, FPGA, specializuotus ASIC ir optines skaičiavimo sistemas.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Patikrinkite, ar neuromorfinio mikroschemos saugumas apima impulsų modelių šifravimą, sinapsinių svorių apsaugą ir aparatine įranga pagrįstą mokymosi taisyklių tikrinimą.                         |   3   | D/V  |
| 4.19.2 | Patikrinkite, ar FPGA pagrindu sukurti AI pagreitintuvai įgyvendina bitų srauto šifravimą, apsaugos nuo pažeidimų mechanizmus ir saugų konfigūracijos pakrovimą su autentifikuotais atnaujinimais. |   3   | D/V  |
| 4.19.3 | Patikrinkite, ar pasirinktinis ASIC saugumas apima mikroschemos saugumo procesorius, aparatinę pasitikėjimo šaknį ir saugų raktų saugojimą su aptikimu, jei bandoma pažeisti.                      |   3   | D/V  |
| 4.19.4 | Patikrinkite, ar optinės skaičiavimo sistemos įgyvendina kvantiniu požiūriu saugią optinę šifravimą, saugų fotoninių perjungimą ir apsaugotą optinį signalo apdorojimą.                            |   3   | D/V  |
| 4.19.5 | Patikrinkite, ar hibridiniai analoginiai-skaitmeniniai DI lustai apima saugią analoginę skaičiavimą, apsaugotą svorių saugojimą ir autentifikuotą analoginio-skaitmeninio keitimo procesą.         |   3   | D/V  |

---

## C4.20 Privatumo Išlaikymo Skaičiavimo Infrastruktūra

Įgyvendinkite infrastruktūros kontrolės priemones privatumą saugančiai skaičiavimui, siekiant apsaugoti jautrius duomenis AI apdorojimo ir analizės metu.

|   #    | Description                                                                                                                                                                                                   | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Patikrinkite, ar homomorfinės šifravimo infrastruktūra leidžia atlikti užšifruotą skaičiavimą jautrioms DI užduotims su kriptografinio vientisumo patikrinimu ir veiklos stebėsena.                           |   3   | D/V  |
| 4.20.2 | Patikrinkite, ar privatios informacijos gavimo sistemos leidžia užklausas duomenų bazėje vykdyti neatskleidžiant užklausų modelių, naudojant kriptografinę prieigos modelių apsaugą.                          |   3   | D/V  |
| 4.20.3 | Patikrinkite, ar saugūs daugiapusių skaičiavimų protokolai leidžia atlikti privatumą išsaugančią AI inferenciją, neatskleidžiant atskirų įvesties duomenų ar tarpinio skaičiavimo rezultatų.                  |   3   | D/V  |
| 4.20.4 | Patikrinkite, ar privatumo saugomas raktų valdymas apima paskirstytą raktų generavimą, slenksčio kriptografiją ir saugų raktų rotavimą su aparatine apsauga.                                                  |   3   | D/V  |
| 4.20.5 | Patikrinkite, ar privatumo išsaugojimo skaičiavimo našumas yra optimizuotas naudojant grupavimą (batching), talpyklos (caching) naudojimą ir aparatinį pagreitį, išlaikant kriptografinio saugumo garantijas. |   3   | D/V  |

---

## C4.15 Agentų sistemos debesų integracijos saugumas ir hibridinis diegimas

Debesų integruotų agentų sistemų saugumo valdikliai hibridinėms vietinėms/debesų architektūroms.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Patikrinkite, ar debesies saugyklos integracija naudoja galutinio taško šifravimą su agento valdomu rakto valdymu.                       |   1   | D/V  |
| 4.15.2 | Patikrinkite, ar hibridinės diegimo saugumo ribos yra aiškiai apibrėžtos su užšifruotais komunikacijos kanalais.                         |   2   | D/V  |
| 4.15.3 | Patikrinkite, ar debesų išteklių prieiga apima nulio-pasitikėjimo patikrą su nuolatine autentifikacija.                                  |   2   | D/V  |
| 4.15.4 | Patikrinkite, ar duomenų saugojimo vietos reikalavimai įgyvendinami kriptografiniu saugyklos vietų patvirtinimu.                         |   3   | D/V  |
| 4.15.5 | Patikrinkite, ar debesų paslaugų teikėjo saugumo vertinimuose yra įtrauktas agentui būdingo grėsmių modeliavimas ir rizikos įvertinimas. |   3   | D/V  |

---

## Nuorodos

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

