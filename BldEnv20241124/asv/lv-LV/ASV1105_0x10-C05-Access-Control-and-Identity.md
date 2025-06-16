# C5 Piekļuves kontrole un identitāte AI komponentiem un lietotājiem

## Kontroles mērķis

Efektīvai piekļuves kontrolei mākslīgā intelekta sistēmām nepieciešama robusta identitātes pārvaldība, kontekstu izprasto atļauju piešķiršana un izpilde izpildes laikā, balstoties uz nulles uzticības principiem. Šie kontroles mehānismi nodrošina, ka cilvēki, pakalpojumi un autonomās sistēmas mijiedarbojas ar modeļiem, datiem un aprēķinu resursiem tikai noteiktajos piekļuves apjomos, nodrošinot nepārtrauktu verifikāciju un revīzijas iespējas.

---

## C5.1 Identitātes pārvaldība un autentifikācija

Izveidojiet kriptogrāfiski pamatotas identitātes visām vienībām ar daudzfaktoru autentifikāciju privilēģētām darbībām.

|   #   | Description                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Pārliecinieties, ka visi cilvēku lietotāji un pakalpojumu principiāli autentificējas caur centralizētu uzņēmuma identitātes pakalpojumu sniedzēju (IdP), izmantojot OIDC/SAML protokolus ar unikālām identitātes-uz-tokenu kartēšanām (bez koplietotām kontām vai akreditācijas datiem). |   1   | D/V  |
| 5.1.2 | Pārliecinieties, ka augsta riska darbības (modeļa izvietošana, svaru eksportēšana, apmācību datu piekļuve, ražošanas konfigurācijas izmaiņas) prasa daudzfaktoru autentifikāciju vai paaugstinātas drošības autentifikāciju ar sesijas atkārtotu pārbaudi.                               |   1   | D/V  |
| 5.1.3 | Pārliecinieties, ka jauni galvenie lietotāji pirms piekļuves saņemšanas ražošanas sistēmai tiek identificēti saskaņā ar NIST 800-63-3 IAL-2 vai tam ekvivalentām prasībām.                                                                                                               |   2   |  D   |
| 5.1.4 | Pārbaudiet, vai piekļuves pārskati tiek veikti ceturksnī ar automatizētu neaktīvo kontu noteikšanu, akreditācijas datu rotācijas izpildi un atslēgšanas darba plūsmām.                                                                                                                   |   2   |  V   |
| 5.1.5 | Pārliecinieties, ka federētie AI aģenti autentificējas, izmantojot parakstītas JWT apliecinājumu, kuriem ir maksimālais derīguma termiņš 24 stundas un kuri satur kriptogrāfisku izcelsmes pierādījumu.                                                                                  |   3   | D/V  |

---

## C5.2 Resursu autorizācija un minimālās tiesības

Ieviest smalki diferencētus piekļuves kontroļu mehānismus visiem mākslīgā intelekta resursiem ar skaidrām atļauju modeļiem un audita žurnāliem.

|   #   | Description                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.2.1 | Pārbaudiet, vai katrs AI resurss (datu kopas, modeļi, galapunkts, vektoru kolekcijas, iegultie indeksi, aprēķinu instances) nodrošina lomu bāzētu piekļuves kontroli ar skaidrām atļauto resursu sarakstiem un noklusējuma aizlieguma politikām. |   1   | D/V  |
| 5.2.2 | Pārbaudiet, vai pakalpojumu kontiem pēc noklusējuma tiek piemēroti vismazākā privilēģiju principa, sākot ar tikai lasāmajām atļaujām, un dokumentētu biznesa pamatojumu nepieciešamību rakstīšanas piekļuvei.                                    |   1   | D/V  |
| 5.2.3 | Pārliecinieties, ka visas piekļuves kontroles izmaiņas ir saistītas ar apstiprinātiem izmaiņu pieprasījumiem un nemaināmi ierakstītas ar laika zīmēm, izpildītāju identitātēm, resursu identifikatoriem un atļauju izmaiņām.                     |   1   |  V   |
| 5.2.4 | Pārliecinieties, ka datu klasifikācijas birkas (PII, PHI, eksporta kontrole, patentēts) automātiski tiek pārvietotas uz atvasinātajiem resursiem (iebūvējumiem, uzvedņu kešatmiņām, modeļu iznākumiem) ar konsekventu politikas īstenošanu.      |   2   |  D   |
| 5.2.5 | Pārbaudiet, vai neatļautas piekļuves mēģinājumi un privilēģiju eskalācijas notikumi izraisa reāllaika brīdinājumus ar kontekstuālu metadatu SIEM sistēmām ne vēlāk kā 5 minūšu laikā.                                                            |   2   | D/V  |

