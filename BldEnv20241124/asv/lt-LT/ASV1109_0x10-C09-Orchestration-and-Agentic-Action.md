# 9 Autonominė koordinacija ir agentinė veiksmų sauga

## Valdymo tikslas

Užtikrinkite, kad autonominės arba daugiaagentės DI sistemos galėtų vykdyti tik tas veiklas, kurios yra aiškiai numatytos, autentifikuotos, audituojamos ir atitinka nustatytus kaštų bei rizikos ribinius nustatymus. Tai apsaugo nuo grėsmių, tokių kaip autonominės sistemos pažeidimas, įrankių piktnaudžiavimas, agentų ciklo aptikimas, komunikacijos užgrobimas, tapatybės klastojimas, spiečiaus manipuliavimas ir ketinimų manipuliavimas.

---

## 9.1 Agentų užduočių planavimo ir rekursijos biudžetai

Apribokite rekursyvų planų vykdymą ir priverstinai įveskite žmogaus patikrą privilegijuotoms veiksmams.

|   #   | Description                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Patikrinkite, ar maksimalus rekursijos gylis, pločio apribojimas, realaus laiko trukmė, žetonų skaičius ir piniginės sąnaudos už agento vykdymą yra centralizuotai sukonfigūruoti ir valdomi versijų kontrolės sistema. |   1   | D/V  |
| 9.1.2 | Patikrinkite, ar privilegijuoti arba negrįžtami veiksmai (pvz., kodo pateikimas, finansiniai pervedimai) prieš vykdymą reikalauja aiškaus žmogaus patvirtinimo per audituojamą kanalą.                                  |   1   | D/V  |
| 9.1.3 | Patikrinkite, ar realaus laiko išteklių stebėjimo įrankiai sukelia grandinės pertraukiklio nutraukimą, kai viršijamas bet kuris biudžeto slenkstis, sustabdant tolesnį užduočių plėtimą.                                |   2   |  D   |
| 9.1.4 | Patikrinkite, ar grandinės pertraukėjų įvykiai yra registruojami su agento ID, suveikimo sąlyga ir užfiksuota plano būsena teisinės apžiūros tikslais.                                                                  |   2   | D/V  |
| 9.1.5 | Patikrinkite, ar saugumo testai apima biudžeto išsekimo ir nekontroliuojamos plano vykdymo scenarijus, patvirtindami saugų sustabdymą be duomenų praradimo.                                                             |   3   |  V   |
| 9.1.6 | Patikrinkite, ar biudžeto politikos yra išreikštos kaip politika-kodas ir įgyvendinamos CI/CD, kad būtų užkirstas kelias konfigūracijos nukrypimams.                                                                    |   3   |  D   |

---

## 9.2 Įrankių papildinių izoliacija

Izoliuokite įrankių sąveikas, kad būtų užkirstas kelias neautorizuotam sistemos prieigai ar kodo vykdymui.

|   #   | Description                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Patikrinkite, ar kiekvienas įrankis/priedas veikia operacinėje sistemoje, konteineryje arba WASM lygmens smėlio dėžėje su minimalia privilegija teikiamomis failų sistemos, tinklo ir sistemos iškvietimų politikomis. |   1   | D/V  |
| 9.2.2 | Patikrinkite, ar yra užtikrinamas smėlio dėžės išteklių kvotų (CPU, atminties, disko, tinklo eigos) ir vykdymo laiko apribojimų taikymas bei jų registravimas.                                                         |   1   | D/V  |
| 9.2.3 | Patikrinkite, ar įrankių dvejetainiai failai arba aprašai yra skaitmeniškai pasirašyti; parašai turi būti patvirtinti prieš juos įkeliamant.                                                                           |   2   | D/V  |
| 9.2.4 | Patikrinkite, ar smėlio dėžės telemetrija siunčiama į SIEM; anomalijos (pvz., bandymai užmegzti išorinius ryšius) sukelia įspėjimus.                                                                                   |   2   |  V   |
| 9.2.5 | Patikrinkite, ar didelės rizikos papildiniai prieš diegiant gamyboje yra išbandomi pagal saugumo peržiūrą ir įsiskverbimo testavimą.                                                                                   |   3   |  V   |
| 9.2.6 | Patikrinkite, ar bandymai pabėgti iš smėlio dėžės automatiškai blokuojami, o pažeidžiantis įskiepį laikinas karantine tol, kol bus atlikta tyrimas.                                                                    |   3   | D/V  |

