<template>
  <div id="app">
    <div>
      Je refais un test que j'ai loupé pour une entreprise j'utilise l'api :<a
        href="https://pokeapi.co/api/v2/pokemon"
        target="_blank"
      >
        Pokemon</a
      >
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
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
