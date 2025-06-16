# Infrastructure C4, Sécurité de la Configuration et du Déploiement

## Objectif de contrôle

L'infrastructure d'IA doit être renforcée contre l'escalade de privilèges, la falsification de la chaîne d'approvisionnement et les mouvements latéraux grâce à une configuration sécurisée, une isolation à l'exécution, des pipelines de déploiement fiables et une surveillance complète. Seuls les composants et configurations d'infrastructure autorisés et validés atteignent la production via des processus contrôlés qui préservent la sécurité, l'intégrité et l'auditabilité.

Objectif principal de la sécurité : Seuls les composants d'infrastructure signés cryptographiquement et analysés pour les vulnérabilités atteignent la production via des pipelines de validation automatisés qui appliquent les politiques de sécurité et maintiennent des pistes d'audit immuables.

---

## C4.1 Isolation de l'environnement d'exécution

Empêchez les échappements de conteneurs et l'escalade de privilèges grâce aux primitives d'isolation au niveau du noyau et aux contrôles d'accès obligatoires.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Vérifiez que tous les conteneurs d'IA abandonnent TOUTES les capacités Linux sauf CAP_SETUID, CAP_SETGID, et les capacités explicitement requises documentées dans les bases de sécurité.                                                                     |   1   | D/V  |
| 4.1.2 | Vérifiez que les profils seccomp bloquent tous les appels système sauf ceux figurant dans les listes blanches pré-approuvées, les violations entraînant la terminaison du conteneur et la génération d'alertes de sécurité.                                   |   1   | D/V  |
| 4.1.3 | Vérifiez que les charges de travail d'IA fonctionnent avec des systèmes de fichiers racine en lecture seule, tmpfs pour les données temporaires, et des volumes nommés pour les données persistantes avec les options de montage noexec appliquées.           |   2   | D/V  |
| 4.1.4 | Vérifiez que la surveillance en temps réel basée sur eBPF (Falco, Tetragon ou équivalent) détecte les tentatives d'escalade de privilèges et termine automatiquement les processus fautifs conformément aux exigences de temps de réponse organisationnelles. |   2   | D/V  |
| 4.1.5 | Vérifiez que les charges de travail d'IA à haut risque s'exécutent dans des environnements isolés matériellement (Intel TXT, AMD SVM, ou nœuds bare-metal dédiés) avec une vérification d'attestation.                                                        |   3   | D/V  |

---

## C4.2 Pipelines sécurisés de construction et de déploiement

Assurez l'intégrité cryptographique et la sécurité de la chaîne d'approvisionnement grâce à des compilations reproductibles et des artefacts signés.

|   #   | Description                                                                                                                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Vérifiez que l'infrastructure en tant que code est analysée avec des outils (tfsec, Checkov ou Terrascan) à chaque commit, bloquant les fusions en cas de détections de sévérité CRITIQUE ou ÉLEVÉE.                                                 |   1   | D/V  |
| 4.2.2 | Vérifiez que les constructions de conteneurs sont reproductibles avec des hachages SHA256 identiques entre les constructions et générez des attestations de provenance SLSA Niveau 3 signées avec Sigstore.                                          |   1   | D/V  |
| 4.2.3 | Vérifiez que les images de conteneurs intègrent des SBOM CycloneDX ou SPDX et sont signées avec Cosign avant le push dans le registre, les images non signées étant rejetées lors du déploiement.                                                    |   2   | D/V  |
| 4.2.4 | Vérifiez que les pipelines CI/CD utilisent des jetons OIDC provenant de HashiCorp Vault, des rôles AWS IAM ou de l'identité gérée Azure avec des durées de vie ne dépassant pas les limites définies par la politique de sécurité organisationnelle. |   2   | D/V  |
| 4.2.5 | Vérifiez que les signatures Cosign et la provenance SLSA sont validées lors du processus de déploiement avant l'exécution du conteneur et que les erreurs de validation entraînent l'échec du déploiement.                                           |   2   | D/V  |
| 4.2.6 | Vérifiez que les environnements de compilation fonctionnent dans des conteneurs éphémères ou des machines virtuelles sans stockage persistant et avec une isolation réseau par rapport aux VPC de production.                                        |   2   | D/V  |