---

## 9.3 Autonominis ciklas ir sąnaudų ribojimas

Aptikite ir sustabdykite nekontroliuojamą agentų tarpusavio rekursiją ir kaštų išpūtimą.

|   #   | Description                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.3.1 | Patikrinkite, ar tarpiniai agentų kvietimai apima ribą skaičiui šuolių (hop-limit) arba gyvavimo laiką (TTL), kuriuos vykdymo laikas mažina ir kontroliuoja. |   1   | D/V  |
| 9.3.2 | Patikrinkite, ar agentai palaiko unikalų iškvietimų grafiko ID, kad būtų galima aptikti savęs iškvietimą arba ciklines schemas.                              |   2   |  D   |
| 9.3.3 | Patikrinkite, ar kaupiamieji skaičiavimo vienetų ir išlaidų skaitikliai sekami pagal užklausos grandinę; viršijus ribą grandinė nutraukiama.                 |   2   | D/V  |
| 9.3.4 | Patikrinkite, ar formali analizė arba modelio tikrinimas įrodo neribotos rekursijos nebuvimą agentų protokoluose.                                            |   3   |  V   |
| 9.3.5 | Patikrinkite, ar ciklo nutraukimo įvykiai sukelia įspėjimus ir tiekia nuolatinių patobulinimų metriką.                                                       |   3   |  D   |

---

## 9.4 Protokolo lygmens netinkamo naudojimo apsauga

Saugūs komunikacijos kanalai tarp agentų ir išorinių sistemų, siekiant užkirsti kelią užgrobimui ar manipuliavimui.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Patikrinkite, ar visi agento įrankiui ir agento agentui siunčiami pranešimai yra autentifikuoti (pvz., abipusio TLS arba JWT) ir užšifruoti nuo pradžios iki pabaigos. |   1   | D/V  |
| 9.4.2 | Patikrinkite, kad schemos būtų griežtai tikrinamos; nežinomi laukai ar neteisingai suformuoti pranešimai yra atmesti.                                                  |   1   |  D   |
| 9.4.3 | Patikrinkite, ar vientisumo tikrinimai (MAC arba skaitmeniniai parašai) apima visą žinutės turinį, įskaitant įrankio parametrus.                                       |   2   | D/V  |
| 9.4.4 | Patikrinkite, ar protokolo sluoksnyje yra užtikrinama pakartotinio paleidimo apsauga (naudojant unikalius skaitmeninius vienetus arba laiko žymių langus).             |   2   |  D   |
| 9.4.5 | Patikrinkite, ar protokolo įgyvendinimai yra tikrinami naudojant fuzz testavimą ir statinę analizę dėl injekcijos ar deserializacijos trūkumų.                         |   3   |  V   |

---

## 9.5 Agento tapatybė ir klastojimo poveikio įrodymas

Užtikrinkite, kad veiksmai būtų priskiriami ir pakeitimai aptinkami.

|   #   | Description                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Patikrinkite, ar kiekvienas agento egzempliorius turi unikalų kriptografinį identitetą (raktų porą arba aparatūros šaknis grindžiamą atpažinimą). |   1   | D/V  |
| 9.5.2 | Patikrinkite, ar visi agentų veiksmai yra pasirašyti ir pažymėti laiku; žurnaluose įtraukta parašas nepasigailėjimui užtikrinti.                  |   2   | D/V  |
| 9.5.3 | Patikrinkite, ar pakeitimų nepajėgiantys žurnalai saugomi pridedamame arba vienkartinio įrašymo terpėje.                                          |   2   |  V   |
| 9.5.4 | Patikrinkite, ar tapatybės raktai keičiasi pagal apibrėžtą grafiką ir esant kompromitacijos indikacijoms.                                         |   3   |  D   |
| 9.5.5 | Patikrinkite, ar klastojimo arba raktų konflikto bandymai sukelia paveikto agento nedelsiamą karantinavimą.                                       |   3   | D/V  |

