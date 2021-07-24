<template>
  <div id="app">
    <h2>Calculator</h2>
    <app-calculator></app-calculator>
  </div>
</template>

<script>
import Calculator from "./components/Calculator.vue"
export default {
  name: 'App',
  components: {
    appCalculator:Calculator
  }
}
</script>

<style lang="scss">
  @import "./assets/scss/app.scss";
  #app{
    h2{
      text-align: center;
      margin-top:2rem;
      color: #fff;
      font-size: 35px;
    }
  }

</style>
