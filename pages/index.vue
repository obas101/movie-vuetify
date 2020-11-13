<template>
  <main class="large-spacer">
    <div class="displayImage">
      <div class="displayImage2">
        <h1 class="display-2" color="white">Welcome.</h1>
        <h2 color="white">
          Millions of movies, TV shows and people to discover. Explore now.
        </h2>
      </div>
    </div>
    <div>
      <div style="margin-top: 23rem">
        <h4>What's Popular</h4>
      </div>
      <v-container>
        <v-layout row wrap>
          <v-flex xs6 sm6 md2 lg2 v-for="movie in movies" :key="movie.id">
            <v-card flat class="ma-3 text-xs-center">
              <v-img
                :src="`https://image.tmdb.org/t/p/w185/${movie.poster_path}`"
              >
              </v-img>
              <v-card-title>
                <div class="caption">{{ movie.title }}</div>
              </v-card-title>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
  </main>
</template>

<script>
export default {
  components: {},
  async asyncData({ $axios }) {
    try {
      let response = await $axios.$get(
        `https://api.themoviedb.org/3/movie/popular?api_key=e6a5ea6901b10430e9110114c0fa6799&language=en-US`
      )
      console.log(response)
      return {
        movies: response.results,
      }
    } catch (error) {
      console.log(error)
    }
  },
}
</script>
<style>
.displayImage {
  /* background-image: url('~/assets/back.jpg'); */
  background-image: url('~assets/back.jpg');

  object-fit: cover;
  background-repeat: no-repeat;
  position: absolute;
  top: -5rem;

  width: 94%;

  margin-left: 2rem;

  /* margin-right: 2rem; */
}
.displayImage2 {
  height: 30rem;

  background-image: linear-gradient(
    to left,
    rgb(255, 165, 0, 0.75),
    rgb(3, 37, 65, 0.75)
  );
  padding-left: 2rem;
  padding-top: 13rem;
}
.title {
  z-index: 1;
}
</style>
