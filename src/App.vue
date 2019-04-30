<template>
  <div id="app">
    <app-navbar></app-navbar>
    <app-movie-grid :movies="movies"></app-movie-grid>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import MovieGrid from "./components/MovieGrid";

export default {
  name: "app",
  data() {
    return {
      movies: [
        {title: 'Test'}
      ]
    };
  },
  components: {
    "app-navbar": Navbar,
    "app-movie-grid": MovieGrid
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
