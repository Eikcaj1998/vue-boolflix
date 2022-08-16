<template>
  <div id="app">
    <TheHeader  @search="getSearchResultApi"/>
    <TheMain 
    :filmApi="filmApi"
    :seriesTvApi="seriesTvApi"/>
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
      apiTvShowsUrl: "https://api.themoviedb.org/3/search/tv",
      apiKey: "ebffa79106c2c5a1ddc8cb2ad9cc1395",
      filmApi: [],
      seriesTvApi:[],
      languageList:[],
    };
  },

  components: {
    TheHeader,
    TheMain
  }, 

  methods: {
    getSearchResultApi(needle) {
      axios
        .get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${needle}`)
        .then((result) => {
          this.filmApi = result.data.results;
          });
      axios
        .get(`${this.apiTvShowsUrl}?api_key=${this.apiKey}&query=${needle}`)
        .then((result) => {
          this.seriesTvApi = result.data.results;
        });    
    },
    
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
