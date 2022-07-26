# TP Noté

* Mise en œuvre des concepts POO abordés
* Ecriture complète de classes et d’applications
* Important :
  * Soyez structuré : noms des fichiers, dossiers,…
    * A minima vous savez écrire la structure de votre classe (propriétés, méthodes, visibilités)
    * Commentez toujours votre code
  * Recherchez le code dans la documentation en ligne ou dans vos TD.
* C’est un travail personnel

---

# TP Noté de POO

durée 1h15, pas de retard accepté / Pas de Symfony.

* A : TP Noté 07/12, 14h00 
* B : TP Noté 07/12, 14h00 
* E : TP Noté 07/12, 8h00
* F : TP Noté 06/12, 8h00

---

# Evaluation écrite

le 15/12, QCM portant sur la POO et sur Symfony. Durée 1h00.

* A partir d’exemple de codes PHP
  * Interpréter le code
  * Repérer des erreurs
  * Proposer des solutions

* Il n’y aura pas d’écriture de code
* Il faudra connaître les concepts et comprendre les concepts pour analyser le code.

---

# Exemple

<div class="col1">
Soit le code suivant

```php
Class A {
  Public $var1;
  Public $var2;
  
  Public function __construct($var1, $var2)
  { 
  …
  }
…
}
```
</div>
<div class="col2">

* Cette classe fait-elle de l'encapsulation ?
* Combien de propriétés ?
* Utilise-t-elle des méthodes magiques ?

</div>

---

# Exemple

<div class="col1">
Soit le code suivant

```php
Class A {
  Protected $var1;
  Protected $var2;
  
  Public function __construct($var1, $var2)
  { …
  }
  
  Public function getVar1()
  {…}
  
  Public function getVar2()
  {…}
}
```
</div>
<div class="col2">

* Cette classe fait-elle de l'encapsulation ?
* Combien de propriétés ?
* Utilise-t-elle des méthodes magiques ?

</div>

---

# Exemple

<div class="col1">
Soit le code suivant

```php
Class A {
  Protected $var1;
  Protected $var2;
  
  Public function __construct($var1, $var2)
  { …
  }
  Public function getVar1()
  {…}
  Public function getVar2()
  {…}
}

Class B extends A {
…
}

```
</div>
<div class="col2">

* Cette classe fait-elle de l'encapsulation ?
* Combien de propriétés ?
* Utilise-t-elle des méthodes magiques ?
* Combien de propriété possède la classe B ?

</div>

---

# Des questions ?
