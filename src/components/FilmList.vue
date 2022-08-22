<template>
<div>
    <h1 class="text-light fw-bold text-center mt-3">Films</h1>
  <div
    class="card"
      @mouseover="isMouseover = true"
      @mouseleave="isMouseover = false">
         <img
         class="img-fluid"
         :src="cover"
         :alt="singleFilmApi.title">
         
    <ul v-show="isMouseover === true">
        <li class="text-light fw-bold"> Titolo: {{singleFilmApi.title}}</li>
        <li class="text-light fw-bold">Titolo originale: {{singleFilmApi.original_title}}</li>
        <li class="text-light fw-bold">
          Lingua:
            <img class="language"
              :src="
                require(`../assets/flags/${singleFilmApi.original_language}.png`)
              "
              alt="language flag"
            />
        </li>
        <li class="text-light fw-bold"> 
        Voto:
        <FontAwesomeIcon v-for="n in 5" 
              :key="n" class="fa-star" 
               :icon=" renderStar(n)"/>
        </li>
        <li>
        <span class="fw-normal text-light overflow py-2" >Overview: {{ singleFilmApi.overview }}</span>
      </li>
    </ul> 
  </div>
  </div>
</template>

<script>
  const imgBaseUrl = "https://image.tmdb.org/t/p/";
  const imgSize = "w342";
  const coverPlaceholder="https://www.altavod.com/assets/images/poster-placeholder.png";
export default {

     data: function () {
    return {
      isMouseover: false,
      languages: [
        "en",
        "it",
      ],


    };

  },
    computed: {
      cover(){
        if(!this.singleFilmApi.poster_path) return coverPlaceholder;
       return imgBaseUrl+imgSize+this.singleFilmApi.poster_path;
      },
      vote(){
        return Math.ceil(this.singleFilmApi.vote_average / 2);
      },
    },
    props:["singleFilmApi"],
    methods: {
      renderStar(n){
       const iconType = this.vote >= n ? ' fa-solid' : ' fa-regular';
        return iconType + " fa-star";
      },
    },
}
</script>

<style lang="scss">
.language {
  width: 2.5rem;
  height: 1.5rem;
}
.fa-star {
  color: goldenrod;
}
.card {
  cursor: pointer;
}
ul{
    font-size: 1.5rem;
    padding: 1.5rem;
    position: absolute;
    top:0;
    left: 0;
    background-color: #030303;
    height: 100%;
    width: 100%;
    overflow-y: auto;
}
</style>