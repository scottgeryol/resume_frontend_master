<template>
  <div class="home">
    <h1>Update your resume:</h1>
    <h1>All Experiences</h1>
    <div>
      Start Date:
      <input type="text" v-model="experience.start_date" />
      End Date:
      <input type="text" v-model="experience.end_date" />
      Job Title:
      <input type="text" v-model="experience.job_title" />
      Company Name:
      <input type="text" v-model="experience.company_name" />
      Details:
      <input type="text" v-model="experience.details" />
    </div>
    <h1>Education</h1>
    <div>
      Start Date:
      <input type="text" v-model="education.start_date" />
      End Date:
      <input type="text" v-model="education.end_date" />
      Degree:
      <input type="text" v-model="education.degree" />
      University:
      <input type="text" v-model="education.university_name" />
      Details:
      <input type="text" v-model="education.details" />
    </div>
    <h1>Projects</h1>
    <div>
      Name:
      <input type="text" v-model="project.name" />
      Description
      <input type="text" v-model="project.description" />
      URL:
      <input type="text" v-model="project.url" />
      Screenshot:
      <input type="text" v-model="project.screenshot" />
    </div>
    <h1>Skills</h1>
    <div>
      <input type="text" v-model="education.skill_name" />
    </div>
    <button v-on:click="updateResume(resume)">Update Resume</button>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      experience: "",
      project: "",
      skill: "",
      education: "",
    };
  },
  created: function() {},
  methods: {
    updateResume: function(resume) {
      var params = {
        start_date: experience.start_date,
        end_date: experience.end_date,
        job_title: experience.job_title,
        company_name: experience.company_name,
        details: experience.details,
      };
      axios.patch("/api/resumes/" + resume.id, params).then(response => {
        this.currentResume = {};
      });
    },
  },
};
</script>