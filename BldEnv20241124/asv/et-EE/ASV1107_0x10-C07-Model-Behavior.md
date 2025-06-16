# C7 mudeli käitumine, väljundkontroll ja ohutuse tagamine

## Kontrollieesmärk

Mudeli väljundid peavad olema struktureeritud, usaldusväärsed, ohutud, seletatavad ning pidevalt tootmiskeskkonnas järelvalvatavad. Selline lähenemine vähendab fantaseerimist, privaatsuslekkeid, kahjulikku sisu ja kontrollimatuid tegevusi, samal ajal suurendades kasutajate usaldust ja regulatiivset vastavust.

---

## C7.1 Väljundi formaadi jõustamine

Range schemas, piiratud dekodeerimine ja järeltöötluse valideerimine takistavad valesti kujundatud või pahatahtliku sisu levikut.

|   #   | Description                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Kinnitage, et vastuse skeemid (nt JSON-skeem) on süsteemipäringusse lisatud ja iga väljund valideeritakse automaatselt; sobimatud väljundid põhjustavad parandamise või tagasilükkamise. |   1   | D/V  |
| 7.1.2 | Kontrollige, et oleks lubatud piiratud dekodeerimine (peatamis- tokenid, regulaaravaldised, maksimaalne tokenite arv), et vältida ülevoogu või prompti-injektsiooni kõrvalkanaleid.      |   1   | D/V  |
| 7.1.3 | Kinnitage, et järeltöötluskomponendid käsitlevad väljundeid usaldamatult ning valideerivad neid skeemide või süstimisohutute deserialiseerijate abil.                                    |   2   | D/V  |
| 7.1.4 | Kontrollige, et valede väljundite sündmused logitakse, piiratakse sagedust ja kuvatakse jälgimissüsteemis.                                                                               |   3   |  V   |

---

## C7.2 Hallutsinatsioonide tuvastamine ja leevendamine

Ebakindluse hindamine ja varuplaanide strateegiad piiravad väljamõeldud vastuseid.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Kontrollige, kas tokeni tasemel log- tõenäosused, ansambli enesekindlus või peenhäälestatud hallutsinatsioonidetektorid annavad igale vastusele usaldusmärkme.                     |   1   | D/V  |
| 7.2.2 | Kinnitage, et allpool määratletud konfigureeritava usalduspiiri jäävad vastused käivitavad tagavaravoo (nt otsingu-põhine genereerimine, sekundaarne mudel või inimese ülevaatus). |   1   | D/V  |
| 7.2.3 | Kinnitage, et hallutsinatsiooni juhtumid on märgistatud põhjusmetaandmetega ning suunatud järelanalüüsi ja peenhäälestuse töövoogudesse.                                           |   2   | D/V  |
| 7.2.4 | Kinnitage, et läviväärtused ja detektorid kalibreeritakse pärast olulisi mudeli või teadmistebaasi uuendusi uuesti.                                                                |   3   | D/V  |
| 7.2.5 | Kinnita, et armatuurlaua visualiseeringud jälgivad hallutsinatsioonimäärasid.                                                                                                      |   3   |  V   |

---

## C7.3 Väljundi turvalisuse ja privaatsuse filtreerimine

Poliitikafiltrid ja red-teami katvus kaitsevad kasutajaid ja konfidentsiaalset teavet.

|   #   | Description                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Kinnitage, et eel- ja järeltuotmise klassifikaatorid blokeerivad poliitikaga kooskõlastatud vihakõne, ahistamise, enesevigastamise, äärmusluse ja seksuaalselt eksplitsiitse sisu. |   1   | D/V  |
| 7.3.2 | Kinnitage, et PII/PCI tuvastamine ja automaatne peitmine toimuvad igas vastuses; rikkumised põhjustavad privaatsusintsidendi.                                                      |   1   | D/V  |
| 7.3.3 | Kontrollige, et konfidentsiaalsuse sildid (nt ärisaladused) kanduksid eri modaalide vahel, et vältida lekkimist tekstis, piltides või koodis.                                      |   2   |  D   |
| 7.3.4 | Kontrollige, et filtri möödaminekukatset või kõrge riskitasemega klassifitseerimist nõuaksid teistkordset kinnitust või kasutaja uuesti autentimist.                               |   3   | D/V  |
| 7.3.5 | Kontrollige, et filtreerimiskünnised vastaksid õiguslikele jurisdiktsioonidele ning kasutaja vanuse/rolli kontekstile.                                                             |   3   | D/V  |

---

## C7.4 Väljundi ja toimingute piiramine

