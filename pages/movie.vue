<script setup lang="ts">
// https://moviesapi.ir/

let movies = reactive([])
const { data, pending, error, refresh } = await useFetch('https://moviesapi.ir/api/v1/movies?page=1', {
  onRequestError({ request, options, error }) {
    console.log('onRequestError')
  },
  onResponse({ request, response, options }) {
    movies = response._data.data;
    console.log('Movies : ' , movies)
  },
  onResponseError({ request, response, options }) {
    console.log('onResponseError')
  }
})

</script>

<template>
  <div>
    <div class="grid grid-cols-6 gap-4 m-12">
      <MovieItem v-for="(movie,i) in movies" :key="i"
                 :poster="movie.poster"
                 :title="movie.title"
                 :year="movie.year"
                 :country="movie.country"
                 :imdb="movie.imdb_rating"
                 :genres="movie.genres"/>
    </div>


  </div>
</template>

<style scoped>

</style>