# 9 Autonomā orķestrēšana un aģentiskā darbību drošība

## Kontroles mērķis

Nodrošiniet, ka autonomās vai daudzagentu mākslīgā intelekta sistēmas var veikt tikai tādas darbības, kas ir skaidri paredzētas, autentificētas, auditējamas un atbilst noteiktiem izmaksu un riska ierobežojumiem. Tas aizsargā pret draudiem, piemēram, autonomās sistēmas kompromitēšanu, rīku ļaunprātīgu izmantošanu, aģentu cilpu atklāšanu, komunikācijas pārņemšanu, identitātes viltošanu, bariņu manipulācijām un nodoma manipulācijām.

---

## 9.1 Aģenta uzdevumu plānošana un rekursijas budžets

Ierobežojiet rekursīvos plānus un noteikt cilvēka pārbaudes punktus privilēģētām darbībām.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Pārbaudiet, vai maksimālā rekursijas dziļuma, platuma, sienas pulksteņa laika, tokenu un naudas izmaksas katrai aģenta izpildei ir centrāli konfigurētas un versiju kontrolētas.                |   1   | D/V  |
| 9.1.2 | Pārliecināties, ka privileģētas vai neatgriezeniskas darbības (piemēram, koda apstiprinājumi, finanšu pārskaitījumi) prasa skaidru cilvēka apstiprinājumu caur auditable kanālu pirms izpildes. |   1   | D/V  |
| 9.1.3 | Pārliecinieties, ka reāllaika resursu monitori aktivizē ķēdes pārtraukuma pārtraukumu, kad tiek pārsniegts jebkāds budžeta slieksnis, apturot turpmāku uzdevuma paplašināšanu.                  |   2   |  D   |
| 9.1.4 | Pārbaudiet, vai ķēdes pārtraucēja notikumi tiek reģistrēti ar aģenta ID, izraisīšanas nosacījumu un noķerto plāna stāvokli tiesu ekspertīzes pārskatīšanai.                                     |   2   | D/V  |
| 9.1.5 | Pārbaudiet, vai drošības testi aptver budžeta izsīkuma un nekontrolētas plāna izpildes scenārijus, apstiprinot drošu apturēšanu bez datu zuduma.                                                |   3   |  V   |
| 9.1.6 | Pārliecinieties, ka budžeta politikas ir izteiktas kā koda politika un tiek īstenotas CI/CD, lai novērstu konfigurācijas novirzes.                                                              |   3   |  D   |

---

## 9.2 Rīka spraudņa izolēšana (sandboxing)

Izolēt rīku mijiedarbības, lai novērstu nesankcionētu piekļuvi sistēmai vai koda izpildi.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.2.1 | Pārliecinieties, ka katrs rīks/spraudnis izpildās operētājsistēmā, konteinerā vai WASM līmeņa smilšu kastē ar minimālas privilēģijas failu sistēmas, tīkla un sistēmas izsaukumu politiku. |   1   | D/V  |
| 9.2.2 | Pārliecinieties, ka smilškastes resursu kvotas (CPU, atmiņa, disks, tīkla izeja) un izpildes laika ierobežojumi tiek ievēroti un ierakstīti.                                               |   1   | D/V  |
| 9.2.3 | Pārliecinieties, ka rīku binārie faili vai apraksti ir digitāli parakstīti; paraksti tiek pārbaudīti pirms ielādes.                                                                        |   2   | D/V  |
| 9.2.4 | Pārbaudiet, vai smilšu kastes telemetrija plūst uz SIEM; novirzes (piemēram, mēģinājumi izveidot izejošas pieslēgumus) izsauc brīdinājumus.                                                |   2   |  V   |
| 9.2.5 | Pārbaudiet, vai augsta riska spraudņi tiek pakļauti drošības pārskatam un iekļūšanas testēšanai pirms ražošanas izvietošanas.                                                              |   3   |  V   |
| 9.2.6 | Pārbaudiet, vai smilšu kastes iziešanas mēģinājumi tiek automātiski bloķēti un pārkāpējs spraudnis tiek izolēts izmeklēšanas gaidīšanas laikā.                                             |   3   | D/V  |

