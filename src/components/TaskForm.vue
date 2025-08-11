<script setup>
import {ref} from 'vue'

const zadanie = ref('')
const emit = defineEmits(['przekaz'])

function przekaz() {
  emit('przekaz', zadanie.value)
  console.log(zadanie.value)
  zadanie.value = ''
}

</script>

<template>
  <input type="text" v-model="zadanie" placeholder="Dodaj zadanie" @keyup.enter="przekaz">
  <button @click="przekaz">dodaj</button>
</template>


<style scoped>

</style>