---

## C4.3 Sécurité Réseau et Contrôle d'Accès

Mettez en œuvre un réseau à confiance zéro avec des politiques de refus par défaut et des communications chiffrées.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Vérifiez que les NetworkPolicies Kubernetes ou tout équivalent implémentent un refus par défaut des flux entrants/sortants avec des règles d'autorisation explicites pour les ports requis (443, 8080, etc.).                                |   1   | D/V  |
| 4.3.2 | Vérifiez que SSH (port 22), RDP (port 3389) et les points de terminaison des métadonnées cloud (169.254.169.254) sont bloqués ou nécessitent une authentification basée sur un certificat.                                                   |   1   | D/V  |
| 4.3.3 | Vérifiez que le trafic de sortie est filtré via des proxies HTTP/HTTPS (Squid, Istio, ou passerelles NAT cloud) avec des listes blanches de domaines et que les requêtes bloquées sont enregistrées.                                         |   2   | D/V  |
| 4.3.4 | Vérifiez que la communication inter-services utilise le TLS mutuel avec des certificats renouvelés conformément à la politique organisationnelle et que la validation des certificats est appliquée (sans utiliser de drapeaux skip-verify). |   2   | D/V  |
| 4.3.5 | Vérifiez que l'infrastructure d'IA fonctionne dans des VPC/VNets dédiés sans accès direct à Internet et communique uniquement via des passerelles NAT ou des hôtes bastion.                                                                  |   2   | D/V  |

---

## C4.4 Gestion des Secrets et des Clés Cryptographiques

Protégez les informations d'identification grâce à un stockage sécurisé par matériel et une rotation automatisée avec un accès à confiance zéro.

|   #   | Description                                                                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Vérifiez que les secrets sont stockés dans HashiCorp Vault, AWS Secrets Manager, Azure Key Vault ou Google Secret Manager avec un chiffrement au repos utilisant AES-256.                                                                                           |   1   | D/V  |
| 4.4.2 | Vérifiez que les clés cryptographiques sont générées dans des HSM conformes à la norme FIPS 140-2 Niveau 2 (AWS CloudHSM, Azure Dedicated HSM) avec une rotation des clés selon la politique cryptographique organisationnelle.                                     |   1   | D/V  |
| 4.4.3 | Vérifiez que la rotation des secrets est automatisée avec un déploiement sans interruption et une rotation immédiate déclenchée par des changements de personnel ou des incidents de sécurité.                                                                      |   2   | D/V  |
| 4.4.4 | Vérifiez que les images de conteneurs sont analysées avec des outils (GitLeaks, TruffleHog ou detect-secrets) bloquant les constructions contenant des clés API, des mots de passe ou des certificats.                                                              |   2   | D/V  |
| 4.4.5 | Vérifiez que l'accès aux secrets de production nécessite une authentification multifacteur (MFA) avec des tokens matériels (YubiKey, FIDO2) et qu'il est enregistré par des journaux d'audit immuables contenant les identités des utilisateurs et les horodatages. |   2   | D/V  |
| 4.4.6 | Vérifiez que les secrets sont injectés via les secrets Kubernetes, les volumes montés ou les conteneurs init et assurez-vous que les secrets ne sont jamais intégrés dans les variables d'environnement ou les images.                                              |   2   | D/V  |

---

## C4.5 Sandbox et Validation des Charges de Travail en IA

Isolez les modèles d'IA non fiables dans des environnements sécurisés avec une analyse comportementale complète.

