<template>
    <div class="movie">
        <div class="poster">
            <img :src="`http://image.tmdb.org/t/p/w300/${movie.poster_path}`" :alt="movie.title">
        </div>
        <div class="details">
            <ul>
                <li><h2>Titolo: {{movie.title}}</h2></li>
                <li><h3>Titolo Originale: {{movie.original_title}}</h3></li>
                <li><lang-flag :iso='movie.original_language'/></li>
                <li><div>Voto: {{movie.vote_average}}</div></li>
            </ul>
            <!-- <h2>Titolo: {{movie.title}}</h2>
            <h3>Titolo Originale: {{movie.original_title}}</h3>
            <lang-flag :iso='movie.original_language'/>
            <div>Voto: {{movie.vote_average}}</div> -->
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
@import '../assets/style/common.scss';

    .movie {
        position: relative;
        height: 100%;
        display: flex;
        overflow: hidden;

        .poster {
            display: flex;
            // margin: 20px 15px;
            height: 100%;
            width: calc(100% / 5);
        }
        .poster img {
            object-fit: cover;
        }
    }

    .movie .details {
        opacity: 0;
        position: absolute;
        top: 0;
        background: rgba(0, 0, 0, 0.9);;
        bottom: 0;
        left: 0;
        right: 0;
        height: 100%;
    }

    .movie:hover .details {
        opacity: 1;
    }

    .details ul {
        list-style: none;

        li h2, h3, div {
            color: #fff;
        }
    }

</style>