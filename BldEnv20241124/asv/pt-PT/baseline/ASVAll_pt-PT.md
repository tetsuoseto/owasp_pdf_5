## Frontispício

### Sobre o Padrão

O Padrão de Verificação de Segurança em Inteligência Artificial (AISVS) é um catálogo orientado pela comunidade de requisitos de segurança que cientistas de dados, engenheiros de MLOps, arquitetos de software, desenvolvedores, testadores, profissionais de segurança, fornecedores de ferramentas, reguladores e consumidores podem utilizar para projetar, construir, testar e verificar sistemas e aplicações confiáveis habilitados por IA. Ele fornece uma linguagem comum para especificar controles de segurança ao longo do ciclo de vida da IA — desde a coleta de dados e o desenvolvimento de modelos até a implantação e o monitoramento contínuo — para que as organizações possam medir e melhorar a resiliência, a privacidade e a segurança de suas soluções de IA.

### Direitos Autorais e Licença

Versão 0.1 (Primeiro Rascunho Público - Trabalho em Andamento), 2025  

![license](images/license.png)
Direitos autorais © 2025 O Projeto AISVS.  

Lançado sob aCreative Commons Attribution‑ShareAlike 4.0 International License.
Para qualquer reutilização ou distribuição, você deve comunicar claramente os termos de licença deste trabalho para os outros.

### Líderes de Projeto

Jim Manico
Aras “Russ” Memisyazici

### Contribuidores e Revisores

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS é um novo padrão criado especificamente para enfrentar os desafios únicos de segurança dos sistemas de inteligência artificial. Embora se baseie em melhores práticas gerais de segurança, cada requisito do AISVS foi desenvolvido do zero para refletir o panorama de ameaças da IA e ajudar as organizações a construir soluções de IA mais seguras e resilientes.

## Prefácio

Bem-vindo ao Padrão de Verificação de Segurança em Inteligência Artificial (AISVS) versão 1.0!

### Introdução

Estabelecida em 2025 através de um esforço colaborativo da comunidade, a AISVS define os requisitos de segurança a serem considerados ao projetar, desenvolver, implantar e operar modelos modernos de IA, pipelines e serviços habilitados por IA.

AISVS v1.0 representa o trabalho combinado de seus líderes de projeto, grupo de trabalho e colaboradores da comunidade mais ampla para produzir uma base prática e testável para a segurança de sistemas de IA.

Nosso objetivo com este lançamento é tornar o AISVS fácil de adotar, mantendo o foco rigoroso em seu escopo definido e abordando o cenário de riscos em rápida evolução, único para IA.

### Principais Objetivos para a Versão 1.0 do AISVS

A versão 1.0 será criada com vários princípios orientadores.

#### Escopo Bem Definido

Cada requisito deve estar alinhado com o nome e a missão da AISVS:

Inteligência Artificial – Os controles operam na camada de IA/ML (dados, modelo, pipeline ou inferência) e são de responsabilidade dos profissionais de IA.
Segurança – Os requisitos mitigam diretamente os riscos identificados de segurança, privacidade ou segurança operacional.
Verificação – A linguagem é escrita para que a conformidade possa ser validada objetivamente.
Padrão – As seções seguem uma estrutura e terminologia consistentes para formar uma referência coerente.
​
---

Seguindo o AISVS, as organizações podem avaliar e fortalecer sistematicamente a postura de segurança de suas soluções de IA, promovendo uma cultura de engenharia de IA segura.

## Usando o AISVS

O Padrão de Verificação de Segurança em Inteligência Artificial (AISVS) define requisitos de segurança para aplicações e serviços modernos de IA, concentrando-se em aspectos sob o controle dos desenvolvedores de aplicações.

O AISVS é destinado a qualquer pessoa que desenvolva ou avalie a segurança de aplicações de IA, incluindo desenvolvedores, arquitetos, engenheiros de segurança e auditores. Este capítulo apresenta a estrutura e o uso do AISVS, incluindo seus níveis de verificação e casos de uso previstos.

### Níveis de Verificação de Segurança em Inteligência Artificial

O AISVS define três níveis crescentes de verificação de segurança. Cada nível adiciona profundidade e complexidade, permitindo que as organizações ajustem sua postura de segurança ao nível de risco de seus sistemas de IA.

As organizações podem começar no Nível 1 e progressivamente adotar níveis mais altos à medida que a maturidade de segurança e a exposição a ameaças aumentam.

#### Definição dos Níveis

Cada requisito na AISVS v1.0 é atribuído a um dos seguintes níveis:

 Requisitos de Nível 1

O Nível 1 inclui os requisitos de segurança mais críticos e fundamentais. Eles se concentram em prevenir ataques comuns que não dependem de outras pré-condições ou vulnerabilidades. A maioria dos controles do Nível 1 é simples de implementar ou essencial o suficiente para justificar o esforço.

 Requisitos de Nível 2

O Nível 2 aborda ataques mais avançados ou menos comuns, assim como defesas em camadas contra ameaças generalizadas. Esses requisitos podem envolver lógica mais complexa ou visar pré-requisitos específicos do ataque.

 Requisitos de Nível 3

O Nível 3 inclui controles que geralmente são mais difíceis de implementar ou têm aplicabilidade situacional. Estes frequentemente representam mecanismos de defesa em profundidade ou mitigações contra ataques de nicho, direcionados ou de alta complexidade.

#### Função (D/V)

Cada requisito do AISVS é marcado de acordo com o público-alvo principal:

D – Requisitos focados no desenvolvedor
V – Requisitos focados no verificador/auditor
D/V – Relevante tanto para desenvolvedores quanto para verificadores

## Governança de Dados de Treinamento C1 e Gestão de Viés

### Objetivo de Controle

Os dados de treinamento devem ser obtidos, manuseados e mantidos de forma a preservar a proveniência, segurança, qualidade e equidade. Fazer isso cumpre obrigações legais e reduz os riscos de viés, contaminação ou violações de privacidade ao longo do ciclo de vida da IA.

---

### C1.1 Procedência dos Dados de Treinamento

Mantenha um inventário verificável de todos os conjuntos de dados, aceite apenas fontes confiáveis e registre cada alteração para auditoria.

 #1.1.1    Level: 1    Role: D/V
 Verifique se um inventário atualizado de cada fonte de dados de treinamento (origem, responsável/proprietário, licença, método de coleta, restrições de uso pretendido e histórico de processamento) é mantido.
 #1.1.2    Level: 1    Role: D/V
 Verifique se apenas conjuntos de dados avaliados quanto à qualidade, representatividade, origem ética e conformidade com licenças são permitidos, reduzindo os riscos de envenenamento, viés incorporado e violação de propriedade intelectual.
 #1.1.3    Level: 1    Role: D/V
 Verifique se a minimização de dados está sendo aplicada para que atributos desnecessários ou sensíveis sejam excluídos.
 #1.1.4    Level: 2    Role: D/V
 Verifique se todas as alterações no conjunto de dados estão sujeitas a um fluxo de aprovação registrado.
 #1.1.5    Level: 2    Role: D/V
 Verifique se a qualidade da rotulagem/anotação é garantida por meio de verificações cruzadas dos revisores ou consenso.
 #1.1.6    Level: 2    Role: D/V
 Verifique se "cartões de dados" ou "fichas técnicas para conjuntos de dados" são mantidos para conjuntos de dados de treinamento significativos, detalhando características, motivações, composição, processos de coleta, pré-processamento e usos recomendados/desencorajados.

---

### C1.2 Segurança e Integridade dos Dados de Treinamento

Restrinja o acesso, criptografe os dados em repouso e em trânsito, e valide a integridade para impedir adulterações ou roubos.

 #1.2.1    Level: 1    Role: D/V
 Verifique se os controles de acesso protegem o armazenamento e os pipelines.
 #1.2.2    Level: 2    Role: D/V
 Verifique se os conjuntos de dados estão criptografados em trânsito e, para todas as informações sensíveis ou pessoalmente identificáveis (PII), em repouso, usando algoritmos criptográficos padrão do setor e práticas de gerenciamento de chaves.
 #1.2.3    Level: 2    Role: D/V
 Verifique se hashes criptográficos ou assinaturas digitais são usados para garantir a integridade dos dados durante o armazenamento e a transferência, e se técnicas automatizadas de detecção de anomalias são aplicadas para proteger contra modificações não autorizadas ou corrupção, incluindo tentativas direcionadas de envenenamento de dados.
 #1.2.4    Level: 3    Role: D/V
 Verifique se as versões dos conjuntos de dados estão rastreadas para permitir reversão.
 #1.2.5    Level: 2    Role: D/V
 Verifique se os dados obsoletos são eliminados com segurança ou anonimizados em conformidade com as políticas de retenção de dados, requisitos regulatórios e para reduzir a superfície de ataque.

---

### C1.3 Completude e Justiça na Representação

Detectar distorções demográficas e aplicar mitigação para que as taxas de erro do modelo sejam equitativas entre os grupos.

 #1.3.1    Level: 1    Role: D/V
 Verifique se os conjuntos de dados são analisados quanto a desequilíbrios representacionais e potenciais vieses em atributos legalmente protegidos (por exemplo, raça, gênero, idade) e outras características eticamente sensíveis relevantes para o domínio de aplicação do modelo (por exemplo, status socioeconômico, localização).
 #1.3.2    Level: 2    Role: D/V
 Verifique se os vieses identificados são mitigados por meio de estratégias documentadas, como reequilíbrio, aumento de dados direcionado, ajustes algorítmicos (por exemplo, técnicas de pré-processamento, processamento e pós-processamento) ou reponderação, e avalie o impacto da mitigação tanto na equidade quanto no desempenho geral do modelo.
 #1.3.3    Level: 2    Role: D/V
 Verifique se as métricas de equidade pós-treinamento são avaliadas e documentadas.
 #1.3.4    Level: 3    Role: D/V
 Verifique se uma política de gerenciamento de viés ao longo do ciclo de vida atribui responsáveis e um ritmo de revisão.

---

### C1.4 Qualidade, Integridade e Segurança da Rotulagem de Dados de Treinamento

Proteja os rótulos com criptografia e exija revisão dupla para classes críticas.

 #1.4.1    Level: 2    Role: D/V
 Verifique se a qualidade da rotulagem/anotação é garantida por meio de diretrizes claras, verificações cruzadas por revisores, mecanismos de consenso (por exemplo, monitoramento do acordo entre anotadores) e processos definidos para resolução de discrepâncias.
 #1.4.2    Level: 2    Role: D/V
 Verifique se hashes criptográficos ou assinaturas digitais são aplicados aos artefatos de rótulo para garantir sua integridade e autenticidade.
 #1.4.3    Level: 2    Role: D/V
 Verifique se as interfaces e plataformas de rotulagem aplicam controles de acesso rigorosos, mantêm registros de auditoria invioláveis de todas as atividades de rotulagem e protegem contra modificações não autorizadas.
 #1.4.4    Level: 3    Role: D/V
 Verifique se os rótulos críticos para segurança, proteção ou equidade (por exemplo, identificação de conteúdo tóxico, achados médicos críticos) recebem revisão dupla independente obrigatória ou verificação robusta equivalente.
 #1.4.5    Level: 2    Role: D/V
 Verifique se as informações sensíveis (incluindo Dados Pessoais Identificáveis - DPI) capturadas inadvertidamente ou necessariamente presentes em etiquetas são editadas, pseudonimizadas, anonimizadas ou criptografadas em repouso e em trânsito, de acordo com os princípios de minimização de dados.
 #1.4.6    Level: 2    Role: D/V
 Verifique se os guias de rotulagem e instruções são abrangentes, controlados por versão e revisados por pares.
 #1.4.7    Level: 2    Role: D/V
 Verifique se os esquemas de dados (incluindo para rótulos) estão claramente definidos e controlados por versão.
 #1.8.2    Level: 2    Role: D/V
 Verifique se os fluxos de trabalho de rotulagem terceirizados ou colaborativos incluem salvaguardas técnicas/procedimentais para garantir a confidencialidade dos dados, integridade, qualidade dos rótulos e prevenir o vazamento de dados.

---

### C1.5 Garantia da Qualidade dos Dados de Treinamento

Combine validação automatizada, verificações manuais pontuais e remediação registrada para garantir a confiabilidade do conjunto de dados.

 #1.5.1    Level: 1    Role: D
 Verifique se os testes automatizados detectam erros de formato, valores nulos e deslocamentos de rótulos em toda ingestão ou transformação significativa.
 #1.5.2    Level: 1    Role: D/V
 Verifique se os conjuntos de dados com falha estão em quarentena com trilhas de auditoria.
 #1.5.3    Level: 2    Role: V
 Verifique se as verificações manuais por especialistas na área abrangem uma amostra estatisticamente significativa (por exemplo, ≥1% ou 1.000 amostras, o que for maior, ou conforme determinado pela avaliação de risco) para identificar problemas sutis de qualidade não detectados pela automação.
 #1.5.4    Level: 2    Role: D/V
 Verifique se as etapas de remediação estão anexadas aos registros de proveniência.
 #1.5.5    Level: 2    Role: D/V
 Verifique se os gates de qualidade bloqueiam conjuntos de dados de qualidade inferior, a menos que exceções sejam aprovadas.

---

### C1.6 Detecção de Envenenamento de Dados

Aplique detecção estatística de anomalias e fluxos de trabalho de quarentena para interromper inserções adversariais.

 #1.6.1    Level: 2    Role: D/V
 Verifique se técnicas de detecção de anomalias (por exemplo, métodos estatísticos, detecção de outliers, análise de embeddings) são aplicadas aos dados de treinamento na ingestão e antes das principais execuções de treinamento para identificar possíveis ataques de envenenamento ou corrupção não intencional dos dados.
 #1.6.2    Level: 2    Role: D/V
 Verifique se as amostras sinalizadas acionam a revisão manual antes do treinamento.
 #1.6.3    Level: 2    Role: V
 Verifique se os resultados alimentam o dossiê de segurança do modelo e informam a inteligência contínua de ameaças.
 #1.6.4    Level: 3    Role: D/V
 Verifique se a lógica de detecção é atualizada com novas informações de ameaça.
 #1.6.5    Level: 3    Role: D/V
 Verifique se os pipelines de aprendizado online monitoram a deriva na distribuição.
 #1.6.6    Level: 3    Role: D/V
 Verifique se defesas específicas contra tipos conhecidos de ataques de envenenamento de dados (por exemplo, inversão de rótulos, inserção de gatilho de porta dos fundos, ataques de instância influente) são consideradas e implementadas com base no perfil de risco do sistema e nas fontes de dados.

---

### C1.7 Exclusão de Dados do Usuário e Aplicação do Consentimento

Respeite as solicitações de exclusão e retirada de consentimento em todos os conjuntos de dados, backups e artefatos derivados.

 #1.7.1    Level: 1    Role: D/V
 Verifique se os fluxos de trabalho de exclusão removem dados primários e derivados e avalie o impacto no modelo, certificando-se de que o impacto nos modelos afetados seja avaliado e, se necessário, tratado (por exemplo, através de re-treinamento ou recalibração).
 #1.7.2    Level: 2    Role: D
 Verifique se existem mecanismos para rastrear e respeitar o escopo e o status do consentimento do usuário (e retiradas) para os dados usados no treinamento, e se o consentimento é validado antes que os dados sejam incorporados em novos processos de treinamento ou atualizações significativas do modelo.
 #1.7.3    Level: 2    Role: V
 Verifique se os fluxos de trabalho são testados anualmente e registrados.

---

### C1.8 Segurança da Cadeia de Suprimentos

Verifique os provedores externos de dados e confirme a integridade por meio de canais autenticados e criptografados.

 #1.8.1    Level: 2    Role: D/V
 Verifique se os fornecedores de dados de terceiros, incluindo provedores de modelos pré-treinados e conjuntos de dados externos, passam por uma due diligence de segurança, privacidade, origem ética e qualidade dos dados antes que seus dados ou modelos sejam integrados.
 #1.8.2    Level: 1    Role: D
 Verifique se as transferências externas utilizam TLS/autenticação e verificações de integridade.
 #1.8.3    Level: 2    Role: D/V
 Verifique se as fontes de dados de alto risco (por exemplo, conjuntos de dados de código aberto com procedência desconhecida, fornecedores não verificados) recebem uma análise aprimorada, como análise em sandbox, verificações extensivas de qualidade/viés e detecção direcionada de envenenamento, antes de serem usadas em aplicações sensíveis.
 #1.8.4    Level: 3    Role: D/V
 Verifique se os modelos pré-treinados obtidos de terceiros são avaliados quanto a vieses embutidos, possíveis portas dos fundos, integridade de sua arquitetura e a proveniência dos dados originais de treinamento antes do ajuste fino ou da implantação.

---

### C1.9 Detecção de Amostras Adversariais

Implemente medidas durante a fase de treinamento, como treinamento adversarial, para aprimorar a resiliência do modelo contra exemplos adversariais.

 #1.9.1    Level: 3    Role: D/V
 Verifique se são implementadas e ajustadas defesas apropriadas, como treinamento adversarial (usando exemplos adversariais gerados), aumento de dados com entradas perturbadas ou técnicas de otimização robusta, para os modelos relevantes com base na avaliação de risco.
 #1.9.2    Level: 2    Role: D/V
 Verifique se, ao utilizar treinamento adversarial, a geração, gestão e versionamento dos conjuntos de dados adversariais estão documentados e controlados.
 #1.9.3    Level: 3    Role: D/V
 Verifique se o impacto do treinamento de robustez a adversários no desempenho do modelo (tanto contra entradas limpas quanto adversárias) e nas métricas de equidade é avaliado, documentado e monitorado.
 #1.9.4    Level: 3    Role: D/V
 Verifique se as estratégias para treinamento adversarial e robustez são periodicamente revisadas e atualizadas para combater técnicas evolutivas de ataque adversarial.

---

### C1.10 Linhagem e Rastreabilidade de Dados

Acompanhe toda a jornada de cada ponto de dados desde a origem até a entrada no modelo para auditoria e resposta a incidentes.

 #1.10.1    Level: 2    Role: D/V
 Verifique se a linhagem de cada ponto de dados, incluindo todas as transformações, ampliações e fusões, está registrada e pode ser reconstruída.
 #1.10.2    Level: 2    Role: D/V
 Verifique se os registros de linhagem são imutáveis, armazenados com segurança e acessíveis para auditorias ou investigações.
 #1.10.3    Level: 2    Role: D/V
 Verifique se o rastreamento de linhagem cobre tanto dados brutos quanto dados sintéticos.

---

### C1.11 Gerenciamento de Dados Sintéticos

Garanta que os dados sintéticos sejam devidamente gerenciados, rotulados e avaliados quanto aos riscos.

 #1.11.1    Level: 2    Role: D/V
 Verifique se todos os dados sintéticos estão claramente rotulados e distinguíveis dos dados reais ao longo de todo o pipeline.
 #1.11.2    Level: 2    Role: D/V
 Verifique se o processo de geração, os parâmetros e o uso previsto dos dados sintéticos estão documentados.
 #1.11.3    Level: 2    Role: D/V
 Verifique se os dados sintéticos foram avaliados quanto ao risco de viés, vazamento de privacidade e problemas de representatividade antes de serem usados no treinamento.

---

### C1.12 Monitoramento de Acesso a Dados e Detecção de Anomalias

Monitorar e alertar sobre acessos incomuns aos dados de treinamento para detectar ameaças internas ou exfiltração.

 #1.12.1    Level: 2    Role: D/V
 Verifique se todo o acesso aos dados de treinamento está registrado, incluindo usuário, hora e ação.
 #1.12.2    Level: 2    Role: D/V
 Verifique se os registros de acesso são regularmente revisados para identificar padrões incomuns, como grandes exportações ou acessos de locais novos.
 #1.12.3    Level: 2    Role: D/V
 Verifique se os alertas são gerados para eventos de acesso suspeitos e investigados prontamente.

---

### C1.13 Políticas de Retenção e Expiração de Dados

Defina e aplique períodos de retenção de dados para minimizar o armazenamento desnecessário de dados.

 #1.13.1    Level: 1    Role: D/V
 Verifique se períodos explícitos de retenção estão definidos para todos os conjuntos de dados de treinamento.
 #1.13.2    Level: 2    Role: D/V
 Verifique se os conjuntos de dados são automaticamente expirados, excluídos ou revisados para exclusão ao final do seu ciclo de vida.
 #1.13.3    Level: 2    Role: D/V
 Verifique se as ações de retenção e exclusão são registradas e auditáveis.

---

### C1.14 Conformidade Regulatória e Jurisdicional

