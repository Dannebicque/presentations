# POO - CM 2 - Point d'étape

* Quelques rappels et précisions
* Des compléments
  * Méthodes magiques
  * Manipuler des objets
* Précisions sur le TP Noté et l'évaluation

---

# Créer une classe (rappels)

* Une classe est la définition d’un objet
  * Des propriétés = variables
  * Des méthodes = fonctions  comportements de l’objet
* UN CODE BIEN ECRIT
  * Distinguer la classe de l’application  un fichier pour la classe, un fichier pour l’application
  * Organiser les classes et les applications dans des dossiers
* Conventions de nommage :
  * Classe : le nom commence par une majuscule
  * Objet, variable en minuscules

---

# Utiliser une classe (rappels)

* Un objet est une instance d’une classe. 
* On créé autant d’objets que l’on souhaite.
* Objet créé grâce à l’instruction NEW. 
  * ```php $unobjet=new Uneclasse(…)```
* Objet détruit grâce à l’instruction UNSET
  * ```php unset($unobjet)```
* La création des objets se fait dans l’application

---

# Créer une application

* On entend par application, la mise en œuvre des classes : créer des objets, manipuler les objets
* Une classe = fichier .php distinct
* Dans l’application fichier .php : utilisation de l’instruction require (ou include)

---

# Créer une application avec un framework

Les quelques règles précédentes peuvent varier dans la mise en pratique avec un framework, type Symfony ou Laravel.

La manière de nommer les classes, où les mettre, comment les appeler ... sont imposés par le framework.

Exemple Symfony prefixe les controllers (qui sont des classes), vous pouvez créer vos propres classes dans le dossier src...

---

# Le constructeur

* Méthode particulière **magique** appelée dès la création de l’instance (new)
* Généralement utilisée pour initialiser les valeurs des propriétés mais pas seulement
* N’est pas obligatoire
* Syntaxe

```php
public function __construct($arg1, $arg2) {
	$this->attribut1=$arg1;
	$this->attribut2=$arg2;
}
```

---

# Le constructeur

* Précisions
* Toutes les propriétés de votre classe ne doivent pas nécessairement être initialisées par le constructeur
* Le constructeur peut initialiser les propriétés qui ne sont pas en paramètres, exemple :
    
```php
public function __construct($arg1, $arg2) {
	$this->attribut1=$arg1 * $arg2;
	$this->attribut3=$arg2 * 0,20;
}
```

---

# Le destructeur

* Méthode particulière **magique** appelée à la suppression de l’instance (unset)
* n'est pas obligatoire
* Syntaxe

```php
public function __destruct() {
    // code à exécuter
}
```

--- 

# Propriétés et méthodes statiques

* Une propriété ou une méthode statique est accessible sans avoir besoin d’instancier la classe
* Une propriété ou une méthode statique est déclarée avec le mot clé static
* Une propriété ou une méthode statique est appelée avec le nom de la classe
* Une propriété ou une méthode statique est appelée avec le symbole ::
* Une méthode ou propriété statique ne peut pas utiliser $this
* Une méthode ou une propriété statique est partagée par toutes les instances d'une classe


---

# Propriétés et méthodes statiques

* Exemple :

```php
class MaClasse {
    public static $attribut = 0;
    public static function methode() {
        echo "Je suis une méthode statique";
    }
}
```

* Utilisation
```php MaClasse::$attribut;```
* ou
```php MaClasse::methode();```

---

# L'encapsulation

* But : créer du code fiable, assurer la cohérence des données
* Concerne les propriétés et les méthodes
* 3 niveaux de visibilité : 
  * **Public** : accessible en dehors de la classe : pas d’encapsulation
  * **Private** : accessible uniquement dans la classe
  * **Protected** : accessible dans la classe et dans les classes filles si héritage
* Accéder à une propriété encapsulée oblige l’utilisation d’une méthode
  * Pour lire la valeur : méthode appelée accesseur ou _getter_
  * Pour modifier la valeur : méthode appelée mutateur ou _setter_

