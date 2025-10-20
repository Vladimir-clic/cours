## Introduction au C sharp

C# (C sharp [siː.ʃɑːp] en anglais britannique) est un langage de programmation orientée objet, commercialisé par Microsoft depuis 2002[2] et destiné à développer sur la plateforme Microsoft .NET, au même titre que d’autres langages liés à cette plateforme (ex. : VB .NET, J#, etc.).

### 1) premiers pas : écrire quelque chose dans la console

```c#
Console.WriteLine("Hello, World!");
```

```WriteLine()``` permet d'écrire puis de sauter une ligne, ```Write()``` ne fait qu'écrire.



```c#
string prenom = Console.ReadLine();
Console.WriteLine($"Bonjour {prenom} !");
```

```ReadLine()``` permet à l'utilisateur de rentrer une chaine de caractère (ici stockée dans ```prenom```. Pour interpoler des variables dans le texte, il faut un ```$``` devant et des ```{}``` qui encadrent les variables.



### 2) Utiliser ```DateTime```
Grâce à DateTime, nous pouvons connaitre et jouer avec le temps, par exemple : 
```c#
Console.WriteLine(DateTime.Now);
```
le programme renvoie ```20/10/2025 19:30:23```, DateTime.Now permet d'obtenir la date et l'heure à la seconde près d'aujourd'hui.
On peut préciser notre demande en ajoutant ```ToString()``` :
```c#
Console.WriteLine(DateTime.Now.ToString("dd/MM/yyyy HH:mm:ss"));
```
Les paramètres de ```ToString``` permettent de ne renvoyer qu'une partie des informations (ici, on a tous mis mais on n'aurait put renvoyer que l'heure ```ToString("HH")```. Les deux lettres permettent d'indiquer que l'on souhaite un nombre à deux chiffres.

Maintenant que nous savons faire ça, nous pouvons essayer de trouver la différence entre deux dates avec ```TimeSpan```

```c#
DateTime date1 = new DateTime(2023, 1, 1);
DateTime date2 = DateTime.Now;

TimeSpan différence = date2-date1;

Console.WriteLine($"Nombre de jours de différence : {différence.Days}");
```
Quelques informations à retenir : 
* ```new``` facilite l'instanciation d'objet en appelant le constructeur d'une classe pour allouer de la mémoire à un nouvel objet (c'est important)
* ```TimeSpan```  représente un intervalle de temps et peut être utilisée pour mesurer des durées ou la différence entre deux valeurs de date et d'heure
* Dans ```différence.Days```, on peut aisaiment remplacer ```Days``` par ```Hours``` ou autre au besoin.

Dans le cas où l'on voudrait transformer un string en une date, on utilise ```DateTime.Parse()``` : 
```c#
string anniversaire = "2005-03-28";
Console.WriteLine(DateTime.Parse(anniversaire));
```
On peut aisaiment changer le string par un ```ReadLine``` qui récupèrera les données de l'utilisateur. Ce système est moins sensible à la casse, on peut remplacer les ```/``` par des ```-``` ou des ```,``` sans problème
