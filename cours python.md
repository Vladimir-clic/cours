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

```python
class Person:
    def __init__(self, prenom, nom, age):
        print("Initialisation de l'instance", self)
        self.prenom = prenom
        self.nom = nom
        self.age = age
        self.nationalite = "français"

patrick = Person(prenom="Patrick", nom="Michaud", age=27)
print(patrick.prenom, patrick.nom)
print(patrick.nationalite)
```
Dans cet exemple, on met en paramètre de ```__init__``` les variables qui seront utiles à la classe. Une fois la classe crée, on peut instancier la classe en l'appelant sous un nom ```nouvelle classe = class() class.variable = "string" ```. Ici, c'est ``` patrick = Person(prenom="Patrick", nom="Michaud", age=27)```eEnsuite, pour appeler ces variables dans la classes ont note ```classe.variable```, dans l'exemple, cela se traduit par ```patrick.prenom``` pour obtenir le prenom de patrick.

La méthode ```__init__``` est une methode spéciale, elle doit obligatoirement retourner ```None```, donc par de ```return``` à l'intérieur, à moins de retourner explicitement ```None```

un autre exemple de création d'initialisation de classe : 
```python
class Chien:
 def __init__(self, name):
 self.name = name
 self.age = 0
 self.nb_ouaf = 0
 def ouaf(self):
 print("OUAF")
 self.nb_ouaf +

fido = Chien()
ducon = Chien()
fido.ouaf()
ducon.ouaf()
ducon.ouaf()
print(fido.nb_ouaf, ducon.nb_ouaf) # Affiche "1 2"
```
#### L'heritage :
On peut définir une classe comme la "continuité" d'une autre. On dit qu'elle hérite d'une autre classe. Toutes les **méthodes** et les **attributs** de la classe parente seront transmises :
```python
# création de classe normale
class Animal:
 def __init__(self):
 self.age = 0
 self.en_vie = True
 def vieillir(self):
 self.age += 1
 if self.age > 30:
 print("Couic")
 self.en_vie = False

# création d'une classe qui prend en paramètre et initialise la classe animal dans son init
class Chien(Animal):
 def __init__(self, name):
 Animal.__init__(self)
 self.name = name
 def ouaf(self):
 print("Ouaf")
fido = Chien()
fido.ouaf()
fido.vieillir()
```

### Mapper une opération à chaque élément d’une liste
```python
inputs = [ 1, 2, 3, 4 ]
output = [ x**2 for x in inputs ]
# Output = [ 1, 4, 9, 16 ]
```
Mapper une operation permet de l'appliquer à la liste, ici, on met au carré à chaque index de la liste (donc de façon exponentielle). Dans cet exemple, on instancie une liste puis on en crée une autre qui utilise une boucle ```for``` pour mettre tous les élément de cette liste au carré.


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
Ici, nous avons une classe ```Toto``` qui prend en paramètre un score qui sera multiplié par 2. output permet de les renvoyer dans la liste du plus petit au plus grand ou du plus grand au plus petit si ```reverse = True```

### Générer des nombres aléatoires
```python
import random
n = random.random() # Nombre entre 0.0 et 1.0
n = random.randrange(0, 15) # Nombre entre 0 et 14
```
La fonction ```random.random()``` permet de créer un nombre aléatoire de 0.0 à 1.0 si il n'a pas de paramètre mais comme dans l'exemple, on peut lui mettre des paramètres pour le limiter ou augmenter ses possibilités.
Ne pas oublier de l'importer ```import random```

### Afficher un message avec un format particulier
```python
name = "Anna"
howami = "depressed"
print(f"Hello {name} how are you today ? Me I'm {howami}")
```
Permet d'écrire plus facilement des messages dans des variables sans virgule

