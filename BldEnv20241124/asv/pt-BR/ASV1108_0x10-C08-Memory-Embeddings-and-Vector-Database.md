# Segurança da Memória C8, Embeddings e Banco de Dados Vetoriais

## Objetivo de Controle

Incorporações (embeddings) e armazenamento vetorial atuam como a "memória ativa" dos sistemas de IA contemporâneos, aceitando continuamente dados fornecidos pelos usuários e os trazendo de volta para os contextos dos modelos por meio da Geração Aumentada por Recuperação (RAG - Retrieval-Augmented Generation). Se deixada sem controle, essa memória pode vazar informações pessoais identificáveis (PII), violar consentimentos ou ser invertida para reconstruir o texto original. O objetivo desta família de controles é fortalecer os pipelines de memória e os bancos de dados vetoriais para que o acesso seja minimamente privilegiado, as incorporações preservem a privacidade, os vetores armazenados expirem ou possam ser revogados sob demanda, e a memória por usuário nunca contamine os prompts ou completions de outro usuário.

---

## C8.1 Controles de Acesso na Memória e Índices RAG

Implemente controles de acesso granulares em cada coleção de vetores.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Verifique se as regras de controle de acesso em nível de linha/namespace restringem as operações de inserção, exclusão e consulta por inquilino, coleção ou tag de documento.     |   1   | D/V  |
| 8.1.2 | Verifique se as chaves de API ou JWTs possuem reivindicações com escopo (por exemplo, IDs de coleção, verbos de ação) e são rotacionadas pelo menos trimestralmente.              |   1   | D/V  |
| 8.1.3 | Verifique se as tentativas de escalonamento de privilégios (por exemplo, consultas de similaridade entre namespaces) são detectadas e registradas em um SIEM dentro de 5 minutos. |   2   | D/V  |
| 8.1.4 | Verifique se o banco de dados vetorial registra o identificador do sujeito da auditoria, operação, ID/namespace do vetor, limiar de similaridade e contagem de resultados.        |   2   | D/V  |
| 8.1.5 | Verifique se as decisões de acesso são testadas quanto a falhas de bypass sempre que os motores são atualizados ou as regras de indexação em shard são alteradas.                 |   3   |  V   |

---

## C8.2 Sanitização e Validação de Embeddings

Pré-analise o texto em busca de informações pessoais identificáveis (PII), redija ou pseudonimiza antes da vetorização e, opcionalmente, pós-processe os embeddings para remover sinais residuais.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 8.2.1 | Verifique se os Dados Pessoais Identificáveis (PII) e os dados regulamentados são detectados por meio de classificadores automatizados e mascarados, tokenizados ou descartados antes da incorporação.                                     |   1   | D/V  |
| 8.2.2 | Verifique se os pipelines de incorporação rejeitam ou colocam em quarentena entradas que contenham código executável ou artefatos não UTF-8 que possam contaminar o índice.                                                                |   1   |  D   |
| 8.2.3 | Verifique se a sanitização local ou métrica de privacidade diferencial é aplicada às embeddings de sentenças cuja distância para qualquer token conhecido de Informação Pessoal Identificável (PII) fica abaixo de um limite configurável. |   2   | D/V  |
| 8.2.4 | Verifique se a eficácia da sanitização (por exemplo, recall da redação de PII, deriva semântica) é validada pelo menos semestralmente contra corpora de referência.                                                                        |   2   |  V   |
| 8.2.5 | Verifique se as configurações de sanitização estão sob controle de versão e se as alterações passam por revisão por pares.                                                                                                                 |   3   | D/V  |

---

## C8.3 Expiração, Revogação e Exclusão de Memória

O "direito ao esquecimento" do GDPR e leis similares exigem a exclusão oportuna; portanto, os repositórios de vetores devem suportar TTLs, exclusões definitivas e tomb-stoning para que vetores revogados não possam ser recuperados ou reindexados.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Verifique se cada vetor e registro de metadados possui um TTL ou rótulo de retenção explícito que seja respeitado por trabalhos automatizados de limpeza.                         |   1   | D/V  |
| 8.3.2 | Verifique se as solicitações de exclusão iniciadas pelo usuário eliminam vetores, metadados, cópias em cache e índices derivados dentro de 30 dias.                               |   1   | D/V  |
| 8.3.3 | Verifique se as exclusões lógicas são seguidas por destruição criptográfica dos blocos de armazenamento, caso o hardware suporte, ou pela destruição da chave do cofre de chaves. |   2   |  D   |
| 8.3.4 | Verifique se os vetores expirados são excluídos dos resultados da busca por vizinhos mais próximos em menos de 500 ms após a expiração.                                           |   3   | D/V  |