---

## 9.6 Daugiaagentės spiečiaus rizikos mažinimas

Mažinti kolektyvinio elgesio pavojus izoliuojant ir naudojant formalią saugumo modeliavimą.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Patikrinkite, ar agentai, veikiantys skirtingose saugumo srityse, vykdomi izoliuotose laiko vykdymo smėlio dėžėse arba tinklo segmentuose.                        |   1   | D/V  |
| 9.6.2 | Patikrinkite, ar spiečių elgsena yra modeliuojama ir formaliai patvirtinama dėl gyvybingumo ir saugumo prieš diegiant.                                            |   3   |  V   |
| 9.6.3 | Patikrinkite, ar vykdymo metu veikiantys stebėtojai aptinka atsirandančius nesaugumo modelius (pvz., osciliacijas, užstrigimus) ir inicijuoja koregacinį veiksmą. |   3   |  D   |

---

## 9.7 Vartotojo ir įrankio autentifikacija / autorizacija

Įdiekite patikimą prieigos kontrolę kiekvienai agento inicijuotai veiklai.

|   #   | Description                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Patikrinkite, ar agentai autentifikuojasi kaip pagrindinės klasės subjektai žemutiniams sistemoms, niekada neprikartodami galutinių naudotojų kredencialų.            |   1   | D/V  |
| 9.7.2 | Patikrinkite, ar smulkiosios autorizacijos politikos riboja, kuriuos įrankius agentas gali iškviesti ir kokius parametrus gali pateikti.                              |   2   |  D   |
| 9.7.3 | Patikrinkite, ar privilegijų patikrinimai atliekami iš naujo kiekvieno kvietimo metu (nuolatinė autorizacija), o ne tik sesijos pradžioje.                            |   2   |  V   |
| 9.7.4 | Patikrinkite, ar deleguotos teisės automatiškai įgaliojamos pasibaigus galiojimo laikui ir reikalauja pakartotinio sutikimo po laiko pabaigos arba srities pakeitimo. |   3   |  D   |

---

## 9.8 Agentų tarpusavio komunikacijos saugumas

Užšifruokite ir užtikrinkite vientisumą visiems tarp agentų siunčiamiems pranešimams, kad būtų užkirstas kelias klausymuisi ir klastojimui.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Patikrinkite, ar agentų kanalams yra privaloma abipusė autentifikacija ir tobulai slaptas persiuntimo šifravimas (pvz., TLS 1.3).                       |   1   | D/V  |
| 9.8.2 | Patikrinkite, ar pranešimo vientisumas ir kilmė yra patvirtinti prieš apdorojimą; nesėkmės sukelia įspėjimus ir pranešimas yra atmestas.                |   1   |  D   |
| 9.8.3 | Patikrinkite, ar komunikacijos metaduomenys (laiko žymos, sekų numeriai) registruojami, siekiant užtikrinti forensinę atkūrimo galimybę.                |   2   | D/V  |
| 9.8.4 | Patikrinkite, ar formalioji patikra arba modelio tikrinimas patvirtina, kad protokolo būsenų mašinos negali būti paveiktos patekti į nesaugias būsenas. |   3   |  V   |

---

## 9.9 Ketinimų patvirtinimas ir apribojimų taikymas

