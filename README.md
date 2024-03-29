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

https://refactoring.guru/fr/design-patterns/abstract-factory

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

https://refactoring.guru/fr/design-patterns/builder

Ce pattern permet d'abstraire la construction d'objet complexes de leur implementation de sorte qu'un client puisse créer des objets complexes sans avoir a se preocuper des differences d'implementation.

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/462c1621-c145-436a-9364-8f5f9b64f62c)

Pourquoi utiliser ce pattern: 
- le client a besoin de construire des objets sans connaitre leur implementation
- un client a besoin de construire des objets complexes ayant plusieurs representations ou implementations

### Le pattern Factory Method

https://refactoring.guru/fr/design-patterns/factory-method

Le but de ce pattern est d'introduire une méthode abstraite de création d'objet en reportant la aux sous-classes concretes la création effective. 

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/5efe4adc-1b73-4e91-a0a5-b4f22d4d68a0)

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/515309d5-5cdb-4b10-9513-30004e8aa0a5)
![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/3ae7082c-7249-47f2-95ae-8abee5248ea6)

### Le pattern Singleton

https://refactoring.guru/fr/design-patterns/singleton

Il faut s'assurer de deux choses lorsqu'on veut mettre en place ce pattern:
- Une classe ne doit posseder qu'une seule instance
- Il faut fournir une méthode de classe qui permet de fournir cette instance unique

### Le pattern Prototype

https://refactoring.guru/fr/design-patterns/prototype

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

https://refactoring.guru/fr/design-patterns/adapter

Le but ici est d'adapter l'interface d'une classe donnee afin qu'elle puissent interagir avec un client

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/d4934791-abf9-4abe-9ec6-cf143094bef2)

### Le pattern Decorator

https://refactoring.guru/fr/design-patterns/decorator

Le pattern Decorator est un pattern de structuration qui permet d'ajouter dynamiquement des fonctionnalités à un objet.

Ici, on cherche a ajouter des fonctionnalités suplémentaire a un objet en prenant soin de ne pas modifier son interface. Toutes modifications apportées par ce pattern sereont transparente vis a vis des clients.

Ce pattern constitue une alternative a l'heritage.

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/bd95fac3-216b-4e12-baae-532118179abb)

Le pattern Decorator peut être utilisé dasn les domains suivants:
- notre application souhaite ajouter dynamiquement des fonctionnalités à un objet sans modifier son interface, autrement dit sans avoir à modifier les clients de cet objet
- une application doit gérer des fonctionnalites qui peuvent être retirées dynamiquement
- l'utilisation de l'héritage n'est pas une option car la hhierarchie d'objets est déjà trop complexe.

### Le pattern Bridge

https://refactoring.guru/fr/design-patterns/bridge

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/063891f9-917c-49e8-a68a-1fd79914f648)
![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/ea7b6542-14cd-417d-8376-95cd8580fa8b)

C'est le principe d'ancapsuler complètement un objet dans un autre objet

### Le pattern Composite

https://refactoring.guru/fr/design-patterns/composite

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/621932d8-7e3b-4c63-9d3d-55420bce62e8)

Au sein de notre système de vente de véhicules, nous voulons représenter les sociétés clientes,
notamment pour connaître le nombre de véhicules dont elles disposent et leur proposer des offres de
maintenance de leur parc.
Les sociétés qui possèdent des filiales demandent des offres de maintenance qui prennent en compte le
parc de véhicules de leurs filiales.
Une solution immédiate consiste à traiter différemment les sociétés sans filiale et celles possédant des
filiales. Cependant cette différence de traitement entre les deux types de société rend l’application plus
complexe et dépendante de la composition interne des sociétés clientes.
Le pattern résout ce problème en unifiant l’interface des deux types de sociétés et en
utilisant la composition récursive. Cette composition récursive est nécessaire car une société peut
posséder des filiales qui possèdent elles-mêmes d’autres filiales.

## Les patterns de comportement

TODO: Ajouter la définition des patterns de comportements

![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/1349a3ac-3903-4007-bdd1-3fe5cc9785d0)
![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/43bdcaea-b484-4abc-9f8d-1ed2f73ac25f)
![image](https://github.com/MegaCretin/design-pattern-csharp/assets/74878108/c398831d-3c15-406d-8057-a52dbadadd4b)




