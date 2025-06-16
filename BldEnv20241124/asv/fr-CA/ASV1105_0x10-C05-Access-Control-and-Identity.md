# Contrôle d'accès C5 et identité pour les composants et utilisateurs d'IA

## Objectif de contrôle

Un contrôle d'accès efficace pour les systèmes d'IA nécessite une gestion robuste des identités, une autorisation contextuelle et une application en temps réel conforme aux principes du zéro confiance. Ces contrôles garantissent que les humains, services et agents autonomes n’interagissent avec les modèles, les données et les ressources informatiques que dans les périmètres explicitement autorisés, avec des capacités continues de vérification et d'audit.

---

## C5.1 Gestion de l'identité et authentification

Établir des identités sécurisées cryptographiquement pour toutes les entités avec une authentification multi-facteurs pour les opérations privilégiées.

|   #   | Description                                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Vérifiez que tous les utilisateurs humains et les principaux de service s’authentifient via un fournisseur d’identité d’entreprise centralisé (IdP) en utilisant les protocoles OIDC/SAML avec des correspondances uniques entre l’identité et le jeton (aucun compte ou identifiant partagé). |   1   | D/V  |
| 5.1.2 | Vérifiez que les opérations à haut risque (déploiement de modèle, exportation de poids, accès aux données d'entraînement, modifications de la configuration en production) nécessitent une authentification multi-facteurs ou une authentification renforcée avec une revalidation de session. |   1   | D/V  |
| 5.1.3 | Vérifiez que les nouveaux responsables subissent une vérification d'identité conforme à la norme NIST 800-63-3 IAL-2 ou à des normes équivalentes avant d'obtenir l'accès au système de production.                                                                                            |   2   |  D   |
| 5.1.4 | Vérifiez que les examens d'accès sont effectués trimestriellement avec une détection automatisée des comptes inactifs, une application de la rotation des identifiants et des flux de travail de désapprovisionnement.                                                                         |   2   |  V   |
| 5.1.5 | Vérifiez que les agents d’IA fédérés s’authentifient via des assertions JWT signées ayant une durée de vie maximale de 24 heures et incluant une preuve cryptographique d’origine.                                                                                                             |   3   | D/V  |

---

## C5.2 Autorisation des ressources et principe du moindre privilège

Implémenter des contrôles d'accès granulaires pour toutes les ressources IA avec des modèles d'autorisation explicites et des pistes d'audit.

|   #   | Description                                                                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Vérifiez que chaque ressource d'IA (ensembles de données, modèles, points de terminaison, collections vectorielles, indices d'intégration, instances de calcul) applique des contrôles d'accès basés sur les rôles avec des listes d'autorisation explicites et des politiques de refus par défaut. |   1   | D/V  |
| 5.2.2 | Vérifiez que les principes de moindre privilège sont appliqués par défaut avec les comptes de service, en commençant par des permissions en lecture seule et en exigeant une justification commerciale documentée pour les accès en écriture.                                                       |   1   | D/V  |
| 5.2.3 | Vérifiez que toutes les modifications du contrôle d'accès sont liées à des demandes de changement approuvées et enregistrées de manière immuable avec des horodatages, les identités des acteurs, les identifiants des ressources et les variations de permissions.                                 |   1   |  V   |
| 5.2.4 | Vérifiez que les étiquettes de classification des données (PII, PHI, sous contrôle à l'exportation, propriétaire) se propagent automatiquement aux ressources dérivées (représentations vectorielles, caches de requêtes, résultats de modèles) avec une application cohérente des politiques.      |   2   |  D   |
| 5.2.5 | Vérifiez que les tentatives d'accès non autorisées et les événements d'élévation de privilèges déclenchent des alertes en temps réel avec des métadonnées contextuelles vers les systèmes SIEM dans un délai de 5 minutes.                                                                          |   2   | D/V  |

---

## C5.3 Évaluation Dynamique de la Politique

Déployez des moteurs de contrôle d'accès basé sur les attributs (ABAC) pour des décisions d'autorisation contextuelles avec des capacités d'audit.

|   #   | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Vérifiez que les décisions d'autorisation sont externalisées vers un moteur de politique dédié (OPA, Cedar ou équivalent) accessible via des API authentifiées avec une protection de l'intégrité cryptographique.                                                                      |   1   | D/V  |
| 5.3.2 | Vérifiez que les politiques évaluent les attributs dynamiques au moment de l'exécution, y compris le niveau de habilitation de l'utilisateur, la classification de la sensibilité des ressources, le contexte de la demande, l'isolation des locataires et les contraintes temporelles. |   1   | D/V  |
| 5.3.3 | Vérifiez que les définitions de politique sont sous contrôle de version, évaluées par des pairs et validées par des tests automatisés dans les pipelines CI/CD avant le déploiement en production.                                                                                      |   2   |  D   |
| 5.3.4 | Vérifiez que les résultats de l'évaluation des politiques incluent des motifs de décision structurés et sont transmis aux systèmes SIEM pour l'analyse de corrélation et la production de rapports de conformité.                                                                       |   2   |  V   |
| 5.3.5 | Vérifiez que les valeurs de temps de vie (TTL) du cache de politique ne dépassent pas 5 minutes pour les ressources à haute sensibilité et 1 heure pour les ressources standard avec des capacités d'invalidation du cache.                                                             |   3   | D/V  |

---

## C5.4 Application de la sécurité au moment de la requête

Mettre en œuvre des contrôles de sécurité au niveau de la base de données avec filtrage obligatoire et des politiques de sécurité au niveau des lignes.

|   #   | Description                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Vérifiez que toutes les requêtes des bases de données vectorielles et SQL incluent les filtres de sécurité obligatoires (ID de locataire, étiquettes de sensibilité, périmètre utilisateur) appliqués au niveau du moteur de base de données, et non dans le code applicatif. |   1   | D/V  |
| 5.4.2 | Vérifiez que les politiques de sécurité au niveau des lignes (RLS) et le masquage au niveau des champs sont activés avec l'héritage des politiques pour toutes les bases de données vectorielles, les indices de recherche et les ensembles de données d'entraînement.        |   1   | D/V  |
| 5.4.3 | Vérifiez que les évaluations d'autorisation échouées empêchent les « attaques du dépositaire confus » en interrompant immédiatement les requêtes et en renvoyant des codes d'erreur d'autorisation explicites plutôt que de retourner des ensembles de résultats vides.       |   2   |  D   |
| 5.4.4 | Vérifiez que la latence d'évaluation de la politique est constamment surveillée avec des alertes automatisées en cas de conditions de dépassement de délai pouvant permettre un contournement de l'autorisation.                                                              |   2   |  V   |
| 5.4.5 | Vérifiez que les mécanismes de nouvelle tentative des requêtes réévaluent les politiques d'autorisation afin de tenir compte des modifications dynamiques des permissions au sein des sessions utilisateur actives.                                                           |   3   | D/V  |

---

## Filtrage de sortie C5.5 et prévention de la perte de données

Déployer des contrôles de post-traitement pour empêcher l'exposition non autorisée des données dans le contenu généré par l'IA.

|   #   | Description                                                                                                                                                                                                                                         | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Vérifiez que les mécanismes de filtrage post-inférence analysent et rédigent les informations personnelles identifiables (IPI), les informations classifiées et les données propriétaires non autorisées avant de livrer le contenu aux demandeurs. |   1   | D/V  |
| 5.5.2 | Vérifiez que les citations, références et attributions de sources dans les résultats du modèle sont validées en fonction des droits du demandeur et supprimées en cas de détection d'un accès non autorisé.                                         |   1   | D/V  |
| 5.5.3 | Vérifiez que les restrictions sur le format de sortie (PDFs purgés, images sans métadonnées, types de fichiers approuvés) sont appliquées en fonction des niveaux d'autorisation des utilisateurs et des classifications des données.               |   2   |  D   |
| 5.5.4 | Vérifiez que les algorithmes de masquage sont déterministes, contrôlés par version, et maintiennent des journaux d'audit pour soutenir les enquêtes de conformité et l'analyse médico-légale.                                                       |   2   |  V   |
| 5.5.5 | Vérifiez que les événements de rédaction à haut risque génèrent des journaux adaptatifs incluant des hachages cryptographiques du contenu original pour une récupération judiciaire sans exposition des données.                                    |   3   |  V   |

---

## C5.6 Isolation Multi-Locataire

Assurer l'isolation cryptographique et logique entre les locataires dans une infrastructure d'IA partagée.

|   #   | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Vérifiez que les espaces mémoire, les magasins d’intégration, les entrées de cache et les fichiers temporaires sont séparés par espace de noms pour chaque locataire, avec une suppression sécurisée lors de la suppression du locataire ou de la terminaison de la session. |   1   | D/V  |
| 5.6.2 | Vérifiez que chaque requête API inclut un identifiant de locataire authentifié, validé cryptographiquement par rapport au contexte de session et aux droits de l'utilisateur.                                                                                                |   1   | D/V  |
| 5.6.3 | Vérifiez que les politiques réseau appliquent des règles de refus par défaut pour la communication inter-locataires au sein des maillages de services et des plateformes d'orchestration de conteneurs.                                                                      |   2   |  D   |
| 5.6.4 | Vérifier que les clés de chiffrement sont uniques par locataire avec prise en charge des clés gérées par le client (CMK) et une isolation cryptographique entre les magasins de données des locataires.                                                                      |   3   |  D   |

---

## C5.7 Autorisation de l'Agent Autonome

Contrôlez les autorisations des agents d'IA et des systèmes autonomes grâce à des jetons de capacité à portée définie et une autorisation continue.

|   #   | Description                                                                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 5.7.1 | Vérifiez que les agents autonomes reçoivent des jetons de capacité limités qui énumèrent explicitement les actions autorisées, les ressources accessibles, les limites temporelles et les contraintes opérationnelles.                                                               |   1   | D/V  |
| 5.7.2 | Vérifiez que les capacités à haut risque (accès au système de fichiers, exécution de code, appels API externes, transactions financières) sont désactivées par défaut et nécessitent des autorisations explicites pour leur activation, accompagnées de justifications commerciales. |   1   | D/V  |
| 5.7.3 | Vérifiez que les jetons de capacité sont liés aux sessions utilisateur, incluent une protection cryptographique d'intégrité, et assurez-vous qu'ils ne peuvent pas être conservés ou réutilisés dans des scénarios hors ligne.                                                       |   2   |  D   |
| 5.7.4 | Vérifiez que les actions initiées par l'agent font l'objet d'une autorisation secondaire via le moteur de politique ABAC avec une évaluation complète du contexte et une journalisation des audits.                                                                                  |   2   |  V   |
| 5.7.5 | Vérifiez que les conditions d'erreur de l'agent et la gestion des exceptions incluent des informations sur la portée des capacités pour soutenir l'analyse des incidents et l'enquête médico-légale.                                                                                 |   3   |  V   |

---

## Références

### Normes et cadres

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Guides de mise en œuvre

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Sécurité spécifique à l'IA

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

