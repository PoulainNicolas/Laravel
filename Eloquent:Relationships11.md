## Eloquent:relationships 1:1 (one to one)

Dans cette section nous allons comment Laravel gère les relations entre les différentes tables.

|  USER | |   PHONE  |
|:-----:|-|--------- |
|id     | |id        |
|name   | |numero    |
|age    | |operateur |
|       | |prefix    |


Dans notre exemple relationnel, 1:1. Un **user** a un **numéro de téléphone** et un **numéro de téléphone** appartient a un **user**

|     USER     | |   PHONE  |
|:------------:|-|----------|
|id            | |id        |
|name          | |numero    |
|age           | |operateur |
|**numero_id** | |prefix    |

Nous voyons dans cet exemple que notre table **user** a maintenant un clé étrangère **numero_id**

Laravel traduit ceci comme 
- hasOne
- belongsTo

### Mise en application

#### 1. Migrations

```php
public function up()
{
    Schema::create('users', function (Blueprint $table) {
        $table->increments('id');
        $table->text('name');
        $table->integer('age');

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
    });
}   
```

#### 2. Modèles
**User.php**

```php
public function phone(){
    // Un télphone appartient à un user
    return $this->belongsTo(User::class);
}
```

**Phone.php**
```php
public function user(){
    // Un user a un numéro de télépone
    return $this->hasOne(Phone::class);
}