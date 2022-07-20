# Concrétement en PHP ?

Les concepts sont les mêmes quelque soit leur langage, mais leur mise en place peut dépendre du langage. Même si la logique est souvent assez similaire.

Nous verrons donc dans cette partie comment cela se concrétise en PHP, et nous ferons le lien avec Symfony.

---

# Définir une classe en PHP

```php [2,17|4-5|8-11|13-16]
<?php
class UneClasse {
    // les propriétés
    public $propriete1;
    public $propriete2;

    // les méthodes
    public function methode1() 
    {
        //une méthode est une fonction en PHP
    }

    public function methode2($arg1, $arg2) 
    {
        //une autre méthode possédant deux arguments obligatoires
    }
}
?>
```

---

# Déclarer une instance de classe

```php [2-9|3|5|11|12|14-15]
<?php
class Voiture {
    public string $marque;

    function freiner(float $forceDeFreinage): void 
    {
        //code de la fonction
    }
}

$mavoiture = new Voiture();
$mavoiture->marque = 'Renault';

echo 'Marque de ma voiture : ';
echo $mavoiture->marque;
?>
```

---

# Execution du code en "mémoire"

Illustration...

---

# Typage en PHP

Quelques mots sur le typage en PHP. Depuis les vers 7.2 et suivante le typage en PHP a été grandement amélioré, et même s'il n'est pas obligatoire est devenu la norme depuis PHP 7.4 et 8 (et suivantes).

**Symfony** tout comme PHP n'impose pas le typage, ceci étant, si vous utilisez des outils de qualité de code, des tests, si vous intervenez sur des projets, ... il y a fort à parier que le code est typé ou qu'il doivent obligatoirement l'être. C'est donc une **très bonne** habitude à prendre.

Cela permet aussi d'aider vous outils à vous indiquer si vous faites des erreurs dans votre code avant même son execution.

---

# Typage en PHP

... cours sur le typage...

---

# Le constructeur

* Le constructeur `__construct()` est une **méthode magique** (c'est à dire qui est automatiquement déclenché lorsque les conditions sont remplies, ici la création d'une instance d'une classe)

```php [1-30|8-17]
<?php
class Voiture
{
    public string $marque;
    public int $puissance;
    public float $kilometrage;

    public function __construct(
        string $arg1,
        int $arg2,
        float $arg3
    ) 
    {
        $this->marque = $arg1;
        $this->puissance = $arg2;
        $this->kilometrage = $arg3;
    }

    public function lireCaracteristiques() 
    {
        return 'Marque : '.$this->marque.', puissance : '.$this->puissance.', kilométrage : '.$this->kilometrage;
    }

    public function utiliser(float $distance)
    {
        $this->kilometrage += $distance;
        // équivalent à : $this->kilometrage = $this->kilometrage + $distance;
    }
}
?>
```

---

# Le constructeur

//schéma...

---

# Opérateur référent de l'objet (->)

```php [1-19|16]
<?php
class Voiture 
{
    public string $marque;

    ...

    public function freiner (int $forceDeFreinage)
    {
        //instruction de la méthode
    }
}

// Instanciation
$maVoiture = new Voiture();
$maVoiture->marque = 'Renault';

echo 'Marqu de ma voiture : ' . $maVoitureMarque;
?>
```

---

# Pour bien programmer en POO (sans framework)

* Séparer le code de définition des classes du code d’instanciation des classes
* Il faut donc créer deux fichiers PHP. Utiliser l’instruction `require('classe.php');` dans le fichier qui contient le code qui instancie.
  * Si vous avez beaucoup de classe ou que vous souhaitez automatiser l'inclusion de vos classes, vous pourriez utiliser le [mécanisme d'autoload de PHP](https://www.php.net/manual/fr/language.oop5.autoload.php) 
* Respecter les conventions de nommage : le nom d’une classe commence par une majuscule, une propriété est toujours en minuscules

