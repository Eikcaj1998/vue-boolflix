<template>
    <ul>
        <li>{{FilmApi.title}}</li>
        <li>{{FilmApi.original_title}}</li>
        <li>{{FilmApi.original_language}}</li>
        <li>{{FilmApi.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    props:["FilmApi"]
}
</script>

<style>

</style>