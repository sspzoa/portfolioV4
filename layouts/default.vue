<script setup lang="ts">

</script>

<template>
  <div class="rootContainer">
    <Navbar />
    <slot />
    <Footer />
  </div>
</template>

<style scoped>
.rootContainer {
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>
