<script setup >

const props = defineProps(['task'])
const emit = defineEmits(['done', 'deleteTask'])
function done() {
emit('toggleDone', task.id)

}
function deleteTask() {
  emit('deleteTask', task.id)

}

</script>


<template>
<div class="task-item">
  <span>
{{task.title}}
  </span>
  <button @click="done">Gotowe</button>
  <button @click="deleteTask">Usuń</button>
</div>
</template>


<style scoped>

</style>