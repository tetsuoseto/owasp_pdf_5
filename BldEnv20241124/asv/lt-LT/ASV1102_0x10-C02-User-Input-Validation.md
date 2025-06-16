# C2 naudotojo įvesties validacija

## Valdymo tikslas

Tvirtas vartotojo įvesties patikrinimas yra pirmoji gynybos linija nuo kai kurių labiausiai žalingų išpuolių prieš DI sistemas. Komandų įpurškimo atakos gali pakeisti sistemos instrukcijas, nutekinti konfidencialius duomenis arba nukreipti modelį į neleistiną elgesį. Jei nėra įdiegtos specialios filtrų sistemos ir instrukcijų hierarchijos, tyrimai rodo, kad „daugiapakopiai“ jailbreak atakos, naudojančios labai ilgus konteksto langus, bus veiksmingos. Taip pat subtilios priešiškos trikdžių atakos — tokios kaip homoglifų pakeitimai arba leetspeak — gali tyliai pakeisti modelio sprendimus.

---

## C2.1 Užklausų injekcijos apsauga

Užklausų įterpimas (prompt injection) yra viena iš didžiausių rizikų dirbtinės intelekto (DI) sistemoms. Gynybos priemonės prieš šią taktiką taiko statinių šablonų filtrų, dinamiškų klasifikatorių ir instrukcijų hierarchijos vykdymo derinį.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Patikrinkite, ar vartotojo įvestys yra tikrinamos pagal nuolat atnaujinamą žinomų užklausų injekcijos šablonų (kalėjimo raktiniai žodžiai, „ignoruoti ankstesnį“, vaidmenų grandinės, netiesioginiai HTML/URL išpuoliai) biblioteką. |   1   | D/V  |
| 2.1.2 | Patikrinkite, ar sistema užtikrina instrukcijų hierarchiją, kurioje sistemos arba kūrėjo žinutės viršija vartotojo instrukcijas, net ir išplėtus konteksto langą.                                                                    |   1   | D/V  |
| 2.1.3 | Patikrinkite, ar kiekvieno modelio ar šablono išleidimo metu atliekami priešpriešiniai vertinimo testai (pvz., Red Team „daugiapakopiai“ komandų raginimai), nustatant sėkmės rodiklio ribas ir automatinio regresijos blokatorius.  |   2   | D/V  |
| 2.1.4 | Patikrinkite, ar trečiųjų šalių turinio (internetinių svetainių, PDF failų, el. laiškų) kilę užklausų tekstai yra išvalomi izoliuoto analizės konteksto metu prieš sujungiami į pagrindinę užklausą.                                 |   2   |  D   |
| 2.1.5 | Patikrinkite, ar visos atnaujinamos užklausų filtrų taisyklės, klasifikatoriaus modelių versijos ir blokavimo sąrašų pakeitimai yra valdomi versijomis ir audituojami.                                                               |   3   | D/V  |

---

## C2.2 Priešinimasis priešiškiems pavyzdžiams

Natūralios kalbos apdorojimo (NLP) modeliai vis dar yra pažeidžiami subtilių simbolių ar žodžių lygmens trikdžių, kurių žmonės dažnai nepastebi, tačiau modeliai linkę klaidingai klasifikuoti.

|   #   | Description                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Patikrinkite, ar pagrindiniai įvesties normalizavimo veiksmai (Unicode NFC, homoglifų žemėlapis, tarpų apkarpymas) atliekami prieš žodžių skaidymą.                                                                          |   1   |  D   |
| 2.2.2 | Patikrinkite, ar statistinės anomalijų aptikimo sistemos žymi įvestis, turinčias neįprastai didelį redagavimo atstumą nuo kalbos normų, perteklinius pasikartojančius žetonus arba nenormalius įterpimo atstumus.            |   2   | D/V  |
| 2.2.3 | Patikrinkite, ar išvadų srautas palaiko pasirenkamus modelio variantus, sustiprintus priešiškumo mokymu arba apsauginiais sluoksniais (pvz., atsitiktinumo taikymą, gynybinę distiliaciją) aukštos rizikos galinėms taškams. |   2   |  D   |
| 2.2.4 | Patikrinkite, ar įtariami priešiški įėjimai yra karantine, registruojami su pilnais duomenų paketais (po asmeninės identifikavimo informacijos pašalinimo).                                                                  |   2   |  V   |
| 2.2.5 | Patikrinkite, ar atsparumo metrikos (žinomų atakų rinkinių sėkmės rodiklis) stebimos laikui bėgant ir ar regresijos sukelia leidimo blokuotuvą.                                                                              |   3   | D/V  |

