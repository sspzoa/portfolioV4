<script setup lang="ts">
import { ref } from 'vue';
import projectsData from '~/src/assets/data/projects.json';

interface Project {
  name: string;
  date: string;
  teamSize: string;
  description: string;
  githubLink: string;
  tags: string[];
  image: string
}

const projects = ref<Project[]>(projectsData);
</script>

<template>
  <div id="projects" class="projectsContainer">
    <h1>My projects</h1>
    <div class="projects">
      <div class="project" v-for="project in projects" :key="project.name">
        <img :id="`${project.name.toLowerCase()}`" :src="`/images/projects/${project.image}`" />
        <div class="textBox">
          <div class="title">
            <h1>{{ project.name }}</h1>
            <p>{{ project.date }} / {{ project.teamSize }}</p>
          </div>
          <h3>{{ project.description }}</h3>
          <NuxtLink style="text-decoration: none; color: inherit;" :to="`https://github.com/${project.githubLink}`">
            <h2>{{ project.githubLink }}</h2>
          </NuxtLink>
          <div class="tags">
            <div class="tag" v-for="tag in project.tags" :key="tag">
              {{ tag }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.projectsContainer {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 2rem;
  padding: 8rem 0;
}

.projects {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}

.project {
  display: flex;
  flex-direction: column;
  width: 100%;
  background-color: var(--box-color);
  border-radius: 1rem;
}

.textBox {
  padding: 1rem;
}

.title {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1rem;
}

.project h1 {
  font-size: 1.5rem;
}

.project h2 {
  font-size: 1rem;
  line-height: 1.5rem;
  color: var(--link-color);
}

.project h3 {
  font-size: 1rem;
  line-height: 1.5;
}

.project p {
  font-size: 1rem;
}

.project img {
  background-color: whitesmoke;
  width: 100%;
  height: 10rem;
  object-fit: contain;
  padding: 3rem 5rem;
  border-top-left-radius: 1rem;
  border-top-right-radius: 1rem;
}

#glud {
  background-color: #92B4CD;
}

#monty {
  background-color: #5D6DBE;
}

.tags {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 1rem;
}

.tag {
  padding: 0.3rem 0.5rem;
  border-radius: 1rem;
  background-color: lightgrey;
  font-size: 1rem;
  line-height: 1.2rem;
  font-weight: 500;
}

.tag:first-child {
  background-color: var(--point-main);
  color: var(--point-text);
}

@media (max-width: 768px) {
  .projectsContainer {
    padding: 5rem 1rem;
    gap: 2rem 1rem;
  }

  .title {
    margin-bottom: 0.5rem;
  }

  .projects {
    grid-gap: 0.5rem;
    grid-template-columns: repeat(1, 1fr);
  }

  .project {
    width: 100%;
    flex-direction: row;
  }

  .project h1 {
    font-size: 0.8rem;
  }

  .project h2 {
    font-size: 0.6rem;
    line-height: 1.2rem;
  }

  .project h3 {
    font-size: 0.6rem;
    line-height: 1.2;
  }

  .project p {
    font-size: 0.6rem;
  }

  .tags {
    margin-top: 0.5rem;
    gap: 0.3rem;
  }

  .tag {
    padding: 0.1rem 0.3rem;
    font-size: 0.6rem;
    line-height: 1rem;
  }

  .project img {
    height: 9rem;
    width: 9rem;
    padding: 2rem;
    border-top-left-radius: 0.5rem;
    border-top-right-radius: 0;
    border-bottom-left-radius: 0.5rem;
  }
}
</style>
