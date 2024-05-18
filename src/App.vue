<template>
  <div class="app">
    <h1>Parent Component</h1>
    <p>Data from Child: {{ childData }}</p>
    <ChildComponent @send-data="updateChildData" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ChildComponent from './components/ChildComponent.vue';

const childData = ref('');

const updateChildData = (data) => {
  childData.value = data;
};
</script>

<style scoped>
.app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 20px;
}

h1 {
  color: #333;
}

p {
  font-size: 18px;
  color: #555;
}
</style>
