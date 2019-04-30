<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <a class="navbar-brand" href="#">MoVue App</a>
      <button class="navbar-toggler" type="button">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Now Playing</a>
          </li>
          <li class="nav-item"><a class="nav-link" href="#">About Me</a></li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input
            class="form-control mr-md-4 mr-sm-2"
            type="search"
            placeholder="Search Here ..."
            v-model="searchInput"
          />
          <button
            class="btn btn-success my-2 my-sm-0"
            type="submit"
            @click.prevent="searchMovie"
          >
            Search
          </button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      searchInput: ""
    };
  },
  methods: {
    searchMovie() {
      console.log(this.searchInput);
    }
  }
};
</script>
