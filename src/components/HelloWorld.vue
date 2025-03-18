<script setup>
import { ref } from 'vue';


const message = ref('Hello Vue 3 with Vite!');
const inputText = ref('');
const counter = ref(0);
const isVisible = ref(true);


const increment = () => {
  counter.value++;
};

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
</script>

<template>
  <div>
   
    <h1>{{ message }}</h1>
    
    
    <input v-model="inputText" placeholder="Type something..." />
    <p>Input: {{ inputText }}</p>
    
    
    <button @click="increment">Click Me ({{ counter }})</button>
    
   
    <button :disabled="counter >= 5">Disable when count ≥ 5</button>
    
    
    <button @click="toggleVisibility">Toggle Message</button>
    <p v-if="isVisible">This message is visible!</p>
  </div>
</template>

<style scoped>
button {
  margin: 5px;
  padding: 10px;
  border: none;
  background-color: #42b983;
  color: white;
  cursor: pointer;
}
button:disabled {
  background-color: gray;
}
</style>