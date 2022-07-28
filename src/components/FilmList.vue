<template>
    <ul>
        <li>{{filmApi.title}}</li>
        <li>{{filmApi.original_title}}</li>
        <li>{{filmApi.original_language}}</li>
        <li>{{filmApi.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    props:["filmApi"]
}
</script>

<style>

</style>