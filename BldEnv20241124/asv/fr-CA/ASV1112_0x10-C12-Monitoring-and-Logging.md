# C12 Surveillance, journalisation et détection d'anomalies

## Objectif de contrôle

Cette section fournit les exigences pour assurer une visibilité en temps réel et médico-légale sur ce que le modèle et les autres composants d'IA voient, font et renvoient, afin que les menaces puissent être détectées, triées et analysées.

## C12.1 Enregistrement des Requêtes et Réponses

|   #    | Description                                                                                                                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Vérifiez que toutes les invites utilisateur et toutes les réponses du modèle sont enregistrées avec les métadonnées appropriées (par exemple, horodatage, ID utilisateur, ID de session, version du modèle).                                                                                   |   1   | D/V  |
| 12.1.2 | Vérifiez que les journaux sont stockés dans des référentiels sécurisés et accessibles avec des politiques de rétention appropriées et des procédures de sauvegarde.                                                                                                                            |   1   | D/V  |
| 12.1.3 | Vérifiez que les systèmes de stockage des journaux mettent en œuvre un chiffrement au repos et en transit pour protéger les informations sensibles contenues dans les journaux.                                                                                                                |   1   | D/V  |
| 12.1.4 | Vérifiez que les données sensibles dans les invites et les résultats sont automatiquement redigées ou masquées avant la journalisation, avec des règles de redaction configurables pour les informations personnelles identifiables (IPI), les identifiants et les informations propriétaires. |   1   | D/V  |
| 12.1.5 | Vérifiez que les décisions politiques et les actions de filtrage de sécurité sont enregistrées avec suffisamment de détails pour permettre l'audit et le débogage des systèmes de modération de contenu.                                                                                       |   2   | D/V  |
| 12.1.6 | Vérifiez que l’intégrité des journaux est protégée, par exemple par des signatures cryptographiques ou un stockage en écriture seule.                                                                                                                                                          |   2   | D/V  |

---

## C12.2 Détection des abus et alertes

|   #    | Description                                                                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Vérifiez que le système détecte et alerte sur les schémas de contournement connus, les tentatives d'injection de prompt et les entrées adversariales en utilisant une détection basée sur les signatures.                                    |   1   | D/V  |
| 12.2.2 | Vérifiez que le système s'intègre aux plateformes existantes de Gestion des Informations et des Événements de Sécurité (SIEM) en utilisant des formats de journaux et des protocoles standards.                                              |   1   | D/V  |
| 12.2.3 | Vérifiez que les événements de sécurité enrichis incluent un contexte spécifique à l'IA, tel que les identifiants de modèle, les scores de confiance et les décisions des filtres de sécurité.                                               |   2   | D/V  |
| 12.2.4 | Vérifiez que la détection d'anomalies comportementales identifie les schémas de conversation inhabituels, les tentatives de réessai excessives ou les comportements de sondage systématiques.                                                |   2   | D/V  |
| 12.2.5 | Vérifiez que les mécanismes d’alerte en temps réel notifient les équipes de sécurité lorsque des violations potentielles de la politique ou des tentatives d’attaque sont détectées.                                                         |   2   | D/V  |
| 12.2.6 | Vérifiez que des règles personnalisées sont incluses pour détecter les modèles de menaces spécifiques à l'IA, notamment les tentatives coordonnées de jailbreak, les campagnes d'injection de prompt et les attaques d'extraction de modèle. |   2   | D/V  |
| 12.2.7 | Vérifiez que les flux de travail automatisés de réponse aux incidents peuvent isoler les modèles compromis, bloquer les utilisateurs malveillants et escalader les événements de sécurité critiques.                                         |   3   | D/V  |

---

## C12.3 Détection de la dérive du modèle

|   #    | Description                                                                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.3.1 | Vérifiez que le système suit les mesures de performance de base telles que la précision, les scores de confiance, la latence et les taux d'erreur à travers les versions du modèle et les périodes de temps. |   1   | D/V  |
| 12.3.2 | Vérifiez que les alertes automatisées se déclenchent lorsque les métriques de performance dépassent les seuils de dégradation prédéfinis ou s'écartent significativement des valeurs de référence.           |   2   | D/V  |
| 12.3.3 | Vérifiez que les systèmes de détection d’hallucinations identifient et signalent les cas où les sorties du modèle contiennent des informations factuellement incorrectes, incohérentes ou fabriquées.        |   2   | D/V  |

---

