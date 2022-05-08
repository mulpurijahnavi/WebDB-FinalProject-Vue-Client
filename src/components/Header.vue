<template>
  <div>
    <h1>{{ title }}</h1>
  </div>

  
</template>

<script>
export default {
  name: "Header", 
  props: {
    title: String,
    
  },
  
};
</script>

<style scoped>
div {
  text-align: center;
}
</style>