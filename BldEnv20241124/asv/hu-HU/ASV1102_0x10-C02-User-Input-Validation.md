# C2 Felhasználói Bemenet Érvényesítés

## Ellenőrzési Célkitűzés

A felhasználói bemenet megbízható érvényesítése az elsődleges védelem az AI rendszerek legkárosabb támadásaival szemben. A prompt befecskendezési támadások felülírhatják a rendszer utasításait, kiszivárogtathatják az érzékeny adatokat, vagy a modellt nem engedélyezett viselkedés felé terelhetik. Kutatások szerint, amíg nincsenek dedikált szűrők és utasítási hierarchiák, a nagyon hosszú kontextus ablakokat kihasználó "többszörös" jailbreak támadások hatékonyak lesznek. Emellett a finom ellenfél perturbációs támadások — például homoglif cserék vagy leetspeak — csendesen megváltoztathatják a modell döntéseit.

---

## C2.1 Utasításbefecskendezés elleni védelem

A prompt befecskendezés az egyik legnagyobb kockázat az AI rendszerek számára. Ennek a taktikának a kivédésére statikus mintaszűrők, dinamikus osztályozók és az utasítási hierarchia betartásának kombinációját alkalmazzák.

|   #   | Description                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Ellenőrizze, hogy a felhasználói bemenetek folyamatosan frissített ismert promptinjekció-mintákat tartalmazó könyvtár ellen legyenek szűrve (például jailbreak kulcsszavak, "figyelmen kívül hagyni az előzőt", szerepjáték-láncok, közvetett HTML/URL támadások). |   1   | D/V  |
| 2.1.2 | Ellenőrizze, hogy a rendszer érvényesíti-e az utasítási hierarchiát, amelyben a rendszer- vagy fejlesztői üzenetek felülírják a felhasználói utasításokat, még a kontextusablak bővítése után is.                                                                  |   1   | D/V  |
| 2.1.3 | Ellenőrizze, hogy a támadó értékelési teszteket (például a Red Team "many-shot" kéréseit) minden modell- vagy prompt-sablon kiadás előtt elvégzik-e, sikerességi küszöbértékek és automatizált akadályozók alkalmazásával a visszaesések elkerülésére.             |   2   | D/V  |
| 2.1.4 | Ellenőrizze, hogy a harmadik féltől származó tartalmakból (weboldalak, PDF-ek, e-mailek) eredő kérések elkülönített elemzési környezetben vannak-e megtisztítva, mielőtt beillesztésre kerülnek a fő kérésbe.                                                      |   2   |  D   |
| 2.1.5 | Ellenőrizze, hogy minden prompt-szűrő szabályfrissítés, osztályozó modellverzió és tiltólista változás verziókezelve és auditálható legyen.                                                                                                                        |   3   | D/V  |

---

## C2.2 Ellenséges példák elleni ellenálló képesség

A természetes nyelvfeldolgozó (NLP) modellek továbbra is érzékenyek az apró karakter- vagy szószintű módosításokra, amelyeket az emberek gyakran nem vesznek észre, ám a modellek hajlamosak tévesen osztályozni.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Ellenőrizze, hogy az alapvető bemeneti normalizációs lépések (Unicode NFC, homoglifák leképezése, szóközök eltávolítása) lefutnak-e a tokenizálás előtt.                                                                                                                  |   1   |  D   |
| 2.2.2 | Ellenőrizze, hogy a statisztikai anomáliaészlelés jelzi-e azokat a bemeneteket, amelyek szokatlanul magas szerkesztési távolsággal rendelkeznek a nyelvi normákhoz képest, túlzottan ismétlődő tokeneket tartalmaznak, vagy rendellenes beágyazási távolságokat mutatnak. |   2   | D/V  |
| 2.2.3 | Ellenőrizze, hogy az inferencia-pipeline támogatja-e az opcionális, támadásálló képzéssel megerősített modellváltozatokat vagy védelmi rétegeket (például véletlenszerűsítés, védelmi desztilláció) a nagy kockázatú végpontok számára.                                   |   2   |  D   |
| 2.2.4 | Ellenőrizze, hogy a gyanús támadó bemenetek elkülönítésre kerülnek, és a teljes adatcsomaggal együtt naplózva vannak (az azonosítható személyes adatok eltávolítása után).                                                                                                |   2   |  V   |
| 2.2.5 | Ellenőrizze, hogy a robosztussági mutatókat (ismert támadási csomagok sikerességi aránya) időben nyomon követik-e, és hogy a regressziók kiadási blokkolót indítanak-e.                                                                                                   |   3   | D/V  |

