<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    name: Object
})
// const props = defineProps(['foo'])
// console.log(props.name)
</script>
<template>
    <h1> {{ props.name.Title }}</h1>
    <ul>
        <li v-for="(value, key) in props.name.Data" :key="value"> {{ key }} - {{ value }}</li>
    </ul>
</template>
<style>
ul {
    list-style: none;
}
</style>