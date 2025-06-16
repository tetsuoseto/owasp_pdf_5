# C13 人類監督、問責與治理

## 控制目標

本章提供了在人工智慧系統中維持人類監督和清晰問責鏈的要求，確保在人工智慧生命週期中具備可解釋性、透明度及倫理管理。

---

## C13.1 緊急停止開關與覆寫機制

當觀察到 AI 系統的不安全行為時，提供關閉或回滾的途徑。

|   #    | Description                     | Level | Role |
| :----: | ------------------------------- | :---: | :--: |
| 13.1.1 | 確認存在手動停止開關機制，以立即中止人工智慧模型的推論和輸出。 |   1   | D/V  |
| 13.1.2 | 確認覆寫控制僅可由授權人員存取。                |   1   |  D   |
| 13.1.3 | 驗證回滾程序能否恢復到先前的模型版本或安全模式操作。      |   3   | D/V  |
| 13.1.4 | 確認覆寫機制定期接受測試。                   |   3   |  V   |

---

## C13.2 人機互動決策檢查點

當風險超過預定閾值時，需獲得人工批准。

|   #    | Description                           | Level | Role |
| :----: | ------------------------------------- | :---: | :--: |
| 13.2.1 | 確認高風險的人工智慧決策在執行前需經明確的人類批准。            |   1   | D/V  |
| 13.2.2 | 驗證風險閾值是否明確定義，並自動觸發人工審核流程。             |   1   |  D   |
| 13.2.3 | 確認在無法於所需時間內取得人類核准時，與時間敏感決策相關的備援程序已存在。 |   2   |  D   |
| 13.2.4 | 確保升級程序定義了針對不同決策類型或風險類別的明確授權層級（如適用）。   |   3   | D/V  |

---

## C13.3 責任鏈與可審計性

記錄操作員行為和模型決策。

|   #    | Description                          | Level | Role |
| :----: | ------------------------------------ | :---: | :--: |
| 13.3.1 | 確認所有人工智慧系統決策及人工干預均有記錄時間戳、使用者身份及決策理由。 |   1   | D/V  |
| 13.3.2 | 驗證審計日誌無法被篡改，並包含完整性驗證機制。              |   2   |  D   |

---

## C13.4 可解釋人工智慧技術

表面特徵重要性、反事實以及局部解釋。

|   #    | Description                               | Level | Role |
| :----: | ----------------------------------------- | :---: | :--: |
| 13.4.1 | 驗證人工智慧系統是否以人類可讀的格式提供其決策的基本解釋。             |   1   | D/V  |
| 13.4.2 | 確認說明品質已通過人工評估研究和指標加以驗證。                   |   2   |  V   |
| 13.4.3 | 驗證對於關鍵決策是否提供特徵重要性分數或歸因方法（如 SHAP、LIME 等）。  |   3   | D/V  |
| 13.4.4 | 驗證反事實解釋是否顯示了如何修改輸入以改變結果，前提是此方法適用於使用案例和領域。 |   3   |  V   |

---

## C13.5 模型卡與使用披露

維護模型卡以說明預期用途、性能指標及倫理考量。

|   #    | Description                                 | Level | Role |
| :----: | ------------------------------------------- | :---: | :--: |
| 13.5.1 | 確認模型說明卡是否記錄了預期使用情境、限制條件及已知的失效模式。            |   1   |  D   |
| 13.5.2 | 確認已揭露適用於不同使用案例的性能指標。                        |   1   | D/V  |
| 13.5.3 | 確認倫理考量、偏見評估、公平性評估、訓練資料特性及已知訓練資料限制均有紀錄並定期更新。 |   2   |  D   |
| 13.5.4 | 確保模型卡在整個模型生命週期中受到版本控制和持續維護，並具備變更追蹤功能。       |   2   | D/V  |

---

## C13.6 不確定性量化

在回應中傳播置信度分數或熵值測量。

|   #    | Description                     | Level | Role |
| :----: | ------------------------------- | :---: | :--: |
| 13.6.1 | 驗證 AI 系統是否提供其輸出結果的置信度分數或不確定性指標。 |   1   |  D   |
| 13.6.2 | 確認不確定性門檻會觸發額外的人為審查或替代決策途徑。      |   2   | D/V  |
| 13.6.3 | 驗證不確定性量化方法是否經過校準並且對照真實數據進行驗證。   |   2   |  V   |
| 13.6.4 | 驗證不確定性傳播是否在多步驟人工智慧工作流程中持續維持。    |   3   | D/V  |

---

## C13.7 面向用戶的透明度報告

定期提供關於事故、漂移和數據使用的揭露。

|   #    | Description                      | Level | Role |
| :----: | -------------------------------- | :---: | :--: |
| 13.7.1 | 確保數據使用政策和用戶同意管理實踐已清楚傳達給相關利益相關者。  |   1   | D/V  |
| 13.7.2 | 確認已進行人工智慧影響評估，並將結果納入報告中。         |   2   | D/V  |
| 13.7.3 | 確認定期發布的透明度報告合理詳細地披露了人工智慧事件和運營指標。 |   2   | D/V  |

### 參考文獻

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

