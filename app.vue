<template>
  <div class="bg-gradient-to-br from-slate-800 via-slate-900 to-slate-950">
    <Navigation />
    <NuxtPage />
  </div>
</template>
<style>
html {
  scroll-behavior: smooth;
}

@keyframes highlight-section {
  0%, 100% {
    background-color: rgb(30 41 59 / 0.8);
  }
  50% {
    background-color: rgba(69, 95, 131, 0.9);
  }
}

.section-highlight {
  animation: highlight-section 2s ease-in-out;
}
</style>