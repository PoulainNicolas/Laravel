## 4. Create
### A. Créons une todo

#### 1. La fonction create()

```
App\Htpp\Controllers\TodoController
```

```php
public function create(){
    return view('todos.create');
}
```
Cette fonction permet d'envoyer l'utilisateur vers une page qui va contenir notre formulaire.

#### 2. la fonction store()

```php
public function store(){
     $request->validate([
            'name'=> 'required',
        ]);

        $todo = new Todo;
        $todo->name = $request['name'];
        $todo->save();

        return redirect('todos');
}
```

Cette fonction permet d'une part de valider ce que l'utilisateur rendre comme donnée
par exemple si l'on veut que notre champ name soit unique

```php
'name'=>'required|unique:todos
```

### B. Affichons notre formulaire
Rendez vous sur la page **create.blade.php** du dossier todos

```php
    {{ Form::open(array('action' => 'TodoController@store')) }}
    
    {{ Form::token() }}

    <div class="form-group">
        {{Form::text('name','',array('class' => 'form-control','placeholder'=>'Votre todo'))}}
    </div>

    {{ Form::close() }}
```

[Les formulaires](https://github.com/pierrenoel/Laravel/blob/master/Les%20formulaires.md)

### B. Placer un lien **Nouvelle todo** dans notre fichier **index.blade.php**

```php
<a href="{{route('todos.create')}}">Nouvelle todo</a>
```



