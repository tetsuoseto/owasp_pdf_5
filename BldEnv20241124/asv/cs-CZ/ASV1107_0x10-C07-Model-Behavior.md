# Chování modelu C7, řízení výstupu a zajištění bezpečnosti

## Řídicí cíl

Výstupy modelu musí být strukturované, spolehlivé, bezpečné, vysvětlitelné a kontinuálně monitorované v produkci. Tím se snižuje výskyt halucinací, úniky soukromí, škodlivý obsah a nekontrolovatelné akce, zároveň se zvyšuje důvěra uživatelů a soulad s regulacemi.

---

## C7.1 Vynucení formátu výstupu

Přísná schémata, omezené dekódování a následná validace zastaví nesprávný nebo škodlivý obsah dříve, než se rozšíří.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.1.1 | Ověřte, že schémata odpovědí (například JSON Schema) jsou poskytnuta v systémovém promptu a každý výstup je automaticky ověřován; výstupy, které neodpovídají, vyvolávají opravu nebo odmítnutí. |   1   | D/V  |
| 7.1.2 | Ověřte, že je povoleno omezené dekódování (stopovací tokeny, regulární výrazy, maximální počet tokenů) k zabránění přetečení nebo vedlejším kanálům injekce do promptu.                          |   1   | D/V  |
| 7.1.3 | Ověřte, že následující komponenty považují výstupy za nedůvěryhodné a ověřují je vůči schématům nebo bezpečným deserializérům odolným vůči injekci.                                              |   2   | D/V  |
| 7.1.4 | Ověřte, že události nesprávného výstupu jsou zaznamenávány, omezeny rychlostí a zobrazeny v monitoringu.                                                                                         |   3   |  V   |

---

## C7.2 Detekce a zmírňování halucinací

Odhad nejistoty a záložní strategie omezují vymyšlené odpovědi.

|   #   | Description                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Ověřte, že pravděpodobnosti na úrovni tokenů, souborová sebe-konzistence nebo jemně doladěné detektory halucinací přiřazují ke každé odpovědi skóre důvěryhodnosti.                   |   1   | D/V  |
| 7.2.2 | Ověřte, že odpovědi pod konfigurovatelným prahem důvěryhodnosti spouštějí náhradní pracovní postupy (např. generování s podporou vyhledávání, sekundární model nebo lidská kontrola). |   1   | D/V  |
| 7.2.3 | Ověřte, že incidenty halucinací jsou označeny metadaty o základní příčině a jsou předávány do analyzovacích procesů po události a do postupů doladění.                                |   2   | D/V  |
| 7.2.4 | Ověřte, že prahy a detektory jsou pře-kalibrovány po významných aktualizacích modelu nebo znalostní báze.                                                                             |   3   | D/V  |
| 7.2.5 | Ověřte, že vizualizace na panelu sledují míru halucinací.                                                                                                                             |   3   |  V   |

---

## C7.3 Výstupní filtrování bezpečnosti a soukromí

Filtry zásad a pokrytí red-teamem chrání uživatele a důvěrná data.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Ověřte, že před a po generaci klasifikátory blokují nenávistný obsah, obtěžování, sebepoškozování, extremistický a sexuálně explicitní obsah v souladu s politikou. |   1   | D/V  |
| 7.3.2 | Ověřte, že detekce PII/PCI a automatické redakce probíhají u každé odpovědi; porušení vyvolávají incident týkající se ochrany soukromí.                             |   1   | D/V  |
| 7.3.3 | Ověřte, že štítky důvěrnosti (např. obchodní tajemství) se přenášejí napříč modalitami, aby se zabránilo úniku v textu, obrázcích nebo kódu.                        |   2   |  D   |
| 7.3.4 | Ověřte, že pokusy o obejití filtru nebo klasifikace s vysokým rizikem vyžadují sekundární schválení nebo opětovné ověření uživatele.                                |   3   | D/V  |
| 7.3.5 | Ověřte, že prahové hodnoty filtrování odpovídají právním jurisdikcím a kontextu věku/role uživatele.                                                                |   3   | D/V  |

---

## C7.4 Omezení výstupu a akcí

