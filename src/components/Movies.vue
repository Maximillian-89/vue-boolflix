<template>
    <ul>
        <li v-for="(movie, index) in movies" :key="index">
            <MovieCard :movie='movie'/>
        </li>
    </ul>
</template>

<script>
import MovieCard from './MovieCard.vue';
// import axios from 'axios';

    export default {
        name: 'Movies',

        // props: {
        //     textImput: String
        // },

        components: {
            MovieCard
        },

        // data() {
        //     return {
        //         movies: []
        //     }
        // },

        // updated() {
        //     axios
        //     .get('https://api.themoviedb.org/3/search/movie', {

        //         params: {
        //             api_key: '538231174889c8f4d14c6638c8c73e43',
        //             query: this.textImput,
        //             language: 'it-IT'
        //         }
        //     })

        //     .then( (recive) => {

        //         if( this.textImput == '' ) {
        //             this.textImput = [];
        //         } else {
        //             this.movies = recive.data.results;
        //         }
        //     } );
        // }
    }
</script>

<style lang="scss" scoped>

</style>