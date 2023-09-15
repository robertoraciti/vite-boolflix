<script>
import CardDetail from "./CardDetail.vue";

export default {
  data() {
    return {
      title: "Cards List",
    };
  },

  components: {
    CardDetail,
  },
};
</script>

<template>
  <h1>{{ title }}</h1>
  <CardDetail />
</template>

<style lang="scss" scoped></style>
