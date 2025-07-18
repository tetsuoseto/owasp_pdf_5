# 11 隱私保護與個人資料管理

## 控制目標

在整個人工智慧生命周期——資料收集、訓練、推論和事件響應中，維持嚴格的隱私保障，確保個人資料僅在明確同意、最小必要範圍、可證明的刪除以及正式隱私保證下進行處理。

---

## 11.1 匿名化與數據最小化

|   #    | Description                              | Level | Role |
| :----: | ---------------------------------------- | :---: | :--: |
| 11.1.1 | 確認已移除或哈希化直接識別符和準識別符。                     |   1   | D/V  |
| 11.1.2 | 驗證自動化審計是否測量 k-匿名性/l-多樣性，並在指標低於政策閾值時發出警報。 |   2   | D/V  |
| 11.1.3 | 驗證模型特徵重要性報告證明識別碼洩漏互信息不超過 ε = 0.01。       |   2   |  V   |
| 11.1.4 | 驗證正式證明或合成數據認證即使在鏈接攻擊下，重新識別風險 ≤ 0.05。     |   3   |  V   |

---

## 11.2 被遺忘權與刪除執行

|   #    | Description                                     | Level | Role |
| :----: | ----------------------------------------------- | :---: | :--: |
| 11.2.1 | 驗證資料主體刪除請求能在少於30天的服務水準協議內傳播至原始資料集、檢查點、嵌入、日誌及備份。 |   1   | D/V  |
| 11.2.2 | 驗證「機器遺忘」程序是否透過經認證的遺忘演算法，實際重新訓練或近似移除資料。          |   2   |  D   |
| 11.2.3 | 驗證影子模型評估證明遺忘後，遺忘記錄對輸出影響少於1%。                    |   2   |  V   |
| 11.2.4 | 驗證刪除事件是否已不可變地記錄並可供監管機構審計。                       |   3   |  V   |

---

## 11.3 差分隱私保障措施

|   #    | Description                     | Level | Role |
| :----: | ------------------------------- | :---: | :--: |
| 11.3.1 | 驗證隱私損失會計儀表板是否在累積 ε 超過政策閾值時發出警報。 |   2   | D/V  |
| 11.3.2 | 驗證黑箱隱私審計是否在宣稱值的10%範圍內準確估計 ε̂。   |   2   |  V   |
| 11.3.3 | 驗證形式證明涵蓋所有後訓練微調和嵌入。             |   3   |  V   |

---

## 11.4 目的限制與範圍擴張保護

|   #    | Description                                      | Level | Role |
| :----: | ------------------------------------------------ | :---: | :--: |
| 11.4.1 | 確認每個資料集和模型檢查點都帶有與原始同意書一致的機器可讀用途標籤。               |   1   |  D   |
| 11.4.2 | 驗證執行時監控器是否能偵測與宣告目的不符的查詢並觸發軟拒絕。                   |   1   | D/V  |
| 11.4.3 | 驗證政策即代碼閘門是否阻止在未經資料保護影響評估（DPIA）審查的情況下將模型重新部署到新領域。 |   3   |  D   |
| 11.4.4 | 驗證正式的可追溯性證明顯示每個個人資料的生命週期均在已同意的範圍內。               |   3   |  V   |

---

## 11.5 同意管理與合法依據追蹤

|   #    | Description                           | Level | Role |
| :----: | ------------------------------------- | :---: | :--: |
| 11.5.1 | 確認同意管理平台（CMP）是否記錄每個資料主體的同意狀態、目的及保留期限。 |   1   | D/V  |
| 11.5.2 | 驗證 API 是否公開同意權杖；模型必須在推理前驗證權杖範圍。       |   2   |  D   |
| 11.5.3 | 確認被拒絕或撤回的同意會在 24 小時內停止處理流程。           |   2   | D/V  |

---

## 11.6 帶有隱私控制的聯邦學習

|   #    | Description                         | Level | Role |
| :----: | ----------------------------------- | :---: | :--: |
| 11.6.1 | 驗證客戶端更新在聚合之前是否採用局部差分隱私噪聲添加。         |   1   |  D   |
| 11.6.2 | 驗證訓練指標具有差分隱私性，且絕不洩露單一用戶的損失值。        |   2   | D/V  |
| 11.6.3 | 確認已啟用抗中毒聚合方法（例如 Krum/Trimmed-Mean）。 |   2   |  V   |
| 11.6.4 | 驗證形式證明展示整體 ε 預算，且效用損失低於 5。          |   3   |  V   |

---

### 參考文獻

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)

