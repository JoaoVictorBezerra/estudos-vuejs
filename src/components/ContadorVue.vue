<script setup>
import { reactive } from 'vue';
const state = reactive({ contador: 0 })
function aumentar() {
    state.contador++
}
function diminuir() {
    state.contador--
}


</script>
<template>
    <p>Contador: {{ state.contador }}</p>
    <button @click="aumentar()">&#88;</button>
    <button @click="diminuir()">&#45;</button>
</template>
<!-- <script>
import { reactive } from 'vue';
export default {

    setup() {
        const state = reactive({ contador: 0 })
        function aumentar() {
            state.contador++
        }
        function diminuir() {
            state.contador--
        }
        return {
            state,
            aumentar,
            diminuir
        }
    }
}
</script> -->