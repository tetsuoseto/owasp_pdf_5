# C6 Sécurité de la chaîne d'approvisionnement pour les modèles, cadres et données

## Objectif de contrôle

Les attaques de la chaîne d'approvisionnement en IA exploitent des modèles, cadres ou ensembles de données tiers pour y insérer des portes dérobées, des biais ou du code exploitable. Ces contrôles fournissent une traçabilité complète, une gestion des vulnérabilités et une surveillance pour protéger l'ensemble du cycle de vie du modèle.

---

## C6.1 Vérification et provenance des modèles pré-entraînés

Évaluez et authentifiez les origines, les licences et les comportements cachés des modèles tiers avant tout ajustement ou déploiement.

|   #   | Description                                                                                                                                                                | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Vérifiez que chaque artefact de modèle tiers inclut un enregistrement de provenance signé identifiant le dépôt source et le hash de commit.                                |   1   | D/V  |
| 6.1.2 | Vérifiez que les modèles sont analysés à la recherche de couches malveillantes ou de déclencheurs de chevaux de Troie à l'aide d'outils automatisés avant l'importation.   |   1   | D/V  |
| 6.1.3 | Vérifiez que l'apprentissage par transfert ajuste finement les modèles pour réussir l'évaluation adversariale afin de détecter les comportements cachés.                   |   2   |  D   |
| 6.1.4 | Vérifiez que les licences des modèles, les étiquettes de contrôle à l’exportation et les déclarations d’origine des données sont enregistrées dans une entrée ML-BOM.      |   2   |  V   |
| 6.1.5 | Vérifiez que les modèles à haut risque (poids publiquement téléchargés, créateurs non vérifiés) restent en quarantaine jusqu'à la révision et l'approbation par un humain. |   3   | D/V  |

---

## C6.2 Analyse des cadres et des bibliothèques

Scanner en continu les frameworks et bibliothèques de ML à la recherche de CVE et de code malveillant pour maintenir la sécurité de la pile d'exécution.

|   #   | Description                                                                                                                                             | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Vérifiez que les pipelines CI exécutent des scanners de dépendances sur les frameworks d'IA et les bibliothèques critiques.                             |   1   | D/V  |
| 6.2.2 | Vérifiez que les vulnérabilités critiques (CVSS ≥ 7,0) bloquent la promotion vers les images de production.                                             |   1   | D/V  |
| 6.2.3 | Vérifiez que l'analyse statique du code s'exécute sur les bibliothèques ML forkées ou fournies en tant que dépendances internes.                        |   2   |  D   |
| 6.2.4 | Vérifiez que les propositions de mise à niveau du framework incluent une évaluation de l’impact sur la sécurité faisant référence aux flux CVE publics. |   2   |  V   |
| 6.2.5 | Vérifiez que les capteurs d'exécution alertent en cas de chargements inattendus de bibliothèques dynamiques qui dévient du SBOM signé.                  |   3   |  V   |

---

## C6.3 Verrouillage et vérification des dépendances

Épinglez chaque dépendance à des digests immuables et reproduisez les builds pour garantir des artefacts identiques et sans altération.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Vérifiez que tous les gestionnaires de paquets appliquent le verrouillage des versions via les fichiers de verrouillage.                      |   1   | D/V  |
| 6.3.2 | Vérifiez que des résumés immuables sont utilisés au lieu de balises modifiables dans les références de conteneurs.                            |   1   | D/V  |
| 6.3.3 | Vérifiez que les contrôles de construction reproductible comparent les hachages entre les exécutions CI pour garantir des sorties identiques. |   2   |  D   |
| 6.3.4 | Vérifiez que les attestations de construction sont conservées pendant 18 mois pour assurer la traçabilité des audits.                         |   2   |  V   |
| 6.3.5 | Vérifiez que les dépendances expirées déclenchent des PR automatisées pour mettre à jour ou forker les versions épinglées.                    |   3   |  D   |

---

## C6.4 Application de la source fiable

