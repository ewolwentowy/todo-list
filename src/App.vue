<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from 'vue'
import TaskList from "./components/TaskList.vue";

const tabZadania = ref([])

function dodajZadanieDoTablicy(dodaj) {
  const noweZadanie = {
    id: tabZadania.value.length + 1,
    trescZad: dodaj,
    gotowe: false
  }
  tabZadania.value.push(noweZadanie)
}

function gotoweZadanie(id) {
  const zad = tabZadania.value.find(zad => zad.id === id)
  zad.gotowe = !zad.gotowe
}

function usunZadanie(id) {
  tabZadania.value = tabZadania.value.filter(zad => zad.id !== id)
}


</script>

<template>
  <task-form @dodaj="dodajZadanieDoTablicy"/>
  <task-list :tabZadania="tabZadania"
             @gotowe="gotoweZadanie"
             @usun="usunZadanie"
  />
</template>

<style scoped>

</style>
