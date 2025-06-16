# Governança de Dados de Treinamento C1 e Gestão de Viés

## Objetivo de Controle

Os dados de treinamento devem ser obtidos, manipulados e mantidos de maneira que preserve a proveniência, segurança, qualidade e imparcialidade. Fazer isso cumpre obrigações legais e reduz os riscos de viés, envenenamento ou violações de privacidade ao longo do ciclo de vida da IA.

---

## C1.1 Procedência dos Dados de Treinamento

Mantenha um inventário verificável de todos os conjuntos de dados, aceite apenas fontes confiáveis e registre todas as alterações para auditoria.

|   #   | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Verifique se um inventário atualizado de todas as fontes de dados de treinamento (origem, responsável/proprietário, licença, método de coleta, restrições de uso pretendido e histórico de processamento) está sendo mantido.                                                    |   1   | D/V  |
| 1.1.2 | Verifique se apenas conjuntos de dados avaliados quanto à qualidade, representatividade, origem ética e conformidade de licenciamento são permitidos, reduzindo os riscos de contaminação, viés incorporado e infração de propriedade intelectual.                               |   1   | D/V  |
| 1.1.3 | Verifique se a minimização de dados está sendo aplicada para que atributos desnecessários ou sensíveis sejam excluídos.                                                                                                                                                          |   1   | D/V  |
| 1.1.4 | Verifique se todas as alterações no conjunto de dados estão sujeitas a um fluxo de trabalho de aprovação registrado.                                                                                                                                                             |   2   | D/V  |
| 1.1.5 | Verifique se a qualidade da rotulagem/anotação é garantida por meio de verificações cruzadas dos revisores ou consenso.                                                                                                                                                          |   2   | D/V  |
| 1.1.6 | Verifique se "fichas de dados" ou "folhas de dados para conjuntos de dados" são mantidas para conjuntos de dados de treinamento significativos, detalhando características, motivações, composição, processos de coleta, pré-processamento e usos recomendados/não recomendados. |   2   | D/V  |

---

## C1.2 Segurança e Integridade dos Dados de Treinamento

Restringir o acesso, criptografar em repouso e em trânsito, e validar a integridade para impedir adulterações ou roubo.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.2.1 | Verifique se os controles de acesso protegem o armazenamento e os pipelines.                                                                                                                                                                                                                                                                           |   1   | D/V  |
| 1.2.2 | Verifique se os conjuntos de dados são criptografados durante a transmissão e, para todas as informações sensíveis ou pessoalmente identificáveis (PII), em repouso, utilizando algoritmos criptográficos padrão da indústria e práticas de gerenciamento de chaves.                                                                                   |   2   | D/V  |
| 1.2.3 | Verifique se hashes criptográficos ou assinaturas digitais são usados para garantir a integridade dos dados durante o armazenamento e a transferência, e se técnicas automatizadas de detecção de anomalias são aplicadas para proteger contra modificações não autorizadas ou corrupção, incluindo tentativas direcionadas de envenenamento de dados. |   2   | D/V  |
| 1.2.4 | Verifique se as versões do conjunto de dados são rastreadas para permitir rollback.                                                                                                                                                                                                                                                                    |   3   | D/V  |
| 1.2.5 | Verifique se os dados obsoletos são eliminados de forma segura ou anonimizados em conformidade com as políticas de retenção de dados, requisitos regulatórios e para reduzir a superfície de ataque.                                                                                                                                                   |   2   | D/V  |

---

## C1.3 Completude e Justiça da Representação