Garantir que todos os dados de treinamento estejam em conformidade com as leis e regulamentos aplicáveis.

 #1.14.1    Level: 2    Role: D/V
 Verifique se os requisitos de residência de dados e transferência transfronteiriça são identificados e aplicados para todos os conjuntos de dados.
 #1.14.2    Level: 2    Role: D/V
 Verifique se as regulamentações específicas do setor (por exemplo, saúde, finanças) são identificadas e tratadas na manipulação de dados.
 #1.14.3    Level: 2    Role: D/V
 Verifique se a conformidade com as leis de privacidade relevantes (por exemplo, GDPR, CCPA) está documentada e revisada regularmente.

---

### C1.15 Marcação d'água e Impressão Digital de Dados

Detectar reutilização não autorizada ou vazamento de dados proprietários ou sensíveis.

 #1.15.1    Level: 3    Role: D/V
 Verifique se os conjuntos de dados ou subconjuntos estão marcados com marca d'água ou digitais onde for viável.
 #1.15.2    Level: 3    Role: D/V
 Verifique se os métodos de marca d'água/impressão digital não introduzem viés ou riscos de privacidade.
 #1.15.3    Level: 3    Role: D/V
 Verifique se são realizadas verificações periódicas para detectar o uso não autorizado ou o vazamento de dados com marca d’água.

---

### C1.16 Gestão dos Direitos do Titular dos Dados

Suportar os direitos do titular dos dados, como acesso, retificação, restrição e objeção.

 #1.16.1    Level: 2    Role: D/V
 Verifique se existem mecanismos para responder a solicitações dos titulares dos dados para acesso, retificação, restrição ou objeção.
 #1.16.2    Level: 2    Role: D/V
 Verifique se as solicitações são registradas, acompanhadas e atendidas dentro dos prazos legalmente exigidos.
 #1.16.3    Level: 2    Role: D/V
 Verifique se os processos dos direitos dos titulares de dados são testados e revisados regularmente para garantir sua eficácia.

---

### C1.17 Análise do Impacto da Versão do Conjunto de Dados

Avalie o impacto das alterações no conjunto de dados antes de atualizar ou substituir as versões.

 #1.17.1    Level: 2    Role: D/V
 Verifique se uma análise de impacto é realizada antes de atualizar ou substituir uma versão do conjunto de dados, abrangendo desempenho do modelo, equidade e conformidade.
 #1.17.2    Level: 2    Role: D/V
 Verifique se os resultados da análise de impacto estão documentados e revisados pelas partes interessadas relevantes.
 #1.17.3    Level: 2    Role: D/V
 Verifique se existem planos de reversão caso novas versões introduzam riscos inaceitáveis ou regressões.

---

### C1.18 Segurança da Força de Trabalho para Anotação de Dados

Garantir a segurança e integridade do pessoal envolvido na anotação de dados.

 #1.18.1    Level: 2    Role: D/V
 Verifique se todo o pessoal envolvido na anotação de dados passou por verificação de antecedentes e foi treinado em segurança e privacidade de dados.
 #1.18.2    Level: 2    Role: D/V
 Verifique se todo o pessoal de anotação assina acordos de confidencialidade e não divulgação.
 #1.18.3    Level: 2    Role: D/V
 Verifique se as plataformas de anotação aplicam controles de acesso e monitoram ameaças internas.

---

### Referências

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Validação de Entrada do Usuário C2

### Objetivo de Controle

A validação robusta da entrada do usuário é uma defesa de primeira linha contra alguns dos ataques mais prejudiciais a sistemas de IA. Ataques de injeção de prompt podem substituir as instruções do sistema, vazar dados sensíveis ou direcionar o modelo para um comportamento não permitido. A menos que filtros dedicados e hierarquias de instruções estejam implementados, pesquisas mostram que "jailbreaks multi-shot" que exploram janelas de contexto muito longas serão eficazes. Além disso, ataques sutis de perturbação adversária — como trocas de homoglifos ou leetspeak — podem mudar silenciosamente as decisões de um modelo.

---

### C2.1 Defesa contra Injeção de Prompt

A injeção de prompt é um dos principais riscos para sistemas de IA. Defesas contra essa tática utilizam uma combinação de filtros de padrão estáticos, classificadores dinâmicos e aplicação hierárquica de instruções.

 #2.1.1    Level: 1    Role: D/V
 Verifique se as entradas do usuário são filtradas contra uma biblioteca continuamente atualizada de padrões conhecidos de injeção de prompt (palavras-chave de jailbreak, "ignorar anterior", cadeias de interpretação de papéis, ataques indiretos por HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Verifique se o sistema aplica uma hierarquia de instruções na qual mensagens do sistema ou do desenvolvedor têm prioridade sobre as instruções do usuário, mesmo após a expansão da janela de contexto.
 #2.1.3    Level: 2    Role: D/V
 Verifique se os testes de avaliação adversarial (por exemplo, prompts "many-shot" da Equipe Vermelha) são realizados antes de cada lançamento de modelo ou template de prompt, com limites de taxa de sucesso e bloqueadores automáticos para regressões.
 #2.1.4    Level: 2    Role: D
 Verifique se os prompts originados de conteúdo de terceiros (páginas da web, PDFs, e-mails) são sanitizados em um contexto de análise isolado antes de serem concatenados ao prompt principal.
 #2.1.5    Level: 3    Role: D/V
 Verifique se todas as atualizações das regras de filtro de prompt, versões dos modelos classificadores e alterações na lista de bloqueio são controladas por versão e auditáveis.

---

### C2.2 Resistência a Exemplos Adversariais

Modelos de Processamento de Linguagem Natural (PLN) ainda são vulneráveis a perturbações sutis em nível de caractere ou palavra que os humanos frequentemente não percebem, mas que os modelos tendem a classificar incorretamente.

 #2.2.1    Level: 1    Role: D
 Verifique se as etapas básicas de normalização de entrada (Unicode NFC, mapeamento de homógrafos, remoção de espaços em branco) são executadas antes da tokenização.
 #2.2.2    Level: 2    Role: D/V
 Verifique se a detecção estatística de anomalias sinaliza entradas com distância de edição incomumente alta em relação às normas linguísticas, tokens repetidos excessivamente ou distâncias anormais de embedding.
 #2.2.3    Level: 2    Role: D
 Verifique se o pipeline de inferência suporta variantes opcionais de modelos fortalecidos por treinamento adversarial ou camadas de defesa (por exemplo, randomização, destilação defensiva) para pontos finais de alto risco.
 #2.2.4    Level: 2    Role: V
 Verifique se as entradas adversariais suspeitas são colocadas em quarentena, registradas com cargas completas (após a redação de PII).
 #2.2.5    Level: 3    Role: D/V
 Verifique se as métricas de robustez (taxa de sucesso de conjuntos de ataques conhecidos) são acompanhadas ao longo do tempo e se regressões acionam um bloqueador de lançamento.

---

### C2.3 Validação de Esquema, Tipo e Comprimento

Ataques de IA com entradas malformadas ou superdimensionadas podem causar erros de análise, vazamento de informações entre campos e esgotamento de recursos. A aplicação rigorosa de esquemas também é um pré-requisito ao realizar chamadas determinísticas de ferramentas.

 #2.3.1    Level: 1    Role: D
 Verifique se todo endpoint de API ou chamada de função define um esquema de entrada explícito (JSON Schema, Protobuf ou equivalente multimodal) e se as entradas são validadas antes da montagem do prompt.
 #2.3.2    Level: 1    Role: D/V
 Verifique se as entradas que excedem os limites máximos de tokens ou bytes são rejeitadas com um erro seguro e nunca truncadas silenciosamente.
 #2.3.3    Level: 2    Role: D/V
 Verifique se as validações de tipo (por exemplo, intervalos numéricos, valores de enumeração, tipos MIME para imagens/áudio) são aplicadas no servidor, não apenas no código cliente.
 #2.3.4    Level: 2    Role: D
 Verifique se os validadores semânticos (por exemplo, JSON Schema) são executados em tempo constante para evitar DoS algorítmico.
 #2.3.5    Level: 3    Role: V
 Verifique se as falhas de validação são registradas com trechos de carga útil redigidos e códigos de erro inequívocos para auxiliar na triagem de segurança.

---

### C2.4 Triagem de Conteúdo e Políticas

Os desenvolvedores devem ser capazes de detectar prompts sintaticamente válidos que solicitem conteúdo proibido (como instruções ilícitas, discurso de ódio e texto protegido por direitos autorais) e impedir que eles se propaguem.

 #2.4.1    Level: 1    Role: D
 Verifique se um classificador de conteúdo (zero shot ou refinado) avalia cada entrada para violência, autoagressão, ódio, conteúdo sexual e solicitações ilegais, com limiares configuráveis.
 #2.4.2    Level: 1    Role: D/V
 Verifique se as entradas que violam as políticas receberão recusas padronizadas ou conclusões seguras para que não se propaguem para chamadas subsequentes de LLM.
 #2.4.3    Level: 2    Role: D
 Verifique se o modelo de triagem ou conjunto de regras é re-treinado/atualizado pelo menos trimestralmente, incorporando novos padrões de jailbreak ou de bypass de políticas observados.
 #2.4.4    Level: 2    Role: D
 Verifique se a triagem respeita as políticas específicas do usuário (idade, restrições legais regionais) por meio de regras baseadas em atributos resolvidas no momento da solicitação.
 #2.4.5    Level: 3    Role: V
 Verifique se os registros de triagem incluem pontuações de confiança do classificador e etiquetas de categoria de política para correlação SOC e futura reprodução por equipe vermelha.

---

### C2.5 Limitação da Taxa de Entrada e Prevenção de Abusos

Os desenvolvedores devem prevenir abusos, exaustão de recursos e ataques automatizados contra sistemas de IA, limitando as taxas de entrada e detectando padrões de uso anômalos.

 #2.5.1    Level: 1    Role: D/V
 Verifique se os limites de taxa por usuário, por IP e por chave de API são aplicados para todos os pontos de entrada de dados.
 #2.5.2    Level: 2    Role: D/V
 Verifique se os limites de taxa de explosão e sustentada estão ajustados para prevenir ataques DoS e de força bruta.
 #2.5.3    Level: 2    Role: D/V
 Verifique se padrões de uso anômalos (por exemplo, solicitações em rápida sucessão, inundação de entradas) acionam bloqueios automáticos ou escalonamentos.
 #2.5.4    Level: 3    Role: V
 Verifique se os registros de prevenção de abuso são mantidos e revisados para identificar padrões emergentes de ataque.

---

### C2.6 Validação de Entrada Multi-Modal

Os sistemas de IA devem incluir validação robusta para entradas não textuais (imagens, áudio, arquivos) para prevenir injeção, evasão ou abuso de recursos.

 #2.6.1    Level: 1    Role: D
 Verifique se todas as entradas não textuais (imagens, áudio, arquivos) são validadas quanto ao tipo, tamanho e formato antes do processamento.
 #2.6.2    Level: 2    Role: D/V
 Verifique se os arquivos são escaneados em busca de malware e cargas úteis esteganográficas antes da ingestão.
 #2.6.3    Level: 2    Role: D/V
 Verifique se as entradas de imagem/áudio são verificadas quanto a perturbações adversariais ou padrões de ataque conhecidos.
 #2.6.4    Level: 3    Role: V
 Verifique se as falhas na validação de entrada multimodal são registradas e acionam alertas para investigação.

---

### C2.7 Proveniência e Atribuição de Entrada

Os sistemas de IA devem suportar auditoria, rastreamento de abusos e conformidade monitorando e etiquetando as origens de todas as entradas dos usuários.

 #2.7.1    Level: 1    Role: D/V
 Verifique se todas as entradas do usuário estão marcadas com metadados (ID do usuário, sessão, origem, carimbo de data/hora, endereço IP) no momento da ingestão.
 #2.7.2    Level: 2    Role: D/V
 Verifique se os metadados de proveniência são mantidos e auditáveis para todas as entradas processadas.
 #2.7.3    Level: 2    Role: D/V
 Verifique se fontes de entrada anômalas ou não confiáveis são sinalizadas e submetidas a uma análise aprimorada ou bloqueio.

---

### C2.8 Detecção Adaptativa de Ameaças em Tempo Real

Os desenvolvedores devem empregar sistemas avançados de detecção de ameaças para IA que se adaptam a novos padrões de ataque e oferecem proteção em tempo real com correspondência de padrões compilados.

 #2.8.1    Level: 1    Role: D/V
 Verifique se os padrões de detecção de ameaças são compilados em mecanismos de regex otimizados para filtragem em tempo real de alto desempenho com impacto mínimo na latência.
 #2.8.2    Level: 1    Role: D/V
 Verifique se os sistemas de detecção de ameaças mantêm bibliotecas de padrões separadas para diferentes categorias de ameaças (injeção de prompt, conteúdo nocivo, dados sensíveis, comandos do sistema).
 #2.8.3    Level: 2    Role: D/V
 Verifique se a detecção adaptativa de ameaças incorpora modelos de aprendizado de máquina que atualizam a sensibilidade a ameaças com base na frequência e nas taxas de sucesso dos ataques.
 #2.8.4    Level: 2    Role: D/V
 Verifique se as fontes de inteligência de ameaça em tempo real atualizam automaticamente as bibliotecas de padrões com novas assinaturas de ataque e IOCs (Indicadores de Comprometimento).
 #2.8.5    Level: 3    Role: D/V
 Verifique se as taxas de falsos positivos na detecção de ameaças são monitoradas continuamente e se a especificidade dos padrões é ajustada automaticamente para minimizar a interferência em casos de uso legítimos.
 #2.8.6    Level: 3    Role: D/V
 Verifique se a análise contextual de ameaças considera a fonte de entrada, os padrões de comportamento do usuário e o histórico da sessão para melhorar a precisão da detecção.
 #2.8.7    Level: 3    Role: D/V
 Verifique se as métricas de desempenho da detecção de ameaças (taxa de detecção, latência de processamento, utilização de recursos) são monitoradas e otimizadas em tempo real.

---

### C2.9 Pipeline de Validação de Segurança Multimodal

Os desenvolvedores devem fornecer validação de segurança para texto, imagem, áudio e outras modalidades de entrada de IA com tipos específicos de detecção de ameaças e isolamento de recursos.

 #2.9.1    Level: 1    Role: D/V
 Verifique se cada modalidade de entrada possui validadores de segurança dedicados com padrões de ameaça documentados (texto: injeção de prompts, imagens: esteganografia, áudio: ataques por espectrograma) e limites de detecção.
 #2.9.2    Level: 2    Role: D/V
 Verifique se as entradas multimodais são processadas em sandboxes isolados com limites de recursos definidos (memória, CPU, tempo de processamento) específicos para cada tipo de modalidade e documentados nas políticas de segurança.
 #2.9.3    Level: 2    Role: D/V
 Verifique se a detecção de ataques cross-modal identifica ataques coordenados que abrangem múltiplos tipos de entrada (por exemplo, cargas ocultas esteganográficas em imagens combinadas com injeção de prompts em texto) usando regras de correlação e geração de alertas.
 #2.9.4    Level: 3    Role: D/V
 Verifique se as falhas de validação multimodal acionam o registro detalhado, incluindo todas as modalidades de entrada, resultados da validação, pontuações de ameaças e análise de correlação com formatos de log estruturados para integração com SIEM.
 #2.9.5    Level: 3    Role: D/V
 Verifique se os classificadores de conteúdo específicos por modalidade são atualizados conforme os cronogramas documentados (no mínimo trimestralmente) com novos padrões de ameaça, exemplos adversariais e benchmarks de desempenho mantidos acima dos limiares básicos.

---

### Referências

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Gerenciamento do Ciclo de Vida do Modelo C3 e Controle de Mudanças

### Objetivo de Controle

Os sistemas de IA devem implementar processos de controle de mudanças que impeçam modificações não autorizadas ou inseguras do modelo de chegarem à produção. Esse controle garante a integridade do modelo durante todo o ciclo de vida — desde o desenvolvimento, passando pela implantação, até a desativação — o que possibilita uma resposta rápida a incidentes e mantém a responsabilização por todas as alterações.

Objetivo Principal de Segurança: Apenas modelos autorizados e validados chegam à produção, empregando processos controlados que mantêm a integridade, rastreabilidade e recuperabilidade.

---

### C3.1 Autorização e Integridade do Modelo

Apenas modelos autorizados com integridade verificada alcançam os ambientes de produção.

 #3.1.1    Level: 1    Role: D/V
 Verifique se todos os artefatos do modelo (pesos, configurações, tokenizadores) estão assinados criptograficamente por entidades autorizadas antes da implantação.
 #3.1.2    Level: 1    Role: D/V
 Verifique se a integridade do modelo é validada no momento da implantação e se as falhas na verificação da assinatura impedem o carregamento do modelo.
 #3.1.3    Level: 2    Role: D/V
 Verifique se os registros de procedência do modelo incluem a identidade da entidade autorizadora, somas de verificação dos dados de treinamento, resultados dos testes de validação com status de aprovação/reprovação e um carimbo de data/hora de criação.
 #3.1.4    Level: 2    Role: D/V
 Verifique se todos os artefatos do modelo utilizam versionamento semântico (MAJOR.MINOR.PATCH) com critérios documentados que especificam quando cada componente da versão deve ser incrementado.
 #3.1.5    Level: 2    Role: V
 Verifique se o rastreamento de dependências mantém um inventário em tempo real que permite a identificação rápida de todos os sistemas consumidores.

---

### C3.2 Validação e Teste do Modelo

Os modelos devem passar por validações definidas de segurança e proteção antes da implantação.

 #3.2.1    Level: 1    Role: D/V
 Verifique se os modelos passam por testes automatizados de segurança que incluem validação de entrada, sanitização de saída e avaliações de segurança com limites de aprovação/reprovação organizacionais pré-acordados antes da implantação.
 #3.2.2    Level: 1    Role: D/V
 Verifique se as falhas de validação bloqueiam automaticamente a implantação do modelo após a aprovação explícita de substituição por parte de pessoal autorizado previamente designado, com justificativas comerciais documentadas.
 #3.2.3    Level: 2    Role: V
 Verifique se os resultados dos testes são assinados criptograficamente e vinculados de forma imutável ao hash da versão específica do modelo que está sendo validada.
 #3.2.4    Level: 2    Role: D/V
 Verifique se as implantações de emergência exigem avaliação de risco de segurança documentada e aprovação de uma autoridade de segurança pré-designada dentro de prazos previamente acordados.

---

### C3.3 Implantação Controlada e Reversão

As implementações do modelo devem ser controladas, monitoradas e reversíveis.

 #3.3.1    Level: 1    Role: D
 Verifique se as implantações em produção implementam mecanismos de lançamento gradual (implantações canário, implantações blue-green) com gatilhos automáticos de reversão baseados em taxas de erro pré-acordadas, limites de latência ou critérios de alerta de segurança.
 #3.3.2    Level: 1    Role: D/V
 Verifique se as capacidades de reversão restauram o estado completo do modelo (pesos, configurações, dependências) de forma atômica dentro de janelas de tempo organizacionais pré-definidas.
 #3.3.3    Level: 2    Role: D/V
 Verifique se os processos de implantação validam assinaturas criptográficas e calculam somas de verificação de integridade antes da ativação do modelo, falhando na implantação em caso de qualquer divergência.
 #3.3.4    Level: 2    Role: D/V
 Verifique se as capacidades de desligamento de emergência do modelo podem desativar os pontos de extremidade do modelo dentro dos tempos de resposta pré-definidos por meio de disjuntores automáticos ou interruptores manuais de desligamento.
 #3.3.5    Level: 2    Role: V
 Verifique se os artefatos de reversão (versões anteriores do modelo, configurações, dependências) são mantidos de acordo com as políticas organizacionais, utilizando armazenamento imutável para resposta a incidentes.

---

### C3.4 Mudança de Responsabilização e Auditoria

Todas as alterações no ciclo de vida do modelo devem ser rastreáveis e auditáveis.

 #3.4.1    Level: 1    Role: V
 Verifique se todas as alterações do modelo (implantação, configuração, desativação) geram registros de auditoria imutáveis, incluindo um carimbo de data/hora, identidade autenticada do ator, tipo de alteração e estados antes/depois.
 #3.4.2    Level: 2    Role: D/V
 Verifique se o acesso ao registro de auditoria requer autorização apropriada e se todas as tentativas de acesso são registradas com a identidade do usuário e um carimbo de data e hora.
 #3.4.3    Level: 2    Role: D/V
 Verifique se os modelos de prompt e as mensagens do sistema são controlados por versão em repositórios git, com revisão de código obrigatória e aprovação dos revisores designados antes da implantação.
 #3.4.4    Level: 2    Role: V
 Verifique se os registros de auditoria incluem detalhes suficientes (hashes do modelo, instantâneos de configuração, versões de dependências) para possibilitar a reconstrução completa do estado do modelo para qualquer data dentro do período de retenção.

---

### C3.5 Práticas de Desenvolvimento Seguro

Os processos de desenvolvimento e treinamento de modelos devem seguir práticas seguras para evitar comprometimentos.

 #3.5.1    Level: 1    Role: D
 Verifique se os ambientes de desenvolvimento, teste e produção do modelo estão separados fisicamente ou logicamente. Eles não devem compartilhar infraestrutura, devem possuir controles de acesso distintos e armazenamentos de dados isolados.
 #3.5.2    Level: 1    Role: D
 Verifique se o treinamento e o ajuste fino do modelo ocorrem em ambientes isolados com acesso controlado à rede.
 #3.5.3    Level: 1    Role: D/V
 Verifique se as fontes de dados de treinamento são validadas por meio de verificações de integridade e autenticadas por fontes confiáveis com cadeia de custódia documentada antes do uso no desenvolvimento do modelo.
 #3.5.4    Level: 2    Role: D
 Verifique se os artefatos de desenvolvimento do modelo (hiperparâmetros, scripts de treinamento, arquivos de configuração) estão armazenados no controle de versão e exigem aprovação da revisão por pares antes de serem usados no treinamento.

---

### C3.6 Aposentadoria e Descomissionamento do Modelo

Os modelos devem ser desativados de forma segura quando não forem mais necessários ou quando forem identificados problemas de segurança.

 #3.6.1    Level: 1    Role: D
 Verifique se os processos de desativação do modelo escaneiam automaticamente os gráficos de dependência, identificam todos os sistemas consumidores e fornecem períodos de aviso prévio previamente acordados antes da desativação.
 #3.6.2    Level: 1    Role: D/V
 Verifique se os artefatos do modelo desativado são apagados de forma segura usando apagamento criptográfico ou sobrescrita múltipla de acordo com as políticas documentadas de retenção de dados, com certificados de destruição verificados.
 #3.6.3    Level: 2    Role: V
 Verifique se os eventos de aposentadoria do modelo são registrados com carimbo de data/hora e identidade do ator, e se as assinaturas do modelo são revogadas para prevenir reutilização.
 #3.6.4    Level: 2    Role: D/V
 Verifique se a aposentadoria emergencial do modelo pode desativar o acesso ao modelo dentro dos prazos de resposta emergencial pré-estabelecidos por meio de interruptores automáticos, caso vulnerabilidades críticas de segurança sejam descobertas.

---

### Referências

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Infraestrutura C4, Configuração e Segurança de Implantação

### Objetivo de Controle

A infraestrutura de IA deve ser reforçada contra escalada de privilégios, adulteração da cadeia de suprimentos e movimentação lateral por meio de configuração segura, isolamento em tempo de execução, pipelines de implantação confiáveis e monitoramento abrangente. Apenas componentes e configurações de infraestrutura autorizados e validados chegam à produção por meio de processos controlados que mantêm a segurança, integridade e auditabilidade.

Objetivo Principal de Segurança: Apenas componentes de infraestrutura assinados criptograficamente e escaneados quanto a vulnerabilidades chegam à produção por meio de pipelines automatizados de validação que aplicam políticas de segurança e mantêm trilhas de auditoria imutáveis.

---

### C4.1 Isolamento do Ambiente de Execução

Prevenir fugas de contêineres e escalonamento de privilégios por meio de primitivas de isolamento em nível de kernel e controles de acesso obrigatórios.

 #4.1.1    Level: 1    Role: D/V
 Verifique se todos os contêineres de IA descartam TODAS as capacidades do Linux, exceto CAP_SETUID, CAP_SETGID e capacidades explicitamente necessárias documentadas nas diretrizes de segurança.
 #4.1.2    Level: 1    Role: D/V
 Verifique se os perfis seccomp bloqueiam todas as chamadas de sistema, exceto aquelas nas listas de permissões pré-aprovadas, com violações resultando na terminação do contêiner e na geração de alertas de segurança.
 #4.1.3    Level: 2    Role: D/V
 Verifique se as cargas de trabalho de IA são executadas com sistemas de arquivos raiz somente leitura, tmpfs para dados temporários e volumes nomeados para dados persistentes, com as opções de montagem noexec aplicadas.
 #4.1.4    Level: 2    Role: D/V
 Verifique se o monitoramento em tempo real baseado em eBPF (Falco, Tetragon ou equivalente) detecta tentativas de escalonamento de privilégios e encerra automaticamente os processos infratores dentro dos requisitos de tempo de resposta organizacional.
 #4.1.5    Level: 3    Role: D/V
 Verifique se as cargas de trabalho de IA de alto risco são executadas em ambientes isolados por hardware (Intel TXT, AMD SVM ou nós bare-metal dedicados) com verificação de atestado.

---

### C4.2 Pipelines Seguros de Construção e Implantação

Garanta a integridade criptográfica e a segurança da cadeia de suprimentos por meio de builds reproduzíveis e artefatos assinados.

 #4.2.1    Level: 1    Role: D/V
 Verifique se a infraestrutura como código é escaneada com ferramentas (tfsec, Checkov ou Terrascan) em cada commit, bloqueando merges com descobertas de severidade CRÍTICA ou ALTA.
 #4.2.2    Level: 1    Role: D/V
 Verifique se as construções de contêiner são reproduzíveis com hashes SHA256 idênticos entre as construções e gere atestações de proveniência SLSA Nível 3 assinadas com Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verifique se as imagens de contêiner incorporam SBOMs CycloneDX ou SPDX e estão assinadas com Cosign antes do envio ao registro, rejeitando imagens não assinadas no momento da implantação.
 #4.2.4    Level: 2    Role: D/V
 Verifique se os pipelines de CI/CD utilizam tokens OIDC do HashiCorp Vault, funções IAM da AWS ou Identidade Gerenciada do Azure com tempos de validade que não excedam os limites definidos pela política de segurança organizacional.
 #4.2.5    Level: 2    Role: D/V
 Verifique se as assinaturas Cosign e a proveniência SLSA são validadas durante o processo de implantação antes da execução do contêiner e que erros de verificação fazem com que a implantação falhe.
 #4.2.6    Level: 2    Role: D/V
 Verifique se os ambientes de build executam em contêineres efêmeros ou VMs sem armazenamento persistente e com isolamento de rede das VPCs de produção.

---

### C4.3 Segurança de Rede e Controle de Acesso

Implemente redes com confiança zero utilizando políticas de negação padrão e comunicações criptografadas.

 #4.3.1    Level: 1    Role: D/V
 Verifique se as NetworkPolicies do Kubernetes ou qualquer equivalente implementam o bloqueio padrão de entrada/saída (default-deny) com regras explícitas de permissão para as portas necessárias (443, 8080, etc.).
 #4.3.2    Level: 1    Role: D/V
 Verifique se as portas SSH (22), RDP (3389) e os endpoints de metadados da nuvem (169.254.169.254) estão bloqueados ou exigem autenticação baseada em certificado.
 #4.3.3    Level: 2    Role: D/V
 Verifique se o tráfego de saída é filtrado através de proxies HTTP/HTTPS (Squid, Istio ou gateways NAT em nuvem) com listas de domínio permitidas e requisições bloqueadas registradas.
 #4.3.4    Level: 2    Role: D/V
 Verifique se a comunicação entre serviços utiliza TLS mútuo com certificados rotacionados conforme a política organizacional e validação de certificados aplicada (sem flags de pular verificação).
 #4.3.5    Level: 2    Role: D/V
 Verifique se a infraestrutura de IA opera em VPCs/VNets dedicadas sem acesso direto à internet e se a comunicação ocorre apenas por meio de gateways NAT ou hosts bastião.

---

### C4.4 Gestão de Segredos e Chaves Criptográficas

Proteja credenciais através de armazenamento suportado por hardware e rotação automatizada com acesso de confiança zero.

 #4.4.1    Level: 1    Role: D/V
 Verifique se os segredos estão armazenados no HashiCorp Vault, AWS Secrets Manager, Azure Key Vault ou Google Secret Manager com criptografia em repouso usando AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verifique se as chaves criptográficas são geradas em HSMs Nível 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) com rotação de chaves de acordo com a política criptográfica organizacional.
 #4.4.3    Level: 2    Role: D/V
 Verifique se a rotação de segredos é automatizada com implantação sem tempo de inatividade e rotação imediata acionada por mudanças de pessoal ou incidentes de segurança.
 #4.4.4    Level: 2    Role: D/V
 Verifique se as imagens de contêiner são escaneadas com ferramentas (GitLeaks, TruffleHog ou detect-secrets) bloqueando builds que contenham chaves de API, senhas ou certificados.
 #4.4.5    Level: 2    Role: D/V
 Verifique se o acesso a segredos de produção requer MFA com tokens de hardware (YubiKey, FIDO2) e é registrado por logs de auditoria imutáveis com identidades de usuários e carimbos de data/hora.
 #4.4.6    Level: 2    Role: D/V
 Verifique se os segredos são injetados por meio de segredos do Kubernetes, volumes montados ou contêineres de inicialização e garanta que os segredos nunca sejam incorporados em variáveis de ambiente ou imagens.

