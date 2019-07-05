## 2. Concept
### A. Avant de se lancer
Pour cet exercice, nous avons besoin d'une seule table
**todo**

### B. Création des modèles, des migrations et des controlleurs

```
php artisan make:model Todo -mcr
```

Avant de migrer, il faut lui assigner les champs. 
```php
  public function up()
    {
        Schema::create('todo', function (Blueprint $table) {
            $table->increments('id');
            $table->string('name');
            $table->timestamps();
        });
    }

```
[Contenu](https://github.com/pierrenoel/Laravel/blob/master/Exercice/003_contenu.md)
