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

  <div>
    <span v-bind:class="{gotowe: zadanie.gotowe}">

    {{ zadanie.tresc }}
    </span>
    <button @click="gotowe">gotowe</button>
    <button @click="usun">usuń</button>
  </div>


</template>


<style scoped>
.gotowe {
  text-decoration: line-through;
}

</style>