### Correction TP algorythme génétique : 
```python
#-*-encoding:utf-8*-

NDIM=5
XMIN=-4
XMAX=4
YMIN=0
XOPTI=0

PCT_BEST = 35
NCELL = 2000

import random
import math

def sphere(inputs):
    s = 0
    for x in inputs:
        s += x ** 2
    return s

def salomon(inputs):
    s = 0
    for x in inputs:
        s += x ** 2
    u = math.pi * 2 * math.sqrt(s)
    res = 1 - math.cos(u) + 0.1 * math.sqrt(s)
    return res

assert salomon([XOPTI, XOPTI]) == YMIN
assert salomon([XMIN, XMAX]) > YMIN
assert salomon([XMAX, XMIN]) > YMIN

def conversion(gene):
    # b = XMIN
    # A = XMAX - XMIN
    return (XMAX - XMIN) * gene + XMIN 

assert conversion(0.0) == XMIN
assert conversion(1.0) == XMAX
assert conversion(0.5) == XOPTI

def trad(genome):    # Liste de gènes
    inputs = []
    for gene in genome:
        inputs.append(conversion(gene))
    return inputs
    
assert trad([1.0, 0.0, 0.5]) == [XMAX, XMIN, XOPTI]

class Cellule:
    def __init__(self):
        self.genome = []
        for _ in range(0, NDIM):
            self.genome.append(random.random())

    def apply(self):
        inputs = trad(self.genome)
        # self.output = salomon(inputs)
        self.output = sphere(inputs)

    def reset(self):
        self.output = None

    def child(self):
        enfant = Cellule()
        enfant.genome = self.genome.copy()
        n = random.randrange(0, len(enfant.genome))
        enfant.genome[n] = random.random()
        return enfant

def opti():
    # Initialisation
    cellules = []
    for _ in range(NCELL):
        cellules.append(Cellule())

    nbgeneration = 0
    while True:
        # Pour chaque génération:
        for cell in cellules:
            cell.apply()
        # On sélectionne les meilleures cellules
        trie = sorted(cellules, key = lambda inp: inp.output)
        print("GEN", nbgeneration, "SCORE", trie[0].output, "GENOME", trie[0].genome)
        # On calcule combien de cellules on garde (X% meilleures)
        ncut = NCELL * (PCT_BEST / 100)

        # On supprime toutes les autres cellules (pas dans les X% meilleures)
        cellules = trie[:int(ncut)]
        parent = 0
        while len(cellules) < NCELL:
            # On complète la génération par des enfants
            cellule_parent = cellules[parent]
            parent += 1    # L'index du parent qu'on sélectionne pour créer l'enfant
            if parent >= ncut:
                parent = 0
            enfant = cellule_parent.child()    # On créé l'enfant
            cellules.append(enfant)    # On ajoute à la liste des cellules (pour la next gen)

        # Et z'est repartiiiiiiiiii
        nbgeneration += 1
        assert len(cellules) == NCELL

opti()
```

### Les décorateurs : 
Les décorateurs sont des éléments important en python, ils permettent d'ajouter du code à une fonction sans modifier cette même fonction. Un décorateur s'écrit comme une fonction mais il se fait appeler avec un ```@``` au dessus de la fonction qu'il prend en paramètre : exemple :
```python
def mon_decorateur(fonction):
    print(f"Appel de la fonction")
    fonction()

@mon_decorateur
def dis_bonjour():
    print("Bonjour ! ")

dis_bonjour

# result : 
#--> Appel de la fonction
#--> Bonjour ! 
```

Dans cet exemple, la fonction a appeler ne prend pas de paramètre mais si elle en prenait, l'affaire se compliquerai :
```python
def log_appel(fonction):
    def decorateur(*args, **kwargs):
        print(f"Appel de la fonction avec args=({args}), kwars=({kwargs})")
        return fonction(*args, **kwargs)
    return decorateur

@log_appel
def addition(a, b):
    print(a + b)

@log_appel
def dire(message, fois=1):
    for _ in range(fois):
        print(message)

addition(3, 7)
dire("Coucou", fois=2)

# résultat : 
# --> Appel de la fonction avec args=((3, 7)), kwars=({})
# --> 10
# --> Appel de la fonction avec args=(('Coucou',)), kwars=({'fois': 2})
# --> Coucou
# --> Coucou
```
Ici, nous sommes dans un cas où les fonctions décorée ont des paramètres. Pour appeler la fonction avec ces même paramètres dans le decorateur, on est obligé de créer une nouvelle fonction dans le décorateur qui prend en paramètre ```*args``` et ```**kwargs``` :
* ```*args``` : liste des variables
* ```*args``` : dictionnaire pour les listes
Puis, on retourne la fonction avec des ```*args``` et ```**kwargs``` en paramètres avant de conclure en retournant la fonction crée dans le décorateur.

Un décorateur peut servir à mesurer le temps que mettent les instructions à s'effectuer, voilà un exemple en utilisant ```time```
```python
import time

def chronometre(fonction):
    start_time = time.time()
    fonction()
    end_time = time.time()
    elapsed_time = end_time - start_time
    print(f"Fonction effectuée en {elapsed_time} secondes")

@chronometre
def travail_long():
    time.sleep(1)
    print("Fait !")

travail_long()

# resultat :
# --> Fait !
# --> Fonction effectuée en 1.0009217262268066 secondes
```

