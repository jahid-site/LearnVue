<script setup>
import { marked } from 'marked'
import { debounce } from 'lodash-es'
import { ref, computed } from 'vue'

const input = ref('# hello')

const output = computed(() => marked(input.value))

const update = debounce((e)=>{
    input.value = e.target.value
}, 100)

</script>

<template>
    <div class="editor">
        <textarea class="input" :value='input' @input='update'></textarea>
        <div class="update" v-html='output'> </div>
    </div>
</template>
<style>
    body {
        margin: 0px;
    }
    
    .editor {
        height: 100vh;
        display: flex;
    }
    
    .input, .output {
        width: 50%;
        height: 100%;
        padding: 0 8px;
        overflow: auto;
        box-sizing: border-box;
    }
    
    .input {
        border: none;
        border-right: 1px solid #ccc;
        resize: none;
        outline: none;
        background-color: #F6F6F6;
        font-size: 14px;
        font-family: 'Monaco', courier, monospace;
        padding: 20px;
    }
    code {
        color: #f66;
    }
</style>

