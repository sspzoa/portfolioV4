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
        <img :id="`${project.name.toLowerCase()}`" :src="`/images/projects/${project.image}`"/>
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
  padding: 6rem 0;
}

.projects {
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.project {
  width: 22.666rem;
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
  background-color: white;
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
</style>
