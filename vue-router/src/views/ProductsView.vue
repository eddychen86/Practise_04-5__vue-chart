<template>
  <div>
    <h1>Products</h1>
  </div>
</template>

<script>
export default {
  name: "ProductView",
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Superman",
          price: 100,
        },
        {
          id: 2,
          name: "Spider-man",
          price: 200,
        },
      ],
    };
  },
};
</script>

<style>
</style>