---

# L'encapsulation

* Exemple :

```php
class MaClasse {
    private int $attribut = 0;
    public function getAttribut() {
        return $this->attribut;
    }
    public function setAttribut(int $valeur) {
        $this->attribut = $valeur;
    }
}
```
* Utilisation
```php $objet->getAttribut();```

* ou

```php $objet->setAttribut(10);```

---

# Quand utiliser Public, Private, Protected ?

* Il n’y a pas de règle explicite pour le choix de la visibilité.
* Il existe deux "écoles"
  * Celle du tout ouvert, et donc de maximiser les propriétés et méthodes public.
    * Avantages :
      * Accès facilité, grande interopérabilité, réduction des erreurs de visibilité, plus grande "transparence" car tout est exposé.
    * Inconvénients :
      * Aucune maîtrise/sécurité a priori, sur les modifications des propriétés,

---

# Quand utiliser Public, Private, Protected ?

* Celle du tout en "private" (pour les propriétés)
  * Avantages:
    * Maîtrise complète des opérations sur les propriétés, car obligation de passer par des getters et des setters.
  * Inconvénients:
    * Lourdeur du code, beaucoup de méthodes ajoutées (getters et setters), même lorsque l’on fait de l’héritage

---

# Quand utiliser Public, Private, Protected ?

* Juste milieu et contexte
  * En fait, il faut s’intéresser au contexte et à l’application que vous développez.
  * L’utilisation de tests, de méthodes de développement avancées (TDD Test Data Driven), peuvent permettre d’affiner les visibilités.

* Et pour nous, étudiants ?
  * Le choix le plus judicieux reste la visibilité protected, et l’utilisation de getters et de setters sur les propriétés pour lesquelles cela est pertinent.

---

# L'héritage

* But : technique de spécialisation d’une classe. 
* La classe fille (enfant) hérite de toutes les propriétés et des méthodes de la classe mère (parent)
* La classe fille peut être spécialisée :
  * par l’ajout de propriétés
  * par l’ajout de méthodes
  * par le redéfinition des méthodes : méthodes de mêmes noms peuvent avoir des comportements différents ou effectuer des opérations sur des données de types différents. C’est le **polymorphisme** (peut prendre plusieurs formes)

---

# L'héritage

* Exemple :

```php
class MaClasseMere {
    protected string $nom = 'Texte';
    
    public function methode() {
        echo "Je suis une méthode de la classe mère";
    }
}
class MaClasseFille extends MaClasseMere {
    public function methodeFille() {
        echo "Je suis une méthode de la classe fille";
        echo $this->nom; //je peux accéder aux propriétés de la classe mère
    }
}
```

---

# L'héritage

* Exemple :

```php
class MaClasseMere {
    
    public function methode() {
        echo "Je suis une méthode de la classe mère";
    }
}
class MaClasseFille extends MaClasseMere {
    public function methode() {
        echo "Je suis une méthode de la classe fille qui remplace le comportement de la classe mère";
    }
}
```

---

# L'héritage

* Exemple :

```php
class MaClasseMere {
    
    public function methode() {
        echo "Je suis une méthode de la classe mère";
    }
}
class MaClasseFille extends MaClasseMere {
    public function methode() {
        echo parent::methode()." Je suis une méthode de la classe fille qui complète le comportement de la classe mère";
    }
}
```

---

# L'héritage

* Héritage multiple : une classe fille (enfant) peut être une classe mère (parent)
* Ne pas oublier : propriété déclarée protected, ne sont visibles que par les classes filles.
* Classe abstraite : mot clé **abstract**
  * permet de créer des modèles de classe : propriétés et méthodes communes à plusieurs classes
  * Ne peut pas être instanciée
* mot clé **final**
  * une classe est déclarée **final** ne peut pas avoir de classe fille
  * Une méthode déclarée **final** ne peut pas être surchargé

