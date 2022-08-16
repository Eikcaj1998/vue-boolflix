<template>
    <ul>
        <li>
         <img 
         :src="`https://image.tmdb.org/t/p/w342${singleFilmApi.poster_path}`">
        </li>
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

      imgBaseUrl: "https://image.tmdb.org/t/p/",
      imgSize: "w342",

    };

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