---

## C8.4 Prevenir Inversão e Vazamento de Embeddings

Defesas recentes — sobreposição de ruído, redes de projeção, perturbação de neurônios de privacidade e criptografia na camada de aplicação — podem reduzir as taxas de inversão em nível de token para menos de 5%.

|   #   | Description                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Verifique se existe um modelo formal de ameaça que cubra ataques de inversão, de associação e de inferência de atributos, e se ele é revisado anualmente.                               |   1   |  V   |
| 8.4.2 | Verifique se a criptografia na camada de aplicação ou a criptografia pesquisável protegem os vetores contra leituras diretas por administradores de infraestrutura ou pessoal da nuvem. |   2   | D/V  |
| 8.4.3 | Verifique se os parâmetros de defesa (ε para DP, ruído σ, posto de projeção k) equilibram a privacidade ≥ 99% de proteção dos tokens e utilidade ≤ 3% de perda de precisão.             |   3   |  V   |
| 8.4.4 | Verifique se as métricas de resistência à inversão fazem parte dos critérios de liberação para atualizações de modelos, com orçamentos de regressão definidos.                          |   3   | D/V  |

---

## C8.5 Aplicação de Escopo para Memória Específica do Usuário

O vazamento entre locatários continua sendo um dos principais riscos do RAG: consultas de similaridade filtradas de forma inadequada podem revelar documentos privados de outro cliente.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Verifique se toda consulta de recuperação é filtrada posteriormente pelo ID do inquilino/usuário antes de ser enviada ao prompt do LLM.                                    |   1   | D/V  |
| 8.5.2 | Verifique se os nomes das coleções ou IDs com namespace são salteados por usuário ou locatário para que os vetores não possam colidir entre escopos.                       |   1   |  D   |
| 8.5.3 | Verifique se os resultados de similaridade acima de um limite de distância configurável, mas fora do escopo do chamador, são descartados e acionam alertas de segurança.   |   2   | D/V  |
| 8.5.4 | Verifique se os testes de estresse multi-inquilino simulam consultas adversariais que tentam recuperar documentos fora do escopo e demonstram ausência total de vazamento. |   2   |  V   |
| 8.5.5 | Verifique se as chaves de criptografia são segregadas por locatário, garantindo isolamento criptográfico mesmo que o armazenamento físico seja compartilhado.              |   3   | D/V  |

---

## C8.6 Segurança Avançada de Sistemas de Memória

Controles de segurança para arquiteturas de memória sofisticadas, incluindo memória episódica, semântica e de trabalho, com requisitos específicos de isolamento e validação.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Verifique se os diferentes tipos de memória (episódica, semântica, de trabalho) possuem contextos de segurança isolados com controles de acesso baseados em funções, chaves de criptografia separadas e padrões de acesso documentados para cada tipo de memória.         |   1   | D/V  |
| 8.6.2 | Verifique se os processos de consolidação de memória incluem validação de segurança para impedir a inserção de memórias maliciosas por meio da sanitização de conteúdo, verificação da fonte e checagem de integridade antes do armazenamento.                            |   2   | D/V  |
| 8.6.3 | Verifique se as consultas de recuperação de memória são validadas e higienizadas para evitar a extração de informações não autorizadas por meio da análise de padrão de consultas, aplicação de controle de acesso e filtragem de resultados.                             |   2   | D/V  |
| 8.6.4 | Verifique se os mecanismos de esquecimento de memória deletam informações sensíveis de forma segura com garantias de apagamento criptográfico usando exclusão de chaves, sobrescrita múltipla ou exclusão segura baseada em hardware com certificados de verificação.     |   3   | D/V  |
| 8.6.5 | Verifique se a integridade do sistema de memória é continuamente monitorada para modificações não autorizadas ou corrupção por meio de somas de verificação, registros de auditoria e alertas automatizados quando o conteúdo da memória muda fora das operações normais. |   3   | D/V  |

---

## Referências

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

