<script setup>
import TaskForm from "./components/TaskForm.vue";
import {ref} from "vue";

const tab = ref([]);


function dodania() {

  tab.push(zadanie.value)
  console.log(tab);
  console.log("dodano");
}
</script>

<template>
<task-form @dodaj="dodania"/>
</template>

<style scoped>

</style>
