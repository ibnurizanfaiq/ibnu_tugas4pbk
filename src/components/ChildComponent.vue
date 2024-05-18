<template>
  <div class="child">
    <h2>Child Component</h2>
    <input v-model="inputData" placeholder="Enter some data" />
    <button @click="emitData">Send Data to Parent</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { defineEmits } from 'vue';

const inputData = ref('');
const emit = defineEmits(['send-data']);

const emitData = () => {
  emit('send-data', inputData.value);
};
</script>

<style scoped>
.child {
  margin-top: 20px;
}

input {
  padding: 10px;
  font-size: 16px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  background-color: #007BFF;
  color: #FFF;
  border: none;
  border-radius: 5px;
}

button:hover {
  background-color: #0056b3;
}
</style>