---

### C4.5 Sandbox e Validação de Carga de Trabalho de IA

Isole modelos de IA não confiáveis em sandboxes seguros com análise comportamental abrangente.

 #4.5.1    Level: 1    Role: D/V
 Verifique se os modelos de IA externos são executados no gVisor, microVMs (como Firecracker, CrossVM) ou contêineres Docker com as opções --security-opt=no-new-privileges e --read-only ativadas.
 #4.5.2    Level: 1    Role: D/V
 Verifique se os ambientes sandbox não possuem conectividade de rede (--network=none) ou apenas acesso ao localhost, com todas as solicitações externas bloqueadas pelas regras do iptables.
 #4.5.3    Level: 2    Role: D/V
 Verifique se a validação do modelo de IA inclui testes automatizados de red team com cobertura de teste definida pela organização e análise comportamental para detecção de backdoor.
 #4.5.4    Level: 2    Role: D/V
 Verifique se, antes de um modelo de IA ser promovido para produção, seus resultados no ambiente sandbox são assinados criptograficamente por pessoal de segurança autorizado e armazenados em registros de auditoria imutáveis.
 #4.5.5    Level: 2    Role: D/V
 Verifique se os ambientes sandbox são destruídos e recriados a partir de imagens originais entre as avaliações, com limpeza completa do sistema de arquivos e da memória.

---

### C4.6 Monitoramento de Segurança da Infraestrutura

Escaneie e monitore continuamente a infraestrutura com remediação automatizada e alertas em tempo real.

 #4.6.1    Level: 1    Role: D/V
 Verifique se as imagens de contêiner são escaneadas de acordo com os cronogramas organizacionais, com vulnerabilidades CRÍTICAS bloqueando a implantação com base nos limiares de risco organizacional.
 #4.6.2    Level: 1    Role: D/V
 Verifique se a infraestrutura atende aos CIS Benchmarks ou aos controles do NIST 800-53 com limites de conformidade definidos pela organização e remediação automatizada para verificações falhas.
 #4.6.3    Level: 2    Role: D/V
 Verifique se as vulnerabilidades de severidade ALTA estão corrigidas de acordo com os prazos de gerenciamento de riscos organizacionais, com procedimentos de emergência para CVEs ativamente explorados.
 #4.6.4    Level: 2    Role: V
 Verifique se os alertas de segurança integram-se com as plataformas SIEM (Splunk, Elastic ou Sentinel) utilizando os formatos CEF ou STIX/TAXII com enriquecimento automatizado.
 #4.6.5    Level: 3    Role: V
 Verifique se as métricas de infraestrutura são exportadas para sistemas de monitoramento (Prometheus, DataDog) com dashboards de SLA e relatórios executivos.
 #4.6.6    Level: 2    Role: D/V
 Verifique se a deriva de configuração é detectada usando ferramentas (Chef InSpec, AWS Config) de acordo com os requisitos de monitoramento da organização, com reversão automática para alterações não autorizadas.

---

### C4.7 Gerenciamento de Recursos de Infraestrutura de IA

Prevenir ataques de exaustão de recursos e garantir a alocação justa de recursos por meio de cotas e monitoramento.

 #4.7.1    Level: 1    Role: D/V
 Verifique se a utilização de GPU/TPU é monitorada com alertas acionados em limites definidos pela organização e escalonamento automático ou balanceamento de carga ativados com base nas políticas de gerenciamento de capacidade.
 #4.7.2    Level: 1    Role: D/V
 Verifique se as métricas de carga de trabalho de IA (latência de inferência, taxa de transferência, taxas de erro) são coletadas de acordo com os requisitos de monitoramento organizacional e correlacionadas com a utilização da infraestrutura.
 #4.7.3    Level: 2    Role: D/V
 Verifique se os ResourceQuotas do Kubernetes ou equivalentes limitam cargas de trabalho individuais de acordo com as políticas organizacionais de alocação de recursos, com limites rígidos aplicados.
 #4.7.4    Level: 2    Role: V
 Verifique se o monitoramento de custos acompanha gastos por carga de trabalho/inquilino com alertas baseados em limites orçamentários organizacionais e controles automatizados para excedentes de orçamento.
 #4.7.5    Level: 3    Role: V
 Verifique se o planejamento de capacidade utiliza dados históricos com períodos de previsão definidos pela organização e provisionamento automatizado de recursos baseado em padrões de demanda.
 #4.7.6    Level: 2    Role: D/V
 Verifique se o esgotamento de recursos aciona os disjuntores de acordo com os requisitos de resposta organizacional, incluindo limitação de taxa baseada em políticas de capacidade e isolamento de carga de trabalho.

---

### C4.8 Controles de Separação e Promoção de Ambiente

Imponha limites ambientais rigorosos com portões de promoção automatizados e validação de segurança.

 #4.8.1    Level: 1    Role: D/V
 Verifique se os ambientes de desenvolvimento/teste/produção operam em VPCs/VNets separadas, sem papéis IAM, grupos de segurança ou conectividade de rede compartilhados.
 #4.8.2    Level: 1    Role: D/V
 Verifique se a promoção de ambiente requer aprovação de pessoal autorizado definido pela organização, com assinaturas criptográficas e trilhas de auditoria imutáveis.
 #4.8.3    Level: 2    Role: D/V
 Verifique se os ambientes de produção bloqueiam o acesso SSH, desabilitam pontos de extremidade de depuração e exigem solicitações de mudança com requisitos organizacionais de aviso prévio, exceto em emergências.
 #4.8.4    Level: 2    Role: D/V
 Verifique se as alterações de infraestrutura como código exigem revisão por pares com testes automatizados e varredura de segurança antes da fusão para o branch principal.
 #4.8.5    Level: 2    Role: D/V
 Verifique se os dados não relacionados à produção estão anonimados de acordo com os requisitos de privacidade organizacional, geração de dados sintéticos ou mascaramento completo dos dados com remoção de informações pessoalmente identificáveis (PII) verificada.
 #4.8.6    Level: 2    Role: D/V
 Verifique se os portões de promoção incluem testes de segurança automatizados (SAST, DAST, varredura de contêiner) com zero achados CRÍTICOS exigidos para aprovação.

---

### C4.9 Backup e Recuperação da Infraestrutura

Assegure a resiliência da infraestrutura por meio de backups automatizados, procedimentos de recuperação testados e capacidades de recuperação de desastres.

 #4.9.1    Level: 1    Role: D/V
 Verifique se as configurações da infraestrutura estão sendo copiadas de segurança de acordo com os cronogramas organizacionais de backup para regiões geograficamente separadas, com a implementação da estratégia de backup 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Verifique se os sistemas de backup operam em redes isoladas com credenciais separadas e armazenamento isolado (air-gapped) para proteção contra ransomware.
 #4.9.3    Level: 2    Role: V
 Verificar se os procedimentos de recuperação são testados e validados por meio de testes automatizados de acordo com os cronogramas organizacionais, com metas de RTO e RPO atendendo aos requisitos da organização.
 #4.9.4    Level: 3    Role: V
 Verifique se a recuperação de desastres inclui runbooks específicos para IA com restauração de pesos do modelo, reconstrução do cluster GPU e mapeamento de dependências de serviços.

---

### C4.10 Conformidade e Governança de Infraestrutura

Mantenha a conformidade regulatória por meio de avaliação contínua, documentação e controles automatizados.

 #4.10.1    Level: 2    Role: D/V
 Verifique se a conformidade da infraestrutura é avaliada de acordo com os cronogramas organizacionais em relação aos controles SOC 2, ISO 27001 ou FedRAMP, com coleta automatizada de evidências.
 #4.10.2    Level: 2    Role: V
 Verifique se a documentação da infraestrutura inclui diagramas de rede, mapas de fluxo de dados e modelos de ameaças atualizados de acordo com os requisitos de gestão de mudanças organizacionais.
 #4.10.3    Level: 3    Role: D/V
 Verifique se as alterações na infraestrutura passam por uma avaliação automatizada do impacto de conformidade com fluxos de trabalho de aprovação regulatória para modificações de alto risco.

---

### C4.11 Segurança de Hardware de IA

Componentes de hardware específicos para IA seguros, incluindo GPUs, TPUs e aceleradores especializados em IA.

 #4.11.1    Level: 2    Role: D/V
 Verifique se o firmware do acelerador de IA (BIOS da GPU, firmware do TPU) é verificado com assinaturas criptográficas e atualizado de acordo com os cronogramas de gerenciamento de patches da organização.
 #4.11.2    Level: 2    Role: D/V
 Verifique que, antes da execução da carga de trabalho, a integridade do acelerador de IA seja validada por meio de atestado de hardware utilizando TPM 2.0, Intel TXT ou AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Verifique se a memória da GPU está isolada entre as cargas de trabalho usando SR-IOV, MIG (GPU Multi-Instância) ou particionamento de hardware equivalente, com sanitização de memória entre os trabalhos.
 #4.11.4    Level: 3    Role: V
 Verifique se a cadeia de fornecimento de hardware de IA inclui a verificação de procedência com certificados do fabricante e a validação de embalagens à prova de violação.
 #4.11.5    Level: 3    Role: D/V
 Verifique se os módulos de segurança de hardware (HSMs) protegem os pesos dos modelos de IA e as chaves criptográficas com a certificação FIPS 140-2 Nível 3 ou Common Criteria EAL4+.

---

### C4.12 Infraestrutura de IA de Borda e Distribuída

Implantações seguras de IA distribuída, incluindo computação de borda, aprendizado federado e arquiteturas multi-site.

 #4.12.1    Level: 2    Role: D/V
 Verifique se os dispositivos de IA de borda autenticam na infraestrutura central usando TLS mútuo com certificados de dispositivo rotacionados de acordo com a política organizacional de gerenciamento de certificados.
 #4.12.2    Level: 2    Role: D/V
 Verifique se os dispositivos de borda implementam boot seguro com assinaturas verificadas e proteção contra rollback, evitando ataques de downgrade de firmware.
 #4.12.3    Level: 3    Role: D/V
 Verifique se a coordenação distribuída de IA utiliza algoritmos de consenso tolerantes a falhas bizantinas com validação dos participantes e detecção de nós maliciosos.
 #4.12.4    Level: 3    Role: D/V
 Verifique se a comunicação de edge para cloud inclui limitação de largura de banda, compressão de dados e capacidades de operação offline com armazenamento local seguro.

---

### C4.13 Segurança de Infraestrutura Multi-Nuvem e Híbrida

Garanta a segurança das cargas de trabalho de IA em vários provedores de nuvem e implantações híbridas de nuvem e on-premises.

 #4.13.1    Level: 2    Role: D/V
 Verifique se as implantações de IA multi-nuvem utilizam federação de identidade independente de nuvem (OIDC, SAML) com gestão centralizada de políticas entre os provedores.
 #4.13.2    Level: 2    Role: D/V
 Verifique se a transferência de dados entre nuvens utiliza criptografia de ponta a ponta com chaves gerenciadas pelo cliente e controles de residência de dados aplicados conforme a jurisdição.
 #4.13.3    Level: 2    Role: D/V
 Verifique se as cargas de trabalho de IA em nuvem híbrida implementam políticas de segurança consistentes entre ambientes locais e na nuvem, com monitoramento e alertas unificados.
 #4.13.4    Level: 3    Role: V
 Verifique se a prevenção de bloqueio de fornecedor de nuvem inclui infraestrutura como código portátil, APIs padronizadas e capacidades de exportação de dados com ferramentas de conversão de formato.
 #4.13.5    Level: 3    Role: V
 Verifique se a otimização de custos em multi-nuvem inclui controles de segurança que previnem a dispersão de recursos, bem como cobranças não autorizadas por transferência de dados entre nuvens.

---

### C4.14 Automação de Infraestrutura e Segurança GitOps

