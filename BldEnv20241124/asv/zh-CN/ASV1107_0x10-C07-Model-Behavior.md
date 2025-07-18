# C7 模型行为、输出控制与安全保障

## 控制目标

模型输出必须具备结构化、可靠、安全、可解释且在生产环境中持续监控。这样做可以减少幻觉现象、隐私泄露、有害内容和失控行为，同时提升用户信任度和合规性。

---

## C7.1 输出格式强制执行

严格的模式、受限的解码和下游验证在内容传播前阻止格式错误或恶意内容。

|   #   | Description                                                 | Level | Role |
| :---: | ----------------------------------------------------------- | :---: | :--: |
| 7.1.1 | 验证系统提示中是否提供了响应模式（例如，JSON模式），并且每个输出都自动进行验证；不符合规范的输出将触发修复或拒绝。 |   1   | D/V  |
| 7.1.2 | 验证已启用约束解码（停止标记、正则表达式、最大令牌数）以防止溢出或提示注入侧信道。                   |   1   | D/V  |
| 7.1.3 | 验证下游组件将输出视为不可信，并根据模式或注入安全的反序列化器对其进行验证。                      |   2   | D/V  |
| 7.1.4 | 验证不当输出事件是否被记录、速率限制并显示在监控中。                                  |   3   |  V   |

---

## C7.2 幻觉检测与缓解

不确定性估计和后备策略遏制了虚构答案。

|   #   | Description                                    | Level | Role |
| :---: | ---------------------------------------------- | :---: | :--: |
| 7.2.1 | 确认基于单词级别的对数概率、集成自洽性或微调的幻觉检测器为每个答案分配置信度评分。      |   1   | D/V  |
| 7.2.2 | 验证低于可配置置信度阈值的响应是否触发回退工作流（例如，检索增强生成、二级模型或人工审核）。 |   1   | D/V  |
| 7.2.3 | 确认幻觉事件已标记根本原因元数据，并被送入事后分析和微调流程。                |   2   | D/V  |
| 7.2.4 | 确认在重大模型或知识库更新后阈值和检测器已重新校准。                     |   3   | D/V  |
| 7.2.5 | 验证仪表盘可视化是否跟踪幻觉率。                               |   3   |  V   |

---

## C7.3 输出安全与隐私过滤

策略过滤器和红队覆盖保护用户及机密数据。

|   #   | Description                                | Level | Role |
| :---: | ------------------------------------------ | :---: | :--: |
| 7.3.1 | 验证生成前和生成后分类器是否阻止符合政策的仇恨、骚扰、自残、极端主义和性露骨内容。  |   1   | D/V  |
| 7.3.2 | 验证在每个响应中是否运行了PII/PCI检测和自动编辑；违规情况将引发隐私事件。   |   1   | D/V  |
| 7.3.3 | 验证机密性标签（例如，商业秘密）是否在多模态间传播，以防止在文本、图像或代码中泄露。 |   2   |  D   |
| 7.3.4 | 验证过滤器绕过尝试或高风险分类是否需要二次审批或用户重新认证。            |   3   | D/V  |
| 7.3.5 | 验证过滤阈值是否反映法律管辖区及用户年龄/角色上下文。                |   3   | D/V  |

---

## C7.4 输出与操作限制

速率限制和审批关卡防止滥用和过度自治。

|   #   | Description                                         | Level | Role |
| :---: | --------------------------------------------------- | :---: | :--: |
| 7.4.1 | 验证每个用户和每个 API 密钥的配额是否限制请求、令牌和费用，并在遇到 429 错误时采用指数退避。 |   1   |  D   |
| 7.4.2 | 验证特权操作（文件写入、代码执行、网络调用）是否需要基于策略的批准或人工介入。             |   1   | D/V  |
| 7.4.3 | 验证跨模态一致性检查确保为同一请求生成的图像、代码和文本不能被用于走私恶意内容。            |   2   | D/V  |
| 7.4.4 | 验证代理委托深度、递归限制和允许的工具列表是否被明确配置。                       |   2   |  D   |
| 7.4.5 | 验证限制违反是否触发结构化安全事件以供SIEM摄取。                          |   3   |  V   |

---

## C7.5 输出可解释性

透明信号提高用户信任和内部调试能力。

|   #   | Description                          | Level | Role |
| :---: | ------------------------------------ | :---: | :--: |
| 7.5.1 | 确认在风险评估认为合适时，向用户展示置信度评分或简要推理摘要。      |   2   | D/V  |
| 7.5.2 | 验证生成的解释避免泄露敏感的系统提示或专有数据。             |   2   | D/V  |
| 7.5.3 | 验证系统是否捕获了令牌级别的对数概率或注意力图，并将其存储以供授权检查。 |   3   |  D   |
| 7.5.4 | 确保可解释性工件与模型发布一起进行版本控制，以便审计。          |   3   |  V   |

---

## C7.6 监控集成

实时可观测性实现了开发与生产之间的闭环。

|   #   | Description                                 | Level | Role |
| :---: | ------------------------------------------- | :---: | :--: |
| 7.6.1 | 验证指标（模式违规、幻觉率、毒性、个人身份信息泄露、延迟、成本）是否流向中央监控平台。 |   1   |  D   |
| 7.6.2 | 验证每个安全指标是否定义了警报阈值，并且具有值班升级路径。               |   1   |  V   |
| 7.6.3 | 验证仪表板是否将输出异常与模型/版本、功能标志和上游数据变化相关联。          |   2   |  V   |
| 7.6.4 | 验证监控数据是否反馈回文档化的MLOps工作流中，用于重新训练、微调或规则更新。    |   2   | D/V  |
| 7.6.5 | 确保对监控管道进行渗透测试并实施访问控制，以避免敏感日志泄露。             |   3   |  V   |

---

## 7.7 生成媒体安全措施

通过执行政策约束、输出验证和可追溯性，确保人工智能系统不生成非法、有害或未经授权的媒体内容。

|   #   | Description                                         | Level | Role |
| :---: | --------------------------------------------------- | :---: | :--: |
| 7.7.1 | 验证系统提示和用户指令是否明确禁止生成非法、有害或未经同意的深度伪造媒体（例如，图像、视频、音频）。  |   1   | D/V  |
| 7.7.2 | 验证提示是否经过筛选，以防止生成冒充、性露骨的深度伪造内容或未经同意描绘真实个人的媒体。        |   2   | D/V  |
| 7.7.3 | 验证系统是否使用感知哈希、水印检测或指纹识别来防止未经授权的版权所有媒体复制。             |   2   |  V   |
| 7.7.4 | 验证所有生成的媒体是否经过加密签名、水印处理，或嵌入防篡改的溯源元数据，以实现下游可追溯性。      |   3   | D/V  |
| 7.7.5 | 验证绕过尝试（例如，提示混淆、俚语、对抗性措辞）是否被检测、记录并限速；重复滥用情况应向监控系统报告。 |   3   |  V   |

## 参考文献

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)

