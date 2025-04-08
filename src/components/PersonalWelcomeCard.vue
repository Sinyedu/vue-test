<template>
  <div class="flex items-center justify-start p-6 space-x-8 w-full">
    <div class="w-32 h-32 rounded-md overflow-hidden border-4 border-indigo-600">
      <img :src="image" alt="Your Picture" class="w-32 h-32 object-cover" />
    </div>
    <div class="text-left">
      <h1 class="text-4xl font-bold text-indigo-600 mb-4">Welcome to My Personal Website</h1>
      <p class="text-lg text-gray-700">
        Hey, I'm {{ name }}, and I'm a Frontend Developer specializing in:
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  name: String,
  image: String,
})
</script>

<style scoped></style>
