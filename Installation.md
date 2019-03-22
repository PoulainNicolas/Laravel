## 1. Composer
Composer est un logiciel gestionnaire de dépendances libre écrit en PHP. Il permet à ses utilisateurs de déclarer et d'installer les bibliothèques dont le projet principal a besoin.

1. Installer composer **sudo apt-get install composer**


## 2. Nouveau projet laravel

1. Création d'un dossier via le terminal
2. **composer create-project --prefer-dist laravel/laravel NomDuProjet**
3. Modification du fichier .env.example en .env
4. Lancer la commande suivante **php artisan key:generate** afin de générer une clé dans le fichier .env
5. Lancer le projet via la commande ***php artisan serve** Il va générer un lien localhost sous le port 8000 afin de laisser le port 80 disponible afin de travailler sous d'autres projets en même temps <http://127.0.0.1:8000>


