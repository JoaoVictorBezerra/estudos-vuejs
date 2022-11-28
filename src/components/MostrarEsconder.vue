<script setup>
import { reactive, ref } from 'vue';


const botao = ref({ status: true, btnTitle: 'Esconder' })

function ocultarTxt() {
    // console.log(botao)
    botao.value.status = !botao.value.status
    if (botao.value.btnTitle != true) {
        botao.value.btnTitle = 'Mostrar'
    }
    else {
        botao.value.btnTitle = 'Esconder'
    }
}
const Active = ref(true)
const isActive = reactive({
    vermelho: Active
})

function mudarClasse() {
    Active.value = !Active.value
}

const state = { count: 0 }

const aumentar = () => {
    state.count++
    console.log(state.count)
}

</script>

<template>

    <p :class="isActive" v-if="botao.status">Clique no botão para esconder o texto</p>
    <button v-on:click="ocultarTxt()">{{ botao.btnTitle }}</button>
    <button v-on:click="mudarClasse()">{{ botao.btnTitle }}</button>

    <p>{{ state.count }}</p>
    <button @click="aumentar">Aumentar</button>

</template>

<style>
.vermelho {
    color: red;
}
</style>