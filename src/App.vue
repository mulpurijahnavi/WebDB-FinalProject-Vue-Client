<template>
  <div class="container">
    <!-- #3 must use the component-->
    <Header title="Most Active Stocks" />
    <StockBox :stocks="stocks" />

    <button class="button" onclick="window.open('https://nodejs-stocks-website.herokuapp.com','_blank')">About Me</button>
  </div>
</template>
<script>
//import HelloWorld from './components/HelloWorld.vue'
// 1
import Header from "./components/Header.vue";
import StockBox from "./components/StockBox.vue";

export default {
  name: "App",
  components: {
    // 2 register the component
    Header,
    StockBox,
  },

  data() {
    return {
      stocks: [],
    };
  },
  methods: {
    // promises
    async fetchStocks() {
      const res = await fetch(
        "https://nodejs-stocks-website.herokuapp.com/api"
      );
      const data = await res.json();
      console.log(data.stocks);
      return data.stocks;
    },
  },

  async created() {
    this.stocks = await this.fetchStocks();
  },
};
</script>



<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Montserrat", sans-serif;
}
.container {
  max-width: 600px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div {
  margin-bottom: 0.5em;
}

.button {
    width: 100%;
    height: 50px;
    margin-top: 10px;
}
</style>


