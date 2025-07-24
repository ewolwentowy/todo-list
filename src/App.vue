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
  <div class="app">
    <TaskForm @addTask="handleResponse"/>
    <TaskList :arrTodo="arrTodo"
            @toggleDone="handleToggleDone"
            @deleteTask="handleDeleteTask"/>
  </div>
</template>

<style scoped>
h1{

  display: flex;
  text-align: center;
  justify-content: center;
margin: 20px;

}
app {
  display: flex;
  justify-content: center;
  align-items: center;


}
</style>
