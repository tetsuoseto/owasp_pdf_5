# Segurança da Cadeia de Suprimentos C6 para Modelos, Frameworks e Dados

## Objetivo de Controle

Ataques à cadeia de suprimentos de IA exploram modelos, frameworks ou conjuntos de dados de terceiros para inserir backdoors, viés ou código explorável. Esses controles fornecem rastreabilidade de ponta a ponta, gerenciamento de vulnerabilidades e monitoramento para proteger todo o ciclo de vida do modelo.

---

## C6.1 Avaliação e Proveniência de Modelos Pré-treinados

Avalie e autentique as origens, licenças e comportamentos ocultos de modelos de terceiros antes de qualquer ajuste fino ou implantação.

|   #   | Description                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Verifique se todo artefato de modelo de terceiros inclui um registro de proveniência assinado que identifica o repositório de origem e o hash do commit. |   1   | D/V  |
| 6.1.2 | Verifique se os modelos são escaneados quanto a camadas maliciosas ou gatilhos de Trojan usando ferramentas automatizadas antes da importação.           |   1   | D/V  |
| 6.1.3 | Verifique se o fine-tuning de transfer learning supera a avaliação adversarial para detectar comportamentos ocultos.                                     |   2   |  D   |
| 6.1.4 | Verifique se as licenças do modelo, as etiquetas de controle de exportação e as declarações de origem dos dados estão registradas em uma entrada ML‑BOM. |   2   |  V   |
| 6.1.5 | Verifique se os modelos de alto risco (pesos carregados publicamente, criadores não verificados) permanecem isolados até a revisão e aprovação humana.   |   3   | D/V  |

---

## C6.2 Varredura de Frameworks e Bibliotecas

Realize varreduras contínuas em frameworks e bibliotecas de ML para CVEs e códigos maliciosos, a fim de manter a pilha de execução segura.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Verifique se os pipelines de CI executam scanners de dependências em frameworks de IA e bibliotecas críticas.                                |   1   | D/V  |
| 6.2.2 | Verifique se vulnerabilidades críticas (CVSS ≥ 7,0) impedem a promoção para imagens de produção.                                             |   1   | D/V  |
| 6.2.3 | Verifique se a análise estática de código é executada em bibliotecas de ML bifurcadas ou fornecidas como dependências.                       |   2   |  D   |
| 6.2.4 | Verifique se as propostas de atualização do framework incluem uma avaliação de impacto de segurança referenciando os feeds públicos de CVE.  |   2   |  V   |
| 6.2.5 | Verifique se os sensores em tempo de execução alertam sobre carregamentos inesperados de bibliotecas dinâmicas que desviam do SBOM assinado. |   3   |  V   |

---

## C6.3 Fixação e Verificação de Dependências

Fixe cada dependência em resumos imutáveis e reproduza as compilações para garantir artefatos idênticos e livres de adulterações.

|   #   | Description                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.3.1 | Verifique se todos os gerenciadores de pacotes aplicam o travamento de versão por meio de arquivos de bloqueio.          |   1   | D/V  |
| 6.3.2 | Verifique se os resumos imutáveis são usados em vez de tags mutáveis nas referências de contêiner.                       |   1   | D/V  |
| 6.3.3 | Verifique se as verificações de build reprodutível comparam hashes entre execuções de CI para garantir saídas idênticas. |   2   |  D   |
| 6.3.4 | Verifique se as atestações de build são armazenadas por 18 meses para rastreabilidade de auditoria.                      |   2   |  V   |
| 6.3.5 | Verifique se as dependências expiradas acionam PRs automatizados para atualizar ou bifurcar versões fixadas.             |   3   |  D   |

---

## C6.4 Aplicação de Fonte Confiável

