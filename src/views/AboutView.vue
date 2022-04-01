<template>

<div class="moreDetails">
  <div class="card" v-if="podaci">
    <p>Author: {{ podaci.authors }}</p>
    <p>Name: {{ podaci.name }}</p>
    <p>Released: {{ podaci.released }}</p>
    <p>isbn: {{ podaci.isbn }}</p>
    <p>Broj stranica: {{ podaci.numberOfPages }}</p>
    <p v-if="podaci.characters">Broj likova: {{ podaci.characters.length }} </p>
    <p>Broj izdavaca: {{ podaci.publisher }}</p>
    <p></p>
  </div>
</div>

</template>

<script>
import axios from "axios";

export default {
  name: "AboutView",

  data() {
    return {
      URL: this.$route.params.URL,
      podaci: [],

    };
  },
  props: {

  },
  async mounted() {
    /* console.log(this.URL); */
    const get = await axios.get(
      this.URL
      );
    this.podaci = get.data;
    
  },
};
</script>

<style></style>
