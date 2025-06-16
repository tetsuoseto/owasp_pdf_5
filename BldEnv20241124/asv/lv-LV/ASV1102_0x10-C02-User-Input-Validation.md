# C2 Lietotāja ievades validācija

## Kontroles mērķis

Lietotāja ievades stingra validācija ir pirmās līnijas aizsardzība pret dažiem no vissmagākajiem uzbrukumiem AI sistēmām. Uzbrukumi, kas izmanto promptu injekciju, var pārrakstīt sistēmas instrukcijas, nopludināt sensitīvus datus vai novirzīt modeli uz aizliegtu uzvedību. Ja nav ieviesti speciāli filtri un instrukciju hierarhijas, pētījumi rāda, ka "multi-shot" jailbreaks, kas izmanto ļoti garus konteksta logus, būs efektīvi. Tāpat smalki pretinieku manipulāciju uzbrukumi—piemēram, homoglifas aizvietojumi vai leetspeak—var klusējot mainīt modeļa lēmumus.

---

## C2.1 Uzvedības injekcijas aizsardzība

Priekšmeta injekcija ir viens no lielākajiem riskiem mākslīgā intelekta sistēmām. Aizsardzība pret šo taktiku izmanto statisku paraugu filtru, dinamisku klasificētāju un instrukciju hierarhijas ievērošanas kombināciju.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Pārliecinieties, ka lietotāja ievades tiek pārbaudītas pret nepārtraukti atjauninātu zināmu uzvednes injekciju paraugu bibliotēku (jailbreak atslēgvārdi, "neklausīt iepriekšējo", lomu spēles ķēdes, netiešas HTML/URL uzbrukumi).        |   1   | D/V  |
| 2.1.2 | Pārbaudiet, vai sistēma ievēro instrukciju hierarhiju, kurā sistēmas vai izstrādātāja ziņojumi pārraksta lietotāja instrukcijas, pat pēc konteksta loga paplašināšanas.                                                                    |   1   | D/V  |
| 2.1.3 | Pārliecināties, ka pretinieciski novērtēšanas testi (piemēram, Red Team "daudzuzdevumu" uzvednes) tiek veikti pirms katras modeļa vai uzvednes veidnes izlaišanas, ar panākumu likmju sliekšņiem un automatizētiem bloķētājiem regresijām. |   2   | D/V  |
| 2.1.4 | Pārliecinieties, ka trešo pušu satura (tīmekļa lapu, PDF failu, e-pastu) izcelsmes aicinājumi tiek sanitizēti izolētā parsēšanas kontekstā, pirms tie tiek salikti kopā ar galveno aicinājumu.                                             |   2   |  D   |
| 2.1.5 | Pārbaudiet, vai visi uzvednes filtra noteikumu atjauninājumi, klasifikatora modeļa versijas un bloķēšanas saraksta izmaiņas ir versiju kontrolētas un auditable.                                                                           |   3   | D/V  |

---

## C2.2 Pretestēšanas piemēru noturība

Dabiskās valodas apstrādes (NLP) modeļi joprojām ir pakļauti smalkām rakstzīmju vai vārdu līmeņa izmaiņām, kuras cilvēki bieži nepamana, bet modeļi mēdz kļūdaini klasificēt.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Pārliecinieties, ka pamata ievades normalizācijas soļi (Unicode NFC, homoglifmu kartēšana, tukšu vietu apgriešana) tiek veikti pirms tokenizācijas.                                                                   |   1   |  D   |
| 2.2.2 | Pārbaudiet, vai statistiskā anomāliju atklāšana atzīmē ievades ar neparasti augstu rediģēšanas attālumu līdz valodas normām, pārmērīgi atkārtotiem tokeniem vai anomāliem iegultās reprezentācijas attālumiem.        |   2   | D/V  |
| 2.2.3 | Pārbaudiet, vai inferenču caurule atbalsta izvēles kārtībā pretdarbības mācīšanas cietinātas modeļa variācijas vai aizsardzības slāņus (piemēram, nejaušināšanu, aizsargājošu destilāciju) augsta riska galapunktiem. |   2   |  D   |
| 2.2.4 | Pārbaudiet, vai aizdomīgie pretinieka ievadi ir izolēti un reģistrēti ar pilniem datu payloadiem (pēc personas identifikācijas datu (PII) aizsegšanas).                                                               |   2   |  V   |
| 2.2.5 | Pārliecinieties, ka robustuma metrikas (zināmu uzbrukumu komplektu veiksmes rādītāji) tiek uzraudzītas laika gaitā un regresijas izsauc izlaiduma bloķētāju.                                                          |   3   | D/V  |

