## 8. Delete
### A. Supprimer une todo

#### 1. La fonction delete()

```
App\Htpp\Controllers\TodoController
```

```php
public function destroy($id){
    $todo = Todo::find($id);
    $todo->delete();
    return redirect('todos');
}
```

### B. Modifions notre fichier **index.blade.php**

```php
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>Todo</th>
      <th>Opérations</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    
    @foreach($todos as $todo)

    <tr>
      <th>{{ $todo->id }}</th>
      <td><a href="{{ route('todos.show',$todo->id) }}">{{ $todo->name }}</a></td>
      <td><a href="{{ route('clients.edit',$client->id) }}"> Modifier</a></td>
      <td>
      {{ Form::model($todo, array('route' => array('todos.destroy', $todo->id), 'method' => 'delete')) }}

      {{ Form::token() }}

      {{ Form::submit('Supprimer',array('class' => 'btn btn-danger')) }}

      {{ Form::close() }}
      </td>
    </tr>
    @endforeach
</table>
```



