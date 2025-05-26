<template>
  <div class="app">
    <h1>Calculadora Aritmética</h1>
    <Calculadora />
  </div>
</template>

<script>
import Calculadora from './components/Calculadora.vue'

export default {
  components: {
    Calculadora
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #fff;
}
</style>
