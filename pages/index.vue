<template>
  <div>
    <main-section />
    <div class="movies" id="movies">
      <div class="movie" v-for="(movie, index) in movies" :key="index">
        <nuxt-link
          :to="{ name: 'movies-movieId', params: { movieId: movie.id } }"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
            alt=""
          />
          <p class="review">{{ movie.vote_average }}</p>
          <p class="overview">{{ movie.overview }}</p>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      movies: [],
    };
  },
  methods: {
    async getMovies() {
      const data = axios.get(
        "https://api.themoviedb.org/3/movie/now_playing?api_key=37ed43a4f8eaa2abd75f9283692947bc&language=en-US&page=1"
      );
      const result = await data;
      console.log();
      result.data.results.forEach((res) => {
        this.movies.push(res);
      });
    },
  },
  async fetch() {
    await this.getMovies();
    console.log(this.movies);
  },
};
</script>
