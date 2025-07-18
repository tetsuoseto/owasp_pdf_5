## Frontispício

### Sobre o Padrão

O Padrão de Verificação de Segurança em Inteligência Artificial (AISVS) é um catálogo orientado pela comunidade com requisitos de segurança que cientistas de dados, engenheiros de MLOps, arquitetos de software, desenvolvedores, testadores, profissionais de segurança, fornecedores de ferramentas, reguladores e consumidores podem usar para projetar, construir, testar e verificar sistemas e aplicações confiáveis habilitados por IA. Ele fornece uma linguagem comum para especificar controles de segurança ao longo do ciclo de vida da IA — desde a coleta de dados e desenvolvimento de modelos até a implantação e monitoramento contínuo — para que as organizações possam medir e melhorar a resiliência, a privacidade e a segurança de suas soluções de IA.

### Direitos Autorais e Licença

Versão 0.1 (Primeiro Rascunho Público - Trabalho em Andamento), 2025  

![license](images/license.png)
Direitos autorais © 2025 O Projeto AISVS.  

Lançado sob aCreative Commons Attribution‑ShareAlike 4.0 International License.
Para qualquer reutilização ou distribuição, você deve comunicar claramente os termos da licença deste trabalho a terceiros.

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

AISVS é um padrão totalmente novo criado especificamente para abordar os desafios únicos de segurança dos sistemas de inteligência artificial. Embora se inspire em melhores práticas de segurança mais amplas, cada requisito do AISVS foi desenvolvido do zero para refletir o cenário de ameaças da IA e ajudar as organizações a construir soluções de IA mais seguras e resilientes.

## Prefácio

Bem-vindo ao Padrão de Verificação de Segurança de Inteligência Artificial (AISVS) versão 1.0!

### Introdução

Estabelecida em 2025 por meio de um esforço colaborativo da comunidade, a AISVS define os requisitos de segurança a serem considerados ao projetar, desenvolver, implantar e operar modelos de IA modernos, pipelines e serviços habilitados por IA.

AISVS v1.0 representa o trabalho conjunto de seus líderes de projeto, grupo de trabalho e colaboradores da comunidade mais ampla para produzir uma linha de base pragmática e testável para a segurança de sistemas de IA.

Nosso objetivo com este lançamento é tornar o AISVS fácil de adotar, mantendo o foco rigoroso em seu escopo definido e abordando o cenário de riscos em rápida evolução, único para a IA.

### Objetivos Principais para a AISVS Versão 1.0

A versão 1.0 será criada com vários princípios orientadores.

#### Escopo Bem Definido

Cada requisito deve estar alinhado com o nome e a missão da AISVS:

Inteligência Artificial – Os controles operam na camada de IA/ML (dados, modelo, pipeline ou inferência) e são responsabilidade dos praticantes de IA.
Segurança – Os requisitos mitigam diretamente os riscos identificados de segurança, privacidade ou segurança.
Verificação – A linguagem é escrita de forma que a conformidade possa ser validada objetivamente.
Padrão – As seções seguem uma estrutura e terminologia consistentes para formar uma referência coerente.
​
---

Seguindo o AISVS, as organizações podem avaliar sistematicamente e fortalecer a postura de segurança de suas soluções de IA, promovendo uma cultura de engenharia de IA segura.

## Usando o AISVS

A Norma de Verificação de Segurança em Inteligência Artificial (AISVS) define requisitos de segurança para aplicações e serviços modernos de IA, focando em aspectos sob controle dos desenvolvedores de aplicações.

O AISVS destina-se a qualquer pessoa que desenvolva ou avalie a segurança de aplicações de IA, incluindo desenvolvedores, arquitetos, engenheiros de segurança e auditores. Este capítulo apresenta a estrutura e o uso do AISVS, incluindo seus níveis de verificação e casos de uso pretendidos.

### Níveis de Verificação de Segurança em Inteligência Artificial

O AISVS define três níveis crescentes de verificação de segurança. Cada nível adiciona profundidade e complexidade, permitindo que as organizações adaptem sua postura de segurança ao nível de risco de seus sistemas de IA.

As organizações podem começar no Nível 1 e progressivamente adotar níveis mais altos à medida que a maturidade de segurança e a exposição a ameaças aumentam.

#### Definição dos Níveis

Cada requisito na AISVS v1.0 é atribuído a um dos seguintes níveis:

 Requisitos de Nível 1

O Nível 1 inclui os requisitos de segurança mais críticos e fundamentais. Esses se concentram na prevenção de ataques comuns que não dependem de outras pré-condições ou vulnerabilidades. A maioria dos controles do Nível 1 é simples de implementar ou essencial o suficiente para justificar o esforço.

 Requisitos do Nível 2

O Nível 2 aborda ataques mais avançados ou menos comuns, bem como defesas em camadas contra ameaças generalizadas. Esses requisitos podem envolver lógica mais complexa ou visar pré-requisitos específicos de ataque.

 Requisitos de Nível 3

O Nível 3 inclui controles que geralmente são mais difíceis de implementar ou que se aplicam em situações específicas. Esses controles frequentemente representam mecanismos de defesa em profundidade ou mitigações contra ataques específicos, direcionados ou de alta complexidade.

#### Função (D/V)

Cada requisito AISVS é marcado de acordo com o público-alvo principal:

D – Requisitos focados no desenvolvedor
V – Requisitos focados no verificador/auditor
D/V – Relevante tanto para desenvolvedores quanto para verificadores

## Governança de Dados de Treinamento C1 e Gestão de Viés

### Objetivo de Controle

Os dados de treinamento devem ser obtidos, manipulados e mantidos de maneira que preserve a proveniência, segurança, qualidade e imparcialidade. Fazer isso cumpre obrigações legais e reduz os riscos de viés, envenenamento ou violações de privacidade ao longo do ciclo de vida da IA.

---

### C1.1 Procedência dos Dados de Treinamento

Mantenha um inventário verificável de todos os conjuntos de dados, aceite apenas fontes confiáveis e registre todas as alterações para auditoria.

 #1.1.1    Level: 1    Role: D/V
 Verifique se um inventário atualizado de todas as fontes de dados de treinamento (origem, responsável/proprietário, licença, método de coleta, restrições de uso pretendido e histórico de processamento) está sendo mantido.
 #1.1.2    Level: 1    Role: D/V
 Verifique se apenas conjuntos de dados avaliados quanto à qualidade, representatividade, origem ética e conformidade de licenciamento são permitidos, reduzindo os riscos de contaminação, viés incorporado e infração de propriedade intelectual.
 #1.1.3    Level: 1    Role: D/V
 Verifique se a minimização de dados está sendo aplicada para que atributos desnecessários ou sensíveis sejam excluídos.
 #1.1.4    Level: 2    Role: D/V
 Verifique se todas as alterações no conjunto de dados estão sujeitas a um fluxo de trabalho de aprovação registrado.
 #1.1.5    Level: 2    Role: D/V
 Verifique se a qualidade da rotulagem/anotação é garantida por meio de verificações cruzadas dos revisores ou consenso.
 #1.1.6    Level: 2    Role: D/V
 Verifique se "fichas de dados" ou "folhas de dados para conjuntos de dados" são mantidas para conjuntos de dados de treinamento significativos, detalhando características, motivações, composição, processos de coleta, pré-processamento e usos recomendados/não recomendados.

---

### C1.2 Segurança e Integridade dos Dados de Treinamento

Restringir o acesso, criptografar em repouso e em trânsito, e validar a integridade para impedir adulterações ou roubo.

 #1.2.1    Level: 1    Role: D/V
 Verifique se os controles de acesso protegem o armazenamento e os pipelines.
 #1.2.2    Level: 2    Role: D/V
 Verifique se os conjuntos de dados são criptografados durante a transmissão e, para todas as informações sensíveis ou pessoalmente identificáveis (PII), em repouso, utilizando algoritmos criptográficos padrão da indústria e práticas de gerenciamento de chaves.
 #1.2.3    Level: 2    Role: D/V
 Verifique se hashes criptográficos ou assinaturas digitais são usados para garantir a integridade dos dados durante o armazenamento e a transferência, e se técnicas automatizadas de detecção de anomalias são aplicadas para proteger contra modificações não autorizadas ou corrupção, incluindo tentativas direcionadas de envenenamento de dados.
 #1.2.4    Level: 3    Role: D/V
 Verifique se as versões do conjunto de dados são rastreadas para permitir rollback.
 #1.2.5    Level: 2    Role: D/V
 Verifique se os dados obsoletos são eliminados de forma segura ou anonimizados em conformidade com as políticas de retenção de dados, requisitos regulatórios e para reduzir a superfície de ataque.

---

### C1.3 Completude e Justiça da Representação

Detectar envies demográficos e aplicar mitigação para que as taxas de erro do modelo sejam equitativas entre os grupos.

 #1.3.1    Level: 1    Role: D/V
 Verifique se os conjuntos de dados são analisados quanto a desequilíbrios representacionais e possíveis vieses em atributos legalmente protegidos (por exemplo, raça, gênero, idade) e outras características eticamente sensíveis relevantes para o domínio de aplicação do modelo (por exemplo, status socioeconômico, localização).
 #1.3.2    Level: 2    Role: D/V
 Verifique se os vieses identificados são mitigados por meio de estratégias documentadas, como reequilíbrio, aumento de dados direcionado, ajustes algorítmicos (por exemplo, técnicas de pré-processamento, processamento durante o algoritmo, pós-processamento) ou reponderação, e avalie o impacto da mitigação tanto na equidade quanto no desempenho geral do modelo.
 #1.3.3    Level: 2    Role: D/V
 Verifique se as métricas de justiça pós-treinamento são avaliadas e documentadas.
 #1.3.4    Level: 3    Role: D/V
 Verifique se uma política de gerenciamento de viés do ciclo de vida designa responsáveis e uma cadência de revisão.

---

### C1.4 Qualidade, Integridade e Segurança da Rotulagem dos Dados de Treinamento

Proteja os rótulos com criptografia e exija revisão dupla para classes críticas.

 #1.4.1    Level: 2    Role: D/V
 Verifique se a qualidade da rotulagem/anotação é garantida por meio de diretrizes claras, verificações cruzadas por revisores, mecanismos de consenso (por exemplo, monitoramento do acordo entre anotadores) e processos definidos para resolver discrepâncias.
 #1.4.2    Level: 2    Role: D/V
 Verifique se hashes criptográficos ou assinaturas digitais são aplicados aos artefatos de rótulo para garantir sua integridade e autenticidade.
 #1.4.3    Level: 2    Role: D/V
 Verifique se as interfaces e plataformas de rotulagem aplicam controles de acesso rigorosos, mantêm registros de auditoria à prova de adulteração de todas as atividades de rotulagem e protegem contra modificações não autorizadas.
 #1.4.4    Level: 3    Role: D/V
 Verifique se os rótulos críticos para segurança, proteção ou equidade (por exemplo, identificação de conteúdo tóxico, descobertas médicas críticas) recebem revisão dupla independente obrigatória ou verificação robusta equivalente.
 #1.4.5    Level: 2    Role: D/V
 Verifique se as informações sensíveis (incluindo PII) capturadas inadvertidamente ou necessariamente presentes em etiquetas estão redigidas, pseudonimizadas, anonimizadas ou criptografadas em repouso e em trânsito, de acordo com os princípios de minimização de dados.
 #1.4.6    Level: 2    Role: D/V
 Verifique se os guias e instruções de rotulagem são abrangentes, controlados por versão e revisados por pares.
 #1.4.7    Level: 2    Role: D/V
 Verifique se os esquemas de dados (incluindo para etiquetas) estão claramente definidos e controlados por versão.
 #1.8.2    Level: 2    Role: D/V
 Verifique se os fluxos de trabalho de rotulagem terceirizados ou baseados em crowdsourcing incluem salvaguardas técnicas/procedimentais para garantir a confidencialidade dos dados, integridade, qualidade dos rótulos e evitar vazamento de dados.

---

### C1.5 Garantia da Qualidade dos Dados de Treinamento

Combine validação automatizada, verificações manuais pontuais e correção registrada para garantir a confiabilidade do conjunto de dados.

 #1.5.1    Level: 1    Role: D
 Verifique se os testes automatizados detectam erros de formato, valores nulos e distorções de rótulos em cada ingestão ou transformação significativa.
 #1.5.2    Level: 1    Role: D/V
 Verifique se os conjuntos de dados com falha estão em quarentena com trilhas de auditoria.
 #1.5.3    Level: 2    Role: V
 Verifique se as verificações pontuais manuais realizadas por especialistas na área cobrem uma amostra estatisticamente significativa (por exemplo, ≥1% ou 1.000 amostras, o que for maior, ou conforme determinado pela avaliação de risco) para identificar questões sutis de qualidade que não foram detectadas pela automação.
 #1.5.4    Level: 2    Role: D/V
 Verifique se as etapas de remediação estão anexadas aos registros de procedência.
 #1.5.5    Level: 2    Role: D/V
 Verifique se os controles de qualidade bloqueiam conjuntos de dados abaixo do padrão, a menos que exceções sejam aprovadas.

---

### C1.6 Detecção de Envenenamento de Dados

Aplicar a detecção estatística de anomalias e fluxos de trabalho de quarentena para impedir inserções adversariais.

 #1.6.1    Level: 2    Role: D/V
 Verifique se as técnicas de detecção de anomalias (por exemplo, métodos estatísticos, detecção de outliers, análise de embeddings) são aplicadas aos dados de treinamento na ingestão e antes das principais execuções de treinamento para identificar possíveis ataques de envenenamento ou corrupção de dados não intencional.
 #1.6.2    Level: 2    Role: D/V
 Verifique se as amostras sinalizadas acionam uma revisão manual antes do treinamento.
 #1.6.3    Level: 2    Role: V
 Verifique se os resultados alimentam o dossiê de segurança do modelo e informam a inteligência contínua de ameaças.
 #1.6.4    Level: 3    Role: D/V
 Verifique se a lógica de detecção foi atualizada com novas informações de ameaças.
 #1.6.5    Level: 3    Role: D/V
 Verifique se os pipelines de aprendizado online monitoram a deriva de distribuição.
 #1.6.6    Level: 3    Role: D/V
 Verifique se defesas específicas contra tipos conhecidos de ataques de envenenamento de dados (por exemplo, inversão de rótulos, inserção de gatilho de backdoor, ataques por instância influente) são consideradas e implementadas com base no perfil de risco do sistema e nas fontes de dados.

---

### C1.7 Exclusão de Dados do Usuário e Aplicação do Consentimento

Atenda aos pedidos de exclusão e retirada de consentimento em todos os conjuntos de dados, backups e artefatos derivados.

 #1.7.1    Level: 1    Role: D/V
 Verifique se os fluxos de trabalho de exclusão eliminam dados primários e derivados e avalie o impacto no modelo, assegurando que o impacto nos modelos afetados seja avaliado e, se necessário, tratado (por exemplo, por meio de re-treinamento ou recalibração).
 #1.7.2    Level: 2    Role: D
 Verifique se existem mecanismos para rastrear e respeitar o escopo e o status do consentimento do usuário (e retiradas) para dados usados no treinamento, e se o consentimento é validado antes que os dados sejam incorporados em novos processos de treinamento ou atualizações significativas do modelo.
 #1.7.3    Level: 2    Role: V
 Verifique se os fluxos de trabalho são testados anualmente e registrados.

---

### C1.8 Segurança da Cadeia de Suprimentos

Avalie os provedores externos de dados e verifique a integridade por meio de canais autenticados e criptografados.

 #1.8.1    Level: 2    Role: D/V
 Verifique se os fornecedores de dados de terceiros, incluindo provedores de modelos pré-treinados e conjuntos de dados externos, passam por uma análise criteriosa de segurança, privacidade, obtenção ética e qualidade dos dados antes que seus dados ou modelos sejam integrados.
 #1.8.2    Level: 1    Role: D
 Verifique se as transferências externas utilizam TLS/autenticação e verificações de integridade.
 #1.8.3    Level: 2    Role: D/V
 Verifique se fontes de dados de alto risco (por exemplo, conjuntos de dados de código aberto com proveniência desconhecida, fornecedores não avaliados) recebem escrutínio ampliado, como análise em ambiente isolado, verificações extensivas de qualidade/viés e detecção direcionada de envenenamento, antes de serem usadas em aplicações sensíveis.
 #1.8.4    Level: 3    Role: D/V
 Verifique se os modelos pré-treinados obtidos de terceiros são avaliados quanto a vieses embutidos, possíveis backdoors, integridade de sua arquitetura e a proveniência dos dados originais de treinamento antes do ajuste fino ou implantação.

---

### C1.9 Detecção de Amostras Adversariais

Implemente medidas durante a fase de treinamento, como treinamento adversarial, para aumentar a resiliência do modelo contra exemplos adversariais.

 #1.9.1    Level: 3    Role: D/V
 Verifique se defesas apropriadas, como treinamento adversarial (usando exemplos adversariais gerados), aumento de dados com entradas perturbadas ou técnicas de otimização robusta, estão implementadas e ajustadas para os modelos relevantes com base na avaliação de risco.
 #1.9.2    Level: 2    Role: D/V
 Verifique se, caso o treinamento adversarial seja utilizado, a geração, o gerenciamento e o versionamento dos conjuntos de dados adversariais estão documentados e controlados.
 #1.9.3    Level: 3    Role: D/V
 Verifique se o impacto do treinamento de robustez adversarial no desempenho do modelo (tanto contra entradas limpas quanto adversariais) e nas métricas de equidade é avaliado, documentado e monitorado.
 #1.9.4    Level: 3    Role: D/V
 Verifique se as estratégias para treinamento adversarial e robustez são periodicamente revisadas e atualizadas para combater as técnicas evolutivas de ataque adversarial.

---

### C1.10 Linhagem e Rastreabilidade de Dados

Acompanhe toda a jornada de cada ponto de dados desde a fonte até a entrada do modelo para auditoria e resposta a incidentes.

 #1.10.1    Level: 2    Role: D/V
 Verifique se a origem de cada ponto de dado, incluindo todas as transformações, aumentos e fusões, está registrada e pode ser reconstruída.
 #1.10.2    Level: 2    Role: D/V
 Verifique se os registros de linhagem são imutáveis, armazenados de forma segura e acessíveis para auditorias ou investigações.
 #1.10.3    Level: 2    Role: D/V
 Verifique se o acompanhamento de linhagem abrange tanto dados brutos quanto dados sintéticos.

---

### C1.11 Gestão de Dados Sintéticos

Garanta que os dados sintéticos sejam devidamente gerenciados, rotulados e avaliados quanto aos riscos.

 #1.11.1    Level: 2    Role: D/V
 Verifique se todos os dados sintéticos estão claramente rotulados e distinguíveis dos dados reais em todo o pipeline.
 #1.11.2    Level: 2    Role: D/V
 Verifique se o processo de geração, parâmetros e uso pretendido dos dados sintéticos estão documentados.
 #1.11.3    Level: 2    Role: D/V
 Verifique se os dados sintéticos são avaliados quanto a riscos de viés, vazamento de privacidade e problemas de representatividade antes de serem usados no treinamento.

---

### C1.12 Monitoramento de Acesso a Dados e Detecção de Anomalias

Monitorar e alertar sobre acessos incomuns aos dados de treinamento para detectar ameaças internas ou exfiltração.

 #1.12.1    Level: 2    Role: D/V
 Verifique se todo o acesso aos dados de treinamento está registrado, incluindo usuário, horário e ação.
 #1.12.2    Level: 2    Role: D/V
 Verifique se os logs de acesso são revisados regularmente para identificar padrões incomuns, como grandes exportações ou acesso a partir de novos locais.
 #1.12.3    Level: 2    Role: D/V
 Verifique se os alertas são gerados para eventos de acesso suspeitos e investigados prontamente.

---

### C1.13 Políticas de Retenção e Expiração de Dados

Defina e aplique períodos de retenção de dados para minimizar o armazenamento desnecessário de dados.

 #1.13.1    Level: 1    Role: D/V
 Verifique se períodos de retenção explícitos estão definidos para todos os conjuntos de dados de treinamento.
 #1.13.2    Level: 2    Role: D/V
 Verifique se os conjuntos de dados são automaticamente expirados, excluídos ou revisados para exclusão ao final de seu ciclo de vida.
 #1.13.3    Level: 2    Role: D/V
 Verifique se as ações de retenção e exclusão são registradas e auditáveis.

