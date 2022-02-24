<template>
  <div class="product-item">
      <li class="product">
        <p>No.{{ id }}</p>
        <h3>{{ name }}</h3>
        <p>${{ price }}</p>
      </li>
    </div>
</template>

<script>
export default {
  name: 'ProductItem',
  props: ['id','name','price']
}
</script>

<style>
  .product-item {
    border: 1px solid;
    margin: 0 5px;
    display: flex;
    flex-wrap: wrap;
  }
  .product-item li {
    border-radius: 5px;
    width: 180px;
    margin: 10px auto;
    box-shadow: 0 2px 10px 1px rgba(0, 0, 0, 0.3);
    list-style: none;
    line-height: 10px;
    transition: .3s;
  }
  .product-item li:hover {
    transform: scale(1.1);
  }
</style>