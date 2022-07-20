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
