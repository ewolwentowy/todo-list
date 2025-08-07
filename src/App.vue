<script setup>
import {ref} from 'vue'
import TaskForm from './components/TaskForm.vue'
import TaskItem from "./components/TaskItem.vue";

const tablicaZadan = ref([])

function obslugaForm(zadanie) {
  tablicaZadan.value.push(zadanie)
  console.log(tablicaZadan.value)
}

function usuwanie(index) {
  tablicaZadan.value.splice(index, 1)
}

function odznacone(index) {

}

</script>

<template>
  <task-form @dodaj="obslugaForm"/>
  <task-item :zad='tablicaZadan'
             @usun="usuwanie"
             @gotowe="odznacone"
  />
</template>

<style scoped>

</style>
