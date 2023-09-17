<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  props: {
    cardInfo: Object,
  },
};
</script>

<template>
  <div class="card">
    <div class="card-body">
      <div class="cover">
        <img :src="cardInfo.image" alt="" srcset="" />
      </div>
      <div class="back-cover">
        <p>Titolo: {{ cardInfo.title }}</p>
        <p>Titolo originale: {{ cardInfo.original_title }}</p>
        <p>Voto: {{ Math.ceil(cardInfo.vote / 2) }}</p>
        <p>Descrizione: {{ cardInfo.description }}</p>
      </div>
      <!-- {{ cardInfo.title }} - {{ cardInfo.original_title }} -
      {{ Math.ceil(cardInfo.vote / 2) }}

      <img
        v-show="cardInfo.language == 'en'"
        src="../../../public/uk.png"
        alt=""
        width="40"
      />
      <img
        v-show="cardInfo.language == 'it'"
        src="../../../public/ita-flag.svg"
        alt=""
        width="40"
      /> -->
    </div>
  </div>
</template>

<style lang="scss" scoped>
.back-cover {
  background-color: black;
  width: 100%;
  height: 450px;
  color: white;
  padding: 20px;
  display: none;

  p {
    margin: 0;
  }
}

.card {
  width: 315px;
  margin: 0 8px 8px 0;
  background-color: transparent;

  img {
    width: 100%;
  }
}
.card:hover .back-cover {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.card:hover .cover {
  display: none;
}
</style>