## C12.4 Télémétrie des performances et du comportement

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Vérifiez que les métriques opérationnelles, y compris la latence des requêtes, la consommation de jetons, l'utilisation de la mémoire et le débit, sont continuellement collectées et surveillées.      |   1   | D/V  |
| 12.4.2 | Vérifiez que les taux de réussite et d'échec sont suivis avec une catégorisation des types d'erreurs et de leurs causes profondes.                                                                      |   1   | D/V  |
| 12.4.3 | Vérifiez que la surveillance de l'utilisation des ressources inclut l'utilisation du GPU/CPU, la consommation de mémoire et les besoins en stockage, avec des alertes en cas de dépassement des seuils. |   2   | D/V  |

---

## C12.5 Planification et exécution de la réponse aux incidents d'IA

|   #    | Description                                                                                                                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Vérifiez que les plans de réponse aux incidents traitent spécifiquement des événements de sécurité liés à l'IA, y compris la compromission de modèles, l'empoisonnement des données et les attaques adversariales. |   1   | D/V  |
| 12.5.2 | Vérifiez que les équipes de réponse aux incidents ont accès à des outils judiciaires spécifiques à l'IA et à une expertise pour enquêter sur le comportement des modèles et les vecteurs d'attaque.                |   2   | D/V  |
| 12.5.3 | Vérifiez que l'analyse post-incident inclut les considérations de réentraînement du modèle, les mises à jour des filtres de sécurité et l'intégration des leçons apprises dans les contrôles de sécurité.          |   3   | D/V  |

---

## C12.5 Détection de la dégradation des performances de l'IA

Surveiller et détecter la dégradation des performances et de la qualité du modèle d'IA au fil du temps.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.5.1 | Vérifiez que la précision, la exactitude, le rappel et les scores F1 du modèle sont continuellement suivis et comparés aux seuils de référence.                                            |   1   | D/V  |
| 12.5.2 | Vérifiez que la détection de dérive des données surveille les changements dans la distribution des entrées pouvant affecter les performances du modèle.                                    |   1   | D/V  |
| 12.5.3 | Vérifiez que la détection de la dérive de concept identifie les changements dans la relation entre les entrées et les sorties attendues.                                                   |   2   | D/V  |
| 12.5.4 | Vérifiez que la dégradation des performances déclenche des alertes automatisées et initie les workflows de réentraînement ou de remplacement du modèle.                                    |   2   | D/V  |
| 12.5.5 | Vérifiez que l'analyse des causes profondes de la dégradation corrèle les baisses de performance avec les changements de données, les problèmes d'infrastructure ou les facteurs externes. |   3   |  V   |

---

## C12.6 Visualisation du DAG et Sécurité du Flux de Travail

Protéger les systèmes de visualisation des flux de travail contre les fuites d'informations et les attaques de manipulation.

|   #    | Description                                                                                                                                                                                          | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Vérifiez que les données de visualisation du DAG sont nettoyées pour supprimer les informations sensibles avant le stockage ou la transmission.                                                      |   1   | D/V  |
| 12.6.2 | Vérifiez que les contrôles d'accès à la visualisation des workflows garantissent que seuls les utilisateurs autorisés peuvent voir les chemins de décision des agents et les traces de raisonnement. |   1   | D/V  |
| 12.6.3 | Vérifiez que l'intégrité des données du DAG est protégée par des signatures cryptographiques et des mécanismes de stockage infalsifiables.                                                           |   2   | D/V  |
| 12.6.4 | Vérifiez que les systèmes de visualisation de flux de travail mettent en œuvre une validation des entrées pour prévenir les attaques par injection via des données de nœud ou d’arête façonnées.     |   2   | D/V  |
| 12.6.5 | Vérifiez que les mises à jour en temps réel des DAG sont soumises à une limitation de débit et validées pour prévenir les attaques par déni de service sur les systèmes de visualisation.            |   3   | D/V  |

---

## C12.7 Surveillance proactive du comportement en matière de sécurité

Détection et prévention des menaces de sécurité par l'analyse proactive du comportement des agents.

|   #    | Description                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 12.7.1 | Vérifiez que les comportements des agents proactifs sont validés en matière de sécurité avant exécution, avec intégration de l’évaluation des risques.       |   1   | D/V  |
| 12.7.2 | Vérifiez que les déclencheurs d'initiative autonome incluent l'évaluation du contexte de sécurité et l'analyse du paysage des menaces.                       |   2   | D/V  |
| 12.7.3 | Vérifiez que les schémas de comportement proactif sont analysés pour leurs implications potentielles en matière de sécurité et leurs conséquences imprévues. |   2   | D/V  |
| 12.7.4 | Vérifiez que les actions proactives critiques pour la sécurité nécessitent des chaînes d'approbation explicites avec des pistes d'audit.                     |   3   | D/V  |
| 12.7.5 | Vérifiez que la détection d'anomalies comportementales identifie les écarts dans les schémas des agents proactifs pouvant indiquer une compromission.        |   3   | D/V  |

---

## Références

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)

