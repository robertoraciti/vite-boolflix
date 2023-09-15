<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      movies: [],
    };
  },

  components: {
    AppHeader,
    AppMain,
  },

  methods: {
    fetchMovies(string) {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            query: string,
            api_key: "321fee9b963d1057eaa31792bfd9c2e9",
          },
        })
        .then((response) => {
          console.log(response.data.results);
          this.movies = response.data.results;
        });
    },
  },

  created() {
    this.fetchMovies();
  },
};
</script>

<template>
  <AppHeader @start-search="fetchMovies" />
  <AppMain />
</template>

<style></style>
