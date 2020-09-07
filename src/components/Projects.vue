<template>
  <section class="project-section" id="projects">
    <v-container>
      <v-row>
        <v-col>
          <h1>Projects</h1>
        </v-col>
      </v-row>
      <v-row class="justify-space-around mb-8 mt-4">
        <v-card v-for="project in projects" v-bind:key="project.name" max-width="350">
          <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"></v-img>
          <v-card-title :href="project.github">{{project.name}}</v-card-title>
          <v-card-subtitle>{{project.desc}}</v-card-subtitle>
          <v-card-actions>
            <v-btn v-for="t in project.tech" v-bind:key="t" text>{{t}}</v-btn>
            <v-spacer></v-spacer>
            <v-btn outlined text :href="project.github" color="primary">Github</v-btn>
          </v-card-actions>
        </v-card>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  data: () => ({
    show: false,
    projects: [
      {
        name: "Java Blogger",
        desc: "A blog website for creating blogs",
        github: "https://github.com/m3da1/blog-site-frontend",
        tech: ["Java", "Vue.js"],
      },
      {
        name: "Web Store",
        desc: "A store site for purchasing stuffs",
        github: "https://github.com/m3da1/vue-web-store",
        tech: ["Vue.js"],
      },
      {
        name: "Job hub",
        desc: "A job recruiting system",
        github: "https://github.com/m3da1/vue-web-store",
        tech: ["Vue.js", "Java", "Spring"],
      },
    ],
  }),
  computed: {
    // capitalize: function (value) {
    //   if (!value) return "";
    //   value = value.toString();
    //   return value.charAt(0).toUpperCase() + value.slice(1).toLowerCase();
    // },
  },
};
</script>

<style scoped>
.project-section {
  background-color: #ffd563;
}
</style>