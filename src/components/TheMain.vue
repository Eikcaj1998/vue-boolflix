<template>
    <main>
        <FilmList
        v-for="singleFilmApi in filmApi"
        :key="singleFilmApi.id"
        :singleFilmApi="singleFilmApi"
        />
        <TvSeries
        v-for="singleTvSeries in seriesTvApi"
        :key="singleTvSeries.id"
        :singleTvSeries="singleTvSeries"
        />

    </main>
</template>
<script>
    import FilmList from "./FilmList.vue";
    import TvSeries from "./TvSeries.vue";
    
    export default {
      components: {
    FilmList,
    TvSeries,
},
    
      props: ["filmApi","seriesTvApi"],
    };
    </script>
    
    <style>
    </style>