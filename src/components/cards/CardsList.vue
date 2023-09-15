<script>
import CardMovies from "./CardMovies.vue";
import CardTv from "./CardTv.vue";
import { store } from "../../data/store.js";

export default {
  data() {
    return {
      title: "Cards List",
      store,
    };
  },

  components: {
    CardMovies,
    CardTv,
  },
};
</script>

<template>
  <h2>Lista Film</h2>
  <!-- <ul>
    <li v-for="movie in store.movies" :key="movie.id">
      {{ movie.title }} - {{ movie.original_title }} - {{ movie.language }} -
      {{ movie.vote }}
    </li>
  </ul> -->
  <CardMovies v-for="movie in store.movies" :key="movie.id" :cardInfo="movie" />
  <h2>Lista Serie TV</h2>
  <CardTv
    v-for="tvSerie in store.tvSeries"
    :key="tvSerie.id"
    :cardInfo="tvSerie"
  />
</template>

<style lang="scss" scoped></style>
