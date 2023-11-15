<template>
  <coin msg="Welcome to Your Vue.js App"/>

</template>

<script>
import coin from './components/coin.vue';


export default {
  name: 'App',
  components: {
    coin
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}
</style>
