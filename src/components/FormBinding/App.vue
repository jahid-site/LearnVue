<script setup>
import { ref } from 'vue'

const text = ref('Edit me')
const checked = ref(true)
const checkedNames = ref(['Jahid Hasan'])
const picked = ref('One')
const selected = ref('A')
const multiSelected = ref(['A'])

</script>
<template>
    <h2>Text Input</h2>
    <input type="text" v-model='text' />
    {{ text }}
    
    <h2>Checkbox</h2>
    <input type="checkbox" id="checkbox" v-model='checked' />
    <label for="checkbox">Checked: {{ checked }} </label>
    
    <h2>Multi Checkbox</h2>
    <p>
        <input type="checkbox" id="jahid" value="Jahid Hasan" v-model='checkedNames' />
        <label for="jahid">Jahid Hasan</label>
    </p>
    <p>
        <input type="checkbox" id="nahid" value="Nahid Hasan" v-model='checkedNames' />
        <label for="nahid">Nahid Hasan</label>
    </p>
    <p>
        <input type="checkbox" id="khaled" value="Khaled Mia" v-model='checkedNames' />
        <label for="khaled">Khaled Mia</label>
    </p>
    <p>
        <input type="checkbox" id="arafat" value="Arafat Hasan" v-model='checkedNames' />
        <label for="arafat">Arafat Hasan</label>
    </p>
    <b>Checked Names: </b> 
    <br/>
    <pre> {{ checkedNames }} </pre>
    
    <h2>Radio</h2>
    <p>
        <input type="radio" id="one" value="One" v-model='picked' />
        <label for="one">One</label>
    </p>
    <p>
        <input type="radio" id="two" value="Two" v-model='picked' />
        <label for="two">Two</label>
    </p>
    <p>
        <input type="radio" id="three" value="Three" v-model='picked' />
        <label for="three">Three</label>
    </p>
    
    <span>Picked: {{ picked }}</span>
    
    <h2>Select</h2>
  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ selected }}</span>

  <h2>Multi Select</h2>
  <select v-model="multiSelected" multiple style="width:100px">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ multiSelected }}</span>
  
</template>