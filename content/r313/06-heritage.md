# Concept N°4 : Héritage

---

# Concept N°4 : Héritage

* Les classes sont organisées hiérarchiquement
* Vous pouvez définir des classes comme points de départ d’autres classes plus spécifiques : spécialisation
* Comme dans un arbre généalogique, les ancêtres transmettent des propriétés et des comportements à leurs descendants.

---

<img src="ressources/r313/jhi4_ei3k_210111.jpg" width="400px" style="border:0px;"/><br>
<a href="https://fr.freepik.com/vecteurs-libre/diagramme-montrant-arbre-genealogique-trois-generations_16267270.htm#query=arbre%20genealogique&position=0&from_view=keyword&track=ais">Image de brgfx</a> sur Freepik

---

# Concept N°4 : Héritage

* La profondeur d’héritage n’est pas limitée
* Les enfants savent déjà faire tout ce que leurs parents peuvent faire
* Le polymorphisme est un mécanisme qui permet à une sous classe de redéfinir une méthode dont elle a hérité tout en gardant la même signature de la méthode.
* Les classes des enfants peuvent surcharger l’implémentation des classes de leurs parents
  * Exemple : CompterCotes() peut être codé différemment pour un Triangle et un Rectangle

---

# Question N°7 : Héritage

````php [1-9|11-15]
class Animal {
  public $name;
  public function __construct($name) {
    $this->name = $name;
  }
  public function eat() {
    echo $this->name . " is eating.";
  }
}

class Dog extends Animal {
  public function bark() {
    echo $this->name . " is barking.";
  }
}

$dog = new Dog("Fido");
$dog->eat(); // Output: Fido is eating.
$dog->bark(); // Output: Fido is barking.
``

---

# Le code hérité :

* Est plus **facile** à écrire
  * Lors de leur création, les classes enfants sont déjà partiellement écrites (réutilisation automatique du code)
  * Surcharge = spécialisation du code
* Est plus **stable**
  * Les classes enfant sont construites sur les fondations éprouvées de leurs parents
* Simplifie la **maintenance**
  * Les méthodes communes aux parents et aux enfants limitent la duplication de code

---

# Pour résumer ...

* L’héritage est un mécanisme qui permet de définir une classe à partir d’une autre classe existante
* La classe existante est appelée la **classe parent**
* La nouvelle classe est appelée la **classe enfant**
* La classe enfant hérite de **toutes les propriétés et méthodes** de la classe parent (sauf si elles sont privées)
* La classe enfant peut surcharger les méthodes de la classe parent

---

# Vous savez tout ! (ou presque)

## Comment vous y mettre dès demain ?

* Pensez différemment la programmation
* Exemples disponibles sur Internet
* Suivez et impliquez-vous dans les TD et les TP : faites le grand plongeon

---

<iframe src="https://giphy.com/embed/14uzPzKMOuVIPu" width="480" height="477" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/14uzPzKMOuVIPu">via GIPHY</a></p>
