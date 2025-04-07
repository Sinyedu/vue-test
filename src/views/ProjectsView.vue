<template>
  <div>
    <h1 class="spurgt">My Projects</h1>
    <ul>
      <li v-for="project in projects" :key="project.id">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <p><strong>Technologies:</strong> {{ project.technologies.join(', ') }}</p>
        <a :href="project.link" target="_blank" rel="noopener noreferrer">View Project</a>
      </li>
    </ul>
    <p v-if="loading">Loading projects...</p>
    <p v-if="error">{{ error }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const projects = ref([])
const loading = ref(true)
const error = ref(null)

onMounted(async () => {
  try {
    const response = await fetch('/portfolio.json')
    if (!response.ok) {
      throw new Error('Failed to fetch projects')
    }
    projects.value = await response.json()
  } catch (err) {
    error.value = 'Failed to load projects.'
    console.error(err)
  } finally {
    loading.value = false
  }
})
</script>

<style lang="scss" scoped>
h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 1rem 0;
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
}

h2 {
  font-size: 1.5rem;
  margin: 0 0 0.5rem;
}

p {
  margin: 0.5rem 0;
}

a {
  color: #007bff;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
</style>
