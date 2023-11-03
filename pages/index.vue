<script setup lang="ts">
import Intro from "~/components/Home/Intro.vue";
import About from "~/components/Home/About.vue";
import Skills from "~/components/Home/Skills.vue";
import Projects from "~/components/Home/Projects.vue";
import Contact from "~/components/Home/Contact.vue";
</script>

<template>
  <div class="container">
    <Intro />
    <About />
    <Skills />
    <Projects />
    <Contact />
  </div>
</template>

<style scoped>
.container {
  max-width: 70rem;
  width: 100%;
}
</style>
