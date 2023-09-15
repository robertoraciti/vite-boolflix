<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      title: "Card",
    };
  },
};
</script>

<template>
  <div class="card">
    <div class="card-body">
      {{ title }}
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
