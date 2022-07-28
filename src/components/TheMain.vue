<template>
    <main>
        <FilmList
        v-for="singleFilmApi in filmApi"
        :key="singleFilmApi.id"
      :singleFilmApi="singleFilmApi"
        />
    </main>
</template>
<script>
    import FilmList from "./FilmList.vue";
    
    export default {
      components: {
        FilmList,
      },
    
      props: ["filmApi"],
    };
    </script>
    
    <style>
    </style>