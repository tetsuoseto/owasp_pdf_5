# Gestion du cycle de vie du modèle C3 et contrôle des modifications

## Objectif de contrôle

Les systèmes d'IA doivent mettre en œuvre des processus de contrôle des modifications qui empêchent les modifications non autorisées ou dangereuses du modèle d'atteindre la production. Ce contrôle garantit l'intégrité du modèle tout au long de son cycle de vie — du développement à la mise en production jusqu'à la mise hors service — ce qui permet une réponse rapide aux incidents et maintient la responsabilité de toutes les modifications.

Objectif principal de sécurité : Seuls les modèles autorisés et validés atteignent la production en utilisant des processus contrôlés qui garantissent l'intégrité, la traçabilité et la récupérabilité.

---

## C3.1 Autorisation et intégrité du modèle

Seuls les modèles autorisés avec une intégrité vérifiée atteignent les environnements de production.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Vérifiez que tous les artefacts du modèle (poids, configurations, tokenizeurs) sont signés cryptographiquement par des entités autorisées avant le déploiement.                                                                                               |   1   | D/V  |
| 3.1.2 | Vérifiez que l'intégrité du modèle est validée au moment du déploiement et que les échecs de vérification de la signature empêchent le chargement du modèle.                                                                                                  |   1   | D/V  |
| 3.1.3 | Vérifiez que les enregistrements de provenance du modèle incluent l'identité de l'entité autorisante, les sommes de contrôle des données d'entraînement, les résultats des tests de validation avec statut réussi/échoué, ainsi qu'un horodatage de création. |   2   | D/V  |
| 3.1.4 | Vérifiez que tous les artefacts du modèle utilisent la version sémantique (MAJOR.MINOR.PATCH) avec des critères documentés spécifiant quand chaque composant de la version doit être incrémenté.                                                              |   2   | D/V  |
| 3.1.5 | Vérifiez que le suivi des dépendances maintient un inventaire en temps réel permettant une identification rapide de tous les systèmes consommateurs.                                                                                                          |   2   |  V   |

---

## C3.2 Validation et test du modèle

Les modèles doivent passer des validations de sécurité et de sûreté définies avant le déploiement.

|   #   | Description                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Vérifiez que les modèles subissent des tests de sécurité automatisés comprenant la validation des entrées, la sanitation des sorties et des évaluations de sécurité avec des seuils de réussite/échec organisationnels préalablement convenus avant le déploiement. |   1   | D/V  |
| 3.2.2 | Vérifiez que les échecs de validation bloquent automatiquement le déploiement du modèle après une approbation explicite de dérogation par du personnel autorisé pré-désigné, avec des justifications commerciales documentées.                                      |   1   | D/V  |
| 3.2.3 | Vérifiez que les résultats des tests sont signés cryptographiquement et liés de manière immuable au hachage de la version spécifique du modèle en cours de validation.                                                                                              |   2   |  V   |
| 3.2.4 | Vérifiez que les déploiements d'urgence nécessitent une évaluation documentée des risques de sécurité et une approbation par une autorité de sécurité prédésignée dans des délais préalablement convenus.                                                           |   2   | D/V  |

---

## C3.3 Déploiement contrôlé et retour arrière

Les déploiements de modèles doivent être contrôlés, surveillés et réversibles.

|   #   | Description                                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.3.1 | Vérifiez que les déploiements en production mettent en œuvre des mécanismes de déploiement progressif (déploiements canari, déploiements bleu-vert) avec des déclencheurs de retour arrière automatisés basés sur des taux d'erreur, des seuils de latence ou des critères d'alerte de sécurité préalablement convenus. |   1   |  D   |
| 3.3.2 | Vérifiez que les capacités de retour en arrière restaurent l'état complet du modèle (poids, configurations, dépendances) de manière atomique dans des fenêtres temporelles organisationnelles prédéfinies.                                                                                                              |   1   | D/V  |
| 3.3.3 | Vérifier que les processus de déploiement valident les signatures cryptographiques et calculent les sommes de contrôle d'intégrité avant l'activation du modèle, en échouant le déploiement en cas de toute discordance.                                                                                                |   2   | D/V  |
| 3.3.4 | Vérifier que les capacités d'arrêt d'urgence du modèle peuvent désactiver les points de terminaison du modèle dans des délais de réponse pré-définis via des disjoncteurs automatiques ou des interrupteurs d'arrêt manuels.                                                                                            |   2   | D/V  |
| 3.3.5 | Vérifiez que les artefacts de restauration (versions précédentes du modèle, configurations, dépendances) sont conservés conformément aux politiques organisationnelles avec un stockage immuable pour la réponse aux incidents.                                                                                         |   2   |  V   |

