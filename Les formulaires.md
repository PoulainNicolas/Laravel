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

### A. Création du formulaire
```PHP
{{ Form::open(array('action' => 'PostController@store')}}
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

### B. Create

```PHP
<div class="row justify-content-center">
    <div class="col-md-5 section">
    
    {{ Form::open(array('action' => 'PostController@store')) }}
    
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

### B. Update

```PHP
<div class="row justify-content-center">
    <div class="col-md-5 section">
    
    {{ Form::model($post, array('route' => array('Posts.update', $post->id), 'method' => 'patch')) }}

    
    {{ Form::token() }}

  <div class="form-group">
        {{Form::label('title','Title')}}
        {{Form::text('title',$post->title,array('class' => 'form-control','placeholder'=>'Titre'))}}
    </div>

    <div class="form-group">
        {{Form::label('content','content')}}
        {{Form::text('content',$post->content,array('class' => 'form-control','placeholder'=>'Content'))}}
    </div>

    <div class="form-group">
        {{ Form::submit('Enregistrer',array('class' => 'btn btn-warning')) }}
    </div>


    {{ Form::close() }}

    </div>
</div>
```

