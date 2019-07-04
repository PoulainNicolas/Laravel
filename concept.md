## 2. Concept
### A. Avant de se lancer
Pour cet exercice, nous avons d'une seule table
**todo**

### B. Création des modèles, des migrations et des controlleurs
```
php artisan make:model Todo -mcr
```

Avant de migrer, il faut lui assigner les champs. 
```php
  public function up()
    {
        Schema::create('crud', function (Blueprint $table) {
            $table->increments('id');
            $table->string('name');
            $table->timestamps();
        });
    }

```

