<template>
    <div class="movies">
        <h1>Films</h1>
        <ul>
            <li class="card-container" v-for="(movie, index) in movies" :key="index">
                <MovieCard :movie='movie'/>
            </li>
        </ul>
        <h1>Serie TV</h1>
        <ul>
            <!-- <li class="card-container" v-for="(movie, index) in movies" :key="index">
                <MovieCard :movie='movie'/>
            </li> -->
        </ul>
    </div>
</template>

<script>
import MovieCard from './MovieCard.vue';

    export default {
        name: 'Movies',

        props: {
            movies: Array
        },

        components: {
            MovieCard
        },
    }
</script>

<style lang="scss" scoped>

    .movies {
        h1 {
            color: #fff;
        }

        ul {
            display: flex;
            flex-wrap: wrap;
            list-style: none;
        }

        .card-container {
            width: calc(100% / 5 - 1.25rem);
            margin: 1.5625rem .625rem;
        }
    }
</style>