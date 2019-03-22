## 4. Les routes

Lorsqu'on affiche une page Web Laravel dans le navigateur, l'URL ne se terminera pas par le nom d'un fichier .html ni .php. Plutôt, il s'agira d'une suite de mots ressemblant à des dossiers et sous-dossiers, comme par exemple http://mondomaine.com/produits/creation.

Laravel fera le lien entre cette suite de mots et une méthode d'action définie dans un contrôleur. Ceci sera réalisé grâce à un système de routage configuré dans Laravel.

Nous allons donc ensemble voir comment écrire des routes. Pour modifier ou ajouter des routes aux projets, il faut modifier le fichier routes/web.php

### 1. Des chaines de caractères
```PHP
Route::get('/', function () {
    return "Hello world";
});
```
Ce bout de code nous indique que lorsque l'utilisateur arrivera sur la page (accueil) du projet soit à la racine, la route lui retournera la chaine de caractère "Hello World".

### 3. Des avec paramètres
```PHP
Route::get('/articles/{n}', function ($n) {
    return "Article n°: " .$n;
});
```
http://127.0.0.1:8000/articles/50
