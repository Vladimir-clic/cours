# :arrow_forward: Cours Python
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

### :arrow_right: Les fonctions :

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
### :arrow_right: Les boucles :
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

### :arrow_right: Les Conditions ```if```
Les opérateurs de conditions permettent, comme dans la boucle ```while```de donner une condition d'activation pour la suite du code mais sans faire de boucle.
```python
condition = True
if condition == True:
    print("La condition est remplie")
```
Si jamais la condition n'était pas remplie, on aurait pu donner un résultat différent grâce à l'operateur ```else``` (sinon)
```python
condition = True
if condition == True:
    print("La condition est remplie")
else :
    print("La condition n'est pas remplie")
```
Délà, grâce à cela, on peut offrir des résultats différents selon si la condition est vrai ou fausse mais on peut encore ajouter d'autres sortie grâce aux ```elif```, on les met entre le ```if``` et le ```else```.
```python
nombre = 4
if nombre == 5:
    print("c'est la moitié de 10")
elif nombre ==7:
    print("le nombre parfait !")
elif nombre ==20:
    print("c'est le double de 10")
else:
    print("un nombre reste un nombre")
```
##  :red_circle: Fonctions intégrées et significations : 
### :small_red_triangle: ```map()``` pour transformer une liste élément par élément :
```python
map(fonction, liste)
```
Applique ```fonction``` à chaque élément de ```liste```. Autre exemple : 
```python
nombres = [1, 2, 3, 4]
resultat = map(lambda x: x * 2, nombres)
print(list(resultat))  # [2, 4, 6, 8]
```
Ici, on définit une liste de nombre, puis on crée une fonction anonyme ```lambda``` (définie plus bas) qui multiplie un nombre par 2, grâce à l'outil ```map```, tous les éléments de ```nombre``` sont ciblé, puis on ```print``` la fonction avec l'outil ```list``` sinon on obtient un truc comme ça : ```<map object at 0x000002724DF2E800>```

### :small_red_triangle: ```filter()``` pour garder seulement certains éléments d'une liste
Elle garde les éléments pour lesquels ```condition``` retourne ```True```. Elle s'écrit :
```python
filter(condition, liste)
```
Exemple : 
```python
nombres = [1, 2, 3, 4]
pairs = filter(lambda x: x % 2 == 0, nombres)
print(list(pairs))  # [2, 4]
```
Dans l'exemple, on définit une liste ```nombre``` qui va être intégré à la variable ```pair``` qui filtre tous les nombres qui, avec n'importe quel opérateurs avec 2 sont égaux à 0 (donc tous les multiples de deux), puis, on appelle cette fonction

### :small_red_triangle: ```sorted()``` pour trier une liste
Elle s'écrit :
```python
sorted(liste)
```
Avec une fonction clé (```key``` permet de personnaliser le tri.):
```python
sorted(liste, key=fonction)
```
Exemple : 
```python
noms = ['Alice', 'Bob', 'Christophe']
# Trier par longueur du nom
tri_par_longueur = sorted(noms, key=lambda x: len(x))
print(tri_par_longueur)  # ['Bob', 'Alice', 'Christophe']
```

### :small_red_triangle: ```eval()``` pour transformer une chaine de caractère en objet
Avec ```eval```, on transforme une chaine de caractère en instruction intéprétable
```python
print(eval("6*7"))
```
Cela donnera un résultat de 42

## Les fonctions anonymes :
(pas clair même pour moi)
### La fonction anonyme ```lambda```
Les lambdas sont utiles pour écrire des fonctions simples et rapides, souvent passées en argument à d'autres fonctions. Elle s'écrit :
```python
lambda arguments: expression
```
```lambda``` : le mot-clé pour créer une fonction lambda.
```arguments``` : les paramètres d’entrée.
```expression``` : ce que la fonction retourne (automatiquement).
Les fonctions ```lambda``` permettent d'écrire des fonctions plus rapidement qu'avec des ```def```

