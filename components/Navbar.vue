<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';

// Reactive state for dark mode
const isDarkMode = ref(false);

// Computed property for button text
const buttonText = computed(() => isDarkMode.value ? 'Light Mode' : 'Dark Mode');

// Method to toggle dark mode
const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  if (isDarkMode.value) {
    document.documentElement.setAttribute('data-theme', 'dark');
    localStorage.setItem('darkMode', 'true');
  } else {
    document.documentElement.removeAttribute('data-theme');
    localStorage.setItem('darkMode', 'false');
  }
};

// Check for saved user preference on mounted
onMounted(() => {
  const savedMode = localStorage.getItem('darkMode');
  if (savedMode === 'true') {
    isDarkMode.value = true;
    document.documentElement.setAttribute('data-theme', 'dark');
  }
});
</script>


<template>
  <div class="navbarContainer">
    <div class="navbar">
      <div class="left">
        <NuxtLink style="text-decoration: none; color: inherit;" to="/" class="logo">
          <img src="/images/intro/sspzoa.png" />
          <h2>Portfolio</h2>
        </NuxtLink>
      </div>
      <div class="items">
        <NuxtLink style="text-decoration: none; color: inherit;" to="/"><p>Home</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="#about"><p>About</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="#skills"><p>Skills</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="#projects"><p>Projects</p></NuxtLink>
      </div>
      <div class="right">
        <button class="themeButton" @click="toggleDarkMode">
          {{ buttonText }}
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.navbarContainer {
  position: fixed;
  z-index: 10;
  width: 100%;
  background-color: var(--transparent-main);
  backdrop-filter: blur(0.5rem);
  padding: 1rem;
  border-bottom: var(--transparent-point) 1px solid;
  display: flex;
  justify-content: center;
  align-items: center;
}

.navbar {
  width: 100%;
  max-width: 70rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.left, .right {
  flex: 1;
  display: flex;
  align-items: center;
}

.left {
  justify-content: flex-start;
}

.right {
  justify-content: flex-end;
}

.logo {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 0.5rem;
}

.logo img {
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 0.3rem;
}

.items {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.items p {
  transition: transform 0.1s ease-in-out, color 0.3s;
}

.items p:hover {
  transform: scale(1.1);
}

.themeButton {
  width: 6.5rem;
  border: none;
  background-color: var(--transparent-point);
  color: var(--text-color);
  padding: 0.5rem 1rem;
  border-radius: 0.3rem;
}
</style>