---

## C2.3 Schemos, tipo ir ilgio tikrinimas

Dažni AI išpuoliai, naudojantys netinkamus arba per didelius įvesties duomenis, gali sukelti analizės klaidas, užrašų išsiliejimą tarp laukų ir išteklių išeikvojimą. Griežtas schemos taikymas taip pat yra būtina sąlyga atliekant deterministinius įrankių kvietimus.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Patikrinkite, ar kiekviena API arba funkcijos kvietimo pabaigos taškas apibrėžia aiškią įvesties schemą (JSON schema, Protobuf arba daugiapolį ekvivalentą) ir ar įvestys yra patvirtinamos prieš sudarant užklausą. |   1   |  D   |
| 2.3.2 | Patikrinkite, ar įvestys, viršijančios maksimalų žodžių ar baitų ribą, yra atmestos su saugia klaida ir niekada nepatenkinamos tyliai apkarpant.                                                                     |   1   | D/V  |
| 2.3.3 | Patikrinkite, ar tipo patikrinimai (pvz., skaitinės reikšmės intervalai, išvardytos reikšmės, MIME tipai paveikslėliams/garsui) yra vykdomi serverio pusėje, o ne tik kliento kode.                                  |   2   | D/V  |
| 2.3.4 | Patikrinkite, ar semantiniai tikrintuvai (pvz., JSON Schema) veikia pastoviu laiku, kad būtų išvengta algoritminio DoS.                                                                                              |   2   |  D   |
| 2.3.5 | Patikrinkite, ar patvirtinimo klaidos yra registruojamos su slaptomis naudotų duomenų ištraukomis ir aiškiais klaidų kodais, siekiant palengvinti saugumo analizę.                                                   |   3   |  V   |

---

## C2.4 Turinys ir politikos tikrinimas

Kūrėjai turėtų sugebėti aptikti sintaksiškai galiojančias užklausas, kurios prašo neleistino turinio (pvz., neteisėtų nurodymų, neapykantos kalbos ir autorių teisių saugomo teksto), ir užkirsti kelią jų plitimui.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Patikrinkite, ar turinio klasifikatorius (nulinio šūvio arba tikslintai paruoštas) įvertina kiekvieną įvestį pagal smurtą, savęs žalojimą, neapykantą, seksualinį turinį ir neteisėtus prašymus, naudojant konfigūruojamus slenksčius. |   1   |  D   |
| 2.4.2 | Patikrinkite, ar įvestys, pažeidžiančios politiką, gaus standartizuotus atsisakymus arba saugius užbaigimus, kad jos nepatektų į tolesnius LLM kvietimus.                                                                              |   1   | D/V  |
| 2.4.3 | Patikrinkite, ar atrankos modelis arba taisyklių rinkinys bent kartą per ketvirtį yra perdaromas/atnaujinamas, įtraukiant naujai pastebėtus „jailbreak“ arba politikos apeidimo modelius.                                              |   2   |  D   |
| 2.4.4 | Patikrinkite, ar atranka gerbia vartotojo specifines politikos taisykles (amžiaus, regioninius teisės apribojimus) pagal atributais pagrįstas taisykles, kurios sprendžiamos prašymo metu.                                             |   2   |  D   |
| 2.4.5 | Patikrinkite, ar atrankos žurnaluose yra įtraukti klasifikatoriaus pasitikėjimo balai ir politikos kategorijų žymos SOC koreliacijai ir būsimam raudonos komandos atkūrimui.                                                           |   3   |  V   |

