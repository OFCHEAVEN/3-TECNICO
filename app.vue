<template>
    <div id="app">
      <h1>Minha Loja Virtual</h1>
      <ShoppingCart />
    </div>
  </template>
  
  <script>
  import ShoppingCart from './components/ShoppingCart.vue';
  
  export default {
    components: {
      ShoppingCart,
    },
  };
  </script>
  