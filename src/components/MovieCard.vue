<template>
    <div class="movie">
        <div class="poster">
            <img :src="`http://image.tmdb.org/t/p/w300/${movie.poster_path}`" :alt="movie.title">
        </div>
        <div class="details">
            <ul>
                <li>Titolo:<h2> {{movie.title}}</h2></li>
                <li>Titolo Originale:<h3> {{movie.original_title}}</h3></li>
                <li>Lingua: <lang-flag :iso='movie.original_language'/></li>
                <li>
                    Voto:
                    <div v-for="(star, index) in Math.floor(movie.vote_average / 2)" :key="index" class="fas fa-star"></div>
                </li>
            </ul>
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
        overflow: hidden;

        .poster {
            display: flex;
            // margin: 20px 15px;
            height: 100%;
        }
        .poster img {
            object-fit: cover;
            width: 100%;
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

        ul li {
            padding: .80rem 3rem;
        }
    }

    .movie:hover .details {
        opacity: 1;
    }

    .details ul {
        list-style: none;

        li {
            color: #fff;
                display: flex;
            align-items: center;
        }

        li h2, h3, div {
            color: #fff;
            margin-left: .625rem;
        }

        li:last-child div {
            margin: 0;
        }
    }

    .fas.fa-star {
        color: gold;
    }

</style>