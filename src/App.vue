<template>
  <div id="app">
    <div class="container">
      <Login :user="user" />

      <FicheProduit :commandFood="commandFood" :affichage="affichage" />

      <ProduitPanier
        :deleteFood="deleteFood"
        :commandes="commandes"
        :affichage="affichage"
      />
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
    },
    deleteFood(id) {
      this.commandes.splice(id, 1);
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
