<script setup>
import {ref, watch} from "vue";

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
    <input type="text" v-model="newTask" placeholder="Dodaj zadanie" @keyup.enter="sendTask" autofocus/>
    <button @click="sendTask" v-bind:disabled="newTask.length === 0">Dodaj</button>
  </div>
  <label for=''>{{ info }}</label>
</template>

<style scoped>

button:disabled:hover {
  cursor: default;
  pointer-events: none;

}

</style>