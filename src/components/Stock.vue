<template>
  <div :class="stock.trending ? 'red' : 'green'">
    <h2>{{ stock.name }} ({{ stock.symbol }})</h2>
    <h4>Current Price: ${{ stock.price }}</h4>
    <h5>Market Cap: {{stock.marketCap}} </h5>
  </div>
</template>

<script>
export default {
  name: "Stock",
  props: {
    stock: Object,
  },
};
</script>

<style scoped>
h4 {
  margin: 2px;
}

div {
  background-color: firebrick;
  color: black;
  padding: 1em;
}

.red {
  background-color: #D885A3 !important;
}

.green{
    background-color: lightgreen !important;
}
</style>