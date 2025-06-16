# 9 Orchestration autonome et action agentique en sécurité

## Objectif de Controle

Garantir que les systèmes d'IA autonomes ou multi-agents ne puissent exécuter que des actions explicitement prévues, authentifiées, auditées, et limitées à des seuils de coûts et de risques définis. Cela protège contre des menaces telles que la compromission du système autonome, le mauvais usage des outils, la détection de boucle d'agent, le détournement de communication, l'usurpation d'identité, la manipulation de essaims, et la manipulation d'intention.

---

## 9.1 Budgets de planification des tâches des agents et de récursion

Limiter les plans récursifs et imposer des points de contrôle humains pour les actions privilégiées.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Vérifiez que la profondeur maximale de récursion, la largeur, le temps réel, les jetons et le coût monétaire par exécution d'agent sont configurés de manière centralisée et contrôlés par version.              |   1   | D/V  |
| 9.1.2 | Vérifiez que les actions privilégiées ou irréversibles (par exemple, les validations de code, les transferts financiers) nécessitent une approbation humaine explicite via un canal auditable avant l'exécution. |   1   | D/V  |
| 9.1.3 | Vérifiez que les moniteurs de ressources en temps réel déclenchent une interruption de disjoncteur lorsque tout seuil de budget est dépassé, arrêtant ainsi toute expansion supplémentaire des tâches.           |   2   |  D   |
| 9.1.4 | Vérifiez que les événements du disjoncteur sont enregistrés avec l'identifiant de l'agent, la condition de déclenchement et l'état du plan capturé pour un examen judiciaire.                                    |   2   | D/V  |
| 9.1.5 | Vérifier que les tests de sécurité couvrent les scénarios d'épuisement du budget et de dérive du plan, en confirmant un arrêt sûr sans perte de données.                                                         |   3   |  V   |
| 9.1.6 | Vérifiez que les politiques budgétaires sont exprimées sous forme de politique en tant que code et appliquées dans les pipelines CI/CD pour empêcher la dérive de configuration.                                 |   3   |  D   |

---

## 9.2 Environnement isolé pour les plugins d'outils

Isoler les interactions des outils afin d'empêcher tout accès non autorisé au système ou toute exécution de code.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.2.1 | Vérifiez que chaque outil/plugin s’exécute à l’intérieur d’un système d’exploitation, d’un conteneur ou d’un bac à sable au niveau WASM avec des politiques de système de fichiers, réseau et appels système à privilèges minimaux. |   1   | D/V  |
| 9.2.2 | Vérifiez que les quotas de ressources du bac à sable (CPU, mémoire, disque, sortie réseau) et les délais d'exécution sont appliqués et enregistrés.                                                                                 |   1   | D/V  |
| 9.2.3 | Vérifiez que les binaires ou descripteurs des outils sont signés numériquement ; les signatures sont validées avant le chargement.                                                                                                  |   2   | D/V  |
| 9.2.4 | Vérifiez que la télémétrie du bac à sable est transmise à un SIEM ; les anomalies (par exemple, les tentatives de connexions sortantes) déclenchent des alertes.                                                                    |   2   |  V   |
| 9.2.5 | Vérifiez que les plugins à haut risque subissent une revue de sécurité et des tests de pénétration avant leur déploiement en production.                                                                                            |   3   |  V   |
| 9.2.6 | Vérifiez que les tentatives d’évasion du bac à sable sont automatiquement bloquées et que le plugin fautif est mis en quarantaine en attente d’une enquête.                                                                         |   3   | D/V  |

---

## 9.3 Boucle Autonome et Limitation des Coûts

Détecter et arrêter la récursion incontrôlée entre agents et les explosions de coûts.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Vérifiez que les appels entre agents incluent une limite de saut ou un TTL que le runtime décrémente et applique.                                              |   1   | D/V  |
| 9.3.2 | Vérifiez que les agents conservent un ID unique de graphe d'invocation afin de détecter les auto-invocations ou les schémas cycliques.                         |   2   |  D   |
| 9.3.3 | Vérifiez que les compteurs cumulatifs d'unités de calcul et de dépenses sont suivis par chaîne de requêtes ; le dépassement de la limite interrompt la chaîne. |   2   | D/V  |
| 9.3.4 | Vérifiez que l'analyse formelle ou la vérification de modèle démontre l'absence de récursion non bornée dans les protocoles d'agent.                           |   3   |  V   |
| 9.3.5 | Vérifiez que les événements d'interruption de boucle génèrent des alertes et alimentent les métriques d'amélioration continue.                                 |   3   |  D   |

