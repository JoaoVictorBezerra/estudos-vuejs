<script setup>
import { reactive, ref, computed } from 'vue';
/*============================== Método utilizando o class binding ==============================*/
import ComponentStyle from './ComponenteStyle.vue'


/*============================== Método utilizando o class binding ==============================*/
const isActive = ref(true)
const hasError = ref(true)
const noError = ref(false)
/*============================================= Fim ============================================*/

/*============================== Método com propriedade computada ==============================*/
const error = ref(null)
/*============================================= Fim ============================================*/

/*============================== Método utilizando o class binding ==============================*/
const objClasseA = reactive({
    grande: isActive //quando o isActive for true ele vai setar a classe grande onde for chamado o objClasseA
})
const objClasseB = reactive({
    error: hasError //quando o isActive for true ele vai setar a classe grande onde for chamado o objClasse
})
const objClasseC = reactive({
    error: hasError,
    grande: isActive
})
const objClassD = reactive({
    azul: !noError.value
})
/*============================================= Fim ============================================*/

/*============================== Método com propriedade computada ==============================*/
const classObj = computed(() => ({
    grande: isActive.value && !error.value, // retornará se isActive tiver algum valor e se error for nulo, caso contrário não retorna
    error: error.value && error.value.type === 'fatal'
}))
/*============================================= Fim ============================================*/

/*============================== Método com Arrays ==============================*/
const classeAtiva = ref('grande')
const classeErro = ref('error')
/*============================================= Fim ============================================*/


/*============================== Método com estilos inline ==============================*/
const corAtiva = ref('aqua')
const tamanhoTexto = ref(30)

const estilizacao = reactive({
    color: 'aqua',
    'font-size': '30px'
})
const underline = reactive({
    'text-decoration': 'underline'
})
/*============================================= Fim ============================================*/

</script>
<template>

    <!-- 
        ============================== Método utilizando o class binding ==============================
        Se isActive tiver o valor de 'true', então atribuirá o valor 'active' no elemento <p></p>. 
        Se o hasError tiver o valor de 'true', então atribuirá o valor 'text-danger' na classe do <p></p> 
    -->
    <h1>Class Binding</h1>
    <p class="static" :class="{ 'grande': isActive, 'error': hasError }">Hello World!</p>
    <p :class="objClasseA">Aqui atribuirá a classe .grande</p>
    <p :class="objClasseB">Aqui atribuirá a classe .error</p>
    <p :class="objClasseC">Aqui atribuirá a classe .error e a classe .grande</p>
    <!-- ============================================= Fim ============================================ -->

    <hr>
    
    <!-- ============================== Método com propriedade computada ============================== -->
    <h1>Computed Properties</h1>
    <p :class="classObj">Esse método é com o Propriedade Computada.</p>
    <!-- ============================================= Fim ============================================ -->
    
    <hr>
    
    <!-- ============================== Método com Arrays ============================== -->
    <h1>Utilizando array no Class Binding</h1>
    <p :class="[classeAtiva, classeErro]">Utilizando o class binding com arrays</p>
    <!-- ============================================= Fim ============================================ -->
    
    <hr>
    
    <!-- ============================== Método com Arrays ============================== -->
    <h1>Utilizando if ternário no Class Binding</h1>
    <!-- 
        Enqunato a var isActive for verdadeira ele irá atribuir o valor da classe para o valor da classeAtiva 
        e se for falso não retorna nada
     -->
    <p :class="isActive ? classeAtiva : ''">Utilizando o operador ternário</p>
    <p :class="[isActive ? classeAtiva : '', classeErro]">Utilizando o operador ternário como um array</p>
    <!-- caso tenhamos varias classes condicionais, devemos utilizar '{ }'  -->
    <p v-bind:class="[{ azul: isActive, sublinhado: !noError }, classeAtiva]">Várias condicionais</p>
    <!-- ============================================= Fim ============================================ -->
    
    <hr>

    <!-- ============================== Método componentizado ============================== -->
    <h1>Utilizando componentes</h1>
    <ComponentStyle :class="objClassD" />
    <!-- Caso seja um condicional, também podemos utilizar dessa forma -->
    <ComponentStyle :class="{ sublinhado: !noError }" />
    <!-- ============================================= Fim ============================================ -->
    
    <hr>

    <!-- ============================== Utilizando Estilos inline ============================== -->
    <p :style="{color: corAtiva, 'font-size': tamanhoTexto + 'px'}">Estilos inline</p>
    <!-- Mas é preferivel simplificar com: -->
    <p :style="estilizacao">Método preferível</p>
    <!-- Também podemos vincular arrays -->
    <p :style="[estilizacao, underline]">Estilizando com array</p>
    <!-- ============================================= Fim ============================================ -->
</template>
<style>
.grande {
    font-size: 22px;
}

.sublinhado {
    text-decoration: underline;
}

.azul {
    color: blue;
}

.error {
    color: red;
    text-decoration: line-through;
}
</style>