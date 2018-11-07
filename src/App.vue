<template>
  <div id="app">
    <booking></booking>
  </div>
</template>

<script>
import Booking from './components/Booking.vue'

export default {
  name: 'app',
  components: {
    Booking
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  /* background-color: #F7F6F2; */
}
</style>
