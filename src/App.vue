<script setup>
import { reactive } from 'vue';
const title = "First VueJS Calculator";
const state = reactive(
  {
    number1: "",
    number2: "",
    operator:""
  }
);

function result() {
if (state.operator === "sum") {
return sum()
} else if (state.operator === "minus") {
return minus()
}else if (state.operator === "multi") {
return multi()
}else if (state.operator === "divide") {
return divide()
} else (state.operator === '');
return ""
}


function insertNumber1(event){
  state.number1 = event.target.value
}
function insertNumber2(event){
  state.number2 = event.target.value
}

function sum (){
   return parseInt(state.number1) + parseInt(state.number2)
}
function minus (){
   return state.number1 - state.number2
}
function multi (){
   return state.number1 * state.number2
}
function divide (){
   return state.number1 / state.number2
}

</script>

<template>
  <header>
    <h1> {{ title }}</h1>
  </header>
  <main>
    <p>{{ state.number1 }}</p> <br/>
    <input type="number" @keyup="insertNumber1"> <br/><br/>
    <select v-model="state.operator">
      <option value="sum"> + </option>
      <option value="minus"> - </option>
      <option value="multi"> * </option>
      <option value="divide"> / </option>
    </select>
    <p>{{ state.number2 }}</p> <br/>
    <input type="number" @keyup="insertNumber2">
    <p v-if="state.number1 !== '' && state.number2 !== ''">The result is {{ result() }}</p>
  </main>
</template>

<style scoped>
</style>
