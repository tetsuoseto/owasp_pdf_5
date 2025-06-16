# 9 Orquestração Autônoma e Ação Agencial em Segurança

## Objetivo de Controle

Garantir que sistemas de IA autônomos ou multiagentes só possam executar ações que sejam explicitamente intencionadas, autenticadas, auditáveis e dentro de limites definidos de custo e risco. Isso protege contra ameaças como Comprometimento de Sistema Autônomo, Uso Indevido de Ferramentas, Detecção de Loop de Agente, Sequestro de Comunicação, Falsificação de Identidade, Manipulação de Enxame e Manipulação de Intenção.

---

## 9.1 Orçamento de Planejamento de Tarefas de Agentes e Recursão

Controle planos recursivos e imponha pontos de verificação humanos para ações privilegiadas.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Verifique se a profundidade máxima de recursão, largura, tempo de relógio de parede, tokens e custo monetário por execução do agente estão configurados centralmente e versionados.                |   1   | D/V  |
| 9.1.2 | Verifique se ações privilegiadas ou irreversíveis (por exemplo, commits de código, transferências financeiras) exigem aprovação explícita humana por meio de um canal auditável antes da execução. |   1   | D/V  |
| 9.1.3 | Verifique se os monitores de recursos em tempo real acionam a interrupção do disjuntor quando qualquer limite de orçamento é excedido, interrompendo a expansão adicional da tarefa.               |   2   |  D   |
| 9.1.4 | Verifique se os eventos do disjuntor são registrados com o ID do agente, a condição de disparo e o estado do plano capturado para revisão forense.                                                 |   2   | D/V  |
| 9.1.5 | Verifique se os testes de segurança cobrem cenários de exaustão do orçamento e planos fora de controle, confirmando a interrupção segura sem perda de dados.                                       |   3   |  V   |
| 9.1.6 | Verifique se as políticas orçamentárias estão expressas como política-como-código e aplicadas em CI/CD para bloquear o desvio de configuração.                                                     |   3   |  D   |

---

## 9.2 Sandboxing de Plugins de Ferramentas

Isole as interações da ferramenta para evitar acesso não autorizado ao sistema ou execução de código.

|   #   | Description                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.2.1 | Verifique se toda ferramenta/plugin é executado dentro de um sistema operacional, contêiner ou sandbox em nível WASM com políticas de menor privilégio para sistema de arquivos, rede e chamadas de sistema. |   1   | D/V  |
| 9.2.2 | Verifique se as cotas de recursos do sandbox (CPU, memória, disco, saída de rede) e os tempos limite de execução estão sendo aplicados e registrados.                                                        |   1   | D/V  |
| 9.2.3 | Verifique se os binários ou descritores da ferramenta estão assinados digitalmente; as assinaturas devem ser validadas antes do carregamento.                                                                |   2   | D/V  |
| 9.2.4 | Verifique se a telemetria do sandbox é transmitida para um SIEM; anomalias (por exemplo, tentativas de conexões de saída) geram alertas.                                                                     |   2   |  V   |
| 9.2.5 | Verifique se plugins de alto risco passam por revisão de segurança e testes de penetração antes do deployment em produção.                                                                                   |   3   |  V   |
| 9.2.6 | Verifique se as tentativas de fuga do sandbox são automaticamente bloqueadas e o plugin infrator é colocado em quarentena aguardando investigação.                                                           |   3   | D/V  |

---

## 9.3 Loop Autônomo e Limitação de Custos

Detectar e interromper recursões descontroladas entre agentes e explosões de custos.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Verifique se as chamadas entre agentes incluem um limite de salto ou TTL que o tempo de execução decrementa e aplica.                                    |   1   | D/V  |
| 9.3.2 | Verifique se os agentes mantêm um ID único de grafo de invocação para identificar auto-invocações ou padrões cíclicos.                                   |   2   |  D   |
| 9.3.3 | Verifique se os contadores acumulados de unidades de computação e gastos são monitorados por cadeia de requisição; ultrapassar o limite aborta a cadeia. |   2   | D/V  |
| 9.3.4 | Verifique se a análise formal ou verificação de modelo demonstra a ausência de recursão ilimitada nos protocolos de agente.                              |   3   |  V   |
| 9.3.5 | Verifique se os eventos de interrupção de loop geram alertas e alimentam métricas de melhoria contínua.                                                  |   3   |  D   |

