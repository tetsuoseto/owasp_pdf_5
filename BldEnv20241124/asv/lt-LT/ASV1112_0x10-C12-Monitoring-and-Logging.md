# C12 Stebėjimas, Įrašymas ir Anomalijų Aptikimas

## Kontrolės tikslas

Šiame skyriuje pateikiami reikalavimai tiesioginiam ir forensiniam matomumui užtikrinti, kas modelis ir kitos DI dalys mato, ką daro ir ką grąžina, kad būtų galima aptikti, išanalizuoti ir išmokti iš grėsmių.

## C12.1 Užklausų ir atsakymų registravimas

|   #    | Description                                                                                                                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Patikrinkite, ar visi vartotojų užklausimai ir modelio atsakymai yra įrašyti kartu su atitinkamais metaduomenimis (pvz., laiko žyma, vartotojo ID, sesijos ID, modelio versija).                                                                                 |   1   | D/V  |
| 12.1.2 | Patikrinkite, ar žurnalai saugomi saugiuose, prieigą kontroliuojamuose saugyklose su tinkamomis saugojimo politikomis ir atsarginių kopijų procedūromis.                                                                                                         |   1   | D/V  |
| 12.1.3 | Patikrinkite, ar žurnalų saugojimo sistemos įgyvendina duomenų šifravimą ramybėje ir perdavimo metu, siekiant apsaugoti žurnaluose esančią konfidencialią informaciją.                                                                                           |   1   | D/V  |
| 12.1.4 | Patikrinkite, ar jautrūs duomenys skatinimuose ir rezultatuose automatiškai ištrinami arba užmaskuojami prieš įrašymą, su konfigūruojamomis redagavimo taisyklėmis asmens identifikavimo informacijai (PII), prieigos duomenims ir konfidencialiai informacijai. |   1   | D/V  |
| 12.1.5 | Patikrinkite, kad politikos sprendimai ir saugumo filtravimo veiksmai būtų registruojami pakankamai detaliai, kad būtų galima atlikti audito patikrinimą ir turinio moderavimo sistemų derinimą.                                                                 |   2   | D/V  |
| 12.1.6 | Patikrinkite, ar žurnalų vientisumas yra apsaugotas, pavyzdžiui, naudojant kriptografinius parašus ar tik rašymui skirtą saugyklą.                                                                                                                               |   2   | D/V  |

---

## C12.2 Piktnaudžiavimo aptikimas ir įspėjimas

|   #    | Description                                                                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Patikrinkite, ar sistema aptinka ir perspėja apie žinomus jailbreak šablonus, paskatų įpurškimo bandymus bei priešiškas įvestis, naudodama parašo pagrindu veikiančią aptikimą.                                                       |   1   | D/V  |
| 12.2.2 | Patikrinkite, ar sistema integruojasi su esamomis Saugumo informacijos ir įvykių valdymo (SIEM) platformomis, naudodama standartinius žurnalų formatus ir protokolus.                                                                 |   1   | D/V  |
| 12.2.3 | Patikrinkite, ar praturtinti saugumo įvykiai apima dirbtinio intelekto specifinį kontekstą, tokį kaip modelio identifikatoriai, pasitikėjimo balai ir saugumo filtrų sprendimai.                                                      |   2   | D/V  |
| 12.2.4 | Patikrinkite, ar elgesio anomalijų aptikimas nustato neįprastus pokalbių modelius, per daug kartojamus bandymus arba sistemingą tyrimų elgesį.                                                                                        |   2   | D/V  |
| 12.2.5 | Patikrinkite, ar realaus laiko įspėjimo mechanizmai informuoja saugumo komandas, kai aptinkami galimi politikos pažeidimai arba atakos bandymai.                                                                                      |   2   | D/V  |
| 12.2.6 | Patikrinkite, ar įtrauktos pasirinktinės taisyklės, skirtos aptikti dirbtinio intelekto specifinius grėsmių modelius, įskaitant koordinuotus sistemos apeidimo bandymus, užklausų injekcijos kampanijas ir modelių ištraukimo atakas. |   2   | D/V  |
| 12.2.7 | Patikrinkite, ar automatizuoti incidentų reagavimo darbo srautai gali izoliuoti pažeistus modelius, blokuoti kenkėjiškus vartotojus ir eskaluoti kritinius saugumo įvykius.                                                           |   3   | D/V  |

---

## C12.3 Modelio pasislinkimo aptikimas

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Patikrinkite, ar sistema stebi pagrindinius veiklos rodiklius, tokius kaip tikslumas, pasitikėjimo balai, delsos laikas ir klaidų rodikliai per modelio versijas ir laiko intervalus. |   1   | D/V  |
| 12.3.2 | Patikrinkite, ar automatizuoti perspėjimai suveikia, kai našumo metrikos viršija iš anksto nustatytas degradacijos ribas arba žymiai nukrypsta nuo bazinių lygių.                     |   2   | D/V  |
| 12.3.3 | Patikrinkite, ar haliucinacijų aptikimo stebėjimo priemonės nustato ir žymi atvejus, kai modelio išvestys yra faktiniu požiūriu neteisingos, prieštaringos arba suklastotos.          |   2   | D/V  |

---

