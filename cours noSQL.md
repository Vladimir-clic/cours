# NoSQL

Les bases de données **NoSQL**  (« not only SQL » en anglais) sont désignées indifféremment comme « non relationnelles » ou « non SQL » pour souligner le fait qu'elles peuvent gérer d'importants volumes de données non structurées et évoluant rapidement, et de manière différente par rapport à une base de données relationnelle (SQL) avec lignes et tables.

On distingue quatre principaux types de bases de données NoSQL : 
* paire clé / valeur,
* orientée colonne,
* orientée graph,
* orientée document

|type|NoSQL|
|--|--|
|Clé–valeur|Redis|
|Colonnes| Cassandra|
|Graphes| Neo4j|
|Documents |MongoDB|


Chacune de ces catégories a un attribut unique et des limites spécifiques. Toutefois aucun de ces quatre types de bases de données ne permet de résoudre n'importe quel problème.

![image nosql](https://media.licdn.com/dms/image/v2/D5612AQE2BSvHQssa9g/article-cover_image-shrink_720_1280/B56ZUDTlf5HQAI-/0/1739517222066?e=2147483647&v=beta&t=_vJI-CdURGVCGbjWsy7AaOhpNEw6eof-8uM8BIAOS7Q "Un bien beau logo !")

# MongoDB :

Dans MongoDB Compass, on utilise le NoSQL **MongoDB**. Au fil des années, **MongoDB** a su séduire de nombreuses entreprises à la recherche d’une base de données NoSQL puissante et hautement évolutive. Bien plus qu’une simple base de données documentaire traditionnelle, **MongoDB** offre des fonctionnalités exceptionnelles, qui le distinguent des autres SGBD.

## Modélisation entre les relations : 
Il existe deux types de relations en NoSQL MongoDB (qui s'apparentent aux foreign key) :
* références (ObjectId)
* Imbriqué (embedded documents)

## Commandes :

Pour faire des selects, comme en sql, on structure notre commande ainsi :
```sql
db.base_de_donné.commande()
```
par exemple, pour sélectionner tout dans la base de donnée ```players```, on s'exprime ainsi :
```sql
db.players.find()
```
```find()```, quand il est vide, fait office de ```*```, si on le remplit, il peut filtrer avec une condition : 
```sql
db.players.find({name : "Romain Gary"})
```
Ici, la console ne va renvoyer que les players avec comme nom "Romain Gary"

Syntaxe de **lookup**
```json
{
   $lookup :
     {
       from : <collection à joindre>,
       localField : <champ des documents d'entrée>,
       foreignField : <champ des documents de la collection "from">,
       as : <champ du tableau de sortie&gt
     }
}
```

```json
db.players.aggregate([
  {
    $lookup: {
      from: "inventory",          // collection à joindre
      localField: "inventory._id",    // champ dans player
      foreignField: "_id",      // champ dans pokemons
      as: "result"     // résultat
    }
  },
  {
 $project: {
      _id: 0,
      name: 1,
      items: {
        $arrayElemAt: ["$result.objects", 0]
      }
 }
  }
])
```
