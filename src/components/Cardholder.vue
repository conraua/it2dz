<template>
  <div class="col-lg-3 col-md-4 col-sm-6 col-xs-12">
    <div class="product-details">
        <h3> {{ product.name }} </h3>
        <img :src = product.image>
        <h5> {{ product.description }} </h5>
        <p> {{ product.price }} Рублей </p>
      </div>
  </div>
</template>

<script>
module.exports = {
  props: ['product'],
  name: 'Cardholder',
}
</script>

<style scoped>
  img {
    align: middle;
    width: 200px;
    height: 200px;
  }
  h3 {
    margin: 10px;
  }
  h5 {
    margin: 10px;
  }
  p {
    margin: 10px;
  }
</style>
