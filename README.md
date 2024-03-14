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

Le code implémente une stratégie de "green code" qui exclut les appels aux microservices de Medecin et Risque lorsque l'utilisateur a le rôle Organisateur. Cette approche vise à améliorer les performances en évitant les traitements superflus lorsque les données des microservices ne sont pas pertinentes pour l'utilisateur concerné. Ainsi, lorsque l'utilisateur est identifié en tant qu'organisateur, seul un appel au microservice Patient est déclenché.

## Utilisation des conteneurs Docker

Chaque microservice est packagé dans un conteneur Docker pour une distribution et un déploiement facile.
