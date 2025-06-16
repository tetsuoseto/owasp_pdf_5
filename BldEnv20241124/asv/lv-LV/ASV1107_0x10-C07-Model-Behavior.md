# C7 modeļa uzvedība, izejas kontrole un drošības nodrošināšana

## Kontroles mērķis

Modeļa izvades dati ir jāveido strukturēti, uzticami, droši, izskaidrojami un nepārtraukti jākontrolē ražošanā. To darot, samazinās halucinācijas, privātuma noplūdes, kaitīgs saturs un nekontrolētas darbības, vienlaikus palielinot lietotāju uzticību un atbilstību regulējošajiem standartiem.

---

## C7.1 Izvades formāta ievērošana

Stingri shēmas, ierobežota atšifrēšana un turpmāka validācija aptur bojātu vai ļaunprātīgu saturu pirms tā izplatīšanās.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Pārliecinieties, ka atbildes shēmas (piemēram, JSON shēma) tiek nodrošinātas sistēmas uzvednē, un katrs izvades rezultāts tiek automātiski pārbaudīts; ne atbilstoši izvades rezultāti izraisīs labošanas vai noraidīšanas procesu. |   1   | D/V  |
| 7.1.2 | Pārliecinieties, ka ir iespējota ierobežotā dekodēšana (apturošās zīmes, regulārie izteicieni, maksimālais tokenu skaits), lai novērstu pārplūšanu vai prompta injekcijas sānu kanālus.                                             |   1   | D/V  |
| 7.1.3 | Pārbaudiet, vai lejupējie komponenti izturas pret izvadiem kā neuzticamiem un validē tos pret shēmām vai injekcijām drošiem de-serializatoriem.                                                                                     |   2   | D/V  |
| 7.1.4 | Pārliecinieties, ka nepareizas izvades notikumi tiek reģistrēti, to ātrums tiek ierobežots un tie tiek attēloti uzraudzībā.                                                                                                         |   3   |  V   |

---

## C7.2 Halucināciju atpazīšana un mazināšana

Nenoteiktības novērtēšana un rezerves stratēģijas ierobežo izdomātas atbildes.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Pārliecinieties, ka katram atbildes rezultātam tiek piešķirts ticamības vērtējums, izmantojot tokanu līmeņa log-varbūtības, ansambļa pašsaskaņas novērtējumu vai labi izstrādātus halucināciju detektorus. |   1   | D/V  |
| 7.2.2 | Pārbaudiet, vai atbildes, kuru ticamības līmenis ir zem konfigurējamas sliekšņa, aktivizē rezerves darbplūsmas (piemēram, meklēšanas pastiprināta ģenerēšana, sekundārs modelis vai cilvēka pārskats).     |   1   | D/V  |
| 7.2.3 | Pārbaudiet, vai halucināciju gadījumi ir atzīmēti ar pamatcēloņa metadatiem un nodoti post-mortēma un precīzas regulēšanas (finetuning) plūsmām.                                                           |   2   | D/V  |
| 7.2.4 | Pārliecinieties, ka sliekšņi un detektori tiek pārrēķināti pēc būtiskām modeļa vai zināšanu bāzes atjaunināšanām.                                                                                          |   3   | D/V  |
| 7.2.5 | Pārbaudiet, vai informācijas paneļa vizualizācijas seko halucināciju līmeņiem.                                                                                                                             |   3   |  V   |

---

## C7.3 Izvades drošības un privātuma filtrēšana

Politikas filtri un sarkano komandu (red-team) pārklājums aizsargā lietotājus un konfidenciālos datus.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Pārliecinieties, ka priekš un pēc ģenerēšanas izmantotie klasifikatori bloķē naida, uzmākšanās, pašnodarbināšanās, ekstrēmistu un seksuāli eksplicītu saturu, kas saskan ar politiku. |   1   | D/V  |
| 7.3.2 | Pārliecinieties, ka katrā atbildē tiek veikta PII/PCI noteikšana un automātiska aizklāšana; pārkāpumi izraisa privātuma incidentu.                                                    |   1   | D/V  |
| 7.3.3 | Pārbaudiet, vai konfidencialitātes birkas (piemēram, komercnoslēpumi) tiek pārnestas starp modalitātēm, lai novērstu noplūdi tekstā, attēlos vai kodā.                                |   2   |  D   |
| 7.3.4 | Pārliecinieties, ka filtra apietas mēģinājumi vai augsta riska klasifikācijas prasa sekundāru apstiprinājumu vai lietotāja atkārtotu autentifikāciju.                                 |   3   | D/V  |
| 7.3.5 | Pārbaudiet, vai filtrēšanas sliekšņi atbilst juridiskajām jurisdikcijām un lietotāja vecuma/lomas kontekstam.                                                                         |   3   | D/V  |

---

## C7.4 Izvades un darbību ierobežošana