---

## 9.3 Autonomais cikls un izmaksu ierobežošana

Atklājiet un apturiet nekontrolētu aģentu savstarpējas rekurences un izmaksu eksploziju.

|   #   | Description                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Pārbaudiet, vai starp aģentiem veiktajām izsaukumiem ir iekļauts hop-limit vai TTL, ko izpildes vide samazina un kontrolē.                                                       |   1   | D/V  |
| 9.3.2 | Pārliecinieties, ka aģenti uztur unikālu izsaukuma grafika ID, lai atklātu pašizsaukumus vai cikliskus modeļus.                                                                  |   2   |  D   |
| 9.3.3 | Pārbaudiet, vai kopsavilkuma skaitītāji par skaitļošanas vienībām un izdevumiem tiek izsekoti katram pieprasījuma ķēdes posmam; ja tiek pārsniegts limits, ķēde tiek pārtraukta. |   2   | D/V  |
| 9.3.4 | Pārbaudiet, vai formālā analīze vai modeļa pārbaude pierāda neierobežotas rekursijas neesamību aģentu protokolos.                                                                |   3   |  V   |
| 9.3.5 | Pārbaudiet, vai cilpas pārtraukšanas notikumi ģenerē brīdinājumus un nodrošina nepārtrauktas uzlabošanas metriku.                                                                |   3   |  D   |

---

## 9.4 Protokola līmeņa ļaunprātīgas izmantošanas aizsardzība

Droši komunikācijas kanāli starp aģentiem un ārējām sistēmām, lai novērstu pārtveršanu vai manipulāciju.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Pārliecinieties, ka visi ziņojumi no aģenta uz rīku un no aģenta uz aģentu ir autentificēti (piemēram, ar abpusēju TLS vai JWT) un ir nodrošināta gala līdz gala šifrēšana. |   1   | D/V  |
| 9.4.2 | Pārbaudiet, vai shēmas tiek stingri validētas; nezināmi lauki vai nederīgi ziņojumi tiek noraidīti.                                                                         |   1   |  D   |
| 9.4.3 | Pārbaudiet, vai integritātes pārbaudes (MAC vai digitālās parakstīšanas) aptver visu ziņojuma saturu, ieskaitot rīka parametrus.                                            |   2   | D/V  |
| 9.4.4 | Pārliecinieties, ka atkārtojuma aizsardzība (nonce vai laika zīmju logi) tiek ievērota protokola līmenī.                                                                    |   2   |  D   |
| 9.4.5 | Pārbaudiet, vai protokolu implementācijas tiek pakļautas fuzzināšanai un statiskajai analīzei, lai atklātu injekcijas vai deserializācijas kļūdas.                          |   3   |  V   |

---

## 9.5 Aģenta identitāte un manipulāciju pierādījumi

Nodrošiniet, ka darbības ir izsekojamas un izmaiņas atklājamas.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Pārliecinieties, ka katram aģenta eksemplāram ir unikāla kriptogrāfiska identitāte (atslēgu pāris vai aparatūras sakņota akreditācija).               |   1   | D/V  |
| 9.5.2 | Pārbaudiet, vai visas aģentu darbības ir parakstītas un laika zīmētas; žurnālos iekļauts paraksts, lai nodrošinātu noraidīšanas neesamību.            |   2   | D/V  |
| 9.5.3 | Pārliecinieties, ka manipulācijām izturīgi žurnāli tiek glabāti tikai pievienošanas režīmā vai rakstīšanas reģistrā, kas atļauj vienreizēju ierakstu. |   2   |  V   |
| 9.5.4 | Pārbaudiet, vai identitātes atslēgas tiek pārslēgtas noteiktā grafikā un kompromisa rādītāju gadījumā.                                                |   3   |  D   |
| 9.5.5 | Pārbaudiet, vai viltojuma vai atslēgu konflikta mēģinājumi nekavējoties izraisīja skartā aģenta karantīnu.                                            |   3   | D/V  |

