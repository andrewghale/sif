<template>
  <div>
    <div v-bind:key="product.id" v-for="product in products">
      <h3>{{ product.name }}</h3>
      {{ product.description }}
      <p>{{ product.price }}</p>
      <button>ADD TO CART</button>
    </div>
  </div>
</template>

<script>
export default {
    name: "Products",
    props: ["products"]
}
</script>

<style>

</style>