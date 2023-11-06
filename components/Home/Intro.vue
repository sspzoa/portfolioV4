<script setup lang="ts">
</script>

<template>
<div class="introContainer">
  <div class="textBox">
    <h1>Hello,<br />I&apos;m Seungpyo Suh</h1>
    <p>I&apos;m a software engineer,<br />proficient in using Android,<br />learning to make cross-platform apps.</p>
  </div>
  <NuxtLink to="#about"><img class="arrow" src="/assets/images/intro/arrow.svg" /></NuxtLink>
  <img class="logo" src="/assets/images/intro/sspzoa.png" />
</div>
</template>

<style scoped>
.introContainer {
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.textBox {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.textBox h1 {
  font-size: 4rem;
  font-weight: 800;
}

.logo {
  width: 15rem;
  border-radius: 2rem;
  box-shadow: 3rem -3rem 5rem rgba(85, 102, 119, 0.8);
}

.arrow {
  height: 1.5rem;
  position: absolute;
  display: flex;
  flex-direction: column;
  bottom: 3rem;
  left: 50%;
  transform: translateX(-50%);
  transition: transform 0.1s ease-in-out;
  text-decoration: none;
  gap: 1rem;
}

.arrow:hover {
  transform: scale(1.1) translateX(-45%);
}
</style>
