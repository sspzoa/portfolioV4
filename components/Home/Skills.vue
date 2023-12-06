<script setup lang="ts">

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
      <img src="/images/skills/firebase.svg" />
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
  padding: 8rem 0;
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
    gap: 2rem 1rem;
  }
  .box {
    grid-template-columns: repeat(2, 1fr);
    padding: 2rem;
    grid-gap: 2rem;
    border-radius: 0.5rem;
  }
  .box img {
    max-width: 8rem;
  }
}
</style>
