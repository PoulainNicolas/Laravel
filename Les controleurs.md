## 7. Les controlleurs
### CRUD
```PHP
php artisan make:controller PostsController --resource
```
Dans le fichier web.php
```PHP
Route::resource('/','PostsController');
```

#### INDEX()
```PHP
$posts = Post::all();
return view('posts.index',compact('posts'));
```
Cette fonction retourne tous les posts à la vues **index** du sous dossier **posts**
