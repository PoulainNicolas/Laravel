## Les controlleurs
### CRUD
```PHP
php artisan make:controller HomeController --resource
```
Dans le fichier web.php
```PHP
Route::resource('/','HomeController');
```

#### INDEX()
```PHP
$posts = Post::all();
return view('home',compact('posts'));
```
