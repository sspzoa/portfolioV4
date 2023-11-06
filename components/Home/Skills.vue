<script setup lang="ts">

</script>

<template>
  <div id="skills" class="skillsContainer">
    <h1>My skills</h1>
    <div class="box">
      <img src="/assets/images/skills/flutter.png" />
      <img src="/assets/images/skills/reactnative.svg" />
      <img src="/assets/images/skills/android.png" />
      <img src="/assets/images/skills/nextjs.png" />
      <img src="/assets/images/skills/nuxt.png" />
      <img src="/assets/images/skills/flask.png" />
      <img src="/assets/images/skills/pytorch.png" />
      <img src="/assets/images/skills/docker.png" />
      <img src="/assets/images/skills/aws.png" />
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
  background-color: white;
  justify-items: center;
  align-items: center;
  width: 100%;
}

.box img {
  max-width: 15rem;
  max-height: 5rem;
}

</style>
