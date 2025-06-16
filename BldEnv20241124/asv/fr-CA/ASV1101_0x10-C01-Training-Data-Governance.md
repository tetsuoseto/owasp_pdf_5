# Gouvernance des données d'entraînement C1 et gestion des biais

## Objectif de contrôle

Les données d'entraînement doivent être obtenues, manipulées et maintenues de manière à préserver la provenance, la sécurité, la qualité et l'équité. Cela permet de remplir les obligations légales et de réduire les risques de biais, d'empoisonnement ou de violations de la vie privée tout au long du cycle de vie de l'IA.

---

## C1.1 Origine des données d'entraînement

Maintenez un inventaire vérifiable de tous les ensembles de données, n'acceptez que des sources fiables et consignez chaque modification pour assurer la traçabilité.

|   #   | Description                                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.1.1 | Vérifiez qu'un inventaire à jour de chaque source de données d'entraînement (origine, responsable/propriétaire, licence, méthode de collecte, contraintes d'utilisation prévues et historique de traitement) est maintenu.                                                                                                                       |   1   | D/V  |
| 1.1.2 | Vérifiez que seuls les ensembles de données validés pour leur qualité, représentativité, approvisionnement éthique et conformité aux licences sont autorisés, réduisant ainsi les risques d'empoisonnement, de biais intégré et de violation de la propriété intellectuelle.                                                                     |   1   | D/V  |
| 1.1.3 | Vérifiez que la minimisation des données est appliquée afin que les attributs inutiles ou sensibles soient exclus.                                                                                                                                                                                                                               |   1   | D/V  |
| 1.1.4 | Vérifiez que toutes les modifications du jeu de données font l'objet d'un processus d'approbation enregistré.                                                                                                                                                                                                                                    |   2   | D/V  |
| 1.1.5 | Vérifiez que la qualité de l'étiquetage/annotation est garantie par des vérifications croisées ou un consensus entre examinateurs.                                                                                                                                                                                                               |   2   | D/V  |
| 1.1.6 | Vérifiez que des « fiches de données » ou des « fiches techniques pour les ensembles de données » sont maintenues pour les ensembles de données d'entraînement importants, détaillant les caractéristiques, les motivations, la composition, les processus de collecte, le prétraitement, ainsi que les utilisations recommandées/déconseillées. |   2   | D/V  |

---

## C1.2 Sécurité et intégrité des données d'entraînement

Restreindre l'accès, chiffrer les données au repos et en transit, et valider l'intégrité pour empêcher la falsification ou le vol.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Vérifiez que les contrôles d'accès protègent le stockage et les pipelines.                                                                                                                                                                                                                                                                                                       |   1   | D/V  |
| 1.2.2 | Vérifiez que les ensembles de données sont chiffrés en transit et, pour toutes les informations sensibles ou personnellement identifiables (IPI), au repos, en utilisant des algorithmes cryptographiques standard de l'industrie et des pratiques de gestion des clés.                                                                                                          |   2   | D/V  |
| 1.2.3 | Vérifiez que des hachages cryptographiques ou des signatures numériques sont utilisés pour garantir l'intégrité des données lors du stockage et du transfert, et que des techniques automatiques de détection d'anomalies sont appliquées pour protéger contre les modifications non autorisées ou la corruption, y compris les tentatives ciblées d'empoisonnement des données. |   2   | D/V  |
| 1.2.4 | Vérifiez que les versions des ensembles de données sont suivies pour permettre un retour en arrière.                                                                                                                                                                                                                                                                             |   3   | D/V  |
| 1.2.5 | Vérifiez que les données obsolètes sont supprimées de manière sécurisée ou anonymisées conformément aux politiques de conservation des données, aux exigences réglementaires, et afin de réduire la surface d'attaque.                                                                                                                                                           |   2   | D/V  |

---

## C1.3 Complétude et Équité de la Représentation

