<script setup lang="ts">
useHead({
  title: "Seungpyo's Portfolio",
  meta: [
    { name: 'description', content: 'My amazing site.' }
  ],
})
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<style>
@font-face {
  font-family: 'SUIT Variable';
  font-weight: 100 900;
  src: url('/fonts/SUIT-Variable.woff2') format('woff2-variations');
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'SUIT Variable', sans-serif;
}

html {
  scroll-behavior: smooth;
}

h1 {
  font-size: 2rem;
  color: black;
  transition: color 0.3s;
}

h2 {
  font-size: 1.5rem;
  color: black;
  transition: color 0.3s;
}

h3 {
  font-size: 1.2rem;
  color: black;
  transition: color 0.3s;
}

p {
  font-size: 1.2rem;
  color: black;
  transition: color 0.3s;
}

.dark * {
  color: white;
}

</style>
