<template>
  <nav class="bg-zinc-900 p-4 fixed top-0 left-0 w-full z-50">
    <ul class="flex justify-end space-x-4">
      <li><router-link to="/" class="text-black hover:underline">Home</router-link></li>
      <li><router-link to="/about" class="text-white hover:underline">About</router-link></li>
      <li><router-link to="/projects" class="text-white hover:underline">Projects</router-link></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavbarView',
}
</script>

<style scoped>
nav {
  z-index: 50;
}
</style>