---

## C2.3 Shēmas, datu tipa un garuma validācija

AI uzbrukumi, kas izmanto nederīgus vai pārmērīgi lielus ievades datus, var izraisīt analizēšanas kļūdas, uzvednes pārliešanu starp laukiem un resursu izsīkšanu. Stingra shēmas ievērošana ir arī priekšnoteikums, veicot deterministisku rīku izsaukumus.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Pārliecinieties, ka katrs API vai funkciju izsaukuma gala punkts definē skaidru ievades shēmu (JSON shēmu, Protobuf vai multimodālu ekvivalentu) un ka ievades tiek validētas pirms prompta sastādīšanas. |   1   |  D   |
| 2.3.2 | Pārliecinieties, ka ievades, kas pārsniedz maksimālo tokenu vai baitu ierobežojumu, tiek noraidītas ar drošu kļūdas ziņu un nekad netiek klusējot saīsinātas.                                             |   1   | D/V  |
| 2.3.3 | Pārliecinieties, ka tipu pārbaudes (piemēram, skaitliskie diapazoni, enum vērtības, MIME tipi attēliem/audio) tiek īstenotas servera pusē, ne tikai klienta kodā.                                         |   2   | D/V  |
| 2.3.4 | Pārbaudiet, vai semantiskie validatori (piemēram, JSON shēma) darbojas konstanta laika režīmā, lai novērstu algoritmisko pakalpojumu atteices uzbrukumu (DoS).                                            |   2   |  D   |
| 2.3.5 | Pārliecinieties, ka validācijas kļūdas tiek reģistrētas ar anonimizētiem saņēmēja fragmentiem un nepārprotamiem kļūdu kodiem, lai atvieglotu drošības trieciena novēršanu.                                |   3   |  V   |

---

## C2.4 Saturs un politikas pārbaude

Izstrādātājiem jāspēj atpazīt sintaktiski derīgus pieprasījumus, kas lūdz aizliegtu saturu (piemēram, nelikumīgas instrukcijas, naida runu un autortiesību aizsargātu tekstu), un novērst to izplatīšanos.

|   #   | Description                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.4.1 | Pārbaudiet, vai satura klasifikators (bez uzlabošanas vai ar uzlabošanu) novērtē katru ievadi pēc vardarbības, pašsavainošanās, naida, seksuāla satura un nelikumīgām prasībām, ar konfigurējamām sliekšņvērtībām. |   1   |  D   |
| 2.4.2 | Pārbaudiet, ka ieejas dati, kas pārkāpj politiku, saņems standartizētas atteikšanās vai drošas pabeigšanas, lai tie netiktu nodoti tālākām LLM izsaukumiem.                                                        |   1   | D/V  |
| 2.4.3 | Pārbaudiet, vai atlases modelis vai noteikumu kopums tiek pārmācīts/atjaunināts vismaz reizi ceturksnī, iekļaujot jaunākās novērotās izvairīšanās no drošības vai politikas apešanas shēmas.                       |   2   |  D   |
| 2.4.4 | Pārbaudiet, vai izvērtēšana ievēro lietotājam specifiskas politikas (vecums, reģionālie juridiskie ierobežojumi) ar atribūtu balstītām noteikumu sistēmām, kuras tiek izšķirtas pieprasījuma laikā.                |   2   |  D   |
| 2.4.5 | Pārbaudiet, vai skrīninga žurnālos ir iekļauti klasifikatora pārliecības rādītāji un politikas kategoriju birkas SOC korelācijai un nākotnes sarkanās komandas atkārtošanai.                                       |   3   |  V   |

