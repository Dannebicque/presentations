# Intranet des IUT de Troyes et RCC

https://github.com/dannebicque/intranetV3 && https://documentation.iutranet.fr (WIP)

---

# Aspects techniques

* Serveur LAMP
* PHP 8.1
* Symfony 6.1
* Base Bootstrap 5 pour le CSS

---

# "Connectivité" (en lecture)

* Apogée
  * Récupération des maquettes (pas optimal)
  * Récupération des étudiants
  * Récupération des groupes
* Celcat
  * Récupération des emplois du temps
* LDAP
  * Récupération des utilisateurs

---

# "Connectivité" (en écriture)

* Apogée
  * Au travers d'un fichier "txt" pour les fins de semestre et l'import des notes

---

# Fonctionnalités pour les étudiants

* Consultation des notes
* Consultation des absences
* Dépôt de justificatifs d'absences
* Demandes de rattrapages
* Consultation de documents, d'informations
* Gestion des stages, des alternances
* Messagerie interne

---

# Fonctionnalités pour les enseignants

* Consultation de l'emploi du temps
* Saisie des absences et consultation des absents sur leurs modules
* Saisie des notes et consultation des notes sur leurs modules
* Suivi des stagiaires et des alternants
* Consultation des documents, des informations
* Messagerie interne pour communiquer avec les étudiants
* Trombinoscope par groupes

---

# Fonctionnalités pour les "responsables"

* Suivi des absences, des justificatifs
* Suivi des notes, sous-commissions (y compris B.U.T.), rattrapages
* Suivi des stages, des alternances (edition des conventions, suivi du process de signature)
* Dépôt de documents, d'informations
* Gestion des prévisionnels, des personnels du département
* Gestion des groupes, des cohortes
* Suivi qualité des formations (enquêtes)

---

# Autres fonctionnalités

- Plusieurs niveaux d'accès
- Lien avec le CAS
- Mutlilangue "ready" (partie étudiante en anglais)
- export CSV, XLS et PDF sur toutes les pages
- Et beaucoup d'autres : https://github.com/Dannebicque/intranetV3/blob/main/readme.md
- 

---

# En cours

* Gestion des plans de cours (démarche qualité)
* Suivi des présents (dans le cadre de l'alternance édition des documents de preuve de présence)
* Accessibilité (déjà RGAA AA pour les étudiants)
* Optimisation des performances (cache, optimisation des requêtes, ...)

---

# A venir, sous réserve d'accès

* Intégration de YouSign pour les conventions de stage (API)
* Certification RGS pour les feuilles de présences

---

# "Besoin" vis à vis de la DN

* Si ca reste "IUT", éventuellement 
  * Accès API YouSign (ou équivalent) ? Celcat ? (plus simple que la BDD)
  * Accompagnement sur la gestion des serveurs et la sécurisation (notamment IUT RCC)
* Si on étend UFR/composantes/formations
  * Gestion des serveurs (mutualisation URCA plutôt que par IUT?)
  * Accompagnement sur le développement bienvenu (notamment pour intégrer une vraie couche de test, CI/CD, optimisation, ...)
    * Alternances, stages ?
* Globalement au niveau "URCA"
  * Difficultés pour acheter des "licences" sur des outils (ex: BugSnag, travisCI (ou CodeClimate), Netlify, licence fontawesome ou éq., ...)
    * Entreprise souvent américaine (pas de BC, paiement CB, refus de compléter des docs administratifs, ...)

---

# Si on souhaite déployer...

* A priori, c'est prêt.
  * L'intranet gère toutes les formes de formations (B.U.T, DUT, Licence, Master, ...)
* Reflexion sur les modalités d'hébergement
  * centralisé ?
  * décentralisé par UFR (comme actuellement ?)


---

# Quelques chiffres

* 159 tables
* plus de 170 000 lignes de code (hors framework)
* 770 heures depuis septembre 2021
* Version 3
  * version 1 sous codeignitier (uniquement MMI, 2013-2017)
  * version 2 sous SF 2->4 (tout l'IUT, février 2018 jusqu'en 2020)
  * version 3 depuis la rentrée 2020 (IUT Troyes), 2021 (IUT RCC)
