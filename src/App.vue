<template>
  <div class="container">
    <Header
      title="Task Tracker"
      :viewAddTasks="viewAddTasks"
      @toggle-add-task="toggleAddTask"
    />
    <AddTask v-show="viewAddTasks" @add-task="addTask" />
    <router-view :viewAddTasks="viewAddTasks"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      tasks: [],
      viewAddTasks: false,
    };
  },
  methods: {
    toggleAddTask() {
      this.viewAddTasks = !this.viewAddTasks;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Anek+Latin:wght@300;400;700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body,
button {
  font-family: "Anek Latin", sans-serif;
}

.container {
  margin: 2em auto;
  padding: 1em 1em;
  border: 1px solid black;
  border-radius: 15px;
  max-width: 425px;
  width: calc(100% - 3.5em);
}
</style>
