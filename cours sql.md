# Présentation du langage sql
Le langage sql sert à structurer des bases de données : en voilà les bases.
Site pour faire des diagrammes sql : https://dbdiagram.io/d

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

### Clé primaire et étrangères (à continuer)
Une clé étrangère est une colonne (ou plusieurs colonnes) d'une base de données qui est reliée à la colonne clé primaire d'une autre table. La clé primaire en question est un simple identifiant 


## :pushpin: Type de langage SQL : (à continuer)
o	Principales commandes SQL :

|nom|Commandes|
|---|---|
|DDL (Data Definition Language)| CREATE, ALTER, DROP|
|DML (Data Manipulation Language)| SELECT, INSERT, UPDATE, DELETE|
|DCL (Data Control Language) |GRANT, REVOKE|
|TCL (Transaction Control Language)|COMMIT, ROLLBACK, SAVEPOINT|


## Gérer une base de données
Une fois que l'on a notre base de donnée, nous pouvons y apporter des modifications, mise à jour, ect..., nous allons voir quelles commandes nous le permettent :

## Commandes : 
### Suppression et mise à jour avec ```ON DELETE``` et ```ON UPDATE```

```ON DELETE CASCADE``` : Supprime automatiquement toutes les lignes associées si la ligne référencée est supprimée.
```sql
FOREIGN KEY (commande_id) REFERENCES Commandes(commande_id) ON DELETE CASCADE
```
```ON UPDATE CASCADE``` : Met à jour automatiquement la clé étrangère si la clé primaire référencée change.
```sql
FOREIGN KEY (commande_id) REFERENCES Commandes(commande_id) ON UPDATE CASCADE
```

### Modifier une table existante avec ```ALTER TABLE``` : (à continuer)
La commande ```ALTER TABLE``` en SQL permet de modifier une table existante. Idéal pour ajouter une colonne, supprimer une colonne ou modifier une colonne existante, par exemple pour changer le type. Elle s'écrit ainsi : 
```sql
ALTER TABLE nom_table
instruction_a_donner
```
Maintenant, voilà quelques type de commande que nous pouvons utiliser avec ```ALTER TABLE```
#### Utilisation d'une clé étrangère avec ```ADD CONSTRAINT```
```sql
ALTER TABLE tableA
ADD CONSTRAINT fk_tableA_tableB
FOREIGN KEY tableA(id_tableA) REFERENCES tableB(id_tableA);
```
