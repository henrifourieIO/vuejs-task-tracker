<template>
  <button class="btn" @click="onClick()" :style="{ background: color }">
    {{ label }}
  </button>
</template>

<script>
export default {
  name: "Button",
  // PROPS
  props: {
    label: {
      type: String,
      default: "Add Task",
    },
    color: {
      type: String,
      default: "#000",
    },
  },

  // METHODS
  methods: {
    onClick() {
      console.log("click");
    },
  },
};
</script>

<style>
.btn {
  border: 0;
  border-radius: 6px;
  color: #fff;
  font-weight: bold;
  padding: 1em;
  min-width: 80px;
  transition: 300ms ease-out;
}

.btn-submit {
  width: 100%;
  background: #000;
}
</style>
