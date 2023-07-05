<script setup>
import { reactive } from 'vue';

const title = "First VueJS Calculator";

const state = reactive(
  {
    number1: '',
    number2: '',
  }
);

function result(){
  return parseInt(state.number2) + parseInt(state.number1);
}

function insertNumber1(event){
  state.number1 = event.target.value
}

function insertNumber2(event){
  state.number2 = event.target.value
}

function sum(event) {

}
</script>

<template>
  <header>
    <h1> {{ title }}</h1>
  </header>
  <main>
    <p>{{ state.number1 }}</p> <br/>
    <input type="number" @keyup="insertNumber1">
    <select>
      <option value="+"> + </option>
      <option value="-"> - </option>
      <option value="*"> * </option>
      <option value="/"> / </option>
    </select>
    <p>{{ state.number2 }}</p> <br/>
    <input type="number" @keyup="insertNumber2">
    <p v-if="state.number1 && state.number2">The result is {{ result() }}</p>
  </main>
</template>

<style scoped>

</style>
