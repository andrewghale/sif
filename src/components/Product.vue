<template>
  <div class="wrapper">
    <h3 class="title">{{ product.name }}</h3>
    <p class="descrip">{{ strippedContentDesc }}</p>
    <label class="price">{{ product.price }}
        <input class="checkbox" type="checkbox">
    </label>
    <button>ADD TO CART</button>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: ["product"],
  computed: {
    strippedContentDesc() {
      let regex = /(<([^>]+)>)/gi;
      return this.product.description.replace(regex, "");
    }
  }
};
</script>
<style lang="scss">

$button-color: rgb(100, 177, 146);
$button-bottom: rgb(69, 139, 109);
$text:rgb(53, 53, 53);

.wrapper {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.title {
    color:$text;
    margin-bottom: 1rem;
}
.descrip {
    color: $text;
    font-weight: medium;
}
.checkbox {
    margin-top: 1rem;
    height: 25px;
    width: 25px;
}
.price {
    font-size: 1.5rem;
    color: $text;
}
button {
    background-color: $button-color;
    color: rgb(255, 255, 255);
    padding: 1.5rem 2rem;
    width: 100%;
    font-size: 1.2rem;
    font-weight: bold;
    border-radius: 3px;
    cursor: pointer;
    border: none;
    border-bottom: 6px solid $button-bottom;
    margin-top: auto;
    transition: border-bottom 0.1s ease-in-out;
    &:active {
    border-bottom: 0px solid $button-bottom;
    transition: border-bottom 0s ease-in-out;
    }
}
</style>