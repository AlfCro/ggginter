<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)

function increment(): void {
  count.value++
}
</script>

<template>
  <div class="app">
    <h1>Vite + Vue + TypeScript POC</h1>
    <p>Testing GitHub Actions workflow</p>
    <button @click="increment">Count: {{ count }}</button>
  </div>
</template>

<style scoped>
.app {
  font-family: sans-serif;
  text-align: center;
  padding: 2rem;
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  cursor: pointer;
}
</style>
