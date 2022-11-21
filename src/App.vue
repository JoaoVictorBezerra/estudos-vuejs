<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <SintaxesVue /> -->
  <ContadorVue/>
</template>

<script>
// import SintaxesVue from './components/SintaxesVue.vue'
import ContadorVue from './components/ContadorVue.vue'

export default {
  name: 'App',
  components: {
    // SintaxesVue
    ContadorVue
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
