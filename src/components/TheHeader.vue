<template>
  <header>
          <form role="search">
            <input
              placeholder="Cerca Film o Serie TV"
              v-model="searchedMovie"
            />
            <button type="submit" @click.prevent="$emit('search',searchedMovie)">
              Cerca
            </button>
          </form>
  </header>
</template>

<script>
export default {
  data: function(){
    return{
      searchedMovie:'',
    }
  },

  methods:{
    
  }
};
</script>

<style>
</style>
