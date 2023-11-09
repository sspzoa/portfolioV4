<script setup lang="ts">
</script>

<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
  <div class="footerContainer">
    <div class="icons">
      <NuxtLink to="mailto:sspzoa@duck.com"><i class="far fa-envelope"></i></NuxtLink>
      <NuxtLink to="https://github.com/sspzoa"><i class="fab fa-github"></i></NuxtLink>
      <NuxtLink to="https://www.instagram.com/_s._.pyo/"><i class="fab fa-instagram"></i></NuxtLink>
      <NuxtLink to="#"><i class="fab fa-linkedin"></i></NuxtLink>
    </div>
    <h3>© 2023 Seungpyo Suh. All rights reserved.</h3>
  </div>
</template>

<style scoped>
.footerContainer {
  display: flex;
  width: 100%;
  padding: 2rem;
  border-top: var(--transparent-point) 1px solid;
  flex-direction: column;
  gap: 1.5rem;
  justify-content: center;
  align-items: center;
}

.footerContainer h3 {
  color: var(--point-sub);
  text-align: center;
}

.icons {
  display: flex;
  flex-direction: row;
  gap: 1.2rem;
}

.icons i {
  font-size: 2.5rem;
  color: var(--point-sub);
  transition: transform 0.1s ease-in-out, color 0.3s;
}

.icons i:hover {
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .footerContainer {
    padding: 1.5rem;
    gap: 0.5rem;
  }
  .icons {
    gap: 0.8rem;
  }
  .icons i {
    font-size: 1.5rem;
  }
}
</style>