|   #   | Description                                                                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.5.1 | Vérifiez que les modèles d'IA externes s'exécutent dans gVisor, des microVM (tels que Firecracker, CrossVM) ou des conteneurs Docker avec les options --security-opt=no-new-privileges et --read-only.              |   1   | D/V  |
| 4.5.2 | Vérifiez que les environnements sandbox n'ont aucune connectivité réseau (--network=none) ou seulement un accès localhost avec toutes les requêtes externes bloquées par des règles iptables.                       |   1   | D/V  |
| 4.5.3 | Vérifiez que la validation du modèle d’IA inclut des tests automatisés de type red-team avec une couverture de test définie par l’organisation et une analyse comportementale pour la détection de portes dérobées. |   2   | D/V  |
| 4.5.4 | Vérifiez qu'avant qu'un modèle d'IA ne soit mis en production, les résultats de son sandbox sont signés cryptographiquement par le personnel de sécurité autorisé et stockés dans des journaux d'audit immuables.   |   2   | D/V  |
| 4.5.5 | Vérifiez que les environnements sandbox sont détruits et recréés à partir d'images maîtresses entre les évaluations, avec un nettoyage complet du système de fichiers et de la mémoire.                             |   2   | D/V  |

---

## C4.6 Surveillance de la sécurité de l'infrastructure

Scanner et surveiller en continu l'infrastructure avec une correction automatisée et des alertes en temps réel.

|   #   | Description                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Vérifier que les images des conteneurs sont analysées conformément aux calendriers organisationnels, avec les vulnérabilités CRITIQUES bloquant le déploiement en fonction des seuils de risque organisationnels.                 |   1   | D/V  |
| 4.6.2 | Vérifiez que l'infrastructure respecte les normes CIS Benchmarks ou les contrôles NIST 800-53 avec des seuils de conformité définis par l'organisation et une remédiation automatisée pour les vérifications échouées.            |   1   | D/V  |
| 4.6.3 | Vérifiez que les vulnérabilités de gravité ÉLEVÉE sont corrigées conformément aux délais de gestion des risques organisationnels, avec des procédures d'urgence pour les CVE activement exploitées.                               |   2   | D/V  |
| 4.6.4 | Vérifiez que les alertes de sécurité s'intègrent avec les plateformes SIEM (Splunk, Elastic ou Sentinel) en utilisant les formats CEF ou STIX/TAXII avec un enrichissement automatisé.                                            |   2   |  V   |
| 4.6.5 | Vérifiez que les métriques d'infrastructure sont exportées vers les systèmes de surveillance (Prometheus, DataDog) avec des tableaux de bord SLA et des rapports exécutifs.                                                       |   3   |  V   |
| 4.6.6 | Vérifiez que la dérive de configuration est détectée à l'aide d'outils (Chef InSpec, AWS Config) conformément aux exigences de surveillance organisationnelle, avec un retour automatique en cas de modifications non autorisées. |   2   | D/V  |

---

## Gestion des ressources d'infrastructure IA C4.7

Prévenir les attaques par épuisement des ressources et garantir une allocation équitable des ressources grâce à des quotas et une surveillance.

|   #   | Description                                                                                                                                                                                                                                                 | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Vérifiez que l'utilisation des GPU/TPU est surveillée avec des alertes déclenchées aux seuils définis par l'organisation et que la mise à l'échelle automatique ou l'équilibrage de charge est activé en fonction des politiques de gestion de la capacité. |   1   | D/V  |
| 4.7.2 | Vérifiez que les métriques de charge de travail de l'IA (latence d'inférence, débit, taux d'erreur) sont collectées conformément aux exigences de surveillance organisationnelles et corrélées à l'utilisation de l'infrastructure.                         |   1   | D/V  |
| 4.7.3 | Vérifiez que les ResourceQuotas de Kubernetes ou leur équivalent limitent les charges de travail individuelles conformément aux politiques d'allocation des ressources de l'organisation, avec des limites strictes appliquées.                             |   2   | D/V  |
| 4.7.4 | Vérifiez que la surveillance des coûts suit les dépenses par charge de travail/locataire avec des alertes basées sur les seuils budgétaires organisationnels et des contrôles automatisés pour les dépassements de budget.                                  |   2   |  V   |
| 4.7.5 | Vérifiez que la planification de la capacité utilise des données historiques avec des périodes de prévision définies par l'organisation et un approvisionnement automatisé des ressources basé sur les modèles de demande.                                  |   3   |  V   |
| 4.7.6 | Vérifiez que l'épuisement des ressources déclenche les disjoncteurs conformément aux exigences de réponse organisationnelle, y compris la limitation du débit basée sur les politiques de capacité et l'isolation de la charge de travail.                  |   2   | D/V  |

