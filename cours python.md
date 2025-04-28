# Cours Python
## Listes de commandes python que j'ai pu apprendre et que je répertorie ici, il y a également des conseils ou d'autres éléments un peu randoms pour que je puisse y avoir facilement accès. Je vais probablement modifier souvent cette liste en y ajoutant, modifiant des éléments (voir en corrigeant des erreurs)


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

##Commandes et significations : 

