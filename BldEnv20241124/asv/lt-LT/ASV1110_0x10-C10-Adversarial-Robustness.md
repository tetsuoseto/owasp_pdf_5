# 10 Priešiškumo atsparumas ir privatumo apsauga

## Valdymo tikslas

Užtikrinkite, kad DI modeliai išliktų patikimi, privatumo saugomi ir atsparūs piktnaudžiavimui susiduriant su išvengimo, darymo išvadų, duomenų išgavimą ar užnuodijimo atakomis.

---

## 10.1 Modelio suderinamumas ir saugumas

Apsaugokite nuo žalingų arba politikos pažeidžiančių rezultatų.

|   #    | Description                                                                                                                                                                                              | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Patikrinkite, ar suderinamumo testų rinkinys (red team užklausos, jailbreiko testai, neleistinas turinys) yra valdomas versijų valdymo sistemoje ir vykdomas kiekvienos modelio versijos išleidimo metu. |   1   | D/V  |
| 10.1.2 | Patikrinkite, ar laikomasi atsisakymo ir saugaus užbaigimo apsaugos priemonių.                                                                                                                           |   1   |  D   |
| 10.1.3 | Patikrinkite, ar automatizuotas vertintojas matuoja kenksmingo turinio dažnį ir žymi regresijas, viršijančias nustatytą ribą.                                                                            |   2   | D/V  |
| 10.1.4 | Patikrinkite, ar kontratralizavimo apmokymai yra dokumentuoti ir atkuriami.                                                                                                                              |   2   |  D   |
| 10.1.5 | Patikrinkite, ar formalūs politikos laikymosi įrodymai arba sertifikuotas stebėjimas apima kritines sritis.                                                                                              |   3   |  V   |

---

## 10.2 Priešpriešinių pavyzdžių stiprinimas

Padidinkite atsparumą manipuliuotiems įvestims. Patikimas priešiškas mokymas ir etaloninis įvertinimas yra dabartinė geriausia praktika.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.2.1 | Patikrinkite, ar projekto saugyklose yra priešiško mokymo konfigūracijos su atkuriamais sėklų parametrais.                     |   1   |  D   |
| 10.2.2 | Patikrinkite, ar priešiškų pavyzdžių aptikimas sukelia blokavimo įspėjimus gamybos procesuose.                                 |   2   | D/V  |
| 10.2.4 | Patikrinkite, ar sertifikuotos patvarumo įrodymai arba intervalo ribų pažymėjimai apima bent jau svarbiausias kritines klases. |   3   |  V   |
| 10.2.5 | Patikrinkite, ar regresijos testai naudoja adaptyvius išpuolius, kad patvirtintų neįžvelgiamą patvarumo praradimą.             |   3   |  V   |

---

## 10.3 Narystės atpažinimo suvaržymas

Apribokite galimybę nuspręsti, ar įrašas buvo mokymo duomenyse. Diferencialinė privatumo apsauga ir pasitikėjimo įvertinimo maskavimas išlieka veiksmingiausi žinomi gynybos metodai.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Patikrinkite, ar kiekvienam užklausos vienetui taikomas entropijos reguliavimas arba temperatūros skalavimas sumažina pernelyg užtikrintas prognozes. |   1   |  D   |
| 10.3.2 | Patikrinkite, ar mokymas naudoja ε-ribotą diferencijuotai privatų optimizavimą jautriems duomenų rinkiniams.                                          |   2   |  D   |
| 10.3.3 | Patikrinkite, ar atakų simuliacijos (šešėlinio modelio arba juodosios dėžės) rodo atakos AUC ≤ 0,60 ant atskirtų duomenų.                             |   2   |  V   |

---

## 10.4 Modelio inversijos atsparumas

Užkirsti kelią privačių atributų rekonstrukcijai. Naujausios apžvalgos pabrėžia išvesties sutrumpinimą ir diferencinio privatumo garantijas kaip praktines apsaugos priemones.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Patikrinkite, kad jautrūs atributai niekada nebūtų tiesiogiai pateikiami; jei reikia, naudokite kategorijas arba vienpusio šifravimo metodus. |   1   |  D   |
| 10.4.2 | Patikrinkite, ar užklausų dažnio apribojimai riboja pasikartojančias adaptacines užklausas iš to paties asmens.                               |   1   | D/V  |
| 10.4.3 | Patikrinkite, ar modelis yra apmokytas su privatumo saugančiu triukšmu.                                                                       |   2   |  D   |

---

## 10.5 Modelio išgavimas – gynyba

Aptikti ir užkirsti kelią neįgaliotam klonavimui. Rekomenduojama naudoti vandens ženklinimą ir užklausų modelių analizę.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Patikrinkite, ar išvados vartai taiko pasaulinius ir pagal API raktą nustatytus spartos ribojimus, pritaikytus modelio įsiminimo slenksčiui.    |   1   |  D   |
| 10.5.2 | Patikrinkite, ar užklausos entropijos ir įvesties daugiabūdingumo statistika yra naudojama automatiniam išgavimų aptikimui.                     |   2   | D/V  |
| 10.5.3 | Patikrinkite, ar trapūs arba tikimybinių vandens ženklai gali būti įrodyti su p < 0,01 per ne daugiau kaip 1 000 užklausų prieš įtariamą kloną. |   2   |  V   |
| 10.5.4 | Patikrinkite, ar vandens ženklų raktai ir suaktyvinimo rinkiniai yra saugomi aparatinės įrangos saugumo modulyje ir keičiami kasmet.            |   3   |  D   |
| 10.5.5 | Patikrinkite, ar ištraukimo įspėjimų įvykiai apima pažeidžiančius užklausimus ir yra integruoti su incidentų reagavimo veiksmų planais.         |   3   |  V   |