---

## C4.8 Séparation des environnements et contrôles de promotion

Appliquez des limites strictes d'environnement avec des barrières automatisées de promotion et une validation de sécurité.

|   #   | Description                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Vérifiez que les environnements de développement/test/production fonctionnent dans des VPC/VNet séparés sans rôles IAM, groupes de sécurité ou connectivité réseau partagés.                                                                                                           |   1   | D/V  |
| 4.8.2 | Vérifier que la promotion de l'environnement nécessite l'approbation du personnel autorisé défini par l'organisation, avec des signatures cryptographiques et des pistes d'audit immuables.                                                                                            |   1   | D/V  |
| 4.8.3 | Vérifiez que les environnements de production bloquent l'accès SSH, désactivent les points de terminaison de débogage et exigent des demandes de changement avec des exigences de préavis organisationnel, sauf en cas d'urgence.                                                      |   2   | D/V  |
| 4.8.4 | Vérifiez que les modifications d'infrastructure en tant que code nécessitent une relecture par les pairs avec des tests automatisés et une analyse de sécurité avant la fusion dans la branche principale.                                                                             |   2   | D/V  |
| 4.8.5 | Vérifiez que les données non productives sont anonymisées conformément aux exigences de confidentialité de l'organisation, à la génération de données synthétiques ou à la mascarade complète des données avec suppression des informations personnelles identifiables (IPI) vérifiée. |   2   | D/V  |
| 4.8.6 | Vérifiez que les étapes de promotion incluent des tests de sécurité automatisés (SAST, DAST, analyse des conteneurs) avec zéro résultat CRITIQUE requis pour l'approbation.                                                                                                            |   2   | D/V  |

---

## C4.9 Sauvegarde et restauration de l'infrastructure

Assurez la résilience de l'infrastructure grâce à des sauvegardes automatisées, des procédures de récupération testées et des capacités de reprise après sinistre.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.9.1 | Vérifiez que les configurations d'infrastructure sont sauvegardées conformément aux calendriers de sauvegarde organisationnels vers des régions géographiquement distinctes avec la mise en œuvre de la stratégie de sauvegarde 3-2-1. |   1   | D/V  |
| 4.9.2 | Vérifiez que les systèmes de sauvegarde fonctionnent dans des réseaux isolés avec des identifiants séparés et un stockage en coupure d'air pour la protection contre les rançongiciels.                                                |   2   | D/V  |
| 4.9.3 | Vérifiez que les procédures de récupération sont testées et validées par des tests automatisés conformément aux calendriers organisationnels, avec des objectifs de RTO et RPO répondant aux exigences de l'organisation.              |   2   |  V   |
| 4.9.4 | Vérifiez que la reprise après sinistre inclut des procédures opérationnelles spécifiques à l'IA avec la restauration des poids des modèles, la reconstruction du cluster GPU, et la cartographie des dépendances des services.         |   3   |  V   |

---

## C4.10 Conformité et Gouvernance des Infrastructures

Maintenez la conformité réglementaire grâce à une évaluation continue, une documentation et des contrôles automatisés.

|   #    | Description                                                                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Vérifiez que la conformité de l'infrastructure est évaluée conformément aux calendriers organisationnels par rapport aux contrôles SOC 2, ISO 27001 ou FedRAMP avec une collecte automatisée des preuves.                 |   2   | D/V  |
| 4.10.2 | Vérifiez que la documentation de l'infrastructure inclut des diagrammes réseau, des cartes de flux de données et des modèles de menace mis à jour conformément aux exigences de gestion des changements organisationnels. |   2   |  V   |
| 4.10.3 | Vérifiez que les changements d'infrastructure font l'objet d'une évaluation automatisée de l'impact sur la conformité avec des flux de travail d'approbation réglementaire pour les modifications à haut risque.          |   3   | D/V  |

