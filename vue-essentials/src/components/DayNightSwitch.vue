<script setup>
import { ref } from 'vue'

const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <h1 v-if="awesome" class="day-container">Morning, wake up! 🌝</h1>
  <h1 v-else class="night-container">Night, time to fly! 🌚</h1>
</template>

<style scoped>
.day-container {
  color: mediumspringgreen;
}

.night-container {
  color: #9457EB;
}

button {
  background-image: linear-gradient(to right, #02AAB0 0%, #00CDAC 51%, #02AAB0 100%);
  margin: 10px;
  padding: 15px 45px;
  text-align: center;
  text-transform: uppercase;
  transition: 0.5s;
  background-size: 200% auto;
  color: white;
  box-shadow: 0 0 20px #eee;
  border-radius: 10px;
}

.close-button {
  padding: 5px;
}

button:hover {
  background-position: right center;
  color: #fff;
  text-decoration: none;
}
</style>
