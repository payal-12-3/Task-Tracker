<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>
<script>
export default {
  name: 'Task',
  props: {
    task: Object,
  },
}
</script>
<style scoped>
.fas {
  color: red;
}
.task {
  background: rgb(219, 219, 219);
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid lightgreen;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
