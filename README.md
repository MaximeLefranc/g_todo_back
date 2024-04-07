# G Todo List Back API

<kbd>![](./readme/gtodoAPI.png)</kbd>

## Instalation des dépendences
À la racine du projet lancer la commande:
### `composer install` 

## Création de la base de donnée
Créer une base de donnée et un utilisateur avec les pleins droits.

## Connexion à la Base de donnée
Dans le fichier .env renseigner les informations pour la connexion à la base de donnée en décommentant la ligne correspondante au SGBDR utilisé et en indiquant les informations de connexions.

```php
# DATABASE_URL="sqlite:///%kernel.project_dir%/var/data.db"
# DATABASE_URL="mysql://app:!ChangeMe!@127.0.0.1:3306/app?serverVersion=8.0.32&charset=utf8mb4"
# DATABASE_URL="mysql://app:!ChangeMe!@127.0.0.1:3306/app?serverVersion=10.11.2-MariaDB&charset=utf8mb4"
DATABASE_URL="postgresql://app:!ChangeMe!@127.0.0.1:5432/app?serverVersion=16&charset=utf8"
```

Exemple:

```php
DATABASE_URL="mysql://gtodolist:gtodolist@127.0.0.1:3306/gtodolist?serverVersion=10.11.2-MariaDB&charset=utf8mb4"
```

## Migration

Lancer la commande 
`bin/console doctrine:migrations:migrate`  afin de créer les tables dans la base de donnée.

## Création des clés SSL pour le token JWT

Lancer la commende 
`bin/console lexik:jwt:generate-keypair` afin de créer une paire de clés SSL nécésaire à l'utilisation du JWToken afin d'avoir une connexion à l'API sécurisée.

*Deux fichiers (private.pem et public.pem) ont dû se créer dans config/jwt/*

## Lancer le serveur

Lancer la commande `php -S 127.0.0.1:8080 -t public` à la racine du projet afin de lancer le serveur et pouvoir profiter de l'API.

## Installer le front

Cloner le repository [front](https://github.com/MaximeLefranc/g_todo_front), suiver le README.md et profiter de la G-Todo List