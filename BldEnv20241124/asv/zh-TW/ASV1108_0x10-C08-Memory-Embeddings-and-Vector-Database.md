# C8 記憶體、嵌入向量與向量資料庫安全性

## 控制目標

嵌入向量與向量存儲充當當代人工智慧系統的「即時記憶」，持續接受使用者提供的資料，並透過檢索增強生成（Retrieval-Augmented Generation，RAG）技術將其重新呈現在模型上下文中。若不加以管理，此記憶可能洩漏個人識別資訊（PII）、違反同意規定，或被逆向工程以重建原始文本。此控制類別的目標是強化記憶管線及向量資料庫，確保存取權限遵循最小權限原則，嵌入向量具備隱私保護特性，儲存的向量能設定過期或隨時撤銷，且每位使用者的記憶不會污染其他使用者的提示或生成結果。

---

## C8.1 記憶體與 RAG 指標的存取控制

對每個向量集合執行細粒度存取控制。

|   #   | Description                                            | Level | Role |
| :---: | ------------------------------------------------------ | :---: | :--: |
| 8.1.1 | 驗證行/命名空間層級的存取控制規則是否限制每個租戶、集合或文件標籤的插入、刪除及查詢操作。          |   1   | D/V  |
| 8.1.2 | 驗證 API 金鑰或 JWT 是否攜帶範圍限定的聲明（例如，集合 ID、操作動詞），並且至少每季度輪換一次。 |   1   | D/V  |
| 8.1.3 | 確認特權提升嘗試（例如跨命名空間的相似性查詢）能在五分鐘內被檢測並記錄到 SIEM 中。           |   2   | D/V  |
| 8.1.4 | 驗證向量資料庫是否記錄審計日誌，包含主體識別碼、操作、向量 ID/命名空間、相似度閾值和結果數量。      |   2   | D/V  |
| 8.1.5 | 驗證在引擎升級或索引分片規則更改時，存取決策是否有繞過漏洞的測試。                      |   3   |  V   |

---

## C8.2 嵌入式消毒與驗證

在向量化之前，先對文本進行個人識別信息（PII）預篩選，並進行遮蔽或假名化，然後可選擇對嵌入向量進行後處理以去除殘留的信號。

|   #   | Description                                          | Level | Role |
| :---: | ---------------------------------------------------- | :---: | :--: |
| 8.2.1 | 確認個人識別資訊（PII）和受規範數據是否透過自動分類器被偵測，並在嵌入前進行遮蔽、標記化或刪除。    |   1   | D/V  |
| 8.2.2 | 驗證嵌入管線是否拒絕或隔離包含可執行代碼或非UTF-8資料的輸入，防止中毒索引。             |   1   |  D   |
| 8.2.3 | 驗證是否對與任何已知個人身份資訊（PII）標記距離低於可配置閾值的句子嵌入應用了本地或度量差分隱私消毒。 |   2   | D/V  |
| 8.2.4 | 確認至少每半年針對基準語料庫驗證去污效能（例如，個人識別資訊刪除的召回率、語義漂移）。          |   2   |  V   |
| 8.2.5 | 確認清理配置已受版本控制且變更通過同儕審查。                               |   3   | D/V  |

---

## C8.3 記憶體過期、撤銷與刪除

GDPR「被遺忘權」及類似法律要求及時刪除資料；因此，向量存儲必須支持存活時間（TTL）、硬刪除及墓碑標記，以確保被撤銷的向量無法被恢復或重新編入索引。

|   #   | Description                                      | Level | Role |
| :---: | ------------------------------------------------ | :---: | :--: |
| 8.3.1 | 確認每個向量和元數據記錄都帶有 TTL 或明確的保留標籤，並且被自動清理作業所遵守。       |   1   | D/V  |
| 8.3.2 | 驗證用戶發起的刪除請求是否在30天內清除向量、元數據、快取副本及衍生索引。            |   1   | D/V  |
| 8.3.3 | 驗證邏輯刪除後，若硬體支援，應接著進行儲存區塊的密碼學銷毀，或透過金鑰保管庫中的金鑰銷毀來完成。 |   2   |  D   |
| 8.3.4 | 驗證過期向量在過期後 500 毫秒內不包含在最近鄰搜尋結果中。                  |   3   | D/V  |