---

## 10.6 Išvedimo laikotarpio užkrėsto duomenų aptikimas

Identifikuokite ir neutralizuokite atgalines duris ar užnuodytus įvesties duomenis.

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Patikrinkite, ar įvestys praeina pro anomalijų detektorių (pvz., STRIP, nuoseklumo įvertinimą) prieš atliekant modelio inferenciją.                                 |   1   |  D   |
| 10.6.2 | Patikrinkite, ar detektorių slenksčiai yra sureguliuoti ant švarių/užnuodytų patikrinimo rinkinių, siekiant užtikrinti mažiau nei 5 % klaidingų teigiamų rezultatų. |   1   |  V   |
| 10.6.3 | Patikrinkite, ar įvestys, pažymėtos kaip užkrėstos, sukelia minkštojo blokavimo ir žmogaus peržiūros darbo eigas.                                                   |   2   |  D   |
| 10.6.4 | Patikrinkite, ar detektoriai yra streso testuojami naudojant adaptacinius, be signalo suaktyvinamų galinių durų atakas.                                             |   2   |  V   |
| 10.6.5 | Patikrinkite, ar aptikimo efektyvumo metrikos yra registruojamos ir periodiškai pervertinėjamos naudojant naują grėsmių informaciją.                                |   3   |  D   |

---

## 10.7 Dinaminis saugumo politikos pritaikymas

Saugumo politikos atnaujinimai realiuoju laiku, pagrįsti grėsmių žvalgyba ir elgsenos analize.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.7.1 | Patikrinkite, ar saugumo politikos gali būti atnaujinamos dinamiškai be agento paleidimo iš naujo, išlaikant politikos versijos vientisumą.                        |   1   | D/V  |
| 10.7.2 | Patikrinkite, ar politikos atnaujinimai yra kriptografiškai pasirašyti įgaliotų saugumo darbuotojų ir patikrinti prieš taikant.                                    |   2   | D/V  |
| 10.7.3 | Patikrinkite, ar dinamiški politikos pakeitimai yra registruojami su pilnais audito įrašais, įskaitant pagrindimą, patvirtinimo grandines ir atšaukimo procedūras. |   2   | D/V  |
| 10.7.4 | Patikrinkite, ar adaptaciniai saugumo mechanizmai reguliuoja grėsmės aptikimo jautrumą pagal rizikos kontekstą ir elgsenos modelius.                               |   3   | D/V  |
| 10.7.5 | Patikrinkite, ar politikos adaptacijos sprendimai yra paaiškinami ir ar yra įtraukti įrodymų takai saugumo komandos peržiūrai.                                     |   3   | D/V  |

---

## 10.8 Atspindžiu grįsta saugumo analizė

Saugumo patikrinimas per agento savirefleksiją ir meta-kognityvinę analizę.

|   #    | Description                                                                                                                                      | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.8.1 | Patikrinkite, ar agento atspindėjimo mechanizmai apima saugumo koncentruotą savęs vertinimą priimant sprendimus ir atliekant veiksmus.           |   1   | D/V  |
| 10.8.2 | Patikrinkite, ar atspindžio išėjimai yra patvirtinti, siekiant užkirsti kelią savianalizės mechanizmų manipuliacijai priešų įvesties duomenimis. |   2   | D/V  |
| 10.8.3 | Patikrinkite, ar metakognityvinė saugumo analizė nustato galimus šališkumus, manipuliacijas ar pažeidimus agento samprotavimo procesuose.        |   2   | D/V  |
| 10.8.4 | Patikrinkite, ar atspindžių pagrindu veikiantys saugumo įspėjimai sukelia sustiprintą stebėjimą ir galimus žmogaus įsikišimo darbo srautus.      |   3   | D/V  |
| 10.8.5 | Patikrinkite, ar nuolatinis mokymasis iš saugumo apmąstymų gerina grėsmių aptikimą, nesumažinant teisėtos funkcionalumo kokybės.                 |   3   | D/V  |

---

## 10.9 Evoliucija ir savęs tobulinimo saugumas

Saugumo kontrolės agentų sistemoms, gebančioms savarankiškai keistis ir vystytis.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Patikrinkite, ar savęs modifikavimo galimybės yra apribotos tik specialiai pažymėtose saugiose zonose su formaliomis verifikacijos ribomis. |   1   | D/V  |
| 10.9.2 | Patikrinkite, ar evoliucijos pasiūlymai praeina saugumo poveikio vertinimą prieš įgyvendinant.                                              |   2   | D/V  |
| 10.9.3 | Patikrinkite, ar savęs tobulinimo mechanizmai apima grąžinimo funkcijas su vientisumo patikrinimu.                                          |   2   | D/V  |
| 10.9.4 | Patikrinkite, ar meta-mokymosi saugumas neleidžia priešiškam tobulinimo algoritmų manipuliavimui.                                           |   3   | D/V  |
| 10.9.5 | Patikrinkite, ar rekursinis savęs tobulinimas yra ribojamas formalių saugumo apribojimų, pateikiant matematinius konvergencijos įrodymus.   |   3   | D/V  |

---

### Nuorodos

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

