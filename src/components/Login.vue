<template>
  <div class="row">
    <p class="jumbotron w-100">
      Login: <input type="text" v-model="user" /> <br /><br />
      Vous êtes connecté en tant que {{ user }}.
    </p>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      user: "Estelle",
    };
  },
};
</script>