Permitir downloads de artefatos apenas de fontes verificadas criptograficamente e aprovadas pela organização, e bloquear todo o restante.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Verifique se os pesos do modelo, os conjuntos de dados e os contêineres são baixados apenas de domínios aprovados ou registros internos.       |   1   | D/V  |
| 6.4.2 | Verifique se as assinaturas Sigstore/Cosign validam a identidade do publicador antes que os artefatos sejam armazenados em cache localmente.   |   1   | D/V  |
| 6.4.3 | Verifique se os proxies de saída bloqueiam downloads de artefatos não autenticados para garantir a aplicação da política de fonte confiável.   |   2   |  D   |
| 6.4.4 | Verifique se as listas de permissões do repositório são revisadas trimestralmente com evidências de justificativa comercial para cada entrada. |   2   |  V   |
| 6.4.5 | Verifique se as violações de política acionam a quarentena dos artefatos e o rollback das execuções de pipeline dependentes.                   |   3   |  V   |

---

## C6.5 Avaliação de Risco de Conjuntos de Dados de Terceiros

Avalie conjuntos de dados externos quanto a envenenamento, viés e conformidade legal, e monitore-os durante todo o seu ciclo de vida.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Verifique se os conjuntos de dados externos passam por uma avaliação de risco de envenenamento (por exemplo, impressão digital de dados, detecção de valores discrepantes). |   1   | D/V  |
| 6.5.2 | Verifique se as métricas de viés (paridade demográfica, igualdade de oportunidade) são calculadas antes da aprovação do conjunto de dados.                                  |   1   |  D   |
| 6.5.3 | Verifique se a proveniência e os termos de licença dos conjuntos de dados estão capturados nas entradas do ML-BOM.                                                          |   2   |  V   |
| 6.5.4 | Verifique se o monitoramento periódico detecta deriva ou corrupção nos conjuntos de dados hospedados.                                                                       |   2   |  V   |
| 6.5.5 | Verifique se o conteúdo proibido (direitos autorais, informações pessoais identificáveis) é removido por meio de limpeza automatizada antes do treinamento.                 |   3   |  D   |

---

## C6.6 Monitoramento de Ataques na Cadeia de Suprimentos

Detecte ameaças na cadeia de suprimentos cedo através de feeds CVE, análises de logs de auditoria e simulações de equipes vermelhas.

|   #   | Description                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.6.1 | Verifique se os logs de auditoria de CI/CD são transmitidos para o SIEM para detectar puxadas de pacotes anômalas ou etapas de construção adulteradas.             |   1   |  V   |
| 6.6.2 | Verifique se os playbooks de resposta a incidentes incluem procedimentos de reversão para modelos ou bibliotecas comprometidos.                                    |   2   |  D   |
| 6.6.3 | Verifique se o enriquecimento de inteligência de ameaças marca indicadores específicos de ML (por exemplo, IoCs de envenenamento de modelo) na triagem de alertas. |   3   |  V   |

---

## C6.7 ML‑BOM para Artefatos de Modelo

Gerar e assinar SBOMs detalhados específicos para ML (ML-BOMs) para que os consumidores finais possam verificar a integridade dos componentes no momento da implantação.

|   #   | Description                                                                                                                                     | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Verifique se todo artefato do modelo publica um ML-BOM que lista conjuntos de dados, pesos, hiperparâmetros e licenças.                         |   1   | D/V  |
| 6.7.2 | Verifique se a geração de ML‑BOM e a assinatura Cosign estão automatizadas na Integração Contínua (CI) e são obrigatórias para a fusão (merge). |   1   | D/V  |
| 6.7.3 | Verifique se as verificações de completude do ML‑BOM falham na compilação se qualquer metadado do componente (hash, licença) estiver faltando.  |   2   |  D   |
| 6.7.4 | Verifique se os consumidores downstream podem consultar ML-BOMs via API para validar modelos importados no momento da implantação.              |   2   |  V   |
| 6.7.5 | Verifique se os ML‑BOMs estão sob controle de versão e comparados para detectar modificações não autorizadas.                                   |   3   |  V   |

---

## Referências

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

