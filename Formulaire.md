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

{{  }}

```