---

## C4.11 Sécurité du matériel d'IA

Sécuriser les composants matériels spécifiques à l'IA, y compris les GPU, TPU et les accélérateurs d'IA spécialisés.

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Vérifiez que le micrologiciel de l'accélérateur IA (BIOS GPU, micrologiciel TPU) est vérifié avec des signatures cryptographiques et mis à jour conformément aux délais de gestion des correctifs de l'organisation. |   2   | D/V  |
| 4.11.2 | Vérifiez qu'avant l'exécution de la charge de travail, l'intégrité de l'accélérateur AI est validée par une attestation matérielle utilisant TPM 2.0, Intel TXT ou AMD SVM.                                          |   2   | D/V  |
| 4.11.3 | Vérifiez que la mémoire GPU est isolée entre les charges de travail en utilisant SR-IOV, MIG (GPU multi-instance) ou un partitionnement matériel équivalent avec une sanitation de la mémoire entre les tâches.      |   2   | D/V  |
| 4.11.4 | Vérifiez que la chaîne d'approvisionnement du matériel d'IA inclut une vérification de la provenance avec des certificats du fabricant et une validation de l'emballage inviolable.                                  |   3   |  V   |
| 4.11.5 | Vérifiez que les modules de sécurité matérielle (HSM) protègent les poids des modèles d’IA et les clés cryptographiques avec une certification FIPS 140-2 Niveau 3 ou Common Criteria EAL4+.                         |   3   | D/V  |

---

## C4.12 Infrastructure d'IA Edge et Distribuée

Déploiements sécurisés d'IA distribuée incluant l'informatique en périphérie, l'apprentissage fédéré et les architectures multi-sites.

|   #    | Description                                                                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.12.1 | Vérifiez que les dispositifs d'IA en périphérie s'authentifient auprès de l'infrastructure centrale en utilisant TLS mutuel avec des certificats de dispositif renouvelés conformément à la politique organisationnelle de gestion des certificats. |   2   | D/V  |
| 4.12.2 | Vérifiez que les dispositifs périphériques mettent en œuvre un démarrage sécurisé avec des signatures vérifiées et une protection contre le retour en arrière afin d'empêcher les attaques de rétrogradation du firmware.                           |   2   | D/V  |
| 4.12.3 | Vérifiez que la coordination d'IA distribuée utilise des algorithmes de consensus tolérants aux fautes byzantines avec validation des participants et détection des nœuds malveillants.                                                             |   3   | D/V  |
| 4.12.4 | Vérifiez que la communication de la périphérie vers le cloud inclut la limitation de la bande passante, la compression des données et les capacités de fonctionnement hors ligne avec un stockage local sécurisé.                                   |   3   | D/V  |

---

## C4.13 Sécurité des infrastructures multi-cloud et hybrides

Sécurisez les charges de travail d'IA sur plusieurs fournisseurs de cloud et dans des déploiements hybrides cloud-sur site.

|   #    | Description                                                                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Vérifiez que les déploiements d'IA multi-cloud utilisent une fédération d'identité indépendante du cloud (OIDC, SAML) avec une gestion centralisée des politiques entre les fournisseurs.                                             |   2   | D/V  |
| 4.13.2 | Vérifiez que le transfert de données inter-cloud utilise un chiffrement de bout en bout avec des clés gérées par le client et que les contrôles de résidence des données sont appliqués conformément à chaque juridiction.            |   2   | D/V  |
| 4.13.3 | Vérifiez que les charges de travail IA en cloud hybride appliquent des politiques de sécurité cohérentes à la fois sur site et dans les environnements cloud, avec une surveillance unifiée et des alertes.                           |   2   | D/V  |
| 4.13.4 | Vérifiez que la prévention de l'enfermement chez un fournisseur cloud comprend une infrastructure en tant que code portable, des API standardisées et des capacités d'exportation de données avec des outils de conversion de format. |   3   |  V   |
| 4.13.5 | Vérifiez que l'optimisation des coûts multi-cloud inclut des contrôles de sécurité empêchant la prolifération des ressources ainsi que les frais non autorisés de transfert de données entre clouds.                                  |   3   |  V   |

