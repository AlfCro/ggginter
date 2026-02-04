<script setup lang="ts">
import { ref, onMounted } from 'vue'

const fishCount = ref(0)
const isMusicPlaying = ref(false)
const audioRef = ref<HTMLAudioElement | null>(null)

function catchFish(): void {
  fishCount.value++
}

function toggleMusic(): void {
  if (audioRef.value) {
    if (isMusicPlaying.value) {
      audioRef.value.pause()
    } else {
      audioRef.value.play()
    }
    isMusicPlaying.value = !isMusicPlaying.value
  }
}

onMounted(() => {
  if (audioRef.value) {
    audioRef.value.volume = 0.5
  }
})
</script>

<template>
  <div class="fish-app">
    <h1>Fish POC</h1>
    <p class="tagline">Dive deep with Vite + Vue + TypeScript!</p>
    <div class="fish-display">
      <span class="fish-icon">🐟</span>
    </div>
    <div class="button-container">
      <button class="fish-button" @click="catchFish">
        Catch Fish! ({{ fishCount }})
      </button>
      <button class="music-button" @click="toggleMusic">
        {{ isMusicPlaying ? '🔇 Pause Music' : '🎵 Play Music' }}
      </button>
    </div>
    <audio ref="audioRef" loop>
      <source src="https://upload.wikimedia.org/wikipedia/commons/c/c8/Aquarium_%28Saint-Sa%C3%ABns%29.ogg" type="audio/ogg">
    </audio>
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
  font-size: 2.5rem;
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

.fish-button:hover,
.music-button:hover {
  background-color: #4dd0e1;
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(0, 188, 212, 0.4);
}

.button-container {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.music-button {
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
</style>
