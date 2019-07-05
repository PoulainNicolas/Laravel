## Eloquent:relationships 1:1 (one to many)

Dans cette section nous allons comment Laravel gère les relations entre les différentes tables.

|  POSTS  | |COMMENTS |
|:-------:|-|-------- |
|id       | |id       |
|title    | |comment  |
|content  | |         |


Dans notre exemple relationnel, 1:n. Un **post** a plusieurs **commentaires** mais un **commentaire** appartient a un **post**

|     POSTS    | |COMMENTS |
|:------------:|-|---------|
|id            | |id       | 
|title         | |comment  |
|content       | |         |
|**comment_id**| |         |

Nous voyons dans cet exemple que notre table **post** a maintenant un clé étrangère **comment_id**

Laravel traduit ceci comme 
- hasMany
- belongsTo

### Mise en application

#### 1. Migrations

```php
public function up()
{
    Schema::create('posts', function (Blueprint $table) {
        $table->increments('id');
        $table->string('title');
        $table->text('content');

        $table->integer('comment_id')->unsigned();

        $table->foreign('comment_id')
            ->references('id')
            ->on('comments')
            ->onDelete('cascade');
    });
}

public function up()
{
    Schema::create('comments', function (Blueprint $table) {
        $table->increments('id');
        $table->text('comment');
    });
}   
```

#### 2. Modèles
**Post.php**

```php
public function comments(){
    // Un post a plusieurs commentaires
    return $this->hasMany(Comment::class);
}
```

**Comment.php**
```php
public function post(){
    // Un commentaire appartient a un post
    return $this->belongsTo(Post::class,'comment_id');
}