# C7 modelio elgsena, išvesties kontrolė ir saugumo užtikrinimas

## Valdymo tikslas

Modelio išvestys turi būti struktūruotos, patikimos, saugios, paaiškinamos ir nuolat stebimos gamybos aplinkoje. Tai sumažina haliucinacijas, privatumo nutekėjimus, žalingą turinį ir nekontroliuojamus veiksmus, tuo pačiu didinant vartotojų pasitikėjimą ir atitiktį reguliavimams.

---

## C7.1 Išvesties formato užtikrinimas

Griežtos schemos, ribotinis dekodavimas ir tolesnė validacija sustabdo neteisingai suformuotą arba kenksmingą turinį dar prieš jam išplitimą.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Patikrinkite, ar atsakymų schemos (pvz., JSON schema) yra pateiktos sistemos paklausime ir ar kiekvienas išvesties rezultatas automatiškai tikrinamas; nesilaikantys reikalavimų rezultatai sukelia taisymą arba atmetimą. |   1   | D/V  |
| 7.1.2 | Patikrinkite, ar įjungtas ribotas dekodavimas (stabdymo ženklai, reguliariosios išraiškos, maksimalus ženklų skaičius), siekiant išvengti perpildymo ar užklausos injekcijos šoninių kanalų.                               |   1   | D/V  |
| 7.1.3 | Patikrinkite, ar tolesnės grandies komponentai traktuoja išvestis kaip nepatikimas ir patikrina jas pagal schemas arba saugius nuo injekcijų de-serializatorius.                                                           |   2   | D/V  |
| 7.1.4 | Patikrinkite, ar netinkami išvesties įvykiai yra registruojami, ribojami pagal dažnį ir pateikiami stebėsenai.                                                                                                             |   3   |  V   |

---

## C7.2 Halucinacijų aptikimas ir mažinimas

Neapibrėžtumo įvertinimas ir atsarginės strategijos riboja suklastotus atsakymus.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Patikrinkite, ar žodžio lygio logaritminės tikimybės, kolektyvinis savikonsistentiškumas arba specialiai pritaikyti haliucinacijų aptikimo įrankiai priskiria pasitikėjimo balą kiekvienam atsakymui.         |   1   | D/V  |
| 7.2.2 | Patikrinkite, ar atsakymai, kurių pasitikėjimo lygis žemesnis už konfigūruojamą slenkstį, sukelia atsarginio veiksmų plano vykdymą (pvz., papildytą gavimo generavimą, antrinį modelį arba žmogaus peržiūrą). |   1   | D/V  |
| 7.2.3 | Patikrinkite, ar haliucinacijų atvejai yra pažymėti šakninių priežasčių metaduomenimis ir perduodami analizės po įvykio bei tobulinimo (finetuning) grandinėms.                                               |   2   | D/V  |
| 7.2.4 | Patikrinkite, ar slenksčiai ir detektoriai yra perkaliibruoti po reikšmingų modelio ar žinių bazės atnaujinimų.                                                                                               |   3   | D/V  |
| 7.2.5 | Patikrinkite, ar skydelio vizualizacijos stebi halucinacijų dažnius.                                                                                                                                          |   3   |  V   |

---

## C7.3 Išvesties saugumo ir privatumo filtravimas

Politikos filtrai ir raudonosios komandos aprėptis saugo vartotojus ir konfidencialius duomenis.

|   #   | Description                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Patikrinkite, ar priešgaminimo ir po generavimo klasifikatoriai blokuoja neapykantos, priekabiavimo, savęs žalojimo, ekstremistinio ir seksualiai atvirą turinį, atitinkantį politiką. |   1   | D/V  |
| 7.3.2 | Patikrinkite, ar kiekviename atsakyme veikia PII/PCI aptikimas ir automatinis slėpimas; pažeidimai sukelia privatumo incidentą.                                                        |   1   | D/V  |
| 7.3.3 | Patikrinkite, ar konfidencialumo žymos (pvz., prekybos paslaptys) sklinda per įvairias turinio formas, kad būtų išvengta nutekėjimo tekste, vaizduose ar kode.                         |   2   |  D   |
| 7.3.4 | Patikrinkite, ar filtro apeidimo bandymai arba didelės rizikos klasifikacijos reikalauja antrinio patvirtinimo arba vartotojo pakartotinio autentifikavimo.                            |   3   | D/V  |
| 7.3.5 | Patikrinkite, ar filtravimo slenkstiai atitinka teisinius jurisdikcijos reikalavimus ir vartotojo amžiaus/vaidmens kontekstą.                                                          |   3   | D/V  |

---

## C7.4 Išvesties ir veiksmų apribojimas

