# Controle de Acesso C5 e Identidade para Componentes e Usuários de IA

## Objetivo de Controle

O controle de acesso eficaz para sistemas de IA requer uma gestão robusta de identidade, autorização consciente do contexto e aplicação em tempo de execução seguindo os princípios de confiança zero. Esses controles garantem que humanos, serviços e agentes autônomos interajam apenas com modelos, dados e recursos computacionais dentro de escopos explicitamente concedidos, com capacidades contínuas de verificação e auditoria.

---

## C5.1 Gerenciamento de Identidade e Autenticação

Estabeleça identidades suportadas criptograficamente para todas as entidades com autenticação multifatorial para operações com privilégios.

|   #   | Description                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Verifique se todos os usuários humanos e principais de serviço autenticam-se através de um provedor de identidade empresarial centralizado (IdP) usando os protocolos OIDC/SAML com mapeamentos exclusivos de identidade para token (sem contas ou credenciais compartilhadas). |   1   | D/V  |
| 5.1.2 | Verifique se operações de alto risco (implantação de modelo, exportação de pesos, acesso a dados de treinamento, alterações na configuração de produção) exigem autenticação multifator ou autenticação escalonada com revalidação da sessão.                                   |   1   | D/V  |
| 5.1.3 | Verifique se os novos responsáveis passam por verificação de identidade alinhada com o NIST 800-63-3 IAL-2 ou normas equivalentes antes de receber acesso ao sistema de produção.                                                                                               |   2   |  D   |
| 5.1.4 | Verifique se as revisões de acesso são realizadas trimestralmente com detecção automatizada de contas inativas, aplicação da rotação de credenciais e fluxos de trabalho de desprovisionamento.                                                                                 |   2   |  V   |
| 5.1.5 | Verifique se os agentes de IA federados se autenticam por meio de asserções JWT assinadas que possuem um tempo máximo de vida útil de 24 horas e incluem prova criptográfica de origem.                                                                                         |   3   | D/V  |

---

## C5.2 Autorização de Recursos e Privilégio Mínimo

Implemente controles de acesso detalhados para todos os recursos de IA com modelos de permissão explícitos e trilhas de auditoria.

|   #   | Description                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Verifique se todos os recursos de IA (conjuntos de dados, modelos, pontos finais, coleções vetoriais, índices de incorporação, instâncias de computação) aplicam controles de acesso baseados em função com listas de permissão explícitas e políticas de negação padrão. |   1   | D/V  |
| 5.2.2 | Verifique se os princípios de menor privilégio são aplicados por padrão nas contas de serviço, começando com permissões apenas de leitura e exigindo justificativa comercial documentada para acesso de escrita.                                                          |   1   | D/V  |
| 5.2.3 | Verifique se todas as modificações no controle de acesso estão vinculadas a solicitações de alteração aprovadas e registradas de forma imutável com carimbos de data e hora, identidades dos atores, identificadores de recursos e variações de permissões.               |   1   |  V   |
| 5.2.4 | Verifique se os rótulos de classificação de dados (PII, PHI, controlados por exportação, proprietários) são automaticamente propagados para os recursos derivados (embeddings, caches de prompt, saídas de modelo) com aplicação consistente da política.                 |   2   |  D   |
| 5.2.5 | Verifique se as tentativas de acesso não autorizadas e os eventos de escalonamento de privilégios acionam alertas em tempo real com metadados contextuais para sistemas SIEM em até 5 minutos.                                                                            |   2   | D/V  |

---

## C5.3 Avaliação Dinâmica de Políticas

Implemente mecanismos de controle de acesso baseado em atributos (ABAC) para decisões de autorização conscientes do contexto, com capacidades de auditoria.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.3.1 | Verifique se as decisões de autorização são externalizadas para um motor de políticas dedicado (OPA, Cedar ou equivalente) acessível por meio de APIs autenticadas com proteção de integridade criptográfica.                              |   1   | D/V  |
| 5.3.2 | Verifique se as políticas avaliam atributos dinâmicos em tempo de execução, incluindo nível de autorização do usuário, classificação de sensibilidade do recurso, contexto da solicitação, isolamento do locatário e restrições temporais. |   1   | D/V  |
| 5.3.3 | Verifique se as definições de política são controladas por versão, revisadas por pares e validadas por meio de testes automatizados em pipelines de CI/CD antes da implantação em produção.                                                |   2   |  D   |
| 5.3.4 | Verifique se os resultados da avaliação da política incluem fundamentos estruturados para a decisão e são transmitidos para sistemas SIEM para análise de correlação e relatórios de conformidade.                                         |   2   |  V   |
| 5.3.5 | Verifique se os valores do tempo de vida (TTL) do cache de políticas não excedem 5 minutos para recursos de alta sensibilidade e 1 hora para recursos padrão com capacidades de invalidação de cache.                                      |   3   | D/V  |

---

## C5.4 Aplicação de Segurança em Tempo de Consulta

