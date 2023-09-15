<script>
import CardsList from "./cards/CardsList.vue";

export default {
  data() {
    return {
      title: "Hello world",
    };
  },

  components: {
    CardsList,
  },
};
</script>

<template>
  <div class="container mt-5">
    <CardsList />
  </div>
</template>

<style lang="scss" scoped></style>
