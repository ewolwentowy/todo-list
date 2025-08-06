<script setup>
import {ref} from "vue";

const emit = defineEmits(['dodaj']);

const dodaj = () => {
  emit('dodaj', zadanie.value);
  console.log(zadanie.value);
}
const zadanie = ref("");


function kasuj() {
  zadanie.value = "";
}



</script>

<template>
  <input v-model="zadanie" type="text" autofocus>
  <button @click="dodaj">Add</button>
  <button @click='kasuj' >Clear</button>
</template>












<style scoped>

</style>