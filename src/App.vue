<script setup lang="ts">
import { ref } from 'vue'

const fishCount = ref(0)

function catchFish(): void {
  fishCount.value++
}
</script>

<template>
  <div class="fish-app">
    <h1>Fish POC</h1>
    <p class="tagline">Dive deep with Vite + Vue + TypeScript!</p>
    <div class="fish-display">
      <span class="fish-icon">🐟</span>
    </div>
    <button class="fish-button" @click="catchFish">
      Catch Fish! ({{ fishCount }})
    </button>
  </div>
</template>

<style scoped>
.fish-app {
  font-family: sans-serif;
  text-align: center;
  padding: 2rem;
  background: linear-gradient(135deg, #e0f7fa 0%, #0097a7 100%);
  min-height: 100vh;
  margin: -8px;
}

h1 {
  color: #01579b;
  text-shadow: 2px 2px 0px #4dd0e1;
}

.tagline {
  color: #006064;
  font-style: italic;
}

.fish-display {
  margin: 2rem 0;
}

.fish-icon {
  font-size: 5rem;
  animation: swim 2s ease-in-out infinite;
}

@keyframes swim {
  0%, 100% { transform: translateX(0) rotate(0deg); }
  25% { transform: translateX(10px) rotate(5deg); }
  75% { transform: translateX(-10px) rotate(-5deg); }
}

.fish-button {
  padding: 1rem 2rem;
  font-size: 1.2rem;
  cursor: pointer;
  background-color: #00bcd4;
  border: 3px solid #01579b;
  border-radius: 25px;
  color: #01579b;
  font-weight: bold;
  transition: all 0.3s ease;
}

.fish-button:hover {
  background-color: #4dd0e1;
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(0, 188, 212, 0.4);
}
</style>
