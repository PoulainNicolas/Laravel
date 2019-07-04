## 2. Concept
### A. Avant de se lancer
Avant de commencer le projet il faut le comprendre. Pour agrémenter l'explication de ce fabuleux framework, je vous 
invite à développer avec moi un crud.

Pour cet exercice, nous avons d'une seule table
**crud**

### B. Création des modèles, des migrations et des controlleurs
```
php artisan make:model Crud -mcr
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

