<template>
  <div id="app">
    <div class="container">
      <Login :user="user" />

      <div class="row">
        <h1 class="w-100" v-bind:class="affichage">
          Produits disponibles
        </h1>

        <div class="col-3" v-for="(produit, index) in produits" :key="index">
          <p class="jumbotron">
            {{ produit }}
            <br />
            <br />
            <button class="btn btn-primary" @click="commandFood(produit)">
              +
            </button>
          </p>
        </div>
      </div>
      <!-- <FicheProduit /> -->

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
// import FicheProduit from "./components/FicheProduit";
// import ProduitPanier from "./components/ProduitPanier";
import Login from "./components/Login";

export default {
  name: "App",
  components: { Login },
  data() {
    return {
      user: "",
      produits: ["Pizza", "Cheese", "Tacos", "Kebab"],
      commandes: [],
      total: [],
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
}
</style>