---

## 9.6 Daudzu aģentu spārna riska mazināšana

Samaziniet kolektīvās uzvedības riskus, izmantojot izolāciju un formālu drošības modelēšanu.

|   #   | Description                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.6.1 | Pārliecinieties, ka aģenti, kas darbojas dažādās drošības domēnās, izpilda izolētās darbības laikā darbināmās smilšu kastēs vai tīkla segmentēs. |   1   | D/V  |
| 9.6.2 | Pārliecinieties, ka spiediena uzvedība ir modelēta un formāli pārbaudīta dzīvotspējai un drošībai pirms izvietošanas.                            |   3   |  V   |
| 9.6.3 | Pārbaudiet, vai izpildes uzraudzības ierīces atklāj jaunas bīstamas parādības (piemēram, svārstības, bloķēšanās) un uzsāk korektīvus pasākumus.  |   3   |  D   |

---

## 9.7 Lietotāja un rīka autentifikācija / autorizācija

Ieviesiet stingru piekļuves kontroli katrai aģenta aktivizētai darbībai.

|   #   | Description                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Pārliecinieties, ka aģenti autentificējas kā pirmšķiras principi uz lejuplūdes sistēmām, nekad neatkārtoti neizmantojot gala lietotāja pilnvaras. |   1   | D/V  |
| 9.7.2 | Pārbaudiet, vai smalki regulētas autorizācijas politikas ierobežo, kurus rīkus aģents var aktivizēt un kādus parametrus tas var norādīt.          |   2   |  D   |
| 9.7.3 | Pārbaudiet, vai privilēģiju pārbaudes tiek pārvērtētas katrā izsaukumā (pastāvīga autorizācija), ne tikai sesijas sākumā.                         |   2   |  V   |
| 9.7.4 | Pārliecinieties, ka deleģētās privilēģijas automātiski beidzas un pēc laika beigām vai domēna izmaiņām ir nepieciešama atkārtota piekrišana.      |   3   |  D   |

---

## 9.8 Aģenta uz aģentu saziņas drošība

Šifrējiet un nodrošiniet visu starp aģentiem sūtīto ziņu integritāti, lai novērstu noklausīšanos un manipulācijas.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Pārbaudiet, vai aģentu kanāliem ir obligāta savstarpējā autentifikācija un pilnīgi uz priekšu droša šifrēšana (piemēram, TLS 1.3).           |   1   | D/V  |
| 9.8.2 | Pārliecinieties, ka pirms apstrādes tiek pārbaudīta ziņojuma integritāte un izcelsme; kļūmes izraisīs brīdinājumus un ziņojuma noraidīšanu.  |   1   |  D   |
| 9.8.3 | Pārbaudiet, vai komunikācijas metadati (laika zīmogi, secības numuri) tiek reģistrēti, lai atbalstītu forensisko atjaunošanu.                |   2   | D/V  |
| 9.8.4 | Pārbaudiet, vai formālā verifikācija vai modeļa pārbaude apstiprina, ka protokola stāvokļu mašīnas nevar tikt novirzītas nedrošos stāvokļos. |   3   |  V   |

---

## 9.9 Nodoma pārbaude un ierobežojumu ievērošana

Pārbaudiet, vai aģenta darbības atbilst lietotāja izteiktajam nodomam un sistēmas ierobežojumiem.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Pārliecinieties, ka iepriekšējās izpildes ierobežojumu risinātāji pārbauda piedāvātās darbības atbilstoši stingri noteiktajām drošības un politikas prasībām.              |   1   |  D   |
| 9.9.2 | Pārbaudiet, vai darbības ar lielu ietekmi (finansiālas, destruktīvas, ar privātuma aizsardzību saistītas) prasa skaidru apstiprinājumu no darbību veicošā lietotāja.       |   2   | D/V  |
| 9.9.3 | Pārbaudiet, vai pēcpārbaudes nosacījumi apstiprina, ka pabeigtās darbības sasniedza paredzētos rezultātus bez blakus efektiem; neatbilstības izraisīs atcelšanu.           |   2   |  V   |
| 9.9.4 | Pārbaudiet, vai formālās metodes (piemēram, modeļu pārbaude, teorēmu pierādīšana) vai īpašību balstīti testi pierāda, ka aģentu plāni atbilst visām deklarētajām prasībām. |   3   |  V   |
| 9.9.5 | Pārliecinieties, ka nolūka neatbilstības vai ierobežojumu pārkāpumu incidenti tiek izmantoti nepārtrauktas uzlabošanas ciklos un draudu informācijas apmaiņā.              |   3   |  D   |