Ātruma ierobežojumi un apstiprināšanas sliekšņi novērš ļaunprātīgu izmantošanu un pārmērīgu autonomiju.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Pārbaudiet, vai kvotas uz lietotāju un API atslēgu līmeni ierobežo pieprasījumus, tokenus un izmaksas, izmantojot eksponenciālu atkārtotu mēģinājumu laiku 429 kļūdu gadījumā.                      |   1   |  D   |
| 7.4.2 | Pārliecinieties, ka privileģētas darbības (failu rakstīšana, koda izpilde, tīkla zvani) prasa politikas balstītu apstiprinājumu vai cilvēka līdzdalību.                                             |   1   | D/V  |
| 7.4.3 | Pārbaudiet, vai starpmodalitātes konsekvences pārbaudes nodrošina, ka attēli, kods un teksts, kas ģenerēti vienam un tam pašam pieprasījumam, nevar tikt izmantoti ļaunprātīgas satura kontrabandā. |   2   | D/V  |
| 7.4.4 | Pārbaudiet, vai aģenta deleģēšanas dziļums, rekursijas ierobežojumi un atļautās rīku listes ir skaidri konfigurētas.                                                                                |   2   |  D   |
| 7.4.5 | Pārbaudiet, vai ierobežojumu pārkāpums izsūta strukturētus drošības notikumus SIEM uzņemšanai.                                                                                                      |   3   |  V   |

---

## C7.5 Izejas izskaidrojamība

Caurspīdīgi signāli uzlabo lietotāja uzticību un iekšējo atkļūdošanu.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Pārbaudiet, vai lietotājam redzamie ticamības rādītāji vai īsi pamatojuma kopsavilkumi tiek parādīti, ja riska novērtējums to uzskata par piemērotu. |   2   | D/V  |
| 7.5.2 | Pārbaudiet, vai ģenerētās paskaidrošanas nerāda jutīgus sistēmas uzvednes vai patentētu informāciju.                                                 |   2   | D/V  |
| 7.5.3 | Pārliecinieties, ka sistēma uztver tokenu līmeņa log-varbūtības vai uzmanības kartes un glabā tās pilnvarotai pārbaudei.                             |   3   |  D   |
| 7.5.4 | Pārliecinieties, ka izskaidrojamības artefakti ir versiju kontrolēti kopā ar modeļa izlaidumiem pārbaudāmības nodrošināšanai.                        |   3   |  V   |

---

## C7.6 Uzraudzības integrācija

Reāllaika novērojamība aizver ciklu starp izstrādi un ražošanu.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Pārbaudiet, vai metrikas (shēmas pārkāpumi, halucināciju līmenis, toksicitāte, personīgi identificējamas informācijas noplūdes, latentums, izmaksas) tiek straumētas uz centrālo uzraudzības platformu. |   1   |  D   |
| 7.6.2 | Pārliecinieties, ka katram drošības rādītājam ir definēti brīdinājuma sliekšņi, kā arī ir noteikti uzraudzības paaugstināšanas ceļi.                                                                    |   1   |  V   |
| 7.6.3 | Pārbaudiet, vai informācijas paneļi korelē izvades anomālijas ar modeli/versiju, funkciju karogu un augšupejošo datu izmaiņām.                                                                          |   2   |  V   |
| 7.6.4 | Pārbaudiet, vai uzraudzības dati tiek atgriezeniski izmantoti atkārtotai apmācībai, precizēšanai vai noteikumu atjaunināšanai dokumentētā MLOps darbplūsmā.                                             |   2   | D/V  |
| 7.6.5 | Pārliecinieties, ka uzraudzības caurules ir veiksmīgi pārbaudītas attiecībā uz uzlaušanas iespējamību un tās ir ar piekļuves kontroli, lai novērstu sensitīvu žurnālu noplūdi.                          |   3   |  V   |

---

## 7.7 Generatīvās mediju aizsardzības pasākumi

Nodrošiniet, ka mākslīgā intelekta sistēmas negenerē nelikumīgu, kaitīgu vai neatļautu mediju saturu, ieviešot politikas ierobežojumus, izvades validāciju un izsekojamību.

|   #   | Description                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Pārbaudiet, vai sistēmas norādījumi un lietotāja instrukcijas skaidri aizliedz radīt nelikumīgu, kaitīgu vai bez piekrišanas veidotu deepfake multimediju (piemēram, attēlus, video, audio).                                     |   1   | D/V  |
| 7.7.2 | Pārbaudiet, vai prompti tiek filtrēti, lai novērstu mēģinājumus ģenerēt imitations, seksuāli eksplicītus deepfake materiālus vai medijus, kuros attēlotas reālas personas bez viņu piekrišanas.                                  |   2   | D/V  |
| 7.7.3 | Pārbaudiet, vai sistēma izmanto uztveres hašēšanu, ūdenszīmes noteikšanu vai pirkstu nospiedumu identifikāciju, lai novērstu autortiesību aizsargātas multimediju neatļautu reproducēšanu.                                       |   2   |  V   |
| 7.7.4 | Pārliecinieties, ka visi ģenerētie multivides faili ir kriptogrāfiski parakstīti, aprīkoti ar ūdenszīmi vai tajos ir iegults pret manipulācijām izturīgs izcelsmes metadatu slānis, lai nodrošinātu turpmāku izsekojamību.       |   3   | D/V  |
| 7.7.5 | Pārbaudiet, vai apiet mēģinājumi (piemēram, uzvednes maskēšana, žargons, kā arī pretiniecisks formulējums) tiek atklāti, reģistrēti un ierobežoti ar ātrumu; atkārtotas ļaunprātīgas darbības tiek nodotas uzraudzības sistēmām. |   3   |  V   |

## Atsauces

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

