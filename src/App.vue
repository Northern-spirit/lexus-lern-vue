<template>
  <div id="app">
    <CardsPlanet />
  </div>
</template>

<script>
import CardsPlanet from "./components/CardsPlanet.vue";

export default {
  name: "App",
  components: {
    CardsPlanet,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
