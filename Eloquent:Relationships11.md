## Eloquent:relationships 1:1 (one to one)

Dans cette section nous allons comment Laravel gère les relations entre les différentes tables.

|  USER | | PHONE |
|:-----:|-|------ |
|id     | |id     |
|name   | |numero |
|age    | |       |


Dans notre exemple relationnel, 1:1. Un **user** a un **numéro de téléphone** et un **numéro de téléphone** appartient a un **user**

|    USER  | |  PHONE |
|:--------:|-|------- |
|id        | |id      |
|name      | |numero  |
|age       | |user_id |

Nous voyons dans cet exemple que notre table **phone** a maintenant un clé étrangère **user_id**

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
    });
}

public function up()
{
    Schema::create('phones', function (Blueprint $table) {
        $table->increments('id');
        $table->text('numero');

        $table->integer('user_id')->unsigned();

        $table->foreign('user_id')
            ->references('id')
            ->on('users')
            ->onDelete('cascade');
    });
}   
```

#### 2. Modèles
**User.php**

```php
public function Phone(){
    // Un télphone appartient à un user
    return $this->belongsTo(User::class);
}
```

**Phone.php**
```php
public function Phone(){
    // Un user a un numéro de télépone
    return $this->hasOne(Phone::class);
}