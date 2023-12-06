<template>
  <div class="container">
    <div ref="introRef" class="fade-section"><Intro /></div>
    <div ref="aboutRef" class="fade-section"><About /></div>
    <div ref="skillsRef" class="fade-section"><Skills /></div>
    <div ref="projectsRef" class="fade-section"><Projects /></div>
  </div>
</template>

<script lang="ts" setup>
import { onMounted, ref } from 'vue';
import Intro from '~/components/Home/Intro.vue';
import About from '~/components/Home/About.vue';
import Skills from '~/components/Home/Skills.vue';
import Projects from '~/components/Home/Projects.vue';

const introRef = ref<HTMLElement | null>(null);
const aboutRef = ref<HTMLElement | null>(null);
const skillsRef = ref<HTMLElement | null>(null);
const projectsRef = ref<HTMLElement | null>(null);

onMounted(() => {
  const elements = [introRef.value, aboutRef.value, skillsRef.value, projectsRef.value];
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('fade-in');
      }
    });
  }, { threshold: 0.8 });

  elements.forEach(el => {
    if (el) observer.observe(el);
  });
});
</script>

<style scoped>
.container {
  max-width: 70rem;
  width: 100%;
}

.fade-section {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 1s ease-out, transform 1s ease-out;
}

.fade-in {
  opacity: 1;
  transform: translateY(0);
}
</style>
