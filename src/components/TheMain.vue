<template>
    <main>
      <div class="container-fluid">
        <div class="row">
          <h1 class="text-light fw-bold text-center mt-3">Films</h1>
          <div class="col-12 d-flex flex-wrap justify-content-between">
          <FilmList
          class="mt-4 film-list"
          v-for="singleFilmApi in filmApi"
          :key="singleFilmApi.id"
          :singleFilmApi="singleFilmApi"
          />
          </div>
        </div>
      <hr class="text-light mt-5">
        <div class="row">
          <h1 class="text-light fw-bold text-center mt-3">Series</h1>
          <div class="col-12 d-flex flex-wrap justify-content-between">
            <TvSeries
            class="mt-4 tv-series"
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

main {
  background-color: #1b1b1b;
}

.film-list,
.tv-series {
  width: calc((100% / 3) - 3rem);
  padding: 2rem;
}


</style>