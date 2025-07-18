# C6 模型、框架與數據的供應鏈安全

## 控制目標

AI 供應鏈攻擊利用第三方模型、框架或數據集來植入後門、偏見或可被利用的程式碼。這些控管措施提供從端到端的來源追蹤、漏洞管理及監控，以保護整個模型生命週期。

---

## C6.1 預訓練模型審核與來源追蹤

在進行任何微調或部署之前，評估並驗證第三方模型的來源、許可權及隱藏行為。

|   #   | Description                                    | Level | Role |
| :---: | ---------------------------------------------- | :---: | :--: |
| 6.1.1 | 確認每個第三方模型工件均包含簽署的來源記錄，該記錄標明來源存儲庫和提交哈希。         |   1   | D/V  |
| 6.1.2 | 在導入模型之前，請使用自動化工具驗證模型是否含有惡意層或木馬觸發器。             |   1   | D/V  |
| 6.1.3 | 驗證轉移學習微調是否通過對抗性評估以檢測隱藏行為。                      |   2   |  D   |
| 6.1.4 | 確認模型授權、出口管制標籤及資料來源聲明是否已記錄在機器學習物料清單（ML-BOM）條目中。 |   2   |  V   |
| 6.1.5 | 確認高風險模型（公開上傳的權重、未經驗證的創作者）在人工審核和簽署之前保持隔離狀態。     |   3   | D/V  |

---

## C6.2 框架與函式庫掃描

持續掃描機器學習框架和函式庫中的 CVE 和惡意程式碼，以保持執行時堆疊的安全。

|   #   | Description                            | Level | Role |
| :---: | -------------------------------------- | :---: | :--: |
| 6.2.1 | 確認 CI 管道對 AI 框架和關鍵庫執行依賴性掃描器。           |   1   | D/V  |
| 6.2.2 | 確認關鍵漏洞（CVSS ≥ 7.0）會阻止推送到生產映像。          |   1   | D/V  |
| 6.2.3 | 驗證靜態程式碼分析是否對分支或供應的機器學習庫進行執行。           |   2   |  D   |
| 6.2.4 | 確認框架升級提案包含參照公開 CVE 資料來源的安全影響評估。        |   2   |  V   |
| 6.2.5 | 驗證執行時感測器是否會對偏離已簽署 SBOM 的異常動態函式庫載入發出警報。 |   3   |  V   |

---

## C6.3 依賴鎖定與驗證

將每個依賴項固定到不可變的摘要，並重現構建以保證生成相同且無篡改的產物。

|   #   | Description                      | Level | Role |
| :---: | -------------------------------- | :---: | :--: |
| 6.3.1 | 驗證所有套件管理器是否通過鎖定檔強制執行版本鎖定。        |   1   | D/V  |
| 6.3.2 | 驗證在容器參考中使用不可變的摘要，而非可變的標籤。        |   1   | D/V  |
| 6.3.3 | 驗證可重複構建檢查通過 CI 運行之間比較哈希值以確保輸出一致。 |   2   |  D   |
| 6.3.4 | 確認建置證明文件已保存18個月以供審計追蹤。           |   2   |  V   |
| 6.3.5 | 驗證過期的相依性是否會觸發自動拉取請求以更新或分叉固定版本。   |   3   |  D   |

---

## C6.4 可信來源強制執行

僅允許從經過加密驗證且組織批准的來源下載工件，並阻擋所有其他來源。

|   #   | Description                                 | Level | Role |
| :---: | ------------------------------------------- | :---: | :--: |
| 6.4.1 | 確認模型權重、資料集和容器僅從核准的網域或內部註冊表下載。               |   1   | D/V  |
| 6.4.2 | 在將工件緩存在本地之前，請驗證 Sigstore/Cosign 簽名以確認發布者身份。 |   1   | D/V  |
| 6.4.3 | 驗證出口代理是否阻擋未經身份驗證的工件下載，以強制執行可信來源政策。          |   2   |  D   |
| 6.4.4 | 驗證儲存庫允許名單是否每季度審查一次，並且對每一項目具備業務正當性證據。        |   2   |  V   |
| 6.4.5 | 驗證政策違規是否會觸發對工件的隔離以及對依賴管線運行的回滾。              |   3   |  V   |

---

## C6.5 第三方數據集風險評估

評估外部數據集的污染、偏差以及法律合規性，並在其整個生命周期中進行監控。

|   #   | Description                         | Level | Role |
| :---: | ----------------------------------- | :---: | :--: |
| 6.5.1 | 驗證外部數據集是否經過污染風險評分（例如，數據指紋識別、離群值檢測）。 |   1   | D/V  |
| 6.5.2 | 確認在數據集審核之前已計算偏差指標（人口統計平等、機會均等）。     |   1   |  D   |
| 6.5.3 | 驗證資料集的來源和授權條款是否已記錄在 ML-BOM 項目中。     |   2   |  V   |
| 6.5.4 | 驗證定期監控是否能檢測出託管資料集中的漂移或損壞。           |   2   |  V   |
| 6.5.5 | 確認在訓練之前，透過自動清理移除不允許的內容（版權、個人識別資訊）。  |   3   |  D   |

---

## C6.6 供應鏈攻擊監控

透過 CVE 資訊來源、審計日誌分析及紅隊模擬，及早偵測供應鏈威脅。

|   #   | Description                                  | Level | Role |
| :---: | -------------------------------------------- | :---: | :--: |
| 6.6.1 | 確認 CI/CD 審計日誌是否串流至 SIEM 以偵測異常的套件下載或被篡改的建置步驟。 |   1   |  V   |
| 6.6.2 | 確認事件回應流程手冊包含受損模型或程式庫的回滾程序。                   |   2   |  D   |
| 6.6.3 | 驗證威脅情報增強是否在警報分流中對機器學習專用指標（例如，模型中毒的 IoC）進行標記。 |   3   |  V   |

---

## C6.7 模型工件的機器學習組件清單（ML-BOM）

生成並簽署詳細的機器學習專用軟體物料清單（ML-BOM），以便下游使用者能在部署時驗證元件的完整性。

|   #   | Description                                        | Level | Role |
| :---: | -------------------------------------------------- | :---: | :--: |
| 6.7.1 | 確認每個模型產物都發佈一個 ML-BOM，該清單列出數據集、權重、超參數和授權。           |   1   | D/V  |
| 6.7.2 | 確認 ML-BOM 的生成和 Cosign 簽名在持續整合（CI）中是自動化的，並且是合併所必需的。 |   1   | D/V  |
| 6.7.3 | 驗證如果任何組件元數據（雜湊值、授權）缺失，ML-BOM 完整性檢查是否會導致建置失敗。       |   2   |  D   |
| 6.7.4 | 驗證下游消費者能夠透過 API 查詢 ML-BOM，以在部署時驗證已導入的模型。           |   2   |  V   |
| 6.7.5 | 驗證 ML‑BOMs 是否受版本控制並進行差異比對以檢測未經授權的修改。               |   3   |  V   |

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

