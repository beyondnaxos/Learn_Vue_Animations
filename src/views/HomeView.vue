<script setup>
import {ref  } from 'vue'


const names = ref([
  'John Doe',
  'Jane Doe',
])

const nameInput = ref('')

const addInvitee = () => {
  names.value.unshift(nameInput.value)
  nameInput.value = ''
}

</script>

<template>
  <main>

    <div class="container">
      <input 
        v-model="nameInput"
        type="text" 
        placeholder="Add person to invite..." 
        @keypress.enter="addInvitee" 
      >
      <ul>
        <li v-for="name in names" :key="name">{{name}}</li>
   
      </ul>
    </div>


  </main>
</template>


<style scoped>

main { 
  width: 100%;
}
.container {
  max-width: 300px;
  margin: 0 auto;
} 

.container input {
  width: 100%;
  border-radius: 5px;
  border: 1px solid rgba(128, 128, 128, 0.13);
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12); 
}

ul {
  display: inline;
  list-style: noe;
  margin: 0px;
  padding: 0px;
}

li {
  list-style: none;
  width: 300px;
  border-radius: 5px;
  padding : 5px 10px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12); 
  text-align: center; 
  cursor: pointer;
  
}
</style>


<!-- <template>
   <main>
      <div class="container">
        <Transition name="fade">
          <h1 v-if="showGreet">Hello World</h1>
          <h1 v-else>Goodbye World</h1>
        </Transition>
      </div>
      <button @click="showGreet = !showGreet">Toogle</button>
  </main> 
</template> -->
<!-- <style  scoped>
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


</style> -->
 