---

## 9.4 Proteção contra Uso Indevido em Nível de Protocolo

Canais de comunicação seguros entre agentes e sistemas externos para prevenir sequestro ou manipulação.

|   #   | Description                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Verifique se todas as mensagens de agente para ferramenta e de agente para agente estão autenticadas (por exemplo, TLS mútuo ou JWT) e criptografadas de ponta a ponta. |   1   | D/V  |
| 9.4.2 | Verifique se os esquemas são estritamente validados; campos desconhecidos ou mensagens malformadas são rejeitados.                                                      |   1   |  D   |
| 9.4.3 | Verifique se as verificações de integridade (MACs ou assinaturas digitais) cobrem toda a carga útil da mensagem, incluindo os parâmetros da ferramenta.                 |   2   | D/V  |
| 9.4.4 | Verifique se a proteção contra repetição (nonces ou janelas de carimbo de tempo) está aplicada na camada do protocolo.                                                  |   2   |  D   |
| 9.4.5 | Verifique se as implementações de protocolo passam por fuzzing e análise estática para detectar falhas de injeção ou desserialização.                                   |   3   |  V   |

---

## 9.5 Identidade do Agente e Evidência de Violação

Garanta que as ações sejam atribuíveis e as modificações detectáveis.

|   #   | Description                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Verifique se cada instância de agente possui uma identidade criptográfica única (par de chaves ou credencial baseada em hardware).                  |   1   | D/V  |
| 9.5.2 | Verifique se todas as ações do agente estão assinadas e carimbadas com data e hora; os registros incluem a assinatura para garantia de não repúdio. |   2   | D/V  |
| 9.5.3 | Verifique se os registros à prova de violação são armazenados em um meio somente para anexar ou gravar uma única vez.                               |   2   |  V   |
| 9.5.4 | Verifique se as chaves de identidade são rotacionadas em um cronograma definido e em indicadores de comprometimento.                                |   3   |  D   |
| 9.5.5 | Verifique se tentativas de falsificação ou conflito de chave ativam a quarentena imediata do agente afetado.                                        |   3   | D/V  |

---

## 9.6 Redução de Riscos em Enxames Multiagentes

Mitigue os riscos do comportamento coletivo através do isolamento e da modelagem formal de segurança.

|   #   | Description                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Verifique se os agentes que operam em diferentes domínios de segurança executam em sandbox de tempo de execução isolados ou em segmentos de rede isolados. |   1   | D/V  |
| 9.6.2 | Verifique se os comportamentos de enxame são modelados e formalmente verificados quanto à vivacidade e segurança antes da implantação.                     |   3   |  V   |
| 9.6.3 | Verifique se os monitores em tempo de execução detectam padrões emergentes de perigo (por exemplo, oscilações, bloqueios) e iniciam ações corretivas.      |   3   |  D   |

---

## 9.7 Autenticação / Autorização de Usuário e Ferramenta

Implemente controles de acesso robustos para cada ação acionada por agentes.

|   #   | Description                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Verifique se os agentes se autenticam como principais de primeira classe em sistemas downstream, nunca reutilizando credenciais do usuário final. |   1   | D/V  |
| 9.7.2 | Verifique se as políticas de autorização detalhadas restringem quais ferramentas um agente pode invocar e quais parâmetros ele pode fornecer.     |   2   |  D   |
| 9.7.3 | Verifique se as verificações de privilégios são reavaliadas a cada chamada (autorização contínua), e não apenas no início da sessão.              |   2   |  V   |
| 9.7.4 | Verifique se os privilégios delegados expiram automaticamente e exigem novo consentimento após o tempo limite ou alteração do escopo.             |   3   |  D   |