---

## 9.10 Aģentu izpētes stratēģijas drošība

Droša dažādu spriešanas stratēģiju izvēle un izpilde, ieskaitot ReAct, Chain-of-Thought un Tree-of-Thoughts pieejas.

|   #    | Description                                                                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Pārbaudiet, vai spriešanas stratēģijas izvēle izmanto determinētus kritērijus (ievades sarežģītība, uzdevuma veids, drošības konteksts) un vai identiskas ievades rada identiskas stratēģijas izvēles tajā pašā drošības kontekstā.      |   1   | D/V  |
| 9.10.2 | Pārliecinieties, ka katrai secināšanas stratēģijai (ReAct, Chain-of-Thought, Tree-of-Thoughts) ir paredzēta ieejas datu validācija, izejas datu sanitizācija un izpildes laika ierobežojumi, kas ir specifiski tās kognitīvajai pieejai. |   1   | D/V  |
| 9.10.3 | Pārliecinieties, ka iemeslošanas stratēģiju pārejas tiek reģistrētas ar pilnīgu kontekstu, tostarp ievades raksturojumiem, atlases kritēriju vērtībām un izpildes metadatiem, lai nodrošinātu audita ceļa atjaunošanu.                   |   2   | D/V  |
| 9.10.4 | Pārbaudiet, vai Tree-of-Thoughts spriešana ietver zaru apgriešanas mehānismus, kas pārtrauc izpēti, kad tiek konstatētas politikas pārkāpšanas, resursu ierobežojumi vai drošības robežas.                                               |   2   | D/V  |
| 9.10.5 | Pārliecinieties, ka ReAct (Iemeslojums-Darbība-Novērošana) cikli ietver validācijas punktus katrā posmā: iepriekšējā soļa pārbaudi, darbības autorizāciju un novērojuma attīrīšanu pirms turpināšanas.                                   |   2   | D/V  |
| 9.10.6 | Pārliecinieties, ka sprieduma stratēģijas veiktspējas metri (izpildes laiks, resursu izmantošana, izvades kvalitāte) tiek uzraudzīti ar automatizētiem brīdinājumiem, kad metri novirzās ārpus konfigurētajām robežvērtībām.             |   3   | D/V  |
| 9.10.7 | Pārbaudiet, vai jauktās spriešanas pieejas, kas apvieno vairākas stratēģijas, uztur visu sastāvdaļu stratēģiju ievaddatu pārbaudi un izejas ierobežojumus, nepārkāpjot nevienu drošības kontroli.                                        |   3   | D/V  |
| 9.10.8 | Pārbaudiet, vai apziņas stratēģijas drošības testēšana ietver fuzingus ar nepareiziem ievaddatiem, pretinieciskiem uzvednēm, kas paredzētas stratēģijas maiņas piespiedšanai, un robežnosacījumu testēšanu katrai kognitīvajai pieejai.  |   3   | D/V  |

---

## 9.11 Aģenta Dzīves cikla stāvokļu pārvaldība un drošība

Droša aģenta inicializācija, stāvokļa pārejas un terminācija ar kriptogrāfiskām audita pēdām un definētām atkopšanas procedūrām.

