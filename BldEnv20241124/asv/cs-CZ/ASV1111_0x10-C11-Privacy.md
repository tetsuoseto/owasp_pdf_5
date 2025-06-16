# 11 Ochrana soukromí a správa osobních údajů

## Řídicí cíl

Dodržujte přísná ujištění o ochraně soukromí v celém životním cyklu umělé inteligence—sběr, trénink, inferenci a reakci na incidenty—tak, aby osobní údaje byly zpracovávány pouze s jasným souhlasem, v nejmenším nezbytném rozsahu, s prokazatelným vymazáním a formálními zárukami ochrany soukromí.

---

## 11.1 Anonymizace a minimalizace dat

|   #    | Description                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.1.1 | Ověřte, že přímé a téměř identifikátory jsou odstraněny nebo zahashovány.                                                                                      |   1   | D/V  |
| 11.1.2 | Ověřte, že automatizované audity měří k-anonymitu/l-rozmanitost a upozorní, když hodnoty klesnou pod stanovené limity.                                         |   2   | D/V  |
| 11.1.3 | Ověřte, že zprávy o důležitosti rysů modelu prokazují, že nedochází k úniku identifikátorů přes ε = 0,01 vzájemné informace.                                   |   2   |  V   |
| 11.1.4 | Ověřte, že formální důkazy nebo certifikace založená na syntetických datech ukazují, že riziko znovuidentifikace je ≤ 0,05 i při útocích pomocí propojení dat. |   3   |  V   |

---

## 11.2 Právo na zapomenutí a vymáhání mazání

|   #    | Description                                                                                                                                                                       | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Ověřte, že žádosti o vymazání údajů subjektu se šíří do surových datových sad, kontrolních bodů, embeddingů, protokolů a záloh v rámci dohod o úrovni služeb kratších než 30 dní. |   1   | D/V  |
| 11.2.2 | Ověřte, že rutiny „machine-unlearning“ fyzicky přeškolují nebo aproximují odstranění pomocí certifikovaných algoritmů pro zapomínání.                                             |   2   |  D   |
| 11.2.3 | Ověřte, že hodnocení pomocí shadow-modelu prokazuje, že zapomenuté záznamy ovlivňují méně než 1 % výstupů po procesu unlearningu.                                                 |   2   |  V   |
| 11.2.4 | Ověřte, že události smazání jsou neměnně zaznamenávány a auditovatelné pro regulátory.                                                                                            |   3   |  V   |

---

## 11.3 Opatření pro ochranu diferencované soukromí

|   #    | Description                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Ověřte, že panely pro sledování ztráty soukromí upozorňují, když kumulativní ε překročí limity stanovené politikou. |   2   | D/V  |
| 11.3.2 | Ověřte, že audity ochrany soukromí typu black-box odhadují ε̂ s odchylkou do 10 % od deklarované hodnoty.           |   2   |  V   |
| 11.3.3 | Ověřte, že formální důkazy zahrnují všechny post-tréninkové doladění a vnoření (embeddingy).                        |   3   |  V   |

---

## 11.4 Omezení účelu a ochrana proti rozšiřování rozsahu

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Ověřte, že každý datový soubor a kontrolní bod modelu obsahuje strojově čitelný štítek účelu v souladu s původním souhlasem.     |   1   |  D   |
| 11.4.2 | Ověřte, že runtime monitory zaznamenávají dotazy neslučitelné s deklarovaným účelem a vyvolávají měkké odmítnutí.                |   1   | D/V  |
| 11.4.3 | Ověřte, že brány založené na zásadách jako kódu blokují opětovné nasazení modelů do nových domén bez přezkumu DPIA.              |   3   |  D   |
| 11.4.4 | Ověřte, že formální důkazy sledovatelnosti ukazují, že každý životní cyklus osobních údajů zůstává v rámci souhlaseného rozsahu. |   3   |  V   |

---

## 11.5 Správa souhlasu a sledování zákonných důvodů

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | Ověřte, že platforma pro správu souhlasů (Consent-Management Platform, CMP) zaznamenává stav souhlasu (opt-in), účel a dobu uchovávání pro každý subjekt údajů. |   1   | D/V  |
| 11.5.2 | Ověřte, že API zpřístupňují souhlasné tokeny; modely musí před inferencí ověřit rozsah tokenu.                                                                  |   2   |  D   |
| 11.5.3 | Ověřte, že zamítnutý nebo stažený souhlas zastaví zpracovatelské procesy do 24 hodin.                                                                           |   2   | D/V  |

---

## 11.6 Federované učení s kontrolami soukromí

|   #    | Description                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Ověřte, že aktualizace klienta využívají přidání šumu lokální diferenciální ochrany soukromí před agregací. |   1   |  D   |
| 11.6.2 | Ověřte, že metriky tréninku jsou diferenciálně privátní a nikdy neodhalují ztrátu jednotlivého klienta.     |   2   | D/V  |
| 11.6.3 | Ověřte, že je povolena odolná agregace proti otravě (např. Krum/Trimmed-Mean).                              |   2   |  V   |
| 11.6.4 | Ověřte, že formální důkazy prokazují celkový ε rozpočet s méně než 5 ztrátou užitku.                        |   3   |  V   |

---

### Reference

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

