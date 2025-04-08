<template>
  <section class="home">
    <NavbarView />
    <transition name="fade" @before-enter="beforeEnter" @enter="enter" @leave="leave">
      <router-view />
    </transition>
  </section>
</template>

<script setup>
import NavbarView from '@/components/layout/NavbarView.vue'
</script>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Home',
  methods: {
    beforeEnter(el) {
      el.style.opacity = 0
    },
    enter(el, done) {
      el.offsetHeight
      el.style.transition = 'opacity 1s ease'
      el.style.opacity = 1
      done()
    },
    leave(el, done) {
      el.style.transition = 'opacity 1s ease'
      el.style.opacity = 0
      done()
    },
  },
}
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

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
