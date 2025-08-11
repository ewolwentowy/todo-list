<script setup>

import TaskItem from "./TaskItem.vue";

 const props = defineProps(['tablicaZadan'])
 const emit = defineEmits(['gotowe', 'usun'])


</script>

<template>
<h2>Lista zadań</h2>
  <ul>
    <li v-for="zadanie in tablicaZadan" :key="zadanie.id">
      <task-item :zadanie="zadanie"
      v-on:gotowe="$emit('gotowe', zadanie.id)"
      v-on:usun="$emit('usun', zadanie.id)"/>
    </li>
  </ul>

</template>













<style scoped>

</style>