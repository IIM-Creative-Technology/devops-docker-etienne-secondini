<template>
  <v-card>
    <v-card-title>
      {{ pokemonInfo.name }}
    </v-card-title>
    <v-card-text>
      <span v-for="type in pokemonInfo.types" :key="type.id">
        {{ type.type.name }}
      </span>
      {{ pokemonInfo.id }}
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Card",
  props: {
    pokemon: {},
  },
  data() {
    return {
      pokemonInfo: {},
      types: [],
    };
  },
  mounted() {
    this.fetchInfoPokemon();
  },
  methods: {
    fetchInfoPokemon: function () {
      const baseURI = this.pokemon.url;
      this.$http.get(baseURI).then(result => {
        this.pokemonInfo = result.data;
        console.log(this.pokemonInfo);
      });
      this.types = this.pokemonInfo.type;
    },
  },
};
</script>

<style></style>
