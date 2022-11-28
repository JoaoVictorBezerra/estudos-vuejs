<script setup>
import { ref } from 'vue';

/*========================== Utilizando manipuladores embutidos ==========================*/
const contador = ref(0)
/*========================== Fim ==========================*/

/*========================== Utilizando manipuladores de métodos ==========================*/
const nome = ref('João Victor')

function elogiar(event) {
    alert(`Hi, ${nome.value}, você é muito inteligente!`)
    if (event) {
        alert(event.target.tagName) // o event.target.tagName recebe automaticamente o objeto DOM event native que o aciona. podemos ver que quem o aciona é o botão conforme a aplicação nos mostra
    }
}
/*========================== Fim ==========================*/
/*========================== Métodos de chamada em manipuladores embutidos ==========================*/
function escrever(msg) {
    alert(msg)
}
function warn(message, event) {
    // now we have access to the native event
    if (event) {
        event.preventDefault()
    }
    alert(message)
}
/*========================== Fim ==========================*/
</script>
<template>
    <h1>Manipulador de Eventos</h1>
    <!-- ================= Manipuladores embutidos ================= -->
    <h2>Manipuladores Embutidos</h2>
    <button @click="contador++">Contador</button>
    <p>{{ contador }}</p>
    <!-- ============================= Fim ============================= -->
    <hr>
    <!-- ================= Manipuladores de métodos ================= -->
    <h2>Manipuladores de métodos</h2>
    <button v-on:click="elogiar">Elogiar</button>
    <!-- ============================= Fim ============================= -->
    <hr>
    <!-- =================== Manipuladores de métodos =================== -->
    <p>Mostrar Mensagem: Gol do Brasil</p>
    <button @click="escrever('Gol do Brasil')">Mostrar Mensagem</button>
    <p>Mostrar Mensagem: João Victor é muito lindo</p>
    <button @click="escrever('João Victor é muito lindo')">Mostrar Mensagem</button>
    <!-- ============================= Fim ============================= -->
    <hr>
    <!-- ========== Acessando Argumentos de manipuladores embutidos ========== -->
    <!-- 
    Quando precisarmos acessar o evento DOM original em um manipulador embutido,
    passamos para um método $event, 
 -->
    <!-- utilizando $event variável especial -->
    <button @click="warn('Form cannot be submitted yet.', $event)">
        Submit
    </button>
    <!-- Utilizando arrow function inline -->
    <button @click="warn((event) => warn('Form cannot be submitted yet', event))">Submit</button>
    <!-- ============================= Fim ============================= -->
    <hr>
    <!-- ================== Modificadores de evento ================== -->
    <!-- ======= A propagação do evento clique será parada ======= -->
    <a @click.stop="doThis"></a>
    <!-- ======= O evento submit não irá recarregar a página ======= -->
    <form @submit.prevent="onSubmit"></form>
    <!-- ======= modificadores podem ser acorrentados/mesclados ======= -->
    <a @click.stop.prevent="doThat"></a>
    <!-- apenas um gatilho manipulador se o event.target for o elemento em si -->
    <!-- i.e. não de um elemento filho -->
    <div @click.self="doThat">...</div>
    <!-- ============================= Fim ============================= -->
    <hr>
    <!-- ==================== Modificadores de tela ==================== -->
    <input @keyup.enter="Enter">
    <!-- ============================= Fim ============================= -->
    
</template>