---

## C2.3 Séma, típus és hossz validáció

Az AI támadások, amelyek hibás vagy túlméretezett bemeneteket tartalmaznak, elemzési hibákat, mezők közötti prompt szivárgást és erőforrás-kimerülést okozhatnak. A szigorú séma-ellenőrzés szintén alapfeltétel a determinisztikus eszközhívások végrehajtásakor.

|   #   | Description                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Ellenőrizze, hogy minden API vagy függvényhívási végpont egyértelmű bemeneti sémát definiál-e (JSON Schema, Protobuf vagy multimodális megfelelő), és hogy a bemenetek érvényesítve vannak-e a prompt összeállítása előtt. |   1   |  D   |
| 2.3.2 | Ellenőrizze, hogy a maximális token- vagy bájthatárokat meghaladó bemenetek biztonságos hibával elutasításra kerülnek, és soha nem kerülnek néma levágásra.                                                                |   1   | D/V  |
| 2.3.3 | Ellenőrizze, hogy a típusellenőrzések (pl. numerikus tartományok, enumerációs értékek, képek/hangok MIME-típusai) szerveroldalon is érvényesítve legyenek, ne csak a kliensoldali kódban.                                  |   2   | D/V  |
| 2.3.4 | Ellenőrizze, hogy a szemantikai validátorok (pl. JSON Schema) állandó idő alatt futnak-e, hogy megakadályozzák az algoritmikus DoS-t.                                                                                      |   2   |  D   |
| 2.3.5 | Ellenőrizze, hogy az érvényesítési hibákat vörösített adatdarabokkal és egyértelmű hibakódokkal rögzítik-e a biztonsági kivizsgálás segítése érdekében.                                                                    |   3   |  V   |

---

## C2.4 Tartalom- és irányelvellenőrzés

A fejlesztőknek képesnek kell lenniük felismerni a szintaktikailag érvényes, de tiltott tartalomra (például illegális utasítások, gyűlöletbeszéd és szerzői jog által védett szöveg) vonatkozó kéréseket, és meg kell akadályozniuk azok terjedését.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Ellenőrizze, hogy a tartalom osztályozó (nulladik lépéses vagy finomhangolt) minden bemenetet értékel-e erőszak, önkárosítás, gyűlölet, szexuális tartalom és illegális kérés szempontjából, konfigurálható küszöbértékekkel. |   1   |  D   |
| 2.4.2 | Ellenőrizze, hogy a szabályzatot sértő bemenetek egységes elutasításokat vagy biztonságos befejezéseket kapnak-e, hogy ne terjedjenek tovább a további LLM-hívásokban.                                                        |   1   | D/V  |
| 2.4.3 | Ellenőrizze, hogy a szűrőmodellt vagy szabályrendszert legalább negyedévente átképezték/frissítették-e, újonnan észlelt jailbreak vagy szabálykerülési minták bevonásával.                                                    |   2   |  D   |
| 2.4.4 | Ellenőrizze, hogy a szűrés megfelel-e a felhasználóra szabott szabályzatoknak (életkor, regionális jogi korlátozások) a kérés időpontjában feloldott attribútumalapú szabályok révén.                                         |   2   |  D   |
| 2.4.5 | Ellenőrizze, hogy a szűrési naplók tartalmazzák-e az osztályozó bizalmi pontszámait és a szabályzati kategória címkéket a SOC korrelációhoz és a későbbi red-team lejátszáshoz.                                               |   3   |  V   |

