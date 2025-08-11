<script setup>

const props = defineProps(['zadanie'])
const emit = defineEmits(['gotowe', 'usun'])

function gotowe() {
  emit('gotowe', props.zadanie.id)
}

function usun() {
  emit('usun', props.zadanie.id)
}

</script>


<template>

<div v-bind:class="{zrobione: zadanie.status}">
  {{zadanie.tresc}}
</div>
  <div>
    <button @click="gotowe">gotowe</button>
    <button @click="usun">usun</button>
  </div>
</template>


<style scoped>
.zrobione {
  text-decoration: line-through;
}
</style>