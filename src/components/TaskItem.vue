<script setup>


const props = defineProps(['tablicaZadan' ])
const emit = defineEmits(['usun', 'gotowe'])

function usun() {
  emit('usun', props.tablicaZadan.id)
}
function gotowe() {
  emit('gotowe', props.tablicaZadan.id)
}

</script>


<template>

  <div>{{zad.tresc}}</div>
  <button @click="gotowe">gotowe</button>
  <button @click="usun">usun</button>


</template>


<style scoped>

</style>