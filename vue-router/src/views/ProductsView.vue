<template>
  <h2>use component</h2>
  <div class="product-list">
    <div style="padding-bottom: 20px">
      No: <input type="text" v-model="No" />
      Name: <input type="text" v-model="name" /> 
      Price:<input type="text" v-model="price" />
    </div>
    <button @click="newItem">Add</button>
  </div>

  <div class="product-list">
    <div class="product-item">
      <productItem
        v-for="product in products"
        :key="product.id"
        :name="product.name"
        :price="product.price"
      ></productItem>
    </div>
  </div>

  <h2>no component</h2>
  <div class="product-list">
    <div class="product-item">
      <li v-for="product in products" :key="product.id" :name="product.name" :price="product.price">
        <p>No.{{ product.id }}</p>
        <h3>{{ product.name }}</h3>
        <p>${{ product.price }}</p>
      </li>
    </div>
  </div>
</template>

<script>
import ProductItem from '@/components/ProductItem.vue';

export default {
  name: 'ProductView',
  components: {
    ProductItem,
  },
  data() {
    return {
      name: '',
      price: 0,
      products: [
        {
          id: 1,
          name: 'Superman',
          price: 100,
        },
        {
          id: 2,
          name: 'Spiderman',
          price: 200,
        },
        {
          id: 3,
          name: 'Ironman',
          price: 300,
        },
        {
          id: 4,
          name: 'Batman',
          price: 400,
        },
      ],
    };
  },
  methods: {
    newItem() {
      let name = this.name;
      let price = this.price;

      this.products.push({
        id: 5,
        name: name,
        price: price,
      });
    },
  },
};
</script>

<style>
.product-list {
  display: flex;
  flex-wrap: wrap;
  width: 800px;
  max-width: 100%;
  margin: 0 auto;
}
</style>
