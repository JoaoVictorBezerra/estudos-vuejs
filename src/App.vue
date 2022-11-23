<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <SintaxesVue /> -->
  <!-- <ContadorVue/> -->
  <!-- <EstilizacaoVue /> -->
  <RenderizacaoLista />
</template>

<script>
// import SintaxesVue from './components/SintaxesVue.vue'
// import ContadorVue from './components/ContadorVue.vue'
// import EstilizacaoVue from './components/EstilizacaoVue.vue';
// import RenderizacaoCondicional from './components/RenderizacaoCondicional.vue';
  import RenderizacaoLista from './components/RenderizacaoLista.vue'
export default {
  name: 'App',
  components: {
    // EstilizacaoVue
    RenderizacaoLista

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