---

## 9.4 Protection contre les utilisations abusives au niveau du protocole

Canaux de communication sécurisés entre les agents et les systèmes externes pour empêcher le détournement ou la manipulation.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Vérifiez que tous les messages entre agent et outil ainsi qu'entre agents sont authentifiés (par exemple, TLS mutuel ou JWT) et chiffrés de bout en bout.     |   1   | D/V  |
| 9.4.2 | Vérifiez que les schémas sont strictement validés ; les champs inconnus ou les messages mal formés sont rejetés.                                              |   1   |  D   |
| 9.4.3 | Vérifiez que les contrôles d'intégrité (MAC ou signatures numériques) couvrent l'ensemble de la charge utile du message, y compris les paramètres de l'outil. |   2   | D/V  |
| 9.4.4 | Vérifiez que la protection contre la relecture (nonces ou fenêtres de timestamp) est appliquée au niveau du protocole.                                        |   2   |  D   |
| 9.4.5 | Vérifiez que les implémentations des protocoles font l'objet de fuzzing et d'analyses statiques pour détecter les failles d'injection ou de désérialisation.  |   3   |  V   |

---

## 9.5 Identité de l'agent et preuves de manipulation

Assurez-vous que les actions sont attribuables et que les modifications sont détectables.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Vérifiez que chaque instance d'agent possède une identité cryptographique unique (paire de clés ou certificat ancré matériellement).        |   1   | D/V  |
| 9.5.2 | Vérifiez que toutes les actions des agents sont signées et horodatées ; les journaux incluent la signature pour assurer la non-répudiation. |   2   | D/V  |
| 9.5.3 | Vérifiez que les journaux à preuve de manipulation sont stockés dans un support accessible en écriture unique ou en mode ajout uniquement.  |   2   |  V   |
| 9.5.4 | Vérifiez que les clés d'identité sont renouvelées selon un calendrier défini et en cas d'indicateurs de compromission.                      |   3   |  D   |
| 9.5.5 | Vérifiez que les tentatives de falsification ou de conflit de clé déclenchent une mise en quarantaine immédiate de l'agent concerné.        |   3   | D/V  |

---

## 9.6 Réduction des risques par essaim multi-agent

Atténuer les risques liés au comportement collectif par l'isolation et la modélisation formelle de la sécurité.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Vérifiez que les agents opérant dans différents domaines de sécurité s’exécutent dans des environnements d’exécution isolés ou des segments réseau distincts. |   1   | D/V  |
| 9.6.2 | Vérifiez que les comportements en essaim sont modélisés et formellement vérifiés pour la vivacité et la sécurité avant le déploiement.                        |   3   |  V   |
| 9.6.3 | Vérifiez que les moniteurs d'exécution détectent les schémas dangereux émergents (par exemple, oscillations, impasses) et initient une action corrective.     |   3   |  D   |

---

## 9.7 Authentification / Autorisation des Utilisateurs et Outils

Mettez en place des contrôles d’accès robustes pour chaque action déclenchée par un agent.

|   #   | Description                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Vérifiez que les agents s'authentifient en tant que principaux de première classe auprès des systèmes en aval, sans jamais réutiliser les identifiants des utilisateurs finaux. |   1   | D/V  |
| 9.7.2 | Vérifiez que les politiques d'autorisation granulaires restreignent les outils qu'un agent peut invoquer ainsi que les paramètres qu'il peut fournir.                           |   2   |  D   |
| 9.7.3 | Vérifiez que les contrôles de privilèges sont réévalués à chaque appel (autorisation continue), et pas seulement au démarrage de la session.                                    |   2   |  V   |
| 9.7.4 | Vérifiez que les privilèges délégués expirent automatiquement et nécessitent un nouveau consentement après un délai d'expiration ou un changement de portée.                    |   3   |  D   |

---

## 9.8 Sécurité de la communication entre agents

Chiffrer et protéger l'intégrité de tous les messages interagents pour empêcher l'écoute clandestine et la falsification.

