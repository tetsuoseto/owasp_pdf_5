# Validation des entrées utilisateur C2

## Objectif de contrôle

Une validation rigoureuse des entrées utilisateur constitue une première ligne de défense contre certaines des attaques les plus dommageables sur les systèmes d'IA. Les attaques par injection de prompt peuvent contourner les instructions du système, divulguer des données sensibles ou orienter le modèle vers un comportement non autorisé. À moins que des filtres dédiés et des hiérarchies d'instructions ne soient en place, les recherches montrent que les "multi-shot" jailbreaks exploitant des fenêtres de contexte très longues seront efficaces. De plus, des attaques adversariales subtiles par perturbation — telles que les substitutions homoglyphes ou le leetspeak — peuvent modifier silencieusement les décisions d’un modèle.

---

## C2.1 Défense contre l'injection de requêtes

L'injection de requêtes est l'un des principaux risques pour les systèmes d'IA. Les défenses contre cette tactique utilisent une combinaison de filtres de motifs statiques, de classificateurs dynamiques et de l'application d'une hiérarchie d'instructions.

|   #   | Description                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.1.1 | Vérifiez que les entrées utilisateur sont filtrées par rapport à une bibliothèque continuellement mise à jour de modèles connus d'injection d'instructions (mots-clés de jailbreak, « ignorer les instructions précédentes », chaînes de jeu de rôle, attaques indirectes via HTML/URL). |   1   | D/V  |
| 2.1.2 | Vérifiez que le système applique une hiérarchie d'instructions dans laquelle les messages du système ou du développeur prévalent sur les instructions de l'utilisateur, même après l'extension de la fenêtre de contexte.                                                                |   1   | D/V  |
| 2.1.3 | Vérifiez que les tests d'évaluation adversariale (par exemple, les invites "many-shot" de l'équipe rouge) sont exécutés avant chaque publication de modèle ou de modèle d'invite, avec des seuils de taux de réussite et des bloqueurs automatisés pour les régressions.                 |   2   | D/V  |
| 2.1.4 | Vérifiez que les invites provenant de contenus tiers (pages web, fichiers PDF, e-mails) sont nettoyées dans un contexte de parse isolé avant d’être concaténées dans l’invite principale.                                                                                                |   2   |  D   |
| 2.1.5 | Vérifiez que toutes les mises à jour des règles de filtrage des prompts, les versions des modèles de classificateurs et les modifications des listes de blocage sont sous contrôle de version et auditables.                                                                             |   3   | D/V  |

---

## C2.2 Résistance aux exemples adversariaux

Les modèles de Traitement Automatique du Langage Naturel (TAL) restent vulnérables aux perturbations subtiles au niveau des caractères ou des mots que les humains ne remarquent souvent pas, mais que les modèles ont tendance à mal classifier.

