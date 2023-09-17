<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      term: "",
    };
  },

  emits: ["start-search"],
};
</script>

<template>
  <div class="header">
    <img src="../../public/logo Netflix.jpg" alt="" srcset="" width="130" />
    <nav class="navbar">
      <div class="container-fluid">
        <form
          @submit.prevent="$emit('start-search', term)"
          class="d-flex"
          role="search"
        >
          <input
            v-model="term"
            class="form-control me-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-danger" type="submit">Search</button>
        </form>
      </div>
    </nav>
  </div>
</template>

<style lang="scss" scoped>
.header {
  background-color: #101010;
  display: flex;
  justify-content: space-between;

  nav {
    background-color: #101010;
  }
}
</style>