Patikrinkite, ar agento veiksmai atitinka vartotojo nurodytą ketinimą ir sistemos apribojimus.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.9.1 | Patikrinkite, ar priešvykdymo apribojimų sprendėjai tikrina siūlomus veiksmus pagal įdiegtas saugos ir politikos taisykles.                                                                      |   1   |  D   |
| 9.9.2 | Patikrinkite, ar aukšto poveikio veiksmai (finansiniai, žalingi, privatumo jautrūs) reikalauja aiškaus ketinimų patvirtinimo iš inicijuojančio vartotojo.                                        |   2   | D/V  |
| 9.9.3 | Patikrinkite, ar po sąlygos patikros patvirtina, kad atlikti veiksmai pasiekė numatytus rezultatus be šalutinių poveikių; neatitikimai sukelia atitikmenų atšaukimą.                             |   2   |  V   |
| 9.9.4 | Patikrinkite, ar formalių metodų (pvz., modelių tikrinimo, teoreminio įrodymo) arba savybių pagrindu atliktų testų pagalba yra įrodyta, kad agentų planai atitinka visas paskelbtas apribojimus. |   3   |  V   |
| 9.9.5 | Patikrinkite, ar ketinimų neatitikimo arba apribojimų pažeidimų incidentai yra naudojami nuolatinio tobulinimo ciklams ir grėsmių žvalgybos dalijimuisi.                                         |   3   |  D   |

---

## 9.10 Agentų loginės strategijos saugumas

Saugus įvairių samprotavimo strategijų, įskaitant ReAct, Chain-of-Thought ir Tree-of-Thoughts metodų, parinkimas ir vykdymas.

|   #    | Description                                                                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Patikrinkite, ar sprendimų strategijos pasirinkimas remiasi deterministiniais kriterijais (įvesties sudėtingumas, užduoties tipas, saugumo kontekstas) ir ar identiškos įvestys toje pačioje saugumo kontekste sukuria identišką strategijos pasirinkimą. |   1   | D/V  |
| 9.10.2 | Patikrinkite, ar kiekviena samprotavimo strategija (ReAct, Chain-of-Thought, Tree-of-Thoughts) turi skirtą įvesties patikrinimą, išvesties valymą ir vykdymo laiko apribojimus, būdingus jos pažintinei metodikai.                                        |   1   | D/V  |
| 9.10.3 | Patikrinkite, ar samprotavimo strategijos perėjimai yra registruojami su išsamiu kontekstu, įskaitant įvesties charakteristikas, atrankos kriterijų reikšmes ir vykdymo metaduomenis, skirtus audito kelio rekonstrukcijai.                               |   2   | D/V  |
| 9.10.4 | Patikrinkite, ar „Mąstymo medžio“ (Tree-of-Thoughts) sprendimo procesas apima šakų apkarpymo mechanizmus, kurie nutraukia tyrinėjimą, kai nustatomi politikos pažeidimai, ištekliai apribojimai arba saugumo ribos.                                       |   2   | D/V  |
| 9.10.5 | Patikrinkite, ar ReAct (Reason-Act-Observe) ciklai apima patikros taškus kiekviename etape: samprotavimo žingsnio patvirtinimą, veiksmų autorizavimą ir stebėjimo išvalymą prieš tęsiant.                                                                 |   2   | D/V  |
| 9.10.6 | Patikrinkite, ar samprotavimo strategijos veikimo rodikliai (vykdymo laikas, išteklių naudojimas, išvesties kokybė) stebimi su automatizuotais įspėjimais, kai rodikliai nukrypsta už nustatytų ribinių verčių.                                           |   3   | D/V  |
| 9.10.7 | Patikrinkite, ar hibridiniai samprotavimo metodai, derinantys kelias strategijas, išlaiko visų sudedamųjų strategijų įvesties patikrinimą ir išvesties apribojimus, neperžengdami jokių saugumo kontrolės mechanizmų.                                     |   3   | D/V  |
| 9.10.8 | Patikrinkite, ar strategijos saugumo tikrinimas apima netaisyklingų įvesties duomenų siuntimą (fuzzing), priešiškus užklausimus, skirtus priversti strategiją keistis, ir ribinių sąlygų testavimą kiekvienam kognityviniam metodui.                      |   3   | D/V  |

---

## 9.11 Agentų gyvavimo ciklo valdymas ir saugumas

Saugus agento inicializavimas, būsenos pereinamieji etapai ir nutraukimas su kriptografiniais audito takais bei apibrėžtomis atkūrimo procedūromis.