---

## C3.4 Responsabilité des changements et audit

Toutes les modifications du cycle de vie du modèle doivent être traçables et auditées.

|   #   | Description                                                                                                                                                                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Vérifiez que toutes les modifications du modèle (déploiement, configuration, retrait) génèrent des enregistrements d'audit immuables comprenant un horodatage, une identité d'acteur authentifiée, un type de modification et les états avant/après.                                  |   1   |  V   |
| 3.4.2 | Vérifiez que l'accès au journal d'audit nécessite une autorisation appropriée et que toutes les tentatives d'accès sont enregistrées avec l'identité de l'utilisateur et un horodatage.                                                                                               |   2   | D/V  |
| 3.4.3 | Vérifiez que les modèles de requêtes (prompt templates) et les messages système sont soumis au contrôle de version dans des dépôts git avec une revue de code obligatoire et une approbation par des réviseurs désignés avant le déploiement.                                         |   2   | D/V  |
| 3.4.4 | Vérifiez que les enregistrements d'audit contiennent suffisamment de détails (empreintes des modèles, instantanés de configuration, versions des dépendances) pour permettre une reconstruction complète de l'état du modèle à n'importe quel moment pendant la période de rétention. |   2   |  V   |

---

## C3.5 Pratiques de Développement Sécurisé

Les processus de développement et de formation des modèles doivent suivre des pratiques sécurisées pour éviter toute compromission.

|   #   | Description                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Vérifiez que les environnements de développement, de test et de production du modèle sont séparés physiquement ou logiquement. Ils ne partagent aucune infrastructure, disposent de contrôles d'accès distincts et de magasins de données isolés.                                |   1   |  D   |
| 3.5.2 | Vérifiez que la formation et le réglage fin du modèle ont lieu dans des environnements isolés avec un accès réseau contrôlé.                                                                                                                                                     |   1   |  D   |
| 3.5.3 | Vérifiez que les sources de données d'entraînement sont validées par des contrôles d'intégrité et authentifiées via des sources fiables avec une chaîne de conservation documentée avant leur utilisation dans le développement du modèle.                                       |   1   | D/V  |
| 3.5.4 | Vérifiez que les artefacts de développement de modèle (hyperparamètres, scripts d'entraînement, fichiers de configuration) sont stockés dans un système de gestion de versions et nécessitent une approbation par revue par les pairs avant d'être utilisés pour l'entraînement. |   2   |  D   |

---

## C3.6 Retrait et mise hors service du modèle

Les modèles doivent être retirés de manière sécurisée lorsqu'ils ne sont plus nécessaires ou lorsqu'on identifie des problèmes de sécurité.

|   #   | Description                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.6.1 | Vérifiez que les processus de retrait des modèles analysent automatiquement les graphes de dépendance, identifient tous les systèmes consommateurs et fournissent des délais de préavis convenus à l'avance avant la mise hors service.                                  |   1   |  D   |
| 3.6.2 | Vérifiez que les artefacts des modèles retirés sont effacés de manière sécurisée en utilisant l'effacement cryptographique ou le réécriture multi-passes conformément aux politiques documentées de rétention des données, avec des certificats de destruction vérifiés. |   1   | D/V  |
| 3.6.3 | Vérifiez que les événements de mise hors service du modèle sont enregistrés avec un horodatage et l'identité de l'acteur, et que les signatures du modèle sont révoquées pour empêcher toute réutilisation.                                                              |   2   |  V   |
| 3.6.4 | Vérifiez que la mise hors service d'urgence du modèle peut désactiver l'accès au modèle dans les délais de réponse d'urgence préétablis grâce à des interrupteurs automatiques en cas de découverte de vulnérabilités critiques de sécurité.                             |   2   | D/V  |

---

## Références

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)

