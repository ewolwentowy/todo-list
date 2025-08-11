<script setup>

import TaskItem from "./TaskItem.vue";

const props = defineProps(['tabZadania'])
const emit = defineEmits(['gotowe', 'usun'])


</script>

<template>

  <ul>
    <li v-for="zad in tabZadania" :key="zad.id">
      <task-item :zad="zad"
                 @gotowe="$emit('gotowe', zad.id)"
                 @usun="$emit('usun', zad.id)"
      />
    </li>
  </ul>


</template>


<style scoped>

</style>