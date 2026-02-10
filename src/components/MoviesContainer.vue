<script setup>
import MovieC from './MovieC.vue'
import movies from '@/data/movies.js'
console.log(movies)
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
