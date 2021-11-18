<template>
  <div class="row product-container">
    <Product v-for="product in productList" :key="product">
      <img
        class="card-img-top"
        :src="product.selectedImage"
        alt="Card image cap"
      />
      <div class="card-body">
        <h5 class="card-title">{{ product.title }}</h5>
        <small> <strong>Quantity : </strong> {{ product.count }} </small>
        <br />
        <small> <strong>Price : $ </strong> {{ product.price }} </small>
        <br />
        <small>
          <strong>Total Price : $ </strong> {{ product.totalPrice }}
        </small>
      </div>
    </Product>
  </div>
</template>

<script>
import { eventBus } from "../main";
import Product from "./Product.vue";
export default {
  components: {
    Product,
  },
  data() {
    return {
      productList: [],
    };
  },
  created() {
    eventBus.$on("addedProduct", (e) => {
      this.productList.push(e);
      eventBus.$emit("counter", this.productList.length);
    });
  },
};
</script>
