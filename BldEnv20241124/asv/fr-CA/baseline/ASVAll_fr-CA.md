## Page de titre

### À propos de la norme

La norme de vérification de la sécurité de l'intelligence artificielle (AISVS) est un catalogue de exigences de sécurité élaboré par la communauté, que les data scientists, ingénieurs MLOps, architectes logiciels, développeurs, testeurs, professionnels de la sécurité, fournisseurs d'outils, régulateurs et consommateurs peuvent utiliser pour concevoir, construire, tester et vérifier des systèmes et applications fiables dotés d'intelligence artificielle. Elle fournit un langage commun pour spécifier les contrôles de sécurité tout au long du cycle de vie de l'IA—depuis la collecte des données et le développement du modèle jusqu'au déploiement et à la surveillance continue—afin que les organisations puissent mesurer et améliorer la résilience, la confidentialité et la sécurité de leurs solutions IA.

### Droits d'auteur et Licence

Version 0.1 (Première ébauche publique - Travail en cours), 2025  

![license](images/license.png)
Droits d'auteur © 2025 Le projet AISVS.  

Publié sous laCreative Commons Attribution‑ShareAlike 4.0 International License.
Pour toute réutilisation ou distribution, vous devez clairement communiquer les conditions de licence de cette œuvre aux autres.

### Chefs de projet

Jim Manico
Aras « Russ » Memisyazici

### Contributeurs et réviseurs

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS est une toute nouvelle norme créée spécifiquement pour répondre aux défis uniques de sécurité des systèmes d'intelligence artificielle. Bien qu'elle s'inspire des meilleures pratiques de sécurité générales, chaque exigence d'AISVS a été développée de zéro afin de refléter le paysage des menaces en IA et d'aider les organisations à construire des solutions d'IA plus sûres et plus résilientes.

## Préface

Bienvenue dans la norme de vérification de la sécurité de l'intelligence artificielle (AISVS) version 1.0 !

### Introduction

Créée en 2025 grâce à un effort collaboratif de la communauté, AISVS définit les exigences de sécurité à prendre en compte lors de la conception, du développement, du déploiement et de l’exploitation des modèles d’IA modernes, des pipelines et des services activés par l’IA.

AISVS v1.0 représente le travail combiné de ses chefs de projet, du groupe de travail et des contributeurs de la communauté élargie pour produire une base pragmatique et testable pour sécuriser les systèmes d'IA.

Notre objectif avec cette version est de rendre AISVS facile à adopter tout en restant strictement concentré sur son périmètre défini et en répondant au paysage de risques en rapide évolution, propre à l'IA.

### Objectifs clés pour AISVS Version 1.0

La version 1.0 sera créée selon plusieurs principes directeurs.

#### Portée bien définie

Chaque exigence doit être conforme au nom et à la mission d’AISVS :

Intelligence artificielle – Les contrôles fonctionnent au niveau de la couche IA/ML (données, modèle, pipeline ou inférence) et sont de la responsabilité des praticiens de l'IA.
Sécurité – Les exigences atténuent directement les risques identifiés en matière de sécurité, de confidentialité ou de sécurité.
Vérification – Le langage est rédigé de manière à ce que la conformité puisse être validée objectivement.
Norme – Les sections suivent une structure et une terminologie cohérentes pour former une référence uniforme.
​
---

En suivant AISVS, les organisations peuvent évaluer systématiquement et renforcer la posture de sécurité de leurs solutions d'IA, favorisant ainsi une culture d'ingénierie de l'IA sécurisée.

## Utilisation de l’AISVS

La norme de vérification de la sécurité de l'intelligence artificielle (AISVS) définit les exigences de sécurité pour les applications et services d'IA modernes, en se concentrant sur les aspects sous le contrôle des développeurs d'applications.

L'AISVS est destiné à toute personne développant ou évaluant la sécurité des applications d'IA, y compris les développeurs, architectes, ingénieurs en sécurité et auditeurs. Ce chapitre présente la structure et l'utilisation de l'AISVS, y compris ses niveaux de vérification et ses cas d'utilisation prévus.

### Niveaux de vérification de la sécurité de l'intelligence artificielle

L'AISVS définit trois niveaux croissants de vérification de la sécurité. Chaque niveau ajoute de la profondeur et de la complexité, permettant aux organisations d'adapter leur posture de sécurité au niveau de risque de leurs systèmes d'IA.

Les organisations peuvent commencer au Niveau 1 et adopter progressivement des niveaux supérieurs à mesure que la maturité de la sécurité et l'exposition aux menaces augmentent.

#### Définition des Niveaux

Chaque exigence dans AISVS v1.0 est assignée à l'un des niveaux suivants :

 Exigences de niveau 1

Le niveau 1 comprend les exigences de sécurité les plus critiques et fondamentales. Celles-ci se concentrent sur la prévention des attaques courantes qui ne dépendent pas d'autres préconditions ou vulnérabilités. La plupart des contrôles de niveau 1 sont soit simples à mettre en œuvre, soit suffisamment essentiels pour justifier l'effort.

 Exigences de niveau 2

Le niveau 2 traite des attaques plus avancées ou moins courantes, ainsi que des défenses en couches contre les menaces généralisées. Ces exigences peuvent impliquer une logique plus complexe ou cibler des prérequis spécifiques aux attaques.

 Exigences de niveau 3

Le niveau 3 inclut des contrôles qui sont généralement plus difficiles à mettre en œuvre ou dont l’applicabilité est situationnelle. Ceux-ci représentent souvent des mécanismes de défense en profondeur ou des mesures d’atténuation contre des attaques de niche, ciblées ou à haute complexité.

#### Rôle (D/V)

Chaque exigence AISVS est indiquée selon le public principal :

D – Exigences axées sur les développeurs
V – Exigences axées sur le vérificateur/contrôleur
D/V – Pertinent à la fois pour les développeurs et les vérificateurs

## Gouvernance des données d'entraînement C1 et gestion des biais

### Objectif de contrôle

Les données d'entraînement doivent être obtenues, manipulées et maintenues de manière à préserver la provenance, la sécurité, la qualité et l'équité. Cela permet de remplir les obligations légales et de réduire les risques de biais, d'empoisonnement ou de violations de la vie privée tout au long du cycle de vie de l'IA.

---

### C1.1 Origine des données d'entraînement

