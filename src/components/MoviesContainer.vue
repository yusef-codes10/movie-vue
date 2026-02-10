<script setup>
import MovieC from './MovieC.vue'
import movies from '@/data/movies.js'
console.log(movies)
</script>

<template>
  <div class="movies-container" v-for="movie in movies" :key="movie.id">
    <MovieC :img="movie.poster" :title="movies.title" />
  </div>
</template>

<style scoped></style>
