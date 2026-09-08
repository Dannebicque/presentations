# Symfony

![Symfony](ressources/r319/logosymfony.png)

---

## Introduction

Symfony est un framework PHP moderne, structuré autour du modèle MVC et d'un noyau HTTP puissant. Conçu pour des applications web de toutes tailles, il met l'accent sur la réutilisabilité (composants), la maintenabilité (architecture claire) et l'écosystème (bundles, packs, et outils).

> Remarque : Symfony a évolué progressivement (4→5→6) — vérifiez la version requise pour vos projets sur https://symfony.com.

---

## Pourquoi utiliser Symfony ?

- **Robuste :** adapté aux petits projets comme aux applications d'entreprise.
- **Écosystème riche :** composants réutilisables, bundles et packs communautaires.
- **Productivité :** outils officiels (Symfony CLI, MakerBundle, Debug toolbar).
- **Bonnes pratiques intégrées :** tests, sécurité, validation, architecture claire.
- **Interopérable :** fonctionne avec Doctrine, API Platform, et la plupart des SGBD.

---

## Composants et bundles

- **Composants natifs :** HttpFoundation, Routing, Console, DependencyInjection, Security, Form, Mailer, Serializer...
- **Bundles officiels :** fournis par l'équipe (ex. WebProfiler, SecurityBundle) pour ajouter des fonctionnalités prêtes à l'emploi.
- **Bundles communautaires :** backoffice, upload, génération de documents, etc. (voir Packagist).

---

## Évolution (rapide)

- Symfony 4 : introduction de Flex et du skeleton pour simplifier l'initialisation de projets.
- Symfony 5 : consolidation et simplification des conventions.
- Symfony 6 : adoption des versions modernes de PHP (PHP 8+), API améliorées et optimisations.

---

## Concepts clés (à connaître)

- **Request → Kernel → Response :** flux central d'une requête HTTP traitée par le framework.
- **Contrôleurs :** actions qui reçoivent des requêtes et retournent des réponses.
- **Routing :** correspondance URL → contrôleur.
- **Services & DI :** logique réutilisable fournie via injection de dépendances.
- **Doctrine (ORM) :** mapping objet-relationnel couramment utilisé.
- **Twig :** moteur de templates par défaut.
- **Formulaires & Validation :** gestion déclarative des formulaires et règles de validation.
- **Security :** authentification, autorisation, rôles et voters.
- **Messenger, EventDispatcher, Console :** fonctionnalités avancées pour files de messages, événements et tâches CLI.

---

## Installation rapide (prérequis)

- PHP (version recommandée : PHP 8.1+ selon les projets)
- Composer
- Symfony CLI (facultatif mais recommandé)

Exemples :

```bash
# via Composer (skeleton)
composer create-project symfony/skeleton mon_projet

# via la CLI Symfony
symfony new mon_projet --full

cd mon_projet
symfony serve
```

Pour ajouter des outils utiles :

```bash
composer require symfony/maker-bundle --dev
composer require orm doctrine
composer require twig
```

---

## Exemple simple de route et contrôleur

Routing (config/routes.yaml) :

```yaml
home:
  path: /
  controller: App\\Controller\\HomeController::index
```

Contrôleur (src/Controller/HomeController.php) :

```php
namespace App\\Controller;

use Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;
use Symfony\\Component\\HttpFoundation\\Response;

class HomeController extends AbstractController
{
    public function index(): Response
    {
        return $this->render('home/index.html.twig');
    }
}
```

---

## Outils et bonnes pratiques

- Utiliser `symfony server:start` (ou `symfony serve`) pour le dev.
- `composer require --dev symfony/debug-bundle` et `maker-bundle` pour accélérer le développement.
- Tester avec PHPUnit et les utilitaires de test fournis par Symfony.
- Utiliser Docker en production si nécessaire et la CLI pour déployer.

---

## Ressources pour apprendre

- Site officiel : https://symfony.com
- Documentation : https://symfony.com/doc
- Tutoriels : https://symfonycasts.com
- Composants : https://symfony.com/components
- Packages : https://packagist.org

---

## Diagramme : Principe de fonctionnement

<img src="ressources/r319/request-response.png" width="600px" style="border:0px;"/>

