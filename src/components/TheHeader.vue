<template>
<form role="search">
    <input
        placeholder="Cerca Film o Serie TV"
        v-model="searchedMovie"
    />
    <button type="submit">
        Cerca
    </button>
</form>
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