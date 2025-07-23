<script setup>
import TaskForm from "./components/TaskForm.vue";
import TaskList from "./components/TaskList.vue";
import {ref} from "vue";

const handleResponse = (addTask) => {
  const obj = {
    id: arrTodo.value.length + 1,
    title: addTask,
    done: false
  }
  arrTodo.value.push(obj)
  console.log(arrTodo.value)
}
const arrTodo = ref([{
  id: 1,
  title: "Zadanie 1",
  done: false
}])

const handleToggleDone = (id) => {
  const task = arrTodo.value.find(task => task.id === id)
  task.done = !task.done

}
const handleDeleteTask = (id) => {
  arrTodo.value = arrTodo.value.filter(task => task.id !== id)
}
</script>

<template>
  <h1>Lista zadań</h1>
  <TaskForm @addTask="handleResponse"/>
  <TaskList :arrTodo="arrTodo"
            @toggleDone="handleToggleDone"
            @deleteTask="handleDeleteTask"/>
</template>

<style scoped>

</style>
