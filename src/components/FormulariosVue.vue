<script setup>
import { ref } from 'vue';

let message = ref('')

let checked = ref(false)

let checkedNames = ref([])

let picked = ref('')

let selected = ref('')

let _selected = ref([])
let toggle = ref(true)
</script>

<template>
    <h1>Formulários</h1>
    <hr>
    <h2>Interpolação com databinding</h2>
    <p>A mensagem é: {{ message }}</p>
    <input v-model="message" placeholder="edit me">
    <hr>
    <h2>Checkbox</h2>
    <input type="checkbox" id="checkbox" v-model="checked">
    <label for="checkbox">{{ checked }}</label>
    <hr>
    <h2>Checkbox com array</h2>
    <p>Nomes Verificados: {{ checkedNames }}</p>

    <input type="checkbox" id="jason" value="Jason" v-model="checkedNames">
    <label for="jason">Jason</label>

    <input type="checkbox" id="rocky" value="Rocky Balboa" v-model="checkedNames">
    <label for="rocky">Rocky Balboa</label>
    <hr>
    <h2>Radio</h2>
    <p>Escolhido: {{ picked }}</p>
    <input type="radio" id="one" value="One" v-model="picked">
    <label for="one">One</label>
    <input type="radio" id="two" value="Two" v-model="picked">
    <label for="two">Two</label>
    <hr>
    <h2>Seleção</h2>
    <div>Selecionado: {{ selected }}</div>
    <select v-model="selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
    <hr>
    <h2>Seleção multipla com array</h2>
    <div>Selecionado: {{ _selected }}</div>
    <select v-model="_selected" multiple>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
    <hr>
    <h2>Caixa de seleção</h2>
    <input type="checkbox" v-model="toggle" true-value="yes" false-value="no">
    <!-- 
        Os atributos true-valuee false-valuenão afetam o valueatributo de entrada, 
        porque os navegadores não incluem caixas desmarcadas nos envios de formulários. 
        Para garantir que um dos dois valores seja enviado em um formulário (por exemplo, 
        "sim" ou "não"), use as entradas de rádio.
    -->
    <input type="checkbox" v-model="toggle" :true-value="dynamicTrueValue" :false-value="dynamicFalseValue" />>
</template>