# Pré-requis

* PHP (tableaux, boucles, tests, variables ...)
* Programmation Orientée Objet (WR313a/WR313e)
* Structure MVC (dès demain !)
* Base de données

---

# Support

Le support est disponible ici : https://docs.mmi-troyes.fr/books/wr313-wr319-2026

---

# CM N°1

* Qu'est ce que Symfony
* Les grands concepts d'un framework

---

# Les concepts du MVC

Le MVC (Model-View-Controller) est un patron de conception qui sépare les responsabilités d'une application en trois parties :

* **Model (Modèle)** : représente les données et la logique métier. Il interagit avec la base de données et contient les règles de gestion.
* **View (Vue)** : est responsable de la présentation des données. Elle génère l'interface utilisateur à partir des données fournies par le modèle.
* **Controller (Contrôleur)** : gère les interactions de l'utilisateur, traite les requêtes, et décide quelle vue afficher en fonction des actions de l'utilisateur.

---

# Avantages du MVC

* **Séparation des responsabilités** : chaque composant a un rôle spécifique, ce qui facilite la maintenance et l'évolution de l'application.
* **Réutilisabilité** : les composants peuvent être réutilisés dans différentes parties de l'application ou dans d'autres projets.
* **Testabilité** : la séparation des composants facilite l'écriture de tests unitaires et fonctionnels.
* **Flexibilité** : il est plus facile de modifier ou de remplacer un composant sans affecter les autres parties de l'application.

---

# Inconvénients du MVC

* **Complexité** : la mise en place du MVC peut être complexe pour les petites applications ou pour les développeurs débutants.
* **Courbe d'apprentissage** : il peut être nécessaire de comprendre les concepts du MVC et de l'architecture logicielle pour l'utiliser efficacement.
* **Surcharge de code** : dans certaines situations, le MVC peut entraîner une augmentation du nombre de fichiers et de classes, ce qui peut rendre le projet plus difficile à gérer.

---

# Pour résumer le MVC

![Schéma du MVC](ressources/r319/mvc.png) (produit avec ChatGPT)

---

# Patterns

Pour votre culture, il existe de nombreux *patterns* (modèles de conception) qui sont des solutions réutilisables à des problèmes courants dans le développement logiciel. Par exemple (non exhaustif) :

*   **Singleton** : garantit qu'une classe n'a qu'une seule instance et fournit un point d'accès global à cette instance.
*   **Factory** : crée des objets sans spécifier explicitement la classe concrète à instancier.
*   **Observer** : définit une dépendance un-à-plusieurs entre des objets, de sorte que lorsqu'un objet change d'état, tous ses dépendants sont notifiés automatiquement.
*   **Strategy** : permet de définir une famille d'algorithmes, de les encapsuler chacun dans une classe à part et de les rendre interchangeables.