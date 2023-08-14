<script setup>
import { ref } from 'vue'

const message = ref('Hello World!')

const reverseMessage = () => {
    message.value = message.value.split('').reverse().join('')
}

const notify = () => {
    alert('Navigation was prevent!')
}

</script>
<template>
    <h1> {{ message }}</h1>
    
    <button @click="reverseMessage">Reverse Message</button>
    
    <button @click="message += '!'">Append '!'</button>
    
    <a href="https://vuejs.org" @click.prevent='notify'> A link e.preventDefault() </a>
</template>

<style>
    button, a {
        display: block;
        margin-bottom: 1rem;
    }
</style>