---

# Résolution de portée

* Opérateur appelé "double deux points" ::, a été abordé dans l’héritage
* Trois mots-clés :
  * parent:: (classe parent)
    * Ex : `parent::__construct(…);`
  * self:: (classe elle-même)
    * Ex : `self::$varstatique`
  * nomdelaclasse:: (spécifie le nom de la classe)
    * Ex : `nomdelaclasse::__construct(…)`

---

# Méthodes magiques

* Les méthodes magiques sont des méthodes qui sont appelées automatiquement par PHP, lors de certains événements
* Elles sont définies par des noms spéciaux, commençant par double underscore __
* Exemples :
  * __construct() : appelée à chaque instanciation de la classe
  * __destruct() : appelée à la fin du script ou à la destruction de l’objet
  * __get() : appelée lors de l’accès à une propriété non définie
  * __set() : appelée lors de l’assignation à une propriété non définie
  * __call() : appelée lors de l’appel à une méthode non définie
  * __toString() : appelée lors de l’appel à la méthode echo sur un objet
  * __isset() : appelée lors de l’appel à la fonction isset() sur une propriété non définie
  * __unset() : appelée lors de l’appel à la fonction unset() sur une propriété non définie

---

# Méthodes magiques

* Exemple :

```php
class MaClasse {
    protected string $nom = 'Texte';
    
    public function __construct() {
        echo "Je suis le constructeur de la classe";
    }
    public function __destruct() {
        echo "Je suis le destructeur de la classe";
    }
    public function __get($nom) {
        echo "Je suis la méthode magique __get()";
    }
    public function __call($nom, $arguments) {
        echo "Je suis la méthode magique __call()";
    }
}
```

---

# Les interfaces

* Une interface est une liste de méthodes à implémenter
* Une classe peut implémenter plusieurs interfaces
* Une classe qui implémente une interface doit définir toutes les méthodes de l’interface
* Une classe peut hériter d’une classe mère et implémenter plusieurs interfaces
* Une interface peut étendre une autre interface
* Une interface ne peut pas être instanciée
* Une interface ne peut pas contenir de propriétés, de méthodes privées, de méthodes statiques, de méthodes magiques
* Une interface est un contrat entre les usagers (les développeurs d’un projet) des différentes classes.
  * Une interface va décrire l’ensemble des méthodes existantes dans une classe
  * Mais sans décrire comment ces méthodes feront pour arriver au résultat

---

# Les interfaces

* L’idée est donc de décrire l’ensemble des méthodes d’une classe.
* On ne va donc retrouver que les noms des méthodes et leurs paramètres.
* Mais pas leur contenu.
* Exemple :

```php
interface Interface1 {
    public function methode1();
    public function methode2();
}
```

---

# Les interfaces

* Exemple :

```php
class MaClasse implements Interface1 {
    public function methode1() {
        echo "Je suis la méthode 1";
    }
    public function methode2() {
        echo "Je suis la méthode 2";
    }
}
```

---

# Héritage et interfaces

* Exemple :

```php
interface Interface1 {
    public function methode1();
    public function methode2();
}

interface Interface2 extends Interface1 {
    public function methode3();
}
```

---

# Héritage et interfaces

* Exemple :

```php
class MaClasse implements Interface2 {
    public function methode1() {
        echo "Je suis la méthode 1";
    }
    public function methode2() {
        echo "Je suis la méthode 2";
    }
    public function methode3() {
        echo "Je suis la méthode 3";
    }
}
```

---

# Les interfaces (synthèse)

* Les interfaces sont des types de données qui définissent un ensemble de méthodes.
* Les méthodes doivent être définies par toute classe qui implémente l’interface.
* Une interface est similaire à une classe, mais
  * contiennent uniquement des déclarations de méthodes, pas leur implémentation
  * ne peuvent pas avoir d’attributs tels que public ou private
* Intérêt : Une conception rigoureuse et évite les oublis (travail en équipe)










