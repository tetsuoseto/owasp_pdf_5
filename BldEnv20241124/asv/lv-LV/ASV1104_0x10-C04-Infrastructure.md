# C4 infrastruktūra, konfigurācija un izvietošanas drošība

## Kontroles mērķis

Mākslīgā intelekta infrastruktūrai jābūt nostiprinātai pret privilēģiju paaugstināšanu, piegādes ķēdes manipulācijām un sānu pārvietošanos, izmantojot drošu konfigurāciju, izpildlaika izolāciju, uzticamas izvietošanas plūsmas un visaptverošu monitoringu. Tikai autorizētas, pārbaudītas infrastruktūras sastāvdaļas un konfigurācijas sasniedz ražošanas vidi kontrolētos procesos, kas uztur drošību, integritāti un audita iespējas.

Pamata drošības mērķis: tikai kriptogrāfiski parakstītas, ievainojamību pārbaudītas infrastruktūras komponentes nokļūst ražošanā, izmantojot automatizētas validācijas plūsmas, kas ievēro drošības politikas un uztur nemainīgas audita pēdas.

---

## C4.1 Izpildes vides izolācija

Novērst konteineru aizbēgšanu un privilēģiju kāpināšanu, izmantojot kodola līmeņa izolācijas primitīvus un obligātus piekļuves kontroles mehānismus.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Pārliecinieties, ka visi AI konteineri atmet VISAS Linux spējas, izņemot CAP_SETUID, CAP_SETGID un skaidri nepieciešamās spējas, kas dokumentētas drošības pamatos.                                                                     |   1   | D/V  |
| 4.1.2 | Pārbaudiet, vai seccomp profili bloķē visus sistēmas izsaukumus, izņemot iepriekš apstiprinātās atļauto sarakstā esošās, pārkāpumiem izraisot container pārtraukšanu un drošības brīdinājumu ģenerēšanu.                                |   1   | D/V  |
| 4.1.3 | Pārliecinieties, ka mākslīgā intelekta darbagrozs darbojas ar tikai lasāmu saknes failu sistēmu, tmpfs pagaidu datiem un nosauktajiem apjomiem pastāvīgajiem datiem ar spēkā esošām noexec piekļuves opcijām.                           |   2   | D/V  |
| 4.1.4 | Pārbaudiet, vai eBPF bāzētā darbības laika uzraudzība (Falco, Tetragon vai līdzvērtīga) atklāj privilēģiju paaugstināšanas mēģinājumus un automātiski pārtrauc pārkāpjošos procesus saskaņā ar organizācijas reaģēšanas laika prasībām. |   2   | D/V  |
| 4.1.5 | Pārbaudiet, vai augsta riska mākslīgā intelekta darbplūsmas tiek izpildītas aparatūras izolētās vidēs (Intel TXT, AMD SVM vai specializētos bare-metal mezglos) ar apliecinājuma verifikāciju.                                          |   3   | D/V  |

---

## C4.2 Drošas izstrādes un izvietošanas cauruļvadi

Nodrošiniet kriptogrāfisko integritāti un piegādes ķēdes drošību, izmantojot atkārtojami veidotas būves un parakstītus artefaktus.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.2.1 | Pārliecinieties, ka infrastruktūra kā kods tiek pārbaudīta ar rīkiem (tfsec, Checkov vai Terrascan) katrā komitā, bloķējot apvienošanu, ja tiek konstatētas KRITIŠKAS vai AUGSTAS nopietnības problēmas.           |   1   | D/V  |
| 4.2.2 | Pārbaudiet, vai konteineru būves ir reproducējamas ar identiskām SHA256 hashs vērtībām starp būvēm un ģenerējiet SLSA 3. līmeņa izcelsmes apliecinājumus, kas parakstīti ar Sigstore.                              |   1   | D/V  |
| 4.2.3 | Pārliecinieties, ka konteineru attēli iekļauj CycloneDX vai SPDX SBOM un ir parakstīti ar Cosign pirms nosūtīšanas uz reģistra, bet nenoparasti attēli tiek noraidīti izvietošanas laikā.                          |   2   | D/V  |
| 4.2.4 | Pārbaudiet, vai CI/CD cauruļvadi izmanto OIDC marķierus no HashiCorp Vault, AWS IAM lomām vai Azure pārvaldītās identitātes ar derīguma termiņiem, kas nepārsniedz organizācijas drošības politikas ierobežojumus. |   2   | D/V  |
| 4.2.5 | Pārliecinieties, ka Cosign paraksti un SLSA izcelsmes dati tiek pārbaudīti izvietošanas procesā pirms konteineru izpildes, un ka pārbaudes kļūdas izraisa izvietošanas neveiksmi.                                  |   2   | D/V  |
| 4.2.6 | Pārbaudiet, vai būvniecības vidēs tiek izmantoti īslaicīgi konteineri vai virtuālās mašīnas bez pastāvīgas atmiņas un ar tīkla izolāciju no ražošanas VPC.                                                         |   2   | D/V  |

