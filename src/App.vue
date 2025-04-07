<template>
  <section class="home">
    <NavbarView />
    <router-view />
  </section>
</template>

<script setup>
import NavbarView from '@/components/layout/NavbarView.vue'
</script>

<style scoped>
.home {
  text-align: center;
  padding: 2rem;
}

.home h1 {
  font-size: 2.5rem;
  color: #42b983;
}

.home p {
  margin: 1rem 0;
  font-size: 1.2rem;
}

button {
  background-color: #42b983;
  border: none;
  padding: 0.75rem 1.5rem;
  color: white;
  font-size: 1rem;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #369870;
}
</style>
