# Sécurité de la mémoire C8, des embeddings et des bases de données vectorielles

## Objectif de contrôle

Les embeddings et les bases de données vectorielles agissent comme la « mémoire vivante » des systèmes d'IA contemporains, acceptant continuellement les données fournies par les utilisateurs et les réintégrant dans les contextes des modèles via la génération augmentée par récupération (RAG). Si cette mémoire n'est pas contrôlée, elle peut divulguer des informations personnelles identifiables (PII), violer le consentement ou être inversée pour reconstruire le texte original. L'objectif de cette famille de contrôles est de renforcer les pipelines de mémoire et les bases de données vectorielles afin que l'accès soit assuré selon le principe du moindre privilège, que les embeddings respectent la confidentialité, que les vecteurs stockés expirent ou puissent être révoqués à la demande, et que la mémoire par utilisateur ne contamine jamais les invites ou complétions d'un autre utilisateur.

---

## C8.1 Contrôles d'accès sur la mémoire et les indices RAG

Appliquer des contrôles d'accès granulaires sur chaque collection vectorielle.

|   #   | Description                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Vérifiez que les règles de contrôle d'accès au niveau des lignes ou des espaces de noms limitent les opérations d'insertion, de suppression et de requête par locataire, collection ou étiquette de document. |   1   | D/V  |
| 8.1.2 | Vérifiez que les clés API ou les JWT comportent des revendications limitées (par exemple, des identifiants de collection, des verbes d'action) et qu'ils sont renouvelés au moins tous les trimestres.        |   1   | D/V  |
| 8.1.3 | Vérifiez que les tentatives d'élévation de privilèges (par exemple, les requêtes de similarité inter-espaces de noms) sont détectées et enregistrées dans un SIEM dans un délai de 5 minutes.                 |   2   | D/V  |
| 8.1.4 | Vérifiez que la base de données vectorielle consigne l'identifiant du sujet de l'audit, l'opération, l'ID/namespaces du vecteur, le seuil de similarité, et le compte des résultats.                          |   2   | D/V  |
| 8.1.5 | Vérifiez que les décisions d'accès sont testées pour des failles de contournement chaque fois que les moteurs sont mis à jour ou que les règles de répartition des index changent.                            |   3   |  V   |

---

## C8.2 Assainissement et Validation des Incrustations

Pré-évaluer le texte pour les informations personnelles identifiables (IPI), les supprimer ou les pseudonymiser avant la vectorisation, et éventuellement post-traiter les embeddings pour éliminer les signaux résiduels.

|   #   | Description                                                                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Vérifiez que les informations personnelles identifiables (IPI) et les données réglementées sont détectées par des classificateurs automatisés et masquées, tokenisées ou supprimées avant l’intégration.                  |   1   | D/V  |
| 8.2.2 | Vérifiez que les pipelines d'intégration rejettent ou mettent en quarantaine les entrées contenant du code exécutable ou des artefacts non UTF-8 qui pourraient contaminer l'index.                                       |   1   |  D   |
| 8.2.3 | Vérifiez que la désanonymisation différentielle locale ou métrique est appliquée aux embeddings de phrases dont la distance à tout jeton PII connu est inférieure à un seuil configurable.                                |   2   | D/V  |
| 8.2.4 | Vérifiez que l'efficacité de la sanitation (par exemple, le rappel de la suppression des données personnelles identifiables, la dérive sémantique) est validée au moins semestriellement à l'aide de corpus de référence. |   2   |  V   |
| 8.2.5 | Vérifiez que les configurations de désinfection sont sous contrôle de version et que les modifications font l'objet d'une revue par les pairs.                                                                            |   3   | D/V  |

---

## C8.3 Expiration, révocation et suppression de la mémoire

Le « droit à l'oubli » du RGPD et des lois similaires exigent une effacement rapide ; les magasins de vecteurs doivent donc prendre en charge les durées de vie (TTL), les suppressions définitives et les marquages de suppression (tomb-stoning) afin que les vecteurs révoqués ne puissent pas être récupérés ou réindexés.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Vérifiez que chaque vecteur et enregistrement de métadonnées porte un TTL ou une étiquette de conservation explicite respectée par les tâches de nettoyage automatisées.                            |   1   | D/V  |
| 8.3.2 | Vérifiez que les demandes de suppression initiées par l'utilisateur purgent les vecteurs, les métadonnées, les copies en cache et les indices dérivés dans un délai de 30 jours.                    |   1   | D/V  |
| 8.3.3 | Vérifiez que les suppressions logiques sont suivies d'un effacement cryptographique des blocs de stockage si le matériel le prend en charge, ou d'une destruction de la clé du coffre-fort de clés. |   2   |  D   |
| 8.3.4 | Vérifiez que les vecteurs expirés sont exclus des résultats de recherche des plus proches voisins en moins de 500 ms après leur expiration.                                                         |   3   | D/V  |

---

## C8.4 Prévenir l'inversion et la fuite d'incorporation

Les défenses récentes—superposition de bruit, réseaux de projection, perturbation de neurones de confidentialité, et chiffrement au niveau de la couche application—peuvent réduire les taux d'inversion au niveau des tokens en dessous de 5 %.

|   #   | Description                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Vérifiez qu'un modèle de menace formel couvrant les attaques par inversion, les attaques d'appartenance et les attaques par inférence d'attribut existe et est révisé chaque année.                 |   1   |  V   |
| 8.4.2 | Vérifiez que le chiffrement au niveau applicatif ou le chiffrement consultable protège les vecteurs contre les lectures directes par les administrateurs d'infrastructure ou le personnel du cloud. |   2   | D/V  |
| 8.4.3 | Vérifiez que les paramètres de défense (ε pour DP, bruit σ, rang de projection k) équilibrent une confidentialité ≥ 99 % de protection des tokens et une utilité ≤ 3 % de perte de précision.       |   3   |  V   |
| 8.4.4 | Vérifiez que les métriques de résilience à l'inversion font partie des critères de validation pour les mises à jour des modèles, avec des budgets de régression définis.                            |   3   | D/V  |

---

## C8.5 Application rigoureuse des restrictions pour la mémoire spécifique à l’utilisateur

La fuite entre locataires reste un risque majeur de RAG : des requêtes de similarité mal filtrées peuvent révéler les documents privés d'un autre client.

|   #   | Description                                                                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Vérifiez que chaque requête de récupération est filtrée a posteriori par l'identifiant du locataire/utilisateur avant d'être transmise à l'invite du LLM.                                               |   1   | D/V  |
| 8.5.2 | Vérifiez que les noms de collections ou les ID avec espaces de noms sont salés par utilisateur ou par locataire afin que les vecteurs ne puissent pas entrer en collision entre les différents espaces. |   1   |  D   |
| 8.5.3 | Vérifiez que les résultats de similarité supérieurs à un seuil de distance configurable mais en dehors du périmètre de l'appelant sont rejetés et déclenchent des alertes de sécurité.                  |   2   | D/V  |
| 8.5.4 | Vérifiez que les tests de résistance multi-locataires simulent des requêtes adversariales tentant d'extraire des documents hors de leur périmètre et démontrent une absence totale de fuite.            |   2   |  V   |
| 8.5.5 | Vérifiez que les clés de chiffrement sont séparées par locataire, garantissant une isolation cryptographique même si le stockage physique est partagé.                                                  |   3   | D/V  |

---

## C8.6 Sécurité avancée des systèmes de mémoire

Contrôles de sécurité pour des architectures mémoire sophistiquées incluant la mémoire épisodique, sémantique et de travail avec des exigences spécifiques d'isolation et de validation.

|   #   | Description                                                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Vérifiez que les différents types de mémoire (épisodique, sémantique, de travail) disposent de contextes de sécurité isolés avec des contrôles d'accès basés sur les rôles, des clés de chiffrement séparées et des modèles d'accès documentés pour chaque type de mémoire.                                             |   1   | D/V  |
| 8.6.2 | Vérifiez que les processus de consolidation de la mémoire incluent une validation de sécurité pour empêcher l'injection de souvenirs malveillants par la sanitation du contenu, la vérification de la source et les contrôles d'intégrité avant le stockage.                                                            |   2   | D/V  |
| 8.6.3 | Vérifiez que les requêtes de récupération de mémoire sont validées et assainies afin d'empêcher l'extraction d'informations non autorisées par l'analyse des modèles de requête, l'application du contrôle d'accès et le filtrage des résultats.                                                                        |   2   | D/V  |
| 8.6.4 | Vérifiez que les mécanismes de suppression de la mémoire suppriment de manière sécurisée les informations sensibles avec des garanties d'effacement cryptographique en utilisant la suppression de clés, la réécriture multiple ou la suppression sécurisée basée sur le matériel avec des certificats de vérification. |   3   | D/V  |
| 8.6.5 | Vérifiez que l’intégrité du système mémoire est continuellement surveillée pour détecter des modifications non autorisées ou des corruptions grâce à des sommes de contrôle, des journaux d’audit et des alertes automatiques lorsque le contenu de la mémoire change en dehors des opérations normales.                |   3   | D/V  |

---

## Références

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