---

## C4.3 Tīkla drošība un piekļuves kontrole

Ieviest nulles uzticības tīklu ar noklusējuma noraidīšanas politikām un šifrētu saziņu.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Pārbaudiet, vai Kubernetes NetworkPolicies vai jebkura līdzvērtīga risinājuma implementācija nodrošina noklusējuma aizliegumu ieejas/izejas satiksmei ar skaidri definētiem atļaujumiem prasītajiem portiem (443, 8080 utt.). |   1   | D/V  |
| 4.3.2 | Pārbaudiet, vai SSH (22. ports), RDP (3389. ports) un mākoņa metadatu galapunkti (169.254.169.254) ir bloķēti vai prasa autentifikāciju, balstītu uz sertifikātu.                                                             |   1   | D/V  |
| 4.3.3 | Pārbaudiet, vai izejošais trafiks tiek filtrēts caur HTTP/HTTPS starpniekserveriem (Squid, Istio vai mākoņa NAT vārtejas) ar domēnu atļauto sarakstu, un bloķētie pieprasījumi tiek reģistrēti.                               |   2   | D/V  |
| 4.3.4 | Pārbaudiet, vai starpservisu saziņa izmanto savstarpējo TLS ar sertifikātiem, kas tiek rotēti saskaņā ar organizācijas politiku, un sertifikātu validācija tiek nodrošināta (bez "skip-verify" karodziņiem).                  |   2   | D/V  |
| 4.3.5 | Pārbaudiet, vai mākslīgā intelekta infrastruktūra darbojas īpašos VPC/VNet tīklos bez tiešas piekļuves internetam un sazinās tikai caur NAT vārtejām vai piekļuves serveriem (bastion hosts).                                 |   2   | D/V  |

---

## C4.4 Noslēpumu un kriptogrāfisko atslēgu pārvaldība

Aizsargājiet akreditācijas datus, izmantojot aparatūras atbalstītu glabāšanu un automātisku rotāciju ar nulles uzticības piekļuvi.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Pārliecinieties, ka slepenie dati tiek glabāti HashiCorp Vault, AWS Secrets Manager, Azure Key Vault vai Google Secret Manager ar AES-256 šifrēšanu miera stāvoklī.                                                                     |   1   | D/V  |
| 4.4.2 | Pārliecinieties, ka kriptogrāfiskās atslēgas tiek ģenerētas FIPS 140-2 2. līmeņa HSM (AWS CloudHSM, Azure Dedicated HSM) ar atslēgu rotāciju saskaņā ar organizācijas kriptogrāfiskās politikas prasībām.                               |   1   | D/V  |
| 4.4.3 | Pārbaudiet, vai slepeno datu grozīšana ir automatizēta ar nulles dīkstāves izvietošanu un tūlītēju grozīšanu, ko izraisījušas personāla izmaiņas vai drošības incidenti.                                                                |   2   | D/V  |
| 4.4.4 | Pārliecinieties, ka konteineru attēli tiek skenēti ar rīkiem (GitLeaks, TruffleHog vai detect-secrets), bloķējot būves, kas satur API atslēgas, paroles vai sertifikātus.                                                               |   2   | D/V  |
| 4.4.5 | Pārbaudiet, vai piekļuve ražošanas slepenajiem datiem prasa daudzfaktoru autentifikāciju ar aparatūras tokeniem (YubiKey, FIDO2) un tiek reģistrēta nemaināmos revīzijas žurnālos ar lietotāju identitātēm un laika zīmēm.              |   2   | D/V  |
| 4.4.6 | Pārbaudiet, vai slepenie dati tiek ievadīti, izmantojot Kubernetes slepenos datus, pievienotos datu apjomus vai inicializācijas konteinerus, un pārliecinieties, ka slepenie dati nekad netiek iestrādāti vides mainīgajos vai attēlos. |   2   | D/V  |

---

## C4.5 AI darba slodzes izolēšana un validācija

