<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from 'vue'
import TaskList from "./components/TaskList.vue";

const tablicaZadan = ref([])

function dodajZadanie(przekaz){
  const objZad = {
    id: tablicaZadan.value.length + 1,
    tekst: przekaz,
    gotowe: false
  }
  tablicaZadan.value.push(objZad)
}

function gotoweZadanie(id){
  const zad = tablicaZadan.value.find(zad => zad.id === id)
  zad.gotowe = !zad.gotowe
}

function usunZadanie(id){
  tablicaZadan.value = tablicaZadan.value.filter(zad => zad.id !== id)
}



</script>

<template>
  <task-form @przekaz="dodajZadanie"/>
<task-list :tablicaZadan="tablicaZadan"
                    @gotowe="gotoweZadanie"
           @usun="usunZadanie"

/>
</template>

<style scoped>

</style>
