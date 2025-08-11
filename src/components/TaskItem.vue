<script setup>

const props = defineProps(['zad'])

const emit = defineEmits(['gotowe', 'usun'])

function gotowe() {
  emit('gotowe', props.zad.id)
}

function usun() {
  emit('usun', props.zad.id)
}

</script>


<template>

  <div :class="{gotowe: zad.gotowe}">
    {{ zad.trescZad }}
    <button @click="gotowe">gotowe</button>
    <button @click="usun">usun</button>
  </div>

</template>


<style scoped>
.gotowe {
  text-decoration: line-through;
}


</style>