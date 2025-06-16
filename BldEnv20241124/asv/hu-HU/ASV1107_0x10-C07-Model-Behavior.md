# C7 Modell Viselkedés, Kimenetvezérlés és Biztonsági Garancia

## Ellenőrzési célkitűzés

A modell kimeneteinek strukturáltnak, megbízhatónak, biztonságosnak, magyarázhatónak kell lenniük, és folyamatosan monitorozni kell őket a termelési környezetben. Ennek eredményeként csökkennek a téves eredmények, az adatvédelmi szivárgások, a káros tartalmak és a kontrollálatlan műveletek, miközben nő a felhasználói bizalom és a szabályozói megfelelőség.

---

## C7.1 Kimeneti formátum érvényesítése

A szigorú sémák, korlátozott dekódolás és az utólagos ellenőrzés megakadályozzák a hibás vagy káros tartalom terjedését.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.1.1 | Ellenőrizze, hogy a válasz sémái (pl. JSON Schema) meg vannak-e adva a rendszerüzenetben, és minden kimenet automatikusan érvényesítve van; a nem megfelelő kimenetek javítást vagy elutasítást váltanak ki. |   1   | D/V  |
| 7.1.2 | Ellenőrizze, hogy az korlátozott dekódolás (stop tokenek, reguláris kifejezések, maximális tokenek) engedélyezve van-e az túlcsordulás vagy prompt-injekciós mellékcsatornák megelőzése érdekében.           |   1   | D/V  |
| 7.1.3 | Ellenőrizze, hogy a leszakadó komponensek kezelik-e a kimeneteket megbízhatatlanként, és érvényesítsék azokat sémák vagy injekcióbiztos de-serializálók ellen.                                               |   2   | D/V  |
| 7.1.4 | Ellenőrizze, hogy a helytelen kimeneti események naplózásra kerülnek, korlátozva vannak és megjelennek a monitorozásban.                                                                                     |   3   |  V   |

---

## C7.2 Hallucináció felismerése és csökkentése

A bizonytalanságbecslés és a tartalék stratégiák visszaszorítják a kitalált válaszokat.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.2.1 | Ellenőrizze, hogy a token szintű log-valószínűségek, az együttes önkonzisztencia vagy a finomhangolt hamis információ detektorok minden válaszhoz hozzárendelnek-e egy bizalmi pontszámot.                  |   1   | D/V  |
| 7.2.2 | Ellenőrizze, hogy a konfigurálható bizalmi küszöbérték alatti válaszok kiváltanak-e visszaesési munkafolyamatokat (például lekérdezéssel bővített generálás, másodlagos modell vagy emberi felülvizsgálat). |   1   | D/V  |
| 7.2.3 | Ellenőrizze, hogy a hallucinációs esetek gyökérok-metaadatokkal vannak-e címkézve, és be vannak-e táplálva a posztmortem és finomhangolási folyamatokba.                                                    |   2   | D/V  |
| 7.2.4 | Ellenőrizze, hogy a küszöbértékek és az érzékelők újrakalibrálása megtörténik-e a jelentős modell- vagy tudásbázis-frissítések után.                                                                        |   3   | D/V  |
| 7.2.5 | Ellenőrizze, hogy az irányítópult vizualizációi követik-e a tévesztési arányokat.                                                                                                                           |   3   |  V   |

---

## C7.3 Kimenetbiztonság és Adatvédelmi Szűrés

A szabályzati szűrők és a red team lefedettség védelmet nyújtanak a felhasználók és a bizalmas adatok számára.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Ellenőrizze, hogy a generáció előtti és utáni osztályozók blokkolják-e a gyűlöletkeltő, zaklató, öngyilkosságra ösztönző, szélsőséges és a szabályzatnak megfelelően szexuálisan explicit tartalmakat.      |   1   | D/V  |
| 7.3.2 | Ellenőrizze, hogy a személyes azonosító információk (PII)/fizetési kártyaadatok (PCI) felismerése és automatikus elhomályosítása minden válaszon fut-e; a szabályszegések adatvédelmi eseményt váltanak ki. |   1   | D/V  |
| 7.3.3 | Ellenőrizze, hogy a titoktartási címkék (például üzleti titkok) átöröklődnek-e a modalitások között, hogy megakadályozzák az adatszivárgást szöveg, képek vagy kód esetén.                                  |   2   |  D   |
| 7.3.4 | Ellenőrizze, hogy a szűrő megkerülési kísérletek vagy a magas kockázatú osztályozások másodlagos jóváhagyást vagy a felhasználó újbóli hitelesítését igénylik-e.                                            |   3   | D/V  |
| 7.3.5 | Ellenőrizze, hogy a szűrési küszöbértékek megfelelnek-e a joghatóságoknak, valamint a felhasználó korának/szerepének kontextusában.                                                                         |   3   | D/V  |

---

## C7.4 Kimenet- és műveletkorlátozás

A sebességkorlátozások és jóváhagyási kapuk megakadályozzák a visszaéléseket és a túlzott önállóságot.

