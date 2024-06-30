<template>
  
  <div>

    <div class="container">
      <h1>Witaj w naszym sklepie internetowym!</h1>
      <p>Znajdziesz tutaj najnowsze trendy w modzie, elektronice, książkach i wielu innych kategoriach. Zapraszamy do zapoznania się z naszą ofertą!</p>
   
      <section class="section">
        <h2 class="section-title">Najnowsze produkty</h2>
        <div class="products">
          <div v-for="product in latestProducts" :key="product.id" class="product">
            <img :src="product.image" :alt="product.name" class="product-image">
            <h3 class="product-name">{{ product.name }}</h3>
            <p class="product-price">Cena: {{ product.price }} zł</p>
            <button @click="addToCart(product.id)" class="button">Dodaj do koszyka</button>
          </div>
        </div>
      </section>

      <section class="section">
        <h2 class="section-title">Promocje</h2>
        <div class="promotions">
          <div v-for="promotion in promotions" :key="promotion.id" class="promotion" @mouseover="highlightPromotion(promotion.id)" @mouseout="removeHighlight(promotion.id)">
            <h3 class="promotion-title" :class="{ 'highlighted': highlightedPromotion === promotion.id }">{{ promotion.name }}</h3>
            <p class="promotion-description">{{ promotion.description }}</p>
          </div>
        </div>
      </section>

      <section class="section">
        <h2 class="section-title">Popularne kategorie</h2>
        <ul class="categories">
          <li v-for="category in popularCategories" :key="category.id" class="category">{{ category.name }}</li>
        </ul>
      </section>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  data() {
    return {
      latestProducts: [
        { id: 1, name: "Papier ścierny ultrastrong", price: 19.99, image: "http://localhost:3000/papier.png" },
        { id: 2, name: "Laczki+", price: 599.99, image: "http://localhost:3000/buty.png" },
        { id: 3, name: "Parasol 'Światłowstręt'", price: 49.99, image: "http://localhost:3000/parasol.png" }
      ],
      promotions: [
        { id: 1, name: "Promocyjne poniedziałki!", description: "Taniej nawet o 20%!" },
        { id: 2, name: "Kup 3, zapłać za 2!", description: "Na wszystkie oznaczone rzeczy" }
      ],
      popularCategories: [
        { id: 1, name: "Elektronika" },
        { id: 2, name: "Akcesoria" },
        { id: 3, name: "Książki" }
      ],
      highlightedPromotion: null
    };
  },
  methods: {
    addToCart(productId) {
      console.log(`Dodałeś do koszyka produkt o ID ${productId}`);
    },
    highlightPromotion(promotionId) {
      this.highlightedPromotion = promotionId;
    },
    removeHighlight(promotionId) {
      if (this.highlightedPromotion === promotionId) {
        this.highlightedPromotion = null;
      }
    }
  }
};
</script>

<style scoped>

.container {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.section {
  margin-bottom: 40px;
}

.section-title {
  font-size: 24px;
  margin-bottom: 20px;
}

.products {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.product {
  width: 200px;
  margin-bottom: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
}

.product-image {
  width: 100%;
  height: auto;
  border-radius: 5px;
}

.product-name {
  font-size: 18px;
  margin-top: 10px;
}

.product-price {
  font-size: 16px;
  margin-top: 5px;
}

.button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.button:hover {
  background-color: #0056b3;
}

.promotion {
  margin-bottom: 20px;
  padding: 20px;
  border: 2px solid #007bff;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.promotion-title {
  color: #007bff;
  font-size: 20px;
}

.promotion-description {
  margin-top: 10px;
  font-size: 16px;
}

.categories {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
}

.category
{
  margin-right: 20px;
  padding: 10px;
  border: 2px solid #007bff;
  border-radius: 5px;
  font-size: 18px;
}

.highlighted {
  background-color: #c7ffae; 
}
</style>