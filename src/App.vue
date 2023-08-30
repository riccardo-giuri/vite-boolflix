<script>
import MovieSearch from './components/MovieSearch.vue';
import MovieList from './components/MovieList.vue';

export default {
  components: {
    MovieSearch,
    MovieList
  },

  data() {
    return {

    }
  }
};
</script>

<template>
  <div class="container pt-4">
    <MovieSearch></MovieSearch>

    <MovieList></MovieList>
  </div>
</template>

<style lang="scss">

</style>
