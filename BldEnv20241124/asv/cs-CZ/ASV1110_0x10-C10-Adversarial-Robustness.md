# 10 Robustnost vůči protivníkům a obrana soukromí

## Řídicí cíl

Zajistěte, aby modely umělé inteligence zůstaly spolehlivé, chránily soukromí a byly odolné vůči zneužití při čelení útokům na obcházení, inferenci, extrakci nebo otravování.

---

## 10.1 Zarovnání modelu a bezpečnost

Chraňte před škodlivými nebo politiku porušujícími výstupy.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Ověřte, že sada testů souladu (red-team výzvy, jailbreakové sondy, nepovolený obsah) je verzována a spuštěna při každém vydání modelu. |   1   | D/V  |
| 10.1.2 | Ověřte, že jsou dodržována pravidla pro odmítnutí a bezpečné dokončení.                                                                |   1   |  D   |
| 10.1.3 | Ověřte, že automatizovaný hodnotitel měří míru škodlivého obsahu a označuje regresi překračující stanovený práh.                       |   2   | D/V  |
| 10.1.4 | Ověřte, že protijailbreakové trénování je zdokumentováno a opakovatelné.                                                               |   2   |  D   |
| 10.1.5 | Ověřte, že formální důkazy dodržování politiky nebo certifikovaný dohled pokrývají kritické oblasti.                                   |   3   |  V   |

---

## 10.2 Zpevnění proti adversariálním příkladům

Zvyšte odolnost vůči manipulovaným vstupům. Robustní adversariální trénink a hodnotící benchmark jsou současnou nejlepší praxí.

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Ověřte, že projektové repozitáře obsahují konfigurace pro trénink protiútoků s reprodukovatelnými náhodnými semeny. |   1   |  D   |
| 10.2.2 | Ověřte, že detekce adversariálních příkladů vyvolává blokující výstrahy v produkčních pipelinech.                   |   2   | D/V  |
| 10.2.4 | Ověřte, že důkazy certifikované odolnosti nebo intervalové hranice pokrývají alespoň nejdůležitější kritické třídy. |   3   |  V   |
| 10.2.5 | Ověřte, že regresní testy používají adaptivní útoky k potvrzení, že nedochází k měřitelnému poklesu robustnosti.    |   3   |  V   |

---

## 10.3 Zmírnění inference členství

Omezte schopnost rozhodnout, zda byl záznam součástí tréninkových dat. Diferenciální soukromí a maskování skóre důvěry zůstávají nejúčinnějšími známými obranami.

|   #    | Description                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Ověřte, že regularizace entropie pro každý dotaz nebo škálování teploty snižuje příliš sebevědomé predikce. |   1   |  D   |
| 10.3.2 | Ověřte, že trénink využívá ε-omezenou diferenciálně soukromou optimalizaci pro citlivé datové sady.         |   2   |  D   |
| 10.3.3 | Ověřte, že simulace útoků (shadow-model nebo black-box) vykazují AUC útoku ≤ 0,60 na vyhrazených datech.    |   2   |  V   |

---

## 10.4 Odolnost proti invertování modelu

Zabraňte rekonstrukci soukromých atributů. Nedávné průzkumy zdůrazňují ořezávání výstupů a záruky diferencované ochrany soukromí (DP) jako praktické obrany.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Ověřte, že citlivé atributy nejsou nikdy přímo zobrazovány; tam, kde je to potřeba, používejte kategorie (buckets) nebo jednosměrné transformace. |   1   |  D   |
| 10.4.2 | Ověřte, že limity rychlosti dotazů omezují opakované adaptivní dotazy od stejného uživatele.                                                      |   1   | D/V  |
| 10.4.3 | Ověřte, že model je trénován s ochranou soukromí pomocí šumu.                                                                                     |   2   |  D   |

---

## 10.5 Ochrana proti extrakci modelu

Detekce a odrazení neautorizovaného klonování. Doporučují se vodotisky a analýza dotazových vzorů.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Ověřte, že inference brány vynucují globální a na klíč API specifické limity rychlosti přizpůsobené prahu zapamatování modelu.  |   1   |  D   |
| 10.5.2 | Ověřte, že statistiky entropie dotazu a plurality vstupu zásobují automatizovaný detektor extrakce.                             |   2   | D/V  |
| 10.5.3 | Ověřte, že křehké nebo pravděpodobnostní vodotisky lze dokázat s p < 0,01 při maximálně 1 000 dotazech proti podezřelému klonu. |   2   |  V   |
| 10.5.4 | Ověřte, zda jsou klíče vodoznaku a spouštěcí sady uloženy v hardwarovém bezpečnostním modulu a zda jsou každoročně rotovány.    |   3   |  D   |
| 10.5.5 | Ověřte, že události extraction-alert zahrnují závadné dotazy a jsou integrovány s návodem na reakci na incidenty.               |   3   |  V   |

