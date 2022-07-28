<template>
    <ul>
        <li>{{singleFilmApi.title}}</li>
        <li>{{singleFilmApi.original_title}}</li>
        <li>
            <img
              v-if="languages.includes(singleFilmApi.original_language)"
              :src="
                require(`../assets/flags/${singleFilmApi.original_language}.png`)
              "
              alt="language flag"
            />
          </li>
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