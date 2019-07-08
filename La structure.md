## 3. La structure
```console
|-app
    |-Htpp
        |-Controllers
          PostController.php
    Post.php
|-bootstrap
|-config
    app.php
    auth.php
    broadcasting.php
    ...
    database.php
|-database
    |-migrations
    2014_10_12_000000_create_users_table
|-public
    |-css
    |-img
    |-js
|-resources
    |-assets
        |-js
        |-sass
    |-views
        |-posts
          index.blade.php    
|-routes
  web.php

```

* Les modèles sont placés à la racine du dossier **app**
* Les controlleurs sont placés dans le dossier **app/Http/Controllers**
* Les vues sont placées dans le dossier **resources/views**

Pour inclure du javascript et du css dans un projet laravel, il faut se rendre dans le dossier
**public** et non dans le dossier **resources**

[Les routes](https://github.com/pierrenoel/Laravel/blob/master/Les%20routes.md)