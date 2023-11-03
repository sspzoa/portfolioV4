<script setup lang="ts">
</script>

<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
  <div class="footerContainer">
    <div class="icons">
      <NuxtLink to="https://github.com/sspzoa"><i class="fab fa-github"></i></NuxtLink>
      <NuxtLink to="https://www.instagram.com/_s._.pyo/"><i class="fab fa-instagram"></i></NuxtLink>
    </div>
    <h3>© 2023 Seungpyo Suh. All rights reserved.</h3>
  </div>
</template>

<style scoped>
.footerContainer {
  display: flex;
  width: 100%;
  padding: 30px;
  border-top: rgba(0, 0, 0, 0.1) 1px solid;
  flex-direction: column;
  gap: 20px;
  justify-content: center;
  align-items: center;
}

.footerContainer h3 {
  color: grey;
  text-align: center;
  margin: 0;
}

.icons {
  display: flex;
  flex-direction: row;
  gap: 15px;
}

.icons i {
  font-size: 2.5rem;
  color: grey;
}
</style>
