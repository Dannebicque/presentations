# Symfony - Écosystème

Symfony nécessite un écosystème d'outils et de conventions.

---

## Composer

[Composer](https://getcomposer.org/) est le gestionnaire de dépendances PHP. Il permet de déclarer et d'installer les bibliothèques nécessaires au projet (packages, bundles, packs).

- Exemple d'installation d'un projet skeleton :

```bash
composer create-project symfony/skeleton mon_projet
```

Composer est l'équivalent back-end de `npm`/`yarn` pour le front.

---

## Entité (modèle)

Une entité est une classe PHP qui représente une table en base de données. Elle contient les propriétés (colonnes) et la logique métier minimale.

Symfony utilise souvent [Doctrine](https://www.doctrine-project.org/) comme ORM pour faire le lien entre entités et tables.

---

## ORM (Object‑Relational Mapping)

Un ORM convertit les objets (entités) en requêtes SQL et inversement. Dans l'écosystème Symfony, Doctrine est l'ORM le plus courant.

Commandes utiles :

```bash
composer require symfony/orm-pack
php bin/console doctrine:database:create
php bin/console make:entity
php bin/console doctrine:migrations:diff
php bin/console doctrine:migrations:migrate
```

---

## Repository

Un `Repository` est une classe qui encapsule la logique de lecture (requêtes) pour une entité. On y place les méthodes complexes de récupération de données.

---

## Configuration : YAML, XML, PHP, Attributes

Symfony supporte plusieurs formats de configuration : YAML, XML, PHP. Historiquement on utilisait des annotations (via des commentaires), aujourd'hui on préfère les *attributes* PHP (depuis PHP 8) pour mettre la configuration au plus près du code.

Exemple d'attribut pour une route (PHP 8+) :

```php
use Symfony\Component\Routing\Annotation\Route;

#[Route('/bonjour', name: 'app_bonjour')]
public function bonjour() { ... }
```

---

## Routes

Les routes lient une URL à un contrôleur. Elles peuvent être définies en YAML, PHP, ou via attributes/annotations.

---

## Bundles

Les bundles sont des paquets réutilisables (modules) contenant du code, des services, des templates... Ils permettent de partager des fonctionnalités entre projets.

---

## Environnements

Symfony distingue par défaut `dev` et `prod` (et permet d'en ajouter d'autres). Les variables d'environnement sont définies dans `.env` ou `.env.local`.

Exemple :

```dotenv
APP_ENV=dev
APP_DEBUG=1
```

En `dev` : pas de cache, barre de debug. En `prod` : cache activé, erreurs masquées.

---

## Profiler (outil de debug)

Le Web Profiler (toolbar) est installé via un pack de développement :

```bash
composer require --dev symfony/profiler-pack
```

Il fournit la barre de débogage et le profiler visible en bas des pages en `dev`.

---

## Maker (génération de code)

Le MakerBundle facilite la génération d'entités, contrôleurs, formulaires, etc. :

```bash
composer require --dev symfony/maker-bundle
php bin/console make:entity
php bin/console make:controller
php bin/console make:form
```

---

## Packs utiles (exemples)

- ORM : `composer require symfony/orm-pack`
- Twig : `composer require symfony/twig-pack`
- API Platform : `composer require api`
- Web profiler : `composer require --dev symfony/profiler-pack`

---

## Moteur de templates

Symfony utilise Twig par défaut. Il existe des packs pour intégrer Twig et les outils associés :

```bash
composer require symfony/twig-pack
```

---

## Conseils pratiques pour les étudiants

- Toujours commencer par `composer install` après avoir récupéré un projet.
- Utiliser `symfony server:start` (ou `symfony serve`) pour le développement local.
- Versionnez `composer.lock` mais ne commitez pas `.env` contenant des secrets.
- Préférez les *attributes* PHP pour les nouvelles applications (lisibilité et autocomplétion).
