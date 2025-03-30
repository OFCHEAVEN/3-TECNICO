<template>
    <div>
      <p>Total de itens no carrinho: {{ cartItemCount }}</p>
    </div>
  </template>
  
  <script>
  import { mapGetters } from 'vuex';
  
  export default {
    computed: {
      ...mapGetters(['cartItemCount']) // Mapeando getter do Vuex
    }
  };
  </script>