---

## C8.4 防止嵌入逆向與洩漏

近期的防禦方法——噪音疊加、投影網絡、隱私神經元擾動和應用層加密——能將標記級反演率降低到5%以下。

|   #   | Description                                                        | Level | Role |
| :---: | ------------------------------------------------------------------ | :---: | :--: |
| 8.4.1 | 確認存在涵蓋反演攻擊、成員資格攻擊和屬性推斷攻擊的正式威脅模型，並且每年進行審查。                          |   1   |  V   |
| 8.4.2 | 驗證應用層加密或可搜尋加密是否能保護向量，避免基礎設施管理員或雲端人員直接讀取。                           |   2   | D/V  |
| 8.4.3 | 驗證防禦參數（DP 的 ε、噪音 σ、投影秩 k）是否在隱私保護達到 ≥ 99% 代幣保護與效用損失 ≤ 3% 準確率之間取得平衡。 |   3   |  V   |
| 8.4.4 | 確認反轉韌性指標是模型更新發布門檻的一部分，並定義了回歸預算。                                    |   3   | D/V  |

---

## C8.5 用戶專用記憶體的範圍強制執行

跨租戶資料洩漏仍然是RAG的主要風險：未正確過濾的相似度查詢可能會揭露其他客戶的私人文件。

|   #   | Description                                     | Level | Role |
| :---: | ----------------------------------------------- | :---: | :--: |
| 8.5.1 | 驗證每個檢索查詢在傳遞至大型語言模型（LLM）提示之前，是否已通過租戶/用戶ID進行後篩選。  |   1   | D/V  |
| 8.5.2 | 驗證集合名稱或命名空間 ID 是否根據用戶或租戶進行加鹽，以確保向量在不同範圍內不會發生衝突。 |   1   |  D   |
| 8.5.3 | 驗證相似度結果是否高於可配置距離閾值但位於呼叫者範圍之外，且會被丟棄並觸發安全警報。      |   2   | D/V  |
| 8.5.4 | 驗證多租戶壓力測試是否模擬試圖檢索範圍外文件的對抗性查詢，並證明無任何訊息外洩。        |   2   |  V   |
| 8.5.5 | 驗證加密金鑰是否依租戶分隔，確保即使物理存儲共用，也能達到密碼學隔離。             |   3   | D/V  |

---

## C8.6 高階記憶系統安全性

包括情節記憶、語義記憶和工作記憶在內的複雜記憶架構的安全控制，具有特定的隔離和驗證要求。

|   #   | Description                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------ | :---: | :--: |
| 8.6.1 | 驗證不同記憶類型（情節記憶、語意記憶、工作記憶）是否具備隔離的安全環境，包括基於角色的存取控制、獨立的加密金鑰，以及記錄每種記憶類型的存取模式。 |   1   | D/V  |
| 8.6.2 | 確認記憶整合過程包含安全驗證，以防止透過內容清理、來源驗證和完整性檢查在儲存前注入惡意記憶。                           |   2   | D/V  |
| 8.6.3 | 驗證記憶檢索查詢是否經過驗證和清理，以防止透過查詢模式分析、訪問控制執行和結果過濾來提取未授權的資訊。                      |   2   | D/V  |
| 8.6.4 | 驗證記憶體遺忘機制是否透過密鑰刪除、多次覆寫或具驗證證書的硬體安全刪除，具備密碼學消除保證，從而安全刪除敏感資訊。                |   3   | D/V  |
| 8.6.5 | 驗證記憶體系統完整性是否透過校驗和、審計日誌以及當記憶體內容在非正常操作下變更時自動警報，持續監控未經授權的修改或損壞。             |   3   | D/V  |

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