---

## 9.8 Segurança na Comunicação Agente-para-Agente

Criptografe e proteja a integridade de todas as mensagens entre agentes para impedir a interceptação e adulteração.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Verifique se a autenticação mútua e a criptografia com segredo perfeito adiante (por exemplo, TLS 1.3) são obrigatórias para os canais do agente.        |   1   | D/V  |
| 9.8.2 | Verifique se a integridade e a origem da mensagem são validadas antes do processamento; falhas geram alertas e descartam a mensagem.                     |   1   |  D   |
| 9.8.3 | Verifique se os metadados de comunicação (carimbos de data e hora, números de sequência) são registrados para suportar a reconstrução forense.           |   2   | D/V  |
| 9.8.4 | Verifique se a verificação formal ou a verificação de modelos confirma que as máquinas de estado do protocolo não podem ser levadas a estados inseguros. |   3   |  V   |

---

## 9.9 Verificação de Intenção e Aplicação de Restrições

Validar que as ações do agente estejam alinhadas com a intenção declarada pelo usuário e as restrições do sistema.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Verifique se os solucionadores de restrições de pré-execução conferem as ações propostas em relação às regras rígidas de segurança e políticas codificadas.                                              |   1   |  D   |
| 9.9.2 | Verifique se ações de alto impacto (financeiras, destrutivas, sensíveis à privacidade) exigem confirmação explícita de intenção do usuário que as inicia.                                                |   2   | D/V  |
| 9.9.3 | Verifique se as verificações pós-condição validam que as ações concluídas alcançaram os efeitos pretendidos sem efeitos colaterais; discrepâncias acionam o rollback.                                    |   2   |  V   |
| 9.9.4 | Verifique se métodos formais (por exemplo, verificação de modelos, prova de teoremas) ou testes baseados em propriedades demonstram que os planos dos agentes satisfazem todas as restrições declaradas. |   3   |  V   |
| 9.9.5 | Verifique se incidentes de incompatibilidade de intenção ou violação de restrições alimentam ciclos de melhoria contínua e compartilhamento de inteligência sobre ameaças.                               |   3   |  D   |

---

## 9.10 Estratégia de Raciocínio do Agente para Segurança

Seleção e execução segura de diferentes estratégias de raciocínio, incluindo as abordagens ReAct, Chain-of-Thought e Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                                                    | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Verifique se a seleção da estratégia de raciocínio utiliza critérios determinísticos (complexidade da entrada, tipo de tarefa, contexto de segurança) e se entradas idênticas produzem seleções de estratégia idênticas dentro do mesmo contexto de segurança. |   1   | D/V  |
| 9.10.2 | Verifique se cada estratégia de raciocínio (ReAct, Chain-of-Thought, Tree-of-Thoughts) possui validação de entrada dedicada, sanitização de saída e limites de tempo de execução específicos para sua abordagem cognitiva.                                     |   1   | D/V  |
| 9.10.3 | Verifique se as transições da estratégia de raciocínio são registradas com contexto completo, incluindo características da entrada, valores dos critérios de seleção e metadados de execução para reconstrução da trilha de auditoria.                         |   2   | D/V  |
| 9.10.4 | Verifique se o raciocínio Tree-of-Thoughts inclui mecanismos de poda de ramificações que encerram a exploração quando são detectadas violações de políticas, limites de recursos ou limites de segurança.                                                      |   2   | D/V  |
| 9.10.5 | Verifique se os ciclos ReAct (Raciocínio-Ação-Observação) incluem pontos de verificação de validação em cada fase: verificação do passo de raciocínio, autorização da ação e higienização da observação antes de prosseguir.                                   |   2   | D/V  |
| 9.10.6 | Verifique se as métricas de desempenho da estratégia de raciocínio (tempo de execução, uso de recursos, qualidade da saída) são monitoradas com alertas automáticos quando as métricas se desviam além dos limites configurados.                               |   3   | D/V  |
| 9.10.7 | Verifique se as abordagens de raciocínio híbrido que combinam múltiplas estratégias mantêm a validação de entrada e as restrições de saída de todas as estratégias constituintes sem contornar quaisquer controles de segurança.                               |   3   | D/V  |
| 9.10.8 | Verifique se o teste de segurança da estratégia de raciocínio inclui fuzzing com entradas malformadas, prompts adversariais projetados para forçar a troca de estratégia e testes de condições de limite para cada abordagem cognitiva.                        |   3   | D/V  |

