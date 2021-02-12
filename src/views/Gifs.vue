<template>
  <div class="container">
    <h1 class="text-center">Gifs</h1>
    <hr />
  </div>
</template>

<script>
export default {
  data: () => ({
    gifs: null,
  }),
  mounted() {
    this.getGifs();
  },
  methods: {
    async getGifs() {
      const res = await this.axios.get(
        "https://api.giphy.com/v1/gifs/random?api_key=YCZzQAunZxEv7WQPi1WaK0PIZ2wqMDvW"
      );

      console.log(res);
    },
  },
};
</script>

<style></style>
