<template>
  <form @submit.prevent="handlePetition">
    <div class="mb-3">
      <label for="categoria" class="form-label">Categoría</label>
      <input
        type="text"
        class="form-control"
        id="categoria"
        aria-describedby="categoriaHelp"
        v-model="search"
      />
    </div>
    <button type="submit" class="btn btn-primary">Search</button>
  </form>
</template>

<script>
export default {
  data: () => ({
    search: "",
  }),
  methods: {
    handlePetition() {
      this.$emit("petition", this.search);
    },
  },
};
</script>

<style></style>
