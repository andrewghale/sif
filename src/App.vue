<template>
  <div id="app">
    <Products v-bind:products="allProducts" />
    <!-- <Parent /> -->
  </div>
</template>

<script>
import json from './utils/sample.json';
import Products from './components/Products.vue';
import Parent from './components/Parent.vue';



const getDiscount = json[0].discountPercent;
const getProducts = json[0].products;

export default{
  name: "App",
  components: {
    Products,
    Parent
  },
    data(){
        return{
            discount: getDiscount,
            allProducts: getProducts
        }
    }
}



</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* background-color: mistyrose; */
  padding: 2rem;
}
</style>
