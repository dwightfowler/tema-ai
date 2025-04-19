<script setup lang="ts">
import Weather from './components/Weather.vue'
</script>

<template>
  <main>
    <h1>Welcome to TEMA-AI</h1>
    <Weather />
  </main>
</template>


<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
