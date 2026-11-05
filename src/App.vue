<script setup lang="ts">
import { ref } from 'vue'

const storeTitle = ref('TechMart Store')
const welcomeMessage = ref('Welcome to our shop')
const productThumbnail = ref('https://via.placeholder.com/150')
const isAvailable = ref('false')
</script>

<template>
  <header class="hero-banner">
    <h1>{{ storeTitle }}</h1>
    <p>{{ welcomeMessage }}</p>
    <img :src="productThumbnail" />
    <button :disabled="!isAvailable">
    {{ isAvailable ? 'buy now' : 'out of stock'  }}  
    </button>
  </header>
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