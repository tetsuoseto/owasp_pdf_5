# C7 模型行為、輸出控制與安全保證

## 控制目標

模型輸出必須具備結構化、可靠、安全、可解釋性，並在生產環境中持續監控。這樣做可減少幻覺、隱私洩漏、有害內容及失控行為，同時提升用戶信任和法規遵循。

---

## C7.1 輸出格式強制執行

嚴格的結構定義、受限解碼及下游驗證能阻止錯誤格式或惡意內容在擴散前傳播。

|   #   | Description                                                      | Level | Role |
| :---: | ---------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | 確認在系統提示中提供了回應架構（例如，JSON Schema），並且每個輸出都會自動進行驗證；不符合規範的輸出會觸發修正或拒絕。 |   1   | D/V  |
| 7.1.2 | 確認已啟用受限解碼（停止標記、正則表達式、最大標記數）以防止溢出或提示注入側通道。                        |   1   | D/V  |
| 7.1.3 | 確認下游組件將輸出視為不可信，並根據架構或防注入安全的反序列化器進行驗證。                            |   2   | D/V  |
| 7.1.4 | 驗證不當輸出事件是否已被記錄、速率限制並呈現於監控系統中。                                    |   3   |  V   |

---

## C7.2 幻覺檢測與緩解

不確定性估計和備援策略可抑制虛構答案。

|   #   | Description                                     | Level | Role |
| :---: | ----------------------------------------------- | :---: | :--: |
| 7.2.1 | 驗證標記層級的對數機率、集合自我一致性，或微調的錯誤生成檢測器是否為每個答案指定信心分數。   |   1   | D/V  |
| 7.2.2 | 驗證低於可配置信心閾值的回應是否會觸發回退工作流程（例如，檢索增強生成、次要模型或人工審查）。 |   1   | D/V  |
| 7.2.3 | 確認幻覺事件已標記根本原因元資料，並輸入至事後檢討及微調流程。                 |   2   | D/V  |
| 7.2.4 | 在重大模型或知識庫更新後，請確認閾值和檢測器已重新校準。                    |   3   | D/V  |
| 7.2.5 | 驗證儀表板視覺化是否追蹤幻覺率。                                |   3   |  V   |

---

## C7.3 輸出安全與隱私過濾

政策過濾器和紅隊覆蓋保護用戶和機密資料。

|   #   | Description                               | Level | Role |
| :---: | ----------------------------------------- | :---: | :--: |
| 7.3.1 | 驗證生成前後的分類器是否能依據政策阻擋仇恨、騷擾、自我傷害、極端主義及性露骨內容。 |   1   | D/V  |
| 7.3.2 | 確認在每個回應中執行PII/PCI偵測和自動遮蔽；違規行為將引發隱私事件。     |   1   | D/V  |
| 7.3.3 | 驗證機密標籤（例如，商業機密）是否能跨模態傳播，以防止在文字、圖像或程式碼中洩漏。 |   2   |  D   |
| 7.3.4 | 確認過濾繞過嘗試或高風險分類需要次級批准或用戶重新身份驗證。            |   3   | D/V  |
| 7.3.5 | 驗證篩選門檻是否符合法律管轄區及使用者年齡/角色背景。               |   3   | D/V  |

---

## C7.4 輸出與行動限制

速率限制和批准閘門可防止濫用和過度自主。

|   #   | Description                                              | Level | Role |
| :---: | -------------------------------------------------------- | :---: | :--: |
| 7.4.1 | 驗證每位使用者及每個 API 金鑰的配額是否限制請求數、令牌數及費用，並在遇到 429 錯誤時採用指數回退機制。 |   1   |  D   |
| 7.4.2 | 驗證特權操作（檔案寫入、代碼執行、網路呼叫）是否需要基於政策的批准或人工介入。                  |   1   | D/V  |
| 7.4.3 | 驗證跨模態一致性檢查確保為同一請求生成的圖像、程式碼和文本無法被用於夾帶惡意內容。                |   2   | D/V  |
| 7.4.4 | 驗證代理委派深度、遞迴限制和允許的工具列表是否已明確配置。                            |   2   |  D   |
| 7.4.5 | 驗證限制違反是否發出結構化安全事件以供 SIEM 擷取。                             |   3   |  V   |

---

## C7.5 輸出可解釋性

透明信號提升用戶信任與內部除錯。

|   #   | Description                             | Level | Role |
| :---: | --------------------------------------- | :---: | :--: |
| 7.5.1 | 確保在風險評估認為適當時，向使用者展示面向使用者的信心水準分數或簡要推理總結。 |   2   | D/V  |
| 7.5.2 | 請確認生成的解釋避免暴露敏感的系統提示或專有資料。               |   2   | D/V  |
| 7.5.3 | 驗證系統是否擷取了標記層級的對數概率或注意力圖，並將其儲存以供授權檢查。    |   3   |  D   |
| 7.5.4 | 確認可解釋性產物與模型版本釋出一併進行版本控制，以確保可審計性。        |   3   |  V   |

---

## C7.6 監控整合

即時可觀測性縮短了開發與生產之間的迴路。

|   #   | Description                                   | Level | Role |
| :---: | --------------------------------------------- | :---: | :--: |
| 7.6.1 | 驗證指標（架構違規、幻覺率、有害性、個人識別資訊洩漏、延遲、成本）是否匯流至中央監控平台。 |   1   |  D   |
| 7.6.2 | 確認每個安全指標都有設定警報閾值，並且具備隨叫隨到的升級路徑。               |   1   |  V   |
| 7.6.3 | 驗證儀表板是否將輸出異常與模型/版本、功能標誌及上游數據變更相關聯。            |   2   |  V   |
| 7.6.4 | 確認監控數據反饋回授至已記錄的 MLOps 工作流程中的再訓練、微調或規則更新。      |   2   | D/V  |
| 7.6.5 | 確認監控管線已進行滲透測試並設有存取控制，以避免敏感日誌洩漏。               |   3   |  V   |

---

## 7.7 生成媒體保障措施

確保人工智慧系統不生成非法、有害或未經授權的媒體內容，透過執行政策限制、輸出驗證及可追溯性來達成。

|   #   | Description                                            | Level | Role |
| :---: | ------------------------------------------------------ | :---: | :--: |
| 7.7.1 | 請確認系統提示和用戶指令明確禁止生成非法、有害或未經同意的深度偽造媒體（例如，圖像、視頻、音頻）。      |   1   | D/V  |
| 7.7.2 | 驗證提示是否有過濾試圖生成冒充、性裸露深度合成影像，或未經同意展示真實個人的媒體。              |   2   | D/V  |
| 7.7.3 | 確認系統使用感知哈希、浮水印檢測或指紋識別來防止未經授權複製受版權保護的媒體。                |   2   |  V   |
| 7.7.4 | 驗證所有生成的媒體均經過加密簽署、加上浮水印，或嵌入防篡改的來源元數據，以確保後續可追溯性。         |   3   | D/V  |
| 7.7.5 | 驗證繞過嘗試（例如，提示混淆、俚語、對抗性措辭）是否被檢測、記錄並限制頻率；重複濫用情況會被呈現給監控系統。 |   3   |  V   |

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

