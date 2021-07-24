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
  @import url('https://fonts.googleapis.com/css2?family=Rubik:wght@300;400&display=swap');
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Rubik', sans-serif;;
  }

  body{
    width: 100%;
    background: #0F4C75;
  }


  #app{
    h2{
      text-align: center;
      margin-top:2rem;
      color: #fff;
      font-size: 35px;
    }
  }

</style>