---

## C5.3 Dinamiskā politikas izvērtēšana

Ieviesiet piekļuves kontroli, kas balstīta uz atribūtiem (ABAC), kontekstuāli apzinātām autorizācijas lēmumu pieņemšanai ar revīzijas iespējām.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Pārbaudiet, vai autorizācijas lēmumi ir ārpus sistēmas nodoti speciālai politikas dzinēja sistēmai (OPA, Cedar vai līdzvērtīgai), kas ir pieejama caur autentificētām API ar kriptogrāfiskās integritātes aizsardzību. |   1   | D/V  |
| 5.3.2 | Pārbaudiet, vai politikas izpēta dinamiskos atribūtus izpildes laikā, tostarp lietotāja piekļuves līmeni, resursa jutīguma klasifikāciju, pieprasījuma kontekstu, nomnieka izolāciju un laika ierobežojumus.           |   1   | D/V  |
| 5.3.3 | Pārliecinieties, ka politikas definīcijas ir versiju kontroles pakļautas, kolēģu pārskatītas un pārbaudītas ar automatizētiem testiem CI/CD cauruļvados pirms izvietošanas ražošanā.                                   |   2   |  D   |
| 5.3.4 | Pārliecinieties, ka politikas izvērtēšanas rezultāti ietver strukturētas lēmumu pamatotības un tiek pārraidīti uz SIEM sistēmām korelācijas analīzei un atbilstības ziņošanai.                                         |   2   |  V   |
| 5.3.5 | Pārbaudiet, vai politikas kešatmiņas laika līdzdzīvošanas (TTL) vērtības nepārsniedz 5 minūtes augstas jutības resursiem un 1 stundu standarta resursiem ar kešatmiņas neapstiprināšanas iespējām.                     |   3   | D/V  |

---

## C5.4 Vaicājuma laikā notiekošā drošības izpilde

Ieviest datubāzes slāņa drošības kontroli ar obligātu filtrēšanu un rindas līmeņa drošības politiku.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Pārliecinieties, ka visos vektoru datubāzes un SQL vaicājumos ir iekļauti obligātie drošības filtri (īpašnieka ID, jutīguma birkas, lietotāja darbības joma), kurus nodrošina datubāzes dzinējs, nevis lietojumprogrammas kods. |   1   | D/V  |
| 5.4.2 | Pārbaudiet, vai rindu līmeņa drošības (RLS) politikas un lauku līmeņa maskēšana ir iespējota ar politikas pārmantošanu visām vektoru datubāzēm, meklēšanas indeksiem un apmācību datu kopām.                                    |   1   | D/V  |
| 5.4.3 | Pārbaudiet, vai neizdevušās autorizācijas pārbaudes novērsīs "sajauktā pārstāvja uzbrukumus", nekavējoties pārtraucot pieprasījumus un atgriežot skaidras autorizācijas kļūdu kodus, nevis atgriežot tukšas rezultātu kopas.    |   2   |  D   |
| 5.4.4 | Pārliecinieties, ka politikas novērtēšanas latentums tiek pastāvīgi uzraudzīts ar automatizētiem brīdinājumiem par laika beigām, kas varētu ļaut apiet autorizāciju.                                                            |   2   |  V   |
| 5.4.5 | Pārliecinieties, ka vaicājuma atkārtošanas mehānismi pārskatī autorizācijas politikas, lai ņemtu vērā dinamiskas atļauju izmaiņas aktīvo lietotāju sesiju laikā.                                                                |   3   | D/V  |

---

## C5.5 Izvades filtrēšana un datu zuduma novēršana

