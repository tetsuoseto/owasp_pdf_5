# 10 Robustesse Adversariale et Défense de la Vie Privée

## Objectif de contrôle

Assurez-vous que les modèles d'IA restent fiables, préservent la vie privée et résistent aux abus lorsqu'ils font face à des attaques d'évasion, d'inférence, d'extraction ou d'empoisonnement.

---

## 10.1 Alignement et sécurité des modèles

Se prémunir contre les résultats nuisibles ou en violation des politiques.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Vérifiez qu'une suite de tests d'alignement (prompts de red-team, sondes de jailbreak, contenu interdit) est sous contrôle de version et exécutée à chaque nouvelle version du modèle. |   1   | D/V  |
| 10.1.2 | Vérifiez que les dispositifs de refus et de complétion sécurisée sont appliqués.                                                                                                       |   1   |  D   |
| 10.1.3 | Vérifiez qu'un évaluateur automatisé mesure le taux de contenu nuisible et signale les régressions dépassant un seuil défini.                                                          |   2   | D/V  |
| 10.1.4 | Vérifiez que la formation contre les contournements de sécurité est documentée et reproductible.                                                                                       |   2   |  D   |
| 10.1.5 | Vérifiez que les preuves formelles de conformité aux politiques ou la surveillance certifiée couvrent les domaines critiques.                                                          |   3   |  V   |

---

## 10.2 Renforcement contre les exemples adverses

Augmenter la résilience aux entrées manipulées. L'entraînement adversarial robuste et l'évaluation par benchmarking sont les meilleures pratiques actuelles.

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Vérifiez que les dépôts du projet incluent des configurations d'entraînement adversarial avec des graines reproductibles.                       |   1   |  D   |
| 10.2.2 | Vérifiez que la détection des exemples adverses génère des alertes de blocage dans les chaînes de production.                                   |   2   | D/V  |
| 10.2.4 | Vérifiez que les preuves de robustesse certifiée ou les certificats de bornes d'intervalle couvrent au moins les classes critiques principales. |   3   |  V   |
| 10.2.5 | Vérifiez que les tests de régression utilisent des attaques adaptatives pour confirmer qu'il n'y a aucune perte de robustesse mesurable.        |   3   |  V   |

---

## 10.3 Atténuation de l’inférence d’appartenance

Limiter la capacité à déterminer si un enregistrement faisait partie des données d'entraînement. La confidentialité différentielle et le masquage des scores de confiance restent les défenses connues les plus efficaces.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.3.1 | Vérifiez que la régularisation de l'entropie par requête ou la mise à l'échelle de la température réduit les prédictions trop confiantes. |   1   |  D   |
| 10.3.2 | Vérifiez que l'entraînement utilise une optimisation différentiellement privée bornée par ε pour les ensembles de données sensibles.      |   2   |  D   |
| 10.3.3 | Vérifiez que les simulations d'attaque (modèle miroir ou boîte noire) montrent une AUC d'attaque ≤ 0,60 sur les données mises de côté.    |   2   |  V   |

---

## 10.4 Résistance à l'inversion de modèle

Empêcher la reconstruction des attributs privés. Des enquêtes récentes soulignent la troncature de sortie et les garanties de confidentialité différentielle (DP) comme des défenses pratiques.

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Vérifiez que les attributs sensibles ne sont jamais directement affichés ; lorsque cela est nécessaire, utilisez des catégories ou des transformations à sens unique. |   1   |  D   |
| 10.4.2 | Vérifiez que les limites de taux de requêtes restreignent les requêtes adaptatives répétées provenant du même principal.                                              |   1   | D/V  |
| 10.4.3 | Vérifiez que le modèle est entraîné avec un bruit préservant la confidentialité.                                                                                      |   2   |  D   |

---

## 10.5 Défense contre l'extraction de modèle

Détecter et dissuader la duplication non autorisée. Il est recommandé d'utiliser le filigrane et l'analyse des modèles de requêtes.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Vérifiez que les passerelles d'inférence appliquent des limites de débit globales et par clé API adaptées au seuil de mémorisation du modèle.             |   1   |  D   |
| 10.5.2 | Vérifiez que les statistiques d'entropie de requête et de pluralité d'entrée alimentent un détecteur d'extraction automatisée.                            |   2   | D/V  |
| 10.5.3 | Vérifiez que les filigranes fragiles ou probabilistes peuvent être prouvés avec p < 0,01 en ≤ 1 000 requêtes contre un clone suspect.                     |   2   |  V   |
| 10.5.4 | Vérifiez que les clés de tatouage numérique et les ensembles de déclencheurs sont stockés dans un module de sécurité matériel et renouvelés chaque année. |   3   |  D   |
| 10.5.5 | Vérifiez que les événements d’alerte d’extraction incluent les requêtes incriminées et sont intégrés aux plans d’intervention en cas d’incident.          |   3   |  V   |

