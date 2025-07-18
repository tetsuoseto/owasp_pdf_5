# C3 模型生命週期管理與變更控制

## 控制目標

AI 系統必須實施變更控制流程，以防止未經授權或不安全的模型修改進入生產環境。此控制措施確保模型在整個生命週期中（從開發、部署到退役）的完整性，從而促進迅速的事件響應並維持對所有變更的問責。

核心安全目標：僅允許經授權且經驗證的模型通過受控流程進入生產，該流程維持完整性、可追溯性和可恢復性。

---

## C3.1 模型授權與完整性

只有經過驗證完整性的授權模型才能進入生產環境。

|   #   | Description                                                 | Level | Role |
| :---: | ----------------------------------------------------------- | :---: | :--: |
| 3.1.1 | 在部署之前，請確認所有模型工件（權重、配置、分詞器）均由授權實體進行了密碼學簽署。                   |   1   | D/V  |
| 3.1.2 | 確認模型完整性在部署時得到驗證，且簽名驗證失敗會阻止模型載入。                             |   1   | D/V  |
| 3.1.3 | 驗證模型來源記錄是否包含授權實體的身份、訓練數據校驗和、驗證測試結果（含通過/失敗狀態）以及創建時間戳。        |   2   | D/V  |
| 3.1.4 | 驗證所有模型產物是否使用語義版本控制（MAJOR.MINOR.PATCH），並附有具體的標準說明何時遞增每個版本元件。 |   2   | D/V  |
| 3.1.5 | 驗證依賴追蹤是否維持即時清單，使得能快速識別所有使用該依賴的系統。                           |   2   |  V   |

---

## C3.2 模型驗證與測試

模型必須通過定義的安全性和安全驗證才能部署。

|   #   | Description                                                  | Level | Role |
| :---: | ------------------------------------------------------------ | :---: | :--: |
| 3.2.1 | 確認模型在部署前經過自動化安全測試，該測試包括輸入驗證、輸出清理，以及以事先約定的組織通過/失敗門檻為基準的安全性評估。 |   1   | D/V  |
| 3.2.2 | 驗證驗證失敗是否在經預先指定的授權人員明確覆寫批准並附有書面業務理由後，自動阻止模型部署。                |   1   | D/V  |
| 3.2.3 | 驗證測試結果是否以密碼學方式簽名，並不可變地連結至被驗證的特定模型版本雜湊。                       |   2   |  V   |
| 3.2.4 | 確認緊急部署需有書面安全風險評估，並於事先約定的時間內獲得預先指定的安全主管批准。                    |   2   | D/V  |

---

## C3.3 控制部署與回滾

模型部署必須受控、受監視且可逆。

|   #   | Description                                                   | Level | Role |
| :---: | ------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | 確認生產部署實施漸進式發布機制（灰度部署、藍綠部署），並根據事先約定的錯誤率、延遲閾值或安全警報標準設置自動回滾觸發條件。 |   1   |  D   |
| 3.3.2 | 驗證回滾功能是否能於預先定義的組織時間窗口內，原子地還原完整模型狀態（包括權重、配置、依賴關係）。             |   1   | D/V  |
| 3.3.3 | 確認部署流程在模型啟用前驗證密碼學簽章並計算完整性檢查碼，若有任何不符則終止部署。                     |   2   | D/V  |
| 3.3.4 | 驗證緊急模型關閉功能能夠透過自動斷路器或手動終止開關，在預先設定的響應時間內停用模型端點。                 |   2   | D/V  |
| 3.3.5 | 驗證回滾產物（先前的模型版本、配置、依賴項）是否依照組織政策並透過不可變儲存加以保留，以利事故響應。            |   2   |  V   |

---

## C3.4 變更責任與稽核

所有模型生命週期變更必須可追溯並可審核。

|   #   | Description                                                        | Level | Role |
| :---: | ------------------------------------------------------------------ | :---: | :--: |
| 3.4.1 | 驗證所有模型變更（部署、配置、退役）是否產生不可變更的稽核紀錄，該紀錄包含時間戳記、已驗證的執行者身份、變更類型，以及變更前後狀態。 |   1   |  V   |
| 3.4.2 | 驗證稽核日誌存取是否需經適當授權，且所有存取嘗試均記錄使用者身份與時間戳。                              |   2   | D/V  |
| 3.4.3 | 確認提示模板和系統訊息在 git 倉庫中進行版本控制，並且在部署前必須由指定的審查者進行代碼審查和批准。               |   2   | D/V  |
| 3.4.4 | 驗證審計記錄是否包含足夠的細節（模型雜湊、配置快照、依賴版本），以便能夠在保留期限內的任何時間點完整重建模型狀態。          |   2   |  V   |

---

## C3.5 安全開發實踐

模型開發和訓練過程必須遵循安全實踐以防止被攻破。

|   #   | Description                                                    | Level | Role |
| :---: | -------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | 驗證模型開發、測試和生產環境在物理上或邏輯上是相互隔離的。它們沒有共用的基礎設施，擁有不同的存取控制，並且數據儲存相互隔離。 |   1   |  D   |
| 3.5.2 | 確保模型訓練和微調在具有受控網路存取的隔離環境中進行。                                    |   1   |  D   |
| 3.5.3 | 確認訓練數據來源在用於模型開發之前，已通過完整性檢查驗證並經由具備文件化監管鏈的可信來源進行身份驗證。            |   1   | D/V  |
| 3.5.4 | 確認模型開發的產物（超參數、訓練腳本、配置文件）已儲存在版本控制中，且在用於訓練前需經同行審核批准。             |   2   |  D   |

---

## C3.6 模型退役與除役

當模型不再需要或發現安全問題時，必須安全地退役。

|   #   | Description                                                   | Level | Role |
| :---: | ------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | 確認模型退役流程會自動掃描依賴圖，識別所有使用系統，並在退役前提供事先約定的通知期限。                   |   1   |  D   |
| 3.6.2 | 根據已記錄的資料保留政策，驗證已退役的模型工件是否經過加密抹除或多遍覆寫安全清除，並確保有經過驗證的銷毀證明。       |   1   | D/V  |
| 3.6.3 | 確認模型退役事件已記錄時間戳和執行者身份，並且模型簽名已被撤銷以防止重複使用。                       |   2   |  V   |
| 3.6.4 | 驗證緊急模型退役功能是否能夠在預先設定的緊急應變時間範圍內，透過自動終止開關，禁用模型存取權限，以應對發現的關鍵安全漏洞。 |   2   | D/V  |

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