---

### C1.14 Conformidade Regulamentar e Jurisdicional

Garanta que todos os dados de treinamento estejam em conformidade com as leis e regulamentos aplicáveis.

 #1.14.1    Level: 2    Role: D/V
 Verifique se os requisitos de residência de dados e transferência transfronteiriça são identificados e aplicados para todos os conjuntos de dados.
 #1.14.2    Level: 2    Role: D/V
 Verifique se as regulamentações específicas do setor (por exemplo, saúde, finanças) são identificadas e tratadas no manejo dos dados.
 #1.14.3    Level: 2    Role: D/V
 Verifique se a conformidade com as leis de privacidade relevantes (por exemplo, GDPR, CCPA) está documentada e é revisada regularmente.

---

### C1.15 Marcação de Água e Marcação Digital de Dados

Detectar reutilização não autorizada ou vazamento de dados proprietários ou sensíveis.

 #1.15.1    Level: 3    Role: D/V
 Verifique se os conjuntos de dados ou subconjuntos estão marcados com marca d'água ou possuem impressão digital quando viável.
 #1.15.2    Level: 3    Role: D/V
 Verifique se os métodos de marca d'água/impressão digital não introduzem viés ou riscos de privacidade.
 #1.15.3    Level: 3    Role: D/V
 Verifique se são realizados controles periódicos para detectar o uso não autorizado ou vazamento de dados com marca d'água.

---

### C1.16 Gestão dos Direitos do Titular dos Dados

Apoiar os direitos do titular dos dados, como acesso, retificação, restrição e objeção.

 #1.16.1    Level: 2    Role: D/V
 Verifique se existem mecanismos para responder a solicitações dos titulares de dados para acesso, retificação, restrição ou objeção.
 #1.16.2    Level: 2    Role: D/V
 Verifique se as solicitações são registradas, monitoradas e atendidas dentro dos prazos legalmente exigidos.
 #1.16.3    Level: 2    Role: D/V
 Verifique se os processos relacionados aos direitos dos titulares de dados são testados e revisados regularmente quanto à sua eficácia.

---

### C1.17 Análise do Impacto da Versão do Conjunto de Dados

Avalie o impacto das alterações no conjunto de dados antes de atualizar ou substituir as versões.

 #1.17.1    Level: 2    Role: D/V
 Verifique se uma análise de impacto é realizada antes de atualizar ou substituir uma versão do conjunto de dados, abrangendo desempenho do modelo, equidade e conformidade.
 #1.17.2    Level: 2    Role: D/V
 Verifique se os resultados da análise de impacto estão documentados e revisados pelos stakeholders relevantes.
 #1.17.3    Level: 2    Role: D/V
 Verifique se existem planos de reversão caso novas versões introduzam riscos inaceitáveis ou regressões.

---

### C1.18 Segurança da Força de Trabalho de Anotação de Dados

Garantir a segurança e integridade do pessoal envolvido na anotação de dados.

 #1.18.1    Level: 2    Role: D/V
 Verifique se todo o pessoal envolvido na anotação de dados foi submetido a verificação de antecedentes e treinado em segurança e privacidade de dados.
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

A validação robusta da entrada do usuário é uma defesa de primeira linha contra alguns dos ataques mais prejudiciais a sistemas de IA. Ataques de injeção de prompt podem sobrescrever instruções do sistema, vazar dados sensíveis ou direcionar o modelo para comportamentos não permitidos. A menos que filtros dedicados e hierarquias de instruções estejam implementados, pesquisas mostram que "jailbreaks" de múltiplos disparos que exploram janelas de contexto muito longas serão eficazes. Além disso, ataques sutis de perturbação adversarial — como trocas de homoglifos ou leetspeak — podem alterar silenciosamente as decisões de um modelo.

---

### C2.1 Defesa contra Injeção de Prompt