Omezení rychlosti a schvalovací brány zabraňují zneužití a nadměrné autonomii.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Ověřte, že limity na uživatele a na klíče API omezují počet požadavků, tokenů a náklady s exponenciálním zpětným odstupem při chybách 429.                                  |   1   |  D   |
| 7.4.2 | Ověřte, že privilegované akce (zápisy do souborů, spuštění kódu, síťové volání) vyžadují schválení založené na politice nebo zásah člověka v procesu.                       |   1   | D/V  |
| 7.4.3 | Ověřte, že kontroly konzistence mezi různými modalitami zajišťují, že obrázky, kód a text generované pro stejný požadavek nemohou být použity k pašování škodlivého obsahu. |   2   | D/V  |
| 7.4.4 | Ověřte, zda jsou hloubka delegace agenta, limity rekurze a povolené seznamy nástrojů výslovně nakonfigurovány.                                                              |   2   |  D   |
| 7.4.5 | Ověřte, že porušení limitů generuje strukturované bezpečnostní události pro příjem do SIEM.                                                                                 |   3   |  V   |

---

## C7.5 Vysvětlitelnost výstupů

Transparentní signály zlepšují důvěru uživatelů a interní ladění.

|   #   | Description                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Ověřte, že uživatelsky viditelné skóre důvěryhodnosti nebo stručné shrnutí zdůvodnění jsou zobrazeny, když to hodnocení rizika považuje za vhodné. |   2   | D/V  |
| 7.5.2 | Ověřte, že generovaná vysvětlení neodhalují citlivé systémové výzvy ani vlastní data.                                                              |   2   | D/V  |
| 7.5.3 | Ověřte, že systém zachycuje logaritmické pravděpodobnosti na úrovni tokenů nebo pozornostní mapy a ukládá je pro autorizovanou kontrolu.           |   3   |  D   |
| 7.5.4 | Ověřte, že artefakty vysvětlitelnosti jsou řízeny verzemi společně s vydáními modelu pro auditovatelnost.                                          |   3   |  V   |

---

## C7.6 Integrace monitorování

Sledovatelnost v reálném čase uzavírá zpětnou vazbu mezi vývojem a produkcí.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Ověřte, že metriky (porušení schématu, míra halucinací, toxicita, úniky osobních údajů, latence, náklady) jsou přenášeny do centrálního monitorovacího systému. |   1   |  D   |
| 7.6.2 | Ověřte, že jsou definovány prahové hodnoty upozornění pro každý bezpečnostní metrík, včetně cest eskalace pro pohotovostní zásahy.                              |   1   |  V   |
| 7.6.3 | Ověřte, že řídicí panely korelují výstupní anomálie s modelem/verzí, příznakem funkce a změnami dat z nadřazených zdrojů.                                       |   2   |  V   |
| 7.6.4 | Ověřte, že monitorovací data se zpětně využívají k přeškolení, doladění nebo aktualizacím pravidel v rámci zdokumentovaného pracovního postupu MLOps.           |   2   | D/V  |
| 7.6.5 | Ověřte, že monitorovací pipeline jsou testovány na průniky a mají řízený přístup, aby se zabránilo úniku citlivých záznamů.                                     |   3   |  V   |

---

## 7.7 Opatření pro ochranu generativních médií

Zajistěte, aby systémy umělé inteligence nevytvářely nelegální, škodlivý nebo nepovolený mediální obsah tím, že prosadíte politiky omezení, ověření výstupu a sledovatelnost.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Ověřte, že systémové výzvy a uživatelské pokyny výslovně zakazují generování nelegálního, škodlivého nebo nevyžádaného deepfake obsahu (např. obrázky, videa, zvuk).                               |   1   | D/V  |
| 7.7.2 | Ověřte, zda jsou příkazy filtrovány kvůli pokusům o generování napodobenin, sexuálně explicitních deepfake videí nebo médií zobrazujících skutečné osoby bez jejich souhlasu.                      |   2   | D/V  |
| 7.7.3 | Ověřte, že systém používá percepční hashování, detekci vodoznaků nebo otiskování pro zabránění neoprávněné reprodukce materiálů chráněných autorskými právy.                                       |   2   |  V   |
| 7.7.4 | Ověřte, že veškerá generovaná média jsou kryptograficky podepsána, opatřena vodoznakem nebo obsahují zabudovaná metadata s ochranou proti manipulaci pro následnou sledovatelnost.                 |   3   | D/V  |
| 7.7.5 | Ověřte, že pokusy o obejití (např. zakrývání příkazů, slang, protivné formulace) jsou detekovány, zaznamenávány a omezovány rychlostí; opakované zneužívání je předkládáno monitorovacím systémům. |   3   |  V   |

## Reference

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