|   #   | Description                                                                                                                                                                 | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Vérifiez que l'authentification mutuelle et le chiffrement à secret parfait rétrograde (par exemple TLS 1.3) sont obligatoires pour les canaux des agents.                  |   1   | D/V  |
| 9.8.2 | Vérifiez que l'intégrité et l'origine du message sont validées avant le traitement ; les échecs déclenchent des alertes et entraînent la suppression du message.            |   1   |  D   |
| 9.8.3 | Vérifiez que les métadonnées de communication (horodatages, numéros de séquence) sont enregistrées pour supporter la reconstitution médico-légale.                          |   2   | D/V  |
| 9.8.4 | Vérifiez que la vérification formelle ou la vérification de modèle confirme que les machines à états du protocole ne peuvent pas être amenées dans des états non sécurisés. |   3   |  V   |

---

## 9.9 Vérification de l'Intention et Application des Contraintes

Valider que les actions de l'agent sont conformes à l'intention exprimée par l'utilisateur et aux contraintes du système.

|   #   | Description                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Vérifiez que les solveurs de contraintes pré-exécution vérifient les actions proposées par rapport aux règles strictes de sécurité et de politique codées en dur.                                                                              |   1   |  D   |
| 9.9.2 | Vérifiez que les actions à fort impact (financières, destructrices, sensibles à la vie privée) nécessitent une confirmation explicite de l’intention de la part de l’utilisateur initiateur.                                                   |   2   | D/V  |
| 9.9.3 | Vérifiez que les contrôles de post-condition valident que les actions terminées ont atteint les effets prévus sans effets secondaires ; les divergences déclenchent un retour en arrière.                                                      |   2   |  V   |
| 9.9.4 | Vérifiez que les méthodes formelles (par exemple, la vérification de modèles, la démonstration automatique de théorèmes) ou les tests basés sur les propriétés démontrent que les plans des agents satisfont toutes les contraintes déclarées. |   3   |  V   |
| 9.9.5 | Vérifiez que les incidents de non-concordance d'intention ou de violation de contraintes alimentent les cycles d'amélioration continue et le partage des renseignements sur les menaces.                                                       |   3   |  D   |

---

## 9.10 Stratégie de Raisonnement de l'Agent - Sécurité