A injeção de prompt é um dos principais riscos para sistemas de IA. As defesas contra essa tática utilizam uma combinação de filtros de padrões estáticos, classificadores dinâmicos e aplicação da hierarquia de instruções.

 #2.1.1    Level: 1    Role: D/V
 Verifique se as entradas do usuário são filtradas contra uma biblioteca continuamente atualizada de padrões conhecidos de injeção de prompt (palavras-chave de jailbreak, "ignorar anterior", cadeias de interpretação de papéis, ataques indiretos via HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Verifique se o sistema aplica uma hierarquia de instruções na qual as mensagens do sistema ou do desenvolvedor substituem as instruções do usuário, mesmo após a expansão da janela de contexto.
 #2.1.3    Level: 2    Role: D/V
 Verifique se os testes de avaliação adversarial (por exemplo, prompts "many-shot" da Equipe Vermelha) são realizados antes de cada lançamento de modelo ou template de prompt, com limites de taxa de sucesso e bloqueadores automáticos para regressões.
 #2.1.4    Level: 2    Role: D
 Verifique se os prompts originados de conteúdo de terceiros (páginas da web, PDFs, e-mails) são higienizados em um contexto de análise isolado antes de serem concatenados ao prompt principal.
 #2.1.5    Level: 3    Role: D/V
 Verifique se todas as atualizações das regras de filtro de prompt, versões dos modelos classificadores e alterações na lista de bloqueio são controladas por versão e auditáveis.

---

### C2.2 Resistência a Exemplos Adversariais

Modelos de Processamento de Linguagem Natural (PLN) ainda são vulneráveis a perturbações sutis a nível de caracteres ou palavras que humanos frequentemente não percebem, mas que os modelos tendem a classificar incorretamente.

 #2.2.1    Level: 1    Role: D
 Verifique se as etapas básicas de normalização de entrada (NFC Unicode, mapeamento de homoglifos, remoção de espaços em branco) são executadas antes da tokenização.
 #2.2.2    Level: 2    Role: D/V
 Verifique se a detecção de anomalias estatísticas sinaliza entradas com distância de edição incomumente alta em relação às normas linguísticas, tokens repetidos excessivamente ou distâncias anormais de incorporação.
 #2.2.3    Level: 2    Role: D
 Verifique se o pipeline de inferência suporta variantes de modelos fortalecidos com treinamento adversarial opcional ou camadas de defesa (por exemplo, randomização, destilação defensiva) para pontos de extremidade de alto risco.
 #2.2.4    Level: 2    Role: V
 Verifique se as entradas adversariais suspeitas estão em quarentena, registradas com as cargas completas (após a redação de informações pessoais identificáveis - PII).
 #2.2.5    Level: 3    Role: D/V
 Verifique se as métricas de robustez (taxa de sucesso dos conjuntos de ataques conhecidos) são monitoradas ao longo do tempo e se as regressões desencadeiam um bloqueio de lançamento.

---

### C2.3 Validação de Esquema, Tipo e Comprimento

Ataques de IA envolvendo entradas malformadas ou superdimensionadas podem causar erros de análise, vazamento de prompts entre campos e esgotamento de recursos. A aplicação rigorosa de esquemas também é um pré-requisito ao realizar chamadas determinísticas de ferramentas.

 #2.3.1    Level: 1    Role: D
 Verifique se todo endpoint de API ou chamada de função define um esquema de entrada explícito (JSON Schema, Protobuf ou equivalente multimodal) e que as entradas são validadas antes da montagem do prompt.
 #2.3.2    Level: 1    Role: D/V
 Verifique se entradas que excedem os limites máximos de tokens ou bytes são rejeitadas com um erro seguro e nunca truncadas silenciosamente.
 #2.3.3    Level: 2    Role: D/V
 Verifique se as verificações de tipo (por exemplo, faixas numéricas, valores de enumeração, tipos MIME para imagens/áudio) são aplicadas no lado do servidor, e não apenas no código cliente.
 #2.3.4    Level: 2    Role: D
 Verifique se os validadores semânticos (por exemplo, JSON Schema) operam em tempo constante para prevenir ataques DoS algorítmicos.
 #2.3.5    Level: 3    Role: V
 Verifique se as falhas de validação são registradas com trechos de carga útil redigidos e códigos de erro inequívocos para auxiliar na triagem de segurança.

---

### C2.4 Triagem de Conteúdo e Política

Os desenvolvedores devem ser capazes de detectar prompts sintaticamente válidos que solicitem conteúdo proibido (como instruções ilícitas, discurso de ódio e texto protegido por direitos autorais) e, em seguida, impedir sua propagação.

 #2.4.1    Level: 1    Role: D
 Verifique se um classificador de conteúdo (zero shot ou ajustado) avalia cada entrada para violência, automutilação, ódio, conteúdo sexual e pedidos ilegais, com limites configuráveis.
 #2.4.2    Level: 1    Role: D/V
 Verifique se as entradas que violam as políticas receberão recusas padronizadas ou conclusões seguras para que não sejam propagadas para chamadas LLM subsequentes.
 #2.4.3    Level: 2    Role: D
 Verifique se o modelo de triagem ou conjunto de regras é re-treinado/atualizado pelo menos trimestralmente, incorporando padrões recém-observados de jailbreak ou de bypass de políticas.
 #2.4.4    Level: 2    Role: D
 Verifique se a triagem respeita as políticas específicas do usuário (idade, restrições legais regionais) por meio de regras baseadas em atributos resolvidas no momento da solicitação.
 #2.4.5    Level: 3    Role: V
 Verifique se os registros de triagem incluem pontuações de confiança do classificador e tags de categoria de política para correlação SOC e reprodução futura em exercícios de red team.

---

### C2.5 Limitação da Taxa de Entrada e Prevenção de Abuso

Os desenvolvedores devem prevenir abusos, exaustão de recursos e ataques automatizados contra sistemas de IA, limitando as taxas de entrada e detectando padrões de uso anômalos.

 #2.5.1    Level: 1    Role: D/V
 Verifique se os limites de taxa por usuário, por IP e por chave de API são aplicados para todos os pontos finais de entrada.
 #2.5.2    Level: 2    Role: D/V
 Verifique se os limites de taxa de burst e de taxa sustentada estão ajustados para prevenir ataques DoS e de força bruta.
 #2.5.3    Level: 2    Role: D/V
 Verifique se padrões de uso anômalos (por exemplo, solicitações em rápida sucessão, inundação de entradas) acionam bloqueios automáticos ou escalonamentos.
 #2.5.4    Level: 3    Role: V
 Verifique se os registros de prevenção de abuso são mantidos e revisados para identificar padrões emergentes de ataque.

---

### C2.6 Validação de Entrada Multi-Modal

Os sistemas de IA devem incluir validação robusta para entradas não textuais (imagens, áudio, arquivos) para prevenir injeção, evasão ou abuso de recursos.

 #2.6.1    Level: 1    Role: D
 Verifique se todas as entradas que não são texto (imagens, áudio, arquivos) são validadas quanto ao tipo, tamanho e formato antes do processamento.
 #2.6.2    Level: 2    Role: D/V
 Verifique se os arquivos são verificados quanto a malware e cargas úteis esteganográficas antes da ingestão.
 #2.6.3    Level: 2    Role: D/V
 Verifique se as entradas de imagem/áudio são verificadas quanto a perturbações adversariais ou padrões de ataque conhecidos.
 #2.6.4    Level: 3    Role: V
 Verifique se as falhas na validação de entrada multimodal são registradas e disparam alertas para investigação.

---

### C2.7 Proveniência e Atribuição da Entrada

Sistemas de IA devem suportar auditoria, rastreamento de abuso e conformidade monitorando e etiquetando as origens de todas as entradas dos usuários.

 #2.7.1    Level: 1    Role: D/V
 Verifique se todas as entradas do usuário são marcadas com metadados (ID do usuário, sessão, origem, carimbo de data/hora, endereço IP) no momento da ingestão.
 #2.7.2    Level: 2    Role: D/V
 Verifique se os metadados de proveniência são mantidos e auditáveis para todas as entradas processadas.
 #2.7.3    Level: 2    Role: D/V
 Verifique se fontes de entrada anômalas ou não confiáveis são sinalizadas e sujeitas a escrutínio aprimorado ou bloqueio.

---

### C2.8 Detecção Adaptativa de Ameaças em Tempo Real

Os desenvolvedores devem empregar sistemas avançados de detecção de ameaças para IA que se adaptem a novos padrões de ataque e ofereçam proteção em tempo real com correspondência de padrões compilados.

 #2.8.1    Level: 1    Role: D/V
 Verifique se os padrões de detecção de ameaças são compilados em mecanismos regex otimizados para filtragem em tempo real de alto desempenho, com impacto mínimo na latência.
 #2.8.2    Level: 1    Role: D/V
 Verifique se os sistemas de detecção de ameaças mantêm bibliotecas de padrões separadas para diferentes categorias de ameaças (injeção de comandos, conteúdo prejudicial, dados sensíveis, comandos do sistema).
 #2.8.3    Level: 2    Role: D/V
 Verifique se a detecção adaptativa de ameaças incorpora modelos de aprendizado de máquina que atualizam a sensibilidade à ameaça com base na frequência e nas taxas de sucesso dos ataques.
 #2.8.4    Level: 2    Role: D/V
 Verifique se os feeds de inteligência de ameaças em tempo real atualizam automaticamente as bibliotecas de padrões com novas assinaturas de ataque e IOCs (Indicadores de Comprometimento).
 #2.8.5    Level: 3    Role: D/V
 Verifique se as taxas de falsos positivos na detecção de ameaças são monitoradas continuamente e se a especificidade do padrão é ajustada automaticamente para minimizar a interferência em casos de uso legítimos.
 #2.8.6    Level: 3    Role: D/V
 Verifique se a análise contextual de ameaças considera a fonte de entrada, os padrões de comportamento do usuário e o histórico da sessão para melhorar a precisão da detecção.
 #2.8.7    Level: 3    Role: D/V
 Verifique se as métricas de desempenho da detecção de ameaças (taxa de detecção, latência de processamento, utilização de recursos) são monitoradas e otimizadas em tempo real.

---

### C2.9 Pipeline de Validação de Segurança Multimodal

Os desenvolvedores devem fornecer validação de segurança para texto, imagem, áudio e outras modalidades de entrada de IA com tipos específicos de detecção de ameaças e isolamento de recursos.

 #2.9.1    Level: 1    Role: D/V
 Verifique se cada modalidade de entrada possui validadores de segurança dedicados com padrões de ameaça documentados (texto: injeção de prompt, imagens: esteganografia, áudio: ataques por espectrograma) e limites de detecção.
 #2.9.2    Level: 2    Role: D/V
 Verifique se as entradas multimodais são processadas em sandboxes isolados com limites de recursos definidos (memória, CPU, tempo de processamento) específicos para cada tipo de modalidade e documentados nas políticas de segurança.
 #2.9.3    Level: 2    Role: D/V
 Verifique se a detecção de ataques cross-modal identifica ataques coordenados abrangendo múltiplos tipos de entrada (por exemplo, cargas úteis esteganográficas em imagens combinadas com injeção de comandos em texto) por meio de regras de correlação e geração de alertas.
 #2.9.4    Level: 3    Role: D/V
 Verifique se as falhas de validação multimodal acionam o registro detalhado, incluindo todas as modalidades de entrada, resultados da validação, pontuações de ameaça e análise de correlação com formatos de log estruturados para integração SIEM.
 #2.9.5    Level: 3    Role: D/V
 Verifique se os classificadores de conteúdo específicos por modalidade são atualizados conforme os cronogramas documentados (mínimo trimestralmente) com novos padrões de ameaça, exemplos adversariais e benchmarks de desempenho mantidos acima dos limiares básicos.

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

Os sistemas de IA devem implementar processos de controle de mudanças que impedem modificações não autorizadas ou inseguras no modelo de chegarem à produção. Esse controle garante a integridade do modelo durante todo o ciclo de vida — desde o desenvolvimento, passando pela implantação, até a desativação — o que possibilita uma resposta rápida a incidentes e mantém a responsabilidade por todas as alterações.

Objetivo Principal de Segurança: Apenas modelos autorizados e validados chegam à produção, por meio da aplicação de processos controlados que mantêm a integridade, rastreabilidade e recuperabilidade.

---

### C3.1 Autorização e Integridade do Modelo

Apenas modelos autorizados com integridade verificada alcançam ambientes de produção.

 #3.1.1    Level: 1    Role: D/V
 Verifique se todos os artefatos do modelo (pesos, configurações, tokenizadores) estão assinados criptograficamente por entidades autorizadas antes da implantação.
 #3.1.2    Level: 1    Role: D/V
 Verifique se a integridade do modelo é validada no momento da implantação e se as falhas na verificação da assinatura impedem o carregamento do modelo.
 #3.1.3    Level: 2    Role: D/V
 Verifique se os registros de proveniência do modelo incluem a identidade da entidade autorizadora, checksums dos dados de treinamento, resultados dos testes de validação com status de aprovação/reprovação e um carimbo de data/hora de criação.
 #3.1.4    Level: 2    Role: D/V
 Verifique se todos os artefatos do modelo usam versionamento semântico (MAJOR.MINOR.PATCH) com critérios documentados especificando quando cada componente da versão deve ser incrementado.
 #3.1.5    Level: 2    Role: V
 Verifique se o rastreamento de dependências mantém um inventário em tempo real que permite a rápida identificação de todos os sistemas consumidores.

---

### C3.2 Validação e Testes do Modelo

Os modelos devem passar por validações definidas de segurança e proteção antes da implantação.

 #3.2.1    Level: 1    Role: D/V
 Verifique se os modelos passam por testes automatizados de segurança que incluem validação de entrada, sanitização de saída e avaliações de segurança com limites de aprovação/reprovação previamente acordados pela organização antes do deployment.
 #3.2.2    Level: 1    Role: D/V
 Verifique que as falhas de validação bloqueiem automaticamente a implantação do modelo após a aprovação explícita de anulação por pessoal autorizado previamente designado, com justificativas comerciais documentadas.
 #3.2.3    Level: 2    Role: V
 Verifique se os resultados do teste são assinados criptograficamente e vinculados de forma imutável ao hash da versão específica do modelo que está sendo validado.
 #3.2.4    Level: 2    Role: D/V
 Verifique se as implantações de emergência exigem avaliação documentada de risco de segurança e aprovação por uma autoridade de segurança pré-designada dentro de prazos pré-acordados.

---

### C3.3 Implantação Controlada e Reversão

As implantações de modelos devem ser controladas, monitoradas e reversíveis.

 #3.3.1    Level: 1    Role: D
 Verifique se as implantações em produção implementam mecanismos de lançamento gradual (implantações canário, implantações azul-verde) com gatilhos automatizados de reversão baseados em taxas de erro pré-acordadas, limites de latência ou critérios de alerta de segurança.
 #3.3.2    Level: 1    Role: D/V
 Verifique se as capacidades de reversão restauram o estado completo do modelo (pesos, configurações, dependências) de forma atômica dentro de janelas de tempo organizacionais pré-definidas.
 #3.3.3    Level: 2    Role: D/V
 Verifique se os processos de implantação validam assinaturas criptográficas e calculam checksums de integridade antes da ativação do modelo, falhando a implantação em caso de qualquer divergência.
 #3.3.4    Level: 2    Role: D/V
 Verifique se as capacidades de desligamento de emergência do modelo podem desativar pontos finais do modelo dentro dos tempos de resposta pré-definidos por meio de disjuntores automáticos ou interruptores manuais.
 #3.3.5    Level: 2    Role: V
 Verifique se os artefatos de rollback (versões anteriores do modelo, configurações, dependências) são mantidos conforme as políticas organizacionais, utilizando armazenamento imutável para resposta a incidentes.

---

### C3.4 Mudança de Responsabilidade e Auditoria

Todas as alterações no ciclo de vida do modelo devem ser rastreáveis e auditáveis.

 #3.4.1    Level: 1    Role: V
 Verifique se todas as alterações no modelo (implantação, configuração, aposentadoria) geram registros de auditoria imutáveis, incluindo um carimbo de data/hora, uma identidade autenticada do ator, um tipo de alteração e os estados antes/depois.
 #3.4.2    Level: 2    Role: D/V
 Verifique se o acesso ao registro de auditoria requer autorização apropriada e se todas as tentativas de acesso são registradas com a identidade do usuário e um carimbo de data/hora.
 #3.4.3    Level: 2    Role: D/V
 Verifique se os modelos de prompt e as mensagens do sistema estão sob controle de versão em repositórios git, com revisão de código obrigatória e aprovação dos revisores designados antes da implantação.
 #3.4.4    Level: 2    Role: V
 Verifique se os registros de auditoria incluem detalhes suficientes (hashes de modelo, instantâneos de configuração, versões de dependências) para permitir a reconstrução completa do estado do modelo para qualquer data e hora dentro do período de retenção.

---

### C3.5 Práticas Seguras de Desenvolvimento

Os processos de desenvolvimento e treinamento de modelos devem seguir práticas seguras para evitar comprometimentos.

 #3.5.1    Level: 1    Role: D
 Verifique se os ambientes de desenvolvimento, teste e produção do modelo estão separados fisicamente ou logicamente. Eles não compartilham infraestrutura, possuem controles de acesso distintos e armazenamentos de dados isolados.
 #3.5.2    Level: 1    Role: D
 Verifique se o treinamento e o ajuste fino do modelo ocorrem em ambientes isolados com acesso controlado à rede.
 #3.5.3    Level: 1    Role: D/V
 Verifique se as fontes de dados de treinamento são validadas por meio de verificações de integridade e autenticadas por fontes confiáveis com cadeia de custódia documentada antes de serem usadas no desenvolvimento do modelo.
 #3.5.4    Level: 2    Role: D
 Verifique se os artefatos de desenvolvimento do modelo (hiperparâmetros, scripts de treinamento, arquivos de configuração) estão armazenados no controle de versão e exigem aprovação da revisão por pares antes de serem usados no treinamento.

---

### C3.6 Aposentadoria e Descomissionamento do Modelo

Os modelos devem ser desativados de forma segura quando não forem mais necessários ou quando forem identificados problemas de segurança.

 #3.6.1    Level: 1    Role: D
 Verifique se os processos de aposentadoria de modelos escaneiam automaticamente os gráficos de dependência, identificam todos os sistemas consumidores e fornecem períodos de aviso prévio previamente acordados antes da desativação.
 #3.6.2    Level: 1    Role: D/V
 Verifique se os artefatos de modelos aposentados são apagados de forma segura usando apagamento criptográfico ou sobrescrição múltipla, de acordo com as políticas documentadas de retenção de dados, com certificados de destruição verificados.
 #3.6.3    Level: 2    Role: V
 Verifique se os eventos de aposentadoria do modelo são registrados com carimbo de data/hora e identidade do ator, e se as assinaturas do modelo são revogadas para evitar reutilização.
 #3.6.4    Level: 2    Role: D/V
 Verifique se a aposentadoria de modelo de emergência pode desabilitar o acesso ao modelo dentro dos prazos preestabelecidos de resposta a emergências por meio de interrupções automáticas caso vulnerabilidades críticas de segurança sejam descobertas.

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

## Infraestrutura C4, Segurança de Configuração e Implantação

### Objetivo de Controle

A infraestrutura de IA deve ser reforçada contra escalonamento de privilégios, adulteração da cadeia de suprimentos e movimentação lateral por meio de configuração segura, isolamento em tempo de execução, pipelines de implantação confiáveis e monitoramento abrangente. Apenas componentes e configurações de infraestrutura autorizados e validados chegam à produção por meio de processos controlados que mantêm a segurança, integridade e auditabilidade.

Objetivo Principal de Segurança: Apenas componentes de infraestrutura assinados criptograficamente e escaneados quanto a vulnerabilidades chegam à produção por meio de pipelines de validação automatizados que aplicam políticas de segurança e mantêm trilhas de auditoria imutáveis.

---

### C4.1 Isolamento do Ambiente de Execução

Prevenir fugas de contêineres e escalonamento de privilégios por meio de primitivas de isolamento em nível de kernel e controles de acesso obrigatórios.

 #4.1.1    Level: 1    Role: D/V
 Verifique se todos os contêineres de IA descartam TODAS as capacidades do Linux, exceto CAP_SETUID, CAP_SETGID e as capacidades explicitamente exigidas documentadas nas linhas de base de segurança.
 #4.1.2    Level: 1    Role: D/V
 Verifique se os perfis seccomp bloqueiam todas as chamadas de sistema, exceto aquelas nas listas de permissões pré-aprovadas, com violações que encerram o contêiner e geram alertas de segurança.
 #4.1.3    Level: 2    Role: D/V
 Verifique se as cargas de trabalho de IA são executadas com sistemas de arquivos raiz somente leitura, tmpfs para dados temporários e volumes nomeados para dados persistentes, com opções de montagem noexec aplicadas.
 #4.1.4    Level: 2    Role: D/V
 Verifique se o monitoramento em tempo de execução baseado em eBPF (Falco, Tetragon ou equivalente) detecta tentativas de escalonamento de privilégios e encerra automaticamente os processos infratores dentro dos requisitos de tempo de resposta organizacional.
 #4.1.5    Level: 3    Role: D/V
 Verifique se as cargas de trabalho de IA de alto risco são executadas em ambientes isolados por hardware (Intel TXT, AMD SVM ou nós bare-metal dedicados) com verificação de atestado.

---

### C4.2 Pipelines Seguras de Construção e Implantação

Garanta a integridade criptográfica e a segurança da cadeia de suprimentos por meio de builds reprodutíveis e artefatos assinados.

 #4.2.1    Level: 1    Role: D/V
 Verifique se a infraestrutura como código é analisada com ferramentas (tfsec, Checkov ou Terrascan) a cada commit, bloqueando merges com achados de gravidade CRÍTICA ou ALTA.
 #4.2.2    Level: 1    Role: D/V
 Verifique se as construções de contêineres são reproduzíveis com hashes SHA256 idênticos entre as construções e gere atestações de proveniência SLSA Nível 3 assinadas com Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Verifique se as imagens de contêiner incorporam SBOMs CycloneDX ou SPDX e estão assinadas com Cosign antes do envio ao registro, rejeitando imagens não assinadas na implantação.
 #4.2.4    Level: 2    Role: D/V
 Verifique se os pipelines de CI/CD utilizam tokens OIDC do HashiCorp Vault, funções IAM da AWS ou Identidade Gerenciada do Azure com tempos de vida que não excedam os limites da política de segurança organizacional.
 #4.2.5    Level: 2    Role: D/V
 Verifique se as assinaturas Cosign e a proveniência SLSA são validadas durante o processo de implantação antes da execução do contêiner e se erros de verificação causam falha na implantação.
 #4.2.6    Level: 2    Role: D/V
 Verifique se os ambientes de build são executados em contêineres ou máquinas virtuais efêmeros, sem armazenamento persistente e com isolamento de rede em relação às VPCs de produção.

---

### C4.3 Segurança de Rede e Controle de Acesso

Implemente a rede de confiança zero com políticas de negação padrão e comunicações criptografadas.

 #4.3.1    Level: 1    Role: D/V
 Verifique se as NetworkPolicies do Kubernetes ou qualquer equivalente implementam negação padrão de entrada/saída com regras explícitas de permissão para as portas necessárias (443, 8080, etc.).
 #4.3.2    Level: 1    Role: D/V
 Verifique se SSH (porta 22), RDP (porta 3389) e os endpoints de metadados da nuvem (169.254.169.254) estão bloqueados ou exigem autenticação baseada em certificado.
 #4.3.3    Level: 2    Role: D/V
 Verifique se o tráfego de saída é filtrado por meio de proxies HTTP/HTTPS (Squid, Istio ou gateways NAT em nuvem) com listas de permissão de domínios e se as solicitações bloqueadas são registradas.
 #4.3.4    Level: 2    Role: D/V
 Verifique se a comunicação entre serviços utiliza TLS mútuo com certificados rotacionados conforme a política organizacional e com validação de certificados aplicada (sem flags de pular verificação).
 #4.3.5    Level: 2    Role: D/V
 Verifique se a infraestrutura de IA opera em VPCs/VNets dedicadas sem acesso direto à internet e se comunica apenas por meio de gateways NAT ou hosts bastião.

---

### C4.4 Gestão de Segredos e Chaves Criptográficas

Proteja credenciais por meio de armazenamento com suporte de hardware e rotação automatizada com acesso de confiança zero.

 #4.4.1    Level: 1    Role: D/V
 Verifique se os segredos estão armazenados no HashiCorp Vault, AWS Secrets Manager, Azure Key Vault ou Google Secret Manager com criptografia em repouso usando AES-256.
 #4.4.2    Level: 1    Role: D/V
 Verifique se as chaves criptográficas são geradas em HSMs Nível 2 FIPS 140-2 (AWS CloudHSM, Azure Dedicated HSM) com rotação de chave conforme a política criptográfica organizacional.
 #4.4.3    Level: 2    Role: D/V
 Verifique se a rotação de segredos é automatizada com implantação sem tempo de inatividade e rotação imediata acionada por mudanças de pessoal ou incidentes de segurança.
 #4.4.4    Level: 2    Role: D/V
 Verifique se as imagens de contêiner são escaneadas com ferramentas (GitLeaks, TruffleHog ou detect-secrets) bloqueando builds que contenham chaves de API, senhas ou certificados.
 #4.4.5    Level: 2    Role: D/V
 Verifique se o acesso ao segredo de produção requer MFA com tokens de hardware (YubiKey, FIDO2) e é registrado por logs de auditoria imutáveis com identidades de usuários e carimbos de data/hora.
 #4.4.6    Level: 2    Role: D/V
 Verifique se os segredos são injetados por meio de segredos do Kubernetes, volumes montados ou contêineres init e garanta que os segredos nunca sejam incorporados em variáveis de ambiente ou imagens.

---

### C4.5 Sandboxing e Validação de Carga de Trabalho de IA

Isole modelos de IA não confiáveis em sandboxes seguros com análise comportamental abrangente.

 #4.5.1    Level: 1    Role: D/V
 Verifique se os modelos de IA externos são executados em gVisor, microVMs (como Firecracker, CrossVM) ou containers Docker com as opções --security-opt=no-new-privileges e --read-only.
 #4.5.2    Level: 1    Role: D/V
 Verifique se os ambientes sandbox não têm conectividade de rede (--network=none) ou possuem acesso apenas ao localhost, com todas as requisições externas bloqueadas por regras do iptables.
 #4.5.3    Level: 2    Role: D/V
 Verifique se a validação do modelo de IA inclui testes automatizados de red-team com cobertura de teste definida organizacionalmente e análise comportamental para detecção de backdoors.
 #4.5.4    Level: 2    Role: D/V
 Verifique se, antes de um modelo de IA ser promovido para produção, seus resultados no ambiente de testes são assinados criptograficamente por pessoal de segurança autorizado e armazenados em registros de auditoria imutáveis.
 #4.5.5    Level: 2    Role: D/V
 Verifique se os ambientes sandbox são destruídos e recriados a partir de imagens de referência entre as avaliações, com limpeza completa do sistema de arquivos e da memória.

---

### C4.6 Monitoramento de Segurança da Infraestrutura

Escaneie e monitore continuamente a infraestrutura com remediação automatizada e alertas em tempo real.

 #4.6.1    Level: 1    Role: D/V
 Verifique se as imagens dos containers são analisadas de acordo com os cronogramas organizacionais, com vulnerabilidades CRÍTICAS bloqueando a implantação com base nos limites de risco organizacional.
 #4.6.2    Level: 1    Role: D/V
 Verifique se a infraestrutura atende aos padrões CIS Benchmarks ou aos controles NIST 800-53 com limiares de conformidade definidos pela organização e remediação automatizada para verificações que falharem.
 #4.6.3    Level: 2    Role: D/V
 Verifique se as vulnerabilidades de severidade ALTA são corrigidas de acordo com os prazos de gerenciamento de risco organizacional, com procedimentos de emergência para CVEs ativamente exploradas.
 #4.6.4    Level: 2    Role: V
 Verifique se os alertas de segurança são integrados com plataformas SIEM (Splunk, Elastic ou Sentinel) usando os formatos CEF ou STIX/TAXII com enriquecimento automatizado.
 #4.6.5    Level: 3    Role: V
 Verifique se as métricas da infraestrutura são exportadas para os sistemas de monitoramento (Prometheus, DataDog) com dashboards de SLA e relatórios executivos.
 #4.6.6    Level: 2    Role: D/V
 Verifique se a deriva de configuração é detectada usando ferramentas (Chef InSpec, AWS Config) de acordo com os requisitos de monitoramento organizacional, com reversão automática para alterações não autorizadas.

---

### C4.7 Gestão de Recursos da Infraestrutura de IA

Prevenir ataques de exaustão de recursos e garantir a alocação justa de recursos por meio de cotas e monitoramento.

 #4.7.1    Level: 1    Role: D/V
 Verifique se a utilização de GPU/TPU é monitorada com alertas acionados nos limites definidos pela organização e com escalonamento automático ou balanceamento de carga ativado com base nas políticas de gerenciamento de capacidade.
 #4.7.2    Level: 1    Role: D/V
 Verifique se as métricas de carga de trabalho de IA (latência de inferência, taxa de transferência, taxas de erro) são coletadas de acordo com os requisitos de monitoramento organizacional e correlacionadas com a utilização da infraestrutura.
 #4.7.3    Level: 2    Role: D/V
 Verifique se os ResourceQuotas do Kubernetes ou equivalente limitam cargas de trabalho individuais conforme as políticas organizacionais de alocação de recursos, com limites rígidos aplicados.
 #4.7.4    Level: 2    Role: V
 Verifique se o monitoramento de custos acompanha os gastos por carga de trabalho/inquilino com alertas baseados em limites orçamentários organizacionais e controles automatizados para excedentes de orçamento.
 #4.7.5    Level: 3    Role: V
 Verifique se o planejamento de capacidade utiliza dados históricos com períodos de previsão definidos pela organização e provisionamento automático de recursos com base nos padrões de demanda.
 #4.7.6    Level: 2    Role: D/V
 Verifique se o esgotamento de recursos aciona os disjuntores conforme os requisitos de resposta organizacional, incluindo limitação de taxa com base em políticas de capacidade e isolamento de carga de trabalho.

---

### C4.8 Controles de Separação de Ambiente e Promoção

Imponha limites rígidos ao ambiente com portões automatizados de promoção e validação de segurança.

 #4.8.1    Level: 1    Role: D/V
 Verifique se os ambientes de desenvolvimento/teste/produção operam em VPCs/VNets separadas, sem papéis IAM compartilhados, grupos de segurança ou conectividade de rede.
 #4.8.2    Level: 1    Role: D/V
 Verifique se a promoção do ambiente requer aprovação de pessoal autorizado definido pela organização, com assinaturas criptográficas e trilhas de auditoria imutáveis.
 #4.8.3    Level: 2    Role: D/V
 Verifique se os ambientes de produção bloqueiam o acesso SSH, desativam endpoints de depuração e exigem solicitações de alteração com requisitos de aviso prévio organizacional, exceto em emergências.
 #4.8.4    Level: 2    Role: D/V
 Verifique que as alterações de infraestrutura como código exigem revisão por pares com testes automatizados e varredura de segurança antes da mesclagem para o branch principal.
 #4.8.5    Level: 2    Role: D/V
 Verifique se os dados não relacionados à produção estão anonimizados de acordo com os requisitos de privacidade organizacional, geração de dados sintéticos ou mascaramento completo de dados com remoção de informações pessoais identificáveis (PII) verificada.
 #4.8.6    Level: 2    Role: D/V
 Verifique se os portões de promoção incluem testes automatizados de segurança (SAST, DAST, varredura de contêiner) com zero achados CRÍTICOS necessários para aprovação.

---

### C4.9 Backup e Recuperação da Infraestrutura

Garanta a resiliência da infraestrutura por meio de backups automatizados, procedimentos de recuperação testados e capacidades de recuperação de desastres.

 #4.9.1    Level: 1    Role: D/V
 Verifique se as configurações da infraestrutura estão sendo respaldadas de acordo com os cronogramas de backup organizacionais para regiões geograficamente separadas, implementando a estratégia de backup 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Verifique se os sistemas de backup operam em redes isoladas com credenciais separadas e armazenamento air-gapped para proteção contra ransomware.
 #4.9.3    Level: 2    Role: V
 Verifique se os procedimentos de recuperação são testados e validados por meio de testes automatizados de acordo com os cronogramas organizacionais, com metas de RTO e RPO atendendo aos requisitos da organização.
 #4.9.4    Level: 3    Role: V
 Verifique se a recuperação de desastres inclui runbooks específicos para IA com restauração de pesos do modelo, reconstrução do cluster de GPU e mapeamento de dependências de serviço.

---

### C4.10 Conformidade e Governança da Infraestrutura

Mantenha a conformidade regulatória por meio de avaliação contínua, documentação e controles automatizados.

 #4.10.1    Level: 2    Role: D/V
 Verifique se a conformidade da infraestrutura é avaliada de acordo com os cronogramas organizacionais em relação aos controles SOC 2, ISO 27001 ou FedRAMP, com coleta automatizada de evidências.
 #4.10.2    Level: 2    Role: V
 Verifique se a documentação da infraestrutura inclui diagramas de rede, mapas de fluxo de dados e modelos de ameaça atualizados de acordo com os requisitos de gerenciamento de mudanças organizacionais.
 #4.10.3    Level: 3    Role: D/V
 Verifique se as alterações na infraestrutura passam por uma avaliação automatizada de impacto de conformidade com fluxos de trabalho de aprovação regulatória para modificações de alto risco.

---

### C4.11 Segurança de Hardware de IA

Componentes de hardware específicos para IA seguros, incluindo GPUs, TPUs e aceleradores de IA especializados.

 #4.11.1    Level: 2    Role: D/V
 Verifique se o firmware do acelerador de IA (BIOS da GPU, firmware do TPU) está verificado com assinaturas criptográficas e atualizado de acordo com os prazos de gerenciamento de patches da organização.
 #4.11.2    Level: 2    Role: D/V
 Verifique se, antes da execução da carga de trabalho, a integridade do acelerador de IA é validada por meio de atestação de hardware usando TPM 2.0, Intel TXT ou AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Verifique se a memória da GPU está isolada entre as cargas de trabalho usando SR-IOV, MIG (GPU Multi-Instância) ou particionamento de hardware equivalente com sanitização da memória entre os trabalhos.
 #4.11.4    Level: 3    Role: V
 Verifique se a cadeia de suprimentos de hardware de IA inclui verificação de procedência com certificados do fabricante e validação de embalagens à prova de violação.
 #4.11.5    Level: 3    Role: D/V
 Verifique se os módulos de segurança de hardware (HSMs) protegem os pesos dos modelos de IA e as chaves criptográficas com certificação FIPS 140-2 Nível 3 ou Common Criteria EAL4+.

---

### C4.12 Infraestrutura de IA de Borda e Distribuída

Implantações seguras de IA distribuída, incluindo computação de borda, aprendizado federado e arquiteturas multi-site.

 #4.12.1    Level: 2    Role: D/V
 Verifique se os dispositivos de IA de borda autenticam na infraestrutura central usando TLS mútuo com certificados de dispositivo rotacionados de acordo com a política organizacional de gestão de certificados.
 #4.12.2    Level: 2    Role: D/V
 Verifique se os dispositivos de borda implementam inicialização segura com assinaturas verificadas e proteção contra reversão para impedir ataques de downgrade de firmware.
 #4.12.3    Level: 3    Role: D/V
 Verifique se a coordenação de IA distribuída utiliza algoritmos de consenso tolerantes a falhas bizantinas com validação dos participantes e detecção de nós maliciosos.
 #4.12.4    Level: 3    Role: D/V
 Verifique se a comunicação de ponta a nuvem inclui limitação de largura de banda, compressão de dados e capacidades de operação offline com armazenamento local seguro.

---

### C4.13 Segurança de Infraestrutura Multi-Nuvem e Híbrida

Proteja cargas de trabalho de IA em vários provedores de nuvem e implantações híbridas de nuvem e on-premises.

 #4.13.1    Level: 2    Role: D/V
 Verifique se as implantações de IA multi-nuvem utilizam federação de identidade agnóstica à nuvem (OIDC, SAML) com gerenciamento centralizado de políticas entre os provedores.
 #4.13.2    Level: 2    Role: D/V
 Verifique se a transferência de dados entre nuvens utiliza criptografia de ponta a ponta com chaves gerenciadas pelo cliente e controles de residência de dados aplicados conforme a jurisdição.
 #4.13.3    Level: 2    Role: D/V
 Verifique se as cargas de trabalho de IA em nuvem híbrida implementam políticas de segurança consistentes em ambientes locais e na nuvem, com monitoramento e alerta unificados.
 #4.13.4    Level: 3    Role: V
 Verifique se a prevenção de dependência exclusiva do fornecedor de nuvem inclui infraestrutura como código portátil, APIs padronizadas e capacidades de exportação de dados com ferramentas de conversão de formato.
 #4.13.5    Level: 3    Role: V
 Verifique se a otimização de custos multi-cloud inclui controles de segurança que impedem a dispersão de recursos, bem como cobranças não autorizadas por transferência de dados entre clouds.

---

### C4.14 Automação de Infraestrutura e Segurança GitOps

Automação segura de pipelines de infraestrutura e fluxos de trabalho GitOps para gerenciamento de infraestrutura de IA.

 #4.14.1    Level: 2    Role: D/V
 Verifique se os repositórios GitOps exigem commits assinados com chaves GPG e regras de proteção de branch que impedem pushes diretos para as branches principais.
 #4.14.2    Level: 2    Role: D/V
 Verifique se a automação da infraestrutura inclui detecção de deriva com capacidades automáticas de remediação e reversão acionadas de acordo com os requisitos de resposta organizacional para alterações não autorizadas.
 #4.14.3    Level: 2    Role: D/V
 Verifique se o provisionamento automatizado da infraestrutura inclui a validação da política de segurança com bloqueio de implantação para configurações não conformes.
 #4.14.4    Level: 2    Role: D/V
 Verifique se os segredos de automação da infraestrutura são gerenciados por meio de operadores externos de segredos (External Secrets Operator, Bank-Vaults) com rotação automática.
 #4.14.5    Level: 3    Role: V
 Verifique se a infraestrutura autocurativa inclui correlação de eventos de segurança com resposta automatizada a incidentes e fluxos de trabalho para notificação das partes interessadas.

---

### C4.15 Segurança da Infraestrutura Resistente a Computação Quântica

Prepare a infraestrutura de IA para ameaças de computação quântica por meio de criptografia pós-quântica e protocolos seguros contra computação quântica.

 #4.15.1    Level: 3    Role: D/V
 Verifique se a infraestrutura de IA implementa algoritmos criptográficos pós-quânticos aprovados pelo NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) para troca de chaves e assinaturas digitais.
 #4.15.2    Level: 3    Role: D/V
 Verifique se os sistemas de distribuição de chaves quânticas (QKD) são implementados para comunicações de IA de alta segurança com protocolos de gerenciamento de chaves à prova de computação quântica.
 #4.15.3    Level: 3    Role: D/V
 Verifique se os frameworks de agilidade criptográfica permitem a migração rápida para novos algoritmos pós-quânticos com rotação automatizada de certificados e chaves.
 #4.15.4    Level: 3    Role: V
 Verifique se a modelagem de ameaças quânticas avalia a vulnerabilidade da infraestrutura de IA a ataques quânticos, com cronogramas de migração documentados e avaliações de risco.
 #4.15.5    Level: 3    Role: D/V
 Verifique se os sistemas criptográficos híbridos clássicos-quânticos fornecem defesa em profundidade durante o período de transição quântica com monitoramento de desempenho.

