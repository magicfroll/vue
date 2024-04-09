<template>
  <div class="product">
    <h2>Product</h2>
    <h3>Name: {{ product.name }}</h3>
    <h3>Price: {{ formattedPrice }}</h3>
    <h4 v-if="product.available">Available</h4>
    <h4 v-else>Out of stock</h4>
    <button @click="product.available = !product.available">Для проверки</button>
  </div>
</template>

<script>
export default {
  name: 'ProductDetails',

  data() {
    return {
      product: {
        name: 'Milk',
        price: 19.99,
        available: true,
      }
    };
  },

  mounted() {
    
  },

  computed: {
    formattedPrice() {
        let formatter = new Intl.NumberFormat("en-US", {                    
                    currency: "USD",
                    style: "currency",
                });
        return formatter.format(this.product.price)
    }
  },
};
</script>

<style>
  .product {
    margin-top: 20px;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
    width: 200px;
    padding: 20px;
    border: 1px solid black;
    border-radius: 20px;
  }
</style>