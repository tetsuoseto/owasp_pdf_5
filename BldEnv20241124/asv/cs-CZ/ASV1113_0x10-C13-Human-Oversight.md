# C13 Lidský dohled, odpovědnost a správa

## Řídicí cíl

Tato kapitola poskytuje požadavky na udržování lidského dohledu a jasných řetězců odpovědnosti v AI systémech, zajišťující vysvětlitelnost, transparentnost a etické řízení během celého životního cyklu AI.

---

## C13.1 Mechanismy nouzového vypínače a přepisování

Poskytněte cesty pro ukončení nebo návrat zpět, když je pozorováno nebezpečné chování AI systému.

|   #    | Description                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Ověřte, že existuje manuální mechanismus nouzového vypnutí pro okamžité zastavení inferencí a výstupů AI modelu. |   1   | D/V  |
| 13.1.2 | Ověřte, že ovládací prvky přepsání jsou přístupné pouze oprávněnému personálu.                                   |   1   |  D   |
| 13.1.3 | Ověřte, že postupy pro návrat zpět mohou obnovit předchozí verze modelu nebo operace v bezpečném režimu.         |   3   | D/V  |
| 13.1.4 | Ověřte, že mechanismy přepsání jsou pravidelně testovány.                                                        |   3   |  V   |

---

## C13.2 Kontrolní body rozhodování s lidským zapojením

Vyžadovat lidské schválení, pokud sázky překročí předem definované prahové hodnoty rizika.

|   #    | Description                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.2.1 | Ověřte, že vysoce riziková rozhodnutí umělé inteligence vyžadují před provedením výslovné schválení člověkem.                              |   1   | D/V  |
| 13.2.2 | Ověřte, že prahové hodnoty rizika jsou jasně definovány a automaticky spouštějí pracovní postupy pro lidskou kontrolu.                     |   1   |  D   |
| 13.2.3 | Ověřte, že časově citlivá rozhodnutí mají záložní postupy pro případ, kdy nelze získat schválení člověkem v požadovaných časových rámcích. |   2   |  D   |
| 13.2.4 | Ověřte, že postupy eskalace definují jasné úrovně pravomocí pro různé typy rozhodnutí nebo kategorie rizik, pokud je to relevantní.        |   3   | D/V  |

---

## C13.3 Řetězec odpovědnosti a auditovatelnost

Zaznamenávejte akce operátora a rozhodnutí modelu.

|   #    | Description                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Ověřte, že všechna rozhodnutí AI systému a lidské zásahy jsou zaznamenány s časovými značkami, identitami uživatelů a odůvodněním rozhodnutí. |   1   | D/V  |
| 13.3.2 | Ověřte, že auditní záznamy nemohou být pozměněny a obsahují mechanismy pro ověření integrity.                                                 |   2   |  D   |

---

## C13.4 Techniky vysvětlitelné umělé inteligence (Explainable-AI)

Význam povrchových rysů, kontrafaktuální případy a lokální vysvětlení.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.4.1 | Ověřte, že AI systémy poskytují základní vysvětlení svých rozhodnutí v lidsky čitelném formátu.                                                                    |   1   | D/V  |
| 13.4.2 | Ověřte, že kvalita vysvětlení je potvrzena prostřednictvím lidských evaluačních studií a metrik.                                                                   |   2   |  V   |
| 13.4.3 | Ověřte, že skóre důležitosti funkcí nebo metody přiřazení (SHAP, LIME, atd.) jsou k dispozici pro kritická rozhodnutí.                                             |   3   | D/V  |
| 13.4.4 | Ověřte, že kontra-faktuální vysvětlení ukazují, jak by bylo možné upravit vstupy tak, aby se změnily výsledky, pokud je to relevantní pro případ použití a doménu. |   3   |  V   |

---

## C13.5 Karty modelů a oznámení o použití

Udržujte modelové karty pro zamýšlené použití, metriky výkonu a etické úvahy.

|   #    | Description                                                                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Ověřte, že modelové karty dokumentují zamýšlené případy použití, omezení a známé režimy selhání.                                                                                         |   1   |  D   |
| 13.5.2 | Ověřte, že metriky výkonnosti jsou zveřejněny napříč různými relevantními použitými scénáři.                                                                                             |   1   | D/V  |
| 13.5.3 | Ověřte, že jsou etické úvahy, hodnocení zaujatosti, posouzení spravedlnosti, charakteristiky tréninkových dat a známá omezení tréninkových dat dokumentována a pravidelně aktualizována. |   2   |  D   |
| 13.5.4 | Ověřte, že modelové karty jsou verzovány a udržovány po celou dobu životního cyklu modelu s evidencí změn.                                                                               |   2   | D/V  |

---

## C13.6 Kvantifikace nejistoty

Šiřte skóre důvěry nebo míry entropie ve odpovědích.

|   #    | Description                                                                                                 | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Ověřte, že AI systémy poskytují s výstupy také hodnoty pravděpodobnosti nebo míry nejistoty.                |   1   |  D   |
| 13.6.2 | Ověřte, že prahové hodnoty nejistoty spouštějí další kontrolu člověkem nebo alternativní rozhodovací cesty. |   2   | D/V  |
| 13.6.3 | Ověřte, že metody kvantifikace nejistoty jsou kalibrovány a validovány vůči datům skutečné hodnoty.         |   2   |  V   |
| 13.6.4 | Ověřte, že šíření neurčitosti je zachováno v průběhu vícekrokových pracovních postupů AI.                   |   3   | D/V  |

---

## C13.7 Uživatelské transparentní zprávy

Pravidelně zveřejňujte informace o incidentech, odchylkách a využívání dat.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Ověřte, že politiky využívání dat a postupy řízení souhlasu uživatelů jsou jasně komunikovány zainteresovaným stranám.                      |   1   | D/V  |
| 13.7.2 | Ověřte, že jsou prováděny hodnocení dopadů umělé inteligence a že jejich výsledky jsou zahrnuty do zpráv.                                   |   2   | D/V  |
| 13.7.3 | Ověřte, že pravidelně zveřejňované zprávy o transparentnosti obsahují sdělení o incidentech AI a provozních metrikách v přiměřeném rozsahu. |   2   | D/V  |

### Reference

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

