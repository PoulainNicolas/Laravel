## 3. Blade
Dans le but de structurer nos vues, Laravel inclut depuis sa version 5 un moteur de template. Celui-ci se
nomme **blade**. 

### A. Créer notre template

```
|-Resources
    |-views
    |-posts
        |- index.blade.php
    |-template
        |- app.blade.php
    welcome.blade.php
```

Dans notre ficher app.blade.php, nous allons structurer notre page web.

```
<!DOCTYPE html>
<html>
<head>
    <title>@yield('title')</title>
</head>
...
<body>

<header>...</header>

<section>
    @yield('MainSection');
</section>

<footer>...</footer>

</body>
</html>

```

Dans ce fichier, nous voyons qu'à certains endroits, nous avons un **yield('')**. 
C'est grâce à ce yield que nous allons insérer notre contenu de manière dynamique.

### A. Implenter du contenu

```
resources/posts/index.blade.php
```

``` 
@section('title','mon site web')

@section('content')
    <p>Hello world</p>
@endsection

```
