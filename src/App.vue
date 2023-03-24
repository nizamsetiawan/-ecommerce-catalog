<template>
  <div id="app">
    <ProductDisplay />
  </div>
</template>

<script>
import ProductDisplay from './components/ProductDisplay.vue'

export default {
  name: 'App',
  components: {
    ProductDisplay
  }
}
</script>

<style>
#app {
  font-family: Inter, Avenir, Helvetica, Arial, sans-serif;
  padding: 0px;
  margin: 0px;
  top: 0px;

  box-sizing: border-box;

}
* {
    margin: 0;
}
</style>
