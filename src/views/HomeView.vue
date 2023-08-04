<script setup>
import {ref} from 'vue'

const showGreet = ref(true)
</script>

<template>
  <main>
      <div class="container">
        <Transition name="fade">
          <h1 v-if="showGreet">Hello World</h1>
          <h1 v-else>Goodbye World</h1>
        </Transition>
      </div>
      <button @click="showGreet = !showGreet">Toogle</button>
  </main>
</template>

<style  scoped>
/* Début de l'animation entry */
.fade-enter-from {
 opacity: 0;
}

/* Fin de l'animation entry*/
.fade-enter-to {
  opacity: 1;   
}

/* setup de l'animation entry */
.fade-enter-active {
  transition: all 0.5s ease;
} 

/* Début de l'animation leave */  
.fade-leave-from {
 opacity: 1;
}

/* Fin de l'animation leave */
.fade-leave-to {
  opacity: 0;   
}

/* setup de l'animation leave */  
.fade-leave-active {
  transition: all 0.5s ease;
} 

.container {
  position: relative;
}

h1 {
  position: absolute;
}

button {
  margin-top: 50px;
}


</style>
 