<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from 'vue'
import TaskList from "./components/TaskList.vue";

const tablicaZadan = ref([{
  id: 1,
  tresc: 'zadanie',
  status: false,
}])

function dodajZadanie(przekaz) {
  const obj = {
    id: tablicaZadan.value.length + 1,
    tresc: przekaz,
    status: false,
  }
  tablicaZadan.value.push(obj)
  console.log(tablicaZadan.value);
}
function usunZadanie(id) {
  tablicaZadan.value = tablicaZadan.value.filter(zadanie => zadanie.id !== id)

}
function gotoweZadanie(id) {
  const zadanie = tablicaZadan.value.find(zadanie => zadanie.id === id)
  zadanie.status = !zadanie.status
}

</script>

<template>
  <task-form @przekaz="dodajZadanie"/>
  <task-list :tablicaZadan="tablicaZadan"
             v-on:gotowe="gotoweZadanie"
             v-on:usun="usunZadanie"
  />
</template>

<style scoped>

</style>
