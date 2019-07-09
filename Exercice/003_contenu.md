## 3. Contenu
### A. Créer du contenu

Pour insérer du contenu dans en base de données, nous avons 2 manières. 
* La première méthode est de se rendre directement dans phpmyadmin et de remplir nos champs. 
* La deuxième mèthode est d'utiliser **php artisan tinker**, c'est celle-ci que nous allons utiliser aujourd'hui.

```console
php artisan tinker
```

```php
>> $todo = App\Todo;
>> $todo->name="Comprendre Laravel";
>> $todo->save();
```

### B. Vérifier si le contenu a bien été crée

```php
>> $todo::all();
```

[Read](https://github.com/pierrenoel/Laravel/blob/master/Exercice/004_read.md)
