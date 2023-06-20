Cours Design Pattern C# 
=============

### Descrition des patterns :

* Nom
* Description
* Exemple de code sous forme de diagrame UML
* La structure standard (abstraite)
* Un exemple de code

## Cas concret d'étude pour ce cours

Nous allons prendre en exemple le cas d'une société qui vend des véhicules en ligne.

## Première grande famille de design pattern: Les patterns de construction

Les patterns de construction déterminent comment faire l'instanciation et la configuration des classes et des objets. Ces patterns permettent également d'encapsuler les classes concrètes et de rendre indépendant la façon dont les objets sont créés.

### Le pattern Abstract Factory

Le pattern Abstract Factory permet, à partir d'une interface, de créer une famille d'objets sans pour autant spécifier de classes concrètes. Pour chaque type d'objet (véhicule ici), nous disposons d'une classe abstraite et de n sous-classes, qui définiront chacune un modèle spécifique. Cela permet de les regrouper en "famille".

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/a7aeac03-265c-49d7-86f3-900fddde5e2e)

L'objet catalogue va prendre obligatoirement une instance FabriqueVéhicule, Scooter, Automobile
Scooter, Automobile sont des classe Abstraite, elles en peuvent pas être appeler.
Et FabriqueVéhicule est une interface.

```c#
public abstract class Scooter
{
  protected string modele;
  protected string couleur;
  protected int puissance;
[...]
```

### Le pattern Builder 
Ce pattern permet d'abstraire la construction d'objet complexes de leur implementation de sorte qu'un client puisse créer des objets complexes sans avoir a se preocuper des differences d'implementation.

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/462c1621-c145-436a-9364-8f5f9b64f62c)

Pourquoi utiliser ce pattern: 
- le client a besoin de construire des objets sans connaitre leur implementation
- un client a besoin de construire des objets complexes ayant plusieurs representations ou implementations

