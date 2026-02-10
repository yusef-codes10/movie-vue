<script setup>
import { defineProps } from 'vue'
import movies from '@/data/movies.js'
console.log(movies)

// we need props heree
defineProps({
  title: {
    type: String,
    required: true,
  },
  img: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="movie">
    <div class="poster">
      <img :src="img" :alt="title" />
    </div>
    <div class="title">
      <h2>{{ title }}</h2>
    </div>
  </div>
</template>

<style scoped>
.movie {
  width: 200px;
  border-radius: 12px;
  overflow: hidden;
  position: relative;
}

.poster {
  width: 100%;
  aspect-ratio: 2 / 3;
  background-color: #111;
}

.poster img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block; /* removes weird gaps */
}

.title {
  padding: 0.5rem;
  text-align: center;
  position: absolute;
  bottom: 10px;
}

.title h2 {
  font-size: 0.9rem;
  line-height: 1.2;
  color: red;
}
</style>