---

## C4.14 Automatisation de l'infrastructure et sécurité GitOps

Automatisation sécurisée des pipelines d'infrastructure et des workflows GitOps pour la gestion de l'infrastructure IA.

|   #    | Description                                                                                                                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.14.1 | Vérifiez que les dépôts GitOps exigent des commits signés avec des clés GPG et des règles de protection de branche empêchant les pushes directs vers les branches principales.                                                                         |   2   | D/V  |
| 4.14.2 | Vérifiez que l'automatisation de l'infrastructure inclut la détection des dérives avec des capacités de remédiation automatique et de retour en arrière déclenchées selon les exigences de réponse organisationnelle aux modifications non autorisées. |   2   | D/V  |
| 4.14.3 | Vérifiez que l’approvisionnement automatisé de l’infrastructure inclut la validation des politiques de sécurité avec blocage du déploiement en cas de configurations non conformes.                                                                    |   2   | D/V  |
| 4.14.4 | Vérifiez que les secrets d'automatisation de l'infrastructure sont gérés via des opérateurs de secrets externes (External Secrets Operator, Bank-Vaults) avec une rotation automatique.                                                                |   2   | D/V  |
| 4.14.5 | Vérifiez que l'infrastructure auto-réparatrice comprend la corrélation des événements de sécurité avec la réponse automatisée aux incidents et les flux de travail de notification des parties prenantes.                                              |   3   |  V   |

---

## C4.15 Sécurité de l'infrastructure résistante au quantique

Préparer l'infrastructure d'IA aux menaces de l'informatique quantique grâce à la cryptographie post-quantique et aux protocoles résistants au quantique.

|   #    | Description                                                                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Vérifiez que l'infrastructure d'IA met en œuvre des algorithmes cryptographiques post-quantiques approuvés par le NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) pour l'échange de clés et les signatures numériques. |   3   | D/V  |
| 4.15.2 | Vérifiez que les systèmes de distribution quantique de clés (QKD) sont mis en œuvre pour les communications IA à haute sécurité avec des protocoles de gestion de clés sûrs quantiques.                                    |   3   | D/V  |
| 4.15.3 | Vérifiez que les cadres d'agilité cryptographique permettent une migration rapide vers de nouveaux algorithmes post-quantiques avec une rotation automatisée des certificats et des clés.                                  |   3   | D/V  |
| 4.15.4 | Vérifiez que la modélisation des menaces quantiques évalue la vulnérabilité de l'infrastructure IA aux attaques quantiques avec des calendriers de migration documentés et des évaluations des risques.                    |   3   |  V   |
| 4.15.5 | Vérifiez que les systèmes cryptographiques hybrides classique-quantique offrent une défense en profondeur pendant la période de transition quantique avec une surveillance des performances.                               |   3   | D/V  |

---

## C4.16 Informatique confidentielle et enclaves sécurisées

