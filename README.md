# Microservices Repository

Ce repository contient cinq microservices développés pour différentes fonctionnalités.

## Structure du Repository

- `Microservice-Front` - Gère l'interface utilisateur et interagit avec les autres microservices.
- `Microservice-Gateway` - Fournit une passerelle pour les requêtes entre les microservices et gère l'authentification.
- `Microservice-Patient` - Gère les informations des patients et les opérations CRUD associées.
- `Microservice-Medecin` - Gère les notes médicales attribuées aux patients par les médecins.
- `Microservice-Risque`  - Calcule le risque de diabète pour les patients en fonction de leurs données médicales.

## Description des Microservices

### Microservice-Front

Microservice responsable de l'interface utilisateur. Il communique avec les autres microservices pour afficher les informations aux utilisateurs finaux. Les fonctionnalités principales incluent l'affichage des patients, l'ajout de nouveaux patients, la modification des informations des patients, etc.

### Microservice-Gateway

Microservice servant de point d'entrée central pour toutes les requêtes. Il gère l'authentification des utilisateurs et dirige les requêtes vers les microservices appropriés en fonction des routes définies. Les fonctionnalités comprennent la gestion de l'authentification, le routage des requêtes, etc.

### Microservice-Patient

Microservice responsable de la gestion des informations relatives aux patients. Il permet d'effectuer des opérations CRUD (Création, Lecture, Mise à jour, Suppression) sur les données des patients, telles que l'ajout de nouveaux patients, la mise à jour des informations des patients, la récupération des détails d'un patient spécifique, etc.

### Microservice-Medecin

Microservice chargé de gérer les notes médicales attribuées aux patients par les médecins. Il permet d'ajouter de nouvelles notes médicales, de récupérer les notes associées à un patient spécifique, etc.

### Microservice-Risque

Microservice responsable du calcul du risque de diabète pour les patients en fonction de leurs données médicales. Il récupère les informations pertinentes sur les patients, telles que les données biométriques et les antécédents médicaux, et utilise un algorithme pour calculer le niveau de risque de diabète.

## Contribuer

Les contributions sont les bienvenues! Si vous souhaitez contribuer à l'amélioration de l'un des microservices ou ajouter de nouvelles fonctionnalités, n'hésitez pas à soumettre une pull request.

## Auteurs

Liste des contributeurs ou de l'équipe de développement derrière ces microservices.

## Licence

Indiquez la licence sous laquelle ce repository est distribué. Par exemple, MIT, Apache, etc.
