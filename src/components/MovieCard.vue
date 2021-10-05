<template>
    <ol>
        <li>Titolo: {{movie.title}}</li>
        <li>Titolo Originale: {{movie.original_title}}</li>
        <li>Lingua Originale: {{movie.original_language}}</li>
        <li>Voto: {{movie.vote_average}}</li>
    </ol>
</template>

<script>
    export default {
        name: 'MovieCard',

        props: {
            movie: Object
        }
    }
</script>

<style lang="scss" scoped>
    ul {
        display: flex;
        flex-direction: column;

        li {

        }
    }

</style>