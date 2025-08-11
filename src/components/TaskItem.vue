<script setup>

const props = defineProps(['zad'])
const emit = defineEmits(['gotowe','usun'])

function gotowe() {
  emit('gotowe' , props.zad.id)
}
function usun() {
  emit('usun', props.zad.id)
}
</script>


<template>
<div >{{zad.tresc}}</div> <button @click="gotowe">gotowe</button><button @click="usun">usun</button>
</template>


<style scoped>

</style>