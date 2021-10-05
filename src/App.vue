<template>
  <div id="app">
    <Header @search='searchElm'/>
    <main>
      <Movies :textImput="resetSearch">
        <MovieCard/>
      </Movies>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MovieCard from './components/MovieCard.vue';
import Movies from './components/Movies.vue';

export default {
  name: 'App',
  components: {
    Header,
    MovieCard,
    Movies
  },

  data() {
    return {
      resetSearch: ''
    }
  },
  
  methods: {
    searchElm(elm) {
      this.resetSearch = elm;
    }
  }

}
</script>

<style lang="scss" scoped>

</style>