```python
ajoute_10 = lambda x: x + 10
print(ajoute_10(5))  # Affiche 15
```
Cette fonction ```lambda``` ajoute 10 au nombre écrit dans ```ajoute_10()``` en fonction ```def```, ça aurait donné ça  :
```python
def ajoute_10(x):
    return x + 10
```
Autre exemple à deux arguments : 
```python
multiplie = lambda a, b: a * b
print(multiplie(3, 4))  # Affiche 12
```
## B2
### Calculer la suite de fibonnaci : 
```python
def fibo(n):
    nb1 = 1
    nb2 = 0
    for i in range(n):
        result = nb1 + nb2
        print(i, " opération : ", result)
        nb2 = nb1
        nb1 = result

fibo(50)
```
### Calculatrice : 
```python
print("Entre une opération mathématique : (avec des espaces entre les symboles)")
operation = input().split()
print (operation)
if operation[1] == "+":
        print(int(operation[0]) + int(operation[2]))
elif operation[1] == "/":
        print(int(operation[0]) // int(operation[2]))
elif operation[1] == "*":
        print(int(operation[0]) * int(operation[2]))
elif operation[1] == "-":
        print(int(operation[0]) - int(operation[2]))
else:
        print("Operation invalide : l'élément ", operation[1], " n'est pas traité.")
```

### Jeux du pendu : 
```python
def pendu(mot):
    
    listmot = list(mot)
    print(listmot)
    
    listdevine = []

    for i in range(len(listmot)):
        listdevine.append("_")
    print(listdevine)

    essais = 0

    while listmot != listdevine:

        print("Essaie de trouver le mot avec des lettres")
        lettre = input()

        for i in range(len(listmot)):
            if listmot[i] == lettre:
                listdevine[i] = lettre
                print(listdevine)
        essais +=1


    print("bravo, tu as réussi en ", essais)

pendu("hello")
```

### Match Pattern : 
```python
import re
def match_pattern(text, pattern):
    
    match = re.search(pattern, text)
    
    if match:
        print(f"Match found: {match.group()}")
        print(f"Start index: {match.start()}")
        print(f"End index: {match.end()}")
        print(f"Span: {match.span()}")
    else:
        print("No match found.")


match_pattern("abcdefghijklmnopqrstuvwxyz", "jkl")
```
### Algoritme de Luhn (imparfait) : 
```python
def algodeluhn(codecarte):
    print(codecarte)

    listchiffre = list(str(codecarte))
    print(listchiffre)
    total = 0

    for i in range(1,len(listchiffre),2):
        nombre = int(listchiffre[i]) * 2
        if nombre >= 10:
            nombre = nombre-9
        total += nombre
        listchiffre[i] = str(nombre)
    
    for i in range(0,len(listchiffre),2):
        total += int(listchiffre[i])

    print(listchiffre)
    print(total)
    if total % 10 ==0:
        result = True
    else:
         result = False
         
    print(result)

algodeluhn(79927398713)   
```

### Les classes : 
La notion la plus importante en programmation **orientée objet** est le concept de classe : Les classes sont des moules qui permettent de créer des objets en série sur le même modèle. Elles s'écrivent ainsi : 
```python
class MaClasse:
  attribut = "Ceci est un attribut"
  def Mamethode(self):
    return "Ceci est une méthode"
```
Les variables initialisée dans une classes sont appelllé les **attributs** et les fonctions les **methodes**.
Pour initialiser un attribut dans un objet, on utilise la methode speciale ```__init__```. Présente partout, elle est appelée la **méthode d'initialisation** et est utilisée pour attribuer des valeurs initiales aux variables qui composent un objet.

### Mapper une opération à chaque élément d’une liste
```python
inputs = [ 1, 2, 3, 4 ]
output = [ x**2 for x in inputs ]
# Output = [ 1, 4, 9, 16 ]
```
Mapper une operation permet de l'appliquer à la liste, ici, on met au carré à chaque index de la liste (donc de façon exponentielle)

### S’assurer qu’une condition est vraie
```python
assert condition == false # Erreur
assert condition == true # OK
```
Permet de renvoyer true ou false en fonction du remplissage ou non de la condition

### Trier une liste avec une comparaison custom
```python
class Toto:
 def __init__(self, score):
 self.score = score ** 2;
input = [Toto(4), Toto(3), Toto(9)]
output = sorted(input, key = lambda inp: inp.score)
# Output contient les classes Toto, ordonnées du plus petit score, au plus grand
output = sorted(input, key = lambda inp: inp.score, reverse=True)
# Maintenant ordonnées du plus grand au plus petit :-)
```
Ici, nous avons une classe ```Toto``` qui prend en paramètre un score qui sera multiplié par 2. 

### 
