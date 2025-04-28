# Cours Python
Listes de commandes python que j'ai pu apprendre et que je répertorie ici, il y a également des conseils ou d'autres éléments un peu randoms pour que je puisse y avoir facilement accès. Je vais probablement modifier souvent cette liste en y ajoutant, modifiant des éléments (voir en corrigeant des erreurs)
## Les bases :

Les variables permettent de stocker des informations grace aux ```=```, cela peut être des chaines de caractères (toujours entre guillement ""), des nombre ou des booléens (Vrai ou Faux)
```python
mot = "banane"
nombre = 5
boolean = True
```

Pour écrire quelque chose sur le terminal, on utilise la commande ```print```, attention aux guillements si c'est une chaine de caractères
```python
print("Hello World")
```

### Les fonctions :

Les fonctions sont des éléments essentiels en python, elles permettent de regrouper du code que l'on peut facilement appeler
```python
def fonction ():
  mot = "banane"
  print(mot)
```
On les appelles en donnant leurs noms suivit de parenthèse ```()```vide ou pleine, ici, elles sont vide
```python
def fonction ():
  mot = "banane"
  print(mot)
fonction()
```
On peut mettre des variables entre parenthèse de notre fonction qui sera réutilisé lors de l'appel de cette même fonction. Par exemple, si notre fonction est un calcul avec une inconnue, on peut être tenté d'essayer plusieurs résultats.
```python
def calcul (x):
  resultat = x*2
  print(resultat)
calcul(2)
calcul(5)
```
### Les boucles :
#### La boucle ```for```
Il existe deux types de boucles : ```for``` et ```while``` :
La commande ```for``` permet de boucler des commandes pour les réitérer un certain nombre de fois, voilà comme il s'exprime : 
```python
for i in range(10):
  print(i)
```
ici, ```i``` est une variable implicite, elle représente le compte de ```range(10)```, à chaques fois que la boucle sera exécutée, ```i``` prendra une valeur de +1, comme si commence avec une valeur de 0, le résultat de ce code donnera un compte de 0 à 9 (à chaque fois on print i)

#### La boucle ```while```
Cette boucle permet d'effectuer une boucle avec une condition d'activation, un "tant que" : "tant que cette condition est validée, je boucle". Par exemple, en reprenant la variable ```i``` de l'explication précédente : "Tant que ```i``` est inférieure à 5, boucle".
```python
i = 1
while i < 10:
    print(i)
    i = i + 1
print("Fin")
```
Dans cet exemple, on peut ne pas voir tout de suite l'intéret de ```while``` mais il peut trouver de nombreuses utilité nottement quand il y a plus de variables ou quand on cherche une valeur.
J'en profite pour dire que la commande clavier ```CONTROL C``` permet de stopper la boucle une fois lancée. Elle sera utile si le résultat de la commande est infinit, par exemple, si on enlevait ```i = i + i```, ```i``` resterai avec une valeure de 1 et la boucle serait infinie.

### Les Conditions ```if```
Les opérateurs de conditions permettent, comme dans la boucle ```while```de donner une condition d'activation pour la suite du code mais sans faire de boucle.
```python

```


## Commandes et significations : 

