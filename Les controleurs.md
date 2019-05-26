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

 GET|HEAD  | todo                   | todo.index       | App\Http\Controllers\TodoController@index                              | web          |
|        | POST      | todo                   | todo.store       | App\Http\Controllers\TodoController@store                              | web          |
|        | GET|HEAD  | todo/create            | todo.create      | App\Http\Controllers\TodoController@create                             | web          |
|        | GET|HEAD  | todo/{todo}            | todo.show        | App\Http\Controllers\TodoController@show                               | web          |
|        | PUT|PATCH | todo/{todo}            | todo.update      | App\Http\Controllers\TodoController@update                             | web          |
|        | DELETE    | todo/{todo}            | todo.destroy     | App\Http\Controllers\TodoController@destroy                            | web          |
|        | GET|HEAD  | todo/{todo}/edit       | todo.edit        | App\Http\Controllers\TodoController@edit                               | web   