---

## C2.5 Bemeneti sebességkorlátozás és visszaélések megelőzése

A fejlesztőknek meg kell akadályozniuk a visszaéléseket, az erőforrás-kimerülést és az automatizált támadásokat az AI rendszerek ellen az input sebességének korlátozásával és a rendellenes használati minták felismerésével.

|   #   | Description                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.5.1 | Ellenőrizze, hogy minden bemeneti végponton érvényesülnek-e a felhasználónkénti, IP-címenkénti és API-kulcsonkénti lekérési korlátozások.                          |   1   | D/V  |
| 2.5.2 | Ellenőrizze, hogy a burst és fenntartott sebességkorlátok megfelelően vannak-e beállítva a DoS és brute force támadások megelőzése érdekében.                      |   2   | D/V  |
| 2.5.3 | Ellenőrizze, hogy a rendellenes használati minták (pl. gyors egymás utáni kérések, bemeneti túlterhelés) automatikus blokkolást vagy továbbításokat váltanak-e ki. |   2   | D/V  |
| 2.5.4 | Ellenőrizze, hogy az visszaélés megelőzési naplók megőrzésre és áttekintésre kerülnek-e az újonnan megjelenő támadási minták felderítése érdekében.                |   3   |  V   |

---

## C2.6 Többmódusú bemeneti érvényesítés

Az AI rendszereknek robosztus érvényesítést kell tartalmazniuk nem szöveges bemenetekre (képek, hang, fájlok), hogy megakadályozzák az injekciót, kikerülést vagy az erőforrásokkal való visszaélést.

|   #   | Description                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.6.1 | Ellenőrizze, hogy minden nem szöveges bemenetet (képek, hangok, fájlok) típus, méret és formátum szerint validálnak-e a feldolgozás előtt. |   1   |  D   |
| 2.6.2 | Győződjön meg arról, hogy a fájlokat malware és szteganográfiai terhelések szempontjából átvizsgálják a feldolgozás előtt.                 |   2   | D/V  |
| 2.6.3 | Ellenőrizze, hogy a kép/hang bemeneteket ártalmas módosítások vagy ismert támadási minták szempontjából vizsgálták-e.                      |   2   | D/V  |
| 2.6.4 | Ellenőrizze, hogy a multimodális bemeneti érvényesítési hibákat naplózzák-e, és hogy ezek riasztásokat váltanak-e ki vizsgálat céljából.   |   3   |  V   |

---

## C2.7 Bemeneti eredetiség és hivatkozás

Az AI rendszereknek támogatniuk kell az auditálást, visszaélések nyomon követését és a megfelelést azáltal, hogy figyelik és megjelölik az összes felhasználói bemenet eredetét.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Ellenőrizze, hogy minden felhasználói bemenet metaadatokkal (felhasználói azonosító, munkamenet, forrás, időbélyeg, IP-cím) van-e ellátva a bevitelkor. |   1   | D/V  |
| 2.7.2 | Ellenőrizze, hogy az összes feldolgozott bemenet esetében a származási metaadatok megőrződnek és auditálhatók legyenek.                                 |   2   | D/V  |
| 2.7.3 | Ellenőrizze, hogy az anomalikus vagy nem megbízható bemeneti forrásokat jelzik-e, és fokozott ellenőrzés vagy blokkolás alá esnek-e.                    |   2   | D/V  |

---

## C2.8 Valós idejű adaptív fenyegetésészlelés

