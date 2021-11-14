<template>
  <div id="app">
    testing
    <PokemonList />
  </div>
</template>

<script>
import PokemonList from "./views/PokemonList.vue";

export default {
  name: "App",
  components: {
    PokemonList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
