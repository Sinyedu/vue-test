<template>
  <div class="p-6">
    <h1 class="text-2xl font-bold mb-4">My Projects</h1>
    <ul>
      <li
        v-for="project in projects"
        :key="project.id"
        class="mb-4 border border-gray-100 p-4 rounded-lg shadow-sm"
      >
        <h2 class="text-xl font-semibold mb-2">{{ project.title }}</h2>
        <p class="mb-2">{{ project.description }}</p>
        <p class="mb-2"><strong>Technologies:</strong> {{ project.technologies.join(', ') }}</p>
        <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          class="text-blue-500 hover:underline"
        >
          View Project
        </a>
      </li>
    </ul>
    <p v-if="loading" class="text-gray-500">Loading projects...</p>
    <p v-if="error" class="text-red-500">{{ error }}</p>
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

<style scoped></style>
