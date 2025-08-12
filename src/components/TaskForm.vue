<script setup>
import { ref } from 'vue'

const emit = defineEmits(['przekaz'])
const zadanie = ref('')

function przekazZadanie(){
  emit('przekaz', zadanie.value)
zadanie.value = ''
}

</script>

<template>
<input type="text" v-model="zadanie" placeholder="dodaj zadanie" autofocus @keyup.enter="przekazZadanie"/>
  <button @click="przekazZadanie" > dodaj</button>
</template>


<style scoped>

</style>