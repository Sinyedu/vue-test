<template>
  <div class="flex flex-col items-center justify-start bg-zinc-800">
    <PersonalWelcomeCard :name="'Simon Erik Nyblom'" :image="'/Simon.jpg'" />

    <TechStackCard />

    <AboutMeCard />
  </div>
</template>

<script setup>
import PersonalWelcomeCard from '../components/PersonalWelcomeCard.vue'
import TechStackCard from '../components/TechStackCard.vue'
import AboutMeCard from '../components/AboutMeCard.vue'
</script>

<style scoped></style>
