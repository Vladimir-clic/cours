 # Cours PHP :
Le langage php est utilisé pour créer des sites web (avec du html), c'est un langage flexible qui peut être exécuter sur terminal, comme langage de programmation ou pour réaliser une suite d'instruction pour l'ordinateur. 

PHP permet de motifier un site afin d'apporter une réponse personnalisé à chaque utilisateurs

Voici un exemple type de code en php : 
```php
<h1>My First PHP Site</h1>
<p>This HTML will get delivered as is</p>
<?php echo "<p>But this code is interpreted by PHP and turned into HTML</p>";?>
<?php echo "<ul><li>You can use any HTML tags,</li><li>like this list.</li></ul>";?>
<footer>
  <p>And this code is back in plain HTML</p>
</footer>
```
Il est difficile de donner une représentation en markdown de ce que cela donne mais en voici une approximation :

>**<h5>My First PHP Site<h5>**
>This HTML will get delivered as is
>But this code is interpreted by PHP and turned into HTML
>* You can use any HTML tags,
>* like this list.\
>And this code is back in plain HTML

### 1 : Hello World
Voilà notre premier **Hello world** :
```php
<?php
echo "Hello, World!";
```
>Hello, World !

La commande ```echo``` permet d'afficher une ou plusieurs expression (ici un **string** : "Hello Wolrd"). La plus grosse différence avec ```print``` est que ```echo``` accepte plusieurs arguments et ne retourne aucune valeur.

On note aussi la présence d'un ```<?php``` au début, c'est une boite qui range le code php pour le séparer du html, en l'occurence, il n'y en a pas mais si il y avait, on devrait conclure le php par un ```?>```

Chaque instruction doit être séparée par un ```;``` point virgule



### 2 : L'annotation du code
Comme dans chaque langage, nous avons besoin de noter des instructions pour nous repérer dans notre avancée sans qu'elles soient exécutée, avec php, nous avons l'embarra du choix :
```sql
<?php
// I will always remember this
echo "Hello, World!"; # My first PHP statement

/* "I've never thought of PHP as more 
than a simple tool to solve problems."
- Rasmus Lerdorf */
echo "\nRasmus is the creator of PHP!";
```
>Hello, World!\
Rasmus is the creator of PHP!

Nous avons donc 3 manière d'annoter notre code :\
* le ```#``` en début de ligne
* les ```//``` en début de ligne
* les ```/*``` en début et ```*/``` en fin


### 3 : Guillemets et à la ligne

Nous avons vu plus tôt que pour écrire du texte, nous utilisons des guillemets, mais que se passe t'il quand nous voulons écrire des guillemets ? On utilise des ```\```, le premier à l'extérieur et le second à l'intérieur:
```php
<?php
echo "She said \"hi\" to the dog";
```
>She saind "hi" to the dog

Et pour une liste ? Comment mettre le texte à la ligne ? On utilise des ```\n``` au début, après les guillemets : 
```php
<?php
echo "\n1. Go to gym";
echo "\n2. Cook dinner";
```
>Go to gym\
>Cook dinner



### 4 : Concaténation

Il existe des opérateurs de concaténation ou "string concatenation" qui permettent d'accomplir des tâches dans notre code. On trouve par exemple le ```.``` qui permet de réhitérer une commande echo, par exemple :
```php
<?php
echo "one ". "hop";
```
>one hop

### 5 : Les variables :

Comme dans tout code, nous pouvons utiliser des variables en php, voilà comment :
```php
<?php
  $my_name = "Aisle Nevertell";
```
La variable se déclare collée à un ```$``` puis, une fois nommé, on lui attribue une donnée grâce à un élément d'assignation : ```=```. Mais maintenant, comment l'appeler ?
```pdp
<?php
// Write your code below:
  $couleur = "jaune";
  echo $couleur;
```
>jaune

On appelle une fonction comme on écrit quelque chose, avec le mot clé ```echo```. On peut, quand on l'appelle, ajouter des mot collé à notre variables, dans ces cas là, on utilise ses ```{ }``` : 
```php
<?php
$animal = "dog";
echo "I am friends with many ${animal}s.";
```
>I am friends with many dogs.

On peut ajouter des données à une variable avec un ```.``` devant le ```=```: 
```php
$liste = "abc";
echo $liste;
$liste .= "def";
echo $liste;
```

Il est possible de réassigner une nouvelle donné à une même variable, que ce soit une donnée écrite ou la donnée d'une autre variable, cela s'écrit ainsi : 
```php
<?php

$movie = "break point";
echo "I'm a fickle person, my favorite movie used to be $movie.";

$old_favorite = $movie;
$movie = "pulp fiction";
echo "\nBut now my favorite is $movie, my old one, was $old_favorite";
```
>I'm a fickle person, my favorite movie used to be break point.
But now my favorite is pulp fiction, my old one, was break point

Quand on donne à une variable la valeur d'une autre variable comme on le fait d'habitude ```$var1 = $var2``` cela copie la valeur de la ```$var1``` vers ```$var2``` mais si on utilise ```=&```, cela assigne à ```$var2``` la même valeur que ```$var1``` et ce, même si cette dernière change.



