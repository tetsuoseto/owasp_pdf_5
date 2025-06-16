# C7 模型行為、輸出控制與安全保證

## 控制目標

模型輸出必須具備結構化、可靠、安全、可解釋，並在生產環境中持續監控。這樣做可以減少幻覺、隱私洩露、有害內容及失控行為，同時提升用戶信任和合規性。

---

## C7.1 輸出格式強制執行

嚴格的結構化模式、受限解碼，以及後續驗證可在錯誤或惡意內容傳播之前將其阻止。

|   #   | Description                                                      | Level | Role |
| :---: | ---------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | 驗證系統提示中是否提供了回應結構（例如，JSON Schema），並且每個輸出均自動進行驗證；不符合規範的輸出將觸發修復或拒絕。 |   1   | D/V  |
| 7.1.2 | 驗證已啟用受限解碼（停止詞、正則表達式、最大令牌數）以防止溢出或提示注入側信道。                         |   1   | D/V  |
| 7.1.3 | 確認下游組件將輸出視為不受信任，並根據結構化架構或注入安全的反序列化器進行驗證。                         |   2   | D/V  |
| 7.1.4 | 驗證不當輸出事件是否有被記錄、速率限制及呈現在監控系統中。                                    |   3   |  V   |

---

## C7.2 幻覺檢測與緩解

不確定性估計與備援策略可抑制捏造答案。

|   #   | Description                                    | Level | Role |
| :---: | ---------------------------------------------- | :---: | :--: |
| 7.2.1 | 驗證標記級對數機率、集成自我一致性或微調幻覺檢測器是否為每個答案分配信心分數。        |   1   | D/V  |
| 7.2.2 | 驗證低於可配置信心閾值的回應是否會觸發回退工作流程（例如檢索增強生成、次級模型或人工審核）。 |   1   | D/V  |
| 7.2.3 | 確認幻覺事件已標註根本原因元數據，並輸入至事後分析及微調流程中。               |   2   | D/V  |
| 7.2.4 | 確認在重大模型或知識庫更新後，閾值和偵測器已重新校準。                    |   3   | D/V  |
| 7.2.5 | 確認儀表板視覺化能追蹤幻覺率。                                |   3   |  V   |

---

## C7.3 輸出安全性與隱私過濾

政策過濾器和紅隊覆蓋範圍保護使用者及機密資料。

|   #   | Description                                          | Level | Role |
| :---: | ---------------------------------------------------- | :---: | :--: |
| 7.3.1 | 驗證生成前後的分類器是否阻擋符合政策的仇恨、騷擾、自我傷害、極端主義和性明確內容。            |   1   | D/V  |
| 7.3.2 | 確認在每個回應中執行個人識別資訊（PII）/支付卡產業（PCI）檢測及自動遮蔽；違規行為將引發隱私事件。 |   1   | D/V  |
| 7.3.3 | 驗證機密標籤（例如，商業機密）是否能跨模態傳遞，以防止在文字、圖像或程式碼中洩漏。            |   2   |  D   |
| 7.3.4 | 驗證過濾器繞過嘗試或高風險分類是否需要二次批准或用戶重新身份驗證。                    |   3   | D/V  |
| 7.3.5 | 確認篩選門檻符合法律管轄區與使用者年齡／角色的情境。                           |   3   | D/V  |

---

## C7.4 輸出與行動限制

速率限制和審核門檻可防止濫用和過度自主。

|   #   | Description                                          | Level | Role |
| :---: | ---------------------------------------------------- | :---: | :--: |
| 7.4.1 | 驗證每用戶和每 API 金鑰配額是否限制請求數、令牌數及成本，並在遇到 429 錯誤時實施指數退避機制。 |   1   |  D   |
| 7.4.2 | 驗證特權操作（文件寫入、程式碼執行、網路呼叫）是否需要基於政策的批准或有人介入審核。           |   1   | D/V  |
| 7.4.3 | 驗證跨模態一致性檢查確保為同一請求生成的圖像、程式碼和文字無法被用於隱匿惡意內容。            |   2   | D/V  |
| 7.4.4 | 確認代理委派深度、遞歸限制和允許的工具列表已明確配置。                          |   2   |  D   |
| 7.4.5 | 驗證限制違規是否會發出結構化安全事件以供 SIEM 採集。                        |   3   |  V   |

---

## C7.5 輸出可解釋性

透明信號提升用戶信任與內部除錯能力。

|   #   | Description                          | Level | Role |
| :---: | ------------------------------------ | :---: | :--: |
| 7.5.1 | 確認在風險評估認為適當時，向使用者展示信心分數或簡短的推理摘要。     |   2   | D/V  |
| 7.5.2 | 確認生成的解釋避免洩露敏感系統提示或專有資料。              |   2   | D/V  |
| 7.5.3 | 驗證系統是否捕捉了詞元層級的對數機率或注意力圖，並將其儲存以供授權檢查。 |   3   |  D   |
| 7.5.4 | 確認可解釋性產物與模型版本發布一同進行版本控制，以確保可審計性。     |   3   |  V   |

---

## C7.6 監控整合

即時可觀測性閉合了開發與生產之間的回路。

|   #   | Description                                        | Level | Role |
| :---: | -------------------------------------------------- | :---: | :--: |
| 7.6.1 | 驗證度量指標（架構違規、虛假資訊率、有害內容、個人識別資訊洩漏、延遲、成本）是否傳送至中央監控平台。 |   1   |  D   |
| 7.6.2 | 確認每個安全指標都定義了警示閾值，並設有待命升級路徑。                        |   1   |  V   |
| 7.6.3 | 驗證儀表板是否將輸出異常與模型/版本、功能標誌及上游數據變更相關聯。                 |   2   |  V   |
| 7.6.4 | 確認監控數據反饋回文件化的 MLOps 工作流程中，用於重新訓練、微調或規則更新。          |   2   | D/V  |
| 7.6.5 | 確認監控管線已進行滲透測試並實施存取控制，以避免敏感日誌洩漏。                    |   3   |  V   |

---

## 7.7 生成媒體防護措施

通過實施政策約束、輸出驗證和可追溯性，確保人工智慧系統不生成非法、有害或未經授權的媒體內容。

|   #   | Description                                              | Level | Role |
| :---: | -------------------------------------------------------- | :---: | :--: |
| 7.7.1 | 確認系統提示和用戶指示明確禁止生成非法、有害或未經同意的深偽媒體（例如圖片、視頻、音頻）。            |   1   | D/V  |
| 7.7.2 | 確認提示詞是否有過濾試圖生成冒充、性露骨的深度偽造或未經同意描繪真實個人的媒體。                 |   2   | D/V  |
| 7.7.3 | 確認系統是否使用感知哈希、浮水印檢測或指紋技術來防止未經授權的版權媒體複製。                   |   2   |  V   |
| 7.7.4 | 驗證所有生成的媒體是否經過密碼學簽名、加上浮水印，或嵌入防篡改的來源元數據，以確保下游的可追溯性。        |   3   | D/V  |
| 7.7.5 | 驗證繞過嘗試（例如，提示模糊化、俚語、對抗性措辭）是否被檢測、記錄並進行速率限制；重複濫用行為應反映至監控系統。 |   3   |  V   |

## 參考文獻

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

