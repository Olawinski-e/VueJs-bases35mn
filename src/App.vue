<template>
  <div id="app">
    <div class="container">
      <Login :user="user" />

      <FicheProduit :commandFood="commandFood" v-bind:class="affichage" />

      <ProduitPanier />
      <ul>
        <li v-for="(commande, index) in commandes" :key="index">
          {{ commande }}
          <button class="btn btn-danger" @click="deleteFood(index)">
            -
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import FicheProduit from "./components/FicheProduit";
import ProduitPanier from "./components/ProduitPanier";
import Login from "./components/Login";

export default {
  name: "App",
  components: { Login, FicheProduit, ProduitPanier },

  data() {
    return {
      user: "",
      produits: [],
      commandes: [],
      affichage: "display-6",
    };
  },
  methods: {
    commandFood(produit) {
      this.commandes.push(produit);
      console.log(this.commandes);
    },
    deleteFood(id) {
      this.commandes.splice(id, 1);
      console.log(this.commandes);
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  li {
    text-align: left;
    margin-bottom: 4px;
  }
}
</style>
