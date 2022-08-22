<template>
    <ul>
        <li>{{ singleTvSeries.name }}</li>
        <li>{{ singleTvSeries.original_name }}</li>
        <li>
        <img class="language"
        :src="require(`../assets/flags/${singleTvSeries.original_language}.png`)" 
        alt="language flag"></li>
        <li>
        <img
         :src="cover"
         :alt="singleTvSeries.title">
        </li>
        <li>{{singleTvSeries.vote_average}}</li>
    </ul>
</template>

<script>
const imgBaseUrl = "https://image.tmdb.org/t/p/";
const imgSize = "w342";
const coverPlaceholder="https://www.altavod.com/assets/images/poster-placeholder.png";
export default {

     data: function () {
    return {
        languages: [
        "en",
        "it",
      ],
    };
  },
  computed: {
      cover(){
        if(!this.singleTvSeries.poster_path) return coverPlaceholder;
       return imgBaseUrl+imgSize+this.singleTvSeries.poster_path
      }
    },
    props:["singleTvSeries"]
}
</script>

<style>
.language {
  width: 2.5rem;
  height: 1.5rem;
}
</style>