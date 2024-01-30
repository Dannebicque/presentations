# Vue.js

Vue.js (aussi appelé plus simplement Vue), est un framework JavaScript open-source utilisé pour construire des interfaces utilisateur et des applications web monopages. Vue a été créé par Evan You et est maintenu par lui et le reste des membres actifs de l'équipe principale travaillant sur le projet et son écosystème.

---

# Vue.js

* Vue.js apporte la notion de composant (qui n'est pas nouvelle en soit, HTML intégre déjà la notion de composant), et permet un "binding" complet entre les éléments (mise à jour réciproque des éléments).
* Vue.js apporte une structuration forte du développement front, une réutilisabilité importante avec la notion de composant et améliore l'interactivité de l'application et l'expérience des utilisateurs.

---

# Vue.js

* Vue.js nécessite un environnement NodeJs pour fonctionner. Le code écrit n'est pas directement exploitable par les navigateurs et implique un mécanisme de "traduction". 
* Un automatisateur de tâche est indispensable, tel que webpack ou, ViteJs qui est recommandé avec la version 3 de Vue.js.
* Vue.js implique également une bonne connaissance de la syntaxe JavaScript et en particulier les versions ECMAScript 6 (ES6) et suivantes.

---

# Un premier exemple

<div class="col1">

```html
<div id="app">
  <button @click="count++">
    Le compteur est à {{ count }}
  </button>
</div>
```

</div>

<div class="col2">

```javascript
import { createApp, ref } from 'vue'

createApp({
  setup() {
    return {
      count: ref(0)
    }
  }
}).mount('#app')
```

</div>

Source : https://fr.vuejs.org/guide/introduction.html

---

# Un premier exemple

Cet exemple illustre les deux principales fonctionnalités de Vue :

* **Rendu déclaratif** : Vue s'appuie sur le standard HTML avec une syntaxe de type template qui permet de décrire de manière déclarative la structure HTML tout en étant basée sur un état JavaScript.

* **Réactivité** : Vue traque automatiquement tout changement d'état JavaScript et met à jour efficacement le DOM en cas de changement.

Source : https://fr.vuejs.org/guide/introduction.html