<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from 'vue'
import TaskList from "./components/TaskList.vue";

const tablicaZadan = ref([])

function dodajDoTablicy(przekaz) {
  const obj = {
    id: tablicaZadan.value.length + 1,
    tresc: przekaz,
    gotowe: false
  }
  tablicaZadan.value.push(obj)
}

function zadanieGotowe(id) {
const zadanie = tablicaZadan.value.find(zadanie => zadanie.id === id)
  zadanie.gotowe = !zadanie.gotowe
}

function zadanieUsun(id) {
tablicaZadan.value = tablicaZadan.value.filter(zadanie => zadanie.id !== id)
}

</script>

<template>
  <task-form @przekaz="dodajDoTablicy"/>
  <task-list :tablicaZadan="tablicaZadan"
             @gotowe="zadanieGotowe"
             @usun="zadanieUsun"
  />

</template>

<style scoped>

</style>
