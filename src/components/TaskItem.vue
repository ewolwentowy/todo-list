<script setup >

const   props  = defineProps(['task'])
const emit = defineEmits(['toggleDone', 'deleteTask'])

function toggleDone() {
emit('toggleDone', props.task.id)
}

function deleteTask() {
  emit('deleteTask', props.task.id)
}

</script>


<template>
<div class="task-item">
  <span v-bind:class="{done: props.task.done}">
{{task.title}}
  </span>
  <button @click="toggleDone">Gotowe</button>
  <button @click="deleteTask">Usuń</button>
</div>
</template>


<style scoped>
.done{
  text-decoration-line: line-through;
  color: gray;
}
</style>