Izolējiet neuzticamos mākslīgā intelekta modeļus drošās smilšu kastēs ar visaptverošu uzvedības analīzi.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Pārbaudiet, vai ārējie AI modeļi tiek izpildīti gVisor, microVM (piemēram, Firecracker, CrossVM) vai Docker konteineros ar --security-opt=no-new-privileges un --read-only karogiem.    |   1   | D/V  |
| 4.5.2 | Pārbaudiet, vai smilšu kastes vidēs nav tīkla savienojuma (--network=none) vai ir piekļuve tikai localhost, ar visiem ārējiem pieprasījumiem bloķētiem, izmantojot iptables noteikumus. |   1   | D/V  |
| 4.5.3 | Pārliecinieties, ka AI modeļa validācija ietver automatizētu sarkano komandu pārbaudi ar organizatoriski noteiktu testēšanas segumu un uzvedības analīzi aizmugures durvju atklāšanai.  |   2   | D/V  |
| 4.5.4 | Pārliecinieties, ka pirms AI modeļa virzīšanas ražošanā tā testa rezultāti tiek kriptogrāfiski parakstīti ar pilnvarotām drošības personām un glabāti nemaināmos audita žurnālos.       |   2   | D/V  |
| 4.5.5 | Pārliecinieties, ka smilškastes vidē tiek iznīcinātas un atjaunotas no zelta attēliem starp novērtējumiem, veicot pilnīgu failu sistēmas un atmiņas attīrīšanu.                         |   2   | D/V  |

---

## C4.6 Infrastruktūras drošības uzraudzība

Nepārtraukti skenējiet un uzraugiet infrastruktūru ar automatizētu problēmu novēršanu un reāllaika brīdinājumiem.

|   #   | Description                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.6.1 | Pārliecinieties, ka konteineru attēli tiek skenēti saskaņā ar organizācijas grafikām, un KRITIŠKAS ievainojamības bloķē izvietošanu, pamatojoties uz organizācijas riska sliekšņiem.                                     |   1   | D/V  |
| 4.6.2 | Pārbaudiet, vai infrastruktūra atbilst CIS vadlīnijām vai NIST 800-53 kontroles prasībām ar organizācijā noteiktiem atbilstības sliekšņiem un automatizētu labošanas mehānismu neveiksmīgu pārbaudes rezultātu gadījumā. |   1   | D/V  |
| 4.6.3 | Pārbaudiet, vai augstas nozīmības ievainojamības ir izlabotas atbilstoši organizācijas riska pārvaldības termiņiem ar ārkārtas procedūrām aktīvi izmantotām CVE ievainojamībām.                                          |   2   | D/V  |
| 4.6.4 | Pārbaudiet, vai drošības brīdinājumi integrējas ar SIEM platformām (Splunk, Elastic vai Sentinel), izmantojot CEF vai STIX/TAXII formātus ar automatizētu bagātināšanu.                                                  |   2   |  V   |
| 4.6.5 | Pārbaudiet, vai infrastruktūras metrikas tiek eksportētas uz uzraudzības sistēmām (Prometheus, DataDog) ar SLA informācijas paneļiem un vadības pārskatiem.                                                              |   3   |  V   |
| 4.6.6 | Pārbaudiet, vai konfigurācijas novirzes tiek atklātas, izmantojot rīkus (Chef InSpec, AWS Config) saskaņā ar organizācijas uzraudzības prasībām ar automātisku atjaunošanu neautorizētām izmaiņām.                       |   2   | D/V  |

---

## C4.7 AI infrastruktūras resursu pārvaldība

Novērst resursu izsīkuma uzbrukumus un nodrošināt taisnīgu resursu sadali, izmantojot kvotas un uzraudzību.

|   #   | Description                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.7.1 | Pārliecinieties, ka GPU/TPU izmantošana tiek uzraudzīta ar signāliem, kas tiek aktivizēti organizācijas noteiktajos sliekšņos, un ka tiek automātiski aktivizēta mērogošana vai slodzes balansēšana, pamatojoties uz kapacitātes pārvaldības politiku. |   1   | D/V  |
| 4.7.2 | Pārbaudiet, vai AI darba slodzes metrikas (secinājumu latentums, caurlaide, kļūdu līmeņi) tiek vāktas atbilstoši organizācijas uzraudzības prasībām un korelētas ar infrastruktūras izmantošanu.                                                       |   1   | D/V  |
| 4.7.3 | Pārbaudiet, vai Kubernetes ResourceQuotas vai tamlīdzīgas funkcijas ierobežo individuālos darba slodzes atbilstoši organizācijas resursu piešķiršanas politikām, nodrošinot stingrus ierobežojumus.                                                    |   2   | D/V  |
| 4.7.4 | Pārbaudiet, vai izmaksu uzraudzība seko līdzi izdevumiem pa darba slodzēm/lietotājiem ar brīdinājumiem, kas balstās uz organizācijas budžeta sliekšņiem, un automatizētiem kontroles mehānismiem budžeta pārsnieguma gadījumā.                         |   2   |  V   |
| 4.7.5 | Pārbaudiet, vai kapacitātes plānošana izmanto vēsturiskos datus ar organizācijas noteiktiem prognozēšanas periodiem un automatizētu resursu nodošanu atbilstoši pieprasījuma modeļiem.                                                                 |   3   |  V   |
| 4.7.6 | Pārbaudiet, vai resursu izsīkums aktivizē ķēžu pārtraucējus atbilstoši organizācijas atbildes prasībām, tostarp ātruma ierobežošanu, pamatojoties uz kapacitātes politiku un darba slodzes izolāciju.                                                  |   2   | D/V  |

