<template>
  <div class="progress">
    <div
      class="progress-bar bg-info"
      role="progressbar"
      :style="{ width: counter * 10 + '%' }"
      aria-valuenow="50"
      aria-valuemin="0"
      aria-valuemax="100"
    >
      {{ counter }}/10
    </div>
  </div>
</template>
<script>
import Products from "./Products.vue";
import { eventBus } from "../main";
export default {
  components: {
    Products,
  },
  data() {
    return {
      counter: null,
    };
  },
  created() {
    eventBus.$on("counter", (e) => {
      this.counter = e;
    });
  },
};
</script>
