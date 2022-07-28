<template>
    <ul>
        <li>{{filmApi.title}}</li>
        <li>{{filmApi.original_title}}</li>
        <li>
            <img
              v-if="languages.includes(singleFilm.original_language)"
              :src="
                require(`../assets/flags/${singleFilm.original_language}.png`)
              "
              alt="language flag"
            />
            <img v-else :src="require(`../assets/flags/rsw.png`)" alt="">
          </li>
        <li>{{filmApi.vote_average}}</li>
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

    props:["filmApi"]
}
</script>

<style>

</style>