A fejlesztőknek fejlett, mesterséges intelligenciára specializált fenyegetésészlelő rendszereket kell alkalmazniuk, amelyek alkalmazkodnak az új támadási mintákhoz, és valós idejű védelmet nyújtanak összekompilált mintaillesztéssel.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Ellenőrizze, hogy a fenyegetésészlelési minták optimalizált reguláris kifejezés motorokká vannak-e fordítva a nagy teljesítményű valós idejű szűrés érdekében, minimális késleltetési hatással.                                   |   1   | D/V  |
| 2.8.2 | Ellenőrizze, hogy a fenyegetésészlelő rendszerek külön mintakönyvtárakat tartanak-e fenn a különböző fenyegetéskategóriákhoz (utasításinjekció, káros tartalom, érzékeny adatok, rendszerparancsok).                              |   1   | D/V  |
| 2.8.3 | Ellenőrizze, hogy az adaptív fenyegetésészlelés tartalmaz-e gépi tanulási modelleket, amelyek frissítik a fenyegetésérzékenységet a támadások gyakorisága és sikerrátái alapján.                                                  |   2   | D/V  |
| 2.8.4 | Ellenőrizze, hogy a valós idejű fenyegetésfelderítő adatok automatikusan frissítik-e a mintagyűjteményeket új támadási aláírásokkal és kompromittálódási indikátorokkal (IOC-k).                                                  |   2   | D/V  |
| 2.8.5 | Bizonyosodjon meg arról, hogy a fenyegetésészlelési hamis pozitív arányokat folyamatosan figyelik, és a minták specifikusságát automatikusan hangolják úgy, hogy minimalizálják a jogos használati esetekbe történő beavatkozást. |   3   | D/V  |
| 2.8.6 | Ellenőrizze, hogy a kontextuális fenyegetés elemzés figyelembe veszi-e a bemeneti forrást, a felhasználói viselkedési mintákat és a munkamenet előzményeit a felismerési pontosság javítása érdekében.                            |   3   | D/V  |
| 2.8.7 | Ellenőrizze, hogy a fenyegetésészlelési teljesítménymutatókat (észlelési arány, feldolgozási késleltetés, erőforrás-használat) valós időben figyelik és optimalizálják.                                                           |   3   | D/V  |

---

## C2.9 Többmodális biztonsági érvényesítési folyamat

A fejlesztőknek biztonsági érvényesítést kell biztosítaniuk a szöveg, kép, hang és egyéb mesterséges intelligencia bemeneti módok esetében, konkrét fenyegetésészlelési típusokkal és erőforrás-elszigeteléssel.

|   #   | Description                                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Ellenőrizze, hogy minden bemeneti modalitás rendelkezik-e dedikált biztonsági érvényesítőkkel, dokumentált fenyegetési mintákkal (szöveg: prompt injekció, képek: steganográfia, hang: spektrogram támadások) és érzékelési küszöbértékekkel.                                                                       |   1   | D/V  |
| 2.9.2 | Ellenőrizze, hogy a többmodális bemenetek elkülönített homokozókban kerülnek feldolgozásra, amelyeknél meghatározott erőforrás-korlátok (memória, CPU, feldolgozási idő) vannak érvényben, melyek minden egyes modalitás típusra külön-külön vonatkoznak, és ezek dokumentálva vannak a biztonsági szabályzatokban. |   2   | D/V  |
| 2.9.3 | Ellenőrizze, hogy a kereszt-modalitású támadásészlelés felismeri-e a több bemeneti típust átfogó koordinált támadásokat (pl. szteganográfiai adatkódok képekben, melyeket szöveges promptinjekcióval kombinálnak) korrelációs szabályok és riasztásgenerálás segítségével.                                          |   2   | D/V  |
| 2.9.4 | Igazolja, hogy a többmodális érvényesítési hibák részletes naplózást váltanak ki, beleértve az összes bemeneti modalitást, az érvényesítési eredményeket, a fenyegetési pontszámokat és a korrelációs elemzést strukturált naplóformátumokkal a SIEM integrációhoz.                                                 |   3   | D/V  |
| 2.9.5 | Ellenőrizze, hogy a modalitás-specifikus tartalom-osztályozók a dokumentált ütemtervek szerint (legalább negyedévente) frissítve legyenek, az új fenyegetési mintákkal, támadó példákkal, és a teljesítménybenchmarkok a minimális küszöbértékek felett maradjanak.                                                 |   3   | D/V  |

---

## Hivatkozások

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

