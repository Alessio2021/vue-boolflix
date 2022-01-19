<template>
  <div id="app">
    <Header @doSearch="getMovie($event)"/>
    <Main :searchMovieMain="searchMovie"/>
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
      searchMovie: '',
      
    }
  },
  methods: {
    getMovie(text) {
      this.searchMovie = text;
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