Automação segura de pipelines de infraestrutura e fluxos de trabalho GitOps para gestão de infraestrutura de IA.

 #4.14.1    Level: 2    Role: D/V
 Verifique se os repositórios GitOps exigem commits assinados com chaves GPG e regras de proteção de branch que impeçam pushes diretos para os branches principais.
 #4.14.2    Level: 2    Role: D/V
 Verifique se a automação da infraestrutura inclui detecção de desvios com capacidades automáticas de remediação e reversão ativadas de acordo com os requisitos de resposta organizacional para mudanças não autorizadas.
 #4.14.3    Level: 2    Role: D/V
 Verifique se o provisionamento automático da infraestrutura inclui a validação da política de segurança com bloqueio de implantação para configurações não conformes.
 #4.14.4    Level: 2    Role: D/V
 Verifique se os segredos da automação de infraestrutura são gerenciados por meio de operadores externos de segredos (External Secrets Operator, Bank-Vaults) com rotação automática.
 #4.14.5    Level: 3    Role: V
 Verifique se a infraestrutura autocurativa inclui correlação de eventos de segurança com resposta automatizada a incidentes e fluxos de trabalho de notificação para as partes interessadas.

---

### C4.15 Segurança de Infraestrutura Resistente a Quantum

Prepare a infraestrutura de IA para ameaças da computação quântica por meio de criptografia pós-quântica e protocolos seguros contra ataques quânticos.

 #4.15.1    Level: 3    Role: D/V
 Verifique se a infraestrutura de IA implementa algoritmos criptográficos pós-quânticos aprovados pelo NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) para troca de chaves e assinaturas digitais.
 #4.15.2    Level: 3    Role: D/V
 Verifique se os sistemas de distribuição de chave quântica (QKD) estão implementados para comunicações de IA de alta segurança com protocolos de gerenciamento de chaves quânticas seguras.
 #4.15.3    Level: 3    Role: D/V
 Verifique se as estruturas de agilidade criptográfica permitem a migração rápida para novos algoritmos pós-quânticos com rotação automatizada de certificados e chaves.
 #4.15.4    Level: 3    Role: V
 Verifique se a modelagem de ameaças quânticas avalia a vulnerabilidade da infraestrutura de IA a ataques quânticos com cronogramas de migração documentados e avaliações de risco.
 #4.15.5    Level: 3    Role: D/V
 Verifique se os sistemas criptográficos híbridos clássico-quânticos oferecem defesa em profundidade durante o período de transição quântica, com monitoramento de desempenho.

---

### C4.16 Computação Confidencial e Enclaves Seguros

Proteja cargas de trabalho de IA e pesos de modelos usando ambientes de execução confiáveis baseados em hardware e tecnologias de computação confidencial.

 #4.16.1    Level: 3    Role: D/V
 Verifique se os modelos sensíveis de IA são executados dentro de enclaves Intel SGX, AMD SEV-SNP ou ARM TrustZone com memória criptografada e verificação de atestado.
 #4.16.2    Level: 3    Role: D/V
 Verifique se os contêineres confidenciais (Kata Containers, gVisor com computação confidencial) isolam as cargas de trabalho de IA com criptografia de memória aplicada pelo hardware.
 #4.16.3    Level: 3    Role: D/V
 Verifique se a atestação remota valida a integridade do enclave antes de carregar os modelos de IA com prova criptográfica da autenticidade do ambiente de execução.
 #4.16.4    Level: 3    Role: D/V
 Verifique se os serviços confidenciais de inferência de IA impedem a extração do modelo por meio de computação criptografada com pesos do modelo selados e execução protegida.
 #4.16.5    Level: 3    Role: D/V
 Verifique se a orquestração do ambiente de execução confiável gerencia o ciclo de vida do enclave seguro com atestação remota e canais de comunicação criptografados.
 #4.16.6    Level: 3    Role: D/V
 Verifique se a computação multipartidária segura (SMPC) permite o treinamento colaborativo de IA sem expor os conjuntos de dados individuais ou os parâmetros do modelo.

---

### C4.17 Infraestrutura de Conhecimento Zero

Implemente sistemas de prova de conhecimento zero para verificação e autenticação de IA preservando a privacidade, sem revelar informações sensíveis.

 #4.17.1    Level: 3    Role: D/V
 Verifique se as provas de conhecimento zero (ZK-SNARKs, ZK-STARKs) confirmam a integridade do modelo de IA e a proveniência do treinamento sem expor os pesos do modelo ou os dados de treinamento.
 #4.17.2    Level: 3    Role: D/V
 Verifique se os sistemas de autenticação baseados em ZK permitem a verificação do usuário preservando a privacidade para serviços de IA sem revelar informações relacionadas à identidade.
 #4.17.3    Level: 3    Role: D/V
 Verifique se os protocolos de interseção privada de conjuntos (PSI) permitem a correspondência segura de dados para IA federada sem expor conjuntos de dados individuais.
 #4.17.4    Level: 3    Role: D/V
 Verifique se os sistemas de aprendizado de máquina de conhecimento zero (ZKML) permitem inferências de IA verificáveis com prova criptográfica de cálculo correto.
 #4.17.5    Level: 3    Role: D/V
 Verifique se os ZK-rollups fornecem processamento de transações de IA escalável e preservador de privacidade, com verificação em lote e redução da carga computacional.

---

### C4.18 Prevenção de Ataques por Canal Lateral

Proteja a infraestrutura de IA contra ataques de canal lateral baseados em tempo, energia, eletromagnéticos e cache que possam vazar informações sensíveis.

 #4.18.1    Level: 3    Role: D/V
 Verifique se o tempo de inferência de IA está normalizado usando algoritmos de tempo constante e preenchimento para evitar ataques de extração de modelo baseados em tempo.
 #4.18.2    Level: 3    Role: D/V
 Verifique se a proteção contra análise de potência inclui injeção de ruído, filtragem da linha de energia e padrões de execução aleatórios para hardware de IA.
 #4.18.3    Level: 3    Role: D/V
 Verifique se a mitigação de canal lateral baseado em cache utiliza particionamento de cache, randomização e instruções de flush para prevenir vazamento de informações.
 #4.18.4    Level: 3    Role: D/V
 Verifique se a proteção contra emissões eletromagnéticas inclui blindagem, filtragem de sinais e processamento aleatório para prevenir ataques do tipo TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Verifique se as defesas contra canais laterais microarquiteturais incluem controles de execução especulativa e ofuscação de padrões de acesso à memória.

---

### C4.19 Segurança de Hardware Neuromórfico e de IA Especializada

Arquiteturas seguras de hardware emergente em IA, incluindo chips neuromórficos, FPGAs, ASICs personalizados e sistemas de computação óptica.

 #4.19.1    Level: 3    Role: D/V
 Verifique se a segurança do chip neuromórfico inclui criptografia do padrão de picos, proteção do peso sináptico e validação da regra de aprendizado baseada em hardware.
 #4.19.2    Level: 3    Role: D/V
 Verifique se os aceleradores de IA baseados em FPGA implementam criptografia de bitstream, mecanismos anti-violação e carregamento seguro de configuração com atualizações autenticadas.
 #4.19.3    Level: 3    Role: D/V
 Verifique se a segurança do ASIC personalizado inclui processadores de segurança no chip, raiz de confiança de hardware e armazenamento seguro de chaves com detecção de violação.
 #4.19.4    Level: 3    Role: D/V
 Verifique se os sistemas de computação óptica implementam criptografia óptica segura contra computação quântica, comutação fotônica segura e processamento protegido de sinais ópticos.
 #4.19.5    Level: 3    Role: D/V
 Verifique se os chips de IA híbridos analógicos-digitais incluem computação analógica segura, armazenamento de pesos protegido e conversão autenticada de analógico para digital.

---

### C4.20 Infraestrutura de Computação com Preservação de Privacidade

Implemente controles de infraestrutura para computação que preserva a privacidade, a fim de proteger dados sensíveis durante o processamento e análise de IA.

 #4.20.1    Level: 3    Role: D/V
 Verifique se a infraestrutura de criptografia homomórfica permite a computação criptografada em cargas de trabalho sensíveis de IA com verificação de integridade criptográfica e monitoramento de desempenho.
 #4.20.2    Level: 3    Role: D/V
 Verifique se os sistemas de recuperação de informação privada permitem consultas em banco de dados sem revelar padrões de consulta, utilizando proteção criptográfica dos padrões de acesso.
 #4.20.3    Level: 3    Role: D/V
 Verifique se os protocolos de computação multipartidária segura permitem a inferência de IA preservando a privacidade, sem expor entradas individuais ou cálculos intermediários.
 #4.20.4    Level: 3    Role: D/V
 Verifique se a gestão de chaves que preserva a privacidade inclui geração distribuída de chaves, criptografia de limiar e rotação segura de chaves com proteção suportada por hardware.
 #4.20.5    Level: 3    Role: D/V
 Verifique se o desempenho da computação preservadora de privacidade está otimizado por meio de agrupamento, cache e aceleração por hardware, mantendo as garantias de segurança criptográfica.

---

### C4.15 Estrutura de Agente Integração de Nuvem de Segurança e Implantação Híbrida

Controles de segurança para estruturas de agentes integradas à nuvem com arquiteturas híbridas on-premises/nuvem.

 #4.15.1    Level: 1    Role: D/V
 Verifique se a integração do armazenamento em nuvem utiliza criptografia de ponta a ponta com gerenciamento de chaves controlado pelo agente.
 #4.15.2    Level: 2    Role: D/V
 Verifique se os limites de segurança da implantação híbrida estão claramente definidos com canais de comunicação criptografados.
 #4.15.3    Level: 2    Role: D/V
 Verifique se o acesso aos recursos em nuvem inclui verificação de confiança zero com autenticação contínua.
 #4.15.4    Level: 3    Role: D/V
 Verifique se os requisitos de residência de dados são aplicados por meio de atestação criptográfica dos locais de armazenamento.
 #4.15.5    Level: 3    Role: D/V
 Verifique se as avaliações de segurança do provedor de nuvem incluem a modelagem de ameaças específica para agentes e a avaliação de riscos.

---

### Referências

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Controle de Acesso C5 e Identidade para Componentes e Usuários de IA

### Objetivo de Controle

O controle de acesso eficaz para sistemas de IA requer uma gestão robusta de identidade, autorização consciente do contexto e aplicação em tempo de execução seguindo os princípios de confiança zero. Esses controles garantem que humanos, serviços e agentes autônomos interajam apenas com modelos, dados e recursos computacionais dentro de escopos explicitamente concedidos, com capacidades contínuas de verificação e auditoria.

---

### C5.1 Gerenciamento de Identidade e Autenticação

Estabeleça identidades suportadas criptograficamente para todas as entidades com autenticação multifatorial para operações com privilégios.

 #5.1.1    Level: 1    Role: D/V
 Verifique se todos os usuários humanos e principais de serviço autenticam-se através de um provedor de identidade empresarial centralizado (IdP) usando os protocolos OIDC/SAML com mapeamentos exclusivos de identidade para token (sem contas ou credenciais compartilhadas).
 #5.1.2    Level: 1    Role: D/V
 Verifique se operações de alto risco (implantação de modelo, exportação de pesos, acesso a dados de treinamento, alterações na configuração de produção) exigem autenticação multifator ou autenticação escalonada com revalidação da sessão.
 #5.1.3    Level: 2    Role: D
 Verifique se os novos responsáveis passam por verificação de identidade alinhada com o NIST 800-63-3 IAL-2 ou normas equivalentes antes de receber acesso ao sistema de produção.
 #5.1.4    Level: 2    Role: V
 Verifique se as revisões de acesso são realizadas trimestralmente com detecção automatizada de contas inativas, aplicação da rotação de credenciais e fluxos de trabalho de desprovisionamento.
 #5.1.5    Level: 3    Role: D/V
 Verifique se os agentes de IA federados se autenticam por meio de asserções JWT assinadas que possuem um tempo máximo de vida útil de 24 horas e incluem prova criptográfica de origem.

---

### C5.2 Autorização de Recursos e Privilégio Mínimo

Implemente controles de acesso detalhados para todos os recursos de IA com modelos de permissão explícitos e trilhas de auditoria.

 #5.2.1    Level: 1    Role: D/V
 Verifique se todos os recursos de IA (conjuntos de dados, modelos, pontos finais, coleções vetoriais, índices de incorporação, instâncias de computação) aplicam controles de acesso baseados em função com listas de permissão explícitas e políticas de negação padrão.
 #5.2.2    Level: 1    Role: D/V
 Verifique se os princípios de menor privilégio são aplicados por padrão nas contas de serviço, começando com permissões apenas de leitura e exigindo justificativa comercial documentada para acesso de escrita.
 #5.2.3    Level: 1    Role: V
 Verifique se todas as modificações no controle de acesso estão vinculadas a solicitações de alteração aprovadas e registradas de forma imutável com carimbos de data e hora, identidades dos atores, identificadores de recursos e variações de permissões.
 #5.2.4    Level: 2    Role: D
 Verifique se os rótulos de classificação de dados (PII, PHI, controlados por exportação, proprietários) são automaticamente propagados para os recursos derivados (embeddings, caches de prompt, saídas de modelo) com aplicação consistente da política.
 #5.2.5    Level: 2    Role: D/V
 Verifique se as tentativas de acesso não autorizadas e os eventos de escalonamento de privilégios acionam alertas em tempo real com metadados contextuais para sistemas SIEM em até 5 minutos.

---

### C5.3 Avaliação Dinâmica de Políticas

Implemente mecanismos de controle de acesso baseado em atributos (ABAC) para decisões de autorização conscientes do contexto, com capacidades de auditoria.

 #5.3.1    Level: 1    Role: D/V
 Verifique se as decisões de autorização são externalizadas para um motor de políticas dedicado (OPA, Cedar ou equivalente) acessível por meio de APIs autenticadas com proteção de integridade criptográfica.
 #5.3.2    Level: 1    Role: D/V
 Verifique se as políticas avaliam atributos dinâmicos em tempo de execução, incluindo nível de autorização do usuário, classificação de sensibilidade do recurso, contexto da solicitação, isolamento do locatário e restrições temporais.
 #5.3.3    Level: 2    Role: D
 Verifique se as definições de política são controladas por versão, revisadas por pares e validadas por meio de testes automatizados em pipelines de CI/CD antes da implantação em produção.
 #5.3.4    Level: 2    Role: V
 Verifique se os resultados da avaliação da política incluem fundamentos estruturados para a decisão e são transmitidos para sistemas SIEM para análise de correlação e relatórios de conformidade.
 #5.3.5    Level: 3    Role: D/V
 Verifique se os valores do tempo de vida (TTL) do cache de políticas não excedem 5 minutos para recursos de alta sensibilidade e 1 hora para recursos padrão com capacidades de invalidação de cache.

---

### C5.4 Aplicação de Segurança em Tempo de Consulta

Implemente controles de segurança na camada de banco de dados com filtragem obrigatória e políticas de segurança em nível de linha.

 #5.4.1    Level: 1    Role: D/V
 Verifique se todas as consultas ao banco de dados vetorial e SQL incluem filtros de segurança obrigatórios (ID do locatário, rótulos de sensibilidade, escopo do usuário) aplicados no nível do mecanismo do banco de dados, não no código da aplicação.
 #5.4.2    Level: 1    Role: D/V
 Verifique se as políticas de segurança em nível de linha (RLS) e mascaramento em nível de campo estão habilitadas com herança de políticas para todos os bancos de dados vetoriais, índices de busca e conjuntos de dados de treinamento.
 #5.4.3    Level: 2    Role: D
 Verifique se as avaliações de autorização falhadas impedirão "ataques de secretário confuso" ao abortar imediatamente as consultas e retornar códigos de erro de autorização explícitos em vez de retornar conjuntos de resultados vazios.
 #5.4.4    Level: 2    Role: V
 Verifique se a latência da avaliação da política é continuamente monitorada com alertas automáticos para condições de tempo limite que possam permitir a violação de autorização.
 #5.4.5    Level: 3    Role: D/V
 Verifique se os mecanismos de tentativa de consulta reavaliam as políticas de autorização para considerar alterações dinâmicas de permissões dentro das sessões ativas do usuário.

---

### Filtragem de Saída C5.5 e Prevenção de Perda de Dados

Implemente controles de pós-processamento para evitar a exposição não autorizada de dados em conteúdo gerado por IA.

 #5.5.1    Level: 1    Role: D/V
 Verifique se os mecanismos de filtragem pós-inferência escaneiam e redigem informações pessoais identificáveis (PII) não autorizadas, informações classificadas e dados proprietários antes de entregar o conteúdo aos solicitantes.
 #5.5.2    Level: 1    Role: D/V
 Verifique se as citações, referências e atribuições de fontes nas saídas do modelo são validadas em relação às permissões do solicitante e removidas caso seja detectado acesso não autorizado.
 #5.5.3    Level: 2    Role: D
 Verifique se as restrições de formato de saída (PDFs sanitizados, imagens com metadados removidos, tipos de arquivos aprovados) são aplicadas com base nos níveis de permissão do usuário e nas classificações de dados.
 #5.5.4    Level: 2    Role: V
 Verifique se os algoritmos de redação são determinísticos, controlados por versões e mantêm registros de auditoria para apoiar investigações de conformidade e análise forense.
 #5.5.5    Level: 3    Role: V
 Verifique se os eventos de redação de alto risco geram logs adaptativos que incluem hashes criptográficos do conteúdo original para recuperação forense sem exposição dos dados.

---

### C5.6 Isolamento Multi-Inquilino

Assegure o isolamento criptográfico e lógico entre os inquilinos em uma infraestrutura de IA compartilhada.

 #5.6.1    Level: 1    Role: D/V
 Verifique se os espaços de memória, armazenamentos de embeddings, entradas de cache e arquivos temporários são segregados por namespace para cada locatário, com limpeza segura na exclusão do locatário ou término da sessão.
 #5.6.2    Level: 1    Role: D/V
 Verifique se toda solicitação de API inclui um identificador de locatário autenticado que é validado criptograficamente em relação ao contexto da sessão e às permissões do usuário.
 #5.6.3    Level: 2    Role: D
 Verifique se as políticas de rede implementam regras de negação padrão para a comunicação entre locatários em malhas de serviço e plataformas de orquestração de contêineres.
 #5.6.4    Level: 3    Role: D
 Verifique se as chaves de criptografia são únicas por locatário com suporte a chave gerenciada pelo cliente (CMK) e isolamento criptográfico entre os armazenamentos de dados dos locatários.

---

### C5.7 Autorização de Agente Autônomo

Controle permissões para agentes de IA e sistemas autônomos por meio de tokens de capacidade definidos e autorização contínua.

 #5.7.1    Level: 1    Role: D/V
 Verifique se os agentes autônomos recebem tokens de capacidade com escopo que enumeram explicitamente as ações permitidas, os recursos acessíveis, os limites de tempo e as restrições operacionais.
 #5.7.2    Level: 1    Role: D/V
 Verifique se as capacidades de alto risco (acesso ao sistema de arquivos, execução de código, chamadas de API externas, transações financeiras) estão desativadas por padrão e exigem autorizações explícitas para ativação com justificativas comerciais.
 #5.7.3    Level: 2    Role: D
 Verifique se os tokens de capacidade estão vinculados às sessões do usuário, incluem proteção criptográfica de integridade e garantam que não possam ser persistidos ou reutilizados em cenários offline.
 #5.7.4    Level: 2    Role: V
 Verifique se as ações iniciadas pelo agente passam por autorização secundária por meio do mecanismo de políticas ABAC com avaliação de contexto completo e registro de auditoria.
 #5.7.5    Level: 3    Role: V
 Verifique se as condições de erro do agente e o tratamento de exceções incluem informações sobre o escopo de capacidade para apoiar a análise de incidentes e a investigação forense.

---

### Referências

#### Normas e Estruturas

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Guias de Implementação

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Segurança Específica para IA

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## Segurança da Cadeia de Suprimentos C6 para Modelos, Frameworks e Dados

### Objetivo de Controle

Ataques à cadeia de suprimentos de IA exploram modelos, frameworks ou conjuntos de dados de terceiros para inserir backdoors, viés ou código explorável. Esses controles fornecem rastreabilidade de ponta a ponta, gerenciamento de vulnerabilidades e monitoramento para proteger todo o ciclo de vida do modelo.

---

### C6.1 Avaliação e Proveniência de Modelos Pré-treinados

Avalie e autentique as origens, licenças e comportamentos ocultos de modelos de terceiros antes de qualquer ajuste fino ou implantação.

 #6.1.1    Level: 1    Role: D/V
 Verifique se todo artefato de modelo de terceiros inclui um registro de proveniência assinado que identifica o repositório de origem e o hash do commit.
 #6.1.2    Level: 1    Role: D/V
 Verifique se os modelos são escaneados quanto a camadas maliciosas ou gatilhos de Trojan usando ferramentas automatizadas antes da importação.
 #6.1.3    Level: 2    Role: D
 Verifique se o fine-tuning de transfer learning supera a avaliação adversarial para detectar comportamentos ocultos.
 #6.1.4    Level: 2    Role: V
 Verifique se as licenças do modelo, as etiquetas de controle de exportação e as declarações de origem dos dados estão registradas em uma entrada ML‑BOM.
 #6.1.5    Level: 3    Role: D/V
 Verifique se os modelos de alto risco (pesos carregados publicamente, criadores não verificados) permanecem isolados até a revisão e aprovação humana.

