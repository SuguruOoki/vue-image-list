<template>
  <div class="button">
    <button>{{ msg }}</button>
  </div>
</template>

<script>
export default {
  name: "MyButton",
  props: {
    buttonText: ""
  },
  data() {
    return {};
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
.button {
  color: #42b983;
}
</style>