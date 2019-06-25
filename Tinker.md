## Tinker

Tinker est une interface pour communiquer plus facilement avec la base de données de votre projet.
Pour y accèder, il faut se rendre dans votre projet actuel.

``` php artisan tinker```

### . Afficher toutes les entrées de votre table

#### A. Lister toutes les entrées
```
App\Post::all();
```

#### B. Limiter les entrées
```
App\Post::limit(2)->get();
```

#### C. Afficher la première entrée
```
App\Post::first();
```

#### D. Afficher un article en particulier
```
App\Post::find(2);
```

### 2. Ajouter un nouveau post
```
$post = new App\Post;
$post->title="Mon premier article";
$post->content="Le contenu de mon premier article ";
$post->save();
```
### 3. Modifier un post
```
$post = new App\Post::find(1);
$post->title="Mon premier article modifié";
$post->content="Le contenu de mon premier article modifié";
$post->save();
```
