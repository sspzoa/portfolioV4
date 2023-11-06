<script>
export default {
  data() {
    return {
      isDarkMode: false
    };
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
    }
  }
};
</script>

<template>
  <div class="navbarContainer" :class="{ dark: isDarkMode }">
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
        <NuxtLink style="text-decoration: none; color: inherit;" to="#contact"><p>Contact</p></NuxtLink>
      </div>
      <div class="right">
        <button class="themeButton" @click="toggleDarkMode">
          {{ isDarkMode ? 'Light Mode' : 'Dark Mode' }}
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
  background-color: rgba(245, 245, 245, 0.5);
  backdrop-filter: blur(0.5rem);
  padding: 1rem;
  border-bottom: rgba(0, 0, 0, 0.1) 1px solid;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: background-color 0.3s;
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
  transition: transform 0.1s ease-in-out;
}

.items p:hover {
  transform: scale(1.1);
}

.themeButton {
  width: 6.5rem;
  border: none;
  background-color: rgba(0, 0, 0, 0.1);
  padding: 0.5rem 1rem;
  border-radius: 0.3rem;
  transition: background-color 0.3s;
}

.dark {
  background-color: rgba(0, 0, 0, 0.7);
}

.dark .themeButton {
  background-color: rgba(255, 255, 255, 0.1);
}

</style>
