<script setup lang="ts">
import { ref } from 'vue'

const storeTitle = ref('TechMart Store')
const welcomeMessage = ref('Welcome to our shop')
const productThumbnail = ref('https://via.placeholder.com/150')
const isAvailable = ref(false)

const itemName = ref('laptop sleeve')
const itemPrice = ref(40)
const quantity = ref(2)
</script>

<template>
  <!-- 1. Store Banner -->
  <header class="hero-banner">
    <h1>{{ storeTitle }}</h1>
    <p>{{ welcomeMessage }}</p>
  </header>

  <!-- 2. Product Details & Checkout Summary -->
  <main class="product-card">
    <img :src="productThumbnail" :alt="itemName" />
    
    <h2>{{ itemName.toUpperCase() }}</h2>
    <p class="price-calc">
      Price: ${{ itemPrice }} x {{ quantity }} = <strong>${{ itemPrice * quantity }}</strong>
    </p>

    <!-- Stock Status -->
    <p :class="quantity > 0 ? 'status-in-stock' : 'status-out'">
      {{ quantity > 0 ? '✓ Ready to Ship' : '✕ Currently Unavailable' }}
    </p>

    <button :disabled="!isAvailable">
      {{ isAvailable ? 'Buy Now' : 'Out of Stock' }}
    </button>
  </main>
</template>

<style scoped>
.hero-banner {
  text-align: center;
  padding: 2rem;
  background-color: #f4f6f8;
}
h1 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
}
p {
  color: #666;
}
</style>