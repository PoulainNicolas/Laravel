## 4. Read
### A. Afficher notre todo 

#### 1. La fonction index()

```
App\Htpp\Controllers\TodoController
```

Rendez-vous dans la fonction index()

```php
public function index(){
    $todos = Todo::all();
    return view('todos.index',compact('todos'));
}
```

#### 2. La vue index

Créer un nouveau dossier dans **resources\views** et nommer-le todo.

```
mkdir todo
cd todo
touch index.blade.php create.blade.php edit.blade.php show.blade.php 
```

#### 3. Se rendre dans le fichier index.blade.php du dossier todo

```php
@foreach($todos as $todo)
    {{ $todo->name }}
@endforeach
```

#### 4. Ajouter nos routes

routes\web.php

```php
Route::resource('/todo','TodoController');

```

#### 4. Lancer le projet

```
php artisan serve
``` 

[Create](https://github.com/pierrenoel/Laravel/blob/master/Exercice/005_create.md)

