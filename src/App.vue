<template>
  <div class="container">
    <img alt="Vue logo" src="./assets/logo.png" />
    <product></product>
  </div>
</template>

<script>
import Product from './components/Product.vue'
export default {
  name: "App",
  components: {
    Product
  },
};
</script>

<style>
</style>
