# 11 隐私保护与个人数据管理

## 控制目标

在整个人工智能生命周期——数据收集、训练、推断和事件响应——中保持严格的隐私保障，确保个人数据仅在明确同意、最低必要范围、可验证删除和正式隐私保证的条件下进行处理。

---

## 11.1 匿名化与数据最小化

|   #    | Description                             | Level | Role |
| :----: | --------------------------------------- | :---: | :--: |
| 11.1.1 | 验证直接标识符和准标识符是否已被删除或哈希处理。                |   1   | D/V  |
| 11.1.2 | 验证自动审计是否测量 k-匿名性 / l-多样性，并在阈值低于政策时发出警报。 |   2   | D/V  |
| 11.1.3 | 验证模型特征重要性报告，确保标识符泄漏的互信息不超过 ε = 0.01。    |   2   |  V   |
| 11.1.4 | 验证形式化证明或合成数据认证在联结攻击下的重新识别风险是否≤ 0.05。    |   3   |  V   |

---

## 11.2 被遗忘权与删除执行

|   #    | Description                                      | Level | Role |
| :----: | ------------------------------------------------ | :---: | :--: |
| 11.2.1 | 验证数据主体删除请求是否在少于30天的服务级别协议内传播至原始数据集、检查点、嵌入、日志和备份。 |   1   | D/V  |
| 11.2.2 | 验证“机器去学习”程序是否通过经认证的去学习算法进行物理再训练或近似移除。            |   2   |  D   |
| 11.2.3 | 验证影子模型评估证明遗忘记录在遗忘后对输出的影响不到1%。                    |   2   |  V   |
| 11.2.4 | 验证删除事件是否被不可篡改地记录并且可供监管机构审计。                      |   3   |  V   |

---

## 11.3 差分隐私保护措施

|   #    | Description                     | Level | Role |
| :----: | ------------------------------- | :---: | :--: |
| 11.3.1 | 验证当累计ε超过策略阈值时，隐私损失计算仪表板是否会发出警报。 |   2   | D/V  |
| 11.3.2 | 验证黑盒隐私审计估计的 ε̂ 是否在声明值的 10% 以内。  |   2   |  V   |
| 11.3.3 | 验证正式证明涵盖所有训练后微调和嵌入。             |   3   |  V   |

---

## 11.4 目的限制与范围扩展保护

|   #    | Description                                      | Level | Role |
| :----: | ------------------------------------------------ | :---: | :--: |
| 11.4.1 | 验证每个数据集和模型检查点是否带有与原始同意一致的机器可读目的标签。               |   1   |  D   |
| 11.4.2 | 验证运行时监视器是否能够检测与声明目的不一致的查询并触发软拒绝。                 |   1   | D/V  |
| 11.4.3 | 验证基于策略即代码的网关在未经数据保护影响评估（DPIA）审查的情况下阻止模型重新部署到新领域。 |   3   |  D   |
| 11.4.4 | 验证形式化的可追溯性证明，确保每个人员数据的生命周期都保持在已同意的范围内。           |   3   |  V   |

---

## 11.5 同意管理与合法依据追踪

|   #    | Description                             | Level | Role |
| :----: | --------------------------------------- | :---: | :--: |
| 11.5.1 | 验证同意管理平台（CMP）是否记录每个数据主体的选择加入状态、用途和保留期限。 |   1   | D/V  |
| 11.5.2 | 验证API是否公开了同意令牌；模型必须在推理前验证令牌范围。          |   2   |  D   |
| 11.5.3 | 确认被拒绝或撤回的同意将在24小时内停止处理流程。               |   2   | D/V  |

---

## 11.6 具有隐私控制的联邦学习

|   #    | Description                   | Level | Role |
| :----: | ----------------------------- | :---: | :--: |
| 11.6.1 | 验证客户端更新在聚合之前是否采用了本地差分隐私噪声添加。  |   1   |  D   |
| 11.6.2 | 验证训练指标是否满足差分隐私，且绝不泄露单个客户端的损失。 |   2   | D/V  |
| 11.6.3 | 确保启用了抗投毒聚合方法（例如，Krum/修剪均值）。   |   2   |  V   |
| 11.6.4 | 验证形式化证明表明整体ε预算的公用损失小于5。       |   3   |  V   |

---

### 参考文献

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