---

## 9.11 Gerenciamento do Ciclo de Vida do Estado do Agente e Segurança

Inicialização segura do agente, transições de estado e finalização com trilhas de auditoria criptográficas e procedimentos de recuperação definidos.

|   #    | Description                                                                                                                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Verifique se a inicialização do agente inclui o estabelecimento de identidade criptográfica com credenciais baseadas em hardware e registros imutáveis de auditoria de inicialização contendo ID do agente, carimbo de data/hora, hash de configuração e parâmetros de inicialização. |   1   | D/V  |
| 9.11.2 | Verifique se as transições de estado do agente estão assinadas criptograficamente, com carimbo de data e hora, e registradas com contexto completo, incluindo eventos desencadeadores, hash do estado anterior, hash do novo estado e validações de segurança realizadas.             |   2   | D/V  |
| 9.11.3 | Verifique se os procedimentos de desligamento do agente incluem a limpeza segura da memória usando apagamento criptográfico ou sobrescrição múltipla, revogação de credenciais com notificação à autoridade certificadora e geração de certificados de término à prova de violação.   |   2   | D/V  |
| 9.11.4 | Verifique se os mecanismos de recuperação do agente validam a integridade do estado usando somas de verificação criptográficas (mínimo SHA-256) e retornam a estados conhecidos como bons quando a corrupção é detectada, com alertas automatizados e requisitos de aprovação manual. |   3   | D/V  |
| 9.11.5 | Verifique se os mecanismos de persistência do agente criptografam os dados de estado sensíveis com chaves AES-256 exclusivas por agente e implementam a rotação segura de chaves em cronogramas configuráveis (máximo de 90 dias) com implantação sem tempo de inatividade.           |   3   | D/V  |

---

## 9.12 Estrutura de Segurança para Integração de Ferramentas

Controles de segurança para carregamento dinâmico de ferramentas, execução e validação de resultados com processos definidos de avaliação de risco e aprovação.

|   #    | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Verifique se os descritores da ferramenta incluem metadados de segurança especificando privilégios necessários (leitura/gravação/execução), níveis de risco (baixo/médio/alto), limites de recursos (CPU, memória, rede) e requisitos de validação documentados nos manifestos da ferramenta. |   1   | D/V  |
| 9.12.2 | Verifique se os resultados da execução da ferramenta são validados contra esquemas esperados (JSON Schema, XML Schema) e políticas de segurança (sanitização de saída, classificação de dados) antes da integração, com limites de tempo e procedimentos de tratamento de erros.              |   1   | D/V  |
| 9.12.3 | Verifique se os registros de interação das ferramentas incluem contexto detalhado de segurança, incluindo uso de privilégios, padrões de acesso a dados, tempo de execução, consumo de recursos e códigos de retorno, com registro estruturado para integração com SIEM.                      |   2   | D/V  |
| 9.12.4 | Verifique se os mecanismos de carregamento dinâmico de ferramentas validam assinaturas digitais utilizando infraestrutura PKI e implementam protocolos seguros de carregamento com isolamento em sandbox e verificação de permissões antes da execução.                                       |   2   | D/V  |
| 9.12.5 | Verifique se as avaliações de segurança das ferramentas são acionadas automaticamente para novas versões com etapas obrigatórias de aprovação, incluindo análise estática, testes dinâmicos e revisão pela equipe de segurança, com critérios de aprovação documentados e requisitos de SLA.  |   3   | D/V  |

---

### Referências

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)

