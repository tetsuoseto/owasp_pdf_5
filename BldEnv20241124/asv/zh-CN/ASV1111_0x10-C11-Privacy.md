# 11 隐私保护与个人数据管理

## 控制目标

在整个人工智能生命周期——数据收集、训练、推理和事件响应过程中，保持严格的隐私保障，确保个人数据仅在明确同意、最小必要范围、可证明的擦除以及正式的隐私保障下被处理。

---

## 11.1 匿名化与数据最小化

|   #    | Description                           | Level | Role |
| :----: | ------------------------------------- | :---: | :--: |
| 11.1.1 | 确认已删除或哈希处理直接标识符和准标识符。                 |   1   | D/V  |
| 11.1.2 | 验证自动审核是否测量k-匿名性/l-多样性，并在阈值低于策略时发出警报。  |   2   | D/V  |
| 11.1.3 | 验证模型特征重要性报告，确保标识符泄露的互信息不超过ε = 0.01。   |   2   |  V   |
| 11.1.4 | 验证形式证明或合成数据认证即使在关联攻击下，重新识别风险也 ≤ 0.05。 |   3   |  V   |

---

## 11.2 被遗忘权与删除执行

|   #    | Description                                      | Level | Role |
| :----: | ------------------------------------------------ | :---: | :--: |
| 11.2.1 | 验证数据主体删除请求是否在少于30天的服务级别协议内传递到原始数据集、检查点、嵌入、日志和备份。 |   1   | D/V  |
| 11.2.2 | 验证“机器遗忘”流程是否通过认证的遗忘算法来物理重新训练或近似移除。               |   2   |  D   |
| 11.2.3 | 验证影子模型评估证明遗忘记录在反学习后对输出的影响少于1%。                   |   2   |  V   |
| 11.2.4 | 验证删除事件是否被不可篡改地记录并且可供监管机构审计。                      |   3   |  V   |

---

## 11.3 差分隐私保护措施

|   #    | Description                      | Level | Role |
| :----: | -------------------------------- | :---: | :--: |
| 11.3.1 | 验证当累积 ε 超过政策阈值时，隐私损失统计仪表盘是否发出警报。 |   2   | D/V  |
| 11.3.2 | 验证黑盒隐私审计估计的 ε̂ 在声明值的 10% 以内。     |   2   |  V   |
| 11.3.3 | 验证形式证明覆盖所有训练后微调和嵌入。              |   3   |  V   |

---

## 11.4 目的限制与范围膨胀防护

|   #    | Description                             | Level | Role |
| :----: | --------------------------------------- | :---: | :--: |
| 11.4.1 | 验证每个数据集和模型检查点是否携带与原始同意相符的机器可读目的标签。      |   1   |  D   |
| 11.4.2 | 验证运行时监视器是否检测到与声明用途不一致的查询并触发软拒绝。         |   1   | D/V  |
| 11.4.3 | 验证策略即代码门控是否阻止在未经过DPIA审核的情况下将模型重新部署到新领域。 |   3   |  D   |
| 11.4.4 | 验证正式的可追溯性证明以确保每个个人数据生命周期都在获得同意的范围内。     |   3   |  V   |

---

## 11.5 同意管理与合法依据追踪

|   #    | Description                             | Level | Role |
| :----: | --------------------------------------- | :---: | :--: |
| 11.5.1 | 验证同意管理平台（CMP）是否记录每个数据主体的选择加入状态、用途和保留期限。 |   1   | D/V  |
| 11.5.2 | 验证API是否公开了同意令牌；模型必须在推理前验证令牌范围。          |   2   |  D   |
| 11.5.3 | 验证被拒绝或撤回的同意在24小时内停止处理流程。                |   2   | D/V  |

---

## 11.6 带隐私控制的联邦学习

|   #    | Description                       | Level | Role |
| :----: | --------------------------------- | :---: | :--: |
| 11.6.1 | 验证客户端更新在聚合前是否采用了局部差分隐私噪声添加。       |   1   |  D   |
| 11.6.2 | 验证训练指标具有差分隐私，且永远不会泄露单个客户的损失。      |   2   | D/V  |
| 11.6.3 | 确认启用了抗投毒聚合（例如，Krum/Trimmed-Mean）。 |   2   |  V   |
| 11.6.4 | 验证形式证明表明整体 ε 预算的效用损失小于 5。         |   3   |  V   |

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