Détecter les biais démographiques et appliquer des mesures d'atténuation afin que les taux d'erreur du modèle soient équitables entre les groupes.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                                                  | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.3.1 | Vérifiez que les jeux de données sont analysés pour détecter les déséquilibres de représentation et les biais potentiels concernant les attributs protégés légalement (par exemple, race, genre, âge) ainsi que d'autres caractéristiques éthiquement sensibles pertinentes pour le domaine d'application du modèle (par exemple, statut socio-économique, localisation).                                    |   1   | D/V  |
| 1.3.2 | Vérifier que les biais identifiés sont atténués grâce à des stratégies documentées telles que le rééquilibrage, l’augmentation ciblée des données, les ajustements algorithmiques (par exemple, les techniques de pré-traitement, traitement en cours ou post-traitement), ou le repondération, et que l’impact de cette atténuation sur l’équité ainsi que sur la performance globale du modèle est évalué. |   2   | D/V  |
| 1.3.3 | Vérifiez que les métriques d'équité post-entraînement sont évaluées et documentées.                                                                                                                                                                                                                                                                                                                          |   2   | D/V  |
| 1.3.4 | Vérifiez qu'une politique de gestion des biais du cycle de vie attribue des responsables et un rythme de révision.                                                                                                                                                                                                                                                                                           |   3   | D/V  |

---

## C1.4 Qualité, intégrité et sécurité de l'étiquetage des données d'entraînement

Protégez les étiquettes par chiffrement et exigez une double vérification pour les classes critiques.

|   #   | Description                                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Vérifiez que la qualité de l'étiquetage/de l'annotation est assurée par des directives claires, des vérifications croisées par les réviseurs, des mécanismes de consensus (par exemple, le suivi de l'accord entre annotateurs) et des processus définis pour résoudre les divergences.                       |   2   | D/V  |
| 1.4.2 | Vérifiez que des hachages cryptographiques ou des signatures numériques sont appliqués aux artefacts d’étiquette afin de garantir leur intégrité et authenticité.                                                                                                                                             |   2   | D/V  |
| 1.4.3 | Vérifiez que les interfaces et plateformes d'étiquetage appliquent des contrôles d'accès stricts, maintiennent des journaux d'audit infalsifiables de toutes les activités d'étiquetage et protègent contre les modifications non autorisées.                                                                 |   2   | D/V  |
| 1.4.4 | Vérifiez que les étiquettes critiques pour la sécurité, la sûreté ou l’équité (par exemple, l’identification de contenu toxique, de résultats médicaux critiques) font l’objet d’un examen obligatoire indépendant en double ou d’une vérification robuste équivalente.                                       |   3   | D/V  |
| 1.4.5 | Vérifiez que les informations sensibles (y compris les données personnelles identifiables) capturées par inadvertance ou nécessairement présentes dans les étiquettes sont expurgées, pseudonymisées, anonymisées ou cryptées au repos et en transit, conformément aux principes de minimisation des données. |   2   | D/V  |
| 1.4.6 | Vérifiez que les guides d'étiquetage et les instructions sont complets, sous contrôle de version et revus par des pairs.                                                                                                                                                                                      |   2   | D/V  |
| 1.4.7 | Vérifiez que les schémas de données (y compris pour les étiquettes) sont clairement définis et soumis à un contrôle de version.                                                                                                                                                                               |   2   | D/V  |
| 1.8.2 | Vérifiez que les flux de travail d'étiquetage externalisés ou participatifs incluent des mesures techniques et procédurales pour garantir la confidentialité des données, leur intégrité, la qualité des étiquettes, et prévenir toute fuite de données.                                                      |   2   | D/V  |

---

## C1.5 Assurance de la qualité des données d'entraînement