---

### C4.16 Computação Confidencial e Enclaves Seguros

Proteja cargas de trabalho de IA e pesos de modelos usando ambientes de execução confiáveis baseados em hardware e tecnologias de computação confidencial.

 #4.16.1    Level: 3    Role: D/V
 Verifique se os modelos de IA sensíveis são executados dentro de enclaves Intel SGX, AMD SEV-SNP ou ARM TrustZone com memória criptografada e verificação de atestação.
 #4.16.2    Level: 3    Role: D/V
 Verifique se contêineres confidenciais (Kata Containers, gVisor com computação confidencial) isolam cargas de trabalho de IA com criptografia de memória aplicada por hardware.
 #4.16.3    Level: 3    Role: D/V
 Verifique que a atestação remota valide a integridade do enclave antes de carregar modelos de IA com prova criptográfica da autenticidade do ambiente de execução.
 #4.16.4    Level: 3    Role: D/V
 Verifique se os serviços confidenciais de inferência em IA previnem a extração de modelos por meio de computação criptografada com pesos do modelo selados e execução protegida.
 #4.16.5    Level: 3    Role: D/V
 Verifique se a orquestração do ambiente de execução confiável gerencia o ciclo de vida do enclave seguro com atestado remoto e canais de comunicação criptografados.
 #4.16.6    Level: 3    Role: D/V
 Verifique se a computação multipartidária segura (SMPC) permite o treinamento colaborativo de IA sem expor conjuntos de dados individuais ou parâmetros do modelo.

---

### C4.17 Infraestrutura de Conhecimento Zero

Implemente sistemas de prova de conhecimento zero para verificação e autenticação de IA que preservem a privacidade, sem revelar informações sensíveis.

 #4.17.1    Level: 3    Role: D/V
 Verifique se as provas de conhecimento zero (ZK-SNARKs, ZK-STARKs) confirmam a integridade do modelo de IA e a proveniência do treinamento sem expor os pesos do modelo ou os dados de treinamento.
 #4.17.2    Level: 3    Role: D/V
 Verifique se os sistemas de autenticação baseados em ZK permitem a verificação do usuário preservando a privacidade para serviços de IA sem revelar informações relacionadas à identidade.
 #4.17.3    Level: 3    Role: D/V
 Verifique se os protocolos de interseção privada de conjuntos (PSI) permitem correspondência segura de dados para IA federada sem expor conjuntos de dados individuais.
 #4.17.4    Level: 3    Role: D/V
 Verifique se os sistemas de aprendizado de máquina de conhecimento zero (ZKML) permitem inferências de IA verificáveis com prova criptográfica de computação correta.
 #4.17.5    Level: 3    Role: D/V
 Verifique que os ZK-rollups fornecem processamento de transações de IA escalável, preservando a privacidade, com verificação em lote e redução da sobrecarga computacional.

---

### C4.18 Prevenção de Ataques por Canal Lateral

Proteja a infraestrutura de IA contra ataques de canal lateral baseados em tempo, energia, eletromagnéticos e cache que possam vazar informações sensíveis.

 #4.18.1    Level: 3    Role: D/V
 Verifique se o tempo de inferência de IA é normalizado usando algoritmos de tempo constante e preenchimento para prevenir ataques de extração de modelos baseados em tempo.
 #4.18.2    Level: 3    Role: D/V
 Verifique se a proteção contra análise de consumo de energia inclui injeção de ruído, filtragem da linha de energia e padrões de execução randomizados para hardware de IA.
 #4.18.3    Level: 3    Role: D/V
 Verifique se a mitigação de canais laterais baseada em cache utiliza particionamento de cache, randomização e instruções de limpeza para prevenir o vazamento de informações.
 #4.18.4    Level: 3    Role: D/V
 Verifique se a proteção contra emanações eletromagnéticas inclui blindagem, filtragem de sinais e processamento aleatório para prevenir ataques do tipo TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Verifique se as defesas contra canais laterais microarquiteturais incluem controles de execução especulativa e ofuscação de padrão de acesso à memória.

---

### C4.19 Segurança de Hardware Neuromórfico e de IA Especializada

Arquiteturas emergentes seguras de hardware de IA, incluindo chips neuromórficos, FPGAs, ASICs personalizados e sistemas de computação óptica.

 #4.19.1    Level: 3    Role: D/V
 Verifique se a segurança do chip neuromórfico inclui criptografia de padrão de picos, proteção de peso sináptico e validação de regra de aprendizado baseada em hardware.
 #4.19.2    Level: 3    Role: D/V
 Verifique se os aceleradores de IA baseados em FPGA implementam criptografia de bitstream, mecanismos anti-manipulação e carregamento seguro de configuração com atualizações autenticadas.
 #4.19.3    Level: 3    Role: D/V
 Verifique se a segurança do ASIC personalizado inclui processadores de segurança integrados, raiz de confiança de hardware e armazenamento seguro de chaves com detecção de violação.
 #4.19.4    Level: 3    Role: D/V
 Verifique se os sistemas de computação óptica implementam criptografia óptica segura contra ataques quânticos, comutação fotônica segura e processamento de sinais ópticos protegido.
 #4.19.5    Level: 3    Role: D/V
 Verifique se os chips de IA híbridos analógicos-digitais incluem computação analógica segura, armazenamento protegido de pesos e conversão analógico-digital autenticada.

---

### C4.20 Infraestrutura de Computação Preservadora de Privacidade

Implemente controles de infraestrutura para computação que preserva a privacidade, a fim de proteger dados sensíveis durante o processamento e análise de IA.

 #4.20.1    Level: 3    Role: D/V
 Verifique se a infraestrutura de criptografia homomórfica permite a computação criptografada em cargas de trabalho sensíveis de IA com verificação de integridade criptográfica e monitoramento de desempenho.
 #4.20.2    Level: 3    Role: D/V
 Verifique se os sistemas de recuperação de informação privada permitem consultas a bancos de dados sem revelar padrões de consulta, com proteção criptográfica dos padrões de acesso.
 #4.20.3    Level: 3    Role: D/V
 Verifique se os protocolos de computação multipartidária segura permitem inferência de IA que preserva a privacidade sem expor as entradas individuais ou os cálculos intermediários.
 #4.20.4    Level: 3    Role: D/V
 Verifique se o gerenciamento de chaves que preserva a privacidade inclui geração distribuída de chaves, criptografia threshold e rotação segura de chaves com proteção suportada por hardware.
 #4.20.5    Level: 3    Role: D/V
 Verifique se o desempenho da computação que preserva a privacidade está otimizado por meio de agrupamento, armazenamento em cache e aceleração de hardware, enquanto mantém as garantias de segurança criptográfica.

---

### C4.15 Segurança da Integração de Nuvem do Framework de Agentes e Implantação Híbrida

Controles de segurança para frameworks de agentes integrados à nuvem com arquiteturas híbridas on-premises/nuvem.

 #4.15.1    Level: 1    Role: D/V
 Verifique se a integração com armazenamento em nuvem utiliza criptografia de ponta a ponta com gerenciamento de chaves controlado pelo agente.
 #4.15.2    Level: 2    Role: D/V
 Verifique se os limites de segurança da implantação híbrida estão claramente definidos com canais de comunicação criptografados.
 #4.15.3    Level: 2    Role: D/V
 Verifique se o acesso aos recursos na nuvem inclui verificação de confiança zero com autenticação contínua.
 #4.15.4    Level: 3    Role: D/V
 Verifique se os requisitos de residência de dados são aplicados por meio de atestação criptográfica dos locais de armazenamento.
 #4.15.5    Level: 3    Role: D/V
 Verifique se as avaliações de segurança do provedor de nuvem incluem modelagem de ameaças específicas para agentes e avaliação de riscos.

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

O controle de acesso efetivo para sistemas de IA requer uma gestão robusta de identidade, autorização consciente do contexto e aplicação em tempo de execução seguindo os princípios de zero confiança. Esses controles garantem que humanos, serviços e agentes autônomos interajam apenas com modelos, dados e recursos computacionais dentro de escopos explicitamente concedidos, com capacidades contínuas de verificação e auditoria.

---

### C5.1 Gestão de Identidade e Autenticação

Estabeleça identidades respaldadas criptograficamente para todas as entidades com autenticação multifatorial para operações privilegiadas.

 #5.1.1    Level: 1    Role: D/V
 Verifique se todos os usuários humanos e principais de serviço se autenticam por meio de um provedor de identidade empresarial centralizado (IdP) usando protocolos OIDC/SAML com mapeamentos únicos de identidade para token (sem contas ou credenciais compartilhadas).
 #5.1.2    Level: 1    Role: D/V
 Verifique se as operações de alto risco (implantação de modelo, exportação de pesos, acesso a dados de treinamento, alterações na configuração de produção) exigem autenticação multifatorial ou autenticação progressiva com revalidação da sessão.
 #5.1.3    Level: 2    Role: D
 Verifique se os novos responsáveis passam por prova de identidade alinhada com o NIST 800-63-3 IAL-2 ou padrões equivalentes antes de receberem acesso ao sistema de produção.
 #5.1.4    Level: 2    Role: V
 Verifique se as revisões de acesso são realizadas trimestralmente com detecção automática de contas inativas, aplicação de rotação de credenciais e fluxos de trabalho de desprovisionamento.
 #5.1.5    Level: 3    Role: D/V
 Verifique se os agentes de IA federados autenticam-se por meio de afirmações JWT assinadas que possuem um tempo máximo de validade de 24 horas e incluem prova criptográfica de origem.

---

### C5.2 Autorização de Recursos e Privilégio Mínimo

Implemente controles de acesso granulares para todos os recursos de IA com modelos de permissão explícitos e trilhas de auditoria.

 #5.2.1    Level: 1    Role: D/V
 Verifique se todos os recursos de IA (conjuntos de dados, modelos, endpoints, coleções de vetores, índices de embedding, instâncias de computação) aplicam controles de acesso baseados em função com listas de permissão explícitas e políticas de negação padrão.
 #5.2.2    Level: 1    Role: D/V
 Verifique se os princípios de menor privilégio são aplicados por padrão nas contas de serviço, começando com permissões somente de leitura e exigindo justificativa comercial documentada para acesso de gravação.
 #5.2.3    Level: 1    Role: V
 Verifique se todas as modificações no controle de acesso estão vinculadas a solicitações de mudança aprovadas e registradas de forma imutável com carimbos de data/hora, identidades dos atores, identificadores de recursos e deltas de permissões.
 #5.2.4    Level: 2    Role: D
 Verifique se os rótulos de classificação de dados (PII, PHI, controlados para exportação, proprietários) se propagam automaticamente para recursos derivados (incorporações, caches de prompts, saídas de modelos) com aplicação consistente da política.
 #5.2.5    Level: 2    Role: D/V
 Verifique se as tentativas de acesso não autorizado e os eventos de escalonamento de privilégios acionam alertas em tempo real com metadados contextuais para sistemas SIEM dentro de 5 minutos.

---

### C5.3 Avaliação Dinâmica de Políticas

Implemente motores de controle de acesso baseado em atributos (ABAC) para decisões de autorização conscientes do contexto, com capacidades de auditoria.

 #5.3.1    Level: 1    Role: D/V
 Verifique se as decisões de autorização são externalizadas para um mecanismo de política dedicado (OPA, Cedar ou equivalente) acessível por meio de APIs autenticadas com proteção de integridade criptográfica.
 #5.3.2    Level: 1    Role: D/V
 Verifique se as políticas avaliam atributos dinâmicos em tempo de execução, incluindo nível de autorização do usuário, classificação de sensibilidade do recurso, contexto da solicitação, isolamento do inquilino e restrições temporais.
 #5.3.3    Level: 2    Role: D
 Verifique se as definições de políticas são controladas por versão, revisadas por pares e validadas por meio de testes automatizados em pipelines de CI/CD antes da implantação em produção.
 #5.3.4    Level: 2    Role: V
 Verifique se os resultados da avaliação da política incluem justificativas estruturadas para a decisão e são transmitidos aos sistemas SIEM para análise de correlação e relatórios de conformidade.
 #5.3.5    Level: 3    Role: D/V
 Verifique se os valores de tempo de vida (TTL) do cache de políticas não excedem 5 minutos para recursos de alta sensibilidade e 1 hora para recursos padrão com capacidades de invalidação de cache.

---

### C5.4 Aplicação de Segurança em Tempo de Consulta

Implemente controles de segurança na camada de banco de dados com filtragem obrigatória e políticas de segurança em nível de linha.

 #5.4.1    Level: 1    Role: D/V
 Verifique se todas as consultas em bancos de dados vetoriais e SQL incluem filtros de segurança obrigatórios (ID do inquilino, rótulos de sensibilidade, escopo do usuário) aplicados no nível do mecanismo de banco de dados, e não no código da aplicação.
 #5.4.2    Level: 1    Role: D/V
 Verifique se as políticas de segurança em nível de linha (RLS) e mascaramento em nível de campo estão habilitadas com herança de políticas para todos os bancos de dados vetoriais, índices de busca e conjuntos de dados de treinamento.
 #5.4.3    Level: 2    Role: D
 Verifique se avaliações de autorização falhadas impedirão "ataques de representante confuso" abortando imediatamente as consultas e retornando códigos explícitos de erro de autorização em vez de retornar conjuntos de resultados vazios.
 #5.4.4    Level: 2    Role: V
 Verifique se a latência na avaliação da política é monitorada continuamente com alertas automatizados para condições de tempo limite que possam permitir a violação de autorização.
 #5.4.5    Level: 3    Role: D/V
 Verifique se os mecanismos de nova tentativa de consulta reavaliam as políticas de autorização para considerar mudanças dinâmicas de permissões dentro de sessões de usuário ativas.

---

### Filtragem de Saída C5.5 e Prevenção de Perda de Dados

Implemente controles de pós-processamento para evitar a exposição não autorizada de dados em conteúdo gerado por IA.

 #5.5.1    Level: 1    Role: D/V
 Verifique se os mecanismos de filtragem pós-inferência escaneiam e redactam informações pessoais identificáveis (PII) não autorizadas, informações classificadas e dados proprietários antes de entregar o conteúdo aos solicitantes.
 #5.5.2    Level: 1    Role: D/V
 Verifique se as citações, referências e atribuições de fontes nos resultados do modelo estão validadas com base nas permissões do solicitante e removidas se for detectado acesso não autorizado.
 #5.5.3    Level: 2    Role: D
 Verifique se as restrições de formato de saída (PDFs sanitizados, imagens sem metadados, tipos de arquivos aprovados) são aplicadas com base nos níveis de permissão do usuário e nas classificações de dados.
 #5.5.4    Level: 2    Role: V
 Verifique se os algoritmos de redação são determinísticos, controlados por versão e mantêm registros de auditoria para apoiar investigações de conformidade e análise forense.
 #5.5.5    Level: 3    Role: V
 Verifique se eventos de redação de alto risco geram logs adaptativos que incluem hashes criptográficos do conteúdo original para recuperação forense sem exposição de dados.

---

### C5.6 Isolamento Multi-Inquilino

Garantir o isolamento criptográfico e lógico entre os inquilinos em infraestrutura de IA compartilhada.

 #5.6.1    Level: 1    Role: D/V
 Verifique se os espaços de memória, armazenamentos de embeddings, entradas de cache e arquivos temporários estão segregados por namespace para cada locatário, com limpeza segura na exclusão do locatário ou término da sessão.
 #5.6.2    Level: 1    Role: D/V
 Verifique se toda solicitação de API inclui um identificador de locatário autenticado que é criptograficamente validado em relação ao contexto da sessão e às permissões do usuário.
 #5.6.3    Level: 2    Role: D
 Verifique se as políticas de rede implementam regras de negação padrão para comunicação entre locatários em malhas de serviço e plataformas de orquestração de contêineres.
 #5.6.4    Level: 3    Role: D
 Verifique se as chaves de criptografia são exclusivas por locatário com suporte a chave gerenciada pelo cliente (CMK) e isolamento criptográfico entre os armazenamentos de dados dos locatários.

---

### C5.7 Autorização de Agente Autônomo

Controle permissões para agentes de IA e sistemas autônomos por meio de tokens de capacidade com escopo e autorização contínua.

 #5.7.1    Level: 1    Role: D/V
 Verifique se os agentes autônomos recebem tokens de capacidade com escopo que enumeram explicitamente as ações permitidas, os recursos acessíveis, os limites de tempo e as restrições operacionais.
 #5.7.2    Level: 1    Role: D/V
 Verifique se as capacidades de alto risco (acesso ao sistema de arquivos, execução de código, chamadas de API externas, transações financeiras) estão desativadas por padrão e requerem autorizações explícitas para ativação com justificativas comerciais.
 #5.7.3    Level: 2    Role: D
 Verifique se os tokens de capacidade estão vinculados às sessões do usuário, incluem proteção de integridade criptográfica e garantem que não possam ser persistidos ou reutilizados em cenários offline.
 #5.7.4    Level: 2    Role: V
 Verifique se as ações iniciadas pelo agente passam por autorização secundária por meio do motor de políticas ABAC com avaliação completa do contexto e registro de auditoria.
 #5.7.5    Level: 3    Role: V
 Verifique se as condições de erro do agente e o tratamento de exceções incluem informações sobre o escopo da capacidade para suportar a análise de incidentes e a investigação forense.

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

Ataques à cadeia de suprimentos de IA exploram modelos, frameworks ou conjuntos de dados de terceiros para inserir portas dos fundos, viés ou código explorável. Esses controles fornecem rastreabilidade de ponta a ponta, gerenciamento de vulnerabilidades e monitoramento para proteger todo o ciclo de vida do modelo.

