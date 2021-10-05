<template>
  <div id="app">
    <Header/>
    <main>
      <Movies>
        <MovieCard/>
      </Movies>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MovieCard from './components/MovieCard.vue';
import Movies from './components/Movies.vue'

export default {
  name: 'App',
  components: {
    Header,
    MovieCard,
    Movies
  }
}
</script>

<style lang="scss" scoped>

</style>
