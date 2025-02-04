# Projet Démonstration Docker et GitHub Actions avec PHP

Ce projet est un exemple démontrant l'utilisation de Docker et GitHub Actions avec une application PHP moderne.
## Technologies Utilisées

- **PHP 8.1** : Dernière version stable de PHP avec ses fonctionnalités modernes
- **Slim Framework** : Framework PHP léger pour créer des APIs REST
- **Composer** : Gestionnaire de dépendances PHP
- **PHPUnit** : Framework de tests unitaires
- **PHP_CodeSniffer** : Outil d'analyse de qualité du code
- **MySQL 8.0** : Système de gestion de base de données
- **Apache** : Serveur web
- **Docker** : Conteneurisation de l'application
- **GitHub Actions** : Pipeline CI/CD

## Structure du Projet

```
.
├── src/
│   └── index.php
├── tests/
│   └── ApiTest.php
├── docker/
│   └── apache.conf
├── composer.json
├── Dockerfile
├── docker-compose.yml
└── .github/
    └── workflows/
        └── ci.yml
```

## Prérequis

- Docker
- Docker Compose
- Git

## Installation et Exécution

1. Cloner le repository :
```bash
git clone [votre-repo]
cd [votre-repo]
```

2. Lancer l'application avec Docker Compose :
```bash
docker-compose up -d
```

3. Accéder à l'application :
Ouvrir un navigateur et aller à `http://localhost:8080`

## Endpoints API

- `GET /` : Message de bienvenue
- `GET /health` : État de l'application
- `GET /info` : Informations sur l'environnement

## Tests

Pour exécuter les tests :
```bash
docker-compose exec web vendor/bin/phpunit
```

## Qualité du Code

Vérification du style de code (PSR-12) :
```bash
docker-compose exec web vendor/bin/phpcs --standard=PSR12 src/
```

## GitHub Actions

Le pipeline CI/CD inclut :
1. **Tests Automatisés** :
   - Validation du composer.json
   - Exécution des tests PHPUnit
   - Vérification du style de code PSR-12

2. **Build et Déploiement** :
   - Construction de l'image Docker
   - Tests de l'application conteneurisée
   - Vérification de la santé du conteneur

## Base de Données

MySQL est inclus et configuré avec :
- Base de données : `demo`
- Utilisateur : `demo`
- Mot de passe : `demo`
- Port : `3306`

## Points d'Apprentissage

Ce projet permet d'apprendre :
1. La conteneurisation d'applications PHP avec Docker
2. L'utilisation de Composer pour la gestion des dépendances
3. La création d'APIs REST avec Slim Framework
4. Les tests unitaires en PHP avec PHPUnit
5. L'intégration continue avec GitHub Actions
6. Les bonnes pratiques de développement PHP (PSR-12)
7. La configuration d'Apache avec PHP
8. L'utilisation de MySQL dans un environnement Docker