Maintenez un inventaire vérifiable de tous les ensembles de données, n'acceptez que des sources fiables et consignez chaque modification pour assurer la traçabilité.

 #1.1.1    Level: 1    Role: D/V
 Vérifiez qu'un inventaire à jour de chaque source de données d'entraînement (origine, responsable/propriétaire, licence, méthode de collecte, contraintes d'utilisation prévues et historique de traitement) est maintenu.
 #1.1.2    Level: 1    Role: D/V
 Vérifiez que seuls les ensembles de données validés pour leur qualité, représentativité, approvisionnement éthique et conformité aux licences sont autorisés, réduisant ainsi les risques d'empoisonnement, de biais intégré et de violation de la propriété intellectuelle.
 #1.1.3    Level: 1    Role: D/V
 Vérifiez que la minimisation des données est appliquée afin que les attributs inutiles ou sensibles soient exclus.
 #1.1.4    Level: 2    Role: D/V
 Vérifiez que toutes les modifications du jeu de données font l'objet d'un processus d'approbation enregistré.
 #1.1.5    Level: 2    Role: D/V
 Vérifiez que la qualité de l'étiquetage/annotation est garantie par des vérifications croisées ou un consensus entre examinateurs.
 #1.1.6    Level: 2    Role: D/V
 Vérifiez que des « fiches de données » ou des « fiches techniques pour les ensembles de données » sont maintenues pour les ensembles de données d'entraînement importants, détaillant les caractéristiques, les motivations, la composition, les processus de collecte, le prétraitement, ainsi que les utilisations recommandées/déconseillées.

---

### C1.2 Sécurité et intégrité des données d'entraînement

Restreindre l'accès, chiffrer les données au repos et en transit, et valider l'intégrité pour empêcher la falsification ou le vol.

 #1.2.1    Level: 1    Role: D/V
 Vérifiez que les contrôles d'accès protègent le stockage et les pipelines.
 #1.2.2    Level: 2    Role: D/V
 Vérifiez que les ensembles de données sont chiffrés en transit et, pour toutes les informations sensibles ou personnellement identifiables (IPI), au repos, en utilisant des algorithmes cryptographiques standard de l'industrie et des pratiques de gestion des clés.
 #1.2.3    Level: 2    Role: D/V
 Vérifiez que des hachages cryptographiques ou des signatures numériques sont utilisés pour garantir l'intégrité des données lors du stockage et du transfert, et que des techniques automatiques de détection d'anomalies sont appliquées pour protéger contre les modifications non autorisées ou la corruption, y compris les tentatives ciblées d'empoisonnement des données.
 #1.2.4    Level: 3    Role: D/V
 Vérifiez que les versions des ensembles de données sont suivies pour permettre un retour en arrière.
 #1.2.5    Level: 2    Role: D/V
 Vérifiez que les données obsolètes sont supprimées de manière sécurisée ou anonymisées conformément aux politiques de conservation des données, aux exigences réglementaires, et afin de réduire la surface d'attaque.

---

### C1.3 Complétude et Équité de la Représentation

Détecter les biais démographiques et appliquer des mesures d'atténuation afin que les taux d'erreur du modèle soient équitables entre les groupes.

 #1.3.1    Level: 1    Role: D/V
 Vérifiez que les jeux de données sont analysés pour détecter les déséquilibres de représentation et les biais potentiels concernant les attributs protégés légalement (par exemple, race, genre, âge) ainsi que d'autres caractéristiques éthiquement sensibles pertinentes pour le domaine d'application du modèle (par exemple, statut socio-économique, localisation).
 #1.3.2    Level: 2    Role: D/V
 Vérifier que les biais identifiés sont atténués grâce à des stratégies documentées telles que le rééquilibrage, l’augmentation ciblée des données, les ajustements algorithmiques (par exemple, les techniques de pré-traitement, traitement en cours ou post-traitement), ou le repondération, et que l’impact de cette atténuation sur l’équité ainsi que sur la performance globale du modèle est évalué.
 #1.3.3    Level: 2    Role: D/V
 Vérifiez que les métriques d'équité post-entraînement sont évaluées et documentées.
 #1.3.4    Level: 3    Role: D/V
 Vérifiez qu'une politique de gestion des biais du cycle de vie attribue des responsables et un rythme de révision.

---

### C1.4 Qualité, intégrité et sécurité de l'étiquetage des données d'entraînement

Protégez les étiquettes par chiffrement et exigez une double vérification pour les classes critiques.

 #1.4.1    Level: 2    Role: D/V
 Vérifiez que la qualité de l'étiquetage/de l'annotation est assurée par des directives claires, des vérifications croisées par les réviseurs, des mécanismes de consensus (par exemple, le suivi de l'accord entre annotateurs) et des processus définis pour résoudre les divergences.
 #1.4.2    Level: 2    Role: D/V
 Vérifiez que des hachages cryptographiques ou des signatures numériques sont appliqués aux artefacts d’étiquette afin de garantir leur intégrité et authenticité.
 #1.4.3    Level: 2    Role: D/V
 Vérifiez que les interfaces et plateformes d'étiquetage appliquent des contrôles d'accès stricts, maintiennent des journaux d'audit infalsifiables de toutes les activités d'étiquetage et protègent contre les modifications non autorisées.
 #1.4.4    Level: 3    Role: D/V
 Vérifiez que les étiquettes critiques pour la sécurité, la sûreté ou l’équité (par exemple, l’identification de contenu toxique, de résultats médicaux critiques) font l’objet d’un examen obligatoire indépendant en double ou d’une vérification robuste équivalente.
 #1.4.5    Level: 2    Role: D/V
 Vérifiez que les informations sensibles (y compris les données personnelles identifiables) capturées par inadvertance ou nécessairement présentes dans les étiquettes sont expurgées, pseudonymisées, anonymisées ou cryptées au repos et en transit, conformément aux principes de minimisation des données.
 #1.4.6    Level: 2    Role: D/V
 Vérifiez que les guides d'étiquetage et les instructions sont complets, sous contrôle de version et revus par des pairs.
 #1.4.7    Level: 2    Role: D/V
 Vérifiez que les schémas de données (y compris pour les étiquettes) sont clairement définis et soumis à un contrôle de version.
 #1.8.2    Level: 2    Role: D/V
 Vérifiez que les flux de travail d'étiquetage externalisés ou participatifs incluent des mesures techniques et procédurales pour garantir la confidentialité des données, leur intégrité, la qualité des étiquettes, et prévenir toute fuite de données.

---

### C1.5 Assurance de la qualité des données d'entraînement

Combinez la validation automatisée, les contrôles ponctuels manuels et la correction journalisée pour garantir la fiabilité des ensembles de données.

 #1.5.1    Level: 1    Role: D
 Vérifiez que les tests automatisés détectent les erreurs de format, les valeurs nulles et les décalages d'étiquettes à chaque ingestion ou transformation significative.
 #1.5.2    Level: 1    Role: D/V
 Vérifiez que les ensembles de données défaillants sont mis en quarantaine avec des pistes d'audit.
 #1.5.3    Level: 2    Role: V
 Vérifiez que les contrôles ponctuels manuels réalisés par des experts du domaine couvrent un échantillon statistiquement significatif (par exemple, ≥1 % ou 1 000 échantillons, selon la valeur la plus élevée, ou tel que déterminé par l'évaluation des risques) pour identifier les problèmes de qualité subtils non détectés par l'automatisation.
 #1.5.4    Level: 2    Role: D/V
 Vérifiez que les étapes de remédiation sont ajoutées aux enregistrements de provenance.
 #1.5.5    Level: 2    Role: D/V
 Vérifiez que les seuils de qualité bloquent les ensembles de données de qualité inférieure, sauf si des exceptions sont approuvées.

---

### C1.6 Détection de l'empoisonnement des données

Appliquer la détection statistique d'anomalies et les flux de travail de mise en quarantaine pour stopper les insertions adverses.

 #1.6.1    Level: 2    Role: D/V
 Vérifiez que des techniques de détection d'anomalies (par exemple, méthodes statistiques, détection des valeurs aberrantes, analyse d'incorporation) sont appliquées aux données d'entraînement lors de leur ingestion et avant les principales sessions d'entraînement afin d'identifier d'éventuelles attaques par empoisonnement ou une corruption involontaire des données.
 #1.6.2    Level: 2    Role: D/V
 Vérifiez que les échantillons signalés déclenchent une révision manuelle avant l'entraînement.
 #1.6.3    Level: 2    Role: V
 Vérifiez que les résultats alimentent le dossier de sécurité du modèle et informent le renseignement continu sur les menaces.
 #1.6.4    Level: 3    Role: D/V
 Vérifiez que la logique de détection est actualisée avec les nouvelles informations sur les menaces.
 #1.6.5    Level: 3    Role: D/V
 Vérifiez que les pipelines d'apprentissage en ligne surveillent la dérive de distribution.
 #1.6.6    Level: 3    Role: D/V
 Vérifiez que des défenses spécifiques contre les types d'attaques connues d'empoisonnement de données (par exemple, inversion d’étiquettes, insertion de déclencheurs de porte dérobée, attaques par instances influentes) sont prises en compte et mises en œuvre en fonction du profil de risque du système et des sources de données.

---

### C1.7 Suppression des données utilisateur et application du consentement

Respecter les demandes de suppression et de retrait du consentement dans l'ensemble des ensembles de données, des sauvegardes et des artefacts dérivés.

 #1.7.1    Level: 1    Role: D/V
 Vérifiez que les workflows de suppression effacent les données primaires et dérivées ainsi que l'impact sur le modèle, et que cet impact sur les modèles affectés est évalué et, si nécessaire, traité (par exemple, par un nouvel entraînement ou une recalibration).
 #1.7.2    Level: 2    Role: D
 Vérifiez que des mécanismes sont en place pour suivre et respecter la portée et le statut du consentement utilisateur (et des retraits) concernant les données utilisées dans l'entraînement, et que le consentement est validé avant que les données ne soient intégrées dans de nouveaux processus d'entraînement ou des mises à jour significatives du modèle.
 #1.7.3    Level: 2    Role: V
 Vérifiez que les workflows sont testés annuellement et consignés dans un journal.

---

### C1.8 Sécurité de la chaîne d'approvisionnement

Évaluer les fournisseurs de données externes et vérifier l'intégrité via des canaux authentifiés et chiffrés.

 #1.8.1    Level: 2    Role: D/V
 Vérifiez que les fournisseurs de données tiers, y compris les prestataires de modèles pré-entraînés et de jeux de données externes, font l'objet d'une diligence raisonnable en matière de sécurité, de confidentialité, d'approvisionnement éthique et de qualité des données avant que leurs données ou modèles ne soient intégrés.
 #1.8.2    Level: 1    Role: D
 Vérifiez que les transferts externes utilisent TLS/authentification et des vérifications d'intégrité.
 #1.8.3    Level: 2    Role: D/V
 Vérifiez que les sources de données à haut risque (par exemple, les ensembles de données open-source dont la provenance est inconnue, les fournisseurs non vérifiés) font l’objet d’un contrôle renforcé, tel qu’une analyse en bac à sable, des vérifications approfondies de qualité/biais, et une détection ciblée de la contamination, avant leur utilisation dans des applications sensibles.
 #1.8.4    Level: 3    Role: D/V
 Vérifiez que les modèles pré-entraînés obtenus auprès de tiers sont évalués pour les biais intégrés, les portes dérobées potentielles, l'intégrité de leur architecture et la provenance de leurs données d'entraînement originales avant l'affinage ou le déploiement.

---

### C1.9 Détection des échantillons adversaires

Mettre en œuvre des mesures pendant la phase d'entraînement, telles que l'entraînement adversarial, pour renforcer la résilience du modèle face aux exemples adversariaux.

 #1.9.1    Level: 3    Role: D/V
 Vérifiez que des défenses appropriées, telles que l'entraînement adversarial (utilisant des exemples adversariaux générés), l'augmentation de données avec des entrées perturbées, ou des techniques d'optimisation robuste, sont mises en œuvre et ajustées pour les modèles pertinents en fonction de l'évaluation des risques.
 #1.9.2    Level: 2    Role: D/V
 Vérifiez que si un entraînement par adversaire est utilisé, la génération, la gestion et la gestion des versions des ensembles de données adversaires sont documentées et contrôlées.
 #1.9.3    Level: 3    Role: D/V
 Vérifiez que l'impact de l'entraînement à la robustesse adversariale sur la performance du modèle (à la fois sur des entrées propres et adversariales) et sur les métriques d'équité est évalué, documenté et suivi.
 #1.9.4    Level: 3    Role: D/V
 Vérifiez que les stratégies d'entraînement adversarial et de robustesse sont régulièrement révisées et mises à jour pour contrer l'évolution des techniques d'attaque adversariale.

---

### C1.10 Traçabilité et Trajectoire des Données

Suivez le parcours complet de chaque point de données depuis la source jusqu'à l'entrée du modèle pour assurer la traçabilité et la réponse aux incidents.

 #1.10.1    Level: 2    Role: D/V
 Vérifiez que la traçabilité de chaque point de données, y compris toutes les transformations, augmentations et fusions, est enregistrée et peut être reconstruite.
 #1.10.2    Level: 2    Role: D/V
 Vérifiez que les enregistrements de lignée sont immuables, stockés de manière sécurisée et accessibles pour les audits ou les enquêtes.
 #1.10.3    Level: 2    Role: D/V
 Vérifiez que le suivi de la lignée couvre à la fois les données brutes et les données synthétiques.

---

### C1.11 Gestion des données synthétiques

Assurez-vous que les données synthétiques sont correctement gérées, étiquetées et évaluées en termes de risques.

 #1.11.1    Level: 2    Role: D/V
 Vérifiez que toutes les données synthétiques sont clairement étiquetées et distinguables des données réelles tout au long du pipeline.
 #1.11.2    Level: 2    Role: D/V
 Vérifiez que le processus de génération, les paramètres et l'utilisation prévue des données synthétiques sont documentés.
 #1.11.3    Level: 2    Role: D/V
 Vérifiez que les données synthétiques ont fait l'objet d'une évaluation des risques concernant les biais, les fuites de confidentialité et les problèmes de représentation avant leur utilisation dans la formation.

---

### C1.12 Surveillance de l'accès aux données et détection des anomalies

Surveiller et alerter en cas d'accès inhabituel aux données d'entraînement afin de détecter les menaces internes ou l'exfiltration.

 #1.12.1    Level: 2    Role: D/V
 Vérifiez que tous les accès aux données d'entraînement sont enregistrés, y compris l'utilisateur, l'heure et l'action.
 #1.12.2    Level: 2    Role: D/V
 Vérifiez que les journaux d'accès sont régulièrement examinés pour détecter des schémas inhabituels, tels que des exportations massives ou des accès depuis de nouveaux emplacements.
 #1.12.3    Level: 2    Role: D/V
 Vérifiez que des alertes sont générées pour les événements d'accès suspects et qu'elles sont enquêtées rapidement.

---

### C1.13 Politiques de conservation et d'expiration des données

Définir et appliquer des périodes de conservation des données afin de minimiser le stockage de données inutile.

 #1.13.1    Level: 1    Role: D/V
 Vérifiez que des périodes de conservation explicites sont définies pour tous les ensembles de données d'entraînement.
 #1.13.2    Level: 2    Role: D/V
 Vérifiez que les ensembles de données sont automatiquement expirés, supprimés ou examinés pour suppression à la fin de leur cycle de vie.
 #1.13.3    Level: 2    Role: D/V
 Vérifiez que les actions de conservation et de suppression sont enregistrées et auditées.

---

### C1.14 Conformité réglementaire et juridictionnelle

Assurez-vous que toutes les données d'entraînement sont conformes aux lois et réglementations en vigueur.

 #1.14.1    Level: 2    Role: D/V
 Vérifiez que les exigences en matière de résidence des données et de transfert transfrontalier sont identifiées et appliquées pour tous les ensembles de données.
 #1.14.2    Level: 2    Role: D/V
 Vérifiez que les réglementations spécifiques à chaque secteur (par exemple, santé, finance) sont identifiées et prises en compte dans la gestion des données.
 #1.14.3    Level: 2    Role: D/V
 Vérifier que la conformité aux lois sur la protection de la vie privée pertinentes (par exemple, RGPD, CCPA) est documentée et revue régulièrement.

---

### C1.15 Filigrane de données et empreinte numérique

Détecter la réutilisation non autorisée ou la fuite de données propriétaires ou sensibles.

 #1.15.1    Level: 3    Role: D/V
 Vérifiez que les ensembles de données ou sous-ensembles sont filigranés ou dotés d'empreintes numériques lorsque cela est possible.
 #1.15.2    Level: 3    Role: D/V
 Vérifiez que les méthodes de filigrane/empreinte ne produisent pas de biais ni de risques pour la vie privée.
 #1.15.3    Level: 3    Role: D/V
 Vérifiez que des contrôles périodiques sont effectués pour détecter toute réutilisation non autorisée ou fuite de données filigranées.

---

### C1.16 Gestion des droits des personnes concernées

Soutenir les droits des personnes concernées tels que l'accès, la rectification, la restriction et l'opposition.

 #1.16.1    Level: 2    Role: D/V
 Vérifiez que des mécanismes existent pour répondre aux demandes des personnes concernées concernant l'accès, la rectification, la limitation ou l'opposition aux données.
 #1.16.2    Level: 2    Role: D/V
 Vérifiez que les demandes sont enregistrées, suivies et satisfaites dans les délais légalement impartis.
 #1.16.3    Level: 2    Role: D/V
 Vérifier que les processus relatifs aux droits des personnes concernées sont testés et revus régulièrement pour en assurer l'efficacité.

---

### C1.17 Analyse de l'impact des versions de jeux de données

Évaluez l'impact des modifications du jeu de données avant de mettre à jour ou de remplacer les versions.

 #1.17.1    Level: 2    Role: D/V
 Vérifiez qu'une analyse d'impact est réalisée avant de mettre à jour ou de remplacer une version de dataset, en couvrant la performance du modèle, l'équité et la conformité.
 #1.17.2    Level: 2    Role: D/V
 Vérifier que les résultats de l'analyse d'impact sont documentés et examinés par les parties prenantes concernées.
 #1.17.3    Level: 2    Role: D/V
 Vérifiez que des plans de retour arrière existent au cas où les nouvelles versions introduiraient des risques inacceptables ou des régressions.

---

### C1.18 Sécurité de la main-d'œuvre pour l'annotation des données

Assurer la sécurité et l'intégrité du personnel impliqué dans l'annotation des données.

 #1.18.1    Level: 2    Role: D/V
 Vérifiez que tout le personnel impliqué dans l'annotation des données a fait l'objet d'une vérification des antécédents et est formé à la sécurité et à la confidentialité des données.
 #1.18.2    Level: 2    Role: D/V
 Vérifiez que tout le personnel d'annotation signe des accords de confidentialité et de non-divulgation.
 #1.18.3    Level: 2    Role: D/V
 Vérifiez que les plateformes d'annotation appliquent des contrôles d'accès et surveillent les menaces internes.

---

### Références

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Validation des entrées utilisateur C2

### Objectif de contrôle

La validation rigoureuse des entrées utilisateur est une première ligne de défense contre certaines des attaques les plus dommageables sur les systèmes d'IA. Les attaques par injection de prompt peuvent contourner les instructions du système, divulguer des données sensibles ou orienter le modèle vers un comportement non autorisé. À moins que des filtres dédiés et des hiérarchies d’instructions ne soient en place, les recherches montrent que les "multi-shot" jailbreaks exploitant des fenêtres de contexte très longues seront efficaces. De plus, des attaques subtiles par perturbations adversariales—comme les substitutions par homoglyphes ou le leetspeak—peuvent modifier silencieusement les décisions d’un modèle.

---

### C2.1 Défense contre l'injection de requêtes

L'injection de prompt est l'un des principaux risques pour les systèmes d'IA. Les défenses contre cette tactique utilisent une combinaison de filtres de motifs statiques, de classificateurs dynamiques et de mise en œuvre de la hiérarchie des instructions.

 #2.1.1    Level: 1    Role: D/V
 Vérifiez que les entrées des utilisateurs sont filtrées contre une bibliothèque continuellement mise à jour de modèles connus d'injection dans les requêtes (mots-clés de contournement, « ignorer les précédents », chaînes de jeu de rôle, attaques indirectes via HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Vérifiez que le système applique une hiérarchie d'instructions dans laquelle les messages du système ou du développeur prévalent sur les instructions de l'utilisateur, même après l'expansion de la fenêtre contextuelle.
 #2.1.3    Level: 2    Role: D/V
 Vérifiez que les tests d’évaluation adversariale (par exemple, les invites « many-shot » de l’équipe rouge) sont effectués avant chaque déploiement de modèle ou de modèle d’invite, avec des seuils de taux de réussite et des bloqueurs automatisés pour les régressions.
 #2.1.4    Level: 2    Role: D
 Vérifiez que les invites provenant de contenus tiers (pages web, PDF, e-mails) sont nettoyées dans un contexte d'analyse isolé avant d'être concaténées dans l'invite principale.
 #2.1.5    Level: 3    Role: D/V
 Vérifiez que toutes les mises à jour des règles de filtrage des invites, les versions des modèles de classificateur et les changements de liste de blocage sont contrôlés par version et audités.

---

### C2.2 Résistance aux exemples adverses

Les modèles de traitement du langage naturel (NLP) restent vulnérables aux perturbations subtiles au niveau des caractères ou des mots, que les humains détectent souvent à peine mais que les modèles ont tendance à mal classer.

 #2.2.1    Level: 1    Role: D
 Vérifiez que les étapes de normalisation de base des entrées (Unicode NFC, mappage des homoglyphes, suppression des espaces) s'exécutent avant la tokenisation.
 #2.2.2    Level: 2    Role: D/V
 Vérifiez que la détection d'anomalies statistiques signale les entrées présentant une distance d'édition exceptionnellement élevée par rapport aux normes linguistiques, un nombre excessif de tokens répétés ou des distances d'incorporation anormales.
 #2.2.3    Level: 2    Role: D
 Vérifiez que le pipeline d'inférence prend en charge des variantes de modèles durcis par entraînement adversarial optionnel ou des couches de défense (par exemple, la randomisation, la distillation défensive) pour les points de terminaison à haut risque.
 #2.2.4    Level: 2    Role: V
 Vérifiez que les entrées suspectées d'être adversariales sont mises en quarantaine, consignées avec les charges utiles complètes (après la suppression des informations personnelles identifiables).
 #2.2.5    Level: 3    Role: D/V
 Vérifiez que les métriques de robustesse (taux de réussite des suites d'attaques connues) sont suivies dans le temps et que les régressions déclenchent un blocage de publication.

---

### C2.3 Validation du schéma, du type et de la longueur

Les attaques d'IA impliquant des entrées mal formées ou surdimensionnées peuvent provoquer des erreurs d'analyse, des débordements de saisie entre les champs, et une saturation des ressources. Une application stricte du schéma est également une condition préalable lors de l'exécution d'appels d'outils déterministes.

 #2.3.1    Level: 1    Role: D
 Vérifiez que chaque point de terminaison d'API ou d'appel de fonction définit un schéma d'entrée explicite (JSON Schema, Protobuf ou équivalent multimodal) et que les entrées sont validées avant l'assemblage de l'invite.
 #2.3.2    Level: 1    Role: D/V
 Vérifiez que les entrées dépassant les limites maximales de jetons ou d'octets sont rejetées avec une erreur sécurisée et ne sont jamais tronquées silencieusement.
 #2.3.3    Level: 2    Role: D/V
 Vérifiez que les vérifications de type (par exemple, plages numériques, valeurs d'énumération, types MIME pour images/audio) sont appliquées côté serveur, et pas uniquement dans le code client.
 #2.3.4    Level: 2    Role: D
 Vérifiez que les validateurs sémantiques (par exemple, JSON Schema) s'exécutent en temps constant pour éviter les attaques par déni de service algorithmique.
 #2.3.5    Level: 3    Role: V
 Vérifiez que les échecs de validation sont enregistrés avec des extraits de charge utile rédigés et des codes d'erreur non ambigus pour faciliter le triage de la sécurité.

---

### C2.4 Filtrage du Contenu et des Politiques

Les développeurs devraient être capables de détecter les invites syntaxiquement valides qui demandent un contenu interdit (tel que des instructions illicites, des discours de haine et des textes protégés par le droit d'auteur), puis empêcher leur diffusion.

 #2.4.1    Level: 1    Role: D
 Vérifiez qu'un classificateur de contenu (zero shot ou affiné) évalue chaque entrée pour la violence, l'automutilation, la haine, le contenu sexuel et les demandes illégales, avec des seuils configurables.
 #2.4.2    Level: 1    Role: D/V
 Vérifiez que les entrées qui violent les politiques recevront des refus standardisés ou des complétions sécurisées afin qu'elles ne soient pas transmises aux appels LLM en aval.
 #2.4.3    Level: 2    Role: D
 Vérifiez que le modèle de filtrage ou l'ensemble des règles est réentraîné/mis à jour au moins chaque trimestre, en incorporant les nouveaux schémas de contournement ou de violation de politique observés.
 #2.4.4    Level: 2    Role: D
 Vérifier que le filtrage respecte les politiques spécifiques à l'utilisateur (âge, contraintes légales régionales) via des règles basées sur les attributs résolues au moment de la demande.
 #2.4.5    Level: 3    Role: V
 Vérifiez que les journaux de filtrage incluent les scores de confiance du classificateur et les étiquettes de catégorie de politique pour la corrélation SOC et la relecture future par l'équipe rouge.

---

### C2.5 Limitation du taux d'entrée et prévention des abus

Les développeurs doivent prévenir les abus, l'épuisement des ressources et les attaques automatisées contre les systèmes d'IA en limitant les taux d'entrée et en détectant les schémas d'utilisation anormaux.

 #2.5.1    Level: 1    Role: D/V
 Vérifiez que les limites de taux par utilisateur, par IP et par clé API sont appliquées pour tous les points de terminaison d'entrée.
 #2.5.2    Level: 2    Role: D/V
 Vérifiez que les limites de débit en rafale et soutenues sont réglées pour prévenir les attaques par déni de service (DoS) et les attaques par force brute.
 #2.5.3    Level: 2    Role: D/V
 Vérifiez que les schémas d'utilisation anomalie (par exemple, les requêtes en rafale, le flood d'entrée) déclenchent des blocages automatiques ou des escalades.
 #2.5.4    Level: 3    Role: V
 Vérifiez que les journaux de prévention des abus sont conservés et examinés pour identifier les nouveaux schémas d'attaque.

---

### C2.6 Validation des entrées multimodales

Les systèmes d'IA devraient inclure une validation rigoureuse des entrées non textuelles (images, audio, fichiers) pour prévenir l'injection, l'évasion ou l'abus de ressources.

 #2.6.1    Level: 1    Role: D
 Vérifiez que toutes les entrées non textuelles (images, audio, fichiers) sont validées quant au type, à la taille et au format avant le traitement.
 #2.6.2    Level: 2    Role: D/V
 Vérifiez que les fichiers sont analysés pour détecter les logiciels malveillants et les charges utiles stéganographiques avant l'ingestion.
 #2.6.3    Level: 2    Role: D/V
 Vérifiez que les entrées d’image/audio sont contrôlées pour détecter les perturbations adversariales ou les schémas d’attaque connus.
 #2.6.4    Level: 3    Role: V
 Vérifiez que les échecs de validation des entrées multimodales sont enregistrés et déclenchent des alertes pour une enquête.

---

### C2.7 Provenance et attribution des entrées

Les systèmes d'IA devraient prendre en charge l'audit, le suivi des abus et la conformité en surveillant et en étiquetant l'origine de toutes les entrées utilisateur.

 #2.7.1    Level: 1    Role: D/V
 Vérifiez que toutes les entrées utilisateur sont marquées avec des métadonnées (ID utilisateur, session, source, horodatage, adresse IP) lors de l'ingestion.
 #2.7.2    Level: 2    Role: D/V
 Vérifiez que les métadonnées de provenance sont conservées et auditées pour toutes les entrées traitées.
 #2.7.3    Level: 2    Role: D/V
 Vérifiez que les sources d'entrée anormales ou non fiables sont signalées et soumises à un contrôle renforcé ou à un blocage.

---

### C2.8 Détection adaptative des menaces en temps réel

Les développeurs devraient utiliser des systèmes avancés de détection des menaces pour l'IA qui s'adaptent aux nouveaux schémas d'attaque et offrent une protection en temps réel grâce à la correspondance de motifs compilés.

 #2.8.1    Level: 1    Role: D/V
 Vérifiez que les modèles de détection des menaces sont compilés dans des moteurs regex optimisés pour un filtrage en temps réel à haute performance avec un impact minimal sur la latence.
 #2.8.2    Level: 1    Role: D/V
 Vérifiez que les systèmes de détection des menaces maintiennent des bibliothèques de modèles distinctes pour différentes catégories de menaces (injection d'invite, contenu nuisible, données sensibles, commandes système).
 #2.8.3    Level: 2    Role: D/V
 Vérifiez que la détection adaptative des menaces intègre des modèles d'apprentissage automatique qui mettent à jour la sensibilité aux menaces en fonction de la fréquence et des taux de réussite des attaques.
 #2.8.4    Level: 2    Role: D/V
 Vérifiez que les flux de renseignements sur les menaces en temps réel mettent automatiquement à jour les bibliothèques de modèles avec de nouvelles signatures d'attaque et des IOCs (Indicateurs de compromission).
 #2.8.5    Level: 3    Role: D/V
 Vérifiez que les taux de faux positifs dans la détection des menaces sont continuellement surveillés et que la spécificité des modèles est automatiquement ajustée pour minimiser les interférences avec les cas d'utilisation légitimes.
 #2.8.6    Level: 3    Role: D/V
 Vérifiez que l'analyse contextuelle des menaces prend en compte la source d'entrée, les comportements des utilisateurs et l'historique des sessions pour améliorer la précision de la détection.
 #2.8.7    Level: 3    Role: D/V
 Vérifiez que les métriques de performance de détection des menaces (taux de détection, latence de traitement, utilisation des ressources) sont surveillées et optimisées en temps réel.

---

### C2.9 Pipeline de validation de la sécurité multimodale

Les développeurs doivent fournir une validation de sécurité pour les modalités d'entrée d'IA texte, image, audio et autres, en intégrant des types spécifiques de détection des menaces et d'isolement des ressources.

 #2.9.1    Level: 1    Role: D/V
 Vérifiez que chaque modalité d'entrée dispose de validateurs de sécurité dédiés avec des schémas de menaces documentés (texte : injection de prompt, images : stéganographie, audio : attaques de spectrogramme) et des seuils de détection.
 #2.9.2    Level: 2    Role: D/V
 Vérifiez que les entrées multi-modales sont traitées dans des environnements isolés avec des limites de ressources définies (mémoire, CPU, temps de traitement) spécifiques à chaque type de modalité et documentées dans les politiques de sécurité.
 #2.9.3    Level: 2    Role: D/V
 Vérifiez que la détection des attaques cross-modales identifie les attaques coordonnées couvrant plusieurs types d’entrée (par exemple, des charges dissimulées stéganographiquement dans des images combinées avec une injection de commande dans du texte) grâce à des règles de corrélation et à la génération d’alertes.
 #2.9.4    Level: 3    Role: D/V
 Vérifiez que les échecs de validation multimodale déclenchent une journalisation détaillée incluant toutes les modalités d'entrée, les résultats de validation, les scores de menace et l'analyse de corrélation avec des formats de journalisation structurés pour l'intégration SIEM.
 #2.9.5    Level: 3    Role: D/V
 Vérifiez que les classificateurs de contenu spécifiques à chaque modalité sont mis à jour conformément aux calendriers documentés (au minimum trimestriellement) avec de nouveaux modèles de menaces, des exemples d'attaques adversariales et des critères de performance maintenus au-dessus des seuils de référence.

---

### Références

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Gestion du cycle de vie du modèle C3 et contrôle des modifications

### Objectif de contrôle

Les systèmes d'IA doivent mettre en œuvre des processus de contrôle des modifications qui empêchent les modifications non autorisées ou dangereuses des modèles d'atteindre la production. Ce contrôle garantit l'intégrité du modèle tout au long de son cycle de vie - depuis le développement jusqu'au déploiement en passant par la mise hors service - ce qui permet une réponse rapide aux incidents et maintient la responsabilité de toutes les modifications.

Objectif principal de la sécurité : seuls les modèles autorisés et validés atteignent la production en employant des processus contrôlés qui maintiennent l'intégrité, la traçabilité et la récupérabilité.

---

### C3.1 Autorisation et Intégrité du Modèle

Seuls les modèles autorisés avec une intégrité vérifiée atteignent les environnements de production.

 #3.1.1    Level: 1    Role: D/V
 Vérifiez que tous les artefacts du modèle (poids, configurations, tokenizers) sont signés cryptographiquement par des entités autorisées avant le déploiement.
 #3.1.2    Level: 1    Role: D/V
 Vérifiez que l'intégrité du modèle est validée au moment du déploiement et que les échecs de vérification de signature empêchent le chargement du modèle.
 #3.1.3    Level: 2    Role: D/V
 Vérifiez que les enregistrements de provenance du modèle incluent l'identité de l'entité autorisante, les sommes de contrôle des données d'entraînement, les résultats des tests de validation avec un statut réussi/échoué, ainsi qu'un horodatage de création.
 #3.1.4    Level: 2    Role: D/V
 Vérifiez que tous les artefacts du modèle utilisent la gestion de version sémantique (MAJOR.MINOR.PATCH) avec des critères documentés précisant quand chaque composant de la version doit être incrémenté.
 #3.1.5    Level: 2    Role: V
 Vérifiez que le suivi des dépendances maintient un inventaire en temps réel permettant l'identification rapide de tous les systèmes consommateurs.

---

### C3.2 Validation et test du modèle

Les modèles doivent passer des validations de sécurité et de sûreté définies avant le déploiement.

 #3.2.1    Level: 1    Role: D/V
 Vérifiez que les modèles subissent des tests de sécurité automatisés incluant la validation des entrées, la sanitation des sorties et des évaluations de sécurité avec des seuils de réussite/échec organisationnels préalablement convenus avant le déploiement.
 #3.2.2    Level: 1    Role: D/V
 Vérifiez que les échecs de validation bloquent automatiquement le déploiement du modèle après une approbation explicite de dérogation par le personnel autorisé pré-désigné avec des justifications commerciales documentées.
 #3.2.3    Level: 2    Role: V
 Vérifiez que les résultats des tests sont signés cryptographiquement et liés de manière immuable au hachage de la version spécifique du modèle en cours de validation.
 #3.2.4    Level: 2    Role: D/V
 Vérifiez que les déploiements d'urgence nécessitent une évaluation documentée des risques de sécurité et une approbation par une autorité de sécurité pré-désignée dans des délais préalablement convenus.

---

### C3.3 Déploiement Contrôlé et Rétablissement

Les déploiements de modèles doivent être contrôlés, surveillés et réversibles.

 #3.3.1    Level: 1    Role: D
 Vérifiez que les déploiements en production mettent en œuvre des mécanismes de déploiement progressif (déploiements canaris, déploiements blue-green) avec des déclencheurs de retour arrière automatisés basés sur des taux d'erreur prédéfinis, des seuils de latence ou des critères d'alerte de sécurité.
 #3.3.2    Level: 1    Role: D/V
 Vérifiez que les capacités de restauration annulent de manière atomique l'état complet du modèle (poids, configurations, dépendances) dans les fenêtres temporelles organisationnelles préétablies.
 #3.3.3    Level: 2    Role: D/V
 Vérifiez que les processus de déploiement valident les signatures cryptographiques et calculent les sommes de contrôle d'intégrité avant l'activation du modèle, en interrompant le déploiement en cas de non-concordance.
 #3.3.4    Level: 2    Role: D/V
 Vérifiez que les capacités d'arrêt d'urgence du modèle peuvent désactiver les points de terminaison du modèle dans les délais de réponse prédéfinis via des coupe-circuits automatisés ou des interrupteurs d'arrêt manuels.
 #3.3.5    Level: 2    Role: V
 Vérifiez que les artefacts de restauration (versions précédentes du modèle, configurations, dépendances) sont conservés conformément aux politiques organisationnelles avec un stockage immuable pour la réponse aux incidents.

---

### C3.4 Responsabilité des changements et audit

Toutes les modifications du cycle de vie du modèle doivent être traçables et auditables.

 #3.4.1    Level: 1    Role: V
 Vérifiez que tous les changements de modèle (déploiement, configuration, suppression) génèrent des enregistrements d'audit immuables incluant un horodatage, une identité d'acteur authentifiée, un type de changement, ainsi que les états avant et après.
 #3.4.2    Level: 2    Role: D/V
 Vérifiez que l'accès au journal d'audit nécessite une autorisation appropriée et que toutes les tentatives d'accès sont enregistrées avec l'identité de l'utilisateur et un horodatage.
 #3.4.3    Level: 2    Role: D/V
 Vérifiez que les modèles de requêtes et les messages système sont soumis au contrôle de version dans les dépôts git, avec un examen de code obligatoire et une approbation par des réviseurs désignés avant déploiement.
 #3.4.4    Level: 2    Role: V
 Vérifiez que les enregistrements d'audit incluent des détails suffisants (empreintes des modèles, instantanés de configuration, versions des dépendances) pour permettre une reconstruction complète de l'état du modèle à tout instant durant la période de conservation.

---

### C3.5 Pratiques de développement sécurisé

Les processus de développement et d'entraînement des modèles doivent suivre des pratiques sécurisées pour prévenir toute compromission.

 #3.5.1    Level: 1    Role: D
 Vérifiez que les environnements de développement, de test et de production du modèle sont séparés physiquement ou logiquement. Ils ne partagent aucune infrastructure, disposent de contrôles d'accès distincts et de magasins de données isolés.
 #3.5.2    Level: 1    Role: D
 Vérifiez que l'entraînement et l'ajustement fin du modèle se déroulent dans des environnements isolés avec un accès réseau contrôlé.
 #3.5.3    Level: 1    Role: D/V
 Vérifiez que les sources de données d’entraînement sont validées par des contrôles d’intégrité et authentifiées via des sources fiables avec une chaîne de garde documentée avant leur utilisation dans le développement du modèle.
 #3.5.4    Level: 2    Role: D
 Vérifiez que les artefacts de développement du modèle (hyperparamètres, scripts d'entraînement, fichiers de configuration) sont stockés dans un système de gestion de versions et nécessitent une approbation de revue par les pairs avant d'être utilisés pour l'entraînement.

---

### C3.6 Retrait et mise hors service du modèle

Les modèles doivent être retirés en toute sécurité lorsqu'ils ne sont plus nécessaires ou lorsque des problèmes de sécurité sont identifiés.

 #3.6.1    Level: 1    Role: D
 Vérifiez que les processus de retrait des modèles analysent automatiquement les graphes de dépendance, identifient tous les systèmes consommateurs et fournissent des périodes de préavis convenues à l'avance avant la mise hors service.
 #3.6.2    Level: 1    Role: D/V
 Vérifiez que les artefacts de modèles retirés sont effacés de manière sécurisée en utilisant l'effacement cryptographique ou la réécriture multiple conformément aux politiques documentées de rétention des données, avec des certificats de destruction vérifiés.
 #3.6.3    Level: 2    Role: V
 Vérifiez que les événements de mise hors service du modèle sont enregistrés avec un horodatage et l'identité de l'acteur, et que les signatures du modèle sont révoquées pour empêcher toute réutilisation.
 #3.6.4    Level: 2    Role: D/V
 Vérifiez que la mise hors service d'urgence du modèle peut désactiver l'accès au modèle dans les délais de réponse d'urgence préétablis grâce à des interrupteurs automatiques si des vulnérabilités de sécurité critiques sont découvertes.

---

### Références

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Infrastructure C4, Configuration et Sécurité du Déploiement

### Objectif de contrôle

L'infrastructure d'IA doit être renforcée contre l'escalade de privilèges, la falsification de la chaîne d'approvisionnement et les déplacements latéraux grâce à une configuration sécurisée, une isolation à l'exécution, des pipelines de déploiement fiables et une surveillance complète. Seuls les composants et configurations d'infrastructure autorisés et validés atteignent la production via des processus contrôlés qui maintiennent la sécurité, l'intégrité et la traçabilité.

Objectif principal de la sécurité : Seuls les composants d'infrastructure signés cryptographiquement et analysés pour les vulnérabilités atteignent la production via des pipelines de validation automatisés qui appliquent les politiques de sécurité et maintiennent des pistes d'audit immuables.

---

### C4.1 Isolation de l'environnement d'exécution

Prévenir les échappements de conteneurs et l'escalade de privilèges grâce aux primitives d'isolation au niveau du noyau et aux contrôles d'accès obligatoires.

 #4.1.1    Level: 1    Role: D/V
 Vérifiez que tous les conteneurs d'IA suppriment TOUTES les capacités Linux sauf CAP_SETUID, CAP_SETGID, et les capacités explicitement requises documentées dans les référentiels de sécurité.
 #4.1.2    Level: 1    Role: D/V
 Vérifiez que les profils seccomp bloquent tous les appels système sauf ceux figurant dans les listes d'autorisation pré-approuvées, les violations entraînant la terminaison du conteneur et la génération d'alertes de sécurité.
 #4.1.3    Level: 2    Role: D/V
 Vérifiez que les charges de travail d'IA s'exécutent avec des systèmes de fichiers racines en lecture seule, tmpfs pour les données temporaires, et des volumes nommés pour les données persistantes avec les options de montage noexec appliquées.
 #4.1.4    Level: 2    Role: D/V
 Vérifiez que la surveillance en temps réel basée sur eBPF (Falco, Tetragon ou équivalent) détecte les tentatives d'escalade de privilèges et tue automatiquement les processus fautifs conformément aux exigences de temps de réponse organisationnelles.
 #4.1.5    Level: 3    Role: D/V
 Vérifiez que les charges de travail d’IA à haut risque s’exécutent dans des environnements isolés matériellement (Intel TXT, AMD SVM ou nœuds bare-metal dédiés) avec une vérification d’attestation.

---

### C4.2 Pipelines de Construction et de Déploiement Sécurisés

Assurez l'intégrité cryptographique et la sécurité de la chaîne d'approvisionnement grâce à des builds reproductibles et des artefacts signés.

 #4.2.1    Level: 1    Role: D/V
 Vérifiez que l'infrastructure en tant que code est analysée avec des outils (tfsec, Checkov ou Terrascan) à chaque commit, bloquant les fusionnements en cas de détections de gravité CRITIQUE ou ÉLEVÉE.
 #4.2.2    Level: 1    Role: D/V
 Vérifiez que les constructions de conteneurs sont reproductibles avec des hachages SHA256 identiques entre les constructions et générez des attestations de provenance SLSA Niveau 3 signées avec Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Vérifiez que les images de conteneurs intègrent des SBOM CycloneDX ou SPDX et sont signées avec Cosign avant le push dans le registre, les images non signées étant rejetées lors du déploiement.
 #4.2.4    Level: 2    Role: D/V
 Vérifiez que les pipelines CI/CD utilisent des jetons OIDC provenant de HashiCorp Vault, des rôles AWS IAM ou de l'identité gérée Azure avec des durées de vie ne dépassant pas les limites définies par la politique de sécurité organisationnelle.
 #4.2.5    Level: 2    Role: D/V
 Vérifiez que les signatures Cosign et la provenance SLSA sont validées pendant le processus de déploiement avant l'exécution du conteneur et que toute erreur de vérification entraîne l'échec du déploiement.
 #4.2.6    Level: 2    Role: D/V
 Vérifiez que les environnements de construction s'exécutent dans des conteneurs éphémères ou des machines virtuelles sans stockage persistant et avec une isolation réseau par rapport aux VPCs de production.

---

### C4.3 Sécurité Réseau et Contrôle d'Accès

Implémentez un réseau à confiance zéro avec des politiques de refus par défaut et des communications chiffrées.

 #4.3.1    Level: 1    Role: D/V
 Vérifiez que les NetworkPolicies de Kubernetes ou tout équivalent mettent en œuvre un refus par défaut des flux entrants/sortants avec des règles d'autorisation explicites pour les ports requis (443, 8080, etc.).
 #4.3.2    Level: 1    Role: D/V
 Vérifiez que SSH (port 22), RDP (port 3389) et les points de terminaison des métadonnées cloud (169.254.169.254) sont bloqués ou nécessitent une authentification basée sur un certificat.
 #4.3.3    Level: 2    Role: D/V
 Vérifiez que le trafic sortant est filtré via des proxys HTTP/HTTPS (Squid, Istio ou passerelles NAT cloud) avec des listes de domaines autorisés et que les requêtes bloquées sont enregistrées.
 #4.3.4    Level: 2    Role: D/V
 Vérifiez que la communication inter-services utilise le TLS mutuel avec des certificats renouvelés conformément à la politique organisationnelle et que la validation des certificats est appliquée (sans utiliser de drapeaux skip-verify).
 #4.3.5    Level: 2    Role: D/V
 Vérifiez que l'infrastructure d'IA fonctionne dans des VPC/VNets dédiés sans accès direct à Internet et communique uniquement via des passerelles NAT ou des hôtes bastion.

---

### C4.4 Gestion des secrets et des clés cryptographiques

Protégez les informations d'identification grâce à un stockage sécurisé par matériel et à une rotation automatisée avec un accès zéro confiance.

 #4.4.1    Level: 1    Role: D/V
 Vérifiez que les secrets sont stockés dans HashiCorp Vault, AWS Secrets Manager, Azure Key Vault ou Google Secret Manager avec un chiffrement au repos utilisant AES-256.
 #4.4.2    Level: 1    Role: D/V
 Vérifiez que les clés cryptographiques sont générées dans des HSM certifiés FIPS 140-2 Niveau 2 (AWS CloudHSM, Azure Dedicated HSM) avec une rotation des clés conforme à la politique cryptographique organisationnelle.
 #4.4.3    Level: 2    Role: D/V
 Vérifiez que la rotation des secrets est automatisée avec un déploiement sans interruption et une rotation immédiate déclenchée par des changements de personnel ou des incidents de sécurité.
 #4.4.4    Level: 2    Role: D/V
 Vérifiez que les images de conteneurs sont analysées avec des outils (GitLeaks, TruffleHog ou detect-secrets) bloquant les constructions contenant des clés API, des mots de passe ou des certificats.
 #4.4.5    Level: 2    Role: D/V
 Vérifiez que l'accès aux secrets de production nécessite une authentification multi-facteurs (MFA) avec des jetons matériels (YubiKey, FIDO2) et est enregistré par des journaux d'audit immuables incluant les identités des utilisateurs et les horodatages.
 #4.4.6    Level: 2    Role: D/V
 Vérifiez que les secrets sont injectés via les secrets Kubernetes, les volumes montés ou les conteneurs d'initialisation, et assurez-vous que les secrets ne sont jamais intégrés dans les variables d'environnement ou les images.

---

### C4.5 Sandbox et validation des charges de travail en IA

Isolez les modèles d'IA non fiables dans des environnements sécurisés avec une analyse comportementale complète.

 #4.5.1    Level: 1    Role: D/V
 Vérifiez que les modèles d'IA externes s'exécutent dans gVisor, des microVM (telles que Firecracker, CrossVM) ou des conteneurs Docker avec les options --security-opt=no-new-privileges et --read-only.
 #4.5.2    Level: 1    Role: D/V
 Vérifiez que les environnements sandbox n'ont aucune connectivité réseau (--network=none) ou uniquement un accès localhost avec toutes les requêtes externes bloquées par les règles iptables.
 #4.5.3    Level: 2    Role: D/V
 Vérifiez que la validation du modèle d'IA inclut des tests automatisés de type red-team avec une couverture de test définie par l'organisation et une analyse comportementale pour la détection de portes dérobées.
 #4.5.4    Level: 2    Role: D/V
 Vérifiez qu'avant qu'un modèle d'IA ne soit mis en production, ses résultats dans le bac à sable sont cryptographiquement signés par le personnel de sécurité autorisé et stockés dans des journaux d'audit immuables.
 #4.5.5    Level: 2    Role: D/V
 Vérifiez que les environnements sandbox sont détruits et recréés à partir d'images maîtresses entre les évaluations, avec un nettoyage complet du système de fichiers et de la mémoire.

---

### C4.6 Surveillance de la sécurité de l'infrastructure

Scanner et surveiller en continu l'infrastructure avec une remédiation automatisée et des alertes en temps réel.

 #4.6.1    Level: 1    Role: D/V
 Vérifiez que les images de conteneurs sont analysées selon les calendriers organisationnels, avec les vulnérabilités CRITIQUES bloquant le déploiement en fonction des seuils de risque organisationnels.
 #4.6.2    Level: 1    Role: D/V
 Vérifiez que l'infrastructure respecte les référentiels CIS Benchmarks ou les contrôles NIST 800-53 avec des seuils de conformité définis par l'organisation et une correction automatisée pour les vérifications échouées.
 #4.6.3    Level: 2    Role: D/V
 Vérifiez que les vulnérabilités de gravité ÉLEVÉE sont corrigées conformément aux délais de gestion des risques organisationnels, avec des procédures d'urgence pour les CVE activement exploitées.
 #4.6.4    Level: 2    Role: V
 Vérifiez que les alertes de sécurité s’intègrent avec les plateformes SIEM (Splunk, Elastic ou Sentinel) en utilisant les formats CEF ou STIX/TAXII avec un enrichissement automatisé.
 #4.6.5    Level: 3    Role: V
 Vérifiez que les métriques d'infrastructure sont exportées vers les systèmes de surveillance (Prometheus, DataDog) avec des tableaux de bord SLA et des rapports exécutifs.
 #4.6.6    Level: 2    Role: D/V
 Vérifiez que la dérive de configuration est détectée à l'aide d'outils (Chef InSpec, AWS Config) conformément aux exigences de surveillance organisationnelles, avec un retour automatique en cas de modifications non autorisées.

---

### Gestion des ressources d'infrastructure IA C4.7

Prévenir les attaques par épuisement des ressources et assurer une allocation équitable des ressources grâce à des quotas et à la surveillance.

 #4.7.1    Level: 1    Role: D/V
 Vérifiez que l'utilisation du GPU/TPU est surveillée avec des alertes déclenchées aux seuils définis par l'organisation et que la mise à l'échelle automatique ou l'équilibrage de charge est activé en fonction des politiques de gestion de la capacité.
 #4.7.2    Level: 1    Role: D/V
 Vérifiez que les métriques de charge de travail de l'IA (latence d'inférence, débit, taux d'erreur) sont collectées conformément aux exigences de surveillance organisationnelles et corrélées à l'utilisation de l'infrastructure.
 #4.7.3    Level: 2    Role: D/V
 Vérifiez que les ResourceQuotas de Kubernetes ou leur équivalent limitent les charges de travail individuelles conformément aux politiques d'allocation des ressources de l'organisation, avec des limites strictes appliquées.
 #4.7.4    Level: 2    Role: V
 Vérifiez que la surveillance des coûts suit les dépenses par charge de travail/locataire avec des alertes basées sur les seuils budgétaires organisationnels et des contrôles automatisés pour les dépassements de budget.
 #4.7.5    Level: 3    Role: V
 Vérifiez que la planification des capacités utilise des données historiques avec des périodes de prévision définies par l'organisation et un approvisionnement automatisé des ressources basé sur les modèles de demande.
 #4.7.6    Level: 2    Role: D/V
 Vérifiez que l'épuisement des ressources déclenche les disjoncteurs conformément aux exigences de réponse organisationnelles, y compris la limitation du débit basée sur les politiques de capacité et l'isolation de la charge de travail.

---

### C4.8 Séparation des Environnements et Contrôles de Promotion

Appliquez des limites strictes à l'environnement avec des barrières de promotion automatisées et une validation de la sécurité.

 #4.8.1    Level: 1    Role: D/V
 Vérifiez que les environnements de développement/test/production fonctionnent dans des VPC/VNet séparés, sans rôles IAM partagés, groupes de sécurité ou connectivité réseau commune.
 #4.8.2    Level: 1    Role: D/V
 Vérifiez que la promotion de l'environnement nécessite l'approbation du personnel autorisé défini par l'organisation, avec des signatures cryptographiques et des pistes d'audit immuables.
 #4.8.3    Level: 2    Role: D/V
 Vérifiez que les environnements de production bloquent l'accès SSH, désactivent les points de terminaison de débogage et exigent des demandes de changement avec des exigences de préavis organisationnel, sauf en cas d'urgence.
 #4.8.4    Level: 2    Role: D/V
 Vérifiez que les modifications de l'infrastructure en tant que code nécessitent une revue par les pairs avec des tests automatisés et une analyse de sécurité avant la fusion dans la branche principale.
 #4.8.5    Level: 2    Role: D/V
 Vérifier que les données non production sont anonymisées conformément aux exigences de confidentialité organisationnelles, à la génération de données synthétiques, ou que le masquage complet des données avec suppression des informations personnellement identifiables (IPI) est vérifié.
 #4.8.6    Level: 2    Role: D/V
 Vérifiez que les étapes de promotion incluent des tests de sécurité automatisés (SAST, DAST, analyse de conteneur) avec zéro résultat CRITIQUE requis pour l'approbation.

---

### C4.9 Sauvegarde et restauration de l'infrastructure

Assurez la résilience de l'infrastructure grâce à des sauvegardes automatisées, des procédures de récupération testées et des capacités de reprise après sinistre.

 #4.9.1    Level: 1    Role: D/V
 Vérifiez que les configurations d'infrastructure sont sauvegardées conformément aux calendriers de sauvegarde organisationnels dans des régions géographiquement distinctes, en appliquant la stratégie de sauvegarde 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Vérifiez que les systèmes de sauvegarde fonctionnent dans des réseaux isolés avec des identifiants distincts et un stockage isolé (air-gapped) pour la protection contre les ransomwares.
 #4.9.3    Level: 2    Role: V
 Vérifiez que les procédures de récupération sont testées et validées par des tests automatisés conformément aux calendriers organisationnels, avec des objectifs de RTO et RPO répondant aux exigences de l'organisation.
 #4.9.4    Level: 3    Role: V
 Vérifiez que le plan de reprise après sinistre inclut des guides d'intervention spécifiques à l'IA avec la restauration des poids du modèle, la reconstruction du cluster GPU et la cartographie des dépendances des services.

---

### C4.10 Conformité et gouvernance des infrastructures

Maintenez la conformité réglementaire grâce à une évaluation continue, une documentation et des contrôles automatisés.

 #4.10.1    Level: 2    Role: D/V
 Vérifiez que la conformité de l'infrastructure est évaluée selon les calendriers organisationnels en fonction des contrôles SOC 2, ISO 27001 ou FedRAMP, avec une collecte automatisée des preuves.
 #4.10.2    Level: 2    Role: V
 Vérifiez que la documentation de l'infrastructure inclut des diagrammes réseau, des cartes de flux de données et des modèles de menaces mis à jour conformément aux exigences de la gestion des changements organisationnels.
 #4.10.3    Level: 3    Role: D/V
 Vérifiez que les modifications de l'infrastructure font l'objet d'une évaluation automatisée de l'impact sur la conformité avec des flux de travail d'approbation réglementaire pour les modifications à haut risque.

---

### C4.11 Sécurité du matériel d'IA

Sécuriser les composants matériels spécifiques à l'IA, y compris les GPU, les TPU et les accélérateurs d'IA spécialisés.

 #4.11.1    Level: 2    Role: D/V
 Vérifiez que le microprogramme de l'accélérateur d'IA (BIOS GPU, microprogramme TPU) est vérifié avec des signatures cryptographiques et mis à jour conformément aux délais de gestion des correctifs de l'organisation.
 #4.11.2    Level: 2    Role: D/V
 Vérifiez qu'avant l'exécution de la charge de travail, l'intégrité de l'accélérateur d'IA est validée par une attestation matérielle utilisant TPM 2.0, Intel TXT ou AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Vérifiez que la mémoire GPU est isolée entre les charges de travail en utilisant SR-IOV, MIG (GPU multi-instance) ou une partition matérielle équivalente avec une désinfection de la mémoire entre les tâches.
 #4.11.4    Level: 3    Role: V
 Vérifiez que la chaîne d'approvisionnement du matériel d'IA comprend une vérification de la provenance avec des certificats du fabricant et une validation de l'emballage inviolable.
 #4.11.5    Level: 3    Role: D/V
 Vérifiez que les modules de sécurité matériels (HSM) protègent les poids des modèles d'IA et les clés cryptographiques avec une certification FIPS 140-2 Niveau 3 ou Common Criteria EAL4+.

---

### C4.12 Infrastructure d'IA en périphérie et distribuée

Déploiements sécurisés d'IA distribuée incluant l'informatique en périphérie, l'apprentissage fédéré et les architectures multisites.

 #4.12.1    Level: 2    Role: D/V
 Vérifiez que les appareils d'IA en périphérie s'authentifient auprès de l'infrastructure centrale en utilisant le TLS mutuel avec des certificats d'appareil renouvelés conformément à la politique de gestion des certificats de l'organisation.
 #4.12.2    Level: 2    Role: D/V
 Vérifiez que les dispositifs périphériques mettent en œuvre un démarrage sécurisé avec des signatures vérifiées et une protection contre le retour en arrière afin d'empêcher les attaques de rétrogradation du firmware.
 #4.12.3    Level: 3    Role: D/V
 Vérifiez que la coordination de l'IA distribuée utilise des algorithmes de consensus tolérants aux fautes byzantines avec validation des participants et détection des nœuds malveillants.
 #4.12.4    Level: 3    Role: D/V
 Vérifiez que la communication de la périphérie vers le cloud inclut la limitation de la bande passante, la compression des données et les capacités de fonctionnement hors ligne avec un stockage local sécurisé.

---

### C4.13 Sécurité des infrastructures multi-cloud et hybrides

Sécurisez les charges de travail d'IA à travers plusieurs fournisseurs de cloud et des déploiements hybrides cloud-sur site.

 #4.13.1    Level: 2    Role: D/V
 Vérifiez que les déploiements d'IA multi-cloud utilisent une fédération d'identité indépendante du cloud (OIDC, SAML) avec une gestion centralisée des politiques entre les fournisseurs.
 #4.13.2    Level: 2    Role: D/V
 Vérifiez que le transfert de données entre clouds utilise un chiffrement de bout en bout avec des clés gérées par le client et que les contrôles de résidence des données sont appliqués selon la juridiction.
 #4.13.3    Level: 2    Role: D/V
 Vérifiez que les charges de travail IA hybrides sur le cloud mettent en œuvre des politiques de sécurité cohérentes à la fois dans les environnements sur site et cloud, avec une surveillance unifiée et des alertes.
 #4.13.4    Level: 3    Role: V
 Vérifiez que la prévention du verrouillage fournisseur cloud inclut une infrastructure en tant que code portable, des API standardisées et des capacités d'exportation de données avec des outils de conversion de format.
 #4.13.5    Level: 3    Role: V
 Vérifiez que l'optimisation des coûts multi-cloud inclut des contrôles de sécurité empêchant la prolifération des ressources ainsi que les frais non autorisés de transfert de données entre clouds.

---

### C4.14 Automatisation de l'infrastructure et sécurité GitOps

Automatisation sécurisée des pipelines d'infrastructure et des workflows GitOps pour la gestion de l'infrastructure IA.

 #4.14.1    Level: 2    Role: D/V
 Vérifiez que les dépôts GitOps exigent des commits signés avec des clés GPG et des règles de protection des branches empêchant les pushs directs vers les branches principales.
 #4.14.2    Level: 2    Role: D/V
 Vérifiez que l'automatisation de l'infrastructure inclut la détection des dérives avec des capacités de remédiation automatique et de retour arrière déclenchées selon les exigences de réponse organisationnelle pour les modifications non autorisées.
 #4.14.3    Level: 2    Role: D/V
 Vérifiez que l'approvisionnement automatisé de l'infrastructure inclut la validation des politiques de sécurité avec blocage du déploiement pour les configurations non conformes.
 #4.14.4    Level: 2    Role: D/V
 Vérifiez que les secrets d'automatisation de l'infrastructure sont gérés via des opérateurs de secrets externes (External Secrets Operator, Bank-Vaults) avec rotation automatique.
 #4.14.5    Level: 3    Role: V
 Vérifiez que l'infrastructure autonome intègre la corrélation des événements de sécurité avec une réponse automatisée aux incidents et des flux de travail de notification des parties prenantes.

---

### C4.15 Sécurité de l'infrastructure résistante au quantique

Préparez l'infrastructure d'IA aux menaces de l'informatique quantique grâce à la cryptographie post-quantique et aux protocoles résistants au quantique.

 #4.15.1    Level: 3    Role: D/V
 Vérifiez que l'infrastructure d'IA met en œuvre des algorithmes cryptographiques post-quantiques approuvés par le NIST (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) pour l'échange de clés et les signatures numériques.
 #4.15.2    Level: 3    Role: D/V
 Vérifiez que les systèmes de distribution de clés quantiques (QKD) sont mis en œuvre pour les communications IA à haute sécurité avec des protocoles de gestion de clés résistants au quantique.
 #4.15.3    Level: 3    Role: D/V
 Vérifiez que les cadres d'agilité cryptographique permettent une migration rapide vers de nouveaux algorithmes post-quantiques avec une rotation automatisée des certificats et des clés.
 #4.15.4    Level: 3    Role: V
 Vérifiez que la modélisation des menaces quantiques évalue la vulnérabilité de l'infrastructure IA aux attaques quantiques avec des calendriers de migration documentés et des évaluations des risques.
 #4.15.5    Level: 3    Role: D/V
 Vérifiez que les systèmes cryptographiques hybrides classiques-quantique offrent une défense en profondeur pendant la période de transition quantique avec une surveillance des performances.

---

### C4.16 Informatique confidentielle et enclaves sécurisées

Protégez les charges de travail d'IA et les poids des modèles en utilisant des environnements d'exécution sécurisés basés sur le matériel et des technologies de calcul confidentiel.

 #4.16.1    Level: 3    Role: D/V
 Vérifiez que les modèles d'IA sensibles s'exécutent au sein des enclaves Intel SGX, AMD SEV-SNP ou ARM TrustZone avec une mémoire chiffrée et une vérification d'attestation.
 #4.16.2    Level: 3    Role: D/V
 Vérifiez que les conteneurs confidentiels (Kata Containers, gVisor avec informatique confidentielle) isolent les charges de travail d'IA grâce au chiffrement de mémoire appliqué par le matériel.
 #4.16.3    Level: 3    Role: D/V
 Vérifiez que l'attestation à distance valide l'intégrité de l'enclave avant de charger les modèles d'IA avec une preuve cryptographique de l'authenticité d'un environnement d'exécution.
 #4.16.4    Level: 3    Role: D/V
 Vérifiez que les services d'inférence IA confidentiels empêchent l'extraction du modèle grâce à un calcul chiffré avec des poids de modèle scellés et une exécution protégée.
 #4.16.5    Level: 3    Role: D/V
 Vérifiez que l'orchestration de l'environnement d'exécution sécurisé gère le cycle de vie de l'enclave sécurisée avec une attestation à distance et des canaux de communication chiffrés.
 #4.16.6    Level: 3    Role: D/V
 Vérifiez que le calcul multipartite sécurisé (SMPC) permet un entraînement collaboratif de l'IA sans exposer les ensembles de données individuels ni les paramètres du modèle.

---

### C4.17 Infrastructure à connaissance zéro

Mettre en œuvre des systèmes de preuve à connaissance nulle pour la vérification et l'authentification de l'IA respectueuses de la vie privée sans révéler d'informations sensibles.

 #4.17.1    Level: 3    Role: D/V
 Vérifiez que les preuves à connaissance nulle (ZK-SNARKs, ZK-STARKs) permettent de vérifier l’intégrité du modèle d’IA et la provenance de son entraînement sans révéler les poids du modèle ni les données d’entraînement.
 #4.17.2    Level: 3    Role: D/V
 Vérifiez que les systèmes d'authentification basés sur ZK permettent une vérification des utilisateurs préservant la vie privée pour les services d'IA sans révéler les informations liées à l'identité.
 #4.17.3    Level: 3    Role: D/V
 Vérifiez que les protocoles d'intersection de ensembles privés (PSI) permettent une correspondance sécurisée des données pour l'IA fédérée sans exposer les ensembles de données individuels.
 #4.17.4    Level: 3    Role: D/V
 Vérifiez que les systèmes d'apprentissage automatique à connaissance zéro (ZKML) permettent des inférences d'IA vérifiables avec une preuve cryptographique de calcul correct.
 #4.17.5    Level: 3    Role: D/V
 Vérifiez que les ZK-rollups offrent un traitement des transactions IA évolutif et préservant la confidentialité avec une vérification par lots et une réduction de la charge computationnelle.

---

### C4.18 Prévention des attaques par canal auxiliaire

Protégez l'infrastructure d'IA contre les attaques par canaux auxiliaires basées sur le temps, la puissance, les ondes électromagnétiques et le cache, qui pourraient divulguer des informations sensibles.

 #4.18.1    Level: 3    Role: D/V
 Vérifiez que le temps d'inférence de l'IA est normalisé en utilisant des algorithmes à temps constant et un remplissage pour empêcher les attaques d'extraction de modèle basées sur le chronométrage.
 #4.18.2    Level: 3    Role: D/V
 Vérifiez que la protection contre l'analyse de puissance inclut l'injection de bruit, le filtrage de la ligne d'alimentation et des schémas d'exécution aléatoires pour le matériel d'IA.
 #4.18.3    Level: 3    Role: D/V
 Vérifiez que l'atténuation des canaux latéraux basés sur le cache utilise la partition du cache, la randomisation et les instructions de vidage pour empêcher la fuite d'informations.
 #4.18.4    Level: 3    Role: D/V
 Vérifiez que la protection contre les émissions électromagnétiques comprend le blindage, le filtrage des signaux et le traitement aléatoire pour prévenir les attaques de type TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Vérifiez que les défenses contre les canaux secondaires microarchitecturaux incluent des contrôles d'exécution spéculative et l'obfuscation des schémas d'accès mémoire.

---

### C4.19 Sécurité du matériel IA neuromorphique et spécialisé

Sécuriser les architectures matérielles émergentes en IA, y compris les puces neuromorphiques, les FPGA, les ASIC personnalisés et les systèmes de calcul optique.

 #4.19.1    Level: 3    Role: D/V
 Vérifiez que la sécurité des puces neuromorphiques inclut le chiffrement des motifs de pics, la protection des poids synaptiques et la validation des règles d'apprentissage basées sur le matériel.
 #4.19.2    Level: 3    Role: D/V
 Vérifiez que les accélérateurs d'IA basés sur FPGA mettent en œuvre le chiffrement du flux binaire, des mécanismes anti-altération et un chargement sécurisé de la configuration avec des mises à jour authentifiées.
 #4.19.3    Level: 3    Role: D/V
 Vérifiez que la sécurité ASIC personnalisée comprend des processeurs de sécurité intégrés, une racine matérielle de confiance et un stockage sécurisé des clés avec détection de falsification.
 #4.19.4    Level: 3    Role: D/V
 Vérifiez que les systèmes de calcul optique mettent en œuvre un chiffrement optique sécurisé face à la quantique, un commutateur photonique sécurisé et un traitement optique du signal protégé.
 #4.19.5    Level: 3    Role: D/V
 Vérifiez que les puces d'IA hybrides analogiques-numériques incluent un calcul analogique sécurisé, un stockage des poids protégé et une conversion analogique-numérique authentifiée.

---

### C4.20 Infrastructure de calcul respectueuse de la vie privée

Mettre en place des contrôles d'infrastructure pour le calcul respectueux de la vie privée afin de protéger les données sensibles lors du traitement et de l'analyse par l'IA.

 #4.20.1    Level: 3    Role: D/V
 Vérifiez que l'infrastructure de chiffrement homomorphe permet le calcul chiffré sur des charges de travail IA sensibles avec une vérification de l'intégrité cryptographique et une surveillance des performances.
 #4.20.2    Level: 3    Role: D/V
 Vérifiez que les systèmes de récupération d'informations privées permettent des requêtes dans les bases de données sans révéler les modèles de requête, grâce à une protection cryptographique des modèles d'accès.
 #4.20.3    Level: 3    Role: D/V
 Vérifiez que les protocoles de calcul multipartite sécurisé permettent une inférence d'IA respectueuse de la vie privée sans exposer les entrées individuelles ni les calculs intermédiaires.
 #4.20.4    Level: 3    Role: D/V
 Vérifiez que la gestion des clés préservant la confidentialité inclut la génération distribuée de clés, la cryptographie seuil, et la rotation sécurisée des clés avec une protection assistée par matériel.
 #4.20.5    Level: 3    Role: D/V
 Vérifiez que la performance du calcul préservant la confidentialité est optimisée grâce à la mise en lots, la mise en cache et l'accélération matérielle tout en maintenant les garanties de sécurité cryptographique.

---

### C4.15 Sécurité de l'intégration cloud du cadre d'agent et déploiement hybride

Contrôles de sécurité pour les frameworks d'agents intégrés au cloud avec des architectures hybrides sur site/cloud.

 #4.15.1    Level: 1    Role: D/V
 Vérifiez que l’intégration du stockage cloud utilise un chiffrement de bout en bout avec une gestion des clés contrôlée par l’agent.
 #4.15.2    Level: 2    Role: D/V
 Vérifiez que les limites de sécurité du déploiement hybride sont clairement définies avec des canaux de communication cryptés.
 #4.15.3    Level: 2    Role: D/V
 Vérifiez que l'accès aux ressources cloud inclut une vérification zero-trust avec une authentification continue.
 #4.15.4    Level: 3    Role: D/V
 Vérifiez que les exigences de résidence des données sont respectées par une attestation cryptographique des emplacements de stockage.
 #4.15.5    Level: 3    Role: D/V
 Vérifiez que les évaluations de sécurité des fournisseurs de cloud incluent une modélisation des menaces spécifique aux agents et une évaluation des risques.

---

### Références

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Contrôle d'accès C5 et identité pour les composants et utilisateurs d'IA

### Objectif de contrôle

Un contrôle d'accès efficace pour les systèmes d'IA nécessite une gestion robuste des identités, une autorisation contextuelle et une application en temps réel conforme aux principes du zéro confiance. Ces contrôles garantissent que les humains, services et agents autonomes n’interagissent avec les modèles, les données et les ressources informatiques que dans les périmètres explicitement autorisés, avec des capacités continues de vérification et d'audit.

---

### C5.1 Gestion de l'identité et authentification

Établir des identités sécurisées cryptographiquement pour toutes les entités avec une authentification multi-facteurs pour les opérations privilégiées.

 #5.1.1    Level: 1    Role: D/V
 Vérifiez que tous les utilisateurs humains et les principaux de service s’authentifient via un fournisseur d’identité d’entreprise centralisé (IdP) en utilisant les protocoles OIDC/SAML avec des correspondances uniques entre l’identité et le jeton (aucun compte ou identifiant partagé).
 #5.1.2    Level: 1    Role: D/V
 Vérifiez que les opérations à haut risque (déploiement de modèle, exportation de poids, accès aux données d'entraînement, modifications de la configuration en production) nécessitent une authentification multi-facteurs ou une authentification renforcée avec une revalidation de session.
 #5.1.3    Level: 2    Role: D
 Vérifiez que les nouveaux responsables subissent une vérification d'identité conforme à la norme NIST 800-63-3 IAL-2 ou à des normes équivalentes avant d'obtenir l'accès au système de production.
 #5.1.4    Level: 2    Role: V
 Vérifiez que les examens d'accès sont effectués trimestriellement avec une détection automatisée des comptes inactifs, une application de la rotation des identifiants et des flux de travail de désapprovisionnement.
 #5.1.5    Level: 3    Role: D/V
 Vérifiez que les agents d’IA fédérés s’authentifient via des assertions JWT signées ayant une durée de vie maximale de 24 heures et incluant une preuve cryptographique d’origine.

---

### C5.2 Autorisation des ressources et principe du moindre privilège

Implémenter des contrôles d'accès granulaires pour toutes les ressources IA avec des modèles d'autorisation explicites et des pistes d'audit.

 #5.2.1    Level: 1    Role: D/V
 Vérifiez que chaque ressource d'IA (ensembles de données, modèles, points de terminaison, collections vectorielles, indices d'intégration, instances de calcul) applique des contrôles d'accès basés sur les rôles avec des listes d'autorisation explicites et des politiques de refus par défaut.
 #5.2.2    Level: 1    Role: D/V
 Vérifiez que les principes de moindre privilège sont appliqués par défaut avec les comptes de service, en commençant par des permissions en lecture seule et en exigeant une justification commerciale documentée pour les accès en écriture.
 #5.2.3    Level: 1    Role: V
 Vérifiez que toutes les modifications du contrôle d'accès sont liées à des demandes de changement approuvées et enregistrées de manière immuable avec des horodatages, les identités des acteurs, les identifiants des ressources et les variations de permissions.
 #5.2.4    Level: 2    Role: D
 Vérifiez que les étiquettes de classification des données (PII, PHI, sous contrôle à l'exportation, propriétaire) se propagent automatiquement aux ressources dérivées (représentations vectorielles, caches de requêtes, résultats de modèles) avec une application cohérente des politiques.
 #5.2.5    Level: 2    Role: D/V
 Vérifiez que les tentatives d'accès non autorisées et les événements d'élévation de privilèges déclenchent des alertes en temps réel avec des métadonnées contextuelles vers les systèmes SIEM dans un délai de 5 minutes.

---

### C5.3 Évaluation Dynamique de la Politique

Déployez des moteurs de contrôle d'accès basé sur les attributs (ABAC) pour des décisions d'autorisation contextuelles avec des capacités d'audit.

 #5.3.1    Level: 1    Role: D/V
 Vérifiez que les décisions d'autorisation sont externalisées vers un moteur de politique dédié (OPA, Cedar ou équivalent) accessible via des API authentifiées avec une protection de l'intégrité cryptographique.
 #5.3.2    Level: 1    Role: D/V
 Vérifiez que les politiques évaluent les attributs dynamiques au moment de l'exécution, y compris le niveau de habilitation de l'utilisateur, la classification de la sensibilité des ressources, le contexte de la demande, l'isolation des locataires et les contraintes temporelles.
 #5.3.3    Level: 2    Role: D
 Vérifiez que les définitions de politique sont sous contrôle de version, évaluées par des pairs et validées par des tests automatisés dans les pipelines CI/CD avant le déploiement en production.
 #5.3.4    Level: 2    Role: V
 Vérifiez que les résultats de l'évaluation des politiques incluent des motifs de décision structurés et sont transmis aux systèmes SIEM pour l'analyse de corrélation et la production de rapports de conformité.
 #5.3.5    Level: 3    Role: D/V
 Vérifiez que les valeurs de temps de vie (TTL) du cache de politique ne dépassent pas 5 minutes pour les ressources à haute sensibilité et 1 heure pour les ressources standard avec des capacités d'invalidation du cache.

---

### C5.4 Application de la sécurité au moment de la requête

Mettre en œuvre des contrôles de sécurité au niveau de la base de données avec filtrage obligatoire et des politiques de sécurité au niveau des lignes.

 #5.4.1    Level: 1    Role: D/V
 Vérifiez que toutes les requêtes des bases de données vectorielles et SQL incluent les filtres de sécurité obligatoires (ID de locataire, étiquettes de sensibilité, périmètre utilisateur) appliqués au niveau du moteur de base de données, et non dans le code applicatif.
 #5.4.2    Level: 1    Role: D/V
 Vérifiez que les politiques de sécurité au niveau des lignes (RLS) et le masquage au niveau des champs sont activés avec l'héritage des politiques pour toutes les bases de données vectorielles, les indices de recherche et les ensembles de données d'entraînement.
 #5.4.3    Level: 2    Role: D
 Vérifiez que les évaluations d'autorisation échouées empêchent les « attaques du dépositaire confus » en interrompant immédiatement les requêtes et en renvoyant des codes d'erreur d'autorisation explicites plutôt que de retourner des ensembles de résultats vides.
 #5.4.4    Level: 2    Role: V
 Vérifiez que la latence d'évaluation de la politique est constamment surveillée avec des alertes automatisées en cas de conditions de dépassement de délai pouvant permettre un contournement de l'autorisation.
 #5.4.5    Level: 3    Role: D/V
 Vérifiez que les mécanismes de nouvelle tentative des requêtes réévaluent les politiques d'autorisation afin de tenir compte des modifications dynamiques des permissions au sein des sessions utilisateur actives.

---

### Filtrage de sortie C5.5 et prévention de la perte de données

Déployer des contrôles de post-traitement pour empêcher l'exposition non autorisée des données dans le contenu généré par l'IA.

 #5.5.1    Level: 1    Role: D/V
 Vérifiez que les mécanismes de filtrage post-inférence analysent et rédigent les informations personnelles identifiables (IPI), les informations classifiées et les données propriétaires non autorisées avant de livrer le contenu aux demandeurs.
 #5.5.2    Level: 1    Role: D/V
 Vérifiez que les citations, références et attributions de sources dans les résultats du modèle sont validées en fonction des droits du demandeur et supprimées en cas de détection d'un accès non autorisé.
 #5.5.3    Level: 2    Role: D
 Vérifiez que les restrictions sur le format de sortie (PDFs purgés, images sans métadonnées, types de fichiers approuvés) sont appliquées en fonction des niveaux d'autorisation des utilisateurs et des classifications des données.
 #5.5.4    Level: 2    Role: V
 Vérifiez que les algorithmes de masquage sont déterministes, contrôlés par version, et maintiennent des journaux d'audit pour soutenir les enquêtes de conformité et l'analyse médico-légale.
 #5.5.5    Level: 3    Role: V
 Vérifiez que les événements de rédaction à haut risque génèrent des journaux adaptatifs incluant des hachages cryptographiques du contenu original pour une récupération judiciaire sans exposition des données.

---

### C5.6 Isolation Multi-Locataire

Assurer l'isolation cryptographique et logique entre les locataires dans une infrastructure d'IA partagée.

 #5.6.1    Level: 1    Role: D/V
 Vérifiez que les espaces mémoire, les magasins d’intégration, les entrées de cache et les fichiers temporaires sont séparés par espace de noms pour chaque locataire, avec une suppression sécurisée lors de la suppression du locataire ou de la terminaison de la session.
 #5.6.2    Level: 1    Role: D/V
 Vérifiez que chaque requête API inclut un identifiant de locataire authentifié, validé cryptographiquement par rapport au contexte de session et aux droits de l'utilisateur.
 #5.6.3    Level: 2    Role: D
 Vérifiez que les politiques réseau appliquent des règles de refus par défaut pour la communication inter-locataires au sein des maillages de services et des plateformes d'orchestration de conteneurs.
 #5.6.4    Level: 3    Role: D
 Vérifier que les clés de chiffrement sont uniques par locataire avec prise en charge des clés gérées par le client (CMK) et une isolation cryptographique entre les magasins de données des locataires.

---

### C5.7 Autorisation de l'Agent Autonome

Contrôlez les autorisations des agents d'IA et des systèmes autonomes grâce à des jetons de capacité à portée définie et une autorisation continue.

 #5.7.1    Level: 1    Role: D/V
 Vérifiez que les agents autonomes reçoivent des jetons de capacité limités qui énumèrent explicitement les actions autorisées, les ressources accessibles, les limites temporelles et les contraintes opérationnelles.
 #5.7.2    Level: 1    Role: D/V
 Vérifiez que les capacités à haut risque (accès au système de fichiers, exécution de code, appels API externes, transactions financières) sont désactivées par défaut et nécessitent des autorisations explicites pour leur activation, accompagnées de justifications commerciales.
 #5.7.3    Level: 2    Role: D
 Vérifiez que les jetons de capacité sont liés aux sessions utilisateur, incluent une protection cryptographique d'intégrité, et assurez-vous qu'ils ne peuvent pas être conservés ou réutilisés dans des scénarios hors ligne.
 #5.7.4    Level: 2    Role: V
 Vérifiez que les actions initiées par l'agent font l'objet d'une autorisation secondaire via le moteur de politique ABAC avec une évaluation complète du contexte et une journalisation des audits.
 #5.7.5    Level: 3    Role: V
 Vérifiez que les conditions d'erreur de l'agent et la gestion des exceptions incluent des informations sur la portée des capacités pour soutenir l'analyse des incidents et l'enquête médico-légale.

---

### Références

#### Normes et cadres

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Guides de mise en œuvre

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Sécurité spécifique à l'IA

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Sécurité de la chaîne d'approvisionnement pour les modèles, cadres et données

### Objectif de contrôle

Les attaques de la chaîne d'approvisionnement en IA exploitent des modèles, cadres ou ensembles de données tiers pour y insérer des portes dérobées, des biais ou du code exploitable. Ces contrôles fournissent une traçabilité complète, une gestion des vulnérabilités et une surveillance pour protéger l'ensemble du cycle de vie du modèle.

---

### C6.1 Vérification et provenance des modèles pré-entraînés

Évaluez et authentifiez les origines, les licences et les comportements cachés des modèles tiers avant tout ajustement ou déploiement.

 #6.1.1    Level: 1    Role: D/V
 Vérifiez que chaque artefact de modèle tiers inclut un enregistrement de provenance signé identifiant le dépôt source et le hash de commit.
 #6.1.2    Level: 1    Role: D/V
 Vérifiez que les modèles sont analysés à la recherche de couches malveillantes ou de déclencheurs de chevaux de Troie à l'aide d'outils automatisés avant l'importation.
 #6.1.3    Level: 2    Role: D
 Vérifiez que l'apprentissage par transfert ajuste finement les modèles pour réussir l'évaluation adversariale afin de détecter les comportements cachés.
 #6.1.4    Level: 2    Role: V
 Vérifiez que les licences des modèles, les étiquettes de contrôle à l’exportation et les déclarations d’origine des données sont enregistrées dans une entrée ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Vérifiez que les modèles à haut risque (poids publiquement téléchargés, créateurs non vérifiés) restent en quarantaine jusqu'à la révision et l'approbation par un humain.

---

### C6.2 Analyse des cadres et des bibliothèques

Scanner en continu les frameworks et bibliothèques de ML à la recherche de CVE et de code malveillant pour maintenir la sécurité de la pile d'exécution.

 #6.2.1    Level: 1    Role: D/V
 Vérifiez que les pipelines CI exécutent des scanners de dépendances sur les frameworks d'IA et les bibliothèques critiques.
 #6.2.2    Level: 1    Role: D/V
 Vérifiez que les vulnérabilités critiques (CVSS ≥ 7,0) bloquent la promotion vers les images de production.
 #6.2.3    Level: 2    Role: D
 Vérifiez que l'analyse statique du code s'exécute sur les bibliothèques ML forkées ou fournies en tant que dépendances internes.
 #6.2.4    Level: 2    Role: V
 Vérifiez que les propositions de mise à niveau du framework incluent une évaluation de l’impact sur la sécurité faisant référence aux flux CVE publics.
 #6.2.5    Level: 3    Role: V
 Vérifiez que les capteurs d'exécution alertent en cas de chargements inattendus de bibliothèques dynamiques qui dévient du SBOM signé.

---

### C6.3 Verrouillage et vérification des dépendances

Épinglez chaque dépendance à des digests immuables et reproduisez les builds pour garantir des artefacts identiques et sans altération.

 #6.3.1    Level: 1    Role: D/V
 Vérifiez que tous les gestionnaires de paquets appliquent le verrouillage des versions via les fichiers de verrouillage.
 #6.3.2    Level: 1    Role: D/V
 Vérifiez que des résumés immuables sont utilisés au lieu de balises modifiables dans les références de conteneurs.
 #6.3.3    Level: 2    Role: D
 Vérifiez que les contrôles de construction reproductible comparent les hachages entre les exécutions CI pour garantir des sorties identiques.
 #6.3.4    Level: 2    Role: V
 Vérifiez que les attestations de construction sont conservées pendant 18 mois pour assurer la traçabilité des audits.
 #6.3.5    Level: 3    Role: D
 Vérifiez que les dépendances expirées déclenchent des PR automatisées pour mettre à jour ou forker les versions épinglées.

---

### C6.4 Application de la source fiable

Autoriser uniquement le téléchargement d'artefacts provenant de sources approuvées par l'organisation et vérifiées cryptographiquement, et bloquer tout le reste.

 #6.4.1    Level: 1    Role: D/V
 Vérifiez que les poids du modèle, les ensembles de données et les conteneurs sont téléchargés uniquement à partir de domaines approuvés ou de registres internes.
 #6.4.2    Level: 1    Role: D/V
 Vérifiez que les signatures Sigstore/Cosign valident l'identité de l'éditeur avant que les artefacts ne soient mis en cache localement.
 #6.4.3    Level: 2    Role: D
 Vérifiez que les proxies de sortie bloquent les téléchargements d’artefacts non authentifiés afin de faire respecter la politique de source de confiance.
 #6.4.4    Level: 2    Role: V
 Vérifiez que les listes blanches des dépôts sont examinées trimestriellement avec une preuve de justification commerciale pour chaque entrée.
 #6.4.5    Level: 3    Role: V
 Vérifier que les violations de politique déclenchent la mise en quarantaine des artefacts et le retour en arrière des exécutions de pipeline dépendantes.

---

### C6.5 Évaluation des risques liés aux ensembles de données tiers

Évaluer les ensembles de données externes pour la contamination, les biais et la conformité légale, et les surveiller tout au long de leur cycle de vie.

 #6.5.1    Level: 1    Role: D/V
 Vérifiez que les ensembles de données externes font l'objet d'une évaluation des risques de contamination (par exemple, empreinte des données, détection des valeurs aberrantes).
 #6.5.2    Level: 1    Role: D
 Vérifiez que les métriques de biais (parité démographique, égalité des chances) sont calculées avant l'approbation du jeu de données.
 #6.5.3    Level: 2    Role: V
 Vérifiez que la provenance et les conditions de licence des ensembles de données sont enregistrées dans les entrées ML-BOM.
 #6.5.4    Level: 2    Role: V
 Vérifiez que la surveillance périodique détecte la dérive ou la corruption des ensembles de données hébergés.
 #6.5.5    Level: 3    Role: D
 Vérifiez que le contenu non autorisé (droits d'auteur, informations personnelles identifiables) est supprimé automatiquement avant l'entraînement.

---

### C6.6 Surveillance des attaques sur la chaîne d'approvisionnement

Détectez tôt les menaces liées à la chaîne d'approvisionnement grâce aux flux CVE, à l'analyse des journaux d'audit et aux simulations d'équipes rouges.

 #6.6.1    Level: 1    Role: V
 Vérifiez que les journaux d'audit CI/CD sont transmis aux systèmes SIEM pour la détection des tirages de paquets anormaux ou des étapes de build altérées.
 #6.6.2    Level: 2    Role: D
 Vérifiez que les procédures d'intervention en cas d'incident comprennent des procédures de retour en arrière pour les modèles ou bibliothèques compromis.
 #6.6.3    Level: 3    Role: V
 Vérifiez que l'enrichissement des renseignements sur les menaces étiquette les indicateurs spécifiques au ML (par exemple, les IoC d'empoisonnement de modèle) lors du triage des alertes.

---

### C6.7 ML‑BOM pour les artefacts de modèle

Générez et signez des SBOMs détaillées spécifiques au ML (ML-BOMs) afin que les utilisateurs en aval puissent vérifier l'intégrité des composants au moment du déploiement.

 #6.7.1    Level: 1    Role: D/V
 Vérifiez que chaque artefact de modèle publie un ML‑BOM listant les jeux de données, les poids, les hyperparamètres et les licences.
 #6.7.2    Level: 1    Role: D/V
 Vérifiez que la génération de ML-BOM et la signature Cosign sont automatisées dans le CI et requises pour la fusion.
 #6.7.3    Level: 2    Role: D
 Vérifiez que les contrôles de complétude ML-BOM échouent la compilation si des métadonnées de composants (hachage, licence) sont manquantes.
 #6.7.4    Level: 2    Role: V
 Vérifiez que les consommateurs en aval peuvent interroger les ML-BOM via l'API pour valider les modèles importés au moment du déploiement.
 #6.7.5    Level: 3    Role: V
 Vérifiez que les ML-BOM sont versionnés et comparés pour détecter les modifications non autorisées.

---

### Références

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Modèle C7 : comportement, contrôle des sorties et assurance de sécurité

### Objectif de contrôle

Les résultats des modèles doivent être structurés, fiables, sûrs, explicables et continuellement surveillés en production. Cela permet de réduire les hallucinations, les fuites de données personnelles, les contenus nuisibles et les actions incontrôlées, tout en augmentant la confiance des utilisateurs et la conformité réglementaire.

---

### C7.1 Application des contraintes sur le format de sortie

Les schémas stricts, le décodage contraint et la validation en aval empêchent le contenu mal formé ou malveillant de se propager.

 #7.1.1    Level: 1    Role: D/V
 Vérifiez que les schémas de réponse (par exemple, JSON Schema) sont fournis dans l'invite système et que chaque sortie est automatiquement validée ; les sorties non conformes déclenchent une réparation ou un rejet.
 #7.1.2    Level: 1    Role: D/V
 Vérifiez que le décodage contraint (tokens d'arrêt, regex, nombre maximal de tokens) est activé pour empêcher les débordements ou les canaux secondaires d'injection de prompts.
 #7.1.3    Level: 2    Role: D/V
 Vérifiez que les composants en aval considèrent les sorties comme non fiables et les valident selon des schémas ou des désérialiseurs sûrs contre les injections.
 #7.1.4    Level: 3    Role: V
 Vérifiez que les événements de sortie incorrecte sont enregistrés, soumis à une limitation de fréquence et affichés dans la surveillance.

---

### C7.2 Détection et atténuation des hallucinations

L'estimation de l'incertitude et les stratégies de repli limitent les réponses fabriquées.

 #7.2.1    Level: 1    Role: D/V
 Vérifiez que les log-probabilités au niveau des tokens, la self-consistency en ensemble, ou les détecteurs d’hallucinations affinés attribuent un score de confiance à chaque réponse.
 #7.2.2    Level: 1    Role: D/V
 Vérifiez que les réponses en dessous d'un seuil de confiance configurable déclenchent des processus de secours (par exemple, génération augmentée par récupération, modèle secondaire ou révision humaine).
 #7.2.3    Level: 2    Role: D/V
 Vérifiez que les incidents d'hallucination sont étiquetés avec des métadonnées de cause racine et intégrés aux pipelines d'analyse post-mortem et de réglage fin.
 #7.2.4    Level: 3    Role: D/V
 Vérifiez que les seuils et les détecteurs sont recalibrés après les mises à jour majeures du modèle ou de la base de connaissances.
 #7.2.5    Level: 3    Role: V
 Vérifiez que les visualisations du tableau de bord suivent les taux d'hallucination.

---

### C7.3 Filtrage de sécurité et de confidentialité des sorties

Les filtres de politique et la couverture par l'équipe rouge protègent les utilisateurs et les données confidentielles.

 #7.3.1    Level: 1    Role: D/V
 Vérifiez que les classificateurs pré- et post-génération bloquent les contenus de haine, de harcèlement, d'automutilation, extrémistes et sexuellement explicites conformément à la politique.
 #7.3.2    Level: 1    Role: D/V
 Vérifiez que la détection des informations personnelles identifiables (PII) et des informations de carte de paiement (PCI) ainsi que la rédaction automatique s'exécutent sur chaque réponse ; les violations entraînent un incident de confidentialité.
 #7.3.3    Level: 2    Role: D
 Vérifiez que les étiquettes de confidentialité (par exemple, les secrets commerciaux) se propagent à travers les modalités afin de prévenir les fuites dans le texte, les images ou le code.
 #7.3.4    Level: 3    Role: D/V
 Vérifiez que les tentatives de contournement du filtre ou les classifications à haut risque nécessitent une approbation secondaire ou une réauthentification de l'utilisateur.
 #7.3.5    Level: 3    Role: D/V
 Vérifiez que les seuils de filtrage reflètent les juridictions légales ainsi que le contexte d'âge et de rôle de l'utilisateur.

---

### C7.4 Limitation de la sortie et des actions

Les limites de taux et les barrières d'approbation empêchent les abus et une autonomie excessive.

 #7.4.1    Level: 1    Role: D
 Vérifiez que les quotas par utilisateur et par clé API limitent les requêtes, les jetons et les coûts avec une temporisation exponentielle en cas d'erreurs 429.
 #7.4.2    Level: 1    Role: D/V
 Vérifiez que les actions privilégiées (écriture de fichiers, exécution de code, appels réseau) nécessitent une approbation basée sur une politique ou l'intervention humaine.
 #7.4.3    Level: 2    Role: D/V
 Vérifiez que les contrôles de cohérence intermodale garantissent que les images, le code et le texte générés pour une même requête ne peuvent pas être utilisés pour introduire du contenu malveillant.
 #7.4.4    Level: 2    Role: D
 Vérifiez que la profondeur de délégation des agents, les limites de récursion et les listes d'outils autorisés sont configurées de manière explicite.
 #7.4.5    Level: 3    Role: V
 Vérifiez que la violation des limites émet des événements de sécurité structurés pour l'ingestion par le SIEM.

---

### C7.5 Explicabilité des résultats

Les signaux transparents améliorent la confiance des utilisateurs et le débogage interne.

 #7.5.1    Level: 2    Role: D/V
 Vérifiez que les scores de confiance destinés à l'utilisateur ou les résumés succincts de raisonnement sont affichés lorsque l’évaluation des risques le juge approprié.
 #7.5.2    Level: 2    Role: D/V
 Vérifiez que les explications générées évitent de révéler des invites système sensibles ou des données propriétaires.
 #7.5.3    Level: 3    Role: D
 Vérifiez que le système capture les log-probabilités au niveau des tokens ou les cartes d'attention et les stocke pour une inspection autorisée.
 #7.5.4    Level: 3    Role: V
 Vérifiez que les artefacts d'explicabilité sont contrôlés par version en même temps que les versions des modèles pour assurer leur traçabilité.

---

### C7.6 Intégration de la surveillance

L'observabilité en temps réel boucle la fermeture entre le développement et la production.

 #7.6.1    Level: 1    Role: D
 Vérifiez que les métriques (violations de schéma, taux d'hallucination, toxicité, fuites de données personnelles identifiables, latence, coût) sont transmises à une plateforme de surveillance centrale.
 #7.6.2    Level: 1    Role: V
 Vérifiez que des seuils d'alerte sont définis pour chaque indicateur de sécurité, avec des voies d'escalade en cas d'astreinte.
 #7.6.3    Level: 2    Role: V
 Vérifiez que les tableaux de bord corrèlent les anomalies de sortie avec le modèle/version, le indicateur de fonctionnalité, et les modifications des données en amont.
 #7.6.4    Level: 2    Role: D/V
 Vérifiez que les données de surveillance sont réinjectées dans le réentraînement, l’ajustement ou la mise à jour des règles au sein d’un flux de travail MLOps documenté.
 #7.6.5    Level: 3    Role: V
 Vérifiez que les pipelines de surveillance sont soumis à des tests de pénétration et contrôlés par accès afin d'éviter la fuite de journaux sensibles.

---

### 7.7 Protections des médias générés

Assurez-vous que les systèmes d'IA ne génèrent pas de contenus médias illégaux, nuisibles ou non autorisés en appliquant des contraintes de politique, une validation des résultats et une traçabilité.

 #7.7.1    Level: 1    Role: D/V
 Vérifiez que les invites système et les instructions utilisateur interdisent explicitement la génération de contenus deepfake illégaux, nuisibles ou non consensuels (par exemple, image, vidéo, audio).
 #7.7.2    Level: 2    Role: D/V
 Vérifiez que les invites sont filtrées pour détecter les tentatives de génération d'usurpations d'identité, de deepfakes à caractère sexuel explicite ou de médias représentant des individus réels sans consentement.
 #7.7.3    Level: 2    Role: V
 Vérifiez que le système utilise le hachage perceptuel, la détection de filigrane ou l'empreinte digitale pour empêcher la reproduction non autorisée des médias protégés par des droits d'auteur.
 #7.7.4    Level: 3    Role: D/V
 Vérifiez que tous les médias générés sont signés cryptographiquement, filigranés ou intégrés avec des métadonnées de provenance résistantes à la falsification pour assurer la traçabilité en aval.
 #7.7.5    Level: 3    Role: V
 Vérifiez que les tentatives de contournement (par exemple, l’obfuscation de requêtes, l’argot, les formulations adverses) sont détectées, enregistrées et soumises à une limitation de fréquence ; les abus répétés sont signalés aux systèmes de surveillance.

### Références

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Sécurité de la mémoire C8, des embeddings et des bases de données vectorielles

### Objectif de Contrôle

Les embeddings et les magasins de vecteurs agissent comme la « mémoire vivante » des systèmes d'IA contemporains, acceptant continuellement les données fournies par les utilisateurs et les réintroduisant dans les contextes des modèles via la génération augmentée par récupération (RAG). Si cette mémoire n'est pas régulée, elle peut divulguer des informations personnelles identifiables (IPI), violer le consentement ou être exploitée pour reconstruire le texte original. L'objectif de cette famille de contrôles est de renforcer les pipelines de mémoire et les bases de données vectorielles afin que l'accès soit basé sur le principe du moindre privilège, que les embeddings préservent la confidentialité, que les vecteurs stockés expirent ou puissent être révoqués à la demande, et que la mémoire par utilisateur ne contamine jamais les requêtes ou complétions d'un autre utilisateur.

---

### C8.1 Contrôles d'accès sur la mémoire et les indices RAG

Appliquez des contrôles d'accès granulaire sur chaque collection de vecteurs.

 #8.1.1    Level: 1    Role: D/V
 Vérifiez que les règles de contrôle d'accès au niveau de la ligne/du namespace restreignent les opérations d'insertion, de suppression et de requête par locataire, collection ou étiquette de document.
 #8.1.2    Level: 1    Role: D/V
 Vérifiez que les clés API ou les JWT contiennent des revendications limitées (par exemple, des identifiants de collection, des verbes d'action) et qu'ils sont renouvelés au moins tous les trimestres.
 #8.1.3    Level: 2    Role: D/V
 Vérifiez que les tentatives d'escalade de privilèges (par exemple, les requêtes de similarité entre espaces de noms) sont détectées et enregistrées dans un SIEM dans un délai de 5 minutes.
 #8.1.4    Level: 2    Role: D/V
 Vérifiez que la base de données vectorielle enregistre dans les journaux l'identifiant du sujet, l'opération, l'ID/namespaces du vecteur, le seuil de similarité et le nombre de résultats.
 #8.1.5    Level: 3    Role: V
 Vérifiez que les décisions d'accès sont testées pour détecter les failles de contournement chaque fois que les moteurs sont mis à jour ou que les règles de fragmentation des index changent.

---

### C8.2 Assainissement et validation des embeddings

Préfiltrer le texte pour les informations personnelles identifiables (IPI), anonymiser ou pseudonymiser avant la vectorisation, et éventuellement post-traiter les embeddings pour éliminer les signaux résiduels.

 #8.2.1    Level: 1    Role: D/V
 Vérifiez que les données PII (informations personnelles identifiables) et réglementées sont détectées via des classificateurs automatisés et masquées, tokenisées ou supprimées avant l'incorporation.
 #8.2.2    Level: 1    Role: D
 Vérifiez que les pipelines d'intégration rejettent ou mettent en quarantaine les entrées contenant du code exécutable ou des artefacts non UTF-8 pouvant corrompre l'index.
 #8.2.3    Level: 2    Role: D/V
 Vérifiez que la désanonymisation locale ou différentielle métrique est appliquée aux embeddings de phrases dont la distance à tout jeton PII connu est inférieure à un seuil configurable.
 #8.2.4    Level: 2    Role: V
 Vérifiez que l'efficacité de la désinfection (par exemple, le rappel de la suppression des informations personnelles identifiables, la dérive sémantique) est validée au moins semestriellement à l'aide de corpus de référence.
 #8.2.5    Level: 3    Role: D/V
 Vérifiez que les configurations de désinfection sont contrôlées par version et que les modifications font l'objet d'une revue par les pairs.

---

### C8.3 Expiration, révocation et suppression de la mémoire

Le "droit à l'oubli" du RGPD et des lois similaires exigent une suppression rapide ; les magasins de vecteurs doivent donc prendre en charge les TTL (temps de vie), les suppressions définitives et les tombstones afin que les vecteurs révoqués ne puissent pas être récupérés ou réindexés.

 #8.3.1    Level: 1    Role: D/V
 Vérifiez que chaque vecteur et chaque enregistrement de métadonnées porte un TTL ou une étiquette de conservation explicite respectée par les tâches de nettoyage automatisées.
 #8.3.2    Level: 1    Role: D/V
 Vérifiez que les demandes de suppression initiées par l'utilisateur purgent les vecteurs, les métadonnées, les copies du cache et les indices dérivés dans les 30 jours.
 #8.3.3    Level: 2    Role: D
 Vérifiez que les suppressions logiques sont suivies d'un effacement cryptographique des blocs de stockage si le matériel le supporte, ou par la destruction des clés du coffre-fort de clés.
 #8.3.4    Level: 3    Role: D/V
 Vérifiez que les vecteurs expirés sont exclus des résultats de recherche par plus proche voisin en moins de 500 ms après leur expiration.

---

### C8.4 Prévenir l'inversion et la fuite d'intégration

Les défenses récentes—superposition de bruit, réseaux de projection, perturbation des neurones de confidentialité et chiffrement au niveau de l'application—peuvent réduire les taux d'inversion au niveau du token à moins de 5 %.

 #8.4.1    Level: 1    Role: V
 Vérifiez qu'un modèle de menace formel couvrant les attaques d'inversion, d'appartenance et d'inférence d'attributs existe et est examiné annuellement.
 #8.4.2    Level: 2    Role: D/V
 Vérifiez que le chiffrement au niveau de l'application ou le chiffrement recherché protège les vecteurs contre les lectures directes par les administrateurs d'infrastructure ou le personnel du cloud.
 #8.4.3    Level: 3    Role: V
 Vérifiez que les paramètres de défense (ε pour la DP, le bruit σ, le rang de projection k) équilibrent la protection de la confidentialité ≥ 99 % des tokens et la perte d'utilité ≤ 3 % de précision.
 #8.4.4    Level: 3    Role: D/V
 Vérifiez que les métriques de résilience à l'inversion font partie des critères de validation pour les mises à jour de modèles, avec des budgets de régression définis.

---

### C8.5 Application de la portée pour la mémoire spécifique à l'utilisateur

La fuite entre locataires reste un risque majeur pour les RAG : des requêtes de similitude mal filtrées peuvent révéler les documents privés d'un autre client.

 #8.5.1    Level: 1    Role: D/V
 Vérifiez que chaque requête de récupération est post-filtrée par l’ID du locataire/utilisateur avant d’être transmise au prompt du LLM.
 #8.5.2    Level: 1    Role: D
 Vérifiez que les noms de collections ou les identifiants avec espace de noms sont salés par utilisateur ou locataire afin que les vecteurs ne puissent pas se chevaucher entre les domaines.
 #8.5.3    Level: 2    Role: D/V
 Vérifiez que les résultats de similarité supérieurs à un seuil de distance configurable mais en dehors du périmètre de l'appelant sont rejetés et déclenchent des alertes de sécurité.
 #8.5.4    Level: 2    Role: V
 Vérifiez que les tests de charge multi-locataires simulent des requêtes adverses tentant de récupérer des documents hors de portée et démontrent une absence totale de fuite.
 #8.5.5    Level: 3    Role: D/V
 Vérifiez que les clés de chiffrement sont isolées par locataire, garantissant une isolation cryptographique même si le stockage physique est partagé.

---

### C8.6 Sécurité avancée des systèmes mémoire

Contrôles de sécurité pour des architectures mémoire sophistiquées incluant la mémoire épisodique, sémantique et de travail avec des exigences spécifiques d'isolation et de validation.

 #8.6.1    Level: 1    Role: D/V
 Vérifiez que les différents types de mémoire (épisodique, sémantique, de travail) disposent de contextes de sécurité isolés avec des contrôles d'accès basés sur les rôles, des clés de chiffrement distinctes et des schémas d'accès documentés pour chaque type de mémoire.
 #8.6.2    Level: 2    Role: D/V
 Vérifiez que les processus de consolidation de la mémoire incluent une validation de sécurité pour empêcher l'injection de souvenirs malveillants grâce à la désinfection du contenu, à la vérification des sources et aux contrôles d'intégrité avant le stockage.
 #8.6.3    Level: 2    Role: D/V
 Vérifiez que les requêtes de récupération de mémoire sont validées et nettoyées pour empêcher l'extraction d'informations non autorisées via l'analyse des schémas de requête, l'application du contrôle d'accès et le filtrage des résultats.
 #8.6.4    Level: 3    Role: D/V
 Vérifiez que les mécanismes d'oubli de la mémoire suppriment de manière sécurisée les informations sensibles avec des garanties d'effacement cryptographique en utilisant la suppression de clés, la réécriture multiple ou la suppression sécurisée basée sur le matériel accompagnée de certificats de vérification.
 #8.6.5    Level: 3    Role: D/V
 Vérifiez que l'intégrité du système mémoire est continuellement surveillée pour détecter toute modification non autorisée ou corruption via des sommes de contrôle, des journaux d'audit, et des alertes automatisées lorsque le contenu de la mémoire change en dehors des opérations normales.

---

### Références

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Orchestration Autonome et Sécurité de l'Action Agentique

### Objectif de contrôle

Assurez-vous que les systèmes d'IA autonomes ou multi-agents ne peuvent exécuter que des actions explicitement prévues, authentifiées, traçables et respectant des seuils limités de coût et de risque. Cela protège contre des menaces telles que la compromission du système autonome, l'utilisation abusive des outils, la détection de boucles d'agent, le détournement de communication, l'usurpation d'identité, la manipulation de essaims et la manipulation des intentions.

---

### 9.1 Budgets de planification des tâches des agents et de récursivité

Limiter les plans récursifs et imposer des points de contrôle humains pour les actions privilégiées.

 #9.1.1    Level: 1    Role: D/V
 Vérifiez que la profondeur maximale de récursion, la largeur, le temps chronométré, les jetons et le coût monétaire par exécution d'agent sont configurés de manière centralisée et contrôlés par versions.
 #9.1.2    Level: 1    Role: D/V
 Vérifiez que les actions privilégiées ou irréversibles (par exemple, les validations de code, les transferts financiers) nécessitent une approbation humaine explicite via un canal auditable avant exécution.
 #9.1.3    Level: 2    Role: D
 Vérifiez que les moniteurs de ressources en temps réel déclenchent une interruption par disjoncteur lorsqu'un seuil de budget est dépassé, arrêtant ainsi toute extension supplémentaire des tâches.
 #9.1.4    Level: 2    Role: D/V
 Vérifiez que les événements de disjoncteur sont enregistrés avec l’identifiant de l’agent, la condition de déclenchement et l’état du plan capturé pour une analyse judiciaire.
 #9.1.5    Level: 3    Role: V
 Vérifiez que les tests de sécurité couvrent les scénarios d'épuisement du budget et de plan incontrôlé, en confirmant un arrêt sécurisé sans perte de données.
 #9.1.6    Level: 3    Role: D
 Vérifiez que les politiques budgétaires sont exprimées en tant que politique-sous-code et appliquées dans le CI/CD afin de bloquer la dérive de configuration.

---

### 9.2 Isolement des plugins d'outils

Isoler les interactions des outils pour prévenir tout accès non autorisé au système ou exécution de code.

 #9.2.1    Level: 1    Role: D/V
 Vérifiez que chaque outil/plugin s'exécute à l'intérieur d'un système d'exploitation, d'un conteneur ou d'un bac à sable au niveau WASM avec des politiques de moindre privilège pour le système de fichiers, le réseau et les appels système.
 #9.2.2    Level: 1    Role: D/V
 Vérifiez que les quotas de ressources du bac à sable (CPU, mémoire, disque, sortie réseau) et les délais d'exécution sont appliqués et enregistrés.
 #9.2.3    Level: 2    Role: D/V
 Vérifiez que les fichiers binaires ou descripteurs des outils sont signés numériquement ; les signatures doivent être validées avant le chargement.
 #9.2.4    Level: 2    Role: V
 Vérifiez que la télémétrie du bac à sable est transmise à un SIEM ; les anomalies (par exemple, les tentatives de connexions sortantes) déclenchent des alertes.
 #9.2.5    Level: 3    Role: V
 Vérifiez que les plugins à haut risque subissent une revue de sécurité et des tests de pénétration avant le déploiement en production.
 #9.2.6    Level: 3    Role: D/V
 Vérifiez que les tentatives d'évasion du bac à sable sont automatiquement bloquées et que le plugin fautif est mis en quarantaine en attendant une enquête.

---

### 9.3 Boucle autonome et limitation des coûts

Détecter et arrêter la récursion incontrôlée entre agents ainsi que les explosions de coûts.

 #9.3.1    Level: 1    Role: D/V
 Vérifiez que les appels inter-agents incluent une limite de sauts ou un TTL que le runtime décrémente et applique.
 #9.3.2    Level: 2    Role: D
 Vérifiez que les agents maintiennent un identifiant unique de graphe d'invocation afin de détecter les auto-invocations ou les motifs cycliques.
 #9.3.3    Level: 2    Role: D/V
 Vérifiez que les compteurs cumulés d'unités de calcul et de dépenses sont suivis pour chaque chaîne de requêtes ; dépasser la limite entraîne l'interruption de la chaîne.
 #9.3.4    Level: 3    Role: V
 Vérifiez que l'analyse formelle ou la vérification de modèle démontre l'absence de récursion non bornée dans les protocoles d'agent.
 #9.3.5    Level: 3    Role: D
 Vérifiez que les événements d'arrêt de boucle génèrent des alertes et alimentent les métriques d'amélioration continue.

---

### 9.4 Protection contre les abus au niveau du protocole

Canaux de communication sécurisés entre les agents et les systèmes externes pour prévenir la prise de contrôle ou la manipulation.

 #9.4.1    Level: 1    Role: D/V
 Vérifiez que tous les messages agent-à-outil et agent-à-agent sont authentifiés (par exemple, TLS mutuel ou JWT) et chiffrés de bout en bout.
 #9.4.2    Level: 1    Role: D
 Vérifiez que les schémas sont strictement validés ; les champs inconnus ou les messages mal formés sont rejetés.
 #9.4.3    Level: 2    Role: D/V
 Vérifiez que les contrôles d'intégrité (MAC ou signatures numériques) couvrent l'intégralité de la charge utile du message, y compris les paramètres de l'outil.
 #9.4.4    Level: 2    Role: D
 Vérifiez que la protection contre la répétition (nonces ou fenêtres temporelles) est appliquée au niveau du protocole.
 #9.4.5    Level: 3    Role: V
 Vérifiez que les implémentations de protocoles subissent des tests d'injection aléatoire (fuzzing) et des analyses statiques pour détecter les failles d'injection ou de désérialisation.

---

### 9.5 Identité de l'agent et preuve de falsification

Assurez-vous que les actions sont attribuables et que les modifications sont détectables.

 #9.5.1    Level: 1    Role: D/V
 Vérifiez que chaque instance d'agent possède une identité cryptographique unique (paire de clés ou certificat ancré matériellement).
 #9.5.2    Level: 2    Role: D/V
 Vérifiez que toutes les actions des agents sont signées et horodatées ; les journaux incluent la signature pour garantir la non-répudiation.
 #9.5.3    Level: 2    Role: V
 Vérifiez que les journaux à preuve de falsification sont stockés sur un support en mode ajout seulement ou en écriture unique.
 #9.5.4    Level: 3    Role: D
 Vérifiez que les clés d'identité sont renouvelées selon un calendrier défini et en cas d'indicateurs de compromission.
 #9.5.5    Level: 3    Role: D/V
 Vérifiez que les tentatives d'usurpation d'identité ou de conflit de clés déclenchent une mise en quarantaine immédiate de l'agent affecté.

---

### 9.6 Réduction des risques par essaim multi-agents

Atténuer les risques liés au comportement collectif par l'isolation et la modélisation formelle de la sécurité.

 #9.6.1    Level: 1    Role: D/V
 Vérifiez que les agents opérant dans différents domaines de sécurité s'exécutent dans des environnements d'exécution isolés ou des segments réseau isolés.
 #9.6.2    Level: 3    Role: V
 Vérifiez que les comportements en essaim sont modélisés et formellement vérifiés pour la vivacité et la sécurité avant le déploiement.
 #9.6.3    Level: 3    Role: D
 Vérifiez que les moniteurs d'exécution détectent les motifs émergents dangereux (par exemple, les oscillations, les interblocages) et initient une action corrective.

---

### 9.7 Authentification / Autorisation des utilisateurs et des outils

Mettre en œuvre des contrôles d'accès robustes pour chaque action déclenchée par un agent.

 #9.7.1    Level: 1    Role: D/V
 Vérifiez que les agents s'authentifient en tant que principaux de première classe auprès des systèmes en aval, sans jamais réutiliser les identifiants des utilisateurs finaux.
 #9.7.2    Level: 2    Role: D
 Vérifiez que les politiques d'autorisation granulaire restreignent les outils qu'un agent peut invoquer ainsi que les paramètres qu'il peut fournir.
 #9.7.3    Level: 2    Role: V
 Vérifiez que les contrôles de privilèges sont réévalués à chaque appel (autorisation continue), et pas seulement au début de la session.
 #9.7.4    Level: 3    Role: D
 Vérifiez que les privilèges délégués expirent automatiquement et nécessitent un nouveau consentement après un délai d'expiration ou un changement de périmètre.

---

### 9.8 Sécurité de la communication entre agents

Chiffrez et protégez l'intégrité de tous les messages entre agents pour empêcher l'espionnage et la falsification.

 #9.8.1    Level: 1    Role: D/V
 Vérifiez que l'authentification mutuelle et le chiffrement à secret parfait (par exemple TLS 1.3) sont obligatoires pour les canaux des agents.
 #9.8.2    Level: 1    Role: D
 Vérifiez que l'intégrité et l'origine du message sont validées avant le traitement ; en cas d'échec, des alertes sont générées et le message est rejeté.
 #9.8.3    Level: 2    Role: D/V
 Vérifiez que les métadonnées de communication (horodatages, numéros de séquence) sont enregistrées pour permettre une reconstitution judiciaire.
 #9.8.4    Level: 3    Role: V
 Vérifiez que la vérification formelle ou la vérification par modèle confirme que les machines à états du protocole ne peuvent pas être amenées à des états non sûrs.

---

### 9.9 Vérification des intentions et application des contraintes

Valider que les actions de l'agent sont conformes à l'intention déclarée de l'utilisateur et aux contraintes du système.

 #9.9.1    Level: 1    Role: D
 Vérifiez que les solveurs de contraintes en pré-exécution vérifient les actions proposées par rapport aux règles de sécurité et de politique codées en dur.
 #9.9.2    Level: 2    Role: D/V
 Vérifiez que les actions à fort impact (financières, destructives, sensibles à la confidentialité) nécessitent une confirmation explicite d'intention de la part de l'utilisateur initiateur.
 #9.9.3    Level: 2    Role: V
 Vérifiez que les vérifications des post-conditions confirment que les actions accomplies ont atteint les effets intentionnés sans effets secondaires ; les écarts déclenchent un retour en arrière.
 #9.9.4    Level: 3    Role: V
 Vérifiez que les méthodes formelles (par exemple, la vérification de modèles, la démonstration de théorèmes) ou les tests basés sur les propriétés démontrent que les plans d'agent satisfont à toutes les contraintes déclarées.
 #9.9.5    Level: 3    Role: D
 Vérifiez que les incidents de décalage d'intention ou de violation de contraintes alimentent les cycles d'amélioration continue et le partage des informations sur les menaces.

---

### 9.10 Sécurité de la stratégie de raisonnement de l'agent

Sélection et exécution sécurisées de différentes stratégies de raisonnement, y compris les approches ReAct, Chaîne de la pensée (Chain-of-Thought) et Arbre de pensées (Tree-of-Thoughts).

 #9.10.1    Level: 1    Role: D/V
 Vérifiez que la sélection de la stratégie de raisonnement utilise des critères déterministes (complexité de l'entrée, type de tâche, contexte de sécurité) et que des entrées identiques produisent des sélections de stratégie identiques dans le même contexte de sécurité.
 #9.10.2    Level: 1    Role: D/V
 Vérifiez que chaque stratégie de raisonnement (ReAct, Chaîne de Pensée, Arbre des Pensées) dispose d’une validation d’entrée dédiée, d’une assainissement de sortie et de limites de temps d’exécution spécifiques à son approche cognitive.
 #9.10.3    Level: 2    Role: D/V
 Vérifiez que les transitions de stratégie de raisonnement sont enregistrées avec un contexte complet incluant les caractéristiques d'entrée, les valeurs des critères de sélection et les métadonnées d'exécution pour la reconstitution de la piste d'audit.
 #9.10.4    Level: 2    Role: D/V
 Vérifiez que le raisonnement Tree-of-Thoughts inclut des mécanismes d'élagage des branches qui interrompent l'exploration lorsqu'une violation de politique, une limite de ressources ou une frontière de sécurité est détectée.
 #9.10.5    Level: 2    Role: D/V
 Vérifiez que les cycles ReAct (Raison-Agir-Observer) incluent des points de contrôle de validation à chaque étape : vérification de l’étape de raisonnement, autorisation de l’action, et assainissement de l’observation avant de continuer.
 #9.10.6    Level: 3    Role: D/V
 Vérifiez que les métriques de performance de la stratégie de raisonnement (temps d'exécution, utilisation des ressources, qualité de sortie) sont surveillées avec des alertes automatisées lorsque les métriques dépassent les seuils configurés.
 #9.10.7    Level: 3    Role: D/V
 Vérifiez que les approches de raisonnement hybrides combinant plusieurs stratégies respectent la validation des entrées et les contraintes de sortie de toutes les stratégies constitutives sans contourner aucun contrôle de sécurité.
 #9.10.8    Level: 3    Role: D/V
 Vérifiez que la stratégie de raisonnement de test de sécurité inclut le fuzzing avec des entrées malformées, des invites adverses conçues pour forcer le changement de stratégie, et des tests des conditions limites pour chaque approche cognitive.

---

### 9.11 Gestion de l'État du Cycle de Vie de l'Agent et Sécurité

Initialisation sécurisée des agents, transitions d'état et terminaison avec des pistes d'audit cryptographiques et des procédures de récupération définies.

 #9.11.1    Level: 1    Role: D/V
 Vérifiez que l'initialisation de l'agent comprend l'établissement d'une identité cryptographique avec des identifiants sécurisés par matériel et des journaux d'audit de démarrage immuables contenant l'ID de l'agent, l'horodatage, le hachage de configuration et les paramètres d'initialisation.
 #9.11.2    Level: 2    Role: D/V
 Vérifiez que les transitions d'état de l'agent sont signées cryptographiquement, horodatées et enregistrées avec un contexte complet comprenant les événements déclencheurs, le hachage de l'état précédent, le hachage du nouvel état et les validations de sécurité effectuées.
 #9.11.3    Level: 2    Role: D/V
 Vérifiez que les procédures d'arrêt de l'agent incluent l'effacement sécurisé de la mémoire utilisant l'effacement cryptographique ou la réécriture multi-pass, la révocation des identifiants avec notification à l'autorité de certification, et la génération de certificats de terminaison inviolables.
 #9.11.4    Level: 3    Role: D/V
 Vérifiez que les mécanismes de récupération des agents valident l'intégrité de l'état à l'aide de sommes de contrôle cryptographiques (minimum SHA-256) et reviennent à des états connus comme fiables en cas de détection de corruption, avec des alertes automatisées et des exigences d'approbation manuelle.
 #9.11.5    Level: 3    Role: D/V
 Vérifiez que les mécanismes de persistance des agents chiffrent les données d'état sensibles avec des clés AES-256 par agent et mettent en œuvre une rotation sécurisée des clés selon des calendriers configurables (maximum 90 jours) avec un déploiement sans interruption.

---

### 9.12 Cadre de sécurité pour l'intégration des outils

Contrôles de sécurité pour le chargement dynamique des outils, leur exécution et la validation des résultats avec des processus définis d'évaluation des risques et d'approbation.

 #9.12.1    Level: 1    Role: D/V
 Vérifiez que les descripteurs d'outils incluent des métadonnées de sécurité spécifiant les privilèges requis (lecture/écriture/exécution), les niveaux de risque (faible/moyen/élevé), les limites de ressources (CPU, mémoire, réseau) et les exigences de validation documentées dans les manifestes des outils.
 #9.12.2    Level: 1    Role: D/V
 Vérifiez que les résultats de l'exécution des outils sont validés par rapport aux schémas attendus (schéma JSON, schéma XML) et aux politiques de sécurité (assainissement des sorties, classification des données) avant l'intégration, avec des limites de temps d'attente et des procédures de gestion des erreurs.
 #9.12.3    Level: 2    Role: D/V
 Vérifiez que les journaux d'interaction des outils incluent un contexte de sécurité détaillé, comprenant l'utilisation des privilèges, les modèles d'accès aux données, le temps d'exécution, la consommation des ressources et les codes de retour, avec une journalisation structurée pour l'intégration SIEM.
 #9.12.4    Level: 2    Role: D/V
 Vérifiez que les mécanismes de chargement dynamique des outils valident les signatures numériques en utilisant l'infrastructure PKI et mettent en œuvre des protocoles de chargement sécurisés avec une isolation en sandbox et une vérification des autorisations avant l'exécution.
 #9.12.5    Level: 3    Role: D/V
 Vérifiez que les évaluations de sécurité des outils sont automatiquement déclenchées pour les nouvelles versions avec des étapes d'approbation obligatoires, incluant l'analyse statique, les tests dynamiques et la revue par l'équipe de sécurité, avec des critères d'approbation documentés et des exigences de SLA.

---

#### Références

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Robustesse Adversariale et Défense de la Vie Privée

### Objectif de contrôle

Veillez à ce que les modèles d'IA restent fiables, respectueux de la vie privée et résistants aux abus lorsqu'ils sont confrontés à des attaques d’évasion, d'inférence, d'extraction ou d'empoisonnement.

---

### 10.1 Alignement et sécurité du modèle

Se prémunir contre les résultats nuisibles ou contraires à la politique.

 #10.1.1    Level: 1    Role: D/V
 Vérifiez qu'une suite de tests d'alignement (invitations de red team, sondes de jailbreak, contenu interdit) est contrôlée par version et exécutée à chaque version du modèle.
 #10.1.2    Level: 1    Role: D
 Vérifiez que les garde-fous de refus et de complétion sécurisée sont appliqués.
 #10.1.3    Level: 2    Role: D/V
 Vérifiez qu'un évaluateur automatisé mesure le taux de contenu nuisible et signale les régressions au-delà d'un seuil défini.
 #10.1.4    Level: 2    Role: D
 Vérifiez que la formation contre les jailbreaks est documentée et reproductible.
 #10.1.5    Level: 3    Role: V
 Vérifiez que les preuves de conformité formelle aux politiques ou la surveillance certifiée couvrent les domaines critiques.

---

### 10.2 Renforcement contre les exemples adverses

Augmenter la résilience aux entrées manipulées. La formation adversariale robuste et l'évaluation par points de référence sont les meilleures pratiques actuelles.

 #10.2.1    Level: 1    Role: D
 Vérifiez que les dépôts du projet incluent des configurations d’entraînement adversarial avec des graines reproductibles.
 #10.2.2    Level: 2    Role: D/V
 Vérifiez que la détection des exemples adverses déclenche des alertes de blocage dans les pipelines de production.
 #10.2.4    Level: 3    Role: V
 Vérifiez que les preuves de robustesse certifiée ou les certificats de bornes d’intervalle couvrent au moins les principales classes critiques.
 #10.2.5    Level: 3    Role: V
 Vérifiez que les tests de régression utilisent des attaques adaptatives pour confirmer l'absence de perte de robustesse mesurable.

---

### 10.3 Atténuation des attaques par inférence d'appartenance

Limiter la capacité à déterminer si un enregistrement faisait partie des données d'entraînement. La confidentialité différentielle et le masquage des scores de confiance restent les défenses connues les plus efficaces.

 #10.3.1    Level: 1    Role: D
 Vérifiez que la régularisation de l'entropie par requête ou la mise à l'échelle de la température réduit les prédictions excessivement confiantes.
 #10.3.2    Level: 2    Role: D
 Vérifiez que la formation utilise une optimisation différentiellement privée bornée par ε pour les ensembles de données sensibles.
 #10.3.3    Level: 2    Role: V
 Vérifiez que les simulations d'attaque (modèle fantôme ou boîte noire) montrent une AUC d'attaque ≤ 0,60 sur les données mises de côté.

---

### 10.4 Résistance à l'inversion de modèle

Empêcher la reconstitution des attributs privés. Des enquêtes récentes mettent en avant la troncature des sorties et les garanties de confidentialité différentielle (DP) comme des défenses pratiques.

 #10.4.1    Level: 1    Role: D
 Vérifiez que les attributs sensibles ne sont jamais directement affichés ; lorsque cela est nécessaire, utilisez des catégories ou des transformations unidirectionnelles.
 #10.4.2    Level: 1    Role: D/V
 Vérifiez que les limites de fréquence des requêtes régulent les requêtes adaptatives répétées provenant du même principal.
 #10.4.3    Level: 2    Role: D
 Vérifiez que le modèle est entraîné avec un bruit préservant la confidentialité.

---

### 10.5 Défense contre l'extraction de modèle

Détecter et empêcher le clonage non autorisé. Le tatouage numérique (watermarking) et l’analyse des motifs de requêtes sont recommandés.

 #10.5.1    Level: 1    Role: D
 Vérifiez que les passerelles d'inférence appliquent des limites de débit globales et par clé API ajustées au seuil de mémorisation du modèle.
 #10.5.2    Level: 2    Role: D/V
 Vérifiez que les statistiques d'entropie de requête et de pluralité d'entrée alimentent un détecteur d'extraction automatisée.
 #10.5.3    Level: 2    Role: V
 Vérifiez que les filigranes fragiles ou probabilistes peuvent être prouvés avec p < 0,01 en ≤ 1 000 requêtes contre un clone suspecté.
 #10.5.4    Level: 3    Role: D
 Vérifiez que les clés de tatouage numérique et les ensembles de déclencheurs sont stockés dans un module de sécurité matériel et renouvelés chaque année.
 #10.5.5    Level: 3    Role: V
 Vérifiez que les événements d'alerte d'extraction incluent les requêtes incriminées et sont intégrés aux scénarios de réponse aux incidents.

---

### 10.6 Détection de données empoisonnées lors de l'inférence

Identifier et neutraliser les entrées compromises ou empoisonnées.

 #10.6.1    Level: 1    Role: D
 Vérifiez que les entrées passent par un détecteur d'anomalies (par exemple, STRIP, score de cohérence) avant l’inférence du modèle.
 #10.6.2    Level: 1    Role: V
 Vérifiez que les seuils du détecteur sont ajustés sur des ensembles de validation propres/empoisonnés afin d’obtenir moins de 5 % de faux positifs.
 #10.6.3    Level: 2    Role: D
 Vérifiez que les entrées signalées comme empoisonnées déclenchent des blocages temporaires et des procédures de révision humaine.
 #10.6.4    Level: 2    Role: V
 Vérifiez que les détecteurs sont soumis à des tests de résistance avec des attaques de porte dérobée adaptatives et sans déclencheur.
 #10.6.5    Level: 3    Role: D
 Vérifiez que les métriques d'efficacité de détection sont enregistrées et réévaluées périodiquement avec des informations actualisées sur les menaces.

---

### 10.7 Adaptation dynamique de la politique de sécurité

Mises à jour des politiques de sécurité en temps réel basées sur le renseignement sur les menaces et l'analyse comportementale.

 #10.7.1    Level: 1    Role: D/V
 Vérifiez que les politiques de sécurité peuvent être mises à jour dynamiquement sans redémarrage de l’agent tout en maintenant l’intégrité de la version de la politique.
 #10.7.2    Level: 2    Role: D/V
 Vérifiez que les mises à jour de la politique sont signées cryptographiquement par le personnel de sécurité autorisé et validées avant leur application.
 #10.7.3    Level: 2    Role: D/V
 Vérifiez que les modifications dynamiques de la politique sont enregistrées avec des pistes d'audit complètes incluant la justification, les chaînes d'approbation et les procédures de restauration.
 #10.7.4    Level: 3    Role: D/V
 Vérifiez que les mécanismes de sécurité adaptative ajustent la sensibilité de détection des menaces en fonction du contexte de risque et des modèles comportementaux.
 #10.7.5    Level: 3    Role: D/V
 Vérifiez que les décisions d'adaptation de la politique sont explicables et incluent des traces de preuves pour l'examen par l'équipe de sécurité.

---

### 10.8 Analyse de sécurité basée sur la réflexion

Validation de la sécurité par auto-réflexion de l'agent et analyse métacognitive.

 #10.8.1    Level: 1    Role: D/V
 Vérifiez que les mécanismes de réflexion de l'agent incluent une auto-évaluation axée sur la sécurité des décisions et des actions.
 #10.8.2    Level: 2    Role: D/V
 Vérifiez que les sorties de réflexion sont validées pour empêcher la manipulation des mécanismes d'auto-évaluation par des entrées adverses.
 #10.8.3    Level: 2    Role: D/V
 Vérifiez que l'analyse de sécurité métacognitive identifie les biais potentiels, les manipulations ou les compromissions dans les processus de raisonnement des agents.
 #10.8.4    Level: 3    Role: D/V
 Vérifiez que les avertissements de sécurité basés sur la réflexion déclenchent une surveillance renforcée et des workflows d'intervention humaine potentielle.
 #10.8.5    Level: 3    Role: D/V
 Vérifiez que l'apprentissage continu à partir des réflexions sur la sécurité améliore la détection des menaces sans dégrader la fonctionnalité légitime.

---

### 10.9 Sécurité de l'évolution et de l'auto-amélioration

Contrôles de sécurité pour les systèmes agents capables d'auto-modification et d'évolution.

 #10.9.1    Level: 1    Role: D/V
 Vérifiez que les capacités d'auto-modification sont limitées aux zones sécurisées désignées avec des frontières de vérification formelles.
 #10.9.2    Level: 2    Role: D/V
 Vérifiez que les propositions d'évolution font l'objet d'une évaluation de l'impact sur la sécurité avant leur mise en œuvre.
 #10.9.3    Level: 2    Role: D/V
 Vérifiez que les mécanismes d'auto-amélioration incluent des capacités de restauration avec vérification d'intégrité.
 #10.9.4    Level: 3    Role: D/V
 Vérifiez que la sécurité de la méta-apprentissage empêche la manipulation adversariale des algorithmes d'amélioration.
 #10.9.5    Level: 3    Role: D/V
 Vérifiez que l'auto-amélioration récursive est limitée par des contraintes de sécurité formelles avec des preuves mathématiques de convergence.

---

#### Références

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Protection de la vie privée et gestion des données personnelles

### Objectif de Contrôle

Maintenir des garanties strictes en matière de confidentialité tout au long du cycle de vie de l'IA—collecte, entraînement, inférence et réponse aux incidents—afin que les données personnelles ne soient traitées qu'avec un consentement clair, une portée minimale nécessaire, une suppression vérifiable et des garanties formelles de confidentialité.

---

### 11.1 Anonymisation et minimisation des données

 #11.1.1    Level: 1    Role: D/V
 Vérifiez que les identifiants directs et quasi-identifiants sont supprimés ou hachés.
 #11.1.2    Level: 2    Role: D/V
 Vérifiez que les audits automatisés mesurent la k-anonymat/l-diversité et alertent lorsque les seuils descendent en dessous de la politique.
 #11.1.3    Level: 2    Role: V
 Vérifiez que les rapports d'importance des caractéristiques du modèle prouvent qu'il n'y a pas de fuite d'identifiant au-delà d'une information mutuelle ε = 0,01.
 #11.1.4    Level: 3    Role: V
 Vérifier que des preuves formelles ou une certification par données synthétiques démontrent un risque de ré-identification ≤ 0,05 même en cas d’attaques par recoupement.

---

### 11.2 Droit à l'oubli et application de la suppression

 #11.2.1    Level: 1    Role: D/V
 Vérifiez que les demandes de suppression de données personnelles se propagent aux jeux de données bruts, points de contrôle, embeddings, journaux et sauvegardes dans les accords de niveau de service en moins de 30 jours.
 #11.2.2    Level: 2    Role: D
 Vérifiez que les routines de « désapprentissage machine » réentraînent physiquement ou approximativement la suppression en utilisant des algorithmes de désapprentissage certifiés.
 #11.2.3    Level: 2    Role: V
 Vérifiez que l'évaluation par modèle miroir prouve que les enregistrements oubliés influencent moins de 1 % des sorties après l'effacement.
 #11.2.4    Level: 3    Role: V
 Vérifiez que les événements de suppression sont consignés de manière immuable et sont auditable pour les régulateurs.

---

### 11.3 Mesures de protection de la confidentialité différentielle

 #11.3.1    Level: 2    Role: D/V
 Vérifiez que les tableaux de bord de comptabilisation des pertes de confidentialité alertent lorsque le cumul ε dépasse les seuils définis par la politique.
 #11.3.2    Level: 2    Role: V
 Vérifiez que les audits de confidentialité en boîte noire estiment ε̂ à moins de 10 % de la valeur déclarée.
 #11.3.3    Level: 3    Role: V
 Vérifiez que les preuves formelles couvrent tous les ajustements fins post-formation et les embeddings.

---

### 11.4 Limitation de l'objectif et protection contre la dérive du périmètre

 #11.4.1    Level: 1    Role: D
 Vérifiez que chaque ensemble de données et point de contrôle de modèle porte une étiquette de but lisible par machine alignée sur le consentement initial.
 #11.4.2    Level: 1    Role: D/V
 Vérifiez que les moniteurs d'exécution détectent les requêtes incompatibles avec l'objectif déclaré et déclenchent un refus doux.
 #11.4.3    Level: 3    Role: D
 Vérifiez que les contrôles policy-as-code bloquent le redéploiement des modèles vers de nouveaux domaines sans examen DPIA.
 #11.4.4    Level: 3    Role: V
 Vérifiez que les preuves formelles de traçabilité démontrent que chaque cycle de vie des données personnelles reste dans le cadre du consentement donné.

---

### 11.5 Gestion du consentement et suivi de la base légale

 #11.5.1    Level: 1    Role: D/V
 Vérifiez qu'une plateforme de gestion du consentement (CMP) enregistre le statut d'acceptation, la finalité et la durée de conservation pour chaque sujet de données.
 #11.5.2    Level: 2    Role: D
 Vérifiez que les API exposent des jetons de consentement ; les modèles doivent valider la portée du jeton avant l'inférence.
 #11.5.3    Level: 2    Role: D/V
 Vérifiez que le refus ou le retrait du consentement interrompt les pipelines de traitement dans un délai de 24 heures.

---

### 11.6 Apprentissage Fédéré avec Contrôles de Confidentialité

 #11.6.1    Level: 1    Role: D
 Vérifiez que les mises à jour des clients utilisent l'ajout de bruit de confidentialité différentielle locale avant l'agrégation.
 #11.6.2    Level: 2    Role: D/V
 Vérifiez que les métriques d'entraînement sont différentiallement privées et ne révèlent jamais la perte d'un seul client.
 #11.6.3    Level: 2    Role: V
 Vérifiez que l’agrégation résistante au empoisonnement (par exemple, Krum/Moyenne Élaguée) est activée.
 #11.6.4    Level: 3    Role: V
 Vérifiez que les preuves formelles démontrent un budget global d'ε avec une perte d'utilité inférieure à 5.

---

#### Références

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Surveillance, journalisation et détection d'anomalies

### Objectif de contrôle

Cette section fournit les exigences pour assurer une visibilité en temps réel et médico-légale sur ce que le modèle et les autres composants d'IA voient, font et renvoient, afin que les menaces puissent être détectées, triées et analysées.

### C12.1 Enregistrement des Requêtes et Réponses

 #12.1.1    Level: 1    Role: D/V
 Vérifiez que toutes les invites utilisateur et toutes les réponses du modèle sont enregistrées avec les métadonnées appropriées (par exemple, horodatage, ID utilisateur, ID de session, version du modèle).
 #12.1.2    Level: 1    Role: D/V
 Vérifiez que les journaux sont stockés dans des référentiels sécurisés et accessibles avec des politiques de rétention appropriées et des procédures de sauvegarde.
 #12.1.3    Level: 1    Role: D/V
 Vérifiez que les systèmes de stockage des journaux mettent en œuvre un chiffrement au repos et en transit pour protéger les informations sensibles contenues dans les journaux.
 #12.1.4    Level: 1    Role: D/V
 Vérifiez que les données sensibles dans les invites et les résultats sont automatiquement redigées ou masquées avant la journalisation, avec des règles de redaction configurables pour les informations personnelles identifiables (IPI), les identifiants et les informations propriétaires.
 #12.1.5    Level: 2    Role: D/V
 Vérifiez que les décisions politiques et les actions de filtrage de sécurité sont enregistrées avec suffisamment de détails pour permettre l'audit et le débogage des systèmes de modération de contenu.
 #12.1.6    Level: 2    Role: D/V
 Vérifiez que l’intégrité des journaux est protégée, par exemple par des signatures cryptographiques ou un stockage en écriture seule.

---

### C12.2 Détection des abus et alertes

 #12.2.1    Level: 1    Role: D/V
 Vérifiez que le système détecte et alerte sur les schémas de contournement connus, les tentatives d'injection de prompt et les entrées adversariales en utilisant une détection basée sur les signatures.
 #12.2.2    Level: 1    Role: D/V
 Vérifiez que le système s'intègre aux plateformes existantes de Gestion des Informations et des Événements de Sécurité (SIEM) en utilisant des formats de journaux et des protocoles standards.
 #12.2.3    Level: 2    Role: D/V
 Vérifiez que les événements de sécurité enrichis incluent un contexte spécifique à l'IA, tel que les identifiants de modèle, les scores de confiance et les décisions des filtres de sécurité.
 #12.2.4    Level: 2    Role: D/V
 Vérifiez que la détection d'anomalies comportementales identifie les schémas de conversation inhabituels, les tentatives de réessai excessives ou les comportements de sondage systématiques.
 #12.2.5    Level: 2    Role: D/V
 Vérifiez que les mécanismes d’alerte en temps réel notifient les équipes de sécurité lorsque des violations potentielles de la politique ou des tentatives d’attaque sont détectées.
 #12.2.6    Level: 2    Role: D/V
 Vérifiez que des règles personnalisées sont incluses pour détecter les modèles de menaces spécifiques à l'IA, notamment les tentatives coordonnées de jailbreak, les campagnes d'injection de prompt et les attaques d'extraction de modèle.
 #12.2.7    Level: 3    Role: D/V
 Vérifiez que les flux de travail automatisés de réponse aux incidents peuvent isoler les modèles compromis, bloquer les utilisateurs malveillants et escalader les événements de sécurité critiques.

---

### C12.3 Détection de la dérive du modèle

 #12.3.1    Level: 1    Role: D/V
 Vérifiez que le système suit les mesures de performance de base telles que la précision, les scores de confiance, la latence et les taux d'erreur à travers les versions du modèle et les périodes de temps.
 #12.3.2    Level: 2    Role: D/V
 Vérifiez que les alertes automatisées se déclenchent lorsque les métriques de performance dépassent les seuils de dégradation prédéfinis ou s'écartent significativement des valeurs de référence.
 #12.3.3    Level: 2    Role: D/V
 Vérifiez que les systèmes de détection d’hallucinations identifient et signalent les cas où les sorties du modèle contiennent des informations factuellement incorrectes, incohérentes ou fabriquées.

---

### C12.4 Télémétrie des performances et du comportement

 #12.4.1    Level: 1    Role: D/V
 Vérifiez que les métriques opérationnelles, y compris la latence des requêtes, la consommation de jetons, l'utilisation de la mémoire et le débit, sont continuellement collectées et surveillées.
 #12.4.2    Level: 1    Role: D/V
 Vérifiez que les taux de réussite et d'échec sont suivis avec une catégorisation des types d'erreurs et de leurs causes profondes.
 #12.4.3    Level: 2    Role: D/V
 Vérifiez que la surveillance de l'utilisation des ressources inclut l'utilisation du GPU/CPU, la consommation de mémoire et les besoins en stockage, avec des alertes en cas de dépassement des seuils.

---

### C12.5 Planification et exécution de la réponse aux incidents d'IA

 #12.5.1    Level: 1    Role: D/V
 Vérifiez que les plans de réponse aux incidents traitent spécifiquement des événements de sécurité liés à l'IA, y compris la compromission de modèles, l'empoisonnement des données et les attaques adversariales.
 #12.5.2    Level: 2    Role: D/V
 Vérifiez que les équipes de réponse aux incidents ont accès à des outils judiciaires spécifiques à l'IA et à une expertise pour enquêter sur le comportement des modèles et les vecteurs d'attaque.
 #12.5.3    Level: 3    Role: D/V
 Vérifiez que l'analyse post-incident inclut les considérations de réentraînement du modèle, les mises à jour des filtres de sécurité et l'intégration des leçons apprises dans les contrôles de sécurité.

---

### C12.5 Détection de la dégradation des performances de l'IA

Surveiller et détecter la dégradation des performances et de la qualité du modèle d'IA au fil du temps.

 #12.5.1    Level: 1    Role: D/V
 Vérifiez que la précision, la exactitude, le rappel et les scores F1 du modèle sont continuellement suivis et comparés aux seuils de référence.
 #12.5.2    Level: 1    Role: D/V
 Vérifiez que la détection de dérive des données surveille les changements dans la distribution des entrées pouvant affecter les performances du modèle.
 #12.5.3    Level: 2    Role: D/V
 Vérifiez que la détection de la dérive de concept identifie les changements dans la relation entre les entrées et les sorties attendues.
 #12.5.4    Level: 2    Role: D/V
 Vérifiez que la dégradation des performances déclenche des alertes automatisées et initie les workflows de réentraînement ou de remplacement du modèle.
 #12.5.5    Level: 3    Role: V
 Vérifiez que l'analyse des causes profondes de la dégradation corrèle les baisses de performance avec les changements de données, les problèmes d'infrastructure ou les facteurs externes.

---

### C12.6 Visualisation du DAG et Sécurité du Flux de Travail

Protéger les systèmes de visualisation des flux de travail contre les fuites d'informations et les attaques de manipulation.

 #12.6.1    Level: 1    Role: D/V
 Vérifiez que les données de visualisation du DAG sont nettoyées pour supprimer les informations sensibles avant le stockage ou la transmission.
 #12.6.2    Level: 1    Role: D/V
 Vérifiez que les contrôles d'accès à la visualisation des workflows garantissent que seuls les utilisateurs autorisés peuvent voir les chemins de décision des agents et les traces de raisonnement.
 #12.6.3    Level: 2    Role: D/V
 Vérifiez que l'intégrité des données du DAG est protégée par des signatures cryptographiques et des mécanismes de stockage infalsifiables.
 #12.6.4    Level: 2    Role: D/V
 Vérifiez que les systèmes de visualisation de flux de travail mettent en œuvre une validation des entrées pour prévenir les attaques par injection via des données de nœud ou d’arête façonnées.
 #12.6.5    Level: 3    Role: D/V
 Vérifiez que les mises à jour en temps réel des DAG sont soumises à une limitation de débit et validées pour prévenir les attaques par déni de service sur les systèmes de visualisation.

---

### C12.7 Surveillance proactive du comportement en matière de sécurité

Détection et prévention des menaces de sécurité par l'analyse proactive du comportement des agents.

 #12.7.1    Level: 1    Role: D/V
 Vérifiez que les comportements des agents proactifs sont validés en matière de sécurité avant exécution, avec intégration de l’évaluation des risques.
 #12.7.2    Level: 2    Role: D/V
 Vérifiez que les déclencheurs d'initiative autonome incluent l'évaluation du contexte de sécurité et l'analyse du paysage des menaces.
 #12.7.3    Level: 2    Role: D/V
 Vérifiez que les schémas de comportement proactif sont analysés pour leurs implications potentielles en matière de sécurité et leurs conséquences imprévues.
 #12.7.4    Level: 3    Role: D/V
 Vérifiez que les actions proactives critiques pour la sécurité nécessitent des chaînes d'approbation explicites avec des pistes d'audit.
 #12.7.5    Level: 3    Role: D/V
 Vérifiez que la détection d'anomalies comportementales identifie les écarts dans les schémas des agents proactifs pouvant indiquer une compromission.

---

### Références

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Supervision Humaine, Responsabilité et Gouvernance

### Objectif de contrôle

Ce chapitre fournit des exigences pour maintenir la supervision humaine et des chaînes de responsabilité claires dans les systèmes d'IA, garantissant l'explicabilité, la transparence et la gestion éthique tout au long du cycle de vie de l'IA.

---

### C13.1 Mécanismes d'arrêt d'urgence et de contournement

Fournir des procédures d'arrêt ou de retour en arrière lorsque des comportements non sécurisés du système d'IA sont observés.

 #13.1.1    Level: 1    Role: D/V
 Vérifiez qu'un mécanisme d'interrupteur manuel existe pour arrêter immédiatement l'inférence et les sorties du modèle d'IA.
 #13.1.2    Level: 1    Role: D
 Vérifiez que les contrôles de remplacement sont accessibles uniquement au personnel autorisé.
 #13.1.3    Level: 3    Role: D/V
 Vérifiez que les procédures de restauration peuvent revenir aux versions précédentes du modèle ou aux opérations en mode sûr.
 #13.1.4    Level: 3    Role: V
 Vérifiez que les mécanismes de dérogation sont testés régulièrement.

---

### C13.2 Points de contrôle de la décision avec intervention humaine

Exiger des approbations humaines lorsque les enjeux dépassent les seuils de risque prédéfinis.

 #13.2.1    Level: 1    Role: D/V
 Vérifiez que les décisions AI à haut risque nécessitent une approbation humaine explicite avant leur exécution.
 #13.2.2    Level: 1    Role: D
 Vérifiez que les seuils de risque sont clairement définis et déclenchent automatiquement des workflows de révision humaine.
 #13.2.3    Level: 2    Role: D
 Vérifiez que les décisions sensibles au facteur temps disposent de procédures de secours lorsque l'approbation humaine ne peut être obtenue dans les délais requis.
 #13.2.4    Level: 3    Role: D/V
 Vérifiez que les procédures d'escalade définissent des niveaux d'autorité clairs pour les différents types de décisions ou catégories de risques, le cas échéant.

---

### C13.3 Chaîne de Responsabilité et Auditabilité

Enregistrer les actions de l'opérateur et les décisions du modèle.

 #13.3.1    Level: 1    Role: D/V
 Vérifiez que toutes les décisions du système d'IA et les interventions humaines sont enregistrées avec des horodatages, les identités des utilisateurs et la justification des décisions.
 #13.3.2    Level: 2    Role: D
 Vérifiez que les journaux d'audit ne peuvent pas être altérés et qu'ils incluent des mécanismes de vérification de l'intégrité.

---

### C13.4 Techniques d'IA explicable

Importance des caractéristiques de surface, contre-factuels et explications locales.

 #13.4.1    Level: 1    Role: D/V
 Vérifiez que les systèmes d'IA fournissent des explications de base pour leurs décisions dans un format lisible par l'homme.
 #13.4.2    Level: 2    Role: V
 Vérifiez que la qualité des explications est validée par des études d'évaluation humaine et des métriques.
 #13.4.3    Level: 3    Role: D/V
 Vérifiez que les scores d'importance des caractéristiques ou les méthodes d'attribution (SHAP, LIME, etc.) sont disponibles pour les décisions critiques.
 #13.4.4    Level: 3    Role: V
 Vérifiez que les explications contrefactuelles montrent comment les entrées pourraient être modifiées pour changer les résultats, si cela est applicable au cas d'utilisation et au domaine.

---

### C13.5 Fiches de modèle et divulgations d'utilisation

Maintenez des fiches de modèle pour l'utilisation prévue, les indicateurs de performance et les considérations éthiques.

 #13.5.1    Level: 1    Role: D
 Vérifiez que les fiches modèles documentent les cas d'utilisation prévus, les limitations et les modes d'échec connus.
 #13.5.2    Level: 1    Role: D/V
 Vérifiez que les métriques de performance pour différents cas d'utilisation applicables sont divulguées.
 #13.5.3    Level: 2    Role: D
 Vérifiez que les considérations éthiques, les évaluations des biais, les évaluations de l'équité, les caractéristiques des données d'entraînement et les limitations connues des données d'entraînement sont documentées et mises à jour régulièrement.
 #13.5.4    Level: 2    Role: D/V
 Vérifiez que les fiches de modèle sont contrôlées par version et maintenues tout au long du cycle de vie du modèle avec un suivi des modifications.

---

### C13.6 Quantification de l'incertitude

Propager les scores de confiance ou les mesures d'entropie dans les réponses.

 #13.6.1    Level: 1    Role: D
 Vérifiez que les systèmes d'IA fournissent des scores de confiance ou des mesures d'incertitude avec leurs résultats.
 #13.6.2    Level: 2    Role: D/V
 Vérifiez que les seuils d'incertitude déclenchent un examen humain supplémentaire ou des voies décisionnelles alternatives.
 #13.6.3    Level: 2    Role: V
 Vérifiez que les méthodes de quantification de l'incertitude sont calibrées et validées par rapport aux données de vérité terrain.
 #13.6.4    Level: 3    Role: D/V
 Vérifiez que la propagation de l'incertitude est maintenue tout au long des flux de travail IA en plusieurs étapes.

---

### C13.7 Rapports de Transparence Destinés aux Utilisateurs

Fournir des déclarations périodiques sur les incidents, les dérives et l'utilisation des données.

 #13.7.1    Level: 1    Role: D/V
 Vérifiez que les politiques d'utilisation des données et les pratiques de gestion du consentement des utilisateurs sont clairement communiquées aux parties prenantes.
 #13.7.2    Level: 2    Role: D/V
 Vérifiez que des évaluations de l'impact de l'IA sont réalisées et que les résultats sont inclus dans les rapports.
 #13.7.3    Level: 2    Role: D/V
 Vérifiez que les rapports de transparence publiés régulièrement dévoilent les incidents liés à l'IA et les mesures opérationnelles avec un niveau de détail raisonnable.

#### Références

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Annexe A : Glossaire

Ce glossaire complet fournit des définitions des termes clés liés à l'IA, à l'apprentissage automatique et à la sécurité utilisés dans l'ensemble de l'AISVS afin de garantir la clarté et une compréhension commune.
​
Exemple d'attaque : Une entrée délibérément conçue pour amener un modèle d'IA à commettre une erreur, souvent en ajoutant des perturbations subtiles imperceptibles pour les humains.
​
Robustesse face aux attaques adverses – La robustesse face aux attaques adverses en IA fait référence à la capacité d'un modèle à maintenir ses performances et à résister à la tromperie ou à la manipulation par des entrées malveillantes intentionnellement conçues pour provoquer des erreurs.
​
Agent – Les agents IA sont des systèmes logiciels qui utilisent l'IA pour poursuivre des objectifs et accomplir des tâches au nom des utilisateurs. Ils démontrent des capacités de raisonnement, de planification et de mémoire, et disposent d'un certain niveau d'autonomie pour prendre des décisions, apprendre et s'adapter.
​
IA agentique : systèmes d'IA capables de fonctionner avec un certain degré d'autonomie pour atteindre des objectifs, prenant souvent des décisions et agissant sans intervention humaine directe.
​
Contrôle d'accès basé sur les attributs (ABAC) : un paradigme de contrôle d'accès où les décisions d'autorisation sont basées sur les attributs de l'utilisateur, de la ressource, de l'action et de l'environnement, évalués au moment de la requête.
​
Attaque par porte dérobée : un type d'attaque par empoisonnement de données où le modèle est entraîné à répondre d'une manière spécifique à certains déclencheurs tout en se comportant normalement sinon.
​
Biais : Erreurs systématiques dans les résultats des modèles d'IA pouvant entraîner des résultats injustes ou discriminatoires pour certains groupes ou dans des contextes spécifiques.
​
Exploitation des biais : une technique d'attaque qui tire parti des biais connus dans les modèles d'IA pour manipuler les résultats ou les sorties.
​
Cedar : le langage de politique et le moteur d'Amazon pour des autorisations granulaires utilisées dans la mise en œuvre de l'ABAC pour les systèmes d'IA.
​
Chaîne de pensée : une technique pour améliorer le raisonnement dans les modèles de langage en générant des étapes intermédiaires de raisonnement avant de produire une réponse finale.
​
Disjoncteurs : Mécanismes qui arrêtent automatiquement les opérations du système d'IA lorsque des seuils de risque spécifiques sont dépassés.
​
Fuite de données : exposition non intentionnelle d'informations sensibles via les résultats ou le comportement d'un modèle d'IA.
​
Empoisonnement des données : la corruption délibérée des données d'entraînement afin de compromettre l'intégrité du modèle, souvent pour installer des portes dérobées ou dégrader les performances.
​
Confidentialité différentielle – La confidentialité différentielle est un cadre mathématiquement rigoureux pour la diffusion d'informations statistiques sur les ensembles de données tout en protégeant la vie privée des individus. Elle permet au détenteur des données de partager des tendances agrégées du groupe tout en limitant les informations divulguées sur des individus spécifiques.
​
Embarquements : Représentations vectorielles denses des données (texte, images, etc.) qui capturent le sens sémantique dans un espace à haute dimension.
​
Explicabilité – L'explicabilité en IA est la capacité d'un système d'IA à fournir des raisons compréhensibles par l'humain pour ses décisions et prédictions, offrant ainsi des éclaircissements sur son fonctionnement interne.
​
Intelligence Artificielle Explicable (XAI) : Systèmes d'IA conçus pour fournir des explications compréhensibles par l'humain concernant leurs décisions et comportements, à travers diverses techniques et cadres.
​
Apprentissage Fédéré : Une approche d'apprentissage automatique où les modèles sont entraînés sur plusieurs dispositifs décentralisés contenant des échantillons de données locales, sans échanger les données elles-mêmes.
​
Garde-fous : Contraintes mises en place pour empêcher les systèmes d'IA de produire des résultats nuisibles, biaisés ou autrement indésirables.
​
Hallucination – Une hallucination d'IA fait référence à un phénomène où un modèle d'IA génère des informations incorrectes ou trompeuses qui ne sont pas basées sur ses données d'entraînement ni sur la réalité factuelle.
​
Humain dans la boucle (HITL) : systèmes conçus pour nécessiter une supervision, une vérification ou une intervention humaine à des points décisionnels cruciaux.
​
Infrastructure as Code (IaC) : Gestion et provisionnement de l'infrastructure via du code au lieu de processus manuels, permettant l'analyse de sécurité et des déploiements cohérents.
​
Jailbreak : Techniques utilisées pour contourner les dispositifs de sécurité dans les systèmes d'IA, en particulier dans les grands modèles de langage, afin de produire du contenu interdit.
​
Principe du moindre privilège : le principe de sécurité consistant à accorder uniquement les droits d'accès minimum nécessaires aux utilisateurs et aux processus.
​
LIME (Explications Locales Interprétables Indépendantes du Modèle) : une technique pour expliquer les prédictions de n'importe quel classificateur d'apprentissage automatique en l'approximant localement avec un modèle interprétable.
​
Attaque par inférence d'appartenance : une attaque visant à déterminer si un point de données spécifique a été utilisé pour entraîner un modèle d'apprentissage automatique.
​
MITRE ATLAS : Paysage des menaces adversariales pour les systèmes d'intelligence artificielle ; une base de connaissances sur les tactiques et techniques adversariales contre les systèmes d'IA.
​
Fiche de modèle – Une fiche de modèle est un document qui fournit des informations standardisées sur la performance, les limites, les usages prévus et les considérations éthiques d'un modèle d'IA afin de promouvoir la transparence et le développement responsable de l'IA.
​
Extraction de modèle : une attaque où un adversaire interroge de manière répétée un modèle cible afin de créer une copie fonctionnellement similaire sans autorisation.
​
Inversion de modèle : une attaque qui tente de reconstruire les données d'entraînement en analysant les sorties du modèle.
​
Gestion du cycle de vie du modèle – La gestion du cycle de vie des modèles d'IA est le processus de supervision de toutes les étapes de l'existence d'un modèle d'IA, y compris sa conception, son développement, son déploiement, sa surveillance, sa maintenance et sa mise hors service éventuelle, afin de garantir qu'il reste efficace et aligné sur les objectifs.
​
Empoisonnement de modèle : introduction de vulnérabilités ou de portes dérobées directement dans un modèle pendant le processus d'entraînement.
​
Vol de modèle : Extraire une copie ou une approximation d'un modèle propriétaire par des requêtes répétées.
​
Système multi-agent : un système composé de plusieurs agents d'IA interagissant, chacun pouvant avoir des capacités et des objectifs différents.
​
OPA (Open Policy Agent) : Un moteur de politique open-source qui permet une application unifiée des politiques à travers l'ensemble de la pile.
​
Apprentissage automatique respectueux de la vie privée (PPML) : Techniques et méthodes pour entraîner et déployer des modèles d'apprentissage automatique tout en protégeant la confidentialité des données d'entraînement.
​
Injection de prompt : une attaque où des instructions malveillantes sont intégrées dans les entrées pour contourner le comportement prévu d’un modèle.
​
RAG (Génération Augmentée par Recherche) : Une technique qui améliore les grands modèles de langage en récupérant des informations pertinentes à partir de sources de connaissances externes avant de générer une réponse.
​
Red-Teaming : La pratique de tester activement les systèmes d'IA en simulant des attaques adverses afin d'identifier les vulnérabilités.
​
SBOM (Liste des composants logiciels) : Un enregistrement formel contenant les détails et les relations dans la chaîne d'approvisionnement des différents composants utilisés dans la construction de logiciels ou de modèles d'IA.
​
SHAP (Explications Additives de Shapley) : Une approche basée sur la théorie des jeux pour expliquer la sortie de n'importe quel modèle d'apprentissage automatique en calculant la contribution de chaque caractéristique à la prédiction.
​
Attaque sur la chaîne d'approvisionnement : compromettre un système en ciblant des éléments moins sécurisés de sa chaîne d'approvisionnement, tels que des bibliothèques tierces, des jeux de données ou des modèles pré-entraînés.
​
Apprentissage par transfert : une technique où un modèle développé pour une tâche est réutilisé comme point de départ pour un modèle destiné à une seconde tâche.
​
Base de données vectorielle : une base de données spécialisée conçue pour stocker des vecteurs haute dimension (embeddings) et effectuer des recherches de similarité efficaces.
​
Analyse de vulnérabilités : Outils automatisés qui identifient les vulnérabilités de sécurité connues dans les composants logiciels, y compris les frameworks d'IA et leurs dépendances.
​
Filigrane : Techniques pour intégrer des marqueurs imperceptibles dans le contenu généré par l'IA afin de suivre son origine ou de détecter la génération par IA.
​
Vulnérabilité Zero-Day : Une vulnérabilité auparavant inconnue que les attaquants peuvent exploiter avant que les développeurs ne créent et déploient un correctif.

## Annexe B : Références

### TODO

## Annexe C : Gouvernance et documentation de la sécurité de l’IA

### Objectif

Cette annexe fournit les exigences fondamentales pour établir des structures organisationnelles, des politiques et des processus afin de gouverner la sécurité de l'IA tout au long du cycle de vie du système.

---

### Adoption du Cadre de Gestion des Risques en IA (AC.1)

Fournir un cadre formel pour identifier, évaluer et atténuer les risques spécifiques à l’IA tout au long du cycle de vie du système.

 #AC.1.1    Level: 1    Role: D/V
 Vérifiez qu'une méthodologie d'évaluation des risques spécifique à l'IA est documentée et mise en œuvre.
 #AC.1.2    Level: 2    Role: D
 Vérifiez que les évaluations des risques sont effectuées aux points clés du cycle de vie de l'IA et avant toute modification significative.
 #AC.1.3    Level: 3    Role: D/V
 Vérifiez que le cadre de gestion des risques est aligné sur les normes établies (par exemple, le NIST AI RMF).

---

### AC.2 Politique et procédures de sécurité de l'IA

Définir et appliquer des normes organisationnelles pour le développement, le déploiement et l'exploitation sécurisés de l'IA.

 #AC.2.1    Level: 1    Role: D/V
 Vérifiez que des politiques de sécurité de l'IA documentées existent.
 #AC.2.2    Level: 2    Role: D
 Vérifiez que les politiques sont examinées et mises à jour au moins une fois par an et après des changements importants dans le paysage des menaces.
 #AC.2.3    Level: 3    Role: D/V
 Vérifiez que les politiques couvrent toutes les catégories AISVS et les exigences réglementaires applicables.

---

### AC.3 Rôles et responsabilités pour la sécurité de l'IA

Établir une responsabilité claire pour la sécurité de l'IA à travers toute l'organisation.

 #AC.3.1    Level: 1    Role: D/V
 Vérifiez que les rôles et responsabilités en matière de sécurité de l'IA sont documentés.
 #AC.3.2    Level: 2    Role: D
 Vérifiez que les personnes responsables possèdent une expertise en sécurité appropriée.
 #AC.3.3    Level: 3    Role: D/V
 Vérifiez qu'un comité d'éthique de l'IA ou un conseil de gouvernance est établi pour les systèmes d'IA à haut risque.

---

### AC.4 Application des lignes directrices de l'IA éthique

Assurer que les systèmes d'IA fonctionnent conformément aux principes éthiques établis.

 #AC.4.1    Level: 1    Role: D/V
 Vérifiez que des lignes directrices éthiques pour le développement et le déploiement de l'IA existent.
 #AC.4.2    Level: 2    Role: D
 Vérifiez que des mécanismes sont en place pour détecter et signaler les violations éthiques.
 #AC.4.3    Level: 3    Role: D/V
 Vérifiez que des examens éthiques réguliers des systèmes d'IA déployés sont effectués.

---

### Surveillance de la conformité réglementaire en matière d'IA

Maintenir la vigilance et la conformité aux réglementations évolutives en matière d'IA.

 #AC.5.1    Level: 1    Role: D/V
 Vérifiez que des processus existent pour identifier les réglementations applicables à l'IA.
 #AC.5.2    Level: 2    Role: D
 Vérifiez que la conformité à toutes les exigences réglementaires est évaluée.
 #AC.5.3    Level: 3    Role: D/V
 Vérifiez que les modifications réglementaires déclenchent des examens et des mises à jour en temps utile des systèmes d'IA.

#### Références

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Annexe D : Gouvernance et vérification du codage sécurisé assisté par IA

### Objectif

Ce chapitre définit les contrôles organisationnels de base pour l'utilisation sûre et efficace des outils de codage assistés par IA lors du développement logiciel, garantissant la sécurité et la traçabilité tout au long du cycle de vie du développement logiciel (SDLC).

---

### AD.1 Flux de travail de codage sécurisé assisté par IA

Intégrer les outils d’IA dans le cycle de vie de développement logiciel sécurisé (SSDLC) de l’organisation sans affaiblir les barrières de sécurité existantes.

 #AD.1.1    Level: 1    Role: D/V
 Vérifiez qu'un workflow documenté décrit quand et comment les outils d'IA peuvent générer, refactoriser ou examiner le code.
 #AD.1.2    Level: 2    Role: D
 Vérifiez que le flux de travail correspond à chaque phase du SSDLC (conception, mise en œuvre, revue de code, tests, déploiement).
 #AD.1.3    Level: 3    Role: D/V
 Vérifier que les métriques (par exemple, la densité de vulnérabilité, le temps moyen de détection) sont collectées sur le code produit par l'IA et comparées aux références basées uniquement sur les humains.

---

### AD.2 Qualification des outils d'IA et modélisation des menaces

Assurez-vous que les outils de codage IA soient évalués en termes de capacités de sécurité, de risques et d'impact sur la chaîne d'approvisionnement avant leur adoption.

 #AD.2.1    Level: 1    Role: D/V
 Vérifiez qu'un modèle de menace pour chaque outil d'IA identifie les risques de mauvaise utilisation, d'inversion de modèle, de fuite de données et de chaîne de dépendances.
 #AD.2.2    Level: 2    Role: D
 Vérifiez que les évaluations des outils incluent une analyse statique/dynamique de tous les composants locaux et une évaluation des points de terminaison SaaS (TLS, authentification/autorisation, journalisation).
 #AD.2.3    Level: 3    Role: D/V
 Vérifiez que les évaluations suivent un cadre reconnu et sont réexécutées après des changements majeurs de version.

---

### AD.3 Gestion sécurisée des invites et du contexte

Prévenir la fuite de secrets, de code propriétaire et de données personnelles lors de la construction des invites ou des contextes pour les modèles d'IA.

 #AD.3.1    Level: 1    Role: D/V
 Vérifiez que les directives écrites interdisent l’envoi de secrets, d’informations d’identification ou de données classifiées dans les invites.
 #AD.3.2    Level: 2    Role: D
 Vérifiez que les contrôles techniques (rédaction côté client, filtres de contexte approuvés) suppriment automatiquement les éléments sensibles.
 #AD.3.3    Level: 3    Role: D/V
 Vérifiez que les invites et les réponses sont tokenisées, cryptées pendant le transit et au repos, et que les périodes de conservation respectent la politique de classification des données.

---

### AD.4 Validation du code généré par l’IA

Détecter et corriger les vulnérabilités introduites par la sortie de l'IA avant que le code ne soit fusionné ou déployé.

 #AD.4.1    Level: 1    Role: D/V
 Vérifiez que le code généré par l’IA est toujours soumis à une revue de code humaine.
 #AD.4.2    Level: 2    Role: D
 Vérifiez que les scanners automatiques (SAST/IAST/DAST) s'exécutent sur chaque pull request contenant du code généré par l'IA et bloquent les fusions en cas de découvertes critiques.
 #AD.4.3    Level: 3    Role: D/V
 Vérifiez que les tests de fuzzing différentiel ou les tests basés sur les propriétés prouvent les comportements critiques pour la sécurité (par exemple, la validation des entrées, la logique d'autorisation).

---

### AD.5 Explicabilité et Traçabilité des Suggestions de Code

Fournir aux auditeurs et aux développeurs des explications sur les raisons d'une suggestion et sur son évolution.

 #AD.5.1    Level: 1    Role: D/V
 Vérifiez que les paires prompt/réponse sont enregistrées avec les identifiants de commit.
 #AD.5.2    Level: 2    Role: D
 Vérifiez que les développeurs peuvent afficher des citations du modèle (extraits de formation, documentation) appuyant une suggestion.
 #AD.5.3    Level: 3    Role: D/V
 Vérifiez que les rapports d'explicabilité sont stockés avec les artefacts de conception et référencés dans les revues de sécurité, conformément aux principes de traçabilité de la norme ISO/IEC 42001.

---

### AD.6 Retour continu et ajustement fin du modèle

Améliorer la performance de la sécurité du modèle au fil du temps tout en empêchant la dérive négative.

 #AD.6.1    Level: 1    Role: D/V
 Vérifiez que les développeurs peuvent signaler les suggestions non sécurisées ou non conformes, et que ces signalements sont suivis.
 #AD.6.2    Level: 2    Role: D
 Vérifiez que les retours agrégés alimentent un ajustement périodique ou une génération augmentée par récupération avec des corpus de codage sécurisé vérifiés (par exemple, les Cheat Sheets OWASP).
 #AD.6.3    Level: 3    Role: D/V
 Vérifiez qu'un système d'évaluation en boucle fermée exécute des tests de régression après chaque ajustement fin ; les métriques de sécurité doivent être égales ou supérieures aux références précédentes avant le déploiement.

---

#### Références

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Annexe E : Exemples d'outils et de cadres

### Objectif

Ce chapitre fournit des exemples d'outils et de cadres pouvant soutenir la mise en œuvre ou la satisfaction d'une exigence AISVS donnée. Ceux-ci ne doivent pas être considérés comme des recommandations ou des approbations de la part de l'équipe AISVS ou du projet de sécurité OWASP GenAI.

---

### AE.1 Gouvernance des données de formation et gestion des biais

Outils utilisés pour l'analyse de données, la gouvernance et la gestion des biais.

 #AE.1.1    Section: 1.1
 Outils de gestion d'inventaire des données : des outils de gestion d'inventaire des données tels que...
 #AE.1.2    Section: 1.2
 Chiffrement en transit Utilisez TLS pour les applications basées sur HTTPS, avec des outils tels que openSSL et le module python`ssl`bibliothèque.

---

### AE.2 Validation des entrées utilisateur

Outils pour gérer et valider les entrées utilisateur.

 #AE.2.1    Section: 2.1
 Outils de défense contre l'injection de prompt : Utilisez des outils de garde-fou tels que NeMo de NVIDIA ou Guardrails AI.

---

## Gouvernance des données d'entraînement C1 et gestion des biais

### C1.1 Provenance des données d'entraînement

Maintenez un inventaire vérifiable de tous les ensembles de données, n'acceptez que des sources fiables et consignez chaque modification pour assurer la traçabilité.

 #1.1.1    Level: 1    Role: D/V
 Vérifiez qu’un inventaire à jour de chaque source de données d’entraînement (origine, gestionnaire/propriétaire, licence, méthode de collecte, contraintes d’utilisation prévues et historique de traitement) est maintenu.

