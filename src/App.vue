<template>
  <div id="app">
    <TheHeader  @search="getFilmApi"/>
    <TheMain :filmApi="filmApi"/>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheMain from "./components/TheMain.vue";
import axios from "axios";

export default {
  name: "App",

  data: function(){
    return {
      apiMovieUrl: "https://api.themoviedb.org/3/search/movie",
      apiKey: "ebffa79106c2c5a1ddc8cb2ad9cc1395",
      filmApi: [],
      languageList:[],
    };
  },

  components: {
    TheHeader,
    TheMain
  }, 

  methods: {
    getFilmApi(needle) {
      axios
        .get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${needle}`)
        .then((result) => {
          this.filmApi = result.data.results;
          })
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
