## 3. Contenu
### A. Créer du contenu

```php
php artisan tinker
>> $todo = App\Todo;
>> $todo->name="Comprendre Laravel";
>> $todo->save();
```

### B. Vérifier si le contenu a bien été crée

```php
php artisan tinker
>> $todo::all();
```


