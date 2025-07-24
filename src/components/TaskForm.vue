<script setup>
import {ref} from "vue";

const emit = defineEmits(['addTask'])
const newTask = ref('')
const info = ref('')


function sendTask() {
  if (newTask.value.length > 0) {
    emit('addTask', newTask.value)
    newTask.value = ''
    info.value = ''

  } else {
    info.value = 'Wpisz treść zadania!'

  }
}

</script>

<template>
  <div>
    <input type="text" v-model="newTask" placeholder="Dodaj zadanie" @keyup.enter="sendTask" autofocus maxlength="35"/>
    <button @click="sendTask" v-bind:disabled="newTask.length === 0">Dodaj</button>
  </div>
  <label >{{ info }}</label>
</template>

<style scoped>

button{
  background-color: rgba(255, 110, 196, 0.78);
  transition: background-color 0.3s;
}
button:hover{
  background-color: rgb(255, 201, 252);
  transform: scale(1.05);
}

button:disabled {
  cursor: default;
  border: 1px solid gray;
  background-color: #dfdfdf;
  transform: scale(1);
}
input{
  height: 35px;
  padding: 10px;
  box-shadow: 5px 5px 5px 0 rgba(0, 0, 0, 0.2);
}
label{
  display: block;
  height: 30px;
  color: #d22222;
}

</style>