Izvietojiet pēcapstrādes kontroles mehānismus, lai novērstu nesankcionētu datu atklāšanu mākslīgi ģenerētā saturā.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Pārbaudiet, vai pēc inferencēšanas filtrēšanas mehānismi skenē un rediģē neatļautu personisko identifikācijas informāciju (PII), klasificētu informāciju un uzņēmuma īpašuma datus pirms satura nodošanas pieprasītājiem. |   1   | D/V  |
| 5.5.2 | Pārbaudiet, vai modeļa izvados norādītie citāti, atsauces un avota norādes ir pārbaudītas pret izsaucēja tiesībām, un tos noņemiet, ja tiek konstatēta nesankcionēta piekļuve.                                            |   1   | D/V  |
| 5.5.3 | Pārbaudiet, vai izvades formāta ierobežojumi (tīrīti PDF faili, metadatu noņemšanas attēli, apstiprināti failu tipi) tiek ievēroti, pamatojoties uz lietotāja piekļuves līmeņiem un datu klasifikācijām.                  |   2   |  D   |
| 5.5.4 | Pārliecinieties, ka redakcijas algoritmi ir deterministiski, versiju kontrolēti un uztur audita žurnālus, lai atbalstītu atbilstības izmeklēšanu un tiesu ekspertīzi.                                                     |   2   |  V   |
| 5.5.5 | Pārbaudiet, vai augsta riska redakcijas notikumi ģenerē adaptīvus žurnālfailus, kuros ietvertas kriptogrāfiskas oriģinālā satura hešvērtības krimināltiesiskai atgūšanai bez datu atklāšanas.                             |   3   |  V   |

---

## C5.6 Daudznomnieku izolācija

Nodrošiniet kriptogrāfisku un loģisku izolāciju starp nomniekiem koplietotā AI infrastruktūrā.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Pārliecinieties, ka atmiņas telpas, iegulto elementu veikali, kešatmiņas ieraksti un pagaidu faili ir nodalīti pa nosaukumu telpām katram nomniekam, ar drošu dzēšanu, dzēšot nomnieku vai pārtraucot sesiju. |   1   | D/V  |
| 5.6.2 | Pārliecinieties, ka katrs API pieprasījums satur autentificētu nomnieka identifikatoru, kas kriptogrāfiski pārbaudīts pret sesijas kontekstu un lietotāja tiesībām.                                           |   1   | D/V  |
| 5.6.3 | Pārbaudiet, vai tīkla politikas īsteno noklusējuma aizlieguma noteikumus starp nomniekiem saziņai pakalpojumu tīklos un konteineru orkestrācijas platformās.                                                  |   2   |  D   |
| 5.6.4 | Pārbaudiet, vai šifrēšanas atslēgas ir unikālas katram nomniekam ar klienta pārvaldītu atslēgu (CMK) atbalstu un kriptogrāfisku izolāciju starp nomnieku datu krātuvēm.                                       |   3   |  D   |

---

## C5.7 Autonomā aģenta autorizācija

Kontrolēt AI aģentu un autonomo sistēmu piekļuves atļaujas, izmantojot ierobežotu spēju tokenus un pastāvīgu autorizāciju.

|   #   | Description                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Pārbaudiet, vai autonómie aģenti saņem ierobežotas iespēju marķierus, kuros skaidri uzskaitītas atļautās darbības, pieejamie resursi, laika ierobežojumi un darbības ierobežojumi.                                                    |   1   | D/V  |
| 5.7.2 | Pārbaudiet, ka augsta riska funkcionalitātes (failu sistēmas piekļuve, koda izpilde, ārējo API izsaukumi, finanšu darījumi) pēc noklusējuma ir atspējotas un prasa skaidras autorizācijas aktivizācijai kopā ar biznesa pamatojumiem. |   1   | D/V  |
| 5.7.3 | Pārliecinieties, ka kapacitātes žetoni ir sasaistīti ar lietotāju sesijām, ietver kriptogrāfisku integritātes aizsardzību un nodrošina, ka tos nav iespējams saglabāt vai atkārtoti izmantot bezsaistes scenārijos.                   |   2   |  D   |
| 5.7.4 | Pārbaudiet, vai aģenta iniciētās darbības tiek pakļautas sekundārai autorizācijai, izmantojot ABAC politikas dzinēju ar pilnīgu konteksta novērtējumu un audita reģistrēšanu.                                                         |   2   |  V   |
| 5.7.5 | Pārbaudiet, vai aģenta kļūdu nosacījumi un izņēmumu apstrāde ietver iespēju darbības jomas informāciju, lai atbalstītu incidentu analīzi un tiesu izmeklēšanu.                                                                        |   3   |  V   |

---

## Atsauces

### Standarti un ietvari

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Izpildes vadlīnijas

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Mākslīgā intelekta specifiskā drošība

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

