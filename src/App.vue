<script setup>
import {ref} from "vue";
import TaskForm from "./components/TaskForm.vue";
import TaskItem from "./components/TaskItem.vue";

const tablica = ref([])

function dotablicy(zadanie){
  tablica.value.push(zadanie)
console.log(tablica.value)
}

</script>

<template>
<task-form @zad="dotablicy"/>
  <task-item :tablica="tablica" />
</template>

<style scoped>

</style>
