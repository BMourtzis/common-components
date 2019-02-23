<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <page-loader :call="prom">Loaded</page-loader>
  </div>
</template>

<script>
import pageloader from "./components/page-loader";

export default {
  name: "app",
  components: {
    "page-loader": pageloader
  },
  data() {
    return {
      prom: new Promise(resolve => {
        setTimeout(resolve, 2000);
      })
    };
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
