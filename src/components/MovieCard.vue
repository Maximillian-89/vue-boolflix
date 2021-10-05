<template>
    <ul>
        <li>{{movie.title}}</li>
        <li>{{movie.original_title}}</li>
        <li>{{movie.original_language}}</li>
        <li>{{movie.vote_average}}</li>
    </ul>
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

        li {
            
        }
    }

</style>