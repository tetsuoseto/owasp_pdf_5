# C8 存储、嵌入和向量数据库安全

## 控制目标

嵌入和向量存储作为现代人工智能系统的“实时记忆”，持续接收用户提供的数据，并通过检索增强生成（RAG）将其呈现在模型上下文中。如果不加以管理，这种记忆可能泄露个人身份信息（PII）、违反用户同意，或被逆向推断以还原原始文本。本控制类别的目标是加强记忆管道和向量数据库的安全，使访问权限遵循最小特权原则，嵌入具有隐私保护功能，存储的向量能够根据需求过期或被撤销，并确保每个用户的记忆不污染其他用户的提示或生成内容。

---

## C8.1 内存和RAG索引的访问控制

对每个向量集合实施细粒度访问控制。

|   #   | Description                                              | Level | Role |
| :---: | -------------------------------------------------------- | :---: | :--: |
| 8.1.1 | 验证行级/命名空间级访问控制规则是否限制了每个租户、集合或文档标签的插入、删除和查询操作。            |   1   | D/V  |
| 8.1.2 | 验证 API 密钥或 JWT 是否包含范围限定的声明（例如，集合 ID、操作动词），并且至少每季度进行一次轮换。 |   1   | D/V  |
| 8.1.3 | 验证特权升级尝试（例如，跨命名空间相似性查询）是否在5分钟内被检测到并记录到SIEM中。             |   2   | D/V  |
| 8.1.4 | 验证向量数据库审计日志是否包含主体标识符、操作、向量ID/命名空间、相似度阈值和结果数量。            |   2   | D/V  |
| 8.1.5 | 确保在引擎升级或索引分片规则更改时，对访问决策进行绕过缺陷测试。                         |   3   |  V   |

---

## C8.2 嵌入清理与验证

在向量化之前，对文本进行个人身份信息（PII）预筛查，进行编辑或假名化，并可选择性地对嵌入向量进行后处理，以去除残留信号。

|   #   | Description                                         | Level | Role |
| :---: | --------------------------------------------------- | :---: | :--: |
| 8.2.1 | 验证通过自动分类器检测到的个人身份信息（PII）和受监管数据，并在嵌入之前进行掩码处理、标记化或丢弃。 |   1   | D/V  |
| 8.2.2 | 验证嵌入管道是否会拒绝或隔离包含可执行代码或非 UTF-8 文本的输入，这些内容可能会污染索引。    |   1   |  D   |
| 8.2.3 | 验证是否对距离任何已知个人身份信息（PII）标记低于可配置阈值的句子嵌入应用了局部或度量差分隐私净化。 |   2   | D/V  |
| 8.2.4 | 验证清理效果（例如，个人身份信息去除的召回率、语义漂移）至少每半年通过基准语料库进行验证。       |   2   |  V   |
| 8.2.5 | 验证清理配置是否受版本控制，并且更改经过同伴审查。                           |   3   | D/V  |

---

## C8.3 内存过期、撤销与删除

GDPR“被遗忘权”及类似法律要求及时删除；因此，向量存储必须支持TTL、硬删除和墓碑机制，以确保被撤销的向量无法被恢复或重新索引。

|   #   | Description                                 | Level | Role |
| :---: | ------------------------------------------- | :---: | :--: |
| 8.3.1 | 验证每个向量和元数据记录是否携带由自动清理任务执行的TTL或显式保留标签。       |   1   | D/V  |
| 8.3.2 | 验证用户发起的删除请求是否在30天内清除向量、元数据、缓存副本和衍生索引。       |   1   | D/V  |
| 8.3.3 | 验证在硬件支持的情况下，逻辑删除是否紧随存储块的加密销毁，或者通过密钥库密钥销毁进行。 |   2   |  D   |
| 8.3.4 | 验证过期向量在过期后500毫秒内被排除在最近邻搜索结果之外。              |   3   | D/V  |

---

## C8.4 防止嵌入反演与泄露

最近的防御方法——噪声叠加、投影网络、隐私神经元扰动和应用层加密——可以将令牌级别的反演率降低到5%以下。

|   #   | Description                                             | Level | Role |
| :---: | ------------------------------------------------------- | :---: | :--: |
| 8.4.1 | 验证是否存在涵盖反演攻击、成员身份攻击和属性推断攻击的正式威胁模型，并确保该模型每年进行审核。         |   1   |  V   |
| 8.4.2 | 验证应用层加密或可搜索加密是否能防止基础设施管理员或云工作人员直接读取向量。                  |   2   | D/V  |
| 8.4.3 | 验证防御参数（DP的ε，噪声σ，投影维度k）是否在隐私保护≥99%令牌保护和效用损失≤3%准确率之间达到平衡。 |   3   |  V   |
| 8.4.4 | 验证反转鲁棒性指标是否作为模型更新发布门控的一部分，并定义了回归预算。                     |   3   | D/V  |

---

## C8.5 用户特定内存的范围强制执行

跨租户泄露仍然是RAG的主要风险：过滤不当的相似性查询可能暴露其他客户的私有文档。

|   #   | Description                                     | Level | Role |
| :---: | ----------------------------------------------- | :---: | :--: |
| 8.5.1 | 在传递给大语言模型（LLM）提示之前，验证每个检索查询是否经过租户/用户ID的后过滤。     |   1   | D/V  |
| 8.5.2 | 验证集合名称或命名空间 ID 是否针对每个用户或租户进行了加盐处理，以防止向量跨范围发生冲突。 |   1   |  D   |
| 8.5.3 | 验证超过可配置距离阈值但在调用者作用域之外的相似性结果是否被丢弃并触发安全警报。        |   2   | D/V  |
| 8.5.4 | 验证多租户压力测试是否模拟了试图检索超出范围文档的对抗性查询，并证明没有信息泄露。       |   2   |  V   |
| 8.5.5 | 验证加密密钥是否按租户隔离，确保即使物理存储共享也实现密码学隔离。               |   3   | D/V  |

---

## C8.6 高级内存系统安全

针对复杂内存架构（包括情节记忆、语义记忆和工作记忆）制定的安全控制措施，涵盖具体的隔离和验证要求。

|   #   | Description                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | 验证不同类型的记忆（情景记忆、语义记忆、工作记忆）是否具有独立的安全上下文，包括基于角色的访问控制、独立的加密密钥以及针对每种记忆类型的访问模式文档。 |   1   | D/V  |
| 8.6.2 | 验证记忆合并过程是否包含安全验证，通过内容清理、来源验证和完整性检查，防止恶意记忆的注入，然后再存储。                         |   2   | D/V  |
| 8.6.3 | 验证内存检索查询是否经过验证和清理，以通过查询模式分析、访问控制执行和结果过滤防止未经授权的信息提取。                         |   2   | D/V  |
| 8.6.4 | 验证内存遗忘机制通过密钥删除、多次覆盖或带有验证证书的硬件安全删除，具备加密擦除保证，安全地删除敏感信息。                       |   3   | D/V  |
| 8.6.5 | 验证内存系统完整性是否通过校验和、审计日志以及当内存内容在正常操作之外发生变化时的自动警报，持续监控是否存在未经授权的修改或损坏。           |   3   | D/V  |

---

## 参考文献

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)

