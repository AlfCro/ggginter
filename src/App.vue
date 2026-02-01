<script setup lang="ts">
import { ref } from 'vue'

const bananaCount = ref(0)

function collectBanana(): void {
  bananaCount.value++
}
</script>

<template>
  <div class="banana-app">
    <h1>Banana POC</h1>
    <p class="tagline">Go bananas with Vite + Vue + TypeScript!</p>
    <div class="banana-display">
      <span class="banana-icon">🍌</span>
    </div>
    <button class="banana-button" @click="collectBanana">
      Collect Banana! ({{ bananaCount }})
    </button>
  </div>
</template>

<style scoped>
.banana-app {
  font-family: sans-serif;
  text-align: center;
  padding: 2rem;
  background: linear-gradient(135deg, #fff9c4 0%, #ffeb3b 100%);
  min-height: 100vh;
  margin: -8px;
}

h1 {
  color: #5d4037;
  text-shadow: 2px 2px 0px #ffcc00;
}

.tagline {
  color: #6d4c41;
  font-style: italic;
}

.banana-display {
  margin: 2rem 0;
}

.banana-icon {
  font-size: 5rem;
  animation: bounce 1s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.banana-button {
  padding: 1rem 2rem;
  font-size: 1.2rem;
  cursor: pointer;
  background-color: #ffc107;
  border: 3px solid #5d4037;
  border-radius: 25px;
  color: #5d4037;
  font-weight: bold;
  transition: all 0.3s ease;
}

.banana-button:hover {
  background-color: #ffeb3b;
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(255, 193, 7, 0.4);
}
</style>
