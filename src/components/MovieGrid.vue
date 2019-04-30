<template>
  <div class="row">
    <movie-card v-for="movie in movies" :movie="movie"></movie-card>
  </div>
</template>

<script>
import Card from "./MovieCard";

export default {
  props: ["movies"],
  components: {
    movieCard: Card
  }
};
</script>