Sélection et exécution sécurisées de différentes stratégies de raisonnement incluant les approches ReAct, Chain-of-Thought, et Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Vérifiez que la sélection de la stratégie de raisonnement utilise des critères déterministes (complexité de l'entrée, type de tâche, contexte de sécurité) et que des entrées identiques produisent des sélections de stratégie identiques dans le même contexte de sécurité. |   1   | D/V  |
| 9.10.2 | Vérifiez que chaque stratégie de raisonnement (ReAct, Chaîne de Pensée, Arbre des Pensées) dispose d'une validation d'entrée dédiée, d'une sanitation des sorties et de limites de temps d'exécution spécifiques à son approche cognitive.                                    |   1   | D/V  |
| 9.10.3 | Vérifiez que les transitions de stratégie de raisonnement sont enregistrées avec un contexte complet incluant les caractéristiques d'entrée, les valeurs des critères de sélection et les métadonnées d'exécution pour la reconstitution de la piste d'audit.                 |   2   | D/V  |
| 9.10.4 | Vérifiez que le raisonnement Tree-of-Thoughts inclut des mécanismes d'élagage des branches qui mettent fin à l'exploration lorsque des violations de politique, des limites de ressources ou des frontières de sécurité sont détectées.                                       |   2   | D/V  |
| 9.10.5 | Vérifiez que les cycles ReAct (Raisonnement-Action-Observation) incluent des points de contrôle de validation à chaque phase : vérification des étapes de raisonnement, autorisation des actions et assainissement des observations avant de poursuivre.                      |   2   | D/V  |
| 9.10.6 | Vérifiez que les métriques de performance de la stratégie de raisonnement (temps d'exécution, utilisation des ressources, qualité de sortie) sont surveillées avec des alertes automatisées lorsque les métriques dépassent les seuils configurés.                            |   3   | D/V  |
| 9.10.7 | Vérifiez que les approches de raisonnement hybrides combinant plusieurs stratégies respectent la validation des entrées et les contraintes de sortie de toutes les stratégies constituantes sans contourner aucun contrôle de sécurité.                                       |   3   | D/V  |
| 9.10.8 | Vérifiez que le test de sécurité de la stratégie de raisonnement inclut le fuzzing avec des entrées malformées, des invites adversariales conçues pour forcer le changement de stratégie, et des tests de conditions aux limites pour chaque approche cognitive.              |   3   | D/V  |

---

## 9.11 Gestion de l'État du Cycle de Vie des Agents et Sécurité

Initialisation sécurisée de l'agent, transitions d'état et terminaison avec des pistes d'audit cryptographiques et des procédures de récupération définies.

|   #    | Description                                                                                                                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Vérifiez que l'initialisation de l'agent inclut l'établissement d'une identité cryptographique avec des informations d'identification sécurisées par matériel ainsi que des journaux d'audit de démarrage immuables contenant l'ID de l'agent, le timestamp, le hachage de configuration et les paramètres d'initialisation. |   1   | D/V  |
| 9.11.2 | Vérifiez que les transitions d’état des agents sont signées cryptographiquement, horodatées et enregistrées avec un contexte complet incluant les événements déclencheurs, le hachage de l’état précédent, le hachage du nouvel état et les validations de sécurité effectuées.                                              |   2   | D/V  |
| 9.11.3 | Vérifiez que les procédures d'arrêt des agents incluent l'effacement sécurisé de la mémoire à l'aide d'une suppression cryptographique ou d'une réécriture multiple, la révocation des identifiants avec notification à l'autorité de certification, ainsi que la génération de certificats de terminaison inviolables.      |   2   | D/V  |
| 9.11.4 | Vérifiez que les mécanismes de récupération des agents valident l'intégrité de l'état en utilisant des sommes de contrôle cryptographiques (minimum SHA-256) et effectuent un retour aux états connus comme sains lorsqu'une corruption est détectée, avec des alertes automatisées et des exigences d'approbation manuelle. |   3   | D/V  |
| 9.11.5 | Vérifiez que les mécanismes de persistance des agents chiffrent les données d'état sensibles avec des clés AES-256 distinctes par agent et mettent en œuvre une rotation sécurisée des clés selon des calendriers configurables (maximum 90 jours) avec un déploiement sans interruption.                                    |   3   | D/V  |

---

## 9.12 Cadre de sécurité pour l'intégration des outils

Contrôles de sécurité pour le chargement dynamique des outils, leur exécution et la validation des résultats avec des processus définis d'évaluation des risques et d'approbation.

|   #    | Description                                                                                                                                                                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Vérifiez que les descripteurs d'outils incluent des métadonnées de sécurité spécifiant les privilèges requis (lecture/écriture/exécution), les niveaux de risque (faible/moyen/élevé), les limites de ressources (CPU, mémoire, réseau) et les exigences de validation documentées dans les manifests des outils.             |   1   | D/V  |
| 9.12.2 | Vérifiez que les résultats d'exécution des outils sont validés conformément aux schémas attendus (schéma JSON, schéma XML) et aux politiques de sécurité (assainissement des sorties, classification des données) avant l'intégration, en respectant les limites de délai d'attente et les procédures de gestion des erreurs. |   1   | D/V  |
| 9.12.3 | Vérifiez que les journaux d'interaction des outils incluent un contexte de sécurité détaillé comprenant l'utilisation des privilèges, les modèles d'accès aux données, le temps d'exécution, la consommation des ressources et les codes de retour, avec une journalisation structurée pour l'intégration SIEM.               |   2   | D/V  |
| 9.12.4 | Vérifiez que les mécanismes de chargement dynamique des outils valident les signatures numériques en utilisant l'infrastructure PKI et mettent en œuvre des protocoles de chargement sécurisés avec isolation par sandbox et vérification des permissions avant l'exécution.                                                  |   2   | D/V  |
| 9.12.5 | Vérifiez que les évaluations de sécurité des outils sont automatiquement déclenchées pour les nouvelles versions avec des étapes d'approbation obligatoires incluant l'analyse statique, les tests dynamiques et la revue par l'équipe de sécurité, avec des critères d'approbation documentés et des exigences de SLA.       |   3   | D/V  |

---

### Références

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