---

## C4.8 Vides atdalīšanas un pārejas kontroles pasākumi

Nodrošiniet stingras vides robežas ar automatizētām paaugstināšanas barjerām un drošības pārbaudēm.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.8.1 | Pārliecinieties, ka izstrādes/testēšanas/ražošanas vidi darbojas atsevišķos VPC/VNet, bez koplietojamām IAM lomām, drošības grupām vai tīkla savienojamības.                                                 |   1   | D/V  |
| 4.8.2 | Pārliecinieties, ka vides paaugstināšana prasa apstiprinājumu no organizācijā definētas pilnvarotas personas ar kriptogrāfiskām parakstiem un nemaināmiem audita ierakstiem.                                 |   1   | D/V  |
| 4.8.3 | Pārliecinieties, ka ražošanas vidēs ir bloķēta SSH piekļuve, atspējoti atkļūdošanas galapunkti un tiek prasīti izmaiņu pieprasījumi ar organizācijas iepriekšēju paziņojumu, izņemot ārkārtas gadījumus.     |   2   | D/V  |
| 4.8.4 | Pārliecinieties, ka infrastruktūras-kā-koda izmaiņas prasa vienaudžu pārskatīšanu ar automatizētu testēšanu un drošības skenēšanu pirms apvienošanas ar galveno zaru.                                        |   2   | D/V  |
| 4.8.5 | Pārbaudiet, vai ne-ražošanas dati ir anonimizēti saskaņā ar organizācijas privātuma prasībām, sintētisko datu ģenerēšanu vai pilnīgu datu maskēšanu ar personu identifikācijas informācijas (PII) noņemšanu. |   2   | D/V  |
| 4.8.6 | Pārliecinieties, ka paaugstināšanas posmos ir iekļauti automatizēti drošības testi (SAST, DAST, konteineru skenēšana), un apstiprināšanai ir nepieciešams, lai nebūtu nevienas KRITIŠKAS atziņas.            |   2   | D/V  |

---

## C4.9 Infrastruktūras dublēšana un atkopšana

Nodrošiniet infrastruktūras noturību, izmantojot automatizētas dublējumkopijas, pārbaudītas atjaunošanas procedūras un katastrofu atjaunošanas iespējas.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Pārbaudiet, vai infrastruktūras konfigurācijas ir dublētas atbilstoši organizācijas dublēšanas grafikam uz ģeogrāfiski atšķirīgām vietām, īstenojot 3-2-1 dublēšanas stratēģiju.                        |   1   | D/V  |
| 4.9.2 | Pārbaudiet, vai rezerves sistēmas darbojas izolētās tīklos ar atsevišķām piekļuves tiesībām un gaisa spraugas tipa krātuvi izspiedējvīrusu aizsardzībai.                                                |   2   | D/V  |
| 4.9.3 | Pārliecinieties, ka atkopšanas procedūras tiek pārbaudītas un validētas ar automatizēto testēšanu, atbilstoši organizācijas grafikam, ņemot vērā RTO un RPO mērķus, kas atbilst organizācijas prasībām. |   2   |  V   |
| 4.9.4 | Pārbaudiet, vai katastrofas atjaunošana ietver AI specifiskas darbību rokasgrāmatas ar modeļa svaru atjaunošanu, GPU klastera atjaunošanu un pakalpojumu atkarību kartēšanu.                            |   3   |  V   |

---

## C4.10 Infrastruktūras atbilstība un pārvaldība

Uzturiet regulatīvo atbilstību, veicot nepārtrauktu novērtēšanu, dokumentēšanu un automatizētu kontroli.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Pārliecinieties, ka infrastruktūras atbilstība tiek novērtēta saskaņā ar organizācijas grafikām pret SOC 2, ISO 27001 vai FedRAMP kontroles prasībām, izmantojot automātisku pierādījumu vākšanu. |   2   | D/V  |
| 4.10.2 | Pārliecinieties, ka infrastruktūras dokumentācijā ir iekļautas tīkla shēmas, datu plūsmas kartes un draudu modeļi, kas atjaunināti saskaņā ar organizācijas izmaiņu vadības prasībām.             |   2   |  V   |
| 4.10.3 | Pārliecinieties, ka infrastruktūras izmaiņas tiek pakļautas automatizētai atbilstības ietekmes novērtēšanai ar regulatīvās apstiprināšanas plūsmām augsta riska modifikācijām.                    |   3   | D/V  |

