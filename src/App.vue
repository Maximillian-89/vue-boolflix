<template>
  <div id="app">
    <Header @search='searchElm'/>
    <main>
      <Movies :movies='movies' :series='seriesTv'>
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
      movies: [],
      seriesTv: [],
      apiKey: '538231174889c8f4d14c6638c8c73e43'
    }
  },

  methods: {
    searchElm(query) {
      //Volendo ci possiamo creare una costante che contiene i parametri di chiamata al server, e lo mettiamo al posto di tutti i dati sotto Es 'params: params' invece di 'params: {apy_key query ecc]'.
      const params = {
        api_key: this.apiKey,
        query: query,
        language: 'it-IT'
      }
      // Search Movies
      axios
      .get('https://api.themoviedb.org/3/search/movie',{
        params: {
          api_key: this.apiKey,
          query: query,
          language: 'it-IT'
        }
      })
      
      .then( (recive) => {
        this.movies = recive.data.results;
      })
      // Search TV Series
      axios
      .get('https://api.themoviedb.org/3/search/tv',{
        //Qui lo usiamo per avere un esempio funzionante.
        params: params
      })

      .then( (recive) => {
        this.seriesTv = recive.data.results;
      })
      
    }
  },
}

</script>

<style lang="scss">
@import './assets/style/common.scss';
@import '~@fortawesome/fontawesome-free/css/all.css';

</style>
