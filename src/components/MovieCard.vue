<template>
    <div class="movie">
        <div class="poster">
            <img :src="`http://image.tmdb.org/t/p/w300/${movie.poster_path}`" :alt="movie.title">
        </div>
        <div class="details">
            <h2>Titolo: {{movie.title}}</h2>
            <h3>Titolo Originale: {{movie.original_title}}</h3>
            <lang-flag :iso='movie.original_language'/>
            <div>Voto: {{movie.vote_average}}</div>
        </div>
    </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

    export default {
        name: 'MovieCard',

        props: {
            movie: Object
        },
        
        components: {
            LangFlag,
        }
    }
</script>

<style lang="scss" scoped>

    .movie {
        position: relative;
    }
    .movie .details {
        opacity: 0;
        position: absolute;
        top: 0;
        background: red;
        bottom: 0;
        width: 100%;
    }

    .movie:hover .details {
        opacity: 1;
    }

</style>