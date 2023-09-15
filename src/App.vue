<script>
import { store } from "./data/store.js";
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  // data() {
  //   return {
  //     store,
  //   };
  // },

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
          store.movies = response.data.results.map((movie) => {
            const {
              id,
              title,
              original_title,
              original_language,
              vote_average,
            } = movie;
            return {
              id,
              title,
              original_title,
              language: original_language,
              vote: vote_average,
            };
          });
        });
    },

    fetchTvSeries(string) {
      axios
        .get(" https://api.themoviedb.org/3/search/tv", {
          params: {
            query: string,
            api_key: "321fee9b963d1057eaa31792bfd9c2e9",
          },
        })
        .then((response) => {
          console.log(response.data.results);
          store.tvSeries = response.data.results.map((tvSerie) => {
            const { id, name, original_name, original_language, vote_average } =
              tvSerie;
            return {
              id,
              title: name,
              original_title: original_name,
              language: original_language,
              vote: vote_average,
            };
          });
        });
    },

    handleSearch(term) {
      this.fetchMovies(term);
      this.fetchTvSeries(term);
    },
  },

  // created() {
  //   this.fetchMovies();
  // },
};
</script>

<template>
  <AppHeader @start-search="handleSearch" />
  <AppMain />
</template>

<style></style>