Protégez les charges de travail d'IA et les poids des modèles en utilisant des environnements d'exécution sécurisés basés sur le matériel et des technologies de calcul confidentiel.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.16.1 | Vérifiez que les modèles d'IA sensibles s'exécutent dans des enclaves Intel SGX, AMD SEV-SNP ou ARM TrustZone avec une mémoire cryptée et une vérification d'attestation.                      |   3   | D/V  |
| 4.16.2 | Vérifiez que les conteneurs confidentiels (Kata Containers, gVisor avec informatique confidentielle) isolent les charges de travail d'IA avec un chiffrement mémoire appliqué par le matériel. |   3   | D/V  |
| 4.16.3 | Vérifiez que l'attestation à distance valide l'intégrité de l'enclave avant de charger les modèles d'IA, avec une preuve cryptographique de l'authenticité de l'environnement d'exécution.     |   3   | D/V  |
| 4.16.4 | Vérifiez que les services d'inférence IA confidentiels empêchent l'extraction du modèle grâce à un calcul chiffré avec des poids de modèle scellés et une exécution protégée.                  |   3   | D/V  |
| 4.16.5 | Vérifiez que l'orchestration de l'environnement d'exécution sécurisé gère le cycle de vie de l'enclave sécurisée avec l'attestation à distance et des canaux de communication chiffrés.        |   3   | D/V  |
| 4.16.6 | Vérifiez que le calcul multipartite sécurisé (SMPC) permet un entraînement collaboratif de l'IA sans exposer les ensembles de données individuels ni les paramètres du modèle.                 |   3   | D/V  |

---

## C4.17 Infrastructure à connaissance zéro

Mettre en œuvre des systèmes de preuve à divulgation nulle de connaissance pour la vérification et l'authentification de l'IA tout en préservant la confidentialité, sans révéler d'informations sensibles.

|   #    | Description                                                                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Vérifiez que les preuves à divulgation nulle de connaissance (ZK-SNARKs, ZK-STARKs) valident l’intégrité du modèle d’IA et la provenance de l’entraînement sans exposer les poids du modèle ni les données d’entraînement.                  |   3   | D/V  |
| 4.17.2 | Vérifiez que les systèmes d'authentification basés sur les preuves à connaissance nulle (ZK) permettent une vérification des utilisateurs préservant la vie privée pour les services d'IA sans révéler les informations liées à l'identité. |   3   | D/V  |
| 4.17.3 | Vérifiez que les protocoles d'intersection privée d'ensembles (PSI) permettent une correspondance sécurisée des données pour l'IA fédérée sans exposer les ensembles de données individuels.                                                |   3   | D/V  |
| 4.17.4 | Vérifiez que les systèmes d'apprentissage automatique à connaissance nulle (ZKML) permettent des inférences d'IA vérifiables grâce à une preuve cryptographique de calcul correct.                                                          |   3   | D/V  |
| 4.17.5 | Vérifiez que les ZK-rollups offrent un traitement des transactions d'IA évolutif et préservant la confidentialité, avec une vérification par lots et une réduction de la charge computationnelle.                                           |   3   | D/V  |

---

## C4.18 Prévention des attaques par canal auxiliaire

Protégez l'infrastructure d'IA contre les attaques par canaux auxiliaires basées sur le timing, la puissance, l'électromagnétisme et le cache, qui pourraient divulguer des informations sensibles.

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Vérifiez que le temps d'inférence de l'IA est normalisé en utilisant des algorithmes à temps constant et du bourrage pour prévenir les attaques d'extraction de modèle basées sur le temps. |   3   | D/V  |
| 4.18.2 | Vérifiez que la protection contre l'analyse de puissance comprend l'injection de bruit, le filtrage de la ligne d'alimentation et les modèles d'exécution aléatoires pour le matériel d'IA. |   3   | D/V  |
| 4.18.3 | Vérifiez que l'atténuation des canaux latéraux basés sur le cache utilise la partition du cache, la randomisation et les instructions de vidage pour empêcher la fuite d'informations.      |   3   | D/V  |
| 4.18.4 | Vérifiez que la protection contre les émissions électromagnétiques inclut le blindage, le filtrage des signaux et le traitement aléatoire afin de prévenir les attaques de type TEMPEST.    |   3   | D/V  |
| 4.18.5 | Vérifiez que les défenses contre les canaux secondaires microarchitecturaux incluent des contrôles de l'exécution spéculative et l'obfuscation des schémas d'accès mémoire.                 |   3   | D/V  |

---

## C4.19 Sécurité matérielle pour l'IA neuromorphique et spécialisée

