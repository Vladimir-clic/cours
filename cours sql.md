# Présentation du langage sql
Le langage sql sert à structurer des bases de données : en voilà les bases.
site pour faire des diagrammes sql : https://dbdiagram.io/d

## Comment créer des bases de données ?
### Création de ```DATABASE``` :
On commence toujours par créer notre ```DATABASE``` qui nous permettra de stoquer nos tables, données, ects...
```sql
CREATE DATABASE magasin;
USE magasin;
```
Ici, on crée la base de donnée puis on l'utilise. On retient que dans cette partie, les commandes sont séparées par des ```;``` mais cela ne sera pas toujours le cas (explication plus tard). Nénamoins, nous allons compllexifier légèrement notre code (c'est souvent comme ça que nous commencerons la création d'une ```DATABASE``` :
```sql
DROP DATABASE IF EXISTS magasin;
CREATE DATABASE magasin;
CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
USE magasin;
```
Le ```DROP DATABASE IF EXISTS magasin;``` permet de détruire la base de donnée **magasin** si elle existe, cela permet de rendre le code **idem potant**.
Autre rajout : ```CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;``` à copier coller, est utilisé pour définir le jeu de caractères et le classement d'une colonne ou d'une base de données dans SQL.

### Création de ```TABLE``` :
Chaque ```DATABASE``` possède un certain nombre de ```TABLES``` qui elles-même contiennent des informations, elles servent à structurer les informations au seins de la ```DATABASE```.
On la crée comme ci :


## Type de langage SQL :
o	Principales commandes SQL :

|nom|Commandes|
|---|---|
|DDL (Data Definition Language)| CREATE, ALTER, DROP|
|DML (Data Manipulation Language)| SELECT, INSERT, UPDATE, DELETE|
|DCL (Data Control Language) |GRANT, REVOKE|
|TCL (Transaction Control Language)|COMMIT, ROLLBACK, SAVEPOINT|