Detectar envies demográficos e aplicar mitigação para que as taxas de erro do modelo sejam equitativas entre os grupos.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Verifique se os conjuntos de dados são analisados quanto a desequilíbrios representacionais e possíveis vieses em atributos legalmente protegidos (por exemplo, raça, gênero, idade) e outras características eticamente sensíveis relevantes para o domínio de aplicação do modelo (por exemplo, status socioeconômico, localização).                                     |   1   | D/V  |
| 1.3.2 | Verifique se os vieses identificados são mitigados por meio de estratégias documentadas, como reequilíbrio, aumento de dados direcionado, ajustes algorítmicos (por exemplo, técnicas de pré-processamento, processamento durante o algoritmo, pós-processamento) ou reponderação, e avalie o impacto da mitigação tanto na equidade quanto no desempenho geral do modelo. |   2   | D/V  |
| 1.3.3 | Verifique se as métricas de justiça pós-treinamento são avaliadas e documentadas.                                                                                                                                                                                                                                                                                          |   2   | D/V  |
| 1.3.4 | Verifique se uma política de gerenciamento de viés do ciclo de vida designa responsáveis e uma cadência de revisão.                                                                                                                                                                                                                                                        |   3   | D/V  |

---

## C1.4 Qualidade, Integridade e Segurança da Rotulagem dos Dados de Treinamento

Proteja os rótulos com criptografia e exija revisão dupla para classes críticas.

|   #   | Description                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Verifique se a qualidade da rotulagem/anotação é garantida por meio de diretrizes claras, verificações cruzadas por revisores, mecanismos de consenso (por exemplo, monitoramento do acordo entre anotadores) e processos definidos para resolver discrepâncias.            |   2   | D/V  |
| 1.4.2 | Verifique se hashes criptográficos ou assinaturas digitais são aplicados aos artefatos de rótulo para garantir sua integridade e autenticidade.                                                                                                                             |   2   | D/V  |
| 1.4.3 | Verifique se as interfaces e plataformas de rotulagem aplicam controles de acesso rigorosos, mantêm registros de auditoria à prova de adulteração de todas as atividades de rotulagem e protegem contra modificações não autorizadas.                                       |   2   | D/V  |
| 1.4.4 | Verifique se os rótulos críticos para segurança, proteção ou equidade (por exemplo, identificação de conteúdo tóxico, descobertas médicas críticas) recebem revisão dupla independente obrigatória ou verificação robusta equivalente.                                      |   3   | D/V  |
| 1.4.5 | Verifique se as informações sensíveis (incluindo PII) capturadas inadvertidamente ou necessariamente presentes em etiquetas estão redigidas, pseudonimizadas, anonimizadas ou criptografadas em repouso e em trânsito, de acordo com os princípios de minimização de dados. |   2   | D/V  |
| 1.4.6 | Verifique se os guias e instruções de rotulagem são abrangentes, controlados por versão e revisados por pares.                                                                                                                                                              |   2   | D/V  |
| 1.4.7 | Verifique se os esquemas de dados (incluindo para etiquetas) estão claramente definidos e controlados por versão.                                                                                                                                                           |   2   | D/V  |
| 1.8.2 | Verifique se os fluxos de trabalho de rotulagem terceirizados ou baseados em crowdsourcing incluem salvaguardas técnicas/procedimentais para garantir a confidencialidade dos dados, integridade, qualidade dos rótulos e evitar vazamento de dados.                        |   2   | D/V  |

---

## C1.5 Garantia da Qualidade dos Dados de Treinamento

Combine validação automatizada, verificações manuais pontuais e correção registrada para garantir a confiabilidade do conjunto de dados.

|   #   | Description                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.5.1 | Verifique se os testes automatizados detectam erros de formato, valores nulos e distorções de rótulos em cada ingestão ou transformação significativa.                                                                                                                                                                            |   1   |  D   |
| 1.5.2 | Verifique se os conjuntos de dados com falha estão em quarentena com trilhas de auditoria.                                                                                                                                                                                                                                        |   1   | D/V  |
| 1.5.3 | Verifique se as verificações pontuais manuais realizadas por especialistas na área cobrem uma amostra estatisticamente significativa (por exemplo, ≥1% ou 1.000 amostras, o que for maior, ou conforme determinado pela avaliação de risco) para identificar questões sutis de qualidade que não foram detectadas pela automação. |   2   |  V   |
| 1.5.4 | Verifique se as etapas de remediação estão anexadas aos registros de procedência.                                                                                                                                                                                                                                                 |   2   | D/V  |
| 1.5.5 | Verifique se os controles de qualidade bloqueiam conjuntos de dados abaixo do padrão, a menos que exceções sejam aprovadas.                                                                                                                                                                                                       |   2   | D/V  |

