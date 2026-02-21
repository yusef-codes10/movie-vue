<script setup>
import MovieC from './MovieC.vue'
import { ref, onMounted } from 'vue'

const movies = ref([])

onMounted(async () => {
  try {
    const API_KEY = import.meta.env.VITE_OMDB_KEY

    const response = await fetch(`https://www.omdbapi.com/?s=batman&apikey=${API_KEY}`)

    const data = await response.json()

    movies.value = data.Search || []

    console.log(movies.value)
  } catch (error) {
    console.log(error)
  }
})
</script>

<template>
  <div class="movies-container">
    <MovieC v-for="movie in movies" :key="movie.id" :img="movie.poster" :title="movie.title" />
  </div>
</template>

<style scoped>
.movies-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
</style>
