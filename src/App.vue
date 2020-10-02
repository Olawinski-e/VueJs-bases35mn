<template>
  <div id="app">
    <div class="container">
      <Login :user="user" />

      <FicheProduit :commandFood="commandFood" :affichage="affichage" />

      <div class="row" v-if="commandes.length > 0">
        <h1 class="w-100" v-bind:class="affichage">
          Produits commandés
        </h1>

        <ul>
          <li v-for="(commande, index) in commandes" :key="index">
            {{ commande }}
            <button class="btn btn-danger" @click="deleteFood(index)">
              -
            </button>
          </li>
        </ul>
      </div>
      <!-- <ProduitPanier /> -->
    </div>
  </div>
</template>

<script>
import FicheProduit from "./components/FicheProduit";
// import ProduitPanier from "./components/ProduitPanier";
import Login from "./components/Login";

export default {
  name: "App",
  components: { Login, FicheProduit },
  data() {
    return {
      user: "",
      produits: [],
      commandes: [],
      affichage: "",
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
}
</style>
