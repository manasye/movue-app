<template>
  <div id="app">
    <app-navbar @searchMovie="search"></app-navbar>
    <app-movie-grid :movies="movies" v-if="!isLoading"></app-movie-grid>
    <app-loader v-else></app-loader>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import MovieGrid from "./components/MovieGrid";
import Loader from "./components/Loader";
import { BASE_URL, API_KEY } from "./Env";

export default {
  name: "app",
  data() {
    return {
      movies: [],
      isLoading: true
    };
  },
  methods: {
    search(title) {
      if (title) {
        this.isLoading = true;
        this.$http
          .get(
            `${BASE_URL}/search/movie?api_key=${API_KEY}&page=1&query=${title}`
          )
          .then(res => {
            this.movies = res.body.results.splice(0, 18);
            this.isLoading = false;
          });
      } else {
        this.fetchNowPlaying();
      }
    },
    fetchNowPlaying() {
      this.isLoading = true;
      this.$http
        .get(`${BASE_URL}/movie/now_playing?api_key=${API_KEY}&page=1`)
        .then(res => {
          this.movies = res.body.results.splice(0, 18);
          this.isLoading = false;
        });
    }
  },
  components: {
    "app-navbar": Navbar,
    "app-movie-grid": MovieGrid,
    "app-loader": Loader
  },
  mounted() {
    this.fetchNowPlaying();
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