|   #    | Description                                                                                                                                                                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Pārbaudiet, vai aģenta inicializācija ietver kriptogrāfiskās identitātes izveidi ar aparatūras atbalstītām akreditācijām un nemaināmām sākotnējās pārbaudes žurnālu ierakstiem, kuros ir iekļauts aģenta ID, laika zīmogs, konfigurācijas hašs un inicializācijas parametri.                                        |   1   | D/V  |
| 9.11.2 | Pārliecinieties, ka aģenta stāvokļa pārejas ir kriptogrāfiski parakstītas, laikspiedola atzīmētas un žurnālfailā ierakstītas ar pilnīgu kontekstu, ieskaitot izraisījošos notikumus, iepriekšējā stāvokļa hašu, jaunā stāvokļa hašu un veiktās drošības validācijas.                                                |   2   | D/V  |
| 9.11.3 | Pārliecinieties, ka aģenta izslēgšanas procedūras ietver drošu atmiņas dzēšanu, izmantojot kriptogrāfisko dzēšanu vai vairākkārtēju pārrakstīšanu, akreditācijas datu atsaukšanu ar sertifikācijas iestādes paziņošanu, kā arī nelikumīgas iejaukšanās pierādījumus sniedzošu pārtraukšanas sertifikātu ģenerēšanu. |   2   | D/V  |
| 9.11.4 | Pārbaudiet, vai aģentu atkopšanas mehānismi validē stāvokļa integritāti, izmantojot kriptogrāfiskos kontrolsummas (vismaz SHA-256), un veic atgriešanos pie zināmi labiem stāvokļiem, kad tiek konstatēta bojājuma koriģēšana ar automatizētām brīdinājuma sistēmām un manuālu apstiprinājumu prasībām.             |   3   | D/V  |
| 9.11.5 | Pārbaudiet, vai aģentu saglabāšanas mehānismi šifrē sensitīvos stāvokļa datus ar katram aģentam atšķirīgām AES-256 atslēgām un īsteno drošu atslēgu rotāciju konfigurējamos grafikā (līdz 90 dienām) ar nulles dīkstāves izvēršanu.                                                                                 |   3   | D/V  |

---

## 9.12 Rīku integrācijas drošības struktūra

Drošības kontroles dinamiskai rīku ielādei, izpildei un rezultātu validācijai ar definētiem riska novērtējuma un apstiprināšanas procesiem.

|   #    | Description                                                                                                                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Pārliecinieties, ka instrumentu aprakstos iekļauts drošības metadati, kas norāda nepieciešamās privilēģijas (lasīšana/rakstīšana/izpilde), riska līmeņus (zems/vidējs/augsts), resursu ierobežojumus (CPU, atmiņa, tīkls) un validācijas prasības, kas dokumentētas instrumentu manifestos. |   1   | D/V  |
| 9.12.2 | Pārbaudiet, vai rīka izpildes rezultāti tiek validēti pret gaidītajiem shēmām (JSON shēma, XML shēma) un drošības politikām (izvades sanitizācija, datu klasifikācija) pirms integrācijas, ievērojot taimeru ierobežojumus un kļūdu apstrādes procedūras.                                   |   1   | D/V  |
| 9.12.3 | Pārbaudiet, vai rīku mijiedarbības žurnāli ietver detalizētu drošības kontekstu, tostarp privilēģiju izmantošanu, datu piekļuves modeļus, izpildes laiku, resursu patēriņu un atgriešanas kodus ar strukturētu žurnālu veidošanu SIEM integrācijai.                                         |   2   | D/V  |
| 9.12.4 | Pārliecinieties, ka dinamiskās rīku ielādes mehānismi pārbauda digitālos parakstus, izmantojot PKI infrastruktūru, un īsteno drošas ielādes protokolus ar smilšu kastes izolāciju un atļauju verifikāciju pirms izpildes.                                                                   |   2   | D/V  |
| 9.12.5 | Pārbaudiet, vai rīka drošības novērtējumi tiek automātiski aktivizēti jauniem versijām ar obligātiem apstiprināšanas posmiem, kas ietver statisko analīzi, dinamisko testēšanu un drošības komandas pārskatu ar dokumentētiem apstiprināšanas kritērijiem un SLA prasībām.                  |   3   | D/V  |

---

### Atsauces

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

