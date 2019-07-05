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