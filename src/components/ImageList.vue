<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="row">
      <div
        class="col-sm-6 col-md-3 col-xl-2"
        v-for="(result, index) in processedResults"
        :key="result.id"
      >
        <a class="card" :href="result.post_url">
          <h5 class="card-title">{{index}}:{{result.author}}</h5>
          <img class="card-img" :src="result.url" :alt="result.post_url" />
          <p class="card-text">{{result.filename}}.</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
const axios = require("axios");
export default {
  name: "ImageList",
  props: {
    msg: String
  },
  data() {
    return {
      info: null,
      results: []
    };
  },
  mounted: function() {
    {
      axios
        .get("https://api.coindesk.com/v1/bpi/currentprice.json")
        .then(response => (this.info = response.data.bpi));

      axios
        .get("https://picsum.photos/list")
        .then(response => (this.results = response.data));
    }
  },
  computed: {
    processedResults: function() {
      let results = this.results;
      for (let i = 0; i < results.length; i++) {
        results[i].url = "https://picsum.photos/300/200?image=" + results[i].id;
      }
      return results;
    }
  }
};
</script>

<style scoped>
a {
  color: #42b983;
}
</style>