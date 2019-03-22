## 1. Installation

### 1. Composer
Composer est un logiciel gestionnaire de dépendances libre écrit en PHP. Il permet à ses utilisateurs de déclarer et d'installer les bibliothèques dont le projet principal a besoin.

1. Installer composer **sudo apt-get install composer**


### 2. Nouveau projet laravel

1. Création d'un dossier via le terminal
2. **composer create-project --prefer-dist laravel/laravel NomDuProjet**
3. Modification du fichier .env.example en .env
4. Exécution de la commande suivante **php artisan key:generate** afin de générer une clé dans le fichier .env
5. Exécution de la commande suivante **php artisan serve** Il va générer un lien localhost sous un autre port (ex:8000) afin de laisser le port 80 disponible afin de travailler sous d'autres projets en même temps.

