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
  <section id="movies" class="cards-container">
    <CardMovies
      v-for="movie in store.movies"
      :key="movie.id"
      :cardInfo="movie"
    />
  </section>
  <h2>Lista Serie TV</h2>
  <section id="tv" class="cards-container">
    <CardTv
      v-for="tvSerie in store.tvSeries"
      :key="tvSerie.id"
      :cardInfo="tvSerie"
    />
  </section>
</template>

<style lang="scss" scoped>
.cards-container {
  display: flex;
  flex-wrap: wrap;
  // justify-content: space-between;
}
h2 {
  color: white;
}
</style>
