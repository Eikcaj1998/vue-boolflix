<template>
    <main>
      <div class="container-fluid">
        <div class="row">
          <div class="d-flex flex-wrap justify-content-between">
          <FilmList
          class="m-4 film-list"
          v-for="singleFilmApi in filmApi"
          :key="singleFilmApi.id"
          :singleFilmApi="singleFilmApi"
          />
          </div>
        </div>
        <div class="row">
          <div class="d-flex flex-wrap justify-content-between">
            <TvSeries
            class="m-4 tv-series"
            v-for="singleTvSeries in seriesTvApi"
            :key="singleTvSeries.id"
            :singleTvSeries="singleTvSeries"
            />
          </div>
      </div>
    </div>

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
    
<style lang="scss">
ul {
  list-style: none;
}


.film-list,
.tv-series {
  width: 300px;
}


</style>