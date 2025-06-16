# 模型、框架與資料的供應鏈安全 C6

## 控制目標

AI 供應鏈攻擊利用第三方模型、框架或數據集來植入後門、偏見或可利用的代碼。這些控制措施提供端到端的來源管理、漏洞管理和監控，以保護整個模型生命週期。

---

## C6.1 預訓練模型審核與來源管理

在任何微調或部署之前，評估並驗證第三方模型的來源、許可證及隱藏行為。

|   #   | Description                                     | Level | Role |
| :---: | ----------------------------------------------- | :---: | :--: |
| 6.1.1 | 驗證每個第三方模型工件是否包含簽署的來源記錄，以識別來源存儲庫和提交哈希。           |   1   | D/V  |
| 6.1.2 | 在導入之前，使用自動化工具驗證模型是否已掃描惡意層或特洛伊木馬觸發器。             |   1   | D/V  |
| 6.1.3 | 驗證遷移學習微調能通過對抗性評估，以偵測隱藏行為。                       |   2   |  D   |
| 6.1.4 | 驗證模型許可證、出口管制標籤及資料來源聲明是否已記錄於機器學習物料清單（ML-BOM）條目中。 |   2   |  V   |
| 6.1.5 | 確認高風險模型（公開上傳的權重、未經驗證的創作者）保持隔離狀態，直到經過人工審查和批准。    |   3   | D/V  |

---

## C6.2 框架與函式庫掃描

持續掃描機器學習框架和函式庫中的已知漏洞（CVE）及惡意代碼，以確保運行時堆疊的安全性。

|   #   | Description                                  | Level | Role |
| :---: | -------------------------------------------- | :---: | :--: |
| 6.2.1 | 確認持續整合（CI）管線會對人工智慧框架和關鍵函式庫執行相依性掃描。           |   1   | D/V  |
| 6.2.2 | 確認關鍵漏洞（CVSS ≥ 7.0）會阻止推廣到生產映像。                |   1   | D/V  |
| 6.2.3 | 驗證靜態代碼分析是否在分叉或外部引入的機器學習庫上運行。                 |   2   |  D   |
| 6.2.4 | 確認框架升級提案包含參考公開CVE資料來源的安全影響評估。                |   2   |  V   |
| 6.2.5 | 驗證運行時感測器是否會對偏離已簽署軟體物料清單（SBOM）的異常動態函式庫載入發出警報。 |   3   |  V   |

---

## C6.3 依賴鎖定與驗證

將每個依賴項固定在不可變的摘要上，並重現構建以保證產生相同且無篡改的工件。

|   #   | Description                             | Level | Role |
| :---: | --------------------------------------- | :---: | :--: |
| 6.3.1 | 確認所有套件管理工具皆透過鎖定檔強制版本固定。                 |   1   | D/V  |
| 6.3.2 | 確認在容器引用中使用的是不可變的摘要而非可變的標籤。              |   1   | D/V  |
| 6.3.3 | 確認可重現構建檢查在持續整合（CI）執行過程中比較雜湊值，以確保輸出結果一致。 |   2   |  D   |
| 6.3.4 | 驗證建置證明已儲存18個月以供稽核追蹤。                    |   2   |  V   |
| 6.3.5 | 驗證過期的相依性是否會觸發自動拉取請求以更新或分支固定版本。          |   3   |  D   |

---

## C6.4 可信來源強制執行

僅允許從經過密碼學驗證且組織批准的來源下載工件，並阻止所有其他來源。

|   #   | Description                                | Level | Role |
| :---: | ------------------------------------------ | :---: | :--: |
| 6.4.1 | 驗證模型權重、資料集和容器僅從核准的域名或內部註冊表下載。              |   1   | D/V  |
| 6.4.2 | 驗證 Sigstore/Cosign 簽名以確認發行者身份，然後再將工件緩存到本地。 |   1   | D/V  |
| 6.4.3 | 驗證外發代理是否阻擋未經身份驗證的工件下載，以執行受信任來源政策。          |   2   |  D   |
| 6.4.4 | 確認倉庫允許清單每季度進行審查，並提供每個條目具備業務合理性的證據。         |   2   |  V   |
| 6.4.5 | 驗證政策違規是否會觸發工件隔離並回滾相關的管線運行。                 |   3   |  V   |

---

## C6.5 第三方數據集風險評估

評估外部數據集的中毒、偏見及法律合規性，並在其整個生命週期中持續監控。

|   #   | Description                             | Level | Role |
| :---: | --------------------------------------- | :---: | :--: |
| 6.5.1 | 確認外部數據集經過汙染風險評分（例如，數據指紋識別、異常值檢測）。       |   1   | D/V  |
| 6.5.2 | 確保在數據集批准之前已計算偏差指標（人口統計平等、機會均等）。         |   1   |  D   |
| 6.5.3 | 驗證資料集的來源和授權條款是否已記錄在機器學習物料清單（ML‑BOM）條目中。 |   2   |  V   |
| 6.5.4 | 驗證定期監控是否能檢測到託管資料集中的漂移或損壞。               |   2   |  V   |
| 6.5.5 | 確認在訓練之前，透過自動清除程序刪除不允許的內容（版權、個人識別資訊）。    |   3   |  D   |

---

## C6.6 供應鏈攻擊監控

通過 CVE 資料流、審計日誌分析和紅隊模擬，及早偵測供應鏈威脅。

|   #   | Description                                   | Level | Role |
| :---: | --------------------------------------------- | :---: | :--: |
| 6.6.1 | 確認 CI/CD 審核日誌是否串流至 SIEM，以偵測異常的套件拉取或遭竄改的建置步驟。  |   1   |  V   |
| 6.6.2 | 確認事件回應流程手冊包含受損模型或函式庫的回滾程序。                    |   2   |  D   |
| 6.6.3 | 驗證威脅情報增強標籤是否在警報分類中標註了特定於機器學習的指標（例如，模型中毒的IoC）。 |   3   |  V   |

---

## C6.7 模型工件的機器學習物料清單 (ML-BOM)

生成並簽署詳細的機器學習專用軟體物料清單（ML‑BOMs），以便下游使用者在部署時能驗證元件完整性。

|   #   | Description                                             | Level | Role |
| :---: | ------------------------------------------------------- | :---: | :--: |
| 6.7.1 | 確認每個模型工件都發布包含資料集、權重、超參數和許可證的機器學習物料清單（ML‑BOM）。           |   1   | D/V  |
| 6.7.2 | 確認機器學習元件清單（ML-BOM）生成和 Cosign 簽名已在持續整合（CI）中自動執行，且為合併所必須。 |   1   | D/V  |
| 6.7.3 | 驗證如果任何元件元資料（雜湊值、授權）遺失，ML-BOM 完整性檢查會導致建置失敗。              |   2   |  D   |
| 6.7.4 | 驗證下游使用者是否能通過 API 查詢機器學習材料清單（ML-BOMs），以在部署時驗證導入的模型。      |   2   |  V   |
| 6.7.5 | 驗證機器學習物料清單（ML-BOMs）是否受版本控制並進行差異比較，以檢測未經授權的修改。           |   3   |  V   |

---

## 參考文獻

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)

