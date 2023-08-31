<script>
import MovieList from './components/MovieList.vue';
import TheHeader from './components/TheHeader.vue';

export default {
  components: {
    MovieList,
    TheHeader
  },

  data() {
    return {

    }
  }
};
</script>

<template>
  <div class="body">


  <div class="container pt-4">
    <TheHeader></TheHeader>
    
    <MovieList></MovieList>
  </div>
  </div>
  
</template>

<style lang="scss">
  .body {
    background-color: rgb(23, 23, 23);
    min-height: 100vh;
  }
</style>