Implemente controles de segurança na camada de banco de dados com filtragem obrigatória e políticas de segurança em nível de linha.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Verifique se todas as consultas ao banco de dados vetorial e SQL incluem filtros de segurança obrigatórios (ID do locatário, rótulos de sensibilidade, escopo do usuário) aplicados no nível do mecanismo do banco de dados, não no código da aplicação. |   1   | D/V  |
| 5.4.2 | Verifique se as políticas de segurança em nível de linha (RLS) e mascaramento em nível de campo estão habilitadas com herança de políticas para todos os bancos de dados vetoriais, índices de busca e conjuntos de dados de treinamento.                |   1   | D/V  |
| 5.4.3 | Verifique se as avaliações de autorização falhadas impedirão "ataques de secretário confuso" ao abortar imediatamente as consultas e retornar códigos de erro de autorização explícitos em vez de retornar conjuntos de resultados vazios.               |   2   |  D   |
| 5.4.4 | Verifique se a latência da avaliação da política é continuamente monitorada com alertas automáticos para condições de tempo limite que possam permitir a violação de autorização.                                                                        |   2   |  V   |
| 5.4.5 | Verifique se os mecanismos de tentativa de consulta reavaliam as políticas de autorização para considerar alterações dinâmicas de permissões dentro das sessões ativas do usuário.                                                                       |   3   | D/V  |

---

## Filtragem de Saída C5.5 e Prevenção de Perda de Dados

Implemente controles de pós-processamento para evitar a exposição não autorizada de dados em conteúdo gerado por IA.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.5.1 | Verifique se os mecanismos de filtragem pós-inferência escaneiam e redigem informações pessoais identificáveis (PII) não autorizadas, informações classificadas e dados proprietários antes de entregar o conteúdo aos solicitantes. |   1   | D/V  |
| 5.5.2 | Verifique se as citações, referências e atribuições de fontes nas saídas do modelo são validadas em relação às permissões do solicitante e removidas caso seja detectado acesso não autorizado.                                      |   1   | D/V  |
| 5.5.3 | Verifique se as restrições de formato de saída (PDFs sanitizados, imagens com metadados removidos, tipos de arquivos aprovados) são aplicadas com base nos níveis de permissão do usuário e nas classificações de dados.             |   2   |  D   |
| 5.5.4 | Verifique se os algoritmos de redação são determinísticos, controlados por versões e mantêm registros de auditoria para apoiar investigações de conformidade e análise forense.                                                      |   2   |  V   |
| 5.5.5 | Verifique se os eventos de redação de alto risco geram logs adaptativos que incluem hashes criptográficos do conteúdo original para recuperação forense sem exposição dos dados.                                                     |   3   |  V   |

---

## C5.6 Isolamento Multi-Inquilino

Assegure o isolamento criptográfico e lógico entre os inquilinos em uma infraestrutura de IA compartilhada.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.6.1 | Verifique se os espaços de memória, armazenamentos de embeddings, entradas de cache e arquivos temporários são segregados por namespace para cada locatário, com limpeza segura na exclusão do locatário ou término da sessão. |   1   | D/V  |
| 5.6.2 | Verifique se toda solicitação de API inclui um identificador de locatário autenticado que é validado criptograficamente em relação ao contexto da sessão e às permissões do usuário.                                           |   1   | D/V  |
| 5.6.3 | Verifique se as políticas de rede implementam regras de negação padrão para a comunicação entre locatários em malhas de serviço e plataformas de orquestração de contêineres.                                                  |   2   |  D   |
| 5.6.4 | Verifique se as chaves de criptografia são únicas por locatário com suporte a chave gerenciada pelo cliente (CMK) e isolamento criptográfico entre os armazenamentos de dados dos locatários.                                  |   3   |  D   |

---

## C5.7 Autorização de Agente Autônomo

Controle permissões para agentes de IA e sistemas autônomos por meio de tokens de capacidade definidos e autorização contínua.

|   #   | Description                                                                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Verifique se os agentes autônomos recebem tokens de capacidade com escopo que enumeram explicitamente as ações permitidas, os recursos acessíveis, os limites de tempo e as restrições operacionais.                                                       |   1   | D/V  |
| 5.7.2 | Verifique se as capacidades de alto risco (acesso ao sistema de arquivos, execução de código, chamadas de API externas, transações financeiras) estão desativadas por padrão e exigem autorizações explícitas para ativação com justificativas comerciais. |   1   | D/V  |
| 5.7.3 | Verifique se os tokens de capacidade estão vinculados às sessões do usuário, incluem proteção criptográfica de integridade e garantam que não possam ser persistidos ou reutilizados em cenários offline.                                                  |   2   |  D   |
| 5.7.4 | Verifique se as ações iniciadas pelo agente passam por autorização secundária por meio do mecanismo de políticas ABAC com avaliação de contexto completo e registro de auditoria.                                                                          |   2   |  V   |
| 5.7.5 | Verifique se as condições de erro do agente e o tratamento de exceções incluem informações sobre o escopo de capacidade para apoiar a análise de incidentes e a investigação forense.                                                                      |   3   |  V   |

---

## Referências

### Normas e Estruturas

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Guias de Implementação

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Segurança Específica para IA

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

