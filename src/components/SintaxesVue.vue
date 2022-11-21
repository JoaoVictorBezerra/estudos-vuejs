<template>
  <h1>Estudos vue.js</h1>
  <hr><!-- Divisor de conteúdo -->
  <h2>Utilizando Data binding</h2>
  <div :id="state.objectOfAttrs.id" :class="state.objectOfAttrs.class">Atribuindo atributos de um objeto</div>
  <div v-bind="state.objectOfAttrs">Atribuindo varios valores de um objeto de uma vez só</div>
  <hr><!-- Divisor de conteúdo -->
  <h2>Utilizando javascript com interpolação</h2>
  <p>{{ state.attrsJs.ok ? 'Verdadeiro' : 'Falso' }}</p>
  <p>{{ state.attrsJs.message.split('').reverse().join('') }}</p>
  <p>{{ state.attrsJs.message.concat(" Victor") }}</p>
  <div :id="`list-${state.id}`">Número declarado do id: {{ state.id }}</div>
  <hr><!-- Divisor de conteúdo -->
  <h2>Somente expressões</h2>
  <p v-if="state.texto.seen">Agora você pode me enxergar</p>
  <button @click="esconder()">{{ state.texto.mensagem }}</button>
  <hr><!-- Divisor de conteúdo -->
  <h2>Argumentos Estáticos</h2>

</template>
<script>
import { reactive } from 'vue';
export default {

  setup() {
    const state = reactive({ // Essa variável irá retornar todos os componentes reativos do nosso template.
      objectOfAttrs: {
        id: 'container',
        class: 'wrapper'
      },
      attrsJs: {
        ok: false,
        message: 'João'
      },
      id: 5,
      disabled: {
        isButtonDisabled: false
      },
      texto: {
        seen: true, // Se mudar para false o paragráfo irá sumir
        mensagem: 'Esconder'
      }
    })
    function esconder() {
      state.texto.seen = !state.texto.seen
      if (state.texto.seen) {
        state.texto.mensagem = 'Esconder'
      } else {
        state.texto.mensagem = 'Mostrar'
      }
    }
    return { // retornar aqui tudo que tiver dentro de uma variável reativa.
      state,
      esconder,
    }
  }
}
</script>
