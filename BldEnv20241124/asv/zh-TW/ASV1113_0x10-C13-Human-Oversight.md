# C13 人類監督、問責制與治理

## 控制目標

本章提供了關於在人工智慧系統中維持人類監督和清晰問責鏈的要求，確保在整個人工智慧生命週期中具備可解釋性、透明性和倫理管理。

---

## C13.1 緊急停止開關與覆蓋機制

當觀察到 AI 系統存在不安全行為時，提供關閉或回滾路徑。

|   #    | Description                    | Level | Role |
| :----: | ------------------------------ | :---: | :--: |
| 13.1.1 | 確認存在手動緊急停止機制，可立即中止 AI 模型推理和輸出。 |   1   | D/V  |
| 13.1.2 | 確認覆蓋控制僅限授權人員可訪問。               |   1   |  D   |
| 13.1.3 | 驗證回滾程序能夠恢復到先前的模型版本或安全模式操作。     |   3   | D/V  |
| 13.1.4 | 確認覆寫機制定期接受測試。                  |   3   |  V   |

---

## C13.2 人機互動決策檢查點

當風險超過預先定義的閾值時，需經人員審核批准。

|   #    | Description                           | Level | Role |
| :----: | ------------------------------------- | :---: | :--: |
| 13.2.1 | 確認高風險的人工智慧決策在執行前需經過明確的人類批准。           |   1   | D/V  |
| 13.2.2 | 確認風險門檻已明確定義，並能自動觸發人工審查工作流程。           |   1   |  D   |
| 13.2.3 | 確保在無法於所需時間內獲得人工審批時，時間敏感決策具備後備程序。      |   2   |  D   |
| 13.2.4 | 確認升級程序是否針對不同決策類型或風險類別（如適用）定義了明確的權限層級。 |   3   | D/V  |

---

## C13.3 責任鏈與可審計性

記錄操作員行為和模型決策。

|   #    | Description                           | Level | Role |
| :----: | ------------------------------------- | :---: | :--: |
| 13.3.1 | 確認所有 AI 系統的決策和人為介入都已記錄時間戳、使用者身份及決策理由。 |   1   | D/V  |
| 13.3.2 | 驗證審計日誌不可被篡改，並包含完整性驗證機制。               |   2   |  D   |

---

## C13.4 可解釋人工智慧技術

表面特徵重要性、反事實分析及局部解釋。

|   #    | Description                              | Level | Role |
| :----: | ---------------------------------------- | :---: | :--: |
| 13.4.1 | 驗證 AI 系統是否以人類可讀的格式提供其決策的基本說明。            |   1   | D/V  |
| 13.4.2 | 確認解釋品質透過人類評估研究和指標進行驗證。                   |   2   |  V   |
| 13.4.3 | 確認關鍵決策是否具備特徵重要性分數或歸因方法（如 SHAP、LIME 等）。   |   3   | D/V  |
| 13.4.4 | 驗證反事實解釋是否展示了如何修改輸入以改變結果，前提是此方法適用於該用例和領域。 |   3   |  V   |

---

## C13.5 模型卡與使用揭露

為預期用途、性能指標及倫理考量維護模型卡。

|   #    | Description                                 | Level | Role |
| :----: | ------------------------------------------- | :---: | :--: |
| 13.5.1 | 確認模型卡文件所載的預期使用案例、限制和已知失效模式。                 |   1   |  D   |
| 13.5.2 | 驗證是否公開了跨不同適用案例的性能指標。                        |   1   | D/V  |
| 13.5.3 | 確認道德考量、偏見評估、公平性評估、訓練數據特性及已知訓練數據限制均有記錄並定期更新。 |   2   |  D   |
| 13.5.4 | 確認模型卡在整個模型生命周期中受到版本控制和維護，並進行變更追蹤。           |   2   | D/V  |

---

## C13.6 不確定性量化

在回應中傳遞信心分數或熵度量。

|   #    | Description                  | Level | Role |
| :----: | ---------------------------- | :---: | :--: |
| 13.6.1 | 確認 AI 系統在其輸出中提供置信度分數或不確定性度量。 |   1   |  D   |
| 13.6.2 | 確認不確定性閾值會觸發額外的人為審查或替代決策路徑。   |   2   | D/V  |
| 13.6.3 | 驗證不確定性量化方法是否已校準並針對真實數據進行驗證。  |   2   |  V   |
| 13.6.4 | 驗證不確定性傳遞在多步驟人工智慧工作流程中得以維持。   |   3   | D/V  |

---

## C13.7 面向用戶的透明度報告

定期提供有關事件、偏移和數據使用的披露。

|   #    | Description                      | Level | Role |
| :----: | -------------------------------- | :---: | :--: |
| 13.7.1 | 確認數據使用政策和用戶同意管理實踐已清楚地傳達給相關利益相關者。 |   1   | D/V  |
| 13.7.2 | 確認已進行 AI 影響評估，並將結果納入報告中。         |   2   | D/V  |
| 13.7.3 | 確認定期發佈的透明度報告合理詳盡地披露了人工智慧事件和運營指標。 |   2   | D/V  |

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

