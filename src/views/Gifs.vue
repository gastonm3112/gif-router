<template>
  <div class="container">
    <h1 class="text-center">Gifs</h1>
    <search @petition="getGifs" />
    <hr />
    <loading />
    <div class="row">
      <div class="col-sm-12" v-for="gif in gifs" :key="gif.id">
        <gif-card :data="gif" class="m-3 w-75" />
      </div>
    </div>
  </div>
</template>

<script>
import Loading from "../components/Loading.vue";
import GifCard from "../components/GifCard.vue";
import Search from "../components/Search.vue";
export default {
  components: { GifCard, Search, Loading },
  data: () => ({
    gifs: {},
  }),
  created() {
    this.getGifs();
  },
  methods: {
    async getGifs(search = "") {
      const apiKey = "YCZzQAunZxEv7WQPi1WaK0PIZ2wqMDvW";

      //Obtiene Gifs desde la API de GIPHY
      const { data } = await this.axios.get(
        `https://api.giphy.com/v1/gifs/search?q=${search}&api_key=${apiKey}`
      );

      //console.log(data);

      this.gifs = data.data; //gifs toma el valor de data

      // console.log(this.gifs);
      // console.log(search);
    },
  },
};
</script>

<style></style>
