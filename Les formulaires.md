## 2. Les formulaires

1. Ouvrir le terminal
```TERMINAL
composer require laravelcollective/html
```

2. Modification du fichier app

Ajouter cette ligne dans les providers
```PHP
Collective\Html\HtmlServiceProvider::class,
```

Ajouter cette ligne dans les alias
```PHP
'Form' => Collective\Html\FormFacade::class,
'Html' => Collective\Html\HtmlFacade::class,
```

## Création du formulaire
```PHP
{{ Form::open(array('action' => 'FooController@store')}}
  // Ajout des éléments du formulaire
{{ Form::close() }}

```

# Les labels
```PHP
{{ Form::label('title','Title) }}

```
# Les inputs
```PHP
{{ Form::text('title,'Title',) }}

```
# Les buttons
```PHP
{{ Form::submit('Envoyer'}}

```

# Attribuer une classe aux éléments de mon formulaire (avec bootstrap par exemple)

Pour attribuer une classe, il faut passer en paramètre un tableau associatif

Exemple:

```PHP
{{ Form::submit('Enregistrer',array('class' => 'btn btn-warning')) }}
```

```PHP
<div class="row justify-content-center">
    <div class="col-md-5 section">
    
    {{ Form::open(array('action' => 'TodoController@store')) }}
    
    {{ Form::token() }}

    <div class="form-group">
        {{Form::label('title','Title')}}
        {{Form::text('title','',array('class' => 'form-control','placeholder'=>'Titre'))}}
    </div>

    <div class="form-group">
        {{Form::label('content','content')}}
        {{Form::text('content','',array('class' => 'form-control','placeholder'=>'Content'))}}
    </div>

    <div class="form-group">
        {{ Form::submit('Enregistrer',array('class' => 'btn btn-warning')) }}
    </div>

    {{ Form::close() }}

    </div>
</div>
```

