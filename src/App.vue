<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from "vue";
import TaskList from "./components/TaskList.vue";


const tablicaZadan = ref([{
  id: Number,
  tresc: String,
  status: Boolean
}])

function przejmij(dodaj) {
  const obj = {
    id: tablicaZadan.value.length + 1,
    tresc: dodaj,
    status: false
  }
  tablicaZadan.value.push(obj)
  console.log(tablicaZadan.value)
}

function gotoweZad(id) {
  tablicaZadan.value.forEach(zad => {
    if (zad.id === id) {
      zad.status = true
    }
  })
}

function usunZad(id) {
  tablicaZadan.value = tablicaZadan.value.filter(zad => zad.id !== id)

}




</script>

<template>
<task-form @dodaj="przejmij"/>
  <task-list :tablicaZadan="tablicaZadan"  @gotowe="gotoweZad" @usun="usunZad"/>

</template>

<style scoped>

</style>