---

### C6.1 Verificação e Procedência de Modelos Pré-treinados

Avalie e autentique as origens, licenças e comportamentos ocultos de modelos de terceiros antes de qualquer ajuste fino ou implantação.

 #6.1.1    Level: 1    Role: D/V
 Verifique se todo artefato de modelo de terceiros inclui um registro de procedência assinado, identificando o repositório de origem e o hash do commit.
 #6.1.2    Level: 1    Role: D/V
 Verifique se os modelos são escaneados em busca de camadas maliciosas ou gatilhos de Trojan utilizando ferramentas automatizadas antes da importação.
 #6.1.3    Level: 2    Role: D
 Verifique se o fine-tuning por transferência de aprendizado passa na avaliação adversarial para detectar comportamentos ocultos.
 #6.1.4    Level: 2    Role: V
 Verifique se as licenças do modelo, as etiquetas de controle de exportação e as declarações de origem dos dados estão registradas em uma entrada ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Verifique se os modelos de alto risco (pesos carregados publicamente, criadores não verificados) permanecem em quarentena até revisão e aprovação humana.

---

### C6.2 Varredura de Framework e Biblioteca

Escaneie continuamente os frameworks e bibliotecas de ML em busca de CVEs e código malicioso para manter a pilha de execução segura.

 #6.2.1    Level: 1    Role: D/V
 Verifique se os pipelines de Integração Contínua (CI) executam scanners de dependências em frameworks de IA e bibliotecas críticas.
 #6.2.2    Level: 1    Role: D/V
 Verifique se vulnerabilidades críticas (CVSS ≥ 7.0) impedem a promoção para imagens de produção.
 #6.2.3    Level: 2    Role: D
 Verifique se a análise estática de código é executada em bibliotecas de ML bifurcadas ou fornecidas como dependências.
 #6.2.4    Level: 2    Role: V
 Verifique se as propostas de atualização do framework incluem uma avaliação de impacto de segurança referenciando feeds públicos de CVE.
 #6.2.5    Level: 3    Role: V
 Verifique se os sensores de tempo de execução alertam sobre carregamentos inesperados de bibliotecas dinâmicas que desviem do SBOM assinado.

---

### C6.3 Fixação e Verificação de Dependências

Fixe cada dependência a resumos imutáveis e reproduza builds para garantir artefatos idênticos e livres de adulterações.

 #6.3.1    Level: 1    Role: D/V
 Verifique se todos os gerenciadores de pacotes aplicam o bloqueio de versão por meio de arquivos de bloqueio.
 #6.3.2    Level: 1    Role: D/V
 Verifique se resumos imutáveis são usados em vez de tags mutáveis nas referências de contêiner.
 #6.3.3    Level: 2    Role: D
 Verifique se as verificações de builds reprodutíveis comparam hashes entre execuções de CI para garantir saídas idênticas.
 #6.3.4    Level: 2    Role: V
 Verifique se as atestações de build são armazenadas por 18 meses para rastreabilidade de auditoria.
 #6.3.5    Level: 3    Role: D
 Verifique se dependências expiradas acionam PRs automatizados para atualizar ou forkar versões fixadas.

---

### C6.4 Aplicação de Fonte Confiável

Permita downloads de artefatos apenas de fontes criptograficamente verificadas e aprovadas pela organização, bloqueando todo o resto.

 #6.4.1    Level: 1    Role: D/V
 Verifique se os pesos do modelo, os conjuntos de dados e os contêineres são baixados apenas de domínios aprovados ou registros internos.
 #6.4.2    Level: 1    Role: D/V
 Verifique se as assinaturas Sigstore/Cosign validam a identidade do publicador antes que os artefatos sejam armazenados em cache localmente.
 #6.4.3    Level: 2    Role: D
 Verifique se os proxies de saída bloqueiam downloads de artefatos não autenticados para aplicar a política de origem confiável.
 #6.4.4    Level: 2    Role: V
 Verifique se as listas de permissão do repositório são revisadas trimestralmente com evidências de justificativa comercial para cada entrada.
 #6.4.5    Level: 3    Role: V
 Verifique se as violações de políticas acionam o isolamento dos artefatos e o retrocesso das execuções de pipeline dependentes.

---

### C6.5 Avaliação de Risco de Conjunto de Dados de Terceiros

Avalie conjuntos de dados externos quanto a envenenamento, viés e conformidade legal, e monitore-os ao longo de todo o seu ciclo de vida.

 #6.5.1    Level: 1    Role: D/V
 Verifique se os conjuntos de dados externos passam pela avaliação de risco de envenenamento (por exemplo, impressão digital de dados, detecção de outliers).
 #6.5.2    Level: 1    Role: D
 Verifique se as métricas de viés (paridade demográfica, igualdade de oportunidade) são calculadas antes da aprovação do conjunto de dados.
 #6.5.3    Level: 2    Role: V
 Verifique se a proveniência e os termos de licença dos conjuntos de dados estão registrados nas entradas do ML-BOM.
 #6.5.4    Level: 2    Role: V
 Verifique se o monitoramento periódico detecta deriva ou corrupção nos conjuntos de dados hospedados.
 #6.5.5    Level: 3    Role: D
 Verifique se o conteúdo proibido (direitos autorais, informações pessoais identificáveis) é removido por meio de limpeza automatizada antes do treinamento.

---

### C6.6 Monitoramento de Ataques na Cadeia de Suprimentos

Detecte ameaças à cadeia de suprimentos precocemente através de feeds CVE, análise de logs de auditoria e simulações de equipe vermelha.

 #6.6.1    Level: 1    Role: V
 Verifique se os logs de auditoria de CI/CD são transmitidos para o SIEM para detecções de puxadas de pacotes anômalas ou etapas de build adulteradas.
 #6.6.2    Level: 2    Role: D
 Verifique se os playbooks de resposta a incidentes incluem procedimentos de reversão para modelos ou bibliotecas comprometidos.
 #6.6.3    Level: 3    Role: V
 Verifique se o enriquecimento de inteligência de ameaças etiqueta indicadores específicos de ML (por exemplo, IoCs de envenenamento de modelo) na triagem de alertas.

---

### C6.7 ML-BOM para Artefatos de Modelos

Gere e assine SBOMs específicas para ML (ML-BOMs) detalhadas para que os consumidores a jusante possam verificar a integridade dos componentes no momento da implantação.

 #6.7.1    Level: 1    Role: D/V
 Verifique se todo artefato de modelo publica um ML-BOM que liste conjuntos de dados, pesos, hiperparâmetros e licenças.
 #6.7.2    Level: 1    Role: D/V
 Verifique se a geração do ML-BOM e a assinatura Cosign são automatizadas na CI e obrigatórias para a fusão.
 #6.7.3    Level: 2    Role: D
 Verifique se as verificações de completude do ML-BOM falham na compilação se algum metadado do componente (hash, licença) estiver ausente.
 #6.7.4    Level: 2    Role: V
 Verifique se os consumidores downstream podem consultar ML-BOMs via API para validar modelos importados no momento da implantação.
 #6.7.5    Level: 3    Role: V
 Verifique se os ML-BOMs são controlados por versões e comparados para detectar modificações não autorizadas.

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

As saídas do modelo devem ser estruturadas, confiáveis, seguras, explicáveis e continuamente monitoradas em produção. Fazer isso reduz alucinações, vazamentos de privacidade, conteúdo prejudicial e ações descontroladas, ao mesmo tempo em que aumenta a confiança dos usuários e a conformidade regulatória.

---

### C7.1 Aplicação do Formato de Saída

Esquemas rigorosos, decodificação restrita e validação a jusante impedem que conteúdo malformado ou malicioso se propague.

 #7.1.1    Level: 1    Role: D/V
 Verifique se os esquemas de resposta (por exemplo, JSON Schema) são fornecidos no prompt do sistema e se toda saída é automaticamente validada; saídas que não estejam em conformidade acionam reparo ou rejeição.
 #7.1.2    Level: 1    Role: D/V
 Verifique se a decodificação restrita (tokens de parada, regex, máximo de tokens) está habilitada para evitar estouro ou canais laterais de injeção de prompt.
 #7.1.3    Level: 2    Role: D/V
 Verifique se os componentes a jusante tratam as saídas como não confiáveis e as validam contra esquemas ou desserializadores seguros contra injeção.
 #7.1.4    Level: 3    Role: V
 Verifique se eventos de saída inadequada são registrados, limitados em taxa e exibidos para monitoramento.

---

### C7.2 Detecção e Mitigação de Alucinações

A estimativa de incerteza e as estratégias de fallback controlam respostas fabricadas.

 #7.2.1    Level: 1    Role: D/V
 Verifique se as log-probabilidades ao nível de token, a auto-consistência do conjunto ou os detectores de alucinação ajustados atribuem uma pontuação de confiança a cada resposta.
 #7.2.2    Level: 1    Role: D/V
 Verifique se as respostas abaixo de um limite de confiança configurável acionam fluxos de trabalho de fallback (por exemplo, geração aumentada por recuperação, modelo secundário ou revisão humana).
 #7.2.3    Level: 2    Role: D/V
 Verifique se os incidentes de alucinação estão etiquetados com metadados de causa raiz e alimentados nos pipelines de análise pós-morte e refinamento.
 #7.2.4    Level: 3    Role: D/V
 Verifique se os limiares e detectores são recalibrados após atualizações importantes do modelo ou da base de conhecimento.
 #7.2.5    Level: 3    Role: V
 Verifique se as visualizações do painel acompanham as taxas de alucinação.

---

### C7.3 Filtragem de Segurança e Privacidade da Saída

Filtros de política e cobertura de red-team protegem usuários e dados confidenciais.

 #7.3.1    Level: 1    Role: D/V
 Verifique se os classificadores pré e pós-geração bloqueiam conteúdo de ódio, assédio, autoagressão, extremista e sexualmente explícito, alinhado à política.
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

Limites de taxa e portões de aprovação previnem abuso e autonomia excessiva.

 #7.4.1    Level: 1    Role: D
 Verifique se as cotas por usuário e por chave de API limitam requisições, tokens e custos, aplicando retrocesso exponencial em erros 429.
 #7.4.2    Level: 1    Role: D/V
 Verifique se as ações privilegiadas (gravações em arquivos, execução de código, chamadas de rede) exigem aprovação baseada em políticas ou intervenção humana.
 #7.4.3    Level: 2    Role: D/V
 Verifique se as verificações de consistência entre modalidades garantem que imagens, código e texto gerados para a mesma solicitação não possam ser usados para introduzir conteúdo malicioso de forma encoberta.
 #7.4.4    Level: 2    Role: D
 Verifique se a profundidade de delegação do agente, os limites de recursão e as listas de ferramentas permitidas estão configurados explicitamente.
 #7.4.5    Level: 3    Role: V
 Verifique se a violação dos limites gera eventos de segurança estruturados para ingestão pelo SIEM.

---

### C7.5 Explicabilidade da Saída

Sinais transparentes melhoram a confiança do usuário e a depuração interna.

 #7.5.1    Level: 2    Role: D/V
 Verifique se as pontuações de confiança apresentadas ao usuário ou resumos breves de raciocínio são exibidos quando a avaliação de risco assim o justificar.
 #7.5.2    Level: 2    Role: D/V
 Verifique se as explicações geradas evitam revelar comandos sensíveis do sistema ou dados proprietários.
 #7.5.3    Level: 3    Role: D
 Verifique se o sistema captura as probabilidades logarítmicas em nível de token ou mapas de atenção e os armazena para inspeção autorizada.
 #7.5.4    Level: 3    Role: V
 Verifique se os artefatos de explicabilidade estão sob controle de versão juntamente com as versões do modelo para garantir auditabilidade.

---

### C7.6 Integração de Monitoramento

A observabilidade em tempo real fecha o ciclo entre desenvolvimento e produção.

 #7.6.1    Level: 1    Role: D
 Verifique se as métricas (violações de esquema, taxa de alucinação, toxicidade, vazamento de dados pessoais, latência, custo) são transmitidas para uma plataforma central de monitoramento.
 #7.6.2    Level: 1    Role: V
 Verifique se os limites de alerta estão definidos para cada métrica de segurança, com caminhos de escalonamento para chamadas de plantão.
 #7.6.3    Level: 2    Role: V
 Verifique se os painéis correlacionam anomalias de saída com modelo/versão, flag de recurso e mudanças nos dados de origem.
 #7.6.4    Level: 2    Role: D/V
 Verifique se os dados de monitoramento são retroalimentados para o re-treinamento, ajuste fino ou atualizações de regras dentro de um fluxo de trabalho MLOps documentado.
 #7.6.5    Level: 3    Role: V
 Verifique se os pipelines de monitoramento são submetidos a testes de penetração e possuem controle de acesso para evitar o vazamento de logs sensíveis.

---

### 7.7 Salvaguardas para Mídia Generativa

Garantir que os sistemas de IA não gerem conteúdo de mídia ilegal, prejudicial ou não autorizado, aplicando restrições de política, validação de saída e rastreabilidade.

 #7.7.1    Level: 1    Role: D/V
 Verifique se os prompts do sistema e as instruções do usuário proíbem explicitamente a geração de mídia deepfake ilegal, prejudicial ou não consensual (por exemplo, imagem, vídeo, áudio).
 #7.7.2    Level: 2    Role: D/V
 Verifique se os prompts são filtrados para evitar tentativas de gerar personificações, deepfakes sexualmente explícitos ou mídia que retrate indivíduos reais sem consentimento.
 #7.7.3    Level: 2    Role: V
 Verifique se o sistema utiliza hashing perceptual, detecção de marca d'água ou fingerprinting para impedir a reprodução não autorizada de mídia protegida por direitos autorais.
 #7.7.4    Level: 3    Role: D/V
 Verifique se toda mídia gerada é assinada criptograficamente, com marca d'água ou incorporada com metadados de procedência resistentes à adulteração para rastreabilidade a jusante.
 #7.7.5    Level: 3    Role: V
 Verifique se as tentativas de contorno (por exemplo, ofuscação de prompt, gírias, formulações adversariais) são detectadas, registradas e submetidas a limitação de taxa; abusos repetidos são reportados aos sistemas de monitoramento.

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

## Segurança da Memória C8, Embeddings e Banco de Dados Vetoriais

### Objetivo de Controle

Incorporações (embeddings) e armazenamento vetorial atuam como a "memória ativa" dos sistemas de IA contemporâneos, aceitando continuamente dados fornecidos pelos usuários e os trazendo de volta para os contextos dos modelos por meio da Geração Aumentada por Recuperação (RAG - Retrieval-Augmented Generation). Se deixada sem controle, essa memória pode vazar informações pessoais identificáveis (PII), violar consentimentos ou ser invertida para reconstruir o texto original. O objetivo desta família de controles é fortalecer os pipelines de memória e os bancos de dados vetoriais para que o acesso seja minimamente privilegiado, as incorporações preservem a privacidade, os vetores armazenados expirem ou possam ser revogados sob demanda, e a memória por usuário nunca contamine os prompts ou completions de outro usuário.

---

### C8.1 Controles de Acesso na Memória e Índices RAG

Implemente controles de acesso granulares em cada coleção de vetores.

 #8.1.1    Level: 1    Role: D/V
 Verifique se as regras de controle de acesso em nível de linha/namespace restringem as operações de inserção, exclusão e consulta por inquilino, coleção ou tag de documento.
 #8.1.2    Level: 1    Role: D/V
 Verifique se as chaves de API ou JWTs possuem reivindicações com escopo (por exemplo, IDs de coleção, verbos de ação) e são rotacionadas pelo menos trimestralmente.
 #8.1.3    Level: 2    Role: D/V
 Verifique se as tentativas de escalonamento de privilégios (por exemplo, consultas de similaridade entre namespaces) são detectadas e registradas em um SIEM dentro de 5 minutos.
 #8.1.4    Level: 2    Role: D/V
 Verifique se o banco de dados vetorial registra o identificador do sujeito da auditoria, operação, ID/namespace do vetor, limiar de similaridade e contagem de resultados.
 #8.1.5    Level: 3    Role: V
 Verifique se as decisões de acesso são testadas quanto a falhas de bypass sempre que os motores são atualizados ou as regras de indexação em shard são alteradas.

---

### C8.2 Sanitização e Validação de Embeddings

Pré-analise o texto em busca de informações pessoais identificáveis (PII), redija ou pseudonimiza antes da vetorização e, opcionalmente, pós-processe os embeddings para remover sinais residuais.

 #8.2.1    Level: 1    Role: D/V
 Verifique se os Dados Pessoais Identificáveis (PII) e os dados regulamentados são detectados por meio de classificadores automatizados e mascarados, tokenizados ou descartados antes da incorporação.
 #8.2.2    Level: 1    Role: D
 Verifique se os pipelines de incorporação rejeitam ou colocam em quarentena entradas que contenham código executável ou artefatos não UTF-8 que possam contaminar o índice.
 #8.2.3    Level: 2    Role: D/V
 Verifique se a sanitização local ou métrica de privacidade diferencial é aplicada às embeddings de sentenças cuja distância para qualquer token conhecido de Informação Pessoal Identificável (PII) fica abaixo de um limite configurável.
 #8.2.4    Level: 2    Role: V
 Verifique se a eficácia da sanitização (por exemplo, recall da redação de PII, deriva semântica) é validada pelo menos semestralmente contra corpora de referência.
 #8.2.5    Level: 3    Role: D/V
 Verifique se as configurações de sanitização estão sob controle de versão e se as alterações passam por revisão por pares.

---

### C8.3 Expiração, Revogação e Exclusão de Memória

O "direito ao esquecimento" do GDPR e leis similares exigem a exclusão oportuna; portanto, os repositórios de vetores devem suportar TTLs, exclusões definitivas e tomb-stoning para que vetores revogados não possam ser recuperados ou reindexados.

 #8.3.1    Level: 1    Role: D/V
 Verifique se cada vetor e registro de metadados possui um TTL ou rótulo de retenção explícito que seja respeitado por trabalhos automatizados de limpeza.
 #8.3.2    Level: 1    Role: D/V
 Verifique se as solicitações de exclusão iniciadas pelo usuário eliminam vetores, metadados, cópias em cache e índices derivados dentro de 30 dias.
 #8.3.3    Level: 2    Role: D
 Verifique se as exclusões lógicas são seguidas por destruição criptográfica dos blocos de armazenamento, caso o hardware suporte, ou pela destruição da chave do cofre de chaves.
 #8.3.4    Level: 3    Role: D/V
 Verifique se os vetores expirados são excluídos dos resultados da busca por vizinhos mais próximos em menos de 500 ms após a expiração.

---

### C8.4 Prevenir Inversão e Vazamento de Embeddings

Defesas recentes — sobreposição de ruído, redes de projeção, perturbação de neurônios de privacidade e criptografia na camada de aplicação — podem reduzir as taxas de inversão em nível de token para menos de 5%.

 #8.4.1    Level: 1    Role: V
 Verifique se existe um modelo formal de ameaça que cubra ataques de inversão, de associação e de inferência de atributos, e se ele é revisado anualmente.
 #8.4.2    Level: 2    Role: D/V
 Verifique se a criptografia na camada de aplicação ou a criptografia pesquisável protegem os vetores contra leituras diretas por administradores de infraestrutura ou pessoal da nuvem.
 #8.4.3    Level: 3    Role: V
 Verifique se os parâmetros de defesa (ε para DP, ruído σ, posto de projeção k) equilibram a privacidade ≥ 99% de proteção dos tokens e utilidade ≤ 3% de perda de precisão.
 #8.4.4    Level: 3    Role: D/V
 Verifique se as métricas de resistência à inversão fazem parte dos critérios de liberação para atualizações de modelos, com orçamentos de regressão definidos.

---

### C8.5 Aplicação de Escopo para Memória Específica do Usuário

O vazamento entre locatários continua sendo um dos principais riscos do RAG: consultas de similaridade filtradas de forma inadequada podem revelar documentos privados de outro cliente.

 #8.5.1    Level: 1    Role: D/V
 Verifique se toda consulta de recuperação é filtrada posteriormente pelo ID do inquilino/usuário antes de ser enviada ao prompt do LLM.
 #8.5.2    Level: 1    Role: D
 Verifique se os nomes das coleções ou IDs com namespace são salteados por usuário ou locatário para que os vetores não possam colidir entre escopos.
 #8.5.3    Level: 2    Role: D/V
 Verifique se os resultados de similaridade acima de um limite de distância configurável, mas fora do escopo do chamador, são descartados e acionam alertas de segurança.
 #8.5.4    Level: 2    Role: V
 Verifique se os testes de estresse multi-inquilino simulam consultas adversariais que tentam recuperar documentos fora do escopo e demonstram ausência total de vazamento.
 #8.5.5    Level: 3    Role: D/V
 Verifique se as chaves de criptografia são segregadas por locatário, garantindo isolamento criptográfico mesmo que o armazenamento físico seja compartilhado.

