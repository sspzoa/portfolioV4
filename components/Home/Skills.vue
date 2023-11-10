<script setup lang="ts">

import Projects from "~/components/Home/Projects.vue";
</script>

<template>
  <div id="skills" class="skillsContainer">
    <h1>My skills</h1>
    <div class="box">
      <img src="/images/skills/flutter.svg" />
      <img src="/images/skills/android.svg" />
      <img src="/images/skills/kotlin.svg" />
      <img src="/images/skills/next.svg" />
      <img src="/images/skills/nuxt.svg" />
      <img src="/images/skills/spring.svg" />
      <img src="/images/skills/mongodb.svg" />
      <img src="/images/skills/docker.svg" />
      <img src="/images/skills/aws.svg" />
    </div>
  </div>
</template>

<style scoped>
.skillsContainer {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 2rem;
  padding: 6rem 0;
}

.box {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 3rem;
  padding: 5rem 6rem;
  border-radius: 1rem;
  background-color: whitesmoke;
  justify-items: center;
  align-items: center;
  width: 100%;
}

.box img {
  max-width: 15rem;
  max-height: 5rem;
}

@media (max-width: 768px) {
  .skillsContainer {
    padding: 5rem 1rem;
    gap: 1rem;
  }
  .box {
    grid-template-columns: repeat(2, 1fr);
    padding: 2rem;
    grid-gap: 2rem;
    border-radius: 0.5rem;
  }
  .box img {
    max-width: 8rem;
    max-height: 3rem;
  }
}
</style>
