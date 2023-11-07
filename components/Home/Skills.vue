<script setup lang="ts">

</script>

<template>
  <div id="skills" class="skillsContainer">
    <h1>My skills</h1>
    <div class="box">
      <img src="/images/skills/flutter.png" />
      <img id="rn" src="/images/skills/reactnative.svg" />
      <img src="/images/skills/jetpackcompose.webp" />
      <img src="/images/skills/nextjs.png" />
      <img src="/images/skills/nuxt.png" />
      <img src="/images/skills/flask.png" />
      <img src="/images/skills/springboot.png" />
      <img src="/images/skills/docker.png" />
      <img id="aws" src="/images/skills/aws.png" />
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
}

#rn {
  max-width: 20rem;
}

#aws {
  max-width: 10rem;
}


</style>
