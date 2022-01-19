<template>
  <div id="app">
    <Header 
      @doSearch="getMovies($event)"
      :searchMovieValue="searchMovieApp"
    />
    <Main 
      :searchMovieMain="searchMovieApp"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",

  components: {
    Header,
    Main,
  },
  data() {
    return {
      searchMovieApp: '',
      staticApi: 'https://api.themoviedb.org/3/search/movie?api_key=401d2b8a5e51bdf6caf8b6e192d59d74&query=',
    }
  },
  methods: {
    getMovies(text) {
      this.searchMovieApp = this.staticApi + text;
    }
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
