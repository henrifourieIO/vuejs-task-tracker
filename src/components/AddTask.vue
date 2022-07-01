<template>
  <form class="add-form" @submit="onSubmit">
    <div class="form-control">
      <label>Task</label>
      <input type="text" name="text" v-model="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input
        type="text"
        name="day"
        v-model="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" name="reminder" v-model="reminder" />
    </div>
    <input type="submit" value="Save Task" class="btn btn-submit" />
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      // Validation
      if (!this.text) {
        alert("Please add a task");
        return;
      }

      // Model
      const newTask = {
        // id: Math.floor(Math.random() * 100000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      // Submit
      this.$emit("add-task", newTask);

      // Reset Data
      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>

<style>
.add-form {
  max-width: 400px;
  margin-bottom: 1.5em;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  gap: 1em;
}

.form-control {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
}

.form-control label {
  font-weight: 800;
}

.form-control input {
  width: 100%;
  max-width: none;
  margin-top: 5px;
  padding: 0.5em 0.6em;
  border-radius: 3px;
  border: 1px solid #bbb;
}

.form-control.form-control-check {
  flex-direction: row;
  align-items: center;
}

.form-control.form-control-check input {
  width: auto;
  margin-left: 1em;
}
</style>
