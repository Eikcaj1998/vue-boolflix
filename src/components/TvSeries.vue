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
        <li><i v-for="n in 5" 
              :key="n"
              :class=" renderStar(n)"></i></li>
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
      },
      vote(){
        return Math.ceil(this.singleTvSeries.vote_average / 2);
      },
    },
    props:["singleTvSeries"],
    methods: {
      renderStar(n){
       const iconType = this.vote >= n ? 'fa-solid' : 'fa-regular';
        return iconType + "fa-star";
      },
    },
}
</script>

<style>
.language {
  width: 2.5rem;
  height: 1.5rem;
}
</style>