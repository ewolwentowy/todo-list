<script setup>
import TaskItem from "./TaskItem.vue";

const props = defineProps(['arrTodo'])
const emit = defineEmits(['toggleDone', 'deleteTask'])
</script>

<template>
  <h3>Lista zadań</h3>
  <div class="task-list">
    <ul>
      <li v-for="task in arrTodo" :key="task.id">
        <TaskItem :task="task"
                 @toggleDone= 'handleToggleDone'
                  @deleteTask= 'handleDeleteTask'
        />
      </li>
    </ul>

  </div>

</template>

<style scoped>

</style>