<template>
  <div class="tasksWrapper">
    <Task
      v-for="task in tasks"
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      :key="task.id"
      :id="task.id"
      :text="task.text"
      :day="task.day"
      :reminder="task.reminder"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
};
</script>

<style>
.tasksWrapper {
  display: flex;
  flex-direction: column;
  gap: 0.3em;
}
</style>
