<script setup>

import TaskItem from "./TaskItem.vue";

const props = defineProps(['tablicaZadan'])
const emit = defineEmits(['gotowe', 'usun'])
</script>

<template>

  <h2>
    Lista zadań:
  </h2>
  <ul v-if="tablicaZadan.length > 0">
    <li v-for="zadanie in tablicaZadan" :key="zadanie.id">
      <task-item :zadanie="zadanie"
                  @gotowe="$emit('gotowe', $event)"
                 @usun="$emit('usun', $event )"
      />
    </li>
  </ul>
  <label v-else>brak zadań na dzisiaj</label>
</template>


<style scoped>

</style>