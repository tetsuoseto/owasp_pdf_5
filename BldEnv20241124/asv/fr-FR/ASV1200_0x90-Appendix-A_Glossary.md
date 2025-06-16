# Annexe A : Glossaire

> Ce glossaire complet fournit des définitions des termes clés de l’IA, de l’AM et de la sécurité utilisés tout au long de l’AISVS afin d’assurer clarté et compréhension commune.
> ​
* Exemple d'adversaire : Une entrée délibérément conçue pour amener un modèle d'IA à commettre une erreur, souvent en ajoutant des perturbations subtiles imperceptibles pour les humains.
  ​
* Robustesse adversariale – La robustesse adversariale en IA désigne la capacité d'un modèle à maintenir ses performances et à résister aux tentatives de manipulation ou de tromperie par des entrées malveillantes spécifiquement conçues pour provoquer des erreurs.
  ​
* Agent – Les agents d'intelligence artificielle sont des systèmes logiciels qui utilisent l'IA pour poursuivre des objectifs et accomplir des tâches au nom des utilisateurs. Ils démontrent des capacités de raisonnement, de planification et de mémoire, et disposent d'un certain niveau d'autonomie pour prendre des décisions, apprendre et s'adapter.
  ​
* IA agentique : Systèmes d'IA capables de fonctionner avec un certain degré d'autonomie pour atteindre des objectifs, prenant souvent des décisions et agissant sans intervention humaine directe.
  ​
* Contrôle d'accès basé sur les attributs (ABAC) : un paradigme de contrôle d'accès où les décisions d'autorisation sont basées sur les attributs de l'utilisateur, de la ressource, de l'action et de l'environnement, évalués au moment de la requête.
  ​
* Attaque par porte dérobée : un type d'attaque par empoisonnement de données où le modèle est entraîné à répondre d'une manière spécifique à certains déclencheurs tout en se comportant normalement dans les autres cas.
  ​
* Biais : erreurs systématiques dans les résultats des modèles d'IA qui peuvent entraîner des résultats injustes ou discriminatoires pour certains groupes ou dans des contextes spécifiques.
  ​
* Exploitation des biais : une technique d'attaque qui profite des biais connus dans les modèles d'IA pour manipuler les résultats ou les issues.
  ​
* Cedar : langage et moteur de politique d'Amazon pour des autorisations fines, utilisé dans la mise en œuvre de l'ABAC pour les systèmes d'IA.
  ​
* Chaîne de raisonnement : une technique pour améliorer le raisonnement dans les modèles de langage en générant des étapes intermédiaires de raisonnement avant de produire une réponse finale.
  ​
* Disjoncteurs : Mécanismes qui arrêtent automatiquement les opérations du système d'IA lorsque des seuils de risque spécifiques sont dépassés.
  ​
* Fuite de données : exposition involontaire d'informations sensibles à travers les résultats ou le comportement d'un modèle d'IA.
  ​
* Empoisonnement des données : la corruption délibérée des données d'entraînement afin de compromettre l'intégrité du modèle, souvent pour installer des portes dérobées ou dégrader les performances.
  ​
* Confidentialité différentielle – La confidentialité différentielle est un cadre mathématiquement rigoureux pour la publication d'informations statistiques sur des ensembles de données tout en protégeant la vie privée des individus concernés. Elle permet au détenteur des données de partager des tendances globales du groupe tout en limitant les informations divulguées sur des individus spécifiques.
  ​
* Représentations vectorielles denses de données (texte, images, etc.) capturant le sens sémantique dans un espace de haute dimension.
  ​
* Explicabilité – L'explicabilité en IA est la capacité d'un système d'IA à fournir des raisons compréhensibles par l'humain pour ses décisions et prédictions, offrant des éclaircissements sur son fonctionnement interne.
  ​
* IA explicable (XAI) : systèmes d'IA conçus pour fournir des explications compréhensibles par l'humain sur leurs décisions et comportements à travers diverses techniques et cadres.
  ​
* Apprentissage Fédéré : une approche d'apprentissage automatique où les modèles sont entraînés sur plusieurs dispositifs décentralisés contenant des échantillons de données locales, sans échanger les données elles-mêmes.
  ​
* Garde-fous : Contraintes mises en place pour empêcher les systèmes d'IA de produire des résultats nuisibles, biaisés ou indésirables.
  ​
* Hallucination – Une hallucination d'IA fait référence à un phénomène où un modèle d'IA génère des informations incorrectes ou trompeuses qui ne sont pas basées sur ses données d'entraînement ou la réalité factuelle.
  ​
* Interaction humaine dans la boucle (HITL) : Systèmes conçus pour nécessiter une supervision, une vérification ou une intervention humaine à des points de décision cruciaux.
  ​
