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

### Créer une table avec ```CREATE``` (à continuer)
Nous l'avons vu plus tôt, ce mot clé sert à créer aussi bien des tables que des bases de donnée\


à continuer...


### Modifier une table existante avec ```ALTER TABLE``` : (DDL)
La commande ```ALTER TABLE``` en SQL permet de modifier une table existante. Idéal pour ajouter une colonne, supprimer une colonne ou modifier une colonne existante, par exemple pour changer le type. Elle s'écrit ainsi : 
```sql
ALTER TABLE nom_table
instruction_a_donner
```
Maintenant, voilà quelques type de commande que nous pouvons utiliser avec ```ALTER TABLE``` :\
```ADD``` pour ajouter une colonne  
```DROP``` pour supprimer une colonne  
```MODIFY``` pour changer le type de la colonne ```MODIFY nom_colonne type_donnees```  
```CHANGE``` pour renommer une colonne (on met le nom original, puis le nouveau nom)  


#### Utilisation d'une clé étrangère avec ```ADD CONSTRAINT```
```sql
ALTER TABLE tableA
ADD CONSTRAINT fk_tableA_tableB
FOREIGN KEY tableA(id_tableA) REFERENCES tableB(id_tableA);
```


### Suppression et mise à jour avec ```ON DELETE``` et ```ON UPDATE``` (DML)

```ON DELETE CASCADE``` : Supprime automatiquement toutes les lignes associées si la ligne référencée est supprimée.
```sql
FOREIGN KEY (commande_id) REFERENCES Commandes(commande_id) ON DELETE CASCADE
```
```ON UPDATE CASCADE``` : Met à jour automatiquement la clé étrangère si la clé primaire référencée change.
```sql
FOREIGN KEY (commande_id) REFERENCES Commandes(commande_id) ON UPDATE CASCADE
```



### Joindre des données avec les différents types de ```JOIN```
#### La jointure commune avec ```INNER JOIN``` :

Dans le langage SQL la commande ```INNER JOIN```, aussi appelée ```EQUIJOIN```, est un type de jointures très communes pour lier plusieurs tables entre-elles. Cette commande retourne les enregistrements lorsqu’il y a au moins une ligne dans chaque colonne qui correspond à la condition.
|table 1|table 2|
|---|---|
|id|fk_id|

```sql
SELECT *
FROM table1
INNER JOIN table2 ON table1.id = table2.fk_id
```

#### Les jointures vers la droite et la gauche avec ```RIGHT JOIN``` et ```LEFT JOIN```

Dans le langage SQL, la commande ```LEFT JOIN``` (aussi appelée ```LEFT OUTER JOIN```) est un type de jointure entre 2 tables. Cela permet de lister tous les résultats de la table de gauche (left = gauche) même s’il n’y a pas de correspondance dans la deuxième tables. ```RIGHT OUTER JOIN```

```sql
SELECT *
FROM table1
LEFT JOIN table2 ON table1.id = table2.fk_id
```

#### Les jointures retournant un produit **Cartésien** avec ```CROSS JOIN``` :

En mathématiques, le produit **cartésien** de deux ensembles X et Y, appelé également ensemble-produit, est l'ensemble de tous les couples dont la première composante appartient à X et la seconde à Y

La commande ```CROSS JOIN``` est un type de jointure sur 2 tables SQL qui permet de retourner le produit **cartésien**. Autrement dit, cela permet de retourner chaque ligne d’une table avec chaque ligne d’une autre table. Ainsi effectuer le produit **cartésien** d’une table A qui contient 30 résultats avec une table B de 40 résultats va produire 1200 résultats (30 x 40 = 1200). En général la commande CROSS JOIN est combinée avec la commande WHERE pour filtrer les résultats qui respectent certaines conditions.

Attention, le nombre de résultat peut facilement être très élevé. S’il est effectué sur des tables avec beaucoup d’enregistrements, cela peut ralentir sensiblement le serveur.

Exemple :
Table légume : 
l_id|l_nom_fr_fr|l_nom_en_gb
|---|---|---|
45|Carotte|Carott|
|46|Oignon|Onion|
|47|Poireau|Leek|

Table fruit :
f_id|f_nom_fr_fr|f_nom_en_gb|
|---|---|---|
|87|Banane|Banana|
|88|Kiwi|Kiwi|
|89|Poire|Pear|

On peut donc utiliser la commande ```CROSS JOIN``` comme ceci :
```
SELECT l_id, l_nom_fr_fr, f_id, f_nom_fr_fr
FROM legume
CROSS JOIN fruit
```


l_id|l_nom_fr_fr|f_id|f_nom_fr_fr|
|---|---|---|---|
|45|Carotte|87|Banane|
|45|Carotte|88|Kiwi|
|45|Carotte|89|Poire|
|46|Oignon|87|Banane|
|46|Oignon|88|Kiwi|
|46|Oignon|89|Poire|
|47|Poireau|87|Banane|
|47|Poireau|88|Kiwi|
|47|Poireau|89|Poire|

3 colonne multiplié par 3 colonne, 9 colonnes avec à chaque fois toutes les variantes possible (le même résultat est atteignable sans utiliser ```CROSS JOIN```

