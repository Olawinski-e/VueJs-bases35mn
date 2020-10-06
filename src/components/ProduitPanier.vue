<template>
  <div class="row">
    <!-- v-if="commandes.length > 0" -->
    <h1 class="w-100" v-bind:class="affichage">
      Produits commandés
    </h1>
  </div>
</template>

<script>
export default {
  name: "ProduitPanier",
  props: {
    commandes: [],
  },
  data() {
    console.log(this.commandes);
    return {
      affichage: "display-6",
    };
  },
};
</script>
