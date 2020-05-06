<template>
  <div class="home">
    <h1>Update your resume:</h1>
    <h1>Experience</h1>
    <!-- <div v-for="resume in resumes"> -->
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
      Description:
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
  <!-- </div> -->
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      experience: "",
      education: "",
      project: "",
      skill: "",
    };
  },
  created: function() {},
  methods: {
    updateResume: function(resume) {
      var params = {
        start_date: resume.experience.start_date,
        end_date: resume.experience.end_date,
        job_title: resume.experience.job_title,
        company_name: resume.experience.company_name,
        details: resume.experience.details,
        start_date: resume.education.start_date,
        end_date: resume.education.end_date,
        degree: resume.education.degree,
        university_name: resume.education.university_name,
        details: resume.education.details,
        name: resume.project.name,
        description: resume.project.name,
        url: resume.project.url,
        screenshot: resume.project.screenshot,
        skill_name: resume.education.skill_name,
      };
      axios.patch("/api/resumes/" + resume.id, params).then(response => {
        this.currentResume = {};
      });
    },
  },
};
</script> 