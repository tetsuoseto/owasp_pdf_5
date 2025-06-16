# C6 供应链安全：模型、框架与数据

## 控制目标

AI 供应链攻击利用第三方模型、框架或数据集植入后门、偏见或可利用的代码。这些控制措施提供端到端的来源追踪、漏洞管理和监控，以保护整个模型生命周期。

---

## C6.1 预训练模型审查与来源管理

在进行任何微调或部署之前，评估并验证第三方模型的来源、许可及隐藏行为。

|   #   | Description                                | Level | Role |
| :---: | ------------------------------------------ | :---: | :--: |
| 6.1.1 | 验证每个第三方模型工件是否包含签名的出处记录，以识别源代码库和提交哈希。       |   1   | D/V  |
| 6.1.2 | 确保模型在导入前使用自动化工具扫描是否存在恶意层或特洛伊木马触发器。         |   1   | D/V  |
| 6.1.3 | 验证迁移学习微调通过对抗性评估以检测隐藏行为。                    |   2   |  D   |
| 6.1.4 | 验证模型许可证、出口控制标签和数据来源声明是否记录在ML-BOM条目中。       |   2   |  V   |
| 6.1.5 | 验证高风险模型（公开上传的权重，未经验证的创建者）在人工审核和批准之前保持隔离状态。 |   3   | D/V  |

---

## C6.2 框架与库扫描

持续扫描机器学习框架和库中的公共漏洞披露（CVE）和恶意代码，以保持运行时堆栈的安全。

|   #   | Description                               | Level | Role |
| :---: | ----------------------------------------- | :---: | :--: |
| 6.2.1 | 验证持续集成（CI）管道是否对人工智能框架和关键库运行依赖扫描器。         |   1   | D/V  |
| 6.2.2 | 验证关键漏洞（CVSS ≥ 7.0）是否阻止推广到生产镜像。            |   1   | D/V  |
| 6.2.3 | 验证静态代码分析是否在分支或集成的机器学习库上运行。                |   2   |  D   |
| 6.2.4 | 验证框架升级提案是否包含引用公共CVE信息源的安全影响评估。            |   2   |  V   |
| 6.2.5 | 验证运行时传感器是否对偏离已签名软件物料清单（SBOM）的意外动态库加载发出警报。 |   3   |  V   |

---

## C6.3 依赖固定与验证

将所有依赖项固定到不可变的摘要，并通过重现构建来保证生成完全相同且无篡改的工件。

|   #   | Description                              | Level | Role |
| :---: | ---------------------------------------- | :---: | :--: |
| 6.3.1 | 验证所有包管理器是否通过锁定文件强制版本固定。                  |   1   | D/V  |
| 6.3.2 | 验证容器引用中使用的是不可变摘要，而非可变标签。                 |   1   | D/V  |
| 6.3.3 | 验证可重现构建检查是否在持续集成（CI）运行之间比较哈希值，以确保输出结果一致。 |   2   |  D   |
| 6.3.4 | 验证构建证明是否存储了18个月，以便审计可追溯性。                |   2   |  V   |
| 6.3.5 | 验证已过期的依赖项是否会触发自动拉取请求，以更新或分叉固定版本。         |   3   |  D   |

---

## C6.4 可信来源执行

仅允许从经过密码学验证的组织批准的来源下载构件，并阻止所有其他来源。

|   #   | Description                               | Level | Role |
| :---: | ----------------------------------------- | :---: | :--: |
| 6.4.1 | 验证模型权重、数据集和容器仅从批准的域名或内部注册表下载。             |   1   | D/V  |
| 6.4.2 | 验证 Sigstore/Cosign 签名以确认发布者身份，然后才在本地缓存工件。 |   1   | D/V  |
| 6.4.3 | 验证出站代理是否阻止未经认证的工件下载，以执行可信来源策略。            |   2   |  D   |
| 6.4.4 | 验证仓库允许名单是否每季度审查一次，并附有每个条目的业务理由的证据。        |   2   |  V   |
| 6.4.5 | 验证策略违规是否会触发工件隔离和依赖流水线运行的回滚。               |   3   |  V   |

---

## C6.5 第三方数据集风险评估

评估外部数据集的投毒、偏见和法律合规性，并在其整个生命周期内进行监控。

|   #   | Description                             | Level | Role |
| :---: | --------------------------------------- | :---: | :--: |
| 6.5.1 | 验证外部数据集是否经过毒害风险评分（例如，数据指纹识别、异常值检测）。     |   1   | D/V  |
| 6.5.2 | 在数据集批准之前，验证偏差指标（人口统计公平性、机会均等）是否已计算。     |   1   |  D   |
| 6.5.3 | 验证数据集的来源和许可条款是否已记录在ML-BOM条目中。           |   2   |  V   |
| 6.5.4 | 验证定期监控是否能够检测到托管数据集中的漂移或损坏。              |   2   |  V   |
| 6.5.5 | 在训练之前，通过自动清洗验证是否已移除不允许的内容（版权信息、个人身份信息）。 |   3   |  D   |

---

## C6.6 供应链攻击监控

通过CVE信息源、审计日志分析和红队模拟，及早检测供应链威胁。

|   #   | Description                                          | Level | Role |
| :---: | ---------------------------------------------------- | :---: | :--: |
| 6.6.1 | 验证 CI/CD 审计日志是否能够流式传输到 SIEM 检测，以发现异常的软件包拉取或被篡改的构建步骤。 |   1   |  V   |
| 6.6.2 | 确认事件响应剧本中包含受损模型或库的回滚程序。                              |   2   |  D   |
| 6.6.3 | 验证威胁情报丰富功能是否对警报分类中的机器学习特定指标（例如模型投毒的威胁指标IoCs）进行了标记。   |   3   |  V   |

---

## C6.7 模型工件的机器学习物料清单（ML-BOM）

生成并签署详细的机器学习专用软件物料清单（ML‑BOMs），以便下游使用者在部署时验证组件的完整性。

|   #   | Description                                       | Level | Role |
| :---: | ------------------------------------------------- | :---: | :--: |
| 6.7.1 | 验证每个模型构件是否发布了包含数据集、权重、超参数和许可证的机器学习物料清单（ML-BOM）。   |   1   | D/V  |
| 6.7.2 | 验证ML-BOM生成和Cosign签名是否在持续集成（CI）中实现自动化，并且作为合并的必需条件。 |   1   | D/V  |
| 6.7.3 | 验证如果任何组件元数据（哈希值、许可）缺失，ML-BOM 完整性检查将导致构建失败。        |   2   |  D   |
| 6.7.4 | 验证下游消费者是否能够通过API查询机器学习物料清单（ML-BOM），以在部署时验证导入的模型。  |   2   |  V   |
| 6.7.5 | 验证机器学习物料清单（ML-BOMs）是否受版本控制并进行差异比较，以检测未经授权的修改。     |   3   |  V   |

---

## 参考文献

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

