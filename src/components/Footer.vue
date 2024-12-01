<script setup lang="ts">
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="bg-gray-900 text-white py-8">
    <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col items-center space-y-6">
        <p class="text-sm font-medium text-gray-400">
          Copyright © {{ currentYear }} Nyoman Baihaqie Putra
        </p>
      </div>
    </div>
  </footer>
</template>