---

### C6.2 Varredura de Frameworks e Bibliotecas

Realize varreduras contínuas em frameworks e bibliotecas de ML para CVEs e códigos maliciosos, a fim de manter a pilha de execução segura.

 #6.2.1    Level: 1    Role: D/V
 Verifique se os pipelines de CI executam scanners de dependências em frameworks de IA e bibliotecas críticas.
 #6.2.2    Level: 1    Role: D/V
 Verifique se vulnerabilidades críticas (CVSS ≥ 7,0) impedem a promoção para imagens de produção.
 #6.2.3    Level: 2    Role: D
 Verifique se a análise estática de código é executada em bibliotecas de ML bifurcadas ou fornecidas como dependências.
 #6.2.4    Level: 2    Role: V
 Verifique se as propostas de atualização do framework incluem uma avaliação de impacto de segurança referenciando os feeds públicos de CVE.
 #6.2.5    Level: 3    Role: V
 Verifique se os sensores em tempo de execução alertam sobre carregamentos inesperados de bibliotecas dinâmicas que desviam do SBOM assinado.

---

### C6.3 Fixação e Verificação de Dependências

Fixe cada dependência em resumos imutáveis e reproduza as compilações para garantir artefatos idênticos e livres de adulterações.

 #6.3.1    Level: 1    Role: D/V
 Verifique se todos os gerenciadores de pacotes aplicam o travamento de versão por meio de arquivos de bloqueio.
 #6.3.2    Level: 1    Role: D/V
 Verifique se os resumos imutáveis são usados em vez de tags mutáveis nas referências de contêiner.
 #6.3.3    Level: 2    Role: D
 Verifique se as verificações de build reprodutível comparam hashes entre execuções de CI para garantir saídas idênticas.
 #6.3.4    Level: 2    Role: V
 Verifique se as atestações de build são armazenadas por 18 meses para rastreabilidade de auditoria.
 #6.3.5    Level: 3    Role: D
 Verifique se as dependências expiradas acionam PRs automatizados para atualizar ou bifurcar versões fixadas.

---

### C6.4 Aplicação de Fonte Confiável

Permitir downloads de artefatos apenas de fontes verificadas criptograficamente e aprovadas pela organização, e bloquear todo o restante.

 #6.4.1    Level: 1    Role: D/V
 Verifique se os pesos do modelo, os conjuntos de dados e os contêineres são baixados apenas de domínios aprovados ou registros internos.
 #6.4.2    Level: 1    Role: D/V
 Verifique se as assinaturas Sigstore/Cosign validam a identidade do publicador antes que os artefatos sejam armazenados em cache localmente.
 #6.4.3    Level: 2    Role: D
 Verifique se os proxies de saída bloqueiam downloads de artefatos não autenticados para garantir a aplicação da política de fonte confiável.
 #6.4.4    Level: 2    Role: V
 Verifique se as listas de permissões do repositório são revisadas trimestralmente com evidências de justificativa comercial para cada entrada.
 #6.4.5    Level: 3    Role: V
 Verifique se as violações de política acionam a quarentena dos artefatos e o rollback das execuções de pipeline dependentes.

---

### C6.5 Avaliação de Risco de Conjuntos de Dados de Terceiros

Avalie conjuntos de dados externos quanto a envenenamento, viés e conformidade legal, e monitore-os durante todo o seu ciclo de vida.

 #6.5.1    Level: 1    Role: D/V
 Verifique se os conjuntos de dados externos passam por uma avaliação de risco de envenenamento (por exemplo, impressão digital de dados, detecção de valores discrepantes).
 #6.5.2    Level: 1    Role: D
 Verifique se as métricas de viés (paridade demográfica, igualdade de oportunidade) são calculadas antes da aprovação do conjunto de dados.
 #6.5.3    Level: 2    Role: V
 Verifique se a proveniência e os termos de licença dos conjuntos de dados estão capturados nas entradas do ML-BOM.
 #6.5.4    Level: 2    Role: V
 Verifique se o monitoramento periódico detecta deriva ou corrupção nos conjuntos de dados hospedados.
 #6.5.5    Level: 3    Role: D
 Verifique se o conteúdo proibido (direitos autorais, informações pessoais identificáveis) é removido por meio de limpeza automatizada antes do treinamento.

---

### C6.6 Monitoramento de Ataques na Cadeia de Suprimentos

Detecte ameaças na cadeia de suprimentos cedo através de feeds CVE, análises de logs de auditoria e simulações de equipes vermelhas.

 #6.6.1    Level: 1    Role: V
 Verifique se os logs de auditoria de CI/CD são transmitidos para o SIEM para detectar puxadas de pacotes anômalas ou etapas de construção adulteradas.
 #6.6.2    Level: 2    Role: D
 Verifique se os playbooks de resposta a incidentes incluem procedimentos de reversão para modelos ou bibliotecas comprometidos.
 #6.6.3    Level: 3    Role: V
 Verifique se o enriquecimento de inteligência de ameaças marca indicadores específicos de ML (por exemplo, IoCs de envenenamento de modelo) na triagem de alertas.

---

### C6.7 ML‑BOM para Artefatos de Modelo

Gerar e assinar SBOMs detalhados específicos para ML (ML-BOMs) para que os consumidores finais possam verificar a integridade dos componentes no momento da implantação.

 #6.7.1    Level: 1    Role: D/V
 Verifique se todo artefato do modelo publica um ML-BOM que lista conjuntos de dados, pesos, hiperparâmetros e licenças.
 #6.7.2    Level: 1    Role: D/V
 Verifique se a geração de ML‑BOM e a assinatura Cosign estão automatizadas na Integração Contínua (CI) e são obrigatórias para a fusão (merge).
 #6.7.3    Level: 2    Role: D
 Verifique se as verificações de completude do ML‑BOM falham na compilação se qualquer metadado do componente (hash, licença) estiver faltando.
 #6.7.4    Level: 2    Role: V
 Verifique se os consumidores downstream podem consultar ML-BOMs via API para validar modelos importados no momento da implantação.
 #6.7.5    Level: 3    Role: V
 Verifique se os ML‑BOMs estão sob controle de versão e comparados para detectar modificações não autorizadas.

---

### Referências

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Comportamento do Modelo C7, Controle de Saída e Garantia de Segurança

### Objetivo de Controle

As saídas do modelo devem ser estruturadas, confiáveis, seguras, explicáveis e continuamente monitoradas em produção. Fazer isso reduz alucinações, vazamentos de privacidade, conteúdo nocivo e ações descontroladas, ao mesmo tempo em que aumenta a confiança do usuário e a conformidade regulatória.

---

### C7.1 Aplicação do Formato de Saída

Esquemas rigorosos, decodificação restrita e validação posterior impedem que conteúdo malformado ou malicioso se propague.

 #7.1.1    Level: 1    Role: D/V
 Verifique se os esquemas de resposta (por exemplo, JSON Schema) são fornecidos no prompt do sistema e se cada saída é automaticamente validada; saídas não conformes disparam reparo ou rejeição.
 #7.1.2    Level: 1    Role: D/V
 Verifique se a decodificação restrita (tokens de parada, regex, máximo de tokens) está ativada para evitar transbordamento ou canais laterais de injeção de prompt.
 #7.1.3    Level: 2    Role: D/V
 Verifique se os componentes a jusante tratam as saídas como não confiáveis e as validam contra esquemas ou desserializadores seguros contra injeção.
 #7.1.4    Level: 3    Role: V
 Verifique se os eventos de saída inadequada são registrados, controlados por taxa e exibidos no monitoramento.

---

### C7.2 Detecção e Mitigação de Alucinações

A estimativa de incerteza e as estratégias de contingência evitam respostas fabricadas.

 #7.2.1    Level: 1    Role: D/V
 Verifique se as log-probabilidades em nível de token, a auto-consistência do conjunto ou os detectores de alucinação ajustados atribuem uma pontuação de confiança a cada resposta.
 #7.2.2    Level: 1    Role: D/V
 Verifique se respostas abaixo de um limiar de confiança configurável acionam fluxos de trabalho de contingência (por exemplo, geração aumentada por recuperação, modelo secundário ou revisão humana).
 #7.2.3    Level: 2    Role: D/V
 Verifique se os incidentes de alucinação estão marcados com metadados de causa raiz e alimentados nos pipelines de análise pós-morte e ajuste fino.
 #7.2.4    Level: 3    Role: D/V
 Verifique se os limiares e detectores são recalibrados após atualizações significativas do modelo ou da base de conhecimento.
 #7.2.5    Level: 3    Role: V
 Verifique se as visualizações do painel acompanham as taxas de alucinação.

---

### C7.3 Filtragem de Segurança e Privacidade de Saída

Filtros de política e cobertura de equipe vermelha protegem os usuários e os dados confidenciais.

 #7.3.1    Level: 1    Role: D/V
 Verifique se os classificadores pré e pós-geração bloqueiam conteúdos de ódio, assédio, autoagressão, extremistas e sexualmente explícitos alinhados à política.
 #7.3.2    Level: 1    Role: D/V
 Verifique se a detecção de PII/PCI e a redação automática são executadas em todas as respostas; violações geram um incidente de privacidade.
 #7.3.3    Level: 2    Role: D
 Verifique se as etiquetas de confidencialidade (por exemplo, segredos comerciais) se propagam entre as modalidades para evitar vazamentos em texto, imagens ou código.
 #7.3.4    Level: 3    Role: D/V
 Verifique se as tentativas de contornar o filtro ou as classificações de alto risco requerem aprovação secundária ou reautenticação do usuário.
 #7.3.5    Level: 3    Role: D/V
 Verifique se os limites de filtragem refletem as jurisdições legais e o contexto de idade/papel do usuário.

---

### C7.4 Limitação de Saída e Ação

Limites de taxa e barreiras de aprovação impedem abusos e autonomia excessiva.

 #7.4.1    Level: 1    Role: D
 Verifique se as cotas por usuário e por chave de API limitam as requisições, tokens e custos com retrocesso exponencial em erros 429.
 #7.4.2    Level: 1    Role: D/V
 Verifique se as ações privilegiadas (gravações de arquivos, execução de código, chamadas de rede) exigem aprovação baseada em política ou intervenção humana.
 #7.4.3    Level: 2    Role: D/V
 Verifique se as verificações de consistência cross-modal garantem que imagens, códigos e textos gerados para a mesma solicitação não possam ser usados para contrabandear conteúdo malicioso.
 #7.4.4    Level: 2    Role: D
 Verifique se a profundidade da delegação do agente, os limites de recursão e as listas de ferramentas permitidas estão configurados explicitamente.
 #7.4.5    Level: 3    Role: V
 Verifique se a violação de limites emite eventos de segurança estruturados para ingestão pelo SIEM.

---

### C7.5 Explicabilidade da Saída

Sinais transparentes melhoram a confiança do usuário e a depuração interna.

 #7.5.1    Level: 2    Role: D/V
 Verifique se as pontuações de confiança visíveis ao usuário ou resumos breves de raciocínio são exibidos quando a avaliação de risco considerar adequado.
 #7.5.2    Level: 2    Role: D/V
 Verifique se as explicações geradas evitam revelar prompts de sistema sensíveis ou dados proprietários.
 #7.5.3    Level: 3    Role: D
 Verifique se o sistema captura as probabilidades logarítmicas no nível de token ou mapas de atenção e os armazena para inspeção autorizada.
 #7.5.4    Level: 3    Role: V
 Verifique se os artefatos de explicabilidade estão sob controle de versão juntamente com as versões do modelo para garantir a auditabilidade.

---

### C7.6 Integração de Monitoramento

A observabilidade em tempo real fecha o ciclo entre desenvolvimento e produção.

 #7.6.1    Level: 1    Role: D
 Verifique se as métricas (violações de esquema, taxa de alucinação, toxicidade, vazamento de informações pessoais identificáveis (PII), latência, custo) são enviadas para uma plataforma central de monitoramento.
 #7.6.2    Level: 1    Role: V
 Verifique se os limiares de alerta estão definidos para cada métrica de segurança, com caminhos de escalonamento para o plantão.
 #7.6.3    Level: 2    Role: V
 Verifique se os painéis correlacionam anomalias de saída com modelo/versão, sinalizador de recurso e mudanças nos dados de origem.
 #7.6.4    Level: 2    Role: D/V
 Verifique se os dados de monitoramento retroalimentam o retrabalho, ajuste fino ou atualizações de regras dentro de um fluxo de trabalho MLOps documentado.
 #7.6.5    Level: 3    Role: V
 Verifique se os pipelines de monitoramento são testados contra penetração e controlados por acesso para evitar o vazamento de logs sensíveis.

---

### 7.7 Salvaguardas para Mídia Generativa

Garantir que os sistemas de IA não gerem conteúdo de mídia ilegal, prejudicial ou não autorizado, aplicando restrições de políticas, validação de saída e rastreabilidade.

 #7.7.1    Level: 1    Role: D/V
 Verifique se as instruções do sistema e as orientações para o usuário proíbem explicitamente a geração de mídias deepfake ilegais, prejudiciais ou não consensuais (por exemplo, imagem, vídeo, áudio).
 #7.7.2    Level: 2    Role: D/V
 Verifique se os prompts são filtrados para tentativas de gerar personificações, deepfakes sexualmente explícitos ou mídia que retrate indivíduos reais sem consentimento.
 #7.7.3    Level: 2    Role: V
 Verifique se o sistema utiliza hashing perceptual, detecção de marca d'água ou impressão digital para prevenir a reprodução não autorizada de mídia protegida por direitos autorais.
 #7.7.4    Level: 3    Role: D/V
 Verifique se toda a mídia gerada está assinada criptograficamente, com marca d'água ou incorporada com metadados de proveniência resistentes a adulterações para rastreabilidade posterior.
 #7.7.5    Level: 3    Role: V
 Verifique se as tentativas de contorno (por exemplo, ofuscação de comandos, gírias, formulação adversarial) são detectadas, registradas e limitadas em taxa; abusos recorrentes são reportados aos sistemas de monitoramento.

### Referências

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Segurança de Memória C8, Embeddings e Banco de Dados Vetorial

### Objetivo de Controle

Incorporação e armazenamento vetorial atuam como a "memória ativa" dos sistemas de IA contemporâneos, aceitando continuamente dados fornecidos pelo usuário e os retornando nos contextos do modelo por meio da Geração Aumentada por Recuperação (RAG). Se deixada sem governança, essa memória pode vazar informações pessoais identificáveis (PII), violar consentimentos ou ser invertida para reconstruir o texto original. O objetivo desta família de controles é fortalecer os pipelines de memória e bancos de dados vetoriais para que o acesso seja pelo princípio do menor privilégio, as incorporações sejam preservadoras de privacidade, vetores armazenados expirem ou possam ser revogados sob demanda, e a memória por usuário nunca contamine as solicitações ou respostas de outro usuário.

---

### C8.1 Controles de Acesso na Memória e Índices RAG

Implemente controles de acesso refinados em todas as coleções de vetores.

 #8.1.1    Level: 1    Role: D/V
 Verifique se as regras de controle de acesso em nível de linha/namespace restringem as operações de inserção, exclusão e consulta por locatário, coleção ou etiqueta de documento.
 #8.1.2    Level: 1    Role: D/V
 Verifique se as chaves de API ou JWTs possuem claims com escopo (por exemplo, IDs de coleção, verbos de ação) e são rotacionadas pelo menos trimestralmente.
 #8.1.3    Level: 2    Role: D/V
 Verifique se tentativas de escalonamento de privilégios (por exemplo, consultas de similaridade entre namespaces) são detectadas e registradas em um SIEM dentro de 5 minutos.
 #8.1.4    Level: 2    Role: D/V
 Verifique se o banco de dados vetorial registra nos logs o identificador do sujeito, a operação, o ID/namespace do vetor, o limite de similaridade e a contagem de resultados.
 #8.1.5    Level: 3    Role: V
 Verifique se as decisões de acesso são testadas para falhas de bypass sempre que os motores são atualizados ou as regras de fragmentação de índice são alteradas.

---

### C8.2 Sanitização e Validação de Embeddings

Pré-analise o texto para informações pessoais identificáveis (PII), redija ou pseudonimize antes da vetorização e, opcionalmente, faça um pós-processamento das embeddings para eliminar sinais residuais.

 #8.2.1    Level: 1    Role: D/V
 Verifique se PII e dados regulamentados são detectados por meio de classificadores automatizados e mascarados, tokenizados ou descartados antes da incorporação.
 #8.2.2    Level: 1    Role: D
 Verifique se os pipelines de incorporação rejeitam ou colocam em quarentena entradas que contenham código executável ou artefatos não UTF-8 que possam contaminar o índice.
 #8.2.3    Level: 2    Role: D/V
 Verifique se a sanitização de privacidade diferencial local ou métrica é aplicada às incorporações de sentenças cuja distância para qualquer token PII conhecido fica abaixo de um limite configurável.
 #8.2.4    Level: 2    Role: V
 Verifique se a eficácia da sanitização (por exemplo, recall da redação de PII, deriva semântica) é validada pelo menos semestralmente contra corpora de referência.
 #8.2.5    Level: 3    Role: D/V
 Verifique se as configurações de sanitização estão sob controle de versão e se as alterações passam por revisão por pares.

---

### C8.3 Expiração, Revogação e Exclusão de Memória

O "direito ao esquecimento" do GDPR e leis semelhantes exigem apagamento oportuno; portanto, os armazenamentos vetoriais devem suportar TTLs, exclusões permanentes e tomb-stoning para que vetores revogados não possam ser recuperados ou reindexados.

 #8.3.1    Level: 1    Role: D/V
 Verifique se cada vetor e registro de metadados possui um TTL ou rótulo de retenção explícito respeitado por trabalhos automatizados de limpeza.
 #8.3.2    Level: 1    Role: D/V
 Verifique se as solicitações de exclusão iniciadas pelo usuário eliminam vetores, metadados, cópias em cache e índices derivados dentro de 30 dias.
 #8.3.3    Level: 2    Role: D
 Verifique se as exclusões lógicas são seguidas pela destruição criptográfica dos blocos de armazenamento, caso o hardware suporte, ou pela destruição da chave do cofre de chaves.
 #8.3.4    Level: 3    Role: D/V
 Verifique se os vetores expirados são excluídos dos resultados da busca por vizinhos mais próximos em menos de 500 ms após a expiração.

---

### C8.4 Prevenir a Inversão e Vazamento de Embeddings

Defesas recentes — superposição de ruído, redes de projeção, perturbação do neurônio de privacidade e criptografia na camada de aplicação — podem reduzir as taxas de inversão em nível de token para abaixo de 5%.

 #8.4.1    Level: 1    Role: V
 Verifique se existe um modelo formal de ameaça que cubra ataques de inversão, associação de membros e inferência de atributos, e se ele é revisado anualmente.
 #8.4.2    Level: 2    Role: D/V
 Verifique se a criptografia na camada de aplicação ou a criptografia pesquisável protege os vetores contra leituras diretas por administradores de infraestrutura ou funcionários da nuvem.
 #8.4.3    Level: 3    Role: V
 Verifique se os parâmetros de defesa (ε para DP, ruído σ, posto da projeção k) equilibram a privacidade ≥ 99% de proteção dos tokens e a utilidade ≤ 3% de perda de precisão.
 #8.4.4    Level: 3    Role: D/V
 Verifique se as métricas de resiliência à inversão fazem parte dos critérios de liberação para atualizações de modelo, com orçamentos de regressão definidos.

---

### C8.5 Aplicação de Escopo para Memória Específica do Usuário

O vazamento entre locatários continua sendo um dos principais riscos do RAG: consultas de similaridade mal filtradas podem revelar documentos privados de outro cliente.

 #8.5.1    Level: 1    Role: D/V
 Verifique se toda consulta de recuperação é pós-filtrada pelo ID do locatário/usuário antes de ser passada para o prompt do LLM.
 #8.5.2    Level: 1    Role: D
 Verifique se os nomes das coleções ou os IDs com namespace são salinizados por usuário ou inquilino para que os vetores não possam colidir entre os escopos.
 #8.5.3    Level: 2    Role: D/V
 Verifique se os resultados de similaridade acima de um limite de distância configurável, mas fora do escopo do chamador, são descartados e acionam alertas de segurança.
 #8.5.4    Level: 2    Role: V
 Verifique se os testes de estresse multi-inquilino simulam consultas adversariais tentando recuperar documentos fora do escopo e demonstrem zero vazamento.
 #8.5.5    Level: 3    Role: D/V
 Verifique se as chaves de criptografia são segregadas por locatário, garantindo isolamento criptográfico mesmo que o armazenamento físico seja compartilhado.

