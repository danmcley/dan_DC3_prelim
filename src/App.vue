<template>
  <div id="app">
    <ProductList :products="products" />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import ProductList from '@/components/ItemList.vue';

export default defineComponent({
  name: 'App',
  components: {
    ProductList,
  },
  data() {
    return {
      products: [
        { 
          id: 1, 
          name: 'Nike', 
          price: 100, 
          isVisible: true,
        },
        { 
          id: 2, 
          name: 'Jordan', 
          price: 50, 
          isVisible: true,
        },
        { 
          id: 3, 
          name: 'Adidas', 
          price: 150, 
          isVisible: true,
        },
      ],
    };
  },
});
</script>

<style scoped>
#app {
  font-family: 'Avenir', Arial, Helvetica, sans-serif;
  text-align: center;
  background-color: #f5f5f5;
  padding: 20px;
}
</style>
