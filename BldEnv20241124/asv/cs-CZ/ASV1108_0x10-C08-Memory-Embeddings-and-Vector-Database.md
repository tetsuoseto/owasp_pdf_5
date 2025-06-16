# Bezpečnost paměti C8, embeddingů a vektorové databáze

## Řídicí cíl

Vložení a vektorové úložiště fungují jako „živá paměť“ současných AI systémů, která neustále přijímá data poskytnutá uživateli a zpětně je zobrazuje v kontextu modelů prostřednictvím generování s doplněním znalostí (Retrieval-Augmented Generation, RAG). Pokud nejsou tyto paměťové kanály správně řízeny, může dojít k úniku osobně identifikovatelných informací (PII), porušení souhlasu nebo k reverzní rekonstrukci původního textu. Cílem této skupiny kontrol je zabezpečit paměťové procesy a vektorové databáze tak, aby přístup byl omezen na nezbytné minimum, vložení bylo navrženo s ohledem na ochranu soukromí, uložené vektory měly časovou platnost nebo bylo možné je na požádání zneplatnit, a aby paměť jednotlivých uživatelů nikdy neovlivňovala vstupy nebo výstupy jiných uživatelů.

---

## C8.1 Řízení přístupu k paměti a indexům RAG

Prosazujte detailní řízení přístupu u každé kolekce vektorů.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Ověřte, že pravidla řízení přístupu na úrovni řádků/jmenných prostorů omezují operace vkládání, mazání a dotazování podle nájemce, kolekce nebo štítku dokumentu. |   1   | D/V  |
| 8.1.2 | Ověřte, že API klíče nebo JWT obsahují omezené nároky (např. ID kolekcí, akční slovesa) a jsou rotovány alespoň čtvrtletně.                                       |   1   | D/V  |
| 8.1.3 | Ověřte, že pokusy o eskalaci oprávnění (např. dotazy na podobnost mezi jmennými prostory) jsou detekovány a zaznamenávány do SIEM do 5 minut.                     |   2   | D/V  |
| 8.1.4 | Ověřte, že vektorová databáze zaznamenává do protokolu identifikátor subjektu, operaci, ID vektoru/prostor jmen, prahovou podobnost a počet výsledků.             |   2   | D/V  |
| 8.1.5 | Ověřte, že jsou rozhodnutí o přístupu testována na chyby obcházení vždy, když jsou aktualizovány motory nebo se mění pravidla dělení indexu.                      |   3   |  V   |

---

## C8.2 Sanitizace a validace vkládání

Předzpracujte text pro osobní identifikovatelné informace (PII), odstraňte je nebo pseudonymizujte před vektorizací a případně po zpracování vektoru odstraňte zbytkové signály.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Ověřte, že PII a regulovaná data jsou detekována pomocí automatizovaných klasifikátorů a před vložením jsou maskována, tokenizována nebo odstraněna.                                                                                                       |   1   | D/V  |
| 8.2.2 | Ověřte, že pipeline vložení odmítají nebo izolují vstupy obsahující spustitelný kód nebo artefakty nevyhovující UTF-8, které by mohly otrávit index.                                                                                                       |   1   |  D   |
| 8.2.3 | Ověřte, že na vektorové reprezentace vět je aplikována lokální nebo metrická diferenciálně privátní sanitizace, pokud je jejich vzdálenost k jakémukoli známému tokenu obsahujícímu osobní identifikovatelné informace (PII) pod konfigurovatelným prahem. |   2   | D/V  |
| 8.2.4 | Ověřte, že účinnost sanitizace (např. zpětné vyhledávání odstranění osobních údajů, sémantický posun) je validována alespoň pololetně vůči referenčním korpusům.                                                                                           |   2   |  V   |
| 8.2.5 | Ověřte, že konfigurační soubory pro sanitizaci jsou verzovány a změny procházejí kontrolou kolegy.                                                                                                                                                         |   3   | D/V  |

---

## C8.3 Vypršení platnosti paměti, odvolání a vymazání

Nařízení GDPR o „právu být zapomenut“ a podobné zákony vyžadují včasné vymazání; vektorové úložiště proto musí podporovat TTL (čas do vypršení platnosti), tvrdé mazání a tomb-stoning, aby nemohlo dojít k obnovení nebo opětovnému indexování zrušených vektorů.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Ověřte, že každý vektor a záznam metadat obsahuje TTL nebo explicitní štítek uchování, který je respektován automatizovanými úklidovými úlohami.        |   1   | D/V  |
| 8.3.2 | Ověřte, že uživatelem iniciované požadavky na smazání odstraní vektory, metadata, kopie mezipaměti a odvozené indexy do 30 dnů.                         |   1   | D/V  |
| 8.3.3 | Ověřte, že logické mazání je následováno kryptografickým destrukcí bloků úložiště, pokud to hardware podporuje, nebo zničením klíče v klíčovém trezoru. |   2   |  D   |
| 8.3.4 | Ověřte, že vypršené vektory jsou vyloučeny z výsledků hledání nejbližších sousedů do 500 ms po vypršení.                                                |   3   | D/V  |

