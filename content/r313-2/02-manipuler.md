# Manipuler les objets

* Comparer les objets
* Parcourir les objets

---

# Identifiant d’objet et clonage

* Lors de l’instanciation, on donne un identifiant à l’objet
  * `$a = new Objet();`
* Ecrire `$b=$a` est équivalent à donner deux identifiants pour le même objet
* Pour cloner un objet, on utilise l’instruction clone 
  * `$b = clone $a;`
  *  ```php
     public function __clone() { 
        $this->instance = ++self::$instances;
     } 
     ```

---

# Comparer les objets

* On peut comparer deux objets avec l’opérateur `==` ou `===`
  * `if ($a == $b) { ... }`
* `==` compare les valeurs de tous les attributs de chaque objet.


