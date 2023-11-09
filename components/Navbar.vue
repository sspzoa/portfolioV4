<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';

const isDarkMode = ref(false);
const showMenu = ref(false); // 메뉴 상태를 위한 반응형 변수

const buttonText = computed(() => isDarkMode.value ? 'Light Mode' : 'Dark Mode');

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

const toggleMenu = () => {
  showMenu.value = !showMenu.value;
};

onMounted(() => {
  const savedMode = localStorage.getItem('darkMode');
  if (savedMode === 'true') {
    isDarkMode.value = true;
    document.documentElement.setAttribute('data-theme', 'dark');
  }
});
</script>

<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
  <div class="navbarContainer">
    <div class="navbar">
      <div class="left">
        <NuxtLink style="text-decoration: none; color: inherit;" to="/" class="logo">
          <img src="/images/intro/sspzoa.png" alt="logo" />
          <h2>Portfolio</h2>
        </NuxtLink>
      </div>
      <div class="hamburger" @click="toggleMenu">
        <i class="fas fa-burger"></i>
      </div>
      <div class="items" v-show="!showMenu">
        <NuxtLink style="text-decoration: none; color: inherit;" to="/"><p>Home</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#about"><p>About</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#skills"><p>Skills</p></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#projects"><p>Projects</p></NuxtLink>
      </div>
      <div class="right" v-show="!showMenu">
        <button class="themeButton" @click="toggleDarkMode">
          {{ buttonText }}
        </button>
      </div>
      <div class="menu" :class="{ 'active': showMenu }">
        <NuxtLink style="text-decoration: none; color: inherit;" to="/" @click="toggleMenu"><h2>Home</h2></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#about" @click="toggleMenu"><h2>About</h2></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#skills" @click="toggleMenu"><h2>Skills</h2></NuxtLink>
        <NuxtLink style="text-decoration: none; color: inherit;" to="/#projects" @click="toggleMenu"><h2>Projects</h2></NuxtLink>
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

i {
  color: var(--text-color);
  font-size: 1.5rem;
}

.themeButton {
  width: 6.5rem;
  border: none;
  background-color: var(--transparent-point);
  color: var(--text-color);
  padding: 0.5rem 1rem;
  border-radius: 0.3rem;
}

.hamburger {
  cursor: pointer;
  display: none;
  flex-direction: column;
  justify-content: space-around;
  height: 2rem;
  z-index: 20;
}

.menu {
  display: none;
  gap: 1rem;
  flex-direction: column;
  padding: 1rem;
  position: fixed;
  top: 0;
  right: -100%;
  width: 60%;
  height: 100vh;
  background-color: var(--background-color);
  border-left: var(--transparent-point) 1px solid;
  transition: right 0.3s, background-color 0.3s;
  padding-top: 3rem;
}

.menu.active {
  right: 0;
}

@media (max-width: 768px) {
  .navbarContainer {
    padding: 0.8rem;
  }

  .hamburger {
    display: flex;
  }

  .items,
  .right {
    display: none;
  }

  .menu {
    display: flex;
  }
}
</style>
