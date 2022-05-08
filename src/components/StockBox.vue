<template>
  <div class="stockbox">
    <div v-for="stock in stocks" :key="stock.symbol">
      <Stock :stock="stock" />
    </div>
  </div>
</template>

<script>
import Stock from "./Stock.vue";
export default {
  name: "StockBox",
  components: {
    Stock,
  },
  props: {
    stocks: Object,
  },
};
</script>


<style>
.stockbox {
  background-color: #FEB139;
  padding: 1em;
  color: gray;
}
</style>