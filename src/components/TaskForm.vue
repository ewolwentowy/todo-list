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
    <input type="text" v-model="newTask" placeholder="Dodaj zadanie" @keyup.enter="sendTask"/>
    <button @click="sendTask" >Dodaj</button>
  </div>
  <label for='' >{{ info }}</label>
</template>

<style scoped>

</style>