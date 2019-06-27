## Liste de toutes les commandes php artisan
### 1. make:controller
```
php artisan make:controller UserController
```
**parametres : --resource**

Création du controlleur **UserController**.
```
php artisan make:controller UserController --resource
```

Le paramètre **--resouce** vous rajoute les fonctions index(), create(), store(), edit(), update(), et destroy() dans votre controlleur.

### 2. make:model
```
php artisan make:model User
```
Création du modèle **User**.

**parametres : --migration --controller --resource**
 
Le paramètre **--migration** crée une migration.
Le paramètre **--controller** crée un controlleur.
Le paramètre **--resource** voir plus haut.

Donc, il est possible lors de la création d'un modèle de lui créer une migration, un controlleur avec ses fonctions vues plus haut.

```
php artisan make:model User --migration --controller --resouce
```
