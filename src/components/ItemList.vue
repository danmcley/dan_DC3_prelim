<template>
  <div class="product-list">
    <h2>Product List</h2>
    <div class="products-container">
      <ProductItem 
        v-for="product in products" 
        :key="product.id" 
        :product="product" 
        @add-to-cart="handleAddToCart" 
      />
    </div>
  </div>
</template>

<script>
import ProductItem from './Item.vue';

export default {
  name: 'ProductList',
  components: {
    ProductItem,
  },
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleAddToCart(product) {
      console.log(`${product.name} added to cart`); 
    },
  },
  computed: {
    filteredItems() {
      return this.item.filter((item) => item.isVisible)
    }
  }
};
</script>

<style scoped>
.product-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.products-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
