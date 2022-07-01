<template>
  <div class="footer">
    <p>Copyright © 2022</p>
    <div class="nav">
      <router-link to="/about">About</router-link>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Footer'
  }
</script>

<style>
  .footer {
    margin-top: 2em;
    text-align: center;
  }
  .footer .nav {
    padding-top: 0.6em;
  }
</style>