---

### C8.6 Segurança Avançada de Sistemas de Memória

Controles de segurança para arquiteturas de memória sofisticadas, incluindo memória episódica, semântica e de trabalho, com requisitos específicos de isolamento e validação.

 #8.6.1    Level: 1    Role: D/V
 Verifique se os diferentes tipos de memória (episódica, semântica, de trabalho) possuem contextos de segurança isolados com controles de acesso baseados em funções, chaves de criptografia separadas e padrões de acesso documentados para cada tipo de memória.
 #8.6.2    Level: 2    Role: D/V
 Verifique se os processos de consolidação de memória incluem validação de segurança para impedir a inserção de memórias maliciosas por meio da sanitização de conteúdo, verificação da fonte e checagem de integridade antes do armazenamento.
 #8.6.3    Level: 2    Role: D/V
 Verifique se as consultas de recuperação de memória são validadas e higienizadas para evitar a extração de informações não autorizadas por meio da análise de padrão de consultas, aplicação de controle de acesso e filtragem de resultados.
 #8.6.4    Level: 3    Role: D/V
 Verifique se os mecanismos de esquecimento de memória deletam informações sensíveis de forma segura com garantias de apagamento criptográfico usando exclusão de chaves, sobrescrita múltipla ou exclusão segura baseada em hardware com certificados de verificação.
 #8.6.5    Level: 3    Role: D/V
 Verifique se a integridade do sistema de memória é continuamente monitorada para modificações não autorizadas ou corrupção por meio de somas de verificação, registros de auditoria e alertas automatizados quando o conteúdo da memória muda fora das operações normais.

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

## 9 Orquestração Autônoma e Segurança de Ação Agentiva

### Objetivo de Controle

Garantir que sistemas de IA autônomos ou multiagentes possam executar apenas ações que sejam explicitamente intencionadas, autenticadas, auditáveis e dentro de limites definidos de custo e risco. Isso protege contra ameaças como Comprometimento de Sistema Autônomo, Uso Indevido de Ferramentas, Detecção de Loop de Agentes, Sequestro de Comunicação, Falsificação de Identidade, Manipulação de Enxames e Manipulação de Intenções.

---

### 9.1 Orçamentos para Planejamento de Tarefas de Agentes e Recursão

Regule planos recursivos e force pontos de verificação humanos para ações privilegiadas.

 #9.1.1    Level: 1    Role: D/V
 Verifique se a profundidade máxima de recursão, largura, tempo de relógio de parede, tokens e custo monetário por execução do agente estão configurados centralmente e controlados por versão.
 #9.1.2    Level: 1    Role: D/V
 Verifique se ações privilegiadas ou irreversíveis (por exemplo, commits de código, transferências financeiras) exigem aprovação humana explícita por meio de um canal auditável antes da execução.
 #9.1.3    Level: 2    Role: D
 Verifique se os monitores de recursos em tempo real acionam a interrupção do disjuntor quando qualquer limite de orçamento é excedido, interrompendo uma expansão adicional de tarefas.
 #9.1.4    Level: 2    Role: D/V
 Verifique se os eventos do disjuntor são registrados com ID do agente, condição de acionamento e estado do plano capturado para revisão forense.
 #9.1.5    Level: 3    Role: V
 Verifique se os testes de segurança cobrem cenários de exaustão de orçamento e planos fora de controle, confirmando a parada segura sem perda de dados.
 #9.1.6    Level: 3    Role: D
 Verifique se as políticas de orçamento estão expressas como política-como-código e são aplicadas em CI/CD para bloquear a deriva de configuração.

---

### 9.2 Isolamento por Sandbox de Plugins de Ferramentas

Isole as interações da ferramenta para evitar acesso não autorizado ao sistema ou execução de código.

 #9.2.1    Level: 1    Role: D/V
 Verifique se toda ferramenta/plugin é executado dentro de um sistema operacional, contêiner ou sandbox em nível WASM com políticas de menor privilégio para sistema de arquivos, rede e chamadas de sistema.
 #9.2.2    Level: 1    Role: D/V
 Verifique se as cotas de recursos do sandbox (CPU, memória, disco, saída de rede) e os tempos limite de execução são aplicados e registrados.
 #9.2.3    Level: 2    Role: D/V
 Verifique se os binários ou descritores da ferramenta estão assinados digitalmente; as assinaturas são validadas antes do carregamento.
 #9.2.4    Level: 2    Role: V
 Verifique se a telemetria do sandbox é transmitida para um SIEM; anomalias (por exemplo, tentativas de conexões de saída) geram alertas.
 #9.2.5    Level: 3    Role: V
 Verifique se os plugins de alto risco passam por revisão de segurança e testes de penetração antes da implantação em produção.
 #9.2.6    Level: 3    Role: D/V
 Verifique se as tentativas de fuga da sandbox são automaticamente bloqueadas e se o plugin infrator é colocado em quarentena enquanto aguarda investigação.

---

### 9.3 Loop Autônomo e Limitação de Custos

Detectar e interromper a recursão descontrolada entre agentes e explosões de custos.

 #9.3.1    Level: 1    Role: D/V
 Verifique se as chamadas entre agentes incluem um limite de saltos ou TTL que o ambiente de execução decrementa e aplica.
 #9.3.2    Level: 2    Role: D
 Verifique se os agentes mantêm um ID único de gráfico de invocação para identificar auto-invocações ou padrões cíclicos.
 #9.3.3    Level: 2    Role: D/V
 Verifique se os contadores cumulativos de unidade de computação e gastos são rastreados por cadeia de solicitação; ultrapassar o limite aborta a cadeia.
 #9.3.4    Level: 3    Role: V
 Verifique se a análise formal ou a verificação de modelos demonstra a ausência de recursão ilimitada nos protocolos dos agentes.
 #9.3.5    Level: 3    Role: D
 Verifique se eventos de interrupção de loop geram alertas e alimentam métricas de melhoria contínua.

---

### 9.4 Proteção Contra Uso Indevido a Nível de Protocolo

Canais de comunicação seguros entre agentes e sistemas externos para prevenir sequestro ou manipulação.

 #9.4.1    Level: 1    Role: D/V
 Verifique se todas as mensagens entre agente e ferramenta, assim como entre agentes, são autenticadas (por exemplo, TLS mútuo ou JWT) e criptografadas de ponta a ponta.
 #9.4.2    Level: 1    Role: D
 Verifique se os esquemas são rigorosamente validados; campos desconhecidos ou mensagens malformadas são rejeitados.
 #9.4.3    Level: 2    Role: D/V
 Verifique se as verificações de integridade (MACs ou assinaturas digitais) cobrem toda a carga útil da mensagem, incluindo os parâmetros da ferramenta.
 #9.4.4    Level: 2    Role: D
 Verifique se a proteção contra repetição (nonces ou janelas de timestamp) é aplicada na camada do protocolo.
 #9.4.5    Level: 3    Role: V
 Verifique se as implementações do protocolo passam por fuzzing e análise estática para identificar falhas de injeção ou desserialização.

---

### 9.5 Identidade do Agente e Evidência de Violação

Assegure que as ações sejam atribuíveis e as modificações detectáveis.

 #9.5.1    Level: 1    Role: D/V
 Verifique se cada instância do agente possui uma identidade criptográfica única (par de chaves ou credencial enraizada em hardware).
 #9.5.2    Level: 2    Role: D/V
 Verifique se todas as ações do agente são assinadas e possuem carimbo de data/hora; os registros incluem a assinatura para não repúdio.
 #9.5.3    Level: 2    Role: V
 Verifique se os logs à prova de adulteração são armazenados em um meio de gravação única ou somente acréscimo.
 #9.5.4    Level: 3    Role: D
 Verifique se as chaves de identidade são rotacionadas em uma programação definida e diante de indicadores de comprometimento.
 #9.5.5    Level: 3    Role: D/V
 Verifique se as tentativas de falsificação ou conflito de chaves acionam a quarentena imediata do agente afetado.

---

### 9.6 Redução de Riscos em Enxames Multiagentes

Mitigue os riscos de comportamento coletivo por meio de isolamento e modelagem formal de segurança.

 #9.6.1    Level: 1    Role: D/V
 Verifique se os agentes que operam em diferentes domínios de segurança executam em sandboxes de tempo de execução isolados ou em segmentos de rede.
 #9.6.2    Level: 3    Role: V
 Verifique se os comportamentos do enxame são modelados e formalmente verificados quanto à vivacidade e segurança antes da implantação.
 #9.6.3    Level: 3    Role: D
 Verifique se os monitores em tempo de execução detectam padrões emergentes de risco (por exemplo, oscilações, impasses) e iniciam ações corretivas.

---

### 9.7 Autenticação / Autorização de Usuário e Ferramenta

Implemente controles de acesso robustos para cada ação acionada por agentes.

 #9.7.1    Level: 1    Role: D/V
 Verifique se os agentes se autenticam como principais de primeira classe para sistemas downstream, nunca reutilizando as credenciais do usuário final.
 #9.7.2    Level: 2    Role: D
 Verifique se as políticas de autorização detalhadas restringem quais ferramentas um agente pode invocar e quais parâmetros ele pode fornecer.
 #9.7.3    Level: 2    Role: V
 Verifique se as verificações de privilégios são reavaliadas a cada chamada (autorização contínua), e não apenas no início da sessão.
 #9.7.4    Level: 3    Role: D
 Verifique se os privilégios delegados expiram automaticamente e exigem novo consentimento após o tempo limite ou mudança de escopo.

---

### 9.8 Segurança na Comunicação entre Agentes

Criptografe e proteja a integridade de todas as mensagens entre agentes para impedir espionagem e adulteração.

 #9.8.1    Level: 1    Role: D/V
 Verifique se a autenticação mútua e a criptografia de segredo perfeito à prova de futuras interceptações (por exemplo, TLS 1.3) são obrigatórias para os canais do agente.
 #9.8.2    Level: 1    Role: D
 Verifique se a integridade e a origem da mensagem são validadas antes do processamento; falhas geram alertas e descartam a mensagem.
 #9.8.3    Level: 2    Role: D/V
 Verifique se os metadados de comunicação (carimbos de data/hora, números de sequência) são registrados para apoiar a reconstrução forense.
 #9.8.4    Level: 3    Role: V
 Verifique se a verificação formal ou a verificação de modelos confirma que as máquinas de estado do protocolo não podem ser levadas a estados inseguros.

---

### 9.9 Verificação de Intenção e Aplicação de Restrições

Validar se as ações do agente estão alinhadas com a intenção declarada pelo usuário e as restrições do sistema.

 #9.9.1    Level: 1    Role: D
 Verifique se os solucionadores de restrições pré-execução verificam as ações propostas em relação às regras rígidas de segurança e políticas pré-definidas.
 #9.9.2    Level: 2    Role: D/V
 Verifique se ações de alto impacto (financeiras, destrutivas, sensíveis à privacidade) exigem confirmação explícita da intenção por parte do usuário que as iniciou.
 #9.9.3    Level: 2    Role: V
 Verifique se as verificações de pós-condição validam que as ações concluídas alcançaram os efeitos pretendidos sem efeitos colaterais; discrepâncias acionam reversão.
 #9.9.4    Level: 3    Role: V
 Verifique se os métodos formais (por exemplo, verificação de modelos, prova de teoremas) ou testes baseados em propriedades demonstram que os planos do agente satisfazem todas as restrições declaradas.
 #9.9.5    Level: 3    Role: D
 Verifique se incidentes de incompatibilidade de intenção ou violação de restrição alimentam ciclos de melhoria contínua e compartilhamento de inteligência sobre ameaças.

---

### 9.10 Segurança da Estratégia de Raciocínio do Agente

Seleção e execução seguras de diferentes estratégias de raciocínio, incluindo as abordagens ReAct, Cadeia de Pensamento e Árvore de Pensamentos.

 #9.10.1    Level: 1    Role: D/V
 Verifique se a seleção da estratégia de raciocínio utiliza critérios determinísticos (complexidade da entrada, tipo de tarefa, contexto de segurança) e se entradas idênticas produzem seleções de estratégia idênticas dentro do mesmo contexto de segurança.
 #9.10.2    Level: 1    Role: D/V
 Verifique se cada estratégia de raciocínio (ReAct, Chain-of-Thought, Tree-of-Thoughts) possui validação de entrada dedicada, sanitização de saída e limites de tempo de execução específicos para sua abordagem cognitiva.
 #9.10.3    Level: 2    Role: D/V
 Verifique se as transições da estratégia de raciocínio são registradas com contexto completo, incluindo características de entrada, valores dos critérios de seleção e metadados de execução para reconstrução da trilha de auditoria.
 #9.10.4    Level: 2    Role: D/V
 Verifique se o raciocínio Tree-of-Thoughts inclui mecanismos de poda de ramificações que encerram a exploração quando são detectadas violações de políticas, limites de recursos ou barreiras de segurança.
 #9.10.5    Level: 2    Role: D/V
 Verifique se os ciclos ReAct (Raciocinar-Agir-Observar) incluem pontos de verificação de validação em cada fase: verificação da etapa de raciocínio, autorização da ação e sanitização da observação antes de prosseguir.
 #9.10.6    Level: 3    Role: D/V
 Verifique se as métricas de desempenho da estratégia de raciocínio (tempo de execução, uso de recursos, qualidade da saída) são monitoradas com alertas automatizados quando as métricas se desviam além dos limiares configurados.
 #9.10.7    Level: 3    Role: D/V
 Verifique se as abordagens de raciocínio híbrido que combinam múltiplas estratégias mantêm a validação de entrada e as restrições de saída de todas as estratégias constituintes, sem contornar quaisquer controles de segurança.
 #9.10.8    Level: 3    Role: D/V
 Verifique que a estratégia de raciocínio para testes de segurança inclui fuzzing com entradas malformadas, prompts adversariais projetados para forçar a mudança de estratégia e testes de condições de limite para cada abordagem cognitiva.

---

### 9.11 Gerenciamento do Estado do Ciclo de Vida do Agente e Segurança

Inicialização segura do agente, transições de estado e terminação com trilhas de auditoria criptográficas e procedimentos de recuperação definidos.

 #9.11.1    Level: 1    Role: D/V
 Verifique se a inicialização do agente inclui o estabelecimento de identidade criptográfica com credenciais suportadas por hardware e registros de auditoria de inicialização imutáveis contendo ID do agente, carimbo de data/hora, hash da configuração e parâmetros de inicialização.
 #9.11.2    Level: 2    Role: D/V
 Verifique se as transições de estado do agente estão assinadas criptograficamente, carimbadas com horário e registradas com contexto completo, incluindo eventos desencadeadores, hash do estado anterior, hash do novo estado e validações de segurança realizadas.
 #9.11.3    Level: 2    Role: D/V
 Verifique se os procedimentos de desligamento do agente incluem a limpeza segura da memória usando apagamento criptográfico ou sobrescrita múltipla, revogação de credenciais com notificação à autoridade certificadora e geração de certificados de término à prova de violação.
 #9.11.4    Level: 3    Role: D/V
 Verifique se os mecanismos de recuperação do agente validam a integridade do estado usando somas de verificação criptográficas (mínimo SHA-256) e fazem rollback para estados conhecidos e estáveis quando uma corrupção é detectada, com alertas automatizados e requisitos de aprovação manual.
 #9.11.5    Level: 3    Role: D/V
 Verifique se os mecanismos de persistência do agente criptografam os dados de estado sensíveis com chaves AES-256 por agente e implementam a rotação segura de chaves em cronogramas configuráveis (máximo de 90 dias) com implantação sem tempo de inatividade.

---

### 9.12 Estrutura de Segurança para Integração de Ferramentas

Controles de segurança para carregamento dinâmico de ferramentas, execução e validação de resultados com processos definidos de avaliação de risco e aprovação.

 #9.12.1    Level: 1    Role: D/V
 Verifique se os descritores da ferramenta incluem metadados de segurança especificando os privilégios necessários (leitura/gravação/execução), níveis de risco (baixo/médio/alto), limites de recursos (CPU, memória, rede) e requisitos de validação documentados nos manifestos da ferramenta.
 #9.12.2    Level: 1    Role: D/V
 Verifique se os resultados da execução da ferramenta são validados em relação aos esquemas esperados (Esquema JSON, Esquema XML) e às políticas de segurança (sanitização de saída, classificação de dados) antes da integração, com limites de tempo e procedimentos de tratamento de erros.
 #9.12.3    Level: 2    Role: D/V
 Verifique se os registros de interação da ferramenta incluem um contexto de segurança detalhado, incluindo uso de privilégios, padrões de acesso a dados, tempo de execução, consumo de recursos e códigos de retorno, com registro estruturado para integração com SIEM.
 #9.12.4    Level: 2    Role: D/V
 Verifique se os mecanismos de carregamento dinâmico de ferramentas validam assinaturas digitais utilizando a infraestrutura de PKI e implementam protocolos de carregamento seguros com isolamento em sandbox e verificação de permissões antes da execução.
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

Assegure que os modelos de IA permaneçam confiáveis, preservem a privacidade e sejam resistentes a abusos ao enfrentar ataques de evasão, inferência, extração ou envenenamento.

---

### 10.1 Alinhamento e Segurança do Modelo

Proteja contra resultados prejudiciais ou que violem políticas.

 #10.1.1    Level: 1    Role: D/V
 Verifique se um conjunto de testes de alinhamento (prompts de red-team, sondagens de jailbreak, conteúdo proibido) está sob controle de versão e é executado em cada lançamento do modelo.
 #10.1.2    Level: 1    Role: D
 Verifique se as barreiras de recusa e de conclusão segura estão sendo aplicadas.
 #10.1.3    Level: 2    Role: D/V
 Verifique se um avaliador automatizado mede a taxa de conteúdo prejudicial e sinaliza regressões além de um limite estabelecido.
 #10.1.4    Level: 2    Role: D
 Verifique se o treinamento contra jailbreak está documentado e é reproduzível.
 #10.1.5    Level: 3    Role: V
 Verifique se as provas formais de conformidade com a política ou o monitoramento certificado abrangem domínios críticos.

---

### 10.2 Endurecimento contra Exemplos Adversariais

Aumentar a resiliência a entradas manipuladas. Treinamento adversarial robusto e pontuação em benchmarks são as melhores práticas atuais.

 #10.2.1    Level: 1    Role: D
 Verifique se os repositórios do projeto incluem configurações de treinamento adversarial com sementes reproduzíveis.
 #10.2.2    Level: 2    Role: D/V
 Verifique se a detecção de exemplos adversariais gera alertas de bloqueio em pipelines de produção.
 #10.2.4    Level: 3    Role: V
 Verifique se as provas de robustez certificada ou certificados de limites de intervalo cobrem pelo menos as principais classes críticas.
 #10.2.5    Level: 3    Role: V
 Verifique se os testes de regressão usam ataques adaptativos para confirmar que não há perda mensurável de robustez.

---

### 10.3 Mitigação de Inferência de Associação

Limitar a capacidade de decidir se um registro estava nos dados de treinamento. A privacidade diferencial e a máscara de pontuação de confiança continuam sendo as defesas conhecidas mais eficazes.

 #10.3.1    Level: 1    Role: D
 Verifique se a regularização da entropia por consulta ou a escalagem de temperatura reduz previsões excessivamente confiantes.
 #10.3.2    Level: 2    Role: D
 Verifique se o treinamento emprega otimização diferencialmente privada limitada por ε para conjuntos de dados sensíveis.
 #10.3.3    Level: 2    Role: V
 Verifique se as simulações de ataque (modelo sombra ou caixa-preta) apresentam AUC de ataque ≤ 0,60 nos dados retidos.

---

### 10.4 Resistência à Inversão de Modelo

