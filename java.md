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

## Héritage : 
```java
public class Vehicule {
    int vitesse;
}
public class Voiture extends Vehicule {
    int nombreDePortes;
}
```
