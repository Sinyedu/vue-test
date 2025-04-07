<template>
  <nav class="navbar">
    <ul class="nav-links">
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About</router-link></li>
      <li><router-link to="/projects">Projects</router-link></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavbarView',
}
</script>

<style scoped>
.navbar {
  background-color: #333;
  padding: 1rem;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1rem;
  margin: 0;
  padding: 0;
}

.nav-links li {
  display: inline;
}

.nav-links a {
  color: white;
  text-decoration: none;
}

.nav-links a:hover {
  text-decoration: underline;
}
</style>
