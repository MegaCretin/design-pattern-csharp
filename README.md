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

### Le pattern Factory Method

Le but de ce pattern est d'introduire une méthode abstraite de création d'objet en reportant la aux sous-classes concretes la création effective. 

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/5efe4adc-1b73-4e91-a0a5-b4f22d4d68a0)

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/515309d5-5cdb-4b10-9513-30004e8aa0a5)
![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/3ae7082c-7249-47f2-95ae-8abee5248ea6)

### Le pattern Singleton

Il faut s'assurer de deux choses lorsqu'on veut mettre en place ce pattern:
- Une classe ne doit posseder qu'une seule instance
- Il faut fournir une méthode de classe qui permet de fournir cette instance unique

### Le pattern Prototype

Le but de ce pattern est de créer de nouveaux objets en dupliquant des objets existants appeles "prototypes".
Ce derniers disposent d'une capacité de clonage

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/7b7b1c12-28b5-4955-bffb-315d256f3e07)

## Introduction des patterns de structuration

L’objectif des patterns de structuration est de faciliter l’indépendance de l’interface d’un objet ou d’un
ensemble d’objets vis-à-vis de son implantation. Dans le cas d’un ensemble d’objets, il s’agit aussi de
rendre cette interface indépendante de la hiérarchie des classes et de la composition des objets.
En fournissant les interfaces, les patterns de structuration encapsulent la composition des objets,
augmentant le niveau d’abstraction du système à l’image des patterns de création qui encapsulent la
création des objets. Les patterns de structuration mettent en avant les interfaces.
L’encapsulation de la composition est réalisée non pas en structurant l’objet lui-même mais en transférant
cette structuration à un second objet. Celui-ci est intimement lié au premier objet. Ce transfert de
structuration signifie que le premier objet détient l’interface vis-à-vis des clients et gère la relation avec le
second objet qui lui gère la composition et n’a aucune interface avec les clients externes.

### Le pattern Adapter

Le but ici est d'adapter l'interface d'une classe donnee afin qu'elle puissent interagir avec un client

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/d4934791-abf9-4abe-9ec6-cf143094bef2)

### Le pattern Decorator

Le pattern Decorator est un pattern de structuration qui permet d'ajouter dynamiquement des fonctionnalités à un objet.

Ici, on cherche a ajouter des fonctionnalités suplémentaire a un objet en prenant soin de ne pas modifier son interface. Toutes modifications apportées par ce pattern sereont transparente vis a vis des clients.

Ce pattern constitue une alternative a l'heritage.

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/bd95fac3-216b-4e12-baae-532118179abb)

