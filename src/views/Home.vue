<template>
  <div class="home">
    <a href="/login">Login</a>
    |
    <a href="/logout">Logout</a>
    |
    <a href="/show">View Resume</a>
    |
    <a href="/update">Update Resume</a>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      message: "Student Access",
    };
  },
  created: function() {},
  methods: {},
};
</script>