|   #    | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Patikrinkite, ar agento inicializavimas apima kriptografinės tapatybės nustatymą naudojant aparatūros pagrindu veikiančius kredencialus ir nekintamus paleidimo audito įrašus, kuriuose yra agento ID, laiko žyma, konfigūracijos maišos reikšmė ir inicializavimo parametrai.   |   1   | D/V  |
| 9.11.2 | Patikrinkite, ar agento būsenos perėjimai yra kriptografiškai pasirašyti, pažymėti laiku ir įrašyti su visa konteksto informacija, įskaitant sužadinimo įvykius, ankstesnės būsenos hešą, naujos būsenos hešą ir atliktus saugumo patikrinimus.                                  |   2   | D/V  |
| 9.11.3 | Patikrinkite, ar agento išjungimo procedūros apima saugų atminties išvalymą naudojant kriptografinį naikinimą arba kelių praeigų perrašymą, kredencialų atšaukimą su sertifikavimo institucijos informavimu ir nepažeidžiamų nutraukimo pažymų sugeneravimą.                     |   2   | D/V  |
| 9.11.4 | Patikrinkite, ar agento atkūrimo mechanizmai tikrina būsenos vientisumą naudodami kriptografinius kontrolinius sumas (mažiausiai SHA-256) ir, aptikus korupciją, grąžina sistemą į žinomas geras būsenas su automatizuotais įspėjimais bei rankinio patvirtinimo reikalavimais.  |   3   | D/V  |
| 9.11.5 | Patikrinkite, ar agento nuolatinio saugojimo mechanizmai šifruoja jautrius būsenos duomenis naudodami kiekvienam agentui skirtus AES-256 raktus ir įgyvendina saugų raktų pasikeitimą pagal konfigūruojamus grafikus (maksimaliai kas 90 dienų) su diegimu be veiklos sutrikimų. |   3   | D/V  |

---

## 9.12 Įrankių integracijos saugumo sistema

Saugumo kontrolės dinamiškam įrankių įkėlimui, vykdymui ir rezultatų patvirtinimui, taikant apibrėžtus rizikos vertinimo ir patvirtinimo procesus.

|   #    | Description                                                                                                                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Patikrinkite, ar įrankių aprašikliai apima saugumo metaduomenis, nurodančius reikiamas teises (skaitymas/rašymas/vykdymas), rizikos lygius (žemas/vidutinis/aukštas), resursų ribas (CPU, atmintis, tinklas) ir validavimo reikalavimus, dokumentuotus įrankių manifestuose.          |   1   | D/V  |
| 9.12.2 | Patikrinkite, ar įrankio vykdymo rezultatai yra patvirtinti pagal numatytus schemas (JSON Schema, XML Schema) ir saugumo politiką (išvesties valymas, duomenų klasifikacija) prieš integruojant su laiko limitų ir klaidų valdymo procedūromis.                                       |   1   | D/V  |
| 9.12.3 | Patikrinkite, ar įrankių sąveikos žurnaluose yra pateikta išsami saugumo konteksto informacija, įskaitant privilegijų naudojimą, duomenų prieigos modelius, vykdymo laiką, išteklių suvartojimą ir grąžinimo kodus, naudojant struktūrizuotą žurnalavimą SIEM integracijai.           |   2   | D/V  |
| 9.12.4 | Patikrinkite, ar dinaminio įrankių įkėlimo mechanizmai patikrina skaitmeninius parašus, naudodami PKI infrastruktūrą, ir įgyvendina saugius įkėlimo protokolus su izoliuota aplinka (sandbox) bei leidimų patikrinimu prieš vykdymą.                                                  |   2   | D/V  |
| 9.12.5 | Patikrinkite, ar įrankių saugumo vertinimai automatiškai inicijuojami naujoms versijoms su privalomais patvirtinimo etapais, įskaitant statinę analizę, dinaminį testavimą ir saugumo komandos peržiūrą, kurių metu taikomi dokumentuoti patvirtinimo kriterijai ir SLA reikalavimai. |   3   | D/V  |

---

### Nuorodos

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