---

## C2.5 Ievades ātruma ierobežošana un ļaunprātīgas izmantošanas novēršana

Izstrādātājiem jānovērš ļaunprātīga izmantošana, resursu izsīkšana un automatizētas uzbrukumu pret mākslīgā intelekta sistēmām, ierobežojot ievades ātrumu un atklājot anomālas lietošanas modeļus.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Pārbaudiet, vai visiem ieejas galapunktiem ir piemēroti ātruma ierobežojumi uz lietotāju, IP adresi un API atslēgu.                                                       |   1   | D/V  |
| 2.5.2 | Pārbaudiet, vai sprādziena un pastāvīgie ātruma ierobežojumi ir noregulēti tā, lai novērstu pakalpojumu atteices (DoS) un brutālas spēka uzbrukumus.                      |   2   | D/V  |
| 2.5.3 | Pārbaudiet, vai anomālas lietošanas shēmas (piemēram, ātras un atkārtotas pieprasījumu sūtīšanas, ievades pārslogošana) izraisa automatizētas bloķēšanas vai eskalācijas. |   2   | D/V  |
| 2.5.4 | Pārliecinieties, ka ļaunprātīgas darbības novēršanas žurnāli tiek saglabāti un pārskatīti, lai identificētu jaunas uzbrukumu zīmējumus.                                   |   3   |  V   |

---

## C2.6 Daudzmoduāla ievades validācija

Mākslīgā intelekta sistēmām jāiekļauj stingra validācija neteksta ievadēm (attēliem, audio, failiem), lai novērstu ievadi, izvairīšanos vai resursu ļaunprātīgu izmantošanu.

|   #   | Description                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.6.1 | Pārliecinieties, ka visi neteksta ievades dati (attēli, audio, faili) tiek pārbaudīti pēc veida, lieluma un formāta pirms apstrādes. |   1   |  D   |
| 2.6.2 | Pārliecinieties, ka faili tiek skenēti, vai tajos nav ļaunprātīgas programmatūras un steganogrāfisku datu, pirms to uzņemšanas.      |   2   | D/V  |
| 2.6.3 | Pārbaudiet, vai attēlu/audio ievades ir pārbaudītas pret pretinieciskiem traucējumiem vai zināmām uzbrukuma shēmām.                  |   2   | D/V  |
| 2.6.4 | Pārbaudiet, vai kļūmes daudzmodu ievades validācijā tiek reģistrētas un izraisa brīdinājumus izmeklēšanai.                           |   3   |  V   |

---

## C2.7 Ievades avots un atribūcija

AI sistēmas būtu jāatbalsta audita veikšanai, ļaunprātīgas izmantošanas izsekošanai un atbilstības nodrošināšanai, uzraugot un atzīmējot visu lietotāju ievades avotus.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Pārliecinieties, ka visi lietotāja ievadi tiek atzīmēti ar metadatiem (lietotāja ID, sesija, avots, laika zīmogs, IP adrese) uzņemšanas brīdī. |   1   | D/V  |
| 2.7.2 | Pārbaudiet, vai avota metadati tiek saglabāti un ir auditējami visiem apstrādātajiem ievades datiem.                                           |   2   | D/V  |
| 2.7.3 | Pārbaudiet, vai anomālie vai neuzticamie ieejas avoti tiek atzīmēti un pakļauti pastiprinātai pārbaudei vai bloķēšanai.                        |   2   | D/V  |

---

## C2.8 Reāllaika adaptīvā draudu noteikšana

