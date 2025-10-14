# Intranet des IUT de Troyes et RCC

https://github.com/dannebicque/intranetV3 && https://github.com/IUTTroyes/uniServices (V4-WIP)

---

# Aspects techniques

* Serveur LAMP
* PHP 8.3
* Symfony 7.2
* Base Bootstrap 5 pour le CSS
* RGPD

---

# "Connectivité" (en lecture)

* Apogée
  * Récupération des maquettes (pas optimal) => Passage sur ORéOF pour la V4
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

* Consultation de l'emploi du temps
* Consultation des notes + bilan semestriel
* Consultation des absences
* Dépôt de justificatifs d'absences
* Demandes de rattrapages
* Consultation de documents, d'informations
* Gestion des stages, des alternances
* Messagerie interne
* ...

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
* Historisation des données sur toute la scolarité des étudiants
* Gestion des plans de cours (démarche qualité)
* Suivi des présents (dans le cadre de l'alternance édition des documents de preuve de présence) + lien avec EduSign (car pas de lien celcat-edusign)

---

# Autres fonctionnalités

- Plusieurs niveaux d'accès
- Lien avec le CAS
- Multilangue "ready" (partie étudiante en anglais)
- export CSV, XLS et PDF sur toutes les pages
- Et beaucoup d'autres : https://github.com/Dannebicque/intranetV3/blob/main/readme.md

---

# En cours / Todo

* Contrat Pédagogique étudiant (obligation des B.U.T.)
* Accessibilité (déjà RGAA AA pour les étudiants)
* Optimisation des performances (cache, optimisation des requêtes, ...)

---

# Si on souhaite déployer...

* A priori, c'est prêt.
  * L'intranet gère toutes les formes de formations (B.U.T, DUT, Licence, Master, ...)
* Reflexion sur les modalités d'hébergement
  * centralisé ?
  * décentralisé par UFR (comme actuellement ?)
* Améliorer (revoir) la récupération des maquettes depuis Apogée

---

# Version 4

* Refonte complète de l'interface (VueJs + Symfony)
* UX plus moderne, approche plus tableau de bord avec indicateurs
* Point central vers les outils
  * Unifolio (outil de portofolio étudiant)
  * Correcto (outil d'aide à la correction) - WIP
  * UniEdt (outil de conception des emplois du temps)
  * Outil de questionnaire (déporté de l'intranet pour usage plus large)

---

# Version 4

* Lien avec ORéOF (via API) pour la récupération des maquettes fiabilisées
* Gestion des étudiants et des programmes sur chaque année (suivi de cohorte repensé)
* Amélioration de l'UX et des fonctionnalités après retours utilisateurs

---

# Quelques chiffres

* 159 tables
* plus de 170 000 lignes de code (hors framework)
* Version 3
  * version 1 sous CodeIgniter (uniquement MMI, 2013-2017)
  * version 2 sous SF 2->4 (tout l'IUT, février 2018 jusqu'en 2020)
  * version 3 depuis la rentrée 2020 (IUT Troyes), 2021 (IUT RCC)
  * version 4 en cours de dev (depuis début 2025, sortie beta janvier 2026, mise en prod juin 2026) => VueJs + SF 7.2
