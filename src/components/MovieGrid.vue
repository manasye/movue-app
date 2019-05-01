<template>
  <div class="container mb-5">
    <div class="row justify-content-center">
      <movie-card v-for="movie in movies" :movie="movie" :key="movie.id"></movie-card>
    </div>
  </div>
</template>

<script>
import Card from "./MovieCard";

export default {
  props: ["movies"],
  components: {
    movieCard: Card
  },
};
</script>
