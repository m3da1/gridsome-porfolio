<template>
  <Layout>
    <About></About>
    <Projects></Projects>
    <Education></Education>
    <Contact></Contact>
  </Layout>
</template>

<script>
import About from "@/components/About.vue";
import Contact from "@/components/Contact.vue";
import Education from "@/components/Education.vue";
import Projects from "@/components/Projects.vue";
export default {
  metaInfo: {
    title: "Index",
  },
  components: {
    About,
    Contact,
    Education,
    Projects,
  },
};
</script>

<style>
</style>
