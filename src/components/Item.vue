<template>
  <div class="product-item">
    <img :src="product.image" alt="Product Image" class="product-image" />
    <h3>{{ product.name }}</h3>
    <p>Price: ${{ product.price }}</p>
    <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  name: 'ProductItem',
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToCart() {
      this.$emit('add-to-cart', this.product);
    },
  },
};
</script>

<style scoped>
.product-item {
  border: 1px solid #ccc;
  padding: 20px;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.product-image {
  max-width: 100px;
  height: auto;
}

button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #218838;
}
</style>