Evitar a reconstrução de atributos privados. Pesquisas recentes destacam a truncagem de saída e garantias de DP como defesas práticas.

 #10.4.1    Level: 1    Role: D
 Verifique se os atributos sensíveis nunca são transmitidos diretamente; quando necessário, utilize agrupamentos (buckets) ou transformações unidirecionais.
 #10.4.2    Level: 1    Role: D/V
 Verifique se os limites de taxa de consulta restringem consultas adaptativas repetidas do mesmo principal.
 #10.4.3    Level: 2    Role: D
 Verifique se o modelo foi treinado com ruído preservador de privacidade.

---

### 10.5 Defesa contra Extração de Modelo

Detectar e impedir clonagem não autorizada. Recomenda-se o uso de marca d'água e análise de padrão de consulta.

 #10.5.1    Level: 1    Role: D
 Verifique se os gateways de inferência aplicam limites de taxa globais e por chave de API ajustados ao limite de memorização do modelo.
 #10.5.2    Level: 2    Role: D/V
 Verifique se as estatísticas de entropia da consulta e pluralidade de entrada alimentam um detector de extração automatizado.
 #10.5.3    Level: 2    Role: V
 Verifique se marcas d'água frágeis ou probabilísticas podem ser comprovadas com p < 0,01 em ≤ 1.000 consultas contra um clone suspeito.
 #10.5.4    Level: 3    Role: D
 Verifique se as chaves de marca d'água e os conjuntos de gatilho estão armazenados em um módulo de segurança de hardware e são rotacionados anualmente.
 #10.5.5    Level: 3    Role: V
 Verifique se os eventos de alerta de extração incluem as consultas infratoras e estão integrados com os playbooks de resposta a incidentes.

---

### 10.6 Detecção de Dados Envenenados no Tempo de Inferência

Identificar e neutralizar entradas com portas traseiras ou envenenadas.

 #10.6.1    Level: 1    Role: D
 Verifique se as entradas passam por um detector de anomalias (por exemplo, STRIP, pontuação de consistência) antes da inferência do modelo.
 #10.6.2    Level: 1    Role: V
 Verifique se os limiares do detector estão ajustados em conjuntos de validação limpos/envenenados para alcançar menos de 5% de falsos positivos.
 #10.6.3    Level: 2    Role: D
 Verifique se as entradas sinalizadas como contaminadas ativam o bloqueio suave e os fluxos de trabalho de revisão humana.
 #10.6.4    Level: 2    Role: V
 Verifique se os detectores são submetidos a testes de estresse com ataques de backdoor adaptativos e sem gatilho.
 #10.6.5    Level: 3    Role: D
 Verifique se as métricas de eficácia de detecção são registradas e reavaliadas periodicamente com novas informações de inteligência sobre ameaças.

---

### 10.7 Adaptação Dinâmica da Política de Segurança

Atualizações em tempo real da política de segurança baseadas em inteligência de ameaças e análise comportamental.

 #10.7.1    Level: 1    Role: D/V
 Verifique se as políticas de segurança podem ser atualizadas dinamicamente sem reiniciar o agente, mantendo a integridade da versão da política.
 #10.7.2    Level: 2    Role: D/V
 Verifique se as atualizações de políticas estão assinadas criptograficamente por pessoal de segurança autorizado e validadas antes da aplicação.
 #10.7.3    Level: 2    Role: D/V
 Verifique se as alterações dinâmicas de políticas são registradas com trilhas completas de auditoria, incluindo justificativas, cadeias de aprovação e procedimentos de reversão.
 #10.7.4    Level: 3    Role: D/V
 Verifique se os mecanismos de segurança adaptativa ajustam a sensibilidade da detecção de ameaças com base no contexto de risco e nos padrões comportamentais.
 #10.7.5    Level: 3    Role: D/V
 Verifique se as decisões de adaptação da política são explicáveis e incluem trilhas de evidências para revisão da equipe de segurança.

---

### 10.8 Análise de Segurança Baseada em Reflexão

Validação de segurança por meio de autorreflexão do agente e análise metacognitiva.

 #10.8.1    Level: 1    Role: D/V
 Verifique se os mecanismos de reflexão do agente incluem autoavaliação focada em segurança das decisões e ações.
 #10.8.2    Level: 2    Role: D/V
 Verifique se as saídas de reflexão são validadas para evitar a manipulação dos mecanismos de autoavaliação por entradas adversariais.
 #10.8.3    Level: 2    Role: D/V
 Verifique se a análise de segurança meta-cognitiva identifica possíveis vieses, manipulações ou comprometimentos nos processos de raciocínio do agente.
 #10.8.4    Level: 3    Role: D/V
 Verifique se os avisos de segurança baseados em reflexão acionam monitoramento aprimorado e fluxos de trabalho potenciais para intervenção humana.
 #10.8.5    Level: 3    Role: D/V
 Verifique se o aprendizado contínuo a partir de reflexões de segurança melhora a detecção de ameaças sem degradar a funcionalidade legítima.

---

### 10.9 Segurança em Evolução e Autoaperfeiçoamento

Controles de segurança para sistemas agentes capazes de auto-modificação e evolução.

 #10.9.1    Level: 1    Role: D/V
 Verifique se as capacidades de auto-modificação estão restritas a áreas seguras designadas com limites formais de verificação.
 #10.9.2    Level: 2    Role: D/V
 Verifique se as propostas de evolução passam por uma avaliação de impacto de segurança antes da implementação.
 #10.9.3    Level: 2    Role: D/V
 Verificar se os mecanismos de autoaperfeiçoamento incluem capacidades de reversão com verificação de integridade.
 #10.9.4    Level: 3    Role: D/V
 Verifique se a segurança do meta-aprendizado previne a manipulação adversarial dos algoritmos de melhoria.
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

Manter garantias rigorosas de privacidade em todo o ciclo de vida da IA—coleta, treinamento, inferência e resposta a incidentes—de modo que os dados pessoais sejam processados apenas com consentimento claro, escopo mínimo necessário, exclusão comprovável e garantias formais de privacidade.

---

### 11.1 Anonimização e Minimização de Dados

 #11.1.1    Level: 1    Role: D/V
 Verifique se os identificadores diretos e quase-identificadores foram removidos ou codificados com hash.
 #11.1.2    Level: 2    Role: D/V
 Verifique se auditorias automatizadas medem k-anonimato/l-diversidade e alertam quando os limites caem abaixo da política.
 #11.1.3    Level: 2    Role: V
 Verifique se os relatórios de importância de características do modelo comprovam que não há vazamento de identificadores além de ε = 0,01 em informação mútua.
 #11.1.4    Level: 3    Role: V
 Verifique se provas formais ou certificação por dados sintéticos mostram risco de reidentificação ≤ 0,05, mesmo sob ataques de ligação.

---

### 11.2 Direito ao Esquecimento e Aplicação da Exclusão

 #11.2.1    Level: 1    Role: D/V
 Verifique se as solicitações de exclusão de dados do titular são propagadas para conjuntos de dados brutos, pontos de verificação, embeddings, logs e backups dentro dos acordos de nível de serviço de menos de 30 dias.
 #11.2.2    Level: 2    Role: D
 Verifique se as rotinas de "desaprendizado de máquina" realmente re-treinam ou aproximam a remoção usando algoritmos certificados de desaprendizado.
 #11.2.3    Level: 2    Role: V
 Verifique que a avaliação do modelo sombra prova que os registros esquecidos influenciam menos de 1% dos resultados após o esquecimento.
 #11.2.4    Level: 3    Role: V
 Verifique se os eventos de exclusão são registrados de forma imutável e auditáveis para os reguladores.

---

### 11.3 Salvaguardas de Privacidade Diferencial

 #11.3.1    Level: 2    Role: D/V
 Verifique se os painéis de controle de contabilização da perda de privacidade alertam quando o ε acumulado excede os limites da política.
 #11.3.2    Level: 2    Role: V
 Verifique se as auditorias de privacidade de caixa-preta estimam ε̂ dentro de 10% do valor declarado.
 #11.3.3    Level: 3    Role: V
 Verifique se as provas formais cobrem todos os ajustes finos pós-treinamento e embeddings.

---

### 11.4 Limitação de Propósito e Proteção contra Expansão de Escopo

 #11.4.1    Level: 1    Role: D
 Verifique se cada conjunto de dados e ponto de verificação do modelo possui uma etiqueta de propósito legível por máquina alinhada ao consentimento original.
 #11.4.2    Level: 1    Role: D/V
 Verificar se os monitores em tempo de execução detectam consultas inconsistentes com o propósito declarado e acionam uma recusa suave.
 #11.4.3    Level: 3    Role: D
 Verifique se os controles de política como código bloqueiam a reimplantação de modelos em novos domínios sem revisão de DPIA.
 #11.4.4    Level: 3    Role: V
 Verifique se as provas formais de rastreabilidade demonstram que todo o ciclo de vida dos dados pessoais permanece dentro do escopo consentido.

---

### 11.5 Gerenciamento de Consentimento e Rastreio com Base Legal

 #11.5.1    Level: 1    Role: D/V
 Verifique se uma Plataforma de Gerenciamento de Consentimento (CMP) registra o status de opt-in, o propósito e o período de retenção por sujeito de dados.
 #11.5.2    Level: 2    Role: D
 Verifique se as APIs expõem tokens de consentimento; os modelos devem validar o escopo do token antes da inferência.
 #11.5.3    Level: 2    Role: D/V
 Verifique se o consentimento negado ou retirado interrompe os pipelines de processamento dentro de 24 horas.

---

### 11.6 Aprendizado Federado com Controles de Privacidade

 #11.6.1    Level: 1    Role: D
 Verifique se as atualizações do cliente utilizam adição de ruído de privacidade diferencial local antes da agregação.
 #11.6.2    Level: 2    Role: D/V
 Verifique se as métricas de treinamento são diferencialmente privadas e nunca revelam a perda de um único cliente.
 #11.6.3    Level: 2    Role: V
 Verifique se a agregação resistente a envenenamento (por exemplo, Krum/Trimmed-Mean) está habilitada.
 #11.6.4    Level: 3    Role: V
 Verifique se as provas formais demonstram um orçamento geral de ε com menos de 5 de perda de utilidade.

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

Esta seção fornece requisitos para oferecer visibilidade em tempo real e forense sobre o que o modelo e outros componentes de IA veem, fazem e retornam, para que as ameaças possam ser detectadas, triadas e analisadas.

### C12.1 Registro de Requisições e Respostas

 #12.1.1    Level: 1    Role: D/V
 Verifique se todas as solicitações dos usuários e as respostas do modelo são registradas com metadados apropriados (por exemplo, carimbo de data/hora, ID do usuário, ID da sessão, versão do modelo).
 #12.1.2    Level: 1    Role: D/V
 Verifique se os logs são armazenados em repositórios seguros, com controle de acesso, políticas de retenção apropriadas e procedimentos de backup.
 #12.1.3    Level: 1    Role: D/V
 Verifique se os sistemas de armazenamento de logs implementam criptografia em repouso e em trânsito para proteger informações sensíveis contidas nos logs.
 #12.1.4    Level: 1    Role: D/V
 Verifique se os dados sensíveis em prompts e saídas são automaticamente redigidos ou mascarados antes do registro, com regras de redação configuráveis para informações pessoais identificáveis (PII), credenciais e informações proprietárias.
 #12.1.5    Level: 2    Role: D/V
 Verifique se as decisões de políticas e as ações de filtragem de segurança são registradas com detalhes suficientes para permitir auditoria e depuração dos sistemas de moderação de conteúdo.
 #12.1.6    Level: 2    Role: D/V
 Verifique se a integridade dos logs está protegida por meio, por exemplo, de assinaturas criptográficas ou armazenamento somente para gravação.

---

### C12.2 Detecção e Alerta de Abuso

 #12.2.1    Level: 1    Role: D/V
 Verifique se o sistema detecta e alerta sobre padrões conhecidos de jailbreak, tentativas de injeção de prompts e entradas adversariais utilizando detecção baseada em assinaturas.
 #12.2.2    Level: 1    Role: D/V
 Verifique se o sistema se integra com as plataformas existentes de Gerenciamento de Informações e Eventos de Segurança (SIEM) utilizando formatos padrão de registro e protocolos.
 #12.2.3    Level: 2    Role: D/V
 Verifique se os eventos de segurança enriquecidos incluem contexto específico de IA, como identificadores de modelo, pontuações de confiança e decisões do filtro de segurança.
 #12.2.4    Level: 2    Role: D/V
 Verifique se a detecção de anomalias comportamentais identifica padrões de conversa incomuns, tentativas excessivas de repetição ou comportamentos de sondagem sistemática.
 #12.2.5    Level: 2    Role: D/V
 Verifique se os mecanismos de alerta em tempo real notificam as equipes de segurança quando possíveis violações de políticas ou tentativas de ataque são detectadas.
 #12.2.6    Level: 2    Role: D/V
 Verifique se regras personalizadas estão incluídas para detectar padrões de ameaça específicos de IA, incluindo tentativas coordenadas de jailbreak, campanhas de injeção de prompt e ataques de extração de modelo.
 #12.2.7    Level: 3    Role: D/V
 Verifique se os fluxos de trabalho automatizados de resposta a incidentes podem isolar modelos comprometidos, bloquear usuários mal-intencionados e escalonar eventos de segurança críticos.

---

### C12.3 Detecção de Deriva do Modelo

 #12.3.1    Level: 1    Role: D/V
 Verifique se o sistema monitora métricas básicas de desempenho, como precisão, pontuações de confiança, latência e taxas de erro, ao longo das versões do modelo e períodos de tempo.
 #12.3.2    Level: 2    Role: D/V
 Verifique se os alertas automáticos são acionados quando as métricas de desempenho excedem os limiares de degradação predefinidos ou desviam-se significativamente das linhas de base.
 #12.3.3    Level: 2    Role: D/V
 Verifique se os monitores de detecção de alucinação identificam e assinalam casos em que as saídas do modelo contêm informações factualmente incorretas, inconsistentes ou fabricadas.

---

### C12.4 Telemetria de Desempenho e Comportamento

 #12.4.1    Level: 1    Role: D/V
 Verifique se as métricas operacionais, incluindo latência de requisição, consumo de tokens, uso de memória e taxa de transferência, são continuamente coletadas e monitoradas.
 #12.4.2    Level: 1    Role: D/V
 Verifique se as taxas de sucesso e falha são monitoradas com a categorização dos tipos de erro e suas causas raízes.
 #12.4.3    Level: 2    Role: D/V
 Verifique se o monitoramento da utilização dos recursos inclui o uso de GPU/CPU, consumo de memória e requisitos de armazenamento, com alertas em caso de violações de limites.

---

### C12.5 Planejamento e Execução de Resposta a Incidentes de IA

 #12.5.1    Level: 1    Role: D/V
 Verifique se os planos de resposta a incidentes abordam especificamente eventos de segurança relacionados à IA, incluindo comprometimento de modelos, envenenamento de dados e ataques adversariais.
 #12.5.2    Level: 2    Role: D/V
 Verifique se as equipes de resposta a incidentes têm acesso a ferramentas forenses específicas de IA e expertise para investigar o comportamento do modelo e vetores de ataque.
 #12.5.3    Level: 3    Role: D/V
 Verifique se a análise pós-incidente inclui considerações sobre o re-treinamento do modelo, atualizações dos filtros de segurança e a integração das lições aprendidas nos controles de segurança.

---

### C12.5 Detecção de Degradação de Desempenho de IA

Monitorar e detectar a degradação no desempenho e na qualidade do modelo de IA ao longo do tempo.

 #12.5.1    Level: 1    Role: D/V
 Verifique se a precisão, precisão, recall e as pontuações F1 do modelo são continuamente monitoradas e comparadas com os limiares de referência.
 #12.5.2    Level: 1    Role: D/V
 Verifique se a detecção de deriva de dados monitora as mudanças na distribuição de entrada que podem impactar o desempenho do modelo.
 #12.5.3    Level: 2    Role: D/V
 Verifique se a detecção de drift conceitual identifica mudanças na relação entre entradas e saídas esperadas.
 #12.5.4    Level: 2    Role: D/V
 Verifique se a degradação do desempenho aciona alertas automáticos e inicia fluxos de trabalho de retreinamento ou substituição do modelo.
 #12.5.5    Level: 3    Role: V
 Verifique se a análise da causa raiz da degradação correlaciona quedas de desempenho com alterações nos dados, problemas na infraestrutura ou fatores externos.

---

### C12.6 Visualização de DAG e Segurança do Fluxo de Trabalho

Proteja os sistemas de visualização de fluxos de trabalho contra vazamento de informações e ataques de manipulação.

 #12.6.1    Level: 1    Role: D/V
 Verifique se os dados de visualização do DAG são higienizados para remover informações sensíveis antes do armazenamento ou transmissão.
 #12.6.2    Level: 1    Role: D/V
 Verifique se os controles de acesso à visualização do fluxo de trabalho garantem que apenas usuários autorizados possam visualizar os caminhos de decisão do agente e os rastros de raciocínio.
 #12.6.3    Level: 2    Role: D/V
 Verifique se a integridade dos dados do DAG está protegida por meio de assinaturas criptográficas e mecanismos de armazenamento à prova de violação.
 #12.6.4    Level: 2    Role: D/V
 Verifique se os sistemas de visualização de fluxo de trabalho implementam validação de entrada para prevenir ataques de injeção através de dados manipulados de nós ou arestas.
 #12.6.5    Level: 3    Role: D/V
 Verifique se as atualizações em tempo real do DAG são limitadas em taxa e validadas para prevenir ataques de negação de serviço em sistemas de visualização.

---

### C12.7 Monitoramento Proativo do Comportamento de Segurança

Detecção e prevenção de ameaças de segurança por meio da análise proativa do comportamento de agentes.

 #12.7.1    Level: 1    Role: D/V
 Verifique se os comportamentos proativos dos agentes são validados em termos de segurança antes da execução, com integração da avaliação de riscos.
 #12.7.2    Level: 2    Role: D/V
 Verifique se os gatilhos de iniciativa autônoma incluem avaliação do contexto de segurança e análise do panorama de ameaças.
 #12.7.3    Level: 2    Role: D/V
 Verifique se os padrões de comportamento proativo são analisados quanto a potenciais implicações de segurança e consequências não intencionais.
 #12.7.4    Level: 3    Role: D/V
 Verifique se as ações proativas críticas para a segurança requerem cadeias de aprovação explícitas com trilhas de auditoria.
 #12.7.5    Level: 3    Role: D/V
 Verifique se a detecção de anomalias comportamentais identifica desvios nos padrões do agente proativo que possam indicar comprometimento.

---

### Referências

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Supervisão Humana, Responsabilidade e Governança

### Objetivo de Controle

Este capítulo fornece requisitos para manter a supervisão humana e cadeias claras de responsabilidade em sistemas de IA, garantindo explicabilidade, transparência e governança ética ao longo do ciclo de vida da IA.

---

### C13.1 Mecanismos de Interruptor de Emergência (Kill-Switch) e Substituição (Override)

Fornecer caminhos de desligamento ou reversão quando um comportamento inseguro do sistema de IA for observado.

 #13.1.1    Level: 1    Role: D/V
 Verifique se existe um mecanismo manual de interrupção para cessar imediatamente a inferência e os resultados do modelo de IA.
 #13.1.2    Level: 1    Role: D
 Verifique se os controles de substituição são acessíveis apenas ao pessoal autorizado.
 #13.1.3    Level: 3    Role: D/V
 Verifique se os procedimentos de reversão podem retornar às versões anteriores do modelo ou às operações em modo seguro.
 #13.1.4    Level: 3    Role: V
 Verifique se os mecanismos de substituição são testados regularmente.

---

### C13.2 Pontos de Verificação de Decisão com Intervenção Humana

Exigir aprovações humanas quando os riscos ultrapassam limites predefinidos.

 #13.2.1    Level: 1    Role: D/V
 Verifique se decisões de IA de alto risco exigem aprovação humana explícita antes da execução.
 #13.2.2    Level: 1    Role: D
 Verifique se os limites de risco estão claramente definidos e acionam automaticamente os fluxos de trabalho de revisão humana.
 #13.2.3    Level: 2    Role: D
 Verifique se decisões sensíveis ao tempo possuem procedimentos alternativos quando a aprovação humana não pode ser obtida dentro dos prazos exigidos.
 #13.2.4    Level: 3    Role: D/V
 Verifique se os procedimentos de escalonamento definem níveis claros de autoridade para diferentes tipos de decisão ou categorias de risco, se aplicável.

---

### C13.3 Cadeia de Responsabilidade e Auditabilidade

