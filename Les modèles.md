## 6. Les modèles
Dans ce chapitre, nous allons voir ce que sont les modèles et à quoi ils servent.
Pour commencer il faut créer un modèle en passant par artisan

```LINUX
php artisan make:model Post
```
En tapant cette commande, laravel vous crée un nouveau fichier "Post" dans le dossier "APP"

```PHP
class Post extends Model
{
    protected $table = 'post'; //

    protected $fillable = array('title,content'); 

    public $timestamps = true;
}
```

Explication

1. **protected $table = 'post'** => on lui indique sur quelle table on désirer travailler
2. **protected $fillable = array('title,content,slug')*** => quelles sont les variables qui vont recevoir des données de la part de l'utilisateur
3. **public $timestamps = true*** => Autorisé d'écrire en base de données l'heure et la date lors de la création ou modification d'un post.

[Les controlleurs](https://github.com/pierrenoel/Laravel/blob/master/Les%20controleurs.md)
