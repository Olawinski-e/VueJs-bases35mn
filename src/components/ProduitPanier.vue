<template>
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
</template>

<script>
export default {
  name: "ProduitPanier",
  props: {
    commandes: Array,
    deleteFood: Function,
    affichage: {
      type: String,
      default() {
        return "";
      },
    },
  },
  data() {
    return {};
  },
};
</script>
