<template>
  <div class="container">
    <h1 class="text-center">Add Products App</h1>
    <hr />
    <NewProduct></NewProduct>
    <br /><br />
    <ProgressBar></ProgressBar>
    <br /><br />
    <h3 class="text-center">Product List</h3>
    <hr />
    <Products></Products>
    <Product></Product>
  </div>
</template>

<script>
import Product from "./components/Product.vue";
import Products from "./components/Products.vue";
import ProgressBar from "./components/Progress.vue";
import NewProduct from "./components/NewProduct.vue";
export default {
  components: {
    NewProduct,
    ProgressBar,
    Products,
    Product,
  },
  data() {
    return {
      productList: [],
      product: {
        selectedImage: null,
      },
    };
  },
  methods: {
    onChange(e) {
      const file = e.target.files[0];
      this.product.selectedImage = URL.createObjectURL(file);
    },
  },
};
</script>

<style>
body {
  background-color: aliceblue;
  padding-top: 20px;
  padding-bottom: 20px;
}

.card {
  margin-right: 5px;
  margin-bottom: 5px;
}

.card:last-child {
  margin-right: 0px;
}

.col-md-2 {
  max-width: 15.666667% !important;
}

.product-container {
  margin-left: 15px;
}
</style>