---

### C8.6 Segurança Avançada do Sistema de Memória

Controles de segurança para arquiteturas de memória sofisticadas, incluindo memória episódica, semântica e de trabalho, com requisitos específicos de isolamento e validação.

 #8.6.1    Level: 1    Role: D/V
 Verifique se os diferentes tipos de memória (episódica, semântica, operacional) possuem contextos de segurança isolados com controles de acesso baseados em função, chaves de criptografia separadas e padrões de acesso documentados para cada tipo de memória.
 #8.6.2    Level: 2    Role: D/V
 Verifique se os processos de consolidação de memória incluem validação de segurança para evitar a injeção de memórias maliciosas por meio de sanitização de conteúdo, verificação de fonte e checagens de integridade antes do armazenamento.
 #8.6.3    Level: 2    Role: D/V
 Verifique se as consultas de recuperação de memória são validadas e higienizadas para evitar a extração de informações não autorizadas por meio da análise do padrão de consulta, aplicação de controle de acesso e filtragem de resultados.
 #8.6.4    Level: 3    Role: D/V
 Verifique se os mecanismos de esquecimento de memória excluem informações confidenciais de forma segura com garantias de apagamento criptográfico, utilizando exclusão de chaves, sobrescrita múltipla ou exclusão segura baseada em hardware com certificados de verificação.
 #8.6.5    Level: 3    Role: D/V
 Verifique se a integridade do sistema de memória é monitorada continuamente para modificações ou corrupções não autorizadas por meio de somas de verificação, logs de auditoria e alertas automatizados quando o conteúdo da memória muda fora das operações normais.

---

### Referências

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Orquestração Autônoma e Ação Agencial em Segurança

### Objetivo de Controle

Garantir que sistemas de IA autônomos ou multiagentes só possam executar ações que sejam explicitamente intencionadas, autenticadas, auditáveis e dentro de limites definidos de custo e risco. Isso protege contra ameaças como Comprometimento de Sistema Autônomo, Uso Indevido de Ferramentas, Detecção de Loop de Agente, Sequestro de Comunicação, Falsificação de Identidade, Manipulação de Enxame e Manipulação de Intenção.

---

### 9.1 Orçamento de Planejamento de Tarefas de Agentes e Recursão

Controle planos recursivos e imponha pontos de verificação humanos para ações privilegiadas.

 #9.1.1    Level: 1    Role: D/V
 Verifique se a profundidade máxima de recursão, largura, tempo de relógio de parede, tokens e custo monetário por execução do agente estão configurados centralmente e versionados.
 #9.1.2    Level: 1    Role: D/V
 Verifique se ações privilegiadas ou irreversíveis (por exemplo, commits de código, transferências financeiras) exigem aprovação explícita humana por meio de um canal auditável antes da execução.
 #9.1.3    Level: 2    Role: D
 Verifique se os monitores de recursos em tempo real acionam a interrupção do disjuntor quando qualquer limite de orçamento é excedido, interrompendo a expansão adicional da tarefa.
 #9.1.4    Level: 2    Role: D/V
 Verifique se os eventos do disjuntor são registrados com o ID do agente, a condição de disparo e o estado do plano capturado para revisão forense.
 #9.1.5    Level: 3    Role: V
 Verifique se os testes de segurança cobrem cenários de exaustão do orçamento e planos fora de controle, confirmando a interrupção segura sem perda de dados.
 #9.1.6    Level: 3    Role: D
 Verifique se as políticas orçamentárias estão expressas como política-como-código e aplicadas em CI/CD para bloquear o desvio de configuração.

---

### 9.2 Sandboxing de Plugins de Ferramentas

Isole as interações da ferramenta para evitar acesso não autorizado ao sistema ou execução de código.

 #9.2.1    Level: 1    Role: D/V
 Verifique se toda ferramenta/plugin é executado dentro de um sistema operacional, contêiner ou sandbox em nível WASM com políticas de menor privilégio para sistema de arquivos, rede e chamadas de sistema.
 #9.2.2    Level: 1    Role: D/V
 Verifique se as cotas de recursos do sandbox (CPU, memória, disco, saída de rede) e os tempos limite de execução estão sendo aplicados e registrados.
 #9.2.3    Level: 2    Role: D/V
 Verifique se os binários ou descritores da ferramenta estão assinados digitalmente; as assinaturas devem ser validadas antes do carregamento.
 #9.2.4    Level: 2    Role: V
 Verifique se a telemetria do sandbox é transmitida para um SIEM; anomalias (por exemplo, tentativas de conexões de saída) geram alertas.
 #9.2.5    Level: 3    Role: V
 Verifique se plugins de alto risco passam por revisão de segurança e testes de penetração antes do deployment em produção.
 #9.2.6    Level: 3    Role: D/V
 Verifique se as tentativas de fuga do sandbox são automaticamente bloqueadas e o plugin infrator é colocado em quarentena aguardando investigação.

---

### 9.3 Loop Autônomo e Limitação de Custos

Detectar e interromper recursões descontroladas entre agentes e explosões de custos.

 #9.3.1    Level: 1    Role: D/V
 Verifique se as chamadas entre agentes incluem um limite de salto ou TTL que o tempo de execução decrementa e aplica.
 #9.3.2    Level: 2    Role: D
 Verifique se os agentes mantêm um ID único de grafo de invocação para identificar auto-invocações ou padrões cíclicos.
 #9.3.3    Level: 2    Role: D/V
 Verifique se os contadores acumulados de unidades de computação e gastos são monitorados por cadeia de requisição; ultrapassar o limite aborta a cadeia.
 #9.3.4    Level: 3    Role: V
 Verifique se a análise formal ou verificação de modelo demonstra a ausência de recursão ilimitada nos protocolos de agente.
 #9.3.5    Level: 3    Role: D
 Verifique se os eventos de interrupção de loop geram alertas e alimentam métricas de melhoria contínua.

---

### 9.4 Proteção contra Uso Indevido em Nível de Protocolo

Canais de comunicação seguros entre agentes e sistemas externos para prevenir sequestro ou manipulação.

 #9.4.1    Level: 1    Role: D/V
 Verifique se todas as mensagens de agente para ferramenta e de agente para agente estão autenticadas (por exemplo, TLS mútuo ou JWT) e criptografadas de ponta a ponta.
 #9.4.2    Level: 1    Role: D
 Verifique se os esquemas são estritamente validados; campos desconhecidos ou mensagens malformadas são rejeitados.
 #9.4.3    Level: 2    Role: D/V
 Verifique se as verificações de integridade (MACs ou assinaturas digitais) cobrem toda a carga útil da mensagem, incluindo os parâmetros da ferramenta.
 #9.4.4    Level: 2    Role: D
 Verifique se a proteção contra repetição (nonces ou janelas de carimbo de tempo) está aplicada na camada do protocolo.
 #9.4.5    Level: 3    Role: V
 Verifique se as implementações de protocolo passam por fuzzing e análise estática para detectar falhas de injeção ou desserialização.

---

### 9.5 Identidade do Agente e Evidência de Violação

Garanta que as ações sejam atribuíveis e as modificações detectáveis.

 #9.5.1    Level: 1    Role: D/V
 Verifique se cada instância de agente possui uma identidade criptográfica única (par de chaves ou credencial baseada em hardware).
 #9.5.2    Level: 2    Role: D/V
 Verifique se todas as ações do agente estão assinadas e carimbadas com data e hora; os registros incluem a assinatura para garantia de não repúdio.
 #9.5.3    Level: 2    Role: V
 Verifique se os registros à prova de violação são armazenados em um meio somente para anexar ou gravar uma única vez.
 #9.5.4    Level: 3    Role: D
 Verifique se as chaves de identidade são rotacionadas em um cronograma definido e em indicadores de comprometimento.
 #9.5.5    Level: 3    Role: D/V
 Verifique se tentativas de falsificação ou conflito de chave ativam a quarentena imediata do agente afetado.

---

### 9.6 Redução de Riscos em Enxames Multiagentes

Mitigue os riscos do comportamento coletivo através do isolamento e da modelagem formal de segurança.

 #9.6.1    Level: 1    Role: D/V
 Verifique se os agentes que operam em diferentes domínios de segurança executam em sandbox de tempo de execução isolados ou em segmentos de rede isolados.
 #9.6.2    Level: 3    Role: V
 Verifique se os comportamentos de enxame são modelados e formalmente verificados quanto à vivacidade e segurança antes da implantação.
 #9.6.3    Level: 3    Role: D
 Verifique se os monitores em tempo de execução detectam padrões emergentes de perigo (por exemplo, oscilações, bloqueios) e iniciam ações corretivas.

---

### 9.7 Autenticação / Autorização de Usuário e Ferramenta

Implemente controles de acesso robustos para cada ação acionada por agentes.

 #9.7.1    Level: 1    Role: D/V
 Verifique se os agentes se autenticam como principais de primeira classe em sistemas downstream, nunca reutilizando credenciais do usuário final.
 #9.7.2    Level: 2    Role: D
 Verifique se as políticas de autorização detalhadas restringem quais ferramentas um agente pode invocar e quais parâmetros ele pode fornecer.
 #9.7.3    Level: 2    Role: V
 Verifique se as verificações de privilégios são reavaliadas a cada chamada (autorização contínua), e não apenas no início da sessão.
 #9.7.4    Level: 3    Role: D
 Verifique se os privilégios delegados expiram automaticamente e exigem novo consentimento após o tempo limite ou alteração do escopo.

---

### 9.8 Segurança na Comunicação Agente-para-Agente

Criptografe e proteja a integridade de todas as mensagens entre agentes para impedir a interceptação e adulteração.

 #9.8.1    Level: 1    Role: D/V
 Verifique se a autenticação mútua e a criptografia com segredo perfeito adiante (por exemplo, TLS 1.3) são obrigatórias para os canais do agente.
 #9.8.2    Level: 1    Role: D
 Verifique se a integridade e a origem da mensagem são validadas antes do processamento; falhas geram alertas e descartam a mensagem.
 #9.8.3    Level: 2    Role: D/V
 Verifique se os metadados de comunicação (carimbos de data e hora, números de sequência) são registrados para suportar a reconstrução forense.
 #9.8.4    Level: 3    Role: V
 Verifique se a verificação formal ou a verificação de modelos confirma que as máquinas de estado do protocolo não podem ser levadas a estados inseguros.

---

### 9.9 Verificação de Intenção e Aplicação de Restrições

Validar que as ações do agente estejam alinhadas com a intenção declarada pelo usuário e as restrições do sistema.

 #9.9.1    Level: 1    Role: D
 Verifique se os solucionadores de restrições de pré-execução conferem as ações propostas em relação às regras rígidas de segurança e políticas codificadas.
 #9.9.2    Level: 2    Role: D/V
 Verifique se ações de alto impacto (financeiras, destrutivas, sensíveis à privacidade) exigem confirmação explícita de intenção do usuário que as inicia.
 #9.9.3    Level: 2    Role: V
 Verifique se as verificações pós-condição validam que as ações concluídas alcançaram os efeitos pretendidos sem efeitos colaterais; discrepâncias acionam o rollback.
 #9.9.4    Level: 3    Role: V
 Verifique se métodos formais (por exemplo, verificação de modelos, prova de teoremas) ou testes baseados em propriedades demonstram que os planos dos agentes satisfazem todas as restrições declaradas.
 #9.9.5    Level: 3    Role: D
 Verifique se incidentes de incompatibilidade de intenção ou violação de restrições alimentam ciclos de melhoria contínua e compartilhamento de inteligência sobre ameaças.

---

### 9.10 Estratégia de Raciocínio do Agente para Segurança

Seleção e execução segura de diferentes estratégias de raciocínio, incluindo as abordagens ReAct, Chain-of-Thought e Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Verifique se a seleção da estratégia de raciocínio utiliza critérios determinísticos (complexidade da entrada, tipo de tarefa, contexto de segurança) e se entradas idênticas produzem seleções de estratégia idênticas dentro do mesmo contexto de segurança.
 #9.10.2    Level: 1    Role: D/V
 Verifique se cada estratégia de raciocínio (ReAct, Chain-of-Thought, Tree-of-Thoughts) possui validação de entrada dedicada, sanitização de saída e limites de tempo de execução específicos para sua abordagem cognitiva.
 #9.10.3    Level: 2    Role: D/V
 Verifique se as transições da estratégia de raciocínio são registradas com contexto completo, incluindo características da entrada, valores dos critérios de seleção e metadados de execução para reconstrução da trilha de auditoria.
 #9.10.4    Level: 2    Role: D/V
 Verifique se o raciocínio Tree-of-Thoughts inclui mecanismos de poda de ramificações que encerram a exploração quando são detectadas violações de políticas, limites de recursos ou limites de segurança.
 #9.10.5    Level: 2    Role: D/V
 Verifique se os ciclos ReAct (Raciocínio-Ação-Observação) incluem pontos de verificação de validação em cada fase: verificação do passo de raciocínio, autorização da ação e higienização da observação antes de prosseguir.
 #9.10.6    Level: 3    Role: D/V
 Verifique se as métricas de desempenho da estratégia de raciocínio (tempo de execução, uso de recursos, qualidade da saída) são monitoradas com alertas automáticos quando as métricas se desviam além dos limites configurados.
 #9.10.7    Level: 3    Role: D/V
 Verifique se as abordagens de raciocínio híbrido que combinam múltiplas estratégias mantêm a validação de entrada e as restrições de saída de todas as estratégias constituintes sem contornar quaisquer controles de segurança.
 #9.10.8    Level: 3    Role: D/V
 Verifique se o teste de segurança da estratégia de raciocínio inclui fuzzing com entradas malformadas, prompts adversariais projetados para forçar a troca de estratégia e testes de condições de limite para cada abordagem cognitiva.

---

### 9.11 Gerenciamento do Ciclo de Vida do Estado do Agente e Segurança

Inicialização segura do agente, transições de estado e finalização com trilhas de auditoria criptográficas e procedimentos de recuperação definidos.

 #9.11.1    Level: 1    Role: D/V
 Verifique se a inicialização do agente inclui o estabelecimento de identidade criptográfica com credenciais baseadas em hardware e registros imutáveis de auditoria de inicialização contendo ID do agente, carimbo de data/hora, hash de configuração e parâmetros de inicialização.
 #9.11.2    Level: 2    Role: D/V
 Verifique se as transições de estado do agente estão assinadas criptograficamente, com carimbo de data e hora, e registradas com contexto completo, incluindo eventos desencadeadores, hash do estado anterior, hash do novo estado e validações de segurança realizadas.
 #9.11.3    Level: 2    Role: D/V
 Verifique se os procedimentos de desligamento do agente incluem a limpeza segura da memória usando apagamento criptográfico ou sobrescrição múltipla, revogação de credenciais com notificação à autoridade certificadora e geração de certificados de término à prova de violação.
 #9.11.4    Level: 3    Role: D/V
 Verifique se os mecanismos de recuperação do agente validam a integridade do estado usando somas de verificação criptográficas (mínimo SHA-256) e retornam a estados conhecidos como bons quando a corrupção é detectada, com alertas automatizados e requisitos de aprovação manual.
 #9.11.5    Level: 3    Role: D/V
 Verifique se os mecanismos de persistência do agente criptografam os dados de estado sensíveis com chaves AES-256 exclusivas por agente e implementam a rotação segura de chaves em cronogramas configuráveis (máximo de 90 dias) com implantação sem tempo de inatividade.

---

### 9.12 Estrutura de Segurança para Integração de Ferramentas

Controles de segurança para carregamento dinâmico de ferramentas, execução e validação de resultados com processos definidos de avaliação de risco e aprovação.

 #9.12.1    Level: 1    Role: D/V
 Verifique se os descritores da ferramenta incluem metadados de segurança especificando privilégios necessários (leitura/gravação/execução), níveis de risco (baixo/médio/alto), limites de recursos (CPU, memória, rede) e requisitos de validação documentados nos manifestos da ferramenta.
 #9.12.2    Level: 1    Role: D/V
 Verifique se os resultados da execução da ferramenta são validados contra esquemas esperados (JSON Schema, XML Schema) e políticas de segurança (sanitização de saída, classificação de dados) antes da integração, com limites de tempo e procedimentos de tratamento de erros.
 #9.12.3    Level: 2    Role: D/V
 Verifique se os registros de interação das ferramentas incluem contexto detalhado de segurança, incluindo uso de privilégios, padrões de acesso a dados, tempo de execução, consumo de recursos e códigos de retorno, com registro estruturado para integração com SIEM.
 #9.12.4    Level: 2    Role: D/V
 Verifique se os mecanismos de carregamento dinâmico de ferramentas validam assinaturas digitais utilizando infraestrutura PKI e implementam protocolos seguros de carregamento com isolamento em sandbox e verificação de permissões antes da execução.
 #9.12.5    Level: 3    Role: D/V
 Verifique se as avaliações de segurança das ferramentas são acionadas automaticamente para novas versões com etapas obrigatórias de aprovação, incluindo análise estática, testes dinâmicos e revisão pela equipe de segurança, com critérios de aprovação documentados e requisitos de SLA.

---

#### Referências

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Robustez Adversarial e Defesa de Privacidade

### Objetivo de Controle

Garanta que os modelos de IA permaneçam confiáveis, preservem a privacidade e sejam resistentes a abusos ao enfrentar ataques de evasão, inferência, extração ou envenenamento.

---

### 10.1 Alinhamento e Segurança do Modelo

Proteja contra resultados prejudiciais ou que violem a política.

 #10.1.1    Level: 1    Role: D/V
 Verifique se uma suíte de testes de alinhamento (prompts de red-team, sondagens de jailbreak, conteúdo não permitido) está sob controle de versão e é executada a cada lançamento do modelo.
 #10.1.2    Level: 1    Role: D
 Verifique se as restrições de recusa e conclusão segura estão sendo aplicadas.
 #10.1.3    Level: 2    Role: D/V
 Verifique se um avaliador automatizado mede a taxa de conteúdo prejudicial e sinaliza regressões que ultrapassem um limite definido.
 #10.1.4    Level: 2    Role: D
 Verifique se o treinamento contra jailbreak está documentado e é reproduzível.
 #10.1.5    Level: 3    Role: V
 Verifique se provas formais de conformidade com políticas ou monitoramento certificado cobrem domínios críticos.

---

### 10.2 Fortalecimento contra Exemplos Adversariais

Aumentar a resiliência a entradas manipuladas. Treinamento adversarial robusto e avaliação por benchmark são as melhores práticas atuais.

 #10.2.1    Level: 1    Role: D
 Verifique se os repositórios do projeto incluem configurações de treinamento adversarial com sementes reproduzíveis.
 #10.2.2    Level: 2    Role: D/V
 Verifique se a detecção de exemplos adversariais gera alertas de bloqueio em pipelines de produção.
 #10.2.4    Level: 3    Role: V
 Verifique se as provas de robustez certificada ou os certificados de limites por intervalo cobrem pelo menos as principais classes críticas.
 #10.2.5    Level: 3    Role: V
 Verifique se os testes de regressão utilizam ataques adaptativos para confirmar que não há perda mensurável de robustez.

---

### 10.3 Mitigação da Inferência de Associação

Limite a capacidade de decidir se um registro estava nos dados de treinamento. A privacidade diferencial e o mascaramento de pontuação de confiança continuam sendo as defesas conhecidas mais eficazes.

 #10.3.1    Level: 1    Role: D
 Verifique se a regularização de entropia por consulta ou o ajuste de temperatura reduzem previsões excessivamente confiantes.
 #10.3.2    Level: 2    Role: D
 Verifique se o treinamento utiliza otimização diferenciada privada com limite ε para conjuntos de dados sensíveis.
 #10.3.3    Level: 2    Role: V
 Verifique se as simulações de ataque (modelo sombra ou caixa preta) apresentam AUC de ataque ≤ 0,60 em dados retidos.

---

### 10.4 Resistência à Inversão de Modelo

Impedir a reconstrução de atributos privados. Pesquisas recentes enfatizam a truncagem de saída e garantias de DP como defesas práticas.

 #10.4.1    Level: 1    Role: D
 Verifique se os atributos sensíveis nunca são exibidos diretamente; quando necessário, use agrupamentos (buckets) ou transformações unidirecionais.
 #10.4.2    Level: 1    Role: D/V
 Verifique se os limites de taxa de consultas restringem consultas adaptativas repetidas do mesmo principal.
 #10.4.3    Level: 2    Role: D
 Verifique se o modelo foi treinado com ruído que preserva a privacidade.

---

### 10.5 Defesa contra Extração de Modelos

