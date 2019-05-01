<template>
  <div class="col-sm-6 col-md-4 col-lg-2 mt-4">
    <div class="movie-container">
      <img :src="preImage + movie.poster_path" alt="" />
      <div class="detail">
        <h5>{{ shortText(movie.title, 15) }}</h5>
        <p class="rating">
          <i class="fas fa-star orange"></i> {{ movie.vote_average }}
        </p>
        <p class="release">Release: {{ movie.release_date }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["movie"],
  data() {
    return {
      preImage: "https://image.tmdb.org/t/p/w500"
    };
  },
  methods: {
    shortText(longText, maxLength) {
      if (longText.length > maxLength) {
        return longText.substring(0, maxLength) + "...";
      }
      return longText;
    }
  }
};
</script>

<style scoped>
.movie-container {
  margin-top: 3vh;
  width: 100%;
  box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.16);
  padding-bottom: 2vh;
  height: 55vh;
}
.movie-container:hover {
  margin-top: 1.5vh;
  transition: margin 200ms;
}
.movie-container .detail {
  margin: 0 1vw;
}
img {
  width: 100%;
  height: 35vh;
}
h5 {
  text-align: center;
  margin-top: 2vh;
  overflow-wrap: break-word;
  color: darkblue;
  height: 7vh;
}
.rating {
  text-align: center;
  margin-bottom: 0.2rem;
}
.orange {
  color: orange;
}
.release {
  color: darkgray;
  font-size: 0.8rem;
  margin-bottom: 0;
  text-align: center;
}
</style>