---

## C1.6 Detecção de Envenenamento de Dados

Aplicar a detecção estatística de anomalias e fluxos de trabalho de quarentena para impedir inserções adversariais.

|   #   | Description                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Verifique se as técnicas de detecção de anomalias (por exemplo, métodos estatísticos, detecção de outliers, análise de embeddings) são aplicadas aos dados de treinamento na ingestão e antes das principais execuções de treinamento para identificar possíveis ataques de envenenamento ou corrupção de dados não intencional. |   2   | D/V  |
| 1.6.2 | Verifique se as amostras sinalizadas acionam uma revisão manual antes do treinamento.                                                                                                                                                                                                                                            |   2   | D/V  |
| 1.6.3 | Verifique se os resultados alimentam o dossiê de segurança do modelo e informam a inteligência contínua de ameaças.                                                                                                                                                                                                              |   2   |  V   |
| 1.6.4 | Verifique se a lógica de detecção foi atualizada com novas informações de ameaças.                                                                                                                                                                                                                                               |   3   | D/V  |
| 1.6.5 | Verifique se os pipelines de aprendizado online monitoram a deriva de distribuição.                                                                                                                                                                                                                                              |   3   | D/V  |
| 1.6.6 | Verifique se defesas específicas contra tipos conhecidos de ataques de envenenamento de dados (por exemplo, inversão de rótulos, inserção de gatilho de backdoor, ataques por instância influente) são consideradas e implementadas com base no perfil de risco do sistema e nas fontes de dados.                                |   3   | D/V  |

---

## C1.7 Exclusão de Dados do Usuário e Aplicação do Consentimento

Atenda aos pedidos de exclusão e retirada de consentimento em todos os conjuntos de dados, backups e artefatos derivados.

|   #   | Description                                                                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Verifique se os fluxos de trabalho de exclusão eliminam dados primários e derivados e avalie o impacto no modelo, assegurando que o impacto nos modelos afetados seja avaliado e, se necessário, tratado (por exemplo, por meio de re-treinamento ou recalibração).                                         |   1   | D/V  |
| 1.7.2 | Verifique se existem mecanismos para rastrear e respeitar o escopo e o status do consentimento do usuário (e retiradas) para dados usados no treinamento, e se o consentimento é validado antes que os dados sejam incorporados em novos processos de treinamento ou atualizações significativas do modelo. |   2   |  D   |
| 1.7.3 | Verifique se os fluxos de trabalho são testados anualmente e registrados.                                                                                                                                                                                                                                   |   2   |  V   |

---

## C1.8 Segurança da Cadeia de Suprimentos

Avalie os provedores externos de dados e verifique a integridade por meio de canais autenticados e criptografados.

|   #   | Description                                                                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Verifique se os fornecedores de dados de terceiros, incluindo provedores de modelos pré-treinados e conjuntos de dados externos, passam por uma análise criteriosa de segurança, privacidade, obtenção ética e qualidade dos dados antes que seus dados ou modelos sejam integrados.                                                                     |   2   | D/V  |
| 1.8.2 | Verifique se as transferências externas utilizam TLS/autenticação e verificações de integridade.                                                                                                                                                                                                                                                         |   1   |  D   |
| 1.8.3 | Verifique se fontes de dados de alto risco (por exemplo, conjuntos de dados de código aberto com proveniência desconhecida, fornecedores não avaliados) recebem escrutínio ampliado, como análise em ambiente isolado, verificações extensivas de qualidade/viés e detecção direcionada de envenenamento, antes de serem usadas em aplicações sensíveis. |   2   | D/V  |
| 1.8.4 | Verifique se os modelos pré-treinados obtidos de terceiros são avaliados quanto a vieses embutidos, possíveis backdoors, integridade de sua arquitetura e a proveniência dos dados originais de treinamento antes do ajuste fino ou implantação.                                                                                                         |   3   | D/V  |