## C12.4 Veiklos ir elgesio telemetrija

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Patikrinkite, ar operaciniai metrikai, įskaitant užklausos vėlavimą, žetonų sunaudojimą, atminties naudojimą ir pralaidumą, nuolat renkami ir stebimi.         |   1   | D/V  |
| 12.4.2 | Patikrinkite, ar sėkmės ir nesėkmės rodikliai fiksuojami kartu su klaidų tipų ir jų priežastinių šaknų kategorizavimu.                                         |   1   | D/V  |
| 12.4.3 | Patikrinkite, ar resursų naudojimo stebėjimas apima GPU/CPU naudojimą, atminties suvartojimą ir saugojimo reikalavimus bei signalizavimą apie ribų pažeidimus. |   2   | D/V  |

---

## C12.5 DI sprendimų reagavimo plano sudarymas ir vykdymas

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Patikrinkite, ar incidentų reagavimo planai aiškiai apima su dirbtiniu intelektu susijusius saugumo įvykius, įskaitant modelio pažeidimą, duomenų apsinuodijimą ir priešiškus išpuolius.      |   1   | D/V  |
| 12.5.2 | Patikrinkite, ar incidentų reagavimo komandos turi prieigą prie dirbtinio intelekto specifinių teisinių įrodymų įrankių ir ekspertizės, kad galėtų tirti modelio elgseną ir atakos vektorius. |   2   | D/V  |
| 12.5.3 | Patikrinkite, ar poįvykio analizėje įtraukti modelio perdavimo svarstymai, saugos filtrų atnaujinimai ir išmoktos pamokos integravimas į saugumo valdiklius.                                  |   3   | D/V  |

---

## C12.5 AI našumo blogėjimo aptikimas

Stebėti ir aptikti dirbtinio intelekto modelio našumo ir kokybės blogėjimą laikui bėgant.

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Patikrinkite, ar modelio tikslumas, preciziškumas, atgaminamumas ir F1 rodikliai yra nuolat stebimi ir lyginami su baziniais slenksčiais.                             |   1   | D/V  |
| 12.5.2 | Patikrinkite, ar duomenų pasiskirstymo pokyčių stebėjimas (data drift detection) fiksuoja įvesties pasiskirstymo pokyčius, kurie gali turėti įtakos modelio veikimui. |   1   | D/V  |
| 12.5.3 | Patikrinkite, ar koncepcijos poslinkio aptikimas identifikuoja pokyčius tarp įvesties duomenų ir tikėtinų išvesties duomenų santykio.                                 |   2   | D/V  |
| 12.5.4 | Patikrinkite, ar veikimo kokybės sumažėjimas sukelia automatinius įspėjimus ir inicijuoja modelio perkvalifikavimo arba pakeitimo darbo procesus.                     |   2   | D/V  |
| 12.5.5 | Patikrinkite, ar nuosmukio priežasčių analizė susieja našumo sumažėjimą su duomenų pokyčiais, infrastruktūros problemomis arba išoriniais veiksniais.                 |   3   |  V   |

---

## C12.6 DAG vizualizacija ir darbo eigos saugumas

Apsaugokite darbo eigos vizualizacijos sistemas nuo informacijos nutekėjimo ir manipuliacijos atakų.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.6.1 | Patikrinkite, ar DAG vizualizacijos duomenys yra išvalyti nuo jautrios informacijos prieš juos saugant arba perduodant.                                                                    |   1   | D/V  |
| 12.6.2 | Patikrinkite, ar darbo eigos vizualizacijos prieigos valdikliai užtikrina, kad tik įgalioti vartotojai galėtų peržiūrėti agentų sprendimų kelius ir argumentacijos sekas.                  |   1   | D/V  |
| 12.6.3 | Patikrinkite, ar DAG duomenų vientisumas yra apsaugotas kriptografiniais parašais ir nuo klastojimo apsaugančiomis saugojimo priemonėmis.                                                  |   2   | D/V  |
| 12.6.4 | Patikrinkite, ar darbo eigos vizualizavimo sistemos įgyvendina įvesties duomenų tikrinimą, kad būtų užkirstas kelias injekcijos atakoms per specialiai paruoštus mazgų ar kraštų duomenis. |   2   | D/V  |
| 12.6.5 | Patikrinkite, ar realaus laiko DAG atnaujinimai yra ribojami pagal dažnį ir tikrinami, siekiant išvengti paslaugų atsisakymo (DoS) atakų vizualizacijos sistemoms.                         |   3   | D/V  |

---

## C12.7 Proaktyvus saugumo elgesio stebėjimas

Saugumo grėsmių aptikimas ir prevencija per proaktyvią agento elgesio analizę.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Patikrinkite, ar proaktyvūs agentų elgesiai yra saugumo patvirtinti prieš vykdymą, integruojant rizikos vertinimą.              |   1   | D/V  |
| 12.7.2 | Patikrinkite, ar autonominio iniciatyvumo suaktyvinimai apima saugumo konteksto vertinimą ir grėsmių kraštovaizdžio įvertinimą. |   2   | D/V  |
| 12.7.3 | Patikrinkite, ar proaktyvūs elgesio modeliai yra analizuojami dėl galimų saugumo pasekmių ir neplanuotų padarinių.              |   2   | D/V  |
| 12.7.4 | Patikrinkite, ar saugumui kritiškai svarbūs proaktyvūs veiksmai reikalauja aiškių patvirtinimo grandinių su audito įrašais.     |   3   | D/V  |
| 12.7.5 | Patikrinkite, ar elgesio anomalijų aptikimas nustato nukrypimus proaktyvių agentų modeliuose, kurie gali rodyti pažeidžiamumą.  |   3   | D/V  |

---

## Nuorodos

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

