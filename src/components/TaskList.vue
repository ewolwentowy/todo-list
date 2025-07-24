<script setup>
import TaskItem from "./TaskItem.vue";

const props = defineProps(['arrTodo', 'handleToggleDone', 'handleDeleteTask'])
const emit = defineEmits(['toggleDone', 'deleteTask'])
</script>

<template>
  <h3>Lista zadań</h3>
  <div class="task-list">
    <ul>
      <li v-for="task in arrTodo" :key="task.id">
        <TaskItem :task="task"
                  @toggleDone="() => $emit('toggleDone', task.id)"
                  @deleteTask="() => $emit('deleteTask', task.id)"
        />
      </li>
    </ul>

  </div>

</template>

<style scoped>
h3{
  font-size: 30px;
text-shadow: 1px 1px 2px black;
}
div{
  margin: 10px;

}
ul{
  list-style-type: none;
}

.task-list {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;

}

</style>