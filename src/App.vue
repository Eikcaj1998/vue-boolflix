<template>
  <div id="app">
    <TheHeader  @search="getFilmApi"/>
    <TheMain/>
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
      filmListFromApi: [],
      tvShowListFromApi: [],
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
        .get(`https://api.themoviedb.org/3/search/movie?api_key=ebffa79106c2c5a1ddc8cb2ad9cc1395&query=${needle}`
        )
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
