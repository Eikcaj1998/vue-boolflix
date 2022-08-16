<template>
    <ul>
        <li>
        <img 
        :src="`https://image.tmdb.org/t/p/w342${singleTvSeries.poster_path}`">
        </li>
        <li>{{ singleTvSeries.name }}</li>
        <li>{{ singleTvSeries.original_name }}</li>
        <li>
        <img class="language"
        :src="require(`../assets/flags/${singleTvSeries.original_language}.png`)" 
        alt="language flag"></li>
        <li>{{singleTvSeries.vote_average}}</li>
    </ul>
</template>

<script>
export default {

     data: function () {
    return {
        languages: [
        "en",
        "it",
      ],

        imgBaseUrl: "https://image.tmdb.org/t/p/",
        imgSize: "w342",

    };
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