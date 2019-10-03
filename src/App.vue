<template>
  <div id="app">
    <div class="top-container">
      <h1 class="main-title">HELP BOOST YOUR BUSINESS</h1>
      <p class="descrip">Some tailored deals to help you achieve your business and clinical goals.</p>
      <p class="offer">*** Introductory offer - up to 50% off! ***</p>
    </div>
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
<style lang="scss">

* {
  box-sizing: border-box;
}

body {
  display: flex;
  justify-content: center;
  font-size: 18px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 2rem;
  color: #2c3e50;
  background-color: rgb(242, 242, 242);
}

h1, h2, h3, h4, h5, h6, p {
  margin: 0;
}

.top-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: white;
  align-items: center;
  width: 100%;
  margin: 1rem;
  padding: 2rem;
  border-radius: 3px;
  box-shadow: 4px 10px 7px 0px rgba(235,235,235,1);
  .main-title {
      color: #2c3e50;
      font-style: italic;
  }
  .descrip {
    margin: 1rem 0;
  }
  .offer {
    font-size: 1.5rem;
    margin-top: 1rem;
  }
}

.offer {
  color: red;
  font-weight: bold;
}

#app {
  width: 80vw;
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>
