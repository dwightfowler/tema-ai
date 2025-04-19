<template>
  <div>
    <h2>Weather Forecast</h2>
    <button @click="loadForecast">Load Forecast</button>
    <ul v-if="forecast.length">
      <li v-for="(day, index) in forecast" :key="index">
        {{ day.date }} — {{ day.temperatureC }}°C / {{ day.temperatureF }}°F — {{ day.summary }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const forecast = ref([])

async function loadForecast() {
  try {
    const response = await fetch(`${import.meta.env.VITE_API_BASE_URL}/weatherforecast`)
    if (!response.ok) throw new Error('Fetch failed')
    forecast.value = await response.json()
  } catch (error) {
    console.error('Error fetching forecast:', error)
  }
}
</script>