---

## C8.4 Prevence inverze a úniku embeddingů

Nedávné obranné metody — překrytí šumu, projekční sítě, perturbace neuronů na úrovni soukromí a šifrování na aplikační vrstvě — mohou snížit míru inverze na úrovni tokenů pod 5 %.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Ověřte, že existuje formální model hrozeb zahrnující útoky na inverzi, členství a odvození atributů, který je přezkoumáván každý rok.                                             |   1   |  V   |
| 8.4.2 | Ověřte, že šifrování na aplikační vrstvě nebo vyhledávací šifrování chrání vektory před přímým čtením ze strany administrátorů infrastruktury nebo zaměstnanců cloudových služeb. |   2   | D/V  |
| 8.4.3 | Ověřte, že obranné parametry (ε pro DP, šum σ, hodnost projekce k) vyvažují ochranu soukromí ≥ 99 % tokenů a užitečnost ≤ 3 % ztráty přesnosti.                                   |   3   |  V   |
| 8.4.4 | Ověřte, že metriky odolnosti vůči inverzi jsou součástí kontrolních bodů pro vydání aktualizací modelu, přičemž jsou definovány rozpočty pro regrese.                             |   3   | D/V  |

---

## C8.5 Vynucování rozsahu pro uživatelsky specifickou paměť

Únik dat mezi nájemníky zůstává hlavním rizikem RAG: nesprávně filtrované dotazy na podobnost mohou odhalit soukromé dokumenty jiného zákazníka.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.5.1 | Ověřte, že každý dotaz na vyhledávání je filtrován podle ID nájemce/uživatele před jeho předáním do výzvy LLM.                                                           |   1   | D/V  |
| 8.5.2 | Ověřte, že názvy kolekcí nebo identifikátory s jmenným prostorem jsou solené pro každého uživatele nebo nájemce, aby se vektory nemohly překrývat mezi různými oblastmi. |   1   |  D   |
| 8.5.3 | Ověřte, že výsledky podobnosti nad konfigurovatelným práhem vzdálenosti, ale mimo dosah volajícího, jsou zahazovány a vyvolávají bezpečnostní upozornění.                |   2   | D/V  |
| 8.5.4 | Ověřte, že testy zátěže pro více nájemců simulují protivné dotazy, které se pokoušejí získat dokumenty mimo rozsah, a prokažte nulový únik dat.                          |   2   |  V   |
| 8.5.5 | Ověřte, že šifrovací klíče jsou odděleny pro každého nájemce, což zajišťuje kryptografickou izolaci i v případě sdíleného fyzického úložiště.                            |   3   | D/V  |

---

## C8.6 Pokročilá bezpečnost paměťových systémů

Bezpečnostní kontroly pro sofistikované paměťové architektury, včetně epizodické, sémantické a pracovní paměti, s konkrétními požadavky na izolaci a validaci.

|   #   | Description                                                                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Ověřte, že různé typy paměti (epizodická, sémantická, pracovní) mají izolované bezpečnostní kontexty s řízením přístupu založeným na rolích, oddělenými šifrovacími klíči a zdokumentovanými vzory přístupu pro každý typ paměti.                 |   1   | D/V  |
| 8.6.2 | Ověřte, že procesy konsolidace paměti zahrnují bezpečnostní validaci k zabránění vkládání škodlivých vzpomínek prostřednictvím čištění obsahu, ověřování zdroje a kontrol integrity před uložením.                                                |   2   | D/V  |
| 8.6.3 | Ověřte, že dotazy pro získávání paměti jsou validovány a sanitovány, aby se zabránilo získávání nepovolených informací prostřednictvím analýzy vzoru dotazů, vynucování přístupové kontroly a filtrování výsledků.                                |   2   | D/V  |
| 8.6.4 | Ověřte, že mechanismy zapomínání v paměti bezpečně vymazávají citlivé informace s kryptografickými zárukami vymazání pomocí odstranění klíčů, vícenásobného přepisování nebo hardwarově založeného bezpečného vymazání s ověřovacími certifikáty. |   3   | D/V  |
| 8.6.5 | Ověřte, že integrita paměťového systému je neustále sledována kvůli neoprávněným úpravám nebo poškození pomocí kontrolních součtů, auditních protokolů a automatizovaných upozornění při změnách obsahu paměti mimo běžný provoz.                 |   3   | D/V  |

---

## Reference

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

