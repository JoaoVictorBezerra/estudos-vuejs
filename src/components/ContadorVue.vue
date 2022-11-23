<!-- Utilizando setup como atributo do script -->
<script setup>
import { nextTick, reactive } from 'vue';
const state = reactive({ contador: 0 })
async function aumentar() {
    state.contador++
    console.log(document.getElementById('contador').textContent) // Sem a atualização em tempo real do DOM
    await nextTick() // Para atualizar o DOM em tempo real
    console.log(document.getElementById('contador').textContent) // Atualizando o DOM em tempo real
}
function diminuir() {
    state.contador--
    nextTick(() => {
        console.log(document.getElementById('contador').textContent) // Atualizando o DOM em tempo real
    })
}
</script>
<template>
    <p id="contador">Contador: {{ state.contador }}</p>
    <button @click="aumentar()">&#88;</button>
    <button @click="diminuir()">&#45;</button>
</template>

<!-- Utilizando a função setup e return -->
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

<!-- Utilizando o método ref -->
<!-- <script setup>
	import { ref } from 'vue'
	const contador = ref(0); // o ref indica que a variável é reativa
	
	function aumentarContador() {
		this.contador++
	}

</script>
<template>
	<p>Contador: {{ contador }}</p>
<button @click="aumentarContador()"></button>
</template> -->