---

## C2.5 Įvesties greičio ribojimas ir piktnaudžiavimo prevencija

Kūrėjai turėtų užkirsti kelią piktnaudžiavimui, išteklių išeikvojimui ir automatizuotiems išpuoliams prieš DI sistemas, ribodami įvesties srautus ir aptikdami anomalinius naudojimosi modelius.

|   #   | Description                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Patikrinkite, ar visiems įvesties galiniams taškams yra taikomi apribojimai pagal vartotoją, IP adresą ir API raktą.                                        |   1   | D/V  |
| 2.5.2 | Patikrinkite, ar sprogstamieji ir pastovūs dažnio apribojimai yra sureguliuoti taip, kad būtų užkirstas kelias DoS ir žiauraus jėgos (brute force) atakoms. |   2   | D/V  |
| 2.5.3 | Patikrinkite, ar anomalūs naudojimo modeliai (pvz., greitos užklausos, įvesties srautas) sukelia automatinius blokavimus arba eskalacijas.                  |   2   | D/V  |
| 2.5.4 | Patikrinkite, ar piktnaudžiavimo prevencijos žurnalai saugomi ir peržiūrimi dėl iškylančių atakų modelių.                                                   |   3   |  V   |

---

## C2.6 Daugiau modalitetų įvesties patikra

DI sistemose turėtų būti įdiegtas patikimas ne teksto duomenų (vaizdų, garso, failų) įvesties validavimas, siekiant išvengti įsilaužimų, apgaulės ar išteklių piktnaudžiavimo.

|   #   | Description                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Patikrinkite, ar visi netekstiniai įvesties duomenys (paveikslėliai, garsas, failai) yra patikrinti pagal tipą, dydį ir formatą prieš apdorojimą. |   1   |  D   |
| 2.6.2 | Patikrinkite, ar failai yra nuskaityti dėl kenkėjiškos programinės įrangos ir steganografinių apkrovų prieš įkeldami.                             |   2   | D/V  |
| 2.6.3 | Patikrinkite, ar vaizdo/garsiniai įvestys yra tikrinamos dėl priešiškų trikdžių ar žinomų atakų modelių.                                          |   2   | D/V  |
| 2.6.4 | Patikrinkite, ar daugiaprametė įvesties patikra klaidos yra užregistruojamos ir sukelia įspėjimus tyrimui.                                        |   3   |  V   |

---

## C2.7 Įvesties kilmės nustatymas ir priskyrimas

DI sistemos turėtų palaikyti auditavimą, piktnaudžiavimo sekimą ir atitiktį, stebėdamos ir žymėdamos visų naudotojo įvesties duomenų kilmę.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Patikrinkite, ar visi vartotojo įvesties duomenys įrašomi su metaduomenimis (vartotojo ID, sesija, šaltinis, laiko žyma, IP adresas) įvedimo metu. |   1   | D/V  |
| 2.7.2 | Patikrinkite, ar kilmės metaduomenys yra išlaikomi ir galima juos patikrinti visiems apdorotiems įvesties duomenims.                               |   2   | D/V  |
| 2.7.3 | Patikrinkite, ar anomalūs arba nepatikimi įvesties šaltiniai yra pažymėti ir taikoma sustiprinta priežiūra arba blokavimas.                        |   2   | D/V  |

---

## C2.8 Realaus laiko adaptatyvus grėsmių aptikimas

Kūrėjai turėtų naudoti pažangias grėsmių aptikimo sistemas dirbtiniam intelektui, kurios prisitaiko prie naujų atakų modelių ir teikia realiojo laiko apsaugą naudojant sukompiliuotą modelių atitikimą.

