# C8 記憶體、嵌入向量與向量資料庫安全性

## 控制目標

嵌入向量和向量存儲作為現代人工智慧系統的「即時記憶」，持續接受用戶提供的數據，並通過檢索增強生成（Retrieval-Augmented Generation，RAG）將其回饋到模型上下文中。如果未加以管控，這種記憶可能會洩露個人識別信息（PII）、違反同意，或被逆向利用來重建原始文本。本控制系列的目標是強化記憶管道和向量資料庫，確保存取遵循最小權限原則，嵌入向量具備隱私保護功能，存儲的向量能夠設定失效時間或按需求撤銷，且每個用戶的記憶永不污染其他用戶的提示或生成結果。

---

## C8.1 記憶體與 RAG 索引的存取控制

對每個向量集合執行細微的存取控制。

|   #   | Description                                              | Level | Role |
| :---: | -------------------------------------------------------- | :---: | :--: |
| 8.1.1 | 驗證每個租戶、集合或文件標籤的列/命名空間級別存取控制規則是否限制插入、刪除和查詢操作。             |   1   | D/V  |
| 8.1.2 | 驗證 API 金鑰或 JWT 是否帶有範圍限定的權利聲明（例如，集合 ID、操作動詞），並且至少每季度輪替一次。 |   1   | D/V  |
| 8.1.3 | 確認權限提升嘗試（例如，跨命名空間相似性查詢）能在 5 分鐘內被偵測並記錄到 SIEM。             |   2   | D/V  |
| 8.1.4 | 驗證向量資料庫是否記錄審核日誌的主體識別符、操作、向量 ID/命名空間、相似度閾值及結果數量。          |   2   | D/V  |
| 8.1.5 | 每當引擎升級或索引分片規則更改時，請驗證存取決策是否有被繞過漏洞的測試。                     |   3   |  V   |

---

## C8.2 嵌入清理與驗證

在向量化之前，預先篩檢文本中的個人識別信息（PII），並進行遮蔽或假名化處理，並可選地對嵌入向量進行後處理，以去除殘留訊號。

|   #   | Description                                              | Level | Role |
| :---: | -------------------------------------------------------- | :---: | :--: |
| 8.2.1 | 確認透過自動分類器檢測到個人識別資訊（PII）和受規範數據，並在嵌入前進行遮罩、標記化或刪除。          |   1   | D/V  |
| 8.2.2 | 確認嵌入流程拒絕或隔離包含可執行代碼或非 UTF-8 內容的輸入，這些內容可能會污染索引。            |   1   |  D   |
| 8.2.3 | 驗證對句子嵌入應用了局部或度量差分隱私淨化，當其與任何已知個人可識別資訊（PII）標記的距離低於可配置的閾值時。 |   2   | D/V  |
| 8.2.4 | 驗證去污效能（例如，個人識別資訊消除的召回率、語意漂移）至少每半年針對基準語料庫進行驗證。            |   2   |  V   |
| 8.2.5 | 驗證清理配置已被版本控制且變更經過同儕審查。                                   |   3   | D/V  |

---

## C8.3 記憶體到期、撤銷與刪除

GDPR「被遺忘權」及類似法規要求及時刪除；因此，向量庫必須支援TTL（存活時間）、硬刪除及墓碑標記，以確保被撤銷的向量無法被恢復或重新索引。

|   #   | Description                                  | Level | Role |
| :---: | -------------------------------------------- | :---: | :--: |
| 8.3.1 | 確認每個向量和元數據記錄都帶有 TTL 或被自動清理任務遵守的明確保留標籤。       |   1   | D/V  |
| 8.3.2 | 驗證使用者發起的刪除請求是否在 30 天內清除向量、元資料、快取副本及衍生索引。     |   1   | D/V  |
| 8.3.3 | 確認邏輯刪除後，若硬體支援，須接著進行儲存區塊的加密銷毀，或是透過金鑰保管庫的金鑰銷毀。 |   2   |  D   |
| 8.3.4 | 驗證過期向量在過期後少於 500 毫秒內會被排除在最近鄰搜尋結果之外。          |   3   | D/V  |

---

## C8.4 防止嵌入反演與洩漏

近期的防禦措施——噪音疊加、投影網絡、隱私神經元擾動以及應用層加密——能將詞元級逆向率降低至5%以下。

|   #   | Description                                                          | Level | Role |
| :---: | -------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | 確認存在涵蓋反演攻擊、成員查詢攻擊及屬性推測攻擊的正式威脅模型，並且每年進行審查。                            |   1   |  V   |
| 8.4.2 | 確認應用層加密或可搜索加密能防止基礎設施管理員或雲端人員直接讀取向量。                                  |   2   | D/V  |
| 8.4.3 | 驗證防禦參數（DP 的 ε、雜訊 σ、投影秩 k）是否在隱私保護 ≥ 99% 的標準下，並且效用損失 ≤ 3% 的準確度範圍內達成平衡。 |   3   |  V   |
| 8.4.4 | 確認反轉抵抗度指標是模型更新發佈門檻的一部分，並且已定義回歸預算。                                    |   3   | D/V  |

---

## C8.5 用戶特定記憶體的範圍執行

跨租戶洩漏仍然是 RAG 的主要風險：未正確過濾的相似性查詢可能會顯示其他客戶的私人文件。

|   #   | Description                                    | Level | Role |
| :---: | ---------------------------------------------- | :---: | :--: |
| 8.5.1 | 確認每個檢索查詢在傳遞給大型語言模型（LLM）提示之前，皆經過租戶/使用者 ID 的後篩選。 |   1   | D/V  |
| 8.5.2 | 確認集合名稱或命名空間 ID 是否根據用戶或租戶進行加鹽，以避免向量在不同作用域中發生衝突。 |   1   |  D   |
| 8.5.3 | 驗證超過可配置距離閾值但不在呼叫者範圍內的相似性結果被丟棄並觸發安全警報。          |   2   | D/V  |
| 8.5.4 | 驗證多租戶壓力測試模擬試圖檢索範圍外文件的對抗性查詢，並證明沒有資料洩漏。          |   2   |  V   |
| 8.5.5 | 驗證加密金鑰是否按租戶分隔，確保即使共享實體存儲，仍能實現加密隔離。             |   3   | D/V  |

---

## C8.6 先進記憶系統安全性

針對複雜記憶體架構（包括情節記憶、語意記憶和工作記憶）制定的安全控制，並包含具體的隔離和驗證需求。

|   #   | Description                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | 驗證不同記憶類型（情節記憶、語意記憶、工作記憶）是否擁有獨立的安全上下文，包含基於角色的存取控制、獨立的加密金鑰，以及每種類型記憶的存取模式文件化。 |   1   | D/V  |
| 8.6.2 | 驗證記憶整合過程包含安全驗證，以透過內容淨化、來源驗證及完整性檢查，防止惡意記憶注入於儲存之前。                           |   2   | D/V  |
| 8.6.3 | 驗證記憶檢索查詢已進行驗證和過濾，以防止通過查詢模式分析、存取控制執行和結果篩選提取未授權資訊。                           |   2   | D/V  |
| 8.6.4 | 驗證記憶體遺忘機制透過密鑰刪除、多次覆寫或具驗證證書的硬體安全刪除，以密碼擦除保證安全地刪除敏感資訊。                        |   3   | D/V  |
| 8.6.5 | 驗證記憶體系統完整性是否透過校驗和、稽核日誌及自動警報持續監控，以防止未經授權的修改或損壞，當記憶體內容在正常操作外發生變更時即發出警示。      |   3   | D/V  |

---

## 參考文獻

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

