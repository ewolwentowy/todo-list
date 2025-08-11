<script setup>
import { ref } from 'vue'
const emit = defineEmits(['dodaj'])
const zadanie = ref('')

function dodaj() {
  emit('dodaj', zadanie.value)
console.log(zadanie);
}
</script>



<template>
<input type="text" v-model="zadanie">
  <button @click="dodaj" >dodaj</button>

</template>









<style scoped>

</style>