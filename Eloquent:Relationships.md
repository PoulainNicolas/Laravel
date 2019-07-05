## Eloquent:relationships

Dans cette section nous allons comment Laravel gère les relations entre les différentes tables.

### 1. Relation 1:1 (one to one)

|  USER | | PHONE |
|:-----:|-|------ |
|id     | |id     |
|name   | |numero |
|age    | |       |


Dans notre exemple relationnel, 1:1. Un **user** a un **numéro de téléphone** et un **numéro de téléphone** appartient a un **user**

|    USER  | | PHONE |
|:--------:|-|------ |
|id        | |id     |
|id_numero | |numero |
|name      | |       |
|age       | |       |

Nous voyons dans cet exemple que notre table **user** a maintenant un clé étrangère **id_numero**

Laravel traduit ceci comme 
- hasOne
- belongsTo

#### Mise en application

**MIGRATION**

```php
public function up()
{
    Schema::create('users', function (Blueprint $table) {
        $table->increments('id');
        $table->text('name');
        $table->text('age');
        $table->integer('numero_id')->unsigned();

        $table->foreign('numero_id')
            ->references('id')
            ->on('phones')
            ->onDelete('cascade');
        });
    }

public function up()
{
    Schema::create('phones', function (Blueprint $table) {
        $table->increments('id');
        $table->text('numero');
    }    
```