Sécuriser les architectures matérielles émergentes en IA, y compris les puces neuromorphiques, les FPGA, les ASIC personnalisés et les systèmes de calcul optique.

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.19.1 | Vérifiez que la sécurité des puces neuromorphiques inclut le chiffrement des schémas de spikes, la protection des poids synaptiques et la validation des règles d'apprentissage basées sur le matériel.            |   3   | D/V  |
| 4.19.2 | Vérifiez que les accélérateurs d'IA basés sur FPGA mettent en œuvre le chiffrement des bitstreams, des mécanismes anti-sabotage et un chargement sécurisé de la configuration avec des mises à jour authentifiées. |   3   | D/V  |
| 4.19.3 | Vérifiez que la sécurité ASIC personnalisée inclut des processeurs de sécurité intégrés, une racine de confiance matérielle, et un stockage sécurisé des clés avec détection d’intrusion.                          |   3   | D/V  |
| 4.19.4 | Vérifiez que les systèmes de calcul optique mettent en œuvre un chiffrement optique quantique sécurisé, une commutation photonique sécurisée et un traitement du signal optique protégé.                           |   3   | D/V  |
| 4.19.5 | Vérifiez que les puces IA hybrides analogiques-numériques incluent un calcul analogique sécurisé, un stockage des poids protégé et une conversion analogique-numérique authentifiée.                               |   3   | D/V  |

---

## C4.20 Infrastructure informatique de calcul préservant la vie privée

Mettre en œuvre des contrôles d'infrastructure pour le calcul respectueux de la vie privée afin de protéger les données sensibles lors du traitement et de l'analyse par l'IA.

|   #    | Description                                                                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.20.1 | Vérifiez que l'infrastructure de chiffrement homomorphe permet le calcul chiffré sur des charges de travail d'IA sensibles avec une vérification cryptographique de l'intégrité et une surveillance des performances.    |   3   | D/V  |
| 4.20.2 | Vérifiez que les systèmes de récupération d'informations privées permettent des requêtes sur la base de données sans révéler les motifs des requêtes grâce à une protection cryptographique des motifs d'accès.          |   3   | D/V  |
| 4.20.3 | Vérifiez que les protocoles de calcul multipartite sécurisé permettent une inférence IA préservant la confidentialité sans exposer les entrées individuelles ni les calculs intermédiaires.                              |   3   | D/V  |
| 4.20.4 | Vérifiez que la gestion des clés préservant la vie privée inclut la génération distribuée des clés, la cryptographie à seuil et la rotation sécurisée des clés avec une protection matérielle.                           |   3   | D/V  |
| 4.20.5 | Vérifiez que la performance du calcul préservant la confidentialité est optimisée grâce au regroupement, à la mise en cache et à l'accélération matérielle tout en maintenant les garanties de sécurité cryptographique. |   3   | D/V  |

---

## C4.15 Sécurité de l'intégration cloud du cadre d'agent et déploiement hybride

Contrôles de sécurité pour les frameworks d'agents intégrés au cloud avec des architectures hybrides sur site/cloud.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Vérifiez que l'intégration du stockage cloud utilise un chiffrement de bout en bout avec une gestion des clés contrôlée par l'agent.                    |   1   | D/V  |
| 4.15.2 | Vérifiez que les limites de sécurité du déploiement hybride sont clairement définies avec des canaux de communication chiffrés.                         |   2   | D/V  |
| 4.15.3 | Vérifiez que l'accès aux ressources cloud inclut une vérification zero-trust avec une authentification continue.                                        |   2   | D/V  |
| 4.15.4 | Vérifiez que les exigences de résidence des données sont appliquées par une attestation cryptographique des emplacements de stockage.                   |   3   | D/V  |
| 4.15.5 | Vérifiez que les évaluations de sécurité du fournisseur cloud incluent une modélisation des menaces spécifique à l'agent et une évaluation des risques. |   3   | D/V  |

---

## Références

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)

