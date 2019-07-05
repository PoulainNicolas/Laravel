## 4. Create
### A. Modifier une todo

#### 1. La fonction edit()

```
App\Htpp\Controllers\TodoController
```

```php
public function edit($id){
    $todo = Todo::find($id)
    return view('todos.edit',compact('todo'));
}
```
Cette fonction va envoyer rediriger l'utilisateur sur la page edit avec l'id de la todo

#### 2. la fonction update()

```php
public function update(Request $request,$id){
     $request->validate([
            'name'=> 'required',
        ]);

        $todo = Todo::find($id);
        $todo->name = $request['name'];
        $todo->save();

        return redirect('todos');
}
```

### B. Affichons notre formulaire edit
Rendez vous sur la page **edit.blade.php** du dossier todos

```php
    {{ Form::model($todo, array('route' => array('clients.update', $client->id), 'method' => 'patch')) }}
    
    {{ Form::token() }}

       <div class="form-group">
        {{Form::text('company',$todo->name,array('class' => 'form-control','placeholder'=>'Votre todo'))}}
    </div>

    {{ Form::close() }}
```

### B. Modifions notre fichier **index.blade.php**

```php
<ul>
    @foreach($todos as $todo)
        <li>{{ $todo->name }} => <a href="{{ route('todos.edit',$todo->id) }}">Modifier</a></li>
    @endforeach
</ul>
<a href="{{route('todos.create')}}">Nouvelle todo</a>
```



