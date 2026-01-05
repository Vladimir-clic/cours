# Cours JAVA :

Java n'a rien à voir avec javascript, il ressemble plus au c# :

faire un hello world : 
```java
public class Main {
    public static void main(String[]args) {
        System.out.printf("Hello world");
    }
}
```

une classe = un fichier

créer une personne : 
```java
class Person {
    //bloc person qui peut avoir un prénom
    public String firstname;
}

public class Main {
    public static void main(String[]args) {

        //person 1
        Person p1 = new Person();
        p1.firstname = "JeanJean";

        //person 2
        Person p2 = new Person();
        p2.firstname = "Velociraptor";
        
    }
}
```
* ```class``` définit une classe
* ```main``` est le point d’entrée

## Variables et types : 
```java
int age = 20;
double prix = 9.99;
String nom = "Alice";
boolean actif = true;
```

## Modèle de classe : 
```java
public class Voiture {
String couleur;
int vitesse;
void accelerer() {
vitesse = vitesse + 10;
}
}
Voiture v = new Voiture();
v.couleur = "Rouge";
v.accelerer();
```

on fait tout en public, on se prend pas la tête

## Contrôle du flux: 
```java

```
## Encapsulation :
```java
public class Compte {
    private double solde;

    public void deposer(double montant) {
        solde += montant;
    }
    public double getSolde() {
    r    eturn solde;
    }
}
```

## Héritage : 
```java
public class Vehicule {
    int vitesse;
}
public class Voiture extends Vehicule {
    int nombreDePortes;
}
```

Une classe = un fichier
Quand on fait une demo = on crée une classe pour lancer un main (exemple : DemArrayList (en pascalcase))
```Control + Alt + l ``` pour remettre bien le code (pour jetbrain)
bonne pratique : si on a créer un constructeur avec un paramètre, il faut créer un constructeur vide explicitement pour pas se faire piéger (propre à java)
ex : 
si on a dans un code : 
```java
    public static void main(String[] args) {

        Vehicle vehicle1 = new Vehicle();
    }
```
dans vehicle, on doit instancier un constructeur vide :
```java
public class Vehicle {

    public String name;

    public Vehicle(){} //celui là !
}
```
un constructeur sert à faire des new, des objects avec des constructeurs par défauts

```java
public class Vehicle {

    public String name;

    public Vehicle(String name){
        this.name = name;
    } 
}
```
quand on a des nom qui ont le même sens, on met un ```this``` pour faire comprendre au code que c'est la même chose

## mettre les éléments dans une liste
```java
        //faire une liste
        // toujours instancier au moins à vide
        ArrayList<Vehicle> vehicles = new ArrayList<>();

        //ajouter des éléments
        vehicles.add(vehicle1);
        vehicles.add(vehicle2);
```

toutes les classes héritent d'une classe "objet" en cachette crée par l'ide

si on crée une liste qui prend en paramètre la classe object, on peut tout mettre dedans, on appelle ça le polymorphisme : 
```java
ArrayList<Object> ListDeTout = new ArrayList<>();
    ListDeTout.add(vehicle1);
    ListDeTout.add("nomtest");
    ListDeTout.add(true);
```

Dans un jeu d'échec, on dirait "j'ai une liste de pieces" plutôt qu'une liste de "j'ai une liste de rois", "j'ai une liste de pions", "j'ai une liste de cavaliers", etc... Donc on fait du polymorphisme, tout hérite de pièces.

classe : PascalCase
variable, fonction : camelCase
