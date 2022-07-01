<template>
  <div
    :class="[reminder ? 'reminder' : '', 'task']"
    @dblclick="$emit('toggle-reminder', id)"
  >
    <h3>
      <span>{{ text }}</span>
      <i @click="$emit('delete-task', id)" class="fas fa-times" />
    </h3>
    <small>{{ day }}</small>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    id: Number,
    text: String,
    day: String,
    reminder: Boolean,
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
};
</script>

<style scoped>
.task {
  background-color: #fafafa;
  border-radius: 3px;
  padding: 0.5em;
  box-shadow: 0px 0px 0px 0px rgba(0, 0, 0, 0);
  transform: translateY(0px) scale(1);
  transition: 200ms ease-in-out;
  cursor: default;
  border-left: 4px solid transparent;
  user-select: none;
}

h3 {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 i {
  font-size: 0.85em;
  cursor: pointer;
  transition: 300ms ease-out;
}

h3 i:hover {
  color: red;
}

small {
  font-weight: 100;
  color: #777;
  text-transform: uppercase;
}

.task:hover {
  transform: translateY(-3px) scale(1.01);
  box-shadow: 0px 4px 6px -4px rgba(0, 0, 0, 0.3);
}

.task.reminder {
  border-color: green;
}
</style>
