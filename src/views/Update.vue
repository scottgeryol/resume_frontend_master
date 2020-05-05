<template>
  <div class="home">
    <div>{{ message }}</div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      message: "Update your resume!",
    };
  },
  created: function() {},
  methods: {},
};
</script>