# Introduction au C sharp

C# (C sharp [siː.ʃɑːp] en anglais britannique) est un langage de programmation orientée objet, commercialisé par Microsoft depuis 2002[2] et destiné à développer sur la plateforme Microsoft .NET, au même titre que d’autres langages liés à cette plateforme (ex. : VB .NET, J#, etc.).

![image csharp](https://miro.medium.com/v2/resize:fit:1400/1*Uuf-_yJY1AuEC4YDfFk9mA.png "Un bien beau logo !")

## :pencil2: 1) premiers pas : écrire quelque chose dans la console

```c#
Console.WriteLine("Hello, World!");
```

```WriteLine()``` permet d'écrire puis de sauter une ligne, ```Write()``` ne fait qu'écrire.



```c#
string prenom = Console.ReadLine();
Console.WriteLine($"Bonjour {prenom} !");
```

```ReadLine()``` permet à l'utilisateur de rentrer une chaine de caractère (ici stockée dans ```prenom```. Pour interpoler des variables dans le texte, il faut un ```$``` devant et des ```{}``` qui encadrent les variables.



### :alarm_clock: 2) Utiliser ```DateTime```
![image csharp](https://blog.ndepend.com/wp-content/uploads/C-DateTime-Format-In-A-Nutshell-1.png "Un bien beau logo !")
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
On peut aisaiment changer le string par un ```ReadLine``` qui récupèrera les données de l'utilisateur. Ce système est moins sensible à la casse, on peut remplacer les ```/``` par des ```-``` ou des ```,``` sans problème.
Voilà un exemple de ce qu'on peut faire avec DateTime : 
```c#
// demander la date de naissance
Console.WriteLine("Quelle est ta date de naissance ? (yyyy/mm/dd)");
// entrer la date dans une variable String
string Stringdate1 = Console.ReadLine();

//Convertir cette date string en date DateTime
DateTime date1 = DateTime.Parse(Stringdate1);
// Obenir la DateTime d'aujourd'hui
DateTime date2 = DateTime.Now;

//Soustraire les années uniquement des deux dates et mettre le résultat dans une variable int
int diff = date2.Year - date1.Year;

//écrire le résultat de la variable int
Console.WriteLine($"Bravo, tu as {diff} ans");
```
## :file_folder: 3) Les classes
![image csharp](https://media.licdn.com/dms/image/v2/D4D12AQFrJXcWLw5rNA/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1661978014745?e=2147483647&v=beta&t=8JorpUyhacFbxA3JONGyz4iQzpzfBi8jir3cso3btIc "Un bien beau logo !")
Les classes jouent un rôle important en C#, il y en a plusieurs types : 



Voilà un exemple de class que l'on peut avoir : 
### 1. Classes **de base** :
* Ce sont les classes standard que vous définissez pour créer des objets. Elles peuvent contenir des membres (propriétés, méthodes, etc.) et peuvent être instanciées.
Exemple :
```
  public class Animal
{
    public string Nom { get; set; }
    public void Parler() { Console.WriteLine("L'animal fait du bruit."); }
}
```
### 2. Classes **statiques** :
* Ces classes ne peuvent pas être instanciées et contiennent uniquement des membres statiques. Elles sont souvent utilisées pour regrouper des méthodes utilitaires.
Exemple :
```c#
public static class MathUtil
{
    public static int Additionner(int a, int b) => a + b;
}
```
### 3. Classes **abstraites** :
* Ces classes ne peuvent pas être instanciées directement. Elles servent de base pour d'autres classes et peuvent contenir des méthodes abstraites (sans implémentation) que les classes dérivées doivent implémenter.
Exemple :
```c#
public abstract class Forme
{
    public abstract double CalculerAire();
}
```
### 4. Classes **dérivées** : 
* Ce sont des classes qui héritent d'une classe de base. Elles peuvent étendre ou modifier le comportement de la classe de base.
Exemple :
```c#
public class Cercle : Forme
{
    public double Rayon { get; set; }
    public override double CalculerAire() => Math.PI * Rayon * Rayon;
}
```
### 5. Classes **internes** :
* Ces classes sont définies à l'intérieur d'une autre classe. Elles sont souvent utilisées pour encapsuler des fonctionnalités qui ne sont pertinentes que pour la classe externe.
Exemple :
```c#
public class Externe
{
    public class Interne
    {
        public void Afficher() { Console.WriteLine("Classe interne."); }
    }
}
```
### 6. **Enregistrements** (Records) :
* Introduits dans C# 9, les enregistrements sont des types de référence conçus pour stocker des données immuables. Ils sont souvent utilisés pour des objets qui ne changent pas après leur création.
Exemple :
```
public record Personne(string Nom, string Prenom);
```
### * Différences clés :
  * **Instanciation** : Les classes de base, dérivées et internes peuvent être instanciées,  tandis que les classes statiques et abstraites ne le peuvent pas.
  * **Mutabilité** : Les classes standard et dérivées sont généralement mutables, tandis que les enregistrements sont immuables par défaut.
  * **Héritage** : Les classes abstraites peuvent être héritées, tandis que les classes statiques ne le peuvent pas.

### Public ou Private ?

Dans une classe, lorsque l'on instancie une variable ou une classe, on peut la mettre en ```public``` ou en ```private```. Les public permettent d'utiliser les propriété de l'objet en dehors de sa classe et les privates non.

```c#
public class Personne
{
    public string Nom { get; set; }
    public string Prenom { get; set; }
}

class Program
{
    static void Main()
    {
        Personne p = new Personne();
        p.Nom = "John";
        p.Prenom = "Doe";
        
        Console.WriteLine($"Bonjour {p.Prenom} {p.Nom} !");
    }
}
```
* Ici, on a une classe publique ```Personne``` qui possède 2 variable : ```Nom``` et ```Prenom```. C'est une sorte de modèle et lorsque l'on veut créer une personne, on va l'instancier comme on a vu plus tôt avec ```new```, puis entrer les données des variables. Ainsi, cela permet d'avoir plusieurs personnes. La classe ```main``` n'est pas anodine, en C#, le compilateur va chercher une classe ```main``` pour l'exécuter en premier.
* On déclare les propriétés avec ```get; set;```, ce qui signifie que l'on peut non seulement accéder aux variables mais en plus les modifier.

On peut améliorer notre code en faisant en sorte que la phrase de fin soit inclue à part entière dans la classe ```personne``` dans sa propre méthode : ```SePresenter()``` :
```c#
public class Personne
{
    public string Nom { get; set; }
    public string Prenom { get; set; }

// ajout d'une méthode SePrésenter
    public void SePresenter()
    {
// la méthode écrit une phrase avec le nom et le prénom
        Console.WriteLine($"Bonjour {Prenom} {Nom} !");
    }
}

class Program
{
    static void Main()
    {
        Personne p = new Personne();
        p.Nom = "John";
        p.Prenom = "Doe";
// appel de la méthode
        p.SePresenter();
        
        
    }
}
```
Voilà une autre version de ce même code auquel on a rajouté une autre classe ```Adresse``` que l'on à lié à la classe ```Personne``` : 
```c#
public class Personne
{
    public string Nom { get; set; }

    public string Prenom { get; set; }

    // déclaration de la propriété adresse dans personne
    public Adresse Adresse { get; set; }

    public void SePresenter()
    {
        // ajout de l'adresse au message final
        Console.WriteLine($"Bonjour {Prenom} {Nom} , tu habites au {Adresse.GetAdresseComplete()}!");
    }
}

public class Adresse
{ 
    public string rue { get; set; }
    public string codepostal { get; set; }
    public string ville { get; set; }

    public string GetAdresseComplete()
    {
        //renvoie cette phrase avec les variables de l'adresse
        return $"Adresse  : {rue} {codepostal} {ville}";
    }
}
class Program
{
    static void Main()
    {
        // création de l'adresse
        Adresse a = new Adresse();
        a.rue = "4 rue des cigogne";
        a.codepostal = "44200";
        a.ville = "Paris";
        
        Personne p = new Personne();
        p.Nom = "John";
        p.Prenom = "Doe";
        p.Adresse = a;
        p.SePresenter();
    }
}
```

### Programmer sur plusieurs classes
Il est conseillé, lorsque le programme prend en taille, de l'étaler sur plusieurs fichier.cs (qu'on appelle classe). Ici, on va créer une classe program.cs et une classe Classes.cs.
* Program.cs instanciera les classes
* Classes.cs les créera
#### Program.cs :
```c#
// nom du projet pour lier les deux classes
using Apprendre_injection_de_dependance;

class Program
{
    static void Main()
    {
        Personne p = new Personne();
        p.Nom = "John";
        p.Age = 20;
        p.SePresenter();

    }
}
```
#### Classes.cs
```c#
namespace Apprendre_injection_de_dependance;

public class Personne
{
    public string Nom  { get; set; }

    public int Age   { get; set; }
    
    public void SePresenter()
    {
        Console.WriteLine($"Je m'appelle {Nom} et j'ai {Age} ans.");
    }
}
```
Un outil utile lors de la rédaction du code est de faire **Alt + Insert** pour générer directement le code dont on a besoin

### Créer des classes qui collaborent : 
#### Program.cs :
```c#
using Apprendre_injection_de_dependance;

class Program
{
    static void Main()
    {
        Animal an = new Animal();
        an.Nom = "Rex";
        an.Espece = "Chien";
        
        Animal an2 = new Animal();
        an2.Nom = "Juan";
        an2.Espece = "Chat";
        
        Proprietaire pro =  new Proprietaire();
        pro.Nom = "Jérémy";
        pro.listeAnimaux =
        [
            an,
            an2
        ];
        pro.PresenterAnimaux();
    }
}
```
#### Classe.cs : 
```c#
namespace Apprendre_injection_de_dependance;

public class Animal
{
    public string Nom { get; set; }
    public string Espece  { get; set; }

    public void FaireDuBruit()
    {
        Console.WriteLine("Wouf !");
    }
}

public class Proprietaire
{
    public string Nom  { get; set; }
    public List<Animal> listeAnimaux  { get; set; }

    public void PresenterAnimaux()
    {
        foreach (var animal in listeAnimaux)
        {
            Console.WriteLine($"{Nom} à un {animal.Espece} qui s'appelle {animal.Nom} ");
        }
    }
}
```
On aborde le sujet des listes, ici, on veut ajouter des informations dans une liste, des informations que l'on a pas lors de sa création.
Une liste s'écrit ainsi : ```List<>``` elle prend en paramètre le type de données qu'elle contiendra.

### Injection de dépendance manuelle :
Une dépendance est un objet dont dépend un autre objet. Nous allons y aller étape par étape en créant un logger dans un nouveau service : 
```c#
public interface ILogger
{ 
    void Log(string message);
}
```
Ici, on définit le contract que le logger doit respecter, à savoir le fait d'envoyer un message string
```c#
public class ConsoleLogger : ILogger
{
    public void Log(string message)
    {
        Console.WriteLine($"[Console] {message}");
    }
}
```
Création d'une classe ConsoleLogger qui prend en paramètre Ilogger et qui va définir comment le log se présentera

```c#
public class ServiceUtilisateur
{

    // 🔸 Dépendance : notre service dépend d’un logger.
    // Mais on ne le crée pas ici. On le reçoit de l’extérieur (c’est l’injection).
    private readonly ILogger _logger;

    // 🔸 Injection de dépendance par constructeur
    // On "injecte" un objet implémentant ILogger lors de la création de ServiceUtilisateur.
    public ServiceUtilisateur(ILogger logger)
    {
        _logger = logger;
    }
    // 🔸 Une méthode qui utilise le logger
    public void AjouterUtilisateur(string nom)
    {
        // Ici, on se fiche de savoir quel type de logger est utilisé.
        // On appelle simplement la méthode Log du contrat ILogger.
        _logger.Log($"Utilisateur {nom} ajouté !");
    }
}
```
```c#
class Program
{
    static void Main()
    {
        // 🔸 On crée manuellement un logger pour la console
        ILogger consoleLogger = new ConsoleLogger();

        // 🔸 On injecte ce logger dans notre service
        var serviceConsole = new ServiceUtilisateur(consoleLogger);

        // 🔸 On utilise le service, qui loguera via la console
        serviceConsole.AjouterUtilisateur("Alice");
```
