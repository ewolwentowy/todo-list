<script setup>

const handleResponse = (addTask) => {
  arrTodo.push(addTask)
  console.log(arrTodo)
}
const arrTodo = [{
  id: 1,
  title: "Zadanie 1",
  done: false
}]

import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";
</script>

<template>
<h1>Lista zadań</h1>
  <TaskForm />
  <TaskList />
</template>

<style scoped>

</style>
