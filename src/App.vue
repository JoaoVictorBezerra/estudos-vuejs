<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <SintaxesVue /> -->
  <!-- <ContadorVue/> -->
  <!-- <EstilizacaoVue /> -->
  <!-- <RenderizacaoLista /> -->
  <!-- <ManipulandoEventos /> -->
  <!-- <MostrarEsconder /> -->
  <!-- <SPT /> -->
  <!-- <ExibeListagem :name="order" /> -->
  <!-- <ExibeListagem :name="user" /> -->
  <!-- <ExibeListagem :name="transaction" /> -->
<FormulariosVue/>
</template>

<script>
// import SintaxesVue from './components/SintaxesVue.vue'
// import ContadorVue from './components/ContadorVue.vue'
// import EstilizacaoVue from './components/EstilizacaoVue.vue';
// import RenderizacaoCondicional from './components/RenderizacaoCondicional.vue';
// import RenderizacaoLista from './components/RenderizacaoLista.vue'
// import ManipulandoEventos from './components/ManipulandoEventos.vue'
// import MostrarEsconder from './components/MostrarEsconder.vue';
// import SPT from './components/SPT.vue';
// import ExibeListagem from './components/ExibeListagem.vue';
import FormulariosVue from './components/FormulariosVue.vue';

export default {
  name: 'App',
  components: {
    // EstilizacaoVue,
    // RenderizacaoLista,
    // ManipulandoEventos,
    // MostrarEsconder,
    // SPT
    // ExibeListagem
    FormulariosVue

  },
  data: () => ({
    order: {
      Title: 'Solicitação',
      Data:
      {
        Making: 'Lorem Ipsum',
        ID: 0,
        Type: 'Lorem Ipsum',
        Status: 'Lorem Ipsum',
        Address: 'Rua Tenente Negrão, 140',
        CardNumber: 123456789,
        Unlock: true,
        UnlockDate: '01/10/2021'
      }
    },
    user: {
      Title: 'Usuário',
      Data:
      {
        Name: 'Lorem Ipsum',
        SocialName: 'Lorem Ipsum',
        RG: 12345678,
        CPF: 987654321,
        Token: 'Lorem Ipsum'
      }
    },
    transaction: {
      Title: 'Transação',
      Data:
      {
        MakingData: 'AAAAAAAAAAA',
        Status: 'BBBBBBBBBBB',
        Value: 'CCCCCCCCCCCC',
        Method: 'DDDDDDDDDDDDD',
        Date: 'EEEEEEEEEEEEEES  '
      }
    }
  })
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
