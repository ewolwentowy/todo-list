<script setup>
import TaskItem from "./TaskItem.vue";
const props = defineProps(['tablicaZadan'])

</script>

<template>

  <ul>
    <li v-for="zad in tablicaZadan" :key="zad.id">
      <task-item :tablicaZadan="tablicaZadan"/>
    </li>
  </ul>

</template>













<style scoped>

</style>