<template>
  <div class="container">
    <h1 class="text-center">Gifs</h1>
    <search />
    <hr />

    <div class="row">
      <div class="col-sm-12">
        <gif-card :data="gifs" class="m-3 w-75" />
      </div>
    </div>
  </div>
</template>

<script>
import GifCard from "../components/GifCard.vue";
import Search from "../components/Search.vue";
export default {
  components: { GifCard, Search },
  data: () => ({
    gifs: {},
  }),
  created() {
    this.getGifs();
  },
  methods: {
    async getGifs() {
      //Obtiene Gifs desde la API de GIPHY
      const { data } = await this.axios.get(
        "https://api.giphy.com/v1/gifs/random?api_key=YCZzQAunZxEv7WQPi1WaK0PIZ2wqMDvW"
      );

      console.log(data);

      this.gifs = data.data; //gifs toma el valor de data

      console.log(this.gifs);
    },
  },
};
</script>

<style></style>