* Infrastructure as Code (IaC) : Gérer et provisionner l'infrastructure via du code plutôt que par des processus manuels, permettant ainsi le scan de sécurité et des déploiements cohérents.
  ​
* Jailbreak : Techniques utilisées pour contourner les garde-fous de sécurité dans les systèmes d'IA, en particulier dans les grands modèles de langage, afin de produire du contenu interdit.
  ​
* Moindre privilège : Le principe de sécurité consistant à accorder uniquement les droits d'accès minimaux nécessaires aux utilisateurs et aux processus.
  ​
* LIME (Explications Locales Interprétables et Modèle-Agnostique) : une technique pour expliquer les prédictions de n'importe quel classificateur d'apprentissage automatique en l'approximant localement avec un modèle interprétable.
  ​
* Attaque par inférence d'appartenance : une attaque visant à déterminer si un point de données spécifique a été utilisé pour entraîner un modèle d'apprentissage automatique.
  ​
* MITRE ATLAS : Paysage des menaces adverses pour les systèmes d'intelligence artificielle ; une base de connaissances des tactiques et techniques adverses contre les systèmes d'IA.
  ​
* Fiche de modèle – Une fiche de modèle est un document qui fournit des informations standardisées sur les performances d’un modèle d’IA, ses limitations, ses usages prévus, et les considérations éthiques afin de promouvoir la transparence et le développement responsable de l’IA.
  ​
* Extraction de modèle : une attaque où un adversaire interroge à plusieurs reprises un modèle cible pour créer une copie fonctionnellement similaire sans autorisation.
  ​
* Inversion de modèle : une attaque qui tente de reconstituer les données d'entraînement en analysant les sorties du modèle.
  ​
* Gestion du cycle de vie des modèles – La gestion du cycle de vie des modèles d'IA est le processus de supervision de toutes les étapes de l'existence d'un modèle d'IA, y compris sa conception, son développement, son déploiement, sa surveillance, sa maintenance et sa mise hors service éventuelle, afin de garantir qu'il reste efficace et conforme aux objectifs.
  ​
* Empoisonnement de modèle : introduction de vulnérabilités ou de portes dérobées directement dans un modèle pendant le processus d'entraînement.
  ​
* Vol de modèle : extraire une copie ou une approximation d'un modèle propriétaire par des requêtes répétées.
  ​
* Système multi-agent : un système composé de plusieurs agents IA interagissant, chacun avec des capacités et des objectifs potentiellement différents.
  ​
* OPA (Open Policy Agent) : un moteur de politique open source qui permet une application unifiée des politiques à travers l'ensemble de la pile.
  ​
* Apprentissage automatique préservant la vie privée (PPML) : Techniques et méthodes pour entraîner et déployer des modèles d'apprentissage automatique tout en protégeant la confidentialité des données d'entraînement.
  ​
* Injection de prompt : une attaque où des instructions malveillantes sont intégrées dans les entrées pour contourner le comportement prévu d'un modèle.
  ​
* RAG (génération augmentée par récupération) : une technique qui améliore les grands modèles de langage en récupérant des informations pertinentes à partir de sources de connaissance externes avant de générer une réponse.
  ​
* Red-Teaming : La pratique consistant à tester activement les systèmes d'IA en simulant des attaques adverses afin d'identifier les vulnérabilités.
  ​
* SBOM (Liste des éléments constitutifs du logiciel) : Un enregistrement formel contenant les détails et les relations de la chaîne d'approvisionnement des différents composants utilisés dans la création de logiciels ou de modèles d'IA.
  ​
* SHAP (SHapley Additive exPlanations) : une approche basée sur la théorie des jeux pour expliquer la sortie de tout modèle d'apprentissage automatique en calculant la contribution de chaque caractéristique à la prédiction.
  ​
* Attaque sur la chaîne d'approvisionnement : compromettre un système en ciblant des éléments moins sécurisés de sa chaîne d'approvisionnement, tels que des bibliothèques tierces, des ensembles de données ou des modèles pré-entraînés.
  ​
* Apprentissage par transfert : une technique où un modèle développé pour une tâche est réutilisé comme point de départ pour un modèle sur une seconde tâche.
  ​
* Base de données vectorielle : une base de données spécialisée conçue pour stocker des vecteurs de haute dimension (représentations vectorielles) et réaliser des recherches de similarité efficaces.
  ​
* Analyse de vulnérabilités : Outils automatisés qui identifient les vulnérabilités de sécurité connues dans les composants logiciels, y compris les frameworks IA et leurs dépendances.
  ​
* Marquage invisible : Techniques pour intégrer des marqueurs imperceptibles dans le contenu généré par l'IA afin de suivre son origine ou de détecter une génération par IA.
  ​
* Vulnérabilité Zero-Day : Une vulnérabilité auparavant inconnue que les attaquants peuvent exploiter avant que les développeurs ne créent et ne déploient un correctif.