---

## C1.9 Detecção de Amostras Adversariais

Implemente medidas durante a fase de treinamento, como treinamento adversarial, para aumentar a resiliência do modelo contra exemplos adversariais.

|   #   | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.9.1 | Verifique se defesas apropriadas, como treinamento adversarial (usando exemplos adversariais gerados), aumento de dados com entradas perturbadas ou técnicas de otimização robusta, estão implementadas e ajustadas para os modelos relevantes com base na avaliação de risco. |   3   | D/V  |
| 1.9.2 | Verifique se, caso o treinamento adversarial seja utilizado, a geração, o gerenciamento e o versionamento dos conjuntos de dados adversariais estão documentados e controlados.                                                                                                |   2   | D/V  |
| 1.9.3 | Verifique se o impacto do treinamento de robustez adversarial no desempenho do modelo (tanto contra entradas limpas quanto adversariais) e nas métricas de equidade é avaliado, documentado e monitorado.                                                                      |   3   | D/V  |
| 1.9.4 | Verifique se as estratégias para treinamento adversarial e robustez são periodicamente revisadas e atualizadas para combater as técnicas evolutivas de ataque adversarial.                                                                                                     |   3   | D/V  |

---

## C1.10 Linhagem e Rastreabilidade de Dados

Acompanhe toda a jornada de cada ponto de dados desde a fonte até a entrada do modelo para auditoria e resposta a incidentes.

|   #    | Description                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Verifique se a origem de cada ponto de dado, incluindo todas as transformações, aumentos e fusões, está registrada e pode ser reconstruída. |   2   | D/V  |
| 1.10.2 | Verifique se os registros de linhagem são imutáveis, armazenados de forma segura e acessíveis para auditorias ou investigações.             |   2   | D/V  |
| 1.10.3 | Verifique se o acompanhamento de linhagem abrange tanto dados brutos quanto dados sintéticos.                                               |   2   | D/V  |

---

## C1.11 Gestão de Dados Sintéticos

Garanta que os dados sintéticos sejam devidamente gerenciados, rotulados e avaliados quanto aos riscos.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.11.1 | Verifique se todos os dados sintéticos estão claramente rotulados e distinguíveis dos dados reais em todo o pipeline.                                                    |   2   | D/V  |
| 1.11.2 | Verifique se o processo de geração, parâmetros e uso pretendido dos dados sintéticos estão documentados.                                                                 |   2   | D/V  |
| 1.11.3 | Verifique se os dados sintéticos são avaliados quanto a riscos de viés, vazamento de privacidade e problemas de representatividade antes de serem usados no treinamento. |   2   | D/V  |

---

## C1.12 Monitoramento de Acesso a Dados e Detecção de Anomalias

Monitorar e alertar sobre acessos incomuns aos dados de treinamento para detectar ameaças internas ou exfiltração.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Verifique se todo o acesso aos dados de treinamento está registrado, incluindo usuário, horário e ação.                                                   |   2   | D/V  |
| 1.12.2 | Verifique se os logs de acesso são revisados regularmente para identificar padrões incomuns, como grandes exportações ou acesso a partir de novos locais. |   2   | D/V  |
| 1.12.3 | Verifique se os alertas são gerados para eventos de acesso suspeitos e investigados prontamente.                                                          |   2   | D/V  |

---

## C1.13 Políticas de Retenção e Expiração de Dados