|   #   | Description                                                                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Vérifiez que les étapes de normalisation de base des entrées (NFC Unicode, mappage des homoglyphes, suppression des espaces blancs) sont effectuées avant la tokenisation.                                                                                      |   1   |  D   |
| 2.2.2 | Vérifiez que la détection d'anomalies statistiques identifie les entrées présentant une distance d'édition anormalement élevée par rapport aux normes linguistiques, des tokens répétés en excès ou des distances d'embedding anormales.                        |   2   | D/V  |
| 2.2.3 | Vérifiez que la chaîne d'inférence prend en charge des variantes de modèles renforcés par entraînement adversarial optionnel ou des couches de défense (par exemple, la randomisation, la distillation défensive) pour les points de terminaison à haut risque. |   2   |  D   |
| 2.2.4 | Vérifiez que les entrées suspectées d'être adversariales sont mises en quarantaine, enregistrées avec la charge utile complète (après la suppression des informations personnelles identifiables).                                                              |   2   |  V   |
| 2.2.5 | Vérifiez que les métriques de robustesse (taux de réussite des suites d'attaques connues) sont suivies dans le temps et que les régressions déclenchent un blocage de publication.                                                                              |   3   | D/V  |

---

## C2.3 Validation du schéma, du type et de la longueur

Les attaques d'IA utilisant des entrées malformées ou surdimensionnées peuvent provoquer des erreurs de parsing, des débordements de prompt entre les champs et une épuisement des ressources. Une application stricte du schéma est également une condition préalable lors de l'exécution d'appels d'outils déterministes.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Vérifiez que chaque point d'appel d'API ou de fonction définit un schéma d'entrée explicite (schéma JSON, Protobuf ou équivalent multimodal) et que les entrées sont validées avant l'assemblage de la requête. |   1   |  D   |
| 2.3.2 | Vérifiez que les entrées dépassant les limites maximales de jetons ou d'octets sont rejetées avec une erreur sécurisée et ne sont jamais tronquées silencieusement.                                             |   1   | D/V  |
| 2.3.3 | Vérifiez que les contrôles de type (par exemple, les plages numériques, les valeurs d’énumération, les types MIME pour les images/audio) sont appliqués côté serveur, et pas seulement dans le code client.     |   2   | D/V  |
| 2.3.4 | Vérifiez que les validateurs sémantiques (par exemple, JSON Schema) s'exécutent en temps constant pour prévenir les attaques par déni de service algorithmique (DoS).                                           |   2   |  D   |
| 2.3.5 | Vérifiez que les échecs de validation sont enregistrés avec des extraits de charge utile expurgés et des codes d'erreur non ambigus pour faciliter le triage de la sécurité.                                    |   3   |  V   |

---

## C2.4 Filtrage de contenu et de politique

Les développeurs doivent être capables de détecter les invites syntaxiquement valides qui demandent un contenu interdit (comme des instructions illicites, des discours haineux et des textes protégés par des droits d'auteur), puis empêcher leur propagation.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.4.1 | Vérifiez qu'un classificateur de contenu (zero shot ou affiné) évalue chaque entrée pour la violence, l'automutilation, la haine, le contenu sexuel et les demandes illégales, avec des seuils configurables.                             |   1   |  D   |
| 2.4.2 | Vérifiez que les entrées qui enfreignent les politiques recevront des refus standardisés ou des complétions sécurisées afin qu'elles ne se propagent pas aux appels LLM en aval.                                                          |   1   | D/V  |
| 2.4.3 | Vérifiez que le modèle de filtrage ou l'ensemble de règles est réentraîné/mis à jour au moins une fois par trimestre, en intégrant les nouveaux schémas de contournement de sécurité ou de contournement de politique récemment observés. |   2   |  D   |
| 2.4.4 | Vérifiez que le filtrage respecte les politiques spécifiques à l’utilisateur (âge, contraintes légales régionales) via des règles basées sur les attributs résolues au moment de la requête.                                              |   2   |  D   |
| 2.4.5 | Vérifiez que les journaux de contrôle incluent les scores de confiance du classificateur et les étiquettes de catégorie de politique pour la corrélation SOC et la relecture future par l’équipe rouge.                                   |   3   |  V   |

---

## C2.5 Limitation du débit d'entrée et prévention des abus

Les développeurs doivent prévenir les abus, l'épuisement des ressources et les attaques automatisées contre les systèmes d'IA en limitant les taux d'entrée et en détectant les schémas d'utilisation anormaux.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.5.1 | Vérifiez que les limites de taux par utilisateur, par adresse IP et par clé API sont appliquées pour tous les points d'entrée des données.                               |   1   | D/V  |
| 2.5.2 | Vérifiez que les limites de taux de rafale et soutenues sont ajustées pour prévenir les attaques par déni de service (DoS) et par force brute.                           |   2   | D/V  |
| 2.5.3 | Vérifiez que les schémas d'utilisation anormaux (par exemple, les requêtes en rafale, le bombardement d'entrées) déclenchent des blocages automatiques ou des escalades. |   2   | D/V  |
| 2.5.4 | Vérifiez que les journaux de prévention des abus sont conservés et examinés pour détecter les schémas d'attaque émergents.                                               |   3   |  V   |

---

## C2.6 Validation d'entrée multi-modale

Les systèmes d'IA doivent inclure une validation robuste des entrées non textuelles (images, audio, fichiers) pour prévenir les injections, l'évasion ou l'abus de ressources.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Vérifiez que toutes les entrées non textuelles (images, audio, fichiers) sont validées en ce qui concerne le type, la taille et le format avant leur traitement. |   1   |  D   |
| 2.6.2 | Vérifiez que les fichiers sont analysés pour détecter les logiciels malveillants et les charges utiles stéganographiques avant l'ingestion.                      |   2   | D/V  |
| 2.6.3 | Vérifiez que les entrées image/audio sont contrôlées pour détecter les perturbations adversariales ou les modèles d'attaques connus.                             |   2   | D/V  |
| 2.6.4 | Vérifiez que les échecs de validation des entrées multimodales sont enregistrés et déclenchent des alertes pour enquête.                                         |   3   |  V   |

---

## C2.7 Provenance et attribution des données d’entrée

Les systèmes d'IA devraient prendre en charge l'audit, le suivi des abus et la conformité en surveillant et en étiquetant les origines de toutes les entrées utilisateur.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.7.1 | Vérifiez que toutes les entrées utilisateur sont étiquetées avec des métadonnées (ID utilisateur, session, source, horodatage, adresse IP) lors de l’ingestion. |   1   | D/V  |
| 2.7.2 | Vérifiez que les métadonnées de provenance sont conservées et auditables pour toutes les entrées traitées.                                                      |   2   | D/V  |
| 2.7.3 | Vérifiez que les sources d'entrée anormales ou non fiables sont signalées et soumises à un examen approfondi ou à un blocage.                                   |   2   | D/V  |

---

## C2.8 Détection adaptative des menaces en temps réel

Les développeurs doivent utiliser des systèmes de détection avancée des menaces pour l'IA qui s'adaptent aux nouveaux schémas d'attaque et offrent une protection en temps réel grâce à la correspondance de motifs compilés.

|   #   | Description                                                                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.8.1 | Vérifiez que les modèles de détection de menaces sont compilés dans des moteurs regex optimisés pour un filtrage en temps réel haute performance avec un impact minimal sur la latence.                                              |   1   | D/V  |
| 2.8.2 | Vérifiez que les systèmes de détection de menaces maintiennent des bibliothèques de modèles distinctes pour différentes catégories de menaces (injection de prompt, contenu nuisible, données sensibles, commandes système).         |   1   | D/V  |
| 2.8.3 | Vérifiez que la détection adaptative des menaces intègre des modèles d'apprentissage automatique qui ajustent la sensibilité aux menaces en fonction de la fréquence des attaques et des taux de réussite.                           |   2   | D/V  |
| 2.8.4 | Vérifiez que les flux d’informations sur les menaces en temps réel mettent automatiquement à jour les bibliothèques de modèles avec de nouvelles signatures d’attaque et des IOC (Indicateurs de Compromission).                     |   2   | D/V  |
| 2.8.5 | Vérifiez que les taux de faux positifs de détection des menaces sont continuellement surveillés et que la spécificité des modèles est automatiquement ajustée pour minimiser les interférences avec les cas d'utilisation légitimes. |   3   | D/V  |
| 2.8.6 | Vérifiez que l'analyse contextuelle des menaces prend en compte la source d'entrée, les modèles de comportement utilisateur et l'historique des sessions afin d'améliorer la précision de la détection.                              |   3   | D/V  |
| 2.8.7 | Vérifiez que les métriques de performance de détection des menaces (taux de détection, latence de traitement, utilisation des ressources) sont surveillées et optimisées en temps réel.                                              |   3   | D/V  |

---

## C2.9 Pipeline de Validation de Sécurité Multi-Modal

Les développeurs devraient fournir une validation de sécurité pour les modalités d'entrée AI telles que le texte, l'image, l'audio et autres, en intégrant des types spécifiques de détection de menaces et d'isolation des ressources.

|   #   | Description                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Vérifiez que chaque modalité d'entrée dispose de validateurs de sécurité dédiés avec des schémas de menaces documentés (texte : injection de commande, images : stéganographie, audio : attaques par spectrogramme) et des seuils de détection.                                                                        |   1   | D/V  |
| 2.9.2 | Vérifiez que les entrées multimodales sont traitées dans des environnements isolés (sandboxes) avec des limites de ressources définies (mémoire, CPU, temps de traitement) spécifiques à chaque type de modalité et documentées dans les politiques de sécurité.                                                       |   2   | D/V  |
| 2.9.3 | Vérifiez que la détection des attaques cross-modales identifie les attaques coordonnées s'étendant sur plusieurs types d'entrée (par exemple, des charges utiles stéganographiques dans des images combinées à des injections de prompt dans le texte) grâce à des règles de corrélation et à la génération d'alertes. |   2   | D/V  |
| 2.9.4 | Vérifiez que les échecs de validation multimodale déclenchent une journalisation détaillée incluant toutes les modalités d'entrée, les résultats de validation, les scores de menace et l'analyse de corrélation avec des formats de journalisation structurés pour l'intégration SIEM.                                |   3   | D/V  |
| 2.9.5 | Vérifiez que les classificateurs de contenu spécifiques à la modalité sont mis à jour conformément aux calendriers documentés (au minimum trimestriellement) avec de nouveaux schémas de menace, des exemples adverses, et que les performances restent supérieures aux seuils de référence.                           |   3   | D/V  |

---

## Références

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)

