# ORéBUT, outil de rédaction des B.U.T.

https://github.com/dannebicque/redigeTonBut && https://orebut.iut.fr

---

# Préambule

Deux outils existent :

* L'intranet des deux IUT permettant un suivi complet de la scolarité des étudiants, des prévisionnels, des stages, de l'alternance, ...
  * pour les détails https://presentations.davidannebicque.fr/intranet
* ORéBUT pour la rédaction des PN des B.U.T.
  * c'est ici 

---

# Résumé

* En quelques mots, cet outil a permis aux 24 spécialités de B.U.T de construire leur programme pédagogique national et le référentiel de compétences.
* Les collégues devaient alimenter différents formulaires et tableaux avec un ensemble de vérification sur des contraintes, des rapports d’ECTS, des volumes horaires ...
* Les matières (ressources ou SAE en BUT) sont associées à des apprentissages critiques et des compétences. Des liens peuvent exister entre ressources (prérequis) et SAE (mobilisation des ressources).
* Les tableaux sont alimentés avec les fiches et réciproquement. Les « totaux » horaires sont contrôlés en rapport avec un cadre global défini nationalement et validé en amont.

---

# Contexte

* Rédiger les programmes des IUT qui impliquent des croisements avec le référentiel de compétences
* Croiser les volumes horaires, les coefficients, les ECTS et fixer les seuils
* Générer le document adapté reprenant l'ensemble des élèments
* Garantir la cohérence de l'ensemble des données.
* Garantir la forme du document produit respectant un modèle imposé

---

# Contexte

* 24 spécialités
* + 9400 pages générées en 24 PDF
* Accès ADIUT, CCN, CPN, GT BUT, PACD, IUT et DGESIP

---

# Aspects techniques

* Serveur LAMP
* PHP 8.1
* Symfony 6.1
* Base Bootstrap 5 pour le CSS
* Hébergé par l'ADIUT

---

# Calendrier de mise en place

* Idée en mai/juin 2021 (existant interne MMI pour la première version)
* Présentation en juillet 2021 d'un premier prototype
* Lancement en septembre 2021 pour les ACD
* Evolution jusqu'en février 2022 selon les "contraintes" et règles
* Mars 2022 premières éditions des versions officielles (modèle DGESIP)

---

# Fonctionnalités

* Saisie du référentiel de compétences
* Saisie des ressources et des SAE
* Croisements des AC et des ressources/SAE
* Saisie des ECTS, des volumes horaires et des coefficients
* Vérifications des données selon les règles imposées
* Plusieurs niveaux de blocage sont possibles pour valider et bloquer les différents éléments progressivement.

---

# Fonctionnalités

L’ensemble des éléments sont exportables :
* en word (fiche ressource/SAE individuelle), dans une version très limitée et sans mise en forme
* en Excel, divers tableaux et synthèses comparatives
* en PDF document complet ou fiche individuelle (modèle simple)
* en PDF format "DGESIP", en passant par un fichier LaTeX
* en XML

---

# Limitations

* Faire un Word avec une structure complexe n’est pas forcément très simple (avec la solution retenue et le temps alloué). 
* Faire un PDF est plus aisé et laisse une grande liberté.
* Passer par LaTeX permet une plus grande finesse dans la mise en page, mais implique, en l'état, une compilation manuelle (script à lancer)

---

# Limitations

Cet outil n’est pas « coopératif » dans le sens ou il n’est pas possible de travailler simultanément sur la même fiche (petite précaution à prendre pour définir qui édite). 

Plusieurs niveaux de droits existent avec un accès total à toutes les formations, un accès en lecture sur toutes les formations, en lecture sur une formation et éditable sur une formation. Sur l’édition plusieurs niveaux existent avec un accès complet sur une formation (création, suppression), et simple édition.

---

# Bilan 

* Au final l’outil a permis de générer un document PDF de plus de 9400 pages contenant le programme des 24 spécialités et 24 PDF individuels.

* En partant de cette base, j’ai généré pour l’IUT de Troyes et celui de Reims la structure de base du tableau des MCC de la DEVU dans lequel il ne restait qu’a indiqué le nombre d’évaluations et les heures d’adaptation locale.
* J'ai généré la codification Apogée pour la saisie par les scolarités
* J'ai alimenté les intranets pour proposer un PN complet aux collègues et étudiants

---

# Perspectives

* Dans l’état, il n’y a pas encore de gestion de version. Il faut préciser ce qu'on entend par versionning.
  * Versionning total type solution "git" ? (difficile à mettre en place en l'état de mes connaissances et temps)
  * Versionning par "snapshot" ? (chaque année universitaire une nouvelle version, plus simple à mettre en place, mais moins souple)

---

# Portage URCA d'ORéBUT

A priori pas de contraintes particulières, il convient de définir les périmètres :

* Notamment existe-t-il une base à importer ? Sous quel format ? (si API, base de données, c’est le plus simple, si document à définir). 
* Est-ce que l’ensemble des formations auront une structure similaire ?
* La proximité de la structure avec celle d’un B.U.T. (je pense que toutes sont plus simple a priori).
* Le type de document à produire.
* Quels services concernés et quelles données sont nécessaires ?

---

# Portage URCA d'ORéBUT

* Besoins :
  * Gestion du serveur par la DN
  * Partage des informations sur la structure du projet en cas de besoin
  * Selon l'importance envisager un stagiaire/alternant pour répondre aux besoins des différents services
  * Selon les documents à produire, il faudra de l'aide technique pour la production des documents (si sur base LaTeX par exemple)

---

# Portage URCA Intranet

* Pas de point bloquant pour un déploiement de tout ou partie (on peut activer et désactiver la presque totalité des fonctionnalités).
  * Manque la gestion des MCC, mais sera intégré d'ici à la rentrée de 2023 et la production des documents pour la DEVU
* Le point central, c'est le prévisionnel et la maquette. 

---

# Portage URCA Intranet

* La problématique, c'est le serveur, actuellement, un dans chaque IUT. Si ca doit se déployer plus largement, il faut une gestion centralisée du/des serveurs, sa maintenance 
  * Mais je dois conserver un accès SSH pour le déploiement des mises à jour. L’intranet est en évolution permanente, des mises à jour sont quasiment quotidiennes souvent esthétiques, mineures, d’améliorations d’ergonomie, et grosso modo à chaque vacance des évolutions majeures.

