<script setup>
import {ref} from 'vue'

const showText = ref(false)
</script>

<template>
  <main>
      <Transition name="fade">
        <h1 v-if="showText">Hello world</h1>
      </Transition>
      <button @click="showText = !showText">Toogle</button>
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


</style>
 