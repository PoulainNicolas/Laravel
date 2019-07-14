## 1. Mise en place du projet
Avant de se lancer dans le développement du projet, il faut préparer son environnement de travail.

### A. Télécharger Laravel via composer
```
composer create-project --prefer-dist laravel/laravel todo
cd todo
``` 
### B. Créer sa base donnée (todo) vide

### C. Renomer le fichier .env.example
```
.env.example
.env
```

### D. Modifier le fichier .env et database.php avec vos données
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=TA BASE DE DONNÉES
DB_USERNAME=Identifiant phpmyadmin
DB_PASSWORD=Mot de passe phpmyadmin
```

### E. Générer une clé pour le projet dans le termnial (si le .env n'a pas d'API KEY)
```
php artisan key:generate
```

[Concept](https://github.com/pierrenoel/Laravel/blob/master/Exercice/002_concept.md)