---

## 10.6 Detekce otrávených dat v době inferenčního vyhodnocení

Identifikujte a neutralizujte zadní vrátka nebo otrávené vstupy.

|   #    | Description                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Ověřte, že vstupy procházejí detektorem anomálií (např. STRIP, skórování konzistence) před samotným odvozením modelu.                               |   1   |  D   |
| 10.6.2 | Ověřte, že prahy detektoru jsou nastaveny na čistých/infikovaných validačních sadách tak, aby dosahovaly méně než 5 % falešně pozitivních výsledků. |   1   |  V   |
| 10.6.3 | Ověřte, že vstupy označené jako otrávené spouštějí měkké blokování a pracovní postupy pro lidskou kontrolu.                                         |   2   |  D   |
| 10.6.4 | Ověřte, že detektory jsou testovány na stres prostřednictvím adaptivních, bezspouštěcích zadních vrátek.                                            |   2   |  V   |
| 10.6.5 | Ověřte, že metriky účinnosti detekce jsou zaznamenávány a pravidelně přehodnocovány s novými zpravodajskými informacemi o hrozbách.                 |   3   |  D   |

---

## 10.7 Dynamická adaptace bezpečnostní politiky

Aktualizace bezpečnostních politik v reálném čase na základě informací o hrozbách a analýzy chování.

|   #    | Description                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Ověřte, že bezpečnostní politiky lze aktualizovat dynamicky bez restartu agenta a zároveň zachovat integritu verze politiky.                          |   1   | D/V  |
| 10.7.2 | Ověřte, že aktualizace politik jsou kryptograficky podepsány autorizovaným bezpečnostním personálem a před aplikací ověřeny.                          |   2   | D/V  |
| 10.7.3 | Ověřte, že dynamické změny politik jsou zaznamenávány s úplnými auditními stopami včetně odůvodnění, schvalovacích řetězců a postupů pro návrat zpět. |   2   | D/V  |
| 10.7.4 | Ověřte, že adaptivní bezpečnostní mechanismy upravují citlivost detekce hrozeb na základě kontextu rizika a behaviorálních vzorců.                    |   3   | D/V  |
| 10.7.5 | Ověřte, že rozhodnutí o přizpůsobení politiky jsou vysvětlitelná a obsahují důkazy pro revizi bezpečnostním týmem.                                    |   3   | D/V  |

---

## 10.8 Bezpečnostní analýza založená na reflexi

Validace bezpečnosti prostřednictvím sebereflexe agenta a metakognitivní analýzy.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Ověřte, že mechanismy reflexe agenta zahrnují bezpečnostně orientované sebehodnocení rozhodnutí a akcí.                                        |   1   | D/V  |
| 10.8.2 | Ověřte, zda jsou výstupy reflexe validovány, aby se zabránilo manipulaci mechanismů sebeposouzení pomocí protivných vstupů.                    |   2   | D/V  |
| 10.8.3 | Ověřte, že meta-kognitivní bezpečnostní analýza identifikuje potenciální zaujatost, manipulaci nebo kompromitaci v procesech uvažování agenta. |   2   | D/V  |
| 10.8.4 | Ověřte, že varování zabezpečení založená na reflexi spouštějí rozšířené monitorování a potenciální pracovní postupy zahrnující lidský zásah.   |   3   | D/V  |
| 10.8.5 | Ověřte, že kontinuální učení ze zabezpečovacích reflexí zlepšuje detekci hrozeb, aniž by docházelo ke zhoršení legitimní funkčnosti.           |   3   | D/V  |

---

## 10.9 Evoluce a bezpečnost samo-zlepšování

Bezpečnostní kontroly pro agentní systémy schopné samo-modifikace a evoluce.

|   #    | Description                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Ověřte, že schopnosti sebesměřování jsou omezeny na určené bezpečné oblasti s formálními ověřovacími hranicemi.           |   1   | D/V  |
| 10.9.2 | Ověřte, že návrhy vývoje podléhají hodnocení dopadů na bezpečnost před jejich zavedením.                                  |   2   | D/V  |
| 10.9.3 | Ověřte, že mechanismy sebezlepšování zahrnují schopnosti zpětného vrácení s ověřením integrity.                           |   2   | D/V  |
| 10.9.4 | Ověřte, že bezpečnost meta-učení zabraňuje protivníkům v manipulaci s algoritmy zlepšování.                               |   3   | D/V  |
| 10.9.5 | Ověřte, že rekurzivní samo-vylepšování je omezeno formálními bezpečnostními omezeními s matematickými důkazy konvergence. |   3   | D/V  |

---

### Reference

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

