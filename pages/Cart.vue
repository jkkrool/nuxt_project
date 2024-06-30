<template>
    <div class="container">
      <h1>Twój koszyk</h1>
      <div v-if="cart.length === 0" class="empty-cart">
        <p>Twój koszyk jest pusty.</p>
        <router-link to="/home" class="button">Przejdź do zakupów</router-link>
      </div>
      <div v-else>
        <p>Twój koszyk jest obecnie pusty.</p>
        <router-link to="/home" class="button">Kontynuuj zakupy</router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cart: [] // Tablica na produkty w koszyku
      };
    },
    created() {

      this.cart = JSON.parse(localStorage.getItem('cart')) || [];
    }
  };
  </script>
  
  <style scoped>
  .container {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
  }
  
  .empty-cart {
    margin-top: 50px;
  }
  
  .button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    text-decoration: none;
  }
  
  .button:hover {
    background-color: #0056b3;
  }
  </style>
  