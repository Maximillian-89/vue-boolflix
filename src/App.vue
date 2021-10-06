<template>
  <div id="app">
    <Header @search='searchElm'/>
    <main>
      <Movies :movies='movies'>
        <MovieCard/>
      </Movies>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MovieCard from './components/MovieCard.vue';
import Movies from './components/Movies.vue';
import axios from 'axios';

export default {
  name: 'App',
  
  components: {
    Header,
    MovieCard,
    Movies
  },

  data() {
    return {
      movies: []
    }
  },

  methods: {
    searchElm(query) {
      axios
      .get('https://api.themoviedb.org/3/search/movie',{
        params: {
          api_key: '538231174889c8f4d14c6638c8c73e43',
          query: query,
          language: 'it-IT'
        }
      })
      
      .then( (recive) => {
        this.movies = recive.data.results;
      })
    }
  },
  
  // data() {
  //   return {
  //     resetSearch: ''
  //   }
  // },
  
  // methods: {
  //   searchElm(elm) {
  //     this.resetSearch = elm;
  //   }
  // }

}
</script>

<style lang="scss" scoped>
@import './assets/style/common.scss';

</style>
