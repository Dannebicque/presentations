# Concept N°3 : Encapsulation

---

# Concept N°3 : Encapsulation

Un objet renferme ses propriétés et ses méthodes (selon la définition donnée par la classe).

<img src="ressources/r313/encapsulation.png" width="500px" style="border:0px;" />

---

# Sans encapsulation

* Toutes les données de mon objet sont accessibles en dehors de celui-ci, sans aucun contrôle sur les modifications réalisées
* => **Danger pour les données** !

---

# Avec l'encapsulation

* Les données ne sont pas accessibles en dehors de l'objet
* Il faut utiliser des **accesseurs** pour accéder aux données
  * Permet de rajouter, si besoin, une couche de contrôle des données en entrée et/ou en sortie

---

# Exemple sans encapsulation

* Une classe (on reviendra sur le détail du code)

```php
class Personne {
  public $age;
  public $prenom;
  ...
}
```
* son utilsation (un objet est instancié)

```php
$p = new Personne();
$p->age = 'David';
$p->prenom = 30;
```

---

# Exemple sans encapsulation

Ce code est syntaxiquement correct, et rien ne va interdire de mettre un nombre dans prénom et une chaîne de caractères dans âge.

Une erreur se déclenchera peut-être, plus tard lors de l'utilisation de cet objet (par exemple augmenter l'age)

---

# Exemple avec encapsulation

* Une classe (on reviendra sur le détail du code)

```php
class Personne {
  private $age; //on change public par private
  private $prenom; //on change public par private
  ...
}
```
* son utilsation (un objet est instancié)

```php
$p = new Personne();
$p->age = 'David';
$p->prenom = 30;
```

Ce code va provoquer une erreur, on ne peut plus accéder directement.

---

# Exemple avec encapsulation

* Une classe (on reviendra sur le détail du code)

```php
class Personne {
  ...
  
  public function setAge($age) {
   if (is_int($age)) { //on peut faire un test
      $this->age = $age;
   } else {
      echo 'indiquer un nombre';
   }
  }
}
```

* son utilsation (un objet est instancié)

```php
$p = new Personne();
$p->setAge(30);
```

---

# Exemple avec encapsulation

Le code est un peu plus long, mais plus fiable. On peut ajouter des tests pour s'assurer que les bonnes informations sont passées dans les propriétés.

---

# Autres avantages

Lorsque l'on travaille à plusieurs, on est sûr que les données ne sont pas modifiées par un autre développeur et on est certain des données que l'on récupère.

---

# Exemple

Lorsque l'on travaille à plusieurs, on est sûr que les données ne sont pas modifiées par un autre développeur et on est certain des données que l'on récupère.

<img src="ressources/r313/encaps1.png" width="600px" style="border:0px;"/>

---

# Exemple

Programme : les données d'un cercle sont une couleur et un rayon. Le code fournit un diamètre, une aire et une circonférence.

<img src="ressources/r313/encaps2.png" width="600px" style="border:0px;"/>

---

# Exemple

Solution 1

<img src="ressources/r313/encaps3.png" width="600px" style="border:0px;"/>

---

# Exemple

Solution 2

<img src="ressources/r313/encaps5.png" width="600px" style="border:0px;"/>

---

# Question N°6 : Encapsulation

Expliquez les avantages que représente l’encapsulation lorsque vous avez à conduire plusieurs types ou marques de véhicules.

<img src="ressources/r313/encaps6.png" width="600px" style="border:0px;"/><!-- .element: class="fragment" data-fragment-index="1" -->

---

# L'encapsulation est 

* plus **facile** à écrire
  * Chaque composant qui utilise des données peut utiliser la forme la plus adaptée de ces données
* plus **stable**
  * Moins de code doit être modifié si le format des données change
* plus simple pour la **maintenance**
  * Moins de code doit être modifié pour introduire de nouvelles fonctionnalités ou corriger des bugs.

---

# Pour résumer

* L'encapsulation c'est interdire l'accès direct aux propriétés d'un objet
* C'est ajouter des assesseurs (getters et setters) pour accéder aux propriétés
* C'est ajouter des contrôles sur les données en entrée et/ou en sortie
