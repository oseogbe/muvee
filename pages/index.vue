<template>
  <div class="home">
    <Hero />
  </div>
</template>

<script>
  import axios from 'axios'
  export default {
    name: 'HomePage',

    data() {
      return {
        movies: [],
      }
    },

    methods: {
      async getMovies() {
        const data = axios.get(
          `https://api.themoviedb.org/3/movie/now_playing?api_key=37ed43a4f8eaa2abd75f9283692947bc&language=en-US&page=1`
        )
        const result = await data
        result.data.results.forEach((movie) => {
          this.movies.push(movie)
        })
      },
    },
  }
  </script>

  <style lang="scss">

  </style>
