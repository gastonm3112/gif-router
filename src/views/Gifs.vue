<template>
  <div class="container">
    <h1 class="text-center">Gifs</h1>
    <hr />
  </div>
</template>

<script>
export default {
  mounted() {
    const res = this.axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(({ data }) => console.log(data));
  },
};
</script>

<style></style>