Defina e aplique períodos de retenção de dados para minimizar o armazenamento desnecessário de dados.

|   #    | Description                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Verifique se períodos de retenção explícitos estão definidos para todos os conjuntos de dados de treinamento.                         |   1   | D/V  |
| 1.13.2 | Verifique se os conjuntos de dados são automaticamente expirados, excluídos ou revisados para exclusão ao final de seu ciclo de vida. |   2   | D/V  |
| 1.13.3 | Verifique se as ações de retenção e exclusão são registradas e auditáveis.                                                            |   2   | D/V  |

---

## C1.14 Conformidade Regulamentar e Jurisdicional

Garanta que todos os dados de treinamento estejam em conformidade com as leis e regulamentos aplicáveis.

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Verifique se os requisitos de residência de dados e transferência transfronteiriça são identificados e aplicados para todos os conjuntos de dados. |   2   | D/V  |
| 1.14.2 | Verifique se as regulamentações específicas do setor (por exemplo, saúde, finanças) são identificadas e tratadas no manejo dos dados.              |   2   | D/V  |
| 1.14.3 | Verifique se a conformidade com as leis de privacidade relevantes (por exemplo, GDPR, CCPA) está documentada e é revisada regularmente.            |   2   | D/V  |

---

## C1.15 Marcação de Água e Marcação Digital de Dados

Detectar reutilização não autorizada ou vazamento de dados proprietários ou sensíveis.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.15.1 | Verifique se os conjuntos de dados ou subconjuntos estão marcados com marca d'água ou possuem impressão digital quando viável. |   3   | D/V  |
| 1.15.2 | Verifique se os métodos de marca d'água/impressão digital não introduzem viés ou riscos de privacidade.                        |   3   | D/V  |
| 1.15.3 | Verifique se são realizados controles periódicos para detectar o uso não autorizado ou vazamento de dados com marca d'água.    |   3   | D/V  |

---

## C1.16 Gestão dos Direitos do Titular dos Dados

Apoiar os direitos do titular dos dados, como acesso, retificação, restrição e objeção.

|   #    | Description                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Verifique se existem mecanismos para responder a solicitações dos titulares de dados para acesso, retificação, restrição ou objeção.    |   2   | D/V  |
| 1.16.2 | Verifique se as solicitações são registradas, monitoradas e atendidas dentro dos prazos legalmente exigidos.                            |   2   | D/V  |
| 1.16.3 | Verifique se os processos relacionados aos direitos dos titulares de dados são testados e revisados regularmente quanto à sua eficácia. |   2   | D/V  |

---

## C1.17 Análise do Impacto da Versão do Conjunto de Dados

Avalie o impacto das alterações no conjunto de dados antes de atualizar ou substituir as versões.

|   #    | Description                                                                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Verifique se uma análise de impacto é realizada antes de atualizar ou substituir uma versão do conjunto de dados, abrangendo desempenho do modelo, equidade e conformidade. |   2   | D/V  |
| 1.17.2 | Verifique se os resultados da análise de impacto estão documentados e revisados pelos stakeholders relevantes.                                                              |   2   | D/V  |
| 1.17.3 | Verifique se existem planos de reversão caso novas versões introduzam riscos inaceitáveis ou regressões.                                                                    |   2   | D/V  |

---

## C1.18 Segurança da Força de Trabalho de Anotação de Dados

Garantir a segurança e integridade do pessoal envolvido na anotação de dados.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.18.1 | Verifique se todo o pessoal envolvido na anotação de dados foi submetido a verificação de antecedentes e treinado em segurança e privacidade de dados. |   2   | D/V  |
| 1.18.2 | Verifique se todo o pessoal de anotação assina acordos de confidencialidade e não divulgação.                                                          |   2   | D/V  |
| 1.18.3 | Verifique se as plataformas de anotação aplicam controles de acesso e monitoram ameaças internas.                                                      |   2   | D/V  |

---

## Referências

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

