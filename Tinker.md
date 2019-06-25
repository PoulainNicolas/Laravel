## Tinker

Tinker est une interface pour communiquer plus facilement avec la base de données de votre projet.
Pour y accèder, il faut se rendre dans votre projet actuel.

``` php artisan tinker```

### 1. Afficher toutes les entrées de votre table
```
App\Post::all();
```

### 2. Ajouter un nouveau post
```
$post = new App\Post;
$post->title="Mon premier article";
$post->content="Le contenu de mon premier article ";
$post->save();
```
