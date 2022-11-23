<script setup>
import { ref, nextTick } from 'vue';
let awesome = ref(true)
function change() {
    this.awesome = !this.awesome
    nextTick(() => {
        console.log(awesome.value)
    })
}
</script>

<template>
    <h1 v-if="awesome">João Victor is awesome!</h1>
    <h1 v-else>Oh no</h1>
    <button @click="change()">Change</button>
</template>