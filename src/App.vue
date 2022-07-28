<template>
  <div id="app">
    <TheHeader  @search="getFilmApi"/>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import axios from "axios";

export default {
  name: "App",

  data: function(){
    return{ 
      filmApi:[],
    
    }
  },

  components: {
    TheHeader,
  }, 

  methods: {
    getFilmApi(needle) {
      axios
        .get(`https://api.themoviedb.org/3/search/movie?api_key=ebffa79106c2c5a1ddc8cb2ad9cc1395&query=${needle}`
        )
        .then((result) => {
          this.filmApi = result.data.results;
          console.warn(this.filmApi)
          })
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
