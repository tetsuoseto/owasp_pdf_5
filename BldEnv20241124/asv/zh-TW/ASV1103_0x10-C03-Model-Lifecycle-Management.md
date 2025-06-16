# C3 模型生命周期管理與變更控制

## 控制目標

人工智慧系統必須實施變更控制流程，以防止未經授權或不安全的模型修改進入生產環境。此控制確保模型在整個生命週期中保持完整性——從開發、部署到退役——從而促進快速事件響應並維持對所有變更的問責。

核心安全目標：僅授權且經驗證的模型通過受控流程進入生產階段，以維護完整性、可追蹤性及可復原性。

---

## C3.1 模型授權與完整性

只有經過驗證完整性的授權模型才能進入生產環境。

|   #   | Description                                                | Level | Role |
| :---: | ---------------------------------------------------------- | :---: | :--: |
| 3.1.1 | 在部署之前，請確認所有模型工件（權重、配置、分詞器）均由授權實體進行了密碼學簽名。                  |   1   | D/V  |
| 3.1.2 | 驗證模型完整性在部署時已被確認，且簽名驗證失敗會阻止模型加載。                            |   1   | D/V  |
| 3.1.3 | 驗證模型來源記錄是否包含授權實體的身份、訓練數據校驗和、驗證測試結果及通過/失敗狀態，以及創建時間戳。        |   2   | D/V  |
| 3.1.4 | 確認所有模型工件均使用語義版本控制（MAJOR.MINOR.PATCH），並且有文件說明每個版本組件遞增的具體標準。 |   2   | D/V  |
| 3.1.5 | 驗證依賴追蹤是否維持即時庫存，從而能夠快速識別所有使用系統。                             |   2   |  V   |

---

## C3.2 模型驗證與測試

模型在部署前必須通過既定的安全與安全性驗證。

|   #   | Description                                               | Level | Role |
| :---: | --------------------------------------------------------- | :---: | :--: |
| 3.2.1 | 確認模型在部署前經過自動化安全測試，該測試包括輸入驗證、輸出淨化及安全評估，並依預先約定的組織通過/失敗標準進行。 |   1   | D/V  |
| 3.2.2 | 確認當經過預先指定的授權人員明確覆核批准並有書面業務理由後，驗證失敗會自動阻止模型部署。              |   1   | D/V  |
| 3.2.3 | 驗證測試結果是否經加密簽名，並且不可變地鏈接到正在驗證的特定模型版本雜湊值。                    |   2   |  V   |
| 3.2.4 | 確認緊急部署需具備文件化的安全風險評估，並在事先約定的時間內取得預先指定的安全權限機關的批准。           |   2   | D/V  |

---

## C3.3 控制式部署與回滾

模型部署必須受到控制、監控，且能夠逆轉。

|   #   | Description                                                     | Level | Role |
| :---: | --------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | 確認生產部署實施漸進式推出機制（金絲雀部署、藍綠部署），並根據事先約定的錯誤率、延遲閾值或安全警報標準，設置自動回滾觸發條件。 |   1   |  D   |
| 3.3.2 | 確認回滾功能能在預定的組織時間窗口內原子性地還原完整的模型狀態（權重、配置、依賴關係）。                    |   1   | D/V  |
| 3.3.3 | 驗證部署流程在模型啟用前會確認密碼學簽章並計算完整性校驗和，且在任何不符情況下中止部署。                    |   2   | D/V  |
| 3.3.4 | 驗證緊急模型關閉功能能否透過自動斷路器或手動終止開關，在預定的響應時間內停用模型端點。                     |   2   | D/V  |
| 3.3.5 | 確認回滾工件（先前的模型版本、配置、依賴項）依照組織政策被保留，並使用不可變存儲以應對事件響應。                |   2   |  V   |

---

## C3.4 變更責任與審計

所有模型生命週期的變更必須可追蹤且可審核。

|   #   | Description                                                      | Level | Role |
| :---: | ---------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | 驗證所有模型變更（部署、配置、退役）均生成不可變的審計記錄，包含時間戳記、經身份驗證的執行者身份、變更類型，以及變更前後的狀態。 |   1   |  V   |
| 3.4.2 | 驗證審計日誌訪問是否需要適當的授權，且所有訪問嘗試均記錄用戶身份和時間戳。                            |   2   | D/V  |
| 3.4.3 | 確認提示範本和系統訊息在 git 倉庫中有版本控制，並且在部署前必須經過指定審核者的強制程式碼審查和批准。            |   2   | D/V  |
| 3.4.4 | 驗證審計記錄是否包含足夠的詳細資訊（模型雜湊值、配置快照、依賴版本），以便在保存期限內的任何時間點能完整重建模型狀態。      |   2   |  V   |

---

## C3.5 安全開發實踐

模型開發和訓練過程必須遵循安全規範，以防止被入侵。

|   #   | Description                                                | Level | Role |
| :---: | ---------------------------------------------------------- | :---: | :--: |
| 3.5.1 | 確認模型開發、測試和生產環境在物理或邏輯上是分離的。它們沒有共享的基礎架構，擁有不同的存取控制，且數據存儲是隔離的。 |   1   |  D   |
| 3.5.2 | 驗證模型訓練和微調是否在具有受控網路存取的隔離環境中進行。                              |   1   |  D   |
| 3.5.3 | 確認訓練數據來源在用於模型開發之前，透過完整性檢查進行驗證，並通過受信任來源進行身份認證，並具備有文件記錄的監管鏈。 |   1   | D/V  |
| 3.5.4 | 確認模型開發的產物（超參數、訓練腳本、配置文件）被存儲在版本控制中，並且在用於訓練前需要同行審核批准。        |   2   |  D   |

---

## C3.6 模型退役與除役

模型在不再需要或發現安全問題時，必須安全地退役。

|   #   | Description                                           | Level | Role |
| :---: | ----------------------------------------------------- | :---: | :--: |
| 3.6.1 | 驗證模型退役流程是否會自動掃描依賴圖，識別所有使用系統，並在退役前提供事先協商的通知期。          |   1   |  D   |
| 3.6.2 | 根據已記錄的資料保存政策，驗證已退役模型的檔案是否透過加密抹除或多重覆寫安全刪除，並附有已驗證的銷毀證明。 |   1   | D/V  |
| 3.6.3 | 驗證模型退役事件是否已記錄時間戳和執行者身分，並且模型簽名是否已被撤銷以防止重複使用。           |   2   |  V   |
| 3.6.4 | 驗證緊急模型退役能否在預先設定的緊急響應時間範圍內，透過自動終止開關禁用模型存取，當發現重大安全漏洞時。  |   2   | D/V  |

---

## 參考文獻

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

