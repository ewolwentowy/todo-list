<script setup>
import { ref } from 'vue'
const props = defineProps(['zad'])

function usun(index) {
emit('usun', index)
}

function gotowe(index) {
  emit('gotowe', index)
}

</script>


<template>

  <ul>
    <li v-for="(zadanie, index) in props.zad" :key="index">
      {{ zadanie }} <button @click="gotowe"> gotowe</button> <button @click="usun"> usun</button>
    </li>
  </ul>


</template>


<style scoped>

</style>