Registre as ações do operador e as decisões do modelo.

 #13.3.1    Level: 1    Role: D/V
 Verifique se todas as decisões do sistema de IA e intervenções humanas são registradas com carimbos de data e hora, identidades dos usuários e justificativas das decisões.
 #13.3.2    Level: 2    Role: D
 Verifique se os registros de auditoria não podem ser adulterados e incluem mecanismos de verificação de integridade.

---

### C13.4 Técnicas de IA Explicável

Importância de características superficiais, contrafactuais e explicações locais.

 #13.4.1    Level: 1    Role: D/V
 Verifique se os sistemas de IA fornecem explicações básicas para suas decisões em formato legível por humanos.
 #13.4.2    Level: 2    Role: V
 Verifique se a qualidade da explicação é validada por meio de estudos e métricas de avaliação humana.
 #13.4.3    Level: 3    Role: D/V
 Verifique se as pontuações de importância das características ou métodos de atribuição (SHAP, LIME, etc.) estão disponíveis para decisões críticas.
 #13.4.4    Level: 3    Role: V
 Verifique se as explicações contrafactuais mostram como os dados de entrada podem ser modificados para alterar os resultados, se aplicável ao caso de uso e ao domínio.

---

### C13.5 Cartões de Modelo e Divulgação de Uso

Manter fichas de modelo para uso pretendido, métricas de desempenho e considerações éticas.

 #13.5.1    Level: 1    Role: D
 Verifique se os cartões de modelo documentam os casos de uso pretendidos, limitações e modos de falha conhecidos.
 #13.5.2    Level: 1    Role: D/V
 Verifique se as métricas de desempenho para diferentes casos de uso aplicáveis são divulgadas.
 #13.5.3    Level: 2    Role: D
 Verifique se as considerações éticas, avaliações de viés, avaliações de justiça, características dos dados de treinamento e limitações conhecidas dos dados de treinamento estão documentadas e atualizadas regularmente.
 #13.5.4    Level: 2    Role: D/V
 Verifique se os cartões do modelo são controlados por versão e mantidos ao longo do ciclo de vida do modelo com rastreamento de alterações.

---

### C13.6 Quantificação da Incerteza

Propagar pontuações de confiança ou medidas de entropia nas respostas.

 #13.6.1    Level: 1    Role: D
 Verifique se os sistemas de IA fornecem pontuações de confiança ou medidas de incerteza com seus resultados.
 #13.6.2    Level: 2    Role: D/V
 Verifique se os limites de incerteza acionam uma revisão humana adicional ou caminhos alternativos de decisão.
 #13.6.3    Level: 2    Role: V
 Verifique se os métodos de quantificação de incerteza estão calibrados e validados em relação aos dados de referência.
 #13.6.4    Level: 3    Role: D/V
 Verifique se a propagação da incerteza é mantida através de fluxos de trabalho de IA em múltiplas etapas.

---

### C13.7 Relatórios de Transparência Voltados ao Usuário

Fornecer divulgações periódicas sobre incidentes, deriva e uso de dados.

 #13.7.1    Level: 1    Role: D/V
 Verifique se as políticas de uso de dados e as práticas de gestão de consentimento do usuário estão claramente comunicadas às partes interessadas.
 #13.7.2    Level: 2    Role: D/V
 Verifique se as avaliações de impacto da IA são realizadas e se os resultados estão incluídos nos relatórios.
 #13.7.3    Level: 2    Role: D/V
 Verifique se os relatórios de transparência publicados regularmente divulgam incidentes de IA e métricas operacionais em detalhes razoáveis.

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

Este glossário abrangente fornece definições dos principais termos de IA, ML e segurança usados em todo o AISVS para garantir clareza e entendimento comum.
​
Exemplo Adversarial: Uma entrada deliberadamente criada para causar um erro em um modelo de IA, frequentemente adicionando perturbações sutis imperceptíveis aos humanos.
​
Robustez Adversarial – A robustez adversarial em IA refere-se à capacidade de um modelo de manter seu desempenho e resistir a ser enganado ou manipulado por entradas maliciosas intencionalmente elaboradas para causar erros.
​
Agente – Agentes de IA são sistemas de software que utilizam IA para perseguir objetivos e realizar tarefas em nome dos usuários. Eles demonstram raciocínio, planejamento e memória, e possuem um nível de autonomia para tomar decisões, aprender e se adaptar.
​
IA Agente: sistemas de IA que podem operar com algum grau de autonomia para alcançar objetivos, frequentemente tomando decisões e realizando ações sem intervenção humana direta.
​
Controle de Acesso Baseado em Atributos (ABAC): Um paradigma de controle de acesso onde as decisões de autorização são baseadas em atributos do usuário, recurso, ação e ambiente, avaliados no momento da consulta.
​
Ataque de Porta dos Fundos: Um tipo de ataque de envenenamento de dados em que o modelo é treinado para responder de maneira específica a certos gatilhos, enquanto se comporta normalmente em outras situações.
​
Viés: Erros sistemáticos nos resultados de modelos de IA que podem levar a resultados injustos ou discriminatórios para certos grupos ou em contextos específicos.
​
Exploração de Viés: Uma técnica de ataque que aproveita vieses conhecidos em modelos de IA para manipular resultados ou saídas.
​
Cedar: Linguagem e mecanismo de política da Amazon para permissões granulares usadas na implementação de ABAC para sistemas de IA.
​
Cadeia de Pensamento: Uma técnica para melhorar o raciocínio em modelos de linguagem, gerando etapas intermediárias de raciocínio antes de produzir uma resposta final.
​
Disjuntores: Mecanismos que interrompem automaticamente as operações do sistema de IA quando determinados limites de risco são excedidos.
​
Vazamento de Dados: Exposição não intencional de informações sensíveis por meio dos resultados ou comportamento do modelo de IA.
​
Envenenamento de Dados: A corrupção deliberada dos dados de treino para comprometer a integridade do modelo, frequentemente para implantar portas dos fundos ou degradar o desempenho.
​
Privacidade Diferencial – Privacidade diferencial é uma estrutura matematicamente rigorosa para a divulgação de informações estatísticas sobre conjuntos de dados, protegendo a privacidade dos indivíduos. Ela permite que um detentor de dados compartilhe padrões agregados do grupo, limitando a informação vazada sobre indivíduos específicos.
​
Incorporação: Representações vetoriais densas de dados (texto, imagens, etc.) que capturam o significado semântico em um espaço de alta dimensionalidade.
​
Explicabilidade – A explicabilidade em IA é a capacidade de um sistema de IA de fornecer razões compreensíveis para humanos sobre suas decisões e previsões, oferecendo insights sobre seu funcionamento interno.
​
Inteligência Artificial Explicável (XAI): sistemas de IA projetados para fornecer explicações compreensíveis aos humanos sobre suas decisões e comportamentos por meio de várias técnicas e estruturas.
​
Aprendizado Federado: Uma abordagem de aprendizado de máquina onde modelos são treinados em múltiplos dispositivos descentralizados que possuem amostras de dados locais, sem a troca dos dados em si.
​
Guardrails: Restrições implementadas para impedir que sistemas de IA produzam resultados prejudiciais, tendenciosos ou indesejáveis.
​
Alucinação – Uma alucinação de IA refere-se a um fenômeno em que um modelo de IA gera informações incorretas ou enganosas que não são baseadas em seus dados de treinamento ou na realidade factual.
​
Human-in-the-Loop (HITL): Sistemas projetados para exigir supervisão, verificação ou intervenção humana em pontos cruciais de decisão.
​
Infraestrutura como Código (IaC): Gerenciamento e provisionamento de infraestrutura por meio de código em vez de processos manuais, permitindo a varredura de segurança e implantações consistentes.
​
Jailbreak: Técnicas usadas para contornar as barreiras de segurança em sistemas de IA, particularmente em grandes modelos de linguagem, para produzir conteúdo proibido.
​
Privilégio Mínimo: O princípio de segurança que concede apenas os direitos de acesso mínimos necessários para usuários e processos.
​
LIME (Explicações Locais Interpretáveis Agnósticas ao Modelo): Uma técnica para explicar as previsões de qualquer classificador de aprendizado de máquina aproximando-o localmente com um modelo interpretável.
​
Ataque de Inferência de Membro: Um ataque que visa determinar se um ponto de dados específico foi usado para treinar um modelo de aprendizado de máquina.
​
MITRE ATLAS: Panorama de Ameaças Adversariais para Sistemas de Inteligência Artificial; uma base de conhecimento sobre táticas e técnicas adversariais contra sistemas de IA.
​
Ficha do Modelo – Uma ficha do modelo é um documento que fornece informações padronizadas sobre o desempenho, limitações, usos pretendidos e considerações éticas de um modelo de IA para promover a transparência e o desenvolvimento responsável de IA.
​
Extração de Modelo: Um ataque onde um adversário consulta repetidamente um modelo alvo para criar uma cópia funcionalmente similar sem autorização.
​
Inversão de Modelo: Um ataque que tenta reconstruir os dados de treinamento analisando as saídas do modelo.
​
Gerenciamento do Ciclo de Vida do Modelo – O Gerenciamento do Ciclo de Vida do Modelo de IA é o processo de supervisão de todas as fases da existência de um modelo de IA, incluindo seu design, desenvolvimento, implantação, monitoramento, manutenção e eventual aposentadoria, para garantir que ele permaneça eficaz e alinhado com os objetivos.
​
Envenenamento de Modelo: Introdução de vulnerabilidades ou portas traseiras diretamente em um modelo durante o processo de treinamento.
​
Roubo/Roubo de Modelo: Extrair uma cópia ou aproximação de um modelo proprietário por meio de consultas repetidas.
​
Sistema Multiagente: Um sistema composto por múltiplos agentes de IA interagindo, cada um com potencialmente diferentes capacidades e objetivos.
​
OPA (Open Policy Agent): Um mecanismo de políticas de código aberto que permite a aplicação unificada de políticas em toda a pilha.
​
Aprendizado de Máquina Preservador de Privacidade (PPML): Técnicas e métodos para treinar e implantar modelos de ML enquanto protegem a privacidade dos dados de treinamento.
​
Injeção de Prompt: Um ataque onde instruções maliciosas são incorporadas nas entradas para substituir o comportamento planejado de um modelo.
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
Banco de Dados Vetorial: Um banco de dados especializado projetado para armazenar vetores de alta dimensão (incorporações) e realizar buscas eficientes por similaridade.
​
Varredura de Vulnerabilidades: Ferramentas automatizadas que identificam vulnerabilidades de segurança conhecidas em componentes de software, incluindo frameworks de IA e dependências.
​
Marcação d'água: Técnicas para embutir marcadores imperceptíveis em conteúdo gerado por IA para rastrear sua origem ou detectar geração por IA.
​
Vulnerabilidade Zero-Day: Uma vulnerabilidade previamente desconhecida que os atacantes podem explorar antes que os desenvolvedores criem e implementem uma correção.

## Apêndice B: Referências

### TODO

## Apêndice C: Governança e Documentação de Segurança de IA

### Objetivo

Este apêndice fornece requisitos fundamentais para estabelecer estruturas organizacionais, políticas e processos para governar a segurança de IA ao longo do ciclo de vida do sistema.

---

### AC.1 Adoção do Quadro de Gerenciamento de Riscos em IA

Fornecer um quadro formal para identificar, avaliar e mitigar riscos específicos de IA ao longo do ciclo de vida do sistema.

 #AC.1.1    Level: 1    Role: D/V
 Verifique se uma metodologia de avaliação de riscos específica para IA está documentada e implementada.
 #AC.1.2    Level: 2    Role: D
 Verifique se avaliações de risco são realizadas em pontos-chave no ciclo de vida da IA e antes de mudanças significativas.
 #AC.1.3    Level: 3    Role: D/V
 Verifique se o framework de gestão de riscos está alinhado com os padrões estabelecidos (por exemplo, NIST AI RMF).

---

### AC.2 Política e Procedimentos de Segurança em IA

Defina e aplique padrões organizacionais para o desenvolvimento, implantação e operação seguros de IA.

 #AC.2.1    Level: 1    Role: D/V
 Verifique se existem políticas de segurança de IA documentadas.
 #AC.2.2    Level: 2    Role: D
 Verifique se as políticas são revisadas e atualizadas pelo menos anualmente e após mudanças significativas no cenário de ameaças.
 #AC.2.3    Level: 3    Role: D/V
 Verifique se as políticas abrangem todas as categorias AISVS e os requisitos regulatórios aplicáveis.

---

### AC.3 Papéis e Responsabilidades para Segurança de IA

Estabeleça uma responsabilidade clara pela segurança da IA em toda a organização.

 #AC.3.1    Level: 1    Role: D/V
 Verifique se os papéis e responsabilidades de segurança em IA estão documentados.
 #AC.3.2    Level: 2    Role: D
 Verifique se as pessoas responsáveis possuem a expertise adequada em segurança.
 #AC.3.3    Level: 3    Role: D/V
 Verifique se um comitê de ética em IA ou conselho de governança foi estabelecido para sistemas de IA de alto risco.

---

### AC.4 Aplicação das Diretrizes de IA Ética

Garantir que os sistemas de IA operem de acordo com princípios éticos estabelecidos.

 #AC.4.1    Level: 1    Role: D/V
 Verifique se existem diretrizes éticas para o desenvolvimento e a implantação de IA.
 #AC.4.2    Level: 2    Role: D
 Verifique se existem mecanismos para detectar e relatar violações éticas.
 #AC.4.3    Level: 3    Role: D/V
 Verifique se revisões éticas regulares dos sistemas de IA implantados são realizadas.

---

### AC.5 Monitoramento de Conformidade Regulatória em IA

Mantenha a consciência e a conformidade com as regulamentações de IA em evolução.

 #AC.5.1    Level: 1    Role: D/V
 Verifique se existem processos para identificar as regulamentações de IA aplicáveis.
 #AC.5.2    Level: 2    Role: D
 Verifique se a conformidade com todos os requisitos regulatórios foi avaliada.
 #AC.5.3    Level: 3    Role: D/V
 Verifique se as mudanças regulatórias acionam revisões e atualizações oportunas nos sistemas de IA.

#### Referências

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Apêndice D: Governança e Verificação da Codificação Segura Assistida por IA

### Objetivo

Este capítulo define controles organizacionais básicos para o uso seguro e eficaz de ferramentas de codificação assistidas por IA durante o desenvolvimento de software, garantindo segurança e rastreabilidade ao longo do Ciclo de Vida do Desenvolvimento de Software (SDLC).

---

### AD.1 Fluxo de Trabalho de Codificação Segura Assistida por IA

Integrar ferramentas de IA no ciclo de vida de desenvolvimento de software seguro (SSDLC) da organização sem enfraquecer os controles de segurança existentes.

 #AD.1.1    Level: 1    Role: D/V
 Verifique se um fluxo de trabalho documentado descreve quando e como as ferramentas de IA podem gerar, refatorar ou revisar código.
 #AD.1.2    Level: 2    Role: D
 Verifique se o fluxo de trabalho corresponde a cada fase do SSDLC (design, implementação, revisão de código, testes, implantação).
 #AD.1.3    Level: 3    Role: D/V
 Verifique se as métricas (por exemplo, densidade de vulnerabilidades, tempo médio para detectar) são coletadas no código produzido por IA e comparadas com as linhas de base produzidas apenas por humanos.

---

### AD.2 Qualificação de Ferramentas de IA e Modelagem de Ameaças

Assegure-se de que as ferramentas de codificação de IA sejam avaliadas quanto às capacidades de segurança, riscos e impacto na cadeia de suprimentos antes da adoção.

 #AD.2.1    Level: 1    Role: D/V
 Verifique se um modelo de ameaça para cada ferramenta de IA identifica riscos de uso indevido, inversão de modelo, vazamento de dados e cadeia de dependência.
 #AD.2.2    Level: 2    Role: D
 Verifique se as avaliações das ferramentas incluem análise estática/dinâmica de quaisquer componentes locais e avaliação dos endpoints SaaS (TLS, autenticação/autorização, registro de logs).
 #AD.2.3    Level: 3    Role: D/V
 Verifique se as avaliações seguem um quadro reconhecido e são refeitas após mudanças significativas de versão.

---

### AD.3 Gestão Segura de Prompt e Contexto

Prevenir o vazamento de segredos, código proprietário e dados pessoais ao construir prompts ou contextos para modelos de IA.

 #AD.3.1    Level: 1    Role: D/V
 Verifique se as orientações escritas proíbem o envio de segredos, credenciais ou dados classificados em prompts.
 #AD.3.2    Level: 2    Role: D
 Verifique se os controles técnicos (redação do lado do cliente, filtros de contexto aprovados) removem automaticamente artefatos sensíveis.
 #AD.3.3    Level: 3    Role: D/V
 Verifique se os prompts e as respostas são tokenizados, criptografados em trânsito e em repouso, e se os períodos de retenção estão em conformidade com a política de classificação de dados.

---

### AD.4 Validação de Código Gerado por IA

Detectar e remediar vulnerabilidades introduzidas pela saída de IA antes que o código seja mesclado ou implantado.

 #AD.4.1    Level: 1    Role: D/V
 Verifique se o código gerado por IA está sempre sujeito à revisão humana de código.
 #AD.4.2    Level: 2    Role: D
 Verifique se os scanners automatizados (SAST/IAST/DAST) são executados em todas as pull requests contendo código gerado por IA e bloqueiem as mesclagens em caso de descobertas críticas.
 #AD.4.3    Level: 3    Role: D/V
 Verifique se os testes diferenciais fuzz ou os testes baseados em propriedades comprovam comportamentos críticos de segurança (por exemplo, validação de entrada, lógica de autorização).

---

### AD.5 Explicabilidade e Rastreabilidade das Sugestões de Código

Fornecer a auditores e desenvolvedores uma visão sobre por que uma sugestão foi feita e como ela evoluiu.

 #AD.5.1    Level: 1    Role: D/V
 Verifique se os pares de prompt/resposta são registrados com IDs de commit.
 #AD.5.2    Level: 2    Role: D
 Verifique se os desenvolvedores conseguem exibir citações do modelo (trechos de treinamento, documentação) que apoiem uma sugestão.
 #AD.5.3    Level: 3    Role: D/V
 Verifique se os relatórios de explicabilidade são armazenados juntamente com os artefatos de design e referenciados nas revisões de segurança, atendendo aos princípios de rastreabilidade da ISO/IEC 42001.

---

### AD.6 Feedback Contínuo e Ajuste Fino do Modelo

Melhore o desempenho de segurança do modelo ao longo do tempo, evitando deriva negativa.

 #AD.6.1    Level: 1    Role: D/V
 Verifique se os desenvolvedores podem sinalizar sugestões inseguras ou não conformes, e se as sinalizações são acompanhadas.
 #AD.6.2    Level: 2    Role: D
 Verifique se o feedback agregado informa o ajuste fino periódico ou a geração aumentada por recuperação com corpora de codificação segura verificados (por exemplo, OWASP Cheat Sheets).
 #AD.6.3    Level: 3    Role: D/V
 Verifique se um ambiente de avaliação em circuito fechado executa testes de regressão após cada ajuste fino; as métricas de segurança devem atender ou superar as linhas de base anteriores antes da implantação.

---

#### Referências

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Apêndice E: Exemplos de Ferramentas e Frameworks

### Objetivo

Este capítulo fornece exemplos de ferramentas e frameworks que podem apoiar a implementação ou o cumprimento de um requisito específico do AISVS. Esses exemplos não devem ser vistos como recomendações ou endossos pela equipe do AISVS ou pelo Projeto de Segurança GenAI da OWASP.

---

### AE.1 Governança de Dados de Treinamento e Gestão de Viés

Ferramentas utilizadas para análise de dados, governança e gerenciamento de viés.

 #AE.1.1    Section: 1.1
 Ferramentas de Inventário de Dados: Ferramentas de gerenciamento de inventário de dados como...
 #AE.1.2    Section: 1.2
 Criptografia em Trânsito Use TLS para aplicações baseadas em HTTPS, com ferramentas como openSSL e o python's`ssl`biblioteca.

---

### AE.2 Validação de Entrada do Usuário

Ferramentas para tratar e validar entradas de usuário.

 #AE.2.1    Section: 2.1
 Ferramentas de Defesa contra Injeção de Prompt: Utilize ferramentas de guardrail como o NeMo da NVIDIA ou Guardrails AI.

---

