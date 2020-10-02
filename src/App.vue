<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <p class="jumbotron w-100">
          Login: <input type="text" v-model="user" /> <br /><br />
          Vous êtes connecté en tant que {{ user }}.
        </p>
      </div>

      <div class="row">
        <div class="col-3" v-for="(produit, index) in produits" :key="index">
          <p class="jumbotron">
            {{ produit }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      user: "Estelle",
      produits: ["Pizza", "Cheese", "Tacos", "Kebab"],
    };
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
