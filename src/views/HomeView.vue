<template>
  <div class="home">
    <!-- <data-info v-for="podaci in podaci" :id="podaci.name" :details="podaci.authors" :key="podaci.name"/> -->

    <div class="card" v-for="podaci in podaci" :key="podaci.url" :id="podaci.url">
      <p>Author: {{ podaci.authors }}</p>
      <p>Name: {{ podaci.name }}</p>
      <p>Released: {{ podaci.released }}</p>
      <router-link :to="{ name: 'AboutView', params: { URL : url } }"> VIŠE </router-link>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      podaci: [],
    };
  },

  async mounted() {
    const get = await axios.get("https://www.anapioficeandfire.com/api/books");
    this.podaci = get.data;
    console.log(this.podaci);
  },
};
</script>

<style scoped>
.card{
  background-color: rgb(185, 185, 185);
  margin: auto;
}
</style>
