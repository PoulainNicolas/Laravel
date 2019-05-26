## 5. Les migrations
Dans ce chapitre, nous allons voir comment créer une table via une migration puis comment l'importer dans notre base de données.

Pour commencer, nous allons demander à artisan de nous créer une migration "create_post_table

```linux
php artisan make:migration create_post_table
```

A l'interieur de ce fichier (database/migrations), vous avez deux fonctions:
1. la fonction UP : Initialisation et description de la table user
2. la fonction DOWN : Suppression de la table User (Via le terminal)

Dans la fonction UP, il va falloir écrire tous les champs de la table User

```PHP
   public function up()
    {
        Schema::create('post', function (Blueprint $table) {
            $table->increments('id');
            $table->string('title');
            $table->text('content');
            $table->string('slug');
            $table->timestamps();
        });
    }
```

$table->TYPE('NOM DU CHAMP')

Une fois ceci fait, il faut migrer la table vers notre base de données

```linux
php artisan migrate
```
