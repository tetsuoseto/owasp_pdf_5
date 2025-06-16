# C13 Supervision Humaine, Responsabilité et Gouvernance

## Objectif de contrôle

Ce chapitre fournit des exigences pour maintenir la supervision humaine et des chaînes de responsabilité claires dans les systèmes d'IA, garantissant l'explicabilité, la transparence et la gestion éthique tout au long du cycle de vie de l'IA.

---

## C13.1 Mécanismes d'arrêt d'urgence et de contournement

Fournir des procédures d'arrêt ou de retour en arrière lorsque des comportements non sécurisés du système d'IA sont observés.

|   #    | Description                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Vérifiez qu'un mécanisme d'interrupteur manuel existe pour arrêter immédiatement l'inférence et les sorties du modèle d'IA.   |   1   | D/V  |
| 13.1.2 | Vérifiez que les contrôles de remplacement sont accessibles uniquement au personnel autorisé.                                 |   1   |  D   |
| 13.1.3 | Vérifiez que les procédures de restauration peuvent revenir aux versions précédentes du modèle ou aux opérations en mode sûr. |   3   | D/V  |
| 13.1.4 | Vérifiez que les mécanismes de dérogation sont testés régulièrement.                                                          |   3   |  V   |

---

## C13.2 Points de contrôle de la décision avec intervention humaine

Exiger des approbations humaines lorsque les enjeux dépassent les seuils de risque prédéfinis.

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Vérifiez que les décisions AI à haut risque nécessitent une approbation humaine explicite avant leur exécution.                                                     |   1   | D/V  |
| 13.2.2 | Vérifiez que les seuils de risque sont clairement définis et déclenchent automatiquement des workflows de révision humaine.                                         |   1   |  D   |
| 13.2.3 | Vérifiez que les décisions sensibles au facteur temps disposent de procédures de secours lorsque l'approbation humaine ne peut être obtenue dans les délais requis. |   2   |  D   |
| 13.2.4 | Vérifiez que les procédures d'escalade définissent des niveaux d'autorité clairs pour les différents types de décisions ou catégories de risques, le cas échéant.   |   3   | D/V  |

---

## C13.3 Chaîne de Responsabilité et Auditabilité

Enregistrer les actions de l'opérateur et les décisions du modèle.

|   #    | Description                                                                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Vérifiez que toutes les décisions du système d'IA et les interventions humaines sont enregistrées avec des horodatages, les identités des utilisateurs et la justification des décisions. |   1   | D/V  |
| 13.3.2 | Vérifiez que les journaux d'audit ne peuvent pas être altérés et qu'ils incluent des mécanismes de vérification de l'intégrité.                                                           |   2   |  D   |

---

## C13.4 Techniques d'IA explicable

Importance des caractéristiques de surface, contre-factuels et explications locales.

|   #    | Description                                                                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Vérifiez que les systèmes d'IA fournissent des explications de base pour leurs décisions dans un format lisible par l'homme.                                                                 |   1   | D/V  |
| 13.4.2 | Vérifiez que la qualité des explications est validée par des études d'évaluation humaine et des métriques.                                                                                   |   2   |  V   |
| 13.4.3 | Vérifiez que les scores d'importance des caractéristiques ou les méthodes d'attribution (SHAP, LIME, etc.) sont disponibles pour les décisions critiques.                                    |   3   | D/V  |
| 13.4.4 | Vérifiez que les explications contrefactuelles montrent comment les entrées pourraient être modifiées pour changer les résultats, si cela est applicable au cas d'utilisation et au domaine. |   3   |  V   |

---

## C13.5 Fiches de modèle et divulgations d'utilisation

Maintenez des fiches de modèle pour l'utilisation prévue, les indicateurs de performance et les considérations éthiques.

|   #    | Description                                                                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Vérifiez que les fiches modèles documentent les cas d'utilisation prévus, les limitations et les modes d'échec connus.                                                                                                                                  |   1   |  D   |
| 13.5.2 | Vérifiez que les métriques de performance pour différents cas d'utilisation applicables sont divulguées.                                                                                                                                                |   1   | D/V  |
| 13.5.3 | Vérifiez que les considérations éthiques, les évaluations des biais, les évaluations de l'équité, les caractéristiques des données d'entraînement et les limitations connues des données d'entraînement sont documentées et mises à jour régulièrement. |   2   |  D   |
| 13.5.4 | Vérifiez que les fiches de modèle sont contrôlées par version et maintenues tout au long du cycle de vie du modèle avec un suivi des modifications.                                                                                                     |   2   | D/V  |

---

## C13.6 Quantification de l'incertitude

Propager les scores de confiance ou les mesures d'entropie dans les réponses.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Vérifiez que les systèmes d'IA fournissent des scores de confiance ou des mesures d'incertitude avec leurs résultats.              |   1   |  D   |
| 13.6.2 | Vérifiez que les seuils d'incertitude déclenchent un examen humain supplémentaire ou des voies décisionnelles alternatives.        |   2   | D/V  |
| 13.6.3 | Vérifiez que les méthodes de quantification de l'incertitude sont calibrées et validées par rapport aux données de vérité terrain. |   2   |  V   |
| 13.6.4 | Vérifiez que la propagation de l'incertitude est maintenue tout au long des flux de travail IA en plusieurs étapes.                |   3   | D/V  |

---

## C13.7 Rapports de Transparence Destinés aux Utilisateurs

Fournir des déclarations périodiques sur les incidents, les dérives et l'utilisation des données.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 13.7.1 | Vérifiez que les politiques d'utilisation des données et les pratiques de gestion du consentement des utilisateurs sont clairement communiquées aux parties prenantes.   |   1   | D/V  |
| 13.7.2 | Vérifiez que des évaluations de l'impact de l'IA sont réalisées et que les résultats sont inclus dans les rapports.                                                      |   2   | D/V  |
| 13.7.3 | Vérifiez que les rapports de transparence publiés régulièrement dévoilent les incidents liés à l'IA et les mesures opérationnelles avec un niveau de détail raisonnable. |   2   | D/V  |

### Références

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)

