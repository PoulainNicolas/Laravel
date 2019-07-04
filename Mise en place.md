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

```PHP
  'mysql' => [
            'driver' => 'mysql',
            'host' => env('DB_HOST', '127.0.0.1'),
            'port' => env('DB_PORT', '3306'),
            'database' => env('DB_DATABASE', 'forge'),
            'username' => env('DB_USERNAME', 'forge'),
            'password' => env('DB_PASSWORD', ''),
            'unix_socket' => env('DB_SOCKET', ''),
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
            'prefix' => '',
            'strict' => true,
            'engine' => null,
        ],
```

### E. Générer une clé pour le projet dans le termnial
```
php artisan key:generate
```