---

## C4.11 Mākslīgā intelekta aparatūras drošība

Nodrošiniet AI specifiskas aparatūras komponentes, tostarp GPU, TPU un specializētus AI akseleratorus.

|   #    | Description                                                                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Pārliecinieties, ka AI paātrinātāja programmatūra (GPU BIOS, TPU programmatūra) ir pārbaudīta ar kriptogrāfiskām parakstiem un atjaunināta saskaņā ar organizācijas ielāpu pārvaldības termiņiem. |   2   | D/V  |
| 4.11.2 | Pārbaudiet, vai pirms darba slodzes izpildes AI akseleratora integritāte tiek pārbaudīta ar aparatūras apliecinājumu, izmantojot TPM 2.0, Intel TXT vai AMD SVM.                                  |   2   | D/V  |
| 4.11.3 | Pārliecinieties, ka GPU atmiņa ir izolēta starp darba slodzēm, izmantojot SR-IOV, MIG (vairāku instanču GPU) vai līdzvērtīgu aparatūras sadalījumu ar atmiņas sanitāriju starp uzdevumiem.        |   2   | D/V  |
| 4.11.4 | Pārbaudiet, vai AI aparatūras piegādes ķēdē ir iekļauta izcelsmes pārbaude ar ražotāja sertifikātiem un iepakojuma bojājumu pazīmju validācija.                                                   |   3   |  V   |
| 4.11.5 | Pārliecinieties, ka aparatūras drošības moduļi (HSM) aizsargā AI modeļu svaru un kriptogrāfiskos atslēgas ar FIPS 140-2 3. līmeņa vai Common Criteria EAL4+ sertifikāciju.                        |   3   | D/V  |

---

## C4.12 Malas un izkliedētas mākslīgā intelekta infrastruktūra

Drošas izkliedētas mākslīgā intelekta izvietošanas, ieskaitot maldatoru aprēķinus, federētās apmācības un daudzvietu arhitektūras.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Pārbaudiet, vai malējās AI ierīces autentificējas centrālajā infrastruktūrā, izmantojot abpusēju TLS ar ierīces sertifikātiem, kas tiek mainīti saskaņā ar organizācijas sertifikātu pārvaldības politiku. |   2   | D/V  |
| 4.12.2 | Pārbaudiet, vai galapunktu ierīces īsteno drošu palaišanu ar pārbaudītām parakstiem un atcelšanas aizsardzību, novēršot programmaparatūras pazemināšanas uzbrukumus.                                       |   2   | D/V  |
| 4.12.3 | Pārbaudiet, vai izkliedētās mākslīgā intelekta koordinācijas procesā tiek izmantotas Bīzantiešu kļūmju noturīgas konsensa algoritmi ar dalībnieku validāciju un ļaunprātīgu mezglu noteikšanu.             |   3   | D/V  |
| 4.12.4 | Pārbaudiet, vai malas un mākoņa komunikācijā ir iekļauta joslas platuma ierobežošana, datu saspiešana un bezsavienojuma režīma iespējas ar drošu lokālu datu glabāšanu.                                    |   3   | D/V  |

---

## C4.13 Multi-mākoņdatošana un hibrīdā infrastruktūras drošība

Nodrošiniet drošus mākslīgā intelekta darba slodzes vairākos mākoņu pakalpojumu sniedzējos un hibrīdā mākoņa un lokālās izvietošanas vidē.

|   #    | Description                                                                                                                                                                                                            | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Pārbaudiet, vai daudzmākoņu mākslīgā intelekta izvietojumi izmanto mākoņiem neatkarīgu identitātes federāciju (OIDC, SAML) ar centralizētu politikas pārvaldību starp pakalpojumu sniedzējiem.                         |   2   | D/V  |
| 4.13.2 | Pārbaudiet, vai starp-mākoņu datu pārraide izmanto beigu līdz beigām šifrēšanu ar klienta pārvaldītiem atslēgām un datu uzturēšanas vadību, kas tiek piemērota atbilstoši jurisdikcijai.                               |   2   | D/V  |
| 4.13.3 | Pārliecinieties, ka hibrīda mākoņa mākslīgā intelekta darba slodzes īsteno konsekventas drošības politikas gan lokālajā, gan mākoņa vidē ar vienotu uzraudzību un brīdināšanu.                                         |   2   | D/V  |
| 4.13.4 | Pārbaudiet, vai mākoņpakalpojumu sniedzēja bloķēšanas novēršana ietver pārnēsājamu infrastruktūru kā kodu (Infrastructure-as-Code), standartizētas API un datu eksportēšanas iespējas ar formātu konvertēšanas rīkiem. |   3   |  V   |
| 4.13.5 | Pārbaudiet, vai daudzmākoņa izmaksu optimizācija ietver drošības kontroles, kas novērš resursu izklīšanu, kā arī nesankcionētas datu pārsūtīšanas izmaksas starp mākoņiem.                                             |   3   |  V   |