Combinez la validation automatisée, les contrôles ponctuels manuels et la correction journalisée pour garantir la fiabilité des ensembles de données.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Vérifiez que les tests automatisés détectent les erreurs de format, les valeurs nulles et les décalages d'étiquettes à chaque ingestion ou transformation significative.                                                                                                                                                                               |   1   |  D   |
| 1.5.2 | Vérifiez que les ensembles de données défaillants sont mis en quarantaine avec des pistes d'audit.                                                                                                                                                                                                                                                     |   1   | D/V  |
| 1.5.3 | Vérifiez que les contrôles ponctuels manuels réalisés par des experts du domaine couvrent un échantillon statistiquement significatif (par exemple, ≥1 % ou 1 000 échantillons, selon la valeur la plus élevée, ou tel que déterminé par l'évaluation des risques) pour identifier les problèmes de qualité subtils non détectés par l'automatisation. |   2   |  V   |
| 1.5.4 | Vérifiez que les étapes de remédiation sont ajoutées aux enregistrements de provenance.                                                                                                                                                                                                                                                                |   2   | D/V  |
| 1.5.5 | Vérifiez que les seuils de qualité bloquent les ensembles de données de qualité inférieure, sauf si des exceptions sont approuvées.                                                                                                                                                                                                                    |   2   | D/V  |

---

## C1.6 Détection de l'empoisonnement des données

Appliquer la détection statistique d'anomalies et les flux de travail de mise en quarantaine pour stopper les insertions adverses.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Vérifiez que des techniques de détection d'anomalies (par exemple, méthodes statistiques, détection des valeurs aberrantes, analyse d'incorporation) sont appliquées aux données d'entraînement lors de leur ingestion et avant les principales sessions d'entraînement afin d'identifier d'éventuelles attaques par empoisonnement ou une corruption involontaire des données. |   2   | D/V  |
| 1.6.2 | Vérifiez que les échantillons signalés déclenchent une révision manuelle avant l'entraînement.                                                                                                                                                                                                                                                                                  |   2   | D/V  |
| 1.6.3 | Vérifiez que les résultats alimentent le dossier de sécurité du modèle et informent le renseignement continu sur les menaces.                                                                                                                                                                                                                                                   |   2   |  V   |
| 1.6.4 | Vérifiez que la logique de détection est actualisée avec les nouvelles informations sur les menaces.                                                                                                                                                                                                                                                                            |   3   | D/V  |
| 1.6.5 | Vérifiez que les pipelines d'apprentissage en ligne surveillent la dérive de distribution.                                                                                                                                                                                                                                                                                      |   3   | D/V  |
| 1.6.6 | Vérifiez que des défenses spécifiques contre les types d'attaques connues d'empoisonnement de données (par exemple, inversion d’étiquettes, insertion de déclencheurs de porte dérobée, attaques par instances influentes) sont prises en compte et mises en œuvre en fonction du profil de risque du système et des sources de données.                                        |   3   | D/V  |

---

## C1.7 Suppression des données utilisateur et application du consentement

Respecter les demandes de suppression et de retrait du consentement dans l'ensemble des ensembles de données, des sauvegardes et des artefacts dérivés.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Vérifiez que les workflows de suppression effacent les données primaires et dérivées ainsi que l'impact sur le modèle, et que cet impact sur les modèles affectés est évalué et, si nécessaire, traité (par exemple, par un nouvel entraînement ou une recalibration).                                                                                            |   1   | D/V  |
| 1.7.2 | Vérifiez que des mécanismes sont en place pour suivre et respecter la portée et le statut du consentement utilisateur (et des retraits) concernant les données utilisées dans l'entraînement, et que le consentement est validé avant que les données ne soient intégrées dans de nouveaux processus d'entraînement ou des mises à jour significatives du modèle. |   2   |  D   |
| 1.7.3 | Vérifiez que les workflows sont testés annuellement et consignés dans un journal.                                                                                                                                                                                                                                                                                 |   2   |  V   |

---

## C1.8 Sécurité de la chaîne d'approvisionnement

Évaluer les fournisseurs de données externes et vérifier l'intégrité via des canaux authentifiés et chiffrés.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.8.1 | Vérifiez que les fournisseurs de données tiers, y compris les prestataires de modèles pré-entraînés et de jeux de données externes, font l'objet d'une diligence raisonnable en matière de sécurité, de confidentialité, d'approvisionnement éthique et de qualité des données avant que leurs données ou modèles ne soient intégrés.                                                              |   2   | D/V  |
| 1.8.2 | Vérifiez que les transferts externes utilisent TLS/authentification et des vérifications d'intégrité.                                                                                                                                                                                                                                                                                              |   1   |  D   |
| 1.8.3 | Vérifiez que les sources de données à haut risque (par exemple, les ensembles de données open-source dont la provenance est inconnue, les fournisseurs non vérifiés) font l’objet d’un contrôle renforcé, tel qu’une analyse en bac à sable, des vérifications approfondies de qualité/biais, et une détection ciblée de la contamination, avant leur utilisation dans des applications sensibles. |   2   | D/V  |
| 1.8.4 | Vérifiez que les modèles pré-entraînés obtenus auprès de tiers sont évalués pour les biais intégrés, les portes dérobées potentielles, l'intégrité de leur architecture et la provenance de leurs données d'entraînement originales avant l'affinage ou le déploiement.                                                                                                                            |   3   | D/V  |

---

## C1.9 Détection des échantillons adversaires

Mettre en œuvre des mesures pendant la phase d'entraînement, telles que l'entraînement adversarial, pour renforcer la résilience du modèle face aux exemples adversariaux.

|   #   | Description                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Vérifiez que des défenses appropriées, telles que l'entraînement adversarial (utilisant des exemples adversariaux générés), l'augmentation de données avec des entrées perturbées, ou des techniques d'optimisation robuste, sont mises en œuvre et ajustées pour les modèles pertinents en fonction de l'évaluation des risques. |   3   | D/V  |
| 1.9.2 | Vérifiez que si un entraînement par adversaire est utilisé, la génération, la gestion et la gestion des versions des ensembles de données adversaires sont documentées et contrôlées.                                                                                                                                             |   2   | D/V  |
| 1.9.3 | Vérifiez que l'impact de l'entraînement à la robustesse adversariale sur la performance du modèle (à la fois sur des entrées propres et adversariales) et sur les métriques d'équité est évalué, documenté et suivi.                                                                                                              |   3   | D/V  |
| 1.9.4 | Vérifiez que les stratégies d'entraînement adversarial et de robustesse sont régulièrement révisées et mises à jour pour contrer l'évolution des techniques d'attaque adversariale.                                                                                                                                               |   3   | D/V  |

---

## C1.10 Traçabilité et Trajectoire des Données

Suivez le parcours complet de chaque point de données depuis la source jusqu'à l'entrée du modèle pour assurer la traçabilité et la réponse aux incidents.

|   #    | Description                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.10.1 | Vérifiez que la traçabilité de chaque point de données, y compris toutes les transformations, augmentations et fusions, est enregistrée et peut être reconstruite. |   2   | D/V  |
| 1.10.2 | Vérifiez que les enregistrements de lignée sont immuables, stockés de manière sécurisée et accessibles pour les audits ou les enquêtes.                            |   2   | D/V  |
| 1.10.3 | Vérifiez que le suivi de la lignée couvre à la fois les données brutes et les données synthétiques.                                                                |   2   | D/V  |

---

## C1.11 Gestion des données synthétiques

Assurez-vous que les données synthétiques sont correctement gérées, étiquetées et évaluées en termes de risques.

|   #    | Description                                                                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Vérifiez que toutes les données synthétiques sont clairement étiquetées et distinguables des données réelles tout au long du pipeline.                                                                               |   2   | D/V  |
| 1.11.2 | Vérifiez que le processus de génération, les paramètres et l'utilisation prévue des données synthétiques sont documentés.                                                                                            |   2   | D/V  |
| 1.11.3 | Vérifiez que les données synthétiques ont fait l'objet d'une évaluation des risques concernant les biais, les fuites de confidentialité et les problèmes de représentation avant leur utilisation dans la formation. |   2   | D/V  |

---

## C1.12 Surveillance de l'accès aux données et détection des anomalies

Surveiller et alerter en cas d'accès inhabituel aux données d'entraînement afin de détecter les menaces internes ou l'exfiltration.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Vérifiez que tous les accès aux données d'entraînement sont enregistrés, y compris l'utilisateur, l'heure et l'action.                                                                |   2   | D/V  |
| 1.12.2 | Vérifiez que les journaux d'accès sont régulièrement examinés pour détecter des schémas inhabituels, tels que des exportations massives ou des accès depuis de nouveaux emplacements. |   2   | D/V  |
| 1.12.3 | Vérifiez que des alertes sont générées pour les événements d'accès suspects et qu'elles sont enquêtées rapidement.                                                                    |   2   | D/V  |

---

## C1.13 Politiques de conservation et d'expiration des données

Définir et appliquer des périodes de conservation des données afin de minimiser le stockage de données inutile.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.13.1 | Vérifiez que des périodes de conservation explicites sont définies pour tous les ensembles de données d'entraînement.                     |   1   | D/V  |
| 1.13.2 | Vérifiez que les ensembles de données sont automatiquement expirés, supprimés ou examinés pour suppression à la fin de leur cycle de vie. |   2   | D/V  |
| 1.13.3 | Vérifiez que les actions de conservation et de suppression sont enregistrées et auditées.                                                 |   2   | D/V  |

---

## C1.14 Conformité réglementaire et juridictionnelle

Assurez-vous que toutes les données d'entraînement sont conformes aux lois et réglementations en vigueur.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Vérifiez que les exigences en matière de résidence des données et de transfert transfrontalier sont identifiées et appliquées pour tous les ensembles de données. |   2   | D/V  |
| 1.14.2 | Vérifiez que les réglementations spécifiques à chaque secteur (par exemple, santé, finance) sont identifiées et prises en compte dans la gestion des données.     |   2   | D/V  |
| 1.14.3 | Vérifier que la conformité aux lois sur la protection de la vie privée pertinentes (par exemple, RGPD, CCPA) est documentée et revue régulièrement.               |   2   | D/V  |

---

## C1.15 Filigrane de données et empreinte numérique

Détecter la réutilisation non autorisée ou la fuite de données propriétaires ou sensibles.

|   #    | Description                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.15.1 | Vérifiez que les ensembles de données ou sous-ensembles sont filigranés ou dotés d'empreintes numériques lorsque cela est possible.    |   3   | D/V  |
| 1.15.2 | Vérifiez que les méthodes de filigrane/empreinte ne produisent pas de biais ni de risques pour la vie privée.                          |   3   | D/V  |
| 1.15.3 | Vérifiez que des contrôles périodiques sont effectués pour détecter toute réutilisation non autorisée ou fuite de données filigranées. |   3   | D/V  |

---

## C1.16 Gestion des droits des personnes concernées

Soutenir les droits des personnes concernées tels que l'accès, la rectification, la restriction et l'opposition.

|   #    | Description                                                                                                                                                               | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Vérifiez que des mécanismes existent pour répondre aux demandes des personnes concernées concernant l'accès, la rectification, la limitation ou l'opposition aux données. |   2   | D/V  |
| 1.16.2 | Vérifiez que les demandes sont enregistrées, suivies et satisfaites dans les délais légalement impartis.                                                                  |   2   | D/V  |
| 1.16.3 | Vérifier que les processus relatifs aux droits des personnes concernées sont testés et revus régulièrement pour en assurer l'efficacité.                                  |   2   | D/V  |

---

## C1.17 Analyse de l'impact des versions de jeux de données

Évaluez l'impact des modifications du jeu de données avant de mettre à jour ou de remplacer les versions.

|   #    | Description                                                                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Vérifiez qu'une analyse d'impact est réalisée avant de mettre à jour ou de remplacer une version de dataset, en couvrant la performance du modèle, l'équité et la conformité. |   2   | D/V  |
| 1.17.2 | Vérifier que les résultats de l'analyse d'impact sont documentés et examinés par les parties prenantes concernées.                                                            |   2   | D/V  |
| 1.17.3 | Vérifiez que des plans de retour arrière existent au cas où les nouvelles versions introduiraient des risques inacceptables ou des régressions.                               |   2   | D/V  |

---

## C1.18 Sécurité de la main-d'œuvre pour l'annotation des données

Assurer la sécurité et l'intégrité du personnel impliqué dans l'annotation des données.

|   #    | Description                                                                                                                                                                             | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Vérifiez que tout le personnel impliqué dans l'annotation des données a fait l'objet d'une vérification des antécédents et est formé à la sécurité et à la confidentialité des données. |   2   | D/V  |
| 1.18.2 | Vérifiez que tout le personnel d'annotation signe des accords de confidentialité et de non-divulgation.                                                                                 |   2   | D/V  |
| 1.18.3 | Vérifiez que les plateformes d'annotation appliquent des contrôles d'accès et surveillent les menaces internes.                                                                         |   2   | D/V  |

---

## Références

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)

