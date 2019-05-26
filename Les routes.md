## 4. Les routes

Les urls de mon site se font de cette sorte: monsite.be/controlleur/action

Exemple: http://mondomaine.com/post/create.

Laravel fait donc le lien entre cette suite de mots et une méthode d'action définie dans un contrôleur. Ceci est réalisé grâce à un système de routage configuré dans Laravel.

Nous allons donc ensemble voir comment écrire des routes. Pour modifier ou ajouter des routes aux projets, il faut modifier le fichier routes/web.php

### 1. Des chaines de caractères
```PHP
Route::get('/', function () {
    return "Hello world";
});
```
Ce bout de code nous indique que lorsque l'utilisateur arrive sur la page (accueil) du projet soit à la racine, la route lui retourne la chaine de caractère "Hello World".

### 3. Des avec paramètres
```PHP
Route::get('/articles/{n}', function ($n) {
    return "Article n°: " .$n;
});
```
cette url http://127.0.0.1:8000/articles/50 retourne "Article n° 50"

### 4. Les regex

```PHP
Route::get('/articles/{n}', function ($n) {
    return "Article n°: " .$n;
})->where('n','[0-9]+');
```

```PHP
Route::get('/post/{category}/{article}',function($category,$article){
    return '/post/' .$category . '/' . $article;
})->where(['category' => '[a-zA-Z]+','article' => '[a-zA-Z]+']);
```

la function where permet de parser les informations reçues via un regex, dans notre cas, il va prendre une infinité de chiffres uniquement.

### 5. Les vues
Jusqu'à présent, nous avons vu comment passer des paramètres vers une autre page. Cependant, on peut également passer une vue soit une page.

```PHP
Route::get('post',function(){
    return view('post');
});
```
### 6. Vues et paramètres

```PHP
Route::get('user/{name}',function(){
    return view('post',compact('name');
});
```
