<template>
  <div class="bg-slate-800/80 backdrop-blur-sm rounded-xl shadow-md p-6 hover:shadow-lg transition-all border border-slate-700/50">
    <div class="text-4xl mb-4 bg-gradient-to-br from-slate-700 to-slate-600 w-12 h-12 rounded-lg flex items-center justify-center">
      {{ icon }}
    </div>
    <h3 class="text-xl font-semibold mb-2 bg-gradient-to-r from-violet-400 to-cyan-400 text-transparent bg-clip-text">
      {{ title }}
    </h3>
    <p class="text-gray-300">{{ description }}</p>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string;
  description: string;
  icon: string;
}>();
</script>