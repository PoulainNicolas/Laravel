## 2. Concept
### A. Avant de se lancer
Avant de commencer le projet il faut le comprendre. Pour agrémenter l'explication de ce fabuleux framework, je vous 
invite à développer avec moi un mini blog. Nous allons établir les tables ainsi que leurs relations.

Pour cet exercice, nous avons besoin de 5 tables
**USERS**
**ROLES**
**POSTS**
**CATEGORIES**
**COMMENTS**

### B. Création des modèles, des migrations et des controlleurs
```
php artisan make:model Post -mcr
php artisan make:model Category -mcr
```

Avant de migrer, il faut lui assigner les champs. 
```php
  public function up()
    {
        Schema::create('posts', function (Blueprint $table) {
            $table->increments('id');
            $table->string('title');
            $table->text('content');
            $table->integer('category_id')->unsigned()->index();
            $table->timestamps();

            $table->foreign('category_id')->references('id')->on('categories');
        });
    }

```

