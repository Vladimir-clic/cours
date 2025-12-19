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
