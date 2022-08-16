<template>
    <ul>
        <li>{{ singleTvSeries.name }}</li>
        <li>{{ singleTvSeries.original_name }}</li>
        <li>
        <img 
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


    };
  },

    props:["singleTvSeries"]
}
</script>

<style>

</style>