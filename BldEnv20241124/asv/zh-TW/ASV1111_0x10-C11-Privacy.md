# 11 隱私保護與個人資料管理

## 控制目標

在整個人工智慧生命週期——資料收集、訓練、推論及事件回應過程中嚴格維護隱私保障，確保個人資料僅在明確同意、必要範圍最小化、可證明消除及正式隱私保證下進行處理。

---

## 11.1 匿名化與資料最小化

|   #    | Description                              | Level | Role |
| :----: | ---------------------------------------- | :---: | :--: |
| 11.1.1 | 驗證直接識別碼和準識別碼已被移除或進行雜湊處理。                 |   1   | D/V  |
| 11.1.2 | 驗證自動化稽核是否衡量 k-匿名性/l-多樣性，並在指標低於政策閾值時發出警報。 |   2   | D/V  |
| 11.1.3 | 驗證模型特徵重要性報告證明沒有超過 ε = 0.01 的識別碼洩漏互信息。    |   2   |  V   |
| 11.1.4 | 驗證形式化證明或合成數據認證，即使在連結攻擊下，重新識別風險仍 ≤ 0.05。  |   3   |  V   |

---

## 11.2 被遺忘權與刪除強制執行

|   #    | Description                                         | Level | Role |
| :----: | --------------------------------------------------- | :---: | :--: |
| 11.2.1 | 驗證資料主體刪除請求是否在少於30天的服務等級協議內，傳播至原始資料集、檢查點、嵌入表示、日誌及備份。 |   1   | D/V  |
| 11.2.2 | 驗證「機器取消學習」程序是否通過認證的取消學習算法實際重新訓練或近似移除數據。             |   2   |  D   |
| 11.2.3 | 驗證影子模型評估證明在遺忘後，被遺忘的記錄對輸出影響少於1%。                     |   2   |  V   |
| 11.2.4 | 確認刪除事件被不可變地記錄並可供監管機構審計。                             |   3   |  V   |

---

## 11.3 差分隱私防護措施

|   #    | Description                     | Level | Role |
| :----: | ------------------------------- | :---: | :--: |
| 11.3.1 | 驗證隱私損失計算儀表板在累積 ε 超過政策閾值時是否發出警報。 |   2   | D/V  |
| 11.3.2 | 驗證黑盒隱私審核估計的 ε̂ 與宣告值相差不超過 10%。   |   2   |  V   |
| 11.3.3 | 驗證形式證明涵蓋所有訓練後微調和嵌入。             |   3   |  V   |

---

## 11.4 目的限制與範圍擴延防護

|   #    | Description                                     | Level | Role |
| :----: | ----------------------------------------------- | :---: | :--: |
| 11.4.1 | 驗證每個數據集和模型檢查點是否攜帶與原始同意相符的機器可讀目的標籤。              |   1   |  D   |
| 11.4.2 | 驗證執行時監控器是否能偵測與宣告用途不符的查詢並觸發軟性拒絕。                 |   1   | D/V  |
| 11.4.3 | 驗證政策即程式碼閘道在未經資料保護影響評估（DPIA）審查的情況下，阻止模型重新部署到新領域。 |   3   |  D   |
| 11.4.4 | 驗證正式的可追蹤性證明，確保每個個人資料生命週期均維持在已同意的範圍內。            |   3   |  V   |

---

## 11.5 同意管理與合法依據追蹤

|   #    | Description                                                         | Level | Role |
| :----: | ------------------------------------------------------------------- | :---: | :--: |
| 11.5.1 | 驗證同意管理平台（Consent-Management Platform，CMP）是否記錄每個資料主體的選擇加入狀態、目的及保留期間。 |   1   | D/V  |
| 11.5.2 | 驗證 API 是否公開同意權杖；模型在推理前必須驗證權杖範圍。                                     |   2   |  D   |
| 11.5.3 | 確認拒絕或撤回同意能在24小時內停止處理流程。                                             |   2   | D/V  |

---

## 11.6 具備隱私控制的聯邦學習

|   #    | Description                         | Level | Role |
| :----: | ----------------------------------- | :---: | :--: |
| 11.6.1 | 驗證客戶端更新在聚合之前是否使用本地差分隱私噪聲添加。         |   1   |  D   |
| 11.6.2 | 驗證訓練指標為差分隱私，且絕不揭露單一客戶端的損失。          |   2   | D/V  |
| 11.6.3 | 確認已啟用抗中毒聚合方法（例如 Krum/Trimmed-Mean）。 |   2   |  V   |
| 11.6.4 | 驗證形式證明顯示整體 ε 預算的效用損失小於 5。           |   3   |  V   |

---

### 參考資料

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

