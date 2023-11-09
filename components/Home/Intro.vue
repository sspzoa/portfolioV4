<script setup lang="ts">
</script>

<template>
  <div class="introContainer">
    <div class="textBox">
      <h1>Hello,<br/>I&apos;m Seungpyo Suh</h1>
      <p>I&apos;m a frontend engineer,<br/>proficient in using Android,<br/>learning to make cross-platform apps.</p>
    </div>
    <NuxtLink to="#about"><img class="arrow" src="/images/intro/arrow.svg"/></NuxtLink>
    <img class="logo" src="/images/intro/sspzoa.png"/>
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

@media (max-width: 768px) {
  .introContainer {
    flex-direction: column;
    justify-content: center;
    gap: 2rem;
    padding: 1rem;
  }

  .textBox h1 {
    font-size: 2rem;
  }

  .textBox {
    align-self: flex-start;
    gap: 1rem;
  }

  .logo {
    width: 8rem;
    margin-right: 1rem;
    align-self: flex-end;
    border-radius: 1rem;
    box-shadow: 2rem -2rem 5rem rgba(85, 102, 119, 0.8);
  }

  .arrow {
    width: 5rem;
  }
}
</style>
