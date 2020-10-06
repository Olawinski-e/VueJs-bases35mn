<template>
  <div class="row">
    <h1 class="w-100" v-bind:class="affichage">
      Produits disponibles
    </h1>
    <div class="col-3" v-for="(produit, index) in produits" :key="index">
      <p class="jumbotron">
        {{ produit }}
        <button class="btn btn-primary" @click="commandFood(produit)">
          +
        </button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "FicheProduit",
  props: {
    commandFood: Function,
    affichage: {
      type: String,
      default() {
        return "";
      },
    },
  },
  data() {
    return {
      produits: ["Pizza", "Cheese", "Tacos", "Kebab"],
    };
  },
};
</script>
