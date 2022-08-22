<template>
  <header>
    <div class="d-flex justify-content-between">
      <h1 class="text-danger fw-bold text-uppercase mx-3 p-2">
        Boolflix
      </h1>
      <div class="mx-3 mt-2 p-2">
          <form class="d-flex" role="search">
            <input
              placeholder="Cerca Film o Serie TV"
              v-model="searchedMovie"
            />
            <button type="submit" @click.prevent="$emit('search',searchedMovie)">
              Cerca
            </button>
          </form>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: function(){
    return{
      searchedMovie:'',
    }
  },

};
</script>

<style lang="scss">
header {
  background-color: #030303;
}
</style>
