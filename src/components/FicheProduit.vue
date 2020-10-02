<template>
  <div class="row">
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
</template>

<script>
export default {
  name: "FicheProduit",
};
</script>