---

## C4.14 Infrastruktūras automatizācija un GitOps drošība

Droša infrastruktūras automatizācijas cauruļvadu un GitOps darba plūsmu nodrošināšana mākslīgā intelekta infrastruktūras pārvaldībai.

|   #    | Description                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Pārliecinieties, ka GitOps repozitoriji prasa parakstītus komitus ar GPG atslēgām un ir ieviesti filiāļu aizsardzības noteikumi, kas neļauj tieši iegriezt izmaiņas galvenajās filiālēs.                                     |   2   | D/V  |
| 4.14.2 | Pārbaudiet, vai infrastruktūras automatizācija ietver noviržu noteikšanu ar automātiskām labošanas un atcelšanas iespējām, kas tiek aktivizētas saskaņā ar organizācijas atbildes prasībām attiecībā uz neatļautām izmaiņām. |   2   | D/V  |
| 4.14.3 | Pārbaudiet, vai automatizētā infrastruktūras nodrošināšana ietver drošības politikas validāciju ar izvietošanas bloķēšanu neatbilstošām konfigurācijām.                                                                      |   2   | D/V  |
| 4.14.4 | Pārbaudiet, vai infrastruktūras automatizācijas noslēpumi tiek pārvaldīti, izmantojot ārējos noslēpumu operatorus (External Secrets Operator, Bank-Vaults) ar automātisku rotāciju.                                          |   2   | D/V  |
| 4.14.5 | Pārbaudiet, ka pašatjaunojošā infrastruktūra ietver drošības notikumu korelāciju ar automatizētu incidentu reaģēšanu un ieinteresēto personu paziņošanas darba plūsmām.                                                      |   3   |  V   |

---

## C4.15 Kvantuizturīgas infrastruktūras drošība

Sagatavojiet mākslīgā intelekta infrastruktūru kvantu skaitļošanas draudu seku novēršanai, izmantojot pēckvantu kriptogrāfiju un kvantu drošas protokolus.

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Pārbaudiet, vai mākslīgā intelekta infrastruktūra ievieš NIST apstiprinātas postkvantu kriptogrāfijas algoritmus (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+), kas paredzēti atslēgu apmaiņai un digitālajām parakstiem. |   3   | D/V  |
| 4.15.2 | Pārbaudiet, vai kvantu atslēgu izplatīšanas (QKD) sistēmas tiek ieviestas augstas drošības AI komunikācijām ar kvantu drošu atslēgu pārvaldības protokoliem.                                                               |   3   | D/V  |
| 4.15.3 | Pārbaudiet, vai kriptogrāfiskās elastības rāmji ļauj ātri pāriet uz jauniem pētkvantu algoritmiem ar automatizētu sertifikātu un atslēgu rotāciju.                                                                         |   3   | D/V  |
| 4.15.4 | Pārbaudiet, vai kvantu draudu modelēšana novērtē AI infrastruktūras neaizsargātību pret kvantu uzbrukumiem, iekļaujot dokumentētus migrācijas grafikus un riska novērtējumus.                                              |   3   |  V   |
| 4.15.5 | Pārbaudiet, vai hibrīdie klasiskie-kvantu kriptogrāfiskie sistēmi nodrošina daudzlīmeņu aizsardzību kvantu pārejas periodā, veicot veiktspējas uzraudzību.                                                                 |   3   | D/V  |

---

## C4.16 Konfidenciālā skaitļošana un drošie konteksti

Aizsargājiet AI darblodas un modeļu svarus, izmantojot aparatūras balstītas uzticamas izpildes vides un konfidenciālu skaitļošanas tehnoloģijas.