Ribojimai ir patvirtinimo vartai neleidžia piktnaudžiauti ir užtikrina kontroliuojamą autonomiją.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.4.1 | Patikrinkite, ar naudotojo ir API rakto kvotos riboja užklausas, žetonus ir kaštus, taikant eksponentinį atsitraukimą 429 klaidų atveju.                                                   |   1   |  D   |
| 7.4.2 | Patikrinkite, ar privilegijuotos operacijos (failų rašymas, kodo vykdymas, tinklo užklausos) reikalauja politikos pagrindu patvirtinimo arba žmogaus įsikišimo.                            |   1   | D/V  |
| 7.4.3 | Patikrinkite, ar kryžmodaliniai nuoseklumo patikrinimai užtikrina, kad vienam užklausimui sugeneruotos nuotraukos, kodas ir tekstas negali būti naudojami piktavališkam turiniui slepiant. |   2   | D/V  |
| 7.4.4 | Patikrinkite, ar agento delegavimo gylis, rekursijos apribojimai ir leidžiamų įrankių sąrašai yra aiškiai sukonfigūruoti.                                                                  |   2   |  D   |
| 7.4.5 | Patikrinkite, ar limitų pažeidimai sukelia struktūruotus saugumo įvykius SIEM įsisavinimui.                                                                                                |   3   |  V   |

---

## C7.5 Išvesties paaiškinamumas

Permatomi signalai gerina vartotojų pasitikėjimą ir vidinį derinimą.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.5.1 | Patikrinkite, ar naudotojui matomi pasitikėjimo įvertinimai ar trumpi sprendimų pateisinimai pateikiami, kai rizikos vertinimas tai laikytina tinkama. |   2   | D/V  |
| 7.5.2 | Patikrinkite, ar sugeneruoti paaiškinimai neatskleidžia jautrių sistemos užklausų ar konfidencialios informacijos.                                     |   2   | D/V  |
| 7.5.3 | Patikrinkite, ar sistema fiksuoja žodžio lygio tikimybės logaritmus arba dėmesio žemėlapius ir saugo juos autorizuotam patikrinimui.                   |   3   |  D   |
| 7.5.4 | Patikrinkite, ar aiškinamumo artefaktai yra valdomi versijų kontrolės sistema kartu su modelių leidimais audito galimybei.                             |   3   |  V   |

---

## C7.6 Stebėjimo integracija

Realaus laiko stebėjimas uždaro ciklą tarp kūrimo ir gamybos.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Patikrinkite, ar įvairūs metrikai (schemos pažeidimai, haliucinacijų dažnis, toksiškumas, asmeninės informacijoss nutekėjimas, vėlavimas, sąnaudos) yra perduodami į centrinę stebėjimo platformą. |   1   |  D   |
| 7.6.2 | Patikrinkite, ar kiekvienam saugumo metrikos rodikliui yra apibrėžti įspėjimo slenksčiai, kartu su budėjimo metu skubios eskalacijos keliais.                                                      |   1   |  V   |
| 7.6.3 | Patikrinkite, ar prietaisų skydeliai koreliuoja išvesties anomalijas su modelio/versijos, funkcijų žymos ir aukštesnio lygio duomenų pakeitimais.                                                  |   2   |  V   |
| 7.6.4 | Patikrinkite, ar stebėjimo duomenys grįžta atgal į pakartotinį mokymą, tikslinimą arba taisyklių atnaujinimą dokumentuoto MLOps darbo eigos metu.                                                  |   2   | D/V  |
| 7.6.5 | Patikrinkite, ar stebėjimo dujotiekiams atliekami įsiskverbimo testai ir ar prieiga yra kontroliuojama, kad būtų išvengta jautrios informacijos nuotėkio.                                          |   3   |  V   |

---

## 7.7 Generatyvinės medijos apsaugos priemonės

Užtikrinkite, kad DI sistemos negeneruotų neteisėtos, žalingos ar neautorizuotos medijos turinio, taikant politikos apribojimus, išvesties patvirtinimą ir stebimumo galimybes.

|   #   | Description                                                                                                                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Patikrinkite, ar sistemos nurodymai ir vartotojo instrukcijos aiškiai draudžia kurti neteisėtą, žalingą arba nepritariamai sukurtą deepfake medžiagą (pvz., vaizdus, vaizdo įrašus, garsą).                                                 |   1   | D/V  |
| 7.7.2 | Patikrinkite, ar prašymai yra filtruojami siekiant užkirsti kelią bandymams generuoti įsikūnijimus, seksualiai atviras giliųjų klastočių ar medžiagą, vaizduojančią tikrus asmenis be jų sutikimo.                                          |   2   | D/V  |
| 7.7.3 | Patikrinkite, ar sistema naudoja perceptual hashing, vandens ženklo aptikimą arba pirštų atspaudų nustatymą, siekiant užkirsti kelią neautorizuotam autorių teisių saugomos medžiagos kopijavimui.                                          |   2   |  V   |
| 7.7.4 | Patikrinkite, ar visa sugeneruota medija yra kriptografiškai pasirašyta, pažymėta vandens ženklais arba įdėta su atspariais klastojimui kilmės metaduomenimis, siekiant užtikrinti tolesnį stebėjimą.                                       |   3   | D/V  |
| 7.7.5 | Patikrinkite, ar apeinimo bandymai (pvz., užklausų užmaskavimas, šnekamoji kalba, priešiškas formuluotės naudojimas) yra aptinkami, registruojami ir ribojami pagal dažnį; pasikartojantis piktnaudžiavimas pranešamas stebėjimo sistemoms. |   3   |  V   |

## Nuorodos

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

