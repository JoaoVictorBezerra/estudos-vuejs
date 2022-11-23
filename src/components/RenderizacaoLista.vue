<script setup>
import { computed } from '@vue/reactivity';
import { reactive, ref } from 'vue';

/*============================ v-for ============================*/
const pessoas = ref([{ name: 'João Victor' }, { name: 'Diogo Andrade' }, { name: 'Daina Elen' }, { name: 'Giovanna Victoria' }])
console.log(pessoas.value)

const items = ref([{ nome: 'Pão' }, { nome: 'Macarrão' }, { nome: 'Refrigerante' }, { nome: 'Açúcar' }])
/*============================ FIM ============================*/

/*======================== Equivalente ao v-for em javascript ========================*/
const letters = ['A', 'B', 'C']
letters.forEach((index) => {
    console.log(index, index.letter)
})
/*============================ FIM ============================*/

/*======================== Utilizando v-for com Objetos ========================*/
const objeto = reactive({
    titulo: 'O Monge e o executivo',
    autor: 'James C. Hunter',
    publicado: 2015
})

/*======================== v-for com intervalo ========================*/
const intervalo = ref([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
const numeroEncontrado = computed(() => {
    return intervalo.value.filter((n) => n == 8)
})

/*============================ FIM ============================*/

/*============================ FIM ============================*/
/*======================== v-if e v-for no mesmo nó ========================*/
const todo = reactive({
    taskOne: {
        id: 1,
        name: 'Workout',
        isDone: true
    },
    taskTwo: {
        id: 2,
        name: 'Swim',
        isDone: false
    },
    taskThree: {
        id: 3,
        name: 'Walk',
        isDone: false
    }
})

/*============================ FIM ============================*/
</script>

<template>
    <!-- ================================ v-for ================================ -->
    <ul>
        <li v-for="indexador of pessoas" :key="indexador">
            {{ indexador.name }}
        </li>
    </ul>
    <hr>
    <ul>
        <li v-for="(item, index) in items" :key="item">{{ index }} - {{ item.nome }}</li>
    </ul>
    <hr>
    <!-- ================================ final ================================ -->

    <!-- <ul>
        <li v-for="item in items" :key="item">
            <span v-for="childItem in item.children" :key="childItem">
                {{ item.message }} {{ childItem }}
            </span>
        </li>
    </ul> -->
    <!-- ================================ v-for com objeto ================================ -->
    <ul>
        <li v-for="(valor) in objeto" :key="valor"> {{ valor }}</li>
    </ul>
    <ul>
        <li v-for="(valor, index) of objeto" :key="index">
            {{ index }}: {{ valor }}
        </li>
    </ul>
    <ul>
        <li v-for="(valor, index, key) of objeto" :key="key">
            {{ key }}. {{ index }}: {{ valor }}
        </li>
    </ul>
    <hr>
    <!-- ================================ Fim ================================ -->

    <!-- ================================ v-for com intervalo ================================ -->
    <span v-for="n in intervalo" :key="n">{{ n }}</span>
    <ul>
        <li v-for="n in 5" :key="n">{{ n }}</li>
    </ul>
    <hr>
    <!-- ================================ Fim ================================ -->

    <!-- ================================ v-for com v-if no mesmo nó ================================ -->
    <ul v-if="todo.taskOne.isDone != false && todo.taskTwo.isDone != false">
        <!-- Veja, caso alterarmos o valor de isDone da taskTwo para true ele volta a exibir a lista-->
        <li v-for="index in todo" :key="index.id"> {{ index.name }}</li>
    </ul>
    <!-- ================================ Fim ================================ -->
    <!-- ================================ Utilizando filter ================================ -->
    <ul>
        <li v-for="n in numeroEncontrado" :key="n"> {{ n }}</li>
    </ul>
    <!-- ================================ Fim ================================ -->

</template>

<style>
ul {
    list-style: none;
}
</style>