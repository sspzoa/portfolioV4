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
  transition: background-color 0.3s, color 0.3s;
}

html {
  scroll-behavior: smooth;
}

:root {
  --background-color: whitesmoke;
  --text-color: black;
  --point-text: white;
  --box-color: white;
  --link-color: darkblue;
  --point-main: black;
  --point-sub: lightgrey;
  --point-sub2: grey;
  --transparent-main: rgba(245, 245, 245, 0.5);
  --transparent-point: rgba(0, 0, 0, 0.1);
}

[data-theme="dark"] {
  --background-color: black;
  --text-color: white;
  --point-text: black;
  --box-color: #333;
  --link-color: dodgerblue;
  --point-main: white;
  --point-sub: grey;
  --point-sub2: lightgrey;
  --transparent-main: rgba(0, 0, 0, 0.5);
  --transparent-point: rgba(255, 255, 255, 0.2);
}


h1 {
  font-size: 2rem;
  color: var(--text-color);
}

h2 {
  font-size: 1.5rem;
  color: var(--text-color);
}

h3 {
  font-size: 1.2rem;
  color: var(--text-color);
}

p {
  font-size: 1.2rem;
  color: var(--text-color);
}
</style>
