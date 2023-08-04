<script setup>
import {ref} from 'vue'

const showText = ref(false)
</script>

<template>
  <main>
      <Transition name="color">
        <h1 v-if="showText">Hello world</h1>
      </Transition>
      <button @click="showText = !showText">Toogle</button>
  </main>
</template>

<style  scoped>
.color-enter-from {
  background-color: indianred; 
  color: white;
}

.color-enter-to {
  background-color: lightsalmon; 
  color: black; 
}

.color-enter-active {
  transition: all 1s;
} 


</style>
 