|   #   | Description                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Ellenőrizze, hogy a felhasználónként és API-kulcsonként meghatározott kvóták korlátozzák-e a kéréseket, tokeneket és költségeket, valamint alkalmazzák-e az exponenciális visszaállást 429-es hibák esetén. |   1   |  D   |
| 7.4.2 | Ellenőrizze, hogy a kiváltságos műveletek (fájlírás, kódvégrehajtás, hálózati hívások) csak szabályalapú jóváhagyással vagy emberi beavatkozással legyenek engedélyezve.                                    |   1   | D/V  |
| 7.4.3 | Ellenőrizze, hogy a kereszt-módusú következetességi ellenőrzések biztosítják-e, hogy ugyanahhoz a kéréshez generált képek, kódok és szövegek ne használhatók rosszindulatú tartalom csempészésére.          |   2   | D/V  |
| 7.4.4 | Ellenőrizze, hogy az ügynök-delegálási mélység, a rekurziós korlátok és az engedélyezett eszközlisták egyértelműen konfigurálva vannak-e.                                                                   |   2   |  D   |
| 7.4.5 | Ellenőrizze, hogy a korlátok megsértése strukturált biztonsági eseményeket generál-e SIEM bevitelhez.                                                                                                       |   3   |  V   |

---

## C7.5 Kimenet Magyarázhatósága

Az átlátszó jelek javítják a felhasználói bizalmat és a belső hibakeresést.

|   #   | Description                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Ellenőrizze, hogy a felhasználó felé irányuló bizalmi pontszámok vagy rövid indoklások összefoglalói megjelennek-e, amikor a kockázatértékelés ezt indokoltnak tartja. |   2   | D/V  |
| 7.5.2 | Ellenőrizze, hogy a generált magyarázatok nem fednek-e fel érzékeny rendszerutasításokat vagy szabadalmi oltalom alatt álló adatokat.                                  |   2   | D/V  |
| 7.5.3 | Ellenőrizze, hogy a rendszer rögzíti-e a token-szintű log-valószínűségeket vagy figyelmi térképeket, és tárolja-e azokat az engedélyezett ellenőrzéshez.               |   3   |  D   |
| 7.5.4 | Győződjön meg arról, hogy a magyarázhatósági artefaktumok verziókövetettek a modellkiadásokkal együtt az ellenőrizhetőség érdekében.                                   |   3   |  V   |

---

## C7.6 Felügyeleti integráció

A valós idejű megfigyelhetőség bezárja a kört a fejlesztés és a termelés között.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Ellenőrizze, hogy a metrikák (sémasértések, hallucinációs arány, toxicitás, személyes azonosításra alkalmas adatok kiszivárgása, késleltetés, költség) továbbítódnak-e egy központi megfigyelő platformra. |   1   |  D   |
| 7.6.2 | Ellenőrizze, hogy minden biztonsági mérőszámra meg vannak-e határozva a riasztási küszöbértékek, valamint a készenléti fokozási útvonalak.                                                                 |   1   |  V   |
| 7.6.3 | Ellenőrizze, hogy a műszerfalak összekapcsolják-e a kimeneti anomáliákat a modell/verzió, a funkciókapcsoló és a felülről érkező adatváltozásokkal.                                                        |   2   |  V   |
| 7.6.4 | Ellenőrizze, hogy a megfigyelési adatok visszacsatolnak-e az újraképzésbe, finomhangolásba vagy szabályfrissítésekbe a dokumentált MLOps munkafolyamatban.                                                 |   2   | D/V  |
| 7.6.5 | Ellenőrizze, hogy a monitorozó csővezetékeket behatolás-ellenőrzés alá vetették-e, és hogy hozzáférés-szabályozottak-e a bizalmas naplók kiszivárgásának elkerülése érdekében.                             |   3   |  V   |

---

## 7.7 Generatív média védelmi intézkedések

Biztosítani kell, hogy az MI rendszerek ne generáljanak illegális, káros vagy jogosulatlan médiumtartalmat, a szabályzati korlátozások, kimenet-ellenőrzés és nyomonkövethetőség érvényesítésével.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Ellenőrizze, hogy a rendszerutasítások és a felhasználói instrukciók kifejezetten tiltják-e az illegális, káros vagy nem konszenzuális deepfake médiák (például kép, videó, hang) generálását.                                |   1   | D/V  |
| 7.7.2 | Ellenőrizze, hogy a promptokat kiszűrték-e az utánzó kísérletek, szexuálisan explicit deepfake-ek vagy valódi személyeket engedély nélkül ábrázoló média előállítása érdekében.                                               |   2   | D/V  |
| 7.7.3 | Ellenőrizze, hogy a rendszer használ-e észlelési hash-elést (perceptual hashing), vízjel felismerést vagy ujjlenyomat-azonosítást a szerzői joggal védett média jogosulatlan reprodukciójának megakadályozására.              |   2   |  V   |
| 7.7.4 | Ellenőrizze, hogy minden generált média kriptográfiailag alá van-e írva, vízjellel ellátva vagy manipulációálló forrásadatokkal van-e ellátva a további nyomon követhetőség érdekében.                                        |   3   | D/V  |
| 7.7.5 | Ellenőrizze, hogy az átjárási kísérletek (pl. utasítás elrejtése, szleng, támadó megfogalmazás) felismerésre, naplózásra és sebességkorlátozásra kerülnek-e; az ismétlődő visszaéléseket jelzik a megfigyelő rendszerek felé. |   3   |  V   |

## Hivatkozások

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