Izstrādātājiem jāizmanto modernas draudu noteikšanas sistēmas mākslīgajam intelektam, kas pielāgojas jauniem uzbrukuma modeļiem un nodrošina reāllaika aizsardzību ar kompilētas paraugu saskaņošanas palīdzību.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Pārliecinieties, ka draudu atpazīšanas modeļi ir apkopoti optimizētās regex dzinējos, lai nodrošinātu augstas veiktspējas reāllaika filtrēšanu ar minimālu latentuma ietekmi.                                          |   1   | D/V  |
| 2.8.2 | Pārliecinieties, ka draudu noteikšanas sistēmām ir atsevišķas modeļu bibliotēkas dažādām draudu kategorijām (uzvedības injekcija, kaitīgs saturs, sensitīvi dati, sistēmas komandas).                                  |   1   | D/V  |
| 2.8.3 | Pārbaudiet, vai adaptīvā draudu noteikšana iekļauj mašīnmācīšanās modeļus, kas atjaunina draudu jutīgumu, pamatojoties uz uzbrukumu biežumu un panākumu rādītājiem.                                                    |   2   | D/V  |
| 2.8.4 | Pārbaudiet, vai reāllaika draudu izlūkošanas plūsmas automātiski atjaunina modeļu bibliotēkas ar jauniem uzbrukuma parakstiem un IOC (compromisa rādītājiem).                                                          |   2   | D/V  |
| 2.8.5 | Pārbaudiet, vai draudu noteikšanas kļūdaini pozitīvo gadījumu līmeņi tiek nepārtraukti uzraudzīti un vai rakstura specifiskums tiek automātiski pielāgots, lai samazinātu traucējumus likumīgām lietošanas situācijām. |   3   | D/V  |
| 2.8.6 | Pārbaudiet, vai kontekstuālā draudu analīze ņem vērā ievades avotu, lietotāja uzvedības modeļus un sesijas vēsturi, lai uzlabotu atklāšanas precizitāti.                                                               |   3   | D/V  |
| 2.8.7 | Pārliecinieties, ka draudu atklāšanas veiktspējas rādītāji (atklāšanas līmenis, apstrādes latentums, resursu izmantošana) tiek uzraudzīti un optimizēti reālajā laikā.                                                 |   3   | D/V  |

---

## C2.9 Daudzmodu drošības validācijas caurule

Izstrādātājiem jānodrošina drošības validācija teksta, attēlu, audio un citām mākslīgā intelekta ievades modalitātēm, izmantojot specifisku draudu noteikšanu un resursu izolāciju.

|   #   | Description                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Pārliecinieties, ka katrai ieejas modālai ir piešķirti drošības validatori ar dokumentētām apdraudējumu modeļiem (teksts: prompta injekcija, attēli: steganogrāfija, audio: spektrogrammas uzbrukumi) un noteiktām atklāšanas robežām.                                              |   1   | D/V  |
| 2.9.2 | Pārliecinieties, ka daudzmodu ievades tiek apstrādātas izolētās smilškastes ar noteiktiem resursu ierobežojumiem (atmiņa, CPU, apstrādes laiks), kas specifiski katram modālitātes tipam un dokumentēti drošības politikās.                                                         |   2   | D/V  |
| 2.9.3 | Pārliecinieties, ka starpmodalitātes uzbrukumu atklāšana identificē koordinētus uzbrukumus, kas pārsniedz vairākus ievades tipus (piemēram, steganogrāfiskas slodzes attēlos kombinācijā ar teksta uzvedņu injekciju), izmantojot korelācijas noteikumus un brīdinājumu ģenerēšanu. |   2   | D/V  |
| 2.9.4 | Pārbaudiet, vai daudzmoduālas validācijas kļūmes izraisīja detalizētu žurnālu veidošanu, ieskaitot visas ievades modalitātes, validācijas rezultātus, draudu vērtējumus un korelācijas analīzi ar strukturētiem žurnālu formātiem SIEM integrācijai.                                |   3   | D/V  |
| 2.9.5 | Pārliecinieties, ka modality-specifiskie satura klasifikatori tiek atjaunināti saskaņā ar dokumentētajiem grafikiem (vismaz reizi ceturksnī) ar jaunām draudu shēmām, pretinieciskiem piemēriem un veiktspējas etaloniem, kas saglabāti virs bāzes līmeņa sliekšņiem.               |   3   | D/V  |

---

## Atsauces

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

