<script setup>
import {ref, defineEmits} from "vue";


const emit = defineEmits(['zad'])

const zadanie = ref('')
function przekaz(){
  emit('zad', zadanie.value)
  console.log(zadanie.value)
}

</script>

<template>
<input type="text" v-model="zadanie">
  <button @click="przekaz" >dodaj</button>

</template>












<style scoped>

</style>