<template>
  <div id="app">
    <ImageList msg="画像一覧表示" />
  </div>
</template>

<script>
import ImageList from "./components/ImageList.vue";

export default {
  name: "app",
  components: {
    ImageList
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