Kiiruspiirangud ja kinnitussillad takistavad väärkasutust ja liigset autonoomiat.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Kinnitage, et kasutajapõhised ja API-võtme-põhised kvodid piiravad päringuid, märke ja kulusid, rakendades 429 vigade korral ekstsponentset tagasilööki. |   1   |  D   |
| 7.4.2 | Kinnitage, et privileegitud toimingud (failikirjutused, koodi täitmine, võrgukõned) nõuavad poliitikapõhist heakskiitu või inimese sekkumist.            |   1   | D/V  |
| 7.4.3 | Kinnitage, et ristmeediline järjepidevuskontroll tagab, et sama päringu jaoks genereeritud pildid, kood ja tekst ei saa sisaldada pahatahtlikku sisu.    |   2   | D/V  |
| 7.4.4 | Kontrollige, et agendi volituste sügavus, rekursiooni piirangud ja lubatud tööriistade nimekirjad oleksid selgelt konfigureeritud.                       |   2   |  D   |
| 7.4.5 | Kinnitage, et piirangute rikkumine tekitab SIEM-i andmete töötlemiseks struktureeritud turvasündmusi.                                                    |   3   |  V   |

---

## C7.5 Väljundi seletatavus

Läbipaistvad signaalid parandavad kasutajate usaldust ja sisemist silumist.

|   #   | Description                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Veenduge, et kasutajale suunatud usaldusväärtused või lühikesed põhjendussummad oleksid esitatud, kui riskihinnang seda õigustab. |   2   | D/V  |
| 7.5.2 | Kinnitage, et genereeritud selgitused ei avalda tundlikke süsteemipäringuid ega ettevõtteandmeid.                                 |   2   | D/V  |
| 7.5.3 | Kontrollige, et süsteem kogub märgitasandi log-tõenäosusi või tähelepanukaarte ning salvestab need volitatud ülevaatuseks.        |   3   |  D   |
| 7.5.4 | Kinnitage, et seletatavuse artefaktid on versioonihalduses koos mudeli väljalasetega auditeeritavuse tagamiseks.                  |   3   |  V   |

---

## C7.6 Jälgimise integreerimine

Reaalajas jälgitavus sulgeb arenduse ja tootmise vahese tagasisideahela.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Kontrollige, et meetrikad (skeemirikete, hallutsinatsiooni määr, toksilisus, isikuandmete lekked, latentsus, kulud) edastataksid kesksesse jälgimisplatvormi. |   1   |  D   |
| 7.6.2 | Kinnitage, et iga turvameetri kohta on määratletud hoiatuskünnised koos valvepersonali eskaleerimisrajadega.                                                  |   1   |  V   |
| 7.6.3 | Kontrollige, et armatuurlaud seostaks väljundi anomaaliad mudeli/versiooni, funktsioonilipu ja ülemise andmete muudatustega.                                  |   2   |  V   |
| 7.6.4 | Kontrollige, et jälgimisandmed tagasisidestatakse ümberõppe, peenhäälestuse või reeglite uuenduste kaudu dokumenteeritud MLOps töövoo raames.                 |   2   | D/V  |
| 7.6.5 | Kinnitage, et järelevalve torujuhtmeid on läbiviidud sissetungimise testiga ja need on juurdepääsupiirangutega, et vältida tundlike logide lekkimist.         |   3   |  V   |

---

## 7.7 Generatiivmeedia turvameetmed

Tagada, et tehisintellekti süsteemid ei loo ebaseaduslikku, kahjulikku ega volitamata meediasisu, rakendades poliitiliste piirangute, väljundi kinnitamise ja jälgitavuse meetmeid.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Kinnitage, et süsteemi käsud ja kasutaja juhised keelavad selgesõnaliselt ebaseadusliku, kahjuliku või nõusolekuta deepfake-meedia (nt pildid, videod, heli) loomise.                                    |   1   | D/V  |
| 7.7.2 | Kontrollige, et päringud oleksid filtreeritud püüdluste suhtes luua identiteedivarguseid, seksuaalselt eksplicitseid sügavvõltsinguid või meediat, mis kujutab tõelisi isikuid ilma nõusolekuta.         |   2   | D/V  |
| 7.7.3 | Kontrollige, kas süsteem kasutab volitamata kopeerimise jaotiseks autoriõigustega kaitstud meedia puhul tajuhästi (perceptual hashing), veejälje tuvastamist või sõrmejälje tehnoloogiat.                |   2   |  V   |
| 7.7.4 | Kinnitage, et kõik genereeritud meediumid on krüptograafiliselt allkirjastatud, veega märgistatud või varustatud rikkumiskindlate päritolu metandmetega allika jälgitavuse tagamiseks.                   |   3   | D/V  |
| 7.7.5 | Veenduge, et läbipääsu katsed (nt päringu varjamine, släng, vaenulikud väljendid) tuvastatakse, logitakse ja määratakse neile kiiruspiirang; korduv kuritarvitamine edastatakse järelevalvesüsteemidele. |   3   |  V   |

## Viited

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

