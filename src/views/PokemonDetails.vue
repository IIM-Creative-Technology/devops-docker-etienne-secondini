<template>
  <v-card class="maxWidth">
    <v-card-title> {{ pokemonInfo.name }} </v-card-title>
    <v-card-text>
      <span v-for="(type, index) in pokemonInfo.types" :key="type.id">
        types{{ index + 1 }}: {{ type.type.name }} <br />
      </span>
      poids: {{ pokemonInfo.weight }} kg<br />
      taille: {{ pokemonInfo.height }} cm<br />
      <span v-for="(ability, index) in pokemonInfo.abilities" :key="ability.id">
        Ability {{ index + 1 }}: {{ ability.ability.name }} <br />
      </span>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "PokemonDetails",
  props: {
    pokemon: {},
  },
  data() {
    return {
      pokemonInfo: {},
      types: [],
      abilities: [],
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

<style scoped>
.maxWidth {
  max-width: 60vw;
}
</style>
