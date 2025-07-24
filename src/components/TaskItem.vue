<script setup>

const props = defineProps(['task'])
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
{{ task.title }}
  </span>
    <button class="btn1" @click="toggleDone">Gotowe</button>
    <button class="btn2" @click="deleteTask">Usuń</button>
  </div>
</template>


<style scoped>
.done {
  text-decoration-line: line-through;
  color: gray;
}

.btn1{
  background-color: rgba(0, 128, 0, 0.58);
  transition: background-color 0.3s;
}
.btn2{
  background-color: rgba(255, 0, 0, 0.66);
  transition: background-color 0.25s;
}

button:hover {
  background-color: #e8ccd1;
transform: scale(1.05);


}

.task-item {
  display: flex;
  align-items: center;
  justify-content: end;
  padding: 10px;
  width: 500px;
  border: 1px solid black;
  border-radius: 10px;
  background-color: #f9fafb;
  box-shadow: 7px 5px 5px 0 rgba(0, 0, 0, 0.2);


}

span {
  background-color: #fdd1e0;
  padding: 10px;
  margin-right: 10px;
  border-radius: 10px;
  box-shadow: 2px 2px 5px 0 rgba(0, 0, 0, 0.2);

}
</style>