|   #    | Description                                                                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Pārbaudiet, vai sensitīvie mākslīgā intelekta modeļi tiek izpildīti Intel SGX nišās, AMD SEV-SNP vai ARM TrustZone ar šifrētu atmiņu un apliecinājuma pārbaudi.                                  |   3   | D/V  |
| 4.16.2 | Pārbaudiet, vai konfidenciālie konteineri (Kata Containers, gVisor ar konfidenciālo skaitļošanu) atdala mākslīgā intelekta darba slodzes, izmantojot aparatūras nodrošinātu atmiņas šifrēšanu.   |   3   | D/V  |
| 4.16.3 | Pārbaudiet, vai attālinātā apliecināšana apstiprina inkubatora integritāti pirms AI modeļu ielādes, izmantojot kriptogrāfisku izpildes vides autentiskuma pierādījumu.                           |   3   | D/V  |
| 4.16.4 | Pārliecinieties, ka konfidenciālas mākslīgā intelekta inferencēšanas pakalpojumi novērš modeļa izgūšanu, izmantojot šifrētas aprēķinus ar noslēgtām modeļa svaru vērtībām un aizsargātu izpildi. |   3   | D/V  |
| 4.16.5 | Pārliecinieties, ka uzticamu izpildes vidi koordinē drošas aploksnes dzīves ciklu, izmantojot attālinātu apstiprināšanu un šifrētus komunikācijas kanālus.                                       |   3   | D/V  |
| 4.16.6 | Pārbaudiet, vai droša vairāku pušu aprēķināšana (SMPC) ļauj veikt sadarbības mākslīgā intelekta apmācību, neizpaužot atsevišķos datu kopumus vai modeļa parametrus.                              |   3   | D/V  |

---

## C4.17 Zināšanu Bezpalīdzības Infrastruktūra

Izstrādājiet nulles zināšanu pierādījumu sistēmas privātuma saglabāšanai mākslīgā intelekta verifikācijā un autentifikācijā, neatklājot sensitīvu informāciju.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.17.1 | Pārliecinieties, ka nulles zināšanu pierādījumi (ZK-SNARKs, ZK-STARKs) pārbauda mākslīgā intelekta modeļa integritāti un apmācības izcelsmi, neizpaužot modeļa svarus vai apmācības datus. |   3   | D/V  |
| 4.17.2 | Pārbaudiet, vai ZK (nulles zināšanu) autentifikācijas sistēmas nodrošina privātumu saglabājošu lietotāja pārbaudi AI pakalpojumiem, neatklājot identitātei saistītu informāciju.           |   3   | D/V  |
| 4.17.3 | Pārliecinieties, ka privātā kopa krustojuma (PSI) protokoli nodrošina drošu datu saskaņošanu federatīvai mākslīgajam intelektam, neizpaužot atsevišķas datu kopas.                         |   3   | D/V  |
| 4.17.4 | Pārbaudiet, vai nulle-ziņas mašīnmācīšanās (ZKML) sistēmas nodrošina pārbaudāmas mākslīgā intelekta secināšanas ar kriptogrāfisku pierādījumu par pareizu aprēķinu.                        |   3   | D/V  |
| 4.17.5 | Pārbaudiet, vai ZK-rollupi nodrošina mērogojamu, privātumu saglabājošu AI darījumu apstrādi ar partiju verifikāciju un samazinātu aprēķinu slodzi.                                         |   3   | D/V  |

---

## C4.18 Blakuskanāla uzbrukuma novēršana

Aizsargājiet AI infrastruktūru no laika, elektroenerģijas, elektromagnētiskajiem un keša bāzētiem sānu kanālu uzbrukumiem, kas varētu nopludināt sensitīvu informāciju.

|   #    | Description                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Pārbaudiet, vai AI inferencēšanas laiks ir normalizēts, izmantojot konstantlaika algoritmus un aizpildījumu, lai novērstu uz laiku balstītas modeļa ekstrakcijas uzbrukumus. |   3   | D/V  |
| 4.18.2 | Pārbaudiet, vai jaudas analīzes aizsardzība ietver trokšņu injekciju, jaudas līnijas filtrēšanu un nejaušinātas izpildes modeļus mākslīgā intelekta aparatūrā.               |   3   | D/V  |
| 4.18.3 | Pārbaudiet, vai kešatmiņā balstīta blakus kanāla novēršana izmanto kešatmiņas partīciju, nejaušināšanu un notīrīšanas instrukcijas, lai novērstu informācijas noplūdi.       |   3   | D/V  |
| 4.18.4 | Pārliecinieties, ka elektromagnētiskās izstarojuma aizsardzība ietver ekrānēšanu, signālu filtrēšanu un nejaušinātu apstrādi, lai novērstu TEMPEST tipa uzbrukumus.          |   3   | D/V  |
| 4.18.5 | Pārliecinieties, ka mikroarhitektūras sānpierakstu aizsardzībās ietilpst spekulatīvās izpildes kontrole un atmiņas piekļuves modeļa maskēšana.                               |   3   | D/V  |

---

## C4.19 Neiromorfu un specializēta AI aparatūras drošība