Renvoyer une erreur : le décorateur peut servir à renvoyer une erreur si les paramètres de la fonction ne sont pas correct grâce à la librairie ```traceback``` :
```python
import traceback

def ignore_erreurs(fonction):
    def decorateur(*args):
        try: 
            fonction(*args)
        except Exception as e:
            print(f"Erreur capturée dans {fonction.__name__} : {e}")
    return decorateur

@ignore_erreurs
def diviser(a,b):
    print(a / b)


diviser(10,2)
diviser(10,0)

#resultat :
# --> 5.0
# erreur
```
Il arrive que le décorateur prenne un paramètre autre que la fonction, dans ce cas, on doit créer une fonction décorateur qui prend la fonction à décorer en paramètre et contient une autre fonction qui prend les arguments de la fonction décorée en paramètre et qui les donne à cette dernière :
```python
def repete(n):
    def decorateur(fonction):
        def wrapper(*args, **kwargs):
            for _ in range(n):
                fonction(*args, **kwargs)
        return wrapper
    return decorateur

@repete(3)
def coucou():
    print("Coucou !")

coucou()
```

### Thread
L'utilisation des threads est très pratique pour exécuter des actions en même temps. Pour cela, il faut deux composant : 
* importer la librairie : ```import threading```
* initialiser le thread : ```mon_thread = threading.Thread(target=fonction)```
Puis, on peut lancer le thread ```mon_thread.start()``` et ```mon_thread.join``` qui attend la fin du thread pour continuer le programme. Donc, tout ce qui est entre les deux sera lancé parallèlement a la fonction dans thread. Exemple :

```python
import threading
import time

def dire_bonjour():
    print("Bonjour !")
    time.sleep(1)
    print("Au revoir !")

mon_thread = threading.Thread(target=dire_bonjour)

print("Début du programme")
mon_thread.start()
print("Fin du programme")
mon_thread.join()

# résultat : 
# --> Début du programme
# --> Bonjour !
# --> Fin du programme
# --> Au revoir !
```
On note que dans l'exemple, comme le thread prenait trop de temps, le programme à affiché ```Fin du programme``` avant de terminer le thread, si on veut annoncer la fin du programme après la fin du thread, il suffit de ```.join``` le thread directement après son lancement (ce qui ferait perdre tout son intéret au thread).

Lorsque l'on appelle des fonction avec des arguments, la création du thread change un peu, si on fait : ```thread = threading.Thread(target=fonction(variable))```, le programme va lancer la fonction immédiatement sans prendre en compte le thread. Pour que cela fonctionne, il faut séparer la fonction des arguments : ```thread = threading.Thread(target=fonction, args=(variable,))```. Voilà un exemple de programme avec plusieurs thread en même temps :

```python
import threading
import time

def travail(num):
    print(f"Thread {num} commence !")
    time.sleep(2)
    print(f"Thread {num} terminé")

thread1 = threading.Thread(target=travail, args=(1,))
thread2 = threading.Thread(target=travail, args=(2,))
thread3 = threading.Thread(target=travail, args=(3,))

print("début du programme")
thread1.start()
thread2.start()
thread3.start()
print("Fin du programme")
thread1.join()
thread2.join()
thread3.join()

# resultat : 
# --> début du programme
# --> Thread 1 commence !
# --> Thread 2 commence !
# --> Thread 3 commence !
# --> Fin du programme
# --> Thread 1 terminé
# --> Thread 3 terminé
# --> Thread 2 terminé
```
L'utilisation de thread est complexe et provoque nombre de bug. Par exemple, lorsque plusieurs thread exécute une même fonction. Pour ça, on peut utiliser des ```lock()```. Ils se compose de 2 commandes principales : 
* ```lock.acquire()``` : n'autorise qu'un thread à passer
* ```lock.release()``` : libère la place pour un autre thread

Exemple d'utilisation de lock : 
```python
import threading

lock = threading.Lock()
compteur = 0

def incrementer():
    global compteur
    
    if lock.acquire():
        try:
            for i in range(100000):
                compteur += 1
        finally:
            lock.release()

thread1 = threading.Thread(target=incrementer)
thread2 = threading.Thread(target=incrementer)

thread1.start()
thread2.start()

thread1.join()
thread2.join()


print(f"Le compteur est à {compteur}")

# résultat : 
# --> Le compteur est à 200000
```
