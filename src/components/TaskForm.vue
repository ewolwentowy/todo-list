<script setup>
import {ref} from 'vue'

const emit = defineEmits(['dodaj'])
const zadanie = ref('')
const info = ref('')

function przekazZadanie() {
  if(zadanie.value !== '') {
    emit('dodaj', zadanie.value)
    zadanie.value = ''
    info.value = ''
  } else {
    info.value = 'podaj treść zadania'

  }
}

</script>

<template>
  <input type="text" v-model="zadanie" @keyup.enter="przekazZadanie" autofocus placeholder="dodaj zadanie">
  <button @click="przekazZadanie">dodaj</button>
  <br>
  <label>{{ info }}</label>
</template>


<style scoped>

</style>