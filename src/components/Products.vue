<template>
  <div class="products-container">
    <div class="product-container" v-for="product in products" v-bind:key="product.id">
      <Product v-bind:product="product" />
    </div>
  </div>
</template>

<script>
import Product from "./Product";
export default {
    name: "Products",
    props: ["products"],
    components: {
      Product
    }
};
</script>

<style lang="scss" scoped>

.products-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%;
  .product-container {
    background-color: rgb(255, 255, 255);
    display: flex;
    flex-direction: column;
    padding: 2rem;
    margin: 1rem;
    min-width: 40%;
    min-height: 500px;
    width: 40%;
    height: 400px;
    border-radius: 3px;
    box-shadow: 2px 10px 7px 0px rgba(235,235,235,0.8);
  }
}
</style>