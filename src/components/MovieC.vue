<script setup>
import { defineProps } from 'vue'
import movies from '@/data/movies.js'
console.log(movies)

// we need props heree
defineProps({
  title: {
    type: String,
  },
  img: {
    type: URL,
  },
})
</script>

<template>
  <div class="movie">
    <img :src="img" :alt="title" />
    <h2>{{ title }}</h2>
  </div>
  right movie
</template>

<style scoped></style>
