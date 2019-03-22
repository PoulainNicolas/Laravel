## 1.Installation

1. Création d'un dossier via le terminal
2. **composer create-project --prefer-dist laravel/laravel NomDuProjet**
3. Modification du fichier .env.example en .env
4. Lancer la commande suivante **php artisan key:generate** afin de générer une clé dans le fichier .env
5. Lancer le projet via la commande ***php artisan serve** Il va générer un lien localhost sous le port 8000 afin de laisser le port 80 disponible afin de travailler sous d'autres projets en même temps <http://127.0.0.1:8000>


## 2. La base de données du projet
1. Création d'une base de donnéés sous PhpMyAdmin
2. Modification du fichier .env (qui se trouve à la racine)
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=app
DB_USERNAME=root
DB_PASSWORD=root
```
3. Modification du fichier database.php
```php
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


