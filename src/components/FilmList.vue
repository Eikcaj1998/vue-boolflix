<template>
    <ul>
        <li>{{singleFilmApi.title}}</li>
        <li>{{singleFilmApi.original_title}}</li>
        <li>
            <img class="language"
              :src="
                require(`../assets/flags/${singleFilmApi.original_language}.png`)
              "
              alt="language flag"
            />
          </li>
        <li>
         <img
         :src="cover"
         :alt="singleFilmApi.title">

        </li>
        <li><i class="fa-solid fa-star"></i>{{singleFilmApi.vote_average}}</li>
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
        if(!this.singleFilmApi.poster_path) return coverPlaceholder;
       return imgBaseUrl+imgSize+this.singleFilmApi.poster_path
      }
    },
    props:["singleFilmApi"]
}
</script>

<style>
.language {
  width: 2.5rem;
  height: 1.5rem;
}
</style>