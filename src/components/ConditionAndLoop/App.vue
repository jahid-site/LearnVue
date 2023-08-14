<script setup>
import { ref } from 'vue'

const show = ref(true)

const list = ref([1, 2, 3, 4, 5])
</script>

<template>
    <button @click='show = !show'>Toggle Show</button>
    <button @click='list.push(list.length + 1)'>Push Numbe</button>
    <button @click='list.pop()'>Pop Number</button>
    <button @click='list.reverse()'>Reverse List</button>
    
    <lu v-if='show && list.length'>
        <li v-for='item of list'>{{ item }}</li>
    </lu>
    <p v-else-if='list.length'>List is not empty but hidden</p>
    <p v-else>List is empty</p>
</template>

<style>
    button {
        font-size: 16px;
        padding: 5px;
        margin: 5px;
        margin-left: 10px;
        border: 1px solid #CCCCCC;
        background: #E1DCDC;
    }
</style>