---

## 10.6 Détection de données empoisonnées au moment de l'inférence

Identifier et neutraliser les entrées contenant une porte dérobée ou empoisonnées.

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.6.1 | Vérifiez que les entrées passent par un détecteur d'anomalies (par exemple, STRIP, scoring de cohérence) avant l'inférence du modèle.                  |   1   |  D   |
| 10.6.2 | Vérifiez que les seuils du détecteur sont ajustés sur des ensembles de validation propres/empoisonnés afin d’obtenir moins de 5 % de faux positifs.    |   1   |  V   |
| 10.6.3 | Vérifiez que les entrées signalées comme empoisonnées déclenchent le blocage doux et les processus de révision humaine.                                |   2   |  D   |
| 10.6.4 | Vérifiez que les détecteurs sont soumis à des tests de résistance avec des attaques de porte dérobée adaptatives et sans déclencheur.                  |   2   |  V   |
| 10.6.5 | Vérifiez que les métriques d'efficacité de détection sont enregistrées et réévaluées périodiquement avec des informations sur les menaces actualisées. |   3   |  D   |

---

## 10.7 Adaptation dynamique de la politique de sécurité

Mises à jour en temps réel des politiques de sécurité basées sur le renseignement sur les menaces et l'analyse comportementale.

|   #    | Description                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Vérifiez que les politiques de sécurité peuvent être mises à jour dynamiquement sans redémarrage de l'agent tout en maintenant l'intégrité de la version des politiques.                                   |   1   | D/V  |
| 10.7.2 | Vérifiez que les mises à jour des politiques sont signées cryptographiquement par le personnel de sécurité autorisé et validées avant leur application.                                                    |   2   | D/V  |
| 10.7.3 | Vérifiez que les modifications dynamiques de la politique sont enregistrées avec des pistes d'audit complètes incluant la justification, les chaînes d'approbation et les procédures de retour en arrière. |   2   | D/V  |
| 10.7.4 | Vérifiez que les mécanismes de sécurité adaptatifs ajustent la sensibilité de la détection des menaces en fonction du contexte de risque et des schémas comportementaux.                                   |   3   | D/V  |
| 10.7.5 | Vérifiez que les décisions d'adaptation de la politique sont explicables et incluent des pistes de preuve pour la révision par l'équipe de sécurité.                                                       |   3   | D/V  |

---

## 10.8 Analyse de sécurité basée sur la réflexion

Validation de la sécurité par auto-réflexion de l'agent et analyse métacognitive.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Vérifiez que les mécanismes de réflexion des agents incluent une auto-évaluation axée sur la sécurité des décisions et des actions.                                     |   1   | D/V  |
| 10.8.2 | Vérifiez que les résultats de la réflexion sont validés afin d'empêcher la manipulation des mécanismes d'auto-évaluation par des entrées adverses.                      |   2   | D/V  |
| 10.8.3 | Vérifiez que l'analyse de sécurité métacognitive identifie les biais potentiels, les manipulations ou les compromissions dans les processus de raisonnement de l'agent. |   2   | D/V  |
| 10.8.4 | Vérifiez que les avertissements de sécurité basés sur la réflexion déclenchent une surveillance renforcée et d'éventuels flux de travail d'intervention humaine.        |   3   | D/V  |
| 10.8.5 | Vérifiez que l'apprentissage continu à partir des réflexions sur la sécurité améliore la détection des menaces sans dégrader la fonctionnalité légitime.                |   3   | D/V  |

---

## 10.9 Sécurité de l’évolution et de l’auto-amélioration

Contrôles de sécurité pour les systèmes d'agents capables d'auto-modification et d'évolution.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Vérifiez que les capacités d'auto-modification sont limitées aux zones sûres désignées avec des frontières de vérification formelle.              |   1   | D/V  |
| 10.9.2 | Vérifiez que les propositions d'évolution font l'objet d'une évaluation de l'impact sur la sécurité avant leur mise en œuvre.                     |   2   | D/V  |
| 10.9.3 | Vérifiez que les mécanismes d'auto-amélioration incluent des capacités de retour en arrière avec vérification de l'intégrité.                     |   2   | D/V  |
| 10.9.4 | Vérifiez que la sécurité de la méta-apprentissage empêche la manipulation adversaire des algorithmes d'amélioration.                              |   3   | D/V  |
| 10.9.5 | Vérifiez que l'amélioration récursive de soi est limitée par des contraintes formelles de sécurité avec des preuves mathématiques de convergence. |   3   | D/V  |

---

### Références

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)

