<template>

<div class="moreDetails">
  <div class="card">
    <p>Author: {{ podaci.podaci.authors }}</p>
    <p>Name: {{ podaci.podaci.name }}</p>
    <p>Released: </p>
    <p>isbn: {{ isbn }}</p>
    <p>Broj stranica: </p>
    <p>Broj likova: </p>
    <p>Broj izdavaca: </p>
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
  async mounted() {
    const get = await axios.get(
      `${this.URL}`
      );
    this.podaci = get.data;
    console.log(this.podaci);
  },
};
</script>

<style></style>
