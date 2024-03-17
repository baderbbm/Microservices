# Microservices Repository

Ce repository contient cinq microservices développés pour différentes fonctionnalités.

## Structure du Repository

- `Microservice-Front` - Gère l'interface utilisateur et interagit avec les autres microservices.
- `Microservice-Gateway` - Fournit une passerelle pour les requêtes entre les microservices et gère l'authentification.
- `Microservice-Patient` - Gère les informations des patients et les opérations associées.
- `Microservice-Medecin` - Gère les notes médicales attribuées aux patients par les médecins.
- `Microservice-Risque`  - Calcule le risque de diabète pour les patients en fonction de leurs données médicales.

## Description des Microservices

### Microservice-Front

Microservice responsable de l'interface utilisateur. Il communique avec les autres microservices pour afficher les informations aux utilisateurs finaux.

### Microservice-Gateway

Microservice servant de point d'entrée central pour toutes les requêtes. Il gère l'authentification des utilisateurs et dirige les requêtes vers les microservices appropriés en fonction des routes définies. Les fonctionnalités comprennent la gestion de l'authentification, le routage des requêtes, etc.

### Microservice-Patient

Microservice responsable de la gestion des informations relatives aux patients. Il permet d'effectuer des opérations telles que l'ajout de nouveaux patients, la mise à jour des informations des patients et la récupération des détails d'un patient spécifique.

### Microservice-Medecin

Microservice chargé de gérer les notes médicales attribuées aux patients par les médecins. Il permet d'ajouter de nouvelles notes médicales et de récupérer les notes associées à un patient spécifique.

### Microservice-Risque

Microservice responsable du calcul du risque de diabète pour les patients en fonction de leurs données médicales. Il récupère les informations pertinentes sur les patients, telles que les données biométriques et les antécédents médicaux, et utilise un algorithme pour calculer le niveau de risque de diabète.

### Green Code

Dans le cadre de mes propositions, j'ai identifié des opportunités d'optimisation au sein du projet, en visant spécifiquement à minimiser l'espace de stockage. Par exemple, dans la table MongoDB hébergée dans le microservice Medecin, le champ "patient" semble redondant puisque chaque entrée est déjà identifiée de manière unique par le champ "patId". Ainsi, pour rationaliser cette base de données, nous pourrions envisager de supprimer le champ "patient" sans compromettre l'intégrité des données. Cette action aurait pour effet de réduire la taille des entrées et de simplifier leur structure, tout en préservant la clarté et la cohérence des informations. Cette approche s'inscrit parfaitement dans une perspective de "Green Code", visant à optimiser l'efficacité des systèmes informatiques tout en réduisant leur impact environnemental grâce à des pratiques de programmation plus efficientes.

De plus, cette proposition est cohérente avec la configuration de la table "service.patient" dans la base de données MySQL, hébergée dans le microservice Patient. Dans cette structure, les détails des patients sont consignés de manière exhaustive avec leurs attributs respectifs, ce qui permet une gestion plus efficace et précise des données médicales. Il est pertinent de noter que le champ "patient" dans MongoDB correspond au champ "nom" dans la base de données MySQL, assurant ainsi une cohérence et une intégration harmonieuse entre les différents composants du système.

Dans le microservice Risque, j'envisage d'adopter une approche où les appels aux autres microservices, tels que Patient et Médecin, ne seraient pas systématiques pour chaque requête du praticien, mais seraient effectués de manière conditionnelle, basée sur un timeout. Mon objectif est de minimiser le nombre d'appels afin de respecter les principes du "green code".

Quant à ma contribution, j'ai déployé une stratégie de "green code" au sein du microservice Front excluant les appels aux microservices de Medecin et Risque lorsque l'utilisateur a le rôle Organisateur. Cette approche vise à améliorer les performances en évitant les traitements superflus lorsque les données des microservices ne sont pas pertinentes pour l'utilisateur concerné. Ainsi, lorsque l'utilisateur est identifié en tant qu'organisateur, seul un appel au microservice Patient est déclenché.

## Utilisation des conteneurs Docker

Chaque microservice est packagé dans un conteneur Docker pour une distribution et un déploiement facile.
