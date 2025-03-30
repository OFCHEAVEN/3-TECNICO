<template>
    <div>
      <h2>Carrinho de Compras</h2>
      <!-- Botão que adiciona um produto ao carrinho -->
      <button @click="addItemToCart({ id: 1, name: 'Produto X', price: 50 })">
        Adicionar Produto X ao Carrinho
      </button>
      <button @click="addItemToCart({ id: 2, name: 'Produto Y', price: 75 })">
        Adicionar Produto Y ao Carrinho
      </button>
  
      <!-- Exibição do número de itens no carrinho -->
      <p>Total de itens no carrinho: {{ cartItemCount }}</p>
  
      <!-- Exibição dos itens no carrinho -->
      <div v-if="cart.length > 0">
        <h3>Itens no Carrinho:</h3>
        <ul>
          <li v-for="item in cart" :key="item.id">
            {{ item.name }} - R$ {{ item.price }}
          </li>
        </ul>
      </div>
      <div v-else>
        <p>O carrinho está vazio.</p>
      </div>
    </div>
  </template>
  
  <script>
  import { mapActions, mapGetters } from 'vuex';
  
  export default {
    computed: {
      ...mapGetters(['cartItemCount', 'cart']), // Obtém os itens do carrinho e a contagem
    },
    methods: {
      ...mapActions(['addToCart']), // Mapeia a ação Vuex
      addItemToCart(product) {
        this.addToCart(product); // Chama a ação ao clicar no botão
      },
    },
  };
  </script>
  