## Eloquent:relationships

Dans cette section nous allons comment Laravel gère les relations entre les différentes tables.

### 1. Relation 1:1 (one to one)

|  USER |
|:-----:|
|id     |     
|name   |      
|age    |      

| PHONE |
|:-----:|
|id (pk)|     
|numero |        


Dans notre exemple relationnel, 1:1. Un **user** a un **numéro de téléphone** et un **numéro de téléphone** appartient a un **user**

|  USER   |
|:-------:|
|id       | 
|id_phone |    
|name     |      
|age      |      

| PHONE |
|:-----:|
|id     |     
|numero |        
