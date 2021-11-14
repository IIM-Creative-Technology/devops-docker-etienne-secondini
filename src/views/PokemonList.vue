<template>
  <div class="centerDiv maxWidth">
    <div class="m3" v-for="pokemon in pokemonList" :key="pokemon.id">
      <router-link
        :to="{ name: 'PokemonDetails', params: { pokemon: pokemon } }"
      >
        <Card :pokemon="pokemon" />
      </router-link>
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
export default {
  name: "PokemonList",
  components: {
    Card,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      pokemonList: {},
    };
  },
  mounted() {
    this.fetchUsers();
  },
  methods: {
    fetchUsers: function () {
      console.log("fucntion called");
      const baseURI = "https://pokeapi.co/api/v2/pokemon";
      this.$http.get(baseURI).then(result => {
        this.pokemonList = result.data.results;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.maxWidth {
  max-width: 50vw;
}
.centerDiv {
  margin: 0 auto;
}
.m3 {
  margin-bottom: 30px;
}
</style>
