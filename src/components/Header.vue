<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      :label="viewAddTasks ? 'Close' : 'Add Task'"
      :color="viewAddTasks ? 'red' : '#000'"
      @click="onClick"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Header",
  props: {
    title: String,
    viewAddTasks: Boolean,
  },
  components: {
    Button,
  },
  methods: {
    onClick() {
      this.$emit("toggle-add-task");
    },
  },
  computed: {
    homePage() {
      if(this.$route.path === '/') {
        return true
      } else {
        return false
      }
    }
  }
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

header h1 {
  font-weight: normal;
}
</style>