Detectar e impedir a clonagem não autorizada. Recomenda-se o uso de marcas d'água e análise de padrões de consulta.

 #10.5.1    Level: 1    Role: D
 Verifique se os gateways de inferência aplicam limites de taxa globais e por chave de API ajustados ao limite de memorização do modelo.
 #10.5.2    Level: 2    Role: D/V
 Verifique se as estatísticas de entropia da consulta e pluralidade da entrada alimentam um detector automático de extração.
 #10.5.3    Level: 2    Role: V
 Verifique se marcas d'água frágeis ou probabilísticas podem ser comprovadas com p < 0,01 em até 1.000 consultas contra um clone suspeito.
 #10.5.4    Level: 3    Role: D
 Verifique se as chaves de marca d'água e os conjuntos de gatilhos estão armazenados em um módulo de segurança de hardware e rotacionados anualmente.
 #10.5.5    Level: 3    Role: V
 Verifique se os eventos de alerta de extração incluem as consultas ofensivas e estão integrados com os roteiros de resposta a incidentes.

---

### 10.6 Detecção de Dados Envenenados em Tempo de Inferência

Identificar e neutralizar entradas com backdoor ou envenenadas.

 #10.6.1    Level: 1    Role: D
 Verifique se as entradas passam por um detector de anomalias (por exemplo, STRIP, pontuação de consistência) antes da inferência do modelo.
 #10.6.2    Level: 1    Role: V
 Verifique se os limiares do detector estão ajustados em conjuntos de validação limpos/envenenados para alcançar menos de 5% de falsos positivos.
 #10.6.3    Level: 2    Role: D
 Verifique se as entradas sinalizadas como envenenadas acionam bloqueio suave e fluxos de trabalho de revisão humana.
 #10.6.4    Level: 2    Role: V
 Verifique se os detectores são submetidos a testes de estresse com ataques de backdoor adaptativos e sem gatilho.
 #10.6.5    Level: 3    Role: D
 Verifique se as métricas de eficácia da detecção estão registradas e são reavaliadas periodicamente com informações atualizadas sobre ameaças.

---

### 10.7 Adaptação Dinâmica de Política de Segurança

Atualizações em tempo real da política de segurança baseadas em inteligência de ameaças e análise comportamental.

 #10.7.1    Level: 1    Role: D/V
 Verifique se as políticas de segurança podem ser atualizadas dinamicamente sem reiniciar o agente, mantendo a integridade da versão da política.
 #10.7.2    Level: 2    Role: D/V
 Verifique se as atualizações de políticas são assinadas criptograficamente por pessoal de segurança autorizado e validadas antes da aplicação.
 #10.7.3    Level: 2    Role: D/V
 Verifique se as alterações dinâmicas da política são registradas com trilhas de auditoria completas, incluindo justificação, cadeias de aprovação e procedimentos de reversão.
 #10.7.4    Level: 3    Role: D/V
 Verifique se os mecanismos de segurança adaptativa ajustam a sensibilidade da detecção de ameaças com base no contexto de risco e nos padrões comportamentais.
 #10.7.5    Level: 3    Role: D/V
 Verifique se as decisões de adaptação da política são explicáveis e incluem trilhas de evidências para revisão pela equipe de segurança.

---

### 10.8 Análise de Segurança Baseada em Reflexão

Validação de segurança por meio de autorreflexão do agente e análise metacognitiva.

 #10.8.1    Level: 1    Role: D/V
 Verifique se os mecanismos de reflexão do agente incluem autoavaliação focada em segurança das decisões e ações.
 #10.8.2    Level: 2    Role: D/V
 Verifique se as saídas de reflexão são validadas para evitar a manipulação de mecanismos de autoavaliação por entradas adversariais.
 #10.8.3    Level: 2    Role: D/V
 Verifique se a análise de segurança meta-cognitiva identifica possíveis viés, manipulação ou comprometimento nos processos de raciocínio do agente.
 #10.8.4    Level: 3    Role: D/V
 Verifique se os avisos de segurança baseados em reflexão acionam monitoramento aprimorado e potenciais fluxos de trabalho para intervenção humana.
 #10.8.5    Level: 3    Role: D/V
 Verifique se o aprendizado contínuo a partir das reflexões de segurança melhora a detecção de ameaças sem prejudicar a funcionalidade legítima.

---

### 10.9 Segurança de Evolução e Autoaperfeiçoamento

Controles de segurança para sistemas agentes capazes de auto modificação e evolução.

 #10.9.1    Level: 1    Role: D/V
 Verifique se as capacidades de auto-modificação estão restritas a áreas seguras designadas com limites de verificação formal.
 #10.9.2    Level: 2    Role: D/V
 Verifique se as propostas de evolução passam por avaliação de impacto de segurança antes da implementação.
 #10.9.3    Level: 2    Role: D/V
 Verifique se os mecanismos de autoaperfeiçoamento incluem capacidades de reversão com verificação de integridade.
 #10.9.4    Level: 3    Role: D/V
 Verifique se a segurança de meta-aprendizagem previne a manipulação adversarial de algoritmos de melhoria.
 #10.9.5    Level: 3    Role: D/V
 Verifique que a autoaperfeiçoamento recursivo é limitado por restrições formais de segurança com provas matemáticas de convergência.

---

#### Referências

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Proteção de Privacidade e Gestão de Dados Pessoais

### Objetivo de Controle

Manter garantias rigorosas de privacidade ao longo de todo o ciclo de vida da IA—coleta, treinamento, inferência e resposta a incidentes—para que os dados pessoais sejam processados apenas com consentimento claro, escopo mínimo necessário, eliminação comprovável e garantias formais de privacidade.

---

### 11.1 Anonimização e Minimização de Dados

 #11.1.1    Level: 1    Role: D/V
 Verifique se os identificadores diretos e quase-identificadores foram removidos ou convertidos em hash.
 #11.1.2    Level: 2    Role: D/V
 Verifique se auditorias automatizadas medem k-anonimato/l-diversidade e alertam quando os limites caem abaixo da política.
 #11.1.3    Level: 2    Role: V
 Verifique se os relatórios de importância das características do modelo comprovam que não há vazamento de identificadores além de ε = 0,01 de informação mútua.
 #11.1.4    Level: 3    Role: V
 Verifique se provas formais ou certificação por dados sintéticos mostram que o risco de reidentificação é ≤ 0,05 mesmo sob ataques de vinculação.

---

### 11.2 Direito ao Esquecimento e Aplicação da Exclusão

 #11.2.1    Level: 1    Role: D/V
 Verifique se as solicitações de exclusão de dados pessoais se propagam para conjuntos de dados brutos, pontos de verificação, embeddings, registros e backups dentro de acordos de nível de serviço inferiores a 30 dias.
 #11.2.2    Level: 2    Role: D
 Verifique se as rotinas de "desaprendizado de máquina" realmente re-treinam ou aproximam a remoção usando algoritmos certificados de desaprendizado.
 #11.2.3    Level: 2    Role: V
 Verifique que a avaliação do modelo sombra prova que os registros esquecidos influenciam menos de 1% dos resultados após o esquecimento.
 #11.2.4    Level: 3    Role: V
 Verifique se os eventos de exclusão são registrados de forma imutável e auditáveis para os reguladores.

---

### 11.3 Salvaguardas de Privacidade Diferencial

 #11.3.1    Level: 2    Role: D/V
 Verifique se os dashboards de contabilização da perda de privacidade alertam quando o ε acumulado ultrapassa os limites da política.
 #11.3.2    Level: 2    Role: V
 Verifique se as auditorias de privacidade em caixa preta estimam ε̂ dentro de 10% do valor declarado.
 #11.3.3    Level: 3    Role: V
 Verifique se as provas formais abrangem todos os ajustes finos e embeddings pós-treinamento.

---

### 11.4 Limitação de Finalidade e Proteção contra Escopo Excessivo

 #11.4.1    Level: 1    Role: D
 Verifique se cada conjunto de dados e ponto de verificação do modelo possui uma etiqueta de propósito legível por máquina alinhada ao consentimento original.
 #11.4.2    Level: 1    Role: D/V
 Verifique se os monitores de tempo de execução detectam consultas inconsistentes com o propósito declarado e acionam uma recusa suave.
 #11.4.3    Level: 3    Role: D
 Verifique se os controles de política como código bloqueiam a reimplantação de modelos em novos domínios sem revisão de DPIA.
 #11.4.4    Level: 3    Role: V
 Verifique se as provas formais de rastreabilidade mostram que todo o ciclo de vida dos dados pessoais permanece dentro do escopo consentido.

---

### 11.5 Gestão de Consentimento e Rastreio com Base Legal

 #11.5.1    Level: 1    Role: D/V
 Verifique se uma Plataforma de Gerenciamento de Consentimento (CMP) registra o status de opt-in, o propósito e o período de retenção por titular de dados.
 #11.5.2    Level: 2    Role: D
 Verifique se as APIs expõem tokens de consentimento; os modelos devem validar o escopo do token antes da inferência.
 #11.5.3    Level: 2    Role: D/V
 Verifique se o consentimento negado ou retirado interrompe os pipelines de processamento dentro de 24 horas.

---

### 11.6 Aprendizado Federado com Controles de Privacidade

 #11.6.1    Level: 1    Role: D
 Verifique se as atualizações do cliente empregam adição de ruído de privacidade diferencial local antes da agregação.
 #11.6.2    Level: 2    Role: D/V
 Verifique se as métricas de treinamento são diferencialmente privadas e nunca revelam a perda de um único cliente.
 #11.6.3    Level: 2    Role: V
 Verifique se a agregação resistente a envenenamento (por exemplo, Krum/Trimmed-Mean) está ativada.
 #11.6.4    Level: 3    Role: V
 Verifique que as provas formais demonstrem o orçamento total de ε com menos de 5 de perda de utilidade.

---

#### Referências

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Monitoramento, Registro e Detecção de Anomalias

### Objetivo de Controle

Esta seção fornece requisitos para oferecer visibilidade em tempo real e forense sobre o que o modelo e outros componentes de IA veem, fazem e retornam, para que ameaças possam ser detectadas, triadas e analisadas.

### C12.1 Registro de Solicitações e Respostas

 #12.1.1    Level: 1    Role: D/V
 Verifique se todos os prompts dos usuários e as respostas do modelo são registrados com metadados apropriados (por exemplo, carimbo de data/hora, ID do usuário, ID da sessão, versão do modelo).
 #12.1.2    Level: 1    Role: D/V
 Verifique se os logs são armazenados em repositórios seguros, com controle de acesso, políticas de retenção apropriadas e procedimentos de backup.
 #12.1.3    Level: 1    Role: D/V
 Verifique se os sistemas de armazenamento de logs implementam criptografia em repouso e em trânsito para proteger informações sensíveis contidas nos logs.
 #12.1.4    Level: 1    Role: D/V
 Verifique se os dados sensíveis em prompts e saídas são automaticamente ocultados ou mascarados antes do registro, com regras de ocultação configuráveis para informações pessoais identificáveis (IPI), credenciais e informações proprietárias.
 #12.1.5    Level: 2    Role: D/V
 Verifique se as decisões de política e as ações de filtragem de segurança são registradas com detalhes suficientes para possibilitar auditoria e depuração dos sistemas de moderação de conteúdo.
 #12.1.6    Level: 2    Role: D/V
 Verifique se a integridade dos logs está protegida por meio de, por exemplo, assinaturas criptográficas ou armazenamento somente para escrita.

---

### C12.2 Detecção e Alerta de Abuso

 #12.2.1    Level: 1    Role: D/V
 Verifique se o sistema detecta e alerta sobre padrões conhecidos de jailbreak, tentativas de injeção de prompts e entradas adversariais usando detecção baseada em assinaturas.
 #12.2.2    Level: 1    Role: D/V
 Verifique se o sistema integra-se com plataformas de Gestão de Informações e Eventos de Segurança (SIEM) existentes, utilizando formatos de log e protocolos padrão.
 #12.2.3    Level: 2    Role: D/V
 Verifique se os eventos de segurança enriquecidos incluem contexto específico de IA, como identificadores de modelo, pontuações de confiança e decisões do filtro de segurança.
 #12.2.4    Level: 2    Role: D/V
 Verifique se a detecção de anomalias comportamentais identifica padrões incomuns de conversa, tentativas excessivas de repetição ou comportamentos sistemáticos de sondagem.
 #12.2.5    Level: 2    Role: D/V
 Verifique se os mecanismos de alerta em tempo real notificam as equipes de segurança quando possíveis violações de políticas ou tentativas de ataque são detectadas.
 #12.2.6    Level: 2    Role: D/V
 Verifique se as regras personalizadas estão incluídas para detectar padrões de ameaças específicos de IA, incluindo tentativas coordenadas de jailbreak, campanhas de injeção de prompt e ataques de extração de modelo.
 #12.2.7    Level: 3    Role: D/V
 Verifique se os fluxos de trabalho automatizados de resposta a incidentes conseguem isolar modelos comprometidos, bloquear usuários maliciosos e escalonar eventos críticos de segurança.

---

### C12.3 Detecção de Deriva de Modelo

 #12.3.1    Level: 1    Role: D/V
 Verifique se o sistema acompanha métricas básicas de desempenho, como precisão, pontuações de confiança, latência e taxas de erro ao longo das versões do modelo e períodos de tempo.
 #12.3.2    Level: 2    Role: D/V
 Verifique se os alertas automatizados são acionados quando as métricas de desempenho excedem os limiares de degradação predefinidos ou se desviam significativamente das linhas de base.
 #12.3.3    Level: 2    Role: D/V
 Verifique se os monitores de detecção de alucinação identificam e sinalizam casos em que as saídas do modelo contêm informações factualmente incorretas, inconsistentes ou fabricadas.

---

### C12.4 Telemetria de Desempenho e Comportamento

 #12.4.1    Level: 1    Role: D/V
 Verifique se as métricas operacionais, incluindo latência de requisição, consumo de tokens, uso de memória e taxa de transferência, são continuamente coletadas e monitoradas.
 #12.4.2    Level: 1    Role: D/V
 Verifique se as taxas de sucesso e falha são monitoradas com a categorização dos tipos de erro e suas causas raízes.
 #12.4.3    Level: 2    Role: D/V
 Verifique se o monitoramento da utilização de recursos inclui o uso de GPU/CPU, consumo de memória e requisitos de armazenamento, com alertas em caso de ultrapassagem dos limites estabelecidos.

---

### C12.5 Planejamento e Execução de Resposta a Incidentes de IA

 #12.5.1    Level: 1    Role: D/V
 Verifique se os planos de resposta a incidentes abordam especificamente eventos de segurança relacionados à IA, incluindo comprometimento de modelos, envenenamento de dados e ataques adversariais.
 #12.5.2    Level: 2    Role: D/V
 Verifique se as equipes de resposta a incidentes têm acesso a ferramentas forenses específicas de IA e expertise para investigar o comportamento do modelo e vetores de ataque.
 #12.5.3    Level: 3    Role: D/V
 Verifique se a análise pós-incidente inclui considerações sobre re-treinamento do modelo, atualizações dos filtros de segurança e integração das lições aprendidas nos controles de segurança.

---

### C12.5 Detecção de Degradação do Desempenho de IA

Monitorar e detectar a degradação no desempenho e na qualidade do modelo de IA ao longo do tempo.

 #12.5.1    Level: 1    Role: D/V
 Verifique se a precisão do modelo, a precisão, o recall e as pontuações F1 são continuamente monitorados e comparados com os limiares de referência.
 #12.5.2    Level: 1    Role: D/V
 Verifique se a detecção de deriva de dados monitora alterações na distribuição de entrada que podem impactar o desempenho do modelo.
 #12.5.3    Level: 2    Role: D/V
 Verifique se a detecção de deriva de conceito identifica mudanças na relação entre entradas e saídas esperadas.
 #12.5.4    Level: 2    Role: D/V
 Verifique se a degradação do desempenho aciona alertas automáticos e inicia fluxos de trabalho de re-treinamento ou substituição do modelo.
 #12.5.5    Level: 3    Role: V
 Verifique se a análise da causa raiz da degradação correlaciona as quedas de desempenho com mudanças nos dados, problemas de infraestrutura ou fatores externos.

---

### C12.6 Visualização de DAG e Segurança do Fluxo de Trabalho

Proteja os sistemas de visualização de fluxo de trabalho contra vazamento de informações e ataques de manipulação.

 #12.6.1    Level: 1    Role: D/V
 Verifique se os dados de visualização do DAG estão sanitizados para remover informações sensíveis antes do armazenamento ou transmissão.
 #12.6.2    Level: 1    Role: D/V
 Verifique se os controles de acesso à visualização do fluxo de trabalho garantem que apenas usuários autorizados possam visualizar os caminhos de decisão do agente e os rastros de raciocínio.
 #12.6.3    Level: 2    Role: D/V
 Verifique se a integridade dos dados DAG está protegida por meio de assinaturas criptográficas e mecanismos de armazenamento à prova de adulteração.
 #12.6.4    Level: 2    Role: D/V
 Verifique se os sistemas de visualização de fluxo de trabalho implementam validação de entrada para prevenir ataques de injeção através de dados manipulados de nós ou arestas.
 #12.6.5    Level: 3    Role: D/V
 Verifique se as atualizações em tempo real do DAG são limitadas em taxa e validadas para prevenir ataques de negação de serviço nos sistemas de visualização.

---

### C12.7 Monitoramento Proativo do Comportamento de Segurança

Detecção e prevenção de ameaças de segurança por meio da análise proativa do comportamento do agente.

 #12.7.1    Level: 1    Role: D/V
 Verifique se os comportamentos proativos do agente são validados quanto à segurança antes da execução, integrando a avaliação de risco.
 #12.7.2    Level: 2    Role: D/V
 Verifique se os gatilhos de iniciativa autônoma incluem avaliação do contexto de segurança e análise do cenário de ameaças.
 #12.7.3    Level: 2    Role: D/V
 Verifique se os padrões de comportamento proativo são analisados quanto a potenciais implicações de segurança e consequências não intencionais.
 #12.7.4    Level: 3    Role: D/V
 Verifique se as ações proativas críticas para a segurança requerem cadeias de aprovação explícitas com trilhas de auditoria.
 #12.7.5    Level: 3    Role: D/V
 Verifique se a detecção de anomalias comportamentais identifica desvios nos padrões de agentes proativos que possam indicar comprometimento.

---

### Referências

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Supervisão Humana, Responsabilidade e Governança

### Objetivo de Controle

Este capítulo fornece requisitos para manter a supervisão humana e cadeias claras de responsabilidade em sistemas de IA, garantindo explicabilidade, transparência e gestão ética ao longo do ciclo de vida da IA.

---

### C13.1 Mecanismos de Interruptor de Emergência e Substituição

Forneça caminhos de desligamento ou reversão quando for observado um comportamento inseguro do sistema de IA.

 #13.1.1    Level: 1    Role: D/V
 Verifique se existe um mecanismo manual de desligamento para interromper imediatamente a inferência e as saídas do modelo de IA.
 #13.1.2    Level: 1    Role: D
 Verifique se os controles de substituição estão acessíveis apenas ao pessoal autorizado.
 #13.1.3    Level: 3    Role: D/V
 Verifique se os procedimentos de rollback podem reverter para versões anteriores do modelo ou operações em modo seguro.
 #13.1.4    Level: 3    Role: V
 Verifique se os mecanismos de substituição são testados regularmente.

---

### C13.2 Pontos de Verificação de Decisão com Intervenção Humana

Exigir aprovações humanas quando os riscos ultrapassarem os limites pré-definidos.

 #13.2.1    Level: 1    Role: D/V
 Verifique se as decisões de IA de alto risco exigem aprovação humana explícita antes da execução.
 #13.2.2    Level: 1    Role: D
 Verifique se os limites de risco estão claramente definidos e acionam automaticamente fluxos de trabalho de revisão humana.
 #13.2.3    Level: 2    Role: D
 Verifique se as decisões sensíveis ao tempo possuem procedimentos alternativos quando a aprovação humana não pode ser obtida dentro dos prazos necessários.
 #13.2.4    Level: 3    Role: D/V
 Verifique se os procedimentos de escalonamento definem níveis claros de autoridade para diferentes tipos de decisão ou categorias de risco, se aplicável.

---

### C13.3 Cadeia de Responsabilidade e Auditabilidade

Registrar ações do operador e decisões do modelo.

 #13.3.1    Level: 1    Role: D/V
 Verifique se todas as decisões do sistema de IA e intervenções humanas são registradas com carimbos de data e hora, identidades dos usuários e justificativas das decisões.
 #13.3.2    Level: 2    Role: D
 Verifique se os logs de auditoria não podem ser adulterados e incluem mecanismos de verificação de integridade.

---

### C13.4 Técnicas de IA Explicável

