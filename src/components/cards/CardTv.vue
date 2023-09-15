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
      <img :src="cardInfo.image" alt="" srcset="" />
      {{ cardInfo.title }} - {{ cardInfo.original_title }} -
      {{ cardInfo.vote }}

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
      />
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