Nodrošiniet drošību jaunajās mākslīgā intelekta aparatūras arhitektūrās, tajā skaitā neiroformu čipos, FPGA, pielāgotos ASIC un optiskās skaitļošanas sistēmās.

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Pārbaudiet, vai neuromorfo mikroshēmas drošība ietver sprādziena modeļu šifrēšanu, sinaptisko svaru aizsardzību un aparatūras bāzētu mācību likmju validāciju.                    |   3   | D/V  |
| 4.19.2 | Pārbaudiet, vai FPGA bāzētie AI paātrinātāji izmanto bitplūsmas šifrēšanu, pretnepilnību mehānismus un drošu konfigurācijas ielādi ar autentificētām atjauninājumiem.             |   3   | D/V  |
| 4.19.3 | Pārbaudiet, vai pielāgotajā ASIC drošībā ir iekļauti uz mikroshēmas esošie drošības procesori, aparatūras uzticības pamats un droša atslēgu glabāšana ar manipulāciju noteikšanu. |   3   | D/V  |
| 4.19.4 | Pārliecinieties, ka optiskās skaitļošanas sistēmas īsteno kvantu drošu optisko šifrēšanu, drošu fotonisko slēgšanu un aizsargātu optisko signālu apstrādi.                        |   3   | D/V  |
| 4.19.5 | Pārbaudiet, vai hibrīdi analogi-digitālie AI mikroshēmas ietver drošu analogo aprēķinu, aizsargātu svaru glabāšanu un autentificētu analogo-digita konversiju.                    |   3   | D/V  |

---

## C4.20 Privātumu saglabājoša skaitļošanas infrastruktūra

Īstenot infrastruktūras kontroli privātumu saglabājošai aprēķinu veikšanai, lai aizsargātu sensitīvus datus AI apstrādes un analīzes laikā.

|   #    | Description                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.20.1 | Pārbaudiet, vai homomorfās šifrēšanas infrastruktūra nodrošina šifrētu aprēķinu jūtīgām mākslīgā intelekta darba slodzēm ar hronogrāfiskās integritātes pārbaudi un veiktspējas uzraudzību.                    |   3   | D/V  |
| 4.20.2 | Pārbaudiet, vai privātās informācijas izgūšanas sistēmas ļauj veikt datubāzes vaicājumus, neatklājot vaicājumu modeļus, nodrošinot piekļuves modeļu kriptogrāfisku aizsardzību.                                |   3   | D/V  |
| 4.20.3 | Pārbaudiet, vai droši vairāku pušu aprēķinu protokoli nodrošina privātumu saglabājošu AI inferenci, neatklājot atsevišķu ievadu vai starprezultātus.                                                           |   3   | D/V  |
| 4.20.4 | Pārbaudiet, vai privātumu saglabājošā atslēgu pārvaldība ietver sadalītu atslēgu ģenerēšanu, sliekšņa kriptogrāfiju un drošu atslēgu rotāciju ar aparatūras atbalstītu aizsardzību.                            |   3   | D/V  |
| 4.20.5 | Pārliecinieties, ka privātumu saglabājošās aprēķinu veiktspēja ir optimizēta, izmantojot partijveida apstrādi, kešošanu un aparatūras paātrinājumu, vienlaikus saglabājot kriptogrāfiskās drošības garantijas. |   3   | D/V  |

---

## C4.15 Aģentu sistēmas mākoņintegrācijas drošība un hibrīda izvietošana

Drošības kontroles mākoņu integrētiem aģentu ietvariem ar hibrīdu lokālo/mākoņu arhitektūru.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Pārliecinieties, ka mākoņkrātuves integrācija izmanto gala līdz gala šifrēšanu ar aģenta kontrolētu atslēgu pārvaldību.                  |   1   | D/V  |
| 4.15.2 | Pārbaudiet, vai hibrīddarba drošības robežas ir skaidri definētas ar šifrētu komunikācijas kanāliem.                                     |   2   | D/V  |
| 4.15.3 | Pārliecinieties, ka piekļuve mākoņresursiem ietver nulles uzticības pārbaudi ar nepārtrauktu autentifikāciju.                            |   2   | D/V  |
| 4.15.4 | Pārbaudiet, vai datu glabāšanas prasības tiek nodrošinātas, izmantojot kriptogrāfisku uzglabāšanas vietu apliecinājumu.                  |   3   | D/V  |
| 4.15.5 | Pārliecinieties, ka mākoņpakalpojumu sniedzēja drošības novērtējumos iekļauta aģentam specifiska draudu modelēšana un riska novērtēšana. |   3   | D/V  |

---

## Atsauces

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

