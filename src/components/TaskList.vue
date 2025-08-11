<script setup>
import TaskItem from "./TaskItem.vue";

const props = defineProps(['tablicaZadan', 'gotowe' , 'usun'])
const emit = defineEmits(['gotowe','usun'])
function gotowe() {
  emit('gotowe', props.zad.id)
}
function usun() {
  emit('usun',props.zad.id)
}
</script>

<template>
  <ul >
    <li v-for="zad in tablicaZadan" :key="zad.id">
      <task-item :zad="zad"
      @gotowe="$emit('gotowe', zad.id)"
      @usun="$emit('usun', zad.id)"/>
    </li>
  </ul>


</template>













<style scoped>

</style>