<template>
  <div id="app">
    <Header @doSearch="getList($event)"/>
    <Main 
      :list="list"
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
      list: {
        movies: [],
        series: [],
      }
    }
  },
  methods: {
    getList(text) {
      this.list.movies = text.movies;
      this.list.series = text.series;
    }
  },
};
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import '~mdb-ui-kit/css/mdb.min.css';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