Autoriser uniquement le téléchargement d'artefacts provenant de sources approuvées par l'organisation et vérifiées cryptographiquement, et bloquer tout le reste.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Vérifiez que les poids du modèle, les ensembles de données et les conteneurs sont téléchargés uniquement à partir de domaines approuvés ou de registres internes. |   1   | D/V  |
| 6.4.2 | Vérifiez que les signatures Sigstore/Cosign valident l'identité de l'éditeur avant que les artefacts ne soient mis en cache localement.                           |   1   | D/V  |
| 6.4.3 | Vérifiez que les proxies de sortie bloquent les téléchargements d’artefacts non authentifiés afin de faire respecter la politique de source de confiance.         |   2   |  D   |
| 6.4.4 | Vérifiez que les listes blanches des dépôts sont examinées trimestriellement avec une preuve de justification commerciale pour chaque entrée.                     |   2   |  V   |
| 6.4.5 | Vérifier que les violations de politique déclenchent la mise en quarantaine des artefacts et le retour en arrière des exécutions de pipeline dépendantes.         |   3   |  V   |

---

## C6.5 Évaluation des risques liés aux ensembles de données tiers

Évaluer les ensembles de données externes pour la contamination, les biais et la conformité légale, et les surveiller tout au long de leur cycle de vie.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.5.1 | Vérifiez que les ensembles de données externes font l'objet d'une évaluation des risques de contamination (par exemple, empreinte des données, détection des valeurs aberrantes). |   1   | D/V  |
| 6.5.2 | Vérifiez que les métriques de biais (parité démographique, égalité des chances) sont calculées avant l'approbation du jeu de données.                                             |   1   |  D   |
| 6.5.3 | Vérifiez que la provenance et les conditions de licence des ensembles de données sont enregistrées dans les entrées ML-BOM.                                                       |   2   |  V   |
| 6.5.4 | Vérifiez que la surveillance périodique détecte la dérive ou la corruption des ensembles de données hébergés.                                                                     |   2   |  V   |
| 6.5.5 | Vérifiez que le contenu non autorisé (droits d'auteur, informations personnelles identifiables) est supprimé automatiquement avant l'entraînement.                                |   3   |  D   |

---

## C6.6 Surveillance des attaques sur la chaîne d'approvisionnement

Détectez tôt les menaces liées à la chaîne d'approvisionnement grâce aux flux CVE, à l'analyse des journaux d'audit et aux simulations d'équipes rouges.

|   #   | Description                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.6.1 | Vérifiez que les journaux d'audit CI/CD sont transmis aux systèmes SIEM pour la détection des tirages de paquets anormaux ou des étapes de build altérées.                                 |   1   |  V   |
| 6.6.2 | Vérifiez que les procédures d'intervention en cas d'incident comprennent des procédures de retour en arrière pour les modèles ou bibliothèques compromis.                                  |   2   |  D   |
| 6.6.3 | Vérifiez que l'enrichissement des renseignements sur les menaces étiquette les indicateurs spécifiques au ML (par exemple, les IoC d'empoisonnement de modèle) lors du triage des alertes. |   3   |  V   |

---

## C6.7 ML‑BOM pour les artefacts de modèle

Générez et signez des SBOMs détaillées spécifiques au ML (ML-BOMs) afin que les utilisateurs en aval puissent vérifier l'intégrité des composants au moment du déploiement.

|   #   | Description                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Vérifiez que chaque artefact de modèle publie un ML‑BOM listant les jeux de données, les poids, les hyperparamètres et les licences.         |   1   | D/V  |
| 6.7.2 | Vérifiez que la génération de ML-BOM et la signature Cosign sont automatisées dans le CI et requises pour la fusion.                         |   1   | D/V  |
| 6.7.3 | Vérifiez que les contrôles de complétude ML-BOM échouent la compilation si des métadonnées de composants (hachage, licence) sont manquantes. |   2   |  D   |
| 6.7.4 | Vérifiez que les consommateurs en aval peuvent interroger les ML-BOM via l'API pour valider les modèles importés au moment du déploiement.   |   2   |  V   |
| 6.7.5 | Vérifiez que les ML-BOM sont versionnés et comparés pour détecter les modifications non autorisées.                                          |   3   |  V   |

---

## Références

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

