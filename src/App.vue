<script setup>
import TaskForm from "./components/TaskForm.vue";
import TaskItem from "./components/TaskItem.vue";
import {ref} from "vue";
import TaskList from "./components/TaskList.vue";

const tablicaZadan = ref([{
  id: Number,
  tresc: String,
  zrobione: Boolean,
}])

function dodajdotablicy(dodaj) {
  const zad = {
    id: tablicaZadan.value.length + 1,
    tresc: dodaj,
    zrobione: false,
  }
  tablicaZadan.value.push(zad)
}
function gotowezadanie(id) {
    tablicaZadan.value.forEach(zadanie => {
      if(zadanie.id === id) {
        zadanie.zrobione = true
      }
    })
}
function usunZadanie(id) {
  tablicaZadan.value.forEach(zadanie => {
    if(zadanie.id === id) {
      tablicaZadan.value.splice(id, 1)
    }
  })
}


</script>

<template>
  <task-form @dodaj="dodajdotablicy"/>
  <task-item  @gotowe="gotowezadanie" @usun="usunZadanie"/>
  <task-list :tablicaZadan="tablicaZadan"/>

</template>

<style scoped>

</style>
