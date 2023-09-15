<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain";

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
    fetchMovies() {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            query: "anelli",
            api_key: "321fee9b963d1057eaa31792bfd9c2e9",
          },
        })
        .then((response) => {
          this.movies = response.data.results;
        });
    },
  },

  created() {
    fetchMovies();
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style></style>
