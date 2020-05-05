<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <a href="/signup">Signup</a> or
    <router-link to="/signup">Signup</router-link>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Studen Access",
    };
  },
  created: function() {},
  methods: {},
};
</script>