Importância das características superficiais, contra-factuais e explicações locais.

 #13.4.1    Level: 1    Role: D/V
 Verifique se os sistemas de IA fornecem explicações básicas para suas decisões em formato legível por humanos.
 #13.4.2    Level: 2    Role: V
 Verifique que a qualidade da explicação é validada através de estudos de avaliação humana e métricas.
 #13.4.3    Level: 3    Role: D/V
 Verifique se as pontuações de importância das características ou os métodos de atribuição (SHAP, LIME, etc.) estão disponíveis para decisões críticas.
 #13.4.4    Level: 3    Role: V
 Verifique se as explicações contrafactuais mostram como as entradas poderiam ser modificadas para alterar os resultados, se aplicável ao caso de uso e domínio.

---

### C13.5 Cartões de Modelo e Divulgação de Uso

Manter cartões de modelo para uso pretendido, métricas de desempenho e considerações éticas.

 #13.5.1    Level: 1    Role: D
 Verifique se as fichas do modelo documentam os casos de uso pretendidos, as limitações e os modos de falha conhecidos.
 #13.5.2    Level: 1    Role: D/V
 Verifique se as métricas de desempenho para diferentes casos de uso aplicáveis estão divulgadas.
 #13.5.3    Level: 2    Role: D
 Verifique se as considerações éticas, avaliações de viés, avaliações de equidade, características dos dados de treinamento e limitações conhecidas dos dados de treinamento estão documentadas e atualizadas regularmente.
 #13.5.4    Level: 2    Role: D/V
 Verifique se os cartões de modelo são controlados por versão e mantidos ao longo do ciclo de vida do modelo com rastreamento de alterações.

---

### C13.6 Quantificação da Incerteza

Propague as pontuações de confiança ou medidas de entropia nas respostas.

 #13.6.1    Level: 1    Role: D
 Verifique se os sistemas de IA fornecem pontuações de confiança ou medidas de incerteza juntamente com seus resultados.
 #13.6.2    Level: 2    Role: D/V
 Verifique se os limites de incerteza acionam uma revisão humana adicional ou caminhos de decisão alternativos.
 #13.6.3    Level: 2    Role: V
 Verifique se os métodos de quantificação de incerteza estão calibrados e validados com dados de referência.
 #13.6.4    Level: 3    Role: D/V
 Verifique se a propagação da incerteza é mantida ao longo de fluxos de trabalho de IA em múltiplas etapas.

---

### C13.7 Relatórios de Transparência para Usuários

Fornecer divulgações periódicas sobre incidentes, deriva e uso de dados.

 #13.7.1    Level: 1    Role: D/V
 Verifique se as políticas de uso de dados e as práticas de gerenciamento de consentimento do usuário são claramente comunicadas às partes interessadas.
 #13.7.2    Level: 2    Role: D/V
 Verifique se as avaliações de impacto da IA são realizadas e se os resultados estão incluídos nos relatórios.
 #13.7.3    Level: 2    Role: D/V
 Verifique se os relatórios de transparência publicados regularmente divulgam incidentes de IA e métricas operacionais com detalhes razoáveis.

#### Referências

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Apêndice A: Glossário

Este glossário abrangente fornece definições dos principais termos de IA, Aprendizado de Máquina e segurança usados ao longo do AISVS para garantir clareza e entendimento comum.
​
Exemplo Adversarial: Uma entrada deliberadamente criada para fazer um modelo de IA cometer um erro, frequentemente adicionando perturbações sutis imperceptíveis para os humanos.
​
Robustez Adversarial – Robustez adversarial em IA refere-se à capacidade de um modelo de manter seu desempenho e resistir a ser enganado ou manipulado por entradas maliciosamente elaboradas, projetadas para causar erros.
​
Agente – Agentes de IA são sistemas de software que utilizam IA para perseguir objetivos e completar tarefas em nome dos usuários. Eles demonstram raciocínio, planejamento e memória, e possuem um nível de autonomia para tomar decisões, aprender e se adaptar.
​
IA Agente: Sistemas de IA que podem operar com certo grau de autonomia para alcançar objetivos, frequentemente tomando decisões e realizando ações sem intervenção humana direta.
​
Controle de Acesso Baseado em Atributos (ABAC): Um paradigma de controle de acesso onde as decisões de autorização são baseadas em atributos do usuário, recurso, ação e ambiente, avaliados no momento da consulta.
​
Ataque de Porta dos Fundos: Um tipo de ataque de envenenamento de dados onde o modelo é treinado para responder de maneira específica a certos gatilhos, enquanto se comporta normalmente em outras situações.
​
Viés: Erros sistemáticos nas saídas dos modelos de IA que podem levar a resultados injustos ou discriminatórios para certos grupos ou em contextos específicos.
​
Exploração de Viés: Uma técnica de ataque que aproveita vieses conhecidos em modelos de IA para manipular saídas ou resultados.
​
Cedar: linguagem e mecanismo de política da Amazon para permissões granulares usadas na implementação de ABAC para sistemas de IA.
​
Cadeia de Pensamento: Uma técnica para melhorar o raciocínio em modelos de linguagem, gerando etapas intermediárias de raciocínio antes de produzir uma resposta final.
​
Disjuntores: Mecanismos que interrompem automaticamente as operações do sistema de IA quando limites específicos de risco são ultrapassados.
​
Vazamento de Dados: Exposição não intencional de informações sensíveis por meio dos resultados ou comportamento do modelo de IA.
​
Envenenamento de Dados: A corrupção deliberada dos dados de treinamento para comprometer a integridade do modelo, frequentemente para instalar portas dos fundos ou degradar o desempenho.
​
Privacidade Diferencial – A privacidade diferencial é uma estrutura matematicamente rigorosa para divulgar informações estatísticas sobre conjuntos de dados, protegendo a privacidade dos indivíduos. Ela permite que o detentor dos dados compartilhe padrões agregados do grupo, limitando as informações vazadas sobre indivíduos específicos.
​
Incorporação: Representações vetoriais densas de dados (texto, imagens, etc.) que capturam o significado semântico em um espaço de alta dimensionalidade.
​
Explicabilidade – Explicabilidade na IA é a capacidade de um sistema de IA fornecer razões compreensíveis para humanos sobre suas decisões e previsões, oferecendo insights sobre seu funcionamento interno.
​
IA Explicável (XAI): Sistemas de IA projetados para fornecer explicações compreensíveis para humanos sobre suas decisões e comportamentos por meio de várias técnicas e estruturas.
​
Aprendizado Federado: Uma abordagem de aprendizado de máquina onde os modelos são treinados em múltiplos dispositivos descentralizados que possuem amostras de dados locais, sem a troca dos próprios dados.
​
Guardrails: Restrições implementadas para evitar que sistemas de IA produzam resultados prejudiciais, tendenciosos ou indesejáveis.
​
Alucinação – Uma alucinação de IA refere-se a um fenômeno onde um modelo de IA gera informações incorretas ou enganosas que não são baseadas em seus dados de treinamento nem na realidade factual.
​
Human-in-the-Loop (HITL): Sistemas projetados para exigir supervisão, verificação ou intervenção humana em pontos decisivos cruciais.
​
Infraestrutura como Código (IaC): Gerenciar e provisionar infraestrutura por meio de código em vez de processos manuais, permitindo a verificação de segurança e implantações consistentes.
​
Jailbreak: Técnicas usadas para contornar as salvaguardas de segurança em sistemas de IA, particularmente em grandes modelos de linguagem, para produzir conteúdo proibido.
​
Princípio do Mínimo Privilégio: O princípio de segurança de conceder apenas os direitos de acesso mínimos necessários para usuários e processos.
​
LIME (Explicações Locais Interpretáveis Independentes de Modelo): Uma técnica para explicar as previsões de qualquer classificador de aprendizado de máquina, aproximando-o localmente com um modelo interpretável.
​
Ataque de Inferência de Associação: Um ataque que visa determinar se um ponto de dado específico foi usado para treinar um modelo de aprendizado de máquina.
​
MITRE ATLAS: Panorama de Ameaças Adversariais para Sistemas de Inteligência Artificial; uma base de conhecimento de táticas e técnicas adversariais contra sistemas de IA.
​
Ficha do Modelo – Uma ficha do modelo é um documento que fornece informações padronizadas sobre o desempenho, limitações, usos pretendidos e considerações éticas de um modelo de IA para promover a transparência e o desenvolvimento responsável de IA.
​
Extração de Modelo: Um ataque onde um adversário consulta repetidamente um modelo alvo para criar uma cópia funcionalmente semelhante sem autorização.
​
Inversão de Modelo: Um ataque que tenta reconstruir os dados de treinamento analisando as saídas do modelo.
​
Gestão do Ciclo de Vida do Modelo – A Gestão do Ciclo de Vida do Modelo de IA é o processo de supervisionar todas as etapas da existência de um modelo de IA, incluindo seu design, desenvolvimento, implantação, monitoramento, manutenção e eventual aposentadoria, para garantir que ele permaneça eficaz e alinhado com os objetivos.
​
Envenenamento de Modelo: Introdução de vulnerabilidades ou portas traseiras diretamente em um modelo durante o processo de treinamento.
​
Roubo/Roubalheira de Modelo: Extrair uma cópia ou aproximação de um modelo proprietário por meio de consultas repetidas.
​
Sistema Multiagente: Um sistema composto por múltiplos agentes de IA interagindo, cada um com capacidades e objetivos potencialmente diferentes.
​
OPA (Open Policy Agent): Um motor de políticas de código aberto que permite a aplicação unificada de políticas em toda a pilha.
​
Aprendizado de Máquina Preservador de Privacidade (PPML): Técnicas e métodos para treinar e implementar modelos de ML enquanto protegem a privacidade dos dados de treinamento.
​
Injeção de Prompt: Um ataque onde instruções maliciosas são incorporadas nas entradas para substituir o comportamento pretendido de um modelo.
​
RAG (Geração Aumentada por Recuperação): Uma técnica que aprimora grandes modelos de linguagem ao recuperar informações relevantes de fontes externas de conhecimento antes de gerar uma resposta.
​
Red-Teaming: A prática de testar ativamente sistemas de IA simulando ataques adversariais para identificar vulnerabilidades.
​
SBOM (Lista de Materiais de Software): Um registro formal que contém os detalhes e as relações da cadeia de suprimentos de vários componentes usados na construção de software ou modelos de IA.
​
SHAP (Explicações Aditivas de Shapley): Uma abordagem baseada na teoria dos jogos para explicar a saída de qualquer modelo de aprendizado de máquina, calculando a contribuição de cada característica para a previsão.
​
Ataque à Cadeia de Suprimentos: Comprometer um sistema ao visar elementos menos seguros em sua cadeia de suprimentos, como bibliotecas de terceiros, conjuntos de dados ou modelos pré-treinados.
​
Aprendizado por Transferência: Uma técnica onde um modelo desenvolvido para uma tarefa é reutilizado como ponto de partida para um modelo em uma segunda tarefa.
​
Banco de Dados Vetorial: Um banco de dados especializado projetado para armazenar vetores de alta dimensão (incorporações) e realizar buscas de similaridade eficientes.
​
Varredura de Vulnerabilidades: Ferramentas automatizadas que identificam vulnerabilidades de segurança conhecidas em componentes de software, incluindo frameworks de IA e dependências.
​
Marcação d'água: Técnicas para incorporar marcadores imperceptíveis em conteúdo gerado por IA para rastrear sua origem ou detectar a geração por IA.
​
Vulnerabilidade Zero-Day: Uma vulnerabilidade previamente desconhecida que os atacantes podem explorar antes que os desenvolvedores criem e implementem uma correção.

## Apêndice B: Referências

### TODO

## Apêndice C: Governança e Documentação de Segurança em IA

### Objetivo

Este apêndice fornece requisitos fundamentais para estabelecer estruturas organizacionais, políticas e processos para governar a segurança de IA ao longo do ciclo de vida do sistema.

---

### AC.1 Adoção do Quadro de Gestão de Riscos de IA

Fornecer uma estrutura formal para identificar, avaliar e mitigar os riscos específicos de IA ao longo do ciclo de vida do sistema.

 #AC.1.1    Level: 1    Role: D/V
 Verifique se uma metodologia de avaliação de riscos específica para IA está documentada e implementada.
 #AC.1.2    Level: 2    Role: D
 Verifique se as avaliações de risco são realizadas em pontos-chave do ciclo de vida da IA e antes de mudanças significativas.
 #AC.1.3    Level: 3    Role: D/V
 Verifique se a estrutura de gerenciamento de riscos está alinhada com os padrões estabelecidos (por exemplo, NIST AI RMF).

---

### AC.2 Política e Procedimentos de Segurança de IA

Definir e impor padrões organizacionais para o desenvolvimento, implantação e operação segura de IA.

 #AC.2.1    Level: 1    Role: D/V
 Verifique se existem políticas de segurança de IA documentadas.
 #AC.2.2    Level: 2    Role: D
 Verifique se as políticas são revisadas e atualizadas pelo menos anualmente e após mudanças significativas no cenário de ameaças.
 #AC.2.3    Level: 3    Role: D/V
 Verifique se as políticas abordam todas as categorias AISVS e os requisitos regulatórios aplicáveis.

---

### AC.3 Papéis e Responsabilidades para a Segurança de IA

Estabeleça uma responsabilidade clara pela segurança da IA em toda a organização.

 #AC.3.1    Level: 1    Role: D/V
 Verifique se os papéis e responsabilidades de segurança de IA estão documentados.
 #AC.3.2    Level: 2    Role: D
 Verifique se as pessoas responsáveis possuem a expertise adequada em segurança.
 #AC.3.3    Level: 3    Role: D/V
 Verifique se um comitê de ética em IA ou um conselho de governança está estabelecido para sistemas de IA de alto risco.

---

### AC.4 Aplicação das Diretrizes de IA Ética

Garantir que os sistemas de IA operem de acordo com princípios éticos estabelecidos.

 #AC.4.1    Level: 1    Role: D/V
 Verifique se existem diretrizes éticas para o desenvolvimento e implantação de IA.
 #AC.4.2    Level: 2    Role: D
 Verifique se existem mecanismos para detectar e relatar violações éticas.
 #AC.4.3    Level: 3    Role: D/V
 Verifique se revisões éticas regulares dos sistemas de IA implantados são realizadas.

---

### AC.5 Monitoramento de Conformidade Regulatória em IA

Mantenha a conscientização sobre e o cumprimento das regulamentações de IA em evolução.

 #AC.5.1    Level: 1    Role: D/V
 Verifique se existem processos para identificar as regulamentações de IA aplicáveis.
 #AC.5.2    Level: 2    Role: D
 Verifique se a conformidade com todos os requisitos regulatórios foi avaliada.
 #AC.5.3    Level: 3    Role: D/V
 Verifique se as mudanças regulatórias desencadeiam revisões e atualizações oportunas dos sistemas de IA.

#### Referências

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Apêndice D: Governança e Verificação de Codificação Segura Assistida por IA

### Objetivo

Este capítulo define controles organizacionais básicos para o uso seguro e eficaz de ferramentas de codificação assistida por IA durante o desenvolvimento de software, garantindo segurança e rastreabilidade ao longo do ciclo de vida do desenvolvimento de software (SDLC).

---

### AD.1 Fluxo de Trabalho de Codificação Segura Assistida por IA

Integrar ferramentas de IA no ciclo de vida seguro de desenvolvimento de software (SSDLC) da organização sem enfraquecer as barreiras de segurança existentes.

 #AD.1.1    Level: 1    Role: D/V
 Verifique se um fluxo de trabalho documentado descreve quando e como as ferramentas de IA podem gerar, refatorar ou revisar código.
 #AD.1.2    Level: 2    Role: D
 Verifique se o fluxo de trabalho corresponde a cada fase do SSDLC (design, implementação, revisão de código, testes, implantação).
 #AD.1.3    Level: 3    Role: D/V
 Verifique se as métricas (por exemplo, densidade de vulnerabilidades, tempo médio para detecção) são coletadas no código produzido por IA e comparadas com os parâmetros de referência apenas humanos.

---

### AD.2 Qualificação de Ferramentas de IA e Modelagem de Ameaças

Garanta que as ferramentas de codificação de IA sejam avaliadas quanto às capacidades de segurança, riscos e impacto na cadeia de suprimentos antes da adoção.

 #AD.2.1    Level: 1    Role: D/V
 Verifique se o modelo de ameaça para cada ferramenta de IA identifica riscos de uso indevido, inversão de modelo, vazamento de dados e cadeia de dependências.
 #AD.2.2    Level: 2    Role: D
 Verifique se as avaliações das ferramentas incluem análise estática/dinâmica de quaisquer componentes locais e avaliação dos endpoints SaaS (TLS, autenticação/autorização, registro).
 #AD.2.3    Level: 3    Role: D/V
 Verifique se as avaliações seguem uma estrutura reconhecida e são refeitas após mudanças significativas na versão.

---

### AD.3 Gerenciamento Seguro de Prompt e Contexto

Prevenir o vazamento de segredos, código proprietário e dados pessoais ao construir prompts ou contextos para modelos de IA.

 #AD.3.1    Level: 1    Role: D/V
 Verifique se as orientações escritas proíbem o envio de segredos, credenciais ou dados classificados em prompts.
 #AD.3.2    Level: 2    Role: D
 Verifique se os controles técnicos (redação do lado do cliente, filtros de contexto aprovados) removem automaticamente artefatos sensíveis.
 #AD.3.3    Level: 3    Role: D/V
 Verifique se os prompts e respostas são tokenizados, criptografados durante a transmissão e em repouso, e se os períodos de retenção estão em conformidade com a política de classificação de dados.

---

### AD.4 Validação de Código Gerado por IA

Detectar e corrigir vulnerabilidades introduzidas pela saída de IA antes que o código seja mesclado ou implantado.

 #AD.4.1    Level: 1    Role: D/V
 Verifique se o código gerado por IA está sempre sujeito à revisão humana de código.
 #AD.4.2    Level: 2    Role: D
 Verifique se os scanners automatizados (SAST/IAST/DAST) são executados em cada pull request contendo código gerado por IA e bloqueie as mesclagens em caso de descobertas críticas.
 #AD.4.3    Level: 3    Role: D/V
 Verifique se os testes diferenciais de fuzzing ou testes baseados em propriedades comprovam comportamentos críticos para a segurança (por exemplo, validação de entrada, lógica de autorização).

---

### AD.5 Explicabilidade e Rastreabilidade das Sugestões de Código

Fornecer aos auditores e desenvolvedores uma compreensão do motivo pelo qual uma sugestão foi feita e como ela evoluiu.

 #AD.5.1    Level: 1    Role: D/V
 Verifique se os pares de prompt/resposta estão registrados com IDs de commit.
 #AD.5.2    Level: 2    Role: D
 Verifique se os desenvolvedores podem exibir citações do modelo (trechos de treinamento, documentação) que apoiem uma sugestão.
 #AD.5.3    Level: 3    Role: D/V
 Verifique se os relatórios de explicabilidade são armazenados com os artefatos de design e referenciados nas revisões de segurança, satisfazendo os princípios de rastreabilidade da ISO/IEC 42001.

---

### AD.6 Feedback Contínuo e Ajuste Fino do Modelo

Melhore o desempenho de segurança do modelo ao longo do tempo enquanto previne o declínio negativo.

 #AD.6.1    Level: 1    Role: D/V
 Verifique se os desenvolvedores podem sinalizar sugestões inseguras ou não conformes, e se essas sinalizações são monitoradas.
 #AD.6.2    Level: 2    Role: D
 Verifique se o feedback agregado informa o ajuste fino periódico ou a geração aumentada por recuperação com corpora de codificação segura avaliados (por exemplo, OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verifique se um ambiente de avaliação em loop fechado executa testes de regressão após cada ajuste fino; os métricas de segurança devem atender ou superar as linhas de base anteriores antes da implantação.

---

#### Referências

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Apêndice E: Exemplos de Ferramentas e Frameworks

### Objetivo

Este capítulo fornece exemplos de ferramentas e frameworks que podem apoiar a implementação ou o cumprimento de um determinado requisito do AISVS. Estes não devem ser vistos como recomendações ou endossos pela equipe do AISVS ou pelo Projeto de Segurança GenAI da OWASP.

---

### AE.1 Governança de Dados de Treinamento e Gestão de Viés

Ferramentas usadas para análise de dados, governança e gerenciamento de viés.

 #AE.1.1    Section: 1.1
 Ferramentas de Inventário de Dados: Ferramentas de gestão de inventário de dados como...
 #AE.1.2    Section: 1.2
 Criptografia em Trânsito Use TLS para aplicações baseadas em HTTPS, com ferramentas como openSSL e o módulo ssl do Python`ssl`biblioteca.

---

### AE.2 Validação da Entrada do Usuário

Ferramentas para lidar e validar entradas de usuário.

 #AE.2.1    Section: 2.1
 Ferramentas de Defesa contra Injeção de Prompt: Use ferramentas de proteção como o NeMo da NVIDIA ou Guardrails AI.

---

