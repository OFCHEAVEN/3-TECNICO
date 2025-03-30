<template>
    <div>
      <h2>{{ product.name }}</h2>
      <button @click="addProductToCart">Adicionar ao Carrinho</button>
    </div>
  </template>
  
  <script>
  import { mapActions } from 'vuex';
  
  export default {
    props: {
      product: Object, // Produto recebido como propriedade
    },
    methods: {
      ...mapActions(['addToCart']), // Mapeando ação do Vuex
      addProductToCart() {
        this.addToCart(this.product);
      }
    }
  };
  </script>
  