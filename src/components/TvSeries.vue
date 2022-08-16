<template>
    <ul>
        <li>{{ singleTvShow.name }}</li>
        <li>{{ singleTvShow.original_name }}</li>
        <li>
        <img 
        :src="require(`../assets/flags/${singleTvShow.original_language}.png`)" 
        alt="language flag"></li>
        <li>{{singleFilmApi.vote_average}}</li>
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


    };
  },

    props:["singleFilmApi"]
}
</script>

<style>

</style>