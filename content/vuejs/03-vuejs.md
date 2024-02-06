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

---

# Mise en garde ...

Attention, VueJs 3 propose deux façons de structurer le code :

* La version "historique" avec les options `data`, `methods`, `computed`, `watch`, `lifecycle hooks`, ... (dite **Option Api**)
* La version "moderne" avec la **composition API**, qui permet de structurer le code de manière plus logique, et plus réutilisable.

Plus d'infos ici : https://vuejs.org/guide/introduction.html#api-styles

---

# Mise en garde (version option API)

```javascript
<script>
export default {
  // Properties returned from data() become reactive state
  // and will be exposed on `this`.
  data() {
    return {
      count: 0
    }
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
  methods: {
    increment() {
      this.count++
    }
  },

  // Lifecycle hooks are called at different stages
  // of a component's lifecycle.
  // This function will be called when the component is mounted.
  mounted() {
    console.log(`The initial count is ${this.count}.`)
  }
}
</script>

<template>
  <button @click="increment">Count is: {{ count }}</button>
</template>
```

---

# Mise en garde (version composition API)

```javascript
<script setup>
import { ref, onMounted } from 'vue'

// reactive state
const count = ref(0)

// functions that mutate state and trigger updates
function increment() {
  count.value++
}

// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})
</script>

<template>
  <button @click="increment">Count is: {{ count }}</button>
</template>
```

---

# Mise en pratique...

Vous aurez besoin de :

* Un terminal
* npm (ou yarn)
* un IDE (VSCode, PHPStorm, ...)
  * Avec les plugins Vue.js et Volar par exemple pour VSCode
* Un navigateur web **avec la console ouverte...**
  * Et le plugin Vue.js https://vuejs.org/guide/scaling-up/tooling.html#browser-devtools  
