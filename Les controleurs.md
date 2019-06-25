## 7. Les controlleurs
### CRUD
```PHP
php artisan make:controller PostsController --resource
```
Dans le fichier web.php
```PHP
Route::resource('/','PostsController');
```

![Route:list](https://github.com/pierrenoel/Laravel/blob/master/route:list.png)

#### index()
```PHP
$posts = Post::all();
return view('posts.index',compact('posts'));
```
Cette fonction retourne tous les posts à la vue **index** du sous dossier **posts**

#### create()
```
return view('post.create');
```
Cette fonction doit renvoyer vers la vue **create** du dossier **post**

#### store(Request $request)
```
 $request->validate([
            'title' => 'required',
            'content' => 'required'
        ]);

        $posts = new Post;
        $posts->title = $request['title'];
        $posts->content = $request['content'];
        $posts->save();

        return redirect('post');
```

#### edit($id)
```
$posts = Todo::find($id);
        return view('post.edit',compact('posts'));
```

#### update(Request $request, $id)
```
$request->validate([
            'title' => 'required',
            'content' => 'required'
        ]);

        $posts = Todo::find($id);
        $posts->title = $request['title'];
        $posts->content = $request['content'];
        $posts->save();

        return redirect('post');
```
#### destroy($id)
```
$posts = Post::find($id);
        $posts->delete();
        return redirect('posts');
```
