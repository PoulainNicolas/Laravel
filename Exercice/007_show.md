## 7. Show
### A. Afficher une todo 

#### 1. La fonction show()

```
App\Htpp\Controllers\TodoController
```

```php
public function show($id){
    $todo = Todo::find($id);
    return view('todos.show',compact('todo'));
}
```
Cette fonction va envoyer rediriger l'utilisateur sur la page show avec l'id de la todo

### B. Afficher notre unique todo

Rendez vous sur la page **show.blade.php** du dossier todos

```php
   {{ $todo->name }}
```

### B. Modifions notre fichier **index.blade.php**

```php
<ul>
    @foreach($todos as $todo)
        <li><a href="{{route('todos.show',$todo->id)}}">{{ $todo->name }}</a> => <a href="{{ route('todos.edit',$todo->id) }}">Modifier</a></li>
    @endforeach
</ul>
<a href="{{route('todos.create')}}">Nouvelle todo</a>
```