|   #   | Description                                                                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Patikrinkite, ar grėsmių aptikimo šablonai yra kompiliuojami į optimizuotus reguliarių išraiškų variklius, užtikrinančius aukšto našumo realaus laiko filtravimą su minimaliu delsos poveikiu.  |   1   | D/V  |
| 2.8.2 | Patvirtinkite, kad grėsmių aptikimo sistemos palaiko atskiras šablonų bibliotekas skirtingoms grėsmių kategorijoms (užklausų injekcija, žalingas turinys, jautrūs duomenys, sistemos komandos). |   1   | D/V  |
| 2.8.3 | Patikrinkite, ar adaptyviojo grėsmių aptikimo sistemoje naudojami mašininio mokymosi modeliai, kurie atnaujina grėsmių jautrumą pagal atakų dažnumą ir sėkmingumo rodiklius.                    |   2   | D/V  |
| 2.8.4 | Patikrinkite, ar realaus laiko grėsmių žvalgybos srautai automatiškai atnaujina šablonų bibliotekas naujais atakų parašais ir pažeidžiamumo rodikliais (IOC - Indicators of Compromise).        |   2   | D/V  |
| 2.8.5 | Patikrinkite, ar grėsmių aptikimo klaidingo teigiamo rodikliai nuolat stebimi ir ar modelio specifiškumas automatiškai reguliuojamas, siekiant sumažinti teisėtų naudojimo atvejų trikdymą.     |   3   | D/V  |
| 2.8.6 | Patikrinkite, ar kontekstinė grėsmių analizė atsižvelgia į įvesties šaltinį, vartotojo elgesio modelius ir sesijos istoriją, siekiant pagerinti aptikimo tikslumą.                              |   3   | D/V  |
| 2.8.7 | Patikrinkite, ar grėsmių aptikimo našumo metrikos (aptikimo rodiklis, apdorojimo delsos laikas, išteklių naudojimas) yra stebimos ir optimizuojamos realiuoju laiku.                            |   3   | D/V  |

---

## C2.9 Daugiarūšis saugumo validavimo vamzdelis

Kūrėjai turėtų užtikrinti saugumo patikrinimą tekstinėms, vaizdo, garso ir kitoms AI įvesties modalitetams, taikydami specifinius grėsmių aptikimo tipus ir išteklių izoliaciją.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Patikrinkite, ar kiekviena įvesties moduliacija turi skirtus saugumo tikrintojus su dokumentuotais grėsmių modeliais (tekstas: užklausų injekcija, vaizdai: steganografija, garsas: spektrogramų atakos) ir aptikimo slenkstženklius.                         |   1   | D/V  |
| 2.9.2 | Patikrinkite, ar daugialypės įvestys yra apdorojamos atskiruose izoliaciniuose aplinkose su apibrėžtais resursų apribojimais (atmintis, CPU, apdorojimo laikas), būdingais kiekvienam modality tipo ir dokumentuotais saugumo politikoje.                     |   2   | D/V  |
| 2.9.3 | Patikrinkite, ar kryžminio režimo atakų aptikimas nustato koordinuotas atakas, apimančias kelis įvesties tipus (pvz., steganografinius krovinius vaizduose, derinamus su užklausų injekcija tekste), naudojant koreliacijos taisykles ir įspėjimų generavimą. |   2   | D/V  |
| 2.9.4 | Patikrinkite, ar daugialypių validacijų klaidos sukelia išsamų žurnalavimą, įskaitant visas įvesties modališkumas, validacijos rezultatus, grėsmės balus ir koreliacijos analizę su struktūruotais žurnalo formatais SIEM integracijai.                       |   3   | D/V  |
| 2.9.5 | Patikrinkite, ar modalumui būdingi turinio klasifikatoriai yra atnaujinami pagal dokumentuotus tvarkaraščius (ne rečiau kaip kas ketvirtį) su naujais grėsmių modeliais, priešiškais pavyzdžiais ir našumo rodikliais, išlaikomais virš bazinių ribų.         |   3   | D/V  |

---

## Nuorodos

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

